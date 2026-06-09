# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180020ce0`
- end: `0x180020d7e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020b7c`
- `0x180031204`

## callees

- `0x180020ce0`
- `0x180021290`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020cf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020cf3`

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
0x180020ce0  push    rbx
0x180020ce2  push    rbp
0x180020ce3  push    rsi
0x180020ce4  push    rdi
0x180020ce5  sub     rsp, 28h
0x180020ce9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180020cf0  mov     bpl, dl
0x180020cf3  call    cs:__imp_GetCurrentThreadId
0x180020cf9  mov     ebx, eax
0x180020cfb  mov     esi, eax
0x180020cfd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180020d07  shr     rbx, 2
0x180020d0b  mul     rbx
0x180020d0e  shr     rdx, 3
0x180020d12  lea     rcx, [rdx+rdx*4]
0x180020d16  add     rcx, rcx
0x180020d19  sub     rbx, rcx
0x180020d1c  mov     rax, [rdi+rbx*8]
0x180020d20  test    rax, rax
0x180020d23  jz      short loc_180020D35
0x180020d25  cmp     [rax], esi
0x180020d27  jz      short loc_180020D2F
0x180020d29  mov     rax, [rax+8]
0x180020d2d  jmp     short loc_180020D20
0x180020d2f  add     rax, 10h
0x180020d33  jmp     short loc_180020D75
0x180020d35  test    bpl, bpl
0x180020d38  jz      short loc_180020D73
0x180020d3a  mov     edx, 18h; dwBytes
0x180020d3f  xor     ecx, ecx; dwFlags
0x180020d41  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180020d46  mov     rcx, rax
0x180020d49  test    rax, rax
0x180020d4c  jz      short loc_180020D73
0x180020d4e  mov     [rax], esi
0x180020d50  xor     eax, eax
0x180020d52  mov     [rcx+4], eax
0x180020d55  mov     [rcx+8], rax
0x180020d59  mov     [rcx+10h], rax
0x180020d5d  mov     rax, [rdi+rbx*8]
0x180020d61  mov     [rcx+8], rax
0x180020d65  lock cmpxchg [rdi+rbx*8], rcx
0x180020d6b  jnz     short loc_180020D5D
0x180020d6d  lea     rax, [rcx+10h]
0x180020d71  jmp     short loc_180020D75
0x180020d73  xor     eax, eax
0x180020d75  add     rsp, 28h
0x180020d79  pop     rdi
0x180020d7a  pop     rsi
0x180020d7b  pop     rbp
0x180020d7c  pop     rbx
0x180020d7d  retn
```
