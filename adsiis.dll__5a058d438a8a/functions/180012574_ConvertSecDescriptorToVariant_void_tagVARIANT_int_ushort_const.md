# ConvertSecDescriptorToVariant(void *,tagVARIANT *,int,ushort const *)

- ea: `0x180012574`
- end: `0x180012975`
- name: `?ConvertSecDescriptorToVariant@@YAJPEAXPEAUtagVARIANT@@HPEBG@Z`
- size: `1025`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, VARIANTARG *pvarg, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180018518`

## callees

- `0x18001201c`
- `0x180012040`
- `0x180012084`
- `0x180012574`
- `0x18001297c`
- `0x1800189bc`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180012797`
- `ole32!CoCreateInstance` at `0x180012797`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180012739`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180012739`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180012705`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180012705`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800126ba`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800126ba`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180012673`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180012673`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18001264f`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18001264f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800127ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800127d8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800127ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800127d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001262c`
- `OLEAUT32!__imp_SysFreeString` at `0x180012634`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180012949`
- `OLEAUT32!__imp_SysFreeString` at `0x180012952`
- `OLEAUT32!__imp_SysFreeString` at `0x18001262c`
- `OLEAUT32!__imp_SysFreeString` at `0x180012634`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180012949`
- `OLEAUT32!__imp_SysFreeString` at `0x180012952`
- `OLEAUT32!__imp_VariantInit` at `0x180012607`
- `OLEAUT32!__imp_VariantInit` at `0x180012607`
- `OLEAUT32!__imp_VariantClear` at `0x180012905`
- `OLEAUT32!__imp_VariantClear` at `0x18001290f`
- `OLEAUT32!__imp_VariantClear` at `0x180012905`
- `OLEAUT32!__imp_VariantClear` at `0x18001290f`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18001291d`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18001292b`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18001291d`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18001292b`

## pseudocode

```c
__int64 __fastcall ConvertSecDescriptorToVariant(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        VARIANTARG *pvarg,
        int a3,
        const unsigned __int16 *a4)
{
  OLECHAR *v5; // rbx
  WCHAR *v7; // r15
  WCHAR *v8; // r14
  OLECHAR *v9; // rdi
  HRESULT LastError; // esi
  PSID v12; // rcx
  PSID v13; // rcx
  ACL *v14; // rcx
  OLECHAR *v15; // rbx
  OLECHAR *v16; // rbx
  bool v17; // zf
  struct tagVARIANT *v18; // rcx
  LONGLONG v19; // rax
  LPVOID ppv; // [rsp+38h] [rbp-79h] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp-71h] BYREF
  DWORD dwRevision; // [rsp+48h] [rbp-69h] BYREF
  OLECHAR *v23; // [rsp+50h] [rbp-61h] BYREF
  BOOL bOwnerDefaulted; // [rsp+58h] [rbp-59h] BYREF
  BOOL bGroupDefaulted; // [rsp+5Ch] [rbp-55h] BYREF
  BOOL bDaclDefaulted; // [rsp+60h] [rbp-51h] BYREF
  BOOL bDaclPresent; // [rsp+64h] [rbp-4Dh] BYREF
  BOOL bSaclDefaulted; // [rsp+68h] [rbp-49h] BYREF
  BOOL bSaclPresent; // [rsp+6Ch] [rbp-45h] BYREF
  PSID pOwner; // [rsp+70h] [rbp-41h] BYREF
  PSID pGroup; // [rsp+78h] [rbp-39h] BYREF
  PACL pSacl; // [rsp+80h] [rbp-31h] BYREF
  OLECHAR *v33; // [rsp+88h] [rbp-29h] BYREF
  LONGLONG v34; // [rsp+90h] [rbp-21h] BYREF
  PACL pDacl; // [rsp+98h] [rbp-19h] BYREF
  OLECHAR *v36; // [rsp+A0h] [rbp-11h] BYREF
  VARIANTARG pvarga; // [rsp+A8h] [rbp-9h] BYREF
  VARIANTARG v38; // [rsp+C0h] [rbp+Fh] BYREF
  WORD pControl; // [rsp+118h] [rbp+67h] BYREF
  struct tagVARIANT *pv; // [rsp+120h] [rbp+6Fh]
  int v41; // [rsp+128h] [rbp+77h]

  v41 = a3;
  pv = pvarg;
  ppv = 0;
  v34 = 0;
  v23 = 0;
  v5 = 0;
  psz = 0;
  v33 = 0;
  v36 = 0;
  v7 = 0;
  bOwnerDefaulted = 0;
  v8 = 0;
  bGroupDefaulted = 0;
  v9 = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  bSaclPresent = 0;
  bDaclPresent = 0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  dwRevision = 0;
  pControl = 0;
  VariantInit(pvarg);
  memset(&pvarga, 0, sizeof(pvarga));
  memset(&v38, 0, sizeof(v38));
  if ( !pSecurityDescriptor )
  {
    SysFreeString(0);
    SysFreeString(0);
    return 2147500037LL;
  }
  if ( !GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
      goto LABEL_35;
  }
  if ( !GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) || (v12 = pOwner) == 0 )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
      goto LABEL_35;
    v12 = pOwner;
  }
  LastError = ConvertSidToFriendlyName(v12, &psz, a4);
  if ( LastError < 0 )
    goto LABEL_34;
  if ( !GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bGroupDefaulted) || (v13 = pGroup) == 0 )
  {
    LastError = HResultGetLastError();
    if ( LastError >= 0 )
    {
      v13 = pGroup;
      goto LABEL_14;
    }
LABEL_34:
    v8 = psz;
    goto LABEL_35;
  }
LABEL_14:
  LastError = ConvertSidToFriendlyName(v13, &v23, a4);
  if ( LastError < 0 )
    goto LABEL_33;
  GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted);
  if ( pDacl )
  {
    LastError = ConvertACLToVariant(pDacl, &v38, a4);
    if ( LastError < 0 )
      goto LABEL_33;
  }
  if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) || (v14 = pSacl) == 0 )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
    {
LABEL_33:
      v7 = v23;
      goto LABEL_34;
    }
    v14 = pSacl;
    if ( !pSacl )
      goto LABEL_22;
  }
  LastError = ConvertACLToVariant(v14, &pvarga, a4);
  if ( LastError < 0 )
    goto LABEL_33;
LABEL_22:
  LastError = CoCreateInstance(&CLSID_SecurityDescriptor, 0, 1u, &IID_IADsSecurityDescriptor, &ppv);
  if ( LastError < 0 )
    goto LABEL_33;
  v8 = psz;
  psz = SysAllocString(psz);
  v15 = psz;
  ATL::CComBSTR::operator=(&v36, &psz);
  SysFreeString(v15);
  v7 = v23;
  v23 = SysAllocString(v23);
  v16 = v23;
  ATL::CComBSTR::operator=(&v33, &v23);
  SysFreeString(v16);
  v9 = v36;
  if ( !v8 || v36 )
  {
    v5 = v33;
    if ( !v7 || v33 )
    {
      (*(void (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 96LL))(ppv, v36);
      (*(void (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 128LL))(ppv, v5);
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, dwRevision);
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 80LL))(ppv, pControl);
      (*(void (__fastcall **)(LPVOID, LONGLONG))(*(_QWORD *)ppv + 160LL))(ppv, v38.llVal);
      (*(void (__fastcall **)(LPVOID, LONGLONG))(*(_QWORD *)ppv + 192LL))(ppv, pvarga.llVal);
      LastError = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LONGLONG *))ppv)(ppv, &IID_IDispatch, &v34);
      if ( LastError >= 0 )
      {
        v17 = v41 == 0;
        v18 = pv;
        v19 = v34;
        pv->vt = 9;
        v18->llVal = v19;
        if ( !v17 )
        {
          LastError = VariantToVariantArray(v18);
          if ( LastError < 0 )
            (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v34 + 16LL))(v34);
        }
      }
      goto LABEL_35;
    }
  }
  else
  {
    v5 = v33;
  }
  LastError = -2147024882;
LABEL_35:
  VariantClear(&pvarga);
  VariantClear(&v38);
  if ( v8 )
    FreeADsStr(v8);
  if ( v7 )
    FreeADsStr(v7);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  SysFreeString(v5);
  SysFreeString(v9);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180012574  mov     rax, rsp
0x180012577  mov     [rax+20h], rbx
0x18001257b  mov     [rax+18h], r8d
0x18001257f  mov     [rax+10h], rdx
0x180012583  push    rbp
0x180012584  push    rsi
0x180012585  push    rdi
0x180012586  push    r12
0x180012588  push    r13
0x18001258a  push    r14
0x18001258c  push    r15
0x18001258e  lea     rbp, [rax-5Fh]
0x180012592  sub     rsp, 0D0h
0x180012599  xor     esi, esi
0x18001259b  xor     eax, eax
0x18001259d  mov     r12, rcx
0x1800125a0  mov     [rbp+57h+ppv], rsi
0x1800125a4  xorps   xmm0, xmm0
0x1800125a7  mov     [rbp+57h+var_78], rsi
0x1800125ab  xorps   xmm1, xmm1
0x1800125ae  mov     [rbp+57h+var_B8], rsi
0x1800125b2  mov     ebx, esi
0x1800125b4  mov     [rbp+57h+psz], rsi
0x1800125b8  mov     rcx, rdx; pvarg
0x1800125bb  mov     [rbp+57h+var_80], rbx
0x1800125bf  mov     r13, r9
0x1800125c2  mov     [rbp+57h+var_68], rsi
0x1800125c6  mov     r15d, esi
0x1800125c9  mov     [rbp+57h+bOwnerDefaulted], esi
0x1800125cc  mov     r14d, esi
0x1800125cf  mov     [rbp+57h+bGroupDefaulted], esi
0x1800125d2  mov     edi, esi
0x1800125d4  mov     [rbp+57h+bDaclDefaulted], esi
0x1800125d7  mov     [rbp+57h+bSaclDefaulted], esi
0x1800125da  mov     [rbp+57h+bSaclPresent], esi
0x1800125dd  mov     [rbp+57h+bDaclPresent], esi
0x1800125e0  mov     [rbp+57h+pOwner], rsi
0x1800125e4  mov     [rbp+57h+pGroup], rsi
0x1800125e8  mov     [rbp+57h+pDacl], rsi
0x1800125ec  mov     [rbp+57h+pSacl], rsi
0x1800125f0  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800125f4  mov     qword ptr [rbp+57h+var_48+10h], rax
0x1800125f8  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x1800125fc  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180012600  mov     [rbp+57h+dwRevision], esi
0x180012603  mov     [rbp+57h+pControl], si
0x180012607  call    cs:__imp_VariantInit
0x18001260d  xor     eax, eax
0x18001260f  xorps   xmm0, xmm0
0x180012612  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180012616  xorps   xmm1, xmm1
0x180012619  mov     qword ptr [rbp+57h+var_48+10h], rax
0x18001261d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180012621  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x180012625  test    r12, r12
0x180012628  jnz     short loc_180012644
0x18001262a  xor     ecx, ecx; bstrString
0x18001262c  call    cs:__imp_SysFreeString
0x180012632  xor     ecx, ecx; bstrString
0x180012634  call    cs:__imp_SysFreeString
0x18001263a  mov     eax, 80004005h
0x18001263f  jmp     loc_18001295A
0x180012644  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x180012648  mov     rcx, r12; pSecurityDescriptor
0x18001264b  lea     rdx, [rbp+57h+pControl]; pControl
0x18001264f  call    cs:__imp_GetSecurityDescriptorControl
0x180012655  test    eax, eax
0x180012657  jnz     short loc_180012668
0x180012659  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x18001265e  mov     esi, eax
0x180012660  test    eax, eax
0x180012662  js      loc_180012901
0x180012668  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18001266c  mov     rcx, r12; pSecurityDescriptor
0x18001266f  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180012673  call    cs:__imp_GetSecurityDescriptorOwner
0x180012679  test    eax, eax
0x18001267b  jz      short loc_180012686
0x18001267d  mov     rcx, [rbp+57h+pOwner]
0x180012681  test    rcx, rcx
0x180012684  jnz     short loc_180012699
0x180012686  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x18001268b  mov     esi, eax
0x18001268d  test    eax, eax
0x18001268f  js      loc_180012901
0x180012695  mov     rcx, [rbp+57h+pOwner]; pSid
0x180012699  mov     r8, r13; unsigned __int16 *
0x18001269c  lea     rdx, [rbp+57h+psz]; unsigned __int16 **
0x1800126a0  call    ?ConvertSidToFriendlyName@@YAJPEAXPEAPEAGPEBG@Z; ConvertSidToFriendlyName(void *,ushort * *,ushort const *)
0x1800126a5  mov     esi, eax
0x1800126a7  test    eax, eax
0x1800126a9  js      loc_1800128FD
0x1800126af  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x1800126b3  mov     rcx, r12; pSecurityDescriptor
0x1800126b6  lea     rdx, [rbp+57h+pGroup]; pGroup
0x1800126ba  call    cs:__imp_GetSecurityDescriptorGroup
0x1800126c0  test    eax, eax
0x1800126c2  jz      short loc_1800126CD
0x1800126c4  mov     rcx, [rbp+57h+pGroup]
0x1800126c8  test    rcx, rcx
0x1800126cb  jnz     short loc_1800126E0
0x1800126cd  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x1800126d2  mov     esi, eax
0x1800126d4  test    eax, eax
0x1800126d6  js      loc_1800128FD
0x1800126dc  mov     rcx, [rbp+57h+pGroup]; pSid
0x1800126e0  mov     r8, r13; unsigned __int16 *
0x1800126e3  lea     rdx, [rbp+57h+var_B8]; unsigned __int16 **
0x1800126e7  call    ?ConvertSidToFriendlyName@@YAJPEAXPEAPEAGPEBG@Z; ConvertSidToFriendlyName(void *,ushort * *,ushort const *)
0x1800126ec  mov     esi, eax
0x1800126ee  test    eax, eax
0x1800126f0  js      loc_1800128F9
0x1800126f6  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x1800126fa  mov     rcx, r12; pSecurityDescriptor
0x1800126fd  lea     r8, [rbp+57h+pDacl]; pDacl
0x180012701  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180012705  call    cs:__imp_GetSecurityDescriptorDacl
0x18001270b  mov     rcx, [rbp+57h+pDacl]; pAcl
0x18001270f  test    rcx, rcx
0x180012712  jz      short loc_18001272A
0x180012714  mov     r8, r13; unsigned __int16 *
0x180012717  lea     rdx, [rbp+57h+var_48]; pvarg
0x18001271b  call    ?ConvertACLToVariant@@YAJPEAU_ACL@@PEAUtagVARIANT@@PEBG@Z; ConvertACLToVariant(_ACL *,tagVARIANT *,ushort const *)
0x180012720  mov     esi, eax
0x180012722  test    eax, eax
0x180012724  js      loc_1800128F9
0x18001272a  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x18001272e  mov     rcx, r12; pSecurityDescriptor
0x180012731  lea     r8, [rbp+57h+pSacl]; pSacl
0x180012735  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x180012739  call    cs:__imp_GetSecurityDescriptorSacl
0x18001273f  test    eax, eax
0x180012741  jz      short loc_18001274C
0x180012743  mov     rcx, [rbp+57h+pSacl]
0x180012747  test    rcx, rcx
0x18001274a  jnz     short loc_180012764
0x18001274c  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x180012751  mov     esi, eax
0x180012753  test    eax, eax
0x180012755  js      loc_1800128F9
0x18001275b  mov     rcx, [rbp+57h+pSacl]; pAcl
0x18001275f  test    rcx, rcx
0x180012762  jz      short loc_18001277A
0x180012764  mov     r8, r13; unsigned __int16 *
0x180012767  lea     rdx, [rbp+57h+pvarg]; pvarg
0x18001276b  call    ?ConvertACLToVariant@@YAJPEAU_ACL@@PEAUtagVARIANT@@PEBG@Z; ConvertACLToVariant(_ACL *,tagVARIANT *,ushort const *)
0x180012770  mov     esi, eax
0x180012772  test    eax, eax
0x180012774  js      loc_1800128F9
0x18001277a  xor     edx, edx; pUnkOuter
0x18001277c  lea     rax, [rbp+57h+ppv]
0x180012780  lea     r9, IID_IADsSecurityDescriptor; riid
0x180012787  mov     [rsp+20h], rax; ppv
0x18001278c  lea     rcx, CLSID_SecurityDescriptor; rclsid
0x180012793  lea     r8d, [rdx+1]; dwClsContext
0x180012797  call    cs:__imp_CoCreateInstance
0x18001279d  mov     esi, eax
0x18001279f  test    eax, eax
0x1800127a1  js      loc_1800128F9
0x1800127a7  mov     r14, [rbp+57h+psz]
0x1800127ab  mov     rcx, r14; psz
0x1800127ae  call    cs:__imp_SysAllocString
0x1800127b4  lea     rdx, [rbp+57h+psz]
0x1800127b8  mov     [rbp+57h+psz], rax
0x1800127bc  lea     rcx, [rbp+57h+var_68]
0x1800127c0  mov     rbx, rax
0x1800127c3  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x1800127c8  mov     rcx, rbx; bstrString
0x1800127cb  call    cs:__imp_SysFreeString
0x1800127d1  mov     r15, [rbp+57h+var_B8]
0x1800127d5  mov     rcx, r15; psz
0x1800127d8  call    cs:__imp_SysAllocString
0x1800127de  lea     rdx, [rbp+57h+var_B8]
0x1800127e2  mov     [rbp+57h+var_B8], rax
0x1800127e6  lea     rcx, [rbp+57h+var_80]
0x1800127ea  mov     rbx, rax
0x1800127ed  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x1800127f2  mov     rcx, rbx; bstrString
0x1800127f5  call    cs:__imp_SysFreeString
0x1800127fb  mov     rdi, [rbp+57h+var_68]
0x1800127ff  test    r14, r14
0x180012802  jz      short loc_18001280F
0x180012804  test    rdi, rdi
0x180012807  jnz     short loc_18001280F
0x180012809  mov     rbx, [rbp+57h+var_80]
0x18001280d  jmp     short loc_18001281D
0x18001280f  mov     rbx, [rbp+57h+var_80]
0x180012813  test    r15, r15
0x180012816  jz      short loc_180012827
0x180012818  test    rbx, rbx
0x18001281b  jnz     short loc_180012827
0x18001281d  mov     esi, 8007000Eh
0x180012822  jmp     loc_180012901
0x180012827  mov     rcx, [rbp+57h+ppv]
0x18001282b  mov     rdx, rdi
0x18001282e  mov     rax, [rcx]
0x180012831  mov     rax, [rax+60h]
0x180012835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001283a  mov     rcx, [rbp+57h+ppv]
0x18001283e  mov     rdx, rbx
0x180012841  mov     rax, [rcx]
0x180012844  mov     rax, [rax+80h]
0x18001284b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012850  mov     rcx, [rbp+57h+ppv]
0x180012854  mov     edx, [rbp+57h+dwRevision]
0x180012857  mov     rax, [rcx]
0x18001285a  mov     rax, [rax+40h]
0x18001285e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012863  mov     rcx, [rbp+57h+ppv]
0x180012867  movzx   edx, [rbp+57h+pControl]
0x18001286b  mov     rax, [rcx]
0x18001286e  mov     rax, [rax+50h]
0x180012872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012877  mov     rcx, [rbp+57h+ppv]
0x18001287b  mov     rdx, qword ptr [rbp+57h+var_48+8]
0x18001287f  mov     rax, [rcx]
0x180012882  mov     rax, [rax+0A0h]
0x180012889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001288e  mov     rcx, [rbp+57h+ppv]
0x180012892  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x180012896  mov     rax, [rcx]
0x180012899  mov     rax, [rax+0C0h]
0x1800128a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128a5  mov     rcx, [rbp+57h+ppv]
0x1800128a9  lea     r8, [rbp+57h+var_78]
0x1800128ad  lea     rdx, IID_IDispatch
0x1800128b4  mov     rax, [rcx]
0x1800128b7  mov     rax, [rax]
0x1800128ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128bf  mov     esi, eax
0x1800128c1  test    eax, eax
0x1800128c3  js      short loc_180012901
0x1800128c5  cmp     [rbp+57h+arg_10], 0
0x1800128c9  mov     rcx, [rbp+57h+pv]; pv
0x1800128cd  mov     rax, [rbp+57h+var_78]
0x1800128d1  mov     word ptr [rcx], 9
0x1800128d6  mov     [rcx+8], rax
0x1800128da  jz      short loc_180012901
0x1800128dc  call    ?VariantToVariantArray@@YAJPEAUtagVARIANT@@@Z; VariantToVariantArray(tagVARIANT *)
0x1800128e1  mov     esi, eax
0x1800128e3  test    eax, eax
0x1800128e5  jns     short loc_180012901
0x1800128e7  mov     rcx, [rbp+57h+var_78]
0x1800128eb  mov     rax, [rcx]
0x1800128ee  mov     rax, [rax+10h]
0x1800128f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128f7  jmp     short loc_180012901
0x1800128f9  mov     r15, [rbp+57h+var_B8]
0x1800128fd  mov     r14, [rbp+57h+psz]
0x180012901  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180012905  call    cs:__imp_VariantClear
0x18001290b  lea     rcx, [rbp+57h+var_48]; pvarg
0x18001290f  call    cs:__imp_VariantClear
0x180012915  test    r14, r14
0x180012918  jz      short loc_180012923
0x18001291a  mov     rcx, r14; pStr
0x18001291d  call    cs:__imp_FreeADsStr
0x180012923  test    r15, r15
0x180012926  jz      short loc_180012931
0x180012928  mov     rcx, r15; pStr
0x18001292b  call    cs:__imp_FreeADsStr
0x180012931  mov     rcx, [rbp+57h+ppv]
0x180012935  test    rcx, rcx
0x180012938  jz      short loc_180012946
0x18001293a  mov     rax, [rcx]
0x18001293d  mov     rax, [rax+10h]
0x180012941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012946  mov     rcx, rbx; bstrString
0x180012949  call    cs:__imp_SysFreeString
0x18001294f  mov     rcx, rdi; bstrString
0x180012952  call    cs:__imp_SysFreeString
0x180012958  mov     eax, esi
0x18001295a  mov     rbx, [rsp+100h+arg_18]
0x180012962  add     rsp, 0D0h
0x180012969  pop     r15
0x18001296b  pop     r14
0x18001296d  pop     r13
0x18001296f  pop     r12
0x180012971  pop     rdi
0x180012972  pop     rsi
0x180012973  pop     rbp
0x180012974  retn
```
