# CAutoLogonManager::_GetSerializationUnlockLogon(_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *)

- ea: `0x18003e3c4`
- end: `0x18003e8d5`
- name: `?_GetSerializationUnlockLogon@CAutoLogonManager@@AEAAJPEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Z`
- size: `1297`
- prototype: `__int64 __fastcall(CAutoLogonManager *__hidden this, struct _CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003e160`

## callees

- `0x18003e3c4`
- `0x18003e8dc`
- `0x18003e960`
- `0x18003e9ec`
- `0x18005d488`
- `0x180062760`
- `0x180063eb0`
- `0x180066448`
- `0x18009d010`

## import_xrefs

- `CredProvCommonCore!__imp_?UnformatUsername@@YAJW4_CREDENTIAL_PROVIDER_USAGE_SCENARIO@@PEBG1_NPEAPEAG3@Z` at `0x18003e53d`
- `CredProvCommonCore!__imp_?UnformatUsername@@YAJW4_CREDENTIAL_PROVIDER_USAGE_SCENARIO@@PEBG1_NPEAPEAG3@Z` at `0x18003e53d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e76f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e76f`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003e725`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003e725`

## string_xrefs

- `0x18003e49d`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18003e58e`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18003e673`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18003e6f7`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18003e803`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAutoLogonManager::_GetSerializationUnlockLogon(
        CAutoLogonManager *this,
        struct _CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *a2)
{
  __int64 *v2; // rcx
  __int64 v4; // rax
  int v5; // ebx
  const unsigned __int16 *v6; // rcx
  const unsigned __int16 *v7; // rdx
  unsigned __int16 **v8; // rcx
  unsigned __int16 *v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rdx
  unsigned __int8 *v17; // rcx
  __int64 v18; // rdx
  unsigned __int16 **v19; // rcx
  unsigned __int16 *v20; // rdx
  __int64 v21; // rdx
  unsigned __int16 *v22; // rdx
  unsigned __int16 *v23; // rdx
  unsigned __int8 *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  unsigned __int16 *v27; // rdx
  int v28; // edi
  __int64 v29; // rcx
  _BYTE *v30; // rbx
  __int64 v31; // rax
  _BYTE *i; // rcx
  unsigned __int16 *v33; // rdx
  unsigned __int16 *v34; // rdx
  unsigned __int16 *v35; // rdx
  unsigned __int16 *v36; // rdx
  const unsigned __int16 *v37; // rdx
  const unsigned __int16 *v38; // rdx
  int NegoAuthPackageId; // eax
  __int64 v40; // rcx
  LPVOID v41; // rdx
  unsigned __int16 *v42; // rdx
  unsigned __int16 *v43; // rdx
  unsigned __int16 *v44; // rdx
  unsigned __int16 *v45; // rdx
  const unsigned __int16 *v46; // rdx
  const unsigned __int16 *v47; // rdx
  int v48; // [rsp+20h] [rbp-99h]
  int v49; // [rsp+20h] [rbp-99h]
  const unsigned __int16 *v50; // [rsp+30h] [rbp-89h] BYREF
  const unsigned __int16 *v51; // [rsp+38h] [rbp-81h] BYREF
  unsigned __int16 *v52; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v53; // [rsp+48h] [rbp-71h] BYREF
  unsigned __int16 *v54; // [rsp+50h] [rbp-69h] BYREF
  _QWORD *p_pv; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int8 *v56; // [rsp+60h] [rbp-59h] BYREF
  char v57; // [rsp+68h] [rbp-51h]
  LPVOID pv; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int16 **v59; // [rsp+78h] [rbp-41h]
  unsigned __int16 *v60; // [rsp+80h] [rbp-39h] BYREF
  char v61; // [rsp+88h] [rbp-31h]
  _KERB_INTERACTIVE_UNLOCK_LOGON v62; // [rsp+90h] [rbp-29h] BYREF
  const unsigned __int16 **v63; // [rsp+D0h] [rbp+17h]
  const unsigned __int16 *v64; // [rsp+D8h] [rbp+1Fh] BYREF
  char v65; // [rsp+E0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  LPMALLOC ppMalloc; // [rsp+120h] [rbp+67h] BYREF
  unsigned int v68; // [rsp+130h] [rbp+77h] BYREF
  unsigned __int16 *v69; // [rsp+138h] [rbp+7Fh] BYREF

  v57 = 1;
  v51 = 0;
  p_pv = &v69;
  v50 = 0;
  v59 = (unsigned __int16 **)&v50;
  v2 = (__int64 *)((char *)this + 8);
  v69 = 0;
  v56 = 0;
  v63 = &v51;
  v60 = 0;
  v4 = *v2;
  v61 = 1;
  v64 = 0;
  v65 = 1;
  v5 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 **, unsigned __int16 **, unsigned __int8 **))(v4 + 88))(
         v2,
         &v64,
         &v60,
         &v56);
  if ( v65 )
  {
    v6 = v64;
    v7 = *v63;
    *v63 = v64;
    if ( v7 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v6, v7);
  }
  if ( v61 )
  {
    v8 = v59;
    v9 = *v59;
    *v59 = v60;
    if ( v9 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v8, v9);
  }
  if ( v57 )
  {
    v10 = p_pv;
    v11 = *p_pv;
    *p_pv = v56;
    if ( v11 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v10, v11);
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
      (const char *)(unsigned int)v5,
      v48);
LABEL_12:
    v13 = v69;
    v69 = 0;
    if ( v13 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v12, v13);
    v14 = v50;
    v50 = 0;
    if ( v14 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v12, v14);
    v15 = v51;
    v51 = 0;
    if ( v15 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v12, v15);
    return (unsigned int)v5;
  }
  v59 = &v52;
  p_pv = &v53;
  v53 = 0;
  v52 = 0;
  v60 = 0;
  v61 = 1;
  v56 = 0;
  v57 = 1;
  v5 = UnformatUsername(CPUS_LOGON, v50, v51, 0, (unsigned __int16 **)&v56, &v60);
  if ( v57 )
  {
    v17 = v56;
    v18 = *p_pv;
    *p_pv = v56;
    if ( v18 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v17, v18);
  }
  if ( v61 )
  {
    v19 = v59;
    v20 = *v59;
    *v59 = v60;
    if ( v20 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v19, v20);
  }
  if ( v5 < 0 )
  {
    v21 = 469;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
      (const char *)(unsigned int)v5,
      v49);
LABEL_28:
    v22 = v52;
    v52 = 0;
    if ( v22 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v12, v22);
    v23 = v53;
    v53 = 0;
    if ( v23 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v12, v23);
    goto LABEL_12;
  }
  *(_QWORD *)&v62.Logon.MessageType = 2;
  memset(&v62.Logon.LogonDomainName, 0, 56);
  v5 = UnicodeStringStringHijack(v53, &v62.Logon.LogonDomainName);
  if ( v5 < 0 )
  {
    v21 = 488;
    goto LABEL_27;
  }
  v5 = UnicodeStringStringHijack(v52, &v62.Logon.UserName);
  if ( v5 < 0 )
  {
    v21 = 489;
    goto LABEL_27;
  }
  p_pv = &v54;
  v54 = 0;
  v56 = 0;
  v57 = 1;
  v5 = _EncryptAndMarshal(v69, (unsigned __int16 **)&v56);
  if ( v57 )
  {
    v24 = v56;
    v25 = *p_pv;
    *p_pv = v56;
    if ( v25 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v24, v25);
  }
  if ( v5 < 0 )
  {
    v26 = 493;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
      (const char *)(unsigned int)v5,
      v49);
LABEL_42:
    v27 = v54;
    v54 = 0;
    if ( v27 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v12, v27);
    goto LABEL_28;
  }
  v5 = UnicodeStringStringHijack(v54, &v62.Logon.Password);
  if ( v5 < 0 )
  {
    v26 = 494;
    goto LABEL_41;
  }
  v68 = 0;
  p_pv = &pv;
  pv = 0;
  v56 = 0;
  v57 = 1;
  v28 = KerbInteractiveUnlockLogonPack(&v62, &v56, &v68);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>>(&p_pv);
  if ( v28 >= 0 )
  {
    LODWORD(ppMalloc) = 0;
    NegoAuthPackageId = GetNegoAuthPackageId((unsigned int *)&ppMalloc);
    v5 = NegoAuthPackageId;
    if ( NegoAuthPackageId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
        (const char *)(unsigned int)NegoAuthPackageId,
        v49);
      v41 = pv;
      pv = 0;
      if ( v41 )
        wil::cotaskmem_secure_deleter::operator()<unsigned short>(v12, v41);
      goto LABEL_42;
    }
    v42 = v54;
    a2->ulAuthenticationPackage = (unsigned int)ppMalloc;
    a2->cbSerialization = v68;
    a2->rgbSerialization = (byte *)pv;
    pv = 0;
    v54 = 0;
    a2->clsidCredentialProvider = CLSID_PasswordCredentialProvider;
    if ( v42 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v40, v42);
    v43 = v52;
    v52 = 0;
    if ( v43 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v40, v43);
    v44 = v53;
    v53 = 0;
    if ( v44 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v40, v44);
    v45 = v69;
    v69 = 0;
    if ( v45 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v40, v45);
    v46 = v50;
    v50 = 0;
    if ( v46 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v40, v46);
    v47 = v51;
    v51 = 0;
    if ( v47 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v40, v47);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
      (const char *)(unsigned int)v28,
      v49);
    v30 = pv;
    pv = 0;
    if ( v30 )
    {
      ppMalloc = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v31 = ((__int64 (__fastcall *)(LPMALLOC, _BYTE *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v30);
        if ( v31 != -1 )
        {
          for ( i = v30; v31; --v31 )
            *i++ = 0;
        }
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      CoTaskMemFree(v30);
    }
    v33 = v54;
    v54 = 0;
    if ( v33 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v29, v33);
    v34 = v52;
    v52 = 0;
    if ( v34 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v29, v34);
    v35 = v53;
    v53 = 0;
    if ( v35 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v29, v35);
    v36 = v69;
    v69 = 0;
    if ( v36 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v29, v36);
    v37 = v50;
    v50 = 0;
    if ( v37 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v29, v37);
    v38 = v51;
    v51 = 0;
    if ( v38 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v29, v38);
    return (unsigned int)v28;
  }
}

```

## disassembly

```asm
0x18003e3c4  push    rbp
0x18003e3c6  push    rbx
0x18003e3c7  push    rsi
0x18003e3c8  push    rdi
0x18003e3c9  push    r14
0x18003e3cb  lea     rbp, [rsp-37h]
0x18003e3d0  sub     rsp, 0F0h
0x18003e3d7  xor     r14d, r14d
0x18003e3da  mov     [rbp+57h+var_A8], 1
0x18003e3de  lea     rax, [rbp+57h+arg_18]
0x18003e3e2  mov     [rsp+110h+var_D8], r14
0x18003e3e7  mov     [rbp+57h+var_B8], rax
0x18003e3eb  lea     r9, [rbp+57h+var_B0]
0x18003e3ef  lea     rax, [rsp+110h+var_E0]
0x18003e3f4  mov     [rsp+110h+var_E0], r14
0x18003e3f9  mov     [rbp+57h+var_98], rax
0x18003e3fd  lea     r8, [rbp+57h+var_90]
0x18003e401  add     rcx, 8
0x18003e405  mov     [rbp+57h+arg_18], r14
0x18003e409  lea     rax, [rsp+110h+var_D8]
0x18003e40e  mov     [rbp+57h+var_B0], r14
0x18003e412  mov     [rbp+57h+var_40], rax
0x18003e416  mov     rsi, rdx
0x18003e419  lea     rdx, [rbp+57h+var_38]
0x18003e41d  mov     [rbp+57h+var_90], r14
0x18003e421  mov     rax, [rcx]
0x18003e424  mov     [rbp+57h+var_88], 1
0x18003e428  mov     [rbp+57h+var_38], r14
0x18003e42c  mov     [rbp+57h+var_30], 1
0x18003e430  mov     rax, [rax+58h]
0x18003e434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e439  mov     ebx, eax
0x18003e43b  cmp     [rbp+57h+var_30], r14b
0x18003e43f  jz      short loc_18003E459
0x18003e441  mov     r8, [rbp+57h+var_40]
0x18003e445  mov     rcx, [rbp+57h+var_38]
0x18003e449  mov     rdx, [r8]
0x18003e44c  mov     [r8], rcx
0x18003e44f  test    rdx, rdx
0x18003e452  jz      short loc_18003E459
0x18003e454  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e459  cmp     [rbp+57h+var_88], r14b
0x18003e45d  jz      short loc_18003E477
0x18003e45f  mov     rcx, [rbp+57h+var_98]
0x18003e463  mov     rax, [rbp+57h+var_90]
0x18003e467  mov     rdx, [rcx]
0x18003e46a  mov     [rcx], rax
0x18003e46d  test    rdx, rdx
0x18003e470  jz      short loc_18003E477
0x18003e472  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e477  cmp     [rbp+57h+var_A8], r14b
0x18003e47b  jz      short loc_18003E495
0x18003e47d  mov     rcx, [rbp+57h+var_B8]
0x18003e481  mov     rax, [rbp+57h+var_B0]
0x18003e485  mov     rdx, [rcx]
0x18003e488  mov     [rcx], rax
0x18003e48b  test    rdx, rdx
0x18003e48e  jz      short loc_18003E495
0x18003e490  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e495  test    ebx, ebx
0x18003e497  jns     short loc_18003E4F2
0x18003e499  mov     rcx, [rbp+5Fh]; this
0x18003e49d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003e4a4  mov     r9d, ebx; char *
0x18003e4a7  mov     edx, 1D0h; void *
0x18003e4ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e4b1  mov     rdx, [rbp+57h+arg_18]
0x18003e4b5  mov     [rbp+57h+arg_18], r14
0x18003e4b9  test    rdx, rdx
0x18003e4bc  jz      short loc_18003E4C3
0x18003e4be  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e4c3  mov     rdx, [rsp+110h+var_E0]
0x18003e4c8  mov     [rsp+110h+var_E0], r14
0x18003e4cd  test    rdx, rdx
0x18003e4d0  jz      short loc_18003E4D7
0x18003e4d2  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e4d7  mov     rdx, [rsp+110h+var_D8]
0x18003e4dc  mov     [rsp+110h+var_D8], r14
0x18003e4e1  test    rdx, rdx
0x18003e4e4  jz      short loc_18003E4EB
0x18003e4e6  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e4eb  mov     eax, ebx
0x18003e4ed  jmp     loc_18003E8C7
0x18003e4f2  mov     r8, [rsp+110h+var_D8]
0x18003e4f7  lea     rax, [rbp+57h+var_D0]
0x18003e4fb  mov     rdx, [rsp+110h+var_E0]
0x18003e500  xor     r9d, r9d
0x18003e503  mov     [rbp+57h+var_98], rax
0x18003e507  lea     rax, [rbp+57h+var_C8]
0x18003e50b  mov     [rbp+57h+var_B8], rax
0x18003e50f  lea     rax, [rbp+57h+var_90]
0x18003e513  mov     [rsp+110h+var_E8], rax
0x18003e518  lea     rax, [rbp+57h+var_B0]
0x18003e51c  lea     ecx, [r9+1]
0x18003e520  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18003e525  mov     [rbp+57h+var_C8], r14
0x18003e529  mov     [rbp+57h+var_D0], r14
0x18003e52d  mov     [rbp+57h+var_90], r14
0x18003e531  mov     [rbp+57h+var_88], 1
0x18003e535  mov     [rbp+57h+var_B0], r14
0x18003e539  mov     [rbp+57h+var_A8], 1
0x18003e53d  call    cs:__imp_?UnformatUsername@@YAJW4_CREDENTIAL_PROVIDER_USAGE_SCENARIO@@PEBG1_NPEAPEAG3@Z; UnformatUsername(_CREDENTIAL_PROVIDER_USAGE_SCENARIO,ushort const *,ushort const *,bool,ushort * *,ushort * *)
0x18003e543  mov     ebx, eax
0x18003e545  cmp     [rbp+57h+var_A8], r14b
0x18003e549  jz      short loc_18003E563
0x18003e54b  mov     r8, [rbp+57h+var_B8]
0x18003e54f  mov     rcx, [rbp+57h+var_B0]
0x18003e553  mov     rdx, [r8]
0x18003e556  mov     [r8], rcx
0x18003e559  test    rdx, rdx
0x18003e55c  jz      short loc_18003E563
0x18003e55e  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e563  cmp     [rbp+57h+var_88], r14b
0x18003e567  jz      short loc_18003E581
0x18003e569  mov     rcx, [rbp+57h+var_98]
0x18003e56d  mov     rax, [rbp+57h+var_90]
0x18003e571  mov     rdx, [rcx]
0x18003e574  mov     [rcx], rax
0x18003e577  test    rdx, rdx
0x18003e57a  jz      short loc_18003E581
0x18003e57c  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e581  test    ebx, ebx
0x18003e583  jns     short loc_18003E5CA
0x18003e585  mov     edx, 1D5h; void *
0x18003e58a  mov     rcx, [rbp+5Fh]; this
0x18003e58e  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003e595  mov     r9d, ebx; char *
0x18003e598  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e59d  mov     rdx, [rbp+57h+var_D0]
0x18003e5a1  mov     [rbp+57h+var_D0], r14
0x18003e5a5  test    rdx, rdx
0x18003e5a8  jz      short loc_18003E5AF
0x18003e5aa  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e5af  mov     rdx, [rbp+57h+var_C8]
0x18003e5b3  mov     [rbp+57h+var_C8], r14
0x18003e5b7  test    rdx, rdx
0x18003e5ba  jz      loc_18003E4B1
0x18003e5c0  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e5c5  jmp     loc_18003E4B1
0x18003e5ca  mov     rcx, [rbp+57h+var_C8]; unsigned __int16 *
0x18003e5ce  lea     rdx, [rbp+57h+var_80.Logon.LogonDomainName]; struct _UNICODE_STRING *
0x18003e5d2  mov     qword ptr [rbp+57h+var_80.Logon.MessageType], 2
0x18003e5da  mov     qword ptr [rbp+57h+var_80.Logon.LogonDomainName.Length], r14
0x18003e5de  mov     qword ptr [rbp+57h+var_80.Logon.UserName.Length], r14
0x18003e5e2  mov     qword ptr [rbp+57h+var_80.Logon.Password.Length], r14
0x18003e5e6  mov     [rbp+57h+var_80.Logon.LogonDomainName.Buffer], r14
0x18003e5ea  mov     [rbp+57h+var_80.Logon.Password.Buffer], r14
0x18003e5ee  mov     [rbp+57h+var_80.Logon.UserName.Buffer], r14
0x18003e5f2  mov     qword ptr [rbp+57h+var_80.LogonId.LowPart], r14
0x18003e5f6  call    ?UnicodeStringStringHijack@@YAJPEBGPEAU_UNICODE_STRING@@@Z; UnicodeStringStringHijack(ushort const *,_UNICODE_STRING *)
0x18003e5fb  mov     ebx, eax
0x18003e5fd  test    eax, eax
0x18003e5ff  jns     short loc_18003E608
0x18003e601  mov     edx, 1E8h
0x18003e606  jmp     short loc_18003E58A
0x18003e608  mov     rcx, [rbp+57h+var_D0]; unsigned __int16 *
0x18003e60c  lea     rdx, [rbp+57h+var_80.Logon.UserName]; struct _UNICODE_STRING *
0x18003e610  call    ?UnicodeStringStringHijack@@YAJPEBGPEAU_UNICODE_STRING@@@Z; UnicodeStringStringHijack(ushort const *,_UNICODE_STRING *)
0x18003e615  mov     ebx, eax
0x18003e617  test    eax, eax
0x18003e619  jns     short loc_18003E625
0x18003e61b  mov     edx, 1E9h
0x18003e620  jmp     loc_18003E58A
0x18003e625  mov     rcx, [rbp+57h+arg_18]; unsigned __int16 *
0x18003e629  lea     rax, [rbp+57h+var_C0]
0x18003e62d  lea     rdx, [rbp+57h+var_B0]; unsigned __int16 **
0x18003e631  mov     [rbp+57h+var_B8], rax
0x18003e635  mov     [rbp+57h+var_C0], r14
0x18003e639  mov     [rbp+57h+var_B0], r14
0x18003e63d  mov     [rbp+57h+var_A8], 1
0x18003e641  call    ?_EncryptAndMarshal@@YAJPEBGPEAPEAG@Z; _EncryptAndMarshal(ushort const *,ushort * *)
0x18003e646  mov     ebx, eax
0x18003e648  cmp     [rbp+57h+var_A8], r14b
0x18003e64c  jz      short loc_18003E666
0x18003e64e  mov     r8, [rbp+57h+var_B8]
0x18003e652  mov     rcx, [rbp+57h+var_B0]
0x18003e656  mov     rdx, [r8]
0x18003e659  mov     [r8], rcx
0x18003e65c  test    rdx, rdx
0x18003e65f  jz      short loc_18003E666
0x18003e661  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e666  test    ebx, ebx
0x18003e668  jns     short loc_18003E69D
0x18003e66a  mov     edx, 1EDh; void *
0x18003e66f  mov     rcx, [rbp+5Fh]; this
0x18003e673  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003e67a  mov     r9d, ebx; char *
0x18003e67d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e682  mov     rdx, [rbp+57h+var_C0]
0x18003e686  mov     [rbp+57h+var_C0], r14
0x18003e68a  test    rdx, rdx
0x18003e68d  jz      loc_18003E59D
0x18003e693  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e698  jmp     loc_18003E59D
0x18003e69d  mov     rcx, [rbp+57h+var_C0]; unsigned __int16 *
0x18003e6a1  lea     rdx, [rbp+57h+var_80.Logon.Password]; struct _UNICODE_STRING *
0x18003e6a5  call    ?UnicodeStringStringHijack@@YAJPEBGPEAU_UNICODE_STRING@@@Z; UnicodeStringStringHijack(ushort const *,_UNICODE_STRING *)
0x18003e6aa  mov     ebx, eax
0x18003e6ac  test    eax, eax
0x18003e6ae  jns     short loc_18003E6B7
0x18003e6b0  mov     edx, 1EEh
0x18003e6b5  jmp     short loc_18003E66F
0x18003e6b7  lea     rax, [rbp+57h+pv]
0x18003e6bb  mov     [rbp+57h+arg_10], r14d
0x18003e6bf  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x18003e6c3  mov     [rbp+57h+var_B8], rax
0x18003e6c7  lea     rdx, [rbp+57h+var_B0]; unsigned __int8 **
0x18003e6cb  mov     [rbp+57h+pv], r14
0x18003e6cf  lea     rcx, [rbp+57h+var_80]; struct _KERB_INTERACTIVE_UNLOCK_LOGON *
0x18003e6d3  mov     [rbp+57h+var_B0], r14
0x18003e6d7  mov     [rbp+57h+var_A8], 1
0x18003e6db  call    ?KerbInteractiveUnlockLogonPack@@YAJAEBU_KERB_INTERACTIVE_UNLOCK_LOGON@@PEAPEAEPEAK@Z; KerbInteractiveUnlockLogonPack(_KERB_INTERACTIVE_UNLOCK_LOGON const &,uchar * *,ulong *)
0x18003e6e0  lea     rcx, [rbp+57h+var_B8]
0x18003e6e4  mov     edi, eax
0x18003e6e6  call    ??1?$out_param_t@V?$unique_ptr@EUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::cotaskmem_secure_deleter>>(void)
0x18003e6eb  test    edi, edi
0x18003e6ed  jns     loc_18003E7EC
0x18003e6f3  mov     rcx, [rbp+5Fh]; this
0x18003e6f7  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003e6fe  mov     r9d, edi; char *
0x18003e701  mov     edx, 1F3h; void *
0x18003e706  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e70b  mov     rbx, [rbp+57h+pv]
0x18003e70f  mov     [rbp+57h+pv], r14
0x18003e713  test    rbx, rbx
0x18003e716  jz      short loc_18003E775
0x18003e718  lea     rdx, [rbp+57h+ppMalloc]; ppMalloc
0x18003e71c  mov     [rbp+57h+ppMalloc], r14
0x18003e720  mov     ecx, 1; dwMemContext
0x18003e725  call    cs:__imp_CoGetMalloc
0x18003e72b  test    eax, eax
0x18003e72d  js      short loc_18003E76C
0x18003e72f  mov     rcx, [rbp+57h+ppMalloc]
0x18003e733  mov     rdx, rbx
0x18003e736  mov     rax, [rcx]
0x18003e739  mov     rax, [rax+30h]
0x18003e73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e742  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e746  jz      short loc_18003E75C
0x18003e748  mov     rcx, rbx
0x18003e74b  test    rax, rax
0x18003e74e  jz      short loc_18003E75C
0x18003e750  mov     [rcx], r14b
0x18003e753  inc     rcx
0x18003e756  sub     rax, 1
0x18003e75a  jnz     short loc_18003E750
0x18003e75c  mov     rcx, [rbp+57h+ppMalloc]
0x18003e760  mov     rax, [rcx]
0x18003e763  mov     rax, [rax+10h]
0x18003e767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e76c  mov     rcx, rbx; pv
0x18003e76f  call    cs:__imp_CoTaskMemFree
0x18003e775  mov     rdx, [rbp+57h+var_C0]
0x18003e779  mov     [rbp+57h+var_C0], r14
0x18003e77d  test    rdx, rdx
0x18003e780  jz      short loc_18003E787
0x18003e782  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e787  mov     rdx, [rbp+57h+var_D0]
0x18003e78b  mov     [rbp+57h+var_D0], r14
0x18003e78f  test    rdx, rdx
0x18003e792  jz      short loc_18003E799
0x18003e794  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e799  mov     rdx, [rbp+57h+var_C8]
0x18003e79d  mov     [rbp+57h+var_C8], r14
0x18003e7a1  test    rdx, rdx
0x18003e7a4  jz      short loc_18003E7AB
0x18003e7a6  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e7ab  mov     rdx, [rbp+57h+arg_18]
0x18003e7af  mov     [rbp+57h+arg_18], r14
0x18003e7b3  test    rdx, rdx
0x18003e7b6  jz      short loc_18003E7BD
0x18003e7b8  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e7bd  mov     rdx, [rsp+110h+var_E0]
0x18003e7c2  mov     [rsp+110h+var_E0], r14
0x18003e7c7  test    rdx, rdx
0x18003e7ca  jz      short loc_18003E7D1
0x18003e7cc  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e7d1  mov     rdx, [rsp+110h+var_D8]
0x18003e7d6  mov     [rsp+110h+var_D8], r14
0x18003e7db  test    rdx, rdx
0x18003e7de  jz      short loc_18003E7E5
0x18003e7e0  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003e7e5  mov     eax, edi
0x18003e7e7  jmp     loc_18003E8C7
0x18003e7ec  lea     rcx, [rbp+57h+ppMalloc]; unsigned int *
0x18003e7f0  mov     dword ptr [rbp+57h+ppMalloc], r14d
0x18003e7f4  call    ?GetNegoAuthPackageId@@YAJPEAK@Z; GetNegoAuthPackageId(ulong *)
0x18003e7f9  mov     ebx, eax
0x18003e7fb  test    eax, eax
0x18003e7fd  jns     short loc_18003E832
0x18003e7ff  mov     rcx, [rbp+5Fh]; this
0x18003e803  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003e80a  mov     r9d, eax; char *
0x18003e80d  mov     edx, 1F7h; void *
0x18003e812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e817  mov     rdx, [rbp+57h+pv]
0x18003e81b  mov     [rbp+57h+pv], r14
0x18003e81f  test    rdx, rdx
0x18003e822  jz      loc_18003E682
0x18003e828  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
  ... truncated ...
```
