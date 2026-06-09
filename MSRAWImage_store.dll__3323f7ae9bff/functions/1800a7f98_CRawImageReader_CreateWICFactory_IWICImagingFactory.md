# CRawImageReader::CreateWICFactory(IWICImagingFactory * *)

- ea: `0x1800a7f98`
- end: `0x1800a81c5`
- name: `?CreateWICFactory@CRawImageReader@@AEAAJPEAPEAUIWICImagingFactory@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, struct IWICImagingFactory **)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a7520`
- `0x1800a7b28`
- `0x1800a8df0`

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
- `0x1800a7f98`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceFromApp` at `0x1800a80a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceFromApp` at `0x1800a80a0`

## string_xrefs

- `0x1800a7fd4`: `CRawImageReader::CreateWICFactory`
- `0x1800a8054`: `CRawImageReader::CreateWICFactory`
- `0x1800a8127`: `CRawImageReader::CreateWICFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRawImageReader::CreateWICFactory(CRawImageReader *this, struct IWICImagingFactory **a2)
{
  int *v4; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  int v7; // ebx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  struct IWICImagingFactory *v10; // rbx
  int v12; // [rsp+28h] [rbp-29h]
  _BYTE v13[8]; // [rsp+38h] [rbp-19h] BYREF
  GUID *v14; // [rsp+40h] [rbp-11h] BYREF
  __int128 v15; // [rsp+48h] [rbp-9h]
  __int64 v16; // [rsp+58h] [rbp+7h]
  _BYTE v17[32]; // [rsp+60h] [rbp+Fh] BYREF
  _QWORD v18[2]; // [rsp+80h] [rbp+2Fh] BYREF

  v16 = -2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v13, "CRawImageReader::CreateWICFactory", 1590);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v18);
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
  }
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v17,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
    "CRawImageReader::CreateWICFactory",
    v4,
    v12);
  *a2 = 0;
  v15 = 0;
  v14 = &IID_IWICImagingFactory;
  v7 = CoCreateInstanceFromApp(&CLSID_WICImagingFactory2, 0, 1, 0, 1, &v14);
  if ( v7 >= 0 )
  {
    v10 = (struct IWICImagingFactory *)v15;
    v18[0] = v15;
    Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(v18);
    if ( (_QWORD)v15 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 16LL))(v15);
      *(_QWORD *)&v15 = 0;
    }
    if ( v10 )
    {
      Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(v18);
      *a2 = v10;
      v7 = 0;
    }
    else
    {
      v7 = -2147024882;
    }
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v18);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *((unsigned int *)this + 14),
        v7);
    }
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)v9 + 499) != v7 )
        CallStackContext::TraceFailure(v9, "CRawImageReader::CreateWICFactory", 1597, v7);
    }
  }
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v17);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800a7f98  mov     rax, rsp
0x1800a7f9b  push    rbp
0x1800a7f9c  push    rdi
0x1800a7f9d  push    r14
0x1800a7f9f  lea     rbp, [rax-5Fh]
0x1800a7fa3  sub     rsp, 90h
0x1800a7faa  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1800a7fb2  mov     [rax+18h], rbx
0x1800a7fb6  mov     [rax+20h], rsi
0x1800a7fba  mov     rax, cs:__security_cookie
0x1800a7fc1  xor     rax, rsp
0x1800a7fc4  mov     [rbp+57h+var_18], rax
0x1800a7fc8  mov     r14, rdx
0x1800a7fcb  mov     rsi, rcx
0x1800a7fce  mov     r8d, 636h; int
0x1800a7fd4  lea     rdx, aCrawimagereade_14; "CRawImageReader::CreateWICFactory"
0x1800a7fdb  lea     rcx, [rbp+57h+var_70]; this
0x1800a7fdf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a7fe4  nop
0x1800a7fe5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a7fec  cmp     byte ptr [rcx+8], 0
0x1800a7ff0  jz      short loc_1800A8047
0x1800a7ff2  cmp     qword ptr [rsi+110h], 0
0x1800a7ffa  jz      short loc_1800A8047
0x1800a7ffc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8001  mov     rdi, rax
0x1800a8004  mov     rcx, [rsi+110h]
0x1800a800b  mov     rdx, [rcx]
0x1800a800e  mov     rax, [rdx+128h]
0x1800a8015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a801a  mov     ebx, eax
0x1800a801c  mov     rcx, [rsi+110h]
0x1800a8023  mov     rdx, [rcx]
0x1800a8026  mov     rax, [rdx+118h]
0x1800a802d  lea     rdx, [rbp+57h+var_28]
0x1800a8031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8036  movups  xmm0, xmmword ptr [rax]
0x1800a8039  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a8041  mov     [rdi+7E0h], ebx
0x1800a8047  lea     rdi, [rsi+38h]
0x1800a804b  neg     rsi
0x1800a804e  sbb     rdx, rdx
0x1800a8051  and     rdx, rdi; struct CTraceBase *
0x1800a8054  lea     r8, aCrawimagereade_14; "CRawImageReader::CreateWICFactory"
0x1800a805b  lea     rcx, [rbp+57h+var_48]; this
0x1800a805f  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a8064  nop
0x1800a8065  mov     qword ptr [r14], 0
0x1800a806c  xorps   xmm0, xmm0
0x1800a806f  movdqu  [rbp+57h+var_60], xmm0
0x1800a8074  lea     rax, IID_IWICImagingFactory
0x1800a807b  mov     [rbp+57h+var_68], rax
0x1800a807f  lea     rax, [rbp+57h+var_68]
0x1800a8083  mov     [rsp+0A0h+var_78], rax
0x1800a8088  mov     esi, 1
0x1800a808d  mov     dword ptr [rsp+0A0h+var_80], esi
0x1800a8091  xor     r9d, r9d
0x1800a8094  mov     r8d, esi
0x1800a8097  xor     edx, edx
0x1800a8099  lea     rcx, CLSID_WICImagingFactory2
0x1800a80a0  call    cs:__imp_CoCreateInstanceFromApp
0x1800a80a7  nop     dword ptr [rax+rax+00h]
0x1800a80ac  mov     ebx, eax
0x1800a80ae  test    eax, eax
0x1800a80b0  jns     loc_1800A8138
0x1800a80b6  lea     rax, WPP_GLOBAL_Control
0x1800a80bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a80c4  cmp     rcx, rax
0x1800a80c7  jz      short loc_1800A80F1
0x1800a80c9  test    [rcx+1Ch], sil
0x1800a80cd  jz      short loc_1800A80F1
0x1800a80cf  cmp     byte ptr [rcx+19h], 4
0x1800a80d3  jb      short loc_1800A80F1
0x1800a80d5  mov     edx, 8Dh
0x1800a80da  mov     dword ptr [rsp+0A0h+var_80], ebx
0x1800a80de  mov     r9d, [rdi]
0x1800a80e1  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a80e8  mov     rcx, [rcx+10h]
0x1800a80ec  call    WPP_SF_Dd
0x1800a80f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a80f8  test    rcx, rcx
0x1800a80fb  jnz     short loc_1800A810B
0x1800a80fd  lea     rcx, off_1800E5190; this
0x1800a8104  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a810b  cmp     byte ptr [rcx+8], 0
0x1800a810f  jz      short loc_1800A818B
0x1800a8111  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8116  cmp     [rax+7CCh], ebx
0x1800a811c  jz      short loc_1800A818B
0x1800a811e  mov     r9d, ebx; int
0x1800a8121  mov     r8d, 63Dh; int
0x1800a8127  lea     rdx, aCrawimagereade_14; "CRawImageReader::CreateWICFactory"
0x1800a812e  mov     rcx, rax; this
0x1800a8131  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8136  jmp     short loc_1800A818B
0x1800a8138  mov     rbx, qword ptr [rbp+57h+var_60]
0x1800a813c  mov     [rbp+57h+var_28], rbx
0x1800a8140  lea     rcx, [rbp+57h+var_28]
0x1800a8144  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x1800a8149  nop
0x1800a814a  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800a814e  test    rcx, rcx
0x1800a8151  jz      short loc_1800A8167
0x1800a8153  mov     rax, [rcx]
0x1800a8156  mov     rax, [rax+10h]
0x1800a815a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a815f  mov     qword ptr [rbp+57h+var_60], 0
0x1800a8167  test    rbx, rbx
0x1800a816a  jnz     short loc_1800A8173
0x1800a816c  mov     ebx, 8007000Eh
0x1800a8171  jmp     short loc_1800A8181
0x1800a8173  lea     rcx, [rbp+57h+var_28]
0x1800a8177  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x1800a817c  mov     [r14], rbx
0x1800a817f  xor     ebx, ebx
0x1800a8181  lea     rcx, [rbp+57h+var_28]
0x1800a8185  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a818a  nop
0x1800a818b  lea     rcx, [rbp+57h+var_48]; this
0x1800a818f  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a8194  nop
0x1800a8195  lea     rcx, [rbp+57h+var_70]; this
0x1800a8199  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a819e  mov     eax, ebx
0x1800a81a0  mov     rcx, [rbp+57h+var_18]
0x1800a81a4  xor     rcx, rsp; StackCookie
0x1800a81a7  call    __security_check_cookie
0x1800a81ac  lea     r11, [rsp+0A0h+var_10]
0x1800a81b4  mov     rbx, [r11+30h]
0x1800a81b8  mov     rsi, [r11+38h]
0x1800a81bc  mov     rsp, r11
0x1800a81bf  pop     r14
0x1800a81c1  pop     rdi
0x1800a81c2  pop     rbp
0x1800a81c3  retn
```
