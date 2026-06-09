# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800080e0`
- end: `0x18000817c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bb94`
- `0x18001bdc8`
- `0x180025240`
- `0x1800253c8`

## callees

- `0x1800080e0`
- `0x180008d74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080f3`

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
0x1800080e0  push    rbx
0x1800080e2  push    rbp
0x1800080e3  push    rsi
0x1800080e4  push    rdi
0x1800080e5  sub     rsp, 28h
0x1800080e9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800080f0  mov     bpl, dl
0x1800080f3  call    cs:__imp_GetCurrentThreadId
0x1800080f9  mov     ebx, eax
0x1800080fb  mov     esi, eax
0x1800080fd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008107  shr     rbx, 2
0x18000810b  mul     rbx
0x18000810e  shr     rdx, 3
0x180008112  lea     rcx, [rdx+rdx*4]
0x180008116  add     rcx, rcx
0x180008119  sub     rbx, rcx
0x18000811c  mov     rax, [rdi+rbx*8]
0x180008120  jmp     short loc_18000812A
0x180008122  cmp     [rax], esi
0x180008124  jz      short loc_18000816B
0x180008126  mov     rax, [rax+8]
0x18000812a  test    rax, rax
0x18000812d  jnz     short loc_180008122
0x18000812f  test    bpl, bpl
0x180008132  jz      short loc_180008171
0x180008134  lea     edx, [rax+18h]; dwBytes
0x180008137  xor     ecx, ecx; dwFlags
0x180008139  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000813e  mov     rcx, rax
0x180008141  test    rax, rax
0x180008144  jz      short loc_180008171
0x180008146  mov     [rax], esi
0x180008148  xor     eax, eax
0x18000814a  mov     [rcx+4], eax
0x18000814d  mov     [rcx+8], rax
0x180008151  mov     [rcx+10h], rax
0x180008155  mov     rax, [rdi+rbx*8]
0x180008159  mov     [rcx+8], rax
0x18000815d  lock cmpxchg [rdi+rbx*8], rcx
0x180008163  jnz     short loc_180008155
0x180008165  lea     rax, [rcx+10h]
0x180008169  jmp     short loc_180008173
0x18000816b  add     rax, 10h
0x18000816f  jmp     short loc_180008173
0x180008171  xor     eax, eax
0x180008173  add     rsp, 28h
0x180008177  pop     rdi
0x180008178  pop     rsi
0x180008179  pop     rbp
0x18000817a  pop     rbx
0x18000817b  retn
```
