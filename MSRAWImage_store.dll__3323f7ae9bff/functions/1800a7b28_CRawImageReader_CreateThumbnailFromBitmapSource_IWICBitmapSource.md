# CRawImageReader::CreateThumbnailFromBitmapSource(IWICBitmapSource *)

- ea: `0x1800a7b28`
- end: `0x1800a7f90`
- name: `?CreateThumbnailFromBitmapSource@CRawImageReader@@AEAAJPEAUIWICBitmapSource@@@Z`
- size: `1128`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, struct IWICBitmapSource *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800a7520`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009c41c`
- `0x18009c44c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a55bc`
- `0x1800a7b28`
- `0x1800a7f98`
- `0x1800b4010`

## string_xrefs

- `0x1800a7b67`: `CRawImageReader::CreateThumbnailFromBitmapSource`
- `0x1800a7da4`: `CRawImageReader::CreateThumbnailFromBitmapSource`

## pseudocode

```c
__int64 __fastcall CRawImageReader::CreateThumbnailFromBitmapSource(CRawImageReader *this, struct IWICBitmapSource *a2)
{
  int *v4; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  unsigned int *v7; // r14
  int v8; // edi
  void ***v9; // rcx
  struct CallStackContext *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // r15d
  unsigned int v13; // r13d
  void ***v14; // rcx
  struct CallStackContext *v15; // rax
  int v16; // r8d
  struct IWICImagingFactory *v17; // rbx
  HRESULT (__stdcall *CreateBitmapScaler)(IWICImagingFactory *, IWICBitmapScaler **); // rdi
  void ***v19; // rcx
  void ***v20; // rcx
  __int64 v21; // rbx
  int v23; // [rsp+28h] [rbp-49h]
  _BYTE v24[8]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v25; // [rsp+40h] [rbp-31h] BYREF
  struct IWICImagingFactory *v26; // [rsp+48h] [rbp-29h] BYREF
  int v27; // [rsp+50h] [rbp-21h] BYREF
  int v28; // [rsp+54h] [rbp-1Dh] BYREF
  __int64 v29; // [rsp+58h] [rbp-19h]
  _BYTE v30[32]; // [rsp+60h] [rbp-11h] BYREF
  _QWORD v31[2]; // [rsp+80h] [rbp+Fh] BYREF

  v29 = -2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v24,
    "CRawImageReader::CreateThumbnailFromBitmapSource",
    1545);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v31);
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
  }
  v7 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v30,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::CreateThumbnailFromBitmapSource",
    v4,
    v23);
  v28 = 0;
  v27 = 0;
  v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, int *, int *))a2->lpVtbl->GetSize)(a2, &v28, &v27);
  if ( v8 >= 0 )
  {
    v11 = v27;
    if ( v28 > (unsigned int)v27 )
      v11 = v28;
    v12 = 1024;
    if ( v11 <= 0x400 )
    {
      Microsoft::WRL::ComPtr<IWICBitmapSource>::operator=((char *)this + 224, a2);
      goto LABEL_54;
    }
    if ( v28 <= (unsigned int)v27 )
    {
      v13 = 1024;
      v12 = (int)(float)((float)((float)v28 / (float)v27) * 1024.0);
    }
    else
    {
      v13 = (int)(float)((float)((float)v27 / (float)v28) * 1024.0);
    }
    v25 = 0;
    v26 = 0;
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v26);
    v8 = CRawImageReader::CreateWICFactory(this, &v26);
    if ( v8 >= 0 )
    {
      v17 = v26;
      CreateBitmapScaler = v26->lpVtbl->CreateBitmapScaler;
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v25);
      v8 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, __int64 *))CreateBitmapScaler)(v17, &v25);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmapSource *, _QWORD, _QWORD, int))(*(_QWORD *)v25 + 64LL))(
               v25,
               a2,
               v12,
               v13,
               3);
        if ( v8 >= 0 )
        {
          v21 = v25;
          v31[0] = v25;
          Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(v31);
          v31[0] = *((_QWORD *)this + 28);
          *((_QWORD *)this + 28) = v21;
          Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v31);
          goto LABEL_31;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v8);
        }
        v20 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v20 + 8) )
          goto LABEL_31;
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v15 + 499) == v8 )
          goto LABEL_31;
        v16 = 1570;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v8);
        }
        v19 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v19 + 8) )
          goto LABEL_31;
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v15 + 499) == v8 )
          goto LABEL_31;
        v16 = 1569;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v8);
      }
      v14 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v14 + 8) )
        goto LABEL_31;
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v15 + 499) == v8 )
        goto LABEL_31;
      v16 = 1568;
    }
    CallStackContext::TraceFailure(v15, "CRawImageReader::CreateThumbnailFromBitmapSource", v16, v8);
LABEL_31:
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v25);
    goto LABEL_54;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v8);
  }
  v9 = (void ***)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v9 = &off_1800E5190;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
  }
  if ( *((_BYTE *)v9 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
    if ( *((_DWORD *)v10 + 499) != v8 )
      CallStackContext::TraceFailure(v10, "CRawImageReader::CreateThumbnailFromBitmapSource", 1549, v8);
  }
LABEL_54:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v30);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a7b28  mov     rax, rsp
0x1800a7b2b  push    rbp
0x1800a7b2c  push    rsi
0x1800a7b2d  push    rdi
0x1800a7b2e  push    r12
0x1800a7b30  push    r13
0x1800a7b32  push    r14
0x1800a7b34  push    r15
0x1800a7b36  lea     rbp, [rax-5Fh]
0x1800a7b3a  sub     rsp, 90h
0x1800a7b41  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x1800a7b49  mov     [rax+18h], rbx
0x1800a7b4d  mov     rax, cs:__security_cookie
0x1800a7b54  xor     rax, rsp
0x1800a7b57  mov     [rbp+57h+var_38], rax
0x1800a7b5b  mov     r12, rdx
0x1800a7b5e  mov     rsi, rcx
0x1800a7b61  mov     r8d, 609h; int
0x1800a7b67  lea     r15, aCrawimagereade_18; "CRawImageReader::CreateThumbnailFromBit"...
0x1800a7b6e  mov     rdx, r15; char *
0x1800a7b71  lea     rcx, [rbp+57h+var_90]; this
0x1800a7b75  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a7b7a  nop
0x1800a7b7b  xor     ebx, ebx
0x1800a7b7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a7b84  cmp     [rcx+8], bl
0x1800a7b87  jz      short loc_1800A7BDF
0x1800a7b89  cmp     [rsi+110h], rbx
0x1800a7b90  jz      short loc_1800A7BDF
0x1800a7b92  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7b97  mov     rdi, rax
0x1800a7b9a  mov     rcx, [rsi+110h]
0x1800a7ba1  mov     rdx, [rcx]
0x1800a7ba4  mov     rax, [rdx+128h]
0x1800a7bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7bb0  mov     ebx, eax
0x1800a7bb2  mov     rcx, [rsi+110h]
0x1800a7bb9  mov     rdx, [rcx]
0x1800a7bbc  mov     rax, [rdx+118h]
0x1800a7bc3  lea     rdx, [rbp+57h+var_48]
0x1800a7bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7bcc  movups  xmm0, xmmword ptr [rax]
0x1800a7bcf  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a7bd7  mov     [rdi+7E0h], ebx
0x1800a7bdd  xor     ebx, ebx
0x1800a7bdf  lea     r14, [rsi+38h]
0x1800a7be3  mov     rax, rsi
0x1800a7be6  neg     rax
0x1800a7be9  sbb     rdx, rdx
0x1800a7bec  and     rdx, r14; struct CTraceBase *
0x1800a7bef  mov     r8, r15; char *
0x1800a7bf2  lea     rcx, [rbp+57h+var_68]; this
0x1800a7bf6  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a7bfb  nop
0x1800a7bfc  mov     [rbp+57h+var_74], ebx
0x1800a7bff  mov     [rbp+57h+var_78], ebx
0x1800a7c02  mov     rax, [r12]
0x1800a7c06  lea     r8, [rbp+57h+var_78]
0x1800a7c0a  lea     rdx, [rbp+57h+var_74]
0x1800a7c0e  mov     rcx, r12
0x1800a7c11  mov     rax, [rax+18h]
0x1800a7c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7c1a  mov     edi, eax
0x1800a7c1c  test    eax, eax
0x1800a7c1e  jns     loc_1800A7CAC
0x1800a7c24  lea     rax, WPP_GLOBAL_Control
0x1800a7c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7c32  cmp     rcx, rax
0x1800a7c35  jz      short loc_1800A7C5F
0x1800a7c37  test    byte ptr [rcx+1Ch], 1
0x1800a7c3b  jz      short loc_1800A7C5F
0x1800a7c3d  cmp     byte ptr [rcx+19h], 4
0x1800a7c41  jb      short loc_1800A7C5F
0x1800a7c43  mov     edx, 89h
0x1800a7c48  mov     [rsp+20h], edi
0x1800a7c4c  mov     r9d, [r14]
0x1800a7c4f  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a7c56  mov     rcx, [rcx+10h]
0x1800a7c5a  call    WPP_SF_Dd
0x1800a7c5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7c66  test    rcx, rcx
0x1800a7c69  jnz     short loc_1800A7C79
0x1800a7c6b  lea     rcx, off_1800E5190; this
0x1800a7c72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7c79  cmp     [rcx+8], bl
0x1800a7c7c  jz      loc_1800A7F53
0x1800a7c82  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7c87  cmp     [rax+7CCh], edi
0x1800a7c8d  jz      loc_1800A7F53
0x1800a7c93  mov     r9d, edi; int
0x1800a7c96  mov     r8d, 60Dh; int
0x1800a7c9c  mov     rdx, r15; char *
0x1800a7c9f  mov     rcx, rax; this
0x1800a7ca2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a7ca7  jmp     loc_1800A7F53
0x1800a7cac  mov     ecx, [rbp+57h+var_78]
0x1800a7caf  mov     eax, ecx
0x1800a7cb1  mov     edx, [rbp+57h+var_74]
0x1800a7cb4  cmp     edx, ecx
0x1800a7cb6  cmova   eax, edx
0x1800a7cb9  mov     r15d, 400h
0x1800a7cbf  cmp     eax, r15d
0x1800a7cc2  jbe     loc_1800A7F43
0x1800a7cc8  xorps   xmm1, xmm1
0x1800a7ccb  xorps   xmm0, xmm0
0x1800a7cce  cmp     edx, ecx
0x1800a7cd0  jbe     short loc_1800A7CEF
0x1800a7cd2  cvtsi2ss xmm1, rcx
0x1800a7cd7  cvtsi2ss xmm0, rdx
0x1800a7cdc  divss   xmm1, xmm0
0x1800a7ce0  mulss   xmm1, cs:__real@44800000
0x1800a7ce8  cvttss2si r13, xmm1
0x1800a7ced  jmp     short loc_1800A7D0D
0x1800a7cef  mov     r13d, r15d
0x1800a7cf2  cvtsi2ss xmm1, rdx
0x1800a7cf7  cvtsi2ss xmm0, rcx
0x1800a7cfc  divss   xmm1, xmm0
0x1800a7d00  mulss   xmm1, cs:__real@44800000
0x1800a7d08  cvttss2si r15, xmm1
0x1800a7d0d  mov     [rbp+57h+var_88], rbx
0x1800a7d11  mov     [rbp+57h+var_80], rbx
0x1800a7d15  lea     rcx, [rbp+57h+var_80]
0x1800a7d19  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a7d1e  lea     rdx, [rbp+57h+var_80]; struct IWICImagingFactory **
0x1800a7d22  mov     rcx, rsi; this
0x1800a7d25  call    ?CreateWICFactory@CRawImageReader@@AEAAJPEAPEAUIWICImagingFactory@@@Z; CRawImageReader::CreateWICFactory(IWICImagingFactory * *)
0x1800a7d2a  mov     edi, eax
0x1800a7d2c  test    eax, eax
0x1800a7d2e  jns     loc_1800A7DCC
0x1800a7d34  lea     rax, WPP_GLOBAL_Control
0x1800a7d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7d42  cmp     rcx, rax
0x1800a7d45  jz      short loc_1800A7D6F
0x1800a7d47  test    byte ptr [rcx+1Ch], 1
0x1800a7d4b  jz      short loc_1800A7D6F
0x1800a7d4d  cmp     byte ptr [rcx+19h], 4
0x1800a7d51  jb      short loc_1800A7D6F
0x1800a7d53  mov     edx, 8Ah
0x1800a7d58  mov     [rsp+20h], edi
0x1800a7d5c  mov     r9d, [r14]
0x1800a7d5f  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a7d66  mov     rcx, [rcx+10h]
0x1800a7d6a  call    WPP_SF_Dd
0x1800a7d6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7d76  test    rcx, rcx
0x1800a7d79  jnz     short loc_1800A7D89
0x1800a7d7b  lea     rcx, off_1800E5190; this
0x1800a7d82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7d89  cmp     [rcx+8], bl
0x1800a7d8c  jz      short loc_1800A7DB4
0x1800a7d8e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7d93  cmp     [rax+7CCh], edi
0x1800a7d99  jz      short loc_1800A7DB4
0x1800a7d9b  mov     r8d, 620h; int
0x1800a7da1  mov     r9d, edi; int
0x1800a7da4  lea     rdx, aCrawimagereade_18; "CRawImageReader::CreateThumbnailFromBit"...
0x1800a7dab  mov     rcx, rax; this
0x1800a7dae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a7db3  nop
0x1800a7db4  lea     rcx, [rbp+57h+var_80]
0x1800a7db8  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a7dbd  nop
0x1800a7dbe  lea     rcx, [rbp+57h+var_88]
0x1800a7dc2  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a7dc7  jmp     loc_1800A7F53
0x1800a7dcc  mov     rbx, [rbp+57h+var_80]
0x1800a7dd0  mov     rax, [rbx]
0x1800a7dd3  mov     rdi, [rax+58h]
0x1800a7dd7  lea     rcx, [rbp+57h+var_88]
0x1800a7ddb  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a7de0  lea     rdx, [rbp+57h+var_88]
0x1800a7de4  mov     rcx, rbx
0x1800a7de7  mov     rax, rdi
0x1800a7dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7def  mov     edi, eax
0x1800a7df1  test    eax, eax
0x1800a7df3  jns     short loc_1800A7E70
0x1800a7df5  lea     rax, WPP_GLOBAL_Control
0x1800a7dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7e03  cmp     rcx, rax
0x1800a7e06  jz      short loc_1800A7E30
0x1800a7e08  test    byte ptr [rcx+1Ch], 1
0x1800a7e0c  jz      short loc_1800A7E30
0x1800a7e0e  cmp     byte ptr [rcx+19h], 4
0x1800a7e12  jb      short loc_1800A7E30
0x1800a7e14  mov     edx, 8Bh
0x1800a7e19  mov     [rsp+20h], edi
0x1800a7e1d  mov     r9d, [r14]
0x1800a7e20  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a7e27  mov     rcx, [rcx+10h]
0x1800a7e2b  call    WPP_SF_Dd
0x1800a7e30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7e37  test    rcx, rcx
0x1800a7e3a  jnz     short loc_1800A7E4A
0x1800a7e3c  lea     rcx, off_1800E5190; this
0x1800a7e43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7e4a  cmp     byte ptr [rcx+8], 0
0x1800a7e4e  jz      loc_1800A7DB4
0x1800a7e54  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7e59  cmp     [rax+7CCh], edi
0x1800a7e5f  jz      loc_1800A7DB4
0x1800a7e65  mov     r8d, 621h
0x1800a7e6b  jmp     loc_1800A7DA1
0x1800a7e70  mov     rcx, [rbp+57h+var_88]
0x1800a7e74  mov     rax, [rcx]
0x1800a7e77  mov     dword ptr [rsp+20h], 3
0x1800a7e7f  mov     r9d, r13d
0x1800a7e82  mov     r8d, r15d
0x1800a7e85  mov     rdx, r12
0x1800a7e88  mov     rax, [rax+40h]
0x1800a7e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7e91  mov     edi, eax
0x1800a7e93  test    eax, eax
0x1800a7e95  jns     short loc_1800A7F12
0x1800a7e97  lea     rax, WPP_GLOBAL_Control
0x1800a7e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7ea5  cmp     rcx, rax
0x1800a7ea8  jz      short loc_1800A7ED2
0x1800a7eaa  test    byte ptr [rcx+1Ch], 1
0x1800a7eae  jz      short loc_1800A7ED2
0x1800a7eb0  cmp     byte ptr [rcx+19h], 4
0x1800a7eb4  jb      short loc_1800A7ED2
0x1800a7eb6  mov     edx, 8Ch
0x1800a7ebb  mov     [rsp+20h], edi
0x1800a7ebf  mov     r9d, [r14]
0x1800a7ec2  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a7ec9  mov     rcx, [rcx+10h]
0x1800a7ecd  call    WPP_SF_Dd
0x1800a7ed2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7ed9  test    rcx, rcx
0x1800a7edc  jnz     short loc_1800A7EEC
0x1800a7ede  lea     rcx, off_1800E5190; this
0x1800a7ee5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7eec  cmp     byte ptr [rcx+8], 0
0x1800a7ef0  jz      loc_1800A7DB4
0x1800a7ef6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7efb  cmp     [rax+7CCh], edi
0x1800a7f01  jz      loc_1800A7DB4
0x1800a7f07  mov     r8d, 622h
0x1800a7f0d  jmp     loc_1800A7DA1
0x1800a7f12  mov     rbx, [rbp+57h+var_88]
0x1800a7f16  mov     [rbp+57h+var_48], rbx
0x1800a7f1a  lea     rcx, [rbp+57h+var_48]
0x1800a7f1e  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x1800a7f23  mov     rax, [rsi+0E0h]
0x1800a7f2a  mov     [rbp+57h+var_48], rax
0x1800a7f2e  mov     [rsi+0E0h], rbx
0x1800a7f35  lea     rcx, [rbp+57h+var_48]
0x1800a7f39  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a7f3e  jmp     loc_1800A7DB4
0x1800a7f43  lea     rcx, [rsi+0E0h]
0x1800a7f4a  mov     rdx, r12
0x1800a7f4d  call    ??4?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@QEAAAEAV012@PEAUIWICBitmapSource@@@Z; Microsoft::WRL::ComPtr<IWICBitmapSource>::operator=(IWICBitmapSource *)
0x1800a7f52  nop
0x1800a7f53  lea     rcx, [rbp+57h+var_68]; this
0x1800a7f57  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a7f5c  nop
0x1800a7f5d  lea     rcx, [rbp+57h+var_90]; this
0x1800a7f61  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a7f66  mov     eax, edi
0x1800a7f68  mov     rcx, [rbp+57h+var_38]
0x1800a7f6c  xor     rcx, rsp; StackCookie
0x1800a7f6f  call    __security_check_cookie
0x1800a7f74  mov     rbx, [rsp+0C0h+arg_10]
0x1800a7f7c  add     rsp, 90h
0x1800a7f83  pop     r15
0x1800a7f85  pop     r14
0x1800a7f87  pop     r13
0x1800a7f89  pop     r12
0x1800a7f8b  pop     rdi
0x1800a7f8c  pop     rsi
0x1800a7f8d  pop     rbp
0x1800a7f8e  retn
```
