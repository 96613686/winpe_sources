# CRawImageReader::RuntimeClassInitialize(IStream *,IMFTelemetrySession *)

- ea: `0x1800ad600`
- end: `0x1800ad98d`
- name: `?RuntimeClassInitialize@CRawImageReader@@QEAAJPEAUIStream@@PEAUIMFTelemetrySession@@@Z`
- size: `909`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, struct IStream *, struct IMFTelemetrySession *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800a444c`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x180003044`
- `0x180006710`
- `0x18009874c`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a42c0`
- `0x1800a555c`
- `0x1800a8588`
- `0x1800acd7c`
- `0x1800ad600`
- `0x1800b4010`

## string_xrefs

- `0x1800ad63d`: `CRawImageReader::RuntimeClassInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRawImageReader::RuntimeClassInitialize(
        CRawImageReader *this,
        struct IStream *a2,
        struct IMFTelemetrySession *a3)
{
  int *v6; // r9
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v8; // esi
  struct CTraceBase *v9; // rdx
  __int64 v10; // rsi
  int v11; // ebx
  void ***v12; // rcx
  struct CallStackContext *v13; // rax
  int v14; // r8d
  LibRaw *v15; // rax
  __int64 v16; // rax
  void ***v17; // rcx
  void ***v18; // rcx
  __int64 v19; // rdx
  const char *v20; // r9
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-78h]
  _BYTE v23[8]; // [rsp+30h] [rbp-68h] BYREF
  LibRaw *v24[2]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v25[32]; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v24[1] = (LibRaw *)-2LL;
  v24[0] = (LibRaw *)a2;
  try
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v23, "CRawImageReader::RuntimeClassInitialize", 338);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                                                              *((_QWORD *)this + 34),
                                                              v25);
      *((_DWORD *)ThreadRelativeContext + 504) = v8;
    }
    if ( this )
    {
      v9 = (CRawImageReader *)((char *)this + 56);
      v10 = (__int64)this + 56;
    }
    else
    {
      v9 = 0;
      v10 = 56;
    }
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v25,
      v9,
      "CRawImageReader::RuntimeClassInitialize",
      v6,
      v22);
    Microsoft::WRL::ComPtr<IMFTelemetrySession>::operator=((char *)this + 272, a3);
    Microsoft::WRL::ComPtr<IStream>::operator=((char *)this + 256, a2);
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 264);
    v11 = Microsoft::WRL::Details::MakeAndInitialize<CLibrawDataStream,CLibrawDataStream,IStream * &>(
            (char *)this + 264,
            v24);
    if ( v11 >= 0 )
    {
      v24[0] = (LibRaw *)operator new(0xBB520u);
      v15 = LibRaw::LibRaw(v24[0], 0);
      *((_QWORD *)this + 18) = v15;
      if ( !v15 )
      {
        v11 = -2147024882;
        goto LABEL_44;
      }
      *((_QWORD *)v15 + 95885) = this;
      *((_QWORD *)v15 + 95884) = CRawImageReader::EXIF_parser_callback;
      v16 = *((_QWORD *)this + 18);
      *(_QWORD *)(v16 + 767048) = this;
      *(_QWORD *)(v16 + 767040) = CRawImageReader::libraw_dataerror_callback;
      *(_DWORD *)(*((_QWORD *)this + 18) + 5244LL) = 0;
      v11 = CRawImageReader::OpenImage(this);
      if ( v11 >= 0 )
      {
        if ( *((_DWORD *)this + 28) && *((_DWORD *)this + 29) )
          goto LABEL_44;
        *((_QWORD *)this + 14) = 0;
        v11 = CRawImageReader::DecodeImage(this);
        if ( v11 >= 0 )
        {
          v19 = *((_QWORD *)this + 17);
          *((_DWORD *)this + 28) = *(unsigned __int16 *)(v19 + 6);
          *((_DWORD *)this + 29) = *(unsigned __int16 *)(v19 + 4);
          goto LABEL_44;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            v11);
        }
        v18 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v18 + 8) )
          goto LABEL_44;
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v13 + 499) == v11 )
          goto LABEL_44;
        v14 = 357;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *(unsigned int *)v10,
            v11);
        }
        v17 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v17 + 8) )
          goto LABEL_44;
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v13 + 499) == v11 )
          goto LABEL_44;
        v14 = 351;
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
          20,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *(unsigned int *)v10,
          v11);
      }
      v12 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v12 + 8) )
        goto LABEL_44;
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v13 + 499) == v11 )
        goto LABEL_44;
      v14 = 341;
    }
    CallStackContext::TraceFailure(v13, "CRawImageReader::RuntimeClassInitialize", v14, v11);
LABEL_44:
    CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v25);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v23);
    result = (unsigned int)v11;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x16D,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x1800ad600  mov     r11, rsp
0x1800ad603  push    rsi
0x1800ad604  push    rdi
0x1800ad605  push    r13
0x1800ad607  push    r14
0x1800ad609  push    r15
0x1800ad60b  sub     rsp, 70h
0x1800ad60f  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x1800ad617  mov     [r11+20h], rbx
0x1800ad61b  mov     rax, cs:__security_cookie
0x1800ad622  xor     rax, rsp
0x1800ad625  mov     [rsp+98h+var_30], rax
0x1800ad62a  mov     r15, r8
0x1800ad62d  mov     r14, rdx
0x1800ad630  mov     rdi, rcx
0x1800ad633  mov     [r11-60h], rdx
0x1800ad637  mov     r8d, 152h; int
0x1800ad63d  lea     r13, aCrawimagereade_15; "CRawImageReader::RuntimeClassInitialize"
0x1800ad644  mov     rdx, r13; char *
0x1800ad647  lea     rcx, [r11-68h]; this
0x1800ad64b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ad650  nop
0x1800ad651  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ad658  cmp     byte ptr [rcx+8], 0
0x1800ad65c  jz      short loc_1800AD6B4
0x1800ad65e  cmp     qword ptr [rdi+110h], 0
0x1800ad666  jz      short loc_1800AD6B4
0x1800ad668  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ad66d  mov     rbx, rax
0x1800ad670  mov     rcx, [rdi+110h]
0x1800ad677  mov     rdx, [rcx]
0x1800ad67a  mov     rax, [rdx+128h]
0x1800ad681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad686  mov     esi, eax
0x1800ad688  mov     rcx, [rdi+110h]
0x1800ad68f  mov     rdx, [rcx]
0x1800ad692  mov     rax, [rdx+118h]
0x1800ad699  lea     rdx, [rsp+98h+var_50]
0x1800ad69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6a3  movups  xmm0, xmmword ptr [rax]
0x1800ad6a6  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800ad6ae  mov     [rbx+7E0h], esi
0x1800ad6b4  test    rdi, rdi
0x1800ad6b7  jz      short loc_1800AD6C2
0x1800ad6b9  lea     rdx, [rdi+38h]
0x1800ad6bd  mov     rsi, rdx
0x1800ad6c0  jmp     short loc_1800AD6C8
0x1800ad6c2  xor     edx, edx; struct CTraceBase *
0x1800ad6c4  lea     rsi, [rdi+38h]
0x1800ad6c8  mov     r8, r13; char *
0x1800ad6cb  lea     rcx, [rsp+98h+var_50]; this
0x1800ad6d0  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ad6d5  nop
0x1800ad6d6  lea     rcx, [rdi+110h]
0x1800ad6dd  mov     rdx, r15
0x1800ad6e0  call    ??4?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFTelemetrySession@@@Z; Microsoft::WRL::ComPtr<IMFTelemetrySession>::operator=(IMFTelemetrySession *)
0x1800ad6e5  lea     rcx, [rdi+100h]
0x1800ad6ec  mov     rdx, r14
0x1800ad6ef  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800ad6f4  lea     rbx, [rdi+108h]
0x1800ad6fb  mov     rcx, rbx
0x1800ad6fe  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800ad703  lea     rdx, [rsp+98h+var_60]
0x1800ad708  mov     rcx, rbx
0x1800ad70b  call    ??$MakeAndInitialize@VCLibrawDataStream@@V1@AEAPEAUIStream@@@Details@WRL@Microsoft@@YAJPEAPEAVCLibrawDataStream@@AEAPEAUIStream@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CLibrawDataStream,CLibrawDataStream,IStream * &>(CLibrawDataStream * *,IStream * &)
0x1800ad710  mov     ebx, eax
0x1800ad712  test    eax, eax
0x1800ad714  jns     loc_1800AD7A3
0x1800ad71a  lea     rax, WPP_GLOBAL_Control
0x1800ad721  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad728  cmp     rcx, rax
0x1800ad72b  jz      short loc_1800AD755
0x1800ad72d  test    byte ptr [rcx+1Ch], 1
0x1800ad731  jz      short loc_1800AD755
0x1800ad733  cmp     byte ptr [rcx+19h], 4
0x1800ad737  jb      short loc_1800AD755
0x1800ad739  mov     edx, 14h
0x1800ad73e  mov     [rsp+98h+var_78], ebx
0x1800ad742  mov     r9d, [rsi]
0x1800ad745  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ad74c  mov     rcx, [rcx+10h]
0x1800ad750  call    WPP_SF_Dd
0x1800ad755  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad75c  test    rcx, rcx
0x1800ad75f  jnz     short loc_1800AD76F
0x1800ad761  lea     rcx, off_1800E5190; this
0x1800ad768  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad76f  cmp     byte ptr [rcx+8], 0
0x1800ad773  jz      loc_1800AD94D
0x1800ad779  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ad77e  cmp     [rax+7CCh], ebx
0x1800ad784  jz      loc_1800AD94D
0x1800ad78a  mov     r8d, 155h; int
0x1800ad790  mov     r9d, ebx; int
0x1800ad793  mov     rdx, r13; char *
0x1800ad796  mov     rcx, rax; this
0x1800ad799  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ad79e  jmp     loc_1800AD94D
0x1800ad7a3  mov     ecx, 0BB520h; Size
0x1800ad7a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ad7ad  mov     [rsp+98h+var_60], rax
0x1800ad7b2  xor     edx, edx; unsigned int
0x1800ad7b4  mov     rcx, rax; this
0x1800ad7b7  call    ??0LibRaw@@QEAA@I@Z; LibRaw::LibRaw(uint)
0x1800ad7bc  nop
0x1800ad7bd  mov     [rdi+90h], rax
0x1800ad7c4  test    rax, rax
0x1800ad7c7  jnz     short loc_1800AD7D3
0x1800ad7c9  mov     ebx, 8007000Eh
0x1800ad7ce  jmp     loc_1800AD94D
0x1800ad7d3  mov     [rax+0BB468h], rdi
0x1800ad7da  lea     rcx, ?EXIF_parser_callback@CRawImageReader@@SAXPEAXHHHI0_J@Z; CRawImageReader::EXIF_parser_callback(void *,int,int,int,uint,void *,__int64)
0x1800ad7e1  mov     [rax+0BB460h], rcx
0x1800ad7e8  mov     rax, [rdi+90h]
0x1800ad7ef  mov     [rax+0BB448h], rdi
0x1800ad7f6  lea     rcx, ?libraw_dataerror_callback@CRawImageReader@@SAXPEAXPEBDH@Z; CRawImageReader::libraw_dataerror_callback(void *,char const *,int)
0x1800ad7fd  mov     [rax+0BB440h], rcx
0x1800ad804  mov     rax, [rdi+90h]
0x1800ad80b  mov     dword ptr [rax+147Ch], 0
0x1800ad815  mov     rcx, rdi; this
0x1800ad818  call    ?OpenImage@CRawImageReader@@AEAAJXZ; CRawImageReader::OpenImage(void)
0x1800ad81d  mov     ebx, eax
0x1800ad81f  test    eax, eax
0x1800ad821  jns     short loc_1800AD89E
0x1800ad823  lea     rax, WPP_GLOBAL_Control
0x1800ad82a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad831  cmp     rcx, rax
0x1800ad834  jz      short loc_1800AD85E
0x1800ad836  test    byte ptr [rcx+1Ch], 1
0x1800ad83a  jz      short loc_1800AD85E
0x1800ad83c  cmp     byte ptr [rcx+19h], 4
0x1800ad840  jb      short loc_1800AD85E
0x1800ad842  mov     edx, 15h
0x1800ad847  mov     [rsp+98h+var_78], ebx
0x1800ad84b  mov     r9d, [rsi]
0x1800ad84e  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ad855  mov     rcx, [rcx+10h]
0x1800ad859  call    WPP_SF_Dd
0x1800ad85e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad865  test    rcx, rcx
0x1800ad868  jnz     short loc_1800AD878
0x1800ad86a  lea     rcx, off_1800E5190; this
0x1800ad871  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad878  cmp     byte ptr [rcx+8], 0
0x1800ad87c  jz      loc_1800AD94D
0x1800ad882  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ad887  cmp     [rax+7CCh], ebx
0x1800ad88d  jz      loc_1800AD94D
0x1800ad893  mov     r8d, 15Fh
0x1800ad899  jmp     loc_1800AD790
0x1800ad89e  cmp     dword ptr [rdi+70h], 0
0x1800ad8a2  jz      short loc_1800AD8AE
0x1800ad8a4  cmp     dword ptr [rdi+74h], 0
0x1800ad8a8  jnz     loc_1800AD94D
0x1800ad8ae  mov     qword ptr [rdi+70h], 0
0x1800ad8b6  mov     rcx, rdi; this
0x1800ad8b9  call    ?DecodeImage@CRawImageReader@@AEAAJXZ; CRawImageReader::DecodeImage(void)
0x1800ad8be  mov     ebx, eax
0x1800ad8c0  test    eax, eax
0x1800ad8c2  jns     short loc_1800AD938
0x1800ad8c4  lea     rax, WPP_GLOBAL_Control
0x1800ad8cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad8d2  cmp     rcx, rax
0x1800ad8d5  jz      short loc_1800AD900
0x1800ad8d7  test    byte ptr [rcx+1Ch], 1
0x1800ad8db  jz      short loc_1800AD900
0x1800ad8dd  cmp     byte ptr [rcx+19h], 4
0x1800ad8e1  jb      short loc_1800AD900
0x1800ad8e3  mov     edx, 16h
0x1800ad8e8  mov     [rsp+98h+var_78], ebx
0x1800ad8ec  mov     r9d, [rdi+38h]
0x1800ad8f0  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ad8f7  mov     rcx, [rcx+10h]
0x1800ad8fb  call    WPP_SF_Dd
0x1800ad900  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad907  test    rcx, rcx
0x1800ad90a  jnz     short loc_1800AD91A
0x1800ad90c  lea     rcx, off_1800E5190; this
0x1800ad913  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad91a  cmp     byte ptr [rcx+8], 0
0x1800ad91e  jz      short loc_1800AD94D
0x1800ad920  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ad925  cmp     [rax+7CCh], ebx
0x1800ad92b  jz      short loc_1800AD94D
0x1800ad92d  mov     r8d, 165h
0x1800ad933  jmp     loc_1800AD790
0x1800ad938  mov     rdx, [rdi+88h]
0x1800ad93f  movzx   ecx, word ptr [rdx+6]
0x1800ad943  mov     [rdi+70h], ecx
0x1800ad946  movzx   ecx, word ptr [rdx+4]
0x1800ad94a  mov     [rdi+74h], ecx
0x1800ad94d  lea     rcx, [rsp+98h+var_50]; this
0x1800ad952  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ad957  nop
0x1800ad958  lea     rcx, [rsp+98h+var_68]; this
0x1800ad95d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ad962  mov     eax, ebx
0x1800ad964  jmp     short loc_1800AD96A
0x1800ad966  mov     eax, dword ptr [rsp+98h+var_60]
0x1800ad96a  mov     rcx, [rsp+98h+var_30]
0x1800ad96f  xor     rcx, rsp; StackCookie
0x1800ad972  call    __security_check_cookie
0x1800ad977  mov     rbx, [rsp+98h+arg_18]
0x1800ad97f  add     rsp, 70h
0x1800ad983  pop     r15
0x1800ad985  pop     r14
0x1800ad987  pop     r13
0x1800ad989  pop     rdi
0x1800ad98a  pop     rsi
0x1800ad98b  retn
```
