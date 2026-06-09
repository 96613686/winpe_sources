# StartAppLockerFltr(void)

- ea: `0x180004754`
- end: `0x18000481f`
- name: `?StartAppLockerFltr@@YAJXZ`
- size: `203`
- prototype: `DWORD(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180003c80`

## callees

- `0x180004754`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000478e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000478e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047db`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800047bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800047fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004807`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800047bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800047fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004807`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800047ae`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800047ae`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800047d1`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800047d1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000476b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000476b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD StartAppLockerFltr(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  unsigned int v5; // ebx
  signed int LastError; // eax

  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( !v0 )
    goto LABEL_2;
  v3 = OpenServiceW(v0, L"applockerfltr", 0x10u);
  v4 = v3;
  if ( !v3 )
  {
    CloseServiceHandle(v1);
LABEL_2:
    if ( (int)GetLastError() > 0 )
      return (unsigned __int16)GetLastError() | 0xC0070000;
    else
      return GetLastError();
  }
  v5 = 0;
  if ( !StartServiceW(v3, 0, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError == 1056 )
    {
      v5 = 0;
    }
    else if ( LastError > 0 )
    {
      v5 = (unsigned __int16)LastError | 0xC0070000;
    }
  }
  CloseServiceHandle(v4);
  CloseServiceHandle(v1);
  return v5;
}

```

## disassembly

```asm
0x180004754  mov     [rsp+arg_0], rbx
0x180004759  mov     [rsp+arg_8], rsi
0x18000475e  push    rdi
0x18000475f  sub     rsp, 20h
0x180004763  xor     edx, edx; lpDatabaseName
0x180004765  xor     ecx, ecx; lpMachineName
0x180004767  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000476b  call    cs:__imp_OpenSCManagerW
0x180004771  mov     rdi, rax
0x180004774  test    rax, rax
0x180004777  jnz     short loc_18000479E
0x180004779  call    cs:__imp_GetLastError
0x18000477f  test    eax, eax
0x180004781  jg      short loc_18000478E
0x180004783  call    cs:__imp_GetLastError
0x180004789  jmp     loc_18000480F
0x18000478e  call    cs:__imp_GetLastError
0x180004794  movzx   eax, ax
0x180004797  or      eax, 0C0070000h
0x18000479c  jmp     short loc_18000480F
0x18000479e  mov     r8d, 10h; dwDesiredAccess
0x1800047a4  lea     rdx, ServiceName; "applockerfltr"
0x1800047ab  mov     rcx, rdi; hSCManager
0x1800047ae  call    cs:__imp_OpenServiceW
0x1800047b4  mov     rsi, rax
0x1800047b7  test    rax, rax
0x1800047ba  jnz     short loc_1800047C7
0x1800047bc  mov     rcx, rdi; hSCObject
0x1800047bf  call    cs:__imp_CloseServiceHandle
0x1800047c5  jmp     short loc_180004779
0x1800047c7  xor     r8d, r8d; lpServiceArgVectors
0x1800047ca  xor     edx, edx; dwNumServiceArgs
0x1800047cc  mov     rcx, rsi; hService
0x1800047cf  xor     ebx, ebx
0x1800047d1  call    cs:__imp_StartServiceW
0x1800047d7  test    eax, eax
0x1800047d9  jnz     short loc_1800047FB
0x1800047db  call    cs:__imp_GetLastError
0x1800047e1  mov     ebx, eax
0x1800047e3  cmp     eax, 420h
0x1800047e8  jnz     short loc_1800047EE
0x1800047ea  xor     ebx, ebx
0x1800047ec  jmp     short loc_1800047FB
0x1800047ee  test    eax, eax
0x1800047f0  jle     short loc_1800047FB
0x1800047f2  movzx   ebx, ax
0x1800047f5  or      ebx, 0C0070000h
0x1800047fb  mov     rcx, rsi; hSCObject
0x1800047fe  call    cs:__imp_CloseServiceHandle
0x180004804  mov     rcx, rdi; hSCObject
0x180004807  call    cs:__imp_CloseServiceHandle
0x18000480d  mov     eax, ebx
0x18000480f  mov     rbx, [rsp+28h+arg_0]
0x180004814  mov     rsi, [rsp+28h+arg_8]
0x180004819  add     rsp, 20h
0x18000481d  pop     rdi
0x18000481e  retn
```
