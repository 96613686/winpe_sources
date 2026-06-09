# CRawImageReader::GetXMPMetadata(IStream * *)

- ea: `0x1800aba40`
- end: `0x1800abf4b`
- name: `?GetXMPMetadata@CRawImageReader@@UEAAJPEAPEAUIStream@@@Z`
- size: `1291`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800020f0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a81cc`
- `0x1800aba40`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800abef3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800abef3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800abb30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800abb30`

## string_xrefs

- `0x1800abb4d`: `CRawImageReader::VerifyImageOpened`
- `0x1800abbc9`: `CRawImageReader::VerifyImageOpened`
- `0x1800abc23`: `CRawImageReader::VerifyImageOpened`
- `0x1800abc4a`: `CRawImageReader::VerifyImageOpened`
- `0x1800abc32`: `avcore\mf\rawimage\rawimagereader\RawImageReader.h`
- `0x1800aba82`: `CRawImageReader::GetXMPMetadata`
- `0x1800abb0c`: `CRawImageReader::GetXMPMetadata`
- `0x1800abd04`: `CRawImageReader::GetXMPMetadata`
- `0x1800abee0`: `CRawImageReader::GetXMPMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRawImageReader::GetXMPMetadata(CRawImageReader *this, struct IStream **a2)
{
  int *v4; // r9
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v6; // edi
  unsigned int *v7; // r14
  int *v8; // r9
  struct CallStackContext *v9; // rdi
  int v10; // r15d
  int XMPStream; // edi
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  int v16; // r8d
  CallStackTracing *v17; // rcx
  __int64 v18; // rcx
  CallStackTracing *v19; // rcx
  __int64 v20; // rcx
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  const char *v23; // r9
  __int64 result; // rax
  int v25; // [rsp+20h] [rbp-B8h]
  int v26; // [rsp+20h] [rbp-B8h]
  char v27; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v28[7]; // [rsp+41h] [rbp-97h] BYREF
  __int64 v29; // [rsp+48h] [rbp-90h]
  _BYTE v30[32]; // [rsp+50h] [rbp-88h] BYREF
  _QWORD v31[4]; // [rsp+70h] [rbp-68h] BYREF
  char *v32; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v29 = -2;
  try
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v28, "CRawImageReader::GetXMPMetadata", 804);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(**((_QWORD **)this + 34) + 280LL))(
                                                              *((_QWORD *)this + 34),
                                                              &v32);
      *((_DWORD *)ThreadRelativeContext + 504) = v6;
    }
    v7 = (unsigned int *)((char *)this + 56);
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v30,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
      "CRawImageReader::GetXMPMetadata",
      v4,
      v25);
    v32 = (char *)this + 64;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    ++*((_DWORD *)this + 258);
    *a2 = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v27, "CRawImageReader::VerifyImageOpened", 88);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)v9 + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 34) + 280LL))(
                                           *((_QWORD *)this + 34),
                                           v31);
      *((_DWORD *)v9 + 504) = v10;
    }
    XMPStream = 0;
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v31,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
      "CRawImageReader::VerifyImageOpened",
      v8,
      v26);
    if ( !*((_BYTE *)this + 108) )
    {
      XMPStream = -2147418113;
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)&off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( *((_DWORD *)v13 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v13, "CRawImageReader::VerifyImageOpened", 89, -2147418113);
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
    CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v31);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v27);
    if ( XMPStream >= 0 )
    {
      XMPStream = CRawImageReader::CreateXMPStream(this);
      if ( XMPStream >= 0 )
      {
        v18 = *((_QWORD *)this + 30);
        if ( !v18 )
          goto LABEL_57;
        XMPStream = (*(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v18 + 104LL))(v18, a2);
        if ( XMPStream >= 0 )
        {
          v20 = (__int64)*a2;
          v31[0] = 0;
          XMPStream = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v20 + 40LL))(v20, 0, 0, 0);
          if ( XMPStream < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                72,
                &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                *v7,
                XMPStream);
            }
            v21 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)&off_1800E5190;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              v22 = CallStackTracing::GetThreadRelativeContext(v21);
              if ( *((_DWORD *)v22 + 499) != XMPStream )
                CallStackContext::TraceFailure(v22, "CRawImageReader::GetXMPMetadata", 816, XMPStream);
            }
          }
          goto LABEL_57;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v7,
            XMPStream);
        }
        v19 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)&off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v19 + 8)
          || (v15 = CallStackTracing::GetThreadRelativeContext(v19), *((_DWORD *)v15 + 499) == XMPStream) )
        {
LABEL_57:
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
          CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v30);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v28);
          return (unsigned int)XMPStream;
        }
        v16 = 815;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            70,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *v7,
            XMPStream);
        }
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)&off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v17 + 8) )
          goto LABEL_57;
        v15 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( *((_DWORD *)v15 + 499) == XMPStream )
          goto LABEL_57;
        v16 = 811;
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
          69,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v7,
          XMPStream);
      }
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)&off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v14 + 8) )
        goto LABEL_57;
      v15 = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)v15 + 499) == XMPStream )
        goto LABEL_57;
      v16 = 809;
    }
    CallStackContext::TraceFailure(v15, "CRawImageReader::GetXMPMetadata", v16, XMPStream);
    goto LABEL_57;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x335,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x1800aba40  mov     rax, rsp
0x1800aba43  push    rdi
0x1800aba44  push    r12
0x1800aba46  push    r13
0x1800aba48  push    r14
0x1800aba4a  push    r15
0x1800aba4c  sub     rsp, 0B0h
0x1800aba53  mov     [rsp+0D8h+var_90], 0FFFFFFFFFFFFFFFEh
0x1800aba5c  mov     [rax+18h], rbx
0x1800aba60  mov     [rax+20h], rsi
0x1800aba64  mov     rax, cs:__security_cookie
0x1800aba6b  xor     rax, rsp
0x1800aba6e  mov     [rsp+0D8h+var_38], rax
0x1800aba76  mov     r13, rdx
0x1800aba79  mov     rsi, rcx
0x1800aba7c  mov     r8d, 324h; int
0x1800aba82  lea     rdx, aCrawimagereade_24; "CRawImageReader::GetXMPMetadata"
0x1800aba89  lea     rcx, [rsp+0D8h+var_97]; this
0x1800aba8e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aba93  nop
0x1800aba94  xor     r15d, r15d
0x1800aba97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aba9e  cmp     [rcx+8], r15b
0x1800abaa2  jz      short loc_1800ABAFC
0x1800abaa4  cmp     [rsi+110h], r15
0x1800abaab  jz      short loc_1800ABAFC
0x1800abaad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abab2  mov     rbx, rax
0x1800abab5  mov     rcx, [rsi+110h]
0x1800ababc  mov     rdx, [rcx]
0x1800ababf  mov     rax, [rdx+128h]
0x1800abac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abacb  mov     edi, eax
0x1800abacd  mov     rcx, [rsi+110h]
0x1800abad4  mov     rdx, [rcx]
0x1800abad7  mov     rax, [rdx+118h]
0x1800abade  lea     rdx, [rsp+0D8h+var_48]
0x1800abae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abaeb  movups  xmm0, xmmword ptr [rax]
0x1800abaee  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800abaf6  mov     [rbx+7E0h], edi
0x1800abafc  lea     r14, [rsi+38h]
0x1800abb00  mov     rax, rsi
0x1800abb03  neg     rax
0x1800abb06  sbb     r12, r12
0x1800abb09  and     r12, r14
0x1800abb0c  lea     r8, aCrawimagereade_24; "CRawImageReader::GetXMPMetadata"
0x1800abb13  mov     rdx, r12; struct CTraceBase *
0x1800abb16  lea     rcx, [rsp+0D8h+var_88]; this
0x1800abb1b  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800abb20  nop
0x1800abb21  lea     rbx, [rsi+40h]
0x1800abb25  mov     [rsp+0D8h+var_48], rbx
0x1800abb2d  mov     rcx, rbx; lpCriticalSection
0x1800abb30  call    cs:__imp_EnterCriticalSection
0x1800abb37  nop     dword ptr [rax+rax+00h]
0x1800abb3c  nop
0x1800abb3d  inc     dword ptr [rsi+408h]
0x1800abb43  mov     [r13+0], r15
0x1800abb47  mov     r8d, 58h ; 'X'; int
0x1800abb4d  lea     rdx, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800abb54  lea     rcx, [rsp+0D8h+var_98]; this
0x1800abb59  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800abb5e  nop
0x1800abb5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800abb66  cmp     [rcx+8], r15b
0x1800abb6a  jz      short loc_1800ABBC6
0x1800abb6c  cmp     [rsi+110h], r15
0x1800abb73  jz      short loc_1800ABBC6
0x1800abb75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abb7a  mov     rdi, rax
0x1800abb7d  mov     rcx, [rsi+110h]
0x1800abb84  mov     rdx, [rcx]
0x1800abb87  mov     rax, [rdx+128h]
0x1800abb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abb93  mov     r15d, eax
0x1800abb96  mov     rcx, [rsi+110h]
0x1800abb9d  mov     rdx, [rcx]
0x1800abba0  mov     rax, [rdx+118h]
0x1800abba7  lea     rdx, [rsp+0D8h+var_68]
0x1800abbac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abbb1  movups  xmm0, xmmword ptr [rax]
0x1800abbb4  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800abbbc  mov     [rdi+7E0h], r15d
0x1800abbc3  xor     r15d, r15d
0x1800abbc6  mov     edi, r15d
0x1800abbc9  lea     r8, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800abbd0  mov     rdx, r12; struct CTraceBase *
0x1800abbd3  lea     rcx, [rsp+0D8h+var_68]; this
0x1800abbd8  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800abbdd  nop
0x1800abbde  cmp     [rsi+6Ch], r15b
0x1800abbe2  jnz     loc_1800ABC6E
0x1800abbe8  mov     edi, 8000FFFFh
0x1800abbed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abbf4  test    rcx, rcx
0x1800abbf7  jnz     short loc_1800ABC07
0x1800abbf9  lea     rcx, off_1800E5190; this
0x1800abc00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abc07  cmp     [rcx+8], r15b
0x1800abc0b  jz      short loc_1800ABC32
0x1800abc0d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abc12  cmp     [rax+7CCh], edi
0x1800abc18  jz      short loc_1800ABC32
0x1800abc1a  mov     r9d, edi; int
0x1800abc1d  mov     r8d, 59h ; 'Y'; int
0x1800abc23  lea     rdx, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800abc2a  mov     rcx, rax; this
0x1800abc2d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800abc32  lea     rax, aAvcoreMfRawima; "avcore\\mf\\rawimage\\rawimagereader\\R"...
0x1800abc39  mov     [rsp+0D8h+var_A0], rax
0x1800abc3e  mov     [rsp+0D8h+var_A8], 59h ; 'Y'
0x1800abc46  mov     [rsp+0D8h+var_B0], edi
0x1800abc4a  lea     rax, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800abc51  mov     [rsp+0D8h+var_B8], rax
0x1800abc56  lea     r9, aSFailed0xXAtLi; "%s failed(0x%X) at line %d in file %s"
0x1800abc5d  mov     edx, 1; unsigned int
0x1800abc62  mov     r8d, edx; unsigned int
0x1800abc65  mov     rcx, r14; this
0x1800abc68  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x1800abc6d  nop
0x1800abc6e  lea     rcx, [rsp+0D8h+var_68]; this
0x1800abc73  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800abc78  nop
0x1800abc79  lea     rcx, [rsp+0D8h+var_98]; this
0x1800abc7e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800abc83  test    edi, edi
0x1800abc85  jns     loc_1800ABD18
0x1800abc8b  lea     rax, WPP_GLOBAL_Control
0x1800abc92  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abc99  cmp     rcx, rax
0x1800abc9c  jz      short loc_1800ABCC6
0x1800abc9e  test    byte ptr [rcx+1Ch], 1
0x1800abca2  jz      short loc_1800ABCC6
0x1800abca4  cmp     byte ptr [rcx+19h], 4
0x1800abca8  jb      short loc_1800ABCC6
0x1800abcaa  mov     edx, 45h ; 'E'
0x1800abcaf  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1800abcb3  mov     r9d, [r14]
0x1800abcb6  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800abcbd  mov     rcx, [rcx+10h]
0x1800abcc1  call    WPP_SF_Dd
0x1800abcc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abccd  test    rcx, rcx
0x1800abcd0  jnz     short loc_1800ABCE0
0x1800abcd2  lea     rcx, off_1800E5190; this
0x1800abcd9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abce0  cmp     [rcx+8], r15b
0x1800abce4  jz      loc_1800ABEF0
0x1800abcea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abcef  cmp     [rax+7CCh], edi
0x1800abcf5  jz      loc_1800ABEF0
0x1800abcfb  mov     r8d, 329h; int
0x1800abd01  mov     r9d, edi; int
0x1800abd04  lea     rdx, aCrawimagereade_24; "CRawImageReader::GetXMPMetadata"
0x1800abd0b  mov     rcx, rax; this
0x1800abd0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800abd13  jmp     loc_1800ABEF0
0x1800abd18  mov     rcx, rsi; this
0x1800abd1b  call    ?CreateXMPStream@CRawImageReader@@AEAAJXZ; CRawImageReader::CreateXMPStream(void)
0x1800abd20  mov     edi, eax
0x1800abd22  test    eax, eax
0x1800abd24  jns     short loc_1800ABDA1
0x1800abd26  lea     rax, WPP_GLOBAL_Control
0x1800abd2d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abd34  cmp     rcx, rax
0x1800abd37  jz      short loc_1800ABD61
0x1800abd39  test    byte ptr [rcx+1Ch], 1
0x1800abd3d  jz      short loc_1800ABD61
0x1800abd3f  cmp     byte ptr [rcx+19h], 4
0x1800abd43  jb      short loc_1800ABD61
0x1800abd45  mov     edx, 46h ; 'F'
0x1800abd4a  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1800abd4e  mov     r9d, [r14]
0x1800abd51  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800abd58  mov     rcx, [rcx+10h]
0x1800abd5c  call    WPP_SF_Dd
0x1800abd61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abd68  test    rcx, rcx
0x1800abd6b  jnz     short loc_1800ABD7B
0x1800abd6d  lea     rcx, off_1800E5190; this
0x1800abd74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abd7b  cmp     [rcx+8], r15b
0x1800abd7f  jz      loc_1800ABEF0
0x1800abd85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abd8a  cmp     [rax+7CCh], edi
0x1800abd90  jz      loc_1800ABEF0
0x1800abd96  mov     r8d, 32Bh
0x1800abd9c  jmp     loc_1800ABD01
0x1800abda1  mov     rcx, [rsi+0F0h]
0x1800abda8  test    rcx, rcx
0x1800abdab  jz      loc_1800ABEF0
0x1800abdb1  mov     rax, [rcx]
0x1800abdb4  mov     rdx, r13
0x1800abdb7  mov     rax, [rax+68h]
0x1800abdbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abdc0  mov     edi, eax
0x1800abdc2  test    eax, eax
0x1800abdc4  jns     short loc_1800ABE41
0x1800abdc6  lea     rax, WPP_GLOBAL_Control
0x1800abdcd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abdd4  cmp     rcx, rax
0x1800abdd7  jz      short loc_1800ABE01
0x1800abdd9  test    byte ptr [rcx+1Ch], 1
0x1800abddd  jz      short loc_1800ABE01
0x1800abddf  cmp     byte ptr [rcx+19h], 4
0x1800abde3  jb      short loc_1800ABE01
0x1800abde5  mov     edx, 47h ; 'G'
0x1800abdea  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1800abdee  mov     r9d, [r14]
0x1800abdf1  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800abdf8  mov     rcx, [rcx+10h]
0x1800abdfc  call    WPP_SF_Dd
0x1800abe01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abe08  test    rcx, rcx
0x1800abe0b  jnz     short loc_1800ABE1B
0x1800abe0d  lea     rcx, off_1800E5190; this
0x1800abe14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abe1b  cmp     [rcx+8], r15b
0x1800abe1f  jz      loc_1800ABEF0
0x1800abe25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abe2a  cmp     [rax+7CCh], edi
0x1800abe30  jz      loc_1800ABEF0
0x1800abe36  mov     r8d, 32Fh
0x1800abe3c  jmp     loc_1800ABD01
0x1800abe41  mov     rcx, [r13+0]
0x1800abe45  mov     [rsp+0D8h+var_68], 0
0x1800abe4e  mov     rax, [rcx]
0x1800abe51  xor     r9d, r9d
0x1800abe54  xor     r8d, r8d
0x1800abe57  mov     rdx, [rsp+0D8h+var_68]
0x1800abe5c  mov     rax, [rax+28h]
0x1800abe60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe65  mov     edi, eax
0x1800abe67  test    eax, eax
0x1800abe69  jns     loc_1800ABEF0
0x1800abe6f  lea     rax, WPP_GLOBAL_Control
0x1800abe76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abe7d  cmp     rcx, rax
0x1800abe80  jz      short loc_1800ABEAA
0x1800abe82  test    byte ptr [rcx+1Ch], 1
0x1800abe86  jz      short loc_1800ABEAA
0x1800abe88  cmp     byte ptr [rcx+19h], 4
0x1800abe8c  jb      short loc_1800ABEAA
0x1800abe8e  mov     edx, 48h ; 'H'
0x1800abe93  mov     dword ptr [rsp+0D8h+var_B8], edi
0x1800abe97  mov     r9d, [r14]
0x1800abe9a  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800abea1  mov     rcx, [rcx+10h]
0x1800abea5  call    WPP_SF_Dd
0x1800abeaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abeb1  test    rcx, rcx
0x1800abeb4  jnz     short loc_1800ABEC4
0x1800abeb6  lea     rcx, off_1800E5190; this
0x1800abebd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abec4  cmp     [rcx+8], r15b
0x1800abec8  jz      short loc_1800ABEF0
0x1800abeca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abecf  cmp     [rax+7CCh], edi
0x1800abed5  jz      short loc_1800ABEF0
0x1800abed7  mov     r9d, edi; int
0x1800abeda  mov     r8d, 330h; int
0x1800abee0  lea     rdx, aCrawimagereade_24; "CRawImageReader::GetXMPMetadata"
0x1800abee7  mov     rcx, rax; this
0x1800abeea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800abeef  nop
0x1800abef0  mov     rcx, rbx; lpCriticalSection
0x1800abef3  call    cs:__imp_LeaveCriticalSection
0x1800abefa  nop     dword ptr [rax+rax+00h]
0x1800abeff  nop
0x1800abf00  lea     rcx, [rsp+0D8h+var_88]; this
0x1800abf05  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800abf0a  nop
0x1800abf0b  lea     rcx, [rsp+0D8h+var_97]; this
0x1800abf10  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800abf15  mov     eax, edi
0x1800abf17  jmp     short loc_1800ABF1D
0x1800abf19  mov     eax, dword ptr [rsp+0D8h+var_68]
0x1800abf1d  mov     rcx, [rsp+0D8h+var_38]
0x1800abf25  xor     rcx, rsp; StackCookie
0x1800abf28  call    __security_check_cookie
0x1800abf2d  lea     r11, [rsp+0D8h+var_28]
0x1800abf35  mov     rbx, [r11+40h]
0x1800abf39  mov     rsi, [r11+48h]
0x1800abf3d  mov     rsp, r11
0x1800abf40  pop     r15
0x1800abf42  pop     r14
0x1800abf44  pop     r13
0x1800abf46  pop     r12
0x1800abf48  pop     rdi
0x1800abf49  retn
```
