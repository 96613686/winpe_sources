# CMFSourceFilter::Load(IMFByteStream *)

- ea: `0x180024710`
- end: `0x18002495d`
- name: `?Load@CMFSourceFilter@@UEAAJPEAUIMFByteStream@@@Z`
- size: `589`
- prototype: `int(CMFSourceFilter *__hidden this, struct IMFByteStream *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800227e0`
- `0x180023690`
- `0x180023c88`
- `0x180023f3c`
- `0x180024710`
- `0x180024964`
- `0x180024bcc`
- `0x180029550`
- `0x180074160`
- `0x1800928c8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800247fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800247fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024755`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024755`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x1800248a4`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x1800248a4`

## pseudocode

```c
__int64 __fastcall CMFSourceFilter::Load(CMFSourceFilter *this, struct IUnknown *a2)
{
  __int64 v5; // rcx
  int (__fastcall ***v6)(_QWORD, GUID *, char *); // rcx
  _QWORD *v7; // rdi
  struct _GUID *v8; // r8
  int MediaTypeStream; // edi
  __int64 v10; // rcx
  bool v11[4]; // [rsp+30h] [rbp-20h] BYREF
  int v12; // [rsp+34h] [rbp-1Ch] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v11[0] = 0;
  v12 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 56));
  v5 = *((_QWORD *)this - 11);
  if ( v5 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, 16, 1);
  v6 = (int (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this - 12);
  v7 = (_QWORD *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    if ( (**v6)(v6, &IID_IGraphBuilder, (char *)this + 48) >= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
    else
      *v7 = 0;
  }
  CMFSourceFilter::_ReleaseByteStream((CMFSourceFilter *)((char *)this - 192));
  if ( *((struct IUnknown **)this + 3) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 3, a2);
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 456) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this - 56));
  MediaTypeStream = CMFSourceFilter::_GetMediaTypeStream(
                      (CMFSourceFilter *)((char *)this - 192),
                      (CMFSourceFilter *)((char *)this + 1704),
                      v8,
                      v11,
                      (enum Mpeg2_TS_Flavor *)&v12);
  if ( MediaTypeStream >= 0 )
  {
    if ( (unsigned int)CMFSourceFilter::_ShouldUsePushMode((CMFSourceFilter *)((char *)this - 192)) )
    {
      *((_DWORD *)this + 14) = 1;
      ppBuffer = 0;
      if ( MFCreateAlignedMemoryBuffer(0x20000u, 0x1FFu, &ppBuffer) >= 0 )
        CMFSourceMPEG2TSPin::SetUseCircularBuffer(*((CMFSourceMPEG2TSPin **)this + 209), ppBuffer);
      if ( v11[0] )
        *(_DWORD *)(*((_QWORD *)this + 209) + 456LL) = v12;
      MediaTypeStream = CBasePin::SetMediaType(
                          (CBasePin *)(*((_QWORD *)this + 209) + 120LL),
                          (CMFSourceFilter *)((char *)this + 1704));
      ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppBuffer);
    }
    else
    {
      MediaTypeStream = (*(__int64 (__fastcall **)(char *, char *))(*((_QWORD *)this + 9) + 72LL))(
                          (char *)this + 72,
                          (char *)this + 1704);
    }
    if ( MediaTypeStream >= 0 )
      goto LABEL_24;
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v11, "CMFSourceFilter::Load", 5353);
    if ( (unsigned __int8)byte_1800EACCB >= 8u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        92,
        &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids,
        (unsigned int)MediaTypeStream);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v11);
  }
  CMFSourceFilter::_ReleaseByteStream((CMFSourceFilter *)((char *)this - 192));
LABEL_24:
  v10 = *((_QWORD *)this - 11);
  if ( v10 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v10 + 24LL))(v10, 16, 0);
  return (unsigned int)MediaTypeStream;
}

```

## disassembly

```asm
0x180024710  mov     [rsp-28h+arg_10], rbx
0x180024715  push    rbp
0x180024716  push    rsi
0x180024717  push    rdi
0x180024718  push    r14
0x18002471a  push    r15
0x18002471c  mov     rbp, rsp
0x18002471f  sub     rsp, 50h
0x180024723  mov     rax, cs:__security_cookie
0x18002472a  xor     rax, rsp
0x18002472d  mov     [rbp+var_10], rax
0x180024731  mov     r14, rdx
0x180024734  mov     rbx, rcx
0x180024737  test    rdx, rdx
0x18002473a  jnz     short loc_180024746
0x18002473c  mov     eax, 80004003h
0x180024741  jmp     loc_18002493C
0x180024746  add     rcx, 0FFFFFFFFFFFFFFC8h; lpCriticalSection
0x18002474a  mov     [rbp+var_20], 0
0x18002474e  mov     [rbp+var_1C], 0
0x180024755  call    cs:__imp_EnterCriticalSection
0x18002475c  nop     dword ptr [rax+rax+00h]
0x180024761  lea     rsi, [rbx-0C0h]
0x180024768  mov     rcx, [rsi+68h]
0x18002476c  test    rcx, rcx
0x18002476f  jz      short loc_180024788
0x180024771  mov     rax, [rcx]
0x180024774  xor     r9d, r9d
0x180024777  mov     rax, [rax+18h]
0x18002477b  lea     edx, [r9+10h]
0x18002477f  lea     r8d, [r9+1]
0x180024783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024788  mov     rcx, [rbx-60h]
0x18002478c  lea     rdi, [rbx+30h]
0x180024790  mov     qword ptr [rdi], 0
0x180024797  test    rcx, rcx
0x18002479a  jz      short loc_1800247CD
0x18002479c  mov     rax, [rcx]
0x18002479f  lea     rdx, IID_IGraphBuilder
0x1800247a6  mov     r8, rdi
0x1800247a9  mov     rax, [rax]
0x1800247ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247b1  test    eax, eax
0x1800247b3  jns     short loc_1800247BE
0x1800247b5  mov     qword ptr [rdi], 0
0x1800247bc  jmp     short loc_1800247CD
0x1800247be  mov     rcx, [rdi]
0x1800247c1  mov     rax, [rcx]
0x1800247c4  mov     rax, [rax+10h]
0x1800247c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247cd  mov     rcx, rsi; this
0x1800247d0  call    ?_ReleaseByteStream@CMFSourceFilter@@QEAAXXZ; CMFSourceFilter::_ReleaseByteStream(void)
0x1800247d5  lea     rcx, [rbx+18h]; struct IUnknown **
0x1800247d9  cmp     [rcx], r14
0x1800247dc  jz      short loc_1800247E6
0x1800247de  mov     rdx, r14; struct IUnknown *
0x1800247e1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800247e6  lea     rcx, [rbx-38h]; lpCriticalSection
0x1800247ea  mov     dword ptr [rbx+10h], 0
0x1800247f1  mov     dword ptr [rbx+720h], 0
0x1800247fb  call    cs:__imp_LeaveCriticalSection
0x180024802  nop     dword ptr [rax+rax+00h]
0x180024807  lea     rax, [rbp+var_1C]
0x18002480b  mov     rcx, rsi; this
0x18002480e  lea     r14, [rbx+6A8h]
0x180024815  mov     [rsp+50h+var_30], rax; enum Mpeg2_TS_Flavor *
0x18002481a  mov     rdx, r14; struct CMediaType *
0x18002481d  lea     r9, [rbp+var_20]; bool *
0x180024821  call    ?_GetMediaTypeStream@CMFSourceFilter@@QEAAJPEAVCMediaType@@PEAU_GUID@@PEA_NPEAW4Mpeg2_TS_Flavor@@@Z; CMFSourceFilter::_GetMediaTypeStream(CMediaType *,_GUID *,bool *,Mpeg2_TS_Flavor *)
0x180024826  mov     edi, eax
0x180024828  test    eax, eax
0x18002482a  jns     short loc_18002487B
0x18002482c  mov     r8d, 14E9h; int
0x180024832  lea     rdx, aCmfsourcefilte_1; "CMFSourceFilter::Load"
0x180024839  lea     rcx, [rbp+var_20]; this
0x18002483d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180024842  cmp     cs:byte_1800EACCB, 8
0x180024849  jb      short loc_18002486D
0x18002484b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024852  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x180024859  mov     edx, 5Ch ; '\'
0x18002485e  mov     r9d, edi
0x180024861  mov     rcx, [rcx+88h]
0x180024868  call    WPP_SF_d
0x18002486d  lea     rcx, [rbp+var_20]; this
0x180024871  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180024876  jmp     loc_180024913
0x18002487b  mov     rcx, rsi; this
0x18002487e  call    ?_ShouldUsePushMode@CMFSourceFilter@@QEAAHXZ; CMFSourceFilter::_ShouldUsePushMode(void)
0x180024883  test    eax, eax
0x180024885  jz      short loc_1800248FA
0x180024887  lea     r8, [rbp+ppBuffer]; ppBuffer
0x18002488b  mov     dword ptr [rbx+38h], 1
0x180024892  mov     edx, 1FFh; cbAligment
0x180024897  mov     [rbp+ppBuffer], 0
0x18002489f  mov     ecx, 20000h; cbMaxLength
0x1800248a4  call    cs:__imp_MFCreateAlignedMemoryBuffer
0x1800248ab  nop     dword ptr [rax+rax+00h]
0x1800248b0  test    eax, eax
0x1800248b2  js      short loc_1800248C4
0x1800248b4  mov     rdx, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x1800248b8  mov     rcx, [rbx+688h]; this
0x1800248bf  call    ?SetUseCircularBuffer@CMFSourceMPEG2TSPin@@QEAAXPEAUIMFMediaBuffer@@@Z; CMFSourceMPEG2TSPin::SetUseCircularBuffer(IMFMediaBuffer *)
0x1800248c4  cmp     [rbp+var_20], 0
0x1800248c8  jz      short loc_1800248DA
0x1800248ca  mov     rcx, [rbx+688h]
0x1800248d1  mov     eax, [rbp+var_1C]
0x1800248d4  mov     [rcx+1C8h], eax
0x1800248da  mov     rcx, [rbx+688h]
0x1800248e1  mov     rdx, r14; struct CMediaType *
0x1800248e4  add     rcx, 78h ; 'x'; this
0x1800248e8  call    ?SetMediaType@CBasePin@@UEAAJPEBVCMediaType@@@Z; CBasePin::SetMediaType(CMediaType const *)
0x1800248ed  lea     rcx, [rbp+ppBuffer]; void *
0x1800248f1  mov     edi, eax
0x1800248f3  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x1800248f8  jmp     short loc_18002490F
0x1800248fa  lea     rcx, [rbx+48h]
0x1800248fe  mov     rdx, r14
0x180024901  mov     rax, [rcx]
0x180024904  mov     rax, [rax+48h]
0x180024908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002490d  mov     edi, eax
0x18002490f  test    edi, edi
0x180024911  jns     short loc_18002491B
0x180024913  mov     rcx, rsi; this
0x180024916  call    ?_ReleaseByteStream@CMFSourceFilter@@QEAAXXZ; CMFSourceFilter::_ReleaseByteStream(void)
0x18002491b  mov     rcx, [rbx-58h]
0x18002491f  test    rcx, rcx
0x180024922  jz      short loc_18002493A
0x180024924  mov     rax, [rcx]
0x180024927  xor     r9d, r9d
0x18002492a  xor     r8d, r8d
0x18002492d  mov     rax, [rax+18h]
0x180024931  lea     edx, [r9+10h]
0x180024935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002493a  mov     eax, edi
0x18002493c  mov     rcx, [rbp+var_10]
0x180024940  xor     rcx, rsp; StackCookie
0x180024943  call    __security_check_cookie
0x180024948  mov     rbx, [rsp+50h+arg_10]
0x180024950  add     rsp, 50h
0x180024954  pop     r15
0x180024956  pop     r14
0x180024958  pop     rdi
0x180024959  pop     rsi
0x18002495a  pop     rbp
0x18002495b  retn
```
