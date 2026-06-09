# WinSAT::MPWorkload::ThreadEntryPoint(void *)

- ea: `0x140074070`
- end: `0x140074101`
- name: `?ThreadEntryPoint@MPWorkload@WinSAT@@CAIPEAX@Z`
- size: `145`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14003ec14`
- `0x140074070`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x140074086`
- `KERNEL32!GetThreadPriority` at `0x140074086`
- `KERNEL32!GetCurrentThread` at `0x14007407d`
- `KERNEL32!GetCurrentThread` at `0x14007407d`

## string_xrefs

- `0x14007408f`: ` CPU ThreadEntryPoint Launched with priority %d`

## pseudocode

```c
__int64 __fastcall WinSAT::MPWorkload::ThreadEntryPoint(int **a1)
{
  int **v1; // rbx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  unsigned int v5; // eax
  __int64 v6; // rdx

  v1 = a1;
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  Log_Text_F("base\\winsat\\exe\\WinSATOp.h", 820, " CPU ThreadEntryPoint Launched with priority %d", ThreadPriority);
  if ( *v1[4] > 0 )
    return 5;
  v5 = (*((__int64 (__fastcall **)(int **))*v1 + 2))(v1);
  v6 = v5;
  if ( !v5 )
  {
    try
    {
      v6 = (*((unsigned int (__fastcall **)(int **))*v1 + 3))(v1);
    }
    catch ( std::bad_alloc )
    {
      v1 = a1;
      v6 = 8;
    }
  }
  return (*((__int64 (__fastcall **)(int **, __int64))*v1 + 4))(v1, v6);
}

```

## disassembly

```asm
0x140074070  mov     [rsp+arg_0], rcx
0x140074075  push    rbx
0x140074076  sub     rsp, 20h
0x14007407a  mov     rbx, rcx
0x14007407d  call    cs:__imp_GetCurrentThread
0x140074083  mov     rcx, rax; hThread
0x140074086  call    cs:__imp_GetThreadPriority
0x14007408c  mov     r9d, eax
0x14007408f  lea     r8, aCpuThreadentry; " CPU ThreadEntryPoint Launched with pri"...
0x140074096  mov     edx, 334h
0x14007409b  lea     rcx, aBaseWinsatExeW_0; "base\\winsat\\exe\\WinSATOp.h"
0x1400740a2  call    Log_Text_F
0x1400740a7  mov     rax, [rbx+20h]
0x1400740ab  mov     edx, [rax]
0x1400740ad  test    edx, edx
0x1400740af  jle     short loc_1400740BC
0x1400740b1  mov     eax, 5
0x1400740b6  add     rsp, 20h
0x1400740ba  pop     rbx
0x1400740bb  retn
0x1400740bc  mov     rax, [rbx]
0x1400740bf  mov     rcx, rbx
0x1400740c2  mov     rax, [rax+10h]
0x1400740c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400740cb  mov     edx, eax
0x1400740cd  test    eax, eax
0x1400740cf  jnz     short loc_1400740ED
0x1400740d1  mov     rax, [rbx]
0x1400740d4  mov     rcx, rbx
0x1400740d7  mov     rax, [rax+18h]
0x1400740db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400740e0  mov     edx, eax
0x1400740e2  jmp     short loc_1400740ED
0x1400740e4  mov     rbx, [rsp+28h+arg_0]
0x1400740e9  mov     edx, [rsp+28h+arg_8]
0x1400740ed  mov     rax, [rbx]
0x1400740f0  mov     rcx, rbx
0x1400740f3  mov     rax, [rax+20h]
0x1400740f7  add     rsp, 20h
0x1400740fb  pop     rbx
0x1400740fc  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
