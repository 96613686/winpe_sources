# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008988`
- end: `0x180008a24`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ca14`

## callees

- `0x180008988`
- `0x180009ccc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000899b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000899b`

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
0x180008988  push    rbx
0x18000898a  push    rbp
0x18000898b  push    rsi
0x18000898c  push    rdi
0x18000898d  sub     rsp, 28h
0x180008991  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008998  mov     bpl, dl
0x18000899b  call    cs:__imp_GetCurrentThreadId
0x1800089a1  mov     ebx, eax
0x1800089a3  mov     esi, eax
0x1800089a5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800089af  shr     rbx, 2
0x1800089b3  mul     rbx
0x1800089b6  shr     rdx, 3
0x1800089ba  lea     rcx, [rdx+rdx*4]
0x1800089be  add     rcx, rcx
0x1800089c1  sub     rbx, rcx
0x1800089c4  mov     rax, [rdi+rbx*8]
0x1800089c8  jmp     short loc_1800089D2
0x1800089ca  cmp     [rax], esi
0x1800089cc  jz      short loc_180008A13
0x1800089ce  mov     rax, [rax+8]
0x1800089d2  test    rax, rax
0x1800089d5  jnz     short loc_1800089CA
0x1800089d7  test    bpl, bpl
0x1800089da  jz      short loc_180008A19
0x1800089dc  lea     edx, [rax+18h]; dwBytes
0x1800089df  xor     ecx, ecx; dwFlags
0x1800089e1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800089e6  mov     rcx, rax
0x1800089e9  test    rax, rax
0x1800089ec  jz      short loc_180008A19
0x1800089ee  mov     [rax], esi
0x1800089f0  xor     eax, eax
0x1800089f2  mov     [rcx+4], eax
0x1800089f5  mov     [rcx+8], rax
0x1800089f9  mov     [rcx+10h], rax
0x1800089fd  mov     rax, [rdi+rbx*8]
0x180008a01  mov     [rcx+8], rax
0x180008a05  lock cmpxchg [rdi+rbx*8], rcx
0x180008a0b  jnz     short loc_1800089FD
0x180008a0d  lea     rax, [rcx+10h]
0x180008a11  jmp     short loc_180008A1B
0x180008a13  add     rax, 10h
0x180008a17  jmp     short loc_180008A1B
0x180008a19  xor     eax, eax
0x180008a1b  add     rsp, 28h
0x180008a1f  pop     rdi
0x180008a20  pop     rsi
0x180008a21  pop     rbp
0x180008a22  pop     rbx
0x180008a23  retn
```
