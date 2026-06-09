# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800046ac`
- end: `0x180004748`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006654`

## callees

- `0x1800046ac`
- `0x1800056bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046bf`

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
0x1800046ac  push    rbx
0x1800046ae  push    rbp
0x1800046af  push    rsi
0x1800046b0  push    rdi
0x1800046b1  sub     rsp, 28h
0x1800046b5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800046bc  mov     bpl, dl
0x1800046bf  call    cs:__imp_GetCurrentThreadId
0x1800046c5  mov     ebx, eax
0x1800046c7  mov     esi, eax
0x1800046c9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800046d3  shr     rbx, 2
0x1800046d7  mul     rbx
0x1800046da  shr     rdx, 3
0x1800046de  lea     rcx, [rdx+rdx*4]
0x1800046e2  add     rcx, rcx
0x1800046e5  sub     rbx, rcx
0x1800046e8  mov     rax, [rdi+rbx*8]
0x1800046ec  jmp     short loc_1800046F6
0x1800046ee  cmp     [rax], esi
0x1800046f0  jz      short loc_180004737
0x1800046f2  mov     rax, [rax+8]
0x1800046f6  test    rax, rax
0x1800046f9  jnz     short loc_1800046EE
0x1800046fb  test    bpl, bpl
0x1800046fe  jz      short loc_18000473D
0x180004700  lea     edx, [rax+18h]; dwBytes
0x180004703  xor     ecx, ecx; dwFlags
0x180004705  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000470a  mov     rcx, rax
0x18000470d  test    rax, rax
0x180004710  jz      short loc_18000473D
0x180004712  mov     [rax], esi
0x180004714  xor     eax, eax
0x180004716  mov     [rcx+4], eax
0x180004719  mov     [rcx+8], rax
0x18000471d  mov     [rcx+10h], rax
0x180004721  mov     rax, [rdi+rbx*8]
0x180004725  mov     [rcx+8], rax
0x180004729  lock cmpxchg [rdi+rbx*8], rcx
0x18000472f  jnz     short loc_180004721
0x180004731  lea     rax, [rcx+10h]
0x180004735  jmp     short loc_18000473F
0x180004737  add     rax, 10h
0x18000473b  jmp     short loc_18000473F
0x18000473d  xor     eax, eax
0x18000473f  add     rsp, 28h
0x180004743  pop     rdi
0x180004744  pop     rsi
0x180004745  pop     rbp
0x180004746  pop     rbx
0x180004747  retn
```
