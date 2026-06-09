# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180008394`
- end: `0x18000844f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b10`

## callees

- `0x180006a78`
- `0x180008394`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800083ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800083ea`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180008394  mov     [rsp+arg_0], rbx
0x180008399  push    rdi
0x18000839a  sub     rsp, 20h
0x18000839e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800083a5  xor     ebx, ebx
0x1800083a7  test    rdi, rdi
0x1800083aa  jz      short loc_18000842A
0x1800083ac  cmp     [rdi+8], rbx
0x1800083b0  jnz     short loc_1800083D7
0x1800083b2  mov     rcx, [rdi]
0x1800083b5  lea     rdx, [rsp+28h+arg_8]
0x1800083ba  mov     [rsp+28h+arg_8], rbx
0x1800083bf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800083c4  test    eax, eax
0x1800083c6  js      short loc_1800083D7
0x1800083c8  cmp     [rdi+8], rbx
0x1800083cc  jnz     short loc_1800083D7
0x1800083ce  mov     rax, [rsp+28h+arg_8]
0x1800083d3  mov     [rdi+8], rax
0x1800083d7  mov     rax, [rdi+8]
0x1800083db  lea     rcx, [rax+20h]
0x1800083df  neg     rax
0x1800083e2  sbb     rdi, rdi
0x1800083e5  and     rdi, rcx
0x1800083e8  jz      short loc_18000842A
0x1800083ea  call    cs:__imp_GetCurrentThreadId
0x1800083f0  mov     r8d, eax
0x1800083f3  mov     r9d, eax
0x1800083f6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008400  shr     r8, 2
0x180008404  mul     r8
0x180008407  shr     rdx, 3
0x18000840b  lea     rcx, [rdx+rdx*4]
0x18000840f  add     rcx, rcx
0x180008412  sub     r8, rcx
0x180008415  mov     rbx, [rdi+r8*8+8]
0x18000841a  jmp     short loc_180008425
0x18000841c  cmp     [rbx], r9d
0x18000841f  jz      short loc_180008438
0x180008421  mov     rbx, [rbx+8]
0x180008425  test    rbx, rbx
0x180008428  jnz     short loc_18000841C
0x18000842a  mov     rax, rbx
0x18000842d  mov     rbx, [rsp+28h+arg_0]
0x180008432  add     rsp, 20h
0x180008436  pop     rdi
0x180008437  retn
0x180008438  add     rbx, 10h
0x18000843c  jz      short loc_18000842A
0x18000843e  cmp     qword ptr [rbx+8], 0
0x180008443  jnz     short loc_18000842A
0x180008445  lea     rax, [rdi+4]
0x180008449  mov     [rbx+8], rax
0x18000844d  jmp     short loc_18000842A
```
