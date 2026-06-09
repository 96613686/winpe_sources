# CKeyboardLayoutData::ReadKeyboardLayoutFromRegister(KeyboardLayoutMode &)

- ea: `0x1800fe888`
- end: `0x1800feab9`
- name: `?ReadKeyboardLayoutFromRegister@CKeyboardLayoutData@@AEAAJAEAW4KeyboardLayoutMode@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(CKeyboardLayoutData *__hidden this, enum KeyboardLayoutMode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fe73c`

## callees

- `0x18000c840`
- `0x180021470`
- `0x18002e1f4`
- `0x180041004`
- `0x180044eb4`
- `0x1800740f4`
- `0x1800fe888`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fe8d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fe9a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fea2f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fe8d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fe9a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fea2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe9ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe9ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe952`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe952`

## string_xrefs

- `0x1800fe944`: `SYSTEM\CurrentControlSet\Services\i8042prt\Parameters`

## pseudocode

```c
__int64 __fastcall CKeyboardLayoutData::ReadKeyboardLayoutFromRegister(LPCWCH *this, enum KeyboardLayoutMode *a2)
{
  wchar_t **v3; // rbx
  HKEY *v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  wchar_t **v8; // rbx
  const WCHAR *v9; // r8
  unsigned int ValueW; // eax
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-268h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-268h]
  const char *pvData; // [rsp+28h] [rbp-260h]
  DWORD pcbData; // [rsp+40h] [rbp-248h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-240h] BYREF
  WCHAR String1[264]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v3 = &off_1802BFA80;
  while ( CompareStringOrdinal(*v3, -1, this[3], -1, 1) != 2 )
  {
    v3 += 2;
    if ( v3 == off_1802BFAA0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x6F,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\language\\lib\\keyboardlayoutdata.cpp",
        (const char *)0x80004005LL,
        (int)"Failed to detect default keyboard layout type",
        pvData);
      goto LABEL_6;
    }
  }
  *(_DWORD *)a2 = *((_DWORD *)v3 + 2);
LABEL_6:
  hkey = 0;
  v5 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\i8042prt\\Parameters", 0, 0x20019u, v5);
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x77,
           (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\language\\lib\\keyboardlayoutdata.cpp",
           (const char *)v6,
           bIgnoreCase);
  }
  else
  {
    v8 = off_1802BFAA0;
    while ( 1 )
    {
      if ( CompareStringOrdinal(*v8, -1, this[3], -1, 1) == 2 )
      {
        v9 = v8[1];
        pcbData = 520;
        ValueW = RegGetValueW(hkey, 0, v9, 2u, 0, String1, &pcbData);
        if ( ValueW )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x89,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\language\\lib\\keyboardlayoutdata.cpp",
            (const char *)ValueW,
            bIgnoreCasea);
        if ( CompareStringOrdinal(String1, -1, v8[2], -1, 1) == 2 )
          break;
      }
      v8 += 4;
      if ( v8 == &off_1802BFBA0 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x95,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\language\\lib\\keyboardlayoutdata.cpp",
          (const char *)0x80004005LL,
          (int)"Failed to detect keyboard layout type",
          pvData);
        goto LABEL_15;
      }
    }
    *(_DWORD *)a2 = *((_DWORD *)v8 + 6);
LABEL_15:
    v7 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v7;
}

```

## disassembly

```asm
0x1800fe888  mov     [rsp+arg_10], rbx
0x1800fe88d  push    rsi
0x1800fe88e  push    rdi
0x1800fe88f  push    r14
0x1800fe891  sub     rsp, 270h
0x1800fe898  mov     rax, cs:__security_cookie
0x1800fe89f  xor     rax, rsp
0x1800fe8a2  mov     [rsp+288h+var_28], rax
0x1800fe8aa  mov     rdi, rdx
0x1800fe8ad  lea     rbx, off_1802BFA80; "ja"
0x1800fe8b4  mov     rsi, rcx
0x1800fe8b7  or      r14d, 0FFFFFFFFh
0x1800fe8bb  mov     r8, [rsi+18h]; lpString2
0x1800fe8bf  mov     r9d, r14d; cchCount2
0x1800fe8c2  mov     rcx, [rbx]; lpString1
0x1800fe8c5  mov     edx, r14d; cchCount1
0x1800fe8c8  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800fe8d0  call    cs:__imp_CompareStringOrdinal
0x1800fe8d7  nop     dword ptr [rax+rax+00h]
0x1800fe8dc  cmp     eax, 2
0x1800fe8df  jz      short loc_1800FE91E
0x1800fe8e1  add     rbx, 10h
0x1800fe8e5  lea     rax, off_1802BFAA0; "ja"
0x1800fe8ec  cmp     rbx, rax
0x1800fe8ef  jnz     short loc_1800FE8BB
0x1800fe8f1  mov     rcx, [rsp+288h]; this
0x1800fe8f9  lea     rax, aFailedToDetect_0; "Failed to detect default keyboard layou"...
0x1800fe900  mov     r9d, 80004005h; char *
0x1800fe906  mov     qword ptr [rsp+288h+bIgnoreCase], rax; int
0x1800fe90b  lea     r8, aShellSystemset_66; "shell\\systemsettingsthreshold\\handler"...
0x1800fe912  mov     edx, 6Fh ; 'o'; void *
0x1800fe917  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fe91c  jmp     short loc_1800FE923
0x1800fe91e  mov     eax, [rbx+8]
0x1800fe921  mov     [rdi], eax
0x1800fe923  lea     rcx, [rsp+288h+hkey]
0x1800fe928  mov     [rsp+288h+hkey], 0
0x1800fe931  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800fe936  mov     r9d, 20019h; samDesired
0x1800fe93c  mov     qword ptr [rsp+288h+bIgnoreCase], rax; unsigned int
0x1800fe941  xor     r8d, r8d; ulOptions
0x1800fe944  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\i8"...
0x1800fe94b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800fe952  call    cs:__imp_RegOpenKeyExW
0x1800fe959  nop     dword ptr [rax+rax+00h]
0x1800fe95e  test    eax, eax
0x1800fe960  jz      short loc_1800FE985
0x1800fe962  mov     rcx, [rsp+288h]; this
0x1800fe96a  lea     r8, aShellSystemset_66; "shell\\systemsettingsthreshold\\handler"...
0x1800fe971  mov     r9d, eax; char *
0x1800fe974  mov     edx, 77h ; 'w'; void *
0x1800fe979  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fe97e  mov     ebx, eax
0x1800fe980  jmp     loc_1800FEA81
0x1800fe985  lea     rbx, off_1802BFAA0; "ja"
0x1800fe98c  mov     r8, [rsi+18h]; lpString2
0x1800fe990  mov     r9d, r14d; cchCount2
0x1800fe993  mov     rcx, [rbx]; lpString1
0x1800fe996  mov     edx, r14d; cchCount1
0x1800fe999  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800fe9a1  call    cs:__imp_CompareStringOrdinal
0x1800fe9a8  nop     dword ptr [rax+rax+00h]
0x1800fe9ad  cmp     eax, 2
0x1800fe9b0  jnz     loc_1800FEA40
0x1800fe9b6  mov     r8, [rbx+8]; lpValue
0x1800fe9ba  lea     rax, [rsp+288h+var_248]
0x1800fe9bf  mov     rcx, [rsp+288h+hkey]; hkey
0x1800fe9c4  mov     r9d, 2; dwFlags
0x1800fe9ca  mov     [rsp+288h+pcbData], rax; pcbData
0x1800fe9cf  xor     edx, edx; lpSubKey
0x1800fe9d1  lea     rax, [rsp+288h+String1]
0x1800fe9d6  mov     [rsp+288h+var_248], 208h
0x1800fe9de  mov     [rsp+288h+pvData], rax; char *
0x1800fe9e3  mov     qword ptr [rsp+288h+bIgnoreCase], 0; unsigned int
0x1800fe9ec  call    cs:__imp_RegGetValueW
0x1800fe9f3  nop     dword ptr [rax+rax+00h]
0x1800fe9f8  test    eax, eax
0x1800fe9fa  jz      short loc_1800FEA18
0x1800fe9fc  mov     rcx, [rsp+288h]; this
0x1800fea04  lea     r8, aShellSystemset_66; "shell\\systemsettingsthreshold\\handler"...
0x1800fea0b  mov     r9d, eax; char *
0x1800fea0e  mov     edx, 89h; void *
0x1800fea13  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800fea18  mov     r8, [rbx+10h]; lpString2
0x1800fea1c  lea     rcx, [rsp+288h+String1]; lpString1
0x1800fea21  mov     r9d, r14d; cchCount2
0x1800fea24  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800fea2c  mov     edx, r14d; cchCount1
0x1800fea2f  call    cs:__imp_CompareStringOrdinal
0x1800fea36  nop     dword ptr [rax+rax+00h]
0x1800fea3b  cmp     eax, 2
0x1800fea3e  jz      short loc_1800FEAB2
0x1800fea40  add     rbx, 20h ; ' '
0x1800fea44  lea     rax, off_1802BFBA0; "SystemSettings_Misc_PointInTimeSettings"...
0x1800fea4b  cmp     rbx, rax
0x1800fea4e  jnz     loc_1800FE98C
0x1800fea54  mov     rcx, [rsp+288h]; this
0x1800fea5c  lea     rax, aFailedToDetect; "Failed to detect keyboard layout type"
0x1800fea63  mov     r9d, 80004005h; char *
0x1800fea69  mov     qword ptr [rsp+288h+bIgnoreCase], rax; int
0x1800fea6e  lea     r8, aShellSystemset_66; "shell\\systemsettingsthreshold\\handler"...
0x1800fea75  mov     edx, 95h; void *
0x1800fea7a  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fea7f  xor     ebx, ebx
0x1800fea81  lea     rcx, [rsp+288h+hkey]
0x1800fea86  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fea8b  mov     eax, ebx
0x1800fea8d  mov     rcx, [rsp+288h+var_28]
0x1800fea95  xor     rcx, rsp; StackCookie
0x1800fea98  call    __security_check_cookie
0x1800fea9d  mov     rbx, [rsp+288h+arg_10]
0x1800feaa5  add     rsp, 270h
0x1800feaac  pop     r14
0x1800feaae  pop     rdi
0x1800feaaf  pop     rsi
0x1800feab0  retn
0x1800feab2  mov     eax, [rbx+18h]
0x1800feab5  mov     [rdi], eax
0x1800feab7  jmp     short loc_1800FEA7F
```
