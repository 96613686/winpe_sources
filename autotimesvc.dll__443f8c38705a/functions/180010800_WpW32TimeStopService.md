# WpW32TimeStopService

- ea: `0x180010800`
- end: `0x180010aba`
- name: `WpW32TimeStopService`
- size: `698`
- prototype: `__int64 __fastcall(char)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x1800061ac`
- `0x1800096b0`
- `0x18000d178`
- `0x18000d330`

## callees

- `0x180001010`
- `0x1800010f4`
- `0x180001218`
- `0x1800012f0`
- `0x180002a70`
- `0x180005820`
- `0x180009174`
- `0x180010044`
- `0x180010068`
- `0x180010800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108d7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800109b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800109b1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180010884`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180010884`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800108a7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800108a7`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800108c9`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800108c9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800109be`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800109be`

## string_xrefs

- `0x180010a0a`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`
- `0x180010a85`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 __fastcall WpW32TimeStopService(char a1)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rax
  const char *v5; // r9
  SC_HANDLE v6; // rbx
  DWORD v7; // eax
  unsigned int v8; // r8d
  int v9; // eax
  DWORD dwCurrentState; // eax
  unsigned int LastError; // ebx
  int v12; // edi
  __int64 v13; // rdx
  unsigned int *v15; // [rsp+20h] [rbp-50h]
  unsigned int v16; // [rsp+30h] [rbp-40h] BYREF
  DWORD v17; // [rsp+34h] [rbp-3Ch]
  SC_HANDLE v18; // [rsp+38h] [rbp-38h] BYREF
  SC_HANDLE v19; // [rsp+40h] [rbp-30h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( (unsigned int)dword_18001C010 > 4 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
  {
    LOBYTE(v16) = a1;
    v15 = &v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(
      (__int64)&dword_18001C010,
      (__int64)byte_180017705,
      0);
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( a1 )
    WpW32TimeSetServiceStartType(4u);
  v2 = OpenSCManagerW(0, 0, 1u);
  v18 = v2;
  if ( !v2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C7,
                  (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                  v3);
    goto LABEL_41;
  }
  v4 = OpenServiceW(v2, L"W32Time", 0x24u);
  v19 = v4;
  v6 = v4;
  if ( !v4 )
  {
    v13 = 459;
LABEL_32:
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v13,
           (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
           v5);
    goto LABEL_33;
  }
  if ( ControlService(v4, 1u, &ServiceStatus) )
  {
    dwCurrentState = ServiceStatus.dwCurrentState;
  }
  else
  {
    v7 = GetLastError();
    if ( v7 == 1062 )
    {
      if ( (unsigned int)dword_18001C010 > 4 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)&dword_18001C010,
          (__int64)&unk_1800177E0,
          0,
          0);
      goto LABEL_30;
    }
    if ( v7 != 1061 )
    {
      if ( v7 )
      {
        v9 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x1DB, v8, (const char *)v7, (unsigned int)v15);
LABEL_33:
        LastError = v9;
        goto LABEL_34;
      }
LABEL_30:
      LastError = 0;
LABEL_34:
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
LABEL_41:
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
      return LastError;
    }
    dwCurrentState = ServiceStatus.dwCurrentState;
    if ( ServiceStatus.dwCurrentState == 1 )
      goto LABEL_30;
    if ( ServiceStatus.dwCurrentState != 3 )
    {
      if ( (unsigned int)dword_18001C010 > 2 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
      {
        v17 = ServiceStatus.dwCurrentState;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18001C010,
          (__int64)word_18001782A,
          0,
          0);
      }
      LastError = -2147023835;
      goto LABEL_34;
    }
  }
  v12 = 0;
  if ( dwCurrentState == 1 )
  {
LABEL_27:
    if ( (unsigned int)dword_18001C010 > 4 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_18001C010,
        (__int64)qword_1800178A0,
        0,
        0);
    goto LABEL_30;
  }
  while ( (unsigned int)++v12 <= 5 )
  {
    Sleep(0x1F4u);
    if ( !QueryServiceStatus(v6, &ServiceStatus) )
    {
      v13 = 518;
      goto LABEL_32;
    }
    if ( ServiceStatus.dwCurrentState == 1 )
      goto LABEL_27;
  }
  if ( (unsigned int)dword_18001C010 > 2 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
  {
    v17 = ServiceStatus.dwCurrentState;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C010,
      (__int64)byte_180017801,
      0,
      0);
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
  return 2147943860LL;
}

```

## disassembly

```asm
0x180010800  push    rbp
0x180010802  push    rbx
0x180010803  push    rsi
0x180010804  push    rdi
0x180010805  push    r12
0x180010807  mov     rbp, rsp
0x18001080a  sub     rsp, 70h
0x18001080e  mov     rax, cs:__security_cookie
0x180010815  xor     rax, rsp
0x180010818  mov     [rbp+var_8], rax
0x18001081c  mov     eax, cs:dword_18001C010
0x180010822  lea     rsi, dword_18001C010
0x180010829  mov     bl, cl
0x18001082b  mov     r12d, 200h
0x180010831  cmp     eax, 4
0x180010834  jbe     short loc_180010863
0x180010836  mov     edx, r12d
0x180010839  mov     rcx, rsi
0x18001083c  call    _tlgKeywordOn
0x180010841  test    al, al
0x180010843  jz      short loc_180010863
0x180010845  lea     rax, [rbp+var_40]
0x180010849  mov     byte ptr [rbp+var_40], bl
0x18001084c  xor     r8d, r8d
0x18001084f  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x180010854  lea     rdx, byte_180017705
0x18001085b  mov     rcx, rsi
0x18001085e  call    ??$Write@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &)
0x180010863  xorps   xmm0, xmm0
0x180010866  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x18001086a  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x18001086e  test    bl, bl
0x180010870  jz      short loc_18001087C
0x180010872  mov     ecx, 4; dwStartType
0x180010877  call    ?WpW32TimeSetServiceStartType@@YAJK@Z; WpW32TimeSetServiceStartType(ulong)
0x18001087c  xor     edx, edx; lpDatabaseName
0x18001087e  xor     ecx, ecx; lpMachineName
0x180010880  lea     r8d, [rdx+1]; dwDesiredAccess
0x180010884  call    cs:__imp_OpenSCManagerW
0x18001088a  mov     [rbp+var_38], rax
0x18001088e  test    rax, rax
0x180010891  jz      loc_180010A81
0x180010897  mov     r8d, 24h ; '$'; dwDesiredAccess
0x18001089d  lea     rdx, aW32time; "W32Time"
0x1800108a4  mov     rcx, rax; hSCManager
0x1800108a7  call    cs:__imp_OpenServiceW
0x1800108ad  mov     [rbp+var_30], rax
0x1800108b1  mov     rbx, rax
0x1800108b4  test    rax, rax
0x1800108b7  jz      loc_180010A7A
0x1800108bd  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x1800108c1  mov     edx, 1; dwControl
0x1800108c6  mov     rcx, rax; hService
0x1800108c9  call    cs:__imp_ControlService
0x1800108cf  test    eax, eax
0x1800108d1  jnz     loc_18001099B
0x1800108d7  call    cs:__imp_GetLastError
0x1800108dd  cmp     eax, 426h
0x1800108e2  jnz     short loc_180010920
0x1800108e4  mov     eax, cs:dword_18001C010
0x1800108ea  cmp     eax, 4
0x1800108ed  jbe     loc_1800109FD
0x1800108f3  mov     rdx, r12
0x1800108f6  mov     rcx, rsi
0x1800108f9  call    _tlgKeywordOn
0x1800108fe  test    al, al
0x180010900  jz      loc_1800109FD
0x180010906  xor     r9d, r9d
0x180010909  lea     rdx, unk_1800177E0
0x180010910  xor     r8d, r8d
0x180010913  mov     rcx, rsi
0x180010916  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001091b  jmp     loc_1800109FD
0x180010920  cmp     eax, 425h
0x180010925  jz      short loc_180010945
0x180010927  test    eax, eax
0x180010929  jz      loc_1800109FD
0x18001092f  mov     rcx, [rbp+28h]; this
0x180010933  mov     r9d, eax; char *
0x180010936  mov     edx, 1DBh; void *
0x18001093b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010940  jmp     loc_180010A16
0x180010945  mov     eax, [rbp+ServiceStatus.dwCurrentState]
0x180010948  cmp     eax, 1
0x18001094b  jz      loc_1800109FD
0x180010951  cmp     eax, 3
0x180010954  jz      short loc_18001099E
0x180010956  mov     eax, cs:dword_18001C010
0x18001095c  cmp     eax, 2
0x18001095f  jbe     short loc_180010994
0x180010961  mov     rdx, r12
0x180010964  mov     rcx, rsi
0x180010967  call    _tlgKeywordOn
0x18001096c  test    al, al
0x18001096e  jz      short loc_180010994
0x180010970  mov     eax, [rbp+ServiceStatus.dwCurrentState]
0x180010973  lea     rdx, word_18001782A
0x18001097a  mov     [rbp+var_3C], eax
0x18001097d  xor     r9d, r9d
0x180010980  lea     rax, [rbp+var_3C]
0x180010984  xor     r8d, r8d
0x180010987  mov     rcx, rsi
0x18001098a  mov     qword ptr [rsp+70h+var_50], rax
0x18001098f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010994  mov     ebx, 80070425h
0x180010999  jmp     short loc_180010A18
0x18001099b  mov     eax, [rbp+ServiceStatus.dwCurrentState]
0x18001099e  xor     edi, edi
0x1800109a0  cmp     eax, 1
0x1800109a3  jz      short loc_1800109CE
0x1800109a5  inc     edi
0x1800109a7  cmp     edi, 5
0x1800109aa  ja      short loc_180010A23
0x1800109ac  mov     ecx, 1F4h; dwMilliseconds
0x1800109b1  call    cs:__imp_Sleep
0x1800109b7  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800109bb  mov     rcx, rbx; hService
0x1800109be  call    cs:__imp_QueryServiceStatus
0x1800109c4  test    eax, eax
0x1800109c6  jz      short loc_180010A01
0x1800109c8  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x1800109cc  jnz     short loc_1800109A5
0x1800109ce  mov     eax, cs:dword_18001C010
0x1800109d4  cmp     eax, 4
0x1800109d7  jbe     short loc_1800109FD
0x1800109d9  mov     rdx, r12
0x1800109dc  mov     rcx, rsi
0x1800109df  call    _tlgKeywordOn
0x1800109e4  test    al, al
0x1800109e6  jz      short loc_1800109FD
0x1800109e8  xor     r9d, r9d
0x1800109eb  lea     rdx, qword_1800178A0
0x1800109f2  xor     r8d, r8d
0x1800109f5  mov     rcx, rsi
0x1800109f8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800109fd  xor     ebx, ebx
0x1800109ff  jmp     short loc_180010A18
0x180010a01  mov     edx, 206h; void *
0x180010a06  mov     rcx, [rbp+28h]; this
0x180010a0a  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x180010a11  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010a16  mov     ebx, eax
0x180010a18  lea     rcx, [rbp+var_30]
0x180010a1c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180010a21  jmp     short loc_180010A98
0x180010a23  mov     eax, cs:dword_18001C010
0x180010a29  cmp     eax, 2
0x180010a2c  jbe     short loc_180010A61
0x180010a2e  mov     rdx, r12
0x180010a31  mov     rcx, rsi
0x180010a34  call    _tlgKeywordOn
0x180010a39  test    al, al
0x180010a3b  jz      short loc_180010A61
0x180010a3d  mov     eax, [rbp+ServiceStatus.dwCurrentState]
0x180010a40  lea     rdx, byte_180017801
0x180010a47  mov     [rbp+var_3C], eax
0x180010a4a  xor     r9d, r9d
0x180010a4d  lea     rax, [rbp+var_3C]
0x180010a51  xor     r8d, r8d
0x180010a54  mov     rcx, rsi
0x180010a57  mov     qword ptr [rsp+70h+var_50], rax
0x180010a5c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010a61  lea     rcx, [rbp+var_30]
0x180010a65  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180010a6a  lea     rcx, [rbp+var_38]
0x180010a6e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180010a73  mov     eax, 800705B4h
0x180010a78  jmp     short loc_180010AA3
0x180010a7a  mov     edx, 1CBh
0x180010a7f  jmp     short loc_180010A06
0x180010a81  mov     rcx, [rbp+28h]; this
0x180010a85  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x180010a8c  mov     edx, 1C7h; void *
0x180010a91  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010a96  mov     ebx, eax
0x180010a98  lea     rcx, [rbp+var_38]
0x180010a9c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180010aa1  mov     eax, ebx
0x180010aa3  mov     rcx, [rbp+var_8]
0x180010aa7  xor     rcx, rsp; StackCookie
0x180010aaa  call    __security_check_cookie
0x180010aaf  add     rsp, 70h
0x180010ab3  pop     r12
0x180010ab5  pop     rdi
0x180010ab6  pop     rsi
0x180010ab7  pop     rbx
0x180010ab8  pop     rbp
0x180010ab9  retn
```
