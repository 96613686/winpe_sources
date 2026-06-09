# CreateTlgAggregateSession

- ea: `0x18001aa2c`
- end: `0x18001ab02`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b568`

## callees

- `0x18001a790`
- `0x18001aa2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aad9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aad9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aa5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aa5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aae7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aae7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001aa74`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001aa74`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001aa96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001aa96`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx
  HANDLE v6; // rax

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_180028B98 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    if ( v5 )
    {
      CancelTimerCallbacksAndDeleteTimer((__int64)v5);
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
    }
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18001aa2c  mov     [rsp+arg_0], rbx
0x18001aa31  mov     [rsp+arg_18], rsi
0x18001aa36  push    rdi
0x18001aa37  sub     rsp, 20h
0x18001aa3b  mov     sil, cl
0x18001aa3e  xor     dil, dil
0x18001aa41  mov     [rsp+28h+arg_8], dil
0x18001aa46  call    cs:__imp_GetProcessHeap
0x18001aa4c  mov     rcx, rax; hHeap
0x18001aa4f  mov     edx, 8; dwFlags
0x18001aa54  mov     r8d, 168h; dwBytes
0x18001aa5a  call    cs:__imp_HeapAlloc
0x18001aa60  mov     rbx, rax
0x18001aa63  mov     [rsp+28h+arg_10], rax
0x18001aa68  test    rax, rax
0x18001aa6b  jz      short loc_18001AAC7
0x18001aa6d  lea     rcx, [rax+108h]; SRWLock
0x18001aa74  call    cs:__imp_InitializeSRWLock
0x18001aa7a  test    sil, sil
0x18001aa7d  jz      short loc_18001AAC4
0x18001aa7f  mov     ecx, cs:dword_180028B98
0x18001aa85  test    ecx, ecx
0x18001aa87  jnz     short loc_18001AAC7
0x18001aa89  xor     r8d, r8d; pcbe
0x18001aa8c  mov     rdx, rbx; pv
0x18001aa8f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18001aa96  call    cs:__imp_CreateThreadpoolTimer
0x18001aa9c  mov     [rbx+158h], rax
0x18001aaa3  jmp     short loc_18001AABA
0x18001aaa5  mov     eax, 1
0x18001aaaa  xchg    eax, cs:dword_180028B98
0x18001aab0  mov     dil, [rsp+28h+arg_8]
0x18001aab5  mov     rbx, [rsp+28h+arg_10]
0x18001aaba  cmp     qword ptr [rbx+158h], 0
0x18001aac2  jz      short loc_18001AAC7
0x18001aac4  mov     dil, 1
0x18001aac7  test    dil, dil
0x18001aaca  jnz     short loc_18001AAEF
0x18001aacc  test    rbx, rbx
0x18001aacf  jz      short loc_18001AAED
0x18001aad1  mov     rcx, rbx
0x18001aad4  call    CancelTimerCallbacksAndDeleteTimer
0x18001aad9  call    cs:__imp_GetProcessHeap
0x18001aadf  mov     rcx, rax; hHeap
0x18001aae2  mov     r8, rbx; lpMem
0x18001aae5  xor     edx, edx; dwFlags
0x18001aae7  call    cs:__imp_HeapFree
0x18001aaed  xor     ebx, ebx
0x18001aaef  mov     rax, rbx
0x18001aaf2  mov     rbx, [rsp+28h+arg_0]
0x18001aaf7  mov     rsi, [rsp+28h+arg_18]
0x18001aafc  add     rsp, 20h
0x18001ab00  pop     rdi
0x18001ab01  retn
0x18001bf86  push    rbp
0x18001bf88  sub     rsp, 20h
0x18001bf8c  mov     rbp, rdx
0x18001bf8f  mov     rax, [rcx]
0x18001bf92  xor     ecx, ecx
0x18001bf94  cmp     dword ptr [rax], 0C000000Dh
0x18001bf9a  setz    cl
0x18001bf9d  mov     eax, ecx
0x18001bf9f  add     rsp, 20h
0x18001bfa3  pop     rbp
0x18001bfa4  retn
```
