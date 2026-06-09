# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d4c0`
- end: `0x18000d55e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d088`
- `0x180017dd0`

## callees

- `0x18000d4c0`
- `0x18000e02c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d4d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d4d3`

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
0x18000d4c0  push    rbx
0x18000d4c2  push    rbp
0x18000d4c3  push    rsi
0x18000d4c4  push    rdi
0x18000d4c5  sub     rsp, 28h
0x18000d4c9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d4d0  mov     bpl, dl
0x18000d4d3  call    cs:__imp_GetCurrentThreadId
0x18000d4d9  mov     ebx, eax
0x18000d4db  mov     esi, eax
0x18000d4dd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d4e7  shr     rbx, 2
0x18000d4eb  mul     rbx
0x18000d4ee  shr     rdx, 3
0x18000d4f2  lea     rcx, [rdx+rdx*4]
0x18000d4f6  add     rcx, rcx
0x18000d4f9  sub     rbx, rcx
0x18000d4fc  mov     rax, [rdi+rbx*8]
0x18000d500  test    rax, rax
0x18000d503  jz      short loc_18000D515
0x18000d505  cmp     [rax], esi
0x18000d507  jz      short loc_18000D50F
0x18000d509  mov     rax, [rax+8]
0x18000d50d  jmp     short loc_18000D500
0x18000d50f  add     rax, 10h
0x18000d513  jmp     short loc_18000D555
0x18000d515  test    bpl, bpl
0x18000d518  jz      short loc_18000D553
0x18000d51a  mov     edx, 18h; dwBytes
0x18000d51f  xor     ecx, ecx; dwFlags
0x18000d521  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d526  mov     rcx, rax
0x18000d529  test    rax, rax
0x18000d52c  jz      short loc_18000D553
0x18000d52e  mov     [rax], esi
0x18000d530  xor     eax, eax
0x18000d532  mov     [rcx+4], eax
0x18000d535  mov     [rcx+8], rax
0x18000d539  mov     [rcx+10h], rax
0x18000d53d  mov     rax, [rdi+rbx*8]
0x18000d541  mov     [rcx+8], rax
0x18000d545  lock cmpxchg [rdi+rbx*8], rcx
0x18000d54b  jnz     short loc_18000D53D
0x18000d54d  lea     rax, [rcx+10h]
0x18000d551  jmp     short loc_18000D555
0x18000d553  xor     eax, eax
0x18000d555  add     rsp, 28h
0x18000d559  pop     rdi
0x18000d55a  pop     rsi
0x18000d55b  pop     rbp
0x18000d55c  pop     rbx
0x18000d55d  retn
```
