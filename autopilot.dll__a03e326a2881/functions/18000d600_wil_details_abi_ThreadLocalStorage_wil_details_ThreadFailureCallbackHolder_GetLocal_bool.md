# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d600`
- end: `0x18000d69c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016838`

## callees

- `0x18000d600`
- `0x18000e6bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d613`

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
0x18000d600  push    rbx
0x18000d602  push    rbp
0x18000d603  push    rsi
0x18000d604  push    rdi
0x18000d605  sub     rsp, 28h
0x18000d609  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d610  mov     bpl, dl
0x18000d613  call    cs:__imp_GetCurrentThreadId
0x18000d619  mov     ebx, eax
0x18000d61b  mov     esi, eax
0x18000d61d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d627  shr     rbx, 2
0x18000d62b  mul     rbx
0x18000d62e  shr     rdx, 3
0x18000d632  lea     rcx, [rdx+rdx*4]
0x18000d636  add     rcx, rcx
0x18000d639  sub     rbx, rcx
0x18000d63c  mov     rax, [rdi+rbx*8]
0x18000d640  jmp     short loc_18000D64A
0x18000d642  cmp     [rax], esi
0x18000d644  jz      short loc_18000D68B
0x18000d646  mov     rax, [rax+8]
0x18000d64a  test    rax, rax
0x18000d64d  jnz     short loc_18000D642
0x18000d64f  test    bpl, bpl
0x18000d652  jz      short loc_18000D691
0x18000d654  lea     edx, [rax+18h]; dwBytes
0x18000d657  xor     ecx, ecx; dwFlags
0x18000d659  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d65e  mov     rcx, rax
0x18000d661  test    rax, rax
0x18000d664  jz      short loc_18000D691
0x18000d666  mov     [rax], esi
0x18000d668  xor     eax, eax
0x18000d66a  mov     [rcx+4], eax
0x18000d66d  mov     [rcx+8], rax
0x18000d671  mov     [rcx+10h], rax
0x18000d675  mov     rax, [rdi+rbx*8]
0x18000d679  mov     [rcx+8], rax
0x18000d67d  lock cmpxchg [rdi+rbx*8], rcx
0x18000d683  jnz     short loc_18000D675
0x18000d685  lea     rax, [rcx+10h]
0x18000d689  jmp     short loc_18000D693
0x18000d68b  add     rax, 10h
0x18000d68f  jmp     short loc_18000D693
0x18000d691  xor     eax, eax
0x18000d693  add     rsp, 28h
0x18000d697  pop     rdi
0x18000d698  pop     rsi
0x18000d699  pop     rbp
0x18000d69a  pop     rbx
0x18000d69b  retn
```
