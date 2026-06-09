# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007e0c`
- end: `0x180007eaa`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007c10`
- `0x18000e794`

## callees

- `0x180007e0c`
- `0x18000879c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e1f`

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
0x180007e0c  push    rbx
0x180007e0e  push    rbp
0x180007e0f  push    rsi
0x180007e10  push    rdi
0x180007e11  sub     rsp, 28h
0x180007e15  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007e1c  mov     bpl, dl
0x180007e1f  call    cs:__imp_GetCurrentThreadId
0x180007e25  mov     ebx, eax
0x180007e27  mov     esi, eax
0x180007e29  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007e33  shr     rbx, 2
0x180007e37  mul     rbx
0x180007e3a  shr     rdx, 3
0x180007e3e  lea     rcx, [rdx+rdx*4]
0x180007e42  add     rcx, rcx
0x180007e45  sub     rbx, rcx
0x180007e48  mov     rax, [rdi+rbx*8]
0x180007e4c  test    rax, rax
0x180007e4f  jz      short loc_180007E61
0x180007e51  cmp     [rax], esi
0x180007e53  jz      short loc_180007E5B
0x180007e55  mov     rax, [rax+8]
0x180007e59  jmp     short loc_180007E4C
0x180007e5b  add     rax, 10h
0x180007e5f  jmp     short loc_180007EA1
0x180007e61  test    bpl, bpl
0x180007e64  jz      short loc_180007E9F
0x180007e66  mov     edx, 18h; dwBytes
0x180007e6b  xor     ecx, ecx; dwFlags
0x180007e6d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007e72  mov     rcx, rax
0x180007e75  test    rax, rax
0x180007e78  jz      short loc_180007E9F
0x180007e7a  mov     [rax], esi
0x180007e7c  xor     eax, eax
0x180007e7e  mov     [rcx+4], eax
0x180007e81  mov     [rcx+8], rax
0x180007e85  mov     [rcx+10h], rax
0x180007e89  mov     rax, [rdi+rbx*8]
0x180007e8d  mov     [rcx+8], rax
0x180007e91  lock cmpxchg [rdi+rbx*8], rcx
0x180007e97  jnz     short loc_180007E89
0x180007e99  lea     rax, [rcx+10h]
0x180007e9d  jmp     short loc_180007EA1
0x180007e9f  xor     eax, eax
0x180007ea1  add     rsp, 28h
0x180007ea5  pop     rdi
0x180007ea6  pop     rsi
0x180007ea7  pop     rbp
0x180007ea8  pop     rbx
0x180007ea9  retn
```
