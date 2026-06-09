# CDSSampleSinkInputPin::AddMediaTypePair(CMediaType &,int)

- ea: `0x180071dbc`
- end: `0x180072278`
- name: `?AddMediaTypePair@CDSSampleSinkInputPin@@IEAAJAEAVCMediaType@@H@Z`
- size: `1212`
- prototype: `__int64 __fastcall(CDSSampleSinkInputPin *__hidden this, struct _AMMediaType *, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18000eb90`
- `0x18005bb20`
- `0x180072280`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180010350`
- `0x1800140b0`
- `0x1800227e0`
- `0x180023738`
- `0x180032a50`
- `0x180048f6c`
- `0x18004d7cc`
- `0x180051ce4`
- `0x1800527ac`
- `0x180071dbc`
- `0x180073d0c`
- `0x180074a06`
- `0x18007cfcc`
- `0x180083720`
- `0x1800c49dc`
- `0x1800c9010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071e89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800720f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800721b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071e89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800720f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800721b4`
- `MFPlat!MFCreateMediaTypeFromRepresentation` at `0x180071e67`
- `MFPlat!MFCreateMediaTypeFromRepresentation` at `0x180071e67`

## pseudocode

```c
__int64 __fastcall CDSSampleSinkInputPin::AddMediaTypePair(
        CDSSampleSinkInputPin *this,
        struct _AMMediaType *a2,
        int a3)
{
  unsigned int i; // ebx
  __int64 v7; // rax
  HRESULT v8; // edi
  CallStackTracing *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  IMFMediaType **v13; // rax
  MFDSMediaTypePair *v14; // rsi
  IMFMediaType *v15; // rcx
  unsigned int v16; // edx
  unsigned int v17; // edx
  CallStackTracing *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  GUID guidRepresentation; // [rsp+30h] [rbp-10h] BYREF
  char v26; // [rsp+80h] [rbp+40h] BYREF
  IMFMediaType *ppIMediaType; // [rsp+88h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v26, "CDSSampleSinkInputPin::AddMediaTypePair", 1293);
  ppIMediaType = 0;
  if ( a3 )
  {
    for ( i = 0; i < *((_DWORD *)this + 140); ++i )
    {
      v7 = CTPtrArray<CDShowStream,20>::operator[]((char *)this + 360, i);
      if ( (unsigned int)CMediaType::operator==(v7 + 8, a2) )
      {
        v8 = 0;
        if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            112,
            &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
            this,
            i);
        goto LABEL_62;
      }
    }
  }
  guidRepresentation = AM_MEDIA_TYPE_REPRESENTATION;
  v8 = MFCreateMediaTypeFromRepresentation(&guidRepresentation, a2, &ppIMediaType);
  if ( v8 >= 0 )
  {
    if ( *((_DWORD *)this + 84) == 2 && (unsigned __int8)_(&MEDIATYPE_Video, a2) && a2->pbFormat )
    {
      if ( ((unsigned __int8)_(&FORMAT_MPEG2Video, &a2->formattype) && a2->cbFormat >= 0x88
         || (unsigned __int8)_(&FORMAT_VideoInfo2, &a2->formattype) && a2->cbFormat >= 0x70)
        && !*((_DWORD *)a2->pbFormat + 12)
        && ((unsigned __int8)_(&MEDIASUBTYPE_MPEG2_VIDEO, &a2->subtype)
         || (unsigned __int8)_(&MEDIASUBTYPE_H264, &a2->subtype)) )
      {
        ((void (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppIMediaType->lpVtbl->SetUINT32)(
          ppIMediaType,
          &MF_MT_INTERLACE_MODE,
          7);
      }
      ((void (__fastcall *)(IMFMediaType *, const GUID *, _QWORD, _QWORD))ppIMediaType->lpVtbl->SetBlob)(
        ppIMediaType,
        &MF_MT_MPEG_SEQUENCE_HEADER,
        0,
        0);
    }
    if ( *((_DWORD *)this + 146) )
      ((void (__fastcall *)(IMFMediaType *, __int64 *, __int64))ppIMediaType->lpVtbl->SetUINT32)(
        ppIMediaType,
        MF_MT_USE_PRIMARY_ADAPTER,
        1);
    v13 = (IMFMediaType **)operator new(0x60u);
    v14 = (MFDSMediaTypePair *)v13;
    if ( v13 )
    {
      v15 = ppIMediaType;
      *v13 = ppIMediaType;
      if ( v15 )
        ((void (__fastcall *)(IMFMediaType *))v15->lpVtbl->AddRef)(v15);
      memset_0((char *)v14 + 8, 0, 0x58u);
      *((_DWORD *)v14 + 12) = 1;
      *((_DWORD *)v14 + 10) = 1;
      CMediaType::Set((MFDSMediaTypePair *)((char *)v14 + 8), a2);
      if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
        WPP_SF_qqq(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          115,
          &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
          this,
          *(_QWORD *)v14,
          (char *)v14 + 8);
      MFDSMediaTypePair::Log(v14, "CDSSampleSinkInputPin::AddMediaTypePair", this);
      v16 = *((_DWORD *)this + 140);
      *(_QWORD *)&guidRepresentation.Data1 = v14;
      if ( (int)CTSparseBlock<unsigned long,SampleSinkEntry *,20,1>::SetValue(
                  (_DWORD *)this + 90,
                  v16,
                  &guidRepresentation) < 0 )
      {
        v18 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        v8 = -2147024882;
        if ( *((_BYTE *)v18 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v18);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CDSSampleSinkInputPin::AddMediaTypePair",
              1375,
              -2147024882);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            116,
            &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
            this,
            -2147024882);
        MFDSMediaTypePair::`scalar deleting destructor'(v14, v17);
      }
      else
      {
        ++*((_DWORD *)this + 140);
      }
    }
    else
    {
      v21 = CallStackTracing::s_wpInstance;
      v8 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v21);
        if ( *((_DWORD *)v23 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v23, "CDSSampleSinkInputPin::AddMediaTypePair", 1365, -2147024882);
      }
      if ( g_wppLevels )
      {
        v12 = 114;
        goto LABEL_61;
      }
    }
  }
  else
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CDSSampleSinkInputPin::AddMediaTypePair", 1325, v8);
    }
    if ( g_wppLevels )
    {
      v12 = 113;
LABEL_61:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, this, v8);
    }
  }
LABEL_62:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppIMediaType);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180071dbc  mov     [rsp-28h+arg_0], rbx
0x180071dc1  push    rbp
0x180071dc2  push    rsi
0x180071dc3  push    rdi
0x180071dc4  push    r14
0x180071dc6  push    r15
0x180071dc8  mov     rbp, rsp
0x180071dcb  sub     rsp, 40h
0x180071dcf  mov     ebx, r8d
0x180071dd2  mov     r14, rdx
0x180071dd5  mov     r15, rcx
0x180071dd8  lea     rdx, aCdssamplesinki_8; "CDSSampleSinkInputPin::AddMediaTypePair"
0x180071ddf  mov     r8d, 50Dh; int
0x180071de5  lea     rcx, [rbp+arg_10]; this
0x180071de9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071dee  mov     [rbp+ppIMediaType], 0
0x180071df6  test    ebx, ebx
0x180071df8  jz      short loc_180071E50
0x180071dfa  xor     ebx, ebx
0x180071dfc  cmp     ebx, [r15+230h]
0x180071e03  jnb     short loc_180071E50
0x180071e05  mov     edx, ebx
0x180071e07  lea     rcx, [r15+168h]
0x180071e0e  call    ??A?$CTPtrArray@VCDShowStream@@$0BE@@@QEBAPEAVCDShowStream@@K@Z; CTPtrArray<CDShowStream,20>::operator[](ulong)
0x180071e13  mov     rdx, r14
0x180071e16  lea     rcx, [rax+8]
0x180071e1a  call    ??8CMediaType@@QEBAHAEBV0@@Z; CMediaType::operator==(CMediaType const &)
0x180071e1f  test    eax, eax
0x180071e21  jnz     short loc_180071E27
0x180071e23  inc     ebx
0x180071e25  jmp     short loc_180071DFC
0x180071e27  xor     edi, edi
0x180071e29  cmp     cs:byte_1800EACCB, 10h
0x180071e30  jb      loc_180072252
0x180071e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180071e3d  lea     edx, [rdi+70h]
0x180071e40  mov     dword ptr [rsp+40h+var_20], ebx
0x180071e44  mov     rcx, [rcx+88h]
0x180071e4b  jmp     loc_180072243
0x180071e50  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x180071e57  lea     r8, [rbp+ppIMediaType]; ppIMediaType
0x180071e5b  mov     rdx, r14; pvRepresentation
0x180071e5e  lea     rcx, [rbp+guidRepresentation]; guidRepresentation
0x180071e62  movdqu  xmmword ptr [rbp+guidRepresentation.Data1], xmm0
0x180071e67  call    cs:__imp_MFCreateMediaTypeFromRepresentation
0x180071e6e  nop     dword ptr [rax+rax+00h]
0x180071e73  mov     edi, eax
0x180071e75  test    eax, eax
0x180071e77  jns     loc_180071F12
0x180071e7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e84  test    rcx, rcx
0x180071e87  jnz     short loc_180071ED0
0x180071e89  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071e90  nop     dword ptr [rax+rax+00h]
0x180071e95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e9c  mov     rcx, rax
0x180071e9f  test    rax, rax
0x180071ea2  jz      short loc_180071EC2
0x180071ea4  mov     rax, [rax]
0x180071ea7  mov     edx, 7F0h
0x180071eac  mov     rax, [rax+8]
0x180071eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071eb5  test    eax, eax
0x180071eb7  jz      short loc_180071EC2
0x180071eb9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071ec0  jmp     short loc_180071ED0
0x180071ec2  lea     rcx, qword_1800EB130; this
0x180071ec9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071ed0  cmp     byte ptr [rcx+8], 0
0x180071ed4  jz      short loc_180071EFB
0x180071ed6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071edb  cmp     [rax+7CCh], edi
0x180071ee1  jz      short loc_180071EFB
0x180071ee3  mov     r9d, edi; int
0x180071ee6  lea     rdx, aCdssamplesinki_8; "CDSSampleSinkInputPin::AddMediaTypePair"
0x180071eed  mov     r8d, 52Dh; int
0x180071ef3  mov     rcx, rax; this
0x180071ef6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071efb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071f02  jb      loc_180072252
0x180071f08  mov     edx, 71h ; 'q'
0x180071f0d  jmp     loc_180072234
0x180071f12  cmp     dword ptr [r15+150h], 2
0x180071f1a  jnz     loc_180071FED
0x180071f20  mov     rdx, r14
0x180071f23  lea     rcx, MEDIATYPE_Video
0x180071f2a  call    __
0x180071f2f  test    al, al
0x180071f31  jz      loc_180071FED
0x180071f37  cmp     qword ptr [r14+50h], 0
0x180071f3c  jz      loc_180071FED
0x180071f42  lea     rdx, [r14+2Ch]
0x180071f46  lea     rcx, FORMAT_MPEG2Video
0x180071f4d  call    __
0x180071f52  test    al, al
0x180071f54  jz      short loc_180071F60
0x180071f56  cmp     dword ptr [r14+48h], 88h
0x180071f5e  jnb     short loc_180071F7B
0x180071f60  lea     rdx, [r14+2Ch]
0x180071f64  lea     rcx, FORMAT_VideoInfo2
0x180071f6b  call    __
0x180071f70  test    al, al
0x180071f72  jz      short loc_180071FCD
0x180071f74  cmp     dword ptr [r14+48h], 70h ; 'p'
0x180071f79  jb      short loc_180071FCD
0x180071f7b  mov     rax, [r14+50h]
0x180071f7f  cmp     dword ptr [rax+30h], 0
0x180071f83  jnz     short loc_180071FCD
0x180071f85  lea     rdx, [r14+10h]
0x180071f89  lea     rcx, MEDIASUBTYPE_MPEG2_VIDEO
0x180071f90  call    __
0x180071f95  test    al, al
0x180071f97  jnz     short loc_180071FAD
0x180071f99  lea     rdx, [r14+10h]
0x180071f9d  lea     rcx, MEDIASUBTYPE_H264
0x180071fa4  call    __
0x180071fa9  test    al, al
0x180071fab  jz      short loc_180071FCD
0x180071fad  mov     rcx, [rbp+ppIMediaType]
0x180071fb1  lea     rdx, MF_MT_INTERLACE_MODE
0x180071fb8  mov     r8d, 7
0x180071fbe  mov     rax, [rcx]
0x180071fc1  mov     rax, [rax+0A8h]
0x180071fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fcd  mov     rcx, [rbp+ppIMediaType]
0x180071fd1  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x180071fd8  xor     r9d, r9d
0x180071fdb  xor     r8d, r8d
0x180071fde  mov     rax, [rcx]
0x180071fe1  mov     rax, [rax+0D0h]
0x180071fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fed  cmp     dword ptr [r15+248h], 0
0x180071ff5  jz      short loc_180072017
0x180071ff7  mov     rcx, [rbp+ppIMediaType]
0x180071ffb  lea     rdx, MF_MT_USE_PRIMARY_ADAPTER
0x180072002  mov     r8d, 1
0x180072008  mov     rax, [rcx]
0x18007200b  mov     rax, [rax+0A8h]
0x180072012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072017  mov     ecx, 60h ; '`'; Size
0x18007201c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072021  mov     rsi, rax
0x180072024  test    rax, rax
0x180072027  jz      loc_1800721A3
0x18007202d  mov     rcx, [rbp+ppIMediaType]
0x180072031  mov     [rax], rcx
0x180072034  test    rcx, rcx
0x180072037  jz      short loc_180072045
0x180072039  mov     rax, [rcx]
0x18007203c  mov     rax, [rax+8]
0x180072040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072045  xor     edx, edx; Val
0x180072047  lea     rcx, [rsi+8]; void *
0x18007204b  lea     r8d, [rdx+58h]; Size
0x18007204f  call    memset_0
0x180072054  mov     rdx, r14; struct _AMMediaType *
0x180072057  mov     dword ptr [rsi+30h], 1
0x18007205e  lea     rcx, [rsi+8]; this
0x180072062  mov     dword ptr [rsi+28h], 1
0x180072069  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18007206e  cmp     cs:byte_1800EACCB, 10h
0x180072075  jb      short loc_1800720AA
0x180072077  mov     rcx, cs:WPP_GLOBAL_Control
0x18007207e  lea     rax, [rsi+8]
0x180072082  mov     [rsp+40h+var_18], rax
0x180072087  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x18007208e  mov     rax, [rsi]
0x180072091  mov     edx, 73h ; 's'
0x180072096  mov     r9, r15
0x180072099  mov     [rsp+40h+var_20], rax
0x18007209e  mov     rcx, [rcx+88h]
0x1800720a5  call    WPP_SF_qqq
0x1800720aa  mov     r8, r15; void *
0x1800720ad  lea     rdx, aCdssamplesinki_8; "CDSSampleSinkInputPin::AddMediaTypePair"
0x1800720b4  mov     rcx, rsi; this
0x1800720b7  call    ?Log@MFDSMediaTypePair@@QEAAXQEBDPEAX@Z; MFDSMediaTypePair::Log(char const * const,void *)
0x1800720bc  mov     edx, [r15+230h]
0x1800720c3  lea     r8, [rbp+guidRepresentation]
0x1800720c7  lea     rcx, [r15+168h]
0x1800720ce  mov     qword ptr [rbp+guidRepresentation.Data1], rsi
0x1800720d2  call    ?SetValue@?$CTSparseBlock@KPEAUSampleSinkEntry@@$0BE@$00@@QEAAJKAEBQEAUSampleSinkEntry@@@Z; CTSparseBlock<ulong,SampleSinkEntry *,20,1>::SetValue(ulong,SampleSinkEntry * const &)
0x1800720d7  test    eax, eax
0x1800720d9  js      short loc_1800720E7
0x1800720db  inc     dword ptr [r15+230h]
0x1800720e2  jmp     loc_180072252
0x1800720e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800720ee  test    rcx, rcx
0x1800720f1  jnz     short loc_18007213A
0x1800720f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800720fa  nop     dword ptr [rax+rax+00h]
0x1800720ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072106  mov     rcx, rax
0x180072109  test    rax, rax
0x18007210c  jz      short loc_18007212C
0x18007210e  mov     rax, [rax]
0x180072111  mov     edx, 7F0h
0x180072116  mov     rax, [rax+8]
0x18007211a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007211f  test    eax, eax
0x180072121  jz      short loc_18007212C
0x180072123  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007212a  jmp     short loc_18007213A
0x18007212c  lea     rcx, qword_1800EB130; this
0x180072133  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007213a  cmp     byte ptr [rcx+8], 0
0x18007213e  mov     edi, 8007000Eh
0x180072143  jz      short loc_18007216A
0x180072145  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007214a  cmp     [rax+7CCh], edi
0x180072150  jz      short loc_18007216A
0x180072152  mov     r9d, edi; int
0x180072155  lea     rdx, aCdssamplesinki_8; "CDSSampleSinkInputPin::AddMediaTypePair"
0x18007215c  mov     r8d, 55Fh; int
0x180072162  mov     rcx, rax; this
0x180072165  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007216a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072171  jb      short loc_180072196
0x180072173  mov     rcx, cs:WPP_GLOBAL_Control
0x18007217a  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x180072181  mov     edx, 74h ; 't'
0x180072186  mov     dword ptr [rsp+40h+var_20], edi
0x18007218a  mov     r9, r15
0x18007218d  mov     rcx, [rcx+10h]
0x180072191  call    WPP_SF_qD
0x180072196  mov     rcx, rsi; this
0x180072199  call    ??_GMFDSMediaTypePair@@QEAAPEAXI@Z; MFDSMediaTypePair::`scalar deleting destructor'(uint)
0x18007219e  jmp     loc_180072252
0x1800721a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800721aa  mov     edi, 8007000Eh
0x1800721af  test    rcx, rcx
0x1800721b2  jnz     short loc_1800721FB
0x1800721b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800721bb  nop     dword ptr [rax+rax+00h]
0x1800721c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800721c7  mov     rcx, rax
0x1800721ca  test    rax, rax
0x1800721cd  jz      short loc_1800721ED
0x1800721cf  mov     rax, [rax]
0x1800721d2  mov     edx, 7F0h
0x1800721d7  mov     rax, [rax+8]
0x1800721db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721e0  test    eax, eax
0x1800721e2  jz      short loc_1800721ED
0x1800721e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800721eb  jmp     short loc_1800721FB
0x1800721ed  lea     rcx, qword_1800EB130; this
0x1800721f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800721fb  cmp     byte ptr [rcx+8], 0
0x1800721ff  jz      short loc_180072226
0x180072201  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072206  cmp     [rax+7CCh], edi
0x18007220c  jz      short loc_180072226
0x18007220e  mov     r9d, edi; int
0x180072211  lea     rdx, aCdssamplesinki_8; "CDSSampleSinkInputPin::AddMediaTypePair"
0x180072218  mov     r8d, 555h; int
0x18007221e  mov     rcx, rax; this
0x180072221  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072226  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007222d  jb      short loc_180072252
0x18007222f  mov     edx, 72h ; 'r'
0x180072234  mov     rcx, cs:WPP_GLOBAL_Control
0x18007223b  mov     dword ptr [rsp+40h+var_20], edi
0x18007223f  mov     rcx, [rcx+10h]
0x180072243  mov     r9, r15
0x180072246  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x18007224d  call    WPP_SF_qD
0x180072252  lea     rcx, [rbp+ppIMediaType]; void *
0x180072256  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x18007225b  lea     rcx, [rbp+arg_10]; this
0x18007225f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180072264  mov     rbx, [rsp+40h+arg_0]
0x180072269  mov     eax, edi
0x18007226b  add     rsp, 40h
0x18007226f  pop     r15
0x180072271  pop     r14
0x180072273  pop     rdi
0x180072274  pop     rsi
0x180072275  pop     rbp
0x180072276  retn
```
