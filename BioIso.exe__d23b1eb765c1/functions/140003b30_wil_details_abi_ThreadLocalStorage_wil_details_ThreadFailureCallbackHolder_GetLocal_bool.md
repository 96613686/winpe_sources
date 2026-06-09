# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140003b30`
- end: `0x140003be6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `182`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140026548`

## callees

- `0x140003b30`
- `0x140027708`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003b43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003b43`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v5; // r8
  __int64 v6; // rsi
  __int64 i; // rax
  DWORD *v9; // rax
  signed __int64 v10; // rcx
  signed __int64 v11; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  v6 = 8 * v5;
  for ( i = *(_QWORD *)(8 * v5 + v2); i; i = *(_QWORD *)(i + 8) )
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
    v11 = *(_QWORD *)(v6 + v2);
    *(_QWORD *)(v10 + 8) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + v2), v10, v11) );
  return v10 + 16;
}

```

## disassembly

```asm
0x140003b30  push    rbx
0x140003b32  push    rbp
0x140003b33  push    rsi
0x140003b34  push    rdi
0x140003b35  sub     rsp, 28h
0x140003b39  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003b40  movzx   ebp, dl
0x140003b43  call    cs:__imp_GetCurrentThreadId
0x140003b4a  nop     dword ptr [rax+rax+00h]
0x140003b4f  mov     r8d, eax
0x140003b52  mov     ebx, eax
0x140003b54  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003b5e  shr     r8, 2
0x140003b62  mul     r8
0x140003b65  shr     rdx, 3
0x140003b69  lea     rcx, [rdx+rdx*4]
0x140003b6d  add     rcx, rcx
0x140003b70  sub     r8, rcx; unsigned __int64
0x140003b73  lea     rsi, ds:0[r8*8]
0x140003b7b  mov     rax, [rsi+rdi]
0x140003b7f  test    rax, rax
0x140003b82  jz      short loc_140003B9C
0x140003b84  cmp     [rax], ebx
0x140003b86  jz      short loc_140003B8E
0x140003b88  mov     rax, [rax+8]
0x140003b8c  jmp     short loc_140003B7F
0x140003b8e  add     rax, 10h
0x140003b92  add     rsp, 28h
0x140003b96  pop     rdi
0x140003b97  pop     rsi
0x140003b98  pop     rbp
0x140003b99  pop     rbx
0x140003b9a  retn
0x140003b9c  test    bpl, bpl
0x140003b9f  jz      short loc_140003BDA
0x140003ba1  mov     edx, 18h; dwBytes
0x140003ba6  xor     ecx, ecx; dwFlags
0x140003ba8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003bad  mov     rcx, rax
0x140003bb0  test    rax, rax
0x140003bb3  jz      short loc_140003BDA
0x140003bb5  mov     [rax], ebx
0x140003bb7  xor     eax, eax
0x140003bb9  mov     [rcx+4], eax
0x140003bbc  mov     [rcx+8], rax
0x140003bc0  mov     [rcx+10h], rax
0x140003bc4  mov     rax, [rsi+rdi]
0x140003bc8  mov     [rcx+8], rax
0x140003bcc  lock cmpxchg [rsi+rdi], rcx
0x140003bd2  jnz     short loc_140003BC4
0x140003bd4  lea     rax, [rcx+10h]
0x140003bd8  jmp     short loc_140003BDC
0x140003bda  xor     eax, eax
0x140003bdc  add     rsp, 28h
0x140003be0  pop     rdi
0x140003be1  pop     rsi
0x140003be2  pop     rbp
0x140003be3  pop     rbx
0x140003be4  retn
```
