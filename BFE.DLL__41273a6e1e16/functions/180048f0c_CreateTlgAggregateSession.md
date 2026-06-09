# CreateTlgAggregateSession

- ea: `0x180048f0c`
- end: `0x180048fe2`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180048df4`

## callees

- `0x180048f0c`
- `0x180077e80`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180048f88`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180048f88`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180048f60`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180048f60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048f26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048f26`

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
    if ( !a1 || !dword_1800F2450 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180048f0c  mov     [rsp+arg_0], rbx
0x180048f11  mov     [rsp+arg_18], rsi
0x180048f16  push    rdi
0x180048f17  sub     rsp, 20h
0x180048f1b  mov     sil, cl
0x180048f1e  xor     dil, dil
0x180048f21  mov     [rsp+28h+arg_8], dil
0x180048f26  call    cs:__imp_GetProcessHeap
0x180048f2d  nop     dword ptr [rax+rax+00h]
0x180048f32  mov     rcx, rax; hHeap
0x180048f35  mov     edx, 8; dwFlags
0x180048f3a  mov     r8d, 168h; dwBytes
0x180048f40  call    cs:__imp_HeapAlloc
0x180048f47  nop     dword ptr [rax+rax+00h]
0x180048f4c  mov     rbx, rax
0x180048f4f  mov     [rsp+28h+arg_10], rax
0x180048f54  test    rax, rax
0x180048f57  jz      short loc_180048FBF
0x180048f59  lea     rcx, [rax+108h]; SRWLock
0x180048f60  call    cs:__imp_InitializeSRWLock
0x180048f67  nop     dword ptr [rax+rax+00h]
0x180048f6c  test    sil, sil
0x180048f6f  jz      short loc_180048FBC
0x180048f71  mov     ecx, cs:dword_1800F2450
0x180048f77  test    ecx, ecx
0x180048f79  jnz     short loc_180048FBF
0x180048f7b  xor     r8d, r8d; pcbe
0x180048f7e  mov     rdx, rbx; pv
0x180048f81  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180048f88  call    cs:__imp_CreateThreadpoolTimer
0x180048f8f  nop     dword ptr [rax+rax+00h]
0x180048f94  mov     [rbx+158h], rax
0x180048f9b  jmp     short loc_180048FB2
0x180048f9d  mov     eax, 1
0x180048fa2  xchg    eax, cs:dword_1800F2450
0x180048fa8  mov     dil, [rsp+28h+arg_8]
0x180048fad  mov     rbx, [rsp+28h+arg_10]
0x180048fb2  cmp     qword ptr [rbx+158h], 0
0x180048fba  jz      short loc_180048FBF
0x180048fbc  mov     dil, 1
0x180048fbf  test    dil, dil
0x180048fc2  jnz     short loc_180048FCE
0x180048fc4  mov     rcx, rbx; lpMem
0x180048fc7  call    DestroyAggregateSession
0x180048fcc  xor     ebx, ebx
0x180048fce  mov     rax, rbx
0x180048fd1  mov     rbx, [rsp+28h+arg_0]
0x180048fd6  mov     rsi, [rsp+28h+arg_18]
0x180048fdb  add     rsp, 20h
0x180048fdf  pop     rdi
0x180048fe0  retn
0x18008ae80  push    rbp
0x18008ae82  sub     rsp, 20h
0x18008ae86  mov     rbp, rdx
0x18008ae89  mov     rax, [rcx]
0x18008ae8c  xor     ecx, ecx
0x18008ae8e  cmp     dword ptr [rax], 0C000000Dh
0x18008ae94  setz    cl
0x18008ae97  mov     eax, ecx
0x18008ae99  add     rsp, 20h
0x18008ae9d  pop     rbp
0x18008ae9e  retn
```
