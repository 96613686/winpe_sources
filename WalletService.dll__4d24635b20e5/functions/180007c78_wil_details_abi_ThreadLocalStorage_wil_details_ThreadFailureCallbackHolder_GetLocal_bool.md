# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007c78`
- end: `0x180007d16`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006ff8`
- `0x18002b194`

## callees

- `0x180007c78`
- `0x1800090d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c8b`

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
0x180007c78  push    rbx
0x180007c7a  push    rbp
0x180007c7b  push    rsi
0x180007c7c  push    rdi
0x180007c7d  sub     rsp, 28h
0x180007c81  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007c88  mov     bpl, dl
0x180007c8b  call    cs:__imp_GetCurrentThreadId
0x180007c91  mov     ebx, eax
0x180007c93  mov     esi, eax
0x180007c95  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007c9f  shr     rbx, 2
0x180007ca3  mul     rbx
0x180007ca6  shr     rdx, 3
0x180007caa  lea     rcx, [rdx+rdx*4]
0x180007cae  add     rcx, rcx
0x180007cb1  sub     rbx, rcx
0x180007cb4  mov     rax, [rdi+rbx*8]
0x180007cb8  test    rax, rax
0x180007cbb  jz      short loc_180007CCD
0x180007cbd  cmp     [rax], esi
0x180007cbf  jz      short loc_180007CC7
0x180007cc1  mov     rax, [rax+8]
0x180007cc5  jmp     short loc_180007CB8
0x180007cc7  add     rax, 10h
0x180007ccb  jmp     short loc_180007D0D
0x180007ccd  test    bpl, bpl
0x180007cd0  jz      short loc_180007D0B
0x180007cd2  mov     edx, 18h; dwBytes
0x180007cd7  xor     ecx, ecx; dwFlags
0x180007cd9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007cde  mov     rcx, rax
0x180007ce1  test    rax, rax
0x180007ce4  jz      short loc_180007D0B
0x180007ce6  mov     [rax], esi
0x180007ce8  xor     eax, eax
0x180007cea  mov     [rcx+4], eax
0x180007ced  mov     [rcx+8], rax
0x180007cf1  mov     [rcx+10h], rax
0x180007cf5  mov     rax, [rdi+rbx*8]
0x180007cf9  mov     [rcx+8], rax
0x180007cfd  lock cmpxchg [rdi+rbx*8], rcx
0x180007d03  jnz     short loc_180007CF5
0x180007d05  lea     rax, [rcx+10h]
0x180007d09  jmp     short loc_180007D0D
0x180007d0b  xor     eax, eax
0x180007d0d  add     rsp, 28h
0x180007d11  pop     rdi
0x180007d12  pop     rsi
0x180007d13  pop     rbp
0x180007d14  pop     rbx
0x180007d15  retn
```
