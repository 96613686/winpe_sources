# CreateTlgAggregateSession

- ea: `0x1800425f0`
- end: `0x1800426c6`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800431d8`

## callees

- `0x1800425f0`
- `0x1800426cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180042644`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180042644`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042624`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042624`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004260a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004260a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004266c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004266c`

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
    if ( !a1 || !dword_18005CB48 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800425f0  mov     [rsp+arg_0], rbx
0x1800425f5  mov     [rsp+arg_18], rsi
0x1800425fa  push    rdi
0x1800425fb  sub     rsp, 30h
0x1800425ff  mov     sil, cl
0x180042602  xor     dil, dil
0x180042605  mov     [rsp+38h+arg_8], dil
0x18004260a  call    cs:__imp_GetProcessHeap
0x180042611  nop     dword ptr [rax+rax+00h]
0x180042616  mov     rcx, rax; hHeap
0x180042619  mov     edx, 8; dwFlags
0x18004261e  mov     r8d, 168h; dwBytes
0x180042624  call    cs:__imp_HeapAlloc
0x18004262b  nop     dword ptr [rax+rax+00h]
0x180042630  mov     rbx, rax
0x180042633  mov     [rsp+38h+arg_10], rax
0x180042638  test    rax, rax
0x18004263b  jz      short loc_1800426A3
0x18004263d  lea     rcx, [rax+108h]; SRWLock
0x180042644  call    cs:__imp_InitializeSRWLock
0x18004264b  nop     dword ptr [rax+rax+00h]
0x180042650  test    sil, sil
0x180042653  jz      short loc_1800426A0
0x180042655  mov     ecx, cs:dword_18005CB48
0x18004265b  test    ecx, ecx
0x18004265d  jnz     short loc_1800426A3
0x18004265f  xor     r8d, r8d; pcbe
0x180042662  mov     rdx, rbx; pv
0x180042665  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18004266c  call    cs:__imp_CreateThreadpoolTimer
0x180042673  nop     dword ptr [rax+rax+00h]
0x180042678  mov     [rbx+158h], rax
0x18004267f  jmp     short loc_180042696
0x180042681  mov     eax, 1
0x180042686  xchg    eax, cs:dword_18005CB48
0x18004268c  mov     dil, [rsp+38h+arg_8]
0x180042691  mov     rbx, [rsp+38h+arg_10]
0x180042696  cmp     qword ptr [rbx+158h], 0
0x18004269e  jz      short loc_1800426A3
0x1800426a0  mov     dil, 1
0x1800426a3  test    dil, dil
0x1800426a6  jnz     short loc_1800426B2
0x1800426a8  mov     rcx, rbx; lpMem
0x1800426ab  call    DestroyAggregateSession
0x1800426b0  xor     ebx, ebx
0x1800426b2  mov     rax, rbx
0x1800426b5  mov     rbx, [rsp+38h+arg_0]
0x1800426ba  mov     rsi, [rsp+38h+arg_18]
0x1800426bf  add     rsp, 30h
0x1800426c3  pop     rdi
0x1800426c4  retn
0x180044956  push    rbp
0x180044958  sub     rsp, 20h
0x18004495c  mov     rbp, rdx
0x18004495f  mov     [rbp+28h], rcx
0x180044963  mov     rax, [rcx]
0x180044966  mov     ecx, [rax]
0x180044968  mov     [rbp+20h], ecx
0x18004496b  xor     eax, eax
0x18004496d  cmp     ecx, 0C000000Dh
0x180044973  setz    al
0x180044976  add     rsp, 20h
0x18004497a  pop     rbp
0x18004497b  retn
```
