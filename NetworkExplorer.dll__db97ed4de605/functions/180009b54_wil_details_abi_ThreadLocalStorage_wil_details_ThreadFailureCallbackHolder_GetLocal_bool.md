# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180009b54`
- end: `0x180009bf2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009624`
- `0x18000ba30`

## callees

- `0x180009b54`
- `0x18000abec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b67`

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
0x180009b54  push    rbx
0x180009b56  push    rbp
0x180009b57  push    rsi
0x180009b58  push    rdi
0x180009b59  sub     rsp, 28h
0x180009b5d  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009b64  mov     bpl, dl
0x180009b67  call    cs:__imp_GetCurrentThreadId
0x180009b6d  mov     ebx, eax
0x180009b6f  mov     esi, eax
0x180009b71  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009b7b  shr     rbx, 2
0x180009b7f  mul     rbx
0x180009b82  shr     rdx, 3
0x180009b86  lea     rcx, [rdx+rdx*4]
0x180009b8a  add     rcx, rcx
0x180009b8d  sub     rbx, rcx
0x180009b90  mov     rax, [rdi+rbx*8]
0x180009b94  test    rax, rax
0x180009b97  jz      short loc_180009BA9
0x180009b99  cmp     [rax], esi
0x180009b9b  jz      short loc_180009BA3
0x180009b9d  mov     rax, [rax+8]
0x180009ba1  jmp     short loc_180009B94
0x180009ba3  add     rax, 10h
0x180009ba7  jmp     short loc_180009BE9
0x180009ba9  test    bpl, bpl
0x180009bac  jz      short loc_180009BE7
0x180009bae  mov     edx, 18h; dwBytes
0x180009bb3  xor     ecx, ecx; dwFlags
0x180009bb5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009bba  mov     rcx, rax
0x180009bbd  test    rax, rax
0x180009bc0  jz      short loc_180009BE7
0x180009bc2  mov     [rax], esi
0x180009bc4  xor     eax, eax
0x180009bc6  mov     [rcx+4], eax
0x180009bc9  mov     [rcx+8], rax
0x180009bcd  mov     [rcx+10h], rax
0x180009bd1  mov     rax, [rdi+rbx*8]
0x180009bd5  mov     [rcx+8], rax
0x180009bd9  lock cmpxchg [rdi+rbx*8], rcx
0x180009bdf  jnz     short loc_180009BD1
0x180009be1  lea     rax, [rcx+10h]
0x180009be5  jmp     short loc_180009BE9
0x180009be7  xor     eax, eax
0x180009be9  add     rsp, 28h
0x180009bed  pop     rdi
0x180009bee  pop     rsi
0x180009bef  pop     rbp
0x180009bf0  pop     rbx
0x180009bf1  retn
```
