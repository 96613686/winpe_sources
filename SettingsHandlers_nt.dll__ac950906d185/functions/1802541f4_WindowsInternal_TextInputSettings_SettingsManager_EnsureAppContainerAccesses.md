# WindowsInternal::TextInputSettings::SettingsManager::EnsureAppContainerAccesses

- ea: `0x1802541f4`
- end: `0x1802544a3`
- name: `WindowsInternal::TextInputSettings::SettingsManager::EnsureAppContainerAccesses`
- size: `687`
- prototype: `__int64 __fastcall(HANDLE handle)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180253f48`

## callees

- `0x180019a00`
- `0x180019a20`
- `0x180041004`
- `0x18007f7bc`
- `0x18013a4b0`
- `0x18022833c`
- `0x180254080`
- `0x1802541f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18025424f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18025424f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18025426e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18025426e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180254219`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180254219`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180254435`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180254435`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1802542ef`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1802542ef`

## string_xrefs

- `0x18025422d`: `shellcommondesktopbase\textinput\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`
- `0x180254282`: `shellcommondesktopbase\textinput\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`
- `0x180254303`: `shellcommondesktopbase\textinput\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`
- `0x18025435a`: `shellcommondesktopbase\textinput\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`
- `0x1802543cd`: `shellcommondesktopbase\textinput\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`
- `0x180254449`: `shellcommondesktopbase\textinput\sharedlibs\settingsmanager\registrysettings\registrysettings.cpp`

## pseudocode

```c
__int64 __fastcall WindowsInternal::TextInputSettings::SettingsManager::EnsureAppContainerAccesses(HANDLE handle)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  PSID v4; // rbx
  const char *v5; // r9
  DWORD SecurityInfo; // eax
  int v7; // eax
  unsigned int v8; // edi
  struct _ACL *v9; // rdx
  int v10; // eax
  struct _ACL *v11; // rax
  DWORD v12; // eax
  unsigned int ppsidGroup; // [rsp+20h] [rbp-40h]
  int ppsidGroupa; // [rsp+20h] [rbp-40h]
  int ppsidGroupb; // [rsp+20h] [rbp-40h]
  unsigned int ppsidGroupc; // [rsp+20h] [rbp-40h]
  PACL pDacl; // [rsp+40h] [rbp-20h] BYREF
  PSID v19; // [rsp+48h] [rbp-18h] BYREF
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
    v4 = v19;
    if ( CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, v19, &cbSid) )
    {
      OldAcl = 0;
      ppSecurityDescriptor = 0;
      wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(
        &ppSecurityDescriptor,
        0);
      SecurityInfo = GetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, &OldAcl, 0, &ppSecurityDescriptor);
      if ( SecurityInfo )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x1EC,
                      (unsigned int)"shellcommondesktopbase\\textinput\\sharedlibs\\settingsmanager\\registrysettings\\re"
                                    "gistrysettings.cpp",
                      (const char *)SecurityInfo,
                      ppsidGroup);
      }
      else
      {
        NewAcl = 0;
        wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(
          &NewAcl,
          0);
        v7 = WindowsInternal::TextInputSettings::SettingsManager::EnsureAccess(Sid, OldAcl, &NewAcl);
        v8 = v7;
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EF,
            (unsigned int)"shellcommondesktopbase\\textinput\\sharedlibs\\settingsmanager\\registrysettings\\registrysettings.cpp",
            (const char *)(unsigned int)v7,
            ppsidGroupa);
          wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&NewAcl);
          wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&ppSecurityDescriptor);
          wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&v19);
          LastError = v8;
          goto LABEL_23;
        }
        pDacl = 0;
        wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(
          &pDacl,
          0);
        v9 = OldAcl;
        if ( NewAcl )
          v9 = NewAcl;
        v10 = WindowsInternal::TextInputSettings::SettingsManager::EnsureAccess(v4, v9, &pDacl);
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
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x1F6,
                        (unsigned int)"shellcommondesktopbase\\textinput\\sharedlibs\\settingsmanager\\registrysettings\\"
                                      "registrysettings.cpp",
                        (const char *)v12,
                        ppsidGroupc);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F2,
            (unsigned int)"shellcommondesktopbase\\textinput\\sharedlibs\\settingsmanager\\registrysettings\\registrysettings.cpp",
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
                    (unsigned int)"shellcommondesktopbase\\textinput\\sharedlibs\\settingsmanager\\registrysettings\\regi"
                                  "strysettings.cpp",
                    v5);
    }
    wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&v19);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1E3,
                  (unsigned int)"shellcommondesktopbase\\textinput\\sharedlibs\\settingsmanager\\registrysettings\\registrysettings.cpp",
                  v2);
  }
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  return LastError;
}

```

## disassembly

```asm
0x1802541f4  mov     [rsp-18h+arg_0], rbx
0x1802541f9  push    rbp
0x1802541fa  push    rsi
0x1802541fb  push    rdi
0x1802541fc  mov     rbp, rsp
0x1802541ff  sub     rsp, 60h
0x180254203  mov     rsi, rcx
0x180254206  mov     [rbp+Sid], 0
0x18025420e  lea     rcx, StringSid; "S-1-15-3-1024-1065365936-1281604716-351"...
0x180254215  lea     rdx, [rbp+Sid]; Sid
0x180254219  call    cs:__imp_ConvertStringSidToSidW
0x180254220  nop     dword ptr [rax+rax+00h]
0x180254225  test    eax, eax
0x180254227  jnz     short loc_180254245
0x180254229  mov     rcx, [rbp+18h]; this
0x18025422d  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\textinput\\shar"...
0x180254234  mov     edx, 1E3h; void *
0x180254239  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18025423e  mov     ebx, eax
0x180254240  jmp     loc_180254487
0x180254245  mov     edx, 44h ; 'D'; uBytes
0x18025424a  xor     ecx, ecx; uFlags
0x18025424c  mov     [rbp+cbSid], edx
0x18025424f  call    cs:__imp_LocalAlloc
0x180254256  nop     dword ptr [rax+rax+00h]
0x18025425b  xor     edx, edx; DomainSid
0x18025425d  lea     r9, [rbp+cbSid]; cbSid
0x180254261  mov     r8, rax; pSid
0x180254264  mov     [rbp+var_18], rax
0x180254268  mov     rbx, rax
0x18025426b  lea     ecx, [rdx+54h]; WellKnownSidType
0x18025426e  call    cs:__imp_CreateWellKnownSid
0x180254275  nop     dword ptr [rax+rax+00h]
0x18025427a  test    eax, eax
0x18025427c  jnz     short loc_1802542A3
0x18025427e  mov     rcx, [rbp+18h]; this
0x180254282  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\textinput\\shar"...
0x180254289  mov     edx, 1E8h; void *
0x18025428e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180254293  mov     ebx, eax
0x180254295  lea     rcx, [rbp+var_18]
0x180254299  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x18025429e  jmp     loc_180254487
0x1802542a3  xor     edx, edx
0x1802542a5  mov     [rbp+OldAcl], 0
0x1802542ad  lea     rcx, [rbp+arg_18]
0x1802542b1  mov     [rbp+arg_18], 0
0x1802542b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x1802542be  xor     r9d, r9d; ppsidOwner
0x1802542c1  lea     rax, [rbp+arg_18]
0x1802542c5  mov     [rsp+60h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1802542ca  mov     rcx, rsi; handle
0x1802542cd  lea     rax, [rbp+OldAcl]
0x1802542d1  mov     [rsp+60h+ppSacl], 0; ppSacl
0x1802542da  mov     [rsp+60h+ppDacl], rax; ppDacl
0x1802542df  lea     edx, [r9+4]; ObjectType
0x1802542e3  mov     [rsp+60h+ppsidGroup], 0; unsigned int
0x1802542ec  mov     r8d, edx; SecurityInfo
0x1802542ef  call    cs:__imp_GetSecurityInfo
0x1802542f6  nop     dword ptr [rax+rax+00h]
0x1802542fb  test    eax, eax
0x1802542fd  jz      short loc_180254327
0x1802542ff  mov     rcx, [rbp+18h]; this
0x180254303  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\textinput\\shar"...
0x18025430a  mov     r9d, eax; char *
0x18025430d  mov     edx, 1ECh; void *
0x180254312  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180254317  mov     ebx, eax
0x180254319  lea     rcx, [rbp+arg_18]
0x18025431d  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180254322  jmp     loc_180254295
0x180254327  xor     edx, edx
0x180254329  mov     [rbp+NewAcl], 0
0x180254331  lea     rcx, [rbp+NewAcl]
0x180254335  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x18025433a  mov     rdx, [rbp+OldAcl]; OldAcl
0x18025433e  lea     rax, [rbp+NewAcl]
0x180254342  mov     rcx, [rbp+Sid]; pSid1
0x180254346  mov     [rsp+60h+ppsidGroup], rax; int
0x18025434b  call    WindowsInternal__TextInputSettings__SettingsManager__EnsureAccess
0x180254350  mov     edi, eax
0x180254352  test    eax, eax
0x180254354  jns     short loc_180254390
0x180254356  mov     rcx, [rbp+18h]; this
0x18025435a  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\textinput\\shar"...
0x180254361  mov     r9d, eax; char *
0x180254364  mov     edx, 1EFh; void *
0x180254369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025436e  lea     rcx, [rbp+NewAcl]
0x180254372  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180254377  lea     rcx, [rbp+arg_18]
0x18025437b  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180254380  lea     rcx, [rbp+var_18]
0x180254384  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180254389  mov     ebx, edi
0x18025438b  jmp     loc_180254487
0x180254390  xor     edx, edx
0x180254392  mov     [rbp+pDacl], 0
0x18025439a  lea     rcx, [rbp+pDacl]
0x18025439e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x1802543a3  mov     rax, [rbp+NewAcl]
0x1802543a7  mov     rcx, rbx; pSid1
0x1802543aa  mov     rdx, [rbp+OldAcl]
0x1802543ae  test    rax, rax
0x1802543b1  cmovnz  rdx, rax; OldAcl
0x1802543b5  lea     rax, [rbp+pDacl]
0x1802543b9  mov     [rsp+60h+ppsidGroup], rax; int
0x1802543be  call    WindowsInternal__TextInputSettings__SettingsManager__EnsureAccess
0x1802543c3  mov     ebx, eax
0x1802543c5  test    eax, eax
0x1802543c7  jns     short loc_1802543F8
0x1802543c9  mov     rcx, [rbp+18h]; this
0x1802543cd  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\textinput\\shar"...
0x1802543d4  mov     r9d, eax; char *
0x1802543d7  mov     edx, 1F2h; void *
0x1802543dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802543e1  lea     rcx, [rbp+pDacl]
0x1802543e5  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x1802543ea  lea     rcx, [rbp+NewAcl]
0x1802543ee  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x1802543f3  jmp     loc_180254319
0x1802543f8  mov     rax, [rbp+NewAcl]
0x1802543fc  mov     rcx, [rbp+pDacl]
0x180254400  test    rax, rax
0x180254403  jnz     short loc_18025440A
0x180254405  test    rcx, rcx
0x180254408  jz      short loc_180254461
0x18025440a  test    rcx, rcx
0x18025440d  mov     [rsp+60h+ppSacl], 0; pSacl
0x180254416  cmovnz  rax, rcx
0x18025441a  xor     r9d, r9d; psidOwner
0x18025441d  mov     [rsp+60h+ppDacl], rax; pDacl
0x180254422  mov     rcx, rsi; handle
0x180254425  mov     [rsp+60h+ppsidGroup], 0; unsigned int
0x18025442e  lea     edx, [r9+4]; ObjectType
0x180254432  mov     r8d, edx; SecurityInfo
0x180254435  call    cs:__imp_SetSecurityInfo
0x18025443c  nop     dword ptr [rax+rax+00h]
0x180254441  test    eax, eax
0x180254443  jz      short loc_180254461
0x180254445  mov     rcx, [rbp+18h]; this
0x180254449  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\textinput\\shar"...
0x180254450  mov     r9d, eax; char *
0x180254453  mov     edx, 1F6h; void *
0x180254458  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18025445d  mov     ebx, eax
0x18025445f  jmp     short loc_1802543E1
0x180254461  lea     rcx, [rbp+pDacl]
0x180254465  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x18025446a  lea     rcx, [rbp+NewAcl]
0x18025446e  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180254473  lea     rcx, [rbp+arg_18]
0x180254477  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x18025447c  lea     rcx, [rbp+var_18]
0x180254480  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180254485  xor     ebx, ebx
0x180254487  lea     rcx, [rbp+Sid]
0x18025448b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180254490  mov     eax, ebx
0x180254492  mov     rbx, [rsp+60h+arg_0]
0x18025449a  add     rsp, 60h
0x18025449e  pop     rdi
0x18025449f  pop     rsi
0x1802544a0  pop     rbp
0x1802544a1  retn
```
