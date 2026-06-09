# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800042fc`
- end: `0x180004398`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005860`
- `0x180005f24`
- `0x180007434`
- `0x18000ac94`

## callees

- `0x1800042fc`
- `0x180004b28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000430f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000430f`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rbx
  __int64 i; // rax
  DWORD *v8; // rax
  signed __int64 v9; // rcx
  signed __int64 v10; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v6 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  for ( i = *(_QWORD *)(v2 + 8 * v6); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      return i + 16;
  }
  if ( !a2 )
    return 0;
  v8 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
  v9 = (signed __int64)v8;
  if ( !v8 )
    return 0;
  *v8 = CurrentThreadId;
  v8[1] = 0;
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  do
  {
    v10 = *(_QWORD *)(v2 + 8 * v6);
    *(_QWORD *)(v9 + 8) = v10;
  }
  while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v6), v9, v10) );
  return v9 + 16;
}

```

## disassembly

```asm
0x1800042fc  push    rbx
0x1800042fe  push    rbp
0x1800042ff  push    rsi
0x180004300  push    rdi
0x180004301  sub     rsp, 28h
0x180004305  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000430c  mov     bpl, dl
0x18000430f  call    cs:__imp_GetCurrentThreadId
0x180004315  mov     ebx, eax
0x180004317  mov     esi, eax
0x180004319  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004323  shr     rbx, 2
0x180004327  mul     rbx
0x18000432a  shr     rdx, 3
0x18000432e  lea     rcx, [rdx+rdx*4]
0x180004332  add     rcx, rcx
0x180004335  sub     rbx, rcx
0x180004338  mov     rax, [rdi+rbx*8]
0x18000433c  jmp     short loc_180004346
0x18000433e  cmp     [rax], esi
0x180004340  jz      short loc_180004387
0x180004342  mov     rax, [rax+8]
0x180004346  test    rax, rax
0x180004349  jnz     short loc_18000433E
0x18000434b  test    bpl, bpl
0x18000434e  jz      short loc_18000438D
0x180004350  lea     edx, [rax+18h]; dwBytes
0x180004353  xor     ecx, ecx; dwFlags
0x180004355  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000435a  mov     rcx, rax
0x18000435d  test    rax, rax
0x180004360  jz      short loc_18000438D
0x180004362  mov     [rax], esi
0x180004364  xor     eax, eax
0x180004366  mov     [rcx+4], eax
0x180004369  mov     [rcx+8], rax
0x18000436d  mov     [rcx+10h], rax
0x180004371  mov     rax, [rdi+rbx*8]
0x180004375  mov     [rcx+8], rax
0x180004379  lock cmpxchg [rdi+rbx*8], rcx
0x18000437f  jnz     short loc_180004371
0x180004381  lea     rax, [rcx+10h]
0x180004385  jmp     short loc_18000438F
0x180004387  add     rax, 10h
0x18000438b  jmp     short loc_18000438F
0x18000438d  xor     eax, eax
0x18000438f  add     rsp, 28h
0x180004393  pop     rdi
0x180004394  pop     rsi
0x180004395  pop     rbp
0x180004396  pop     rbx
0x180004397  retn
```
