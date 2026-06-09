# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006f6c`
- end: `0x18000700a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006a94`
- `0x1800107b0`

## callees

- `0x180006f6c`
- `0x1800082d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f7f`

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
0x180006f6c  push    rbx
0x180006f6e  push    rbp
0x180006f6f  push    rsi
0x180006f70  push    rdi
0x180006f71  sub     rsp, 28h
0x180006f75  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006f7c  mov     bpl, dl
0x180006f7f  call    cs:__imp_GetCurrentThreadId
0x180006f85  mov     ebx, eax
0x180006f87  mov     esi, eax
0x180006f89  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006f93  shr     rbx, 2
0x180006f97  mul     rbx
0x180006f9a  shr     rdx, 3
0x180006f9e  lea     rcx, [rdx+rdx*4]
0x180006fa2  add     rcx, rcx
0x180006fa5  sub     rbx, rcx
0x180006fa8  mov     rax, [rdi+rbx*8]
0x180006fac  test    rax, rax
0x180006faf  jz      short loc_180006FC1
0x180006fb1  cmp     [rax], esi
0x180006fb3  jz      short loc_180006FBB
0x180006fb5  mov     rax, [rax+8]
0x180006fb9  jmp     short loc_180006FAC
0x180006fbb  add     rax, 10h
0x180006fbf  jmp     short loc_180007001
0x180006fc1  test    bpl, bpl
0x180006fc4  jz      short loc_180006FFF
0x180006fc6  mov     edx, 18h; dwBytes
0x180006fcb  xor     ecx, ecx; dwFlags
0x180006fcd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006fd2  mov     rcx, rax
0x180006fd5  test    rax, rax
0x180006fd8  jz      short loc_180006FFF
0x180006fda  mov     [rax], esi
0x180006fdc  xor     eax, eax
0x180006fde  mov     [rcx+4], eax
0x180006fe1  mov     [rcx+8], rax
0x180006fe5  mov     [rcx+10h], rax
0x180006fe9  mov     rax, [rdi+rbx*8]
0x180006fed  mov     [rcx+8], rax
0x180006ff1  lock cmpxchg [rdi+rbx*8], rcx
0x180006ff7  jnz     short loc_180006FE9
0x180006ff9  lea     rax, [rcx+10h]
0x180006ffd  jmp     short loc_180007001
0x180006fff  xor     eax, eax
0x180007001  add     rsp, 28h
0x180007005  pop     rdi
0x180007006  pop     rsi
0x180007007  pop     rbp
0x180007008  pop     rbx
0x180007009  retn
```
