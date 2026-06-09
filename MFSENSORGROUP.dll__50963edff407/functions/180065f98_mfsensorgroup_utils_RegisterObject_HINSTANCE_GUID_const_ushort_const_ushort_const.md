# mfsensorgroup_utils::RegisterObject(HINSTANCE__ *,_GUID const &,ushort const *,ushort const *)

- ea: `0x180065f98`
- end: `0x1800661ce`
- name: `?RegisterObject@mfsensorgroup_utils@@YAJPEAUHINSTANCE__@@AEBU_GUID@@PEBG2@Z`
- size: `566`
- prototype: `__int64 __fastcall(mfsensorgroup_utils *__hidden this, HINSTANCE, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180065c10`

## callees

- `0x180005fa0`
- `0x180028d5c`
- `0x180028e5c`
- `0x180044f30`
- `0x180045900`
- `0x180065c38`
- `0x180065d74`
- `0x180065f98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800660a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800660a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800660ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800660ac`

## string_xrefs

- `0x18006605a`: `Sensor Group Class Factory (DllRegisterServer)`
- `0x18006614f`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall mfsensorgroup_utils::RegisterObject(
        mfsensorgroup_utils *this,
        HINSTANCE a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4)
{
  HMODULE v4; // rdi
  mfsensorgroup_utils *v5; // rcx
  unsigned __int16 *v6; // r8
  signed int v7; // ebx
  __int64 v8; // rdx
  int RegKeyAndStringValue; // eax
  __int64 v10; // rdx
  signed int LastError; // eax
  unsigned __int16 v13[4]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = g_hModule;
  hKey = 0;
  *(_QWORD *)v13 = 0;
  memset_0(Filename, 0, 0x208u);
  v15 = 0;
  if ( v4 )
  {
    RegKeyAndStringValue = mfsensorgroup_utils::CreateObjectKeyName(v5, Filename, v6, &v15);
    v7 = RegKeyAndStringValue;
    if ( RegKeyAndStringValue >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      RegKeyAndStringValue = mfsensorgroup_utils::CreateRegKeyAndStringValue(
                               HKEY_LOCAL_MACHINE,
                               Filename,
                               0,
                               L"Sensor Group Class Factory (DllRegisterServer)",
                               (unsigned __int16 *)&hKey);
      v7 = RegKeyAndStringValue;
      if ( RegKeyAndStringValue >= 0 )
      {
        if ( !GetModuleFileNameW(v4, Filename, 0x104u) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( v7 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_24;
            v8 = 28;
            goto LABEL_4;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          v13,
          0);
        RegKeyAndStringValue = mfsensorgroup_utils::CreateRegKeyAndStringValue(
                                 hKey,
                                 (const WCHAR *)&stru_180080E38,
                                 0,
                                 Filename,
                                 v13);
        v7 = RegKeyAndStringValue;
        if ( RegKeyAndStringValue >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            v13,
            0);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            v13,
            0);
          RegKeyAndStringValue = mfsensorgroup_utils::CreateRegKeyAndStringValue(
                                   hKey,
                                   (const WCHAR *)&stru_180080E38,
                                   L"ThreadingModel",
                                   L"Both",
                                   v13);
          v7 = RegKeyAndStringValue;
          if ( RegKeyAndStringValue >= 0 || !g_wppLevels )
            goto LABEL_24;
          v10 = 30;
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_24;
          v10 = 29;
        }
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_24;
        v10 = 27;
      }
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_24;
      v10 = 26;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids,
      0,
      RegKeyAndStringValue);
    goto LABEL_24;
  }
  v7 = -2147024809;
  if ( g_wppLevels )
  {
    v8 = 23;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids, 0, v7);
  }
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v13);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180065f98  mov     [rsp-8+arg_0], rbx
0x180065f9d  mov     [rsp-8+arg_8], rdi
0x180065fa2  push    rbp
0x180065fa3  lea     rbp, [rsp-170h]
0x180065fab  sub     rsp, 270h
0x180065fb2  mov     rax, cs:__security_cookie
0x180065fb9  xor     rax, rsp
0x180065fbc  mov     [rbp+170h+var_10], rax
0x180065fc3  mov     rdi, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModule
0x180065fca  lea     rcx, [rsp+270h+Filename]; void *
0x180065fcf  xor     edx, edx; Val
0x180065fd1  mov     [rsp+270h+hKey], 0
0x180065fda  mov     r8d, 208h; Size
0x180065fe0  mov     qword ptr [rsp+270h+var_240], 0
0x180065fe9  call    memset_0
0x180065fee  mov     [rsp+270h+var_230], 0
0x180065ff7  test    rdi, rdi
0x180065ffa  jnz     short loc_18006601A
0x180065ffc  mov     ebx, 80070057h
0x180066001  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066008  jb      loc_180066194
0x18006600e  lea     edx, [rdi+17h]
0x180066011  mov     dword ptr [rsp+270h+var_250], ebx
0x180066015  jmp     loc_18006617A
0x18006601a  lea     r9, [rsp+270h+var_230]; unsigned __int64
0x18006601f  lea     rdx, [rsp+270h+Filename]; struct _GUID *
0x180066024  call    ?CreateObjectKeyName@mfsensorgroup_utils@@YAJAEBU_GUID@@PEAG_KPEA_K@Z; mfsensorgroup_utils::CreateObjectKeyName(_GUID const &,ushort *,unsigned __int64,unsigned __int64 *)
0x180066029  mov     ebx, eax
0x18006602b  test    eax, eax
0x18006602d  jns     short loc_180066046
0x18006602f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066036  jb      loc_180066194
0x18006603c  mov     edx, 1Ah
0x180066041  jmp     loc_180066176
0x180066046  xor     edx, edx
0x180066048  lea     rcx, [rsp+270h+hKey]
0x18006604d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180066052  lea     rax, [rsp+270h+hKey]
0x180066057  xor     r8d, r8d; lpValueName
0x18006605a  lea     r9, aSensorGroupCla; "Sensor Group Class Factory (DllRegister"...
0x180066061  mov     [rsp+270h+var_250], rax; unsigned __int16 *
0x180066066  lea     rdx, [rsp+270h+Filename]; lpSubKey
0x18006606b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180066072  call    ?CreateRegKeyAndStringValue@mfsensorgroup_utils@@YAJPEAUHKEY__@@PEBG11PEAPEAU2@@Z; mfsensorgroup_utils::CreateRegKeyAndStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,HKEY__ * *)
0x180066077  mov     ebx, eax
0x180066079  test    eax, eax
0x18006607b  jns     short loc_180066094
0x18006607d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066084  jb      loc_180066194
0x18006608a  mov     edx, 1Bh
0x18006608f  jmp     loc_180066176
0x180066094  mov     r8d, 104h; nSize
0x18006609a  lea     rdx, [rsp+270h+Filename]; lpFilename
0x18006609f  mov     rcx, rdi; hModule
0x1800660a2  call    cs:__imp_GetModuleFileNameW
0x1800660a8  test    eax, eax
0x1800660aa  jnz     short loc_1800660DC
0x1800660ac  call    cs:__imp_GetLastError
0x1800660b2  mov     ebx, eax
0x1800660b4  test    eax, eax
0x1800660b6  jle     short loc_1800660C1
0x1800660b8  movzx   ebx, ax
0x1800660bb  or      ebx, 80070000h
0x1800660c1  test    ebx, ebx
0x1800660c3  jns     short loc_1800660DC
0x1800660c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800660cc  jb      loc_180066194
0x1800660d2  mov     edx, 1Ch
0x1800660d7  jmp     loc_180066011
0x1800660dc  xor     edx, edx
0x1800660de  lea     rcx, [rsp+270h+var_240]
0x1800660e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800660e8  mov     rcx, [rsp+270h+hKey]; hKey
0x1800660ed  lea     rax, [rsp+270h+var_240]
0x1800660f2  lea     r9, [rsp+270h+Filename]; unsigned __int16 *
0x1800660f7  mov     [rsp+270h+var_250], rax; unsigned __int16 *
0x1800660fc  xor     r8d, r8d; lpValueName
0x1800660ff  lea     rdx, stru_180080E38; lpSubKey
0x180066106  call    ?CreateRegKeyAndStringValue@mfsensorgroup_utils@@YAJPEAUHKEY__@@PEBG11PEAPEAU2@@Z; mfsensorgroup_utils::CreateRegKeyAndStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,HKEY__ * *)
0x18006610b  mov     ebx, eax
0x18006610d  test    eax, eax
0x18006610f  jns     short loc_180066121
0x180066111  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066118  jb      short loc_180066194
0x18006611a  mov     edx, 1Dh
0x18006611f  jmp     short loc_180066176
0x180066121  xor     edx, edx
0x180066123  lea     rcx, [rsp+270h+var_240]
0x180066128  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006612d  xor     edx, edx
0x18006612f  lea     rcx, [rsp+270h+var_240]
0x180066134  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180066139  mov     rcx, [rsp+270h+hKey]; hKey
0x18006613e  lea     rax, [rsp+270h+var_240]
0x180066143  lea     r9, aBoth; "Both"
0x18006614a  mov     [rsp+270h+var_250], rax; unsigned __int16 *
0x18006614f  lea     r8, aThreadingmodel; "ThreadingModel"
0x180066156  lea     rdx, stru_180080E38; lpSubKey
0x18006615d  call    ?CreateRegKeyAndStringValue@mfsensorgroup_utils@@YAJPEAUHKEY__@@PEBG11PEAPEAU2@@Z; mfsensorgroup_utils::CreateRegKeyAndStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,HKEY__ * *)
0x180066162  mov     ebx, eax
0x180066164  test    eax, eax
0x180066166  jns     short loc_180066194
0x180066168  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006616f  jb      short loc_180066194
0x180066171  mov     edx, 1Eh
0x180066176  mov     dword ptr [rsp+270h+var_250], eax
0x18006617a  mov     rcx, cs:WPP_GLOBAL_Control
0x180066181  lea     r8, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids
0x180066188  xor     r9d, r9d
0x18006618b  mov     rcx, [rcx+10h]
0x18006618f  call    WPP_SF_qD
0x180066194  lea     rcx, [rsp+270h+var_240]
0x180066199  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006619e  lea     rcx, [rsp+270h+hKey]
0x1800661a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800661a8  mov     eax, ebx
0x1800661aa  mov     rcx, [rbp+170h+var_10]
0x1800661b1  xor     rcx, rsp; StackCookie
0x1800661b4  call    __security_check_cookie
0x1800661b9  lea     r11, [rsp+270h+var_s0]
0x1800661c1  mov     rbx, [r11+10h]
0x1800661c5  mov     rdi, [r11+18h]
0x1800661c9  mov     rsp, r11
0x1800661cc  pop     rbp
0x1800661cd  retn
```
