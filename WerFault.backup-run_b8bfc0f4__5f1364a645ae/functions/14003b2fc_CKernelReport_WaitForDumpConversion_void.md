# CKernelReport::WaitForDumpConversion(void)

- ea: `0x14003b2fc`
- end: `0x14003b3a6`
- name: `?WaitForDumpConversion@CKernelReport@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140039614`

## callees

- `0x14003902c`
- `0x14003b2fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14003b340`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14003b340`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003b330`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003b330`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14003b317`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14003b317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b349`

## string_xrefs

- `0x14003b372`: `Access denied for the event %ws`

## pseudocode

```c
__int64 __fastcall CKernelReport::WaitForDumpConversion(CKernelReport *this)
{
  HANDLE v1; // rax
  void *v2; // rbx
  wil::details *v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag4 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = OpenMutexW(0x100001u, 0, L"Global\\WerKernelVerticalGeneratingDump");
  v2 = v1;
  if ( (unsigned __int64)v1 + 1 > 1 )
  {
    if ( (WaitForSingleObject(v1, 0xFFFFFFFF) & 0xFFFFFF7F) == 0 )
      ReleaseMutex(v2);
    CloseHandle(v2);
    return 0;
  }
  if ( GetLastError() != 5 )
    return 0;
  LODWORD(v4) = GetLastError();
  wil::details::in1diag4::Log_Win32Msg(
    retaddr,
    (void *)0x36F,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::WaitForDumpConversion",
    v4,
    (unsigned int)"Access denied for the event %ws",
    (const char *)L"Global\\WerKernelVerticalGeneratingDump");
  return 2147942405LL;
}

```

## disassembly

```asm
0x14003b2fc  mov     [rsp+arg_0], rbx
0x14003b301  push    rdi
0x14003b302  sub     rsp, 40h
0x14003b306  lea     rdi, aGlobalWerkerne_1; "Global\\WerKernelVerticalGeneratingDump"
0x14003b30d  xor     edx, edx; bInheritHandle
0x14003b30f  mov     r8, rdi; lpName
0x14003b312  mov     ecx, 100001h; dwDesiredAccess
0x14003b317  call    cs:__imp_OpenMutexW
0x14003b31d  mov     rbx, rax
0x14003b320  lea     rcx, [rax+1]
0x14003b324  cmp     rcx, 1
0x14003b328  jbe     short loc_14003B35C
0x14003b32a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003b32d  mov     rcx, rax; hHandle
0x14003b330  call    cs:__imp_WaitForSingleObject
0x14003b336  test    eax, 0FFFFFF7Fh
0x14003b33b  jnz     short loc_14003B346
0x14003b33d  mov     rcx, rbx; hMutex
0x14003b340  call    cs:__imp_ReleaseMutex
0x14003b346  mov     rcx, rbx; hObject
0x14003b349  call    cs:__imp_CloseHandle
0x14003b34f  xor     eax, eax
0x14003b351  mov     rbx, [rsp+48h+arg_0]
0x14003b356  add     rsp, 40h
0x14003b35a  pop     rdi
0x14003b35b  retn
0x14003b35c  call    cs:__imp_GetLastError
0x14003b362  cmp     eax, 5
0x14003b365  jnz     short loc_14003B34F
0x14003b367  call    cs:__imp_GetLastError
0x14003b36d  mov     rcx, [rsp+48h]; this
0x14003b372  lea     rdx, aAccessDeniedFo; "Access denied for the event %ws"
0x14003b379  mov     [rsp+48h+var_18], rdi; char *
0x14003b37e  lea     r9, aCkernelreportW; "CKernelReport::WaitForDumpConversion"
0x14003b385  mov     qword ptr [rsp+48h+var_20], rdx; unsigned int
0x14003b38a  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003b391  mov     edx, 36Fh; void *
0x14003b396  mov     dword ptr [rsp+48h+var_28], eax; wil::details *
0x14003b39a  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003b39f  mov     eax, 80070005h
0x14003b3a4  jmp     short loc_14003B351
```
