# ServicePackageSuspendedNotificationImpl(ushort const *,ulong,ushort const *,ulong,_GUID const * const)

- ea: `0x180063534`
- end: `0x1800637bd`
- name: `?ServicePackageSuspendedNotificationImpl@@YAJPEBGK0KQEBU_GUID@@@Z`
- size: `649`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, const struct _GUID *const)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180063410`
- `0x180084350`

## callees

- `0x180004738`
- `0x180012dc0`
- `0x180013b50`
- `0x180017740`
- `0x18002bc9c`
- `0x1800397ac`
- `0x18003b69c`
- `0x180042188`
- `0x180046f88`
- `0x180055750`
- `0x180055bac`
- `0x1800593bc`
- `0x180063534`
- `0x18006ad98`
- `0x180075e60`
- `0x18008e1f4`
- `0x1800909f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800635c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180063718`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800635c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180063718`

## string_xrefs

- `0x180063604`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800637ab`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800635eb`: `ServicePackageSuspendedNotificationImpl PsmKey:%s, sid:%s`
- `0x1800635f7`: `ServicePackageSuspendedNotificationImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ServicePackageSuspendedNotificationImpl(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        const struct _GUID *const a5)
{
  unsigned int v10; // esi
  ULONGLONG TickCount64; // r15
  const WCHAR *v12; // rcx
  unsigned __int16 **v13; // rcx
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rcx
  const unsigned __int16 *v16; // rcx
  const unsigned __int16 *v17; // rax
  const WCHAR *v18; // rdx
  const char *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  const WCHAR *v23; // rax
  wil *v24; // rcx
  int Format; // [rsp+20h] [rbp-C8h]
  unsigned int v26; // [rsp+40h] [rbp-A8h] BYREF
  ULONGLONG v27; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-98h] BYREF
  const WCHAR *v29; // [rsp+58h] [rbp-90h] BYREF
  unsigned __int16 *Src[3]; // [rsp+60h] [rbp-88h] BYREF
  unsigned __int64 v31; // [rsp+78h] [rbp-70h]
  _BYTE v32[16]; // [rsp+80h] [rbp-68h] BYREF
  __int64 v33; // [rsp+90h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  ProcessReference(v28);
  if ( !a1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9ED,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)0x80004003LL,
      Format);
  GetPackageFullNameFromPsmKey(Src);
  if ( SkipForAppCompat((const WCHAR *)Src) )
  {
    ContentIdString::~ContentIdString((ContentIdString *)Src);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v28);
    return 0;
  }
  else
  {
    v10 = 0;
    TickCount64 = GetTickCount64();
    v27 = TickCount64;
    v12 = a3;
    if ( !a3 )
      v12 = &LocaleName;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x9F2u,
      "ServicePackageSuspendedNotificationImpl",
      (wchar_t *)L"ServicePackageSuspendedNotificationImpl PsmKey:%s, sid:%s",
      a1,
      v12);
    try
    {
      GetAppSessionIds(v32, a4, a5);
      if ( v33 )
      {
        v13 = Src;
        if ( v31 > 7 )
          v13 = (unsigned __int16 **)Src[0];
        SetLicenseAppSessions(v13, a2, a3, v32);
      }
      v14 = (const unsigned __int16 *)Src;
      if ( v31 > 7 )
        v14 = Src[0];
      RemovePendingRequest(a1, v14, a2, a3);
      v15 = (const unsigned __int16 *)Src;
      if ( v31 > 7 )
        v15 = Src[0];
      UnleaseAllPackages(v15, a2, a3);
      v16 = (const unsigned __int16 *)Src;
      if ( v31 > 7 )
        v16 = Src[0];
      RemoveFromTrialStateMap(v16, a2, a3);
      if ( v31 > 7 )
      {
        v17 = Src[0];
        v18 = Src[0];
      }
      else
      {
        v17 = (const unsigned __int16 *)Src;
        v18 = (const WCHAR *)Src;
      }
      DropLicense(a1, v18, a2, a3, v17);
      ContentIdString::~ContentIdString((ContentIdString *)v32);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xA07,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        v19);
      v26 = wil::ResultFromCaughtException(v24);
      v10 = v26;
      TickCount64 = v27;
    }
    if ( (unsigned int)dword_1800F11D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
    {
      v27 = GetTickCount64() - TickCount64;
      v26 = v10;
      v23 = (const WCHAR *)Src;
      if ( v31 > 7 )
        v23 = Src[0];
      v29 = v23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v20,
        (unsigned __int8 *)&word_1800D714E,
        v21,
        v22,
        &v29,
        (__int64)&v26,
        (__int64)&v27);
    }
    ContentIdString::~ContentIdString((ContentIdString *)Src);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v28);
    return v10;
  }
}

```

## disassembly

```asm
0x180063534  push    rbx
0x180063536  push    rsi
0x180063537  push    rdi
0x180063538  push    r12
0x18006353a  push    r13
0x18006353c  push    r14
0x18006353e  push    r15
0x180063540  sub     rsp, 0B0h
0x180063547  mov     rax, cs:__security_cookie
0x18006354e  xor     rax, rsp
0x180063551  mov     [rsp+0E8h+var_48], rax
0x180063559  mov     r12d, r9d
0x18006355c  mov     rbx, r8
0x18006355f  mov     edi, edx
0x180063561  mov     r14, rcx
0x180063564  mov     r13, [rsp+0E8h+arg_20]
0x18006356c  lea     rcx, [rsp+0E8h+var_98]
0x180063571  call    ?ProcessReference@@YA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; ProcessReference(void)
0x180063576  nop
0x180063577  mov     rcx, [rsp+0E8h]; this
0x18006357f  test    r14, r14
0x180063582  jz      loc_1800637A5
0x180063588  mov     rdx, r14
0x18006358b  lea     rcx, [rsp+0E8h+Src]
0x180063590  call    ?GetPackageFullNameFromPsmKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetPackageFullNameFromPsmKey(ushort const *)
0x180063595  nop
0x180063596  lea     rcx, [rsp+0E8h+Src]
0x18006359b  call    ?SkipForAppCompat@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SkipForAppCompat(std::wstring const &)
0x1800635a0  test    al, al
0x1800635a2  jz      short loc_1800635C0
0x1800635a4  lea     rcx, [rsp+0E8h+Src]; this
0x1800635a9  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800635ae  nop
0x1800635af  lea     rcx, [rsp+0E8h+var_98]
0x1800635b4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800635b9  xor     eax, eax
0x1800635bb  jmp     loc_180063782
0x1800635c0  xor     esi, esi
0x1800635c2  call    cs:__imp_GetTickCount64
0x1800635c8  mov     r15, rax
0x1800635cb  mov     [rsp+0E8h+var_A0], rax
0x1800635d0  lea     rax, LocaleName
0x1800635d7  mov     rcx, rbx
0x1800635da  test    rbx, rbx
0x1800635dd  cmovz   rcx, rax
0x1800635e1  mov     [rsp+0E8h+var_B8], rcx
0x1800635e6  mov     [rsp+0E8h+var_C0], r14
0x1800635eb  lea     rax, aServicepackage_1; "ServicePackageSuspendedNotificationImpl"...
0x1800635f2  mov     [rsp+0E8h+Format], rax; Format
0x1800635f7  lea     r9, aServicepackage_4; "ServicePackageSuspendedNotificationImpl"
0x1800635fe  mov     r8d, 9F2h; unsigned int
0x180063604  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006360b  lea     ecx, [rsi+3]; unsigned int
0x18006360e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180063613  nop
0x180063614  mov     r8, r13
0x180063617  mov     edx, r12d
0x18006361a  lea     rcx, [rsp+0E8h+var_68]
0x180063622  call    ?GetAppSessionIds@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEBU_GUID@@@Z; GetAppSessionIds(ulong,_GUID const * const)
0x180063627  nop
0x180063628  cmp     [rsp+0E8h+var_58], rsi
0x180063630  jz      short loc_180063655
0x180063632  lea     rcx, [rsp+0E8h+Src]
0x180063637  cmp     [rsp+0E8h+var_70], 7
0x18006363d  cmova   rcx, [rsp+0E8h+Src]
0x180063643  lea     r9, [rsp+0E8h+var_68]
0x18006364b  mov     r8, rbx
0x18006364e  mov     edx, edi
0x180063650  call    ?SetLicenseAppSessions@@YAXPEBGK0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SetLicenseAppSessions(ushort const *,ulong,ushort const *,std::wstring const &)
0x180063655  lea     rdx, [rsp+0E8h+Src]
0x18006365a  cmp     [rsp+0E8h+var_70], 7
0x180063660  cmova   rdx, [rsp+0E8h+Src]; Src
0x180063666  mov     r9, rbx; unsigned __int16 *
0x180063669  mov     r8d, edi; unsigned int
0x18006366c  mov     rcx, r14; unsigned __int16 *
0x18006366f  call    ?RemovePendingRequest@@YAXPEBG0K0@Z; RemovePendingRequest(ushort const *,ushort const *,ulong,ushort const *)
0x180063674  lea     rcx, [rsp+0E8h+Src]
0x180063679  cmp     [rsp+0E8h+var_70], 7
0x18006367f  cmova   rcx, [rsp+0E8h+Src]; unsigned __int16 *
0x180063685  mov     r8, rbx; unsigned __int16 *
0x180063688  mov     edx, edi; unsigned int
0x18006368a  call    ?UnleaseAllPackages@@YAXPEBGK0@Z; UnleaseAllPackages(ushort const *,ulong,ushort const *)
0x18006368f  lea     rcx, [rsp+0E8h+Src]
0x180063694  cmp     [rsp+0E8h+var_70], 7
0x18006369a  cmova   rcx, [rsp+0E8h+Src]; unsigned __int16 *
0x1800636a0  mov     r8, rbx; unsigned __int16 *
0x1800636a3  mov     edx, edi; unsigned int
0x1800636a5  call    ?RemoveFromTrialStateMap@@YAXPEBGK0@Z; RemoveFromTrialStateMap(ushort const *,ulong,ushort const *)
0x1800636aa  cmp     [rsp+0E8h+var_70], 7
0x1800636b0  ja      short loc_1800636BE
0x1800636b2  lea     rax, [rsp+0E8h+Src]
0x1800636b7  lea     rdx, [rsp+0E8h+Src]
0x1800636bc  jmp     short loc_1800636C6
0x1800636be  mov     rax, [rsp+0E8h+Src]
0x1800636c3  mov     rdx, rax; lpString1
0x1800636c6  mov     [rsp+0E8h+Format], rax; unsigned __int16 *
0x1800636cb  mov     r9, rbx; unsigned __int16 *
0x1800636ce  mov     r8d, edi; unsigned int
0x1800636d1  mov     rcx, r14; unsigned __int16 *
0x1800636d4  call    ?DropLicense@@YAXPEBG0K00@Z; DropLicense(ushort const *,ushort const *,ulong,ushort const *,ushort const *)
0x1800636d9  nop
0x1800636da  lea     rcx, [rsp+0E8h+var_68]; this
0x1800636e2  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800636e7  nop
0x1800636e8  jmp     short loc_1800636F3
0x1800636ea  mov     esi, [rsp+0E8h+var_A8]
0x1800636ee  mov     r15, [rsp+0E8h+var_A0]
0x1800636f3  mov     eax, cs:dword_1800F11D0
0x1800636f9  cmp     eax, 5
0x1800636fc  jbe     short loc_18006376B
0x1800636fe  mov     rdx, 200000000000h
0x180063708  lea     rcx, dword_1800F11D0
0x18006370f  call    _tlgKeywordOn
0x180063714  test    al, al
0x180063716  jz      short loc_18006376B
0x180063718  call    cs:__imp_GetTickCount64
0x18006371e  sub     rax, r15
0x180063721  mov     [rsp+0E8h+var_A0], rax
0x180063726  mov     [rsp+0E8h+var_A8], esi
0x18006372a  lea     rax, [rsp+0E8h+Src]
0x18006372f  cmp     [rsp+0E8h+var_70], 7
0x180063735  cmova   rax, [rsp+0E8h+Src]
0x18006373b  mov     [rsp+0E8h+var_90], rax
0x180063740  lea     rax, [rsp+0E8h+var_A0]
0x180063745  mov     [rsp+0E8h+var_B8], rax
0x18006374a  lea     rax, [rsp+0E8h+var_A8]
0x18006374f  mov     [rsp+0E8h+var_C0], rax
0x180063754  lea     rax, [rsp+0E8h+var_90]
0x180063759  mov     [rsp+0E8h+Format], rax
0x18006375e  lea     rdx, word_1800D714E
0x180063765  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18006376a  nop
0x18006376b  lea     rcx, [rsp+0E8h+Src]; this
0x180063770  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180063775  nop
0x180063776  lea     rcx, [rsp+0E8h+var_98]
0x18006377b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180063780  mov     eax, esi
0x180063782  mov     rcx, [rsp+0E8h+var_48]
0x18006378a  xor     rcx, rsp; StackCookie
0x18006378d  call    __security_check_cookie
0x180063792  add     rsp, 0B0h
0x180063799  pop     r15
0x18006379b  pop     r14
0x18006379d  pop     r13
0x18006379f  pop     r12
0x1800637a1  pop     rdi
0x1800637a2  pop     rsi
0x1800637a3  pop     rbx
0x1800637a4  retn
0x1800637a5  mov     r9d, 80004003h; char *
0x1800637ab  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800637b2  mov     edx, 9EDh; void *
0x1800637b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
