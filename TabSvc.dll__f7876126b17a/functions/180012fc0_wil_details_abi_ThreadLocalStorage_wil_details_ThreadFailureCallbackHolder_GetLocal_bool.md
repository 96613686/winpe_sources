# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180012fc0`
- end: `0x18001306e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `174`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ec9c`
- `0x180021990`

## callees

- `0x180012fc0`
- `0x180024860`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012fd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012fd3`

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
0x180012fc0  push    rbx
0x180012fc2  push    rbp
0x180012fc3  push    rsi
0x180012fc4  push    rdi
0x180012fc5  sub     rsp, 28h
0x180012fc9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012fd0  movzx   ebp, dl
0x180012fd3  call    cs:__imp_GetCurrentThreadId
0x180012fd9  mov     r8d, eax
0x180012fdc  mov     ebx, eax
0x180012fde  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180012fe8  shr     r8, 2
0x180012fec  mul     r8
0x180012fef  shr     rdx, 3
0x180012ff3  lea     rcx, [rdx+rdx*4]
0x180012ff7  add     rcx, rcx
0x180012ffa  sub     r8, rcx; unsigned __int64
0x180012ffd  lea     rsi, ds:0[r8*8]
0x180013005  mov     rax, [rsi+rdi]
0x180013009  test    rax, rax
0x18001300c  jz      short loc_180013025
0x18001300e  cmp     [rax], ebx
0x180013010  jz      short loc_180013018
0x180013012  mov     rax, [rax+8]
0x180013016  jmp     short loc_180013009
0x180013018  add     rax, 10h
0x18001301c  add     rsp, 28h
0x180013020  pop     rdi
0x180013021  pop     rsi
0x180013022  pop     rbp
0x180013023  pop     rbx
0x180013024  retn
0x180013025  test    bpl, bpl
0x180013028  jz      short loc_180013063
0x18001302a  mov     edx, 18h; dwBytes
0x18001302f  xor     ecx, ecx; dwFlags
0x180013031  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013036  mov     rcx, rax
0x180013039  test    rax, rax
0x18001303c  jz      short loc_180013063
0x18001303e  mov     [rax], ebx
0x180013040  xor     eax, eax
0x180013042  mov     [rcx+4], eax
0x180013045  mov     [rcx+8], rax
0x180013049  mov     [rcx+10h], rax
0x18001304d  mov     rax, [rsi+rdi]
0x180013051  mov     [rcx+8], rax
0x180013055  lock cmpxchg [rsi+rdi], rcx
0x18001305b  jnz     short loc_18001304D
0x18001305d  lea     rax, [rcx+10h]
0x180013061  jmp     short loc_180013065
0x180013063  xor     eax, eax
0x180013065  add     rsp, 28h
0x180013069  pop     rdi
0x18001306a  pop     rsi
0x18001306b  pop     rbp
0x18001306c  pop     rbx
0x18001306d  retn
```
