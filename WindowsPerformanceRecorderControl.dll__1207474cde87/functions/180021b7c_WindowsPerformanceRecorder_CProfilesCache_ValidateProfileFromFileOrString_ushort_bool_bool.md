# WindowsPerformanceRecorder::CProfilesCache::ValidateProfileFromFileOrString(ushort *,bool,bool)

- ea: `0x180021b7c`
- end: `0x18002255e`
- name: `?ValidateProfileFromFileOrString@CProfilesCache@WindowsPerformanceRecorder@@QEAAJPEAG_N1@Z`
- size: `2530`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CProfilesCache *this, OLECHAR *psz, char, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800218a8`
- `0x180042638`

## callees

- `0x180008330`
- `0x180009a84`
- `0x180016480`
- `0x180021b7c`
- `0x180022564`
- `0x1800226d0`
- `0x1800234f0`
- `0x180040a04`
- `0x180044210`
- `0x1800490b0`
- `0x18004ab0c`
- `0x18004b39c`
- `0x180070b3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021cb0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021cb0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180021d44`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180021d44`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180021c93`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180021c93`
- `OLEAUT32!__imp_SysAllocString` at `0x1800220ce`
- `OLEAUT32!__imp_SysAllocString` at `0x18002233c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800220ce`
- `OLEAUT32!__imp_SysAllocString` at `0x18002233c`
- `OLEAUT32!__imp_SysFreeString` at `0x180021f6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180022017`
- `OLEAUT32!__imp_SysFreeString` at `0x180022249`
- `OLEAUT32!__imp_SysFreeString` at `0x180022494`
- `OLEAUT32!__imp_SysFreeString` at `0x180022515`
- `OLEAUT32!__imp_SysFreeString` at `0x180021f6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180022017`
- `OLEAUT32!__imp_SysFreeString` at `0x180022249`
- `OLEAUT32!__imp_SysFreeString` at `0x180022494`
- `OLEAUT32!__imp_SysFreeString` at `0x180022515`
- `OLEAUT32!__imp_VariantClear` at `0x180021f56`
- `OLEAUT32!__imp_VariantClear` at `0x180021ff6`
- `OLEAUT32!__imp_VariantClear` at `0x1800220b9`
- `OLEAUT32!__imp_VariantClear` at `0x180022143`
- `OLEAUT32!__imp_VariantClear` at `0x180022228`
- `OLEAUT32!__imp_VariantClear` at `0x1800222f9`
- `OLEAUT32!__imp_VariantClear` at `0x18002232d`
- `OLEAUT32!__imp_VariantClear` at `0x1800223b2`
- `OLEAUT32!__imp_VariantClear` at `0x180022473`
- `OLEAUT32!__imp_VariantClear` at `0x180022500`
- `OLEAUT32!__imp_VariantClear` at `0x180021f56`
- `OLEAUT32!__imp_VariantClear` at `0x180021ff6`
- `OLEAUT32!__imp_VariantClear` at `0x1800220b9`
- `OLEAUT32!__imp_VariantClear` at `0x180022143`
- `OLEAUT32!__imp_VariantClear` at `0x180022228`
- `OLEAUT32!__imp_VariantClear` at `0x1800222f9`
- `OLEAUT32!__imp_VariantClear` at `0x18002232d`
- `OLEAUT32!__imp_VariantClear` at `0x1800223b2`
- `OLEAUT32!__imp_VariantClear` at `0x180022473`
- `OLEAUT32!__imp_VariantClear` at `0x180022500`

## string_xrefs

- `0x180021c8c`: `msxml6.dll`
- `0x180021ca6`: `DllGetClassObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall WindowsPerformanceRecorder::CProfilesCache::ValidateProfileFromFileOrString(
        WindowsPerformanceRecorder::CProfilesCache *this,
        OLECHAR *psz,
        char a3,
        bool a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  struct IXMLDOMParseError *v10; // rbx
  struct IXMLDOMParseErrorVtbl *lpVtbl; // rdi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int XMLFromResource; // ebx
  int Error; // eax
  const unsigned __int16 *v16; // r9
  OLECHAR *v17; // rcx
  OLECHAR *v18; // rdi
  LONGLONG v19; // rbx
  _QWORD *v20; // rbx
  __int64 v21; // rsi
  _QWORD *v22; // rbx
  __int64 (__fastcall *v23)(_QWORD *, VARIANTARG *); // rsi
  _QWORD *v24; // rbx
  __int64 v25; // rsi
  _WORD v26[2]; // [rsp+30h] [rbp-E8h] BYREF
  int v27; // [rsp+34h] [rbp-E4h] BYREF
  LONGLONG v28; // [rsp+38h] [rbp-E0h] BYREF
  struct IXMLDOMParseError *v29; // [rsp+40h] [rbp-D8h] BYREF
  _QWORD *v30; // [rsp+48h] [rbp-D0h] BYREF
  _QWORD v31[2]; // [rsp+50h] [rbp-C8h] BYREF
  VARIANTARG v32; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+80h] [rbp-98h] BYREF
  __int64 v34; // [rsp+88h] [rbp-90h] BYREF
  BSTR bstrString[2]; // [rsp+90h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-78h] BYREF
  HMODULE phModule; // [rsp+B8h] [rbp-60h] BYREF
  VARIANTARG v38; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-38h]
  ATL::CAtlException *v40; // [rsp+E8h] [rbp-30h] BYREF

  v39 = -2;
  if ( WindowsPerformanceRecorder::CProfilesCache::sc_fUseMinimalBuiltInProfiles )
    return 2147942450LL;
  if ( a3 )
  {
    WindowsPerformanceRecorder::Impl::CFileKey::CFileKey((WindowsPerformanceRecorder::Impl::CFileKey *)bstrString);
    try
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64 *)&v29,
        (char *)psz);
      WindowsPerformanceRecorder::Impl::CFileKey::CFileKey((WindowsPerformanceRecorder::Impl::CFileKey *)&v32);
      ATL::CSimpleStringT<unsigned short,0>::operator=(bstrString, &v32);
      bstrString[1] = v32.bstrVal;
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v32);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v29);
      v7 = WindowsPerformanceRecorder::Impl::CFileKey::SetFileTime((WindowsPerformanceRecorder::Impl::CFileKey *)bstrString);
    }
    catch ( ATL::CAtlException *v40 )
    {
      return *(unsigned int *)v40;
    }
    v8 = v7;
    if ( v7 < 0 )
    {
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)bstrString);
      return v8;
    }
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)bstrString);
  }
  v29 = 0;
  result = WindowsPerformanceRecorder::CWPRControl::GetInstance((struct WindowsPerformanceRecorder::CWPRControl **)&v29);
  if ( (int)result < 0 )
    return result;
  v10 = v29;
  lpVtbl = v29[9].lpVtbl;
  if ( !lpVtbl )
  {
    if ( v29[8].lpVtbl
      || (Library = LoadLibraryExW(L"msxml6.dll", 0, 0x800u),
          (v10[8].lpVtbl = (struct IXMLDOMParseErrorVtbl *)Library) != 0)
      && (ProcAddress = GetProcAddress(Library, "DllGetClassObject"),
          (v10[9].lpVtbl = (struct IXMLDOMParseErrorVtbl *)ProcAddress) != 0) )
    {
      lpVtbl = v10[9].lpVtbl;
      goto LABEL_13;
    }
    return 2147942450LL;
  }
LABEL_13:
  v33 = 0;
  v34 = 0;
  XMLFromResource = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))lpVtbl)(
                      &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
                      &IID_IClassFactory,
                      &v33);
  if ( XMLFromResource < 0 )
  {
LABEL_98:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
    return (unsigned int)XMLFromResource;
  }
  Error = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))lpVtbl)(
            &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
            &IID_IClassFactory,
            &v34);
  if ( Error < 0 )
  {
LABEL_15:
    XMLFromResource = Error;
    goto LABEL_98;
  }
  phModule = 0;
  if ( !GetModuleHandleExW(
          6u,
          (LPCWSTR)WindowsPerformanceRecorder::CProfilesCache::GetWPRControlBuiltInProfileFileName,
          &phModule) )
  {
    Error = ATL::AtlHresultFromLastError();
    goto LABEL_15;
  }
  bstrString[0] = 0;
  XMLFromResource = ((int (__stdcall *)(WindowsPerformanceRecorder::Impl *, unsigned __int16 **, HINSTANCE, const unsigned __int16 *))WindowsPerformanceRecorder::Impl::LoadXMLFromResource)(
                      (WindowsPerformanceRecorder::Impl *)bstrString,
                      (unsigned __int16 **)phModule,
                      (HINSTANCE)&stru_1800987A8,
                      v16);
  if ( XMLFromResource < 0 )
    goto LABEL_19;
  v28 = 0;
  XMLFromResource = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, LONGLONG *))(*(_QWORD *)v33 + 24LL))(
                      v33,
                      0,
                      &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                      &v28);
  if ( XMLFromResource < 0
    || (XMLFromResource = (*(__int64 (__fastcall **)(LONGLONG, _QWORD))(*(_QWORD *)v28 + 504LL))(v28, 0),
        XMLFromResource < 0)
    || (XMLFromResource = (*(__int64 (__fastcall **)(LONGLONG, __int64))(*(_QWORD *)v28 + 544LL))(v28, 0xFFFFFFFFLL),
        XMLFromResource < 0) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
LABEL_19:
    v17 = bstrString[0];
LABEL_97:
    SysFreeString(v17);
    goto LABEL_98;
  }
  v18 = bstrString[0];
  v19 = v28;
  v26[0] = 0;
  (*(void (__fastcall **)(LONGLONG, BSTR, _WORD *))(*(_QWORD *)v28 + 520LL))(v28, bstrString[0], v26);
  if ( !v26[0] )
  {
    v29 = 0;
    if ( (*(unsigned int (__fastcall **)(LONGLONG, struct IXMLDOMParseError **))(*(_QWORD *)v19 + 480LL))(v19, &v29)
      || (v27 = 0,
          WindowsPerformanceRecorder::CProfilesCache::LogProfileValidationError(this, v29, &v27, 0),
          XMLFromResource = v27,
          v27 >= 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      XMLFromResource = -984086783;
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    }
    goto LABEL_96;
  }
  pvarg.vt = 9;
  pvarg.llVal = v28;
  if ( v28 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v28 + 8LL))(v28);
  v31[0] = 0;
  XMLFromResource = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD *))(*(_QWORD *)v34 + 24LL))(
                      v34,
                      0,
                      &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
                      v31);
  if ( XMLFromResource < 0
    || (XMLFromResource = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v31[0] + 120LL))(v31[0], 0xFFFFFFFFLL),
        XMLFromResource < 0) )
  {
LABEL_95:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v31);
    VariantClear(&pvarg);
LABEL_96:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    v17 = v18;
    goto LABEL_97;
  }
  v32 = pvarg;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)v31[0] + 56LL))(v31[0], 0, &v32) < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v31);
    VariantClear(&pvarg);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    SysFreeString(v18);
    XMLFromResource = -984086784;
    goto LABEL_98;
  }
  v30 = 0;
  XMLFromResource = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD **))(*(_QWORD *)v33 + 24LL))(
                      v33,
                      0,
                      &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                      &v30);
  if ( XMLFromResource < 0 )
  {
    if ( v30 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v30 + 16LL))(v30, *v30);
    if ( v31[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 16LL))(v31[0]);
    VariantClear(&pvarg);
    if ( v28 )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v28 + 16LL))(v28);
    SysFreeString(v18);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( !v33 )
      return (unsigned int)XMLFromResource;
    goto LABEL_45;
  }
  XMLFromResource = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v30 + 504LL))(v30, 0);
  if ( XMLFromResource < 0
    || (XMLFromResource = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v30 + 544LL))(v30, 0), XMLFromResource < 0) )
  {
LABEL_94:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    goto LABEL_95;
  }
  v20 = v30;
  v26[0] = 0;
  v21 = *v30;
  if ( a3 )
  {
    v32.vt = 0;
    VariantClear(&v32);
    v32.vt = 8;
    v32.llVal = (LONGLONG)SysAllocString(psz);
    if ( !v32.llVal && psz )
    {
      v32.vt = 10;
      v32.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v38 = v32;
    (*(void (__fastcall **)(_QWORD *, VARIANTARG *, _WORD *))(v21 + 464))(v20, &v38, v26);
    VariantClear(&v32);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *, OLECHAR *, _WORD *))(v21 + 520))(v30, psz, v26);
  }
  if ( !v26[0] )
  {
    v29 = 0;
    if ( !(*(unsigned int (__fastcall **)(_QWORD *, struct IXMLDOMParseError **))(*v20 + 480LL))(v20, &v29) )
    {
      v27 = 0;
      WindowsPerformanceRecorder::CProfilesCache::LogProfileValidationError(this, v29, &v27, a4);
      XMLFromResource = v27;
      if ( v27 < 0 )
      {
LABEL_57:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
        goto LABEL_94;
      }
    }
LABEL_93:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    XMLFromResource = -984086783;
    goto LABEL_94;
  }
  XMLFromResource = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v30 + 544LL))(v30, 0xFFFFFFFFLL);
  if ( XMLFromResource < 0 )
  {
    if ( v30 )
      (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
    if ( v31[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 16LL))(v31[0]);
    VariantClear(&pvarg);
    if ( v28 )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v28 + 16LL))(v28);
    SysFreeString(v18);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( !v33 )
      return (unsigned int)XMLFromResource;
LABEL_45:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return (unsigned int)XMLFromResource;
  }
  v22 = v30;
  v23 = *(__int64 (__fastcall **)(_QWORD *, VARIANTARG *))(*v30 + 624LL);
  v32.vt = 9;
  v32.llVal = v31[0];
  if ( v31[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 8LL))(v31[0]);
  v38 = v32;
  XMLFromResource = v23(v22, &v38);
  VariantClear(&v32);
  if ( XMLFromResource < 0 )
    goto LABEL_94;
  v24 = v30;
  v26[0] = 0;
  v25 = *v30;
  if ( a3 )
  {
    v32.vt = 0;
    VariantClear(&v32);
    v32.vt = 8;
    v32.llVal = (LONGLONG)SysAllocString(psz);
    if ( !v32.llVal && psz )
    {
      v32.vt = 10;
      v32.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v38 = v32;
    (*(void (__fastcall **)(_QWORD *, VARIANTARG *, _WORD *))(v25 + 464))(v24, &v38, v26);
    VariantClear(&v32);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *, OLECHAR *, _WORD *))(v25 + 520))(v30, psz, v26);
  }
  if ( !v26[0] )
  {
    v29 = 0;
    if ( !(*(unsigned int (__fastcall **)(_QWORD *, struct IXMLDOMParseError **))(*v24 + 480LL))(v24, &v29) )
    {
      v27 = 0;
      WindowsPerformanceRecorder::CProfilesCache::LogProfileValidationError(this, v29, &v27, a4);
      XMLFromResource = v27;
      if ( v27 < 0 )
        goto LABEL_57;
    }
    goto LABEL_93;
  }
  if ( v30 )
    (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
  if ( v31[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 16LL))(v31[0]);
  VariantClear(&pvarg);
  if ( v28 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v28 + 16LL))(v28);
  SysFreeString(v18);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return 0;
}

```

## disassembly

```asm
0x180021b7c  mov     rax, rsp
0x180021b7f  mov     [rax+20h], r9b
0x180021b83  push    rdi
0x180021b84  push    r12
0x180021b86  push    r13
0x180021b88  push    r14
0x180021b8a  push    r15
0x180021b8c  sub     rsp, 0F0h
0x180021b93  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180021b9b  mov     [rax+8], rbx
0x180021b9f  mov     [rax+10h], rsi
0x180021ba3  mov     r12b, r8b
0x180021ba6  mov     r14, rdx
0x180021ba9  mov     r13, rcx
0x180021bac  xor     r15d, r15d
0x180021baf  cmp     cs:?sc_fUseMinimalBuiltInProfiles@CProfilesCache@WindowsPerformanceRecorder@@0_NA, r15b; bool WindowsPerformanceRecorder::CProfilesCache::sc_fUseMinimalBuiltInProfiles
0x180021bb6  jnz     loc_18002253B
0x180021bbc  test    r8b, r8b
0x180021bbf  jz      loc_180021C59
0x180021bc5  lea     rcx, [rax-88h]; this
0x180021bcc  call    ??0CFileKey@Impl@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Impl::CFileKey::CFileKey(void)
0x180021bd1  nop
0x180021bd2  mov     rdx, r14
0x180021bd5  lea     rcx, [rsp+118h+var_D8]
0x180021bda  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180021bdf  nop
0x180021be0  mov     rdx, rax
0x180021be3  lea     rcx, [rsp+118h+var_B8]; this
0x180021be8  call    ??0CFileKey@Impl@WindowsPerformanceRecorder@@QEAA@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WindowsPerformanceRecorder::Impl::CFileKey::CFileKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180021bed  nop
0x180021bee  lea     rdx, [rsp+118h+var_B8]
0x180021bf3  lea     rcx, [rsp+118h+bstrString]
0x180021bfb  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180021c00  mov     rax, qword ptr [rsp+118h+var_B8+8]
0x180021c05  mov     [rsp+118h+var_80], rax
0x180021c0d  lea     rcx, [rsp+118h+var_B8]; this
0x180021c12  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180021c17  nop
0x180021c18  lea     rcx, [rsp+118h+var_D8]; this
0x180021c1d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180021c22  lea     rcx, [rsp+118h+bstrString]; this
0x180021c2a  call    ?SetFileTime@CFileKey@Impl@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::Impl::CFileKey::SetFileTime(void)
0x180021c2f  mov     ebx, eax
0x180021c31  lea     rcx, [rsp+118h+bstrString]; this
0x180021c39  test    eax, eax
0x180021c3b  jns     short loc_180021C49
0x180021c3d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180021c42  mov     eax, ebx
0x180021c44  jmp     loc_180022540
0x180021c49  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180021c4e  jmp     short loc_180021C59
0x180021c50  mov     eax, [rsp+118h+var_E4]
0x180021c54  jmp     loc_180022540
0x180021c59  mov     [rsp+118h+var_D8], r15
0x180021c5e  lea     rcx, [rsp+118h+var_D8]; struct WindowsPerformanceRecorder::CWPRControl **
0x180021c63  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x180021c68  test    eax, eax
0x180021c6a  js      loc_180022540
0x180021c70  mov     rbx, [rsp+118h+var_D8]
0x180021c75  mov     rdi, [rbx+48h]
0x180021c79  test    rdi, rdi
0x180021c7c  jnz     short loc_180021CC7
0x180021c7e  cmp     [rbx+40h], r15
0x180021c82  jnz     short loc_180021CC3
0x180021c84  xor     edx, edx; hFile
0x180021c86  mov     r8d, 800h; dwFlags
0x180021c8c  lea     rcx, LibFileName; "msxml6.dll"
0x180021c93  call    cs:__imp_LoadLibraryExW
0x180021c99  mov     [rbx+40h], rax
0x180021c9d  test    rax, rax
0x180021ca0  jz      loc_18002253B
0x180021ca6  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180021cad  mov     rcx, rax; hModule
0x180021cb0  call    cs:__imp_GetProcAddress
0x180021cb6  mov     [rbx+48h], rax
0x180021cba  test    rax, rax
0x180021cbd  jz      loc_18002253B
0x180021cc3  mov     rdi, [rbx+48h]
0x180021cc7  mov     [rsp+118h+var_98], r15
0x180021ccf  mov     [rsp+118h+var_90], r15
0x180021cd7  lea     r8, [rsp+118h+var_98]
0x180021cdf  lea     rdx, IID_IClassFactory
0x180021ce6  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5
0x180021ced  mov     rax, rdi
0x180021cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cf5  mov     ebx, eax
0x180021cf7  test    eax, eax
0x180021cf9  js      loc_18002251C
0x180021cff  lea     r8, [rsp+118h+var_90]
0x180021d07  lea     rdx, IID_IClassFactory
0x180021d0e  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5
0x180021d15  mov     rax, rdi
0x180021d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d1d  test    eax, eax
0x180021d1f  jns     short loc_180021D28
0x180021d21  mov     ebx, eax
0x180021d23  jmp     loc_18002251C
0x180021d28  mov     [rsp+118h+phModule], r15
0x180021d30  lea     r8, [rsp+118h+phModule]; phModule
0x180021d38  lea     rdx, ?GetWPRControlBuiltInProfileFileName@CProfilesCache@WindowsPerformanceRecorder@@SAPEBGXZ; lpModuleName
0x180021d3f  mov     ecx, 6; dwFlags
0x180021d44  call    cs:__imp_GetModuleHandleExW
0x180021d4a  test    eax, eax
0x180021d4c  jnz     short loc_180021D55
0x180021d4e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180021d53  jmp     short loc_180021D21
0x180021d55  mov     [rsp+118h+bstrString], r15
0x180021d5d  lea     r8, stru_1800987A8; HINSTANCE
0x180021d64  mov     rdx, [rsp+118h+phModule]; unsigned __int16 **
0x180021d6c  lea     rcx, [rsp+118h+bstrString]; this
0x180021d74  call    ?LoadXMLFromResource@Impl@WindowsPerformanceRecorder@@YAJPEAPEAGPEAUHINSTANCE__@@PEBG@Z; WindowsPerformanceRecorder::Impl::LoadXMLFromResource(ushort * *,HINSTANCE__ *,ushort const *)
0x180021d79  mov     ebx, eax
0x180021d7b  test    eax, eax
0x180021d7d  jns     short loc_180021D8C
0x180021d7f  mov     rcx, [rsp+118h+bstrString]
0x180021d87  jmp     loc_180022515
0x180021d8c  mov     [rsp+118h+var_E0], r15
0x180021d91  mov     rcx, [rsp+118h+var_98]
0x180021d99  mov     rax, [rcx]
0x180021d9c  lea     r9, [rsp+118h+var_E0]
0x180021da1  lea     r8, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x180021da8  xor     edx, edx
0x180021daa  mov     rax, [rax+18h]
0x180021dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021db3  mov     ebx, eax
0x180021db5  test    eax, eax
0x180021db7  jns     short loc_180021DC5
0x180021db9  lea     rcx, [rsp+118h+var_E0]
0x180021dbe  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021dc3  jmp     short loc_180021D7F
0x180021dc5  mov     rcx, [rsp+118h+var_E0]
0x180021dca  mov     rax, [rcx]
0x180021dcd  xor     edx, edx
0x180021dcf  mov     rax, [rax+1F8h]
0x180021dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ddb  mov     ebx, eax
0x180021ddd  test    eax, eax
0x180021ddf  js      short loc_180021DB9
0x180021de1  mov     rcx, [rsp+118h+var_E0]
0x180021de6  mov     rax, [rcx]
0x180021de9  or      esi, 0FFFFFFFFh
0x180021dec  mov     edx, esi
0x180021dee  mov     rax, [rax+220h]
0x180021df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dfa  mov     ebx, eax
0x180021dfc  test    eax, eax
0x180021dfe  js      short loc_180021DB9
0x180021e00  mov     rdi, [rsp+118h+bstrString]
0x180021e08  mov     rbx, [rsp+118h+var_E0]
0x180021e0d  mov     [rsp+118h+var_E8], r15w
0x180021e13  mov     rax, [rbx]
0x180021e16  lea     r8, [rsp+118h+var_E8]
0x180021e1b  mov     rdx, rdi
0x180021e1e  mov     rcx, rbx
0x180021e21  mov     rax, [rax+208h]
0x180021e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e2d  cmp     [rsp+118h+var_E8], r15w
0x180021e33  jnz     short loc_180021E91
0x180021e35  mov     [rsp+118h+var_D8], r15
0x180021e3a  mov     rax, [rbx]
0x180021e3d  lea     rdx, [rsp+118h+var_D8]
0x180021e42  mov     rcx, rbx
0x180021e45  mov     rax, [rax+1E0h]
0x180021e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e51  test    eax, eax
0x180021e53  jnz     loc_180021F7B
0x180021e59  mov     [rsp+118h+var_E4], r15d
0x180021e5e  xor     r9d, r9d; bool
0x180021e61  lea     r8, [rsp+118h+var_E4]; int *
0x180021e66  mov     rdx, [rsp+118h+var_D8]; struct IXMLDOMParseError *
0x180021e6b  mov     rcx, r13; this
0x180021e6e  call    ?LogProfileValidationError@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEAUIXMLDOMParseError@@AEAJ_N@Z; WindowsPerformanceRecorder::CProfilesCache::LogProfileValidationError(IXMLDOMParseError *,long &,bool)
0x180021e73  mov     ebx, [rsp+118h+var_E4]
0x180021e77  test    ebx, ebx
0x180021e79  jns     loc_180021F7B
0x180021e7f  lea     rcx, [rsp+118h+var_D8]
0x180021e84  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021e89  test    ebx, ebx
0x180021e8b  js      loc_180022507
0x180021e91  mov     rcx, [rsp+118h+var_E0]
0x180021e96  mov     eax, 9
0x180021e9b  mov     word ptr [rsp+118h+pvarg], ax
0x180021ea3  mov     qword ptr [rsp+118h+pvarg+8], rcx
0x180021eab  test    rcx, rcx
0x180021eae  jz      short loc_180021EBD
0x180021eb0  mov     rax, [rcx]
0x180021eb3  mov     rax, [rax+8]
0x180021eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ebc  nop
0x180021ebd  mov     [rsp+118h+var_C8], r15
0x180021ec2  mov     rcx, [rsp+118h+var_90]
0x180021eca  mov     rax, [rcx]
0x180021ecd  lea     r9, [rsp+118h+var_C8]
0x180021ed2  lea     r8, _GUID_88d96a07_f192_11d4_a65f_0040963251e5
0x180021ed9  xor     edx, edx
0x180021edb  mov     rax, [rax+18h]
0x180021edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ee4  mov     ebx, eax
0x180021ee6  test    eax, eax
0x180021ee8  js      loc_1800224ED
0x180021eee  mov     rcx, [rsp+118h+var_C8]
0x180021ef3  mov     rax, [rcx]
0x180021ef6  mov     edx, esi
0x180021ef8  mov     rax, [rax+78h]
0x180021efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f01  mov     ebx, eax
0x180021f03  test    eax, eax
0x180021f05  js      loc_1800224ED
0x180021f0b  mov     rcx, [rsp+118h+var_C8]
0x180021f10  movups  xmm0, xmmword ptr [rsp+118h+pvarg]
0x180021f18  movaps  xmmword ptr [rsp+118h+var_B8], xmm0
0x180021f1d  movsd   xmm1, qword ptr [rsp+118h+pvarg+10h]
0x180021f26  movsd   qword ptr [rsp+118h+var_B8+10h], xmm1
0x180021f2c  mov     rax, [rcx]
0x180021f2f  lea     r8, [rsp+118h+var_B8]
0x180021f34  xor     edx, edx
0x180021f36  mov     rax, [rax+38h]
0x180021f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f3f  test    eax, eax
0x180021f41  jns     short loc_180021F8F
0x180021f43  lea     rcx, [rsp+118h+var_C8]
0x180021f48  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021f4d  nop
0x180021f4e  lea     rcx, [rsp+118h+pvarg]; pvarg
0x180021f56  call    cs:__imp_VariantClear
0x180021f5c  nop
0x180021f5d  lea     rcx, [rsp+118h+var_E0]
0x180021f62  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021f67  nop
0x180021f68  mov     rcx, rdi; bstrString
0x180021f6b  call    cs:__imp_SysFreeString
0x180021f71  mov     ebx, 0C5580700h
0x180021f76  jmp     loc_18002251C
0x180021f7b  lea     rcx, [rsp+118h+var_D8]
0x180021f80  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021f85  mov     ebx, 0C5580701h
0x180021f8a  jmp     loc_180022507
0x180021f8f  mov     [rsp+118h+var_D0], r15
0x180021f94  mov     rcx, [rsp+118h+var_98]
0x180021f9c  mov     rax, [rcx]
0x180021f9f  lea     r9, [rsp+118h+var_D0]
0x180021fa4  lea     r8, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x180021fab  xor     edx, edx
0x180021fad  mov     rax, [rax+18h]
0x180021fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb6  mov     ebx, eax
0x180021fb8  test    eax, eax
0x180021fba  jns     loc_180022057
0x180021fc0  mov     rcx, [rsp+118h+var_D0]
0x180021fc5  test    rcx, rcx
0x180021fc8  jz      short loc_180021FD7
0x180021fca  mov     rdx, [rcx]
0x180021fcd  mov     rax, [rdx+10h]
0x180021fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fd6  nop
0x180021fd7  mov     rcx, [rsp+118h+var_C8]
0x180021fdc  test    rcx, rcx
0x180021fdf  jz      short loc_180021FEE
0x180021fe1  mov     rax, [rcx]
0x180021fe4  mov     rax, [rax+10h]
0x180021fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fed  nop
0x180021fee  lea     rcx, [rsp+118h+pvarg]; pvarg
0x180021ff6  call    cs:__imp_VariantClear
0x180021ffc  nop
0x180021ffd  mov     rcx, [rsp+118h+var_E0]
0x180022002  test    rcx, rcx
0x180022005  jz      short loc_180022014
0x180022007  mov     rax, [rcx]
0x18002200a  mov     rax, [rax+10h]
0x18002200e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022013  nop
0x180022014  mov     rcx, rdi; bstrString
0x180022017  call    cs:__imp_SysFreeString
0x18002201d  nop
0x18002201e  mov     rcx, [rsp+118h+var_90]
0x180022026  test    rcx, rcx
0x180022029  jz      short loc_180022038
0x18002202b  mov     rax, [rcx]
0x18002202e  mov     rax, [rax+10h]
0x180022032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022037  nop
0x180022038  mov     rcx, [rsp+118h+var_98]
0x180022040  test    rcx, rcx
0x180022043  jz      short loc_180022052
0x180022045  mov     rax, [rcx]
0x180022048  mov     rax, [rax+10h]
0x18002204c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022051  nop
0x180022052  jmp     loc_180022537
0x180022057  mov     rcx, [rsp+118h+var_D0]
0x18002205c  mov     rax, [rcx]
0x18002205f  xor     edx, edx
0x180022061  mov     rax, [rax+1F8h]
0x180022068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002206d  mov     ebx, eax
0x18002206f  test    eax, eax
0x180022071  js      loc_1800224E2
0x180022077  mov     rcx, [rsp+118h+var_D0]
0x18002207c  mov     rax, [rcx]
  ... truncated ...
```
