# CreateTlgAggregateSession

- ea: `0x180011c00`
- end: `0x180011cbd`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011a64`

## callees

- `0x180011c00`
- `0x180011f14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011c2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011c2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c1a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180011c48`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180011c48`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011c6a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011c6a`

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
    if ( !a1 || !dword_1800537B0 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180011c00  mov     [rsp+arg_0], rbx
0x180011c05  mov     [rsp+arg_18], rsi
0x180011c0a  push    rdi
0x180011c0b  sub     rsp, 20h
0x180011c0f  mov     sil, cl
0x180011c12  xor     dil, dil
0x180011c15  mov     [rsp+28h+arg_8], dil
0x180011c1a  call    cs:__imp_GetProcessHeap
0x180011c20  mov     rcx, rax; hHeap
0x180011c23  mov     edx, 8; dwFlags
0x180011c28  mov     r8d, 168h; dwBytes
0x180011c2e  call    cs:__imp_HeapAlloc
0x180011c34  mov     rbx, rax
0x180011c37  mov     [rsp+28h+arg_10], rax
0x180011c3c  test    rax, rax
0x180011c3f  jz      short loc_180011C9B
0x180011c41  lea     rcx, [rax+108h]; SRWLock
0x180011c48  call    cs:__imp_InitializeSRWLock
0x180011c4e  test    sil, sil
0x180011c51  jz      short loc_180011C98
0x180011c53  mov     ecx, cs:dword_1800537B0
0x180011c59  test    ecx, ecx
0x180011c5b  jnz     short loc_180011C9B
0x180011c5d  xor     r8d, r8d; pcbe
0x180011c60  mov     rdx, rbx; pv
0x180011c63  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180011c6a  call    cs:__imp_CreateThreadpoolTimer
0x180011c70  mov     [rbx+158h], rax
0x180011c77  jmp     short loc_180011C8E
0x180011c79  mov     eax, 1
0x180011c7e  xchg    eax, cs:dword_1800537B0
0x180011c84  mov     dil, [rsp+28h+arg_8]
0x180011c89  mov     rbx, [rsp+28h+arg_10]
0x180011c8e  cmp     qword ptr [rbx+158h], 0
0x180011c96  jz      short loc_180011C9B
0x180011c98  mov     dil, 1
0x180011c9b  test    dil, dil
0x180011c9e  jnz     short loc_180011CAA
0x180011ca0  mov     rcx, rbx; lpMem
0x180011ca3  call    DestroyAggregateSession
0x180011ca8  xor     ebx, ebx
0x180011caa  mov     rax, rbx
0x180011cad  mov     rbx, [rsp+28h+arg_0]
0x180011cb2  mov     rsi, [rsp+28h+arg_18]
0x180011cb7  add     rsp, 20h
0x180011cbb  pop     rdi
0x180011cbc  retn
0x180039c62  push    rbp
0x180039c64  sub     rsp, 20h
0x180039c68  mov     rbp, rdx
0x180039c6b  mov     rax, [rcx]
0x180039c6e  xor     ecx, ecx
0x180039c70  cmp     dword ptr [rax], 0C000000Dh
0x180039c76  setz    cl
0x180039c79  mov     eax, ecx
0x180039c7b  add     rsp, 20h
0x180039c7f  pop     rbp
0x180039c80  retn
```
