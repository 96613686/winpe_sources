# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180005c5c`
- end: `0x180005cfa`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005788`
- `0x1800105c8`

## callees

- `0x180005c5c`
- `0x180006f5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c6f`

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
0x180005c5c  push    rbx
0x180005c5e  push    rbp
0x180005c5f  push    rsi
0x180005c60  push    rdi
0x180005c61  sub     rsp, 28h
0x180005c65  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005c6c  mov     bpl, dl
0x180005c6f  call    cs:__imp_GetCurrentThreadId
0x180005c75  mov     ebx, eax
0x180005c77  mov     esi, eax
0x180005c79  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005c83  shr     rbx, 2
0x180005c87  mul     rbx
0x180005c8a  shr     rdx, 3
0x180005c8e  lea     rcx, [rdx+rdx*4]
0x180005c92  add     rcx, rcx
0x180005c95  sub     rbx, rcx
0x180005c98  mov     rax, [rdi+rbx*8]
0x180005c9c  test    rax, rax
0x180005c9f  jz      short loc_180005CB1
0x180005ca1  cmp     [rax], esi
0x180005ca3  jz      short loc_180005CAB
0x180005ca5  mov     rax, [rax+8]
0x180005ca9  jmp     short loc_180005C9C
0x180005cab  add     rax, 10h
0x180005caf  jmp     short loc_180005CF1
0x180005cb1  test    bpl, bpl
0x180005cb4  jz      short loc_180005CEF
0x180005cb6  mov     edx, 18h; dwBytes
0x180005cbb  xor     ecx, ecx; dwFlags
0x180005cbd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005cc2  mov     rcx, rax
0x180005cc5  test    rax, rax
0x180005cc8  jz      short loc_180005CEF
0x180005cca  mov     [rax], esi
0x180005ccc  xor     eax, eax
0x180005cce  mov     [rcx+4], eax
0x180005cd1  mov     [rcx+8], rax
0x180005cd5  mov     [rcx+10h], rax
0x180005cd9  mov     rax, [rdi+rbx*8]
0x180005cdd  mov     [rcx+8], rax
0x180005ce1  lock cmpxchg [rdi+rbx*8], rcx
0x180005ce7  jnz     short loc_180005CD9
0x180005ce9  lea     rax, [rcx+10h]
0x180005ced  jmp     short loc_180005CF1
0x180005cef  xor     eax, eax
0x180005cf1  add     rsp, 28h
0x180005cf5  pop     rdi
0x180005cf6  pop     rsi
0x180005cf7  pop     rbp
0x180005cf8  pop     rbx
0x180005cf9  retn
```
