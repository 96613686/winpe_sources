# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d620`
- end: `0x18000d6c3`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `163`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016e40`

## callees

- `0x18000d620`
- `0x18000e7b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d633`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d633`

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
0x18000d620  push    rbx
0x18000d622  push    rbp
0x18000d623  push    rsi
0x18000d624  push    rdi
0x18000d625  sub     rsp, 28h
0x18000d629  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d630  mov     bpl, dl
0x18000d633  call    cs:__imp_GetCurrentThreadId
0x18000d63a  nop     dword ptr [rax+rax+00h]
0x18000d63f  mov     ebx, eax
0x18000d641  mov     esi, eax
0x18000d643  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d64d  shr     rbx, 2
0x18000d651  mul     rbx
0x18000d654  shr     rdx, 3
0x18000d658  lea     rcx, [rdx+rdx*4]
0x18000d65c  add     rcx, rcx
0x18000d65f  sub     rbx, rcx
0x18000d662  mov     rax, [rdi+rbx*8]
0x18000d666  jmp     short loc_18000D670
0x18000d668  cmp     [rax], esi
0x18000d66a  jz      short loc_18000D6B1
0x18000d66c  mov     rax, [rax+8]
0x18000d670  test    rax, rax
0x18000d673  jnz     short loc_18000D668
0x18000d675  test    bpl, bpl
0x18000d678  jz      short loc_18000D6B7
0x18000d67a  lea     edx, [rax+18h]; dwBytes
0x18000d67d  xor     ecx, ecx; dwFlags
0x18000d67f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d684  mov     rcx, rax
0x18000d687  test    rax, rax
0x18000d68a  jz      short loc_18000D6B7
0x18000d68c  mov     [rax], esi
0x18000d68e  xor     eax, eax
0x18000d690  mov     [rcx+4], eax
0x18000d693  mov     [rcx+8], rax
0x18000d697  mov     [rcx+10h], rax
0x18000d69b  mov     rax, [rdi+rbx*8]
0x18000d69f  mov     [rcx+8], rax
0x18000d6a3  lock cmpxchg [rdi+rbx*8], rcx
0x18000d6a9  jnz     short loc_18000D69B
0x18000d6ab  lea     rax, [rcx+10h]
0x18000d6af  jmp     short loc_18000D6B9
0x18000d6b1  add     rax, 10h
0x18000d6b5  jmp     short loc_18000D6B9
0x18000d6b7  xor     eax, eax
0x18000d6b9  add     rsp, 28h
0x18000d6bd  pop     rdi
0x18000d6be  pop     rsi
0x18000d6bf  pop     rbp
0x18000d6c0  pop     rbx
0x18000d6c1  retn
```
