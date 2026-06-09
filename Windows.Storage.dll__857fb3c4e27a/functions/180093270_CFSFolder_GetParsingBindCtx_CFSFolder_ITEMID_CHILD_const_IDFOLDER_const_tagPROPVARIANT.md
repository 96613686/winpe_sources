# CFSFolder::_GetParsingBindCtx(CFSFolder *,_ITEMID_CHILD const *,IDFOLDER const *,tagPROPVARIANT *)

- ea: `0x180093270`
- end: `0x180093c10`
- name: `?_GetParsingBindCtx@CFSFolder@@KAJPEAV1@PEFBU_ITEMID_CHILD@@PEFBUIDFOLDER@@PEAUtagPROPVARIANT@@@Z`
- size: `2464`
- prototype: `__int64 __fastcall(struct CFSFolder *, const struct _ITEMID_CHILD *, const struct IDFOLDER *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180041b00`
- `0x180043320`
- `0x180047ec0`
- `0x1800495e0`
- `0x18005bf00`
- `0x180092210`
- `0x180093270`
- `0x180093c20`
- `0x180093ef0`
- `0x1800979d0`
- `0x18009d164`
- `0x1800d998c`
- `0x180155330`
- `0x1801553f0`
- `0x1803a4cb0`
- `0x1803a518c`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800939d1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180093b2b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800939d1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180093b2b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800932eb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180093a1e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180093a37`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800932eb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180093a1e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180093a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009389e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009394c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009395c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009396c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009389e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009394c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009395c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009396c`
- `SHCORE!__imp_ualstrcpynW` at `0x180093415`
- `SHCORE!__imp_ualstrcpynW` at `0x180093a9d`
- `SHCORE!__imp_ualstrcpynW` at `0x180093415`
- `SHCORE!__imp_ualstrcpynW` at `0x180093a9d`
- `SHCORE!__imp_ualstrlenW` at `0x180093acc`
- `SHCORE!__imp_ualstrlenW` at `0x180093b96`
- `SHCORE!__imp_ualstrlenW` at `0x180093acc`
- `SHCORE!__imp_ualstrlenW` at `0x180093b96`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800936b3`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800936b3`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18009364c`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18009364c`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180093bfb`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180093bfb`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x180093524`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x180093524`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFSFolder::_GetParsingBindCtx(
        struct _GUID *a1,
        const struct _ITEMID_CHILD *a2,
        const struct IDFOLDER *a3,
        struct tagPROPVARIANT *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  struct IDFOLDER *v11; // r10
  WCHAR *v12; // rdx
  WCHAR *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  WCHAR *v16; // r8
  WCHAR v17; // ax
  WCHAR *v18; // rcx
  LPITEMIDLIST v19; // rsi
  unsigned int v20; // r8d
  HRESULT inited; // ebx
  char *v22; // rdi
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rax
  LPBC v27; // rdi
  int v28; // ebx
  __int64 v29; // rax
  const ITEMIDLIST *v30; // rcx
  int v31; // eax
  const ITEMIDLIST *v32; // rcx
  CShellItem *v33; // rax
  CShellItem *v34; // rax
  CShellItem *v35; // rdi
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  const void *v40; // rbx
  unsigned __int64 v41; // r8
  __int64 v42; // r8
  unsigned __int64 *v43; // r8
  unsigned int v44; // ecx
  int v45; // eax
  int v46; // eax
  unsigned int v47; // ecx
  int v48; // eax
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPBC ppbc; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+40h] [rbp-C0h] BYREF
  struct IShellItem *v52[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v53[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v54; // [rsp+70h] [rbp-90h]
  LPVOID v55; // [rsp+78h] [rbp-88h]
  LPVOID pv; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  struct IDFOLDER *v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h]
  WCHAR *v62; // [rsp+C8h] [rbp-38h]
  int v63; // [rsp+E0h] [rbp-20h]
  WCHAR value[278]; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned int FullFileAttributes; // [rsp+310h] [rbp+210h] BYREF
  struct _FILETIME v66; // [rsp+314h] [rbp+214h] BYREF
  struct _FILETIME v67; // [rsp+31Ch] [rbp+21Ch] BYREF
  struct _FILETIME FileTime; // [rsp+324h] [rbp+224h] BYREF
  int v69; // [rsp+32Ch] [rbp+22Ch]
  int v70; // [rsp+330h] [rbp+230h]
  int v71; // [rsp+334h] [rbp+234h]
  char v72; // [rsp+33Ch] [rbp+23Ch] BYREF
  WCHAR WideCharStr[14]; // [rsp+544h] [rbp+444h] BYREF
  __int64 v74; // [rsp+560h] [rbp+460h]
  _BYTE v75[24]; // [rsp+568h] [rbp+468h] BYREF
  __int128 v76; // [rsp+580h] [rbp+480h] BYREF
  _OWORD v77[2]; // [rsp+590h] [rbp+490h]

  CFileSysItemString::CFileSysItemString((CFileSysItemString *)v53, (struct CFSFolder *)a1, a2, a3);
  memset_0(&FullFileAttributes, 0, 0x268u);
  v8 = v61;
  if ( DosDateTimeToFileTime(*((_WORD *)v60 + 4), *((_WORD *)v60 + 5), &FileTime)
    || (int)ResultFromKnownLastError() >= 0 )
  {
    if ( v8 )
    {
      if ( *(_WORD *)(v8 + 2) >= 9u )
      {
        v9 = *(unsigned int *)(v8 + 42);
        if ( (_DWORD)v9 )
        {
          v10 = FileTime.dwLowDateTime + ((unsigned __int64)FileTime.dwHighDateTime << 32) - v9;
          FileTime.dwLowDateTime -= v9;
          FileTime.dwHighDateTime = HIDWORD(v10);
        }
      }
    }
  }
  FullFileAttributes = GetFullFileAttributes(v60);
  v11 = v60;
  v70 = *((_DWORD *)v60 + 1);
  if ( v62 )
    goto LABEL_92;
  if ( (v63 & 1) == 0 )
  {
    if ( v61 )
    {
      v12 = (WCHAR *)(v61 + *(unsigned __int16 *)(v61 + 16));
      if ( ((unsigned __int8)v12 & 1) == 0 )
      {
        if ( v12 != value )
        {
          v62 = (WCHAR *)(v61 + *(unsigned __int16 *)(v61 + 16));
          goto LABEL_12;
        }
LABEL_99:
        v63 = 1;
LABEL_12:
        if ( !v62 )
          goto LABEL_13;
LABEL_92:
        v13 = v62;
        goto LABEL_14;
      }
    }
    else
    {
      if ( (*((_BYTE *)v60 + 2) & 0x34) != 0x34 )
      {
        MultiByteToWideChar(0, 0, (LPCCH)v60 + 14, -1, value, 260);
        goto LABEL_98;
      }
      v12 = (WCHAR *)((char *)v60 + 14);
    }
    ualstrcpynW(value, v12, 260);
LABEL_98:
    v11 = v60;
    goto LABEL_99;
  }
LABEL_13:
  v13 = value;
LABEL_14:
  v14 = 2147483646;
  v15 = 260;
  v16 = (WCHAR *)&v72;
  do
  {
    if ( !v14 )
      break;
    v17 = *v13;
    if ( !*v13 )
      break;
    ++v13;
    *v16++ = v17;
    --v14;
    --v15;
  }
  while ( v15 );
  v18 = v16 - 1;
  if ( v15 )
    v18 = v16;
  v19 = 0;
  *v18 = 0;
  v20 = 0;
  if ( (*((_BYTE *)v11 + 2) & 0x34) == 0x34 )
  {
    if ( !v61 )
    {
      v46 = ualstrlenW((char *)v11 + 14, v13, 0, v15);
      v11 = v60;
      v47 = *(unsigned __int16 *)v60;
      if ( v47 <= 2 * v46 + 16
        || (v48 = UnalignedStringCbLengthW(
                    (const unsigned __int16 *)((char *)v60 + (unsigned int)(2 * v46 + 2) + 14),
                    v47 - (2 * v46 + 2) - 14,
                    (unsigned __int64 *)(unsigned int)(2 * v46 + 2)),
            v11 = v60,
            v48 < 0) )
      {
        v20 = 0;
      }
    }
    ualstrcpynW(WideCharStr, (char *)v11 + v20 + 14, 14);
  }
  else
  {
    if ( !v61 )
    {
      v42 = -1;
      do
        ++v42;
      while ( *((_BYTE *)v11 + v42 + 14) );
      v43 = (unsigned __int64 *)(unsigned int)(v42 + 1);
      v44 = *(unsigned __int16 *)v11;
      if ( v44 <= (int)v43 + 14
        || (v45 = StringCbLengthA((const char *)v11 + (unsigned int)v43 + 14, v44 - (unsigned int)v43 - 14, v43),
            v11 = v60,
            v45 < 0) )
      {
        v20 = 0;
      }
    }
    if ( !MultiByteToWideChar(0, 0, (LPCCH)v11 + v20 + 14, -1, WideCharStr, 14) )
      memset(WideCharStr, 0, sizeof(WideCharStr));
  }
  if ( v61 )
  {
    DosDateTimeToFileTime(*(_WORD *)(v61 + 8), *(_WORD *)(v61 + 10), &v66);
    DosDateTimeToFileTime(*(_WORD *)(v61 + 12), *(_WORD *)(v61 + 14), &v67);
    if ( *(_WORD *)(v61 + 2) >= 7u )
    {
      v74 = *(_QWORD *)(v61 + 20);
      v71 = *(_DWORD *)(v61 + 32);
      v69 = *(_DWORD *)(v61 + 28);
    }
  }
  v51 = 0;
  inited = -2147024882;
  v22 = (char *)operator new(0x278u, (const struct std::nothrow_t *)&std::nothrow);
  v52[0] = (struct IShellItem *)v22;
  if ( v22 )
  {
    *(_QWORD *)v22 = &CFileSysBindData::`vftable';
    *((_DWORD *)v22 + 2) = 1;
    memset_0(v22 + 40, 0, 0x250u);
    *((_QWORD *)v22 + 2) = 0;
    *(_OWORD *)(v22 + 24) = xmmword_180702890;
    inited = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v22)(
               v22,
               &GUID_3acf075f_71db_4afa_81f0_3fc4fdf2a5b8,
               &v51);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
    if ( inited >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v51 + 24LL))(v51, &FullFileAttributes);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 40LL))(v51, v74);
      CFileSysItemString::GetJunctionClsid(v53, 1, v75);
      (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v51 + 56LL))(v51, v75);
      ppbc = 0;
      inited = CreateBindCtx(0, &ppbc);
      if ( inited < 0 )
      {
LABEL_75:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        goto LABEL_76;
      }
      v52[0] = (struct IShellItem *)16;
      v52[1] = (struct IShellItem *)4096;
      inited = ((__int64 (__fastcall *)(LPBC, struct IShellItem **))ppbc->lpVtbl->SetBindOptions)(ppbc, v52);
      if ( inited < 0 )
      {
        SafeRelease<IFilterCreationCallback>(&ppbc);
        goto LABEL_75;
      }
      inited = ((__int64 (__fastcall *)(LPBC, const unsigned __int16 *, __int64))ppbc->lpVtbl->RegisterObjectParam)(
                 ppbc,
                 L"File System Bind Data",
                 v51);
      if ( inited < 0 )
        goto LABEL_74;
      if ( (v63 & 4) == 0 )
      {
        value[0] = 0;
        if ( v61 )
        {
          if ( *(_WORD *)(v61 + 2) >= 7u && (v25 = *(unsigned __int16 *)(v61 + 36), (_WORD)v25) )
          {
            v40 = (const void *)(v61 + v25);
            v41 = ualstrlenW(v61 + v25, v61, v23, v24) + 1;
            if ( v41 <= 0x104 )
            {
              memcpy_0(value, v40, 2 * v41);
              goto LABEL_35;
            }
          }
          else
          {
            v26 = *(unsigned __int16 *)(v61 + 18);
            if ( (_WORD)v26 )
            {
              SHAnsiToUnicode((PCSTR)(v61 + v26), value, 260);
              goto LABEL_35;
            }
          }
        }
        value[0] = 0;
      }
LABEL_35:
      v63 = 4;
      if ( value[0] )
      {
        v27 = ppbc;
        if ( ppbc )
        {
          ppv = 0;
          v52[0] = 0;
          if ( ((int (__fastcall *)(LPBC, const unsigned __int16 *, struct IShellItem **))ppbc->lpVtbl->GetObjectParam)(
                 ppbc,
                 L"SHBindCtxPropertyBag",
                 v52) >= 0
            && (v28 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, void **))v52[0]->lpVtbl->QueryInterface)(
                        v52[0],
                        &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                        &ppv),
                ((void (__fastcall *)(struct IShellItem *))v52[0]->lpVtbl->Release)(v52[0]),
                v28 >= 0)
            || (inited = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv), inited >= 0)
            && (v76 = *(_OWORD *)L"SHBindCtxPropertyBag",
                v77[0] = *(_OWORD *)L"xPropertyBag",
                *(_OWORD *)((char *)v77 + 10) = *(_OWORD *)L"ertyBag",
                inited = ((__int64 (__fastcall *)(LPBC, __int128 *, void *))v27->lpVtbl->RegisterObjectParam)(
                           v27,
                           &v76,
                           ppv),
                inited >= 0) )
          {
            inited = PSPropertyBag_WriteStr((IPropertyBag *)ppv, L"LocalizedResourceName", value);
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        else
        {
          inited = -2147024809;
        }
        if ( inited < 0 )
          goto LABEL_74;
      }
      if ( !ILFindFirstHiddenID(a2) )
        goto LABEL_72;
      v52[0] = 0;
      v29 = *(_QWORD *)&a1[31].Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v29 )
        v29 = *(_QWORD *)a1[31].Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( v29 )
      {
        v31 = SHGetKnownFolderIDList_Internal(a1 + 31, 0x1000u, 0, (struct _ITEMIDLIST_ABSOLUTE **)v52);
        v19 = (LPITEMIDLIST)v52[0];
      }
      else
      {
        v30 = *(const ITEMIDLIST **)a1[27].Data4;
        if ( !v30 )
          goto LABEL_52;
        v19 = ILClone(v30);
        v31 = 0;
        if ( !v19 )
          v31 = -2147024882;
      }
      if ( v31 >= 0 )
        goto LABEL_56;
      v19 = 0;
LABEL_52:
      v32 = *(const ITEMIDLIST **)&a1[27].Data1;
      if ( v32 )
      {
        v19 = ILClone(v32);
        inited = 0;
        if ( !v19 )
          inited = -2147024882;
      }
      else
      {
        inited = -2147024809;
      }
      if ( inited < 0 )
        goto LABEL_74;
LABEL_56:
      v52[0] = 0;
      ppv = 0;
      inited = -2147024882;
      v33 = (CShellItem *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v33 )
      {
        v34 = CShellItem::CShellItem(v33);
        v35 = v34;
        if ( v34 )
        {
          inited = CObjectWithThreadUseDetection::InitApartmentId((CShellItem *)((char *)v34 + 80));
          if ( inited >= 0 )
            inited = (**(__int64 (__fastcall ***)(CShellItem *, GUID *, void **))v35)(
                       v35,
                       &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                       &ppv);
          (*(void (__fastcall **)(CShellItem *))(*(_QWORD *)v35 + 16LL))(v35);
          if ( inited < 0 )
          {
LABEL_71:
            CoTaskMemFree(v19);
            if ( inited >= 0 )
            {
LABEL_72:
              inited = ((__int64 (__fastcall *)(LPBC, GUID *, ULONG *))ppbc->lpVtbl->QueryInterface)(
                         ppbc,
                         &GUID_00000000_0000_0000_c000_000000000046,
                         &a4->decVal.Lo32);
              if ( inited >= 0 )
                a4->vt = 13;
            }
LABEL_74:
            ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
            goto LABEL_75;
          }
          inited = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, _QWORD, const struct _ITEMID_CHILD *))(*(_QWORD *)ppv + 24LL))(
                     ppv,
                     v19,
                     0,
                     a2);
          if ( inited >= 0 )
            inited = (**(__int64 (__fastcall ***)(void *, GUID *, struct IShellItem **))ppv)(
                       ppv,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       v52);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
      }
      if ( inited >= 0 )
      {
        if ( ((((*((_BYTE *)a3 + 2) & 0x37) - 50) & 0xFB) != 0 || (unsigned int)(*((_DWORD *)a3 + 1) - 1) <= 0xFFFFFFFD)
          && *((_WORD *)a3 + 4)
          || (inited = MarkItemAsSimple(v52[0]), inited >= 0) )
        {
          inited = ((__int64 (__fastcall *)(LPBC, const unsigned __int16 *, struct IShellItem *))ppbc->lpVtbl->RegisterObjectParam)(
                     ppbc,
                     L"ParseOriginalItem",
                     v52[0]);
        }
        ((void (__fastcall *)(struct IShellItem *))v52[0]->lpVtbl->Release)(v52[0]);
      }
      goto LABEL_71;
    }
  }
LABEL_76:
  v53[0] = &CFileSysItemString::`vftable';
  v36 = v59;
  v59 = 0;
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  v37 = v57;
  v57 = 0;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  v38 = v58;
  v58 = 0;
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v55 )
    CoTaskMemFree(v55);
  if ( v54 )
    CoTaskMemFree(v54);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180093270  mov     [rsp-8+arg_10], rbx
0x180093275  push    rbp
0x180093276  push    rsi
0x180093277  push    rdi
0x180093278  push    r12
0x18009327a  push    r13
0x18009327c  push    r14
0x18009327e  push    r15
0x180093280  lea     rbp, [rsp-4C0h]
0x180093288  sub     rsp, 5C0h
0x18009328f  mov     rax, cs:__security_cookie
0x180093296  xor     rax, rsp
0x180093299  mov     [rbp+4F0h+var_40], rax
0x1800932a0  mov     r13, r9
0x1800932a3  mov     r15, r8
0x1800932a6  mov     r12, rdx
0x1800932a9  mov     r14, rcx
0x1800932ac  mov     r9, r8; struct IDFOLDER *
0x1800932af  mov     r8, rdx; struct _ITEMIDLIST_RELATIVE *
0x1800932b2  mov     rdx, rcx; struct CFSFolder *
0x1800932b5  lea     rcx, [rsp+5F0h+var_590]; this
0x1800932ba  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x1800932bf  nop
0x1800932c0  xor     edx, edx; Val
0x1800932c2  mov     r8d, 268h; Size
0x1800932c8  lea     rcx, [rbp+4F0h+var_2E0]; void *
0x1800932cf  call    memset_0
0x1800932d4  mov     rbx, [rbp+4F0h+var_538]
0x1800932d8  mov     rcx, [rbp+4F0h+var_540]
0x1800932dc  lea     r8, [rbp+4F0h+FileTime]; lpFileTime
0x1800932e3  movzx   edx, word ptr [rcx+0Ah]; wFatTime
0x1800932e7  movzx   ecx, word ptr [rcx+8]; wFatDate
0x1800932eb  call    cs:__imp_DosDateTimeToFileTime
0x1800932f1  test    eax, eax
0x1800932f3  jz      loc_180093AB3
0x1800932f9  test    rbx, rbx
0x1800932fc  jz      short loc_180093332
0x1800932fe  cmp     word ptr [rbx+2], 9
0x180093303  jb      short loc_180093332
0x180093305  mov     eax, [rbx+2Ah]
0x180093308  test    eax, eax
0x18009330a  jz      short loc_180093332
0x18009330c  mov     ecx, [rbp+4F0h+FileTime.dwHighDateTime]
0x180093312  shl     rcx, 20h
0x180093316  sub     rcx, rax
0x180093319  mov     eax, [rbp+4F0h+FileTime.dwLowDateTime]
0x18009331f  add     rcx, rax
0x180093322  mov     [rbp+4F0h+FileTime.dwLowDateTime], ecx
0x180093328  shr     rcx, 20h
0x18009332c  mov     [rbp+4F0h+FileTime.dwHighDateTime], ecx
0x180093332  mov     rcx, [rbp+4F0h+var_540]; struct IDFOLDER *
0x180093336  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x18009333b  mov     [rbp+4F0h+var_2E0], eax
0x180093341  mov     r10, [rbp+4F0h+var_540]
0x180093345  mov     eax, [r10+4]
0x180093349  mov     [rbp+4F0h+var_2C0], eax
0x18009334f  cmp     [rbp+4F0h+var_528], 0
0x180093354  jnz     loc_1800939F5
0x18009335a  test    byte ptr [rbp+4F0h+var_510], 1
0x18009335e  jnz     short loc_180093399
0x180093360  mov     rcx, [rbp+4F0h+var_538]
0x180093364  test    rcx, rcx
0x180093367  jz      loc_180093B01
0x18009336d  movzx   edx, word ptr [rcx+10h]
0x180093371  add     rdx, rcx
0x180093374  test    dl, 1
0x180093377  jnz     loc_180093A93
0x18009337d  lea     rax, [rbp+4F0h+value]
0x180093381  cmp     rdx, rax
0x180093384  jz      loc_180093AA7
0x18009338a  mov     [rbp+4F0h+var_528], rdx
0x18009338e  cmp     [rbp+4F0h+var_528], 0
0x180093393  jnz     loc_1800939F5
0x180093399  lea     rdx, [rbp+4F0h+value]
0x18009339d  mov     ecx, 7FFFFFFEh
0x1800933a2  mov     r9d, 104h
0x1800933a8  lea     r8, [rbp+4F0h+var_2B4]
0x1800933af  nop
0x1800933b0  test    rcx, rcx
0x1800933b3  jz      short loc_1800933D2
0x1800933b5  movzx   eax, word ptr [rdx]
0x1800933b8  test    ax, ax
0x1800933bb  jz      short loc_1800933D2
0x1800933bd  add     rdx, 2
0x1800933c1  mov     [r8], ax
0x1800933c5  add     r8, 2
0x1800933c9  dec     rcx
0x1800933cc  sub     r9, 1
0x1800933d0  jnz     short loc_1800933B0
0x1800933d2  lea     rcx, [r8-2]
0x1800933d6  test    r9, r9
0x1800933d9  cmovnz  rcx, r8
0x1800933dd  xor     esi, esi
0x1800933df  mov     [rcx], si
0x1800933e2  movzx   eax, byte ptr [r10+2]
0x1800933e7  and     al, 34h
0x1800933e9  mov     r8d, esi
0x1800933ec  cmp     al, 34h ; '4'
0x1800933ee  jnz     loc_18009399F
0x1800933f4  cmp     [rbp+4F0h+var_538], rsi
0x1800933f8  jz      loc_180093B92
0x1800933fe  mov     eax, r8d
0x180093401  lea     rdx, [r10+0Eh]
0x180093405  add     rdx, rax
0x180093408  mov     r8d, 0Eh
0x18009340e  lea     rcx, [rbp+4F0h+WideCharStr]
0x180093415  call    cs:__imp_ualstrcpynW
0x18009341b  mov     rcx, [rbp+4F0h+var_538]
0x18009341f  test    rcx, rcx
0x180093422  jnz     loc_180093A0F
0x180093428  mov     [rsp+5F0h+var_5B0], rsi
0x18009342d  mov     ebx, 8007000Eh
0x180093432  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180093439  mov     ecx, 278h; unsigned __int64
0x18009343e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180093443  mov     rdi, rax
0x180093446  mov     [rsp+5F0h+var_5A8], rax
0x18009344b  test    rax, rax
0x18009344e  jz      loc_1800938F4
0x180093454  lea     rax, ??_7CFileSysBindData@@6B@; const CFileSysBindData::`vftable'
0x18009345b  mov     [rdi], rax
0x18009345e  mov     dword ptr [rdi+8], 1
0x180093465  lea     rcx, [rdi+28h]; void *
0x180093469  xor     edx, edx; Val
0x18009346b  mov     r8d, 250h; Size
0x180093471  call    memset_0
0x180093476  xor     eax, eax
0x180093478  mov     [rdi+10h], rax
0x18009347c  movups  xmm0, cs:xmmword_180702890
0x180093483  movups  xmmword ptr [rdi+18h], xmm0
0x180093487  mov     rax, [rdi]
0x18009348a  lea     r8, [rsp+5F0h+var_5B0]
0x18009348f  lea     rdx, _GUID_3acf075f_71db_4afa_81f0_3fc4fdf2a5b8
0x180093496  mov     rcx, rdi
0x180093499  mov     rax, [rax]
0x18009349c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934a1  mov     ebx, eax
0x1800934a3  mov     rax, [rdi]
0x1800934a6  mov     rcx, rdi
0x1800934a9  mov     rax, [rax+10h]
0x1800934ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934b2  test    ebx, ebx
0x1800934b4  js      loc_1800938F4
0x1800934ba  mov     rcx, [rsp+5F0h+var_5B0]
0x1800934bf  mov     rax, [rcx]
0x1800934c2  lea     rdx, [rbp+4F0h+var_2E0]
0x1800934c9  mov     rax, [rax+18h]
0x1800934cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934d2  mov     rcx, [rsp+5F0h+var_5B0]
0x1800934d7  mov     rax, [rcx]
0x1800934da  mov     rdx, [rbp+4F0h+var_90]
0x1800934e1  mov     rax, [rax+28h]
0x1800934e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934ea  lea     r8, [rbp+4F0h+var_88]
0x1800934f1  mov     edx, 1
0x1800934f6  lea     rcx, [rsp+5F0h+var_590]
0x1800934fb  call    ?GetJunctionClsid@CFileSysItemString@@QEAAHW4FSIS_JUNCTION_FLAGS@@PEAU_GUID@@@Z; CFileSysItemString::GetJunctionClsid(FSIS_JUNCTION_FLAGS,_GUID *)
0x180093500  mov     rcx, [rsp+5F0h+var_5B0]
0x180093505  mov     rax, [rcx]
0x180093508  lea     rdx, [rbp+4F0h+var_88]
0x18009350f  mov     rax, [rax+38h]
0x180093513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093518  mov     [rsp+5F0h+ppbc], rsi
0x18009351d  lea     rdx, [rsp+5F0h+ppbc]; ppbc
0x180093522  xor     ecx, ecx; reserved
0x180093524  call    cs:__imp_CreateBindCtx
0x18009352a  mov     ebx, eax
0x18009352c  test    eax, eax
0x18009352e  js      loc_1800938E1
0x180093534  mov     [rsp+5F0h+var_5A8], 10h
0x18009353d  mov     [rsp+5F0h+var_5A0], 1000h
0x180093546  mov     rcx, [rsp+5F0h+ppbc]
0x18009354b  mov     rax, [rcx]
0x18009354e  lea     rdx, [rsp+5F0h+var_5A8]
0x180093553  mov     rax, [rax+30h]
0x180093557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009355c  mov     ebx, eax
0x18009355e  test    eax, eax
0x180093560  js      loc_180093BDE
0x180093566  mov     rcx, [rsp+5F0h+ppbc]
0x18009356b  mov     rax, [rcx]
0x18009356e  mov     r8, [rsp+5F0h+var_5B0]
0x180093573  lea     rdx, aFileSystemBind; "File System Bind Data"
0x18009357a  mov     rax, [rax+48h]
0x18009357e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093583  mov     ebx, eax
0x180093585  test    eax, eax
0x180093587  js      loc_1800938D0
0x18009358d  test    byte ptr [rbp+4F0h+var_510], 4
0x180093591  jnz     short loc_1800935C5
0x180093593  mov     [rbp+4F0h+value], si
0x180093597  mov     rdx, [rbp+4F0h+var_538]
0x18009359b  test    rdx, rdx
0x18009359e  jz      short loc_1800935C1
0x1800935a0  cmp     word ptr [rdx+2], 7
0x1800935a5  jb      short loc_1800935B4
0x1800935a7  movzx   eax, word ptr [rdx+24h]
0x1800935ab  test    ax, ax
0x1800935ae  jnz     loc_180093AC5
0x1800935b4  movzx   eax, word ptr [rdx+12h]
0x1800935b8  test    ax, ax
0x1800935bb  jnz     loc_180093BED
0x1800935c1  mov     [rbp+4F0h+value], si
0x1800935c5  mov     [rbp+4F0h+var_510], 4
0x1800935cc  cmp     [rbp+4F0h+value], si
0x1800935d0  jz      loc_1800936D4
0x1800935d6  mov     rdi, [rsp+5F0h+ppbc]
0x1800935db  test    rdi, rdi
0x1800935de  jz      loc_180093C06
0x1800935e4  mov     [rsp+5F0h+ppv], rsi
0x1800935e9  mov     [rsp+5F0h+var_5A8], rsi
0x1800935ee  mov     rax, [rdi]
0x1800935f1  lea     r8, [rsp+5F0h+var_5A8]
0x1800935f6  lea     rdx, aShbindctxprope; "SHBindCtxPropertyBag"
0x1800935fd  mov     rcx, rdi
0x180093600  mov     rax, [rax+50h]
0x180093604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093609  test    eax, eax
0x18009360b  js      short loc_180093640
0x18009360d  mov     rcx, [rsp+5F0h+var_5A8]
0x180093612  mov     rax, [rcx]
0x180093615  lea     r8, [rsp+5F0h+ppv]
0x18009361a  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x180093621  mov     rax, [rax]
0x180093624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093629  mov     ebx, eax
0x18009362b  mov     rcx, [rsp+5F0h+var_5A8]
0x180093630  mov     rdx, [rcx]
0x180093633  mov     rax, [rdx+10h]
0x180093637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009363c  test    ebx, ebx
0x18009363e  jns     short loc_1800936A3
0x180093640  lea     rdx, [rsp+5F0h+ppv]; ppv
0x180093645  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18009364c  call    cs:__imp_PSCreateMemoryPropertyStore
0x180093652  mov     ebx, eax
0x180093654  test    eax, eax
0x180093656  js      short loc_1800936CC
0x180093658  movups  xmm0, xmmword ptr cs:aShbindctxprope; "SHBindCtxPropertyBag"
0x18009365f  movups  [rbp+4F0h+var_70], xmm0
0x180093666  movups  xmm1, xmmword ptr cs:aShbindctxprope+10h; "xPropertyBag"
0x18009366d  movups  xmmword ptr [rbp+4F0h+var_60], xmm1
0x180093674  movups  xmm0, xmmword ptr cs:aShbindctxprope+1Ah; "ertyBag"
0x18009367b  movups  xmmword ptr [rbp+4F0h+var_60+0Ah], xmm0
0x180093682  mov     rax, [rdi]
0x180093685  mov     r8, [rsp+5F0h+ppv]
0x18009368a  lea     rdx, [rbp+4F0h+var_70]
0x180093691  mov     rcx, rdi
0x180093694  mov     rax, [rax+48h]
0x180093698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009369d  mov     ebx, eax
0x18009369f  test    eax, eax
0x1800936a1  js      short loc_1800936CC
0x1800936a3  lea     r8, [rbp+4F0h+value]; value
0x1800936a7  lea     rdx, aLocalizedresou_0; "LocalizedResourceName"
0x1800936ae  mov     rcx, [rsp+5F0h+ppv]; propBag
0x1800936b3  call    cs:__imp_PSPropertyBag_WriteStr
0x1800936b9  mov     ebx, eax
0x1800936bb  mov     rcx, [rsp+5F0h+ppv]
0x1800936c0  mov     rax, [rcx]
0x1800936c3  mov     rax, [rax+10h]
0x1800936c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800936cc  test    ebx, ebx
0x1800936ce  js      loc_1800938D0
0x1800936d4  mov     rcx, r12; struct _ITEMIDLIST_RELATIVE *
0x1800936d7  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x1800936dc  test    rax, rax
0x1800936df  jz      loc_1800938A8
0x1800936e5  mov     [rsp+5F0h+var_5A8], rsi
0x1800936ea  lea     rcx, [r14+1F0h]; struct _GUID *
0x1800936f1  mov     rax, [rcx]
0x1800936f4  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800936fb  jnz     short loc_180093708
0x1800936fd  mov     rax, [rcx+8]
0x180093701  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180093708  test    rax, rax
0x18009370b  jnz     loc_180093A6E
0x180093711  mov     rcx, [r14+1B8h]; pidl
0x180093718  test    rcx, rcx
0x18009371b  jz      loc_180093AF7
0x180093721  call    ILClone
0x180093726  mov     rsi, rax
0x180093729  xor     eax, eax
0x18009372b  test    rsi, rsi
0x18009372e  mov     edi, 8007000Eh
0x180093733  cmovz   eax, edi
0x180093736  test    eax, eax
0x180093738  jns     short loc_180093764
0x18009373a  xor     esi, esi
0x18009373c  mov     rcx, [r14+1B0h]; pidl
0x180093743  test    rcx, rcx
0x180093746  jz      loc_180093B36
0x18009374c  call    ILClone
0x180093751  mov     rsi, rax
0x180093754  xor     ebx, ebx
0x180093756  test    rax, rax
0x180093759  cmovz   ebx, edi
0x18009375c  test    ebx, ebx
0x18009375e  js      loc_1800938D0
0x180093764  mov     [rsp+5F0h+var_5A8], 0
  ... truncated ...
```
