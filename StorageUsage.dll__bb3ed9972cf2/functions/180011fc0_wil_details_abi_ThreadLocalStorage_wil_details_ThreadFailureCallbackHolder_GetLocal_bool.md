# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180011fc0`
- end: `0x18001205e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800119e0`
- `0x180029a38`

## callees

- `0x180011fc0`
- `0x180014268`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011fd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011fd3`

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
0x180011fc0  push    rbx
0x180011fc2  push    rbp
0x180011fc3  push    rsi
0x180011fc4  push    rdi
0x180011fc5  sub     rsp, 28h
0x180011fc9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011fd0  mov     bpl, dl
0x180011fd3  call    cs:__imp_GetCurrentThreadId
0x180011fd9  mov     ebx, eax
0x180011fdb  mov     esi, eax
0x180011fdd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180011fe7  shr     rbx, 2
0x180011feb  mul     rbx
0x180011fee  shr     rdx, 3
0x180011ff2  lea     rcx, [rdx+rdx*4]
0x180011ff6  add     rcx, rcx
0x180011ff9  sub     rbx, rcx
0x180011ffc  mov     rax, [rdi+rbx*8]
0x180012000  test    rax, rax
0x180012003  jz      short loc_180012015
0x180012005  cmp     [rax], esi
0x180012007  jz      short loc_18001200F
0x180012009  mov     rax, [rax+8]
0x18001200d  jmp     short loc_180012000
0x18001200f  add     rax, 10h
0x180012013  jmp     short loc_180012055
0x180012015  test    bpl, bpl
0x180012018  jz      short loc_180012053
0x18001201a  mov     edx, 18h; dwBytes
0x18001201f  xor     ecx, ecx; dwFlags
0x180012021  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180012026  mov     rcx, rax
0x180012029  test    rax, rax
0x18001202c  jz      short loc_180012053
0x18001202e  mov     [rax], esi
0x180012030  xor     eax, eax
0x180012032  mov     [rcx+4], eax
0x180012035  mov     [rcx+8], rax
0x180012039  mov     [rcx+10h], rax
0x18001203d  mov     rax, [rdi+rbx*8]
0x180012041  mov     [rcx+8], rax
0x180012045  lock cmpxchg [rdi+rbx*8], rcx
0x18001204b  jnz     short loc_18001203D
0x18001204d  lea     rax, [rcx+10h]
0x180012051  jmp     short loc_180012055
0x180012053  xor     eax, eax
0x180012055  add     rsp, 28h
0x180012059  pop     rdi
0x18001205a  pop     rsi
0x18001205b  pop     rbp
0x18001205c  pop     rbx
0x18001205d  retn
```
