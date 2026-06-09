# CRawImageReader::GetPreview(IWICBitmapSource * *)

- ea: `0x1800aafe0`
- end: `0x1800ab45b`
- name: `?GetPreview@CRawImageReader@@UEAAJPEAPEAUIWICBitmapSource@@@Z`
- size: `1147`
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
- `0x1800a8df0`
- `0x1800aafe0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab392`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab0e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab0e2`
- `MFPlat!MFGetSystemTime` at `0x1800ab01c`
- `MFPlat!MFGetSystemTime` at `0x1800ab3c2`
- `MFPlat!MFGetSystemTime` at `0x1800ab01c`
- `MFPlat!MFGetSystemTime` at `0x1800ab3c2`

## string_xrefs

- `0x1800ab121`: `CRawImageReader::VerifyImageOpened`
- `0x1800ab19f`: `CRawImageReader::VerifyImageOpened`
- `0x1800ab1f9`: `CRawImageReader::VerifyImageOpened`
- `0x1800ab220`: `CRawImageReader::VerifyImageOpened`
- `0x1800ab208`: `avcore\mf\rawimage\rawimagereader\RawImageReader.h`
- `0x1800ab036`: `CRawImageReader::GetPreview`
- `0x1800ab0be`: `CRawImageReader::GetPreview`
- `0x1800ab2db`: `CRawImageReader::GetPreview`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRawImageReader::GetPreview(CRawImageReader *this, struct IWICBitmapSource **a2)
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
  int v15; // edi
  void ***v16; // rcx
  struct CallStackContext *v17; // rax
  void ***v18; // rcx
  struct CallStackContext *v19; // rax
  int v20; // r8d
  void ***v21; // rcx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  MFTIME v25; // rdx
  const char *v26; // r9
  __int64 result; // rax
  int v28; // [rsp+20h] [rbp-B8h]
  int v29; // [rsp+20h] [rbp-B8h]
  char v30; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v31[7]; // [rsp+41h] [rbp-97h] BYREF
  _QWORD v32[2]; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v33[32]; // [rsp+58h] [rbp-80h] BYREF
  int v34[8]; // [rsp+78h] [rbp-60h] BYREF
  char *v35; // [rsp+98h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v32[1] = -2;
  try
  {
    v4 = MFGetSystemTime();
    v32[0] = v4;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v31, "CRawImageReader::GetPreview", 464);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(**((_QWORD **)this + 34) + 280LL))(
                                                              *((_QWORD *)this + 34),
                                                              &v35);
      *((_DWORD *)ThreadRelativeContext + 504) = v7;
    }
    v8 = (unsigned int *)((char *)this + 56);
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v33,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
      "CRawImageReader::GetPreview",
      v5,
      v28);
    v35 = (char *)this + 64;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    *a2 = 0;
    if ( (unsigned int)dword_1800E50F0 > 4 )
    {
      *(_QWORD *)v34 = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v9,
        (unsigned int)byte_1800D75AD,
        v10,
        v11,
        (__int64)v34);
    }
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v30, "CRawImageReader::VerifyImageOpened", 88);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)v13 + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 34) + 280LL))(
                                            *((_QWORD *)this + 34),
                                            v34);
      *((_DWORD *)v13 + 504) = v14;
      v4 = v32[0];
    }
    v15 = 0;
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v34,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
      "CRawImageReader::VerifyImageOpened",
      v12,
      v29);
    if ( !*((_BYTE *)this + 108) )
    {
      v15 = -2147418113;
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
    CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v34);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v30);
    if ( v15 >= 0 )
    {
      v15 = CRawImageReader::DecodePreview(this);
      if ( v15 >= 0 )
      {
        if ( *((_QWORD *)this + 29) )
        {
          Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef((char *)this + 232);
          *a2 = (struct IWICBitmapSource *)*((_QWORD *)this + 29);
          v15 = 0;
        }
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v8, v15);
      }
      v21 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v21 + 8)
        || (v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21), *((_DWORD *)v19 + 499) == v15) )
      {
LABEL_40:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
        if ( (unsigned int)dword_1800E50F0 > 4 )
        {
          v32[0] = this;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            v22,
            (unsigned int)byte_1800D7579,
            v23,
            v24,
            (__int64)v32);
        }
        v25 = MFGetSystemTime() - v4;
        if ( v15 >= 0 )
        {
          (*(void (__fastcall **)(char *, MFTIME))(*((_QWORD *)this + 111) + 16LL))((char *)this + 888, v25);
        }
        else
        {
          (*(void (__fastcall **)(char *, MFTIME))(*((_QWORD *)this + 120) + 16LL))((char *)this + 960, v25);
          if ( *((int *)this + 148) >= 0 )
            *((_DWORD *)this + 148) = v15;
        }
        CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v33);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v31);
        return (unsigned int)v15;
      }
      v20 = 478;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v8, v15);
      }
      v18 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v18 + 8) )
        goto LABEL_40;
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v19 + 499) == v15 )
        goto LABEL_40;
      v20 = 476;
    }
    CallStackContext::TraceFailure(v19, "CRawImageReader::GetPreview", v20, v15);
    goto LABEL_40;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x200,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x1800aafe0  mov     rax, rsp
0x1800aafe3  push    rdi
0x1800aafe4  push    r12
0x1800aafe6  push    r13
0x1800aafe8  push    r14
0x1800aafea  push    r15
0x1800aafec  sub     rsp, 0B0h
0x1800aaff3  mov     [rsp+0D8h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800aaffc  mov     [rax+18h], rbx
0x1800ab000  mov     [rax+20h], rsi
0x1800ab004  mov     rax, cs:__security_cookie
0x1800ab00b  xor     rax, rsp
0x1800ab00e  mov     [rsp+0D8h+var_30], rax
0x1800ab016  mov     r13, rdx
0x1800ab019  mov     rsi, rcx
0x1800ab01c  call    cs:__imp_MFGetSystemTime
0x1800ab023  nop     dword ptr [rax+rax+00h]
0x1800ab028  mov     r15, rax
0x1800ab02b  mov     [rsp+0D8h+var_90], rax
0x1800ab030  mov     r8d, 1D0h; int
0x1800ab036  lea     rdx, aCrawimagereade_4; "CRawImageReader::GetPreview"
0x1800ab03d  lea     rcx, [rsp+0D8h+var_97]; this
0x1800ab042  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ab047  nop
0x1800ab048  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab04f  cmp     byte ptr [rcx+8], 0
0x1800ab053  jz      short loc_1800AB0AE
0x1800ab055  cmp     qword ptr [rsi+110h], 0
0x1800ab05d  jz      short loc_1800AB0AE
0x1800ab05f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab064  mov     rbx, rax
0x1800ab067  mov     rcx, [rsi+110h]
0x1800ab06e  mov     rdx, [rcx]
0x1800ab071  mov     rax, [rdx+128h]
0x1800ab078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab07d  mov     edi, eax
0x1800ab07f  mov     rcx, [rsi+110h]
0x1800ab086  mov     rdx, [rcx]
0x1800ab089  mov     rax, [rdx+118h]
0x1800ab090  lea     rdx, [rsp+0D8h+var_40]
0x1800ab098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab09d  movups  xmm0, xmmword ptr [rax]
0x1800ab0a0  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800ab0a8  mov     [rbx+7E0h], edi
0x1800ab0ae  lea     r12, [rsi+38h]
0x1800ab0b2  mov     rax, rsi
0x1800ab0b5  neg     rax
0x1800ab0b8  sbb     r14, r14
0x1800ab0bb  and     r14, r12
0x1800ab0be  lea     r8, aCrawimagereade_4; "CRawImageReader::GetPreview"
0x1800ab0c5  mov     rdx, r14; struct CTraceBase *
0x1800ab0c8  lea     rcx, [rsp+0D8h+var_80]; this
0x1800ab0cd  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ab0d2  nop
0x1800ab0d3  lea     rbx, [rsi+40h]
0x1800ab0d7  mov     [rsp+0D8h+var_40], rbx
0x1800ab0df  mov     rcx, rbx; lpCriticalSection
0x1800ab0e2  call    cs:__imp_EnterCriticalSection
0x1800ab0e9  nop     dword ptr [rax+rax+00h]
0x1800ab0ee  nop
0x1800ab0ef  mov     qword ptr [r13+0], 0
0x1800ab0f7  cmp     cs:dword_1800E50F0, 4
0x1800ab0fe  jbe     short loc_1800AB11B
0x1800ab100  mov     qword ptr [rsp+0D8h+var_60], rsi
0x1800ab105  lea     rax, [rsp+0D8h+var_60]
0x1800ab10a  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x1800ab10f  lea     rdx, byte_1800D75AD
0x1800ab116  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800ab11b  mov     r8d, 58h ; 'X'; int
0x1800ab121  lea     rdx, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800ab128  lea     rcx, [rsp+0D8h+var_98]; this
0x1800ab12d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ab132  nop
0x1800ab133  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab13a  cmp     byte ptr [rcx+8], 0
0x1800ab13e  jz      short loc_1800AB19D
0x1800ab140  cmp     qword ptr [rsi+110h], 0
0x1800ab148  jz      short loc_1800AB19D
0x1800ab14a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab14f  mov     rdi, rax
0x1800ab152  mov     rcx, [rsi+110h]
0x1800ab159  mov     rdx, [rcx]
0x1800ab15c  mov     rax, [rdx+128h]
0x1800ab163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab168  mov     r15d, eax
0x1800ab16b  mov     rcx, [rsi+110h]
0x1800ab172  mov     rdx, [rcx]
0x1800ab175  mov     rax, [rdx+118h]
0x1800ab17c  lea     rdx, [rsp+0D8h+var_60]
0x1800ab181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab186  movups  xmm0, xmmword ptr [rax]
0x1800ab189  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ab191  mov     [rdi+7E0h], r15d
0x1800ab198  mov     r15, [rsp+0D8h+var_90]
0x1800ab19d  xor     edi, edi
0x1800ab19f  lea     r8, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800ab1a6  mov     rdx, r14; struct CTraceBase *
0x1800ab1a9  lea     rcx, [rsp+0D8h+var_60]; this
0x1800ab1ae  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ab1b3  nop
0x1800ab1b4  cmp     [rsi+6Ch], dil
0x1800ab1b8  jnz     loc_1800AB244
0x1800ab1be  mov     edi, 8000FFFFh
0x1800ab1c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab1ca  test    rcx, rcx
0x1800ab1cd  jnz     short loc_1800AB1DD
0x1800ab1cf  lea     rcx, off_1800E5190; this
0x1800ab1d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab1dd  cmp     byte ptr [rcx+8], 0
0x1800ab1e1  jz      short loc_1800AB208
0x1800ab1e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab1e8  cmp     [rax+7CCh], edi
0x1800ab1ee  jz      short loc_1800AB208
0x1800ab1f0  mov     r9d, edi; int
0x1800ab1f3  mov     r8d, 59h ; 'Y'; int
0x1800ab1f9  lea     rdx, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800ab200  mov     rcx, rax; this
0x1800ab203  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab208  lea     rax, aAvcoreMfRawima; "avcore\\mf\\rawimage\\rawimagereader\\R"...
0x1800ab20f  mov     [rsp+0D8h+var_A0], rax
0x1800ab214  mov     [rsp+0D8h+var_A8], 59h ; 'Y'
0x1800ab21c  mov     [rsp+0D8h+var_B0], edi
0x1800ab220  lea     rax, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800ab227  mov     qword ptr [rsp+0D8h+var_B8], rax
0x1800ab22c  lea     r9, aSFailed0xXAtLi; "%s failed(0x%X) at line %d in file %s"
0x1800ab233  mov     edx, 1; unsigned int
0x1800ab238  mov     r8d, edx; unsigned int
0x1800ab23b  mov     rcx, r12; this
0x1800ab23e  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x1800ab243  nop
0x1800ab244  lea     rcx, [rsp+0D8h+var_60]; this
0x1800ab249  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ab24e  nop
0x1800ab24f  lea     rcx, [rsp+0D8h+var_98]; this
0x1800ab254  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ab259  test    edi, edi
0x1800ab25b  jns     loc_1800AB2EF
0x1800ab261  lea     rax, WPP_GLOBAL_Control
0x1800ab268  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab26f  cmp     rcx, rax
0x1800ab272  jz      short loc_1800AB29D
0x1800ab274  test    byte ptr [rcx+1Ch], 1
0x1800ab278  jz      short loc_1800AB29D
0x1800ab27a  cmp     byte ptr [rcx+19h], 4
0x1800ab27e  jb      short loc_1800AB29D
0x1800ab280  mov     edx, 1Ch
0x1800ab285  mov     [rsp+0D8h+var_B8], edi
0x1800ab289  mov     r9d, [r12]
0x1800ab28d  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ab294  mov     rcx, [rcx+10h]
0x1800ab298  call    WPP_SF_Dd
0x1800ab29d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab2a4  test    rcx, rcx
0x1800ab2a7  jnz     short loc_1800AB2B7
0x1800ab2a9  lea     rcx, off_1800E5190; this
0x1800ab2b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab2b7  cmp     byte ptr [rcx+8], 0
0x1800ab2bb  jz      loc_1800AB38F
0x1800ab2c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab2c6  cmp     [rax+7CCh], edi
0x1800ab2cc  jz      loc_1800AB38F
0x1800ab2d2  mov     r8d, 1DCh; int
0x1800ab2d8  mov     r9d, edi; int
0x1800ab2db  lea     rdx, aCrawimagereade_4; "CRawImageReader::GetPreview"
0x1800ab2e2  mov     rcx, rax; this
0x1800ab2e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab2ea  jmp     loc_1800AB38F
0x1800ab2ef  mov     rcx, rsi; this
0x1800ab2f2  call    ?DecodePreview@CRawImageReader@@AEAAJXZ; CRawImageReader::DecodePreview(void)
0x1800ab2f7  mov     edi, eax
0x1800ab2f9  test    eax, eax
0x1800ab2fb  jns     short loc_1800AB371
0x1800ab2fd  lea     rax, WPP_GLOBAL_Control
0x1800ab304  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab30b  cmp     rcx, rax
0x1800ab30e  jz      short loc_1800AB339
0x1800ab310  test    byte ptr [rcx+1Ch], 1
0x1800ab314  jz      short loc_1800AB339
0x1800ab316  cmp     byte ptr [rcx+19h], 4
0x1800ab31a  jb      short loc_1800AB339
0x1800ab31c  mov     edx, 1Dh
0x1800ab321  mov     [rsp+0D8h+var_B8], edi
0x1800ab325  mov     r9d, [r12]
0x1800ab329  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800ab330  mov     rcx, [rcx+10h]
0x1800ab334  call    WPP_SF_Dd
0x1800ab339  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab340  test    rcx, rcx
0x1800ab343  jnz     short loc_1800AB353
0x1800ab345  lea     rcx, off_1800E5190; this
0x1800ab34c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab353  cmp     byte ptr [rcx+8], 0
0x1800ab357  jz      short loc_1800AB38F
0x1800ab359  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab35e  cmp     [rax+7CCh], edi
0x1800ab364  jz      short loc_1800AB38F
0x1800ab366  mov     r8d, 1DEh
0x1800ab36c  jmp     loc_1800AB2D8
0x1800ab371  lea     r14, [rsi+0E8h]
0x1800ab378  cmp     qword ptr [r14], 0
0x1800ab37c  jz      short loc_1800AB38F
0x1800ab37e  mov     rcx, r14
0x1800ab381  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x1800ab386  mov     rax, [r14]
0x1800ab389  mov     [r13+0], rax
0x1800ab38d  xor     edi, edi
0x1800ab38f  mov     rcx, rbx; lpCriticalSection
0x1800ab392  call    cs:__imp_LeaveCriticalSection
0x1800ab399  nop     dword ptr [rax+rax+00h]
0x1800ab39e  cmp     cs:dword_1800E50F0, 4
0x1800ab3a5  jbe     short loc_1800AB3C2
0x1800ab3a7  mov     [rsp+0D8h+var_90], rsi
0x1800ab3ac  lea     rax, [rsp+0D8h+var_90]
0x1800ab3b1  mov     qword ptr [rsp+0D8h+var_B8], rax
0x1800ab3b6  lea     rdx, byte_1800D7579
0x1800ab3bd  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800ab3c2  call    cs:__imp_MFGetSystemTime
0x1800ab3c9  nop     dword ptr [rax+rax+00h]
0x1800ab3ce  mov     rdx, rax
0x1800ab3d1  sub     rdx, r15
0x1800ab3d4  test    edi, edi
0x1800ab3d6  jns     short loc_1800AB3FC
0x1800ab3d8  lea     rcx, [rsi+3C0h]
0x1800ab3df  mov     rax, [rcx]
0x1800ab3e2  mov     rax, [rax+10h]
0x1800ab3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab3eb  cmp     dword ptr [rsi+250h], 0
0x1800ab3f2  jl      short loc_1800AB410
0x1800ab3f4  mov     [rsi+250h], edi
0x1800ab3fa  jmp     short loc_1800AB410
0x1800ab3fc  lea     rcx, [rsi+378h]
0x1800ab403  mov     rax, [rcx]
0x1800ab406  mov     rax, [rax+10h]
0x1800ab40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab40f  nop
0x1800ab410  lea     rcx, [rsp+0D8h+var_80]; this
0x1800ab415  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ab41a  nop
0x1800ab41b  lea     rcx, [rsp+0D8h+var_97]; this
0x1800ab420  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ab425  mov     eax, edi
0x1800ab427  jmp     short loc_1800AB42D
0x1800ab429  mov     eax, [rsp+0D8h+var_60]
0x1800ab42d  mov     rcx, [rsp+0D8h+var_30]
0x1800ab435  xor     rcx, rsp; StackCookie
0x1800ab438  call    __security_check_cookie
0x1800ab43d  lea     r11, [rsp+0D8h+var_28]
0x1800ab445  mov     rbx, [r11+40h]
0x1800ab449  mov     rsi, [r11+48h]
0x1800ab44d  mov     rsp, r11
0x1800ab450  pop     r15
0x1800ab452  pop     r14
0x1800ab454  pop     r13
0x1800ab456  pop     r12
0x1800ab458  pop     rdi
0x1800ab459  retn
```
