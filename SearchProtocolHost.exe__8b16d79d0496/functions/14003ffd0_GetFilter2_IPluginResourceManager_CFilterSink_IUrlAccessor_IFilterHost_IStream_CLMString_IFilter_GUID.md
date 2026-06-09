# GetFilter2(IPluginResourceManager *,CFilterSink *,IUrlAccessor *,IFilterHost *,IStream *,CLMString &,IFilter * *,_GUID *)

- ea: `0x14003ffd0`
- end: `0x140040530`
- name: `?GetFilter2@@YAJPEAUIPluginResourceManager@@PEAVCFilterSink@@PEAUIUrlAccessor@@PEAUIFilterHost@@PEAUIStream@@AEAVCLMString@@PEAPEAUIFilter@@PEAU_GUID@@@Z`
- size: `1376`
- prototype: `__int64 __fastcall(struct IPluginResourceManager *, struct CFilterSink *, struct IUrlAccessor *, struct IFilterHost *, struct IStream *, struct CLMString *, struct IFilter **, struct _GUID *)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x140005240`
- `0x14000cce4`
- `0x14000e614`
- `0x14000e898`
- `0x14000e97c`
- `0x14000ea30`
- `0x140010494`
- `0x140015b14`
- `0x140016098`
- `0x14001d940`
- `0x1400216e4`
- `0x1400317e8`
- `0x14003376c`
- `0x1400339d0`
- `0x140033cbc`
- `0x140033ea0`
- `0x14003e7c8`
- `0x14003ff88`
- `0x14003ffd0`
- `0x140040538`
- `0x140041564`
- `0x140041628`
- `0x140042314`
- `0x14004dddc`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1400403e2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1400403e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetFilter2(
        struct IPluginResourceManager *a1,
        struct CFilterSink *a2,
        struct IUrlAccessor *a3,
        struct IFilterHost *a4,
        struct IStream *a5,
        struct CLMString *a6,
        struct IFilter **a7,
        struct _GUID *a8)
{
  struct IFilter **v11; // rbx
  int v12; // eax
  __int128 *v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // r8d
  __int64 Extension; // rax
  __int64 v17; // rax
  HRESULT (__stdcall *GetDocFormat)(IUrlAccessor *, WCHAR[], DWORD, DWORD *); // rbx
  wchar_t *Buffer; // rax
  unsigned int v20; // eax
  __int64 v21; // r15
  int v22; // r10d
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rdx
  int v26; // ebx
  int v27; // r14d
  char v28; // di
  bool v29; // zf
  const wchar_t *v30; // rcx
  int Filter2Internal; // eax
  int SemanticSetting; // [rsp+50h] [rbp-B0h]
  unsigned int v34; // [rsp+60h] [rbp-A0h] BYREF
  struct IFilter **v35; // [rsp+68h] [rbp-98h]
  __int128 *v36; // [rsp+70h] [rbp-90h]
  _QWORD v37[2]; // [rsp+78h] [rbp-88h] BYREF
  GUID pclsid; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v39[5]; // [rsp+A8h] [rbp-58h] BYREF
  void **v40; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  __int16 v43; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v44; // [rsp+130h] [rbp+30h] BYREF
  void **v45; // [rsp+140h] [rbp+40h] BYREF
  __int16 *v46; // [rsp+148h] [rbp+48h]
  __int64 v47; // [rsp+150h] [rbp+50h]
  __int16 v48; // [rsp+158h] [rbp+58h] BYREF
  WCHAR v49[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  void **v50; // [rsp+1C0h] [rbp+C0h] BYREF
  int v51; // [rsp+1C8h] [rbp+C8h]
  void **v52; // [rsp+1D8h] [rbp+D8h]
  __int16 *v53; // [rsp+1E0h] [rbp+E0h]
  __int64 v54; // [rsp+1E8h] [rbp+E8h]
  __int16 v55; // [rsp+1F0h] [rbp+F0h] BYREF
  int v56; // [rsp+398h] [rbp+298h]
  void **v57; // [rsp+3A0h] [rbp+2A0h] BYREF
  wchar_t *v58; // [rsp+3A8h] [rbp+2A8h]
  __int64 v59; // [rsp+3B0h] [rbp+2B0h]
  __int16 v60; // [rsp+3B8h] [rbp+2B8h] BYREF

  v37[1] = -2;
  *(_QWORD *)&pclsid.Data1 = a1;
  v11 = a7;
  v35 = a7;
  if ( a2 && a3 && a7 && a5 && a4 )
  {
    v44 = 0;
    v34 = 0;
    v46 = &v48;
    v47 = 33;
    v48 = 0;
    v45 = &TLMString<32,32,1024>::`vftable';
    v41 = (unsigned __int64)&v43;
    v42 = 33;
    v43 = 0;
    v40 = &TLMString<32,32,1024>::`vftable';
    v12 = ((__int64 (__fastcall *)(struct IUrlAccessor *, __int128 *))a3->lpVtbl->GetCLSID)(a3, &v44);
    v13 = &v44;
    if ( v12 < 0 )
      v13 = 0;
    v36 = v13;
    v37[0] = 0;
    v58 = (wchar_t *)&v60;
    v59 = 193;
    v60 = 0;
    v57 = &TLMString<192,64,32767>::`vftable';
    if ( ((__int64 (__fastcall *)(struct IUrlAccessor *, GUID *, _QWORD *))a3->lpVtbl->QueryInterface)(
           a3,
           &GUID_c7310734_ac80_11d1_8df3_00c04fb6ef4f,
           v37) >= 0 )
    {
      ImportLMString<IUrlAccessor2,long (IUrlAccessor2::*)(wchar_t * const,unsigned long,unsigned long *)>(
        v37[0],
        v14,
        &v57);
      v51 = 0;
      v53 = &v55;
      v54 = 193;
      v55 = 0;
      v52 = &TLMString<192,64,32767>::`vftable';
      v50 = &CComObjectStackRefCount<CURL>::`vftable';
      v56 = 0;
      CURL::Init((CURL *)&v50, v58, v15);
      if ( *(_DWORD *)(CURL::GetExtension(&v50, v39) + 4) )
      {
        Extension = CURL::GetExtension(&v50, v39);
        CLMString::operator=(&v45, Extension);
      }
      CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(&v50);
    }
    if ( !HIDWORD(v47) )
    {
      v17 = CURL::GetExtension((char *)a2 + 1072, v39);
      CLMString::operator=(&v45, v17);
      if ( !HIDWORD(v47) )
      {
        GetDocFormat = a3->lpVtbl->GetDocFormat;
        Buffer = CLMString::GetBuffer((CLMString *)&v40, 0);
        if ( ((int (__fastcall *)(struct IUrlAccessor *, wchar_t *, __int64, unsigned int *))GetDocFormat)(
               a3,
               Buffer,
               33,
               &v34) < 0 )
        {
          HIDWORD(v42) = 0;
          *(_WORD *)v41 = 0;
        }
        else
        {
          CLMString::Truncate((CLMString *)&v40, v34);
          v20 = CLMString::Find((CLMString *)&v40, 0x3Bu, 0);
          if ( v20 != -1 )
            CLMString::Truncate((CLMString *)&v40, v20);
        }
        v11 = v35;
      }
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl'::`2'::impl) )
      {
        SemanticSetting = CFilterSink::GetSemanticSetting(a2);
        Filter2Internal = GetFilter2Internal(
                            *(_QWORD *)&pclsid.Data1,
                            v36,
                            a4,
                            a5,
                            v41 & -(__int64)(HIDWORD(v42) != 0),
                            v46,
                            *((_QWORD *)a6 + 1),
                            v11,
                            a8,
                            0,
                            SemanticSetting,
                            0);
      }
      else
      {
        Filter2Internal = GetFilter2Internal(
                            *(_QWORD *)&pclsid.Data1,
                            v36,
                            a4,
                            a5,
                            v41 & -(__int64)(HIDWORD(v42) != 0),
                            v46,
                            *((_QWORD *)a6 + 1),
                            v11,
                            a8,
                            0,
                            0,
                            0);
      }
      v26 = Filter2Internal;
      goto LABEL_46;
    }
    v21 = *((_QWORD *)a2 + 138);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
    {
      LODWORD(v35) = *((_DWORD *)a2 + 662);
      v22 = CFilterSink::GetSemanticSetting(a2);
      v23 = v41 & -(__int64)(HIDWORD(v42) != 0);
      v24 = (int)v35;
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl'::`2'::impl) )
      {
        v22 = CFilterSink::GetSemanticSetting(a2);
        v25 = -(__int64)(HIDWORD(v42) != 0);
      }
      else
      {
        v25 = -(__int64)(HIDWORD(v42) != 0);
        v22 = 0;
      }
      v23 = v41 & v25;
      v24 = 0;
    }
    v26 = GetFilter2Internal(
            *(_QWORD *)&pclsid.Data1,
            v36,
            a4,
            a5,
            v23,
            v46,
            *((_QWORD *)a6 + 1),
            v11,
            a8,
            v21,
            v22,
            v24);
    v27 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl'::`2'::impl) )
      v27 = CFilterSink::GetSemanticSetting(a2);
    if ( !IsSemanticIndexingAllowed() || v27 )
      goto LABEL_46;
    std::wstring::wstring(v49, v21);
    ParseExtensionFromUrl((__int64)v39, v49);
    std::wstring::_Tidy_deallocate(v49);
    std::wstring::wstring(&pclsid, v21);
    v28 = IsSemanticImageIndexingApplicableOnItem(&pclsid);
    std::wstring::_Tidy_deallocate(&pclsid);
    if ( v26 == -2147218154 )
    {
      v29 = v28 == 0;
    }
    else
    {
      if ( v26 < 0 )
        goto LABEL_41;
      if ( !v28 )
        goto LABEL_41;
      pclsid = 0;
      if ( CLSIDFromString(L"{97D926B2-7ED2-449B-BD9B-9BB6958D2A1D}", &pclsid) < 0 )
        goto LABEL_41;
      if ( *(_QWORD *)&a8->Data1 != *(_QWORD *)&pclsid.Data1 )
      {
LABEL_38:
        v30 = (const wchar_t *)v39;
        if ( v39[3] > (wchar_t *)7 )
          v30 = v39[0];
        SemanticSearchTelemetryAggregated::ReportSemanticFilterOverwritten(v30);
        goto LABEL_41;
      }
      v29 = *(_QWORD *)a8->Data4 == *(_QWORD *)pclsid.Data4;
    }
    if ( !v29 )
      goto LABEL_38;
LABEL_41:
    std::wstring::_Tidy_deallocate(v39);
LABEL_46:
    TLMString<192,64,32767>::~TLMString<192,64,32767>(&v57);
    TComPointer<IBindCtx>::~TComPointer<IBindCtx>(v37);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v40);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v45);
    return (unsigned int)v26;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x14003ffd0  push    rbp
0x14003ffd2  push    rbx
0x14003ffd3  push    rsi
0x14003ffd4  push    rdi
0x14003ffd5  push    r12
0x14003ffd7  push    r13
0x14003ffd9  push    r14
0x14003ffdb  push    r15
0x14003ffdd  lea     rbp, [rsp-458h]
0x14003ffe5  sub     rsp, 558h
0x14003ffec  mov     [rbp+490h+var_510], 0FFFFFFFFFFFFFFFEh
0x14003fff4  mov     rax, cs:__security_cookie
0x14003fffb  xor     rax, rsp
0x14003fffe  mov     [rbp+490h+var_50], rax
0x140040005  mov     r12, r9
0x140040008  mov     r15, r8
0x14004000b  mov     rdi, rdx
0x14004000e  mov     qword ptr [rbp+490h+pclsid.Data1], rcx
0x140040012  mov     r13, [rbp+490h+arg_20]
0x140040019  mov     r14, [rbp+490h+arg_28]
0x140040020  mov     rbx, [rbp+490h+arg_30]
0x140040027  mov     [rsp+590h+var_528], rbx
0x14004002c  mov     rsi, [rbp+490h+arg_38]
0x140040033  xor     edx, edx
0x140040035  test    rdi, rdi
0x140040038  jz      loc_140040508
0x14004003e  test    r8, r8
0x140040041  jz      loc_140040508
0x140040047  test    rbx, rbx
0x14004004a  jz      loc_140040508
0x140040050  test    r13, r13
0x140040053  jz      loc_140040508
0x140040059  test    r9, r9
0x14004005c  jz      loc_140040508
0x140040062  xorps   xmm0, xmm0
0x140040065  movups  [rbp+490h+var_460], xmm0
0x140040069  mov     [rsp+590h+var_530], edx
0x14004006d  lea     rax, [rbp+490h+var_438]
0x140040071  mov     [rbp+490h+var_448], rax
0x140040075  mov     [rbp+490h+var_440], 21h ; '!'
0x14004007d  mov     [rbp+490h+var_438], dx
0x140040081  lea     rcx, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x140040088  mov     [rbp+490h+var_450], rcx
0x14004008c  lea     rax, [rbp+490h+var_4A8]
0x140040090  mov     [rbp+490h+var_4B8], rax
0x140040094  mov     [rbp+490h+var_4B0], 21h ; '!'
0x14004009c  mov     [rbp+490h+var_4A8], dx
0x1400400a0  mov     [rbp+490h+var_4C0], rcx
0x1400400a4  mov     rax, [r8]
0x1400400a7  lea     rdx, [rbp+490h+var_460]
0x1400400ab  mov     rcx, r8
0x1400400ae  mov     rax, [rax+28h]
0x1400400b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400400b7  lea     rdx, [rbp+490h+var_460]
0x1400400bb  xor     ecx, ecx
0x1400400bd  test    eax, eax
0x1400400bf  cmovs   rdx, rcx
0x1400400c3  mov     [rsp+590h+var_520], rdx
0x1400400c8  mov     [rsp+590h+var_518], rcx
0x1400400cd  lea     rax, [rbp+490h+var_1D8]
0x1400400d4  mov     [rbp+490h+var_1E8], rax
0x1400400db  mov     [rbp+490h+var_1E0], 0C1h
0x1400400e6  xor     eax, eax
0x1400400e8  mov     [rbp+490h+var_1D8], ax
0x1400400ef  lea     rax, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x1400400f6  mov     [rbp+490h+var_1F0], rax
0x1400400fd  mov     rax, [r15]
0x140040100  lea     r8, [rsp+590h+var_518]
0x140040105  lea     rdx, _GUID_c7310734_ac80_11d1_8df3_00c04fb6ef4f
0x14004010c  mov     rcx, r15
0x14004010f  mov     rax, [rax]
0x140040112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040117  test    eax, eax
0x140040119  js      loc_1400401CC
0x14004011f  lea     r8, [rbp+490h+var_1F0]
0x140040126  mov     rcx, [rsp+590h+var_518]
0x14004012b  call    ??$ImportLMString@UIUrlAccessor2@@P81@EAAJQEA_WKPEAK@Z@@YAJPEAUIUrlAccessor2@@P80@EAAJQEA_WKPEAK@ZAEAVCLMString@@@Z; ImportLMString<IUrlAccessor2,long (IUrlAccessor2::*)(wchar_t * const,ulong,ulong *)>(IUrlAccessor2 *,long (IUrlAccessor2::*)(wchar_t * const,ulong,ulong *),CLMString &)
0x140040130  xor     ecx, ecx
0x140040132  mov     [rbp+490h+var_3C8], ecx
0x140040138  lea     rax, [rbp+490h+var_3A0]
0x14004013f  mov     [rbp+490h+var_3B0], rax
0x140040146  mov     [rbp+490h+var_3A8], 0C1h
0x140040151  mov     [rbp+490h+var_3A0], cx
0x140040158  lea     rax, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x14004015f  mov     [rbp+490h+var_3B8], rax
0x140040166  lea     rax, ??_7?$CComObjectStackRefCount@VCURL@@@@6B@; const CComObjectStackRefCount<CURL>::`vftable'
0x14004016d  mov     [rbp+490h+var_3D0], rax
0x140040174  mov     [rbp+490h+var_1F8], ecx
0x14004017a  mov     rdx, [rbp+490h+var_1E8]; wchar_t *
0x140040181  lea     rcx, [rbp+490h+var_3D0]; this
0x140040188  call    ?Init@CURL@@QEAAJPEB_WK@Z; CURL::Init(wchar_t const *,ulong)
0x14004018d  lea     rdx, [rbp+490h+var_4E8]
0x140040191  lea     rcx, [rbp+490h+var_3D0]
0x140040198  call    ?GetExtension@CURL@@QEAA?AVCLMSubStr@@XZ; CURL::GetExtension(void)
0x14004019d  cmp     dword ptr [rax+4], 0
0x1400401a1  jz      short loc_1400401C0
0x1400401a3  lea     rdx, [rbp+490h+var_4E8]
0x1400401a7  lea     rcx, [rbp+490h+var_3D0]
0x1400401ae  call    ?GetExtension@CURL@@QEAA?AVCLMSubStr@@XZ; CURL::GetExtension(void)
0x1400401b3  mov     rdx, rax
0x1400401b6  lea     rcx, [rbp+490h+var_450]
0x1400401ba  call    ??4CLMString@@QEAAXAEBVCLMSubStr@@@Z; CLMString::operator=(CLMSubStr const &)
0x1400401bf  nop
0x1400401c0  lea     rcx, [rbp+490h+var_3D0]
0x1400401c7  call    ??1?$CComObjectStackRefCount@VCURL@@@@QEAA@XZ; CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(void)
0x1400401cc  cmp     dword ptr [rbp+490h+var_440+4], 0
0x1400401d0  jnz     loc_14004026C
0x1400401d6  lea     rcx, [rdi+430h]
0x1400401dd  lea     rdx, [rbp+490h+var_4E8]
0x1400401e1  call    ?GetExtension@CURL@@QEAA?AVCLMSubStr@@XZ; CURL::GetExtension(void)
0x1400401e6  mov     rdx, rax
0x1400401e9  lea     rcx, [rbp+490h+var_450]
0x1400401ed  call    ??4CLMString@@QEAAXAEBVCLMSubStr@@@Z; CLMString::operator=(CLMSubStr const &)
0x1400401f2  cmp     dword ptr [rbp+490h+var_440+4], 0
0x1400401f6  jnz     short loc_14004026C
0x1400401f8  mov     rax, [r15]
0x1400401fb  mov     rbx, [rax+20h]
0x1400401ff  xor     edx, edx; int
0x140040201  lea     rcx, [rbp+490h+var_4C0]; this
0x140040205  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x14004020a  lea     r9, [rsp+590h+var_530]
0x14004020f  mov     r8d, 21h ; '!'
0x140040215  mov     rdx, rax
0x140040218  mov     rcx, r15
0x14004021b  mov     rax, rbx
0x14004021e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040223  test    eax, eax
0x140040225  js      short loc_140040257
0x140040227  mov     edx, [rsp+590h+var_530]; unsigned int
0x14004022b  lea     rcx, [rbp+490h+var_4C0]; this
0x14004022f  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x140040234  mov     edx, 3Bh ; ';'; wchar_t
0x140040239  xor     r8d, r8d; unsigned int
0x14004023c  lea     rcx, [rbp+490h+var_4C0]; this
0x140040240  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x140040245  cmp     eax, 0FFFFFFFFh
0x140040248  jz      short loc_140040267
0x14004024a  mov     edx, eax; unsigned int
0x14004024c  lea     rcx, [rbp+490h+var_4C0]; this
0x140040250  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x140040255  jmp     short loc_140040267
0x140040257  mov     dword ptr [rbp+490h+var_4B0+4], 0
0x14004025e  xor     ecx, ecx
0x140040260  mov     rax, [rbp+490h+var_4B8]
0x140040264  mov     [rax], cx
0x140040267  mov     rbx, [rsp+590h+var_528]
0x14004026c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x140040273  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x140040278  test    al, al
0x14004027a  jz      loc_140040421
0x140040280  mov     r15, [rdi+450h]
0x140040287  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55904201@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201> `wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl(void)'::`2'::impl
0x14004028e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(void)
0x140040293  test    al, al
0x140040295  jz      short loc_1400402BE
0x140040297  mov     eax, [rdi+0A58h]
0x14004029d  mov     dword ptr [rsp+590h+var_528], eax
0x1400402a1  mov     rcx, rdi
0x1400402a4  call    ?GetSemanticSetting@CFilterSink@@QEBA?AW4SemanticSetting@@XZ; CFilterSink::GetSemanticSetting(void)
0x1400402a9  mov     r10d, eax
0x1400402ac  mov     ecx, dword ptr [rbp+490h+var_4B0+4]
0x1400402af  neg     ecx
0x1400402b1  sbb     rdx, rdx
0x1400402b4  and     rdx, [rbp+490h+var_4B8]
0x1400402b8  mov     eax, dword ptr [rsp+590h+var_528]
0x1400402bc  jmp     short loc_1400402F4
0x1400402be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56981110@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110> `wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl(void)'::`2'::impl
0x1400402c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(void)
0x1400402ca  test    al, al
0x1400402cc  jz      short loc_1400402E3
0x1400402ce  mov     rcx, rdi
0x1400402d1  call    ?GetSemanticSetting@CFilterSink@@QEBA?AW4SemanticSetting@@XZ; CFilterSink::GetSemanticSetting(void)
0x1400402d6  mov     r10d, eax
0x1400402d9  mov     eax, dword ptr [rbp+490h+var_4B0+4]
0x1400402dc  neg     eax
0x1400402de  sbb     rdx, rdx
0x1400402e1  jmp     short loc_1400402EE
0x1400402e3  mov     eax, dword ptr [rbp+490h+var_4B0+4]
0x1400402e6  neg     eax
0x1400402e8  sbb     rdx, rdx
0x1400402eb  xor     r10d, r10d
0x1400402ee  and     rdx, [rbp+490h+var_4B8]
0x1400402f2  xor     eax, eax
0x1400402f4  mov     r9, [r14+8]
0x1400402f8  mov     r8, [rbp+490h+var_448]
0x1400402fc  mov     [rsp+590h+var_538], eax
0x140040300  mov     [rsp+590h+var_540], r10d
0x140040305  mov     [rsp+590h+var_548], r15
0x14004030a  mov     [rsp+590h+var_550], rsi
0x14004030f  mov     [rsp+590h+var_558], rbx
0x140040314  mov     [rsp+590h+var_560], r9
0x140040319  mov     [rsp+590h+var_568], r8
0x14004031e  mov     [rsp+590h+var_570], rdx
0x140040323  mov     r9, r13
0x140040326  mov     r8, r12
0x140040329  mov     rdx, [rsp+590h+var_520]
0x14004032e  mov     rcx, qword ptr [rbp+490h+pclsid.Data1]
0x140040332  call    ?GetFilter2Internal@@YAJPEAUIPluginResourceManager@@PEAU_GUID@@PEAUIFilterHost@@PEAUIStream@@PEB_W44PEAPEAUIFilter@@14W4SemanticSetting@@W4tagFilterProcessingFlags@@@Z; GetFilter2Internal(IPluginResourceManager *,_GUID *,IFilterHost *,IStream *,wchar_t const *,wchar_t const *,wchar_t const *,IFilter * *,_GUID *,wchar_t const *,SemanticSetting,tagFilterProcessingFlags)
0x140040337  mov     ebx, eax
0x140040339  xor     r14d, r14d
0x14004033c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56981110@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110> `wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl(void)'::`2'::impl
0x140040343  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(void)
0x140040348  test    al, al
0x14004034a  jz      short loc_140040357
0x14004034c  mov     rcx, rdi
0x14004034f  call    ?GetSemanticSetting@CFilterSink@@QEBA?AW4SemanticSetting@@XZ; CFilterSink::GetSemanticSetting(void)
0x140040354  mov     r14d, eax
0x140040357  call    ?IsSemanticIndexingAllowed@@YA_NXZ; IsSemanticIndexingAllowed(void)
0x14004035c  test    al, al
0x14004035e  jz      loc_1400404D9
0x140040364  test    r14d, r14d
0x140040367  jnz     loc_1400404D9
0x14004036d  mov     rdx, r15
0x140040370  lea     rcx, [rbp+490h+var_3F0]
0x140040377  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14004037c  lea     rdx, [rbp+490h+var_3F0]
0x140040383  lea     rcx, [rbp+490h+var_4E8]
0x140040387  call    ?ParseExtensionFromUrl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@Z; ParseExtensionFromUrl(std::wstring const &)
0x14004038c  nop
0x14004038d  lea     rcx, [rbp+490h+var_3F0]
0x140040394  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140040399  mov     rdx, r15
0x14004039c  lea     rcx, [rbp+490h+pclsid]
0x1400403a0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400403a5  lea     rcx, [rbp+490h+pclsid]
0x1400403a9  call    ?IsSemanticImageIndexingApplicableOnItem@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; IsSemanticImageIndexingApplicableOnItem(std::wstring const &)
0x1400403ae  mov     dil, al
0x1400403b1  lea     rcx, [rbp+490h+pclsid]
0x1400403b5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400403ba  cmp     ebx, 80040D16h
0x1400403c0  jnz     short loc_1400403C7
0x1400403c2  test    dil, dil
0x1400403c5  jmp     short loc_1400403FD
0x1400403c7  test    ebx, ebx
0x1400403c9  js      short loc_140040413
0x1400403cb  test    dil, dil
0x1400403ce  jz      short loc_140040413
0x1400403d0  xorps   xmm0, xmm0
0x1400403d3  movups  xmmword ptr [rbp+490h+pclsid.Data1], xmm0
0x1400403d7  lea     rdx, [rbp+490h+pclsid]; pclsid
0x1400403db  mov     rcx, cs:lpsz; lpsz
0x1400403e2  call    cs:__imp_CLSIDFromString
0x1400403e8  test    eax, eax
0x1400403ea  js      short loc_140040413
0x1400403ec  mov     rax, [rsi]
0x1400403ef  cmp     rax, qword ptr [rbp+490h+pclsid.Data1]
0x1400403f3  jnz     short loc_1400403FF
0x1400403f5  mov     rax, [rsi+8]
0x1400403f9  cmp     rax, qword ptr [rbp+490h+pclsid.Data4]
0x1400403fd  jz      short loc_140040413
0x1400403ff  lea     rcx, [rbp+490h+var_4E8]
0x140040403  cmp     [rbp+490h+var_4D0], 7
0x140040408  cmova   rcx, [rbp+490h+var_4E8]; wchar_t *
0x14004040d  call    ?ReportSemanticFilterOverwritten@SemanticSearchTelemetryAggregated@@SAXPEB_W@Z; SemanticSearchTelemetryAggregated::ReportSemanticFilterOverwritten(wchar_t const *)
0x140040412  nop
0x140040413  lea     rcx, [rbp+490h+var_4E8]
0x140040417  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004041c  jmp     loc_1400404D9
0x140040421  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56981110@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110> `wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl(void)'::`2'::impl
0x140040428  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(void)
0x14004042d  test    al, al
0x14004042f  jz      short loc_14004047D
0x140040431  mov     rcx, rdi
0x140040434  call    ?GetSemanticSetting@CFilterSink@@QEBA?AW4SemanticSetting@@XZ; CFilterSink::GetSemanticSetting(void)
0x140040439  mov     r8, [r14+8]
0x14004043d  mov     r9, [rbp+490h+var_448]
0x140040441  mov     ecx, dword ptr [rbp+490h+var_4B0+4]
0x140040444  neg     ecx
0x140040446  sbb     rdx, rdx
0x140040449  and     rdx, [rbp+490h+var_4B8]
0x14004044d  mov     [rsp+590h+var_538], 0
0x140040455  mov     [rsp+590h+var_540], eax
0x140040459  mov     [rsp+590h+var_548], 0
0x140040462  mov     [rsp+590h+var_550], rsi
0x140040467  mov     [rsp+590h+var_558], rbx
0x14004046c  mov     [rsp+590h+var_560], r8
0x140040471  mov     [rsp+590h+var_568], r9
0x140040476  mov     [rsp+590h+var_570], rdx
0x14004047b  jmp     short loc_1400404C3
0x14004047d  mov     rdx, [r14+8]
0x140040481  mov     r8, [rbp+490h+var_448]
0x140040485  mov     eax, dword ptr [rbp+490h+var_4B0+4]
0x140040488  neg     eax
0x14004048a  sbb     rcx, rcx
0x14004048d  and     rcx, [rbp+490h+var_4B8]
0x140040491  mov     [rsp+590h+var_538], 0
0x140040499  mov     [rsp+590h+var_540], 0
0x1400404a1  mov     [rsp+590h+var_548], 0
0x1400404aa  mov     [rsp+590h+var_550], rsi
0x1400404af  mov     [rsp+590h+var_558], rbx
0x1400404b4  mov     [rsp+590h+var_560], rdx
0x1400404b9  mov     [rsp+590h+var_568], r8
0x1400404be  mov     [rsp+590h+var_570], rcx
0x1400404c3  mov     r9, r13
0x1400404c6  mov     r8, r12
0x1400404c9  mov     rdx, [rsp+590h+var_520]
0x1400404ce  mov     rcx, qword ptr [rbp+490h+pclsid.Data1]
0x1400404d2  call    ?GetFilter2Internal@@YAJPEAUIPluginResourceManager@@PEAU_GUID@@PEAUIFilterHost@@PEAUIStream@@PEB_W44PEAPEAUIFilter@@14W4SemanticSetting@@W4tagFilterProcessingFlags@@@Z; GetFilter2Internal(IPluginResourceManager *,_GUID *,IFilterHost *,IStream *,wchar_t const *,wchar_t const *,wchar_t const *,IFilter * *,_GUID *,wchar_t const *,SemanticSetting,tagFilterProcessingFlags)
0x1400404d7  mov     ebx, eax
0x1400404d9  lea     rcx, [rbp+490h+var_1F0]
  ... truncated ...
```
