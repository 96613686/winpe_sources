# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000627c`
- end: `0x18000631a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005da4`
- `0x180015054`

## callees

- `0x18000627c`
- `0x180006fcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000628f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000628f`

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
0x18000627c  push    rbx
0x18000627e  push    rbp
0x18000627f  push    rsi
0x180006280  push    rdi
0x180006281  sub     rsp, 28h
0x180006285  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000628c  mov     bpl, dl
0x18000628f  call    cs:__imp_GetCurrentThreadId
0x180006295  mov     ebx, eax
0x180006297  mov     esi, eax
0x180006299  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800062a3  shr     rbx, 2
0x1800062a7  mul     rbx
0x1800062aa  shr     rdx, 3
0x1800062ae  lea     rcx, [rdx+rdx*4]
0x1800062b2  add     rcx, rcx
0x1800062b5  sub     rbx, rcx
0x1800062b8  mov     rax, [rdi+rbx*8]
0x1800062bc  test    rax, rax
0x1800062bf  jz      short loc_1800062D1
0x1800062c1  cmp     [rax], esi
0x1800062c3  jz      short loc_1800062CB
0x1800062c5  mov     rax, [rax+8]
0x1800062c9  jmp     short loc_1800062BC
0x1800062cb  add     rax, 10h
0x1800062cf  jmp     short loc_180006311
0x1800062d1  test    bpl, bpl
0x1800062d4  jz      short loc_18000630F
0x1800062d6  mov     edx, 18h; dwBytes
0x1800062db  xor     ecx, ecx; dwFlags
0x1800062dd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800062e2  mov     rcx, rax
0x1800062e5  test    rax, rax
0x1800062e8  jz      short loc_18000630F
0x1800062ea  mov     [rax], esi
0x1800062ec  xor     eax, eax
0x1800062ee  mov     [rcx+4], eax
0x1800062f1  mov     [rcx+8], rax
0x1800062f5  mov     [rcx+10h], rax
0x1800062f9  mov     rax, [rdi+rbx*8]
0x1800062fd  mov     [rcx+8], rax
0x180006301  lock cmpxchg [rdi+rbx*8], rcx
0x180006307  jnz     short loc_1800062F9
0x180006309  lea     rax, [rcx+10h]
0x18000630d  jmp     short loc_180006311
0x18000630f  xor     eax, eax
0x180006311  add     rsp, 28h
0x180006315  pop     rdi
0x180006316  pop     rsi
0x180006317  pop     rbp
0x180006318  pop     rbx
0x180006319  retn
```
