# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800060ec`
- end: `0x18000618a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005c14`
- `0x18001b614`

## callees

- `0x1800060ec`
- `0x180006c98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060ff`

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
0x1800060ec  push    rbx
0x1800060ee  push    rbp
0x1800060ef  push    rsi
0x1800060f0  push    rdi
0x1800060f1  sub     rsp, 28h
0x1800060f5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800060fc  mov     bpl, dl
0x1800060ff  call    cs:__imp_GetCurrentThreadId
0x180006105  mov     ebx, eax
0x180006107  mov     esi, eax
0x180006109  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006113  shr     rbx, 2
0x180006117  mul     rbx
0x18000611a  shr     rdx, 3
0x18000611e  lea     rcx, [rdx+rdx*4]
0x180006122  add     rcx, rcx
0x180006125  sub     rbx, rcx
0x180006128  mov     rax, [rdi+rbx*8]
0x18000612c  test    rax, rax
0x18000612f  jz      short loc_180006141
0x180006131  cmp     [rax], esi
0x180006133  jz      short loc_18000613B
0x180006135  mov     rax, [rax+8]
0x180006139  jmp     short loc_18000612C
0x18000613b  add     rax, 10h
0x18000613f  jmp     short loc_180006181
0x180006141  test    bpl, bpl
0x180006144  jz      short loc_18000617F
0x180006146  mov     edx, 18h; dwBytes
0x18000614b  xor     ecx, ecx; dwFlags
0x18000614d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006152  mov     rcx, rax
0x180006155  test    rax, rax
0x180006158  jz      short loc_18000617F
0x18000615a  mov     [rax], esi
0x18000615c  xor     eax, eax
0x18000615e  mov     [rcx+4], eax
0x180006161  mov     [rcx+8], rax
0x180006165  mov     [rcx+10h], rax
0x180006169  mov     rax, [rdi+rbx*8]
0x18000616d  mov     [rcx+8], rax
0x180006171  lock cmpxchg [rdi+rbx*8], rcx
0x180006177  jnz     short loc_180006169
0x180006179  lea     rax, [rcx+10h]
0x18000617d  jmp     short loc_180006181
0x18000617f  xor     eax, eax
0x180006181  add     rsp, 28h
0x180006185  pop     rdi
0x180006186  pop     rsi
0x180006187  pop     rbp
0x180006188  pop     rbx
0x180006189  retn
```
