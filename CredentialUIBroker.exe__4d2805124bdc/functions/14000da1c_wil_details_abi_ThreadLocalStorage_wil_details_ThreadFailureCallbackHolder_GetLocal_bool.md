# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x14000da1c`
- end: `0x14000daba`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cea0`
- `0x140014a54`

## callees

- `0x14000da1c`
- `0x1400107dc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000da2f`
- `KERNEL32!GetCurrentThreadId` at `0x14000da2f`

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
0x14000da1c  push    rbx
0x14000da1e  push    rbp
0x14000da1f  push    rsi
0x14000da20  push    rdi
0x14000da21  sub     rsp, 28h
0x14000da25  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000da2c  mov     bpl, dl
0x14000da2f  call    cs:__imp_GetCurrentThreadId
0x14000da35  mov     ebx, eax
0x14000da37  mov     esi, eax
0x14000da39  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000da43  shr     rbx, 2
0x14000da47  mul     rbx
0x14000da4a  shr     rdx, 3
0x14000da4e  lea     rcx, [rdx+rdx*4]
0x14000da52  add     rcx, rcx
0x14000da55  sub     rbx, rcx
0x14000da58  mov     rax, [rdi+rbx*8]
0x14000da5c  test    rax, rax
0x14000da5f  jz      short loc_14000DA71
0x14000da61  cmp     [rax], esi
0x14000da63  jz      short loc_14000DA6B
0x14000da65  mov     rax, [rax+8]
0x14000da69  jmp     short loc_14000DA5C
0x14000da6b  add     rax, 10h
0x14000da6f  jmp     short loc_14000DAB1
0x14000da71  test    bpl, bpl
0x14000da74  jz      short loc_14000DAAF
0x14000da76  mov     edx, 18h; dwBytes
0x14000da7b  xor     ecx, ecx; dwFlags
0x14000da7d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000da82  mov     rcx, rax
0x14000da85  test    rax, rax
0x14000da88  jz      short loc_14000DAAF
0x14000da8a  mov     [rax], esi
0x14000da8c  xor     eax, eax
0x14000da8e  mov     [rcx+4], eax
0x14000da91  mov     [rcx+8], rax
0x14000da95  mov     [rcx+10h], rax
0x14000da99  mov     rax, [rdi+rbx*8]
0x14000da9d  mov     [rcx+8], rax
0x14000daa1  lock cmpxchg [rdi+rbx*8], rcx
0x14000daa7  jnz     short loc_14000DA99
0x14000daa9  lea     rax, [rcx+10h]
0x14000daad  jmp     short loc_14000DAB1
0x14000daaf  xor     eax, eax
0x14000dab1  add     rsp, 28h
0x14000dab5  pop     rdi
0x14000dab6  pop     rsi
0x14000dab7  pop     rbp
0x14000dab8  pop     rbx
0x14000dab9  retn
```
