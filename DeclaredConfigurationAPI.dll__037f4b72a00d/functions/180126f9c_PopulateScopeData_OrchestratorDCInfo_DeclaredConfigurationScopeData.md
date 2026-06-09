# PopulateScopeData(OrchestratorDCInfo,DeclaredConfigurationScopeData *)

- ea: `0x180126f9c`
- end: `0x180127137`
- name: `?PopulateScopeData@@YAJUOrchestratorDCInfo@@PEAUDeclaredConfigurationScopeData@@@Z`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180121ed0`

## callees

- `0x18000b9e0`
- `0x18001d090`
- `0x18004d158`
- `0x180058b3c`
- `0x18009a2e4`
- `0x180126f9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012700f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012706f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012700f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012706f`
- `OLEAUT32!__imp_SysAllocString` at `0x180126fd6`
- `OLEAUT32!__imp_SysAllocString` at `0x180127049`
- `OLEAUT32!__imp_SysAllocString` at `0x180127088`
- `OLEAUT32!__imp_SysAllocString` at `0x180126fd6`
- `OLEAUT32!__imp_SysAllocString` at `0x180127049`
- `OLEAUT32!__imp_SysAllocString` at `0x180127088`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012702a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012702a`

## string_xrefs

- `0x180127036`: `Failed DmGetActiveUserSid`
- `0x180127097`: `Out of memory allocating scopeData.m_pszUserSid`
- `0x1801270b0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\utils.cpp`
- `0x1801270f2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PopulateScopeData(OLECHAR *a1, __int64 a2)
{
  OLECHAR *v3; // rsi
  BSTR v4; // rax
  const char *v5; // rax
  __int64 v6; // rdx
  const OLECHAR *v7; // rbx
  const OLECHAR *v8; // rcx
  int ActiveUserSid; // edi
  BSTR v10; // rax
  const OLECHAR *v11; // rcx
  const char *v13; // [rsp+28h] [rbp-40h]
  OLECHAR *psz[2]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = a1;
  psz[1] = a1;
  psz[0] = 0;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(OLECHAR **)a1;
  v4 = SysAllocString(a1);
  *(_QWORD *)a2 = v4;
  if ( !v4 )
  {
    v5 = "Out of memory allocating scopeData.m_pszEnrollmentId";
    v6 = 13;
LABEL_21:
    ActiveUserSid = -2147024882;
    goto LABEL_22;
  }
  v7 = v3 + 16;
  if ( *((_QWORD *)v3 + 7) <= 7u )
    v8 = v3 + 16;
  else
    v8 = *(const OLECHAR **)v7;
  if ( !(unsigned int)_o__wcsicmp(v8, L"user") )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      psz,
      0);
    ActiveUserSid = DmGetActiveUserSid(psz);
    if ( ActiveUserSid < 0 )
    {
      v5 = "Failed DmGetActiveUserSid";
      v6 = 18;
LABEL_22:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\utils.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        (int)v5,
        v13);
      goto LABEL_23;
    }
    v10 = SysAllocString(psz[0]);
    *(_DWORD *)(a2 + 16) = 1;
    goto LABEL_19;
  }
  if ( *((_QWORD *)v3 + 7) <= 7u )
    v11 = v3 + 16;
  else
    v11 = *(const OLECHAR **)v7;
  if ( !(unsigned int)_o__wcsicmp(v11, L"device") )
  {
    ActiveUserSid = 0;
    if ( *((_QWORD *)v3 + 7) > 7u )
      v7 = *(const OLECHAR **)v7;
    v10 = SysAllocString(v7);
LABEL_19:
    *(_QWORD *)(a2 + 8) = v10;
    if ( v10 )
    {
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(psz);
      OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v3);
      return (unsigned int)ActiveUserSid;
    }
    v5 = "Out of memory allocating scopeData.m_pszUserSid";
    v6 = 33;
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x1C,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\utils.cpp",
    (const char *)0x80070057LL,
    (int)"info.userId is not user or device",
    v13);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(psz);
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v3);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180126f9c  mov     [rsp+arg_10], rbx
0x180126fa1  push    rsi
0x180126fa2  push    rdi
0x180126fa3  push    r14
0x180126fa5  sub     rsp, 50h
0x180126fa9  mov     rax, cs:__security_cookie
0x180126fb0  xor     rax, rsp
0x180126fb3  mov     [rsp+68h+var_28], rax
0x180126fb8  mov     r14, rdx
0x180126fbb  mov     rsi, rcx
0x180126fbe  mov     [rsp+68h+var_30], rcx
0x180126fc3  mov     [rsp+68h+psz], 0
0x180126fcc  cmp     qword ptr [rcx+18h], 7
0x180126fd1  jbe     short loc_180126FD6
0x180126fd3  mov     rcx, [rcx]; psz
0x180126fd6  call    cs:__imp_SysAllocString
0x180126fdc  mov     [r14], rax
0x180126fdf  test    rax, rax
0x180126fe2  jnz     short loc_180126FF5
0x180126fe4  lea     rax, aOutOfMemoryAll_0; "Out of memory allocating scopeData.m_ps"...
0x180126feb  mov     edx, 0Dh
0x180126ff0  jmp     loc_1801270A3
0x180126ff5  lea     rbx, [rsi+20h]
0x180126ff9  cmp     qword ptr [rbx+18h], 7
0x180126ffe  jbe     short loc_180127005
0x180127000  mov     rcx, [rbx]
0x180127003  jmp     short loc_180127008
0x180127005  mov     rcx, rbx
0x180127008  lea     rdx, aUser_0; "user"
0x18012700f  call    cs:__imp__o__wcsicmp
0x180127015  test    eax, eax
0x180127017  jnz     short loc_180127059
0x180127019  xor     edx, edx
0x18012701b  lea     rcx, [rsp+68h+psz]
0x180127020  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180127025  lea     rcx, [rsp+68h+psz]
0x18012702a  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180127030  mov     edi, eax
0x180127032  test    eax, eax
0x180127034  jns     short loc_180127044
0x180127036  lea     rax, aFailedDmgetact_0; "Failed DmGetActiveUserSid"
0x18012703d  mov     edx, 12h
0x180127042  jmp     short loc_1801270A8
0x180127044  mov     rcx, [rsp+68h+psz]; psz
0x180127049  call    cs:__imp_SysAllocString
0x18012704f  mov     dword ptr [r14+10h], 1
0x180127057  jmp     short loc_18012708E
0x180127059  cmp     qword ptr [rbx+18h], 7
0x18012705e  jbe     short loc_180127065
0x180127060  mov     rcx, [rbx]
0x180127063  jmp     short loc_180127068
0x180127065  mov     rcx, rbx
0x180127068  lea     rdx, aDevice_4; "device"
0x18012706f  call    cs:__imp__o__wcsicmp
0x180127075  test    eax, eax
0x180127077  jnz     short loc_1801270D9
0x180127079  xor     edi, edi
0x18012707b  cmp     qword ptr [rbx+18h], 7
0x180127080  jbe     short loc_180127085
0x180127082  mov     rbx, [rbx]
0x180127085  mov     rcx, rbx; psz
0x180127088  call    cs:__imp_SysAllocString
0x18012708e  mov     [r14+8], rax
0x180127092  test    rax, rax
0x180127095  jnz     short loc_1801270C2
0x180127097  lea     rax, aOutOfMemoryAll; "Out of memory allocating scopeData.m_ps"...
0x18012709e  mov     edx, 21h ; '!'; void *
0x1801270a3  mov     edi, 8007000Eh
0x1801270a8  mov     qword ptr [rsp+68h+var_48], rax; int
0x1801270ad  mov     r9d, edi; char *
0x1801270b0  lea     r8, aOnecoreuapAdmi_42; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1801270b7  mov     rcx, [rsp+68h]; this
0x1801270bc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801270c1  nop
0x1801270c2  lea     rcx, [rsp+68h+psz]
0x1801270c7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801270cc  nop
0x1801270cd  mov     rcx, rsi; this
0x1801270d0  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x1801270d5  mov     eax, edi
0x1801270d7  jmp     short loc_180127119
0x1801270d9  mov     rcx, [rsp+68h]; this
0x1801270de  lea     rax, aInfoUseridIsNo; "info.userId is not user or device"
0x1801270e5  mov     qword ptr [rsp+68h+var_48], rax; int
0x1801270ea  mov     ebx, 80070057h
0x1801270ef  mov     r9d, ebx; char *
0x1801270f2  lea     r8, aOnecoreuapAdmi_42; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1801270f9  mov     edx, 1Ch; void *
0x1801270fe  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180127103  nop
0x180127104  lea     rcx, [rsp+68h+psz]
0x180127109  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012710e  nop
0x18012710f  mov     rcx, rsi; this
0x180127112  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x180127117  mov     eax, ebx
0x180127119  mov     rcx, [rsp+68h+var_28]
0x18012711e  xor     rcx, rsp; StackCookie
0x180127121  call    __security_check_cookie
0x180127126  mov     rbx, [rsp+68h+arg_10]
0x18012712e  add     rsp, 50h
0x180127132  pop     r14
0x180127134  pop     rdi
0x180127135  pop     rsi
0x180127136  retn
```
