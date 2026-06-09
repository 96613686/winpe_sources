# GameInputFailFast

- ea: `0x140007488`
- end: `0x140007580`
- name: `GameInputFailFast`
- size: `248`
- prototype: `NTSTATUS __fastcall(NTSTATUS, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000704c`

## callees

- `0x140007488`

## import_xrefs

- `ntdll!NtTerminateProcess` at `0x140007574`
- `ntdll!NtTerminateProcess` at `0x140007574`
- `ntdll!RtlCaptureContext` at `0x1400074c3`
- `ntdll!RtlCaptureContext` at `0x1400074c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140007567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140007567`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x140007561`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x140007561`

## pseudocode

```c
NTSTATUS __fastcall GameInputFailFast(NTSTATUS a1, unsigned int a2)
{
  HANDLE CurrentProcess; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  NTSTATUS ExitStatus; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+38h] [rbp+10h]

  v6 = a2;
  ExitStatus = a1;
  if ( NtCurrentPeb()->BeingDebugged || (MEMORY[0x7FFE02D4] & 3) == 3 )
    __debugbreak();
  RtlCaptureContext(&pContextRecord);
  pContextRecord.Rip = (DWORD64)retaddr;
  pContextRecord.Rsp = (DWORD64)&ExitStatus;
  pExceptionRecord.ExceptionCode = 1073741845;
  pExceptionRecord.ExceptionFlags = 1;
  pExceptionRecord.ExceptionRecord = 0;
  pExceptionRecord.ExceptionAddress = retaddr;
  pExceptionRecord.NumberParameters = 2;
  pExceptionRecord.ExceptionInformation[0] = ExitStatus;
  pExceptionRecord.ExceptionInformation[1] = v6;
  RaiseFailFastException(&pExceptionRecord, &pContextRecord, 2u);
  CurrentProcess = GetCurrentProcess();
  return NtTerminateProcess(CurrentProcess, ExitStatus);
}

```

## disassembly

```asm
0x140007488  mov     [rsp+arg_8], edx
0x14000748c  mov     [rsp+ExitStatus], ecx
0x140007490  sub     rsp, 28h
0x140007494  mov     rax, gs:60h
0x14000749d  movzx   eax, byte ptr [rax+2]
0x1400074a1  test    eax, eax
0x1400074a3  jnz     short loc_1400074BB
0x1400074a5  mov     eax, 2D4h
0x1400074aa  add     rax, 7FFE0000h
0x1400074b0  movzx   eax, byte ptr [rax]
0x1400074b3  and     eax, 3
0x1400074b6  cmp     eax, 3
0x1400074b9  jnz     short loc_1400074BC
0x1400074bb  int     3; Trap to Debugger
0x1400074bc  lea     rcx, pContextRecord; ContextRecord
0x1400074c3  call    cs:__imp_RtlCaptureContext
0x1400074c9  mov     rax, [rsp+28h]
0x1400074ce  mov     cs:pContextRecord.Rip, rax
0x1400074d5  lea     rax, [rsp+28h]
0x1400074da  add     rax, 8
0x1400074de  mov     cs:pContextRecord.Rsp, rax
0x1400074e5  mov     cs:pExceptionRecord.ExceptionCode, 40000015h
0x1400074ef  mov     cs:pExceptionRecord.ExceptionFlags, 1
0x1400074f9  mov     cs:pExceptionRecord.ExceptionRecord, 0
0x140007504  mov     rax, cs:pContextRecord.Rip
0x14000750b  mov     cs:pExceptionRecord.ExceptionAddress, rax
0x140007512  mov     cs:pExceptionRecord.NumberParameters, 2
0x14000751c  movsxd  rax, [rsp+28h+ExitStatus]
0x140007521  mov     ecx, 8
0x140007526  imul    rcx, 0
0x14000752a  lea     rdx, pExceptionRecord.ExceptionInformation
0x140007531  mov     [rdx+rcx], rax
0x140007535  mov     eax, [rsp+28h+arg_8]
0x140007539  mov     ecx, 8
0x14000753e  imul    rcx, 1
0x140007542  lea     rdx, pExceptionRecord.ExceptionInformation
0x140007549  mov     [rdx+rcx], rax
0x14000754d  mov     r8d, 2; dwFlags
0x140007553  lea     rdx, pContextRecord; pContextRecord
0x14000755a  lea     rcx, pExceptionRecord; pExceptionRecord
0x140007561  call    cs:__imp_RaiseFailFastException
0x140007567  call    cs:__imp_GetCurrentProcess
0x14000756d  mov     edx, [rsp+28h+ExitStatus]; ExitStatus
0x140007571  mov     rcx, rax; ProcessHandle
0x140007574  call    cs:__imp_NtTerminateProcess
0x14000757a  nop
0x14000757b  add     rsp, 28h
0x14000757f  retn
```
