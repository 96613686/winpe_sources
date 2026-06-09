# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007990`
- end: `0x180007a2c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a2e4`
- `0x18002a440`
- `0x18002a648`
- `0x18002a7a4`
- `0x18002a924`

## callees

- `0x180007990`
- `0x1800088e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079a3`

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
0x180007990  push    rbx
0x180007992  push    rbp
0x180007993  push    rsi
0x180007994  push    rdi
0x180007995  sub     rsp, 28h
0x180007999  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800079a0  mov     bpl, dl
0x1800079a3  call    cs:__imp_GetCurrentThreadId
0x1800079a9  mov     ebx, eax
0x1800079ab  mov     esi, eax
0x1800079ad  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800079b7  shr     rbx, 2
0x1800079bb  mul     rbx
0x1800079be  shr     rdx, 3
0x1800079c2  lea     rcx, [rdx+rdx*4]
0x1800079c6  add     rcx, rcx
0x1800079c9  sub     rbx, rcx
0x1800079cc  mov     rax, [rdi+rbx*8]
0x1800079d0  jmp     short loc_1800079DA
0x1800079d2  cmp     [rax], esi
0x1800079d4  jz      short loc_180007A1B
0x1800079d6  mov     rax, [rax+8]
0x1800079da  test    rax, rax
0x1800079dd  jnz     short loc_1800079D2
0x1800079df  test    bpl, bpl
0x1800079e2  jz      short loc_180007A21
0x1800079e4  lea     edx, [rax+18h]; dwBytes
0x1800079e7  xor     ecx, ecx; dwFlags
0x1800079e9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800079ee  mov     rcx, rax
0x1800079f1  test    rax, rax
0x1800079f4  jz      short loc_180007A21
0x1800079f6  mov     [rax], esi
0x1800079f8  xor     eax, eax
0x1800079fa  mov     [rcx+4], eax
0x1800079fd  mov     [rcx+8], rax
0x180007a01  mov     [rcx+10h], rax
0x180007a05  mov     rax, [rdi+rbx*8]
0x180007a09  mov     [rcx+8], rax
0x180007a0d  lock cmpxchg [rdi+rbx*8], rcx
0x180007a13  jnz     short loc_180007A05
0x180007a15  lea     rax, [rcx+10h]
0x180007a19  jmp     short loc_180007A23
0x180007a1b  add     rax, 10h
0x180007a1f  jmp     short loc_180007A23
0x180007a21  xor     eax, eax
0x180007a23  add     rsp, 28h
0x180007a27  pop     rdi
0x180007a28  pop     rsi
0x180007a29  pop     rbp
0x180007a2a  pop     rbx
0x180007a2b  retn
```
