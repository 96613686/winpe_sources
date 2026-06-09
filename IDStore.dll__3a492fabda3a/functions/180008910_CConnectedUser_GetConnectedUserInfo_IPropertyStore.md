# CConnectedUser::GetConnectedUserInfo(IPropertyStore * *)

- ea: `0x180008910`
- end: `0x180009c1c`
- name: `?GetConnectedUserInfo@CConnectedUser@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `4876`
- prototype: `__int64 __fastcall(CConnectedUser *this, struct IPropertyStore **, __int64, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003560`
- `0x180008910`
- `0x180009c30`
- `0x18000dff0`
- `0x18000fb96`
- `0x180014430`
- `0x1800144b4`
- `0x1800144f4`
- `0x1800145a0`
- `0x1800152b0`
- `0x1800183dc`
- `0x1800191ac`
- `0x180019210`
- `0x180019722`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008b81`
- `msvcrt!memcpy_s` at `0x180008d4f`
- `msvcrt!memcpy_s` at `0x180008f6c`
- `msvcrt!memcpy_s` at `0x180009283`
- `msvcrt!memcpy_s` at `0x180008b81`
- `msvcrt!memcpy_s` at `0x180008d4f`
- `msvcrt!memcpy_s` at `0x180008f6c`
- `msvcrt!memcpy_s` at `0x180009283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000908a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000908a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008b59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008d24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180009256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008b59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008d24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180009256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008fa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800091a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800092c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008fa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800091a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800092c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008b20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008c33`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008dfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008eef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009011`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000903d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009322`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008b20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008c33`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008dfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008eef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009011`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000903d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008efa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000909a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008efa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000909a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180008e48`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000916e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180008e48`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000916e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800089e1`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800089e1`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180008ae0`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180008ae0`
- `SAMLIB!SamRidToSid` at `0x180009156`
- `SAMLIB!SamRidToSid` at `0x180009156`
- `SAMLIB!SamQueryInformationUser` at `0x180008a61`
- `SAMLIB!SamQueryInformationUser` at `0x180008a80`
- `SAMLIB!SamQueryInformationUser` at `0x180008a61`
- `SAMLIB!SamQueryInformationUser` at `0x180008a80`
- `SAMLIB!SamFreeMemory` at `0x180009062`
- `SAMLIB!SamFreeMemory` at `0x180009077`
- `SAMLIB!SamFreeMemory` at `0x1800090af`
- `SAMLIB!SamFreeMemory` at `0x180009062`
- `SAMLIB!SamFreeMemory` at `0x180009077`
- `SAMLIB!SamFreeMemory` at `0x1800090af`
- `SAMLIB!SamCloseHandle` at `0x18000904d`
- `SAMLIB!SamCloseHandle` at `0x18000904d`
- `SAMLIB!SamOpenUser` at `0x180008a44`
- `SAMLIB!SamOpenUser` at `0x180008a44`

## pseudocode

```c
__int64 __fastcall CConnectedUser::GetConnectedUserInfo(
        CConnectedUser *this,
        struct IPropertyStore **a2,
        __int64 a3,
        int a4)
{
  CIdentityProfileHandler *v6; // rcx
  void *v7; // rdi
  HRESULT v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  const struct _GUID *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rax
  int v16; // eax
  int v17; // ebx
  const struct _GUID *v18; // rbx
  __int64 v19; // rax
  int LastError; // eax
  const void *const *v21; // rsi
  __int64 v22; // rcx
  unsigned int v23; // r15d
  __int64 v24; // r14
  void *v25; // rbx
  unsigned __int64 v26; // rsi
  unsigned __int64 v27; // rax
  SIZE_T v28; // r12
  void *v29; // rax
  void *v30; // r14
  int v31; // eax
  const void *const *v32; // r14
  int v33; // eax
  unsigned int v34; // r12d
  unsigned int v35; // ecx
  rsize_t v36; // r15
  unsigned int v37; // r12d
  LPVOID v38; // rax
  unsigned __int64 v39; // rax
  SIZE_T v40; // r14
  void *v41; // rax
  void *v42; // rbx
  unsigned int *v43; // rcx
  __int64 v44; // rbx
  LPWSTR v45; // rbx
  unsigned __int64 v46; // rax
  SIZE_T v47; // r15
  void *v48; // rax
  void *v49; // r14
  const void *const *v50; // rbx
  int v51; // eax
  unsigned int v52; // eax
  rsize_t v53; // r14
  LPVOID v54; // rax
  unsigned __int64 v55; // rax
  SIZE_T v56; // r14
  void *v57; // rax
  void *v58; // rbx
  CIdentityProfileHandler *v59; // rcx
  int v60; // edx
  __int64 v61; // r8
  int v62; // r9d
  int v63; // ecx
  int v64; // ebx
  CIdentityProfileHandler *v65; // rcx
  unsigned int v67; // ebx
  __int64 v68; // rax
  int v69; // eax
  LPWSTR v70; // rbx
  size_t v71; // r14
  void *v72; // rax
  void *v73; // rsi
  struct IPropertyStore *v74; // rax
  const void *const *v75; // rbx
  int v76; // eax
  unsigned int v77; // r14d
  LPVOID v78; // rax
  unsigned __int64 v79; // rax
  SIZE_T v80; // r14
  void *v81; // rax
  void *v82; // rbx
  __int64 v83; // r9
  __int64 v84; // rdx
  __int64 v85; // r9
  CIdentityProfileHandler *v86; // rcx
  __int64 v87; // rdx
  unsigned int v88; // ecx
  unsigned int v89; // ecx
  struct IPropertyStore *v90; // rax
  unsigned int v91; // r14d
  int v92; // eax
  CIdentityProfileHandler *v93; // rcx
  __int64 v94; // rdx
  HRESULT ConnectedAADUserInfo; // [rsp+30h] [rbp-D0h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v97; // [rsp+48h] [rbp-B8h]
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v99; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v101; // [rsp+68h] [rbp-98h] BYREF
  __int64 v102; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  CConnectedUser *v104; // [rsp+80h] [rbp-80h]
  _QWORD v105[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v106; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v107[40]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v108[40]; // [rsp+100h] [rbp+0h] BYREF

  v104 = this;
  ppv = 0;
  ConnectedAADUserInfo = 0;
  *(_OWORD *)ppropvar = 0;
  v97 = 0;
  v102 = 0;
  v99 = 0;
  v101 = 0;
  StringSid = 0;
  Sid = 0;
  v105[1] = "CConnectedUser::GetConnectedUserInfo";
  v105[0] = &ConnectedAADUserInfo;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUser::GetConnectedUserInfo");
    v6 = WPP_GLOBAL_Control;
  }
  *(_OWORD *)ppropvar = 0;
  v97 = 0;
  if ( !a2 )
  {
    v64 = -2147467261;
    ConnectedAADUserInfo = -2147467261;
    if ( v6 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v6 + 2), 16, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, 2147500035LL);
      v64 = ConnectedAADUserInfo;
      v6 = WPP_GLOBAL_Control;
    }
    if ( v64 < 0 )
    {
      if ( v6 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      {
LABEL_124:
        if ( ppv )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        return (unsigned int)v64;
      }
      if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
      {
        WPP_SF_sL(*((_QWORD *)v6 + 2), (_DWORD)a2, a3, (unsigned int)"CConnectedUser::GetConnectedUserInfo", v64);
        v6 = WPP_GLOBAL_Control;
      }
    }
    if ( v6 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x400) != 0 )
      WPP_SF_s(*((_QWORD *)v6 + 2), 12, a3, "CConnectedUser::GetConnectedUserInfo");
    goto LABEL_124;
  }
  v7 = 0;
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)v6, (int)&GetUserInfoStart, a3, a4, &v106);
  v8 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  ConnectedAADUserInfo = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
        (unsigned int)v8);
    }
    goto LABEL_75;
  }
  v11 = (const struct _GUID *)((char *)this + 68);
  v12 = *(_QWORD *)((char *)this + 68) - 0x4967A148B16898C6LL;
  if ( *(_QWORD *)((char *)this + 68) == 0x4967A148B16898C6LL )
    v12 = *(_QWORD *)((char *)this + 76) - 0x2085DA55D7647191LL;
  if ( !v12 )
  {
    ConnectedAADUserInfo = CConnectedUser::GetConnectedAADUserInfo(this, (struct IPropertyStore *)ppv);
    v90 = (struct IPropertyStore *)ppv;
    ppv = 0;
    *a2 = v90;
    goto LABEL_75;
  }
  v13 = *((_QWORD *)this + 11);
  if ( v13 )
  {
    v14 = *((_DWORD *)this + 16);
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
    v16 = SamOpenUser(v15, 0x2000000, v14, &v102);
    if ( v16 < 0 )
    {
      v92 = v16 | 0x10000000;
      ConnectedAADUserInfo = v92;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
          *((unsigned int *)this + 16),
          v92);
      }
      goto LABEL_75;
    }
    v17 = SamQueryInformationUser(v102, 28, &v99);
    if ( v17 < 0 )
    {
      v93 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_206;
      }
      v94 = 20;
    }
    else
    {
      v17 = SamQueryInformationUser(v102, 21, &v101);
      if ( v17 >= 0 )
      {
        if ( (*v99 & 0x70000) != 0x70000 )
        {
          ConnectedAADUserInfo = -2147019873;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_DD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
              *v99,
              -2147019873);
          }
          goto LABEL_75;
        }
        if ( (*(_BYTE *)(v101 + 284) & 4) == 0 )
        {
          ConnectedAADUserInfo = -2147019873;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_DD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
              *(unsigned int *)(v101 + 284),
              -2147019873);
          }
          goto LABEL_75;
        }
        v18 = (const struct _GUID *)(v99 + 24);
        v19 = *((_QWORD *)v99 + 12) - *(_QWORD *)&v11->Data1;
        if ( !v19 )
          v19 = *((_QWORD *)v99 + 13) - *(_QWORD *)((char *)this + 76);
        if ( v19 )
        {
          ConnectedAADUserInfo = -2147019873;
          memset_0(v107, 0, 0x4Eu);
          memset_0(v108, 0, 0x4Eu);
          IDGuidToString(v18, v107, 0x27u);
          IDGuidToString(v11, v108, 0x27u);
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              (unsigned int)WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
              (unsigned int)v107,
              (__int64)v108,
              ConnectedAADUserInfo);
          }
          goto LABEL_75;
        }
        ConnectedAADUserInfo = InitPropVariantFromCLSID((const IID *const)((char *)this + 68), ppropvar);
        if ( ConnectedAADUserInfo < 0 )
        {
          memset_0(v107, 0, 0x4Eu);
          IDGuidToString((const struct _GUID *)((char *)this + 68), v107, 0x27u);
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              (unsigned int)WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
              (unsigned int)v107,
              ConnectedAADUserInfo);
          }
          goto LABEL_75;
        }
        LastError = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                      ppv,
                      &PKEY_Identity_ProviderID,
                      ppropvar);
        ConnectedAADUserInfo = LastError;
        if ( LastError < 0 )
        {
          v59 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v84 = 26;
            goto LABEL_215;
          }
          goto LABEL_75;
        }
        PropVariantClear(ppropvar);
        v21 = (const void *const *)(v99 + 20);
        if ( v99 == (unsigned int *)-80LL
          || (v22 = *(unsigned __int16 *)v21, (unsigned __int16)v22 > *((_WORD *)v99 + 41))
          || (v23 = v22 + 2, (((_BYTE)v22 + 2) & 1) != 0) )
        {
          v83 = 2147942487LL;
        }
        else
        {
          v24 = *(unsigned __int16 *)v21;
          v25 = CoTaskMemRealloc(0, v22 + 2);
          if ( v25 )
          {
            if ( *(_WORD *)v21 )
              memcpy_s(v25, v24 + 2, v21[1], *(unsigned __int16 *)v21);
            *((_WORD *)v25 + ((unsigned __int64)*(unsigned __int16 *)v21 >> 1)) = 0;
            v7 = v25;
            ConnectedAADUserInfo = 0;
            v26 = -1;
            v27 = -1;
            do
              ++v27;
            while ( *((_WORD *)v25 + v27) );
            if ( v27 >= 0x7FFFFFFF || (v28 = 2 * v27 + 2, v29 = CoTaskMemAlloc(v28), (v30 = v29) == 0) )
            {
              *(_OWORD *)ppropvar = 0;
              v97 = 0;
              ConnectedAADUserInfo = -2147024882;
              v86 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              {
                goto LABEL_75;
              }
              v87 = 28;
              v85 = 2147942414LL;
              goto LABEL_221;
            }
            memcpy_0(v29, v25, v28);
            LOWORD(ppropvar[0]) = 31;
            ppropvar[1] = v30;
            ConnectedAADUserInfo = 0;
            v31 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                    ppv,
                    &PKEY_IdentityProvider_Name,
                    ppropvar);
            ConnectedAADUserInfo = v31;
            if ( v31 < 0 )
            {
              v86 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              {
                goto LABEL_75;
              }
              v87 = 29;
              v85 = (unsigned int)v31;
              goto LABEL_221;
            }
            PropVariantClear(ppropvar);
            v32 = (const void *const *)(v99 + 16);
            if ( v99 == (unsigned int *)-64LL
              || (v33 = *(unsigned __int16 *)v32, (unsigned __int16)v33 > *((_WORD *)v99 + 33))
              || (v34 = v33 + 2, (((_BYTE)v33 + 2) & 1) != 0) )
            {
              v85 = 2147942487LL;
            }
            else
            {
              v35 = v23 >> 1;
              v36 = v34;
              if ( 2 * (unsigned __int64)v35 >= v34 )
              {
                v37 = v35;
                goto LABEL_43;
              }
              v38 = CoTaskMemRealloc(v25, v34);
              if ( v38 )
              {
                v37 = v34 >> 1;
                v7 = v38;
LABEL_43:
                if ( *(_WORD *)v32 )
                  memcpy_s(v7, v36, v32[1], *(unsigned __int16 *)v32);
                *((_WORD *)v7 + ((unsigned __int64)*(unsigned __int16 *)v32 >> 1)) = 0;
                ConnectedAADUserInfo = 0;
                v39 = -1;
                do
                  ++v39;
                while ( *((_WORD *)v7 + v39) );
                if ( v39 >= 0x7FFFFFFF || (v40 = 2 * v39 + 2, v41 = CoTaskMemAlloc(v40), (v42 = v41) == 0) )
                {
                  *(_OWORD *)ppropvar = 0;
                  v97 = 0;
                  ConnectedAADUserInfo = -2147024882;
                  v59 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    v84 = 31;
                    v83 = 2147942414LL;
                    goto LABEL_146;
                  }
                  goto LABEL_75;
                }
                memcpy_0(v41, v7, v40);
                LOWORD(ppropvar[0]) = 31;
                ppropvar[1] = v42;
                ConnectedAADUserInfo = 0;
                LastError = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                              ppv,
                              &PKEY_Identity_UserName,
                              ppropvar);
                ConnectedAADUserInfo = LastError;
                if ( LastError < 0 )
                {
                  v59 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    v84 = 32;
                    goto LABEL_215;
                  }
                  goto LABEL_75;
                }
                PropVariantClear(ppropvar);
                v43 = v99;
                if ( (*v99 & 0x400000) != 0 && *((_QWORD *)v99 + 19) )
                {
                  LOWORD(ppropvar[0]) = 65;
                  v97 = *((_QWORD *)v99 + 19);
                  LODWORD(ppropvar[1]) = v99[36];
                  LastError = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                ppv,
                                &PKEY_Identity_ProviderData,
                                ppropvar);
                  ConnectedAADUserInfo = LastError;
                  *(_OWORD *)ppropvar = 0;
                  v97 = 0;
                  if ( LastError < 0 )
                  {
                    v59 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      v84 = 33;
                      goto LABEL_215;
                    }
                    goto LABEL_75;
                  }
                  v43 = v99;
                }
                v44 = v101;
                if ( (*(_BYTE *)(v101 + 284) & 2) == 0 )
                {
LABEL_52:
                  if ( (*v43 & 0x100000) == 0 || !v43[32] )
                  {
LABEL_97:
                    v67 = *(_DWORD *)(v44 + 272);
                    v68 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v104 + 11) + 24LL))(*((_QWORD *)v104 + 11));
                    v69 = SamRidToSid(v68, v67, &Sid);
                    if ( v69 < 0 )
                    {
                      LastError = v69 | 0x10000000;
                      ConnectedAADUserInfo = LastError;
                      v59 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                      {
                        v84 = 43;
LABEL_215:
                        v83 = (unsigned int)LastError;
                        goto LABEL_146;
                      }
                    }
                    else if ( ConvertSidToStringSidW(Sid, &StringSid) )
                    {
                      v70 = StringSid;
                      do
                        ++v26;
                      while ( StringSid[v26] );
                      if ( v26 < 0x7FFFFFFF && (v71 = 2 * v26 + 2, v72 = CoTaskMemAlloc(v71), (v73 = v72) != 0) )
                      {
                        memcpy_0(v72, v70, v71);
                        LOWORD(ppropvar[0]) = 31;
                        ppropvar[1] = v73;
                        ConnectedAADUserInfo = 0;
                        LastError = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                      ppv,
                                      &PKEY_Identity_PrimarySid,
                                      ppropvar);
                        ConnectedAADUserInfo = LastError;
                        if ( LastError >= 0 )
                        {
                          v74 = (struct IPropertyStore *)ppv;
                          ppv = 0;
                          *a2 = v74;
                          goto LABEL_75;
                        }
                        v59 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        {
                          v84 = 46;
                          goto LABEL_215;
                        }
                      }
                      else
                      {
                        *(_OWORD *)ppropvar = 0;
                        v97 = 0;
                        ConnectedAADUserInfo = -2147024882;
                        v59 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        {
                          v84 = 45;
                          v83 = 2147942414LL;
                          goto LABEL_146;
                        }
                      }
                    }
                    else
                    {
                      LastError = GetLastError();
                      if ( LastError > 0 )
                        v89 = (unsigned __int16)LastError | 0x80070000;
                      else
                        v89 = LastError;
                      ConnectedAADUserInfo = v89;
                      v59 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                      {
                        v84 = 44;
                        goto LABEL_215;
                      }
                    }
LABEL_75:
                    PropVariantClear(ppropvar);
                    if ( v102 )
                    {
                      SamCloseHandle(v102);
                      v102 = 0;
                    }
                    if ( v99 )
                    {
                      SamFreeMemory(v99);
                      v99 = 0;
                    }
                    if ( v101 )
                    {
                      SamFreeMemory(v101);
                      v101 = 0;
                    }
                    if ( v7 )
                      CoTaskMemFree(v7);
                    if ( StringSid )
                    {
                      LocalFree(StringSid);
                      StringSid = 0;
                    }
                    v63 = (int)Sid;
                    if ( Sid )
                    {
                      SamFreeMemory(Sid);
                      Sid = 0;
                    }
                    if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
                      McGenEventWrite_EventWriteTransfer(v63, (int)&GetUserInfoStop, v61, v62, &v106);
                    v64 = ConnectedAADUserInfo;
                    if ( ConnectedAADUserInfo < 0 )
                    {
                      v65 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
                      {
LABEL_94:
                        if ( ppv )
                          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                        return (unsigned int)v64;
                      }
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                      {
LABEL_91:
                        if ( v65 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)v65 + 7) & 0x400) != 0 )
                        {
                          WPP_SF_s(*((_QWORD *)v65 + 2), 12, v61, "CConnectedUser::GetConnectedUserInfo");
                        }
                        goto LABEL_94;
                      }
                      WPP_SF_sL(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v60,
                        v61,
                        (unsigned int)"CConnectedUser::GetConnectedUserInfo",
                        ConnectedAADUserInfo);
                    }
                    v65 = WPP_GLOBAL_Control;
                    goto LABEL_91;
                  }
                  if ( !ConvertSidToStringSidW(*((PSID *)v43 + 17), &StringSid) )
                  {
                    LastError = GetLastError();
                    if ( LastError > 0 )
                      v88 = (unsigned __int16)LastError | 0x80070000;
                    else
                      v88 = LastError;
                    ConnectedAADUserInfo = v88;
                    v59 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      v84 = 37;
                      goto LABEL_215;
                    }
                    goto LABEL_75;
                  }
                  v45 = StringSid;
                  v46 = -1;
                  do
                    ++v46;
                  while ( StringSid[v46] );
                  if ( v46 < 0x7FFFFFFF )
                  {
                    v47 = 2 * v46 + 2;
                    v48 = CoTaskMemAlloc(v47);
                    v49 = v48;
                    if ( v48 )
                    {
                      memcpy_0(v48, v45, v47);
                      LOWORD(ppropvar[0]) = 31;
                      ppropvar[1] = v49;
                      ConnectedAADUserInfo = 0;
                      LastError = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    &PKEY_Identity_InternetSid,
                                    ppropvar);
                      ConnectedAADUserInfo = LastError;
                      if ( LastError < 0 )
                      {
                        v59 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        {
                          v84 = 39;
                          goto LABEL_215;
                        }
                        goto LABEL_75;
                      }
                      PropVariantClear(ppropvar);
                      LocalFree(StringSid);
                      StringSid = 0;
                      v50 = (const void *const *)(v99 + 28);
                      if ( v99 == (unsigned int *)-112LL
                        || (v51 = *(unsigned __int16 *)v50, (unsigned __int16)v51 > *((_WORD *)v99 + 57))
                        || (v52 = v51 + 2, (v52 & 1) != 0) )
                      {
                        v83 = 2147942487LL;
                      }
                      else
                      {
                        v53 = v52;
                        if ( 2 * (unsigned __int64)v37 >= v52 )
                        {
LABEL_66:
                          if ( *(_WORD *)v50 )
                            memcpy_s(v7, v53, v50[1], *(unsigned __int16 *)v50);
                          *((_WORD *)v7 + ((unsigned __int64)*(unsigned __int16 *)v50 >> 1)) = 0;
                          ConnectedAADUserInfo = 0;
                          v55 = -1;
                          do
                            ++v55;
                          while ( *((_WORD *)v7 + v55) );
                          if ( v55 >= 0x7FFFFFFF || (v56 = 2 * v55 + 2, v57 = CoTaskMemAlloc(v56), (v58 = v57) == 0) )
                          {
                            *(_OWORD *)ppropvar = 0;
                            v97 = 0;
                            ConnectedAADUserInfo = -2147024882;
                            v59 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                            {
                              v84 = 41;
                              v83 = 2147942414LL;
                              goto LABEL_146;
                            }
                            goto LABEL_75;
                          }
                          memcpy_0(v57, v7, v56);
                          LOWORD(ppropvar[0]) = 31;
                          ppropvar[1] = v58;
                          ConnectedAADUserInfo = 0;
                          LastError = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                        ppv,
                                        &PKEY_Identity_UniqueID,
                                        ppropvar);
                          ConnectedAADUserInfo = LastError;
                          if ( LastError < 0 )
                          {
                            v59 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                            {
                              v84 = 42;
                              goto LABEL_215;
                            }
                            goto LABEL_75;
                          }
                          PropVariantClear(ppropvar);
                          v44 = v101;
                          goto LABEL_97;
                        }
                        v54 = CoTaskMemRealloc(v7, v52);
                        if ( v54 )
                        {
                          v7 = v54;
                          goto LABEL_66;
                        }
                        v83 = 2147942414LL;
                      }
                      ConnectedAADUserInfo = v83;
                      v59 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                      {
                        goto LABEL_75;
                      }
                      v84 = 40;
LABEL_146:
                      WPP_SF_d(*((_QWORD *)v59 + 2), v84, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, v83);
                      goto LABEL_75;
                    }
                  }
                  *(_OWORD *)ppropvar = 0;
                  v97 = 0;
                  ConnectedAADUserInfo = -2147024882;
                  v86 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                  {
                    goto LABEL_75;
                  }
                  v87 = 38;
                  v85 = 2147942414LL;
LABEL_221:
                  WPP_SF_d(*((_QWORD *)v86 + 2), v87, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, v85);
                  goto LABEL_75;
                }
                v75 = (const void *const *)(v101 + 64);
                if ( v101 == -64
                  || (v76 = *(unsigned __int16 *)v75, (unsigned __int16)v76 > *(_WORD *)(v101 + 66))
                  || (v77 = v76 + 2, (((_BYTE)v76 + 2) & 1) != 0) )
                {
                  v83 = 2147942487LL;
                }
                else
                {
                  if ( 2 * (unsigned __int64)v37 >= v77 )
                  {
LABEL_111:
                    if ( *(_WORD *)v75 )
                      memcpy_s(v7, v77, v75[1], *(unsigned __int16 *)v75);
                    *((_WORD *)v7 + ((unsigned __int64)*(unsigned __int16 *)v75 >> 1)) = 0;
                    ConnectedAADUserInfo = 0;
                    v79 = -1;
                    do
                      ++v79;
                    while ( *((_WORD *)v7 + v79) );
                    if ( v79 >= 0x7FFFFFFF || (v80 = 2 * v79 + 2, v81 = CoTaskMemAlloc(v80), (v82 = v81) == 0) )
                    {
                      *(_OWORD *)ppropvar = 0;
                      v97 = 0;
                      ConnectedAADUserInfo = -2147024882;
                      v59 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                      {
                        v84 = 35;
                        v83 = 2147942414LL;
                        goto LABEL_146;
                      }
                      goto LABEL_75;
                    }
                    memcpy_0(v81, v7, v80);
                    LOWORD(ppropvar[0]) = 31;
                    ppropvar[1] = v82;
                    ConnectedAADUserInfo = 0;
                    ConnectedAADUserInfo = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                             ppv,
                                             &PKEY_Identity_DisplayName,
                                             ppropvar);
                    PropVariantClear(ppropvar);
                    v83 = (unsigned int)ConnectedAADUserInfo;
                    if ( ConnectedAADUserInfo < 0 )
                    {
                      v59 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                      {
                        goto LABEL_75;
                      }
                      v84 = 36;
                      goto LABEL_146;
                    }
                    v43 = v99;
                    v44 = v101;
                    goto LABEL_52;
                  }
                  v78 = CoTaskMemRealloc(v7, v77);
                  if ( v78 )
                  {
                    v37 = v77 >> 1;
                    v7 = v78;
                    goto LABEL_111;
                  }
                  v83 = 2147942414LL;
                }
                ConnectedAADUserInfo = v83;
                v59 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                {
                  goto LABEL_75;
                }
                v84 = 34;
                goto LABEL_146;
              }
              v85 = 2147942414LL;
            }
            ConnectedAADUserInfo = v85;
            v86 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            {
              goto LABEL_75;
            }
            v87 = 30;
            goto LABEL_221;
          }
          v83 = 2147942414LL;
        }
        ConnectedAADUserInfo = v83;
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_75;
        }
        v84 = 27;
        goto LABEL_146;
      }
      v93 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_206:
        ConnectedAADUserInfo = v17 | 0x10000000;
        goto LABEL_75;
      }
      v94 = 21;
    }
    WPP_SF_d(*((_QWORD *)v93 + 2), v94, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, (unsigned int)v17);
    goto LABEL_206;
  }
  v91 = -2147019873;
  ConnectedAADUserInfo = -2147019873;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, 2147947423LL);
    v91 = ConnectedAADUserInfo;
  }
  CLogBlock::~CLogBlock((CLogBlock *)v105, v9, v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v91;
}

```

## disassembly

```asm
0x180008910  mov     [rsp-8+arg_10], rbx
0x180008915  push    rbp
0x180008916  push    rsi
0x180008917  push    rdi
0x180008918  push    r12
0x18000891a  push    r13
0x18000891c  push    r14
0x18000891e  push    r15
0x180008920  lea     rbp, [rsp-60h]
0x180008925  sub     rsp, 160h
0x18000892c  mov     rax, cs:__security_cookie
0x180008933  xor     rax, rsp
0x180008936  mov     [rbp+90h+var_40], rax
0x18000893a  mov     r13, rdx
0x18000893d  mov     r14, rcx
0x180008940  mov     [rbp+90h+var_110], rcx
0x180008944  xor     r15d, r15d
0x180008947  mov     [rsp+190h+ppv], r15
0x18000894c  mov     [rsp+190h+var_160], r15d
0x180008951  xorps   xmm0, xmm0
0x180008954  xor     eax, eax
0x180008956  movups  xmmword ptr [rsp+190h+ppropvar], xmm0
0x18000895b  mov     [rsp+190h+var_148], rax
0x180008960  mov     [rsp+190h+var_120], r15
0x180008965  mov     [rsp+190h+var_138], r15
0x18000896a  mov     [rsp+190h+var_128], r15
0x18000896f  mov     [rsp+190h+StringSid], r15
0x180008974  mov     [rsp+190h+Sid], r15
0x180008979  lea     rsi, aCconnecteduser_0; "CConnectedUser::GetConnectedUserInfo"
0x180008980  mov     [rbp+90h+var_100], rsi
0x180008984  lea     rax, [rsp+190h+var_160]
0x180008989  mov     [rbp+90h+var_108], rax
0x18000898d  lea     r12, WPP_GLOBAL_Control
0x180008994  mov     rcx, cs:WPP_GLOBAL_Control; int
0x18000899b  cmp     rcx, r12
0x18000899e  jz      short loc_1800089AD
0x1800089a0  test    dword ptr [rcx+1Ch], 400h
0x1800089a7  jnz     loc_18000978B
0x1800089ad  xorps   xmm0, xmm0
0x1800089b0  xor     eax, eax
0x1800089b2  movups  xmmword ptr [rsp+190h+ppropvar], xmm0
0x1800089b7  mov     [rsp+190h+var_148], rax
0x1800089bc  test    r13, r13
0x1800089bf  jz      loc_180009345
0x1800089c5  mov     rdi, r15
0x1800089c8  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x1800089cf  jnz     loc_1800097F3
0x1800089d5  lea     rdx, [rsp+190h+ppv]; ppv
0x1800089da  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800089e1  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800089e7  mov     [rsp+190h+var_160], eax
0x1800089eb  test    eax, eax
0x1800089ed  js      loc_180009450
0x1800089f3  lea     rsi, [r14+44h]
0x1800089f7  mov     rax, [rsi]
0x1800089fa  sub     rax, qword ptr cs:xmmword_18001E7E0
0x180008a01  jnz     short loc_180008A0E
0x180008a03  mov     rax, [rsi+8]
0x180008a07  sub     rax, qword ptr cs:xmmword_18001E7E0+8
0x180008a0e  test    rax, rax
0x180008a11  jz      loc_18000980D
0x180008a17  mov     rcx, [r14+58h]
0x180008a1b  test    rcx, rcx
0x180008a1e  jz      loc_180009831
0x180008a24  mov     ebx, [r14+40h]
0x180008a28  mov     rax, [rcx]
0x180008a2b  mov     rax, [rax+18h]
0x180008a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a34  lea     r9, [rsp+190h+var_120]
0x180008a39  mov     r8d, ebx
0x180008a3c  mov     edx, 2000000h
0x180008a41  mov     rcx, rax
0x180008a44  call    cs:__imp_SamOpenUser
0x180008a4a  test    eax, eax
0x180008a4c  js      loc_180009889
0x180008a52  lea     r8, [rsp+190h+var_138]
0x180008a57  mov     edx, 1Ch
0x180008a5c  mov     rcx, [rsp+190h+var_120]
0x180008a61  call    cs:__imp_SamQueryInformationUser
0x180008a67  mov     ebx, eax
0x180008a69  test    eax, eax
0x180008a6b  js      loc_1800098BD
0x180008a71  lea     r8, [rsp+190h+var_128]
0x180008a76  mov     edx, 15h
0x180008a7b  mov     rcx, [rsp+190h+var_120]
0x180008a80  call    cs:__imp_SamQueryInformationUser
0x180008a86  mov     ebx, eax
0x180008a88  test    eax, eax
0x180008a8a  js      loc_1800098FB
0x180008a90  mov     r8, [rsp+190h+var_138]
0x180008a95  mov     eax, [r8]
0x180008a98  and     eax, 70000h
0x180008a9d  cmp     eax, 70000h
0x180008aa2  jnz     loc_1800095F2
0x180008aa8  mov     r9, [rsp+190h+var_128]
0x180008aad  test    byte ptr [r9+11Ch], 4
0x180008ab5  jz      loc_1800096B1
0x180008abb  lea     rbx, [r8+60h]
0x180008abf  mov     rax, [rbx]
0x180008ac2  sub     rax, [rsi]
0x180008ac5  jnz     short loc_180008ACF
0x180008ac7  mov     rax, [rbx+8]
0x180008acb  sub     rax, [rsi+8]
0x180008acf  test    rax, rax
0x180008ad2  jnz     loc_180008C84
0x180008ad8  lea     rdx, [rsp+190h+ppropvar]; ppropvar
0x180008add  mov     rcx, rsi; clsid
0x180008ae0  call    cs:__imp_InitPropVariantFromCLSID
0x180008ae6  mov     [rsp+190h+var_160], eax
0x180008aea  test    eax, eax
0x180008aec  js      loc_18000990F
0x180008af2  mov     rcx, [rsp+190h+ppv]
0x180008af7  mov     rax, [rcx]
0x180008afa  lea     r8, [rsp+190h+ppropvar]
0x180008aff  lea     rdx, PKEY_Identity_ProviderID
0x180008b06  mov     rax, [rax+30h]
0x180008b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0f  mov     [rsp+190h+var_160], eax
0x180008b13  test    eax, eax
0x180008b15  js      loc_180009021
0x180008b1b  lea     rcx, [rsp+190h+ppropvar]; pvar
0x180008b20  call    cs:__imp_PropVariantClear
0x180008b26  mov     rsi, [rsp+190h+var_138]
0x180008b2b  add     rsi, 50h ; 'P'
0x180008b2f  jz      loc_1800094BD
0x180008b35  movzx   ecx, word ptr [rsi]
0x180008b38  cmp     cx, [rsi+2]
0x180008b3c  ja      loc_1800094BD
0x180008b42  lea     r15d, [rcx+2]
0x180008b46  test    r15b, 1
0x180008b4a  jnz     loc_180009990
0x180008b50  mov     r14d, ecx
0x180008b53  lea     rdx, [rcx+2]; cb
0x180008b57  xor     ecx, ecx; pv
0x180008b59  call    cs:__imp_CoTaskMemRealloc
0x180008b5f  mov     rbx, rax
0x180008b62  test    rax, rax
0x180008b65  jz      loc_180009998
0x180008b6b  movzx   eax, word ptr [rsi]
0x180008b6e  test    ax, ax
0x180008b71  jz      short loc_180008B87
0x180008b73  mov     r9d, eax; SourceSize
0x180008b76  mov     r8, [rsi+8]; Source
0x180008b7a  lea     rdx, [r14+2]; DestinationSize
0x180008b7e  mov     rcx, rbx; Destination
0x180008b81  call    cs:__imp_memcpy_s
0x180008b87  movzx   ecx, word ptr [rsi]
0x180008b8a  shr     rcx, 1
0x180008b8d  xor     eax, eax
0x180008b8f  mov     [rbx+rcx*2], ax
0x180008b93  mov     rdi, rbx
0x180008b96  mov     [rsp+190h+var_160], eax
0x180008b9a  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180008ba1  mov     rax, rsi
0x180008ba4  inc     rax
0x180008ba7  cmp     word ptr [rbx+rax*2], 0
0x180008bac  jnz     short loc_180008BA4
0x180008bae  cmp     rax, 7FFFFFFFh
0x180008bb4  jnb     loc_180009BB3
0x180008bba  lea     r12, ds:2[rax*2]
0x180008bc2  mov     rcx, r12; cb
0x180008bc5  call    cs:__imp_CoTaskMemAlloc
0x180008bcb  mov     r14, rax
0x180008bce  test    rax, rax
0x180008bd1  jz      loc_180009BAC
0x180008bd7  mov     r8, r12; Size
0x180008bda  mov     rdx, rbx; Src
0x180008bdd  mov     rcx, rax; void *
0x180008be0  call    memcpy_0
0x180008be5  mov     eax, 1Fh
0x180008bea  mov     word ptr [rsp+190h+ppropvar], ax
0x180008bef  mov     dword ptr [rsp+190h+ppropvar+8], r14d
0x180008bf4  sar     r14, 20h
0x180008bf8  mov     dword ptr [rsp+190h+ppropvar+0Ch], r14d
0x180008bfd  mov     [rsp+190h+var_160], 0
0x180008c05  mov     rcx, [rsp+190h+ppv]
0x180008c0a  mov     rax, [rcx]
0x180008c0d  lea     r8, [rsp+190h+ppropvar]
0x180008c12  lea     rdx, PKEY_IdentityProvider_Name
0x180008c19  mov     rax, [rax+30h]
0x180008c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c22  mov     [rsp+190h+var_160], eax
0x180008c26  test    eax, eax
0x180008c28  js      loc_1800099A6
0x180008c2e  lea     rcx, [rsp+190h+ppropvar]; pvar
0x180008c33  call    cs:__imp_PropVariantClear
0x180008c39  mov     r14, [rsp+190h+var_138]
0x180008c3e  add     r14, 40h ; '@'
0x180008c42  jz      loc_180009487
0x180008c48  movzx   eax, word ptr [r14]
0x180008c4c  cmp     ax, [r14+2]
0x180008c51  ja      loc_180009487
0x180008c57  lea     r12d, [rax+2]
0x180008c5b  test    r12b, 1
0x180008c5f  jnz     loc_180009487
0x180008c65  shr     r15d, 1
0x180008c68  mov     ecx, r15d
0x180008c6b  mov     r15d, r12d
0x180008c6e  mov     eax, ecx
0x180008c70  add     rax, rax
0x180008c73  cmp     rax, r15
0x180008c76  jb      loc_180008D1E
0x180008c7c  mov     r12d, ecx
0x180008c7f  jmp     loc_180008D39
0x180008c84  mov     r14d, 8007139Fh
0x180008c8a  mov     [rsp+190h+var_160], r14d
0x180008c8f  xor     edx, edx; Val
0x180008c91  mov     r8d, 4Eh ; 'N'; Size
0x180008c97  lea     rcx, [rbp+90h+var_E0]; void *
0x180008c9b  call    memset_0
0x180008ca0  xor     edx, edx; Val
0x180008ca2  mov     r8d, 4Eh ; 'N'; Size
0x180008ca8  lea     rcx, [rbp+90h+var_90]; void *
0x180008cac  call    memset_0
0x180008cb1  mov     r8d, 27h ; '''; unsigned int
0x180008cb7  lea     rdx, [rbp+90h+var_E0]; unsigned __int16 *
0x180008cbb  mov     rcx, rbx; struct _GUID *
0x180008cbe  call    ?IDGuidToString@@YAJPEBU_GUID@@PEAGK@Z; IDGuidToString(_GUID const *,ushort *,ulong)
0x180008cc3  mov     r8d, 27h ; '''; unsigned int
0x180008cc9  lea     rdx, [rbp+90h+var_90]; unsigned __int16 *
0x180008ccd  mov     rcx, rsi; struct _GUID *
0x180008cd0  call    ?IDGuidToString@@YAJPEBU_GUID@@PEAGK@Z; IDGuidToString(_GUID const *,ushort *,ulong)
0x180008cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cdc  cmp     rcx, r12
0x180008cdf  jz      loc_180009031
0x180008ce5  test    byte ptr [rcx+1Ch], 4
0x180008ce9  jz      loc_180009031
0x180008cef  mov     edx, 18h
0x180008cf4  mov     eax, [rsp+190h+var_160]
0x180008cf8  mov     [rsp+190h+var_168], eax
0x180008cfc  lea     rax, [rbp+90h+var_90]
0x180008d00  mov     [rsp+190h+var_170], rax
0x180008d05  lea     r9, [rbp+90h+var_E0]
0x180008d09  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180008d10  mov     rcx, [rcx+10h]
0x180008d14  call    WPP_SF_SSD
0x180008d19  jmp     loc_180009031
0x180008d1e  mov     rdx, r15; cb
0x180008d21  mov     rcx, rbx; pv
0x180008d24  call    cs:__imp_CoTaskMemRealloc
0x180008d2a  test    rax, rax
0x180008d2d  jz      loc_1800099EC
0x180008d33  shr     r12d, 1
0x180008d36  mov     rdi, rax
0x180008d39  movzx   eax, word ptr [r14]
0x180008d3d  test    ax, ax
0x180008d40  jz      short loc_180008D55
0x180008d42  mov     r9d, eax; SourceSize
0x180008d45  mov     r8, [r14+8]; Source
0x180008d49  mov     rdx, r15; DestinationSize
0x180008d4c  mov     rcx, rdi; Destination
0x180008d4f  call    cs:__imp_memcpy_s
0x180008d55  movzx   ecx, word ptr [r14]
0x180008d59  shr     rcx, 1
0x180008d5c  xor     r15d, r15d
0x180008d5f  mov     [rdi+rcx*2], r15w
0x180008d64  mov     [rsp+190h+var_160], r15d
0x180008d69  mov     rax, rsi
0x180008d6c  nop     dword ptr [rax+00h]
0x180008d70  inc     rax
0x180008d73  cmp     [rdi+rax*2], r15w
0x180008d78  jnz     short loc_180008D70
0x180008d7a  cmp     rax, 7FFFFFFFh
0x180008d80  jnb     loc_180009B61
0x180008d86  lea     r14, ds:2[rax*2]
0x180008d8e  mov     rcx, r14; cb
0x180008d91  call    cs:__imp_CoTaskMemAlloc
0x180008d97  mov     rbx, rax
0x180008d9a  test    rax, rax
0x180008d9d  jz      loc_180009B61
0x180008da3  mov     r8, r14; Size
0x180008da6  mov     rdx, rdi; Src
0x180008da9  mov     rcx, rax; void *
0x180008dac  call    memcpy_0
0x180008db1  mov     eax, 1Fh
0x180008db6  mov     word ptr [rsp+190h+ppropvar], ax
0x180008dbb  mov     dword ptr [rsp+190h+ppropvar+8], ebx
0x180008dbf  sar     rbx, 20h
0x180008dc3  mov     dword ptr [rsp+190h+ppropvar+0Ch], ebx
0x180008dc7  mov     [rsp+190h+var_160], r15d
0x180008dcc  mov     rcx, [rsp+190h+ppv]
0x180008dd1  mov     rax, [rcx]
0x180008dd4  lea     r8, [rsp+190h+ppropvar]
0x180008dd9  lea     rdx, PKEY_Identity_UserName
0x180008de0  mov     rax, [rax+30h]
0x180008de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008de9  mov     [rsp+190h+var_160], eax
0x180008ded  test    eax, eax
0x180008def  js      loc_18000962C
0x180008df5  lea     rcx, [rsp+190h+ppropvar]; pvar
0x180008dfa  call    cs:__imp_PropVariantClear
0x180008e00  mov     rcx, [rsp+190h+var_138]
0x180008e05  test    dword ptr [rcx], 400000h
0x180008e0b  jnz     loc_1800093C0
0x180008e11  mov     rbx, [rsp+190h+var_128]
0x180008e16  test    byte ptr [rbx+11Ch], 2
0x180008e1d  jnz     loc_18000921D
0x180008e23  test    dword ptr [rcx], 100000h
0x180008e29  jz      loc_18000912C
0x180008e2f  cmp     dword ptr [rcx+80h], 0
  ... truncated ...
```
