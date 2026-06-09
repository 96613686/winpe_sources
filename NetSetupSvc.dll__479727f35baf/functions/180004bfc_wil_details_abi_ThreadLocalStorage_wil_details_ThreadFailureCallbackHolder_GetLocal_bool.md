# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180004bfc`
- end: `0x180004c9a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004728`
- `0x180014d60`

## callees

- `0x180004bfc`
- `0x1800058b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c0f`

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
0x180004bfc  push    rbx
0x180004bfe  push    rbp
0x180004bff  push    rsi
0x180004c00  push    rdi
0x180004c01  sub     rsp, 28h
0x180004c05  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004c0c  mov     bpl, dl
0x180004c0f  call    cs:__imp_GetCurrentThreadId
0x180004c15  mov     ebx, eax
0x180004c17  mov     esi, eax
0x180004c19  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004c23  shr     rbx, 2
0x180004c27  mul     rbx
0x180004c2a  shr     rdx, 3
0x180004c2e  lea     rcx, [rdx+rdx*4]
0x180004c32  add     rcx, rcx
0x180004c35  sub     rbx, rcx
0x180004c38  mov     rax, [rdi+rbx*8]
0x180004c3c  test    rax, rax
0x180004c3f  jz      short loc_180004C51
0x180004c41  cmp     [rax], esi
0x180004c43  jz      short loc_180004C4B
0x180004c45  mov     rax, [rax+8]
0x180004c49  jmp     short loc_180004C3C
0x180004c4b  add     rax, 10h
0x180004c4f  jmp     short loc_180004C91
0x180004c51  test    bpl, bpl
0x180004c54  jz      short loc_180004C8F
0x180004c56  mov     edx, 18h; dwBytes
0x180004c5b  xor     ecx, ecx; dwFlags
0x180004c5d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004c62  mov     rcx, rax
0x180004c65  test    rax, rax
0x180004c68  jz      short loc_180004C8F
0x180004c6a  mov     [rax], esi
0x180004c6c  xor     eax, eax
0x180004c6e  mov     [rcx+4], eax
0x180004c71  mov     [rcx+8], rax
0x180004c75  mov     [rcx+10h], rax
0x180004c79  mov     rax, [rdi+rbx*8]
0x180004c7d  mov     [rcx+8], rax
0x180004c81  lock cmpxchg [rdi+rbx*8], rcx
0x180004c87  jnz     short loc_180004C79
0x180004c89  lea     rax, [rcx+10h]
0x180004c8d  jmp     short loc_180004C91
0x180004c8f  xor     eax, eax
0x180004c91  add     rsp, 28h
0x180004c95  pop     rdi
0x180004c96  pop     rsi
0x180004c97  pop     rbp
0x180004c98  pop     rbx
0x180004c99  retn
```
