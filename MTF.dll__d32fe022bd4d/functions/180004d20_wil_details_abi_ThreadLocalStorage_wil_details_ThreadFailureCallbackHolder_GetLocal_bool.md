# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180004d20`
- end: `0x180004dbc`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b19c`
- `0x18001b314`
- `0x18001b48c`
- `0x18001b604`
- `0x18001b77c`

## callees

- `0x180004d20`
- `0x18000599c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d33`

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
0x180004d20  push    rbx
0x180004d22  push    rbp
0x180004d23  push    rsi
0x180004d24  push    rdi
0x180004d25  sub     rsp, 28h
0x180004d29  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004d30  mov     bpl, dl
0x180004d33  call    cs:__imp_GetCurrentThreadId
0x180004d39  mov     ebx, eax
0x180004d3b  mov     esi, eax
0x180004d3d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004d47  shr     rbx, 2
0x180004d4b  mul     rbx
0x180004d4e  shr     rdx, 3
0x180004d52  lea     rcx, [rdx+rdx*4]
0x180004d56  add     rcx, rcx
0x180004d59  sub     rbx, rcx
0x180004d5c  mov     rax, [rdi+rbx*8]
0x180004d60  jmp     short loc_180004D6A
0x180004d62  cmp     [rax], esi
0x180004d64  jz      short loc_180004DAB
0x180004d66  mov     rax, [rax+8]
0x180004d6a  test    rax, rax
0x180004d6d  jnz     short loc_180004D62
0x180004d6f  test    bpl, bpl
0x180004d72  jz      short loc_180004DB1
0x180004d74  lea     edx, [rax+18h]; dwBytes
0x180004d77  xor     ecx, ecx; dwFlags
0x180004d79  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d7e  mov     rcx, rax
0x180004d81  test    rax, rax
0x180004d84  jz      short loc_180004DB1
0x180004d86  mov     [rax], esi
0x180004d88  xor     eax, eax
0x180004d8a  mov     [rcx+4], eax
0x180004d8d  mov     [rcx+8], rax
0x180004d91  mov     [rcx+10h], rax
0x180004d95  mov     rax, [rdi+rbx*8]
0x180004d99  mov     [rcx+8], rax
0x180004d9d  lock cmpxchg [rdi+rbx*8], rcx
0x180004da3  jnz     short loc_180004D95
0x180004da5  lea     rax, [rcx+10h]
0x180004da9  jmp     short loc_180004DB3
0x180004dab  add     rax, 10h
0x180004daf  jmp     short loc_180004DB3
0x180004db1  xor     eax, eax
0x180004db3  add     rsp, 28h
0x180004db7  pop     rdi
0x180004db8  pop     rsi
0x180004db9  pop     rbp
0x180004dba  pop     rbx
0x180004dbb  retn
```
