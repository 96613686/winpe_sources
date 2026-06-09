# CreateTlgAggregateSession

- ea: `0x140045184`
- end: `0x140045241`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140045da8`

## callees

- `0x140045184`
- `0x140045248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400451cc`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400451cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400451b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400451b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004519e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004519e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400451ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400451ee`

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
    if ( !a1 || !dword_1400979A4 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x140045184  mov     [rsp+arg_0], rbx
0x140045189  mov     [rsp+arg_18], rsi
0x14004518e  push    rdi
0x14004518f  sub     rsp, 20h
0x140045193  mov     sil, cl
0x140045196  xor     dil, dil
0x140045199  mov     [rsp+28h+arg_8], dil
0x14004519e  call    cs:__imp_GetProcessHeap
0x1400451a4  mov     rcx, rax; hHeap
0x1400451a7  mov     edx, 8; dwFlags
0x1400451ac  mov     r8d, 168h; dwBytes
0x1400451b2  call    cs:__imp_HeapAlloc
0x1400451b8  mov     rbx, rax
0x1400451bb  mov     [rsp+28h+arg_10], rax
0x1400451c0  test    rax, rax
0x1400451c3  jz      short loc_14004521F
0x1400451c5  lea     rcx, [rax+108h]; SRWLock
0x1400451cc  call    cs:__imp_InitializeSRWLock
0x1400451d2  test    sil, sil
0x1400451d5  jz      short loc_14004521C
0x1400451d7  mov     ecx, cs:dword_1400979A4
0x1400451dd  test    ecx, ecx
0x1400451df  jnz     short loc_14004521F
0x1400451e1  xor     r8d, r8d; pcbe
0x1400451e4  mov     rdx, rbx; pv
0x1400451e7  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1400451ee  call    cs:__imp_CreateThreadpoolTimer
0x1400451f4  mov     [rbx+158h], rax
0x1400451fb  jmp     short loc_140045212
0x1400451fd  mov     eax, 1
0x140045202  xchg    eax, cs:dword_1400979A4
0x140045208  mov     dil, [rsp+28h+arg_8]
0x14004520d  mov     rbx, [rsp+28h+arg_10]
0x140045212  cmp     qword ptr [rbx+158h], 0
0x14004521a  jz      short loc_14004521F
0x14004521c  mov     dil, 1
0x14004521f  test    dil, dil
0x140045222  jnz     short loc_14004522E
0x140045224  mov     rcx, rbx; lpMem
0x140045227  call    DestroyAggregateSession
0x14004522c  xor     ebx, ebx
0x14004522e  mov     rax, rbx
0x140045231  mov     rbx, [rsp+28h+arg_0]
0x140045236  mov     rsi, [rsp+28h+arg_18]
0x14004523b  add     rsp, 20h
0x14004523f  pop     rdi
0x140045240  retn
0x14006d83c  push    rbp
0x14006d83e  sub     rsp, 20h
0x14006d842  mov     rbp, rdx
0x14006d845  mov     rax, [rcx]
0x14006d848  xor     ecx, ecx
0x14006d84a  cmp     dword ptr [rax], 0C000000Dh
0x14006d850  setz    cl
0x14006d853  mov     eax, ecx
0x14006d855  add     rsp, 20h
0x14006d859  pop     rbp
0x14006d85a  retn
```
