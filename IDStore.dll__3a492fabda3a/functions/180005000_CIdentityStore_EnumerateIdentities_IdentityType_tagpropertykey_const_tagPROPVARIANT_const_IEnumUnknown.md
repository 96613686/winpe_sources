# CIdentityStore::EnumerateIdentities(_IdentityType,_tagpropertykey const *,tagPROPVARIANT const *,IEnumUnknown * *)

- ea: `0x180005000`
- end: `0x180005e8b`
- name: `?EnumerateIdentities@CIdentityStore@@UEAAJW4_IdentityType@@PEBU_tagpropertykey@@PEBUtagPROPVARIANT@@PEAPEAUIEnumUnknown@@@Z`
- size: `3723`
- prototype: `__int64 __fastcall(CIdentityStore *this, const unsigned __int16 *, const struct _tagpropertykey *, PROPVARIANT *, struct IEnumUnknown **)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005000`
- `0x180005ea0`
- `0x1800074dc`
- `0x18000b1c0`
- `0x18000c9f8`
- `0x18000ca30`
- `0x18000cef0`
- `0x18000dff0`
- `0x18000fba2`
- `0x180014430`
- `0x1800144b4`
- `0x1800144f4`
- `0x180014618`
- `0x1800191ac`
- `0x180019210`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000528f`
- `msvcrt!_wcsicmp` at `0x180005a66`
- `msvcrt!_wcsicmp` at `0x18000528f`
- `msvcrt!_wcsicmp` at `0x180005a66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800051bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000566d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800051bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000566d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005cd2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005ddf`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005cd2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005ddf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005656`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800052ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000530a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005334`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800052ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000530a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005334`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800058fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800059cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800058fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800059cc`
- `PROPSYS!PropVariantCompareEx` at `0x1800058eb`
- `PROPSYS!PropVariantCompareEx` at `0x1800059bd`
- `PROPSYS!PropVariantCompareEx` at `0x1800058eb`
- `PROPSYS!PropVariantCompareEx` at `0x1800059bd`

## pseudocode

```c
__int64 __fastcall CIdentityStore::EnumerateIdentities(
        CIdentityStore *this,
        const unsigned __int16 *a2,
        const struct _tagpropertykey *a3,
        PROPVARIANT *a4,
        struct IEnumUnknown **a5)
{
  PROPVARIANT *v5; // r15
  const struct _tagpropertykey *v6; // r13
  enum _IdentityType v7; // r14d
  CIdentityStore *v8; // rdi
  int v9; // ecx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  SIZE_T v13; // rsi
  unsigned int v14; // r12d
  unsigned int k; // r14d
  __int64 v16; // rdi
  __int64 v17; // r13
  unsigned int v18; // ecx
  __int64 v19; // r15
  unsigned int v20; // edi
  void *v21; // r12
  HANDLE v22; // rax
  LPVOID v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 i; // rbx
  const wchar_t *v27; // rcx
  CIdentityProfileHandler *v28; // rcx
  LPVOID *v29; // rsi
  unsigned int v30; // r12d
  unsigned int v31; // r14d
  __int64 v32; // r15
  LPVOID v33; // rcx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  struct IPropertyStore *v39; // rdi
  struct IPropertyStore *v40; // rcx
  struct IPropertyStore *v41; // rbx
  int v42; // eax
  __int64 v43; // r13
  unsigned int v44; // edx
  unsigned int v45; // ebx
  void *v46; // r14
  HANDLE ProcessHeap; // rax
  LPVOID v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // r9
  __int64 v53; // rdx
  __int64 v54; // rcx
  unsigned __int8 v55; // r15
  int v56; // eax
  unsigned __int8 v57; // bl
  int v58; // eax
  PROPVARIANT *v59; // rdx
  const wchar_t *v60; // rcx
  __int64 v61; // r9
  __int64 j; // rdi
  const unsigned __int16 *v63; // rdx
  __int64 v64; // r12
  const unsigned __int16 *v65; // rdx
  PEVENT_DATA_DESCRIPTOR v66; // [rsp+20h] [rbp-A1h]
  SIZE_T dwBytes; // [rsp+30h] [rbp-91h] BYREF
  struct IPropertyStore *v68; // [rsp+38h] [rbp-89h] BYREF
  struct IPropertyStore *v69; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v70; // [rsp+48h] [rbp-79h] BYREF
  __int64 v71; // [rsp+50h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-69h] BYREF
  unsigned int v73; // [rsp+60h] [rbp-61h] BYREF
  int v74; // [rsp+64h] [rbp-5Dh] BYREF
  enum _IdentityType v75; // [rsp+68h] [rbp-59h]
  const struct _tagpropertykey *v76; // [rsp+70h] [rbp-51h]
  PROPVARIANT *propvar1; // [rsp+78h] [rbp-49h]
  struct tagPROPVARIANT propvar2; // [rsp+80h] [rbp-41h] BYREF
  CIdentityStore *v79; // [rsp+98h] [rbp-29h]
  struct _EVENT_DATA_DESCRIPTOR v80; // [rsp+A0h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v81; // [rsp+B0h] [rbp-11h] BYREF

  v5 = a4;
  propvar1 = a4;
  v6 = a3;
  v76 = a3;
  v7 = (int)a2;
  v75 = (int)a2;
  v8 = this;
  v79 = this;
  v81.Ptr = (ULONGLONG)a5;
  v73 = 0;
  dwBytes = 0;
  pv = 0;
  v70 = 0;
  v9 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CIdentityStore::EnumerateIdentities");
  }
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v9, (int)&EnumerateIdentitiesStart, (int)a3, (int)a4, &v80);
  if ( !a5 )
  {
    v11 = -2147024809;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_43;
    }
    v51 = 34;
    v52 = 2147942487LL;
LABEL_228:
    WPP_SF_d(*((_QWORD *)v28 + 2), v51, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v52);
    goto LABEL_43;
  }
  if ( !v6 )
  {
    if ( !v5 )
    {
LABEL_9:
      GetConnectedIdentities(v7, (struct _IDENTITY_ENTRY **)&pv, &v70);
      goto LABEL_10;
    }
    goto LABEL_225;
  }
  if ( !v5 )
  {
LABEL_225:
    v11 = -2147467261;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_43;
    }
    v51 = 35;
    v52 = 2147500035LL;
    goto LABEL_228;
  }
  if ( v6->pid == 5 )
  {
    v25 = *(_QWORD *)&v6->fmtid.Data1 - *(_QWORD *)&PKEY_Keywords.fmtid.Data1;
    if ( *(_QWORD *)&v6->fmtid.Data1 == *(_QWORD *)&PKEY_Keywords.fmtid.Data1 )
      v25 = *(_QWORD *)v6->fmtid.Data4 - *(_QWORD *)PKEY_Keywords.fmtid.Data4;
    if ( !v25 )
    {
      if ( *(_WORD *)v5 == 4127 )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)v5 + 2); i = (unsigned int)(i + 1) )
        {
          v27 = (const wchar_t *)*((_QWORD *)v5[2] + i);
          if ( v27 && !_wcsicmp(v27, L"connected") )
            goto LABEL_9;
        }
      }
      else if ( *(_WORD *)v5 == 31 )
      {
        v60 = (const wchar_t *)v5[1];
        if ( v60 )
        {
          if ( !_wcsicmp(v60, L"connected") )
            goto LABEL_9;
        }
      }
    }
  }
LABEL_10:
  v10 = (*(__int64 (__fastcall **)(CIdentityStore *, unsigned int *))(*(_QWORD *)v8 + 24LL))(v8, &v73);
  v11 = v10;
  if ( v10 < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_43;
    }
    v51 = 36;
    v52 = (unsigned int)v10;
    goto LABEL_228;
  }
  v12 = ATL::CComObject<CGenericEnum>::CreateInstance(&dwBytes);
  v11 = v12;
  v13 = dwBytes;
  if ( v12 >= 0 )
  {
    (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)dwBytes + 8LL))(dwBytes);
    *(GUID *)(v13 + 92) = GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99;
    v14 = 0;
    if ( !v73 )
      goto LABEL_13;
    do
    {
      dwBytes = 0;
      v71 = 0;
      v80.Ptr = 0;
      v35 = (*(__int64 (__fastcall **)(CIdentityStore *, _QWORD, _QWORD, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v8 + 32LL))(
              v8,
              v14,
              0,
              &v80);
      if ( v35 < 0 )
      {
        a2 = (const unsigned __int16 *)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          LODWORD(v66) = v35;
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, a3, v14, v66);
        }
        if ( v80.Ptr )
          (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v80.Ptr + 16LL))(v80.Ptr);
        if ( v71 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
        if ( dwBytes )
          (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)dwBytes + 16LL))(dwBytes);
        goto LABEL_68;
      }
      if ( !v80.Ptr )
      {
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v14);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v80);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&dwBytes);
        goto LABEL_68;
      }
      v36 = (**(__int64 (__fastcall ***)(ULONGLONG, GUID *, SIZE_T *))v80.Ptr)(
              v80.Ptr,
              &GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5,
              &dwBytes);
      if ( v36 < 0 )
      {
        a2 = (const unsigned __int16 *)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          LODWORD(v66) = v36;
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, a3, v14, v66);
        }
        if ( v80.Ptr )
          (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v80.Ptr + 16LL))(v80.Ptr);
        if ( v71 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
        if ( dwBytes )
          (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)dwBytes + 16LL))(dwBytes);
        goto LABEL_68;
      }
      v37 = (*(__int64 (__fastcall **)(SIZE_T, _QWORD, const struct _tagpropertykey *, PROPVARIANT *, __int64 *))(*(_QWORD *)dwBytes + 24LL))(
              dwBytes,
              (unsigned int)v7,
              v6,
              v5,
              &v71);
      if ( v37 < 0 )
      {
        a2 = (const unsigned __int16 *)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          LODWORD(v66) = v37;
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, a3, v14, v66);
        }
        if ( v80.Ptr )
          (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v80.Ptr + 16LL))(v80.Ptr);
        if ( v71 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
        if ( dwBytes )
          (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)dwBytes + 16LL))(dwBytes);
        goto LABEL_68;
      }
      if ( !v71 )
      {
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v14);
        }
        if ( v80.Ptr )
          (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v80.Ptr + 16LL))(v80.Ptr);
        if ( v71 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
        if ( dwBytes )
          (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)dwBytes + 16LL))(dwBytes);
        goto LABEL_68;
      }
      while ( 1 )
      {
        v68 = 0;
        v69 = 0;
        v38 = (*(__int64 (__fastcall **)(__int64, __int64, struct IPropertyStore **, _QWORD))(*(_QWORD *)v71 + 24LL))(
                v71,
                1,
                &v68,
                0);
        if ( v38 < 0 )
          break;
        if ( v38 == 1 )
          goto LABEL_108;
        v39 = v68;
        if ( !v68 )
        {
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v14);
            v39 = v68;
          }
          if ( v69 )
          {
            ((void (__fastcall *)(struct IPropertyStore *))v69->lpVtbl->Release)(v69);
            v39 = v68;
          }
          if ( v39 )
            ((void (__fastcall *)(struct IPropertyStore *))v39->lpVtbl->Release)(v39);
          goto LABEL_112;
        }
        v40 = v69;
        if ( v69 != v68 )
        {
          v41 = v69;
          v69 = 0;
          ((void (__fastcall *)(struct IPropertyStore *, GUID *, struct IPropertyStore **))v68->lpVtbl->QueryInterface)(
            v68,
            &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
            &v69);
          v39 = v68;
          v40 = v69;
          if ( v41 )
          {
            ((void (__fastcall *)(struct IPropertyStore *))v41->lpVtbl->Release)(v41);
            v39 = v68;
            v40 = v69;
          }
        }
        if ( v40 )
        {
          v74 = 1;
          if ( pv )
          {
            v42 = MergeConnectedId((struct _IDENTITY_ENTRY *)pv, v70, v40, &v74);
            if ( v42 < 0 )
            {
              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  46,
                  WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
                  (unsigned int)v42);
              }
            }
            else if ( !v74 )
            {
              goto LABEL_84;
            }
            v40 = v69;
            v39 = v68;
          }
          if ( v6 && v5 )
          {
            v57 = 0;
            memset(&propvar2, 0, sizeof(propvar2));
            v58 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, struct tagPROPVARIANT *))v40->lpVtbl->GetValue)(
                    v40,
                    v6,
                    &propvar2);
            if ( v58 < 0 )
            {
              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_DD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  120,
                  WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
                  v6->pid,
                  v58);
              }
            }
            else if ( (unsigned int)operator==(v6) )
            {
              if ( *(_WORD *)v5 == 4127 )
              {
                for ( j = 0; (unsigned int)j < *((_DWORD *)v5 + 2); j = (unsigned int)(j + 1) )
                {
                  v63 = (const unsigned __int16 *)*((_QWORD *)v5[2] + j);
                  if ( !v63 || !ContainsKeyword(&propvar2, v63) )
                    goto LABEL_160;
                }
                v57 = 1;
              }
              else if ( *(_WORD *)v5 == 31 )
              {
                v57 = ContainsKeyword(&propvar2, (const unsigned __int16 *)v5[1]);
              }
            }
            else
            {
              v57 = PropVariantCompareEx(v5, (const PROPVARIANT *const)&propvar2, PVCU_DEFAULT, 8) == 0;
            }
LABEL_160:
            PropVariantClear((PROPVARIANT *)&propvar2);
            if ( !v57 )
              goto LABEL_84;
            v39 = v68;
            v40 = v69;
          }
          v43 = *(unsigned int *)(v13 + 72);
          v44 = v43 + 1;
          if ( (_DWORD)v43 != -1 )
          {
            if ( v44 <= *(_DWORD *)(v13 + 76) )
            {
LABEL_106:
              memmove_0(
                (void *)(8 * v43 + *(_QWORD *)(v13 + 64) + 8),
                (const void *)(8 * v43 + *(_QWORD *)(v13 + 64)),
                8LL * (unsigned int)(*(_DWORD *)(v13 + 72) - v43));
              v49 = *(unsigned int *)(v13 + 72);
              *(_DWORD *)(v13 + 72) = v49 + 1;
              v50 = *(_QWORD *)(v13 + 64);
              if ( 8 * v43 + v50 )
              {
                *(_QWORD *)(v50 + 8 * v49) = v39;
                ((void (__fastcall *)(struct IPropertyStore *))v39->lpVtbl->AddRef)(v39);
              }
            }
            else
            {
              v45 = v44 + (v44 >> 1) + 32;
              v46 = *(void **)(v13 + 64);
              ProcessHeap = GetProcessHeap();
              if ( v46 )
                v48 = HeapReAlloc(ProcessHeap, 0, v46, 8 * v45);
              else
                v48 = HeapAlloc(ProcessHeap, 0, 8 * v45);
              if ( v48 )
              {
                *(_QWORD *)(v13 + 64) = v48;
                *(_DWORD *)(v13 + 76) = v45;
                goto LABEL_106;
              }
            }
LABEL_84:
            v40 = v69;
            v39 = v68;
          }
          if ( v40 )
          {
            ((void (__fastcall *)(struct IPropertyStore *))v40->lpVtbl->Release)(v40);
            v39 = v68;
          }
          if ( v39 )
            ((void (__fastcall *)(struct IPropertyStore *))v39->lpVtbl->Release)(v39);
          v6 = v76;
          v5 = propvar1;
        }
        else if ( v39 )
        {
          ((void (__fastcall *)(struct IPropertyStore *))v39->lpVtbl->Release)(v39);
        }
      }
      a2 = (const unsigned __int16 *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        LODWORD(v66) = v38;
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, a3, v14, v66);
      }
LABEL_108:
      if ( v69 )
        ((void (__fastcall *)(struct IPropertyStore *))v69->lpVtbl->Release)(v69);
      if ( v68 )
        ((void (__fastcall *)(struct IPropertyStore *))v68->lpVtbl->Release)(v68);
LABEL_112:
      if ( v80.Ptr )
        (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v80.Ptr + 16LL))(v80.Ptr);
      if ( v71 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      if ( dwBytes )
        (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)dwBytes + 16LL))(dwBytes);
      v8 = v79;
      v7 = v75;
LABEL_68:
      ++v14;
    }
    while ( v14 < v73 );
LABEL_13:
    if ( pv )
    {
      for ( k = 0; ; ++k )
      {
        if ( k >= v70 )
          goto LABEL_40;
        v16 = 32LL * k;
        if ( v75 != IDENTITIES_ME_ONLY || *(_DWORD *)((char *)pv + v16 + 24) )
        {
          v11 = AddKeywordProperty(*(struct IPropertyStore **)((char *)pv + v16 + 16), a2, (__int64)a3);
          if ( v11 < 0 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v53 = 47;
              goto LABEL_224;
            }
            goto LABEL_41;
          }
          if ( !v6 || !v5 )
            break;
          v54 = *(_QWORD *)((char *)pv + v16 + 16);
          v55 = 0;
          memset(&propvar2, 0, sizeof(propvar2));
          v56 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, struct tagPROPVARIANT *))(*(_QWORD *)v54 + 40LL))(
                  v54,
                  v6,
                  &propvar2);
          if ( v56 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_DD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                120,
                WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
                v6->pid,
                v56);
            }
          }
          else if ( (unsigned int)operator==(v6) )
          {
            v59 = propvar1;
            if ( *(_WORD *)propvar1 == 4127 )
            {
              v64 = 0;
              while ( (unsigned int)v64 < *((_DWORD *)v59 + 2) )
              {
                v65 = (const unsigned __int16 *)*((_QWORD *)v59[2] + v64);
                if ( !v65 || !ContainsKeyword(&propvar2, v65) )
                  goto LABEL_146;
                v64 = (unsigned int)(v64 + 1);
                v59 = propvar1;
              }
              v55 = 1;
            }
            else if ( *(_WORD *)propvar1 == 31 )
            {
              v55 = ContainsKeyword(&propvar2, (const unsigned __int16 *)propvar1[1]);
            }
          }
          else
          {
            v55 = PropVariantCompareEx(propvar1, (const PROPVARIANT *const)&propvar2, PVCU_DEFAULT, 8) == 0;
          }
LABEL_146:
          PropVariantClear((PROPVARIANT *)&propvar2);
          if ( v55 )
            break;
        }
LABEL_28:
        v5 = propvar1;
      }
      v17 = *(unsigned int *)(v13 + 72);
      v18 = v17 + 1;
      if ( (_DWORD)v17 != -1 )
      {
        v19 = *(_QWORD *)((char *)pv + v16 + 16);
        if ( v18 > *(_DWORD *)(v13 + 76) )
        {
          v20 = v18 + (v18 >> 1) + 32;
          v21 = *(void **)(v13 + 64);
          dwBytes = 8 * v20;
          v22 = GetProcessHeap();
          if ( v21 )
            v23 = HeapReAlloc(v22, 0, v21, dwBytes);
          else
            v23 = HeapAlloc(v22, 0, dwBytes);
          if ( !v23 )
            goto LABEL_27;
          *(_QWORD *)(v13 + 64) = v23;
          *(_DWORD *)(v13 + 76) = v20;
        }
        memmove_0(
          (void *)(8 * v17 + *(_QWORD *)(v13 + 64) + 8),
          (const void *)(8 * v17 + *(_QWORD *)(v13 + 64)),
          8LL * (unsigned int)(*(_DWORD *)(v13 + 72) - v17));
        v24 = *(unsigned int *)(v13 + 72);
        *(_DWORD *)(v13 + 72) = v24 + 1;
        a2 = *(const unsigned __int16 **)(v13 + 64);
        if ( &a2[4 * v17] )
        {
          *(_QWORD *)&a2[4 * v24] = v19;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
LABEL_27:
      v6 = v76;
      goto LABEL_28;
    }
LABEL_40:
    v11 = (**(__int64 (__fastcall ***)(SIZE_T, GUID *, ULONGLONG))v13)(
            v13,
            &GUID_00000100_0000_0000_c000_000000000046,
            v81.Ptr);
    if ( v11 >= 0 )
      goto LABEL_41;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_41;
    }
    v53 = 48;
LABEL_224:
    v61 = (unsigned int)v11;
    goto LABEL_178;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v53 = 37;
    v61 = (unsigned int)v12;
LABEL_178:
    WPP_SF_d(*((_QWORD *)v28 + 2), v53, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v61);
  }
LABEL_41:
  if ( v13 )
    (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_43:
  v29 = (LPVOID *)pv;
  if ( pv )
  {
    v30 = v70;
    v31 = 0;
    if ( v70 )
    {
      v32 = 0;
      do
      {
        CoTaskMemFree(v29[4 * v32]);
        CoTaskMemFree(v29[4 * v32 + 1]);
        v33 = v29[4 * v32 + 2];
        if ( v33 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
        ++v31;
        ++v32;
      }
      while ( v31 < v30 );
    }
    CoTaskMemFree(v29);
  }
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)v28, (int)&EnumerateIdentitiesStop, (int)a3, (int)a4, &v81);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return (unsigned int)v11;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_sL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"CIdentityStore::EnumerateIdentities",
        v11);
  }
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, a3, "CIdentityStore::EnumerateIdentities");
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005000  push    rbp
0x180005002  push    rbx
0x180005003  push    rsi
0x180005004  push    rdi
0x180005005  push    r12
0x180005007  push    r13
0x180005009  push    r14
0x18000500b  push    r15
0x18000500d  lea     rbp, [rsp-17h]
0x180005012  sub     rsp, 0D8h
0x180005019  mov     rax, cs:__security_cookie
0x180005020  xor     rax, rsp
0x180005023  mov     [rbp+4Fh+var_50], rax
0x180005027  mov     r15, r9
0x18000502a  mov     [rbp+4Fh+propvar1], r9
0x18000502e  mov     r13, r8
0x180005031  mov     [rbp+4Fh+var_A0], r8
0x180005035  mov     r14d, edx
0x180005038  mov     [rbp+4Fh+var_A8], edx
0x18000503b  mov     rdi, rcx
0x18000503e  mov     [rbp+4Fh+var_78], rcx
0x180005042  mov     rbx, [rbp+4Fh+arg_20]
0x180005046  mov     [rbp+4Fh+var_60.Ptr], rbx
0x18000504a  mov     [rbp+4Fh+var_B0], 0
0x180005051  mov     [rsp+110h+dwBytes], 0
0x18000505a  mov     [rbp+4Fh+pv], 0
0x180005062  mov     [rbp+4Fh+var_C8], 0
0x180005069  lea     r12, WPP_GLOBAL_Control
0x180005070  mov     rcx, cs:WPP_GLOBAL_Control; int
0x180005077  cmp     rcx, r12
0x18000507a  jz      short loc_180005089
0x18000507c  test    dword ptr [rcx+1Ch], 400h
0x180005083  jnz     loc_180005A79
0x180005089  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180005090  jnz     loc_180005A93
0x180005096  test    rbx, rbx
0x180005099  jz      loc_180005AAD
0x18000509f  mov     ecx, 101Fh
0x1800050a4  test    r13, r13
0x1800050a7  jnz     loc_18000522D
0x1800050ad  test    r15, r15
0x1800050b0  jnz     loc_180005E18
0x1800050b6  lea     r8, [rbp+4Fh+var_C8]; unsigned int *
0x1800050ba  lea     rdx, [rbp+4Fh+pv]; struct _IDENTITY_ENTRY **
0x1800050be  mov     ecx, r14d; enum _IdentityType
0x1800050c1  call    ?GetConnectedIdentities@@YAJW4_IdentityType@@PEAPEAU_IDENTITY_ENTRY@@PEAK@Z; GetConnectedIdentities(_IdentityType,_IDENTITY_ENTRY * *,ulong *)
0x1800050c6  mov     rax, [rdi]
0x1800050c9  lea     rdx, [rbp+4Fh+var_B0]
0x1800050cd  mov     rcx, rdi
0x1800050d0  mov     rax, [rax+18h]
0x1800050d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d9  mov     ebx, eax
0x1800050db  test    eax, eax
0x1800050dd  js      loc_180005756
0x1800050e3  lea     rcx, [rsp+110h+dwBytes]
0x1800050e8  call    ?CreateInstance@?$CComObject@VCGenericEnum@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CGenericEnum>::CreateInstance(ATL::CComObject<CGenericEnum> * *)
0x1800050ed  mov     ebx, eax
0x1800050ef  mov     rsi, [rsp+110h+dwBytes]
0x1800050f4  test    eax, eax
0x1800050f6  js      loc_180005ADC
0x1800050fc  mov     rax, [rsi]
0x1800050ff  mov     rcx, rsi
0x180005102  mov     rax, [rax+8]
0x180005106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510b  movups  xmm0, xmmword ptr cs:_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data1
0x180005112  movups  xmmword ptr [rsi+5Ch], xmm0
0x180005116  xor     ebx, ebx
0x180005118  xor     r12d, r12d
0x18000511b  cmp     [rbp+4Fh+var_B0], ebx
0x18000511e  ja      loc_180005391
0x180005124  cmp     [rbp+4Fh+pv], 0
0x180005129  jz      loc_1800052A5
0x18000512f  xor     r14d, r14d
0x180005132  cmp     r14d, [rbp+4Fh+var_C8]
0x180005136  jnb     loc_1800052A1
0x18000513c  mov     edi, r14d
0x18000513f  shl     rdi, 5
0x180005143  cmp     [rbp+4Fh+var_A8], 1
0x180005147  jz      loc_180005D44
0x18000514d  mov     rcx, [rbp+4Fh+pv]
0x180005151  mov     rcx, [rdi+rcx+10h]; struct IPropertyStore *
0x180005156  call    ?AddKeywordProperty@@YAJPEAUIPropertyStore@@PEBG@Z; AddKeywordProperty(IPropertyStore *,ushort const *)
0x18000515b  mov     ebx, eax
0x18000515d  test    eax, eax
0x18000515f  js      loc_18000577D
0x180005165  test    r13, r13
0x180005168  jnz     loc_18000588D
0x18000516e  mov     r13d, [rsi+48h]
0x180005172  lea     ecx, [r13+1]
0x180005176  cmp     ecx, 1
0x180005179  jb      loc_18000521D
0x18000517f  mov     rax, [rbp+4Fh+pv]
0x180005183  mov     r15, [rdi+rax+10h]
0x180005188  cmp     ecx, [rsi+4Ch]
0x18000518b  jbe     short loc_1800051D1
0x18000518d  mov     edi, ecx
0x18000518f  shr     edi, 1
0x180005191  add     edi, 20h ; ' '
0x180005194  add     edi, ecx
0x180005196  mov     r12, [rsi+40h]
0x18000519a  lea     eax, ds:0[rdi*8]
0x1800051a1  mov     [rsp+110h+dwBytes], rax
0x1800051a6  call    cs:__imp_GetProcessHeap
0x1800051ac  xor     edx, edx; dwFlags
0x1800051ae  mov     rcx, rax; hHeap
0x1800051b1  test    r12, r12
0x1800051b4  jnz     loc_180005DD7
0x1800051ba  mov     r8, [rsp+110h+dwBytes]; dwBytes
0x1800051bf  call    cs:__imp_HeapAlloc
0x1800051c5  test    rax, rax
0x1800051c8  jz      short loc_18000521D
0x1800051ca  mov     [rsi+40h], rax
0x1800051ce  mov     [rsi+4Ch], edi
0x1800051d1  lea     rdi, ds:0[r13*8]
0x1800051d9  mov     rdx, [rsi+40h]
0x1800051dd  add     rdx, rdi; Src
0x1800051e0  mov     r8d, [rsi+48h]
0x1800051e4  sub     r8d, r13d
0x1800051e7  shl     r8, 3; Size
0x1800051eb  lea     rcx, [rdx+8]; void *
0x1800051ef  call    memmove_0
0x1800051f4  mov     ecx, [rsi+48h]
0x1800051f7  lea     eax, [rcx+1]
0x1800051fa  mov     [rsi+48h], eax
0x1800051fd  mov     rdx, [rsi+40h]
0x180005201  lea     rax, [rdi+rdx]
0x180005205  test    rax, rax
0x180005208  jz      short loc_18000521D
0x18000520a  mov     [rdx+rcx*8], r15
0x18000520e  mov     rax, [r15]
0x180005211  mov     rcx, r15
0x180005214  mov     rax, [rax+8]
0x180005218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000521d  mov     r13, [rbp+4Fh+var_A0]
0x180005221  inc     r14d
0x180005224  mov     r15, [rbp+4Fh+propvar1]
0x180005228  jmp     loc_180005132
0x18000522d  test    r15, r15
0x180005230  jz      loc_180005E18
0x180005236  cmp     dword ptr [r13+10h], 5
0x18000523b  jnz     loc_1800050C6
0x180005241  mov     rax, [r13+0]
0x180005245  sub     rax, qword ptr cs:PKEY_Keywords.fmtid.Data1
0x18000524c  jnz     short loc_180005259
0x18000524e  mov     rax, [r13+8]
0x180005252  sub     rax, qword ptr cs:PKEY_Keywords.fmtid.Data4
0x180005259  test    rax, rax
0x18000525c  jnz     loc_1800050C6
0x180005262  movzx   eax, word ptr [r15]
0x180005266  cmp     ax, cx
0x180005269  jnz     loc_180005A48
0x18000526f  xor     ebx, ebx
0x180005271  cmp     ebx, [r15+8]
0x180005275  jnb     loc_1800050C6
0x18000527b  mov     rax, [r15+10h]
0x18000527f  mov     rcx, [rax+rbx*8]; String1
0x180005283  test    rcx, rcx
0x180005286  jz      short loc_18000529D
0x180005288  lea     rdx, aConnected_0; "connected"
0x18000528f  call    cs:__imp__wcsicmp
0x180005295  test    eax, eax
0x180005297  jz      loc_1800050B6
0x18000529d  inc     ebx
0x18000529f  jmp     short loc_180005271
0x1800052a1  test    ebx, ebx
0x1800052a3  js      short loc_1800052C8
0x1800052a5  mov     rax, [rsi]
0x1800052a8  mov     r8, [rbp+4Fh+var_60.Ptr]
0x1800052ac  lea     rdx, _GUID_00000100_0000_0000_c000_000000000046
0x1800052b3  mov     rcx, rsi
0x1800052b6  mov     rax, [rax]
0x1800052b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052be  mov     ebx, eax
0x1800052c0  test    eax, eax
0x1800052c2  js      loc_180005DEA
0x1800052c8  test    rsi, rsi
0x1800052cb  jz      short loc_1800052DC
0x1800052cd  mov     rax, [rsi]
0x1800052d0  mov     rcx, rsi
0x1800052d3  mov     rax, [rax+10h]
0x1800052d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052dc  mov     rsi, [rbp+4Fh+pv]
0x1800052e0  test    rsi, rsi
0x1800052e3  jz      short loc_18000533A
0x1800052e5  mov     r12d, [rbp+4Fh+var_C8]
0x1800052e9  xor     r14d, r14d
0x1800052ec  test    r12d, r12d
0x1800052ef  jz      short loc_180005331
0x1800052f1  xor     r15d, r15d
0x1800052f4  mov     rdi, r15
0x1800052f7  shl     rdi, 5
0x1800052fb  mov     rcx, [rdi+rsi]; pv
0x1800052ff  call    cs:__imp_CoTaskMemFree
0x180005305  mov     rcx, [rdi+rsi+8]; pv
0x18000530a  call    cs:__imp_CoTaskMemFree
0x180005310  mov     rcx, [rdi+rsi+10h]
0x180005315  test    rcx, rcx
0x180005318  jz      short loc_180005326
0x18000531a  mov     rax, [rcx]
0x18000531d  mov     rax, [rax+10h]
0x180005321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005326  inc     r14d
0x180005329  inc     r15
0x18000532c  cmp     r14d, r12d
0x18000532f  jb      short loc_1800052F4
0x180005331  mov     rcx, rsi; pv
0x180005334  call    cs:__imp_CoTaskMemFree
0x18000533a  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180005341  jnz     loc_180005E57
0x180005347  test    ebx, ebx
0x180005349  js      loc_180005853
0x18000534f  lea     rdi, WPP_GLOBAL_Control
0x180005356  mov     rcx, cs:WPP_GLOBAL_Control
0x18000535d  cmp     rcx, rdi
0x180005360  jz      short loc_18000536F
0x180005362  test    dword ptr [rcx+1Ch], 400h
0x180005369  jnz     loc_180005E71
0x18000536f  mov     eax, ebx
0x180005371  mov     rcx, [rbp+4Fh+var_50]
0x180005375  xor     rcx, rsp; StackCookie
0x180005378  call    __security_check_cookie
0x18000537d  add     rsp, 0D8h
0x180005384  pop     r15
0x180005386  pop     r14
0x180005388  pop     r13
0x18000538a  pop     r12
0x18000538c  pop     rdi
0x18000538d  pop     rsi
0x18000538e  pop     rbx
0x18000538f  pop     rbp
0x180005390  retn
0x180005391  xor     ebx, ebx
0x180005393  mov     [rsp+110h+dwBytes], rbx
0x180005398  mov     [rbp+4Fh+var_C0], rbx
0x18000539c  mov     [rbp+4Fh+var_70.Ptr], rbx
0x1800053a0  mov     rax, [rdi]
0x1800053a3  lea     r9, [rbp+4Fh+var_70]
0x1800053a7  xor     r8d, r8d
0x1800053aa  mov     edx, r12d
0x1800053ad  mov     rcx, rdi
0x1800053b0  mov     rax, [rax+20h]
0x1800053b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b9  test    eax, eax
0x1800053bb  js      loc_1800057A8
0x1800053c1  mov     rcx, [rbp+4Fh+var_70.Ptr]
0x1800053c5  test    rcx, rcx
0x1800053c8  jz      loc_180005B37
0x1800053ce  mov     rax, [rcx]
0x1800053d1  lea     r8, [rsp+110h+dwBytes]
0x1800053d6  lea     rdx, _GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5
0x1800053dd  mov     rax, [rax]
0x1800053e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e5  nop
0x1800053e6  test    eax, eax
0x1800053e8  js      loc_1800055B9
0x1800053ee  mov     rcx, [rsp+110h+dwBytes]
0x1800053f3  mov     rax, [rcx]
0x1800053f6  lea     rdx, [rbp+4Fh+var_C0]
0x1800053fa  mov     [rsp+110h+var_F0], rdx
0x1800053ff  mov     r9, r15
0x180005402  mov     r8, r13
0x180005405  mov     edx, r14d
0x180005408  mov     rax, [rax+18h]
0x18000540c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005411  test    eax, eax
0x180005413  jns     short loc_180005481
0x180005415  mov     rcx, cs:WPP_GLOBAL_Control
0x18000541c  lea     rdx, WPP_GLOBAL_Control
0x180005423  cmp     rcx, rdx
0x180005426  jnz     loc_180005BAD
0x18000542c  mov     rcx, [rbp+4Fh+var_70.Ptr]
0x180005430  test    rcx, rcx
0x180005433  jz      short loc_180005442
0x180005435  mov     rax, [rcx]
0x180005438  mov     rax, [rax+10h]
0x18000543c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005441  nop
0x180005442  mov     rcx, [rbp+4Fh+var_C0]
0x180005446  test    rcx, rcx
0x180005449  jz      short loc_180005458
0x18000544b  mov     rax, [rcx]
0x18000544e  mov     rax, [rax+10h]
0x180005452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005457  nop
0x180005458  mov     rcx, [rsp+110h+dwBytes]
0x18000545d  test    rcx, rcx
0x180005460  jz      short loc_18000546F
0x180005462  mov     rax, [rcx]
0x180005465  mov     rax, [rax+10h]
0x180005469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000546e  nop
0x18000546f  inc     r12d
0x180005472  cmp     r12d, [rbp+4Fh+var_B0]
0x180005476  jb      loc_180005391
0x18000547c  jmp     loc_180005124
0x180005481  cmp     [rbp+4Fh+var_C0], 0
0x180005486  jz      loc_18000590F
0x18000548c  nop     dword ptr [rax+00h]
0x180005490  mov     [rsp+110h+var_D8], rbx
0x180005495  mov     [rsp+110h+var_D0], rbx
  ... truncated ...
```
