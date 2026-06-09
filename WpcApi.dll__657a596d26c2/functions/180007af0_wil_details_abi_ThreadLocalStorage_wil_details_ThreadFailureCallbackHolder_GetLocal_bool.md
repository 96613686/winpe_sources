# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007af0`
- end: `0x180007b8c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012a30`
- `0x180012ba8`
- `0x180012d20`
- `0x180012e98`
- `0x180020720`

## callees

- `0x180007af0`
- `0x180008b08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b03`

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
0x180007af0  push    rbx
0x180007af2  push    rbp
0x180007af3  push    rsi
0x180007af4  push    rdi
0x180007af5  sub     rsp, 28h
0x180007af9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007b00  mov     bpl, dl
0x180007b03  call    cs:__imp_GetCurrentThreadId
0x180007b09  mov     ebx, eax
0x180007b0b  mov     esi, eax
0x180007b0d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007b17  shr     rbx, 2
0x180007b1b  mul     rbx
0x180007b1e  shr     rdx, 3
0x180007b22  lea     rcx, [rdx+rdx*4]
0x180007b26  add     rcx, rcx
0x180007b29  sub     rbx, rcx
0x180007b2c  mov     rax, [rdi+rbx*8]
0x180007b30  jmp     short loc_180007B3A
0x180007b32  cmp     [rax], esi
0x180007b34  jz      short loc_180007B7B
0x180007b36  mov     rax, [rax+8]
0x180007b3a  test    rax, rax
0x180007b3d  jnz     short loc_180007B32
0x180007b3f  test    bpl, bpl
0x180007b42  jz      short loc_180007B81
0x180007b44  lea     edx, [rax+18h]; dwBytes
0x180007b47  xor     ecx, ecx; dwFlags
0x180007b49  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007b4e  mov     rcx, rax
0x180007b51  test    rax, rax
0x180007b54  jz      short loc_180007B81
0x180007b56  mov     [rax], esi
0x180007b58  xor     eax, eax
0x180007b5a  mov     [rcx+4], eax
0x180007b5d  mov     [rcx+8], rax
0x180007b61  mov     [rcx+10h], rax
0x180007b65  mov     rax, [rdi+rbx*8]
0x180007b69  mov     [rcx+8], rax
0x180007b6d  lock cmpxchg [rdi+rbx*8], rcx
0x180007b73  jnz     short loc_180007B65
0x180007b75  lea     rax, [rcx+10h]
0x180007b79  jmp     short loc_180007B83
0x180007b7b  add     rax, 10h
0x180007b7f  jmp     short loc_180007B83
0x180007b81  xor     eax, eax
0x180007b83  add     rsp, 28h
0x180007b87  pop     rdi
0x180007b88  pop     rsi
0x180007b89  pop     rbp
0x180007b8a  pop     rbx
0x180007b8b  retn
```
