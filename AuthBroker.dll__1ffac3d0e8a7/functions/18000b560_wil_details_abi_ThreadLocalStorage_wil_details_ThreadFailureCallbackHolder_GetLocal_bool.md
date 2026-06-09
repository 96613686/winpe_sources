# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000b560`
- end: `0x18000b5fe`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `wil::details::ThreadFailureCallbackHolder **__fastcall(wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> *this, bool shouldAllocate)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000af88`
- `0x18001b028`

## callees

- `0x18000b560`
- `0x18000c6b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b573`

## pseudocode

```c
wil::details::ThreadFailureCallbackHolder **__fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> *this,
        bool shouldAllocate)
{
  wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> *v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // rbx
  wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::Node *volatile i; // rax
  DWORD *v8; // rax
  signed __int64 v9; // rcx
  signed __int64 v10; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  for ( i = v2->m_hashArray[v5]; i; i = i->pNext )
  {
    if ( i->threadId == CurrentThreadId )
      return &i->value;
  }
  if ( !shouldAllocate )
    return 0;
  v8 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u);
  v9 = (signed __int64)v8;
  if ( !v8 )
    return 0;
  *v8 = CurrentThreadId;
  v8[1] = 0;
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  do
  {
    v10 = (signed __int64)v2->m_hashArray[v5];
    *(_QWORD *)(v9 + 8) = v10;
  }
  while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)&v2->m_hashArray[v5], v9, v10) );
  return (wil::details::ThreadFailureCallbackHolder **)(v9 + 16);
}

```

## disassembly

```asm
0x18000b560  push    rbx
0x18000b562  push    rbp
0x18000b563  push    rsi
0x18000b564  push    rdi
0x18000b565  sub     rsp, 28h
0x18000b569  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b570  mov     bpl, shouldAllocate
0x18000b573  call    cs:__imp_GetCurrentThreadId
0x18000b579  mov     ebx, eax
0x18000b57b  mov     esi, eax
0x18000b57d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b587  shr     rbx, 2
0x18000b58b  mul     rbx
0x18000b58e  shr     rdx, 3
0x18000b592  lea     rcx, [rdx+rdx*4]
0x18000b596  add     rcx, rcx
0x18000b599  sub     rbx, rcx
0x18000b59c  mov     rax, [rdi+rbx*8]
0x18000b5a0  test    rax, rax
0x18000b5a3  jz      short loc_18000B5B5
0x18000b5a5  cmp     [rax], esi
0x18000b5a7  jz      short loc_18000B5AF
0x18000b5a9  mov     rax, [rax+8]
0x18000b5ad  jmp     short loc_18000B5A0
0x18000b5af  add     rax, 10h
0x18000b5b3  jmp     short loc_18000B5F5
0x18000b5b5  test    bpl, bpl
0x18000b5b8  jz      short loc_18000B5F3
0x18000b5ba  mov     edx, 18h; size
0x18000b5bf  xor     ecx, ecx; flags
0x18000b5c1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b5c6  mov     rcx, rax
0x18000b5c9  test    rax, rax
0x18000b5cc  jz      short loc_18000B5F3
0x18000b5ce  mov     [rax], esi
0x18000b5d0  xor     eax, eax
0x18000b5d2  mov     [rcx+4], eax
0x18000b5d5  mov     [rcx+8], rax
0x18000b5d9  mov     [rcx+10h], rax
0x18000b5dd  mov     rax, [rdi+rbx*8]
0x18000b5e1  mov     [rcx+8], rax
0x18000b5e5  lock cmpxchg [rdi+rbx*8], rcx
0x18000b5eb  jnz     short loc_18000B5DD
0x18000b5ed  lea     rax, [rcx+10h]
0x18000b5f1  jmp     short loc_18000B5F5
0x18000b5f3  xor     eax, eax
0x18000b5f5  add     rsp, 28h
0x18000b5f9  pop     rdi
0x18000b5fa  pop     rsi
0x18000b5fb  pop     rbp
0x18000b5fc  pop     rbx
0x18000b5fd  retn
```
