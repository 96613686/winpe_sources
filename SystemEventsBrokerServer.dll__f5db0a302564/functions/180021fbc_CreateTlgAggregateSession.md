# CreateTlgAggregateSession

- ea: `0x180021fbc`
- end: `0x180022079`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c8e4`

## callees

- `0x180021fbc`
- `0x180022080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180022004`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180022004`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021fea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021fea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021fd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021fd6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180022026`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180022026`

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
    if ( !a1 || !dword_180036E18 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180021fbc  mov     [rsp+arg_0], rbx
0x180021fc1  mov     [rsp+arg_18], rsi
0x180021fc6  push    rdi
0x180021fc7  sub     rsp, 20h
0x180021fcb  mov     sil, cl
0x180021fce  xor     dil, dil
0x180021fd1  mov     [rsp+28h+arg_8], dil
0x180021fd6  call    cs:__imp_GetProcessHeap
0x180021fdc  mov     rcx, rax; hHeap
0x180021fdf  mov     edx, 8; dwFlags
0x180021fe4  mov     r8d, 168h; dwBytes
0x180021fea  call    cs:__imp_HeapAlloc
0x180021ff0  mov     rbx, rax
0x180021ff3  mov     [rsp+28h+arg_10], rax
0x180021ff8  test    rax, rax
0x180021ffb  jz      short loc_180022057
0x180021ffd  lea     rcx, [rax+108h]; SRWLock
0x180022004  call    cs:__imp_InitializeSRWLock
0x18002200a  test    sil, sil
0x18002200d  jz      short loc_180022054
0x18002200f  mov     ecx, cs:dword_180036E18
0x180022015  test    ecx, ecx
0x180022017  jnz     short loc_180022057
0x180022019  xor     r8d, r8d; pcbe
0x18002201c  mov     rdx, rbx; pv
0x18002201f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180022026  call    cs:__imp_CreateThreadpoolTimer
0x18002202c  mov     [rbx+158h], rax
0x180022033  jmp     short loc_18002204A
0x180022035  mov     eax, 1
0x18002203a  xchg    eax, cs:dword_180036E18
0x180022040  mov     dil, [rsp+28h+arg_8]
0x180022045  mov     rbx, [rsp+28h+arg_10]
0x18002204a  cmp     qword ptr [rbx+158h], 0
0x180022052  jz      short loc_180022057
0x180022054  mov     dil, 1
0x180022057  test    dil, dil
0x18002205a  jnz     short loc_180022066
0x18002205c  mov     rcx, rbx; lpMem
0x18002205f  call    DestroyAggregateSession
0x180022064  xor     ebx, ebx
0x180022066  mov     rax, rbx
0x180022069  mov     rbx, [rsp+28h+arg_0]
0x18002206e  mov     rsi, [rsp+28h+arg_18]
0x180022073  add     rsp, 20h
0x180022077  pop     rdi
0x180022078  retn
0x180026227  push    rbp
0x180026229  sub     rsp, 20h
0x18002622d  mov     rbp, rdx
0x180026230  mov     rax, [rcx]
0x180026233  xor     ecx, ecx
0x180026235  cmp     dword ptr [rax], 0C000000Dh
0x18002623b  setz    cl
0x18002623e  mov     eax, ecx
0x180026240  add     rsp, 20h
0x180026244  pop     rbp
0x180026245  retn
```
