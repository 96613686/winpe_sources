# CreateTlgAggregateSession

- ea: `0x180022480`
- end: `0x18002253d`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023070`

## callees

- `0x180022480`
- `0x180022544`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800224c8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800224c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800224ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800224ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002249a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002249a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800224ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800224ea`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_18005FA08 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    DestroyAggregateSession(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180022480  mov     [rsp+arg_0], rbx
0x180022485  mov     [rsp+arg_18], rsi
0x18002248a  push    rdi
0x18002248b  sub     rsp, 20h
0x18002248f  mov     sil, cl
0x180022492  xor     dil, dil
0x180022495  mov     [rsp+28h+arg_8], dil
0x18002249a  call    cs:__imp_GetProcessHeap
0x1800224a0  mov     rcx, rax; hHeap
0x1800224a3  mov     edx, 8; dwFlags
0x1800224a8  mov     r8d, 168h; dwBytes
0x1800224ae  call    cs:__imp_HeapAlloc
0x1800224b4  mov     rbx, rax
0x1800224b7  mov     [rsp+28h+arg_10], rax
0x1800224bc  test    rax, rax
0x1800224bf  jz      short loc_18002251B
0x1800224c1  lea     rcx, [rax+108h]; SRWLock
0x1800224c8  call    cs:__imp_InitializeSRWLock
0x1800224ce  test    sil, sil
0x1800224d1  jz      short loc_180022518
0x1800224d3  mov     ecx, cs:dword_18005FA08
0x1800224d9  test    ecx, ecx
0x1800224db  jnz     short loc_18002251B
0x1800224dd  xor     r8d, r8d; pcbe
0x1800224e0  mov     rdx, rbx; pv
0x1800224e3  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800224ea  call    cs:__imp_CreateThreadpoolTimer
0x1800224f0  mov     [rbx+158h], rax
0x1800224f7  jmp     short loc_18002250E
0x1800224f9  mov     eax, 1
0x1800224fe  xchg    eax, cs:dword_18005FA08
0x180022504  mov     dil, [rsp+28h+arg_8]
0x180022509  mov     rbx, [rsp+28h+arg_10]
0x18002250e  cmp     qword ptr [rbx+158h], 0
0x180022516  jz      short loc_18002251B
0x180022518  mov     dil, 1
0x18002251b  test    dil, dil
0x18002251e  jnz     short loc_18002252A
0x180022520  mov     rcx, rbx; lpMem
0x180022523  call    DestroyAggregateSession
0x180022528  xor     ebx, ebx
0x18002252a  mov     rax, rbx
0x18002252d  mov     rbx, [rsp+28h+arg_0]
0x180022532  mov     rsi, [rsp+28h+arg_18]
0x180022537  add     rsp, 20h
0x18002253b  pop     rdi
0x18002253c  retn
0x180043733  push    rbp
0x180043735  sub     rsp, 20h
0x180043739  mov     rbp, rdx
0x18004373c  mov     rax, [rcx]
0x18004373f  xor     ecx, ecx
0x180043741  cmp     dword ptr [rax], 0C000000Dh
0x180043747  setz    cl
0x18004374a  mov     eax, ecx
0x18004374c  add     rsp, 20h
0x180043750  pop     rbp
0x180043751  retn
```
