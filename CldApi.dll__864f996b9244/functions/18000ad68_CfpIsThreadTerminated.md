# CfpIsThreadTerminated

- ea: `0x18000ad68`
- end: `0x18000add2`
- name: `CfpIsThreadTerminated`
- size: `106`
- prototype: `__int64 __fastcall(DWORD dwThreadId)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007cf0`

## callees

- `0x18000ad68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000ad84`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000ad84`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000ad9a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000ad9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adbf`

## pseudocode

```c
__int64 __fastcall CfpIsThreadTerminated(DWORD dwThreadId)
{
  HANDLE v1; // rax
  void *v2; // rbx
  unsigned int v3; // edi
  DWORD ExitCode; // [rsp+38h] [rbp+10h] BYREF

  ExitCode = 0;
  v1 = OpenThread(0x800u, 0, dwThreadId);
  v2 = v1;
  if ( v1 && (!GetExitCodeThread(v1, &ExitCode) || ExitCode == 259) )
  {
    v3 = 0;
LABEL_6:
    CloseHandle(v2);
    return v3;
  }
  v3 = 1;
  if ( v2 )
    goto LABEL_6;
  return v3;
}

```

## disassembly

```asm
0x18000ad68  mov     [rsp+arg_0], rbx
0x18000ad6d  push    rdi
0x18000ad6e  sub     rsp, 20h
0x18000ad72  mov     r8d, ecx; dwThreadId
0x18000ad75  mov     [rsp+28h+ExitCode], 0
0x18000ad7d  mov     ecx, 800h; dwDesiredAccess
0x18000ad82  xor     edx, edx; bInheritHandle
0x18000ad84  call    cs:__imp_OpenThread
0x18000ad8a  mov     rbx, rax
0x18000ad8d  test    rax, rax
0x18000ad90  jz      short loc_18000ADB2
0x18000ad92  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x18000ad97  mov     rcx, rax; hThread
0x18000ad9a  call    cs:__imp_GetExitCodeThread
0x18000ada0  test    eax, eax
0x18000ada2  jz      short loc_18000ADAE
0x18000ada4  cmp     [rsp+28h+ExitCode], 103h
0x18000adac  jnz     short loc_18000ADB2
0x18000adae  xor     edi, edi
0x18000adb0  jmp     short loc_18000ADBC
0x18000adb2  mov     edi, 1
0x18000adb7  test    rbx, rbx
0x18000adba  jz      short loc_18000ADC5
0x18000adbc  mov     rcx, rbx; hObject
0x18000adbf  call    cs:__imp_CloseHandle
0x18000adc5  mov     rbx, [rsp+28h+arg_0]
0x18000adca  mov     eax, edi
0x18000adcc  add     rsp, 20h
0x18000add0  pop     rdi
0x18000add1  retn
```
