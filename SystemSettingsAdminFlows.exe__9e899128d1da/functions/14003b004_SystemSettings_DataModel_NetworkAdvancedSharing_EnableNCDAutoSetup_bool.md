# SystemSettings::DataModel::NetworkAdvancedSharing::EnableNCDAutoSetup(bool)

- ea: `0x14003b004`
- end: `0x14003b18c`
- name: `?EnableNCDAutoSetup@NetworkAdvancedSharing@DataModel@SystemSettings@@SAJ_N@Z`
- size: `392`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x14001f3b4`
- `0x14001f3d4`
- `0x140029ed8`
- `0x14003af00`
- `0x14003b004`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14003b097`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14003b097`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14003b0e1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14003b0e1`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x14003b12f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x14003b12f`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14003b14b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14003b14b`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::NetworkAdvancedSharing::EnableNCDAutoSetup(unsigned __int8 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  SC_HANDLE v6; // rax
  const char *v7; // r9
  unsigned int v8; // ebx
  SC_HANDLE v9; // rax
  const char *v10; // r9
  unsigned int LastError; // ebx
  int v12; // [rsp+20h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES *v13; // [rsp+30h] [rbp-58h]
  SC_HANDLE v14; // [rsp+40h] [rbp-48h] BYREF
  SC_HANDLE v15; // [rsp+48h] [rbp-40h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  LODWORD(v14) = a1;
  v2 = _RegSetKeyValueWithSDDL(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup\\Private",
         L"AutoSetup",
         4u,
         &v14,
         4u,
         v13);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( (v3 & 0x80000000) == 0 )
  {
    v6 = OpenSCManagerW(0, 0, 1u);
    v14 = v6;
    if ( v6 )
    {
      v9 = OpenServiceW(v6, L"NcdAutoSetup", 0x30u);
      v15 = v9;
      if ( v9 )
      {
        if ( a1 )
        {
          StartServiceW(v9, 0, 0);
        }
        else
        {
          memset(&ServiceStatus, 0, sizeof(ServiceStatus));
          ControlService(v9, 1u, &ServiceStatus);
        }
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
        result = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x31,
                      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
                      v10);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
        result = LastError;
      }
    }
    else
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2E,
             (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
             v7);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
      result = v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadvancedsharing.cpp",
      (const char *)v3,
      v12);
    result = v3;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      LODWORD(v14) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x3F,
                       (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadvancedsharing\\lib\\networkadv"
                                     "ancedsharing.cpp",
                       v4);
      result = (unsigned int)v14;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x14003b004  mov     r11, rsp
0x14003b007  mov     [r11+8], rbx
0x14003b00b  push    rdi
0x14003b00c  sub     rsp, 80h
0x14003b013  mov     rax, cs:__security_cookie
0x14003b01a  xor     rax, rsp
0x14003b01d  mov     [rsp+88h+var_18], rax
0x14003b022  movzx   edi, cl
0x14003b025  mov     dword ptr [rsp+88h+var_48], edi
0x14003b029  mov     r9d, 4; unsigned int
0x14003b02f  mov     [r11-60h], r9d
0x14003b033  lea     rax, [r11-48h]
0x14003b037  mov     [r11-68h], rax
0x14003b03b  lea     r8, aAutosetup; "AutoSetup"
0x14003b042  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14003b049  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14003b050  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x14003b055  mov     ebx, eax
0x14003b057  test    eax, eax
0x14003b059  jle     short loc_14003B064
0x14003b05b  movzx   ebx, ax
0x14003b05e  or      ebx, 80070000h
0x14003b064  test    ebx, ebx
0x14003b066  jns     short loc_14003B08B
0x14003b068  mov     rcx, [rsp+88h]; this
0x14003b070  mov     r9d, ebx; char *
0x14003b073  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b07a  mov     edx, 2Ah ; '*'; void *
0x14003b07f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b084  mov     eax, ebx
0x14003b086  jmp     loc_14003B16D
0x14003b08b  mov     ebx, 1
0x14003b090  mov     r8d, ebx; dwDesiredAccess
0x14003b093  xor     edx, edx; lpDatabaseName
0x14003b095  xor     ecx, ecx; lpMachineName
0x14003b097  call    cs:__imp_OpenSCManagerW
0x14003b09d  mov     [rsp+88h+var_48], rax
0x14003b0a2  test    rax, rax
0x14003b0a5  jnz     short loc_14003B0D1
0x14003b0a7  mov     rcx, [rsp+88h]; this
0x14003b0af  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b0b6  lea     edx, [rbx+2Dh]; void *
0x14003b0b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003b0be  mov     ebx, eax
0x14003b0c0  lea     rcx, [rsp+88h+var_48]
0x14003b0c5  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14003b0ca  mov     eax, ebx
0x14003b0cc  jmp     loc_14003B16D
0x14003b0d1  mov     r8d, 30h ; '0'; dwDesiredAccess
0x14003b0d7  lea     rdx, ServiceName; "NcdAutoSetup"
0x14003b0de  mov     rcx, rax; hSCManager
0x14003b0e1  call    cs:__imp_OpenServiceW
0x14003b0e7  mov     [rsp+88h+var_40], rax
0x14003b0ec  test    rax, rax
0x14003b0ef  jnz     short loc_14003B122
0x14003b0f1  mov     rcx, [rsp+88h]; this
0x14003b0f9  lea     r8, aPcshellShellSy_16; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003b100  lea     edx, [rax+31h]; void *
0x14003b103  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003b108  mov     ebx, eax
0x14003b10a  lea     rcx, [rsp+88h+var_40]
0x14003b10f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14003b114  lea     rcx, [rsp+88h+var_48]
0x14003b119  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14003b11e  mov     eax, ebx
0x14003b120  jmp     short loc_14003B16D
0x14003b122  mov     rcx, rax; hService
0x14003b125  test    dil, dil
0x14003b128  jz      short loc_14003B137
0x14003b12a  xor     r8d, r8d; lpServiceArgVectors
0x14003b12d  xor     edx, edx; dwNumServiceArgs
0x14003b12f  call    cs:__imp_StartServiceW
0x14003b135  jmp     short loc_14003B151
0x14003b137  xorps   xmm0, xmm0
0x14003b13a  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x14003b13f  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x14003b144  lea     r8, [rsp+88h+ServiceStatus]; lpServiceStatus
0x14003b149  mov     edx, ebx; dwControl
0x14003b14b  call    cs:__imp_ControlService
0x14003b151  lea     rcx, [rsp+88h+var_40]
0x14003b156  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14003b15b  lea     rcx, [rsp+88h+var_48]
0x14003b160  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14003b165  xor     eax, eax
0x14003b167  jmp     short loc_14003B16D
0x14003b169  mov     eax, dword ptr [rsp+88h+var_48]
0x14003b16d  mov     rcx, [rsp+88h+var_18]
0x14003b172  xor     rcx, rsp; StackCookie
0x14003b175  call    __security_check_cookie
0x14003b17a  mov     rbx, [rsp+88h+arg_0]
0x14003b182  add     rsp, 80h
0x14003b189  pop     rdi
0x14003b18a  retn
```
