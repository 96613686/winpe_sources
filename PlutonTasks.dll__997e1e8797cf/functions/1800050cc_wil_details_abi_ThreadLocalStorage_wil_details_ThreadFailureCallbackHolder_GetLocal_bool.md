# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800050cc`
- end: `0x18000516a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004bf8`

## callees

- `0x1800050cc`
- `0x1800062c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050df`

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
0x1800050cc  push    rbx
0x1800050ce  push    rbp
0x1800050cf  push    rsi
0x1800050d0  push    rdi
0x1800050d1  sub     rsp, 28h
0x1800050d5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800050dc  mov     bpl, dl
0x1800050df  call    cs:__imp_GetCurrentThreadId
0x1800050e5  mov     ebx, eax
0x1800050e7  mov     esi, eax
0x1800050e9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800050f3  shr     rbx, 2
0x1800050f7  mul     rbx
0x1800050fa  shr     rdx, 3
0x1800050fe  lea     rcx, [rdx+rdx*4]
0x180005102  add     rcx, rcx
0x180005105  sub     rbx, rcx
0x180005108  mov     rax, [rdi+rbx*8]
0x18000510c  test    rax, rax
0x18000510f  jz      short loc_180005121
0x180005111  cmp     [rax], esi
0x180005113  jz      short loc_18000511B
0x180005115  mov     rax, [rax+8]
0x180005119  jmp     short loc_18000510C
0x18000511b  add     rax, 10h
0x18000511f  jmp     short loc_180005161
0x180005121  test    bpl, bpl
0x180005124  jz      short loc_18000515F
0x180005126  mov     edx, 18h; dwBytes
0x18000512b  xor     ecx, ecx; dwFlags
0x18000512d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005132  mov     rcx, rax
0x180005135  test    rax, rax
0x180005138  jz      short loc_18000515F
0x18000513a  mov     [rax], esi
0x18000513c  xor     eax, eax
0x18000513e  mov     [rcx+4], eax
0x180005141  mov     [rcx+8], rax
0x180005145  mov     [rcx+10h], rax
0x180005149  mov     rax, [rdi+rbx*8]
0x18000514d  mov     [rcx+8], rax
0x180005151  lock cmpxchg [rdi+rbx*8], rcx
0x180005157  jnz     short loc_180005149
0x180005159  lea     rax, [rcx+10h]
0x18000515d  jmp     short loc_180005161
0x18000515f  xor     eax, eax
0x180005161  add     rsp, 28h
0x180005165  pop     rdi
0x180005166  pop     rsi
0x180005167  pop     rbp
0x180005168  pop     rbx
0x180005169  retn
```
