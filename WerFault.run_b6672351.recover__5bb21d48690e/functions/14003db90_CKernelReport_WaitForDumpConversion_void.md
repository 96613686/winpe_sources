# CKernelReport::WaitForDumpConversion(void)

- ea: `0x14003db90`
- end: `0x14003dc5f`
- name: `?WaitForDumpConversion@CKernelReport@@QEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003bbd4`

## callees

- `0x14003b56c`
- `0x14003db90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14003dbe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14003dbe0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003dbca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003dbca`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14003dbab`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14003dbab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dc1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dc1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003dbef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003dbef`

## string_xrefs

- `0x14003dc2b`: `Access denied for the event %ws`

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
    (void *)0x365,
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
0x14003db90  mov     [rsp+arg_0], rbx
0x14003db95  push    rdi
0x14003db96  sub     rsp, 40h
0x14003db9a  lea     rdi, aGlobalWerkerne_1; "Global\\WerKernelVerticalGeneratingDump"
0x14003dba1  xor     edx, edx; bInheritHandle
0x14003dba3  mov     r8, rdi; lpName
0x14003dba6  mov     ecx, 100001h; dwDesiredAccess
0x14003dbab  call    cs:__imp_OpenMutexW
0x14003dbb2  nop     dword ptr [rax+rax+00h]
0x14003dbb7  mov     rbx, rax
0x14003dbba  lea     rcx, [rax+1]
0x14003dbbe  cmp     rcx, 1
0x14003dbc2  jbe     short loc_14003DC09
0x14003dbc4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003dbc7  mov     rcx, rax; hHandle
0x14003dbca  call    cs:__imp_WaitForSingleObject
0x14003dbd1  nop     dword ptr [rax+rax+00h]
0x14003dbd6  test    eax, 0FFFFFF7Fh
0x14003dbdb  jnz     short loc_14003DBEC
0x14003dbdd  mov     rcx, rbx; hMutex
0x14003dbe0  call    cs:__imp_ReleaseMutex
0x14003dbe7  nop     dword ptr [rax+rax+00h]
0x14003dbec  mov     rcx, rbx; hObject
0x14003dbef  call    cs:__imp_CloseHandle
0x14003dbf6  nop     dword ptr [rax+rax+00h]
0x14003dbfb  xor     eax, eax
0x14003dbfd  mov     rbx, [rsp+48h+arg_0]
0x14003dc02  add     rsp, 40h
0x14003dc06  pop     rdi
0x14003dc07  retn
0x14003dc09  call    cs:__imp_GetLastError
0x14003dc10  nop     dword ptr [rax+rax+00h]
0x14003dc15  cmp     eax, 5
0x14003dc18  jnz     short loc_14003DBFB
0x14003dc1a  call    cs:__imp_GetLastError
0x14003dc21  nop     dword ptr [rax+rax+00h]
0x14003dc26  mov     rcx, [rsp+48h]; this
0x14003dc2b  lea     rdx, aAccessDeniedFo; "Access denied for the event %ws"
0x14003dc32  mov     [rsp+48h+var_18], rdi; char *
0x14003dc37  lea     r9, aCkernelreportW; "CKernelReport::WaitForDumpConversion"
0x14003dc3e  mov     qword ptr [rsp+48h+var_20], rdx; unsigned int
0x14003dc43  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003dc4a  mov     edx, 365h; void *
0x14003dc4f  mov     dword ptr [rsp+48h+var_28], eax; wil::details *
0x14003dc53  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003dc58  mov     eax, 80070005h
0x14003dc5d  jmp     short loc_14003DBFD
```
