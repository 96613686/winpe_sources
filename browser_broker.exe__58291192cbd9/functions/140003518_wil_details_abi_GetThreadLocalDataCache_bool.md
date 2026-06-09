# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140003518`
- end: `0x1400035d5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ea0`

## callees

- `0x1400029f4`
- `0x140003518`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003572`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003572`

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
0x140003518  mov     [rsp+arg_0], rbx
0x14000351d  push    rdi
0x14000351e  sub     rsp, 20h
0x140003522  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140003529  xor     ebx, ebx
0x14000352b  test    rdi, rdi
0x14000352e  jz      loc_1400035C7
0x140003534  cmp     [rdi+8], rbx
0x140003538  jnz     short loc_14000355F
0x14000353a  mov     rcx, [rdi]
0x14000353d  lea     rdx, [rsp+28h+arg_8]
0x140003542  mov     [rsp+28h+arg_8], rbx
0x140003547  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000354c  test    eax, eax
0x14000354e  js      short loc_14000355F
0x140003550  cmp     [rdi+8], rbx
0x140003554  jnz     short loc_14000355F
0x140003556  mov     rax, [rsp+28h+arg_8]
0x14000355b  mov     [rdi+8], rax
0x14000355f  mov     rax, [rdi+8]
0x140003563  lea     rcx, [rax+20h]
0x140003567  neg     rax
0x14000356a  sbb     rdi, rdi
0x14000356d  and     rdi, rcx
0x140003570  jz      short loc_1400035C7
0x140003572  call    cs:__imp_GetCurrentThreadId
0x140003578  mov     r8d, eax
0x14000357b  mov     r9d, eax
0x14000357e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003588  shr     r8, 2
0x14000358c  mul     r8
0x14000358f  shr     rdx, 3
0x140003593  lea     rcx, [rdx+rdx*4]
0x140003597  add     rcx, rcx
0x14000359a  sub     r8, rcx
0x14000359d  mov     rbx, [rdi+r8*8+8]
0x1400035a2  test    rbx, rbx
0x1400035a5  jz      short loc_1400035C7
0x1400035a7  cmp     [rbx], r9d
0x1400035aa  jz      short loc_1400035B2
0x1400035ac  mov     rbx, [rbx+8]
0x1400035b0  jmp     short loc_1400035A2
0x1400035b2  add     rbx, 10h
0x1400035b6  jz      short loc_1400035C7
0x1400035b8  cmp     qword ptr [rbx+8], 0
0x1400035bd  jnz     short loc_1400035C7
0x1400035bf  lea     rax, [rdi+4]
0x1400035c3  mov     [rbx+8], rax
0x1400035c7  mov     rax, rbx
0x1400035ca  mov     rbx, [rsp+28h+arg_0]
0x1400035cf  add     rsp, 20h
0x1400035d3  pop     rdi
0x1400035d4  retn
```
