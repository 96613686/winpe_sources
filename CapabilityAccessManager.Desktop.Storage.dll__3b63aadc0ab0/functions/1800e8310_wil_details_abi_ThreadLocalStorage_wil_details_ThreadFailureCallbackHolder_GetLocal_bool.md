# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800e8310`
- end: `0x1800e83ac`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800ed544`
- `0x1800ed5f0`
- `0x1800fc0cc`
- `0x180108d14`

## callees

- `0x1800e8310`
- `0x1800e90b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e8323`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e8323`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800e8310  push    rbx
0x1800e8312  push    rbp
0x1800e8313  push    rsi
0x1800e8314  push    rdi
0x1800e8315  sub     rsp, 28h
0x1800e8319  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800e8320  mov     bpl, dl
0x1800e8323  call    cs:__imp_GetCurrentThreadId
0x1800e8329  mov     ebx, eax
0x1800e832b  mov     esi, eax
0x1800e832d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800e8337  shr     rbx, 2
0x1800e833b  mul     rbx
0x1800e833e  shr     rdx, 3
0x1800e8342  lea     rcx, [rdx+rdx*4]
0x1800e8346  add     rcx, rcx
0x1800e8349  sub     rbx, rcx
0x1800e834c  mov     rax, [rdi+rbx*8]
0x1800e8350  jmp     short loc_1800E835A
0x1800e8352  cmp     [rax], esi
0x1800e8354  jz      short loc_1800E839B
0x1800e8356  mov     rax, [rax+8]
0x1800e835a  test    rax, rax
0x1800e835d  jnz     short loc_1800E8352
0x1800e835f  test    bpl, bpl
0x1800e8362  jz      short loc_1800E83A1
0x1800e8364  lea     edx, [rax+18h]; dwBytes
0x1800e8367  xor     ecx, ecx; dwFlags
0x1800e8369  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800e836e  mov     rcx, rax
0x1800e8371  test    rax, rax
0x1800e8374  jz      short loc_1800E83A1
0x1800e8376  mov     [rax], esi
0x1800e8378  xor     eax, eax
0x1800e837a  mov     [rcx+4], eax
0x1800e837d  mov     [rcx+8], rax
0x1800e8381  mov     [rcx+10h], rax
0x1800e8385  mov     rax, [rdi+rbx*8]
0x1800e8389  mov     [rcx+8], rax
0x1800e838d  lock cmpxchg [rdi+rbx*8], rcx
0x1800e8393  jnz     short loc_1800E8385
0x1800e8395  lea     rax, [rcx+10h]
0x1800e8399  jmp     short loc_1800E83A3
0x1800e839b  add     rax, 10h
0x1800e839f  jmp     short loc_1800E83A3
0x1800e83a1  xor     eax, eax
0x1800e83a3  add     rsp, 28h
0x1800e83a7  pop     rdi
0x1800e83a8  pop     rsi
0x1800e83a9  pop     rbp
0x1800e83aa  pop     rbx
0x1800e83ab  retn
```
