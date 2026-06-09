# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000c8dc`
- end: `0x18000c97a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c404`
- `0x1800295e8`

## callees

- `0x18000c8dc`
- `0x18000db6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c8ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c8ef`

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
0x18000c8dc  push    rbx
0x18000c8de  push    rbp
0x18000c8df  push    rsi
0x18000c8e0  push    rdi
0x18000c8e1  sub     rsp, 28h
0x18000c8e5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c8ec  mov     bpl, dl
0x18000c8ef  call    cs:__imp_GetCurrentThreadId
0x18000c8f5  mov     ebx, eax
0x18000c8f7  mov     esi, eax
0x18000c8f9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c903  shr     rbx, 2
0x18000c907  mul     rbx
0x18000c90a  shr     rdx, 3
0x18000c90e  lea     rcx, [rdx+rdx*4]
0x18000c912  add     rcx, rcx
0x18000c915  sub     rbx, rcx
0x18000c918  mov     rax, [rdi+rbx*8]
0x18000c91c  test    rax, rax
0x18000c91f  jz      short loc_18000C931
0x18000c921  cmp     [rax], esi
0x18000c923  jz      short loc_18000C92B
0x18000c925  mov     rax, [rax+8]
0x18000c929  jmp     short loc_18000C91C
0x18000c92b  add     rax, 10h
0x18000c92f  jmp     short loc_18000C971
0x18000c931  test    bpl, bpl
0x18000c934  jz      short loc_18000C96F
0x18000c936  mov     edx, 18h; dwBytes
0x18000c93b  xor     ecx, ecx; dwFlags
0x18000c93d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c942  mov     rcx, rax
0x18000c945  test    rax, rax
0x18000c948  jz      short loc_18000C96F
0x18000c94a  mov     [rax], esi
0x18000c94c  xor     eax, eax
0x18000c94e  mov     [rcx+4], eax
0x18000c951  mov     [rcx+8], rax
0x18000c955  mov     [rcx+10h], rax
0x18000c959  mov     rax, [rdi+rbx*8]
0x18000c95d  mov     [rcx+8], rax
0x18000c961  lock cmpxchg [rdi+rbx*8], rcx
0x18000c967  jnz     short loc_18000C959
0x18000c969  lea     rax, [rcx+10h]
0x18000c96d  jmp     short loc_18000C971
0x18000c96f  xor     eax, eax
0x18000c971  add     rsp, 28h
0x18000c975  pop     rdi
0x18000c976  pop     rsi
0x18000c977  pop     rbp
0x18000c978  pop     rbx
0x18000c979  retn
```
