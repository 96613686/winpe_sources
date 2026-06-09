# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180005330`
- end: `0x1800053cc`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d9a0`
- `0x18000df78`
- `0x18000f094`
- `0x18000f28c`

## callees

- `0x180005330`
- `0x180005e58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005343`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005343`

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
0x180005330  push    rbx
0x180005332  push    rbp
0x180005333  push    rsi
0x180005334  push    rdi
0x180005335  sub     rsp, 28h
0x180005339  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005340  mov     bpl, dl
0x180005343  call    cs:__imp_GetCurrentThreadId
0x180005349  mov     ebx, eax
0x18000534b  mov     esi, eax
0x18000534d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005357  shr     rbx, 2
0x18000535b  mul     rbx
0x18000535e  shr     rdx, 3
0x180005362  lea     rcx, [rdx+rdx*4]
0x180005366  add     rcx, rcx
0x180005369  sub     rbx, rcx
0x18000536c  mov     rax, [rdi+rbx*8]
0x180005370  jmp     short loc_18000537A
0x180005372  cmp     [rax], esi
0x180005374  jz      short loc_1800053BB
0x180005376  mov     rax, [rax+8]
0x18000537a  test    rax, rax
0x18000537d  jnz     short loc_180005372
0x18000537f  test    bpl, bpl
0x180005382  jz      short loc_1800053C1
0x180005384  lea     edx, [rax+18h]; dwBytes
0x180005387  xor     ecx, ecx; dwFlags
0x180005389  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000538e  mov     rcx, rax
0x180005391  test    rax, rax
0x180005394  jz      short loc_1800053C1
0x180005396  mov     [rax], esi
0x180005398  xor     eax, eax
0x18000539a  mov     [rcx+4], eax
0x18000539d  mov     [rcx+8], rax
0x1800053a1  mov     [rcx+10h], rax
0x1800053a5  mov     rax, [rdi+rbx*8]
0x1800053a9  mov     [rcx+8], rax
0x1800053ad  lock cmpxchg [rdi+rbx*8], rcx
0x1800053b3  jnz     short loc_1800053A5
0x1800053b5  lea     rax, [rcx+10h]
0x1800053b9  jmp     short loc_1800053C3
0x1800053bb  add     rax, 10h
0x1800053bf  jmp     short loc_1800053C3
0x1800053c1  xor     eax, eax
0x1800053c3  add     rsp, 28h
0x1800053c7  pop     rdi
0x1800053c8  pop     rsi
0x1800053c9  pop     rbp
0x1800053ca  pop     rbx
0x1800053cb  retn
```
