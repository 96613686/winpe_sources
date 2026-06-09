# OSIntegration::DEH::AlarmExtensionHandler::_RestoreToAlarmSlot(OSIntegration::DEH::Internal::AlarmSlotHelper *)

- ea: `0x1800e7804`
- end: `0x1800e7b24`
- name: `?_RestoreToAlarmSlot@AlarmExtensionHandler@DEH@OSIntegration@@AEAAJPEAVAlarmSlotHelper@Internal@23@@Z`
- size: `800`
- prototype: `__int64 __fastcall(OSIntegration::DEH::AlarmExtensionHandler *__hidden this, struct OSIntegration::DEH::Internal::AlarmSlotHelper *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e6fd4`

## callees

- `0x180015590`
- `0x18001adb4`
- `0x180021e80`
- `0x18003193c`
- `0x180033ca0`
- `0x180069eb4`
- `0x18007cdc0`
- `0x1800aed10`
- `0x1800e7358`
- `0x1800e7804`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800e784d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800e784d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e7a18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e7a58`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e7a96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e7acf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e7a18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e7a58`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e7a96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e7acf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e79ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e79ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800e78f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800e78f1`

## string_xrefs

- `0x1800e7867`: `onecore\admin\appmodel\osim\src\deh\alarm\alarmextensionhandler.cpp`
- `0x1800e78af`: `onecore\admin\appmodel\osim\src\deh\alarm\alarmextensionhandler.cpp`
- `0x1800e7910`: `onecore\admin\appmodel\osim\src\deh\alarm\alarmextensionhandler.cpp`
- `0x1800e79cd`: `onecore\admin\appmodel\osim\src\deh\alarm\alarmextensionhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::AlarmExtensionHandler::_RestoreToAlarmSlot(
        OSIntegration::DEH::AlarmExtensionHandler *this,
        struct OSIntegration::DEH::Internal::AlarmSlotHelper *a2)
{
  HKEY *v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int RegkeySD; // edi
  __int64 v10; // rdx
  OSIntegration::DEH::AlarmExtensionHandler *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  void *v21; // [rsp+68h] [rbp-98h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  hKey = 0;
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = RegOpenCurrentUser(0x2001Fu, v4);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1C1,
           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\alarm\\alarmextensionhandler.cpp",
           (const char *)v5,
           dwOptions);
    goto LABEL_24;
  }
  *(_QWORD *)dwOptionsa = *((_QWORD *)a2 + 1);
  RegkeySD = StringCchPrintfW(
               SubKey,
               0x104u,
               L"%s\\%s",
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\Alarm");
  if ( RegkeySD < 0 )
  {
    v10 = 452;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\alarm\\alarmextensionhandler.cpp",
      (const char *)(unsigned int)RegkeySD,
      dwOptionsa[0]);
    v6 = RegkeySD;
    goto LABEL_24;
  }
  if ( !*((_QWORD *)this + 13) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)(*((_QWORD *)this + 13) + 784LL), &StringSid) )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\alarm\\alarmextensionhandler.cpp",
      (const char *)0x8007000ELL,
      dwOptionsa[0]);
    goto LABEL_24;
  }
  v21 = 0;
  RegkeySD = OSIntegration::DEH::AlarmExtensionHandler::_GetRegkeySD(v11, StringSid, &v21);
  if ( RegkeySD < 0 )
  {
    v10 = 459;
    goto LABEL_5;
  }
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = v21;
  phkResult = 0;
  v12 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, &phkResult, 0);
  if ( v12 )
  {
    v13 = 464;
  }
  else
  {
    v12 = RegSetValueExW(phkResult, L"PackageFullName", 0, 1u, *((const BYTE **)a2 + 4), 2 * *((_DWORD *)a2 + 6) + 2);
    if ( v12 )
    {
      v13 = 472;
    }
    else
    {
      v12 = RegSetValueExW(phkResult, L"Version", 0, 1u, *((const BYTE **)a2 + 7), 2 * *((_DWORD *)a2 + 12) + 2);
      if ( v12 )
      {
        v13 = 480;
      }
      else
      {
        v12 = RegSetValueExW(phkResult, L"NCBEnabled", 0, 4u, (const BYTE *)a2 + 72, 4u);
        if ( v12 )
        {
          v13 = 488;
        }
        else
        {
          v12 = RegSetValueExW(phkResult, L"UiOrder", 0, 4u, (const BYTE *)a2 + 76, 4u);
          if ( !v12 )
          {
            Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
            v6 = 0;
            goto LABEL_24;
          }
          v13 = 496;
        }
      }
    }
  }
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v13,
         (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\alarm\\alarmextensionhandler.cpp",
         (const char *)v12,
         dwOptionsb);
  Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x1800e7804  mov     [rsp-8+arg_10], rbx
0x1800e7809  push    rbp
0x1800e780a  push    rsi
0x1800e780b  push    rdi
0x1800e780c  lea     rbp, [rsp-1B0h]
0x1800e7814  sub     rsp, 2B0h
0x1800e781b  mov     rax, cs:__security_cookie
0x1800e7822  xor     rax, rsp
0x1800e7825  mov     [rbp+1C0h+var_20], rax
0x1800e782c  mov     rbx, rdx
0x1800e782f  mov     rsi, rcx
0x1800e7832  mov     [rsp+2C0h+hKey], 0
0x1800e783b  lea     rcx, [rsp+2C0h+hKey]
0x1800e7840  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800e7845  mov     rdx, rax; phkResult
0x1800e7848  mov     ecx, 2001Fh; samDesired
0x1800e784d  call    cs:__imp_RegOpenCurrentUser
0x1800e7854  nop     dword ptr [rax+rax+00h]
0x1800e7859  test    eax, eax
0x1800e785b  jz      short loc_1800E787F
0x1800e785d  mov     rcx, [rbp+1C8h]; this
0x1800e7864  mov     r9d, eax; char *
0x1800e7867  lea     r8, aOnecoreAdminAp_113; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e786e  mov     edx, 1C1h; void *
0x1800e7873  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e7878  mov     ebx, eax
0x1800e787a  jmp     loc_1800E7AF5
0x1800e787f  mov     rax, [rbx+8]
0x1800e7883  mov     qword ptr [rsp+2C0h+dwOptions], rax; int
0x1800e7888  lea     r9, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800e788f  lea     r8, aSS; "%s\\%s"
0x1800e7896  mov     edx, 104h; unsigned __int64
0x1800e789b  lea     rcx, [rbp+1C0h+SubKey]; unsigned __int16 *
0x1800e789f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e78a4  mov     edi, eax
0x1800e78a6  test    eax, eax
0x1800e78a8  jns     short loc_1800E78CC
0x1800e78aa  mov     edx, 1C4h; void *
0x1800e78af  lea     r8, aOnecoreAdminAp_113; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e78b6  mov     r9d, edi; char *
0x1800e78b9  mov     rcx, [rbp+1C8h]; this
0x1800e78c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e78c5  mov     ebx, edi
0x1800e78c7  jmp     loc_1800E7AF5
0x1800e78cc  cmp     qword ptr [rsi+68h], 0
0x1800e78d1  jnz     short loc_1800E78D8
0x1800e78d3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "outgoingPackage != nullptr")
0x1800e78d8  mov     [rsp+2C0h+StringSid], 0
0x1800e78e1  mov     rcx, [rsi+68h]
0x1800e78e5  lea     rdx, [rsp+2C0h+StringSid]; StringSid
0x1800e78ea  mov     rcx, [rcx+310h]; Sid
0x1800e78f1  call    cs:__imp_ConvertSidToStringSidW
0x1800e78f8  nop     dword ptr [rax+rax+00h]
0x1800e78fd  test    eax, eax
0x1800e78ff  jnz     short loc_1800E7926
0x1800e7901  mov     rcx, [rbp+1C8h]; this
0x1800e7908  mov     ebx, 8007000Eh
0x1800e790d  mov     r9d, ebx; char *
0x1800e7910  lea     r8, aOnecoreAdminAp_113; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e7917  mov     edx, 1C8h; void *
0x1800e791c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7921  jmp     loc_1800E7AF5
0x1800e7926  mov     [rsp+2C0h+var_258], 0
0x1800e792f  lea     r8, [rsp+2C0h+var_258]; void **
0x1800e7934  mov     rdx, [rsp+2C0h+StringSid]; unsigned __int16 *
0x1800e7939  call    ?_GetRegkeySD@AlarmExtensionHandler@DEH@OSIntegration@@AEAAJPEBGPEAPEAX@Z; OSIntegration::DEH::AlarmExtensionHandler::_GetRegkeySD(ushort const *,void * *)
0x1800e793e  mov     edi, eax
0x1800e7940  test    eax, eax
0x1800e7942  jns     short loc_1800E794E
0x1800e7944  mov     edx, 1CBh
0x1800e7949  jmp     loc_1800E78AF
0x1800e794e  mov     qword ptr [rsp+2C0h+SecurityAttributes.nLength], 18h
0x1800e7957  xorps   xmm0, xmm0
0x1800e795a  movups  xmmword ptr [rsp+2C0h+SecurityAttributes.lpSecurityDescriptor], xmm0
0x1800e795f  mov     rax, [rsp+2C0h+var_258]
0x1800e7964  mov     [rsp+2C0h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800e7969  mov     [rsp+2C0h+var_270], 0
0x1800e7972  mov     [rsp+2C0h+lpdwDisposition], 0; lpdwDisposition
0x1800e797b  lea     rax, [rsp+2C0h+var_270]
0x1800e7980  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800e7985  lea     rax, [rsp+2C0h+SecurityAttributes]
0x1800e798a  mov     [rsp+2C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800e798f  mov     [rsp+2C0h+samDesired], 2001Fh; samDesired
0x1800e7997  mov     [rsp+2C0h+dwOptions], 0; unsigned int
0x1800e799f  xor     r9d, r9d; lpClass
0x1800e79a2  xor     r8d, r8d; Reserved
0x1800e79a5  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x1800e79a9  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800e79ae  call    cs:__imp_RegCreateKeyExW
0x1800e79b5  nop     dword ptr [rax+rax+00h]
0x1800e79ba  test    eax, eax
0x1800e79bc  jz      short loc_1800E79EA
0x1800e79be  mov     edx, 1D0h; void *
0x1800e79c3  mov     rcx, [rbp+1C8h]; this
0x1800e79ca  mov     r9d, eax; char *
0x1800e79cd  lea     r8, aOnecoreAdminAp_113; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e79d4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e79d9  mov     ebx, eax
0x1800e79db  mov     rcx, [rsp+2C0h+var_270]
0x1800e79e0  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800e79e5  jmp     loc_1800E7AF5
0x1800e79ea  mov     eax, [rbx+18h]
0x1800e79ed  lea     eax, ds:2[rax*2]
0x1800e79f4  mov     [rsp+2C0h+samDesired], eax; cbData
0x1800e79f8  mov     rax, [rbx+20h]
0x1800e79fc  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x1800e7a01  mov     edi, 1
0x1800e7a06  mov     r9d, edi; dwType
0x1800e7a09  xor     r8d, r8d; Reserved
0x1800e7a0c  lea     rdx, aPackagefullnam_0; "PackageFullName"
0x1800e7a13  mov     rcx, [rsp+2C0h+var_270]; hKey
0x1800e7a18  call    cs:__imp_RegSetValueExW
0x1800e7a1f  nop     dword ptr [rax+rax+00h]
0x1800e7a24  test    eax, eax
0x1800e7a26  jz      short loc_1800E7A2F
0x1800e7a28  mov     edx, 1D8h
0x1800e7a2d  jmp     short loc_1800E79C3
0x1800e7a2f  mov     eax, [rbx+30h]
0x1800e7a32  lea     eax, ds:2[rax*2]
0x1800e7a39  mov     [rsp+2C0h+samDesired], eax; cbData
0x1800e7a3d  mov     rax, [rbx+38h]
0x1800e7a41  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x1800e7a46  mov     r9d, edi; dwType
0x1800e7a49  xor     r8d, r8d; Reserved
0x1800e7a4c  lea     rdx, aVersion; "Version"
0x1800e7a53  mov     rcx, [rsp+2C0h+var_270]; hKey
0x1800e7a58  call    cs:__imp_RegSetValueExW
0x1800e7a5f  nop     dword ptr [rax+rax+00h]
0x1800e7a64  test    eax, eax
0x1800e7a66  jz      short loc_1800E7A72
0x1800e7a68  mov     edx, 1E0h
0x1800e7a6d  jmp     loc_1800E79C3
0x1800e7a72  lea     rax, [rbx+48h]
0x1800e7a76  mov     edi, 4
0x1800e7a7b  mov     [rsp+2C0h+samDesired], edi; cbData
0x1800e7a7f  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x1800e7a84  mov     r9d, edi; dwType
0x1800e7a87  xor     r8d, r8d; Reserved
0x1800e7a8a  lea     rdx, aNcbenabled; "NCBEnabled"
0x1800e7a91  mov     rcx, [rsp+2C0h+var_270]; hKey
0x1800e7a96  call    cs:__imp_RegSetValueExW
0x1800e7a9d  nop     dword ptr [rax+rax+00h]
0x1800e7aa2  test    eax, eax
0x1800e7aa4  jz      short loc_1800E7AB0
0x1800e7aa6  mov     edx, 1E8h
0x1800e7aab  jmp     loc_1800E79C3
0x1800e7ab0  lea     rax, [rbx+4Ch]
0x1800e7ab4  mov     [rsp+2C0h+samDesired], edi; cbData
0x1800e7ab8  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x1800e7abd  mov     r9d, edi; dwType
0x1800e7ac0  xor     r8d, r8d; Reserved
0x1800e7ac3  lea     rdx, aUiorder; "UiOrder"
0x1800e7aca  mov     rcx, [rsp+2C0h+var_270]; hKey
0x1800e7acf  call    cs:__imp_RegSetValueExW
0x1800e7ad6  nop     dword ptr [rax+rax+00h]
0x1800e7adb  test    eax, eax
0x1800e7add  jz      short loc_1800E7AE9
0x1800e7adf  mov     edx, 1F0h
0x1800e7ae4  jmp     loc_1800E79C3
0x1800e7ae9  mov     rcx, [rsp+2C0h+var_270]
0x1800e7aee  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800e7af3  xor     ebx, ebx
0x1800e7af5  lea     rcx, [rsp+2C0h+hKey]
0x1800e7afa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e7aff  mov     eax, ebx
0x1800e7b01  mov     rcx, [rbp+1C0h+var_20]
0x1800e7b08  xor     rcx, rsp; StackCookie
0x1800e7b0b  call    __security_check_cookie
0x1800e7b10  mov     rbx, [rsp+2C0h+arg_10]
0x1800e7b18  add     rsp, 2B0h
0x1800e7b1f  pop     rdi
0x1800e7b20  pop     rsi
0x1800e7b21  pop     rbp
0x1800e7b22  retn
```
