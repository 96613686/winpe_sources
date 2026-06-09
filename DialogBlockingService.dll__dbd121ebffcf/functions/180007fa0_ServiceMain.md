# ServiceMain

- ea: `0x180007fa0`
- end: `0x1800080d7`
- name: `ServiceMain`
- size: `311`
- prototype: `void()`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001620`
- `0x180001644`
- `0x180004140`
- `0x180006804`
- `0x1800077c4`
- `0x180007fa0`
- `0x1800099d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080b4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008069`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008069`

## string_xrefs

- `0x18000807c`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
void ServiceMain()
{
  signed int v0; // eax
  Windows::Internal::DialogBlocking::ServiceSessions *v1; // rbx
  char v2; // [rsp+20h] [rbp-39h] BYREF
  char *v3; // [rsp+28h] [rbp-31h] BYREF
  Windows::Internal::ServiceModuleBase *v4; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v5[5]; // [rsp+38h] [rbp-21h] BYREF
  SERVICE_STATUS_HANDLE hServiceStatus[2]; // [rsp+60h] [rbp+7h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp+17h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp+37h]
  Windows::Internal::DialogBlocking::ServiceSessions *v9; // [rsp+98h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  hObject = 0;
  v9 = 0;
  v2 = 0;
  v4 = 0;
  v5[0] = hServiceStatus;
  v5[1] = &v2;
  v5[2] = &v4;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  v5[3] = &v3;
  *(_OWORD *)hServiceStatus = 0;
  ServiceStatus.dwServiceType = 16;
  ServiceStatus.dwCurrentState = 4;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 4097;
  v0 = _lambda_3b1bd3dc794689acd37fb36ea0a30994_::operator()((__int64)v5);
  LODWORD(v3) = v0;
  if ( (v0 & 0x1FFF0000) == 0x70000 )
  {
    ServiceStatus.dwWin32ExitCode = (unsigned __int16)v0;
  }
  else
  {
    if ( v0 < 0 )
      ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = v0;
  }
  if ( v4 )
    Windows::Internal::ServiceModuleBase::Uninitialize(v4);
  ServiceStatus.dwCurrentState = 1;
  SetServiceStatus(hServiceStatus[1], &ServiceStatus);
  if ( (int)v3 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v3);
  v1 = v9;
  if ( v9 )
  {
    Windows::Internal::DialogBlocking::ServiceSessions::~ServiceSessions(v9);
    operator delete(v1);
  }
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180007fa0  mov     [rsp-8+arg_0], rbx
0x180007fa5  push    rbp
0x180007fa6  lea     rbp, [rsp-57h]
0x180007fab  sub     rsp, 0B0h
0x180007fb2  mov     rax, cs:__security_cookie
0x180007fb9  xor     rax, rsp
0x180007fbc  mov     [rbp+57h+var_10], rax
0x180007fc0  xor     eax, eax
0x180007fc2  lea     rcx, [rbp+57h+var_78]
0x180007fc6  mov     [rbp+57h+hObject], rax
0x180007fca  xorps   xmm1, xmm1
0x180007fcd  mov     [rbp+57h+var_18], rax
0x180007fd1  xorps   xmm0, xmm0
0x180007fd4  mov     [rbp+57h+var_90], al
0x180007fd7  mov     [rbp+57h+var_80], rax
0x180007fdb  lea     rax, [rbp+57h+hServiceStatus]
0x180007fdf  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm1
0x180007fe3  mov     [rbp+57h+var_78], rax
0x180007fe7  lea     rax, [rbp+57h+var_90]
0x180007feb  mov     [rbp+57h+var_70], rax
0x180007fef  lea     rax, [rbp+57h+var_80]
0x180007ff3  mov     [rbp+57h+var_68], rax
0x180007ff7  lea     rax, [rbp+57h+var_88]
0x180007ffb  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm1
0x180007fff  mov     [rbp+57h+var_60], rax
0x180008003  movdqa  xmmword ptr [rbp+57h+hServiceStatus], xmm0
0x180008008  mov     [rbp+57h+ServiceStatus.dwServiceType], 10h
0x18000800f  mov     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x180008016  mov     qword ptr [rbp+57h+ServiceStatus.dwControlsAccepted], 1001h
0x18000801e  call    ??R_lambda_3b1bd3dc794689acd37fb36ea0a30994_@@QEBA@XZ; _lambda_3b1bd3dc794689acd37fb36ea0a30994_::operator()(void)
0x180008023  mov     ecx, eax
0x180008025  mov     dword ptr [rbp+57h+var_88], eax
0x180008028  and     ecx, 1FFF0000h
0x18000802e  cmp     ecx, 70000h
0x180008034  jnz     short loc_18000803E
0x180008036  movzx   eax, ax
0x180008039  mov     [rbp+57h+ServiceStatus.dwWin32ExitCode], eax
0x18000803c  jmp     short loc_18000804C
0x18000803e  test    eax, eax
0x180008040  jns     short loc_180008049
0x180008042  mov     [rbp+57h+ServiceStatus.dwWin32ExitCode], 42Ah
0x180008049  mov     [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], eax
0x18000804c  mov     rcx, [rbp+57h+var_80]; this
0x180008050  test    rcx, rcx
0x180008053  jz      short loc_18000805A
0x180008055  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000805a  mov     rcx, [rbp+57h+hServiceStatus+8]; hServiceStatus
0x18000805e  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180008062  mov     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x180008069  call    cs:__imp_SetServiceStatus
0x18000806f  mov     r9d, dword ptr [rbp+57h+var_88]; char *
0x180008073  test    r9d, r9d
0x180008076  jns     short loc_18000808D
0x180008078  mov     rcx, [rbp+5Fh]; this
0x18000807c  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180008083  mov     edx, 275h; void *
0x180008088  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000808d  mov     rbx, [rbp+57h+var_18]
0x180008091  test    rbx, rbx
0x180008094  jz      short loc_1800080AB
0x180008096  mov     rcx, rbx; this
0x180008099  call    ??1ServiceSessions@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::ServiceSessions::~ServiceSessions(void)
0x18000809e  mov     edx, 60h ; '`'; unsigned __int64
0x1800080a3  mov     rcx, rbx; void *
0x1800080a6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800080ab  mov     rcx, [rbp+57h+hObject]; hObject
0x1800080af  test    rcx, rcx
0x1800080b2  jz      short loc_1800080BA
0x1800080b4  call    cs:__imp_CloseHandle
0x1800080ba  mov     rcx, [rbp+57h+var_10]
0x1800080be  xor     rcx, rsp; StackCookie
0x1800080c1  call    __security_check_cookie
0x1800080c6  mov     rbx, [rsp+0B0h+arg_0]
0x1800080ce  add     rsp, 0B0h
0x1800080d5  pop     rbp
0x1800080d6  retn
```
