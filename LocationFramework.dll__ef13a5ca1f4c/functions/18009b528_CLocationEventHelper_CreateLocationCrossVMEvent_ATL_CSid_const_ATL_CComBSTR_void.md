# CLocationEventHelper::CreateLocationCrossVMEvent(ATL::CSid const &,ATL::CComBSTR &,void * *)

- ea: `0x18009b528`
- end: `0x18009b8cf`
- name: `?CreateLocationCrossVMEvent@CLocationEventHelper@@SAJAEBVCSid@ATL@@AEAVCComBSTR@3@PEAPEAX@Z`
- size: `935`
- prototype: `__int64 __fastcall(const struct ATL::CSid *, struct ATL::CComBSTR *, void **)`
- caller_count: `3`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800170b8`
- `0x1800d9600`
- `0x1800f93ec`

## callees

- `0x180016e30`
- `0x180016e8c`
- `0x1800178e0`
- `0x180017a6c`
- `0x180018228`
- `0x180018308`
- `0x1800187c0`
- `0x180018dc4`
- `0x18001e170`
- `0x18001e4dc`
- `0x18001eb88`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x180050c00`
- `0x180054f9c`
- `0x18009b528`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800ac108`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b564`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b685`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b6b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b89d`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b564`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b685`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b6b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b89d`
- `ntdll!NtCreateCrossVmEvent` at `0x18009b814`
- `ntdll!NtCreateCrossVmEvent` at `0x18009b814`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009b637`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009b637`
- `ext-ms-win-containers-policymanagercli-l1-1-0!CpmcGetContainerIdForUser` at `0x18009b7ac`
- `ext-ms-win-containers-policymanagercli-l1-1-0!CpmcGetContainerIdForUser` at `0x18009b7ac`

## string_xrefs

- `0x18009b787`: `CLocationEventHelper::CreateLocationCrossVMEvent`
- `0x18009b78e`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationEventHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CLocationEventHelper::CreateLocationCrossVMEvent(const struct ATL::CSid *a1, BSTR *a2, void **a3)
{
  HRESULT v6; // edi
  __int64 v8; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  signed int ContainerIdForUser; // eax
  unsigned int v12; // r8d
  unsigned __int8 v13; // r9
  bool v14; // r8
  int v15; // eax
  void *v16; // rax
  wil::details *v17; // [rsp+28h] [rbp-D8h]
  BSTR v18; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  void *v23; // [rsp+70h] [rbp-90h] BYREF
  void **v24; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v25; // [rsp+80h] [rbp-80h]
  void **v26; // [rsp+88h] [rbp-78h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v30; // [rsp+B8h] [rbp-48h]
  _QWORD v31[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v32[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v33; // [rsp+E8h] [rbp-18h]
  __int64 v34; // [rsp+F8h] [rbp-8h]
  __int64 v35; // [rsp+100h] [rbp+0h]
  GUID pguid; // [rsp+108h] [rbp+8h] BYREF
  GUID v37; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v38[128]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+1F8h] [rbp+F8h]

  SysFreeString(*a2);
  *a2 = 0;
  *a3 = 0;
  v18 = 0;
  pguid = 0;
  v26 = &ATL::CAccessToken::`vftable';
  v27 = 0;
  v28 = 0;
  memset_0(v38, 0, 0x78u);
  ATL::CSid::CSid((ATL::CSid *)v38);
  v24 = &ATL::CSecurityDesc::`vftable';
  v25 = 0;
  v32[1] = 0;
  v32[2] = 0x200000000LL;
  v32[0] = &ATL::CDacl::`vftable';
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v31[0] = &ATL::CSecurityDesc::`vftable';
  v31[1] = 0;
  v29 = 0u;
  v30 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v6 = CoCreateGuid(&pguid);
  if ( v6 < 0 )
  {
    v31[0] = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v31);
    ATL::CDacl::~CDacl((ATL::CDacl *)v32);
    v24 = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v24);
    ATL::CSid::~CSid((ATL::CSid *)v38);
    v26 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&v26);
    SysFreeString(0);
    return (unsigned int)v6;
  }
  v8 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &pguid);
  ATL::CComBSTR::operator=(&v18, v8);
  SysFreeString(bstrString);
  if ( !ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&v26, 8u) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_18;
  }
  if ( ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)&v26, (__int64)v38) )
  {
    ATL::CSecurityDesc::SetOwner((PSECURITY_DESCRIPTOR *)&v24, (const struct ATL::CSid *)v38);
    if ( ATL::CSid::IsValid(a1) )
      ATL::CDacl::AddAllowedAce((ATL::CDacl *)v32, a1, v12, v13);
    ATL::CSecurityDesc::SetDacl((ATL::CSecurityDesc *)&v24, (const struct ATL::CDacl *)v32, v12);
    ATL::CSecurityAttributes::Set((ATL::CSecurityAttributes *)&v29, (const struct ATL::CSecurityDesc *)&v24, v14);
    v37 = GUID_NULL;
    if ( !(unsigned __int8)IsCpmcGetContainerIdForUserPresent() )
    {
      v10 = -2147467263;
      LODWORD(v17) = -2147467263;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationEventHelper.h",
        "CLocationEventHelper::CreateLocationCrossVMEvent",
        "!(wil::verify_bool(IsCpmcGetContainerIdForUserPresent()))",
        v17,
        (int)v18);
      goto LABEL_18;
    }
    ContainerIdForUser = CpmcGetContainerIdForUser((char *)a1 + 8, &v37);
    if ( ContainerIdForUser >= 0 )
    {
      LODWORD(v20) = 48;
      *((_QWORD *)&v20 + 1) = 0;
      DWORD2(v21) = 0;
      *(_QWORD *)&v21 = 0;
      v22 = v25;
      v23 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v23,
        0);
      v15 = NtCreateCrossVmEvent(&v23, 2031619, &v20, 0, &pguid, &v37, v18);
      if ( v15 >= 0 )
      {
        v16 = v23;
        v23 = 0;
        *a3 = v16;
        ATL::CComBSTR::operator=(a2, &v18);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
        v10 = 0;
      }
      else
      {
        v10 = v15 | 0x10000000;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
      }
      goto LABEL_18;
    }
  }
  else
  {
    ContainerIdForUser = GetLastError();
    if ( ContainerIdForUser > 0 )
      ContainerIdForUser = (unsigned __int16)ContainerIdForUser | 0x80070000;
  }
  v10 = ContainerIdForUser;
LABEL_18:
  v31[0] = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v31);
  ATL::CDacl::~CDacl((ATL::CDacl *)v32);
  v24 = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v24);
  ATL::CSid::~CSid((ATL::CSid *)v38);
  v26 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v26);
  SysFreeString(v18);
  return v10;
}

```

## disassembly

```asm
0x18009b528  mov     [rsp-8+arg_18], rbx
0x18009b52d  push    rbp
0x18009b52e  push    rsi
0x18009b52f  push    rdi
0x18009b530  push    r12
0x18009b532  push    r13
0x18009b534  push    r14
0x18009b536  push    r15
0x18009b538  lea     rbp, [rsp-0C0h]
0x18009b540  sub     rsp, 1C0h
0x18009b547  mov     rax, cs:__security_cookie
0x18009b54e  xor     rax, rsp
0x18009b551  mov     [rbp+0F0h+var_40], rax
0x18009b558  mov     r14, r8
0x18009b55b  mov     rsi, rdx
0x18009b55e  mov     rbx, rcx
0x18009b561  mov     rcx, [rdx]; bstrString
0x18009b564  call    cs:__imp_SysFreeString
0x18009b56a  xor     r15d, r15d
0x18009b56d  mov     [rsi], r15
0x18009b570  mov     [r14], r15
0x18009b573  mov     [rsp+1F0h+var_1C0], r15; int
0x18009b578  xorps   xmm0, xmm0
0x18009b57b  movups  xmmword ptr [rbp+0F0h+pguid.Data1], xmm0
0x18009b57f  xorps   xmm1, xmm1
0x18009b582  movups  [rbp+0F0h+var_168], xmm1
0x18009b586  movups  [rbp+0F0h+var_158], xmm1
0x18009b58a  lea     r13, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18009b591  mov     qword ptr [rbp+0F0h+var_168], r13
0x18009b595  movdqu  [rbp+0F0h+var_168+8], xmm0
0x18009b59a  mov     qword ptr [rbp+0F0h+var_158+8], r15
0x18009b59e  xor     edx, edx; Val
0x18009b5a0  lea     r8d, [r15+78h]; Size
0x18009b5a4  lea     rcx, [rbp+0F0h+var_C0]; void *
0x18009b5a8  call    memset_0
0x18009b5ad  lea     rcx, [rbp+0F0h+var_C0]; this
0x18009b5b1  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x18009b5b6  nop
0x18009b5b7  xorps   xmm0, xmm0
0x18009b5ba  movups  [rsp+1F0h+var_178], xmm0
0x18009b5bf  lea     r12, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x18009b5c6  mov     qword ptr [rsp+1F0h+var_178], r12
0x18009b5cb  mov     qword ptr [rbp+0F0h+var_178+8], r15
0x18009b5cf  xor     eax, eax
0x18009b5d1  movups  [rbp+0F0h+var_120], xmm0
0x18009b5d5  movups  [rbp+0F0h+var_110], xmm0
0x18009b5d9  movups  [rbp+0F0h+var_100], xmm0
0x18009b5dd  mov     [rbp+0F0h+var_F0], rax
0x18009b5e1  mov     qword ptr [rbp+0F0h+var_120+8], r15
0x18009b5e5  mov     byte ptr [rbp+0F0h+var_110], r15b
0x18009b5e9  mov     dword ptr [rbp+0F0h+var_110+4], 2
0x18009b5f0  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x18009b5f7  mov     qword ptr [rbp+0F0h+var_120], rax
0x18009b5fb  movdqu  [rbp+0F0h+var_110+8], xmm0
0x18009b600  mov     qword ptr [rbp+0F0h+var_100+8], r15
0x18009b604  mov     dword ptr [rbp+0F0h+var_F0], r15d
0x18009b608  movups  [rbp+0F0h+var_148], xmm0
0x18009b60c  movups  [rbp+0F0h+var_138], xmm0
0x18009b610  mov     qword ptr [rbp+0F0h+var_138+8], r12
0x18009b614  mov     [rbp+0F0h+var_128], r15
0x18009b618  mov     dword ptr [rbp+0F0h+var_148], r15d
0x18009b61c  mov     qword ptr [rbp+0F0h+var_148+8], r15
0x18009b620  mov     dword ptr [rbp+0F0h+var_138], r15d
0x18009b624  movups  [rsp+1F0h+var_1B0], xmm0
0x18009b629  movups  [rsp+1F0h+var_1A0], xmm0
0x18009b62e  movups  [rsp+1F0h+var_190], xmm0
0x18009b633  lea     rcx, [rbp+0F0h+pguid]; pguid
0x18009b637  call    cs:__imp_CoCreateGuid
0x18009b63d  mov     edi, eax
0x18009b63f  test    eax, eax
0x18009b641  jns     short loc_18009B692
0x18009b643  mov     qword ptr [rbp+0F0h+var_138+8], r12
0x18009b647  lea     rcx, [rbp+0F0h+var_138+8]; this
0x18009b64b  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x18009b650  nop
0x18009b651  lea     rcx, [rbp+0F0h+var_120]; this
0x18009b655  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x18009b65a  nop
0x18009b65b  mov     qword ptr [rsp+1F0h+var_178], r12
0x18009b660  lea     rcx, [rsp+1F0h+var_178]; this
0x18009b665  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x18009b66a  nop
0x18009b66b  lea     rcx, [rbp+0F0h+var_C0]; this
0x18009b66f  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18009b674  nop
0x18009b675  mov     qword ptr [rbp+0F0h+var_168], r13
0x18009b679  lea     rcx, [rbp+0F0h+var_168]; this
0x18009b67d  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18009b682  nop
0x18009b683  xor     ecx, ecx; bstrString
0x18009b685  call    cs:__imp_SysFreeString
0x18009b68b  mov     eax, edi
0x18009b68d  jmp     loc_18009B8A5
0x18009b692  lea     rdx, [rbp+0F0h+pguid]; struct _GUID *
0x18009b696  lea     rcx, [rsp+1F0h+bstrString]; this
0x18009b69b  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x18009b6a0  nop
0x18009b6a1  mov     rdx, rax
0x18009b6a4  lea     rcx, [rsp+1F0h+var_1C0]
0x18009b6a9  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18009b6ae  nop
0x18009b6af  mov     rcx, [rsp+1F0h+bstrString]; bstrString
0x18009b6b4  call    cs:__imp_SysFreeString
0x18009b6ba  mov     edx, 8; unsigned int
0x18009b6bf  lea     rcx, [rbp+0F0h+var_168]; this
0x18009b6c3  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x18009b6c8  test    al, al
0x18009b6ca  jnz     short loc_18009B6EA
0x18009b6cc  call    cs:__imp_GetLastError
0x18009b6d2  mov     ebx, eax
0x18009b6d4  test    eax, eax
0x18009b6d6  jle     loc_18009B858
0x18009b6dc  movzx   ebx, ax
0x18009b6df  or      ebx, 80070000h
0x18009b6e5  jmp     loc_18009B858
0x18009b6ea  lea     rdx, [rbp+0F0h+var_C0]
0x18009b6ee  lea     rcx, [rbp+0F0h+var_168]
0x18009b6f2  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x18009b6f7  test    al, al
0x18009b6f9  jnz     short loc_18009B714
0x18009b6fb  call    cs:__imp_GetLastError
0x18009b701  test    eax, eax
0x18009b703  jle     short loc_18009B70D
0x18009b705  movzx   eax, ax
0x18009b708  or      eax, 80070000h
0x18009b70d  mov     ebx, eax
0x18009b70f  jmp     loc_18009B858
0x18009b714  lea     rdx, [rbp+0F0h+var_C0]; struct ATL::CSid *
0x18009b718  lea     rcx, [rsp+1F0h+var_178]; this
0x18009b71d  call    ?SetOwner@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z; ATL::CSecurityDesc::SetOwner(ATL::CSid const &,bool)
0x18009b722  mov     rcx, rbx; this
0x18009b725  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18009b72a  test    al, al
0x18009b72c  jz      short loc_18009B73A
0x18009b72e  mov     rdx, rbx; struct ATL::CSid *
0x18009b731  lea     rcx, [rbp+0F0h+var_120]; this
0x18009b735  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18009b73a  lea     rdx, [rbp+0F0h+var_120]; struct ATL::CDacl *
0x18009b73e  lea     rcx, [rsp+1F0h+var_178]; this
0x18009b743  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x18009b748  lea     rdx, [rsp+1F0h+var_178]; struct ATL::CSecurityDesc *
0x18009b74d  lea     rcx, [rbp+0F0h+var_148]; this
0x18009b751  call    ?Set@CSecurityAttributes@ATL@@QEAAXAEBVCSecurityDesc@2@_N@Z; ATL::CSecurityAttributes::Set(ATL::CSecurityDesc const &,bool)
0x18009b756  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009b75d  movdqu  xmmword ptr [rbp+0F0h+var_D8.Data1], xmm0
0x18009b762  call    IsCpmcGetContainerIdForUserPresent
0x18009b767  test    al, al
0x18009b769  jnz     short loc_18009B7A4
0x18009b76b  mov     rcx, [rbp+0F8h]; this
0x18009b772  mov     ebx, 80004001h
0x18009b777  mov     dword ptr [rsp+1F0h+var_1C8], ebx; wil::details *
0x18009b77b  lea     rax, aWilVerifyBoolI; "!(wil::verify_bool(IsCpmcGetContainerId"...
0x18009b782  mov     [rsp+1F0h+var_1D0], rax; char *
0x18009b787  lea     r9, aClocationevent_1; "CLocationEventHelper::CreateLocationCro"...
0x18009b78e  lea     r8, aOnecoreuapDriv; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18009b795  mov     edx, 9Bh; void *
0x18009b79a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009b79f  jmp     loc_18009B858
0x18009b7a4  lea     rcx, [rbx+8]
0x18009b7a8  lea     rdx, [rbp+0F0h+var_D8]
0x18009b7ac  call    cs:__imp_CpmcGetContainerIdForUser
0x18009b7b2  test    eax, eax
0x18009b7b4  js      loc_18009B70D
0x18009b7ba  mov     dword ptr [rsp+1F0h+var_1B0], 30h ; '0'
0x18009b7c2  mov     qword ptr [rsp+1F0h+var_1B0+8], r15
0x18009b7c7  mov     dword ptr [rsp+1F0h+var_1A0+8], r15d
0x18009b7cc  mov     qword ptr [rsp+1F0h+var_1A0], r15
0x18009b7d1  mov     qword ptr [rsp+1F0h+var_190+8], r15
0x18009b7d6  mov     rax, qword ptr [rbp+0F0h+var_178+8]
0x18009b7da  mov     qword ptr [rsp+1F0h+var_190], rax
0x18009b7df  mov     [rsp+1F0h+var_180], r15
0x18009b7e4  xor     edx, edx
0x18009b7e6  lea     rcx, [rsp+1F0h+var_180]
0x18009b7eb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009b7f0  lea     rax, [rbp+0F0h+var_D8]
0x18009b7f4  mov     [rsp+1F0h+var_1C8], rax
0x18009b7f9  lea     rax, [rbp+0F0h+pguid]
0x18009b7fd  mov     [rsp+1F0h+var_1D0], rax
0x18009b802  xor     r9d, r9d
0x18009b805  lea     r8, [rsp+1F0h+var_1B0]
0x18009b80a  mov     edx, 1F0003h
0x18009b80f  lea     rcx, [rsp+1F0h+var_180]
0x18009b814  call    cs:__imp_NtCreateCrossVmEvent
0x18009b81a  mov     ebx, eax
0x18009b81c  test    eax, eax
0x18009b81e  jns     short loc_18009B830
0x18009b820  bts     ebx, 1Ch
0x18009b824  lea     rcx, [rsp+1F0h+var_180]
0x18009b829  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009b82e  jmp     short loc_18009B858
0x18009b830  mov     rax, [rsp+1F0h+var_180]
0x18009b835  mov     [rsp+1F0h+var_180], r15
0x18009b83a  mov     [r14], rax
0x18009b83d  lea     rdx, [rsp+1F0h+var_1C0]
0x18009b842  mov     rcx, rsi
0x18009b845  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18009b84a  nop
0x18009b84b  lea     rcx, [rsp+1F0h+var_180]
0x18009b850  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009b855  mov     ebx, r15d
0x18009b858  mov     qword ptr [rbp+0F0h+var_138+8], r12
0x18009b85c  lea     rcx, [rbp+0F0h+var_138+8]; this
0x18009b860  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x18009b865  nop
0x18009b866  lea     rcx, [rbp+0F0h+var_120]; this
0x18009b86a  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x18009b86f  nop
0x18009b870  mov     qword ptr [rsp+1F0h+var_178], r12
0x18009b875  lea     rcx, [rsp+1F0h+var_178]; this
0x18009b87a  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x18009b87f  nop
0x18009b880  lea     rcx, [rbp+0F0h+var_C0]; this
0x18009b884  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18009b889  nop
0x18009b88a  mov     qword ptr [rbp+0F0h+var_168], r13
0x18009b88e  lea     rcx, [rbp+0F0h+var_168]; this
0x18009b892  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18009b897  nop
0x18009b898  mov     rcx, [rsp+1F0h+var_1C0]; bstrString
0x18009b89d  call    cs:__imp_SysFreeString
0x18009b8a3  mov     eax, ebx
0x18009b8a5  mov     rcx, [rbp+0F0h+var_40]
0x18009b8ac  xor     rcx, rsp; StackCookie
0x18009b8af  call    __security_check_cookie
0x18009b8b4  mov     rbx, [rsp+1F0h+arg_18]
0x18009b8bc  add     rsp, 1C0h
0x18009b8c3  pop     r15
0x18009b8c5  pop     r14
0x18009b8c7  pop     r13
0x18009b8c9  pop     r12
0x18009b8cb  pop     rdi
0x18009b8cc  pop     rsi
0x18009b8cd  pop     rbp
0x18009b8ce  retn
```
