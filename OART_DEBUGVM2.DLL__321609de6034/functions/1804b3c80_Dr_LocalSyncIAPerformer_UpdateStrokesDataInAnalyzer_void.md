# Dr::LocalSyncIAPerformer::UpdateStrokesDataInAnalyzer(void)

- ea: `0x1804b3c80`
- end: `0x1804b46a4`
- name: `?UpdateStrokesDataInAnalyzer@LocalSyncIAPerformer@Dr@@AEAAJXZ`
- size: `2596`
- prototype: `__int64 __fastcall(Dr::LocalSyncIAPerformer *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1804b33f0`

## callees

- `0x18002a690`
- `0x18004d170`
- `0x180107b50`
- `0x180276a40`
- `0x180279050`
- `0x18028ecf0`
- `0x18048121c`
- `0x1804814f8`
- `0x1804b3c80`
- `0x1804b46a4`
- `0x1804b4880`
- `0x1804b4920`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b3e82`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b3e82`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1804b42cf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1804b42cf`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1804b3fc1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1804b4263`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1804b3fc1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1804b4263`
- `OLEAUT32!__imp_VariantInit` at `0x1804b3f2b`
- `OLEAUT32!__imp_VariantInit` at `0x1804b3f5e`
- `OLEAUT32!__imp_VariantInit` at `0x1804b41d3`
- `OLEAUT32!__imp_VariantInit` at `0x1804b4203`
- `OLEAUT32!__imp_VariantInit` at `0x1804b433e`
- `OLEAUT32!__imp_VariantInit` at `0x1804b43a6`
- `OLEAUT32!__imp_VariantInit` at `0x1804b3f2b`
- `OLEAUT32!__imp_VariantInit` at `0x1804b3f5e`
- `OLEAUT32!__imp_VariantInit` at `0x1804b41d3`
- `OLEAUT32!__imp_VariantInit` at `0x1804b4203`
- `OLEAUT32!__imp_VariantInit` at `0x1804b433e`
- `OLEAUT32!__imp_VariantInit` at `0x1804b43a6`
- `OLEAUT32!__imp_VariantClear` at `0x1804b3fcc`
- `OLEAUT32!__imp_VariantClear` at `0x1804b3fe3`
- `OLEAUT32!__imp_VariantClear` at `0x1804b426f`
- `OLEAUT32!__imp_VariantClear` at `0x1804b4281`
- `OLEAUT32!__imp_VariantClear` at `0x1804b440a`
- `OLEAUT32!__imp_VariantClear` at `0x1804b442d`
- `OLEAUT32!__imp_VariantClear` at `0x1804b3fcc`
- `OLEAUT32!__imp_VariantClear` at `0x1804b3fe3`
- `OLEAUT32!__imp_VariantClear` at `0x1804b426f`
- `OLEAUT32!__imp_VariantClear` at `0x1804b4281`
- `OLEAUT32!__imp_VariantClear` at `0x1804b440a`
- `OLEAUT32!__imp_VariantClear` at `0x1804b442d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b3f99`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b4064`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b423b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b43e5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b447f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b3f99`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b4064`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b423b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b43e5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1804b447f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b3fae`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b4250`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b43fe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b4588`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b4677`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b3fae`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b4250`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b43fe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b4588`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804b4677`
- `ole32!CLSIDFromString` at `0x1804b40c6`
- `ole32!CLSIDFromString` at `0x1804b44dc`
- `ole32!CLSIDFromString` at `0x1804b40c6`
- `ole32!CLSIDFromString` at `0x1804b44dc`

## pseudocode

```c
__int64 __fastcall Dr::LocalSyncIAPerformer::UpdateStrokesDataInAnalyzer(Dr::LocalSyncIAPerformer *this)
{
  Dr::LocalSyncIAPerformer *v1; // r12
  __int64 v2; // r13
  HRESULT StrokeTimestamp; // r15d
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 *i; // rdi
  void *Checked; // rax
  int v9; // ebx
  void *v10; // rax
  int v11; // ebx
  Dr::InkDocAnalyzerHelpers *v12; // rax
  struct Art::IInkDrawing *v13; // rdx
  struct tagPOINT InkOffsetWrtHostBoundsInHm; // r14
  signed int v15; // edx
  unsigned int v16; // r13d
  _DWORD *j; // rcx
  Dr *v19; // r12
  __int64 v20; // r13
  unsigned __int64 *v21; // r8
  unsigned int v22; // r8d
  unsigned __int64 v23; // r15
  unsigned __int128 v24; // rax
  char *v25; // rbx
  unsigned int v26; // r13d
  __int64 v27; // r8
  CLSID *v28; // rdx
  unsigned int v29; // edx
  __int64 v30; // rax
  signed int v31; // ebx
  __int64 v32; // rdi
  char *v33; // rdi
  __int64 v34; // r12
  HRESULT (__stdcall *QueryInterface)(IInkStrokeDisp *, const IID *const, void **); // r12
  Dr *v36; // rbx
  __int64 (__fastcall *v37)(Dr *, _QWORD, unsigned int *); // rsi
  _QWORD *v38; // rax
  __int64 v39; // rax
  unsigned int v40; // r8d
  unsigned __int64 v41; // r15
  unsigned __int128 v42; // rax
  char *v43; // rbx
  unsigned int v44; // esi
  __int64 v45; // r8
  CLSID *v46; // rdx
  LONG y; // r8d
  __int64 v48; // rcx
  Dr *v49; // [rsp+40h] [rbp-C0h] BYREF
  struct IInkStrokeDisp v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h] BYREF
  void *ppvData; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v53; // [rsp+60h] [rbp-A0h] BYREF
  Ofc::CProxyPtrImpl *v54; // [rsp+68h] [rbp-98h] BYREF
  char *v55; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v57; // [rsp+90h] [rbp-70h] BYREF
  int v58; // [rsp+98h] [rbp-68h]
  struct tagPOINT v59; // [rsp+A0h] [rbp-60h]
  __int64 v60; // [rsp+A8h] [rbp-58h]
  VARIANTARG v61; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG Block; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG v63; // [rsp+E0h] [rbp-20h] BYREF
  char *v64; // [rsp+100h] [rbp+0h]
  unsigned int v66; // [rsp+168h] [rbp+68h] BYREF
  signed int v67; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v68; // [rsp+178h] [rbp+78h] BYREF

  v1 = this;
  v2 = 0;
  StrokeTimestamp = 0;
  v4 = *((_QWORD *)this + 4);
  if ( *(_DWORD *)(v4 + 64) != 1 )
  {
    if ( *(_DWORD *)(v4 + 64) == 2 )
    {
      v30 = (__int64)(*(_QWORD *)(v4 + 176) - *(_QWORD *)(v4 + 168)) >> 3;
      if ( !(_DWORD)v30 )
        return 2147500037LL;
      v31 = 0;
      v30 = (int)v30;
      v59 = (struct tagPOINT)(int)v30;
      while ( 1 )
      {
        v68 = v31;
        if ( v2 >= v30 )
          break;
        v32 = *(_QWORD *)(v4 + 168);
        if ( v31 >= (unsigned __int64)((*(_QWORD *)(v4 + 176) - v32) >> 3) )
          _invoke_watson(0, 0, 0, 0, 0);
        v33 = *(char **)(v32 + 8 * v2);
        v64 = v33;
        if ( v33 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 8LL))(v33);
        v34 = *((_QWORD *)v1 + 2);
        v60 = v34;
        v67 = v31;
        if ( v33 && v34 )
        {
          VariantInit(&v61);
          StrokeTimestamp = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, VARIANTARG *))(*(_QWORD *)v33 + 240LL))(
                              v33,
                              0,
                              0xFFFFFFFFLL,
                              &v61);
          if ( StrokeTimestamp >= 0 )
          {
            VariantInit(&pvarg);
            StrokeTimestamp = (*(__int64 (__fastcall **)(char *, VARIANTARG *))(*(_QWORD *)v33 + 144LL))(v33, &pvarg);
            if ( StrokeTimestamp >= 0 )
            {
              v49 = 0;
              v50.lpVtbl = 0;
              StrokeTimestamp = SafeArrayAccessData(v61.parray, (void **)&v49);
              if ( StrokeTimestamp >= 0 )
              {
                StrokeTimestamp = SafeArrayAccessData(pvarg.parray, (void **)&v50.lpVtbl);
                if ( StrokeTimestamp >= 0 )
                {
                  v41 = *(unsigned int *)(pvarg.llVal + 24);
                  v66 = *(_DWORD *)(v61.llVal + 24);
                  v42 = v41 * (unsigned __int128)0x10uLL;
                  if ( !is_mul_ok(v41, 0x10u) )
                    *(_QWORD *)&v42 = -1;
                  v43 = (char *)Mso::Memory::Throw::AllocateEx(
                                  (Mso::Memory::Throw *)v42,
                                  *((unsigned __int64 *)&v42 + 1),
                                  v40);
                  v55 = v43;
                  v44 = 0;
                  do
                  {
                    if ( v44 >= (unsigned int)v41 )
                      break;
                    v45 = v44;
                    v46 = (CLSID *)&v43[16 * v44++];
                  }
                  while ( CLSIDFromString(*((LPCOLESTR *)&v50.lpVtbl->QueryInterface + v45), v46) >= 0 );
                  v53 = v66 / (unsigned int)v41;
                  StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, __int64, signed int *, _QWORD, char *, unsigned int *, Dr *))(*(_QWORD *)v34 + 216LL))(
                                      v34,
                                      1,
                                      &v67,
                                      (unsigned int)v41,
                                      v43,
                                      &v53,
                                      v49);
                  operator delete(v43);
                }
              }
              if ( SafeArrayUnaccessData(pvarg.parray) < 0 || SafeArrayUnaccessData(v61.parray) < 0 )
                MsoShipAssertTagProc(963851372);
            }
            VariantClear(&pvarg);
          }
          QueryInterface = 0;
          if ( StrokeTimestamp >= 0 )
          {
            v49 = 0;
            StrokeTimestamp = (*(__int64 (__fastcall **)(char *, Dr **))(*(_QWORD *)v33 + 96LL))(v33, &v49);
            if ( StrokeTimestamp >= 0 )
            {
              LOWORD(v66) = 0;
              v36 = v49;
              v37 = *(__int64 (__fastcall **)(Dr *, _QWORD, unsigned int *))(*(_QWORD *)v49 + 104LL);
              v38 = (_QWORD *)Ofc::TSingleton<Dr::CGuidTimeStampBstrOwner>::Instance();
              StrokeTimestamp = v37(v36, *v38, &v66);
              if ( StrokeTimestamp >= 0 )
              {
                if ( (_WORD)v66 )
                {
                  VariantInit(&Block);
                  memset(&pvarg, 0, sizeof(pvarg));
                  pvarg.llVal = *(_QWORD *)Ofc::TSingleton<Dr::CGuidTimeStampBstrOwner>::Instance();
                  pvarg.vt = 8;
                  ppvData = 0;
                  v39 = *(_QWORD *)v49;
                  v63 = pvarg;
                  StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, VARIANTARG *, void **))(v39 + 72))(
                                      v49,
                                      &v63,
                                      &ppvData);
                  if ( StrokeTimestamp >= 0 )
                  {
                    VariantInit(&pvarg);
                    StrokeTimestamp = (*(__int64 (__fastcall **)(void *, VARIANTARG *))(*(_QWORD *)ppvData + 64LL))(
                                        ppvData,
                                        &pvarg);
                    if ( StrokeTimestamp >= 0 && pvarg.vt == 8209 )
                    {
                      v50.lpVtbl = 0;
                      StrokeTimestamp = SafeArrayAccessData(pvarg.parray, (void **)&v50.lpVtbl);
                      if ( StrokeTimestamp >= 0 )
                      {
                        QueryInterface = v50.lpVtbl->QueryInterface;
                        SafeArrayUnaccessData(pvarg.parray);
                      }
                    }
                    VariantClear(&pvarg);
                  }
                  if ( ppvData )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvData + 16LL))(ppvData);
                  VariantClear(&Block);
                }
                else
                {
                  QueryInterface = 0;
                  StrokeTimestamp = 1;
                }
              }
            }
            if ( v49 )
              (*(void (__fastcall **)(Dr *))(*(_QWORD *)v49 + 16LL))(v49);
            if ( StrokeTimestamp >= 0 )
              StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, _QWORD, HRESULT (__stdcall *)(IInkStrokeDisp *, const IID *const, void **)))(*(_QWORD *)v60 + 464LL))(
                                  v60,
                                  (unsigned int)v67,
                                  QueryInterface);
          }
          VariantClear(&v61);
          v31 = v68;
        }
        else
        {
          StrokeTimestamp = -2147024809;
        }
        if ( StrokeTimestamp < 0 )
        {
          if ( v33 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 16LL))(v33);
          return (unsigned int)StrokeTimestamp;
        }
        if ( v33 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 16LL))(v33);
        ++v31;
        ++v2;
        v30 = (__int64)v59;
        v1 = this;
      }
    }
    return (unsigned int)StrokeTimestamp;
  }
  std::list<Dr::InkDocAnalyzer::InkInfoForAnalysis>::list<Dr::InkDocAnalyzer::InkInfoForAnalysis>(&Block, v4 + 136);
  if ( Block.llVal )
  {
    v6 = *(__int64 **)&Block.vt;
    for ( i = **(__int64 ***)&Block.vt; ; i = (__int64 *)*i )
    {
      if ( i == v6 )
        goto LABEL_115;
      v54 = Ofc::CProxyPtrImpl::CheckedStrongAddRef((struct Ofc::CProxyPtrImpl *)i[2]);
      Ofc::TArray<float>::TArray<float>(&v63, i + 3);
      Checked = Ofc::CProxyPtrImpl::GetChecked(v54);
      (*(void (__fastcall **)(void *, char **))(*(_QWORD *)Checked + 72LL))(Checked, &v55);
      v51 = 0;
      v9 = (*(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v55 + 56LL))(v55, &v51);
      if ( v9 < 0 )
      {
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        if ( v55 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v55 + 16LL))(v55);
        Ofc::TArray<Art::FontSizeFrequency>::~TArray<Art::FontSizeFrequency>((void *const *)&v63);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
        std::list<Dr::InkDocAnalyzer::InkInfoForAnalysis>::~list<Dr::InkDocAnalyzer::InkInfoForAnalysis>(&Block);
        return (unsigned int)v9;
      }
      v67 = 0;
      StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, signed int *))(*(_QWORD *)v51 + 56LL))(v51, &v67);
      if ( StrokeTimestamp < 0 )
        goto LABEL_110;
      v10 = Ofc::CProxyPtrImpl::GetChecked(v54);
      v11 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v10 + 8LL))(v10);
      v58 = v11;
      v12 = (Dr::InkDocAnalyzerHelpers *)Ofc::CProxyPtrImpl::GetChecked(v54);
      InkOffsetWrtHostBoundsInHm = Dr::InkDocAnalyzerHelpers::GetInkOffsetWrtHostBoundsInHm(v12, v13);
      v59 = InkOffsetWrtHostBoundsInHm;
      v15 = 0;
LABEL_8:
      v66 = v15;
      if ( v15 < v67 )
        break;
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v55 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v55 + 16LL))(v55);
      operator delete(*(void **)&v63.vt);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
    }
    v16 = v15 + v11 * (*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v1 + 4) + 40LL) + 16LL) != 0 ? 0x3E8 : 0);
    for ( j = *(_DWORD **)&v63.vt; ; ++j )
    {
      if ( j == (_DWORD *)(*(_QWORD *)&v63.vt + 4LL * v63.cyVal.Lo) )
        goto LABEL_22;
      if ( *j == v16 )
        break;
    }
    v49 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, Dr **))(*(_QWORD *)v51 + 96LL))(v51, v66, &v49);
    if ( v9 >= 0 )
    {
      v19 = v49;
      v57 = v16;
      v20 = *((_QWORD *)this + 2);
      v60 = v20;
      if ( v49 && v20 )
      {
        VariantInit(&pvarg);
        StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, _QWORD, __int64, VARIANTARG *))(*(_QWORD *)v19 + 240LL))(
                            v19,
                            0,
                            0xFFFFFFFFLL,
                            &pvarg);
        if ( StrokeTimestamp >= 0 )
        {
          VariantInit(&v61);
          StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, VARIANTARG *))(*(_QWORD *)v19 + 144LL))(v19, &v61);
          if ( StrokeTimestamp >= 0 )
          {
            ppvData = 0;
            v50.lpVtbl = 0;
            StrokeTimestamp = SafeArrayAccessData(pvarg.parray, &ppvData);
            if ( StrokeTimestamp >= 0 )
            {
              StrokeTimestamp = SafeArrayAccessData(v61.parray, (void **)&v50.lpVtbl);
              if ( StrokeTimestamp >= 0 )
              {
                v23 = *(unsigned int *)(v61.llVal + 24);
                v53 = *(_DWORD *)(pvarg.llVal + 24);
                v24 = v23 * (unsigned __int128)0x10uLL;
                if ( !is_mul_ok(v23, 0x10u) )
                  *(_QWORD *)&v24 = -1;
                v25 = (char *)Mso::Memory::Throw::AllocateEx(
                                (Mso::Memory::Throw *)v24,
                                *((unsigned __int64 *)&v24 + 1),
                                v22);
                v64 = v25;
                v26 = 0;
                do
                {
                  if ( v26 >= (unsigned int)v23 )
                    break;
                  v27 = v26;
                  v28 = (CLSID *)&v25[16 * v26++];
                }
                while ( CLSIDFromString(*((LPCOLESTR *)&v50.lpVtbl->QueryInterface + v27), v28) >= 0 );
                v68 = v53 / (unsigned int)v23;
                v29 = 0;
                if ( v53 / (unsigned int)v23 )
                {
                  y = v59.y;
                  do
                  {
                    v48 = (unsigned int)v23 * v29;
                    *((_DWORD *)ppvData + v48) += InkOffsetWrtHostBoundsInHm.x;
                    *((_DWORD *)ppvData + (unsigned int)(v48 + 1)) += y;
                    ++v29;
                  }
                  while ( v29 < v68 );
                }
                v20 = v60;
                StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, _QWORD, char *, unsigned int *, void *))(*(_QWORD *)v60 + 216LL))(
                                    v60,
                                    1,
                                    &v57,
                                    (unsigned int)v23,
                                    v25,
                                    &v68,
                                    ppvData);
                operator delete(v25);
              }
            }
            if ( SafeArrayUnaccessData(v61.parray) < 0 || SafeArrayUnaccessData(pvarg.parray) < 0 )
              MsoShipAssertTagProc(963851372);
          }
          VariantClear(&v61);
        }
        v50.lpVtbl = 0;
        if ( StrokeTimestamp >= 0 )
        {
          StrokeTimestamp = Dr::GetStrokeTimestamp(v19, &v50, v21);
          if ( StrokeTimestamp >= 0 )
            StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IInkStrokeDispVtbl *))(*(_QWORD *)v20 + 464LL))(
                                v20,
                                v57,
                                v50.lpVtbl);
        }
        VariantClear(&pvarg);
        v19 = v49;
      }
      else
      {
        StrokeTimestamp = -2147024809;
      }
      if ( StrokeTimestamp >= 0 )
      {
        if ( v19 )
          (*(void (__fastcall **)(Dr *))(*(_QWORD *)v19 + 16LL))(v19);
        v11 = v58;
        v1 = this;
LABEL_22:
        v15 = v66 + 1;
        goto LABEL_8;
      }
      if ( v19 )
        (*(void (__fastcall **)(Dr *))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_110:
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v55 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v55 + 16LL))(v55);
      Ofc::TArray<Art::FontSizeFrequency>::~TArray<Art::FontSizeFrequency>((void *const *)&v63);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
LABEL_115:
      std::list<Dr::InkDocAnalyzer::InkInfoForAnalysis>::~list<Dr::InkDocAnalyzer::InkInfoForAnalysis>(&Block);
      return (unsigned int)StrokeTimestamp;
    }
    if ( v49 )
      (*(void (__fastcall **)(Dr *))(*(_QWORD *)v49 + 16LL))(v49);
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    if ( v55 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v55 + 16LL))(v55);
    operator delete(*(void **)&v63.vt);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
  }
  else
  {
    v9 = -2147467259;
  }
  std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *>::_Free_non_head<std::allocator<std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *>>>(
    v5,
    *(_QWORD *)&Block.vt);
  free(*(void **)&Block.vt);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1804b3c80  mov     [rsp-8+arg_0], rcx
0x1804b3c85  push    rbp
0x1804b3c86  push    rbx
0x1804b3c87  push    rsi
0x1804b3c88  push    rdi
0x1804b3c89  push    r12
0x1804b3c8b  push    r13
0x1804b3c8d  push    r14
0x1804b3c8f  push    r15
0x1804b3c91  lea     rbp, [rsp-18h]
0x1804b3c96  sub     rsp, 118h
0x1804b3c9d  mov     r12, rcx
0x1804b3ca0  xor     r13d, r13d
0x1804b3ca3  mov     r15d, r13d
0x1804b3ca6  mov     r14, [rcx+20h]
0x1804b3caa  cmp     dword ptr [r14+40h], 1
0x1804b3caf  jnz     loc_1804B4134
0x1804b3cb5  lea     rdx, [r14+88h]
0x1804b3cbc  lea     rcx, [rbp+50h+Block]
0x1804b3cc0  call    ??0?$list@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@V?$allocator@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@@std@@@std@@QEAA@AEBV01@@Z; std::list<Dr::InkDocAnalyzer::InkInfoForAnalysis>::list<Dr::InkDocAnalyzer::InkInfoForAnalysis>(std::list<Dr::InkDocAnalyzer::InkInfoForAnalysis> const &)
0x1804b3cc5  cmp     [rbp+50h+var_80], r13
0x1804b3cc9  jz      loc_1804B401C
0x1804b3ccf  nop
0x1804b3cd0  mov     rsi, [rbp+50h+Block]
0x1804b3cd4  mov     rdi, [rsi]
0x1804b3cd7  cmp     rdi, rsi
0x1804b3cda  jz      loc_1804B4601
0x1804b3ce0  mov     rcx, [rdi+10h]; struct Ofc::CProxyPtrImpl *
0x1804b3ce4  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1804b3ce9  mov     [rsp+150h+var_E8], rax
0x1804b3cee  lea     rdx, [rdi+18h]
0x1804b3cf2  lea     rcx, [rbp+50h+var_70]
0x1804b3cf6  call    ??0?$TArray@M@Ofc@@QEAA@AEBV01@@Z; Ofc::TArray<float>::TArray<float>(Ofc::TArray<float> const &)
0x1804b3cfb  mov     rcx, [rsp+150h+var_E8]; this
0x1804b3d00  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1804b3d05  mov     rcx, rax
0x1804b3d08  mov     rax, [rax]
0x1804b3d0b  lea     rdx, [rsp+150h+var_E0]
0x1804b3d10  mov     rax, [rax+48h]
0x1804b3d14  call    cs:__guard_dispatch_icall_fptr
0x1804b3d1a  mov     [rsp+150h+var_100], r13
0x1804b3d1f  mov     rcx, [rsp+150h+var_E0]
0x1804b3d24  mov     rax, [rcx]
0x1804b3d27  lea     rdx, [rsp+150h+var_100]
0x1804b3d2c  mov     rax, [rax+38h]
0x1804b3d30  call    cs:__guard_dispatch_icall_fptr
0x1804b3d36  mov     ebx, eax
0x1804b3d38  test    eax, eax
0x1804b3d3a  js      loc_1804B460F
0x1804b3d40  mov     [rbp+50h+arg_10], r13d
0x1804b3d44  mov     rcx, [rsp+150h+var_100]
0x1804b3d49  mov     rax, [rcx]
0x1804b3d4c  lea     rdx, [rbp+50h+arg_10]
0x1804b3d50  mov     rax, [rax+38h]
0x1804b3d54  call    cs:__guard_dispatch_icall_fptr
0x1804b3d5a  mov     r15d, eax
0x1804b3d5d  test    eax, eax
0x1804b3d5f  js      loc_1804B45BD
0x1804b3d65  mov     rcx, [rsp+150h+var_E8]; this
0x1804b3d6a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1804b3d6f  mov     rdx, rax
0x1804b3d72  mov     rcx, [rax]
0x1804b3d75  mov     rax, [rcx+8]
0x1804b3d79  mov     rcx, rdx
0x1804b3d7c  call    cs:__guard_dispatch_icall_fptr
0x1804b3d82  mov     ebx, eax
0x1804b3d84  mov     [rbp+50h+var_B8], eax
0x1804b3d87  mov     rcx, [rsp+150h+var_E8]; this
0x1804b3d8c  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1804b3d91  mov     rcx, rax; this
0x1804b3d94  call    ?GetInkOffsetWrtHostBoundsInHm@InkDocAnalyzerHelpers@Dr@@YA?AUtagPOINT@@AEAUIInkDrawing@Art@@@Z; Dr::InkDocAnalyzerHelpers::GetInkOffsetWrtHostBoundsInHm(Art::IInkDrawing &)
0x1804b3d99  mov     r14, rax
0x1804b3d9c  mov     [rbp+50h+var_B0], rax
0x1804b3da0  mov     edx, r13d
0x1804b3da3  mov     [rbp+50h+arg_8], edx
0x1804b3da6  cmp     edx, [rbp+50h+arg_10]
0x1804b3da9  jge     loc_1804B3EB4
0x1804b3daf  mov     rax, [r12+20h]
0x1804b3db4  mov     rcx, [rax+28h]
0x1804b3db8  mov     rax, [rcx+10h]
0x1804b3dbc  neg     rax
0x1804b3dbf  sbb     r13d, r13d
0x1804b3dc2  and     r13d, 3E8h
0x1804b3dc9  imul    r13d, ebx
0x1804b3dcd  add     r13d, edx
0x1804b3dd0  mov     rcx, [rbp+50h+var_70]
0x1804b3dd4  mov     eax, dword ptr [rbp+50h+var_70+8]
0x1804b3dd7  lea     rdx, [rcx+rax*4]
0x1804b3ddb  cmp     rcx, rdx
0x1804b3dde  jz      loc_1804B3E9E
0x1804b3de4  cmp     [rcx], r13d
0x1804b3de7  jnz     loc_1804B3EAB
0x1804b3ded  xor     r15d, r15d
0x1804b3df0  mov     [rsp+150h+var_110], r15
0x1804b3df5  mov     rcx, [rsp+150h+var_100]
0x1804b3dfa  mov     rax, [rcx]
0x1804b3dfd  lea     r8, [rsp+150h+var_110]
0x1804b3e02  mov     edx, [rbp+50h+arg_8]
0x1804b3e05  mov     rax, [rax+60h]
0x1804b3e09  call    cs:__guard_dispatch_icall_fptr
0x1804b3e0f  mov     ebx, eax
0x1804b3e11  test    eax, eax
0x1804b3e13  jns     loc_1804B3EFF
0x1804b3e19  mov     rcx, [rsp+150h+var_110]
0x1804b3e1e  test    rcx, rcx
0x1804b3e21  jz      short loc_1804B3E31
0x1804b3e23  mov     rax, [rcx]
0x1804b3e26  mov     rax, [rax+10h]
0x1804b3e2a  call    cs:__guard_dispatch_icall_fptr
0x1804b3e30  nop
0x1804b3e31  mov     rcx, [rsp+150h+var_100]
0x1804b3e36  test    rcx, rcx
0x1804b3e39  jz      short loc_1804B3E49
0x1804b3e3b  mov     rax, [rcx]
0x1804b3e3e  mov     rax, [rax+10h]
0x1804b3e42  call    cs:__guard_dispatch_icall_fptr
0x1804b3e48  nop
0x1804b3e49  mov     rcx, [rsp+150h+var_E0]
0x1804b3e4e  test    rcx, rcx
0x1804b3e51  jz      short loc_1804B3E61
0x1804b3e53  mov     rax, [rcx]
0x1804b3e56  mov     rax, [rax+10h]
0x1804b3e5a  call    cs:__guard_dispatch_icall_fptr
0x1804b3e60  nop
0x1804b3e61  mov     rcx, [rbp+50h+var_70]; void *
0x1804b3e65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1804b3e6a  lea     rcx, [rsp+150h+var_E8]; struct Ofc::CProxyPtrImpl **
0x1804b3e6f  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1804b3e74  nop
0x1804b3e75  mov     rdx, [rbp+50h+Block]
0x1804b3e79  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@PEAX@std@@@std@@@?$_List_node@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *>::_Free_non_head<std::allocator<std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *>>>(std::allocator<std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *>> &,std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *> *)
0x1804b3e7e  mov     rcx, [rbp+50h+Block]; Block
0x1804b3e82  call    cs:__imp_free
0x1804b3e88  mov     eax, ebx
0x1804b3e8a  add     rsp, 118h
0x1804b3e91  pop     r15
0x1804b3e93  pop     r14
0x1804b3e95  pop     r13
0x1804b3e97  pop     r12
0x1804b3e99  pop     rdi
0x1804b3e9a  pop     rsi
0x1804b3e9b  pop     rbx
0x1804b3e9c  pop     rbp
0x1804b3e9d  retn
0x1804b3e9e  xor     r13d, r13d
0x1804b3ea1  mov     edx, [rbp+50h+arg_8]
0x1804b3ea4  inc     edx
0x1804b3ea6  jmp     loc_1804B3DA3
0x1804b3eab  add     rcx, 4
0x1804b3eaf  jmp     loc_1804B3DDB
0x1804b3eb4  mov     rcx, [rsp+150h+var_100]
0x1804b3eb9  test    rcx, rcx
0x1804b3ebc  jz      short loc_1804B3ECC
0x1804b3ebe  mov     rax, [rcx]
0x1804b3ec1  mov     rax, [rax+10h]
0x1804b3ec5  call    cs:__guard_dispatch_icall_fptr
0x1804b3ecb  nop
0x1804b3ecc  mov     rcx, [rsp+150h+var_E0]
0x1804b3ed1  test    rcx, rcx
0x1804b3ed4  jz      short loc_1804B3EE4
0x1804b3ed6  mov     rax, [rcx]
0x1804b3ed9  mov     rax, [rax+10h]
0x1804b3edd  call    cs:__guard_dispatch_icall_fptr
0x1804b3ee3  nop
0x1804b3ee4  mov     rcx, [rbp+50h+var_70]; void *
0x1804b3ee8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1804b3eed  lea     rcx, [rsp+150h+var_E8]; struct Ofc::CProxyPtrImpl **
0x1804b3ef2  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1804b3ef7  mov     rdi, [rdi]
0x1804b3efa  jmp     loc_1804B3CD7
0x1804b3eff  mov     r12, [rsp+150h+var_110]
0x1804b3f04  mov     [rbp+50h+var_C0], r13d
0x1804b3f08  mov     r13, [rbp+50h+arg_0]
0x1804b3f0c  mov     r13, [r13+10h]
0x1804b3f10  mov     [rbp+50h+var_A8], r13
0x1804b3f14  test    r12, r12
0x1804b3f17  jz      loc_1804B459B
0x1804b3f1d  test    r13, r13
0x1804b3f20  jz      loc_1804B459B
0x1804b3f26  lea     rcx, [rsp+150h+pvarg]; pvarg
0x1804b3f2b  call    cs:__imp_VariantInit
0x1804b3f31  mov     rax, [r12]
0x1804b3f35  lea     r9, [rsp+150h+pvarg]
0x1804b3f3a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1804b3f3e  mov     r8d, ebx
0x1804b3f41  xor     edx, edx
0x1804b3f43  mov     rcx, r12
0x1804b3f46  mov     rax, [rax+0F0h]
0x1804b3f4d  call    cs:__guard_dispatch_icall_fptr
0x1804b3f53  mov     r15d, eax
0x1804b3f56  test    eax, eax
0x1804b3f58  js      short loc_1804B3FD2
0x1804b3f5a  lea     rcx, [rbp+50h+var_A0]; pvarg
0x1804b3f5e  call    cs:__imp_VariantInit
0x1804b3f64  mov     rax, [r12]
0x1804b3f68  lea     rdx, [rbp+50h+var_A0]
0x1804b3f6c  mov     rcx, r12
0x1804b3f6f  mov     rax, [rax+90h]
0x1804b3f76  call    cs:__guard_dispatch_icall_fptr
0x1804b3f7c  mov     r15d, eax
0x1804b3f7f  xor     eax, eax
0x1804b3f81  test    r15d, r15d
0x1804b3f84  js      short loc_1804B3FC8
0x1804b3f86  mov     [rsp+150h+ppvData], rax
0x1804b3f8b  mov     [rsp+150h+var_108.lpVtbl], rax
0x1804b3f90  lea     rdx, [rsp+150h+ppvData]; ppvData
0x1804b3f95  mov     rcx, qword ptr [rbp+50h+pvarg+8]; psa
0x1804b3f99  call    cs:__imp_SafeArrayAccessData
0x1804b3f9f  mov     r15d, eax
0x1804b3fa2  test    eax, eax
0x1804b3fa4  jns     loc_1804B405B
0x1804b3faa  mov     rcx, qword ptr [rbp+50h+var_A0+8]; psa
0x1804b3fae  call    cs:__imp_SafeArrayUnaccessData
0x1804b3fb4  test    eax, eax
0x1804b3fb6  jns     loc_1804B4584
0x1804b3fbc  mov     ecx, 3973346Ch
0x1804b3fc1  call    cs:__imp_MsoShipAssertTagProc
0x1804b3fc7  nop
0x1804b3fc8  lea     rcx, [rbp+50h+var_A0]; pvarg
0x1804b3fcc  call    cs:__imp_VariantClear
0x1804b3fd2  xor     ebx, ebx
0x1804b3fd4  mov     [rsp+150h+var_108.lpVtbl], rbx
0x1804b3fd9  test    r15d, r15d
0x1804b3fdc  jns     short loc_1804B4026
0x1804b3fde  lea     rcx, [rsp+150h+pvarg]; pvarg
0x1804b3fe3  call    cs:__imp_VariantClear
0x1804b3fe9  mov     r12, [rsp+150h+var_110]
0x1804b3fee  xor     r13d, r13d
0x1804b3ff1  test    r15d, r15d
0x1804b3ff4  js      loc_1804B45A6
0x1804b3ffa  test    r12, r12
0x1804b3ffd  jz      short loc_1804B4010
0x1804b3fff  mov     rax, [r12]
0x1804b4003  mov     rcx, r12
0x1804b4006  mov     rax, [rax+10h]
0x1804b400a  call    cs:__guard_dispatch_icall_fptr
0x1804b4010  mov     ebx, [rbp+50h+var_B8]
0x1804b4013  mov     r12, [rbp+50h+arg_0]
0x1804b4017  jmp     loc_1804B3EA1
0x1804b401c  mov     ebx, 80004005h
0x1804b4021  jmp     loc_1804B3E75
0x1804b4026  lea     rdx, [rsp+150h+var_108]; struct IInkStrokeDisp *
0x1804b402b  mov     rcx, r12; this
0x1804b402e  call    ?GetStrokeTimestamp@Dr@@YAJPEAUIInkStrokeDisp@@AEA_K@Z; Dr::GetStrokeTimestamp(IInkStrokeDisp *,unsigned __int64 &)
0x1804b4033  mov     r15d, eax
0x1804b4036  test    eax, eax
0x1804b4038  js      short loc_1804B3FDE
0x1804b403a  mov     rax, [r13+0]
0x1804b403e  mov     r8, [rsp+150h+var_108.lpVtbl]
0x1804b4043  mov     edx, [rbp+50h+var_C0]
0x1804b4046  mov     rcx, r13
0x1804b4049  mov     rax, [rax+1D0h]
0x1804b4050  call    cs:__guard_dispatch_icall_fptr
0x1804b4056  mov     r15d, eax
0x1804b4059  jmp     short loc_1804B3FDE
0x1804b405b  lea     rdx, [rsp+150h+var_108]; ppvData
0x1804b4060  mov     rcx, qword ptr [rbp+50h+var_A0+8]; psa
0x1804b4064  call    cs:__imp_SafeArrayAccessData
0x1804b406a  mov     r15d, eax
0x1804b406d  test    eax, eax
0x1804b406f  js      loc_1804B3FAA
0x1804b4075  mov     rax, qword ptr [rbp+50h+var_A0+8]
0x1804b4079  mov     r15d, [rax+18h]
0x1804b407d  mov     rax, qword ptr [rbp+50h+pvarg+8]
0x1804b4081  mov     eax, [rax+18h]
0x1804b4084  mov     [rsp+150h+var_F0], eax
0x1804b4088  mov     eax, 10h
0x1804b408d  mul     r15
0x1804b4090  cmovb   rax, rbx
0x1804b4094  mov     rcx, rax; this
0x1804b4097  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804b409c  mov     rbx, rax
0x1804b409f  mov     [rbp+50h+var_50], rax
0x1804b40a3  xor     ecx, ecx
0x1804b40a5  mov     r13d, ecx
0x1804b40a8  cmp     r13d, r15d
0x1804b40ab  jnb     short loc_1804B40D2
0x1804b40ad  mov     r8d, r13d
0x1804b40b0  mov     edx, r13d
0x1804b40b3  shl     rdx, 4
0x1804b40b7  add     rdx, rbx; pclsid
0x1804b40ba  mov     rcx, [rsp+150h+var_108.lpVtbl]
0x1804b40bf  inc     r13d
0x1804b40c2  mov     rcx, [rcx+r8*8]; lpsz
0x1804b40c6  call    cs:__imp_CLSIDFromString
0x1804b40cc  xor     ecx, ecx
0x1804b40ce  test    eax, eax
0x1804b40d0  jns     short loc_1804B40A8
0x1804b40d2  xor     edx, edx
0x1804b40d4  mov     eax, [rsp+150h+var_F0]
0x1804b40d8  div     r15d
0x1804b40db  mov     [rbp+50h+arg_18], eax
0x1804b40de  mov     edx, ecx
0x1804b40e0  test    eax, eax
0x1804b40e2  jnz     loc_1804B455A
0x1804b40e8  mov     r13, [rbp+50h+var_A8]
0x1804b40ec  mov     rax, [r13+0]
0x1804b40f0  mov     rcx, [rsp+150h+ppvData]
0x1804b40f5  mov     [rsp+150h+var_120], rcx
0x1804b40fa  lea     rcx, [rbp+50h+arg_18]
  ... truncated ...
```
