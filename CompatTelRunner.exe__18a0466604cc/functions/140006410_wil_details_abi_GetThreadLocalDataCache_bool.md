# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140006410`
- end: `0x1400064cb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ae0`

## callees

- `0x140004668`
- `0x140006410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006466`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006466`

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
0x140006410  mov     [rsp+arg_0], rbx
0x140006415  push    rdi
0x140006416  sub     rsp, 20h
0x14000641a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140006421  xor     ebx, ebx
0x140006423  test    rdi, rdi
0x140006426  jz      short loc_1400064A6
0x140006428  cmp     [rdi+8], rbx
0x14000642c  jnz     short loc_140006453
0x14000642e  mov     rcx, [rdi]
0x140006431  lea     rdx, [rsp+28h+arg_8]
0x140006436  mov     [rsp+28h+arg_8], rbx
0x14000643b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140006440  test    eax, eax
0x140006442  js      short loc_140006453
0x140006444  cmp     [rdi+8], rbx
0x140006448  jnz     short loc_140006453
0x14000644a  mov     rax, [rsp+28h+arg_8]
0x14000644f  mov     [rdi+8], rax
0x140006453  mov     rax, [rdi+8]
0x140006457  lea     rcx, [rax+20h]
0x14000645b  neg     rax
0x14000645e  sbb     rdi, rdi
0x140006461  and     rdi, rcx
0x140006464  jz      short loc_1400064A6
0x140006466  call    cs:__imp_GetCurrentThreadId
0x14000646c  mov     r8d, eax
0x14000646f  mov     r9d, eax
0x140006472  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000647c  shr     r8, 2
0x140006480  mul     r8
0x140006483  shr     rdx, 3
0x140006487  lea     rcx, [rdx+rdx*4]
0x14000648b  add     rcx, rcx
0x14000648e  sub     r8, rcx
0x140006491  mov     rbx, [rdi+r8*8+8]
0x140006496  jmp     short loc_1400064A1
0x140006498  cmp     [rbx], r9d
0x14000649b  jz      short loc_1400064B4
0x14000649d  mov     rbx, [rbx+8]
0x1400064a1  test    rbx, rbx
0x1400064a4  jnz     short loc_140006498
0x1400064a6  mov     rax, rbx
0x1400064a9  mov     rbx, [rsp+28h+arg_0]
0x1400064ae  add     rsp, 20h
0x1400064b2  pop     rdi
0x1400064b3  retn
0x1400064b4  add     rbx, 10h
0x1400064b8  jz      short loc_1400064A6
0x1400064ba  cmp     qword ptr [rbx+8], 0
0x1400064bf  jnz     short loc_1400064A6
0x1400064c1  lea     rax, [rdi+4]
0x1400064c5  mov     [rbx+8], rax
0x1400064c9  jmp     short loc_1400064A6
```
