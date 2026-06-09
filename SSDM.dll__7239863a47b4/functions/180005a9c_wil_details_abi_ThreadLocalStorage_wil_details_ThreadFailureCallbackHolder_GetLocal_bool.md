# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180005a9c`
- end: `0x180005b38`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005ec0`
- `0x18000b328`

## callees

- `0x180005a9c`
- `0x18000694c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005aaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005aaf`

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
0x180005a9c  push    rbx
0x180005a9e  push    rbp
0x180005a9f  push    rsi
0x180005aa0  push    rdi
0x180005aa1  sub     rsp, 28h
0x180005aa5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005aac  mov     bpl, dl
0x180005aaf  call    cs:__imp_GetCurrentThreadId
0x180005ab5  mov     ebx, eax
0x180005ab7  mov     esi, eax
0x180005ab9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005ac3  shr     rbx, 2
0x180005ac7  mul     rbx
0x180005aca  shr     rdx, 3
0x180005ace  lea     rcx, [rdx+rdx*4]
0x180005ad2  add     rcx, rcx
0x180005ad5  sub     rbx, rcx
0x180005ad8  mov     rax, [rdi+rbx*8]
0x180005adc  jmp     short loc_180005AE6
0x180005ade  cmp     [rax], esi
0x180005ae0  jz      short loc_180005B27
0x180005ae2  mov     rax, [rax+8]
0x180005ae6  test    rax, rax
0x180005ae9  jnz     short loc_180005ADE
0x180005aeb  test    bpl, bpl
0x180005aee  jz      short loc_180005B2D
0x180005af0  lea     edx, [rax+18h]; dwBytes
0x180005af3  xor     ecx, ecx; dwFlags
0x180005af5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005afa  mov     rcx, rax
0x180005afd  test    rax, rax
0x180005b00  jz      short loc_180005B2D
0x180005b02  mov     [rax], esi
0x180005b04  xor     eax, eax
0x180005b06  mov     [rcx+4], eax
0x180005b09  mov     [rcx+8], rax
0x180005b0d  mov     [rcx+10h], rax
0x180005b11  mov     rax, [rdi+rbx*8]
0x180005b15  mov     [rcx+8], rax
0x180005b19  lock cmpxchg [rdi+rbx*8], rcx
0x180005b1f  jnz     short loc_180005B11
0x180005b21  lea     rax, [rcx+10h]
0x180005b25  jmp     short loc_180005B2F
0x180005b27  add     rax, 10h
0x180005b2b  jmp     short loc_180005B2F
0x180005b2d  xor     eax, eax
0x180005b2f  add     rsp, 28h
0x180005b33  pop     rdi
0x180005b34  pop     rsi
0x180005b35  pop     rbp
0x180005b36  pop     rbx
0x180005b37  retn
```
