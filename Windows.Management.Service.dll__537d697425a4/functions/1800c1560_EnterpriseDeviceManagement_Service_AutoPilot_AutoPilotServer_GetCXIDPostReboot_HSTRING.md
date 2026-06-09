# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotServer::GetCXIDPostReboot(HSTRING__ * *)

- ea: `0x1800c1560`
- end: `0x1800c172f`
- name: `?GetCXIDPostReboot@AutoPilotServer@AutoPilot@Service@EnterpriseDeviceManagement@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180067e54`
- `0x180080984`
- `0x180088144`
- `0x18008aea8`
- `0x18008aecc`
- `0x180090810`
- `0x1800a35f8`
- `0x1800bd914`
- `0x1800c1560`
- `0x180179f94`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c16c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c16c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c15c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1673`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c15c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1673`

## string_xrefs

- `0x1800c1620`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotserver.cpp`
- `0x1800c1687`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotserver.cpp`
- `0x1800c16d9`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotserver.cpp`
- `0x1800c15b7`: `UpdateRebootCXID`
- `0x1800c1645`: `UpdateRebootCXID`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotServer::GetCXIDPostReboot(
        EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotServer *this,
        HSTRING *a2)
{
  bool v3; // al
  const WCHAR *v4; // rsi
  const WCHAR *v5; // rdx
  LSTATUS ValueW; // eax
  PVOID pvData; // rbx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  HRESULT v11; // eax
  int pdwType; // [rsp+20h] [rbp-30h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-30h]
  _BYTE v15[16]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD pcbData; // [rsp+88h] [rbp+38h] BYREF
  HSTRING string; // [rsp+90h] [rbp+40h] BYREF
  PVOID v19; // [rsp+98h] [rbp+48h] BYREF

  *a2 = 0;
  pcbData = 0;
  v19 = 0;
  v3 = ZTPIsStateSeparationEnabled();
  v4 = (const WCHAR *)&stru_18022EC60;
  v5 = (const WCHAR *)&stru_18022EC60;
  if ( !v3 )
    v5 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v5, L"UpdateRebootCXID", 2u, 0, 0, &pcbData);
  if ( ValueW )
  {
    if ( (unsigned int)(ValueW - 2) > 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_17;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v15,
    0,
    (unsigned __int64)pcbData >> 1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v19,
    v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v15);
  pvData = v19;
  if ( v19 )
  {
    if ( !ZTPIsStateSeparationEnabled() )
      v4 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
    v9 = RegGetValueW(HKEY_LOCAL_MACHINE, v4, L"UpdateRebootCXID", 2u, 0, pvData, &pcbData);
    if ( v9 )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xBF,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotserver.cpp",
             (const char *)v9,
             pdwTypea);
    }
    else
    {
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)pvData + v10) );
      v11 = WindowsCreateString((PCNZWCH)pvData, v10, &string);
      v8 = v11;
      if ( v11 >= 0 )
      {
        *a2 = string;
        string = 0;
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
LABEL_17:
        v8 = 0;
        goto LABEL_18;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotserver.cpp",
        (const char *)(unsigned int)v11,
        pdwTypea);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
    }
  }
  else
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotserver.cpp",
      (const char *)0x8007000ELL,
      pdwType);
  }
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
  return v8;
}

```

## disassembly

```asm
0x1800c1560  mov     [rsp-28h+arg_0], rbx
0x1800c1565  push    rbp
0x1800c1566  push    rsi
0x1800c1567  push    rdi
0x1800c1568  push    r13
0x1800c156a  push    r14
0x1800c156c  mov     rbp, rsp
0x1800c156f  sub     rsp, 50h
0x1800c1573  xor     r14d, r14d
0x1800c1576  mov     rdi, rdx
0x1800c1579  mov     [rdx], r14
0x1800c157c  mov     [rbp+arg_8], r14d
0x1800c1580  mov     [rbp+arg_18], r14
0x1800c1584  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800c1589  test    al, al
0x1800c158b  lea     rsi, stru_18022EC60
0x1800c1592  lea     rax, [rbp+arg_8]
0x1800c1596  mov     rdx, rsi
0x1800c1599  mov     [rsp+50h+pcbData], rax; pcbData
0x1800c159e  lea     r13, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800c15a5  mov     [rsp+50h+pvData], r14; pvData
0x1800c15aa  lea     r9d, [r14+2]; dwFlags
0x1800c15ae  cmovz   rdx, r13; lpSubKey
0x1800c15b2  mov     [rsp+50h+pdwType], r14; int
0x1800c15b7  lea     r8, aUpdaterebootcx; "UpdateRebootCXID"
0x1800c15be  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800c15c5  call    cs:__imp_RegGetValueW
0x1800c15cc  nop     dword ptr [rax+rax+00h]
0x1800c15d1  test    eax, eax
0x1800c15d3  jz      short loc_1800C15EB
0x1800c15d5  add     eax, 0FFFFFFFEh
0x1800c15d8  cmp     eax, 1
0x1800c15db  jbe     loc_1800C170C
0x1800c15e1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "((ERROR_FILE_NOT_FOUND == result) || (ERROR_PATH_NOT_FOUND == result))", "Failed with an unexpected error while getting query size")
0x1800c15e6  jmp     loc_1800C170C
0x1800c15eb  mov     r8d, [rbp+arg_8]
0x1800c15ef  lea     rcx, [rbp+var_10]
0x1800c15f3  shr     r8, 1
0x1800c15f6  xor     edx, edx
0x1800c15f8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800c15fd  lea     rdx, [rbp+var_10]
0x1800c1601  lea     rcx, [rbp+arg_18]
0x1800c1605  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800c160a  lea     rcx, [rbp+var_10]
0x1800c160e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c1613  mov     rbx, [rbp+arg_18]
0x1800c1617  test    rbx, rbx
0x1800c161a  jnz     short loc_1800C163E
0x1800c161c  mov     rcx, [rbp+28h]; this
0x1800c1620  lea     r8, aOnecoreuapAdmi_60; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c1627  mov     ebx, 8007000Eh
0x1800c162c  mov     edx, 0B6h; void *
0x1800c1631  mov     r9d, ebx; char *
0x1800c1634  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1639  jmp     loc_1800C170F
0x1800c163e  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800c1643  test    al, al
0x1800c1645  lea     r8, aUpdaterebootcx; "UpdateRebootCXID"
0x1800c164c  lea     rax, [rbp+arg_8]
0x1800c1650  mov     r9d, 2; dwFlags
0x1800c1656  mov     [rsp+50h+pcbData], rax; pcbData
0x1800c165b  cmovz   rsi, r13
0x1800c165f  mov     rdx, rsi; lpSubKey
0x1800c1662  mov     [rsp+50h+pvData], rbx; pvData
0x1800c1667  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800c166e  mov     [rsp+50h+pdwType], r14; int
0x1800c1673  call    cs:__imp_RegGetValueW
0x1800c167a  nop     dword ptr [rax+rax+00h]
0x1800c167f  test    eax, eax
0x1800c1681  jz      short loc_1800C169F
0x1800c1683  mov     rcx, [rbp+28h]; this
0x1800c1687  lea     r8, aOnecoreuapAdmi_60; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c168e  mov     r9d, eax; char *
0x1800c1691  mov     edx, 0BFh; void *
0x1800c1696  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c169b  mov     ebx, eax
0x1800c169d  jmp     short loc_1800C170F
0x1800c169f  xor     edx, edx
0x1800c16a1  mov     [rbp+string], r14
0x1800c16a5  lea     rcx, [rbp+string]
0x1800c16a9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800c16ae  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800c16b2  inc     rdx; length
0x1800c16b5  cmp     [rbx+rdx*2], r14w
0x1800c16ba  jnz     short loc_1800C16B2
0x1800c16bc  lea     r8, [rbp+string]; string
0x1800c16c0  mov     rcx, rbx; sourceString
0x1800c16c3  call    cs:__imp_WindowsCreateString
0x1800c16ca  nop     dword ptr [rax+rax+00h]
0x1800c16cf  mov     ebx, eax
0x1800c16d1  test    eax, eax
0x1800c16d3  jns     short loc_1800C16F8
0x1800c16d5  mov     rcx, [rbp+28h]; this
0x1800c16d9  lea     r8, aOnecoreuapAdmi_60; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c16e0  mov     r9d, eax; char *
0x1800c16e3  mov     edx, 0C2h; void *
0x1800c16e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c16ed  lea     rcx, [rbp+string]; this
0x1800c16f1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c16f6  jmp     short loc_1800C170F
0x1800c16f8  mov     rax, [rbp+string]
0x1800c16fc  lea     rcx, [rbp+string]; this
0x1800c1700  mov     [rdi], rax
0x1800c1703  mov     [rbp+string], r14
0x1800c1707  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c170c  mov     ebx, r14d
0x1800c170f  lea     rcx, [rbp+arg_18]
0x1800c1713  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c1718  mov     eax, ebx
0x1800c171a  mov     rbx, [rsp+50h+arg_0]
0x1800c1722  add     rsp, 50h
0x1800c1726  pop     r14
0x1800c1728  pop     r13
0x1800c172a  pop     rdi
0x1800c172b  pop     rsi
0x1800c172c  pop     rbp
0x1800c172d  retn
```
