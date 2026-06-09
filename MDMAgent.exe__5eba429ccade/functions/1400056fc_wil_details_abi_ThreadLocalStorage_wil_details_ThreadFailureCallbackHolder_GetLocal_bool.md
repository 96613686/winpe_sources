# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400056fc`
- end: `0x14000579a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005224`
- `0x140016b48`

## callees

- `0x1400056fc`
- `0x140006568`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000570f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000570f`

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
  DWORD *v9; // rax
  signed __int64 v10; // rcx
  signed __int64 v11; // rax

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
  v9 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
  v10 = (signed __int64)v9;
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v11 = *(_QWORD *)(v2 + 8 * v6);
    *(_QWORD *)(v10 + 8) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v6), v10, v11) );
  return v10 + 16;
}

```

## disassembly

```asm
0x1400056fc  push    rbx
0x1400056fe  push    rbp
0x1400056ff  push    rsi
0x140005700  push    rdi
0x140005701  sub     rsp, 28h
0x140005705  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000570c  mov     bpl, dl
0x14000570f  call    cs:__imp_GetCurrentThreadId
0x140005715  mov     ebx, eax
0x140005717  mov     esi, eax
0x140005719  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005723  shr     rbx, 2
0x140005727  mul     rbx
0x14000572a  shr     rdx, 3
0x14000572e  lea     rcx, [rdx+rdx*4]
0x140005732  add     rcx, rcx
0x140005735  sub     rbx, rcx
0x140005738  mov     rax, [rdi+rbx*8]
0x14000573c  test    rax, rax
0x14000573f  jz      short loc_140005751
0x140005741  cmp     [rax], esi
0x140005743  jz      short loc_14000574B
0x140005745  mov     rax, [rax+8]
0x140005749  jmp     short loc_14000573C
0x14000574b  add     rax, 10h
0x14000574f  jmp     short loc_140005791
0x140005751  test    bpl, bpl
0x140005754  jz      short loc_14000578F
0x140005756  mov     edx, 18h; dwBytes
0x14000575b  xor     ecx, ecx; dwFlags
0x14000575d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005762  mov     rcx, rax
0x140005765  test    rax, rax
0x140005768  jz      short loc_14000578F
0x14000576a  mov     [rax], esi
0x14000576c  xor     eax, eax
0x14000576e  mov     [rcx+4], eax
0x140005771  mov     [rcx+8], rax
0x140005775  mov     [rcx+10h], rax
0x140005779  mov     rax, [rdi+rbx*8]
0x14000577d  mov     [rcx+8], rax
0x140005781  lock cmpxchg [rdi+rbx*8], rcx
0x140005787  jnz     short loc_140005779
0x140005789  lea     rax, [rcx+10h]
0x14000578d  jmp     short loc_140005791
0x14000578f  xor     eax, eax
0x140005791  add     rsp, 28h
0x140005795  pop     rdi
0x140005796  pop     rsi
0x140005797  pop     rbp
0x140005798  pop     rbx
0x140005799  retn
```
