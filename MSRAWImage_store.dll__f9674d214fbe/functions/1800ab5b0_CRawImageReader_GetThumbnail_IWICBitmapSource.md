# CRawImageReader::GetThumbnail(IWICBitmapSource * *)

- ea: `0x1800ab5b0`
- end: `0x1800aba35`
- name: `?GetThumbnail@CRawImageReader@@UEAAJPEAPEAUIWICBitmapSource@@@Z`
- size: `1157`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, struct IWICBitmapSource **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001220`
- `0x180002040`
- `0x1800020a0`
- `0x1800020f0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009c41c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a7520`
- `0x1800ab5b0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab96c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab96c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab6b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab6b2`
- `MFPlat!MFGetSystemTime` at `0x1800ab5ec`
- `MFPlat!MFGetSystemTime` at `0x1800ab99c`
- `MFPlat!MFGetSystemTime` at `0x1800ab5ec`
- `MFPlat!MFGetSystemTime` at `0x1800ab99c`

## string_xrefs

- `0x1800ab6f1`: `CRawImageReader::VerifyImageOpened`
- `0x1800ab76f`: `CRawImageReader::VerifyImageOpened`
- `0x1800ab7c9`: `CRawImageReader::VerifyImageOpened`
- `0x1800ab7f0`: `CRawImageReader::VerifyImageOpened`
- `0x1800ab7d8`: `avcore\mf\rawimage\rawimagereader\RawImageReader.h`
- `0x1800ab606`: `CRawImageReader::GetThumbnail`
- `0x1800ab68e`: `CRawImageReader::GetThumbnail`
- `0x1800ab8ab`: `CRawImageReader::GetThumbnail`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRawImageReader::GetThumbnail(CRawImageReader *this, struct IWICBitmapSource **a2)
{
  MFTIME v4; // r15
  int *v5; // r9
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v7; // edi
  unsigned int *v8; // r12
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int *v12; // r9
  struct CallStackContext *v13; // rdi
  int v14; // r15d
  int Thumbnail; // edi
  void ***v16; // rcx
  struct CallStackContext *v17; // rax
  void ***v18; // rcx
  struct CallStackContext *v19; // rax
  int v20; // r8d
  struct IWICBitmapSource **v21; // r14
  void ***v22; // rcx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  MFTIME v26; // rdx
  const char *v27; // r9
  __int64 result; // rax
  int v29; // [rsp+20h] [rbp-B8h]
  int v30; // [rsp+20h] [rbp-B8h]
  char v31; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v32[7]; // [rsp+41h] [rbp-97h] BYREF
  _QWORD v33[2]; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v34[32]; // [rsp+58h] [rbp-80h] BYREF
  int v35[8]; // [rsp+78h] [rbp-60h] BYREF
  char *v36; // [rsp+98h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v33[1] = -2;
  try
  {
    v4 = MFGetSystemTime();
    v33[0] = v4;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v32, "CRawImageReader::GetThumbnail", 399);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(**((_QWORD **)this + 34) + 280LL))(
                                                              *((_QWORD *)this + 34),
                                                              &v36);
      *((_DWORD *)ThreadRelativeContext + 504) = v7;
    }
    v8 = (unsigned int *)((char *)this + 56);
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v34,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
      "CRawImageReader::GetThumbnail",
      v5,
      v29);
    v36 = (char *)this + 64;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    *a2 = 0;
    if ( (unsigned int)dword_1800E50F0 > 4 )
    {
      *(_QWORD *)v35 = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v9,
        (unsigned int)&unk_1800D7617,
        v10,
        v11,
        (__int64)v35);
    }
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v31, "CRawImageReader::VerifyImageOpened", 88);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)v13 + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 34) + 280LL))(
                                            *((_QWORD *)this + 34),
                                            v35);
      *((_DWORD *)v13 + 504) = v14;
      v4 = v33[0];
    }
    Thumbnail = 0;
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v35,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
      "CRawImageReader::VerifyImageOpened",
      v12,
      v30);
    if ( !*((_BYTE *)this + 108) )
    {
      Thumbnail = -2147418113;
      v16 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v17 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v17, "CRawImageReader::VerifyImageOpened", 89, -2147418113);
      }
      CTraceBase::OutputMsg(
        (CRawImageReader *)((char *)this + 56),
        1u,
        1u,
        "%s failed(0x%X) at line %d in file %s",
        "CRawImageReader::VerifyImageOpened",
        -2147418113,
        89,
        "avcore\\mf\\rawimage\\rawimagereader\\RawImageReader.h");
    }
    CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v35);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v31);
    if ( Thumbnail < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v8,
          Thumbnail);
      }
      v18 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v18 + 8) )
        goto LABEL_41;
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v19 + 499) == Thumbnail )
        goto LABEL_41;
      v20 = 411;
      goto LABEL_27;
    }
    v21 = (struct IWICBitmapSource **)((char *)this + 224);
    if ( !*((_QWORD *)this + 28) )
    {
      Thumbnail = CRawImageReader::CreateThumbnail(this);
      if ( Thumbnail < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v8,
            Thumbnail);
        }
        v22 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v22 + 8) )
          goto LABEL_41;
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v19 + 499) == Thumbnail )
          goto LABEL_41;
        v20 = 415;
LABEL_27:
        CallStackContext::TraceFailure(v19, "CRawImageReader::GetThumbnail", v20, Thumbnail);
LABEL_41:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        if ( (unsigned int)dword_1800E50F0 > 4 )
        {
          v33[0] = this;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            v23,
            (unsigned int)&unk_1800D75E1,
            v24,
            v25,
            (__int64)v33);
        }
        v26 = MFGetSystemTime() - v4;
        if ( Thumbnail >= 0 )
        {
          (*(void (__fastcall **)(char *, MFTIME))(*((_QWORD *)this + 93) + 16LL))((char *)this + 744, v26);
        }
        else
        {
          (*(void (__fastcall **)(char *, MFTIME))(*((_QWORD *)this + 102) + 16LL))((char *)this + 816, v26);
          if ( *((int *)this + 147) >= 0 )
            *((_DWORD *)this + 147) = Thumbnail;
        }
        CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v34);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v32);
        return (unsigned int)Thumbnail;
      }
      if ( !*v21 )
        goto LABEL_41;
    }
    Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef((char *)this + 224);
    *a2 = *v21;
    Thumbnail = 0;
    goto LABEL_41;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1C2,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           v27);
  }
  return result;
}

```

## disassembly

```asm
0x1800ab5b0  mov     rax, rsp
0x1800ab5b3  push    rdi
0x1800ab5b4  push    r12
0x1800ab5b6  push    r13
0x1800ab5b8  push    r14
0x1800ab5ba  push    r15
0x1800ab5bc  sub     rsp, 0B0h
0x1800ab5c3  mov     [rsp+0D8h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800ab5cc  mov     [rax+18h], rbx
0x1800ab5d0  mov     [rax+20h], rsi
0x1800ab5d4  mov     rax, cs:__security_cookie
0x1800ab5db  xor     rax, rsp
0x1800ab5de  mov     [rsp+0D8h+var_30], rax
0x1800ab5e6  mov     r13, rdx
0x1800ab5e9  mov     rsi, rcx
0x1800ab5ec  call    cs:__imp_MFGetSystemTime
0x1800ab5f3  nop     dword ptr [rax+rax+00h]
0x1800ab5f8  mov     r15, rax
0x1800ab5fb  mov     [rsp+0D8h+var_90], rax
0x1800ab600  mov     r8d, 18Fh; int
0x1800ab606  lea     rdx, aCrawimagereade_12; "CRawImageReader::GetThumbnail"
0x1800ab60d  lea     rcx, [rsp+0D8h+var_97]; this
0x1800ab612  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ab617  nop
0x1800ab618  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab61f  cmp     byte ptr [rcx+8], 0
0x1800ab623  jz      short loc_1800AB67E
0x1800ab625  cmp     qword ptr [rsi+110h], 0
0x1800ab62d  jz      short loc_1800AB67E
0x1800ab62f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab634  mov     rbx, rax
0x1800ab637  mov     rcx, [rsi+110h]
0x1800ab63e  mov     rdx, [rcx]
0x1800ab641  mov     rax, [rdx+128h]
0x1800ab648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab64d  mov     edi, eax
0x1800ab64f  mov     rcx, [rsi+110h]
0x1800ab656  mov     rdx, [rcx]
0x1800ab659  mov     rax, [rdx+118h]
0x1800ab660  lea     rdx, [rsp+0D8h+var_40]
0x1800ab668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab66d  movups  xmm0, xmmword ptr [rax]
0x1800ab670  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800ab678  mov     [rbx+7E0h], edi
0x1800ab67e  lea     r12, [rsi+38h]
0x1800ab682  mov     rax, rsi
0x1800ab685  neg     rax
0x1800ab688  sbb     r14, r14
0x1800ab68b  and     r14, r12
0x1800ab68e  lea     r8, aCrawimagereade_12; "CRawImageReader::GetThumbnail"
0x1800ab695  mov     rdx, r14; struct CTraceBase *
0x1800ab698  lea     rcx, [rsp+0D8h+var_80]; this
0x1800ab69d  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ab6a2  nop
0x1800ab6a3  lea     rbx, [rsi+40h]
0x1800ab6a7  mov     [rsp+0D8h+var_40], rbx
0x1800ab6af  mov     rcx, rbx; lpCriticalSection
0x1800ab6b2  call    cs:__imp_EnterCriticalSection
0x1800ab6b9  nop     dword ptr [rax+rax+00h]
0x1800ab6be  nop
0x1800ab6bf  mov     qword ptr [r13+0], 0
0x1800ab6c7  cmp     cs:dword_1800E50F0, 4
0x1800ab6ce  jbe     short loc_1800AB6EB
0x1800ab6d0  mov     qword ptr [rsp+0D8h+var_60], rsi
0x1800ab6d5  lea     rax, [rsp+0D8h+var_60]
0x1800ab6da  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x1800ab6df  lea     rdx, unk_1800D7617
0x1800ab6e6  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800ab6eb  mov     r8d, 58h ; 'X'; int
0x1800ab6f1  lea     rdx, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800ab6f8  lea     rcx, [rsp+0D8h+var_98]; this
0x1800ab6fd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ab702  nop
0x1800ab703  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab70a  cmp     byte ptr [rcx+8], 0
0x1800ab70e  jz      short loc_1800AB76D
0x1800ab710  cmp     qword ptr [rsi+110h], 0
0x1800ab718  jz      short loc_1800AB76D
0x1800ab71a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab71f  mov     rdi, rax
0x1800ab722  mov     rcx, [rsi+110h]
0x1800ab729  mov     rdx, [rcx]
0x1800ab72c  mov     rax, [rdx+128h]
0x1800ab733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab738  mov     r15d, eax
0x1800ab73b  mov     rcx, [rsi+110h]
0x1800ab742  mov     rdx, [rcx]
0x1800ab745  mov     rax, [rdx+118h]
0x1800ab74c  lea     rdx, [rsp+0D8h+var_60]
0x1800ab751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab756  movups  xmm0, xmmword ptr [rax]
0x1800ab759  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ab761  mov     [rdi+7E0h], r15d
0x1800ab768  mov     r15, [rsp+0D8h+var_90]
0x1800ab76d  xor     edi, edi
0x1800ab76f  lea     r8, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800ab776  mov     rdx, r14; struct CTraceBase *
0x1800ab779  lea     rcx, [rsp+0D8h+var_60]; this
0x1800ab77e  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ab783  nop
0x1800ab784  cmp     [rsi+6Ch], dil
0x1800ab788  jnz     loc_1800AB814
0x1800ab78e  mov     edi, 8000FFFFh
0x1800ab793  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab79a  test    rcx, rcx
0x1800ab79d  jnz     short loc_1800AB7AD
0x1800ab79f  lea     rcx, off_1800E5190; this
0x1800ab7a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab7ad  cmp     byte ptr [rcx+8], 0
0x1800ab7b1  jz      short loc_1800AB7D8
0x1800ab7b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab7b8  cmp     [rax+7CCh], edi
0x1800ab7be  jz      short loc_1800AB7D8
0x1800ab7c0  mov     r9d, edi; int
0x1800ab7c3  mov     r8d, 59h ; 'Y'; int
0x1800ab7c9  lea     rdx, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800ab7d0  mov     rcx, rax; this
0x1800ab7d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab7d8  lea     rax, aAvcoreMfRawima; "avcore\\mf\\rawimage\\rawimagereader\\R"...
0x1800ab7df  mov     [rsp+0D8h+var_A0], rax
0x1800ab7e4  mov     [rsp+0D8h+var_A8], 59h ; 'Y'
0x1800ab7ec  mov     [rsp+0D8h+var_B0], edi
0x1800ab7f0  lea     rax, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800ab7f7  mov     qword ptr [rsp+0D8h+var_B8], rax
0x1800ab7fc  lea     r9, aSFailed0xXAtLi; "%s failed(0x%X) at line %d in file %s"
0x1800ab803  mov     edx, 1; unsigned int
0x1800ab808  mov     r8d, edx; unsigned int
0x1800ab80b  mov     rcx, r12; this
0x1800ab80e  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x1800ab813  nop
0x1800ab814  lea     rcx, [rsp+0D8h+var_60]; this
0x1800ab819  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ab81e  nop
0x1800ab81f  lea     rcx, [rsp+0D8h+var_98]; this
0x1800ab824  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ab829  test    edi, edi
0x1800ab82b  jns     loc_1800AB8BF
0x1800ab831  lea     rax, WPP_GLOBAL_Control
0x1800ab838  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab83f  cmp     rcx, rax
0x1800ab842  jz      short loc_1800AB86D
0x1800ab844  test    byte ptr [rcx+1Ch], 1
0x1800ab848  jz      short loc_1800AB86D
0x1800ab84a  cmp     byte ptr [rcx+19h], 4
0x1800ab84e  jb      short loc_1800AB86D
0x1800ab850  mov     edx, 19h
0x1800ab855  mov     [rsp+0D8h+var_B8], edi
0x1800ab859  mov     r9d, [r12]
0x1800ab85d  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ab864  mov     rcx, [rcx+10h]
0x1800ab868  call    WPP_SF_Dd
0x1800ab86d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab874  test    rcx, rcx
0x1800ab877  jnz     short loc_1800AB887
0x1800ab879  lea     rcx, off_1800E5190; this
0x1800ab880  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab887  cmp     byte ptr [rcx+8], 0
0x1800ab88b  jz      loc_1800AB969
0x1800ab891  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab896  cmp     [rax+7CCh], edi
0x1800ab89c  jz      loc_1800AB969
0x1800ab8a2  mov     r8d, 19Bh; int
0x1800ab8a8  mov     r9d, edi; int
0x1800ab8ab  lea     rdx, aCrawimagereade_12; "CRawImageReader::GetThumbnail"
0x1800ab8b2  mov     rcx, rax; this
0x1800ab8b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab8ba  jmp     loc_1800AB969
0x1800ab8bf  lea     r14, [rsi+0E0h]
0x1800ab8c6  cmp     qword ptr [r14], 0
0x1800ab8ca  jnz     loc_1800AB958
0x1800ab8d0  mov     rcx, rsi; this
0x1800ab8d3  call    ?CreateThumbnail@CRawImageReader@@AEAAJXZ; CRawImageReader::CreateThumbnail(void)
0x1800ab8d8  mov     edi, eax
0x1800ab8da  test    eax, eax
0x1800ab8dc  jns     short loc_1800AB952
0x1800ab8de  lea     rax, WPP_GLOBAL_Control
0x1800ab8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab8ec  cmp     rcx, rax
0x1800ab8ef  jz      short loc_1800AB91A
0x1800ab8f1  test    byte ptr [rcx+1Ch], 1
0x1800ab8f5  jz      short loc_1800AB91A
0x1800ab8f7  cmp     byte ptr [rcx+19h], 4
0x1800ab8fb  jb      short loc_1800AB91A
0x1800ab8fd  mov     edx, 1Ah
0x1800ab902  mov     [rsp+0D8h+var_B8], edi
0x1800ab906  mov     r9d, [r12]
0x1800ab90a  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ab911  mov     rcx, [rcx+10h]
0x1800ab915  call    WPP_SF_Dd
0x1800ab91a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab921  test    rcx, rcx
0x1800ab924  jnz     short loc_1800AB934
0x1800ab926  lea     rcx, off_1800E5190; this
0x1800ab92d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab934  cmp     byte ptr [rcx+8], 0
0x1800ab938  jz      short loc_1800AB969
0x1800ab93a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab93f  cmp     [rax+7CCh], edi
0x1800ab945  jz      short loc_1800AB969
0x1800ab947  mov     r8d, 19Fh
0x1800ab94d  jmp     loc_1800AB8A8
0x1800ab952  cmp     qword ptr [r14], 0
0x1800ab956  jz      short loc_1800AB969
0x1800ab958  mov     rcx, r14
0x1800ab95b  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x1800ab960  mov     rax, [r14]
0x1800ab963  mov     [r13+0], rax
0x1800ab967  xor     edi, edi
0x1800ab969  mov     rcx, rbx; lpCriticalSection
0x1800ab96c  call    cs:__imp_LeaveCriticalSection
0x1800ab973  nop     dword ptr [rax+rax+00h]
0x1800ab978  cmp     cs:dword_1800E50F0, 4
0x1800ab97f  jbe     short loc_1800AB99C
0x1800ab981  mov     [rsp+0D8h+var_90], rsi
0x1800ab986  lea     rax, [rsp+0D8h+var_90]
0x1800ab98b  mov     qword ptr [rsp+0D8h+var_B8], rax
0x1800ab990  lea     rdx, unk_1800D75E1
0x1800ab997  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800ab99c  call    cs:__imp_MFGetSystemTime
0x1800ab9a3  nop     dword ptr [rax+rax+00h]
0x1800ab9a8  mov     rdx, rax
0x1800ab9ab  sub     rdx, r15
0x1800ab9ae  test    edi, edi
0x1800ab9b0  jns     short loc_1800AB9D6
0x1800ab9b2  lea     rcx, [rsi+330h]
0x1800ab9b9  mov     rax, [rcx]
0x1800ab9bc  mov     rax, [rax+10h]
0x1800ab9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab9c5  cmp     dword ptr [rsi+24Ch], 0
0x1800ab9cc  jl      short loc_1800AB9EA
0x1800ab9ce  mov     [rsi+24Ch], edi
0x1800ab9d4  jmp     short loc_1800AB9EA
0x1800ab9d6  lea     rcx, [rsi+2E8h]
0x1800ab9dd  mov     rax, [rcx]
0x1800ab9e0  mov     rax, [rax+10h]
0x1800ab9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab9e9  nop
0x1800ab9ea  lea     rcx, [rsp+0D8h+var_80]; this
0x1800ab9ef  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ab9f4  nop
0x1800ab9f5  lea     rcx, [rsp+0D8h+var_97]; this
0x1800ab9fa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ab9ff  mov     eax, edi
0x1800aba01  jmp     short loc_1800ABA07
0x1800aba03  mov     eax, [rsp+0D8h+var_60]
0x1800aba07  mov     rcx, [rsp+0D8h+var_30]
0x1800aba0f  xor     rcx, rsp; StackCookie
0x1800aba12  call    __security_check_cookie
0x1800aba17  lea     r11, [rsp+0D8h+var_28]
0x1800aba1f  mov     rbx, [r11+40h]
0x1800aba23  mov     rsi, [r11+48h]
0x1800aba27  mov     rsp, r11
0x1800aba2a  pop     r15
0x1800aba2c  pop     r14
0x1800aba2e  pop     r13
0x1800aba30  pop     r12
0x1800aba32  pop     rdi
0x1800aba33  retn
```
