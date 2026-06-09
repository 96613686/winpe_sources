# Dr::LocalSyncIAPerformer::UpdateStrokesDataInAnalyzer(void)

- ea: `0x1803a26a4`
- end: `0x1803a30cc`
- name: `?UpdateStrokesDataInAnalyzer@LocalSyncIAPerformer@Dr@@AEAAJXZ`
- size: `2600`
- prototype: `__int64 __fastcall(Dr::LocalSyncIAPerformer *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1803a4c50`

## callees

- `0x180030d70`
- `0x180065990`
- `0x1800659a0`
- `0x180071720`
- `0x180153038`
- `0x18033e9c8`
- `0x18033ecb0`
- `0x1803a17d4`
- `0x1803a26a4`
- `0x1803a30d0`
- `0x1803a32ac`
- `0x1803a3348`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803a28ad`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803a28ad`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1803a2cfa`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1803a2cfa`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803a29ec`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803a2c8e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803a29ec`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803a2c8e`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2956`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2989`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2bfe`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2c2e`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2d69`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2dd1`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2956`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2989`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2bfe`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2c2e`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2d69`
- `OLEAUT32!__imp_VariantInit` at `0x1803a2dd1`
- `OLEAUT32!__imp_VariantClear` at `0x1803a29f7`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2a0e`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2c9a`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2cac`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2e35`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2e58`
- `OLEAUT32!__imp_VariantClear` at `0x1803a29f7`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2a0e`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2c9a`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2cac`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2e35`
- `OLEAUT32!__imp_VariantClear` at `0x1803a2e58`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a29c4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a2a8f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a2c66`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a2e10`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a2eaa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a29c4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a2a8f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a2c66`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a2e10`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1803a2eaa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a29d9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a2c7b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a2e29`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a2fb3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a309f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a29d9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a2c7b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a2e29`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a2fb3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1803a309f`
- `ole32!CLSIDFromString` at `0x1803a2af1`
- `ole32!CLSIDFromString` at `0x1803a2f07`
- `ole32!CLSIDFromString` at `0x1803a2af1`
- `ole32!CLSIDFromString` at `0x1803a2f07`

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
0x1803a26a4  mov     [rsp-8+arg_0], rcx
0x1803a26a9  push    rbp
0x1803a26aa  push    rbx
0x1803a26ab  push    rsi
0x1803a26ac  push    rdi
0x1803a26ad  push    r12
0x1803a26af  push    r13
0x1803a26b1  push    r14
0x1803a26b3  push    r15
0x1803a26b5  lea     rbp, [rsp-18h]
0x1803a26ba  sub     rsp, 118h
0x1803a26c1  mov     r12, rcx
0x1803a26c4  xor     r13d, r13d
0x1803a26c7  mov     r15d, r13d
0x1803a26ca  mov     r14, [rcx+20h]
0x1803a26ce  cmp     dword ptr [r14+40h], 1
0x1803a26d3  jnz     loc_1803A2B5F
0x1803a26d9  lea     rdx, [r14+88h]
0x1803a26e0  lea     rcx, [rbp+50h+Block]
0x1803a26e4  call    ??0?$list@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@V?$allocator@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@@std@@@std@@QEAA@AEBV01@@Z; std::list<Dr::InkDocAnalyzer::InkInfoForAnalysis>::list<Dr::InkDocAnalyzer::InkInfoForAnalysis>(std::list<Dr::InkDocAnalyzer::InkInfoForAnalysis> const &)
0x1803a26e9  cmp     [rbp+50h+var_80], r13
0x1803a26ed  jz      loc_1803A2A47
0x1803a26f3  mov     rsi, [rbp+50h+Block]
0x1803a26f7  mov     rdi, [rsi]
0x1803a26fa  cmp     rdi, rsi
0x1803a26fd  jz      loc_1803A302C
0x1803a2703  mov     rcx, [rdi+10h]; struct Ofc::CProxyPtrImpl *
0x1803a2707  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1803a270c  mov     [rsp+150h+var_E8], rax
0x1803a2711  lea     rdx, [rdi+18h]
0x1803a2715  lea     rcx, [rbp+50h+var_70]
0x1803a2719  call    ??0?$TArray@M@Ofc@@QEAA@AEBV01@@Z; Ofc::TArray<float>::TArray<float>(Ofc::TArray<float> const &)
0x1803a271e  mov     rcx, [rsp+150h+var_E8]; this
0x1803a2723  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803a2728  mov     rcx, rax
0x1803a272b  mov     rax, [rax]
0x1803a272e  lea     rdx, [rsp+150h+var_E0]
0x1803a2733  mov     rax, [rax+48h]
0x1803a2737  call    cs:__guard_dispatch_icall_fptr
0x1803a273d  mov     [rsp+150h+var_100], r13
0x1803a2742  mov     rcx, [rsp+150h+var_E0]
0x1803a2747  mov     rax, [rcx]
0x1803a274a  lea     rdx, [rsp+150h+var_100]
0x1803a274f  mov     rax, [rax+38h]
0x1803a2753  call    cs:__guard_dispatch_icall_fptr
0x1803a2759  mov     ebx, eax
0x1803a275b  test    eax, eax
0x1803a275d  js      loc_1803A303A
0x1803a2763  mov     [rbp+50h+arg_10], r13d
0x1803a2767  mov     rcx, [rsp+150h+var_100]
0x1803a276c  mov     rax, [rcx]
0x1803a276f  lea     rdx, [rbp+50h+arg_10]
0x1803a2773  mov     rax, [rax+38h]
0x1803a2777  call    cs:__guard_dispatch_icall_fptr
0x1803a277d  mov     r15d, eax
0x1803a2780  test    eax, eax
0x1803a2782  js      loc_1803A2FE8
0x1803a2788  mov     rcx, [rsp+150h+var_E8]; this
0x1803a278d  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803a2792  mov     rdx, rax
0x1803a2795  mov     rcx, [rax]
0x1803a2798  mov     rax, [rcx+8]
0x1803a279c  mov     rcx, rdx
0x1803a279f  call    cs:__guard_dispatch_icall_fptr
0x1803a27a5  mov     ebx, eax
0x1803a27a7  mov     [rbp+50h+var_B8], eax
0x1803a27aa  mov     rcx, [rsp+150h+var_E8]; this
0x1803a27af  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803a27b4  mov     rcx, rax; this
0x1803a27b7  call    ?GetInkOffsetWrtHostBoundsInHm@InkDocAnalyzerHelpers@Dr@@YA?AUtagPOINT@@AEAUIInkDrawing@Art@@@Z; Dr::InkDocAnalyzerHelpers::GetInkOffsetWrtHostBoundsInHm(Art::IInkDrawing &)
0x1803a27bc  mov     r14, rax
0x1803a27bf  mov     [rbp+50h+var_B0], rax
0x1803a27c3  mov     edx, r13d
0x1803a27c6  mov     [rbp+50h+arg_8], edx
0x1803a27c9  cmp     edx, [rbp+50h+arg_10]
0x1803a27cc  jge     loc_1803A28DF
0x1803a27d2  mov     rax, [r12+20h]
0x1803a27d7  mov     rcx, [rax+28h]
0x1803a27db  mov     rax, [rcx+10h]
0x1803a27df  neg     rax
0x1803a27e2  sbb     r13d, r13d
0x1803a27e5  and     r13d, 3E8h
0x1803a27ec  imul    r13d, ebx
0x1803a27f0  add     r13d, edx
0x1803a27f3  mov     rcx, [rbp+50h+var_70]
0x1803a27f7  mov     eax, dword ptr [rbp+50h+var_70+8]
0x1803a27fa  lea     rdx, [rcx+rax*4]
0x1803a27fe  cmp     rcx, rdx
0x1803a2801  jz      loc_1803A28C9
0x1803a2807  cmp     [rcx], r13d
0x1803a280a  jnz     loc_1803A28D6
0x1803a2810  xor     r15d, r15d
0x1803a2813  mov     [rsp+150h+var_110], r15
0x1803a2818  mov     rcx, [rsp+150h+var_100]
0x1803a281d  mov     rax, [rcx]
0x1803a2820  lea     r8, [rsp+150h+var_110]
0x1803a2825  mov     edx, [rbp+50h+arg_8]
0x1803a2828  mov     rax, [rax+60h]
0x1803a282c  call    cs:__guard_dispatch_icall_fptr
0x1803a2832  mov     ebx, eax
0x1803a2834  test    eax, eax
0x1803a2836  jns     loc_1803A292A
0x1803a283c  mov     rcx, [rsp+150h+var_110]
0x1803a2841  test    rcx, rcx
0x1803a2844  jz      short loc_1803A2854
0x1803a2846  mov     rax, [rcx]
0x1803a2849  mov     rax, [rax+10h]
0x1803a284d  call    cs:__guard_dispatch_icall_fptr
0x1803a2853  nop
0x1803a2854  mov     rcx, [rsp+150h+var_100]
0x1803a2859  test    rcx, rcx
0x1803a285c  jz      short loc_1803A286C
0x1803a285e  mov     rax, [rcx]
0x1803a2861  mov     rax, [rax+10h]
0x1803a2865  call    cs:__guard_dispatch_icall_fptr
0x1803a286b  nop
0x1803a286c  mov     rcx, [rsp+150h+var_E0]
0x1803a2871  test    rcx, rcx
0x1803a2874  jz      short loc_1803A2884
0x1803a2876  mov     rax, [rcx]
0x1803a2879  mov     rax, [rax+10h]
0x1803a287d  call    cs:__guard_dispatch_icall_fptr
0x1803a2883  nop
0x1803a2884  mov     rcx, [rbp+50h+var_70]; void *
0x1803a2888  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1803a288d  lea     rcx, [rsp+150h+var_E8]; struct Ofc::CProxyPtrImpl **
0x1803a2892  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1803a2897  nop
0x1803a2898  nop     dword ptr [rax+rax+00000000h]
0x1803a28a0  mov     rdx, [rbp+50h+Block]
0x1803a28a4  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@PEAX@std@@@std@@@?$_List_node@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UInkInfoForAnalysis@InkDocAnalyzer@Dr@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *>::_Free_non_head<std::allocator<std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *>>>(std::allocator<std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *>> &,std::_List_node<Dr::InkDocAnalyzer::InkInfoForAnalysis,void *> *)
0x1803a28a9  mov     rcx, [rbp+50h+Block]; Block
0x1803a28ad  call    cs:__imp_free
0x1803a28b3  mov     eax, ebx
0x1803a28b5  add     rsp, 118h
0x1803a28bc  pop     r15
0x1803a28be  pop     r14
0x1803a28c0  pop     r13
0x1803a28c2  pop     r12
0x1803a28c4  pop     rdi
0x1803a28c5  pop     rsi
0x1803a28c6  pop     rbx
0x1803a28c7  pop     rbp
0x1803a28c8  retn
0x1803a28c9  xor     r13d, r13d
0x1803a28cc  mov     edx, [rbp+50h+arg_8]
0x1803a28cf  inc     edx
0x1803a28d1  jmp     loc_1803A27C6
0x1803a28d6  add     rcx, 4
0x1803a28da  jmp     loc_1803A27FE
0x1803a28df  mov     rcx, [rsp+150h+var_100]
0x1803a28e4  test    rcx, rcx
0x1803a28e7  jz      short loc_1803A28F7
0x1803a28e9  mov     rax, [rcx]
0x1803a28ec  mov     rax, [rax+10h]
0x1803a28f0  call    cs:__guard_dispatch_icall_fptr
0x1803a28f6  nop
0x1803a28f7  mov     rcx, [rsp+150h+var_E0]
0x1803a28fc  test    rcx, rcx
0x1803a28ff  jz      short loc_1803A290F
0x1803a2901  mov     rax, [rcx]
0x1803a2904  mov     rax, [rax+10h]
0x1803a2908  call    cs:__guard_dispatch_icall_fptr
0x1803a290e  nop
0x1803a290f  mov     rcx, [rbp+50h+var_70]; void *
0x1803a2913  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1803a2918  lea     rcx, [rsp+150h+var_E8]; struct Ofc::CProxyPtrImpl **
0x1803a291d  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1803a2922  mov     rdi, [rdi]
0x1803a2925  jmp     loc_1803A26FA
0x1803a292a  mov     r12, [rsp+150h+var_110]
0x1803a292f  mov     [rbp+50h+var_C0], r13d
0x1803a2933  mov     r13, [rbp+50h+arg_0]
0x1803a2937  mov     r13, [r13+10h]
0x1803a293b  mov     [rbp+50h+var_A8], r13
0x1803a293f  test    r12, r12
0x1803a2942  jz      loc_1803A2FC6
0x1803a2948  test    r13, r13
0x1803a294b  jz      loc_1803A2FC6
0x1803a2951  lea     rcx, [rsp+150h+pvarg]; pvarg
0x1803a2956  call    cs:__imp_VariantInit
0x1803a295c  mov     rax, [r12]
0x1803a2960  lea     r9, [rsp+150h+pvarg]
0x1803a2965  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1803a2969  mov     r8d, ebx
0x1803a296c  xor     edx, edx
0x1803a296e  mov     rcx, r12
0x1803a2971  mov     rax, [rax+0F0h]
0x1803a2978  call    cs:__guard_dispatch_icall_fptr
0x1803a297e  mov     r15d, eax
0x1803a2981  test    eax, eax
0x1803a2983  js      short loc_1803A29FD
0x1803a2985  lea     rcx, [rbp+50h+var_A0]; pvarg
0x1803a2989  call    cs:__imp_VariantInit
0x1803a298f  mov     rax, [r12]
0x1803a2993  lea     rdx, [rbp+50h+var_A0]
0x1803a2997  mov     rcx, r12
0x1803a299a  mov     rax, [rax+90h]
0x1803a29a1  call    cs:__guard_dispatch_icall_fptr
0x1803a29a7  mov     r15d, eax
0x1803a29aa  xor     eax, eax
0x1803a29ac  test    r15d, r15d
0x1803a29af  js      short loc_1803A29F3
0x1803a29b1  mov     [rsp+150h+ppvData], rax
0x1803a29b6  mov     [rsp+150h+var_108.lpVtbl], rax
0x1803a29bb  lea     rdx, [rsp+150h+ppvData]; ppvData
0x1803a29c0  mov     rcx, qword ptr [rbp+50h+pvarg+8]; psa
0x1803a29c4  call    cs:__imp_SafeArrayAccessData
0x1803a29ca  mov     r15d, eax
0x1803a29cd  test    eax, eax
0x1803a29cf  jns     loc_1803A2A86
0x1803a29d5  mov     rcx, qword ptr [rbp+50h+var_A0+8]; psa
0x1803a29d9  call    cs:__imp_SafeArrayUnaccessData
0x1803a29df  test    eax, eax
0x1803a29e1  jns     loc_1803A2FAF
0x1803a29e7  mov     ecx, 3973346Ch
0x1803a29ec  call    cs:__imp_MsoShipAssertTagProc
0x1803a29f2  nop
0x1803a29f3  lea     rcx, [rbp+50h+var_A0]; pvarg
0x1803a29f7  call    cs:__imp_VariantClear
0x1803a29fd  xor     ebx, ebx
0x1803a29ff  mov     [rsp+150h+var_108.lpVtbl], rbx
0x1803a2a04  test    r15d, r15d
0x1803a2a07  jns     short loc_1803A2A51
0x1803a2a09  lea     rcx, [rsp+150h+pvarg]; pvarg
0x1803a2a0e  call    cs:__imp_VariantClear
0x1803a2a14  mov     r12, [rsp+150h+var_110]
0x1803a2a19  xor     r13d, r13d
0x1803a2a1c  test    r15d, r15d
0x1803a2a1f  js      loc_1803A2FD1
0x1803a2a25  test    r12, r12
0x1803a2a28  jz      short loc_1803A2A3B
0x1803a2a2a  mov     rax, [r12]
0x1803a2a2e  mov     rcx, r12
0x1803a2a31  mov     rax, [rax+10h]
0x1803a2a35  call    cs:__guard_dispatch_icall_fptr
0x1803a2a3b  mov     ebx, [rbp+50h+var_B8]
0x1803a2a3e  mov     r12, [rbp+50h+arg_0]
0x1803a2a42  jmp     loc_1803A28CC
0x1803a2a47  mov     ebx, 80004005h
0x1803a2a4c  jmp     loc_1803A28A0
0x1803a2a51  lea     rdx, [rsp+150h+var_108]; struct IInkStrokeDisp *
0x1803a2a56  mov     rcx, r12; this
0x1803a2a59  call    ?GetStrokeTimestamp@Dr@@YAJPEAUIInkStrokeDisp@@AEA_K@Z; Dr::GetStrokeTimestamp(IInkStrokeDisp *,unsigned __int64 &)
0x1803a2a5e  mov     r15d, eax
0x1803a2a61  test    eax, eax
0x1803a2a63  js      short loc_1803A2A09
0x1803a2a65  mov     rax, [r13+0]
0x1803a2a69  mov     r8, [rsp+150h+var_108.lpVtbl]
0x1803a2a6e  mov     edx, [rbp+50h+var_C0]
0x1803a2a71  mov     rcx, r13
0x1803a2a74  mov     rax, [rax+1D0h]
0x1803a2a7b  call    cs:__guard_dispatch_icall_fptr
0x1803a2a81  mov     r15d, eax
0x1803a2a84  jmp     short loc_1803A2A09
0x1803a2a86  lea     rdx, [rsp+150h+var_108]; ppvData
0x1803a2a8b  mov     rcx, qword ptr [rbp+50h+var_A0+8]; psa
0x1803a2a8f  call    cs:__imp_SafeArrayAccessData
0x1803a2a95  mov     r15d, eax
0x1803a2a98  test    eax, eax
0x1803a2a9a  js      loc_1803A29D5
0x1803a2aa0  mov     rax, qword ptr [rbp+50h+var_A0+8]
0x1803a2aa4  mov     r15d, [rax+18h]
0x1803a2aa8  mov     rax, qword ptr [rbp+50h+pvarg+8]
0x1803a2aac  mov     eax, [rax+18h]
0x1803a2aaf  mov     [rsp+150h+var_F0], eax
0x1803a2ab3  mov     eax, 10h
0x1803a2ab8  mul     r15
0x1803a2abb  cmovb   rax, rbx
0x1803a2abf  mov     rcx, rax; this
0x1803a2ac2  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1803a2ac7  mov     rbx, rax
0x1803a2aca  mov     [rbp+50h+var_50], rax
0x1803a2ace  xor     ecx, ecx
0x1803a2ad0  mov     r13d, ecx
0x1803a2ad3  cmp     r13d, r15d
0x1803a2ad6  jnb     short loc_1803A2AFD
0x1803a2ad8  mov     r8d, r13d
0x1803a2adb  mov     edx, r13d
0x1803a2ade  shl     rdx, 4
0x1803a2ae2  add     rdx, rbx; pclsid
0x1803a2ae5  mov     rcx, [rsp+150h+var_108.lpVtbl]
0x1803a2aea  inc     r13d
0x1803a2aed  mov     rcx, [rcx+r8*8]; lpsz
0x1803a2af1  call    cs:__imp_CLSIDFromString
0x1803a2af7  xor     ecx, ecx
0x1803a2af9  test    eax, eax
0x1803a2afb  jns     short loc_1803A2AD3
0x1803a2afd  xor     edx, edx
0x1803a2aff  mov     eax, [rsp+150h+var_F0]
0x1803a2b03  div     r15d
0x1803a2b06  mov     [rbp+50h+arg_18], eax
0x1803a2b09  mov     edx, ecx
0x1803a2b0b  test    eax, eax
0x1803a2b0d  jnz     loc_1803A2F85
0x1803a2b13  mov     r13, [rbp+50h+var_A8]
0x1803a2b17  mov     rax, [r13+0]
0x1803a2b1b  mov     rcx, [rsp+150h+ppvData]
0x1803a2b20  mov     [rsp+150h+var_120], rcx
0x1803a2b25  lea     rcx, [rbp+50h+arg_18]
  ... truncated ...
```
