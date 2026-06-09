# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140009b98`
- end: `0x140009c34`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400196a0`
- `0x1400197f4`
- `0x140019948`

## callees

- `0x140009b98`
- `0x14000ba08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009bab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009bab`

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
0x140009b98  push    rbx
0x140009b9a  push    rbp
0x140009b9b  push    rsi
0x140009b9c  push    rdi
0x140009b9d  sub     rsp, 28h
0x140009ba1  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140009ba8  mov     bpl, dl
0x140009bab  call    cs:__imp_GetCurrentThreadId
0x140009bb1  mov     ebx, eax
0x140009bb3  mov     esi, eax
0x140009bb5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140009bbf  shr     rbx, 2
0x140009bc3  mul     rbx
0x140009bc6  shr     rdx, 3
0x140009bca  lea     rcx, [rdx+rdx*4]
0x140009bce  add     rcx, rcx
0x140009bd1  sub     rbx, rcx
0x140009bd4  mov     rax, [rdi+rbx*8]
0x140009bd8  jmp     short loc_140009BE2
0x140009bda  cmp     [rax], esi
0x140009bdc  jz      short loc_140009C23
0x140009bde  mov     rax, [rax+8]
0x140009be2  test    rax, rax
0x140009be5  jnz     short loc_140009BDA
0x140009be7  test    bpl, bpl
0x140009bea  jz      short loc_140009C29
0x140009bec  lea     edx, [rax+18h]; dwBytes
0x140009bef  xor     ecx, ecx; dwFlags
0x140009bf1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009bf6  mov     rcx, rax
0x140009bf9  test    rax, rax
0x140009bfc  jz      short loc_140009C29
0x140009bfe  mov     [rax], esi
0x140009c00  xor     eax, eax
0x140009c02  mov     [rcx+4], eax
0x140009c05  mov     [rcx+8], rax
0x140009c09  mov     [rcx+10h], rax
0x140009c0d  mov     rax, [rdi+rbx*8]
0x140009c11  mov     [rcx+8], rax
0x140009c15  lock cmpxchg [rdi+rbx*8], rcx
0x140009c1b  jnz     short loc_140009C0D
0x140009c1d  lea     rax, [rcx+10h]
0x140009c21  jmp     short loc_140009C2B
0x140009c23  add     rax, 10h
0x140009c27  jmp     short loc_140009C2B
0x140009c29  xor     eax, eax
0x140009c2b  add     rsp, 28h
0x140009c2f  pop     rdi
0x140009c30  pop     rsi
0x140009c31  pop     rbp
0x140009c32  pop     rbx
0x140009c33  retn
```
