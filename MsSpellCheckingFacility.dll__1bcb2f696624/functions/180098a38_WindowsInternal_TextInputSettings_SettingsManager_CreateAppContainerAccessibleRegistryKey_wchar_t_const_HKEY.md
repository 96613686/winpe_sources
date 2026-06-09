# WindowsInternal::TextInputSettings::SettingsManager::CreateAppContainerAccessibleRegistryKey(wchar_t const *,HKEY__ * *)

- ea: `0x180098a38`
- end: `0x180098b3e`
- name: `?CreateAppContainerAccessibleRegistryKey@SettingsManager@TextInputSettings@WindowsInternal@@YAJPEB_WPEAPEAUHKEY__@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(WindowsInternal::TextInputSettings::SettingsManager *__hidden this, const wchar_t *, HKEY *)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007d4cc`
- `0x18009aa94`
- `0x18009ac30`
- `0x18009ad00`
- `0x18009ae50`
- `0x18009af90`

## callees

- `0x18004aa2c`
- `0x18007ca90`
- `0x180098a38`
- `0x180098cc8`
- `0x18009a2d0`
- `0x18009a680`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180098ab4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180098b05`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180098ab4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180098b05`

## string_xrefs

- `0x180098ad6`: `mincore\textinput\dev\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`

## pseudocode

```c
__int64 __fastcall WindowsInternal::TextInputSettings::SettingsManager::CreateAppContainerAccessibleRegistryKey(
        WindowsInternal::TextInputSettings::SettingsManager *this,
        wchar_t *a2,
        HKEY *a3,
        wchar_t *a4)
{
  unsigned int v5; // eax
  unsigned int v6; // r8d
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rax
  unsigned int v12; // [rsp+20h] [rbp-28h]
  unsigned int v13; // [rsp+20h] [rbp-28h]
  unsigned int v14; // [rsp+28h] [rbp-20h]
  unsigned int *v15; // [rsp+40h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY v17; // [rsp+50h] [rbp+8h] BYREF
  struct _SECURITY_ATTRIBUTES handle; // [rsp+58h] [rbp+10h] BYREF

  HIDWORD(v17) = HIDWORD(this);
  *(_QWORD *)a2 = 0;
  LODWORD(v17) = 0;
  *(_QWORD *)&handle.nLength = 0;
  v5 = RegHelpers::RegCreateKeyExW(
         this,
         (HKEY)L"Software\\Microsoft\\TabletTip\\1.7",
         (const wchar_t *)a3,
         a4,
         v12,
         v14,
         &handle,
         &v17,
         v15);
  if ( v5 )
  {
    v7 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x210, v6, (const char *)v5, v13);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&handle);
    RegDeleteKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\TabletTip\\1.7", 0, 0);
    return v7;
  }
  else
  {
    v9 = WindowsInternal::TextInputSettings::SettingsManager::EnsureAppContainerAccesses(*(HANDLE *)&handle.nLength);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v11 = *(_QWORD *)&handle.nLength;
      *(_QWORD *)&handle.nLength = 0;
      *(_QWORD *)a2 = v11;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&handle);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x212,
        (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\settingsmanager\\registrysettings\\registrysettings.cpp",
        (const char *)(unsigned int)v9,
        v13);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&handle);
      RegDeleteKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\TabletTip\\1.7", 0, 0);
      return v10;
    }
  }
}

```

## disassembly

```asm
0x180098a38  mov     r11, rsp
0x180098a3b  mov     [r11+18h], rbx
0x180098a3f  mov     [r11+8], rcx
0x180098a43  push    rdi; unsigned int *
0x180098a44  sub     rsp, 40h
0x180098a48  mov     rbx, rdx
0x180098a4b  mov     qword ptr [rdx], 0
0x180098a52  mov     dword ptr [rsp+48h+arg_0], 0
0x180098a5a  mov     qword ptr [r11+10h], 0
0x180098a62  lea     rax, [r11+8]
0x180098a66  mov     [r11-10h], rax
0x180098a6a  lea     rax, [r11+10h]
0x180098a6e  mov     [r11-18h], rax
0x180098a72  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\TabletTip\\1.7"
0x180098a79  call    ?RegCreateKeyExW@RegHelpers@@YAJPEAUHKEY__@@PEB_WPEA_WKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; RegHelpers::RegCreateKeyExW(HKEY__ *,wchar_t const *,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180098a7e  test    eax, eax
0x180098a80  jz      short loc_180098ABE
0x180098a82  mov     rcx, [rsp+48h]; this
0x180098a87  mov     r9d, eax; char *
0x180098a8a  mov     edx, 210h; void *
0x180098a8f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180098a94  mov     ebx, eax
0x180098a96  lea     rcx, [rsp+48h+handle]
0x180098a9b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098aa0  xor     r9d, r9d; Reserved
0x180098aa3  xor     r8d, r8d; samDesired
0x180098aa6  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\TabletTip\\1.7"
0x180098aad  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180098ab4  call    cs:__imp_RegDeleteKeyExW
0x180098aba  mov     eax, ebx
0x180098abc  jmp     short loc_180098B32
0x180098abe  mov     rcx, [rsp+48h+handle]; handle
0x180098ac3  call    WindowsInternal__TextInputSettings__SettingsManager__EnsureAppContainerAccesses
0x180098ac8  mov     edi, eax
0x180098aca  test    eax, eax
0x180098acc  jns     short loc_180098B0F
0x180098ace  mov     rcx, [rsp+48h]; this
0x180098ad3  mov     r9d, eax; char *
0x180098ad6  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\sharedlibs\\se"...
0x180098add  mov     edx, 212h; void *
0x180098ae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098ae7  lea     rcx, [rsp+48h+handle]
0x180098aec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098af1  xor     r9d, r9d; Reserved
0x180098af4  xor     r8d, r8d; samDesired
0x180098af7  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\TabletTip\\1.7"
0x180098afe  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180098b05  call    cs:__imp_RegDeleteKeyExW
0x180098b0b  mov     eax, edi
0x180098b0d  jmp     short loc_180098B32
0x180098b0f  mov     rax, [rsp+48h+handle]
0x180098b14  mov     [rsp+48h+handle], 0
0x180098b1d  mov     [rbx], rax
0x180098b20  lea     rcx, [rsp+48h+handle]
0x180098b25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098b2a  xor     eax, eax
0x180098b2c  jmp     short loc_180098B32
0x180098b2e  mov     eax, dword ptr [rsp+48h+arg_0]
0x180098b32  mov     rbx, [rsp+48h+arg_10]
0x180098b37  add     rsp, 40h
0x180098b3b  pop     rdi
0x180098b3c  retn
```
