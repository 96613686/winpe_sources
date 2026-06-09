# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180005988`
- end: `0x180005a26`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800054a4`
- `0x1800114d8`

## callees

- `0x180005988`
- `0x1800065c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000599b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000599b`

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
0x180005988  push    rbx
0x18000598a  push    rbp
0x18000598b  push    rsi
0x18000598c  push    rdi
0x18000598d  sub     rsp, 28h
0x180005991  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005998  mov     bpl, dl
0x18000599b  call    cs:__imp_GetCurrentThreadId
0x1800059a1  mov     ebx, eax
0x1800059a3  mov     esi, eax
0x1800059a5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800059af  shr     rbx, 2
0x1800059b3  mul     rbx
0x1800059b6  shr     rdx, 3
0x1800059ba  lea     rcx, [rdx+rdx*4]
0x1800059be  add     rcx, rcx
0x1800059c1  sub     rbx, rcx
0x1800059c4  mov     rax, [rdi+rbx*8]
0x1800059c8  test    rax, rax
0x1800059cb  jz      short loc_1800059DD
0x1800059cd  cmp     [rax], esi
0x1800059cf  jz      short loc_1800059D7
0x1800059d1  mov     rax, [rax+8]
0x1800059d5  jmp     short loc_1800059C8
0x1800059d7  add     rax, 10h
0x1800059db  jmp     short loc_180005A1D
0x1800059dd  test    bpl, bpl
0x1800059e0  jz      short loc_180005A1B
0x1800059e2  mov     edx, 18h; dwBytes
0x1800059e7  xor     ecx, ecx; dwFlags
0x1800059e9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800059ee  mov     rcx, rax
0x1800059f1  test    rax, rax
0x1800059f4  jz      short loc_180005A1B
0x1800059f6  mov     [rax], esi
0x1800059f8  xor     eax, eax
0x1800059fa  mov     [rcx+4], eax
0x1800059fd  mov     [rcx+8], rax
0x180005a01  mov     [rcx+10h], rax
0x180005a05  mov     rax, [rdi+rbx*8]
0x180005a09  mov     [rcx+8], rax
0x180005a0d  lock cmpxchg [rdi+rbx*8], rcx
0x180005a13  jnz     short loc_180005A05
0x180005a15  lea     rax, [rcx+10h]
0x180005a19  jmp     short loc_180005A1D
0x180005a1b  xor     eax, eax
0x180005a1d  add     rsp, 28h
0x180005a21  pop     rdi
0x180005a22  pop     rsi
0x180005a23  pop     rbp
0x180005a24  pop     rbx
0x180005a25  retn
```
