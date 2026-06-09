# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800069ec`
- end: `0x180006a8a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006328`
- `0x18001bcec`

## callees

- `0x1800069ec`
- `0x180007e0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069ff`

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
0x1800069ec  push    rbx
0x1800069ee  push    rbp
0x1800069ef  push    rsi
0x1800069f0  push    rdi
0x1800069f1  sub     rsp, 28h
0x1800069f5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800069fc  mov     bpl, dl
0x1800069ff  call    cs:__imp_GetCurrentThreadId
0x180006a05  mov     ebx, eax
0x180006a07  mov     esi, eax
0x180006a09  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006a13  shr     rbx, 2
0x180006a17  mul     rbx
0x180006a1a  shr     rdx, 3
0x180006a1e  lea     rcx, [rdx+rdx*4]
0x180006a22  add     rcx, rcx
0x180006a25  sub     rbx, rcx
0x180006a28  mov     rax, [rdi+rbx*8]
0x180006a2c  test    rax, rax
0x180006a2f  jz      short loc_180006A41
0x180006a31  cmp     [rax], esi
0x180006a33  jz      short loc_180006A3B
0x180006a35  mov     rax, [rax+8]
0x180006a39  jmp     short loc_180006A2C
0x180006a3b  add     rax, 10h
0x180006a3f  jmp     short loc_180006A81
0x180006a41  test    bpl, bpl
0x180006a44  jz      short loc_180006A7F
0x180006a46  mov     edx, 18h; dwBytes
0x180006a4b  xor     ecx, ecx; dwFlags
0x180006a4d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006a52  mov     rcx, rax
0x180006a55  test    rax, rax
0x180006a58  jz      short loc_180006A7F
0x180006a5a  mov     [rax], esi
0x180006a5c  xor     eax, eax
0x180006a5e  mov     [rcx+4], eax
0x180006a61  mov     [rcx+8], rax
0x180006a65  mov     [rcx+10h], rax
0x180006a69  mov     rax, [rdi+rbx*8]
0x180006a6d  mov     [rcx+8], rax
0x180006a71  lock cmpxchg [rdi+rbx*8], rcx
0x180006a77  jnz     short loc_180006A69
0x180006a79  lea     rax, [rcx+10h]
0x180006a7d  jmp     short loc_180006A81
0x180006a7f  xor     eax, eax
0x180006a81  add     rsp, 28h
0x180006a85  pop     rdi
0x180006a86  pop     rsi
0x180006a87  pop     rbp
0x180006a88  pop     rbx
0x180006a89  retn
```
