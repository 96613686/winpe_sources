# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000783c`
- end: `0x1800078da`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000734c`
- `0x180040cd0`

## callees

- `0x18000783c`
- `0x180008ee8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000784f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000784f`

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
0x18000783c  push    rbx
0x18000783e  push    rbp
0x18000783f  push    rsi
0x180007840  push    rdi
0x180007841  sub     rsp, 28h
0x180007845  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000784c  mov     bpl, dl
0x18000784f  call    cs:__imp_GetCurrentThreadId
0x180007855  mov     ebx, eax
0x180007857  mov     esi, eax
0x180007859  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007863  shr     rbx, 2
0x180007867  mul     rbx
0x18000786a  shr     rdx, 3
0x18000786e  lea     rcx, [rdx+rdx*4]
0x180007872  add     rcx, rcx
0x180007875  sub     rbx, rcx
0x180007878  mov     rax, [rdi+rbx*8]
0x18000787c  test    rax, rax
0x18000787f  jz      short loc_180007891
0x180007881  cmp     [rax], esi
0x180007883  jz      short loc_18000788B
0x180007885  mov     rax, [rax+8]
0x180007889  jmp     short loc_18000787C
0x18000788b  add     rax, 10h
0x18000788f  jmp     short loc_1800078D1
0x180007891  test    bpl, bpl
0x180007894  jz      short loc_1800078CF
0x180007896  mov     edx, 18h; dwBytes
0x18000789b  xor     ecx, ecx; dwFlags
0x18000789d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800078a2  mov     rcx, rax
0x1800078a5  test    rax, rax
0x1800078a8  jz      short loc_1800078CF
0x1800078aa  mov     [rax], esi
0x1800078ac  xor     eax, eax
0x1800078ae  mov     [rcx+4], eax
0x1800078b1  mov     [rcx+8], rax
0x1800078b5  mov     [rcx+10h], rax
0x1800078b9  mov     rax, [rdi+rbx*8]
0x1800078bd  mov     [rcx+8], rax
0x1800078c1  lock cmpxchg [rdi+rbx*8], rcx
0x1800078c7  jnz     short loc_1800078B9
0x1800078c9  lea     rax, [rcx+10h]
0x1800078cd  jmp     short loc_1800078D1
0x1800078cf  xor     eax, eax
0x1800078d1  add     rsp, 28h
0x1800078d5  pop     rdi
0x1800078d6  pop     rsi
0x1800078d7  pop     rbp
0x1800078d8  pop     rbx
0x1800078d9  retn
```
