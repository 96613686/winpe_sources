# OSIntegration::DEH::Internal::DefaultBackgroundTasksClassHelper::WritePackageCapabilitiesInternal(OSIntegration::Package const *,OSIntegration::Tools::MoCOMHelper const *,ulong)

- ea: `0x180070614`
- end: `0x180070a56`
- name: `?WritePackageCapabilitiesInternal@DefaultBackgroundTasksClassHelper@Internal@DEH@OSIntegration@@CAJPEBVPackage@4@PEBVMoCOMHelper@Tools@4@K@Z`
- size: `1090`
- prototype: `__int64 __fastcall(const struct OSIntegration::Package *, const BYTE **, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180070530`

## callees

- `0x180012964`
- `0x18004f3c4`
- `0x180067050`
- `0x180070614`
- `0x180070a5c`
- `0x180070b78`
- `0x180087238`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a116c`
- `0x1800a2854`
- `0x1800f0260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800709dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800709dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070756`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800708c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007093a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070756`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800708c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007093a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800709ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180070a16`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800709ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180070a16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070981`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070981`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180070797`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180070797`

## string_xrefs

- `0x1800706e0`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x180070769`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x1800707a8`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x180070815`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x180070847`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x18007094e`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x1800709bf`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::DEH::Internal::DefaultBackgroundTasksClassHelper::WritePackageCapabilitiesInternal(
        const struct OSIntegration::Package *a1,
        const BYTE **a2,
        int a3)
{
  int IsStateSeparationEnabled; // eax
  unsigned int LastError; // ebx
  __int64 v8; // rdx
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  __int64 v11; // rdx
  const char *v12; // r9
  int v13; // eax
  int RegkeySD; // eax
  __int64 v15; // rdx
  HKEY *v16; // rax
  LSTATUS v17; // eax
  void *v18; // r9
  bool v19; // sf
  HKEY *v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // eax
  const char *dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  const char *dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-E0h]
  bool v28; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[784]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  *(_DWORD *)Data = a3;
  if ( *((_BYTE *)a1 + 403) )
    return 0;
  hKey = 0;
  if ( !*((_BYTE *)a1 + 406) )
  {
    StringSid = 0;
    if ( !ConvertSidToStringSidW(*((PSID *)a1 + 98), &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x99,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgrou"
                                  "ndtasksclasshelper.cpp",
                    v12);
LABEL_17:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
      goto LABEL_41;
    }
    dwOptionsb = L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability";
    v13 = StringCchPrintfW(SubKey, 0x30Cu, L"%s\\%s\\%s\\%s", StringSid);
    LastError = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgroundtasksclasshelper.cpp",
        (const char *)(unsigned int)v13,
        (int)L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability");
      goto LABEL_17;
    }
    hMem = 0;
    RegkeySD = OSIntegration::DEH::Internal::DefaultBackgroundTasksClassHelper::GetRegkeySD(StringSid, &hMem);
    LastError = RegkeySD;
    if ( RegkeySD < 0 )
    {
      v15 = 164;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgroundtasksclasshelper.cpp",
        (const char *)(unsigned int)RegkeySD,
        (int)dwOptionsb);
LABEL_23:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
      goto LABEL_17;
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = hMem;
    v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v17 = RegCreateKeyExW(HKEY_USERS, SubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, v16, 0);
    v19 = v17 < 0;
    if ( v17 > 0 )
      v19 = 1;
    if ( v19 )
    {
      RegkeySD = OSIntegration::DEH::Internal::BackgroundTasks::ResetRegistryACL(
                   StringSid,
                   SubKey,
                   (unsigned __int16 *)hMem,
                   v18);
      LastError = RegkeySD;
      if ( RegkeySD < 0 )
      {
        v15 = 184;
        goto LABEL_22;
      }
      v20 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
      v21 = RegCreateKeyExW(HKEY_USERS, SubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, v20, 0);
      if ( v21 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0xC1,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgr"
                                    "oundtasksclasshelper.cpp",
                      (const char *)v21,
                      dwOptionsc);
        goto LABEL_23;
      }
    }
    if ( hMem )
      LocalFree(hMem);
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_35;
  }
  v28 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v28);
  LastError = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled >= 0 )
  {
    if ( v28 )
    {
      dwOptions = L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability";
      IsStateSeparationEnabled = StringCchPrintfW(SubKey, 0x30Cu, L"%s\\%s\\%s\\%s", L"OSDATA");
      LastError = IsStateSeparationEnabled;
      if ( IsStateSeparationEnabled < 0 )
      {
        v8 = 127;
        goto LABEL_9;
      }
    }
    else
    {
      LODWORD(dwOptions) = *((_QWORD *)a1 + 89);
      IsStateSeparationEnabled = StringCchPrintfW(
                                   SubKey,
                                   0x30Cu,
                                   L"%s\\%s\\%s",
                                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\"
                                    "BackgroundCapability");
      LastError = IsStateSeparationEnabled;
      if ( IsStateSeparationEnabled < 0 )
      {
        v8 = 136;
        goto LABEL_9;
      }
    }
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
    if ( Key )
    {
      v11 = 147;
LABEL_14:
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v11,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgrou"
                                  "ndtasksclasshelper.cpp",
                    (const char *)Key,
                    dwOptionsa);
      goto LABEL_41;
    }
LABEL_35:
    v22 = RegSetValueExW(hKey, L"Capabilities", 0, 4u, Data, 4u);
    if ( v22 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xCA,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgrou"
                                  "ndtasksclasshelper.cpp",
                    (const char *)v22,
                    dwOptionsd);
      if ( hKey )
        RegCloseKey(hKey);
      return LastError;
    }
    Key = RegSetValueExW(hKey, L"AppUserModelId", 0, 1u, a2[34], 2 * *((_DWORD *)a2 + 66) + 2);
    if ( !Key )
    {
      LastError = 0;
      goto LABEL_41;
    }
    v11 = 209;
    goto LABEL_14;
  }
  v8 = 116;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgroundtasksclasshelper.cpp",
    (const char *)(unsigned int)IsStateSeparationEnabled,
    (int)dwOptions);
LABEL_41:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return LastError;
}

```

## disassembly

```asm
0x180070614  push    rbp
0x180070616  push    rbx
0x180070617  push    rsi
0x180070618  push    rdi
0x180070619  push    r14
0x18007061b  lea     rbp, [rsp-5C0h]
0x180070623  sub     rsp, 6C0h
0x18007062a  mov     rax, cs:__security_cookie
0x180070631  xor     rax, rsp
0x180070634  mov     [rbp+5E0h+var_30], rax
0x18007063b  mov     rsi, rdx
0x18007063e  mov     rdi, rcx
0x180070641  mov     dword ptr [rsp+6E0h+Data], r8d
0x180070646  xor     r14d, r14d
0x180070649  cmp     [rcx+193h], r14b
0x180070650  jz      short loc_180070659
0x180070652  xor     eax, eax
0x180070654  jmp     loc_180070A39
0x180070659  mov     [rsp+6E0h+hKey], r14
0x18007065e  cmp     [rcx+196h], r14b
0x180070665  jz      loc_180070786
0x18007066b  mov     [rsp+6E0h+var_690], r14b
0x180070670  lea     rcx, [rsp+6E0h+var_690]; bool *
0x180070675  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x18007067a  mov     ebx, eax
0x18007067c  test    eax, eax
0x18007067e  jns     short loc_180070687
0x180070680  mov     edx, 74h ; 't'
0x180070685  jmp     short loc_1800706D6
0x180070687  mov     rax, [rsi+38h]
0x18007068b  mov     rcx, [rdi+2C8h]
0x180070692  mov     edx, 30Ch; unsigned __int64
0x180070697  cmp     [rsp+6E0h+var_690], r14b
0x18007069c  jz      short loc_1800706F1
0x18007069e  mov     [rsp+6E0h+lpSecurityAttributes], rax
0x1800706a3  mov     qword ptr [rsp+6E0h+samDesired], rcx
0x1800706a8  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800706af  mov     qword ptr [rsp+6E0h+dwOptions], rax; int
0x1800706b4  lea     r9, aOsdata; "OSDATA"
0x1800706bb  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800706c2  lea     rcx, [rbp+5E0h+SubKey]; Buffer
0x1800706c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800706cb  mov     ebx, eax
0x1800706cd  test    eax, eax
0x1800706cf  jns     short loc_18007071F
0x1800706d1  mov     edx, 7Fh; void *
0x1800706d6  mov     rcx, [rbp+5E8h]; this
0x1800706dd  mov     r9d, eax; char *
0x1800706e0  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800706e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800706ec  jmp     loc_180070A2D
0x1800706f1  mov     qword ptr [rsp+6E0h+samDesired], rax
0x1800706f6  mov     qword ptr [rsp+6E0h+dwOptions], rcx
0x1800706fb  lea     r9, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180070702  lea     r8, aSSS; "%s\\%s\\%s"
0x180070709  lea     rcx, [rbp+5E0h+SubKey]; Buffer
0x18007070d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070712  mov     ebx, eax
0x180070714  test    eax, eax
0x180070716  jns     short loc_18007071F
0x180070718  mov     edx, 88h
0x18007071d  jmp     short loc_1800706D6
0x18007071f  lea     rcx, [rsp+6E0h+hKey]
0x180070724  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180070729  mov     [rsp+6E0h+lpdwDisposition], r14; lpdwDisposition
0x18007072e  mov     [rsp+6E0h+phkResult], rax; phkResult
0x180070733  mov     [rsp+6E0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180070738  mov     [rsp+6E0h+samDesired], 2001Fh; samDesired
0x180070740  mov     [rsp+6E0h+dwOptions], r14d; unsigned int
0x180070745  xor     r9d, r9d; lpClass
0x180070748  xor     r8d, r8d; Reserved
0x18007074b  lea     rdx, [rbp+5E0h+SubKey]; lpSubKey
0x18007074f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180070756  call    cs:__imp_RegCreateKeyExW
0x18007075c  test    eax, eax
0x18007075e  jz      loc_180070987
0x180070764  mov     edx, 93h; void *
0x180070769  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180070770  mov     r9d, eax; char *
0x180070773  mov     rcx, [rbp+5E8h]; this
0x18007077a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007077f  mov     ebx, eax
0x180070781  jmp     loc_180070A2D
0x180070786  mov     [rsp+6E0h+StringSid], r14
0x18007078b  lea     rdx, [rsp+6E0h+StringSid]; StringSid
0x180070790  mov     rcx, [rcx+310h]; Sid
0x180070797  call    cs:__imp_ConvertSidToStringSidW
0x18007079d  test    eax, eax
0x18007079f  jnz     short loc_1800707CA
0x1800707a1  mov     rcx, [rbp+5E8h]; this
0x1800707a8  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800707af  mov     edx, 99h; void *
0x1800707b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800707b9  mov     ebx, eax
0x1800707bb  lea     rcx, [rsp+6E0h+StringSid]
0x1800707c0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800707c5  jmp     loc_180070A2D
0x1800707ca  mov     rax, [rsi+38h]
0x1800707ce  mov     [rsp+6E0h+lpSecurityAttributes], rax
0x1800707d3  mov     rax, [rdi+2C8h]
0x1800707da  mov     qword ptr [rsp+6E0h+samDesired], rax
0x1800707df  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800707e6  mov     qword ptr [rsp+6E0h+dwOptions], rax; int
0x1800707eb  mov     r9, [rsp+6E0h+StringSid]
0x1800707f0  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800707f7  mov     edx, 30Ch; unsigned __int64
0x1800707fc  lea     rcx, [rbp+5E0h+SubKey]; Buffer
0x180070800  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070805  mov     ebx, eax
0x180070807  test    eax, eax
0x180070809  jns     short loc_180070828
0x18007080b  mov     rcx, [rbp+5E8h]; this
0x180070812  mov     r9d, eax; char *
0x180070815  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007081c  mov     edx, 0A1h; void *
0x180070821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070826  jmp     short loc_1800707BB
0x180070828  mov     [rsp+6E0h+hMem], r14
0x18007082d  lea     rdx, [rsp+6E0h+hMem]; void **
0x180070832  mov     rcx, [rsp+6E0h+StringSid]; unsigned __int16 *
0x180070837  call    ?GetRegkeySD@DefaultBackgroundTasksClassHelper@Internal@DEH@OSIntegration@@CAJPEBGPEAPEAX@Z; OSIntegration::DEH::Internal::DefaultBackgroundTasksClassHelper::GetRegkeySD(ushort const *,void * *)
0x18007083c  mov     ebx, eax
0x18007083e  test    eax, eax
0x180070840  jns     short loc_18007086D
0x180070842  mov     edx, 0A4h; void *
0x180070847  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007084e  mov     r9d, eax; char *
0x180070851  mov     rcx, [rbp+5E8h]; this
0x180070858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007085d  nop
0x18007085e  lea     rcx, [rsp+6E0h+hMem]
0x180070863  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180070868  jmp     loc_1800707BB
0x18007086d  mov     qword ptr [rsp+6E0h+SecurityAttributes.nLength], 18h
0x180070876  xorps   xmm0, xmm0
0x180070879  movups  xmmword ptr [rbp+5E0h+SecurityAttributes.lpSecurityDescriptor], xmm0
0x18007087d  mov     rax, [rsp+6E0h+hMem]
0x180070882  mov     [rbp+5E0h+SecurityAttributes.lpSecurityDescriptor], rax
0x180070886  lea     rcx, [rsp+6E0h+hKey]
0x18007088b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180070890  mov     [rsp+6E0h+lpdwDisposition], r14; lpdwDisposition
0x180070895  mov     [rsp+6E0h+phkResult], rax; phkResult
0x18007089a  lea     rax, [rsp+6E0h+SecurityAttributes]
0x18007089f  mov     [rsp+6E0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800708a4  mov     [rsp+6E0h+samDesired], 2001Fh; samDesired
0x1800708ac  mov     [rsp+6E0h+dwOptions], r14d; dwOptions
0x1800708b1  xor     r9d, r9d; lpClass
0x1800708b4  xor     r8d, r8d; Reserved
0x1800708b7  lea     rdx, [rbp+5E0h+SubKey]; lpSubKey
0x1800708bb  mov     rdi, 0FFFFFFFF80000003h
0x1800708c2  mov     rcx, rdi; hKey
0x1800708c5  call    cs:__imp_RegCreateKeyExW
0x1800708cb  test    eax, eax
0x1800708cd  jle     short loc_1800708D9
0x1800708cf  movzx   eax, ax
0x1800708d2  or      eax, 80070000h
0x1800708d7  test    eax, eax
0x1800708d9  jns     loc_180070966
0x1800708df  mov     r8, [rsp+6E0h+hMem]; unsigned __int16 *
0x1800708e4  lea     rdx, [rbp+5E0h+SubKey]; unsigned __int16 *
0x1800708e8  mov     rcx, [rsp+6E0h+StringSid]; StringSid
0x1800708ed  call    ?ResetRegistryACL@BackgroundTasks@Internal@DEH@OSIntegration@@YAJPEBG0PEAX@Z; OSIntegration::DEH::Internal::BackgroundTasks::ResetRegistryACL(ushort const *,ushort const *,void *)
0x1800708f2  mov     ebx, eax
0x1800708f4  test    eax, eax
0x1800708f6  jns     short loc_180070902
0x1800708f8  mov     edx, 0B8h
0x1800708fd  jmp     loc_180070847
0x180070902  lea     rcx, [rsp+6E0h+hKey]
0x180070907  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18007090c  mov     [rsp+6E0h+lpdwDisposition], r14; lpdwDisposition
0x180070911  mov     [rsp+6E0h+phkResult], rax; phkResult
0x180070916  lea     rax, [rsp+6E0h+SecurityAttributes]
0x18007091b  mov     [rsp+6E0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180070920  mov     [rsp+6E0h+samDesired], 2001Fh; samDesired
0x180070928  mov     [rsp+6E0h+dwOptions], r14d; unsigned int
0x18007092d  xor     r9d, r9d; lpClass
0x180070930  xor     r8d, r8d; Reserved
0x180070933  lea     rdx, [rbp+5E0h+SubKey]; lpSubKey
0x180070937  mov     rcx, rdi; hKey
0x18007093a  call    cs:__imp_RegCreateKeyExW
0x180070940  test    eax, eax
0x180070942  jz      short loc_180070966
0x180070944  mov     rcx, [rbp+5E8h]; this
0x18007094b  mov     r9d, eax; char *
0x18007094e  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180070955  mov     edx, 0C1h; void *
0x18007095a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007095f  mov     ebx, eax
0x180070961  jmp     loc_18007085E
0x180070966  mov     rcx, [rsp+6E0h+hMem]; hMem
0x18007096b  test    rcx, rcx
0x18007096e  jz      short loc_180070977
0x180070970  call    cs:__imp_LocalFree
0x180070976  nop
0x180070977  mov     rcx, [rsp+6E0h+StringSid]; hMem
0x18007097c  test    rcx, rcx
0x18007097f  jz      short loc_180070987
0x180070981  call    cs:__imp_LocalFree
0x180070987  mov     r9d, 4; dwType
0x18007098d  mov     [rsp+6E0h+samDesired], r9d; cbData
0x180070992  lea     rax, [rsp+6E0h+Data]
0x180070997  mov     qword ptr [rsp+6E0h+dwOptions], rax; unsigned int
0x18007099c  xor     r8d, r8d; Reserved
0x18007099f  lea     rdx, aCapabilities; "Capabilities"
0x1800709a6  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1800709ab  call    cs:__imp_RegSetValueExW
0x1800709b1  test    eax, eax
0x1800709b3  jz      short loc_1800709E4
0x1800709b5  mov     rcx, [rbp+5E8h]; this
0x1800709bc  mov     r9d, eax; char *
0x1800709bf  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800709c6  mov     edx, 0CAh; void *
0x1800709cb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800709d0  mov     ebx, eax
0x1800709d2  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1800709d7  test    rcx, rcx
0x1800709da  jz      short loc_180070A37
0x1800709dc  call    cs:__imp_RegCloseKey
0x1800709e2  jmp     short loc_180070A37
0x1800709e4  mov     eax, [rsi+108h]
0x1800709ea  lea     eax, ds:2[rax*2]
0x1800709f1  mov     [rsp+6E0h+samDesired], eax; cbData
0x1800709f5  mov     rax, [rsi+110h]
0x1800709fc  mov     qword ptr [rsp+6E0h+dwOptions], rax; lpData
0x180070a01  mov     r9d, 1; dwType
0x180070a07  xor     r8d, r8d; Reserved
0x180070a0a  lea     rdx, aAppusermodelid_1; "AppUserModelId"
0x180070a11  mov     rcx, [rsp+6E0h+hKey]; hKey
0x180070a16  call    cs:__imp_RegSetValueExW
0x180070a1c  test    eax, eax
0x180070a1e  jz      short loc_180070A2A
0x180070a20  mov     edx, 0D1h
0x180070a25  jmp     loc_180070769
0x180070a2a  mov     ebx, r14d
0x180070a2d  lea     rcx, [rsp+6E0h+hKey]
0x180070a32  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180070a37  mov     eax, ebx
0x180070a39  mov     rcx, [rbp+5E0h+var_30]
0x180070a40  xor     rcx, rsp; StackCookie
0x180070a43  call    __security_check_cookie
0x180070a48  add     rsp, 6C0h
0x180070a4f  pop     r14
0x180070a51  pop     rdi
0x180070a52  pop     rsi
0x180070a53  pop     rbx
0x180070a54  pop     rbp
0x180070a55  retn
```
