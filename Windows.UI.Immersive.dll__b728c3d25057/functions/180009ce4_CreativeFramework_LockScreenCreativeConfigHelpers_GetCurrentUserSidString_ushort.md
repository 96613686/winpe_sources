# CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)

- ea: `0x180009ce4`
- end: `0x180009ee5`
- name: `?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z`
- size: `513`
- prototype: `__int64 __fastcall(CreativeFramework::LockScreenCreativeConfigHelpers *__hidden this, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009f0c`
- `0x18001a530`
- `0x1800b5a30`

## callees

- `0x180009ce4`
- `0x180009eec`
- `0x18000a910`
- `0x18000d2b8`
- `0x18001a3d0`
- `0x180034c6c`
- `0x180034db4`
- `0x180050ba0`
- `0x1800b9bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009d6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009d7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009d6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009d7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009d3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009df7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009d3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009df7`

## string_xrefs

- `0x180009d4f`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x180009dbc`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x180009e08`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x180009e5a`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x180009e38`: `LoggedOnUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        unsigned __int16 **a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int v6; // eax
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  BYTE *v10; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-50h]
  unsigned int phkResulta; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  HKEY v15; // [rsp+38h] [rbp-38h] BYREF
  BYTE *v16; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h]
  __int64 v18; // [rsp+50h] [rbp-20h]
  WCHAR SubKey[8]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  *(_QWORD *)this = 0;
  hKey = 0;
  v15 = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         9u,
         &v15);
  if ( !v3 )
  {
    v5 = StringCchPrintfW(SubKey, 8u, L"%d", NtCurrentPeb()->SessionId);
    v4 = v5;
    if ( v5 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v6 = RegOpenKeyExW(v15, SubKey, 0, 1u, &hKey);
      if ( v6 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x64,
               (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
               (const char *)v6,
               phkResulta);
      }
      else
      {
        v16 = 0;
        v17 = 0;
        v18 = 0;
        v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
               &v16,
               hKey,
               L"LoggedOnUserSID");
        v4 = v7;
        if ( v7 >= 0 )
        {
          v10 = v16;
          if ( v16 )
          {
            v16 = 0;
            v18 = 0;
            v17 = 0;
            *(_QWORD *)this = v10;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
            v4 = 0;
            goto LABEL_14;
          }
          v4 = -2147024882;
          v8 = 2147942414LL;
          v9 = 104;
        }
        else
        {
          v8 = (unsigned int)v7;
          v9 = 103;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
          (const char *)v8,
          phkResulta);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)(unsigned int)v5,
        phkResult);
    }
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
    return v4;
  }
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x60,
         (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
         (const char *)v3,
         phkResult);
  if ( v15 )
    RegCloseKey(v15);
  return v4;
}

```

## disassembly

```asm
0x180009ce4  mov     [rsp-8+arg_8], rbx
0x180009ce9  mov     [rsp-8+arg_10], rdi
0x180009cee  push    rbp
0x180009cef  mov     rbp, rsp
0x180009cf2  sub     rsp, 70h
0x180009cf6  mov     rax, cs:__security_cookie
0x180009cfd  xor     rax, rsp
0x180009d00  mov     [rbp+var_8], rax
0x180009d04  mov     rdi, rcx
0x180009d07  mov     qword ptr [rcx], 0
0x180009d0e  mov     [rbp+hKey], 0
0x180009d16  mov     [rbp+var_38], 0
0x180009d1e  lea     rax, [rbp+var_38]
0x180009d22  mov     qword ptr [rsp+70h+phkResult], rax; int
0x180009d27  mov     r9d, 9; samDesired
0x180009d2d  xor     r8d, r8d; ulOptions
0x180009d30  lea     rdx, ?c_sessionDataKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009d37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009d3e  call    cs:__imp_RegOpenKeyExW
0x180009d44  test    eax, eax
0x180009d46  jz      short loc_180009D8A
0x180009d48  mov     rcx, [rbp+8]; this
0x180009d4c  mov     r9d, eax; char *
0x180009d4f  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x180009d56  mov     edx, 60h ; '`'; void *
0x180009d5b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009d60  mov     ebx, eax
0x180009d62  mov     rcx, [rbp+hKey]; hKey
0x180009d66  test    rcx, rcx
0x180009d69  jz      short loc_180009D72
0x180009d6b  call    cs:__imp_RegCloseKey
0x180009d71  nop
0x180009d72  mov     rcx, [rbp+var_38]; hKey
0x180009d76  test    rcx, rcx
0x180009d79  jz      loc_180009EC5
0x180009d7f  call    cs:__imp_RegCloseKey
0x180009d85  jmp     loc_180009EC5
0x180009d8a  mov     r9, gs:60h
0x180009d93  mov     r9d, [r9+2C0h]
0x180009d9a  lea     r8, aD; "%d"
0x180009da1  mov     edx, 8; unsigned __int64
0x180009da6  lea     rcx, [rbp+SubKey]; unsigned __int16 *
0x180009daa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009daf  mov     ebx, eax
0x180009db1  test    eax, eax
0x180009db3  jns     short loc_180009DD2
0x180009db5  mov     rcx, [rbp+8]; this
0x180009db9  mov     r9d, eax; char *
0x180009dbc  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x180009dc3  mov     edx, 63h ; 'c'; void *
0x180009dc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dcd  jmp     loc_180009EB2
0x180009dd2  xor     edx, edx
0x180009dd4  lea     rcx, [rbp+hKey]
0x180009dd8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180009ddd  lea     rax, [rbp+hKey]
0x180009de1  mov     qword ptr [rsp+70h+phkResult], rax; int
0x180009de6  mov     r9d, 1; samDesired
0x180009dec  xor     r8d, r8d; ulOptions
0x180009def  lea     rdx, [rbp+SubKey]; lpSubKey
0x180009df3  mov     rcx, [rbp+var_38]; hKey
0x180009df7  call    cs:__imp_RegOpenKeyExW
0x180009dfd  test    eax, eax
0x180009dff  jz      short loc_180009E20
0x180009e01  mov     rcx, [rbp+8]; this
0x180009e05  mov     r9d, eax; char *
0x180009e08  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x180009e0f  mov     edx, 64h ; 'd'; void *
0x180009e14  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009e19  mov     ebx, eax
0x180009e1b  jmp     loc_180009EB2
0x180009e20  mov     [rbp+var_30], 0
0x180009e28  mov     [rbp+var_28], 0
0x180009e30  mov     [rbp+var_20], 0
0x180009e38  lea     r8, ?c_loggedOnUserSid@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "LoggedOnUserSID"
0x180009e3f  mov     rdx, [rbp+hKey]
0x180009e43  lea     rcx, [rbp+var_30]
0x180009e47  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180009e4c  mov     ebx, eax
0x180009e4e  test    eax, eax
0x180009e50  jns     short loc_180009E76
0x180009e52  mov     r9d, eax; char *
0x180009e55  mov     edx, 67h ; 'g'; void *
0x180009e5a  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x180009e61  mov     rcx, [rbp+8]; this
0x180009e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e6a  nop
0x180009e6b  lea     rcx, [rbp+var_30]
0x180009e6f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009e74  jmp     short loc_180009EB2
0x180009e76  mov     rax, [rbp+var_30]
0x180009e7a  test    rax, rax
0x180009e7d  jnz     short loc_180009E8C
0x180009e7f  mov     ebx, 8007000Eh
0x180009e84  mov     r9d, ebx
0x180009e87  lea     edx, [rax+68h]
0x180009e8a  jmp     short loc_180009E5A
0x180009e8c  mov     [rbp+var_30], 0
0x180009e94  mov     [rbp+var_20], 0
0x180009e9c  mov     [rbp+var_28], 0
0x180009ea4  mov     [rdi], rax
0x180009ea7  lea     rcx, [rbp+var_30]
0x180009eab  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009eb0  xor     ebx, ebx
0x180009eb2  lea     rcx, [rbp+hKey]
0x180009eb6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009ebb  nop
0x180009ebc  lea     rcx, [rbp+var_38]
0x180009ec0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009ec5  mov     eax, ebx
0x180009ec7  mov     rcx, [rbp+var_8]
0x180009ecb  xor     rcx, rsp; StackCookie
0x180009ece  call    __security_check_cookie
0x180009ed3  lea     r11, [rsp+70h+var_s0]
0x180009ed8  mov     rbx, [r11+18h]
0x180009edc  mov     rdi, [r11+20h]
0x180009ee0  mov     rsp, r11
0x180009ee3  pop     rbp
0x180009ee4  retn
```
