# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000630c`
- end: `0x1800063aa`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005e1c`
- `0x180018d9c`

## callees

- `0x18000630c`
- `0x1800070cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000631f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000631f`

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
0x18000630c  push    rbx
0x18000630e  push    rbp
0x18000630f  push    rsi
0x180006310  push    rdi
0x180006311  sub     rsp, 28h
0x180006315  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000631c  mov     bpl, dl
0x18000631f  call    cs:__imp_GetCurrentThreadId
0x180006325  mov     ebx, eax
0x180006327  mov     esi, eax
0x180006329  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006333  shr     rbx, 2
0x180006337  mul     rbx
0x18000633a  shr     rdx, 3
0x18000633e  lea     rcx, [rdx+rdx*4]
0x180006342  add     rcx, rcx
0x180006345  sub     rbx, rcx
0x180006348  mov     rax, [rdi+rbx*8]
0x18000634c  test    rax, rax
0x18000634f  jz      short loc_180006361
0x180006351  cmp     [rax], esi
0x180006353  jz      short loc_18000635B
0x180006355  mov     rax, [rax+8]
0x180006359  jmp     short loc_18000634C
0x18000635b  add     rax, 10h
0x18000635f  jmp     short loc_1800063A1
0x180006361  test    bpl, bpl
0x180006364  jz      short loc_18000639F
0x180006366  mov     edx, 18h; dwBytes
0x18000636b  xor     ecx, ecx; dwFlags
0x18000636d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006372  mov     rcx, rax
0x180006375  test    rax, rax
0x180006378  jz      short loc_18000639F
0x18000637a  mov     [rax], esi
0x18000637c  xor     eax, eax
0x18000637e  mov     [rcx+4], eax
0x180006381  mov     [rcx+8], rax
0x180006385  mov     [rcx+10h], rax
0x180006389  mov     rax, [rdi+rbx*8]
0x18000638d  mov     [rcx+8], rax
0x180006391  lock cmpxchg [rdi+rbx*8], rcx
0x180006397  jnz     short loc_180006389
0x180006399  lea     rax, [rcx+10h]
0x18000639d  jmp     short loc_1800063A1
0x18000639f  xor     eax, eax
0x1800063a1  add     rsp, 28h
0x1800063a5  pop     rdi
0x1800063a6  pop     rsi
0x1800063a7  pop     rbp
0x1800063a8  pop     rbx
0x1800063a9  retn
```
