# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotServer::GetCXIDPostReboot(HSTRING__ * *)

- ea: `0x1800bf6f0`
- end: `0x1800bf8ac`
- name: `?GetCXIDPostReboot@AutoPilotServer@AutoPilot@Service@EnterpriseDeviceManagement@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180067a54`
- `0x18007ff90`
- `0x1800873a4`
- `0x180089ff4`
- `0x18008a014`
- `0x18008f6a8`
- `0x1800a1fe4`
- `0x1800bbb40`
- `0x1800bf6f0`
- `0x1801759bc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bf847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bf847`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf755`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf7fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf755`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf7fd`

## string_xrefs

- `0x1800bf7aa`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotserver.cpp`
- `0x1800bf80b`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotserver.cpp`
- `0x1800bf857`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotserver.cpp`
- `0x1800bf747`: `UpdateRebootCXID`
- `0x1800bf7cf`: `UpdateRebootCXID`

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
  v4 = (const WCHAR *)&stru_180228C20;
  v5 = (const WCHAR *)&stru_180228C20;
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
0x1800bf6f0  mov     [rsp-28h+arg_0], rbx
0x1800bf6f5  push    rbp
0x1800bf6f6  push    rsi
0x1800bf6f7  push    rdi
0x1800bf6f8  push    r13
0x1800bf6fa  push    r14
0x1800bf6fc  mov     rbp, rsp
0x1800bf6ff  sub     rsp, 50h
0x1800bf703  xor     r14d, r14d
0x1800bf706  mov     rdi, rdx
0x1800bf709  mov     [rdx], r14
0x1800bf70c  mov     [rbp+arg_8], r14d
0x1800bf710  mov     [rbp+arg_18], r14
0x1800bf714  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800bf719  test    al, al
0x1800bf71b  lea     rsi, stru_180228C20
0x1800bf722  lea     rax, [rbp+arg_8]
0x1800bf726  mov     rdx, rsi
0x1800bf729  mov     [rsp+50h+pcbData], rax; pcbData
0x1800bf72e  lea     r13, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800bf735  mov     [rsp+50h+pvData], r14; pvData
0x1800bf73a  lea     r9d, [r14+2]; dwFlags
0x1800bf73e  cmovz   rdx, r13; lpSubKey
0x1800bf742  mov     [rsp+50h+pdwType], r14; int
0x1800bf747  lea     r8, aUpdaterebootcx; "UpdateRebootCXID"
0x1800bf74e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800bf755  call    cs:__imp_RegGetValueW
0x1800bf75b  test    eax, eax
0x1800bf75d  jz      short loc_1800BF775
0x1800bf75f  add     eax, 0FFFFFFFEh
0x1800bf762  cmp     eax, 1
0x1800bf765  jbe     loc_1800BF88A
0x1800bf76b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800bf770  jmp     loc_1800BF88A
0x1800bf775  mov     r8d, [rbp+arg_8]
0x1800bf779  lea     rcx, [rbp+var_10]
0x1800bf77d  shr     r8, 1
0x1800bf780  xor     edx, edx
0x1800bf782  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800bf787  lea     rdx, [rbp+var_10]
0x1800bf78b  lea     rcx, [rbp+arg_18]
0x1800bf78f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800bf794  lea     rcx, [rbp+var_10]
0x1800bf798  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bf79d  mov     rbx, [rbp+arg_18]
0x1800bf7a1  test    rbx, rbx
0x1800bf7a4  jnz     short loc_1800BF7C8
0x1800bf7a6  mov     rcx, [rbp+28h]; this
0x1800bf7aa  lea     r8, aOnecoreuapAdmi_60; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800bf7b1  mov     ebx, 8007000Eh
0x1800bf7b6  mov     edx, 0B6h; void *
0x1800bf7bb  mov     r9d, ebx; char *
0x1800bf7be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf7c3  jmp     loc_1800BF88D
0x1800bf7c8  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800bf7cd  test    al, al
0x1800bf7cf  lea     r8, aUpdaterebootcx; "UpdateRebootCXID"
0x1800bf7d6  lea     rax, [rbp+arg_8]
0x1800bf7da  mov     r9d, 2; dwFlags
0x1800bf7e0  mov     [rsp+50h+pcbData], rax; pcbData
0x1800bf7e5  cmovz   rsi, r13
0x1800bf7e9  mov     rdx, rsi; lpSubKey
0x1800bf7ec  mov     [rsp+50h+pvData], rbx; pvData
0x1800bf7f1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800bf7f8  mov     [rsp+50h+pdwType], r14; int
0x1800bf7fd  call    cs:__imp_RegGetValueW
0x1800bf803  test    eax, eax
0x1800bf805  jz      short loc_1800BF823
0x1800bf807  mov     rcx, [rbp+28h]; this
0x1800bf80b  lea     r8, aOnecoreuapAdmi_60; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800bf812  mov     r9d, eax; char *
0x1800bf815  mov     edx, 0BFh; void *
0x1800bf81a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bf81f  mov     ebx, eax
0x1800bf821  jmp     short loc_1800BF88D
0x1800bf823  xor     edx, edx
0x1800bf825  mov     [rbp+string], r14
0x1800bf829  lea     rcx, [rbp+string]
0x1800bf82d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800bf832  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bf836  inc     rdx; length
0x1800bf839  cmp     [rbx+rdx*2], r14w
0x1800bf83e  jnz     short loc_1800BF836
0x1800bf840  lea     r8, [rbp+string]; string
0x1800bf844  mov     rcx, rbx; sourceString
0x1800bf847  call    cs:__imp_WindowsCreateString
0x1800bf84d  mov     ebx, eax
0x1800bf84f  test    eax, eax
0x1800bf851  jns     short loc_1800BF876
0x1800bf853  mov     rcx, [rbp+28h]; this
0x1800bf857  lea     r8, aOnecoreuapAdmi_60; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800bf85e  mov     r9d, eax; char *
0x1800bf861  mov     edx, 0C2h; void *
0x1800bf866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf86b  lea     rcx, [rbp+string]; this
0x1800bf86f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800bf874  jmp     short loc_1800BF88D
0x1800bf876  mov     rax, [rbp+string]
0x1800bf87a  lea     rcx, [rbp+string]; this
0x1800bf87e  mov     [rdi], rax
0x1800bf881  mov     [rbp+string], r14
0x1800bf885  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800bf88a  mov     ebx, r14d
0x1800bf88d  lea     rcx, [rbp+arg_18]
0x1800bf891  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bf896  mov     eax, ebx
0x1800bf898  mov     rbx, [rsp+50h+arg_0]
0x1800bf8a0  add     rsp, 50h
0x1800bf8a4  pop     r14
0x1800bf8a6  pop     r13
0x1800bf8a8  pop     rdi
0x1800bf8a9  pop     rsi
0x1800bf8aa  pop     rbp
0x1800bf8ab  retn
```
