# SystemSettings::DataModel::CopyCurrentUserSettings::IntlLoadNtUserHive(ushort const *,ushort const *,uchar *)

- ea: `0x140044000`
- end: `0x140044189`
- name: `?IntlLoadNtUserHive@CopyCurrentUserSettings@DataModel@SystemSettings@@CAPEAUHKEY__@@PEBG0PEAE@Z`
- size: `393`
- prototype: `static HKEY(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14004435c`
- `0x1400445f0`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14000ed38`
- `0x140026058`
- `0x140026134`
- `0x14002c070`
- `0x14002c2d4`
- `0x140044000`
- `0x1400447b4`
- `0x140044b1c`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140044126`
- `KERNEL32!RegOpenKeyExW` at `0x140044126`
- `KERNEL32!RegLoadKeyW` at `0x1400440aa`
- `KERNEL32!RegLoadKeyW` at `0x1400440aa`
- `USERENV!GetDefaultUserProfileDirectoryW` at `0x14004405c`
- `USERENV!GetDefaultUserProfileDirectoryW` at `0x14004405c`

## string_xrefs

- `0x1400440a3`: `TempKey`
- `0x1400440d8`: `TempKey`

## pseudocode

```c
HKEY __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlLoadNtUserHive(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char *a3)
{
  const unsigned __int16 *v5; // rcx
  LSTATUS KeyW; // ebx
  const unsigned __int16 *v7; // rcx
  const unsigned __int16 *v8; // rcx
  HKEY *phkResult; // rax
  HKEY v10; // rbx
  HKEY v12; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchSize; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ProfileDir[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[256]; // [rsp+250h] [rbp+150h] BYREF

  v12 = 0;
  memset_0(ProfileDir, 0, 0x208u);
  cchSize = 260;
  if ( GetDefaultUserProfileDirectoryW(ProfileDir, &cchSize) )
  {
    if ( StringCchCatW(ProfileDir, 0x104u, L"\\NTUSER.DAT") >= 0
      && (int)SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetPrivilegeAccessToken(
                v5,
                1,
                (unsigned __int8 *)a3) >= 0 )
    {
      KeyW = RegLoadKeyW(HKEY_USERS, L"TempKey", ProfileDir);
      SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetPrivilegeAccessToken(v7, *a3, (unsigned __int8 *)a3);
      if ( !KeyW )
      {
        memset_0(SubKey, 0, sizeof(SubKey));
        if ( StringCchPrintfW(SubKey, 0x100u, L"%s\\%s", L"TempKey", a2) >= 0 )
        {
          phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v12);
          if ( RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20006u, phkResult) )
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &v12,
              0);
        }
        if ( !v12 )
          SystemSettings::DataModel::CopyCurrentUserSettings::IntlUnloadNtUserHive(v8, (unsigned __int8 *)a3);
      }
    }
  }
  v10 = v12;
  v12 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
  return v10;
}

```

## disassembly

```asm
0x140044000  mov     [rsp-8+arg_0], rbx
0x140044005  push    rbp
0x140044006  push    rsi
0x140044007  push    rdi
0x140044008  lea     rbp, [rsp-360h]
0x140044010  sub     rsp, 460h
0x140044017  mov     rax, cs:__security_cookie
0x14004401e  xor     rax, rsp
0x140044021  mov     [rbp+370h+var_20], rax
0x140044028  mov     rdi, r8
0x14004402b  mov     [rsp+470h+var_440], 0
0x140044034  mov     rsi, rdx
0x140044037  lea     rcx, [rsp+470h+ProfileDir]; void *
0x14004403c  xor     edx, edx; Val
0x14004403e  mov     r8d, 208h; Size
0x140044044  call    memset_0
0x140044049  mov     ebx, 104h
0x14004404e  lea     rdx, [rsp+470h+cchSize]; lpcchSize
0x140044053  lea     rcx, [rsp+470h+ProfileDir]; lpProfileDir
0x140044058  mov     [rsp+470h+cchSize], ebx
0x14004405c  call    cs:__imp_GetDefaultUserProfileDirectoryW
0x140044062  test    eax, eax
0x140044064  jz      loc_14004414C
0x14004406a  lea     r8, aNtuserDat; "\\NTUSER.DAT"
0x140044071  mov     edx, ebx; unsigned __int64
0x140044073  lea     rcx, [rsp+470h+ProfileDir]; unsigned __int16 *
0x140044078  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14004407d  test    eax, eax
0x14004407f  js      loc_14004414C
0x140044085  mov     r8, rdi; unsigned __int8 *
0x140044088  mov     dl, 1; unsigned __int8
0x14004408a  call    ?IntlSetPrivilegeAccessToken@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEBGEPEAE@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetPrivilegeAccessToken(ushort const *,uchar,uchar *)
0x14004408f  test    eax, eax
0x140044091  js      loc_14004414C
0x140044097  lea     r8, [rsp+470h+ProfileDir]; lpFile
0x14004409c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1400440a3  lea     rdx, aTempkey; "TempKey"
0x1400440aa  call    cs:__imp_RegLoadKeyW
0x1400440b0  mov     dl, [rdi]; unsigned __int8
0x1400440b2  mov     r8, rdi; unsigned __int8 *
0x1400440b5  mov     ebx, eax
0x1400440b7  call    ?IntlSetPrivilegeAccessToken@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEBGEPEAE@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetPrivilegeAccessToken(ushort const *,uchar,uchar *)
0x1400440bc  test    ebx, ebx
0x1400440be  jnz     loc_14004414C
0x1400440c4  xor     edx, edx; Val
0x1400440c6  lea     rcx, [rbp+370h+SubKey]; void *
0x1400440cd  mov     r8d, 200h; Size
0x1400440d3  call    memset_0
0x1400440d8  lea     r9, aTempkey; "TempKey"
0x1400440df  mov     [rsp+470h+phkResult], rsi
0x1400440e4  lea     r8, aSS_0; "%s\\%s"
0x1400440eb  mov     edx, 100h; unsigned __int64
0x1400440f0  lea     rcx, [rbp+370h+SubKey]; unsigned __int16 *
0x1400440f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400440fc  test    eax, eax
0x1400440fe  js      short loc_14004413C
0x140044100  lea     rcx, [rsp+470h+var_440]
0x140044105  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x14004410a  mov     r9d, 20006h; samDesired
0x140044110  mov     [rsp+470h+phkResult], rax; phkResult
0x140044115  xor     r8d, r8d; ulOptions
0x140044118  lea     rdx, [rbp+370h+SubKey]; lpSubKey
0x14004411f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x140044126  call    cs:__imp_RegOpenKeyExW
0x14004412c  test    eax, eax
0x14004412e  jz      short loc_14004413C
0x140044130  xor     edx, edx
0x140044132  lea     rcx, [rsp+470h+var_440]
0x140044137  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14004413c  cmp     [rsp+470h+var_440], 0
0x140044142  jnz     short loc_14004414C
0x140044144  mov     rdx, rdi; unsigned __int8 *
0x140044147  call    ?IntlUnloadNtUserHive@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEBGPEAE@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlUnloadNtUserHive(ushort const *,uchar *)
0x14004414c  mov     rbx, [rsp+470h+var_440]
0x140044151  lea     rcx, [rsp+470h+var_440]
0x140044156  mov     [rsp+470h+var_440], 0
0x14004415f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140044164  mov     rax, rbx
0x140044167  mov     rcx, [rbp+370h+var_20]
0x14004416e  xor     rcx, rsp; StackCookie
0x140044171  call    __security_check_cookie
0x140044176  mov     rbx, [rsp+470h+arg_0]
0x14004417e  add     rsp, 460h
0x140044185  pop     rdi
0x140044186  pop     rsi
0x140044187  pop     rbp
0x140044188  retn
```
