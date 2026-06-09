# WindowsInternal::TextInputSettings::SettingsManager::EnsureAppContainerAccesses

- ea: `0x180098cc8`
- end: `0x180098f26`
- name: `WindowsInternal::TextInputSettings::SettingsManager::EnsureAppContainerAccesses`
- size: `606`
- prototype: `__int64 __fastcall(HANDLE handle)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180098a38`

## callees

- `0x18004aa2c`
- `0x18004aa50`
- `0x180098228`
- `0x180098248`
- `0x180098b70`
- `0x180098cc8`
- `0x18009a680`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098d1d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098d1d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098d36`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098d36`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180098ced`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180098ced`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180098da6`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180098da6`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180098ec6`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180098ec6`

## string_xrefs

- `0x180098cfb`: `mincore\textinput\dev\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`
- `0x180098d44`: `mincore\textinput\dev\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`
- `0x180098df6`: `mincore\textinput\dev\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`
- `0x180098e5e`: `mincore\textinput\dev\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`

## pseudocode

```c
__int64 __fastcall WindowsInternal::TextInputSettings::SettingsManager::EnsureAppContainerAccesses(HANDLE handle)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  const char *v4; // r9
  DWORD SecurityInfo; // eax
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // edi
  struct _ACL *v9; // rdx
  int v10; // eax
  struct _ACL *v11; // rax
  DWORD v12; // eax
  unsigned int v13; // r8d
  unsigned int ppsidGroup; // [rsp+20h] [rbp-40h]
  int ppsidGroupa; // [rsp+20h] [rbp-40h]
  int ppsidGroupb; // [rsp+20h] [rbp-40h]
  unsigned int ppsidGroupc; // [rsp+20h] [rbp-40h]
  PSID v19; // [rsp+40h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-18h] BYREF
  PACL OldAcl; // [rsp+50h] [rbp-10h] BYREF
  PSID Sid; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD cbSid; // [rsp+88h] [rbp+28h] BYREF
  PACL NewAcl; // [rsp+90h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+98h] [rbp+38h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(
         L"S-1-15-3-1024-1065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681",
         &Sid) )
  {
    cbSid = 68;
    v19 = LocalAlloc(0, 0x44u);
    if ( CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, v19, &cbSid) )
    {
      OldAcl = 0;
      ppSecurityDescriptor = 0;
      SecurityInfo = GetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, &OldAcl, 0, &ppSecurityDescriptor);
      if ( SecurityInfo )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x1EC,
                      v6,
                      (const char *)SecurityInfo,
                      ppsidGroup);
      }
      else
      {
        NewAcl = 0;
        v7 = WindowsInternal::TextInputSettings::SettingsManager::EnsureAccess(Sid, OldAcl, &NewAcl);
        v8 = v7;
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EF,
            (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\settingsmanager\\registrysettings\\registrysettings.cpp",
            (const char *)(unsigned int)v7,
            ppsidGroupa);
          wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&NewAcl);
          wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&ppSecurityDescriptor);
          wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&v19);
          LastError = v8;
          goto LABEL_23;
        }
        v9 = OldAcl;
        pDacl = 0;
        if ( NewAcl )
          v9 = NewAcl;
        v10 = WindowsInternal::TextInputSettings::SettingsManager::EnsureAccess(v19, v9, &pDacl);
        LastError = v10;
        if ( v10 >= 0 )
        {
          v11 = NewAcl;
          if ( !NewAcl && !pDacl )
            goto LABEL_22;
          if ( pDacl )
            v11 = pDacl;
          v12 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, v11, 0);
          if ( !v12 )
          {
LABEL_22:
            wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&pDacl);
            wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&NewAcl);
            wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&ppSecurityDescriptor);
            wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&v19);
            LastError = 0;
            goto LABEL_23;
          }
          LastError = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x1F6, v13, (const char *)v12, ppsidGroupc);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F2,
            (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\settingsmanager\\registrysettings\\registrysettings.cpp",
            (const char *)(unsigned int)v10,
            ppsidGroupb);
        }
        wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&pDacl);
        wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&NewAcl);
      }
      wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&ppSecurityDescriptor);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1E8,
                    (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\settingsmanager\\registrysettings\\registrysettings.cpp",
                    v4);
    }
    wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&v19);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1E3,
                  (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\settingsmanager\\registrysettings\\registrysettings.cpp",
                  v2);
  }
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  return LastError;
}

```

## disassembly

```asm
0x180098cc8  mov     [rsp-18h+arg_0], rbx
0x180098ccd  push    rbp
0x180098cce  push    rsi
0x180098ccf  push    rdi
0x180098cd0  mov     rbp, rsp
0x180098cd3  sub     rsp, 60h
0x180098cd7  mov     rsi, rcx
0x180098cda  mov     [rbp+Sid], 0
0x180098ce2  lea     rcx, StringSid; "S-1-15-3-1024-1065365936-1281604716-351"...
0x180098ce9  lea     rdx, [rbp+Sid]; Sid
0x180098ced  call    cs:__imp_ConvertStringSidToSidW
0x180098cf3  test    eax, eax
0x180098cf5  jnz     short loc_180098D13
0x180098cf7  mov     rcx, [rbp+18h]; this
0x180098cfb  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\sharedlibs\\se"...
0x180098d02  mov     edx, 1E3h; void *
0x180098d07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180098d0c  mov     ebx, eax
0x180098d0e  jmp     loc_180098F0B
0x180098d13  mov     edx, 44h ; 'D'; uBytes
0x180098d18  xor     ecx, ecx; uFlags
0x180098d1a  mov     [rbp+cbSid], edx
0x180098d1d  call    cs:__imp_LocalAlloc
0x180098d23  xor     edx, edx; DomainSid
0x180098d25  lea     r9, [rbp+cbSid]; cbSid
0x180098d29  mov     r8, rax; pSid
0x180098d2c  mov     [rbp+var_20], rax
0x180098d30  mov     rbx, rax
0x180098d33  lea     ecx, [rdx+54h]; WellKnownSidType
0x180098d36  call    cs:__imp_CreateWellKnownSid
0x180098d3c  test    eax, eax
0x180098d3e  jnz     short loc_180098D65
0x180098d40  mov     rcx, [rbp+18h]; this
0x180098d44  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\sharedlibs\\se"...
0x180098d4b  mov     edx, 1E8h; void *
0x180098d50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180098d55  mov     ebx, eax
0x180098d57  lea     rcx, [rbp+var_20]
0x180098d5b  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098d60  jmp     loc_180098F0B
0x180098d65  xor     r9d, r9d; ppsidOwner
0x180098d68  mov     [rbp+OldAcl], 0
0x180098d70  lea     rax, [rbp+arg_18]
0x180098d74  mov     [rbp+arg_18], 0
0x180098d7c  mov     [rsp+60h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180098d81  mov     rcx, rsi; handle
0x180098d84  lea     rax, [rbp+OldAcl]
0x180098d88  mov     [rsp+60h+ppSacl], 0; ppSacl
0x180098d91  lea     edx, [r9+4]; ObjectType
0x180098d95  mov     [rsp+60h+ppDacl], rax; ppDacl
0x180098d9a  mov     r8d, edx; SecurityInfo
0x180098d9d  mov     [rsp+60h+ppsidGroup], 0; unsigned int
0x180098da6  call    cs:__imp_GetSecurityInfo
0x180098dac  test    eax, eax
0x180098dae  jz      short loc_180098DCE
0x180098db0  mov     rcx, [rbp+18h]; this
0x180098db4  mov     r9d, eax; char *
0x180098db7  mov     edx, 1ECh; void *
0x180098dbc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180098dc1  mov     ebx, eax
0x180098dc3  lea     rcx, [rbp+arg_18]
0x180098dc7  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098dcc  jmp     short loc_180098D57
0x180098dce  mov     rdx, [rbp+OldAcl]; OldAcl
0x180098dd2  lea     rax, [rbp+NewAcl]
0x180098dd6  mov     rcx, [rbp+Sid]; pSid1
0x180098dda  mov     [rsp+60h+ppsidGroup], rax; int
0x180098ddf  mov     [rbp+NewAcl], 0
0x180098de7  call    WindowsInternal__TextInputSettings__SettingsManager__EnsureAccess
0x180098dec  mov     edi, eax
0x180098dee  test    eax, eax
0x180098df0  jns     short loc_180098E2C
0x180098df2  mov     rcx, [rbp+18h]; this
0x180098df6  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\sharedlibs\\se"...
0x180098dfd  mov     r9d, eax; char *
0x180098e00  mov     edx, 1EFh; void *
0x180098e05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098e0a  lea     rcx, [rbp+NewAcl]
0x180098e0e  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098e13  lea     rcx, [rbp+arg_18]
0x180098e17  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098e1c  lea     rcx, [rbp+var_20]
0x180098e20  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098e25  mov     ebx, edi
0x180098e27  jmp     loc_180098F0B
0x180098e2c  mov     rax, [rbp+NewAcl]
0x180098e30  mov     rcx, rbx; pSid1
0x180098e33  mov     rdx, [rbp+OldAcl]
0x180098e37  test    rax, rax
0x180098e3a  mov     [rbp+pDacl], 0
0x180098e42  cmovnz  rdx, rax; OldAcl
0x180098e46  lea     rax, [rbp+pDacl]
0x180098e4a  mov     [rsp+60h+ppsidGroup], rax; int
0x180098e4f  call    WindowsInternal__TextInputSettings__SettingsManager__EnsureAccess
0x180098e54  mov     ebx, eax
0x180098e56  test    eax, eax
0x180098e58  jns     short loc_180098E89
0x180098e5a  mov     rcx, [rbp+18h]; this
0x180098e5e  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\sharedlibs\\se"...
0x180098e65  mov     r9d, eax; char *
0x180098e68  mov     edx, 1F2h; void *
0x180098e6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098e72  lea     rcx, [rbp+pDacl]
0x180098e76  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098e7b  lea     rcx, [rbp+NewAcl]
0x180098e7f  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098e84  jmp     loc_180098DC3
0x180098e89  mov     rax, [rbp+NewAcl]
0x180098e8d  mov     rcx, [rbp+pDacl]
0x180098e91  test    rax, rax
0x180098e94  jnz     short loc_180098E9B
0x180098e96  test    rcx, rcx
0x180098e99  jz      short loc_180098EE5
0x180098e9b  test    rcx, rcx
0x180098e9e  mov     [rsp+60h+ppSacl], 0; pSacl
0x180098ea7  cmovnz  rax, rcx
0x180098eab  xor     r9d, r9d; psidOwner
0x180098eae  mov     [rsp+60h+ppDacl], rax; pDacl
0x180098eb3  mov     rcx, rsi; handle
0x180098eb6  mov     [rsp+60h+ppsidGroup], 0; unsigned int
0x180098ebf  lea     edx, [r9+4]; ObjectType
0x180098ec3  mov     r8d, edx; SecurityInfo
0x180098ec6  call    cs:__imp_SetSecurityInfo
0x180098ecc  test    eax, eax
0x180098ece  jz      short loc_180098EE5
0x180098ed0  mov     rcx, [rbp+18h]; this
0x180098ed4  mov     r9d, eax; char *
0x180098ed7  mov     edx, 1F6h; void *
0x180098edc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180098ee1  mov     ebx, eax
0x180098ee3  jmp     short loc_180098E72
0x180098ee5  lea     rcx, [rbp+pDacl]
0x180098ee9  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098eee  lea     rcx, [rbp+NewAcl]
0x180098ef2  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098ef7  lea     rcx, [rbp+arg_18]
0x180098efb  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098f00  lea     rcx, [rbp+var_20]
0x180098f04  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098f09  xor     ebx, ebx
0x180098f0b  lea     rcx, [rbp+Sid]
0x180098f0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180098f14  mov     eax, ebx
0x180098f16  mov     rbx, [rsp+60h+arg_0]
0x180098f1e  add     rsp, 60h
0x180098f22  pop     rdi
0x180098f23  pop     rsi
0x180098f24  pop     rbp
0x180098f25  retn
```
