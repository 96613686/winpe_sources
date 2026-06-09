# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006b3c`
- end: `0x180006bda`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000663c`
- `0x18000ecb0`

## callees

- `0x180006b3c`
- `0x1800078f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b4f`

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
0x180006b3c  push    rbx
0x180006b3e  push    rbp
0x180006b3f  push    rsi
0x180006b40  push    rdi
0x180006b41  sub     rsp, 28h
0x180006b45  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006b4c  mov     bpl, dl
0x180006b4f  call    cs:__imp_GetCurrentThreadId
0x180006b55  mov     ebx, eax
0x180006b57  mov     esi, eax
0x180006b59  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006b63  shr     rbx, 2
0x180006b67  mul     rbx
0x180006b6a  shr     rdx, 3
0x180006b6e  lea     rcx, [rdx+rdx*4]
0x180006b72  add     rcx, rcx
0x180006b75  sub     rbx, rcx
0x180006b78  mov     rax, [rdi+rbx*8]
0x180006b7c  test    rax, rax
0x180006b7f  jz      short loc_180006B91
0x180006b81  cmp     [rax], esi
0x180006b83  jz      short loc_180006B8B
0x180006b85  mov     rax, [rax+8]
0x180006b89  jmp     short loc_180006B7C
0x180006b8b  add     rax, 10h
0x180006b8f  jmp     short loc_180006BD1
0x180006b91  test    bpl, bpl
0x180006b94  jz      short loc_180006BCF
0x180006b96  mov     edx, 18h; dwBytes
0x180006b9b  xor     ecx, ecx; dwFlags
0x180006b9d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006ba2  mov     rcx, rax
0x180006ba5  test    rax, rax
0x180006ba8  jz      short loc_180006BCF
0x180006baa  mov     [rax], esi
0x180006bac  xor     eax, eax
0x180006bae  mov     [rcx+4], eax
0x180006bb1  mov     [rcx+8], rax
0x180006bb5  mov     [rcx+10h], rax
0x180006bb9  mov     rax, [rdi+rbx*8]
0x180006bbd  mov     [rcx+8], rax
0x180006bc1  lock cmpxchg [rdi+rbx*8], rcx
0x180006bc7  jnz     short loc_180006BB9
0x180006bc9  lea     rax, [rcx+10h]
0x180006bcd  jmp     short loc_180006BD1
0x180006bcf  xor     eax, eax
0x180006bd1  add     rsp, 28h
0x180006bd5  pop     rdi
0x180006bd6  pop     rsi
0x180006bd7  pop     rbp
0x180006bd8  pop     rbx
0x180006bd9  retn
```
