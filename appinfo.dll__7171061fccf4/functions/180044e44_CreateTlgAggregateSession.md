# CreateTlgAggregateSession

- ea: `0x180044e44`
- end: `0x180044f01`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e270`
- `0x180012170`
- `0x180012c20`
- `0x180013720`
- `0x180014690`
- `0x1800156b0`
- `0x180016610`
- `0x180045a40`

## callees

- `0x180044e44`
- `0x180044f08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180044e8c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180044e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044e5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044e5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044e72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044e72`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180044eae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180044eae`

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
    if ( !a1 || !dword_180060AF8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180044e44  mov     [rsp+arg_0], rbx
0x180044e49  mov     [rsp+arg_18], rsi
0x180044e4e  push    rdi
0x180044e4f  sub     rsp, 20h
0x180044e53  mov     sil, cl
0x180044e56  xor     dil, dil
0x180044e59  mov     [rsp+28h+arg_8], dil
0x180044e5e  call    cs:__imp_GetProcessHeap
0x180044e64  mov     rcx, rax; hHeap
0x180044e67  mov     edx, 8; dwFlags
0x180044e6c  mov     r8d, 168h; dwBytes
0x180044e72  call    cs:__imp_HeapAlloc
0x180044e78  mov     rbx, rax
0x180044e7b  mov     [rsp+28h+arg_10], rax
0x180044e80  test    rax, rax
0x180044e83  jz      short loc_180044EDF
0x180044e85  lea     rcx, [rax+108h]; SRWLock
0x180044e8c  call    cs:__imp_InitializeSRWLock
0x180044e92  test    sil, sil
0x180044e95  jz      short loc_180044EDC
0x180044e97  mov     ecx, cs:dword_180060AF8
0x180044e9d  test    ecx, ecx
0x180044e9f  jnz     short loc_180044EDF
0x180044ea1  xor     r8d, r8d; pcbe
0x180044ea4  mov     rdx, rbx; pv
0x180044ea7  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180044eae  call    cs:__imp_CreateThreadpoolTimer
0x180044eb4  mov     [rbx+158h], rax
0x180044ebb  jmp     short loc_180044ED2
0x180044ebd  mov     eax, 1
0x180044ec2  xchg    eax, cs:dword_180060AF8
0x180044ec8  mov     dil, [rsp+28h+arg_8]
0x180044ecd  mov     rbx, [rsp+28h+arg_10]
0x180044ed2  cmp     qword ptr [rbx+158h], 0
0x180044eda  jz      short loc_180044EDF
0x180044edc  mov     dil, 1
0x180044edf  test    dil, dil
0x180044ee2  jnz     short loc_180044EEE
0x180044ee4  mov     rcx, rbx; lpMem
0x180044ee7  call    DestroyAggregateSession
0x180044eec  xor     ebx, ebx
0x180044eee  mov     rax, rbx
0x180044ef1  mov     rbx, [rsp+28h+arg_0]
0x180044ef6  mov     rsi, [rsp+28h+arg_18]
0x180044efb  add     rsp, 20h
0x180044eff  pop     rdi
0x180044f00  retn
0x180047266  push    rbp
0x180047268  sub     rsp, 20h
0x18004726c  mov     rbp, rdx
0x18004726f  mov     rax, [rcx]
0x180047272  xor     ecx, ecx
0x180047274  cmp     dword ptr [rax], 0C000000Dh
0x18004727a  setz    cl
0x18004727d  mov     eax, ecx
0x18004727f  add     rsp, 20h
0x180047283  pop     rbp
0x180047284  retn
```
