# CRawImageReader::DecodeImage(void)

- ea: `0x1800a8588`
- end: `0x1800a8de8`
- name: `?DecodeImage@CRawImageReader@@AEAAJXZ`
- size: `2144`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a7520`
- `0x1800aa7f0`
- `0x1800ad600`

## callees

- `0x180001220`
- `0x180001710`
- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x180002e18`
- `0x180006bc0`
- `0x180007b70`
- `0x180008330`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009e8b8`
- `0x1800a2d70`
- `0x1800a2db4`
- `0x1800a34f8`
- `0x1800a81cc`
- `0x1800a8588`
- `0x1800a8df0`
- `0x1800abf54`
- `0x1800b4010`

## string_xrefs

- `0x1800a85d1`: `CRawImageReader::DecodeImage`
- `0x1800a865e`: `CRawImageReader::DecodeImage`
- `0x1800a8d8c`: `CRawImageReader::DecodeImage`

## pseudocode

```c
__int64 __fastcall CRawImageReader::DecodeImage(CRawImageReader *this)
{
  int *v2; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  struct CTraceBase *v5; // rdx
  __int64 v6; // r12
  unsigned __int64 v7; // rdx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int XMPStream; // ebx
  void ***v12; // rcx
  struct CallStackContext *v13; // rax
  int v14; // r8d
  int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  PVOID *v19; // rcx
  void ***v20; // rcx
  int v21; // r9d
  int v22; // r8d
  int v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  PVOID *v27; // rcx
  void ***v28; // rcx
  __int64 v29; // rax
  PVOID *v30; // rcx
  void ***v31; // rcx
  unsigned __int64 v32; // rax
  void ***v33; // rcx
  __int64 v34; // r9
  void ***v35; // rcx
  PVOID *v36; // rcx
  void ***v37; // rcx
  void ***v38; // rcx
  int v40; // [rsp+28h] [rbp-39h]
  _BYTE v41[4]; // [rsp+38h] [rbp-29h] BYREF
  int v42; // [rsp+3Ch] [rbp-25h] BYREF
  CRawImageReader *v43; // [rsp+40h] [rbp-21h] BYREF
  unsigned __int8 *v44[2]; // [rsp+48h] [rbp-19h] BYREF
  _BYTE v45[32]; // [rsp+58h] [rbp-9h] BYREF
  _QWORD v46[2]; // [rsp+78h] [rbp+17h] BYREF

  v44[1] = (unsigned __int8 *)-2LL;
  v44[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v41, "CRawImageReader::DecodeImage", 589);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v46);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
  }
  if ( this )
  {
    v5 = (CRawImageReader *)((char *)this + 56);
    v6 = (__int64)this + 56;
  }
  else
  {
    v5 = 0;
    v6 = 56;
  }
  CTraceBase::CAutoTrace::CAutoTrace((CTraceBase::CAutoTrace *)v45, v5, "CRawImageReader::DecodeImage", v2, v40);
  if ( !*((_BYTE *)this + 104) )
  {
    if ( (unsigned int)dword_1800E50F0 > 4 )
    {
      v43 = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v8,
        (unsigned int)&unk_1800D74E0,
        v9,
        v10,
        (__int64)&v43);
    }
    XMPStream = CRawImageReader::InitializeRawProcessorForDecodeImage(this, v44);
    if ( XMPStream < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *(unsigned int *)v6,
          XMPStream);
      }
      v12 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v13 + 499) != XMPStream )
        {
          v14 = 601;
LABEL_131:
          v21 = XMPStream;
          goto LABEL_132;
        }
      }
      goto LABEL_133;
    }
    v15 = LibRaw::unpack(*((LibRaw **)this + 18));
    v42 = v15;
    if ( v15 )
    {
      if ( (unsigned int)dword_1800E50F0 > 4 )
      {
        LODWORD(v43) = v15;
        v46[0] = this;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&word_1800D749E,
          v17,
          v18,
          (__int64)v46,
          (__int64)&v43);
        v15 = v42;
      }
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *(unsigned int *)v6,
          v15);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
      XMPStream = -2003292320;
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
        WPP_SF_Dd(v19[2], 38, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *(unsigned int *)v6, -2003292320);
      v20 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v20 + 8) )
        goto LABEL_133;
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v13 + 499) == -2003292320 )
        goto LABEL_133;
      v21 = -2003292320;
      v14 = 614;
      goto LABEL_132;
    }
    v22 = *(_DWORD *)(*((_QWORD *)this + 18) + 381540LL);
    if ( v22
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *(unsigned int *)v6,
        v22);
    }
    v23 = LibRaw::dcraw_process(*((LibRaw **)this + 18));
    v42 = v23;
    if ( (unsigned int)dword_1800E50F0 > 4 )
    {
      LODWORD(v43) = v23;
      v46[0] = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v24,
        (unsigned int)&dword_1800D745C,
        v25,
        v26,
        (__int64)v46,
        (__int64)&v43);
      v23 = v42;
    }
    if ( v23 )
    {
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *(unsigned int *)v6,
          v23);
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
      XMPStream = -2003292320;
      if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 1) != 0 && *((_BYTE *)v27 + 25) >= 4u )
        WPP_SF_Dd(v27[2], 41, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *(unsigned int *)v6, -2003292320);
      v28 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v28 + 8) )
        goto LABEL_133;
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
      if ( *((_DWORD *)v13 + 499) == -2003292320 )
        goto LABEL_133;
      v21 = -2003292320;
      v14 = 634;
      goto LABEL_132;
    }
    v29 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 18) + 16LL))(*((_QWORD *)this + 18), &v42);
    *((_QWORD *)this + 17) = v29;
    if ( !v29 )
    {
      XMPStream = -2147024882;
      goto LABEL_133;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *(unsigned int *)v6,
        *(unsigned __int16 *)(v29 + 6));
    }
    *((_BYTE *)this + 104) = 1;
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 256);
  }
  if ( *((_DWORD *)this + 28) && *((_DWORD *)this + 28) != *(unsigned __int16 *)(*((_QWORD *)this + 17) + 6LL)
    || *((_DWORD *)this + 29) && *((_DWORD *)this + 29) != *(unsigned __int16 *)(*((_QWORD *)this + 17) + 4LL) )
  {
    v30 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *((unsigned int *)this + 14));
      v30 = (PVOID *)WPP_GLOBAL_Control;
    }
    XMPStream = -2003292320;
    if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 && *((_BYTE *)v30 + 25) >= 4u )
      WPP_SF_Dd(v30[2], 44, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *((unsigned int *)this + 14), -2003292320);
    v31 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( !*((_BYTE *)v31 + 8) )
      goto LABEL_133;
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
    if ( *((_DWORD *)v13 + 499) == -2003292320 )
      goto LABEL_133;
    v21 = -2003292320;
    v14 = 652;
    goto LABEL_132;
  }
  v7 = *((_QWORD *)this + 17);
  v32 = 3 * *(unsigned __int16 *)(v7 + 4) * (unsigned __int64)*(unsigned __int16 *)(v7 + 6);
  if ( v32 > 0xFFFFFFFF )
  {
    XMPStream = -2147024362;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *((unsigned int *)this + 14),
        -2147024362);
    }
    v38 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v38 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
      if ( *((_DWORD *)v13 + 499) != -2147024362 )
      {
        v14 = 658;
        goto LABEL_131;
      }
    }
    goto LABEL_133;
  }
  if ( !(_DWORD)v32 || (unsigned int)v32 > *(_DWORD *)(v7 + 12) )
  {
    v36 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *((unsigned int *)this + 14));
      v36 = (PVOID *)WPP_GLOBAL_Control;
    }
    XMPStream = -2003292320;
    if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 1) != 0 && *((_BYTE *)v36 + 25) >= 4u )
      WPP_SF_Dd(v36[2], 48, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *((unsigned int *)this + 14), -2003292320);
    v37 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( !*((_BYTE *)v37 + 8) )
      goto LABEL_133;
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
    if ( *((_DWORD *)v13 + 499) == -2003292320 )
      goto LABEL_133;
    v21 = -2003292320;
    v14 = 663;
LABEL_132:
    CallStackContext::TraceFailure(v13, "CRawImageReader::DecodeImage", v14, v21);
    goto LABEL_133;
  }
  XMPStream = CRawImageReader::DecodePreview(this);
  if ( XMPStream >= 0 )
  {
    XMPStream = CRawImageReader::CreateXMPStream(this);
    v34 = *((unsigned int *)this + 14);
    if ( XMPStream >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, v34);
      }
      LibRaw::recycle(*((LibRaw **)this + 18));
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          v34,
          XMPStream);
      }
      v35 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v13 + 499) != XMPStream )
        {
          v14 = 668;
          goto LABEL_131;
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *((unsigned int *)this + 14),
        XMPStream);
    }
    v33 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( *((_DWORD *)v13 + 499) != XMPStream )
      {
        v14 = 667;
        goto LABEL_131;
      }
    }
  }
LABEL_133:
  operator delete(v44[0], v7);
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v45);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
  return (unsigned int)XMPStream;
}

```

## disassembly

```asm
0x1800a8588  mov     rax, rsp
0x1800a858b  push    rbp
0x1800a858c  push    r12
0x1800a858e  push    r13
0x1800a8590  push    r14
0x1800a8592  push    r15
0x1800a8594  lea     rbp, [rax-5Fh]
0x1800a8598  sub     rsp, 90h
0x1800a859f  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x1800a85a7  mov     [rax+10h], rbx
0x1800a85ab  mov     [rax+18h], rsi
0x1800a85af  mov     [rax+20h], rdi
0x1800a85b3  mov     rax, cs:__security_cookie
0x1800a85ba  xor     rax, rsp
0x1800a85bd  mov     [rbp+57h+var_30], rax
0x1800a85c1  mov     rsi, rcx
0x1800a85c4  xor     r13d, r13d
0x1800a85c7  mov     [rbp+57h+var_70], r13
0x1800a85cb  mov     r8d, 24Dh; int
0x1800a85d1  lea     rdx, aCrawimagereade_6; "CRawImageReader::DecodeImage"
0x1800a85d8  lea     rcx, [rbp+57h+var_80]; this
0x1800a85dc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a85e1  nop
0x1800a85e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a85e9  cmp     [rcx+8], r13b
0x1800a85ed  jz      short loc_1800A8649
0x1800a85ef  cmp     [rsi+110h], r13
0x1800a85f6  jz      short loc_1800A8649
0x1800a85f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a85fd  mov     rdi, rax
0x1800a8600  mov     rdx, [rsi+110h]
0x1800a8607  mov     rcx, [rdx]
0x1800a860a  mov     rax, [rcx+128h]
0x1800a8611  mov     rcx, rdx
0x1800a8614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8619  mov     ebx, eax
0x1800a861b  mov     r8, [rsi+110h]
0x1800a8622  mov     rcx, [r8]
0x1800a8625  mov     rax, [rcx+118h]
0x1800a862c  lea     rdx, [rbp+57h+var_40]
0x1800a8630  mov     rcx, r8
0x1800a8633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8638  movups  xmm0, xmmword ptr [rax]
0x1800a863b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a8643  mov     [rdi+7E0h], ebx
0x1800a8649  test    rsi, rsi
0x1800a864c  jz      short loc_1800A8657
0x1800a864e  lea     rdx, [rsi+38h]
0x1800a8652  mov     r12, rdx
0x1800a8655  jmp     short loc_1800A865E
0x1800a8657  mov     rdx, r13; struct CTraceBase *
0x1800a865a  lea     r12, [rsi+38h]
0x1800a865e  lea     r8, aCrawimagereade_6; "CRawImageReader::DecodeImage"
0x1800a8665  lea     rcx, [rbp+57h+var_60]; this
0x1800a8669  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a866e  nop
0x1800a866f  mov     edi, 4
0x1800a8674  lea     rbx, WPP_GLOBAL_Control
0x1800a867b  mov     r14b, 1
0x1800a867e  lea     r15, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a8685  cmp     [rsi+68h], r13b
0x1800a8689  jnz     loc_1800A8A07
0x1800a868f  cmp     cs:dword_1800E50F0, edi
0x1800a8695  jbe     short loc_1800A86B0
0x1800a8697  mov     [rbp+57h+var_78], rsi
0x1800a869b  lea     rax, [rbp+57h+var_78]
0x1800a869f  mov     [rsp+0B0h+var_90], rax
0x1800a86a4  lea     rdx, unk_1800D74E0
0x1800a86ab  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800a86b0  lea     rdx, [rbp+57h+var_70]; unsigned __int8 **
0x1800a86b4  mov     rcx, rsi; this
0x1800a86b7  call    ?InitializeRawProcessorForDecodeImage@CRawImageReader@@AEAAJPEAPEAE@Z; CRawImageReader::InitializeRawProcessorForDecodeImage(uchar * *)
0x1800a86bc  mov     ebx, eax
0x1800a86be  test    eax, eax
0x1800a86c0  jns     short loc_1800A873A
0x1800a86c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a86c9  lea     rax, WPP_GLOBAL_Control
0x1800a86d0  cmp     rcx, rax
0x1800a86d3  jz      short loc_1800A86FA
0x1800a86d5  test    [rcx+1Ch], r14b
0x1800a86d9  jz      short loc_1800A86FA
0x1800a86db  cmp     [rcx+19h], dil
0x1800a86df  jb      short loc_1800A86FA
0x1800a86e1  mov     edx, 24h ; '$'
0x1800a86e6  mov     dword ptr [rsp+0B0h+var_90], ebx
0x1800a86ea  mov     r9d, [r12]
0x1800a86ee  mov     r8, r15
0x1800a86f1  mov     rcx, [rcx+10h]
0x1800a86f5  call    WPP_SF_Dd
0x1800a86fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8701  test    rcx, rcx
0x1800a8704  jnz     short loc_1800A8714
0x1800a8706  lea     rcx, off_1800E5190; this
0x1800a870d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8714  cmp     [rcx+8], r13b
0x1800a8718  jz      loc_1800A8D9B
0x1800a871e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8723  cmp     [rax+7CCh], ebx
0x1800a8729  jz      loc_1800A8D9B
0x1800a872f  mov     r8d, 259h
0x1800a8735  jmp     loc_1800A8D89
0x1800a873a  mov     rcx, [rsi+90h]; this
0x1800a8741  call    ?unpack@LibRaw@@QEAAHXZ; LibRaw::unpack(void)
0x1800a8746  mov     [rbp+57h+var_7C], eax
0x1800a8749  test    eax, eax
0x1800a874b  jz      loc_1800A883B
0x1800a8751  cmp     cs:dword_1800E50F0, edi
0x1800a8757  jbe     short loc_1800A8781
0x1800a8759  mov     dword ptr [rbp+57h+var_78], eax
0x1800a875c  mov     [rbp+57h+var_40], rsi
0x1800a8760  lea     rax, [rbp+57h+var_78]
0x1800a8764  mov     [rsp+0B0h+var_88], rax
0x1800a8769  lea     rax, [rbp+57h+var_40]
0x1800a876d  mov     [rsp+0B0h+var_90], rax
0x1800a8772  lea     rdx, word_1800D749E
0x1800a8779  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800a877e  mov     eax, [rbp+57h+var_7C]
0x1800a8781  lea     r15, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a8788  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a878f  lea     rsi, WPP_GLOBAL_Control
0x1800a8796  cmp     rcx, rsi
0x1800a8799  jz      short loc_1800A87C7
0x1800a879b  test    [rcx+1Ch], r14b
0x1800a879f  jz      short loc_1800A87C7
0x1800a87a1  cmp     [rcx+19h], dil
0x1800a87a5  jb      short loc_1800A87C7
0x1800a87a7  mov     edx, 25h ; '%'
0x1800a87ac  mov     dword ptr [rsp+0B0h+var_90], eax
0x1800a87b0  mov     r9d, [r12]
0x1800a87b4  mov     r8, r15
0x1800a87b7  mov     rcx, [rcx+10h]
0x1800a87bb  call    WPP_SF_Dd
0x1800a87c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a87c7  mov     edi, 88982F60h
0x1800a87cc  mov     ebx, edi
0x1800a87ce  cmp     rcx, rsi
0x1800a87d1  jz      short loc_1800A87F8
0x1800a87d3  test    [rcx+1Ch], r14b
0x1800a87d7  jz      short loc_1800A87F8
0x1800a87d9  cmp     byte ptr [rcx+19h], 4
0x1800a87dd  jb      short loc_1800A87F8
0x1800a87df  mov     edx, 26h ; '&'
0x1800a87e4  mov     dword ptr [rsp+0B0h+var_90], edi
0x1800a87e8  mov     r9d, [r12]
0x1800a87ec  mov     r8, r15
0x1800a87ef  mov     rcx, [rcx+10h]
0x1800a87f3  call    WPP_SF_Dd
0x1800a87f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a87ff  test    rcx, rcx
0x1800a8802  jnz     short loc_1800A8812
0x1800a8804  lea     rcx, off_1800E5190; this
0x1800a880b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8812  cmp     [rcx+8], r13b
0x1800a8816  jz      loc_1800A8D9B
0x1800a881c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8821  cmp     [rax+7CCh], edi
0x1800a8827  jz      loc_1800A8D9B
0x1800a882d  mov     r9d, edi
0x1800a8830  mov     r8d, 266h
0x1800a8836  jmp     loc_1800A8D8C
0x1800a883b  mov     rax, [rsi+90h]
0x1800a8842  mov     r8d, [rax+5D264h]
0x1800a8849  test    r8d, r8d
0x1800a884c  jz      short loc_1800A8889
0x1800a884e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8855  lea     rbx, WPP_GLOBAL_Control
0x1800a885c  cmp     rcx, rbx
0x1800a885f  jz      short loc_1800A8890
0x1800a8861  test    [rcx+1Ch], r14b
0x1800a8865  jz      short loc_1800A8890
0x1800a8867  cmp     [rcx+19h], dil
0x1800a886b  jb      short loc_1800A8890
0x1800a886d  mov     edx, 27h ; '''
0x1800a8872  mov     dword ptr [rsp+0B0h+var_90], r8d
0x1800a8877  mov     r9d, [r12]
0x1800a887b  mov     r8, r15
0x1800a887e  mov     rcx, [rcx+10h]
0x1800a8882  call    WPP_SF_Dd
0x1800a8887  jmp     short loc_1800A8890
0x1800a8889  lea     rbx, WPP_GLOBAL_Control
0x1800a8890  mov     rcx, [rsi+90h]; this
0x1800a8897  call    ?dcraw_process@LibRaw@@QEAAHXZ; LibRaw::dcraw_process(void)
0x1800a889c  mov     [rbp+57h+var_7C], eax
0x1800a889f  cmp     cs:dword_1800E50F0, edi
0x1800a88a5  jbe     short loc_1800A88CF
0x1800a88a7  mov     dword ptr [rbp+57h+var_78], eax
0x1800a88aa  mov     [rbp+57h+var_40], rsi
0x1800a88ae  lea     rax, [rbp+57h+var_78]
0x1800a88b2  mov     [rsp+0B0h+var_88], rax
0x1800a88b7  lea     rax, [rbp+57h+var_40]
0x1800a88bb  mov     [rsp+0B0h+var_90], rax
0x1800a88c0  lea     rdx, dword_1800D745C
0x1800a88c7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800a88cc  mov     eax, [rbp+57h+var_7C]
0x1800a88cf  test    eax, eax
0x1800a88d1  jz      loc_1800A898A
0x1800a88d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a88de  cmp     rcx, rbx
0x1800a88e1  jz      short loc_1800A890F
0x1800a88e3  test    [rcx+1Ch], r14b
0x1800a88e7  jz      short loc_1800A890F
0x1800a88e9  cmp     [rcx+19h], dil
0x1800a88ed  jb      short loc_1800A890F
0x1800a88ef  mov     edx, 28h ; '('
0x1800a88f4  mov     dword ptr [rsp+0B0h+var_90], eax
0x1800a88f8  mov     r9d, [r12]
0x1800a88fc  mov     r8, r15
0x1800a88ff  mov     rcx, [rcx+10h]
0x1800a8903  call    WPP_SF_Dd
0x1800a8908  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a890f  mov     edi, 88982F60h
0x1800a8914  mov     ebx, edi
0x1800a8916  lea     rax, WPP_GLOBAL_Control
0x1800a891d  cmp     rcx, rax
0x1800a8920  jz      short loc_1800A8947
0x1800a8922  test    [rcx+1Ch], r14b
0x1800a8926  jz      short loc_1800A8947
0x1800a8928  cmp     byte ptr [rcx+19h], 4
0x1800a892c  jb      short loc_1800A8947
0x1800a892e  mov     edx, 29h ; ')'
0x1800a8933  mov     dword ptr [rsp+0B0h+var_90], edi
0x1800a8937  mov     r9d, [r12]
0x1800a893b  mov     r8, r15
0x1800a893e  mov     rcx, [rcx+10h]
0x1800a8942  call    WPP_SF_Dd
0x1800a8947  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a894e  test    rcx, rcx
0x1800a8951  jnz     short loc_1800A8961
0x1800a8953  lea     rcx, off_1800E5190; this
0x1800a895a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8961  cmp     [rcx+8], r13b
0x1800a8965  jz      loc_1800A8D9B
0x1800a896b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8970  cmp     [rax+7CCh], edi
0x1800a8976  jz      loc_1800A8D9B
0x1800a897c  mov     r9d, edi
0x1800a897f  mov     r8d, 27Ah
0x1800a8985  jmp     loc_1800A8D8C
0x1800a898a  mov     rcx, [rsi+90h]
0x1800a8991  mov     rax, [rcx]
0x1800a8994  lea     rdx, [rbp+57h+var_7C]
0x1800a8998  mov     rax, [rax+10h]
0x1800a899c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a89a1  mov     rcx, rax
0x1800a89a4  mov     [rsi+88h], rax
0x1800a89ab  test    rax, rax
0x1800a89ae  jnz     short loc_1800A89BA
0x1800a89b0  mov     ebx, 8007000Eh
0x1800a89b5  jmp     loc_1800A8D9B
0x1800a89ba  mov     r10, cs:WPP_GLOBAL_Control
0x1800a89c1  cmp     r10, rbx
0x1800a89c4  jz      short loc_1800A89F7
0x1800a89c6  test    [r10+1Ch], r14b
0x1800a89ca  jz      short loc_1800A89F7
0x1800a89cc  cmp     [r10+19h], dil
0x1800a89d0  jb      short loc_1800A89F7
0x1800a89d2  movzx   eax, word ptr [rax+4]
0x1800a89d6  movzx   ecx, word ptr [rcx+6]
0x1800a89da  mov     edx, 2Ah ; '*'
0x1800a89df  mov     dword ptr [rsp+0B0h+var_88], eax
0x1800a89e3  mov     dword ptr [rsp+0B0h+var_90], ecx
0x1800a89e7  mov     r9d, [r12]
0x1800a89eb  mov     r8, r15
0x1800a89ee  mov     rcx, [r10+10h]
0x1800a89f2  call    WPP_SF_DDD
0x1800a89f7  mov     [rsi+68h], r14b
0x1800a89fb  lea     rcx, [rsi+100h]
0x1800a8a02  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a8a07  cmp     [rsi+70h], r13d
0x1800a8a0b  jz      short loc_1800A8A1D
0x1800a8a0d  mov     rax, [rsi+88h]
0x1800a8a14  movzx   ecx, word ptr [rax+6]
0x1800a8a18  cmp     [rsi+70h], ecx
0x1800a8a1b  jnz     short loc_1800A8A3B
0x1800a8a1d  cmp     [rsi+74h], r13d
0x1800a8a21  jz      loc_1800A8AEA
0x1800a8a27  mov     rax, [rsi+88h]
0x1800a8a2e  movzx   ecx, word ptr [rax+4]
0x1800a8a32  cmp     [rsi+74h], ecx
0x1800a8a35  jz      loc_1800A8AEA
0x1800a8a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8a42  cmp     rcx, rbx
0x1800a8a45  jz      short loc_1800A8A6F
0x1800a8a47  test    [rcx+1Ch], r14b
0x1800a8a4b  jz      short loc_1800A8A6F
0x1800a8a4d  cmp     [rcx+19h], dil
0x1800a8a51  jb      short loc_1800A8A6F
0x1800a8a53  mov     edx, 2Bh ; '+'
0x1800a8a58  mov     r9d, [rsi+38h]
0x1800a8a5c  mov     r8, r15
0x1800a8a5f  mov     rcx, [rcx+10h]
0x1800a8a63  call    WPP_SF_D
0x1800a8a68  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8a6f  mov     edi, 88982F60h
0x1800a8a74  mov     ebx, edi
0x1800a8a76  lea     rax, WPP_GLOBAL_Control
0x1800a8a7d  cmp     rcx, rax
0x1800a8a80  jz      short loc_1800A8AA7
0x1800a8a82  test    [rcx+1Ch], r14b
0x1800a8a86  jz      short loc_1800A8AA7
  ... truncated ...
```
