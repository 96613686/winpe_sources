# CShellItem::Compare(IShellItem *,ulong,int *)

- ea: `0x1800ce3a0`
- end: `0x1800cee9a`
- name: `?Compare@CShellItem@@UEAAJPEAUIShellItem@@KPEAH@Z`
- size: `2810`
- prototype: `int(CShellItem *__hidden this, struct IShellItem *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180051fd0`
- `0x180054860`
- `0x180054c30`
- `0x180054ce0`
- `0x1800551a0`
- `0x1800ce3a0`
- `0x1800cfc30`
- `0x1800d0990`
- `0x1800d2dc0`
- `0x1800d6b80`
- `0x1800dd190`
- `0x1800dd910`
- `0x180170cf0`
- `0x1803a4cb0`
- `0x1803a96d9`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800cec80`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800cec80`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800cedc1`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800cedc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce9f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce9f8`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800ce48c`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800ce48c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce450`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce450`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ce93c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ce93c`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ce43a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ce43a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce9ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce9c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cec2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cecfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce9ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce9c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cec2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cecfd`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800cede4`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800cede4`

## string_xrefs

- `0x1800cecc9`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CShellItem::Compare(CShellItem *this, struct IUnknown *a2, int a3, int *a4)
{
  CShellItem *v5; // r15
  char *v6; // r12
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  int DebugInfo_high; // ebx
  int v9; // eax
  DWORD CurrentThreadId; // ebx
  HRESULT ApartmentType; // r13d
  struct IShellItem *v12; // rdi
  void **v13; // rsi
  int ItemFromObjectWorker; // ebx
  __int64 v15; // rsi
  int (__fastcall ***v16)(_QWORD, GUID *, APTTYPE *); // rbx
  int v17; // esi
  int v18; // esi
  int v19; // edi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r9
  const WCHAR *v23; // rcx
  const WCHAR *v24; // r8
  __int64 v25; // rdx
  int v26; // eax
  __int64 *v27; // rcx
  __int64 *v28; // rcx
  unsigned __int16 *v30; // r12
  unsigned __int16 *v31; // r15
  HRESULT v32; // ebx
  unsigned __int16 *v33; // rdx
  int v34; // r10d
  int v35; // r11d
  __int64 v36; // r9
  __int64 v37; // rcx
  int v38; // r8d
  unsigned __int16 *v39; // rdx
  __int64 v40; // rcx
  __int64 *v41; // rbx
  __int64 *v42; // rcx
  const struct _ITEMIDLIST_RELATIVE *v43; // rcx
  const ITEMIDLIST *v44; // rax
  ITEMIDLIST *v45; // r15
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-D0h]
  struct _ITEMIDLIST_RELATIVE **v48; // [rsp+38h] [rbp-C8h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+58h] [rbp-A8h] BYREF
  APTTYPE pAptType[2]; // [rsp+60h] [rbp-A0h] BYREF
  CShellItem *v52; // [rsp+68h] [rbp-98h] BYREF
  int (__fastcall ***v53)(_QWORD, GUID *, APTTYPEQUALIFIER *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  int (__fastcall ***v55)(_QWORD, GUID *, APTTYPE *); // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v57; // [rsp+90h] [rbp-70h] BYREF
  __int64 v58; // [rsp+98h] [rbp-68h] BYREF
  LPCWCH lpString2; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-58h]
  __int64 v61; // [rsp+B0h] [rbp-50h]
  LPCWCH lpString1; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+C8h] [rbp-38h]
  WCHAR Filename[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  LODWORD(v54) = a3;
  v5 = this;
  v52 = this;
  *a4 = 0;
  v6 = (char *)this - 8;
  v48 = (struct _ITEMIDLIST_RELATIVE **)((char *)this - 8);
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  if ( this == (CShellItem *)8 )
    v7 = 0;
  lpCriticalSection = v7;
  DebugInfo_high = HIDWORD(v7[1].DebugInfo);
  if ( DebugInfo_high != 2 )
  {
    v9 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
      goto LABEL_5;
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      if ( FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1 )
        goto LABEL_133;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 1;
    }
    else if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess != 1 )
    {
      goto LABEL_16;
    }
    if ( DebugInfo_high == 1 )
    {
      if ( !(unsigned int)IsAppCompatModeEnabled(16) )
      {
        v9 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
        if ( v9 != 1 )
          goto LABEL_16;
        goto LABEL_6;
      }
LABEL_133:
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_16;
    }
  }
LABEL_6:
  if ( LODWORD(v7[1].DebugInfo) != -3 )
  {
    CurrentThreadId = 0;
    pAptType[0] = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(pAptType, pAptQualifier);
    if ( ApartmentType >= 0 )
    {
      if ( pAptType[0] == APTTYPE_MAINSTA || pAptType[0] == APTTYPE_STA )
      {
        CurrentThreadId = GetCurrentThreadId();
      }
      else if ( pAptType[0] == APTTYPE_NA )
      {
        CurrentThreadId = -1;
      }
      if ( CurrentThreadId != LODWORD(v7[1].DebugInfo) )
        ApartmentType = -2147417842;
    }
    if ( ApartmentType < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
        (const char *)(unsigned int)ApartmentType,
        bIgnoreCase);
      goto LABEL_18;
    }
  }
LABEL_16:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection(v7) )
    ApartmentType = 0;
LABEL_18:
  if ( ApartmentType >= 0 )
  {
    v12 = (struct IShellItem *)v5;
    if ( !v6 )
      v12 = 0;
    if ( v12 && a2 )
    {
      if ( v12 == (struct IShellItem *)a2 )
      {
LABEL_107:
        ItemFromObjectWorker = 0;
        v7 = lpCriticalSection;
        goto LABEL_77;
      }
      *(_QWORD *)pAptQualifier = 0;
      v53 = 0;
      if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, APTTYPEQUALIFIER *))v12->lpVtbl->QueryInterface)(
             v12,
             &GUID_00000000_0000_0000_c000_000000000046,
             pAptQualifier) < 0 )
        goto LABEL_27;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_00000000_0000_0000_c000_000000000046,
             &v53) >= 0 )
      {
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *)))(*v53)[2])(v53);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
        if ( *(int (__fastcall ****)(_QWORD, GUID *, APTTYPEQUALIFIER *))pAptQualifier != v53 )
          goto LABEL_27;
        goto LABEL_107;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
    }
LABEL_27:
    v53 = 0;
    v13 = (void **)((char *)v5 + 168);
    if ( !*((_QWORD *)v5 + 21) )
    {
      v43 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)v5 + 16);
      *v13 = 0;
      ItemFromObjectWorker = -2147024809;
      if ( v43 )
      {
        v44 = (const ITEMIDLIST *)ILCloneParent(v43);
        v45 = (ITEMIDLIST *)v44;
        if ( !v44 )
        {
          ItemFromObjectWorker = -2147024882;
          goto LABEL_76;
        }
        ItemFromObjectWorker = SHBindToObject(0, v44, 0, &GUID_000214e6_0000_0000_c000_000000000046, v13);
        CoTaskMemFree(v45);
        v5 = v52;
      }
      if ( ItemFromObjectWorker < 0 )
        goto LABEL_76;
      if ( *((_DWORD *)v5 + 50) )
        IUnknown_PrepareForCaching((struct IUnknown *)*v13);
    }
    ItemFromObjectWorker = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))*v13)(
                             *v13,
                             &GUID_000214e6_0000_0000_c000_000000000046,
                             &v53);
    if ( ItemFromObjectWorker < 0 )
    {
LABEL_76:
      v7 = lpCriticalSection;
      goto LABEL_77;
    }
    v15 = 0;
    v58 = 0;
    ItemFromObjectWorker = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                             a2,
                             &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                             &v58);
    if ( ItemFromObjectWorker < 0 )
    {
LABEL_75:
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *)))(*v53)[2])(v53);
      goto LABEL_76;
    }
    v55 = 0;
    pv = 0;
    v57 = 0;
    ItemFromObjectWorker = (*(__int64 (__fastcall **)(__int64, LPVOID *, int (__fastcall ****)(_QWORD, GUID *, APTTYPE *), LPVOID *))(*(_QWORD *)v58 + 32LL))(
                             v58,
                             &pv,
                             &v55,
                             &v57);
    if ( ItemFromObjectWorker < 0 )
    {
LABEL_74:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      goto LABEL_75;
    }
    if ( !*((_QWORD *)v6 + 20) && !(unsigned int)CShellItem::_IsDesktop((CShellItem *)v6) )
    {
      ItemFromObjectWorker = SHGetIDListFromObject(*((IUnknown **)v6 + 22), (LPITEMIDLIST *)v6 + 20);
      if ( ItemFromObjectWorker < 0 )
        goto LABEL_73;
    }
    if ( v53 )
    {
      v16 = v55;
      if ( v55 )
      {
        if ( v53 == (int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *))v55 )
          goto LABEL_38;
        *(_QWORD *)pAptQualifier = 0;
        *(_QWORD *)pAptType = 0;
        if ( (**v53)(v53, &GUID_00000000_0000_0000_c000_000000000046, pAptQualifier) >= 0 )
        {
          if ( (**v16)(v16, &GUID_00000000_0000_0000_c000_000000000046, pAptType) < 0 )
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
          }
          else
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
            if ( *(_QWORD *)pAptQualifier == *(_QWORD *)pAptType )
              goto LABEL_38;
          }
        }
      }
    }
    v30 = (unsigned __int16 *)*((_QWORD *)v5 + 19);
    v31 = (unsigned __int16 *)pv;
    if ( pv != v30 )
    {
      if ( !pv || !v30 )
        goto LABEL_100;
      *(_QWORD *)pAptQualifier = 0;
      v32 = SHGetDesktopFolder((IShellFolder **)pAptQualifier);
      if ( v32 >= 0 )
      {
        if ( v30 == v31 )
        {
          v32 = 0;
        }
        else
        {
          v33 = v30;
          v34 = 0;
          v35 = 2;
          v36 = 2;
          do
          {
            v37 = *v33;
            if ( !(_WORD)v37 )
              break;
            v36 = (unsigned int)(v37 + v36);
            ++v34;
            v33 = (unsigned __int16 *)((char *)v33 + v37);
          }
          while ( v33 );
          v38 = 0;
          if ( v31 )
          {
            v39 = v31;
            do
            {
              v40 = *v39;
              if ( !(_WORD)v40 )
                break;
              v35 += v40;
              ++v38;
              v39 = (unsigned __int16 *)((char *)v39 + v40);
            }
            while ( v39 );
          }
          else
          {
            v35 = 0;
          }
          if ( v34 == v38 && (_DWORD)v36 == v35 && !memcmp_0(v30, v31, (unsigned int)v36) )
          {
            v32 = 0;
          }
          else
          {
            v41 = *(__int64 **)pAptQualifier;
            *(_QWORD *)pAptType = 0;
            if ( (***(int (__fastcall ****)(_QWORD, GUID *, APTTYPE *, __int64))pAptQualifier)(
                   *(_QWORD *)pAptQualifier,
                   &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                   pAptType,
                   v36) >= 0 )
            {
              v15 = 0x10000000;
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
            }
            v32 = (*(__int64 (__fastcall **)(__int64 *, __int64, unsigned __int16 *, unsigned __int16 *))(*v41 + 56))(
                    v41,
                    v15,
                    v30,
                    v31);
          }
        }
      }
      v42 = *(__int64 **)pAptQualifier;
      if ( *(_QWORD *)pAptQualifier )
      {
        *(_QWORD *)pAptQualifier = 0;
        (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
      }
      if ( v32 )
      {
LABEL_100:
        if ( !v48[17] )
        {
          if ( (unsigned int)CShellItem::_IsDesktop((CShellItem *)v48) )
          {
            SHILClone(v48[18], v48 + 17);
          }
          else
          {
            ItemFromObjectWorker = CShellItem::_EnsureParentIdList((CShellItem *)v48);
            if ( ItemFromObjectWorker < 0 )
              goto LABEL_73;
            ItemFromObjectWorker = SHILCombine(v48[20], v48[18], v48 + 17);
            if ( ItemFromObjectWorker < 0 )
              goto LABEL_73;
          }
        }
        *(_QWORD *)pAptQualifier = 0;
        if ( _GetIDListFromObjectWorker(a2, (struct _ITEMIDLIST_ABSOLUTE **)pAptQualifier) < 0 )
        {
          *(_QWORD *)pAptType = 0;
          ItemFromObjectWorker = _GetItemFromObjectWorker(
                                   a2,
                                   &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
                                   (void **)pAptType);
          if ( ItemFromObjectWorker < 0
            || (ItemFromObjectWorker = (*(__int64 (__fastcall **)(_QWORD, APTTYPEQUALIFIER *))(**(_QWORD **)pAptType
                                                                                             + 40LL))(
                                         *(_QWORD *)pAptType,
                                         pAptQualifier),
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType),
                ItemFromObjectWorker < 0) )
          {
LABEL_73:
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, APTTYPE *)))(*v55)[2])(v55);
            CoTaskMemFree(pv);
            CoTaskMemFree(v57);
            goto LABEL_74;
          }
        }
        *(_QWORD *)pAptType = 0;
        ItemFromObjectWorker = SHGetDesktopFolder((IShellFolder **)pAptType);
        v17 = v54;
        if ( ItemFromObjectWorker >= 0 )
        {
          ItemFromObjectWorker = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)pAptType + 56LL))(
                                   *(_QWORD *)pAptType,
                                   (unsigned int)v54 & 0xF0000000,
                                   *((_QWORD *)v52 + 16),
                                   *(_QWORD *)pAptQualifier);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
        }
        CoTaskMemFree(*(LPVOID *)pAptQualifier);
LABEL_39:
        if ( ItemFromObjectWorker >= 0 )
        {
          *a4 = (__int16)ItemFromObjectWorker;
          if ( (_WORD)ItemFromObjectWorker )
          {
            if ( (v17 & 0x20000000) != 0 )
            {
              *(_QWORD *)pAptType = 0;
              *(_QWORD *)pAptQualifier = 0;
              if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, APTTYPEQUALIFIER *))v12->lpVtbl->BindToHandler)(
                     v12,
                     0,
                     &BHID_SFObject,
                     &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
                     pAptQualifier) >= 0 )
              {
                v52 = 0;
                v18 = (*(__int64 (__fastcall **)(_QWORD, CShellItem **))(**(_QWORD **)pAptQualifier + 32LL))(
                        *(_QWORD *)pAptQualifier,
                        &v52);
                if ( v18 >= 0 )
                {
                  v18 = (**(__int64 (__fastcall ***)(CShellItem *, GUID *, APTTYPE *))v52)(
                          v52,
                          &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                          pAptType);
                  (*(void (__fastcall **)(CShellItem *))(*(_QWORD *)v52 + 16LL))(v52);
                }
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
                if ( v18 >= 0 )
                  goto LABEL_47;
              }
              if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, APTTYPE *))v12->lpVtbl->QueryInterface)(
                     v12,
                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                     pAptType) >= 0 )
              {
LABEL_47:
                *(_QWORD *)pAptQualifier = 0;
                v54 = 0;
                if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, const GUID *, GUID *, __int64 *))a2->lpVtbl[1].QueryInterface)(
                       a2,
                       0,
                       &BHID_SFObject,
                       &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
                       &v54) >= 0 )
                {
                  v52 = 0;
                  v19 = (*(__int64 (__fastcall **)(__int64, CShellItem **))(*(_QWORD *)v54 + 32LL))(v54, &v52);
                  if ( v19 >= 0 )
                  {
                    v19 = (**(__int64 (__fastcall ***)(CShellItem *, GUID *, APTTYPEQUALIFIER *))v52)(
                            v52,
                            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                            pAptQualifier);
                    (*(void (__fastcall **)(CShellItem *))(*(_QWORD *)v52 + 16LL))(v52);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
                  if ( v19 >= 0 )
                    goto LABEL_52;
                }
                if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, APTTYPEQUALIFIER *))a2->lpVtbl->QueryInterface)(
                       a2,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       pAptQualifier) >= 0 )
                {
LABEL_52:
                  lpString1 = 0;
                  v63 = 0;
                  v64 = 0;
                  v20 = **(_QWORD **)pAptType;
                  v63 = -1;
                  v64 = -1;
                  if ( (*(int (__fastcall **)(_QWORD, __int64, LPCWCH *))(v20 + 40))(
                         *(_QWORD *)pAptType,
                         2147647488LL,
                         &lpString1) >= 0 )
                  {
                    lpString2 = 0;
                    v60 = 0;
                    v61 = 0;
                    v21 = **(_QWORD **)pAptQualifier;
                    v60 = -1;
                    v61 = -1;
                    if ( (*(int (__fastcall **)(_QWORD, __int64, LPCWCH *))(v21 + 40))(
                           *(_QWORD *)pAptQualifier,
                           2147647488LL,
                           &lpString2) >= 0 )
                    {
                      v22 = v60;
                      if ( v60 == -1 )
                      {
                        if ( lpString2 )
                        {
                          do
                            ++v22;
                          while ( lpString2[v22] );
                        }
                        else
                        {
                          LODWORD(v22) = 0;
                        }
                      }
                      v23 = &WindowName;
                      v24 = &WindowName;
                      if ( lpString2 )
                        v24 = lpString2;
                      v25 = v63;
                      if ( v63 == -1 )
                      {
                        if ( lpString1 )
                        {
                          do
                            ++v25;
                          while ( lpString1[v25] );
                        }
                        else
                        {
                          LODWORD(v25) = 0;
                        }
                      }
                      if ( lpString1 )
                        v23 = lpString1;
                      v26 = CompareStringOrdinal(v23, v25, v24, v22, 1);
                      *a4 = v26 - 2;
                      ItemFromObjectWorker = v26 != 2;
                    }
                    if ( lpString2 )
                      CoTaskMemFree((LPVOID)lpString2);
                  }
                  if ( lpString1 )
                    CoTaskMemFree((LPVOID)lpString1);
                }
                v27 = *(__int64 **)pAptQualifier;
                if ( *(_QWORD *)pAptQualifier )
                {
                  *(_QWORD *)pAptQualifier = 0;
                  (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
                }
              }
              v28 = *(__int64 **)pAptType;
              if ( *(_QWORD *)pAptType )
              {
                *(_QWORD *)pAptType = 0;
                (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
              }
            }
            else
            {
              ItemFromObjectWorker = 1;
            }
          }
          else
          {
            ItemFromObjectWorker = 0;
          }
        }
        goto LABEL_73;
      }
    }
    v5 = v52;
LABEL_38:
    v17 = v54;
    ItemFromObjectWorker = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *), _QWORD, _QWORD, LPVOID))(*v53)[7])(
                             v53,
                             (unsigned int)v54 & 0xF0000000,
                             *((_QWORD *)v5 + 17),
                             v57);
    goto LABEL_39;
  }
  ItemFromObjectWorker = ApartmentType;
LABEL_77:
  if ( ApartmentType >= 0 )
    LeaveCriticalSection(v7);
  return (unsigned int)ItemFromObjectWorker;
}

```

## disassembly

```asm
0x1800ce3a0  push    rbp
0x1800ce3a2  push    rbx
0x1800ce3a3  push    rsi
0x1800ce3a4  push    rdi
0x1800ce3a5  push    r12
0x1800ce3a7  push    r13
0x1800ce3a9  push    r14
0x1800ce3ab  push    r15
0x1800ce3ad  lea     rbp, [rsp-1F8h]
0x1800ce3b5  sub     rsp, 2F8h
0x1800ce3bc  mov     rax, cs:__security_cookie
0x1800ce3c3  xor     rax, rsp
0x1800ce3c6  mov     [rbp+230h+var_50], rax
0x1800ce3cd  mov     [rsp+330h+var_2F0], r9
0x1800ce3d2  mov     dword ptr [rsp+330h+var_2B8], r8d
0x1800ce3d7  mov     r14, rdx
0x1800ce3da  mov     r15, rcx
0x1800ce3dd  mov     [rsp+330h+var_2C8], rcx
0x1800ce3e2  xor     esi, esi
0x1800ce3e4  mov     [r9], esi
0x1800ce3e7  lea     r12, [rcx-8]
0x1800ce3eb  mov     [rsp+330h+var_2F8], r12
0x1800ce3f0  lea     rdi, [rcx+48h]
0x1800ce3f4  test    r12, r12
0x1800ce3f7  cmovz   rdi, rsi
0x1800ce3fb  mov     [rsp+330h+lpCriticalSection], rdi
0x1800ce400  mov     [rsp+330h+var_2E8], rdi
0x1800ce405  mov     ebx, [rdi+2Ch]
0x1800ce408  cmp     ebx, 2
0x1800ce40b  jz      short loc_1800CE420
0x1800ce40d  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800ce413  test    eax, eax
0x1800ce415  jz      loc_1800CEC74
0x1800ce41b  cmp     eax, 1
0x1800ce41e  jnz     short loc_1800CE489
0x1800ce420  cmp     dword ptr [rdi+28h], 0FFFFFFFDh
0x1800ce424  jz      short loc_1800CE489
0x1800ce426  mov     ebx, esi
0x1800ce428  mov     [rsp+330h+pAptType], esi
0x1800ce42c  mov     [rsp+330h+pAptQualifier], esi
0x1800ce430  lea     rdx, [rsp+330h+pAptQualifier]; pAptQualifier
0x1800ce435  lea     rcx, [rsp+330h+pAptType]; pAptType
0x1800ce43a  call    cs:__imp_CoGetApartmentType
0x1800ce440  mov     r13d, eax
0x1800ce443  test    eax, eax
0x1800ce445  js      short loc_1800CE479
0x1800ce447  mov     edx, [rsp+330h+pAptType]
0x1800ce44b  cmp     edx, 3
0x1800ce44e  jnz     short loc_1800CE45A
0x1800ce450  call    cs:__imp_GetCurrentThreadId
0x1800ce456  mov     ebx, eax
0x1800ce458  jmp     short loc_1800CE470
0x1800ce45a  test    edx, edx
0x1800ce45c  jz      short loc_1800CE450
0x1800ce45e  sub     edx, 1
0x1800ce461  jz      short loc_1800CE470
0x1800ce463  cmp     edx, 1
0x1800ce466  jz      loc_1800CED91
0x1800ce46c  test    eax, eax
0x1800ce46e  js      short loc_1800CE479
0x1800ce470  cmp     ebx, [rdi+28h]
0x1800ce473  jnz     loc_1800CEDFD
0x1800ce479  mov     rcx, [rbp+238h]; this
0x1800ce480  test    r13d, r13d
0x1800ce483  js      loc_1800CECC6
0x1800ce489  mov     rcx, rdi; lpCriticalSection
0x1800ce48c  call    cs:__imp_TryEnterCriticalSection
0x1800ce492  mov     r13d, 8001010Eh
0x1800ce498  test    eax, eax
0x1800ce49a  cmovnz  r13d, esi
0x1800ce49e  mov     [rsp+330h+var_2E0], r13d
0x1800ce4a3  test    r13d, r13d
0x1800ce4a6  js      loc_1800CEE08
0x1800ce4ac  mov     rdi, r15
0x1800ce4af  test    r12, r12
0x1800ce4b2  cmovz   rdi, rsi
0x1800ce4b6  test    rdi, rdi
0x1800ce4b9  jz      loc_1800CE54D
0x1800ce4bf  test    r14, r14
0x1800ce4c2  jz      loc_1800CE54D
0x1800ce4c8  cmp     rdi, r14
0x1800ce4cb  jz      loc_1800CEC35
0x1800ce4d1  mov     qword ptr [rsp+330h+pAptQualifier], rsi
0x1800ce4d6  mov     [rsp+330h+var_2C0], rsi
0x1800ce4db  mov     rax, [rdi]
0x1800ce4de  lea     r8, [rsp+330h+pAptQualifier]
0x1800ce4e3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800ce4ea  mov     rcx, rdi
0x1800ce4ed  mov     rax, [rax]
0x1800ce4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce4f5  test    eax, eax
0x1800ce4f7  js      short loc_1800CE54D
0x1800ce4f9  mov     rax, [r14]
0x1800ce4fc  lea     r8, [rsp+330h+var_2C0]
0x1800ce501  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800ce508  mov     rcx, r14
0x1800ce50b  mov     rax, [rax]
0x1800ce50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce513  test    eax, eax
0x1800ce515  js      loc_1800CED7B
0x1800ce51b  mov     rcx, [rsp+330h+var_2C0]
0x1800ce520  mov     rax, [rcx]
0x1800ce523  mov     rax, [rax+10h]
0x1800ce527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce52c  mov     rcx, qword ptr [rsp+330h+pAptQualifier]
0x1800ce531  mov     rax, [rcx]
0x1800ce534  mov     rax, [rax+10h]
0x1800ce538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce53d  mov     rax, [rsp+330h+var_2C0]
0x1800ce542  cmp     qword ptr [rsp+330h+pAptQualifier], rax
0x1800ce547  jz      loc_1800CEC35
0x1800ce54d  mov     [rsp+330h+var_2C0], rsi
0x1800ce552  lea     rsi, [r15+0A8h]
0x1800ce559  cmp     qword ptr [rsi], 0
0x1800ce55d  jz      loc_1800CEC41
0x1800ce563  mov     rcx, [rsi]
0x1800ce566  mov     rax, [rcx]
0x1800ce569  lea     r8, [rsp+330h+var_2C0]
0x1800ce56e  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800ce575  mov     rax, [rax]
0x1800ce578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce57d  mov     ebx, eax
0x1800ce57f  test    eax, eax
0x1800ce581  js      loc_1800CE9EB
0x1800ce587  xor     esi, esi
0x1800ce589  mov     [rbp+230h+var_298], rsi
0x1800ce58d  mov     rax, [r14]
0x1800ce590  lea     r8, [rbp+230h+var_298]
0x1800ce594  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x1800ce59b  mov     rcx, r14
0x1800ce59e  mov     rax, [rax]
0x1800ce5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce5a6  mov     ebx, eax
0x1800ce5a8  test    eax, eax
0x1800ce5aa  js      loc_1800CE9DA
0x1800ce5b0  mov     [rbp+230h+var_2B0], rsi
0x1800ce5b4  mov     [rbp+230h+pv], rsi
0x1800ce5b8  mov     [rbp+230h+var_2A0], rsi
0x1800ce5bc  mov     rcx, [rbp+230h+var_298]
0x1800ce5c0  mov     rax, [rcx]
0x1800ce5c3  lea     r9, [rbp+230h+var_2A0]
0x1800ce5c7  lea     r8, [rbp+230h+var_2B0]
0x1800ce5cb  lea     rdx, [rbp+230h+pv]
0x1800ce5cf  mov     rax, [rax+20h]
0x1800ce5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce5d8  mov     ebx, eax
0x1800ce5da  test    eax, eax
0x1800ce5dc  js      loc_1800CE9CA
0x1800ce5e2  cmp     [r12+0A0h], rsi
0x1800ce5ea  jz      loc_1800CED47
0x1800ce5f0  mov     rcx, [rsp+330h+var_2C0]
0x1800ce5f5  test    rcx, rcx
0x1800ce5f8  jz      loc_1800CEA34
0x1800ce5fe  mov     rbx, [rbp+230h+var_2B0]
0x1800ce602  test    rbx, rbx
0x1800ce605  jz      loc_1800CEA34
0x1800ce60b  cmp     rcx, rbx
0x1800ce60e  jz      short loc_1800CE68D
0x1800ce610  mov     qword ptr [rsp+330h+pAptQualifier], rsi
0x1800ce615  mov     qword ptr [rsp+330h+pAptType], rsi
0x1800ce61a  mov     rax, [rcx]
0x1800ce61d  lea     r8, [rsp+330h+pAptQualifier]
0x1800ce622  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800ce629  mov     rax, [rax]
0x1800ce62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce631  test    eax, eax
0x1800ce633  js      loc_1800CEA34
0x1800ce639  mov     rax, [rbx]
0x1800ce63c  lea     r8, [rsp+330h+pAptType]
0x1800ce641  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800ce648  mov     rcx, rbx
0x1800ce64b  mov     rax, [rax]
0x1800ce64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce653  test    eax, eax
0x1800ce655  js      loc_1800CEA23
0x1800ce65b  mov     rcx, qword ptr [rsp+330h+pAptType]
0x1800ce660  mov     rax, [rcx]
0x1800ce663  mov     rax, [rax+10h]
0x1800ce667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce66c  mov     rcx, qword ptr [rsp+330h+pAptQualifier]
0x1800ce671  mov     rax, [rcx]
0x1800ce674  mov     rax, [rax+10h]
0x1800ce678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce67d  mov     rax, qword ptr [rsp+330h+pAptType]
0x1800ce682  cmp     qword ptr [rsp+330h+pAptQualifier], rax
0x1800ce687  jnz     loc_1800CEA34
0x1800ce68d  mov     rcx, [rsp+330h+var_2C0]
0x1800ce692  mov     rax, [rcx]
0x1800ce695  mov     esi, dword ptr [rsp+330h+var_2B8]
0x1800ce699  mov     edx, esi
0x1800ce69b  mov     r9d, 0F0000000h
0x1800ce6a1  and     rdx, r9
0x1800ce6a4  mov     r9, [rbp+230h+var_2A0]
0x1800ce6a8  mov     r8, [r15+88h]
0x1800ce6af  mov     rax, [rax+38h]
0x1800ce6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce6b8  mov     ebx, eax
0x1800ce6ba  xor     r12d, r12d
0x1800ce6bd  test    ebx, ebx
0x1800ce6bf  js      loc_1800CE9A6
0x1800ce6c5  movsx   eax, bx
0x1800ce6c8  mov     r15, [rsp+330h+var_2F0]
0x1800ce6cd  mov     [r15], eax
0x1800ce6d0  test    bx, bx
0x1800ce6d3  jz      loc_1800CED35
0x1800ce6d9  bt      esi, 1Dh
0x1800ce6dd  jnb     loc_1800CED3D
0x1800ce6e3  mov     qword ptr [rsp+330h+pAptType], r12
0x1800ce6e8  mov     qword ptr [rsp+330h+pAptQualifier], r12
0x1800ce6ed  mov     rax, [rdi]
0x1800ce6f0  lea     rcx, [rsp+330h+pAptQualifier]
0x1800ce6f5  mov     qword ptr [rsp+330h+bIgnoreCase], rcx
0x1800ce6fa  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x1800ce701  lea     r8, BHID_SFObject
0x1800ce708  xor     edx, edx
0x1800ce70a  mov     rcx, rdi
0x1800ce70d  mov     rax, [rax+18h]
0x1800ce711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce716  test    eax, eax
0x1800ce718  js      short loc_1800CE77F
0x1800ce71a  mov     [rsp+330h+var_2C8], r12
0x1800ce71f  mov     rcx, qword ptr [rsp+330h+pAptQualifier]
0x1800ce724  mov     rax, [rcx]
0x1800ce727  lea     rdx, [rsp+330h+var_2C8]
0x1800ce72c  mov     rax, [rax+20h]
0x1800ce730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce735  mov     esi, eax
0x1800ce737  test    eax, eax
0x1800ce739  js      short loc_1800CE76A
0x1800ce73b  mov     rcx, [rsp+330h+var_2C8]
0x1800ce740  mov     rax, [rcx]
0x1800ce743  lea     r8, [rsp+330h+pAptType]
0x1800ce748  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800ce74f  mov     rax, [rax]
0x1800ce752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce757  mov     esi, eax
0x1800ce759  mov     rcx, [rsp+330h+var_2C8]
0x1800ce75e  mov     rax, [rcx]
0x1800ce761  mov     rax, [rax+10h]
0x1800ce765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce76a  mov     rcx, qword ptr [rsp+330h+pAptQualifier]
0x1800ce76f  mov     rax, [rcx]
0x1800ce772  mov     rax, [rax+10h]
0x1800ce776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce77b  test    esi, esi
0x1800ce77d  jns     short loc_1800CE7A1
0x1800ce77f  mov     rax, [rdi]
0x1800ce782  lea     r8, [rsp+330h+pAptType]
0x1800ce787  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800ce78e  mov     rcx, rdi
0x1800ce791  mov     rax, [rax]
0x1800ce794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce799  test    eax, eax
0x1800ce79b  js      loc_1800CE98A
0x1800ce7a1  mov     qword ptr [rsp+330h+pAptQualifier], r12
0x1800ce7a6  mov     [rsp+330h+var_2B8], r12
0x1800ce7ab  mov     rax, [r14]
0x1800ce7ae  lea     rcx, [rsp+330h+var_2B8]
0x1800ce7b3  mov     qword ptr [rsp+330h+bIgnoreCase], rcx
0x1800ce7b8  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x1800ce7bf  lea     r8, BHID_SFObject
0x1800ce7c6  xor     edx, edx
0x1800ce7c8  mov     rcx, r14
0x1800ce7cb  mov     rax, [rax+18h]
0x1800ce7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce7d4  test    eax, eax
0x1800ce7d6  js      short loc_1800CE83D
0x1800ce7d8  mov     [rsp+330h+var_2C8], r12
0x1800ce7dd  mov     rcx, [rsp+330h+var_2B8]
0x1800ce7e2  mov     rax, [rcx]
0x1800ce7e5  lea     rdx, [rsp+330h+var_2C8]
0x1800ce7ea  mov     rax, [rax+20h]
0x1800ce7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce7f3  mov     edi, eax
0x1800ce7f5  test    eax, eax
0x1800ce7f7  js      short loc_1800CE828
0x1800ce7f9  mov     rcx, [rsp+330h+var_2C8]
0x1800ce7fe  mov     rax, [rcx]
0x1800ce801  lea     r8, [rsp+330h+pAptQualifier]
0x1800ce806  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800ce80d  mov     rax, [rax]
0x1800ce810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce815  mov     edi, eax
0x1800ce817  mov     rcx, [rsp+330h+var_2C8]
0x1800ce81c  mov     rax, [rcx]
0x1800ce81f  mov     rax, [rax+10h]
0x1800ce823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce828  mov     rcx, [rsp+330h+var_2B8]
0x1800ce82d  mov     rax, [rcx]
0x1800ce830  mov     rax, [rax+10h]
0x1800ce834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce839  test    edi, edi
0x1800ce83b  jns     short loc_1800CE85F
0x1800ce83d  mov     rax, [r14]
0x1800ce840  lea     r8, [rsp+330h+pAptQualifier]
0x1800ce845  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800ce84c  mov     rcx, r14
0x1800ce84f  mov     rax, [rax]
0x1800ce852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce857  test    eax, eax
  ... truncated ...
```
