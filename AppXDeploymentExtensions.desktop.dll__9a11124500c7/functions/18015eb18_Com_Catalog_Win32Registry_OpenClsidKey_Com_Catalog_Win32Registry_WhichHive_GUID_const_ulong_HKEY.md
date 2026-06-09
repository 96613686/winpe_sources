# Com::Catalog::Win32Registry::OpenClsidKey(Com::Catalog::Win32Registry::WhichHive,_GUID const &,ulong,HKEY__ * *)

- ea: `0x18015eb18`
- end: `0x18015ecd9`
- name: `?OpenClsidKey@Win32Registry@Catalog@Com@@YAJW4WhichHive@123@AEBU_GUID@@KPEAPEAUHKEY__@@@Z`
- size: `449`
- prototype: `int __high(enum Com::Catalog::Win32Registry::WhichHive, const struct _GUID *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180157ea0`

## callees

- `0x18003193c`
- `0x180033ca0`
- `0x1800606d4`
- `0x18006a4c8`
- `0x1800aed10`
- `0x18013a4ac`
- `0x18015eb18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18015eb74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18015ec11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18015ec7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18015eb74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18015ec11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18015ec7f`

## string_xrefs

- `0x18015eb93`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18015ebc5`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18015ec35`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18015eb88`: `Com::Catalog::Win32Registry::OpenClassesRootKey`
- `0x18015eb9a`: `::RegOpenKeyExW(GetHiveKey(whichHive), GetClassesRootPathRelativeToHiveKey(whichHive), 0 , samDesired, key)`
- `0x18015ebba`: `Com::Catalog::Win32Registry::OpenClsidKey`
- `0x18015ec3c`: `Com::Catalog::Win32Registry::OpenClsidKey`
- `0x18015ebcc`: `OpenClassesRootKey(whichHive, KEY_READ, &classesRootKey)`
- `0x18015ec98`: `::RegOpenKeyExW(clsidTopLevelKey.get(), GuidString(clsid), 0 , samDesired, key)`
- `0x18015ec2a`: `::RegOpenKeyExW(classesRootKey.get(), Constants::CLSID, 0 , KEY_READ, &clsidTopLevelKey)`
- `0x18015ebfc`: `CLSID`

## pseudocode

```c
__int64 __fastcall Com::Catalog::Win32Registry::OpenClsidKey(__int64 a1, __int64 a2, __int64 a3, HKEY *a4)
{
  HKEY *phkResult; // rax
  LSTATUS v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  HKEY *v9; // rax
  LSTATUS v10; // eax
  __int64 v11; // rdx
  const char *v12; // rax
  const WCHAR *v13; // rax
  LSTATUS v14; // eax
  wil::details *v16; // [rsp+28h] [rbp-21h]
  HKEY v17; // [rsp+30h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-11h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-9h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a4 = 0;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes", 0, 0x20019u, phkResult);
  if ( v6
    && (LODWORD(v16) = v6,
        v7 = wil::details::in1diag5::Return_Win32(
               retaddr,
               (void *)0x9F,
               (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
               "Com::Catalog::Win32Registry::OpenClassesRootKey",
               "::RegOpenKeyExW(GetHiveKey(whichHive), GetClassesRootPathRelativeToHiveKey(whichHive), 0 , samDesired, key)",
               v16,
               (unsigned int)v17),
        v8 = v7,
        v7 < 0) )
  {
    LODWORD(v16) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
      "Com::Catalog::Win32Registry::OpenClsidKey",
      "OpenClassesRootKey(whichHive, KEY_READ, &classesRootKey)",
      (const char *)v16,
      (int)v17);
  }
  else
  {
    v17 = 0;
    v9 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v17);
    v10 = RegOpenKeyExW(hKey, L"CLSID", 0, 0x20019u, v9);
    if ( v10 )
    {
      LODWORD(v16) = v10;
      v11 = 171;
      v12 = "::RegOpenKeyExW(classesRootKey.get(), Constants::CLSID, 0 , KEY_READ, &clsidTopLevelKey)";
    }
    else
    {
      v13 = (const WCHAR *)GuidString::GuidString(sz, &GUID_ac28605c_a3c1_4901_bed2_1b3de859ce23);
      v14 = RegOpenKeyExW(v17, v13, 0, 0x20019u, a4);
      if ( !v14 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
        v8 = 0;
        goto LABEL_10;
      }
      LODWORD(v16) = v14;
      v11 = 173;
      v12 = "::RegOpenKeyExW(clsidTopLevelKey.get(), GuidString(clsid), 0 , samDesired, key)";
    }
    v8 = wil::details::in1diag5::Return_Win32(
           retaddr,
           (void *)v11,
           (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
           "Com::Catalog::Win32Registry::OpenClsidKey",
           v12,
           v16,
           (unsigned int)v17);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
  }
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x18015eb18  mov     [rsp-8+arg_0], rbx
0x18015eb1d  mov     [rsp-8+arg_8], rdi
0x18015eb22  push    rbp
0x18015eb23  lea     rbp, [rsp-57h]
0x18015eb28  sub     rsp, 0A0h
0x18015eb2f  mov     rax, cs:__security_cookie
0x18015eb36  xor     rax, rsp
0x18015eb39  mov     [rbp+57h+var_10], rax
0x18015eb3d  lea     rcx, [rbp+57h+hKey]
0x18015eb41  mov     qword ptr [r9], 0
0x18015eb48  mov     rdi, r9
0x18015eb4b  mov     [rbp+57h+hKey], 0
0x18015eb53  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18015eb58  mov     r9d, 20019h; samDesired
0x18015eb5e  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18015eb63  xor     r8d, r8d; ulOptions
0x18015eb66  lea     rdx, aSoftwareClasse_3; "Software\\Classes"
0x18015eb6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18015eb74  call    cs:__imp_RegOpenKeyExW
0x18015eb7b  nop     dword ptr [rax+rax+00h]
0x18015eb80  test    eax, eax
0x18015eb82  jz      short loc_18015EBE7
0x18015eb84  mov     rcx, [rbp+5Fh]; this
0x18015eb88  lea     r9, aComCatalogWin3_1; "Com::Catalog::Win32Registry::OpenClasse"...
0x18015eb8f  mov     dword ptr [rsp+0A0h+var_78], eax; wil::details *
0x18015eb93  lea     r8, aOnecorePrivate_2; "onecore\\private\\com\\inc\\combase\\Co"...
0x18015eb9a  lea     rax, aRegopenkeyexwG; "::RegOpenKeyExW(GetHiveKey(whichHive), "...
0x18015eba1  mov     edx, 9Fh; void *
0x18015eba6  mov     [rsp+0A0h+phkResult], rax; char *
0x18015ebab  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x18015ebb0  mov     ebx, eax
0x18015ebb2  test    eax, eax
0x18015ebb4  jns     short loc_18015EBE7
0x18015ebb6  mov     rcx, [rbp+5Fh]; this
0x18015ebba  lea     r9, aComCatalogWin3_0; "Com::Catalog::Win32Registry::OpenClsidK"...
0x18015ebc1  mov     dword ptr [rsp+0A0h+var_78], eax; char *
0x18015ebc5  lea     r8, aOnecorePrivate_2; "onecore\\private\\com\\inc\\combase\\Co"...
0x18015ebcc  lea     rax, aOpenclassesroo; "OpenClassesRootKey(whichHive, KEY_READ,"...
0x18015ebd3  mov     edx, 0A8h; void *
0x18015ebd8  mov     [rsp+0A0h+phkResult], rax; char *
0x18015ebdd  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18015ebe2  jmp     loc_18015ECAC
0x18015ebe7  lea     rcx, [rbp+57h+var_70]
0x18015ebeb  mov     [rbp+57h+var_70], 0
0x18015ebf3  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18015ebf8  mov     rcx, [rbp+57h+hKey]; hKey
0x18015ebfc  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; "CLSID"
0x18015ec03  mov     r9d, 20019h; samDesired
0x18015ec09  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18015ec0e  xor     r8d, r8d; ulOptions
0x18015ec11  call    cs:__imp_RegOpenKeyExW
0x18015ec18  nop     dword ptr [rax+rax+00h]
0x18015ec1d  test    eax, eax
0x18015ec1f  jz      short loc_18015EC5A
0x18015ec21  mov     dword ptr [rsp+0A0h+var_78], eax; wil::details *
0x18015ec25  mov     edx, 0ABh; void *
0x18015ec2a  lea     rax, aRegopenkeyexwC_1; "::RegOpenKeyExW(classesRootKey.get(), C"...
0x18015ec31  mov     rcx, [rbp+5Fh]; this
0x18015ec35  lea     r8, aOnecorePrivate_2; "onecore\\private\\com\\inc\\combase\\Co"...
0x18015ec3c  lea     r9, aComCatalogWin3_0; "Com::Catalog::Win32Registry::OpenClsidK"...
0x18015ec43  mov     [rsp+0A0h+phkResult], rax; char *
0x18015ec48  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x18015ec4d  lea     rcx, [rbp+57h+var_70]
0x18015ec51  mov     ebx, eax
0x18015ec53  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18015ec58  jmp     short loc_18015ECAC
0x18015ec5a  lea     rdx, _GUID_ac28605c_a3c1_4901_bed2_1b3de859ce23; rguid
0x18015ec61  lea     rcx, [rbp+57h+sz]; lpsz
0x18015ec65  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x18015ec6a  mov     rcx, [rbp+57h+var_70]; hKey
0x18015ec6e  mov     r9d, 20019h; samDesired
0x18015ec74  xor     r8d, r8d; ulOptions
0x18015ec77  mov     [rsp+0A0h+phkResult], rdi; phkResult
0x18015ec7c  mov     rdx, rax; lpSubKey
0x18015ec7f  call    cs:__imp_RegOpenKeyExW
0x18015ec86  nop     dword ptr [rax+rax+00h]
0x18015ec8b  test    eax, eax
0x18015ec8d  jz      short loc_18015ECA1
0x18015ec8f  mov     dword ptr [rsp+0A0h+var_78], eax
0x18015ec93  mov     edx, 0ADh
0x18015ec98  lea     rax, aRegopenkeyexwC; "::RegOpenKeyExW(clsidTopLevelKey.get(),"...
0x18015ec9f  jmp     short loc_18015EC31
0x18015eca1  lea     rcx, [rbp+57h+var_70]
0x18015eca5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18015ecaa  xor     ebx, ebx
0x18015ecac  lea     rcx, [rbp+57h+hKey]
0x18015ecb0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18015ecb5  mov     eax, ebx
0x18015ecb7  mov     rcx, [rbp+57h+var_10]
0x18015ecbb  xor     rcx, rsp; StackCookie
0x18015ecbe  call    __security_check_cookie
0x18015ecc3  lea     r11, [rsp+0A0h+var_s0]
0x18015eccb  mov     rbx, [r11+10h]
0x18015eccf  mov     rdi, [r11+18h]
0x18015ecd3  mov     rsp, r11
0x18015ecd6  pop     rbp
0x18015ecd7  retn
```
