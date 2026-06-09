# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400056a0`
- end: `0x14000573c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008cac`
- `0x14000a314`

## callees

- `0x1400056a0`
- `0x1400061e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400056b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400056b3`

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
0x1400056a0  push    rbx
0x1400056a2  push    rbp
0x1400056a3  push    rsi
0x1400056a4  push    rdi
0x1400056a5  sub     rsp, 28h
0x1400056a9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400056b0  mov     bpl, dl
0x1400056b3  call    cs:__imp_GetCurrentThreadId
0x1400056b9  mov     ebx, eax
0x1400056bb  mov     esi, eax
0x1400056bd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400056c7  shr     rbx, 2
0x1400056cb  mul     rbx
0x1400056ce  shr     rdx, 3
0x1400056d2  lea     rcx, [rdx+rdx*4]
0x1400056d6  add     rcx, rcx
0x1400056d9  sub     rbx, rcx
0x1400056dc  mov     rax, [rdi+rbx*8]
0x1400056e0  jmp     short loc_1400056EA
0x1400056e2  cmp     [rax], esi
0x1400056e4  jz      short loc_14000572B
0x1400056e6  mov     rax, [rax+8]
0x1400056ea  test    rax, rax
0x1400056ed  jnz     short loc_1400056E2
0x1400056ef  test    bpl, bpl
0x1400056f2  jz      short loc_140005731
0x1400056f4  lea     edx, [rax+18h]; dwBytes
0x1400056f7  xor     ecx, ecx; dwFlags
0x1400056f9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400056fe  mov     rcx, rax
0x140005701  test    rax, rax
0x140005704  jz      short loc_140005731
0x140005706  mov     [rax], esi
0x140005708  xor     eax, eax
0x14000570a  mov     [rcx+4], eax
0x14000570d  mov     [rcx+8], rax
0x140005711  mov     [rcx+10h], rax
0x140005715  mov     rax, [rdi+rbx*8]
0x140005719  mov     [rcx+8], rax
0x14000571d  lock cmpxchg [rdi+rbx*8], rcx
0x140005723  jnz     short loc_140005715
0x140005725  lea     rax, [rcx+10h]
0x140005729  jmp     short loc_140005733
0x14000572b  add     rax, 10h
0x14000572f  jmp     short loc_140005733
0x140005731  xor     eax, eax
0x140005733  add     rsp, 28h
0x140005737  pop     rdi
0x140005738  pop     rsi
0x140005739  pop     rbp
0x14000573a  pop     rbx
0x14000573b  retn
```
