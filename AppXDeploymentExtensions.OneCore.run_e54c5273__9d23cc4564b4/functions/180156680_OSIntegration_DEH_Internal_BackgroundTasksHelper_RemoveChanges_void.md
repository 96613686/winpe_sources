# OSIntegration::DEH::Internal::BackgroundTasksHelper::RemoveChanges(void)

- ea: `0x180156680`
- end: `0x180156968`
- name: `?RemoveChanges@BackgroundTasksHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `744`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::BackgroundTasksHelper *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180012964`
- `0x18004f3c4`
- `0x180067050`
- `0x180070b78`
- `0x180080b84`
- `0x180087238`
- `0x180098bf4`
- `0x1800f0260`
- `0x180156680`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801568ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801568ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180156856`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180156856`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801568dc`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180156939`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801568dc`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180156939`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801567a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801567a7`
- `Windows.Networking.Vpn!VpnClientPluginUninstall` at `0x180156920`
- `Windows.Networking.Vpn!VpnClientPluginUninstall` at `0x180156920`

## string_xrefs

- `0x180156740`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtaskshelper.cpp`
- `0x1801567be`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtaskshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::Internal::BackgroundTasksHelper::RemoveChanges(
        OSIntegration::DEH::Internal::BackgroundTasksHelper *this)
{
  __int64 v2; // rax
  int IsStateSeparationEnabled; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  HKEY *v11; // rax
  LSTATUS v12; // eax
  bool v13; // sf
  LSTATUS v14; // eax
  bool v15; // sf
  LSTATUS v16; // eax
  bool v17; // sf
  DWORD v18; // eax
  __int64 v19; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  bool v21; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[520]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v2 = *((_QWORD *)this + 3);
  if ( *(_BYTE *)(v2 + 403) )
    return 0;
  hKey[0] = 0;
  if ( !*(_BYTE *)(v2 + 406) )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( ConvertSidToStringSidW(*(PSID *)(*((_QWORD *)this + 3) + 784LL), &StringSid) )
    {
      phkResult = (PHKEY)L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability";
      v10 = StringCchPrintfW(SubKey, 0x208u, L"%s\\%s\\%s", StringSid);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v7 = -2147483645;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
        goto LABEL_19;
      }
      v8 = (unsigned int)v10;
      v9 = 849;
    }
    else
    {
      v5 = -2147024882;
      v8 = 2147942414LL;
      v9 = 843;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtaskshelper.cpp",
      (const char *)v8,
      (int)phkResult);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    goto LABEL_36;
  }
  v21 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v21);
  v5 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled >= 0 )
  {
    if ( v21 )
    {
      phkResult = (PHKEY)L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability";
      IsStateSeparationEnabled = StringCchPrintfW(SubKey, 0x208u, L"%s\\%s\\%s", L"OSDATA");
      v5 = IsStateSeparationEnabled;
      if ( IsStateSeparationEnabled < 0 )
      {
        v6 = 826;
        goto LABEL_9;
      }
    }
    else
    {
      phkResult = *(PHKEY *)(*((_QWORD *)this + 3) + 712LL);
      IsStateSeparationEnabled = StringCchPrintfW(
                                   SubKey,
                                   0x208u,
                                   L"%s\\%s",
                                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\"
                                    "BackgroundCapability");
      v5 = IsStateSeparationEnabled;
      if ( IsStateSeparationEnabled < 0 )
      {
        v6 = 835;
        goto LABEL_9;
      }
    }
    v7 = -2147483646;
LABEL_19:
    v11 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
    v12 = RegOpenKeyExW((HKEY)v7, SubKey, 0, 0x2001Fu, v11);
    v13 = v12 < 0;
    if ( v12 > 0 )
      v13 = 1;
    if ( v13 )
      goto LABEL_35;
    cSubKeys = 0;
    v14 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v15 = v14 < 0;
    if ( v14 > 0 )
      v15 = 1;
    if ( v15 )
      goto LABEL_35;
    if ( !cSubKeys )
      goto LABEL_34;
    v16 = RegDeleteKeyW(hKey[0], *(LPCWSTR *)(*((_QWORD *)this + 20) + 56LL));
    v17 = v16 < 0;
    if ( v16 > 0 )
      v17 = 1;
    if ( v17 )
      goto LABEL_35;
    v18 = --cSubKeys;
    v19 = *((_QWORD *)this + 3);
    if ( !*(_BYTE *)(v19 + 406) && (*((_BYTE *)this + 192) & 0x20) != 0 )
    {
      if ( (VpnClientPluginUninstall(*(const unsigned __int16 **)(v19 + 224), *(void **)(v19 + 784)) & 0x80000000) != 0 )
        goto LABEL_35;
      v18 = cSubKeys;
    }
    if ( !v18 )
LABEL_34:
      RegDeleteKeyW((HKEY)v7, SubKey);
LABEL_35:
    v5 = 0;
    goto LABEL_36;
  }
  v6 = 816;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtaskshelper.cpp",
    (const char *)(unsigned int)IsStateSeparationEnabled,
    (int)phkResult);
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return v5;
}

```

## disassembly

```asm
0x180156680  push    rbp
0x180156682  push    rbx
0x180156683  push    rsi
0x180156684  push    rdi
0x180156685  lea     rbp, [rsp-3A8h]
0x18015668d  sub     rsp, 4A8h
0x180156694  mov     rax, cs:__security_cookie
0x18015669b  xor     rax, rsp
0x18015669e  mov     [rbp+3C0h+var_30], rax
0x1801566a5  mov     rdi, rcx
0x1801566a8  mov     rax, [rcx+18h]
0x1801566ac  xor     esi, esi
0x1801566ae  cmp     [rax+193h], sil
0x1801566b5  jz      short loc_1801566BE
0x1801566b7  xor     eax, eax
0x1801566b9  jmp     loc_18015694D
0x1801566be  mov     [rsp+4C0h+hKey], rsi
0x1801566c3  cmp     [rax+196h], sil
0x1801566ca  jz      loc_180156786
0x1801566d0  mov     [rsp+4C0h+var_460], sil
0x1801566d5  lea     rcx, [rsp+4C0h+var_460]; bool *
0x1801566da  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1801566df  mov     ebx, eax
0x1801566e1  test    eax, eax
0x1801566e3  jns     short loc_1801566EC
0x1801566e5  mov     edx, 330h
0x1801566ea  jmp     short loc_180156736
0x1801566ec  mov     rax, [rdi+18h]
0x1801566f0  mov     rcx, [rax+2C8h]
0x1801566f7  mov     edx, 208h; unsigned __int64
0x1801566fc  cmp     [rsp+4C0h+var_460], sil
0x180156701  jz      short loc_180156751
0x180156703  mov     [rsp+4C0h+lpcbMaxSubKeyLen], rcx
0x180156708  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18015670f  mov     [rsp+4C0h+phkResult], rax; int
0x180156714  lea     r9, aOsdata; "OSDATA"
0x18015671b  lea     r8, aSSS; "%s\\%s\\%s"
0x180156722  lea     rcx, [rbp+3C0h+SubKey]; Buffer
0x180156726  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18015672b  mov     ebx, eax
0x18015672d  test    eax, eax
0x18015672f  jns     short loc_18015677A
0x180156731  mov     edx, 33Ah; void *
0x180156736  mov     rcx, [rbp+3C8h]; this
0x18015673d  mov     r9d, eax; char *
0x180156740  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180156747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015674c  jmp     loc_180156941
0x180156751  mov     [rsp+4C0h+phkResult], rcx
0x180156756  lea     r9, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18015675d  lea     r8, aSS; "%s\\%s"
0x180156764  lea     rcx, [rbp+3C0h+SubKey]; Buffer
0x180156768  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18015676d  mov     ebx, eax
0x18015676f  test    eax, eax
0x180156771  jns     short loc_18015677A
0x180156773  mov     edx, 343h
0x180156778  jmp     short loc_180156736
0x18015677a  mov     rbx, 0FFFFFFFF80000002h
0x180156781  jmp     loc_180156837
0x180156786  mov     [rsp+4C0h+StringSid], rsi
0x18015678b  xor     edx, edx
0x18015678d  lea     rcx, [rsp+4C0h+StringSid]
0x180156792  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180156797  mov     rcx, [rdi+18h]
0x18015679b  lea     rdx, [rsp+4C0h+StringSid]; StringSid
0x1801567a0  mov     rcx, [rcx+310h]; Sid
0x1801567a7  call    cs:__imp_ConvertSidToStringSidW
0x1801567ad  test    eax, eax
0x1801567af  jnz     short loc_1801567E0
0x1801567b1  mov     ebx, 8007000Eh
0x1801567b6  mov     r9d, ebx; char *
0x1801567b9  mov     edx, 34Bh; void *
0x1801567be  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801567c5  mov     rcx, [rbp+3C8h]; this
0x1801567cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801567d1  lea     rcx, [rsp+4C0h+StringSid]
0x1801567d6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1801567db  jmp     loc_180156941
0x1801567e0  mov     rax, [rdi+18h]
0x1801567e4  mov     rcx, [rax+2C8h]
0x1801567eb  mov     [rsp+4C0h+lpcbMaxSubKeyLen], rcx
0x1801567f0  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801567f7  mov     [rsp+4C0h+phkResult], rax
0x1801567fc  mov     r9, [rsp+4C0h+StringSid]
0x180156801  lea     r8, aSSS; "%s\\%s\\%s"
0x180156808  mov     edx, 208h; unsigned __int64
0x18015680d  lea     rcx, [rbp+3C0h+SubKey]; Buffer
0x180156811  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180156816  mov     ebx, eax
0x180156818  test    eax, eax
0x18015681a  jns     short loc_180156826
0x18015681c  mov     r9d, eax
0x18015681f  mov     edx, 351h
0x180156824  jmp     short loc_1801567BE
0x180156826  mov     rbx, 0FFFFFFFF80000003h
0x18015682d  lea     rcx, [rsp+4C0h+StringSid]
0x180156832  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180156837  lea     rcx, [rsp+4C0h+hKey]
0x18015683c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180156841  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180156846  mov     r9d, 2001Fh; samDesired
0x18015684c  xor     r8d, r8d; ulOptions
0x18015684f  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x180156853  mov     rcx, rbx; hKey
0x180156856  call    cs:__imp_RegOpenKeyExW
0x18015685c  test    eax, eax
0x18015685e  jle     short loc_18015686A
0x180156860  movzx   eax, ax
0x180156863  or      eax, 80070000h
0x180156868  test    eax, eax
0x18015686a  js      loc_18015693F
0x180156870  mov     [rsp+4C0h+cSubKeys], esi
0x180156874  mov     [rsp+4C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180156879  mov     [rsp+4C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18015687e  mov     [rsp+4C0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180156883  mov     [rsp+4C0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180156888  mov     [rsp+4C0h+lpcValues], rsi; lpcValues
0x18015688d  mov     [rsp+4C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180156892  mov     [rsp+4C0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180156897  lea     rax, [rsp+4C0h+cSubKeys]
0x18015689c  mov     [rsp+4C0h+phkResult], rax; lpcSubKeys
0x1801568a1  xor     r9d, r9d; lpReserved
0x1801568a4  xor     r8d, r8d; lpcchClass
0x1801568a7  xor     edx, edx; lpClass
0x1801568a9  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1801568ae  call    cs:__imp_RegQueryInfoKeyW
0x1801568b4  test    eax, eax
0x1801568b6  jle     short loc_1801568C2
0x1801568b8  movzx   eax, ax
0x1801568bb  or      eax, 80070000h
0x1801568c0  test    eax, eax
0x1801568c2  js      short loc_18015693F
0x1801568c4  mov     eax, [rsp+4C0h+cSubKeys]
0x1801568c8  test    eax, eax
0x1801568ca  jz      short loc_180156932
0x1801568cc  mov     rdx, [rdi+0A0h]
0x1801568d3  mov     rdx, [rdx+38h]; lpSubKey
0x1801568d7  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1801568dc  call    cs:__imp_RegDeleteKeyW
0x1801568e2  test    eax, eax
0x1801568e4  jle     short loc_1801568F0
0x1801568e6  movzx   eax, ax
0x1801568e9  or      eax, 80070000h
0x1801568ee  test    eax, eax
0x1801568f0  js      short loc_18015693F
0x1801568f2  mov     eax, [rsp+4C0h+cSubKeys]
0x1801568f6  dec     eax
0x1801568f8  mov     [rsp+4C0h+cSubKeys], eax
0x1801568fc  mov     rcx, [rdi+18h]
0x180156900  cmp     [rcx+196h], sil
0x180156907  jnz     short loc_18015692E
0x180156909  test    byte ptr [rdi+0C0h], 20h
0x180156910  jz      short loc_18015692E
0x180156912  mov     rdx, [rcx+310h]
0x180156919  mov     rcx, [rcx+0E0h]
0x180156920  call    cs:__imp_?VpnClientPluginUninstall@@YAKPEBGPEAX@Z; VpnClientPluginUninstall(ushort const *,void *)
0x180156926  test    eax, eax
0x180156928  js      short loc_18015693F
0x18015692a  mov     eax, [rsp+4C0h+cSubKeys]
0x18015692e  test    eax, eax
0x180156930  jnz     short loc_18015693F
0x180156932  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x180156936  mov     rcx, rbx; hKey
0x180156939  call    cs:__imp_RegDeleteKeyW
0x18015693f  mov     ebx, esi
0x180156941  lea     rcx, [rsp+4C0h+hKey]
0x180156946  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18015694b  mov     eax, ebx
0x18015694d  mov     rcx, [rbp+3C0h+var_30]
0x180156954  xor     rcx, rsp; StackCookie
0x180156957  call    __security_check_cookie
0x18015695c  add     rsp, 4A8h
0x180156963  pop     rdi
0x180156964  pop     rsi
0x180156965  pop     rbx
0x180156966  pop     rbp
0x180156967  retn
```
