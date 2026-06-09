# Microsoft::CoreUI::Registrar::RemoteRegistrarClient::WaitForServiceStartup(void)

- ea: `0x1800c1f1c`
- end: `0x1800c2071`
- name: `?WaitForServiceStartup@RemoteRegistrarClient@Registrar@CoreUI@Microsoft@@CA_NXZ`
- size: `341`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180062790`

## callees

- `0x180007d80`
- `0x18003950c`
- `0x18008f584`
- `0x18009d670`
- `0x1800a2128`
- `0x1800c1f1c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c201d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c201d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c2005`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c2005`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c1f75`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c1f75`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800c2013`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800c2013`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c1fbd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c1fcb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c1fbd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c1fcb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c1f53`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c1f53`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800c1f8b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800c1f8b`

## pseudocode

```c
char Microsoft::CoreUI::Registrar::RemoteRegistrarClient::WaitForServiceStartup(void)
{
  char v0; // si
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rbx
  SC_HANDLE v4; // rax
  signed int LastError; // eax
  bool v6; // zf
  const char *v8; // rdx
  Cn::DllName *v9; // rcx
  void **v10; // r8
  DWORD v11; // eax
  unsigned int (*v12)(struct SC_HANDLE__ *, unsigned int, unsigned int, void *); // rax
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  v0 = 1;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( !v1 )
  {
    v3 = 0;
LABEL_5:
    LastError = GetLastError();
    v6 = LastError == 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError == 0;
    }
    if ( !v6 )
    {
      if ( LastError != -2147024891 )
        CFlat::Abandonment::FailWithHR(LastError, 0, 0);
      v0 = 0;
    }
    goto LABEL_10;
  }
  v4 = OpenServiceW(v1, L"CoreMessagingRegistrar", 0x14u);
  v3 = v4;
  if ( !v4 || !QueryServiceStatus(v4, &ServiceStatus) )
    goto LABEL_5;
  if ( ServiceStatus.dwCurrentState != 4 )
  {
    GetTickCount64();
    while ( !StartServiceW(v3, 0, 0) )
    {
      v11 = GetLastError();
      if ( v11 == 1056 )
        break;
      if ( v11 != 1053 )
        Cn::FailFast::ForWin32();
    }
    v12 = Microsoft::CoreUI::Registrar::g_pfnWaitServiceState;
    if ( !Microsoft::CoreUI::Registrar::g_pfnWaitServiceState )
    {
      Cn::DllName::Import(v9, v8, v10);
      v12 = Microsoft::CoreUI::Registrar::g_pfnWaitServiceState;
    }
    if ( ((unsigned int (__fastcall *)(SC_HANDLE, __int64, __int64))v12)(v3, 8, 0xFFFFFFFFLL) != 4 )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode();
  }
LABEL_10:
  if ( v2 )
  {
    CloseServiceHandle(v2);
    if ( v3 )
      CloseServiceHandle(v3);
  }
  return v0;
}

```

## disassembly

```asm
0x1800c1f1c  mov     [rsp+arg_0], rbx
0x1800c1f21  mov     [rsp+arg_8], rsi
0x1800c1f26  push    rdi
0x1800c1f27  sub     rsp, 60h
0x1800c1f2b  mov     rax, cs:__security_cookie
0x1800c1f32  xor     rax, rsp
0x1800c1f35  mov     [rsp+68h+var_18], rax
0x1800c1f3a  xorps   xmm0, xmm0
0x1800c1f3d  mov     esi, 1
0x1800c1f42  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x1800c1f47  mov     r8d, esi; dwDesiredAccess
0x1800c1f4a  xor     edx, edx; lpDatabaseName
0x1800c1f4c  xor     ecx, ecx; lpMachineName
0x1800c1f4e  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800c1f53  call    cs:__imp_OpenSCManagerW
0x1800c1f59  mov     rdi, rax
0x1800c1f5c  test    rax, rax
0x1800c1f5f  jnz     short loc_1800C1F65
0x1800c1f61  xor     ebx, ebx
0x1800c1f63  jmp     short loc_1800C1F95
0x1800c1f65  mov     r8d, 14h; dwDesiredAccess
0x1800c1f6b  lea     rdx, ServiceName; "CoreMessagingRegistrar"
0x1800c1f72  mov     rcx, rdi; hSCManager
0x1800c1f75  call    cs:__imp_OpenServiceW
0x1800c1f7b  mov     rbx, rax
0x1800c1f7e  test    rax, rax
0x1800c1f81  jz      short loc_1800C1F95
0x1800c1f83  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x1800c1f88  mov     rcx, rax; hService
0x1800c1f8b  call    cs:__imp_QueryServiceStatus
0x1800c1f91  test    eax, eax
0x1800c1f93  jnz     short loc_1800C1FFE
0x1800c1f95  call    cs:__imp_GetLastError
0x1800c1f9b  test    eax, eax
0x1800c1f9d  jle     short loc_1800C1FA9
0x1800c1f9f  movzx   eax, ax
0x1800c1fa2  or      eax, 80070000h
0x1800c1fa7  test    eax, eax
0x1800c1fa9  jz      short loc_1800C1FB5
0x1800c1fab  cmp     eax, 80070005h
0x1800c1fb0  jnz     short loc_1800C1FF1
0x1800c1fb2  xor     sil, sil
0x1800c1fb5  test    rdi, rdi
0x1800c1fb8  jz      short loc_1800C1FD1
0x1800c1fba  mov     rcx, rdi; hSCObject
0x1800c1fbd  call    cs:__imp_CloseServiceHandle
0x1800c1fc3  test    rbx, rbx
0x1800c1fc6  jz      short loc_1800C1FD1
0x1800c1fc8  mov     rcx, rbx; hSCObject
0x1800c1fcb  call    cs:__imp_CloseServiceHandle
0x1800c1fd1  mov     al, sil
0x1800c1fd4  mov     rcx, [rsp+68h+var_18]
0x1800c1fd9  xor     rcx, rsp; StackCookie
0x1800c1fdc  call    __security_check_cookie
0x1800c1fe1  mov     rbx, [rsp+68h+arg_0]
0x1800c1fe6  mov     rsi, [rsp+68h+arg_8]
0x1800c1feb  add     rsp, 60h
0x1800c1fef  pop     rdi
0x1800c1ff0  retn
0x1800c1ff1  xor     r8d, r8d; int
0x1800c1ff4  xor     edx, edx; void *
0x1800c1ff6  mov     ecx, eax; int
0x1800c1ff8  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800c1ffe  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 4
0x1800c2003  jz      short loc_1800C1FB5
0x1800c2005  call    cs:__imp_GetTickCount64
0x1800c200b  xor     r8d, r8d; lpServiceArgVectors
0x1800c200e  xor     edx, edx; dwNumServiceArgs
0x1800c2010  mov     rcx, rbx; hService
0x1800c2013  call    cs:__imp_StartServiceW
0x1800c2019  test    eax, eax
0x1800c201b  jnz     short loc_1800C2037
0x1800c201d  call    cs:__imp_GetLastError
0x1800c2023  cmp     eax, 420h
0x1800c2028  jz      short loc_1800C2037
0x1800c202a  cmp     eax, 41Dh
0x1800c202f  jz      short loc_1800C200B
0x1800c2031  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x1800c2037  mov     rax, cs:?g_pfnWaitServiceState@Registrar@CoreUI@Microsoft@@3P6AKPEAUSC_HANDLE__@@KKPEAX@ZEA; ulong (*Microsoft::CoreUI::Registrar::g_pfnWaitServiceState)(SC_HANDLE__ *,ulong,ulong,void *)
0x1800c203e  test    rax, rax
0x1800c2041  jnz     short loc_1800C204F
0x1800c2043  call    ?Import@DllName@Cn@@QEAAXPEBDPEAPEAX@Z; Cn::DllName::Import(char const *,void * *)
0x1800c2048  mov     rax, cs:?g_pfnWaitServiceState@Registrar@CoreUI@Microsoft@@3P6AKPEAUSC_HANDLE__@@KKPEAX@ZEA; ulong (*Microsoft::CoreUI::Registrar::g_pfnWaitServiceState)(SC_HANDLE__ *,ulong,ulong,void *)
0x1800c204f  xor     r9d, r9d
0x1800c2052  or      r8d, 0FFFFFFFFh
0x1800c2056  mov     rcx, rbx
0x1800c2059  lea     edx, [r9+8]
0x1800c205d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2062  cmp     eax, 4
0x1800c2065  jz      loc_1800C1FB5
0x1800c206b  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
```
