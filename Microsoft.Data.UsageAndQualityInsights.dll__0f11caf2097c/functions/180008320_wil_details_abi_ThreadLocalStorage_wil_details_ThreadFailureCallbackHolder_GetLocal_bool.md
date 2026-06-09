# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008320`
- end: `0x1800083bc`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012998`
- `0x180012aa4`
- `0x18001ac5c`
- `0x18001c060`
- `0x18002b6a8`
- `0x180046cf0`
- `0x18004c184`
- `0x1800e6bb8`
- `0x1800e75bc`
- `0x1800f4eb4`

## callees

- `0x180008320`
- `0x180009058`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008333`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008333`

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
0x180008320  push    rbx
0x180008322  push    rbp
0x180008323  push    rsi
0x180008324  push    rdi
0x180008325  sub     rsp, 28h
0x180008329  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008330  mov     bpl, dl
0x180008333  call    cs:__imp_GetCurrentThreadId
0x180008339  mov     ebx, eax
0x18000833b  mov     esi, eax
0x18000833d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008347  shr     rbx, 2
0x18000834b  mul     rbx
0x18000834e  shr     rdx, 3
0x180008352  lea     rcx, [rdx+rdx*4]
0x180008356  add     rcx, rcx
0x180008359  sub     rbx, rcx
0x18000835c  mov     rax, [rdi+rbx*8]
0x180008360  jmp     short loc_18000836A
0x180008362  cmp     [rax], esi
0x180008364  jz      short loc_1800083AB
0x180008366  mov     rax, [rax+8]
0x18000836a  test    rax, rax
0x18000836d  jnz     short loc_180008362
0x18000836f  test    bpl, bpl
0x180008372  jz      short loc_1800083B1
0x180008374  lea     edx, [rax+18h]; dwBytes
0x180008377  xor     ecx, ecx; dwFlags
0x180008379  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000837e  mov     rcx, rax
0x180008381  test    rax, rax
0x180008384  jz      short loc_1800083B1
0x180008386  mov     [rax], esi
0x180008388  xor     eax, eax
0x18000838a  mov     [rcx+4], eax
0x18000838d  mov     [rcx+8], rax
0x180008391  mov     [rcx+10h], rax
0x180008395  mov     rax, [rdi+rbx*8]
0x180008399  mov     [rcx+8], rax
0x18000839d  lock cmpxchg [rdi+rbx*8], rcx
0x1800083a3  jnz     short loc_180008395
0x1800083a5  lea     rax, [rcx+10h]
0x1800083a9  jmp     short loc_1800083B3
0x1800083ab  add     rax, 10h
0x1800083af  jmp     short loc_1800083B3
0x1800083b1  xor     eax, eax
0x1800083b3  add     rsp, 28h
0x1800083b7  pop     rdi
0x1800083b8  pop     rsi
0x1800083b9  pop     rbp
0x1800083ba  pop     rbx
0x1800083bb  retn
```
