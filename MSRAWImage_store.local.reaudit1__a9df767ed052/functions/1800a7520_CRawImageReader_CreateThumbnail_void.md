# CRawImageReader::CreateThumbnail(void)

- ea: `0x1800a7520`
- end: `0x1800a7b22`
- name: `?CreateThumbnail@CRawImageReader@@AEAAJXZ`
- size: `1538`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800ab5b0`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a4024`
- `0x1800a7520`
- `0x1800a7b28`
- `0x1800a7f98`
- `0x1800a8588`
- `0x1800a8df0`
- `0x1800b4010`

## string_xrefs

- `0x1800a7562`: `CRawImageReader::CreateThumbnail`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRawImageReader::CreateThumbnail(CRawImageReader *this)
{
  int *v2; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  unsigned int *v5; // r14
  int ThumbnailFromBitmapSource; // ebx
  void ***v7; // rcx
  struct CallStackContext *v8; // rax
  int v9; // r8d
  __int64 v10; // rcx
  void ***v11; // rcx
  void ***v12; // rcx
  int v13; // r15d
  void ***v14; // rcx
  struct CallStackContext *v15; // rax
  int v16; // r8d
  struct IWICImagingFactory *v17; // rbx
  HRESULT (__stdcall *CreateBitmapFromMemory)(IWICImagingFactory *, UINT, UINT, REFWICPixelFormatGUID, UINT, UINT, BYTE *, IWICBitmap **); // rdi
  void ***v19; // rcx
  void ***v20; // rcx
  struct CallStackContext *v21; // rax
  int v22; // r8d
  void ***v23; // rcx
  int v25; // [rsp+28h] [rbp-59h]
  _BYTE v26[8]; // [rsp+58h] [rbp-29h] BYREF
  struct IWICImagingFactory *v27; // [rsp+60h] [rbp-21h] BYREF
  __int64 v28; // [rsp+68h] [rbp-19h] BYREF
  unsigned int v29; // [rsp+70h] [rbp-11h] BYREF
  unsigned int v30; // [rsp+74h] [rbp-Dh] BYREF
  __int64 v31; // [rsp+78h] [rbp-9h]
  _BYTE v32[32]; // [rsp+80h] [rbp-1h] BYREF
  struct IWICBitmapSource *v33[2]; // [rsp+A0h] [rbp+1Fh] BYREF

  v31 = -2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v26, "CRawImageReader::CreateThumbnail", 1501);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, struct IWICBitmapSource **))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v33);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
  }
  v5 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v32,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::CreateThumbnail",
    v2,
    v25);
  ThumbnailFromBitmapSource = CRawImageReader::DecodePreview(this);
  if ( ThumbnailFromBitmapSource < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *v5,
        ThumbnailFromBitmapSource);
    }
    v7 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v8 + 499) != ThumbnailFromBitmapSource )
      {
        v9 = 1502;
LABEL_14:
        CallStackContext::TraceFailure(v8, "CRawImageReader::CreateThumbnail", v9, ThumbnailFromBitmapSource);
        goto LABEL_82;
      }
    }
    goto LABEL_82;
  }
  v10 = *((_QWORD *)this + 29);
  if ( !v10
    || (v30 = 0,
        v29 = 0,
        (*(void (__fastcall **)(__int64, unsigned int *, unsigned int *))(*(_QWORD *)v10 + 24LL))(v10, &v30, &v29),
        v30 > v29 != *((_DWORD *)this + 28) > *((_DWORD *)this + 29)) )
  {
    ThumbnailFromBitmapSource = CRawImageReader::DecodeImage(this);
    if ( ThumbnailFromBitmapSource < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          131,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v5,
          ThumbnailFromBitmapSource);
      }
      v12 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v8 + 499) != ThumbnailFromBitmapSource )
        {
          v9 = 1517;
          goto LABEL_14;
        }
      }
      goto LABEL_82;
    }
    v13 = 3 * *(unsigned __int16 *)(*((_QWORD *)this + 17) + 6LL);
    v28 = 0;
    v27 = 0;
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v27);
    ThumbnailFromBitmapSource = CRawImageReader::CreateWICFactory(this, &v27);
    if ( ThumbnailFromBitmapSource < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          133,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v5,
          ThumbnailFromBitmapSource);
      }
      v14 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v14 + 8) )
        goto LABEL_81;
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v15 + 499) == ThumbnailFromBitmapSource )
        goto LABEL_81;
      v16 = 1524;
      goto LABEL_48;
    }
    v17 = v27;
    CreateBitmapFromMemory = v27->lpVtbl->CreateBitmapFromMemory;
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v28);
    ThumbnailFromBitmapSource = ((__int64 (__fastcall *)(struct IWICImagingFactory *, _QWORD, _QWORD, GUID *, int, _DWORD, __int64, __int64 *))CreateBitmapFromMemory)(
                                  v17,
                                  *(unsigned __int16 *)(*((_QWORD *)this + 17) + 6LL),
                                  *(unsigned __int16 *)(*((_QWORD *)this + 17) + 4LL),
                                  &GUID_WICPixelFormat24bppRGB,
                                  v13,
                                  *(_DWORD *)(*((_QWORD *)this + 17) + 12LL),
                                  *((_QWORD *)this + 17) + 16LL,
                                  &v28);
    if ( ThumbnailFromBitmapSource < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v5,
          ThumbnailFromBitmapSource);
      }
      v19 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v19 + 8) )
        goto LABEL_81;
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v15 + 499) == ThumbnailFromBitmapSource )
        goto LABEL_81;
      v16 = 1525;
LABEL_48:
      CallStackContext::TraceFailure(v15, "CRawImageReader::CreateThumbnail", v16, ThumbnailFromBitmapSource);
LABEL_81:
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v28);
      goto LABEL_82;
    }
    v33[0] = 0;
    ThumbnailFromBitmapSource = Microsoft::WRL::ComPtr<IWICBitmap>::As<IWICBitmapSource>(&v28, v33);
    if ( ThumbnailFromBitmapSource >= 0 )
    {
      ThumbnailFromBitmapSource = CRawImageReader::CreateThumbnailFromBitmapSource(this, v33[0]);
      if ( ThumbnailFromBitmapSource >= 0 )
        goto LABEL_80;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          136,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v5,
          ThumbnailFromBitmapSource);
      }
      v23 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v23 + 8) )
        goto LABEL_80;
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v21 + 499) == ThumbnailFromBitmapSource )
        goto LABEL_80;
      v22 = 1530;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v5,
          ThumbnailFromBitmapSource);
      }
      v20 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v20 + 8) )
        goto LABEL_80;
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v21 + 499) == ThumbnailFromBitmapSource )
        goto LABEL_80;
      v22 = 1527;
    }
    CallStackContext::TraceFailure(v21, "CRawImageReader::CreateThumbnail", v22, ThumbnailFromBitmapSource);
LABEL_80:
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v33);
    goto LABEL_81;
  }
  ThumbnailFromBitmapSource = CRawImageReader::CreateThumbnailFromBitmapSource(
                                this,
                                *((struct IWICBitmapSource **)this + 29));
  if ( ThumbnailFromBitmapSource >= 0 )
  {
    ThumbnailFromBitmapSource = 0;
    goto LABEL_82;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      130,
      &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
      *v5,
      ThumbnailFromBitmapSource);
  }
  v11 = (void ***)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v11 = &off_1800E5190;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v8 + 499) != ThumbnailFromBitmapSource )
    {
      v9 = 1511;
      goto LABEL_14;
    }
  }
LABEL_82:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v32);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v26);
  return (unsigned int)ThumbnailFromBitmapSource;
}

```

## disassembly

```asm
0x1800a7520  mov     rax, rsp
0x1800a7523  push    rbp
0x1800a7524  push    r12
0x1800a7526  push    r13
0x1800a7528  push    r14
0x1800a752a  push    r15
0x1800a752c  lea     rbp, [rax-5Fh]
0x1800a7530  sub     rsp, 0B0h
0x1800a7537  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x1800a753f  mov     [rax+10h], rbx
0x1800a7543  mov     [rax+18h], rsi
0x1800a7547  mov     [rax+20h], rdi
0x1800a754b  mov     rax, cs:__security_cookie
0x1800a7552  xor     rax, rsp
0x1800a7555  mov     [rbp+57h+var_28], rax
0x1800a7559  mov     rsi, rcx
0x1800a755c  mov     r8d, 5DDh; int
0x1800a7562  lea     r13, aCrawimagereade_3; "CRawImageReader::CreateThumbnail"
0x1800a7569  mov     rdx, r13; char *
0x1800a756c  lea     rcx, [rbp+57h+var_80]; this
0x1800a7570  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a7575  nop
0x1800a7576  xor     r12d, r12d
0x1800a7579  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a7580  cmp     [rcx+8], r12b
0x1800a7584  jz      short loc_1800A75E0
0x1800a7586  cmp     [rsi+110h], r12
0x1800a758d  jz      short loc_1800A75E0
0x1800a758f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7594  mov     rdi, rax
0x1800a7597  mov     rdx, [rsi+110h]
0x1800a759e  mov     rcx, [rdx]
0x1800a75a1  mov     rax, [rcx+128h]
0x1800a75a8  mov     rcx, rdx
0x1800a75ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a75b0  mov     ebx, eax
0x1800a75b2  mov     r8, [rsi+110h]
0x1800a75b9  mov     rcx, [r8]
0x1800a75bc  mov     rax, [rcx+118h]
0x1800a75c3  lea     rdx, [rbp+57h+var_38]
0x1800a75c7  mov     rcx, r8
0x1800a75ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a75cf  movups  xmm0, xmmword ptr [rax]
0x1800a75d2  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a75da  mov     [rdi+7E0h], ebx
0x1800a75e0  lea     r14, [rsi+38h]
0x1800a75e4  mov     rax, rsi
0x1800a75e7  neg     rax
0x1800a75ea  sbb     rdx, rdx
0x1800a75ed  and     rdx, r14; struct CTraceBase *
0x1800a75f0  mov     r8, r13; char *
0x1800a75f3  lea     rcx, [rbp+57h+var_58]; this
0x1800a75f7  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a75fc  nop
0x1800a75fd  mov     rcx, rsi; this
0x1800a7600  call    ?DecodePreview@CRawImageReader@@AEAAJXZ; CRawImageReader::DecodePreview(void)
0x1800a7605  mov     ebx, eax
0x1800a7607  test    eax, eax
0x1800a7609  jns     loc_1800A7698
0x1800a760f  lea     rax, WPP_GLOBAL_Control
0x1800a7616  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a761d  cmp     rcx, rax
0x1800a7620  jz      short loc_1800A764A
0x1800a7622  test    byte ptr [rcx+1Ch], 1
0x1800a7626  jz      short loc_1800A764A
0x1800a7628  cmp     byte ptr [rcx+19h], 4
0x1800a762c  jb      short loc_1800A764A
0x1800a762e  mov     edx, 81h
0x1800a7633  mov     [rsp+0D0h+var_B0], ebx
0x1800a7637  mov     r9d, [r14]
0x1800a763a  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a7641  mov     rcx, [rcx+10h]
0x1800a7645  call    WPP_SF_Dd
0x1800a764a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7651  test    rcx, rcx
0x1800a7654  jnz     short loc_1800A7664
0x1800a7656  lea     rcx, off_1800E5190; this
0x1800a765d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7664  cmp     [rcx+8], r12b
0x1800a7668  jz      loc_1800A7ADF
0x1800a766e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7673  cmp     [rax+7CCh], ebx
0x1800a7679  jz      loc_1800A7ADF
0x1800a767f  mov     r8d, 5DEh; int
0x1800a7685  mov     r9d, ebx; int
0x1800a7688  mov     rdx, r13; char *
0x1800a768b  mov     rcx, rax; this
0x1800a768e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a7693  jmp     loc_1800A7ADF
0x1800a7698  mov     rcx, [rsi+0E8h]
0x1800a769f  test    rcx, rcx
0x1800a76a2  jz      loc_1800A777E
0x1800a76a8  mov     [rbp+57h+var_64], r12d
0x1800a76ac  mov     [rbp+57h+var_68], r12d
0x1800a76b0  mov     rax, [rcx]
0x1800a76b3  lea     r8, [rbp+57h+var_68]
0x1800a76b7  lea     rdx, [rbp+57h+var_64]
0x1800a76bb  mov     rax, [rax+18h]
0x1800a76bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a76c4  mov     r8d, r12d
0x1800a76c7  mov     eax, [rbp+57h+var_68]
0x1800a76ca  cmp     [rbp+57h+var_64], eax
0x1800a76cd  setnbe  r8b
0x1800a76d1  mov     edx, r12d
0x1800a76d4  mov     eax, [rsi+74h]
0x1800a76d7  cmp     [rsi+70h], eax
0x1800a76da  setnle  dl
0x1800a76dd  cmp     r8d, edx
0x1800a76e0  jnz     loc_1800A777E
0x1800a76e6  mov     rdx, [rsi+0E8h]; struct IWICBitmapSource *
0x1800a76ed  mov     rcx, rsi; this
0x1800a76f0  call    ?CreateThumbnailFromBitmapSource@CRawImageReader@@AEAAJPEAUIWICBitmapSource@@@Z; CRawImageReader::CreateThumbnailFromBitmapSource(IWICBitmapSource *)
0x1800a76f5  mov     ebx, eax
0x1800a76f7  test    eax, eax
0x1800a76f9  jns     short loc_1800A7776
0x1800a76fb  lea     rax, WPP_GLOBAL_Control
0x1800a7702  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7709  cmp     rcx, rax
0x1800a770c  jz      short loc_1800A7736
0x1800a770e  test    byte ptr [rcx+1Ch], 1
0x1800a7712  jz      short loc_1800A7736
0x1800a7714  cmp     byte ptr [rcx+19h], 4
0x1800a7718  jb      short loc_1800A7736
0x1800a771a  mov     edx, 82h
0x1800a771f  mov     [rsp+0D0h+var_B0], ebx
0x1800a7723  mov     r9d, [r14]
0x1800a7726  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a772d  mov     rcx, [rcx+10h]
0x1800a7731  call    WPP_SF_Dd
0x1800a7736  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a773d  test    rcx, rcx
0x1800a7740  jnz     short loc_1800A7750
0x1800a7742  lea     rcx, off_1800E5190; this
0x1800a7749  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7750  cmp     [rcx+8], r12b
0x1800a7754  jz      loc_1800A7ADF
0x1800a775a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a775f  cmp     [rax+7CCh], ebx
0x1800a7765  jz      loc_1800A7ADF
0x1800a776b  mov     r8d, 5E7h
0x1800a7771  jmp     loc_1800A7685
0x1800a7776  mov     ebx, r12d
0x1800a7779  jmp     loc_1800A7ADF
0x1800a777e  mov     rcx, rsi; this
0x1800a7781  call    ?DecodeImage@CRawImageReader@@AEAAJXZ; CRawImageReader::DecodeImage(void)
0x1800a7786  mov     ebx, eax
0x1800a7788  test    eax, eax
0x1800a778a  jns     short loc_1800A7807
0x1800a778c  lea     rax, WPP_GLOBAL_Control
0x1800a7793  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a779a  cmp     rcx, rax
0x1800a779d  jz      short loc_1800A77C7
0x1800a779f  test    byte ptr [rcx+1Ch], 1
0x1800a77a3  jz      short loc_1800A77C7
0x1800a77a5  cmp     byte ptr [rcx+19h], 4
0x1800a77a9  jb      short loc_1800A77C7
0x1800a77ab  mov     edx, 83h
0x1800a77b0  mov     [rsp+0D0h+var_B0], ebx
0x1800a77b4  mov     r9d, [r14]
0x1800a77b7  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a77be  mov     rcx, [rcx+10h]
0x1800a77c2  call    WPP_SF_Dd
0x1800a77c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a77ce  test    rcx, rcx
0x1800a77d1  jnz     short loc_1800A77E1
0x1800a77d3  lea     rcx, off_1800E5190; this
0x1800a77da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a77e1  cmp     [rcx+8], r12b
0x1800a77e5  jz      loc_1800A7ADF
0x1800a77eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a77f0  cmp     [rax+7CCh], ebx
0x1800a77f6  jz      loc_1800A7ADF
0x1800a77fc  mov     r8d, 5EDh
0x1800a7802  jmp     loc_1800A7685
0x1800a7807  mov     rax, [rsi+88h]
0x1800a780e  movzx   ecx, word ptr [rax+6]
0x1800a7812  lea     r15d, [rcx+rcx*2]
0x1800a7816  mov     [rbp+57h+var_70], r12
0x1800a781a  mov     [rbp+57h+var_78], r12
0x1800a781e  lea     rcx, [rbp+57h+var_78]
0x1800a7822  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a7827  lea     rdx, [rbp+57h+var_78]; struct IWICImagingFactory **
0x1800a782b  mov     rcx, rsi; this
0x1800a782e  call    ?CreateWICFactory@CRawImageReader@@AEAAJPEAPEAUIWICImagingFactory@@@Z; CRawImageReader::CreateWICFactory(IWICImagingFactory * *)
0x1800a7833  mov     ebx, eax
0x1800a7835  test    eax, eax
0x1800a7837  jns     loc_1800A78C6
0x1800a783d  lea     rax, WPP_GLOBAL_Control
0x1800a7844  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a784b  cmp     rcx, rax
0x1800a784e  jz      short loc_1800A7878
0x1800a7850  test    byte ptr [rcx+1Ch], 1
0x1800a7854  jz      short loc_1800A7878
0x1800a7856  cmp     byte ptr [rcx+19h], 4
0x1800a785a  jb      short loc_1800A7878
0x1800a785c  mov     edx, 85h
0x1800a7861  mov     [rsp+0D0h+var_B0], ebx
0x1800a7865  mov     r9d, [r14]
0x1800a7868  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a786f  mov     rcx, [rcx+10h]
0x1800a7873  call    WPP_SF_Dd
0x1800a7878  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a787f  test    rcx, rcx
0x1800a7882  jnz     short loc_1800A7892
0x1800a7884  lea     rcx, off_1800E5190; this
0x1800a788b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7892  cmp     [rcx+8], r12b
0x1800a7896  jz      loc_1800A7ACB
0x1800a789c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a78a1  cmp     [rax+7CCh], ebx
0x1800a78a7  jz      loc_1800A7ACB
0x1800a78ad  mov     r8d, 5F4h; int
0x1800a78b3  mov     r9d, ebx; int
0x1800a78b6  mov     rdx, r13; char *
0x1800a78b9  mov     rcx, rax; this
0x1800a78bc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a78c1  jmp     loc_1800A7ACB
0x1800a78c6  mov     rbx, [rbp+57h+var_78]
0x1800a78ca  mov     rax, [rbx]
0x1800a78cd  mov     rdi, [rax+0A0h]
0x1800a78d4  lea     rcx, [rbp+57h+var_70]
0x1800a78d8  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a78dd  mov     r9, [rsi+88h]
0x1800a78e4  lea     rcx, [r9+10h]
0x1800a78e8  movzx   r8d, word ptr [r9+4]
0x1800a78ed  movzx   edx, word ptr [r9+6]
0x1800a78f2  lea     rax, [rbp+57h+var_70]
0x1800a78f6  mov     [rsp+0D0h+var_98], rax
0x1800a78fb  mov     [rsp+0D0h+var_A0], rcx
0x1800a7900  mov     ecx, [r9+0Ch]
0x1800a7904  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x1800a7908  mov     [rsp+0D0h+var_B0], r15d
0x1800a790d  lea     r9, GUID_WICPixelFormat24bppRGB
0x1800a7914  mov     rcx, rbx
0x1800a7917  mov     rax, rdi
0x1800a791a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a791f  mov     ebx, eax
0x1800a7921  test    eax, eax
0x1800a7923  jns     short loc_1800A79A0
0x1800a7925  lea     rax, WPP_GLOBAL_Control
0x1800a792c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7933  cmp     rcx, rax
0x1800a7936  jz      short loc_1800A7960
0x1800a7938  test    byte ptr [rcx+1Ch], 1
0x1800a793c  jz      short loc_1800A7960
0x1800a793e  cmp     byte ptr [rcx+19h], 4
0x1800a7942  jb      short loc_1800A7960
0x1800a7944  mov     edx, 86h
0x1800a7949  mov     [rsp+0D0h+var_B0], ebx
0x1800a794d  mov     r9d, [r14]
0x1800a7950  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a7957  mov     rcx, [rcx+10h]
0x1800a795b  call    WPP_SF_Dd
0x1800a7960  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7967  test    rcx, rcx
0x1800a796a  jnz     short loc_1800A797A
0x1800a796c  lea     rcx, off_1800E5190; this
0x1800a7973  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a797a  cmp     [rcx+8], r12b
0x1800a797e  jz      loc_1800A7ACB
0x1800a7984  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7989  cmp     [rax+7CCh], ebx
0x1800a798f  jz      loc_1800A7ACB
0x1800a7995  mov     r8d, 5F5h
0x1800a799b  jmp     loc_1800A78B3
0x1800a79a0  mov     [rbp+57h+var_38], r12
0x1800a79a4  lea     rdx, [rbp+57h+var_38]
0x1800a79a8  lea     rcx, [rbp+57h+var_70]
0x1800a79ac  call    ??$As@UIWICBitmapSource@@@?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWICBitmap>::As<IWICBitmapSource>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWICBitmapSource>>)
0x1800a79b1  mov     ebx, eax
0x1800a79b3  test    eax, eax
0x1800a79b5  jns     short loc_1800A7A32
0x1800a79b7  lea     rax, WPP_GLOBAL_Control
0x1800a79be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a79c5  cmp     rcx, rax
0x1800a79c8  jz      short loc_1800A79F2
0x1800a79ca  test    byte ptr [rcx+1Ch], 1
0x1800a79ce  jz      short loc_1800A79F2
0x1800a79d0  cmp     byte ptr [rcx+19h], 4
0x1800a79d4  jb      short loc_1800A79F2
0x1800a79d6  mov     edx, 87h
0x1800a79db  mov     [rsp+0D0h+var_B0], ebx
0x1800a79df  mov     r9d, [r14]
0x1800a79e2  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a79e9  mov     rcx, [rcx+10h]
0x1800a79ed  call    WPP_SF_Dd
0x1800a79f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a79f9  test    rcx, rcx
0x1800a79fc  jnz     short loc_1800A7A0C
0x1800a79fe  lea     rcx, off_1800E5190; this
0x1800a7a05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7a0c  cmp     [rcx+8], r12b
0x1800a7a10  jz      loc_1800A7AC1
0x1800a7a16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7a1b  cmp     [rax+7CCh], ebx
0x1800a7a21  jz      loc_1800A7AC1
0x1800a7a27  mov     r8d, 5F7h
0x1800a7a2d  jmp     loc_1800A7AB2
0x1800a7a32  mov     rdx, [rbp+57h+var_38]; struct IWICBitmapSource *
0x1800a7a36  mov     rcx, rsi; this
  ... truncated ...
```
