# CMapi2Accessor::Init(CMapi2Handler *,wchar_t const *,tagBLOB const *,_FILETIME &,ulong)

- ea: `0x180016044`
- end: `0x180016604`
- name: `?Init@CMapi2Accessor@@QEAAJPEAVCMapi2Handler@@PEB_WPEBUtagBLOB@@AEAU_FILETIME@@K@Z`
- size: `1472`
- prototype: `__int64 __fastcall(CMapi2Accessor *__hidden this, struct CMapi2Handler *, const wchar_t *, const struct tagBLOB *, struct _FILETIME *, unsigned int)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f370`

## callees

- `0x180002300`
- `0x18000e658`
- `0x18000e8ac`
- `0x18000ea18`
- `0x18000ebac`
- `0x1800113ac`
- `0x1800113ec`
- `0x180011884`
- `0x18001269c`
- `0x180012a74`
- `0x18001356c`
- `0x18001359c`
- `0x180013f78`
- `0x180014014`
- `0x180014420`
- `0x180014448`
- `0x1800149cc`
- `0x180014e40`
- `0x180014f08`
- `0x180015144`
- `0x1800151b4`
- `0x1800151f4`
- `0x180016044`
- `0x1800166e4`
- `0x180016948`
- `0x1800172fc`
- `0x18001e1e0`
- `0x18001e280`
- `0x18001f990`
- `0x180023b60`
- `0x180024824`
- `0x180029e98`
- `0x18002a18c`
- `0x18002a398`
- `0x18002aa4c`
- `0x1800321dc`
- `0x18003a060`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800162f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800162f6`

## string_xrefs

- `0x1800160db`: `CMapi2Accessor:%s\n`
- `0x1800160f9`: `CMapi2Accessor for %s`
- `0x1800161c0`: `CMapi2Accessor::Init() blocked url %s`
- `0x1800162d8`: `InitDirFilter url (%s) and children will be deleted from index`

## pseudocode

```c
__int64 __fastcall CMapi2Accessor::Init(
        CMapi2Accessor *this,
        struct CMapi2Handler *a2,
        const wchar_t *a3,
        const struct tagBLOB *a4,
        struct _FILETIME *a5,
        unsigned int a6)
{
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  _QWORD *v13; // rax
  wchar_t v14; // dx
  int v15; // edi
  int IsAttachmentOK; // eax
  _BYTE *v17; // rcx
  __int64 v18; // rbx
  CMapi2RowFilter *v19; // rbx
  int v20; // eax
  int DocFormat; // r14d
  unsigned int v22; // r9d
  CMapi2RowFilter *v23; // rbx
  int inited; // eax
  unsigned int v25; // r8d
  int v26; // ebx
  __int64 v27; // rax
  int v28; // ebx
  __int64 v29; // rax
  const wchar_t *v30; // rdx
  unsigned int v31; // r9d
  const wchar_t *v32; // rdx
  const wchar_t *v33; // [rsp+20h] [rbp-E0h]
  CMapi2RowFilter *v34; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v36[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[64]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v38[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h]
  void **v40; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v41; // [rsp+B8h] [rbp-48h]
  int v42; // [rsp+C0h] [rbp-40h]
  char v43; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v44[20]; // [rsp+110h] [rbp+10h] BYREF
  int v45; // [rsp+124h] [rbp+24h]
  _BYTE v46[416]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t v47[4096]; // [rsp+450h] [rbp+350h] BYREF
  wchar_t v48[4096]; // [rsp+2450h] [rbp+2350h] BYREF

  if ( !a3 )
    return 2147500035LL;
  *((_QWORD *)this + 8) = a2;
  *((_DWORD *)this + 446) = 1;
  *((_QWORD *)this + 224) = 0;
  *((_DWORD *)this + 450) = a6;
  CLMString::operator=((char *)this + 96, a3);
  CMapiBlob::FromBlob((CMapi2Accessor *)((char *)this + 512), a4);
  MSNUtil::CDebug::dprintf(L"CMapi2Accessor:%s\n", *((_QWORD *)this + 13));
  CMapiUrl::CMapiUrl((CMapiUrl *)v37, *((const wchar_t **)this + 13));
  CLogger::Info(L"CMapi2Accessor for %s", a3);
  if ( *(int *)(v39 - 16) <= 0 )
    goto LABEL_10;
  v10 = CMapiUrl::AttachmentName(v37, &v35);
  v11 = CMapiUrl::AttachmentName(v37, v36);
  v12 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(v11, 47, 0);
  v13 = (_QWORD *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(
                    v10,
                    &v34,
                    (unsigned int)(v12 + 1));
  TLMString<192,64,32767>::TLMString<192,64,32767>(v46, *v13);
  ATL::CStringData::Release((CMapi2RowFilter *)((char *)v34 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v36[0] - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
  if ( (unsigned int)CLMString::Find((CLMString *)v46, v14, 0) == -1 )
  {
    IsAttachmentOK = CMapi2Accessor::IsAttachmentOK(this, (struct CMapiUrl *)v37);
    if ( IsAttachmentOK )
    {
      CLogger::Info(IsAttachmentOK, L"CMapi2Accessor::Init() blocked url %s", a3);
      v15 = -2147218169;
      goto LABEL_8;
    }
    TLMString<192,64,32767>::~TLMString<192,64,32767>(v46);
LABEL_10:
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      &v35,
      v38);
    v18 = v35;
    TLMString<192,64,32767>::TLMString<192,64,32767>(v44, v35);
    ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
    v34 = 0;
    if ( v45 )
    {
      *((_DWORD *)this + 447) = 1;
      v15 = ATL::CComObject<CMapi2RowFilter>::CreateInstance(&v34);
      if ( v15 < 0 )
        goto LABEL_12;
      TComNoUnkPointer<CMapi2RowFilter>::TComNoUnkPointer<CMapi2RowFilter>(&v34, v34);
      v23 = v34;
      v15 = (**(__int64 (__fastcall ***)(CMapi2RowFilter *, GUID *, char *))v34)(v34, &IID_IFilter, (char *)this + 88);
      if ( v15 < 0 )
        goto LABEL_17;
      inited = CMapi2RowFilter::InitRowFilter(v23, this, 0);
      DocFormat = inited;
      v15 = 266755;
      if ( inited == 266755 )
        goto LABEL_17;
      if ( inited < 0 )
      {
        CLogger::Warning(inited, L"InitRowFilter failed");
        if ( ((DocFormat + 2147221241) & 0xFFFFFFF7) == 0 )
          DocFormat = -2147216895;
        v15 = DocFormat;
        goto LABEL_17;
      }
      *((_DWORD *)this + 20) = *((_DWORD *)v23 + 5418);
      *((_DWORD *)this + 18) = *((_DWORD *)v23 + 5421);
      *((_DWORD *)this + 19) = *((_DWORD *)v23 + 5422);
      CMapi2RowFilter::GetItemPathDisplay(v23, 0, v48, 0x1000u);
      CLMString::operator=((char *)this + 536, v48);
      CLMString::operator=((char *)this + 1368, (char *)v23 + 8768);
      if ( *(int *)(v39 - 16) <= 0 )
      {
        DocFormat = CMapi2RowFilter::GetDocFormat(v23, v48, v25);
        CLMString::operator=((char *)this + 952, v48);
        *((_DWORD *)this + 446) = CMapi2RowFilter::FHasAttachment(v23);
      }
      else
      {
        *((_DWORD *)this + 446) = 0;
        CMapi2RowFilter::GetDocFormat(v23, v48, v25);
        CLMString::operator=((char *)this + 952, v48);
        v26 = *(_DWORD *)(*(_QWORD *)CMapiUrl::AttachmentName(v37, &v35) - 16LL);
        ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
        if ( v26 > 0 )
        {
          CLMString::operator=((char *)this + 952, &dword_1800444C4);
          v27 = CMapiUrl::AttachmentName(v37, &v35);
          v28 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(v27, 46);
          ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
          if ( v28 > 0 )
          {
            v29 = CMapiUrl::AttachmentName(v37, v36);
            v30 = *(const wchar_t **)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(
                                       v29,
                                       &v35,
                                       (unsigned int)v28);
            v40 = &CLMString::`vftable';
            v41 = (wchar_t *)&v43;
            v42 = 33;
            CLMString::AssignInConstructor((CLMString *)&v40, v30, 0xFFFFFFFF);
            v40 = &TLMString<32,32,1024>::`vftable';
            ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v36[0] - 24LL));
            CRegistry::CRegistry((CRegistry *)v47, HKEY_CLASSES_ROOT, v41, v31, v33);
            CRegistry::GetValue((CRegistry *)v47, v32, (CMapi2Accessor *)((char *)this + 952));
            CRegistry::~CRegistry((CRegistry *)v47);
            TLMString<32,32,1024>::~TLMString<32,32,1024>(&v40);
          }
        }
      }
    }
    else
    {
      *((_QWORD *)this + 223) = 1;
      v15 = ATL::CComObject<CMapi2DirFilter>::CreateInstance(&v34);
      if ( v15 < 0 )
      {
LABEL_12:
        v17 = v44;
        goto LABEL_13;
      }
      v19 = v34;
      if ( v34 )
        (*(void (__fastcall **)(CMapi2RowFilter *))(*(_QWORD *)v34 + 8LL))(v34);
      v15 = (**(__int64 (__fastcall ***)(CMapi2RowFilter *, GUID *, char *))v19)(v19, &IID_IFilter, (char *)this + 88);
      if ( v15 < 0 )
      {
LABEL_17:
        TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v34);
        goto LABEL_12;
      }
      v20 = CMapi2DirFilter::InitDirFilter(v19, this, a5, a6);
      DocFormat = v20;
      if ( v20 >= 0 )
      {
        v15 = 266755;
        if ( v20 == 266755 )
          goto LABEL_17;
        GetSystemTimeAsFileTime((LPFILETIME)this + 9);
        CMapi2DirFilter::GetItemPathDisplay(v19, 0, v47, v22);
        CLMString::operator=((char *)this + 536, v47);
        CLMString::operator=((char *)this + 952, L"MAPI/IPM.Folder");
      }
      else
      {
        CLogger::Warning(v20, L"InitDirFilter failed");
        if ( ((DocFormat + 2147221241) & 0xFFFFFFF7) == 0 )
        {
          DocFormat = -2147216895;
          CLogger::Warning(-2147216895, L"InitDirFilter url (%s) and children will be deleted from index", a3);
        }
      }
    }
    TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v34);
    TLMString<192,64,32767>::~TLMString<192,64,32767>(v44);
    v15 = DocFormat;
    goto LABEL_38;
  }
  v15 = -2147216895;
LABEL_8:
  v17 = v46;
LABEL_13:
  TLMString<192,64,32767>::~TLMString<192,64,32767>(v17);
LABEL_38:
  CMapiUrl::~CMapiUrl((CMapiUrl *)v37);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180016044  push    rbp
0x180016046  push    rbx
0x180016047  push    rsi
0x180016048  push    rdi
0x180016049  push    r12
0x18001604b  push    r14
0x18001604d  push    r15
0x18001604f  lea     rbp, [rsp-4360h]
0x180016057  mov     eax, 4460h
0x18001605c  call    _alloca_probe
0x180016061  sub     rsp, rax
0x180016064  mov     rax, cs:__security_cookie
0x18001606b  xor     rax, rsp
0x18001606e  mov     [rbp+4390h+var_40], rax
0x180016075  mov     rbx, r9
0x180016078  mov     r15, r8
0x18001607b  mov     rsi, rcx
0x18001607e  mov     r12, [rbp+4390h+arg_20]
0x180016085  test    r8, r8
0x180016088  jnz     short loc_180016094
0x18001608a  mov     eax, 80004003h
0x18001608f  jmp     loc_1800165E3
0x180016094  mov     [rcx+40h], rdx
0x180016098  mov     edi, 1
0x18001609d  mov     [rcx+6F8h], edi
0x1800160a3  mov     qword ptr [rcx+700h], 0
0x1800160ae  mov     r14d, [rbp+4390h+arg_28]
0x1800160b5  mov     [rcx+708h], r14d
0x1800160bc  add     rcx, 60h ; '`'
0x1800160c0  mov     rdx, r15
0x1800160c3  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800160c8  lea     rcx, [rsi+200h]; this
0x1800160cf  mov     rdx, rbx; struct tagBLOB *
0x1800160d2  call    ?FromBlob@CMapiBlob@@QEAAJPEBUtagBLOB@@@Z; CMapiBlob::FromBlob(tagBLOB const *)
0x1800160d7  mov     rdx, [rsi+68h]
0x1800160db  lea     rcx, aCmapi2accessor_5; "CMapi2Accessor:%s\n"
0x1800160e2  call    ?dprintf@CDebug@MSNUtil@@SAHPEB_WZZ; MSNUtil::CDebug::dprintf(wchar_t const *,...)
0x1800160e7  mov     rdx, [rsi+68h]; wchar_t *
0x1800160eb  lea     rcx, [rsp+4490h+var_4440]; this
0x1800160f0  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x1800160f5  nop
0x1800160f6  mov     rdx, r15
0x1800160f9  lea     rcx, aCmapi2accessor_3; "CMapi2Accessor for %s"
0x180016100  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180016105  mov     rax, [rbp+4390h+var_43F8]
0x180016109  cmp     dword ptr [rax-10h], 0
0x18001610d  jle     loc_1800161E8
0x180016113  lea     rdx, [rsp+4490h+var_4458]
0x180016118  lea     rcx, [rsp+4490h+var_4440]
0x18001611d  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x180016122  mov     rbx, rax
0x180016125  lea     rdx, [rsp+4490h+var_4450]
0x18001612a  lea     rcx, [rsp+4490h+var_4440]
0x18001612f  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x180016134  nop
0x180016135  lea     edx, [rdi+2Eh]
0x180016138  xor     r8d, r8d
0x18001613b  mov     rcx, rax
0x18001613e  call    ?Find@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAH_WH@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Find(wchar_t,int)
0x180016143  lea     r8d, [rdi+rax]
0x180016147  lea     rdx, [rsp+4490h+var_4460]
0x18001614c  mov     rcx, rbx
0x18001614f  call    ?Mid@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(int)
0x180016154  nop
0x180016155  mov     rdx, [rax]
0x180016158  lea     rcx, [rbp+4390h+var_41E0]
0x18001615f  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(wchar_t const *)
0x180016164  nop
0x180016165  mov     rcx, [rsp+4490h+var_4460]
0x18001616a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001616e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016173  nop
0x180016174  mov     rcx, [rsp+4490h+var_4450]
0x180016179  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001617d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016182  nop
0x180016183  mov     rcx, [rsp+4490h+var_4458]
0x180016188  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001618c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016191  xor     r8d, r8d; unsigned int
0x180016194  lea     rcx, [rbp+4390h+var_41E0]; this
0x18001619b  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x1800161a0  cmp     eax, 0FFFFFFFFh
0x1800161a3  jz      short loc_1800161AC
0x1800161a5  mov     edi, 80041201h
0x1800161aa  jmp     short loc_1800161D3
0x1800161ac  lea     rdx, [rsp+4490h+var_4440]; struct CMapiUrl *
0x1800161b1  mov     rcx, rsi; this
0x1800161b4  call    ?IsAttachmentOK@CMapi2Accessor@@QEAAJAEAVCMapiUrl@@@Z; CMapi2Accessor::IsAttachmentOK(CMapiUrl &)
0x1800161b9  test    eax, eax
0x1800161bb  jz      short loc_1800161DC
0x1800161bd  mov     r8, r15
0x1800161c0  lea     rdx, aCmapi2accessor_2; "CMapi2Accessor::Init() blocked url %s"
0x1800161c7  mov     ecx, eax; int
0x1800161c9  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x1800161ce  mov     edi, 80040D07h
0x1800161d3  lea     rcx, [rbp+4390h+var_41E0]
0x1800161da  jmp     short loc_180016244
0x1800161dc  lea     rcx, [rbp+4390h+var_41E0]
0x1800161e3  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x1800161e8  lea     rdx, [rbp+4390h+var_4400]
0x1800161ec  lea     rcx, [rsp+4490h+var_4458]
0x1800161f1  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800161f6  nop
0x1800161f7  mov     rbx, [rsp+4490h+var_4458]
0x1800161fc  mov     rdx, rbx
0x1800161ff  lea     rcx, [rbp+4390h+var_4380]
0x180016203  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(wchar_t const *)
0x180016208  nop
0x180016209  lea     rcx, [rbx-18h]; this
0x18001620d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016212  mov     [rsp+4490h+var_4460], 0
0x18001621b  lea     rcx, [rsp+4490h+var_4460]
0x180016220  cmp     [rbp+4390h+var_436C], 0
0x180016224  jnz     loc_180016343
0x18001622a  mov     qword ptr [rsi+6F8h], 1
0x180016235  call    ?CreateInstance@?$CComObject@VCMapi2DirFilter@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMapi2DirFilter>::CreateInstance(ATL::CComObject<CMapi2DirFilter> * *)
0x18001623a  mov     edi, eax
0x18001623c  test    eax, eax
0x18001623e  jns     short loc_18001624E
0x180016240  lea     rcx, [rbp+4390h+var_4380]
0x180016244  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x180016249  jmp     loc_1800165D7
0x18001624e  mov     rbx, [rsp+4490h+var_4460]
0x180016253  mov     [rsp+4490h+var_4460], rbx
0x180016258  test    rbx, rbx
0x18001625b  jz      short loc_18001626D
0x18001625d  mov     rax, [rbx]
0x180016260  mov     rcx, rbx
0x180016263  mov     rax, [rax+8]
0x180016267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001626c  nop
0x18001626d  mov     rax, [rbx]
0x180016270  lea     r8, [rsi+58h]
0x180016274  lea     rdx, IID_IFilter
0x18001627b  mov     rcx, rbx
0x18001627e  mov     rax, [rax]
0x180016281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016286  mov     edi, eax
0x180016288  test    eax, eax
0x18001628a  jns     short loc_180016298
0x18001628c  lea     rcx, [rsp+4490h+var_4460]
0x180016291  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x180016296  jmp     short loc_180016240
0x180016298  mov     r9d, r14d; unsigned int
0x18001629b  mov     r8, r12; struct _FILETIME *
0x18001629e  mov     rdx, rsi; struct CMapi2Accessor *
0x1800162a1  mov     rcx, rbx; this
0x1800162a4  call    ?InitDirFilter@CMapi2DirFilter@@QEAAJPEAVCMapi2Accessor@@AEBU_FILETIME@@K@Z; CMapi2DirFilter::InitDirFilter(CMapi2Accessor *,_FILETIME const &,ulong)
0x1800162a9  mov     r14d, eax
0x1800162ac  test    eax, eax
0x1800162ae  jns     short loc_1800162E8
0x1800162b0  lea     rdx, aInitdirfilterF; "InitDirFilter failed"
0x1800162b7  mov     ecx, eax; int
0x1800162b9  call    ?Warning@CLogger@@SAXJPEB_WZZ; CLogger::Warning(long,wchar_t const *,...)
0x1800162be  lea     ecx, [r14+7FFBFEF9h]
0x1800162c5  test    ecx, 0FFFFFFF7h
0x1800162cb  jnz     short loc_180016334
0x1800162cd  mov     edi, 80041201h
0x1800162d2  mov     r14d, edi
0x1800162d5  mov     r8, r15
0x1800162d8  lea     rdx, aInitdirfilterU; "InitDirFilter url (%s) and children wil"...
0x1800162df  mov     ecx, edi; int
0x1800162e1  call    ?Warning@CLogger@@SAXJPEB_WZZ; CLogger::Warning(long,wchar_t const *,...)
0x1800162e6  jmp     short loc_180016334
0x1800162e8  mov     edi, 41203h
0x1800162ed  cmp     r14d, edi
0x1800162f0  jz      short loc_18001628C
0x1800162f2  lea     rcx, [rsi+48h]; lpSystemTimeAsFileTime
0x1800162f6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800162fc  lea     r8, [rbp+4390h+var_4040]; wchar_t *
0x180016303  xor     edx, edx; int
0x180016305  mov     rcx, rbx; this
0x180016308  call    ?GetItemPathDisplay@CMapi2DirFilter@@QEAAJHPEA_WK@Z; CMapi2DirFilter::GetItemPathDisplay(int,wchar_t *,ulong)
0x18001630d  lea     rcx, [rsi+218h]
0x180016314  lea     rdx, [rbp+4390h+var_4040]
0x18001631b  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180016320  lea     rcx, [rsi+3B8h]
0x180016327  lea     rdx, aMapiIpmFolder; "MAPI/IPM.Folder"
0x18001632e  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180016333  nop
0x180016334  lea     rcx, [rsp+4490h+var_4460]
0x180016339  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x18001633e  jmp     loc_1800165CB
0x180016343  mov     [rsi+6FCh], edi
0x180016349  call    ?CreateInstance@?$CComObject@VCMapi2RowFilter@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMapi2RowFilter>::CreateInstance(ATL::CComObject<CMapi2RowFilter> * *)
0x18001634e  mov     edi, eax
0x180016350  test    eax, eax
0x180016352  js      loc_180016240
0x180016358  mov     rdx, [rsp+4490h+var_4460]
0x18001635d  lea     rcx, [rsp+4490h+var_4460]
0x180016362  call    ??0?$TComNoUnkPointer@VCMapi2RowFilter@@@@QEAA@PEAVCMapi2RowFilter@@@Z; TComNoUnkPointer<CMapi2RowFilter>::TComNoUnkPointer<CMapi2RowFilter>(CMapi2RowFilter *)
0x180016367  nop
0x180016368  mov     rbx, [rsp+4490h+var_4460]
0x18001636d  mov     rax, [rbx]
0x180016370  lea     r8, [rsi+58h]
0x180016374  lea     rdx, IID_IFilter
0x18001637b  mov     rcx, rbx
0x18001637e  mov     rax, [rax]
0x180016381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016386  mov     edi, eax
0x180016388  test    eax, eax
0x18001638a  jns     short loc_18001639B
0x18001638c  lea     rcx, [rsp+4490h+var_4460]
0x180016391  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x180016396  jmp     loc_180016240
0x18001639b  xor     r8d, r8d; struct IMessage *
0x18001639e  mov     rdx, rsi; struct CMapi2Accessor *
0x1800163a1  mov     rcx, rbx; this
0x1800163a4  call    ?InitRowFilter@CMapi2RowFilter@@QEAAJPEAVCMapi2Accessor@@PEAUIMessage@@@Z; CMapi2RowFilter::InitRowFilter(CMapi2Accessor *,IMessage *)
0x1800163a9  mov     r14d, eax
0x1800163ac  mov     edi, 41203h
0x1800163b1  cmp     eax, edi
0x1800163b3  jz      short loc_18001638C
0x1800163b5  test    eax, eax
0x1800163b7  jns     short loc_1800163E1
0x1800163b9  lea     rdx, aInitrowfilterF_0; "InitRowFilter failed"
0x1800163c0  mov     ecx, eax; int
0x1800163c2  call    ?Warning@CLogger@@SAXJPEB_WZZ; CLogger::Warning(long,wchar_t const *,...)
0x1800163c7  lea     eax, [r14+7FFBFEF9h]
0x1800163ce  test    eax, 0FFFFFFF7h
0x1800163d3  mov     edi, 80041201h
0x1800163d8  cmovz   r14d, edi
0x1800163dc  mov     edi, r14d
0x1800163df  jmp     short loc_18001638C
0x1800163e1  mov     eax, [rbx+54A8h]
0x1800163e7  mov     [rsi+50h], eax
0x1800163ea  mov     eax, [rbx+54B4h]
0x1800163f0  mov     [rsi+48h], eax
0x1800163f3  mov     eax, [rbx+54B8h]
0x1800163f9  mov     [rsi+4Ch], eax
0x1800163fc  mov     r9d, 1000h; unsigned int
0x180016402  lea     r8, [rbp+4390h+var_2040]; wchar_t *
0x180016409  xor     edx, edx; int
0x18001640b  mov     rcx, rbx; this
0x18001640e  call    ?GetItemPathDisplay@CMapi2RowFilter@@QEAAJHPEA_WK@Z; CMapi2RowFilter::GetItemPathDisplay(int,wchar_t *,ulong)
0x180016413  lea     rcx, [rsi+218h]
0x18001641a  lea     rdx, [rbp+4390h+var_2040]
0x180016421  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180016426  lea     rdx, [rbx+2240h]
0x18001642d  lea     rcx, [rsi+558h]
0x180016434  call    ??4CLMString@@QEAAXAEBV0@@Z; CLMString::operator=(CLMString const &)
0x180016439  mov     rax, [rbp+4390h+var_43F8]
0x18001643d  lea     rdx, [rbp+4390h+var_2040]; wchar_t *
0x180016444  mov     rcx, rbx; this
0x180016447  cmp     dword ptr [rax-10h], 0
0x18001644b  jle     loc_180016597
0x180016451  lea     rdi, [rsi+3B8h]
0x180016458  mov     dword ptr [rsi+6F8h], 0
0x180016462  call    ?GetDocFormat@CMapi2RowFilter@@QEAAJPEA_WK@Z; CMapi2RowFilter::GetDocFormat(wchar_t *,ulong)
0x180016467  lea     rdx, [rbp+4390h+var_2040]
0x18001646e  mov     rcx, rdi
0x180016471  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180016476  lea     rdx, [rsp+4490h+var_4458]
0x18001647b  lea     rcx, [rsp+4490h+var_4440]
0x180016480  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x180016485  mov     rcx, [rax]
0x180016488  mov     ebx, [rcx-10h]
0x18001648b  mov     rcx, [rsp+4490h+var_4458]
0x180016490  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016494  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016499  test    ebx, ebx
0x18001649b  jle     loc_1800165C0
0x1800164a1  lea     rdx, dword_1800444C4
0x1800164a8  mov     rcx, rdi
0x1800164ab  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800164b0  lea     rdx, [rsp+4490h+var_4458]
0x1800164b5  lea     rcx, [rsp+4490h+var_4440]
0x1800164ba  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x1800164bf  mov     edx, 2Eh ; '.'
0x1800164c4  mov     rcx, rax
0x1800164c7  call    ?ReverseFind@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAH_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(wchar_t)
0x1800164cc  mov     ebx, eax
0x1800164ce  mov     rcx, [rsp+4490h+var_4458]
0x1800164d3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800164d7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800164dc  test    ebx, ebx
0x1800164de  jle     loc_1800165C0
0x1800164e4  lea     rdx, [rsp+4490h+var_4450]
0x1800164e9  lea     rcx, [rsp+4490h+var_4440]
0x1800164ee  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x1800164f3  nop
0x1800164f4  mov     r8d, ebx
0x1800164f7  lea     rdx, [rsp+4490h+var_4458]
0x1800164fc  mov     rcx, rax
0x1800164ff  call    ?Mid@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(int)
0x180016504  nop
0x180016505  mov     rdx, [rax]; wchar_t *
0x180016508  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18001650f  mov     [rbp+4390h+var_43E0], rax
0x180016513  lea     rax, [rbp+4390h+var_43C8]
0x180016517  mov     [rbp+4390h+var_43D8], rax
0x18001651b  mov     [rbp+4390h+var_43D0], 21h ; '!'
0x180016522  or      r8d, 0FFFFFFFFh; unsigned int
0x180016526  lea     rcx, [rbp+4390h+var_43E0]; this
0x18001652a  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x18001652f  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x180016536  mov     [rbp+4390h+var_43E0], rax
0x18001653a  mov     rcx, [rsp+4490h+var_4458]
0x18001653f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
  ... truncated ...
```
