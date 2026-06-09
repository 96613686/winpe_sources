# std::thread::_Invoke_std::tuple__lambda_c111077bd45a71f2803fa46ebe479ec2____0_

- ea: `0x14000b170`
- end: `0x14000b248`
- name: `std::thread::_Invoke_std::tuple__lambda_c111077bd45a71f2803fa46ebe479ec2____0_`
- size: `216`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001e34`
- `0x14000b170`
- `0x1400151b0`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x14000b22d`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x14000b22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b1e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b1e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000b1cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000b1cf`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14000b1dd`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14000b1dd`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14000b1a8`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14000b1a8`

## string_xrefs

- `0x14000b20f`: `Exiting monitor thread`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_c111077bd45a71f2803fa46ebe479ec2____0_(HANDLE **a1)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  *(_OWORD *)Handles = 0;
  Handles[0] = **a1;
  Handles[1] = *a1[1];
  if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) == 1 )
  {
    AslLogCallPrintf(
      3,
      "main::<lambda_c111077bd45a71f2803fa46ebe479ec2>::operator ()",
      617,
      "Switching to background scheduling because WindowCloseEvent was signaled");
    CurrentProcess = GetCurrentProcess();
    if ( !SetPriorityClass(CurrentProcess, 0x100000u) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "main::<lambda_c111077bd45a71f2803fa46ebe479ec2>::operator ()",
        620,
        "SetPriorityClass failed [%d]",
        LastError);
    }
  }
  AslLogCallPrintf(3, "main::<lambda_c111077bd45a71f2803fa46ebe479ec2>::operator ()", 626, "Exiting monitor thread");
  _Cnd_do_broadcast_at_thread_exit();
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x14000b170  push    rbx
0x14000b172  sub     rsp, 40h
0x14000b176  mov     rbx, rcx
0x14000b179  xorps   xmm0, xmm0
0x14000b17c  movups  xmmword ptr [rsp+48h+Handles], xmm0
0x14000b181  mov     rax, [rcx]
0x14000b184  mov     rdx, [rax]
0x14000b187  mov     [rsp+48h+Handles], rdx
0x14000b18c  mov     rax, [rcx+8]
0x14000b190  mov     rdx, [rax]
0x14000b193  mov     [rsp+48h+Handles+8], rdx
0x14000b198  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14000b19c  xor     r8d, r8d; bWaitAll
0x14000b19f  lea     rdx, [rsp+48h+Handles]; lpHandles
0x14000b1a4  lea     ecx, [r8+2]; nCount
0x14000b1a8  call    cs:__imp_WaitForMultipleObjects
0x14000b1ae  cmp     eax, 1
0x14000b1b1  jnz     short loc_14000B20F
0x14000b1b3  lea     r9, aSwitchingToBac; "Switching to background scheduling beca"...
0x14000b1ba  mov     r8d, 269h
0x14000b1c0  lea     rdx, aMainLambdaC111; "main::<lambda_c111077bd45a71f2803fa46eb"...
0x14000b1c7  lea     ecx, [rax+2]
0x14000b1ca  call    AslLogCallPrintf
0x14000b1cf  call    cs:__imp_GetCurrentProcess
0x14000b1d5  mov     rcx, rax; hProcess
0x14000b1d8  mov     edx, 100000h; dwPriorityClass
0x14000b1dd  call    cs:__imp_SetPriorityClass
0x14000b1e3  test    eax, eax
0x14000b1e5  jnz     short loc_14000B20F
0x14000b1e7  call    cs:__imp_GetLastError
0x14000b1ed  mov     [rsp+48h+var_28], eax
0x14000b1f1  lea     r9, aSetprioritycla; "SetPriorityClass failed [%d]"
0x14000b1f8  mov     r8d, 26Ch
0x14000b1fe  lea     rdx, aMainLambdaC111; "main::<lambda_c111077bd45a71f2803fa46eb"...
0x14000b205  mov     ecx, 1
0x14000b20a  call    AslLogCallPrintf
0x14000b20f  lea     r9, aExitingMonitor; "Exiting monitor thread"
0x14000b216  mov     r8d, 272h
0x14000b21c  lea     rdx, aMainLambdaC111; "main::<lambda_c111077bd45a71f2803fa46eb"...
0x14000b223  mov     ecx, 3
0x14000b228  call    AslLogCallPrintf
0x14000b22d  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x14000b233  mov     edx, 10h; unsigned __int64
0x14000b238  mov     rcx, rbx; void *
0x14000b23b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b240  xor     eax, eax
0x14000b242  add     rsp, 40h
0x14000b246  pop     rbx
0x14000b247  retn
```
