# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::IsAppInForeground(void)

- ea: `0x18006fbb0`
- end: `0x18006fe1d`
- name: `?IsAppInForeground@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA_NXZ`
- size: `621`
- prototype: `bool __fastcall(Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006874c`

## callees

- `0x1800094c0`
- `0x18001d00c`
- `0x1800210d4`
- `0x18002392c`
- `0x180029408`
- `0x18002f240`
- `0x18003cde0`
- `0x180045f78`
- `0x18006fbb0`
- `0x1800a04b0`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006fcac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006fcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fd17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fd4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fd4b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006fd09`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006fd09`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x18006fcc4`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x18006fcc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006fc93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006fc93`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x18006fc1d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x18006fc1d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006fc4d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006fc4d`

## string_xrefs

- `0x18006fc8c`: `Windows.Internal.CapabilityAccess.Foreground.AppForegroundHelper`
- `0x18006fc27`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::IsAppInForeground(
        Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *this)
{
  __int64 v2; // rax
  int v3; // eax
  int v4; // eax
  __int64 v5; // rbx
  int ActivationFactoryAsUser; // eax
  char *v7; // rbx
  unsigned __int16 **v8; // r8
  signed int LastError; // eax
  signed int ProcessAppId; // edi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING); // rbx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v16; // rcx
  unsigned __int16 *v17; // [rsp+20h] [rbp-48h] BYREF
  __int64 v18; // [rsp+28h] [rbp-40h] BYREF
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
  }
  v19 = 0;
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 232);
  v3 = UMgrQueryUserContextFromSid(v2, &v19);
  if ( v3 >= 0
    || (wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA3A,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)(unsigned int)v3,
          (int)v17),
        v4 = UMgrQueryUserContext(*((_QWORD *)this + 56), &v19),
        v4 >= 0) )
  {
    v5 = v19;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA3D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
      (const char *)(unsigned int)v4,
      (int)v17);
    v5 = 0;
    v19 = 0;
  }
  v18 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Foreground.AppForegroundHelper",
         0x40u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactoryAsUser = RoGetActivationFactoryAsUser(string, v5, &GUID_6301710b_9e49_4d27_acbe_01a8370c4796, &v18);
  if ( ActivationFactoryAsUser < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA4A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
      (const char *)(unsigned int)ActivationFactoryAsUser,
      (int)v17);
  v17 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v17,
    0);
  v17 = 0;
  v7 = (char *)OpenProcess(0x1000u, 0, *((_DWORD *)this + 12));
  if ( v7 )
    goto LABEL_17;
  LastError = GetLastError();
  ProcessAppId = LastError;
  if ( LastError > 0 )
    ProcessAppId = (unsigned __int16)LastError | 0x80070000;
  if ( ProcessAppId >= 0 )
  {
LABEL_17:
    ProcessAppId = CallerIdentity::GetProcessAppId(v7, &v17, v8);
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v7);
  }
  if ( ProcessAppId < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA4D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
      (const char *)(unsigned int)ProcessAppId,
      (int)v17);
  v11 = v18;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v18 + 48LL);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&string, v17);
  v13 = v12(v11, string);
  if ( v13 )
  {
    if ( v13 != -2147024891 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA5A,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)v13,
        (int)v17);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
    v16 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return 0;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18006fbb0  push    rbp
0x18006fbb2  push    rbx
0x18006fbb3  push    rdi
0x18006fbb4  push    r14
0x18006fbb6  mov     rbp, rsp
0x18006fbb9  sub     rsp, 68h
0x18006fbbd  mov     rax, cs:__security_cookie
0x18006fbc4  xor     rax, rsp
0x18006fbc7  mov     [rbp+var_10], rax
0x18006fbcb  mov     rdi, rcx
0x18006fbce  lea     rax, WPP_GLOBAL_Control
0x18006fbd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fbdc  cmp     rcx, rax
0x18006fbdf  jz      short loc_18006FC02
0x18006fbe1  test    byte ptr [rcx+1Ch], 1
0x18006fbe5  jz      short loc_18006FC02
0x18006fbe7  cmp     byte ptr [rcx+19h], 5
0x18006fbeb  jb      short loc_18006FC02
0x18006fbed  mov     edx, 28h ; '('
0x18006fbf2  lea     r8, WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids
0x18006fbf9  mov     rcx, [rcx+10h]
0x18006fbfd  call    WPP_SF_
0x18006fc02  mov     [rbp+var_38], 0
0x18006fc0a  lea     rcx, [rdi+0E8h]
0x18006fc11  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006fc16  lea     rdx, [rbp+var_38]
0x18006fc1a  mov     rcx, rax
0x18006fc1d  call    cs:__imp_UMgrQueryUserContextFromSid
0x18006fc23  mov     rcx, [rbp+20h]; this
0x18006fc27  lea     r14, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006fc2e  test    eax, eax
0x18006fc30  jns     short loc_18006FC73
0x18006fc32  mov     r9d, eax; char *
0x18006fc35  mov     r8, r14; unsigned int
0x18006fc38  mov     edx, 0A3Ah; void *
0x18006fc3d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006fc42  lea     rdx, [rbp+var_38]
0x18006fc46  mov     rcx, [rdi+1C0h]
0x18006fc4d  call    cs:__imp_UMgrQueryUserContext
0x18006fc53  mov     rcx, [rbp+20h]; this
0x18006fc57  test    eax, eax
0x18006fc59  jns     short loc_18006FC73
0x18006fc5b  mov     r9d, eax; char *
0x18006fc5e  mov     r8, r14; unsigned int
0x18006fc61  mov     edx, 0A3Dh; void *
0x18006fc66  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006fc6b  xor     ebx, ebx
0x18006fc6d  mov     [rbp+var_38], rbx
0x18006fc71  jmp     short loc_18006FC77
0x18006fc73  mov     rbx, [rbp+var_38]
0x18006fc77  mov     [rbp+var_40], 0
0x18006fc7f  lea     r9, [rbp+string]; string
0x18006fc83  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18006fc87  mov     edx, 40h ; '@'; length
0x18006fc8c  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Foreground_AppForegroundHelper@@3QBGB; "Windows.Internal.CapabilityAccess.Foreg"...
0x18006fc93  call    cs:__imp_WindowsCreateStringReference
0x18006fc99  test    eax, eax
0x18006fc9b  jns     short loc_18006FCB2
0x18006fc9d  xor     r9d, r9d; lpArguments
0x18006fca0  xor     r8d, r8d; nNumberOfArguments
0x18006fca3  lea     edx, [r9+1]; dwExceptionFlags
0x18006fca7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006fcac  call    cs:__imp_RaiseException
0x18006fcb2  lea     r9, [rbp+var_40]
0x18006fcb6  lea     r8, _GUID_6301710b_9e49_4d27_acbe_01a8370c4796
0x18006fcbd  mov     rdx, rbx
0x18006fcc0  mov     rcx, [rbp+string]
0x18006fcc4  call    cs:__imp_RoGetActivationFactoryAsUser
0x18006fcca  mov     rcx, [rbp+20h]; this
0x18006fcce  test    eax, eax
0x18006fcd0  jns     short loc_18006FCE3
0x18006fcd2  mov     r9d, eax; char *
0x18006fcd5  mov     r8, r14; unsigned int
0x18006fcd8  mov     edx, 0A4Ah; void *
0x18006fcdd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fce3  mov     [rbp+var_48], 0
0x18006fceb  xor     edx, edx
0x18006fced  lea     rcx, [rbp+var_48]
0x18006fcf1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006fcf6  mov     [rbp+var_48], 0
0x18006fcfe  mov     r8d, [rdi+30h]; dwProcessId
0x18006fd02  xor     edx, edx; bInheritHandle
0x18006fd04  mov     ecx, 1000h; dwDesiredAccess
0x18006fd09  call    cs:__imp_OpenProcess
0x18006fd0f  mov     rbx, rax
0x18006fd12  test    rax, rax
0x18006fd15  jnz     short loc_18006FD30
0x18006fd17  call    cs:__imp_GetLastError
0x18006fd1d  mov     edi, eax
0x18006fd1f  test    eax, eax
0x18006fd21  jle     short loc_18006FD2C
0x18006fd23  movzx   edi, ax
0x18006fd26  or      edi, 80070000h
0x18006fd2c  test    edi, edi
0x18006fd2e  js      short loc_18006FD51
0x18006fd30  lea     rdx, [rbp+var_48]; void *
0x18006fd34  mov     rcx, rbx; ProcessHandle
0x18006fd37  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x18006fd3c  mov     edi, eax
0x18006fd3e  lea     rax, [rbx-1]
0x18006fd42  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006fd46  ja      short loc_18006FD51
0x18006fd48  mov     rcx, rbx; hObject
0x18006fd4b  call    cs:__imp_CloseHandle
0x18006fd51  mov     rcx, [rbp+20h]; this
0x18006fd55  test    edi, edi
0x18006fd57  jns     short loc_18006FD6A
0x18006fd59  mov     r9d, edi; char *
0x18006fd5c  mov     r8, r14; unsigned int
0x18006fd5f  mov     edx, 0A4Dh; void *
0x18006fd64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006fd6a  mov     rdi, [rbp+var_40]
0x18006fd6e  mov     rax, [rdi]
0x18006fd71  mov     rbx, [rax+30h]
0x18006fd75  mov     rdx, [rbp+var_48]; unsigned __int16 *
0x18006fd79  lea     rcx, [rbp+string]; this
0x18006fd7d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18006fd82  mov     rdx, [rbp+string]
0x18006fd86  mov     rcx, rdi
0x18006fd89  mov     rax, rbx
0x18006fd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd91  test    eax, eax
0x18006fd93  jnz     short loc_18006FDD5
0x18006fd95  lea     rcx, [rbp+var_48]
0x18006fd99  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006fd9e  nop
0x18006fd9f  mov     rcx, [rbp+var_40]
0x18006fda3  test    rcx, rcx
0x18006fda6  jz      short loc_18006FDBD
0x18006fda8  mov     [rbp+var_40], 0
0x18006fdb0  mov     rdx, [rcx]
0x18006fdb3  mov     rax, [rdx+10h]
0x18006fdb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fdbc  nop
0x18006fdbd  mov     al, 1
0x18006fdbf  mov     rcx, [rbp+var_10]
0x18006fdc3  xor     rcx, rsp; StackCookie
0x18006fdc6  call    __security_check_cookie
0x18006fdcb  add     rsp, 68h
0x18006fdcf  pop     r14
0x18006fdd1  pop     rdi
0x18006fdd2  pop     rbx
0x18006fdd3  pop     rbp
0x18006fdd4  retn
0x18006fdd5  cmp     eax, 80070005h
0x18006fdda  jnz     short loc_18006FE08
0x18006fddc  lea     rcx, [rbp+var_48]
0x18006fde0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006fde5  nop
0x18006fde6  mov     rcx, [rbp+var_40]
0x18006fdea  test    rcx, rcx
0x18006fded  jz      short loc_18006FE04
0x18006fdef  mov     [rbp+var_40], 0
0x18006fdf7  mov     rax, [rcx]
0x18006fdfa  mov     rax, [rax+10h]
0x18006fdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe03  nop
0x18006fe04  xor     al, al
0x18006fe06  jmp     short loc_18006FDBF
0x18006fe08  mov     rcx, [rbp+20h]; this
0x18006fe0c  mov     r9d, eax; char *
0x18006fe0f  mov     r8, r14; unsigned int
0x18006fe12  mov     edx, 0A5Ah; void *
0x18006fe17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
