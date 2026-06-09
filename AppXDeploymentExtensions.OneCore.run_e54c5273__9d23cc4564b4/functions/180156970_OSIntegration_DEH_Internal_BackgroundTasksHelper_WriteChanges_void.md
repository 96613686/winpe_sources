# OSIntegration::DEH::Internal::BackgroundTasksHelper::WriteChanges(void)

- ea: `0x180156970`
- end: `0x180156daa`
- name: `?WriteChanges@BackgroundTasksHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `1082`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::BackgroundTasksHelper *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180012964`
- `0x18004f3c4`
- `0x180067050`
- `0x180070b78`
- `0x180080b84`
- `0x180084c40`
- `0x1800853cc`
- `0x180087238`
- `0x180098bf4`
- `0x1800a116c`
- `0x1800a219c`
- `0x1800a2854`
- `0x1800f0260`
- `0x180156970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180156ac1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180156c3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180156ac1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180156c3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180156cc8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180156d22`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180156cc8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180156d22`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180156b0e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180156b0e`
- `Windows.Networking.Vpn!VpnClientPluginInstall` at `0x180156d61`
- `Windows.Networking.Vpn!VpnClientPluginInstall` at `0x180156d61`

## string_xrefs

- `0x1801569bc`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtaskshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::Internal::BackgroundTasksHelper::WriteChanges(
        OSIntegration::DEH::Internal::BackgroundTasksHelper *this)
{
  __int64 v2; // rax
  int IsStateSeparationEnabled; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  OSIntegration::DEH::Internal::BackgroundTasksHelper *v13; // rcx
  int RegkeySD; // eax
  __int64 v15; // rdx
  HKEY *v16; // rax
  int v17; // eax
  void *v18; // r9
  const BYTE **v19; // rcx
  __int64 v20; // rdx
  const char *dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  bool v24; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v26; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[784]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+5D8h]

  v2 = *((_QWORD *)this + 3);
  if ( *(_BYTE *)(v2 + 403) )
    return 0;
  hKey = 0;
  if ( !*(_BYTE *)(v2 + 406) )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( ConvertSidToStringSidW(*(PSID *)(*((_QWORD *)this + 3) + 784LL), &StringSid) )
    {
      dwOptions = L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability";
      v12 = StringCchPrintfW(SubKey, 0x30Cu, L"%s\\%s\\%s\\%s", StringSid);
      v5 = v12;
      if ( v12 >= 0 )
      {
        v26 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &v26,
          0);
        RegkeySD = OSIntegration::DEH::Internal::BackgroundTasksHelper::GetRegkeySD(v13, StringSid, (void **)&v26);
        v5 = RegkeySD;
        if ( RegkeySD >= 0 )
        {
          *(_QWORD *)&SecurityAttributes.nLength = 24;
          *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
          SecurityAttributes.lpSecurityDescriptor = v26;
          v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
          v17 = RegCreateKeyExW(HKEY_USERS, SubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, v16, 0);
          if ( v17 > 0 )
            v17 = (unsigned __int16)v17 | 0x80070000;
          if ( v17 >= 0
            || (wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x2E8,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtaskshelper.cpp",
                  (const char *)(unsigned int)v17,
                  dwOptionsb),
                RegkeySD = OSIntegration::DEH::Internal::BackgroundTasks::ResetRegistryACL(StringSid, SubKey, v26, v18),
                v5 = RegkeySD,
                RegkeySD >= 0) )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
            goto LABEL_30;
          }
          v15 = 746;
        }
        else
        {
          v15 = 732;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtaskshelper.cpp",
          (const char *)(unsigned int)RegkeySD,
          (int)dwOptions);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
LABEL_18:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
        goto LABEL_41;
      }
      v10 = (unsigned int)v12;
      v11 = 729;
    }
    else
    {
      v5 = -2147024882;
      v10 = 2147942414LL;
      v11 = 722;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtaskshelper.cpp",
      (const char *)v10,
      (int)dwOptions);
    goto LABEL_18;
  }
  v24 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v24);
  v5 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled >= 0 )
  {
    if ( v24 )
    {
      dwOptions = L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability";
      IsStateSeparationEnabled = StringCchPrintfW(SubKey, 0x30Cu, L"%s\\%s\\%s\\%s", L"OSDATA");
      v5 = IsStateSeparationEnabled;
      if ( IsStateSeparationEnabled < 0 )
      {
        v6 = 698;
        goto LABEL_9;
      }
    }
    else
    {
      LODWORD(dwOptions) = *(_QWORD *)(*((_QWORD *)this + 3) + 712LL);
      IsStateSeparationEnabled = StringCchPrintfW(
                                   SubKey,
                                   0x30Cu,
                                   L"%s\\%s\\%s",
                                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\"
                                    "BackgroundCapability");
      v5 = IsStateSeparationEnabled;
      if ( IsStateSeparationEnabled < 0 )
      {
        v6 = 707;
        goto LABEL_9;
      }
    }
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
    if ( Key )
    {
      v9 = 717;
LABEL_14:
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtaskshelper.cpp",
             (const char *)Key,
             dwOptionsa);
      goto LABEL_41;
    }
LABEL_30:
    Key = RegSetValueExW(hKey, L"Capabilities", 0, 4u, (const BYTE *)this + 192, 4u);
    if ( Key )
    {
      v9 = 766;
    }
    else
    {
      v19 = (const BYTE **)((char *)this + 168);
      if ( !*((_QWORD *)this + 22) )
        v19 = (const BYTE **)(*((_QWORD *)this + 20) + 264LL);
      Key = RegSetValueExW(hKey, L"AppUserModelId", 0, 1u, v19[1], 2 * *(_DWORD *)v19 + 2);
      if ( Key )
      {
        v9 = 784;
      }
      else
      {
        v20 = *((_QWORD *)this + 3);
        if ( *(_BYTE *)(v20 + 406)
          || (*((_BYTE *)this + 192) & 0x20) == 0
          || (Key = VpnClientPluginInstall(
                      *(const unsigned __int16 **)(*((_QWORD *)this + 20) + 104LL),
                      *(const unsigned __int16 **)(v20 + 224),
                      *(void **)(v20 + 784))) == 0 )
        {
          v5 = 0;
          goto LABEL_41;
        }
        v9 = 795;
      }
    }
    goto LABEL_14;
  }
  v6 = 687;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtaskshelper.cpp",
    (const char *)(unsigned int)IsStateSeparationEnabled,
    (int)dwOptions);
LABEL_41:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x180156970  mov     [rsp-8+arg_8], rbx
0x180156975  mov     [rsp-8+arg_10], rsi
0x18015697a  push    rbp
0x18015697b  push    rdi
0x18015697c  push    r14
0x18015697e  lea     rbp, [rsp-5C0h]
0x180156986  sub     rsp, 6C0h
0x18015698d  mov     rax, cs:__security_cookie
0x180156994  xor     rax, rsp
0x180156997  mov     [rbp+5D0h+var_20], rax
0x18015699e  mov     rdi, rcx
0x1801569a1  mov     rax, [rcx+18h]
0x1801569a5  xor     esi, esi
0x1801569a7  cmp     [rax+193h], sil
0x1801569ae  jz      short loc_1801569B7
0x1801569b0  xor     eax, eax
0x1801569b2  jmp     loc_180156D83
0x1801569b7  mov     [rsp+6D0h+hKey], rsi
0x1801569bc  lea     r14, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801569c3  cmp     [rax+196h], sil
0x1801569ca  jz      loc_180156AED
0x1801569d0  mov     [rsp+6D0h+var_680], sil
0x1801569d5  lea     rcx, [rsp+6D0h+var_680]; bool *
0x1801569da  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1801569df  mov     ebx, eax
0x1801569e1  test    eax, eax
0x1801569e3  jns     short loc_1801569EC
0x1801569e5  mov     edx, 2AFh
0x1801569ea  jmp     short loc_180156A46
0x1801569ec  mov     rax, [rdi+0A0h]
0x1801569f3  mov     rcx, [rax+38h]
0x1801569f7  mov     rax, [rdi+18h]
0x1801569fb  mov     edx, 30Ch; unsigned __int64
0x180156a00  mov     rax, [rax+2C8h]
0x180156a07  cmp     [rsp+6D0h+var_680], sil
0x180156a0c  jz      short loc_180156A5D
0x180156a0e  mov     [rsp+6D0h+lpSecurityAttributes], rcx
0x180156a13  mov     qword ptr [rsp+6D0h+samDesired], rax
0x180156a18  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180156a1f  mov     qword ptr [rsp+6D0h+dwOptions], rax; int
0x180156a24  lea     r9, aOsdata; "OSDATA"
0x180156a2b  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180156a32  lea     rcx, [rbp+5D0h+SubKey]; Buffer
0x180156a36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180156a3b  mov     ebx, eax
0x180156a3d  test    eax, eax
0x180156a3f  jns     short loc_180156A8B
0x180156a41  mov     edx, 2BAh; void *
0x180156a46  mov     rcx, [rbp+5D8h]; this
0x180156a4d  mov     r9d, eax; char *
0x180156a50  mov     r8, r14; unsigned int
0x180156a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180156a58  jmp     loc_180156D77
0x180156a5d  mov     qword ptr [rsp+6D0h+samDesired], rcx
0x180156a62  mov     qword ptr [rsp+6D0h+dwOptions], rax
0x180156a67  lea     r9, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180156a6e  lea     r8, aSSS; "%s\\%s\\%s"
0x180156a75  lea     rcx, [rbp+5D0h+SubKey]; Buffer
0x180156a79  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180156a7e  mov     ebx, eax
0x180156a80  test    eax, eax
0x180156a82  jns     short loc_180156A8B
0x180156a84  mov     edx, 2C3h
0x180156a89  jmp     short loc_180156A46
0x180156a8b  lea     rcx, [rsp+6D0h+hKey]
0x180156a90  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180156a95  mov     [rsp+6D0h+lpdwDisposition], rsi; lpdwDisposition
0x180156a9a  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180156a9f  mov     [rsp+6D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180156aa4  mov     [rsp+6D0h+samDesired], 2001Fh; samDesired
0x180156aac  mov     [rsp+6D0h+dwOptions], esi; unsigned int
0x180156ab0  xor     r9d, r9d; lpClass
0x180156ab3  xor     r8d, r8d; Reserved
0x180156ab6  lea     rdx, [rbp+5D0h+SubKey]; lpSubKey
0x180156aba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180156ac1  call    cs:__imp_RegCreateKeyExW
0x180156ac7  test    eax, eax
0x180156ac9  jz      loc_180156CA2
0x180156acf  mov     edx, 2CDh; void *
0x180156ad4  mov     r8, r14; unsigned int
0x180156ad7  mov     r9d, eax; char *
0x180156ada  mov     rcx, [rbp+5D8h]; this
0x180156ae1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180156ae6  mov     ebx, eax
0x180156ae8  jmp     loc_180156D77
0x180156aed  mov     [rsp+6D0h+StringSid], rsi
0x180156af2  xor     edx, edx
0x180156af4  lea     rcx, [rsp+6D0h+StringSid]
0x180156af9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180156afe  mov     rcx, [rdi+18h]
0x180156b02  lea     rdx, [rsp+6D0h+StringSid]; StringSid
0x180156b07  mov     rcx, [rcx+310h]; Sid
0x180156b0e  call    cs:__imp_ConvertSidToStringSidW
0x180156b14  test    eax, eax
0x180156b16  jnz     short loc_180156B44
0x180156b18  mov     ebx, 8007000Eh
0x180156b1d  mov     r9d, ebx; char *
0x180156b20  mov     edx, 2D2h; void *
0x180156b25  mov     r8, r14; unsigned int
0x180156b28  mov     rcx, [rbp+5D8h]; this
0x180156b2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180156b34  nop
0x180156b35  lea     rcx, [rsp+6D0h+StringSid]
0x180156b3a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180156b3f  jmp     loc_180156D77
0x180156b44  mov     rax, [rdi+0A0h]
0x180156b4b  mov     rcx, [rdi+18h]
0x180156b4f  mov     rax, [rax+38h]
0x180156b53  mov     [rsp+6D0h+lpSecurityAttributes], rax
0x180156b58  mov     rax, [rcx+2C8h]
0x180156b5f  mov     qword ptr [rsp+6D0h+samDesired], rax
0x180156b64  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180156b6b  mov     qword ptr [rsp+6D0h+dwOptions], rax; int
0x180156b70  mov     r9, [rsp+6D0h+StringSid]
0x180156b75  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180156b7c  mov     edx, 30Ch; unsigned __int64
0x180156b81  lea     rcx, [rbp+5D0h+SubKey]; Buffer
0x180156b85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180156b8a  mov     ebx, eax
0x180156b8c  test    eax, eax
0x180156b8e  jns     short loc_180156B9A
0x180156b90  mov     r9d, eax
0x180156b93  mov     edx, 2D9h
0x180156b98  jmp     short loc_180156B25
0x180156b9a  mov     [rsp+6D0h+var_670], rsi
0x180156b9f  xor     edx, edx
0x180156ba1  lea     rcx, [rsp+6D0h+var_670]
0x180156ba6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180156bab  lea     r8, [rsp+6D0h+var_670]; void **
0x180156bb0  mov     rdx, [rsp+6D0h+StringSid]; unsigned __int16 *
0x180156bb5  call    ?GetRegkeySD@BackgroundTasksHelper@Internal@DEH@OSIntegration@@AEAAJPEBGPEAPEAX@Z; OSIntegration::DEH::Internal::BackgroundTasksHelper::GetRegkeySD(ushort const *,void * *)
0x180156bba  mov     ebx, eax
0x180156bbc  test    eax, eax
0x180156bbe  jns     short loc_180156BE7
0x180156bc0  mov     edx, 2DCh; void *
0x180156bc5  mov     r8, r14; unsigned int
0x180156bc8  mov     r9d, eax; char *
0x180156bcb  mov     rcx, [rbp+5D8h]; this
0x180156bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180156bd7  nop
0x180156bd8  lea     rcx, [rsp+6D0h+var_670]
0x180156bdd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180156be2  jmp     loc_180156B35
0x180156be7  mov     qword ptr [rsp+6D0h+SecurityAttributes.nLength], 18h
0x180156bf0  xorps   xmm0, xmm0
0x180156bf3  movups  xmmword ptr [rsp+6D0h+SecurityAttributes.lpSecurityDescriptor], xmm0
0x180156bf8  mov     rax, [rsp+6D0h+var_670]
0x180156bfd  mov     [rsp+6D0h+SecurityAttributes.lpSecurityDescriptor], rax
0x180156c02  lea     rcx, [rsp+6D0h+hKey]
0x180156c07  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180156c0c  mov     [rsp+6D0h+lpdwDisposition], rsi; lpdwDisposition
0x180156c11  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180156c16  lea     rax, [rsp+6D0h+SecurityAttributes]
0x180156c1b  mov     [rsp+6D0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180156c20  mov     [rsp+6D0h+samDesired], 2001Fh; samDesired
0x180156c28  mov     [rsp+6D0h+dwOptions], esi; int
0x180156c2c  xor     r9d, r9d; lpClass
0x180156c2f  xor     r8d, r8d; Reserved
0x180156c32  lea     rdx, [rbp+5D0h+SubKey]; lpSubKey
0x180156c36  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180156c3d  call    cs:__imp_RegCreateKeyExW
0x180156c43  test    eax, eax
0x180156c45  jle     short loc_180156C4F
0x180156c47  movzx   eax, ax
0x180156c4a  or      eax, 80070000h
0x180156c4f  mov     rcx, [rbp+5D8h]; this
0x180156c56  test    eax, eax
0x180156c58  jns     short loc_180156C8D
0x180156c5a  mov     r9d, eax; char *
0x180156c5d  mov     r8, r14; unsigned int
0x180156c60  mov     edx, 2E8h; void *
0x180156c65  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180156c6a  mov     r8, [rsp+6D0h+var_670]; unsigned __int16 *
0x180156c6f  lea     rdx, [rbp+5D0h+SubKey]; unsigned __int16 *
0x180156c73  mov     rcx, [rsp+6D0h+StringSid]; StringSid
0x180156c78  call    ?ResetRegistryACL@BackgroundTasks@Internal@DEH@OSIntegration@@YAJPEBG0PEAX@Z; OSIntegration::DEH::Internal::BackgroundTasks::ResetRegistryACL(ushort const *,ushort const *,void *)
0x180156c7d  mov     ebx, eax
0x180156c7f  test    eax, eax
0x180156c81  jns     short loc_180156C8D
0x180156c83  mov     edx, 2EAh
0x180156c88  jmp     loc_180156BC5
0x180156c8d  lea     rcx, [rsp+6D0h+var_670]
0x180156c92  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180156c97  nop
0x180156c98  lea     rcx, [rsp+6D0h+StringSid]
0x180156c9d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180156ca2  lea     rbx, [rdi+0C0h]
0x180156ca9  mov     r9d, 4; dwType
0x180156caf  mov     [rsp+6D0h+samDesired], r9d; cbData
0x180156cb4  mov     qword ptr [rsp+6D0h+dwOptions], rbx; lpData
0x180156cb9  xor     r8d, r8d; Reserved
0x180156cbc  lea     rdx, aCapabilities; "Capabilities"
0x180156cc3  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180156cc8  call    cs:__imp_RegSetValueExW
0x180156cce  test    eax, eax
0x180156cd0  jz      short loc_180156CDC
0x180156cd2  mov     edx, 2FEh
0x180156cd7  jmp     loc_180156AD4
0x180156cdc  lea     rcx, [rdi+0A8h]
0x180156ce3  cmp     [rcx+8], rsi
0x180156ce7  jnz     short loc_180156CF7
0x180156ce9  mov     rcx, [rdi+0A0h]
0x180156cf0  add     rcx, 108h
0x180156cf7  mov     eax, [rcx]
0x180156cf9  lea     eax, ds:2[rax*2]
0x180156d00  mov     [rsp+6D0h+samDesired], eax; cbData
0x180156d04  mov     rax, [rcx+8]
0x180156d08  mov     qword ptr [rsp+6D0h+dwOptions], rax; lpData
0x180156d0d  mov     r9d, 1; dwType
0x180156d13  xor     r8d, r8d; Reserved
0x180156d16  lea     rdx, aAppusermodelid_1; "AppUserModelId"
0x180156d1d  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180156d22  call    cs:__imp_RegSetValueExW
0x180156d28  test    eax, eax
0x180156d2a  jz      short loc_180156D36
0x180156d2c  mov     edx, 310h
0x180156d31  jmp     loc_180156AD4
0x180156d36  mov     rdx, [rdi+18h]
0x180156d3a  cmp     [rdx+196h], sil
0x180156d41  jnz     short loc_180156D75
0x180156d43  test    byte ptr [rbx], 20h
0x180156d46  jz      short loc_180156D75
0x180156d48  mov     rcx, [rdi+0A0h]
0x180156d4f  mov     r8, [rdx+310h]
0x180156d56  mov     rdx, [rdx+0E0h]
0x180156d5d  mov     rcx, [rcx+68h]
0x180156d61  call    cs:__imp_?VpnClientPluginInstall@@YAKPEBG0PEAX@Z; VpnClientPluginInstall(ushort const *,ushort const *,void *)
0x180156d67  test    eax, eax
0x180156d69  jz      short loc_180156D75
0x180156d6b  mov     edx, 31Bh
0x180156d70  jmp     loc_180156AD4
0x180156d75  mov     ebx, esi
0x180156d77  lea     rcx, [rsp+6D0h+hKey]
0x180156d7c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180156d81  mov     eax, ebx
0x180156d83  mov     rcx, [rbp+5D0h+var_20]
0x180156d8a  xor     rcx, rsp; StackCookie
0x180156d8d  call    __security_check_cookie
0x180156d92  lea     r11, [rsp+6D0h+var_10]
0x180156d9a  mov     rbx, [r11+28h]
0x180156d9e  mov     rsi, [r11+30h]
0x180156da2  mov     rsp, r11
0x180156da5  pop     r14
0x180156da7  pop     rdi
0x180156da8  pop     rbp
0x180156da9  retn
```
