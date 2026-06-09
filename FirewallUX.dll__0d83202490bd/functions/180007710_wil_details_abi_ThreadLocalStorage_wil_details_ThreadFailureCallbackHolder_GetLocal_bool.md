# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007710`
- end: `0x1800077ac`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009fc8`

## callees

- `0x180007710`
- `0x18000877c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007723`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007723`

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
0x180007710  push    rbx
0x180007712  push    rbp
0x180007713  push    rsi
0x180007714  push    rdi
0x180007715  sub     rsp, 28h
0x180007719  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007720  mov     bpl, dl
0x180007723  call    cs:__imp_GetCurrentThreadId
0x180007729  mov     ebx, eax
0x18000772b  mov     esi, eax
0x18000772d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007737  shr     rbx, 2
0x18000773b  mul     rbx
0x18000773e  shr     rdx, 3
0x180007742  lea     rcx, [rdx+rdx*4]
0x180007746  add     rcx, rcx
0x180007749  sub     rbx, rcx
0x18000774c  mov     rax, [rdi+rbx*8]
0x180007750  jmp     short loc_18000775A
0x180007752  cmp     [rax], esi
0x180007754  jz      short loc_18000779B
0x180007756  mov     rax, [rax+8]
0x18000775a  test    rax, rax
0x18000775d  jnz     short loc_180007752
0x18000775f  test    bpl, bpl
0x180007762  jz      short loc_1800077A1
0x180007764  lea     edx, [rax+18h]; dwBytes
0x180007767  xor     ecx, ecx; dwFlags
0x180007769  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000776e  mov     rcx, rax
0x180007771  test    rax, rax
0x180007774  jz      short loc_1800077A1
0x180007776  mov     [rax], esi
0x180007778  xor     eax, eax
0x18000777a  mov     [rcx+4], eax
0x18000777d  mov     [rcx+8], rax
0x180007781  mov     [rcx+10h], rax
0x180007785  mov     rax, [rdi+rbx*8]
0x180007789  mov     [rcx+8], rax
0x18000778d  lock cmpxchg [rdi+rbx*8], rcx
0x180007793  jnz     short loc_180007785
0x180007795  lea     rax, [rcx+10h]
0x180007799  jmp     short loc_1800077A3
0x18000779b  add     rax, 10h
0x18000779f  jmp     short loc_1800077A3
0x1800077a1  xor     eax, eax
0x1800077a3  add     rsp, 28h
0x1800077a7  pop     rdi
0x1800077a8  pop     rsi
0x1800077a9  pop     rbp
0x1800077aa  pop     rbx
0x1800077ab  retn
```
