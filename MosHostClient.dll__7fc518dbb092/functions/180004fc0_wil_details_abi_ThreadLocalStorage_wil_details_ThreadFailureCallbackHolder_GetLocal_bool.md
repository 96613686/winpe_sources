# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180004fc0`
- end: `0x18000505c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b28c`

## callees

- `0x180004fc0`
- `0x180005bac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fd3`

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
0x180004fc0  push    rbx
0x180004fc2  push    rbp
0x180004fc3  push    rsi
0x180004fc4  push    rdi
0x180004fc5  sub     rsp, 28h
0x180004fc9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004fd0  mov     bpl, dl
0x180004fd3  call    cs:__imp_GetCurrentThreadId
0x180004fd9  mov     ebx, eax
0x180004fdb  mov     esi, eax
0x180004fdd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004fe7  shr     rbx, 2
0x180004feb  mul     rbx
0x180004fee  shr     rdx, 3
0x180004ff2  lea     rcx, [rdx+rdx*4]
0x180004ff6  add     rcx, rcx
0x180004ff9  sub     rbx, rcx
0x180004ffc  mov     rax, [rdi+rbx*8]
0x180005000  jmp     short loc_18000500A
0x180005002  cmp     [rax], esi
0x180005004  jz      short loc_18000504B
0x180005006  mov     rax, [rax+8]
0x18000500a  test    rax, rax
0x18000500d  jnz     short loc_180005002
0x18000500f  test    bpl, bpl
0x180005012  jz      short loc_180005051
0x180005014  lea     edx, [rax+18h]; dwBytes
0x180005017  xor     ecx, ecx; dwFlags
0x180005019  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000501e  mov     rcx, rax
0x180005021  test    rax, rax
0x180005024  jz      short loc_180005051
0x180005026  mov     [rax], esi
0x180005028  xor     eax, eax
0x18000502a  mov     [rcx+4], eax
0x18000502d  mov     [rcx+8], rax
0x180005031  mov     [rcx+10h], rax
0x180005035  mov     rax, [rdi+rbx*8]
0x180005039  mov     [rcx+8], rax
0x18000503d  lock cmpxchg [rdi+rbx*8], rcx
0x180005043  jnz     short loc_180005035
0x180005045  lea     rax, [rcx+10h]
0x180005049  jmp     short loc_180005053
0x18000504b  add     rax, 10h
0x18000504f  jmp     short loc_180005053
0x180005051  xor     eax, eax
0x180005053  add     rsp, 28h
0x180005057  pop     rdi
0x180005058  pop     rsi
0x180005059  pop     rbp
0x18000505a  pop     rbx
0x18000505b  retn
```
