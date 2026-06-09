# CRawImageReader::GetImageSize(void)

- ea: `0x1800aac90`
- end: `0x1800aafd1`
- name: `?GetImageSize@CRawImageReader@@UEAA?AUtagSIZE@@XZ`
- size: `833`
- prototype: `struct tagSIZE __fastcall(CRawImageReader *__hidden this)`
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
- `0x1800a2db4`
- `0x1800a34f8`
- `0x1800aac90`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aaf72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aaf72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aad63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aad63`

## string_xrefs

- `0x1800aad75`: `CRawImageReader::VerifyImageOpened`
- `0x1800aadf2`: `CRawImageReader::VerifyImageOpened`
- `0x1800aae5a`: `avcore\mf\rawimage\rawimagereader\RawImageReader.h`
- `0x1800aacc1`: `CRawImageReader::GetImageSize`
- `0x1800aad45`: `CRawImageReader::GetImageSize`
- `0x1800aaf12`: `CRawImageReader::GetImageSize`

## pseudocode

```c
struct tagSIZE __fastcall CRawImageReader::GetImageSize(CRawImageReader *this, _DWORD *a2)
{
  int *v4; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  __int128 v7; // xmm0
  unsigned int *v8; // r15
  int *v9; // r9
  struct CallStackContext *v10; // rsi
  int v11; // edi
  __int128 v12; // xmm0
  int v13; // edi
  void ***v14; // rcx
  struct CallStackContext *v15; // rax
  void ***v16; // rcx
  struct CallStackContext *v17; // rax
  int v19; // [rsp+20h] [rbp-98h]
  int v20; // [rsp+20h] [rbp-98h]
  _BYTE v21[8]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v22[32]; // [rsp+48h] [rbp-70h] BYREF
  _BYTE v23[32]; // [rsp+68h] [rbp-50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v21, "CRawImageReader::GetImageSize", 376);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    v7 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                      *((_QWORD *)this + 34),
                      v23);
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
    *((_OWORD *)ThreadRelativeContext + 125) = v7;
  }
  v8 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v22,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
    "CRawImageReader::GetImageSize",
    v4,
    v19);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ++*((_DWORD *)this + 260);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v21, "CRawImageReader::VerifyImageOpened", 88);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    v12 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                       *((_QWORD *)this + 34),
                       v23);
    *((_DWORD *)v10 + 504) = v11;
    *((_OWORD *)v10 + 125) = v12;
  }
  v13 = 0;
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v23,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
    "CRawImageReader::VerifyImageOpened",
    v9,
    v20);
  if ( !*((_BYTE *)this + 108) )
  {
    v14 = (void ***)CallStackTracing::s_wpInstance;
    v13 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v15 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v15, "CRawImageReader::VerifyImageOpened", 89, -2147418113);
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
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v23);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v21);
  if ( v13 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        *v8,
        *((_DWORD *)this + 28));
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v8, v13);
    }
    v16 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v17 + 499) != v13 )
        CallStackContext::TraceFailure(v17, "CRawImageReader::GetImageSize", 380, v13);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *a2 = *((_DWORD *)this + 28);
  a2[1] = *((_DWORD *)this + 29);
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v22);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v21);
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x1800aac90  mov     [rsp+arg_10], rbx
0x1800aac95  mov     [rsp+arg_18], rbp
0x1800aac9a  push    rsi
0x1800aac9b  push    rdi
0x1800aac9c  push    r12
0x1800aac9e  push    r14
0x1800aaca0  push    r15
0x1800aaca2  sub     rsp, 90h
0x1800aaca9  mov     rax, cs:__security_cookie
0x1800aacb0  xor     rax, rsp
0x1800aacb3  mov     [rsp+0B8h+var_30], rax
0x1800aacbb  mov     r12, rdx
0x1800aacbe  mov     rbp, rcx
0x1800aacc1  lea     rdx, aCrawimagereade_22; "CRawImageReader::GetImageSize"
0x1800aacc8  mov     r8d, 178h; int
0x1800aacce  lea     rcx, [rsp+0B8h+var_78]; this
0x1800aacd3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aacd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aacdf  cmp     byte ptr [rcx+8], 0
0x1800aace3  jz      short loc_1800AAD3B
0x1800aace5  cmp     qword ptr [rbp+110h], 0
0x1800aaced  jz      short loc_1800AAD3B
0x1800aacef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aacf4  mov     rcx, [rbp+110h]
0x1800aacfb  mov     rdi, rax
0x1800aacfe  mov     rax, [rcx]
0x1800aad01  mov     rax, [rax+128h]
0x1800aad08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aad0d  mov     rcx, [rbp+110h]
0x1800aad14  lea     rdx, [rsp+0B8h+var_50]
0x1800aad19  mov     ebx, eax
0x1800aad1b  mov     rax, [rcx]
0x1800aad1e  mov     rax, [rax+118h]
0x1800aad25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aad2a  movups  xmm0, xmmword ptr [rax]
0x1800aad2d  mov     [rdi+7E0h], ebx
0x1800aad33  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800aad3b  mov     rax, rbp
0x1800aad3e  lea     r15, [rbp+38h]
0x1800aad42  neg     rax
0x1800aad45  lea     r8, aCrawimagereade_22; "CRawImageReader::GetImageSize"
0x1800aad4c  lea     rcx, [rsp+0B8h+var_70]; this
0x1800aad51  sbb     r14, r14
0x1800aad54  and     r14, r15
0x1800aad57  mov     rdx, r14; struct CTraceBase *
0x1800aad5a  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800aad5f  lea     rcx, [rbp+40h]; lpCriticalSection
0x1800aad63  call    cs:__imp_EnterCriticalSection
0x1800aad6a  nop     dword ptr [rax+rax+00h]
0x1800aad6f  inc     dword ptr [rbp+410h]
0x1800aad75  lea     rsi, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800aad7c  mov     rdx, rsi; char *
0x1800aad7f  lea     rcx, [rsp+0B8h+var_78]; this
0x1800aad84  mov     r8d, 58h ; 'X'; int
0x1800aad8a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aad8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aad96  cmp     byte ptr [rcx+8], 0
0x1800aad9a  jz      short loc_1800AADF9
0x1800aad9c  cmp     qword ptr [rbp+110h], 0
0x1800aada4  jz      short loc_1800AADF9
0x1800aada6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aadab  mov     rcx, [rbp+110h]
0x1800aadb2  mov     rsi, rax
0x1800aadb5  mov     rax, [rcx]
0x1800aadb8  mov     rax, [rax+128h]
0x1800aadbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aadc4  mov     rcx, [rbp+110h]
0x1800aadcb  lea     rdx, [rsp+0B8h+var_50]
0x1800aadd0  mov     edi, eax
0x1800aadd2  mov     rax, [rcx]
0x1800aadd5  mov     rax, [rax+118h]
0x1800aaddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aade1  movups  xmm0, xmmword ptr [rax]
0x1800aade4  mov     [rsi+7E0h], edi
0x1800aadea  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x1800aadf2  lea     rsi, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800aadf9  mov     r8, rsi; char *
0x1800aadfc  lea     rcx, [rsp+0B8h+var_50]; this
0x1800aae01  mov     rdx, r14; struct CTraceBase *
0x1800aae04  xor     edi, edi
0x1800aae06  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800aae0b  cmp     [rbp+6Ch], dil
0x1800aae0f  jnz     short loc_1800AAE8B
0x1800aae11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aae18  mov     edi, 8000FFFFh
0x1800aae1d  test    rcx, rcx
0x1800aae20  jnz     short loc_1800AAE30
0x1800aae22  lea     rcx, off_1800E5190; this
0x1800aae29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aae30  cmp     byte ptr [rcx+8], 0
0x1800aae34  mov     r14d, 59h ; 'Y'
0x1800aae3a  jz      short loc_1800AAE5A
0x1800aae3c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aae41  cmp     [rax+7CCh], edi
0x1800aae47  jz      short loc_1800AAE5A
0x1800aae49  mov     r9d, edi; int
0x1800aae4c  mov     r8d, r14d; int
0x1800aae4f  mov     rdx, rsi; char *
0x1800aae52  mov     rcx, rax; this
0x1800aae55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aae5a  lea     rax, aAvcoreMfRawima; "avcore\\mf\\rawimage\\rawimagereader\\R"...
0x1800aae61  mov     edx, 1; unsigned int
0x1800aae66  mov     [rsp+0B8h+var_80], rax
0x1800aae6b  lea     r9, aSFailed0xXAtLi; "%s failed(0x%X) at line %d in file %s"
0x1800aae72  mov     [rsp+0B8h+var_88], r14d
0x1800aae77  mov     r8d, edx; unsigned int
0x1800aae7a  mov     [rsp+0B8h+var_90], edi
0x1800aae7e  mov     rcx, r15; this
0x1800aae81  mov     [rsp+0B8h+var_98], rsi
0x1800aae86  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x1800aae8b  lea     rcx, [rsp+0B8h+var_50]; this
0x1800aae90  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800aae95  lea     rcx, [rsp+0B8h+var_78]; this
0x1800aae9a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800aae9f  test    edi, edi
0x1800aaea1  jns     loc_1800AAF29
0x1800aaea7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaeae  lea     rax, WPP_GLOBAL_Control
0x1800aaeb5  cmp     rcx, rax
0x1800aaeb8  jz      short loc_1800AAEE2
0x1800aaeba  test    byte ptr [rcx+1Ch], 1
0x1800aaebe  jz      short loc_1800AAEE2
0x1800aaec0  cmp     byte ptr [rcx+19h], 4
0x1800aaec4  jb      short loc_1800AAEE2
0x1800aaec6  mov     r9d, [r15]
0x1800aaec9  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aaed0  mov     rcx, [rcx+10h]
0x1800aaed4  mov     edx, 17h
0x1800aaed9  mov     dword ptr [rsp+0B8h+var_98], edi
0x1800aaedd  call    WPP_SF_Dd
0x1800aaee2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaee9  test    rcx, rcx
0x1800aaeec  jnz     short loc_1800AAEFC
0x1800aaeee  lea     rcx, off_1800E5190; this
0x1800aaef5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaefc  cmp     byte ptr [rcx+8], 0
0x1800aaf00  jz      short loc_1800AAF6E
0x1800aaf02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aaf07  cmp     [rax+7CCh], edi
0x1800aaf0d  jz      short loc_1800AAF6E
0x1800aaf0f  mov     r9d, edi; int
0x1800aaf12  lea     rdx, aCrawimagereade_22; "CRawImageReader::GetImageSize"
0x1800aaf19  mov     r8d, 17Ch; int
0x1800aaf1f  mov     rcx, rax; this
0x1800aaf22  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aaf27  jmp     short loc_1800AAF6E
0x1800aaf29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaf30  lea     rax, WPP_GLOBAL_Control
0x1800aaf37  cmp     rcx, rax
0x1800aaf3a  jz      short loc_1800AAF6E
0x1800aaf3c  test    byte ptr [rcx+1Ch], 1
0x1800aaf40  jz      short loc_1800AAF6E
0x1800aaf42  cmp     byte ptr [rcx+19h], 4
0x1800aaf46  jb      short loc_1800AAF6E
0x1800aaf48  mov     eax, [rbp+74h]
0x1800aaf4b  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800aaf52  mov     r9d, [r15]
0x1800aaf55  mov     edx, 18h
0x1800aaf5a  mov     rcx, [rcx+10h]
0x1800aaf5e  mov     [rsp+0B8h+var_90], eax
0x1800aaf62  mov     eax, [rbp+70h]
0x1800aaf65  mov     dword ptr [rsp+0B8h+var_98], eax
0x1800aaf69  call    WPP_SF_DDD
0x1800aaf6e  lea     rcx, [rbp+40h]; lpCriticalSection
0x1800aaf72  call    cs:__imp_LeaveCriticalSection
0x1800aaf79  nop     dword ptr [rax+rax+00h]
0x1800aaf7e  mov     ecx, [rbp+70h]
0x1800aaf81  mov     [r12], ecx
0x1800aaf85  mov     ecx, [rbp+74h]
0x1800aaf88  mov     [r12+4], ecx
0x1800aaf8d  lea     rcx, [rsp+0B8h+var_70]; this
0x1800aaf92  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800aaf97  lea     rcx, [rsp+0B8h+var_78]; this
0x1800aaf9c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800aafa1  mov     rax, r12
0x1800aafa4  mov     rcx, [rsp+0B8h+var_30]
0x1800aafac  xor     rcx, rsp; StackCookie
0x1800aafaf  call    __security_check_cookie
0x1800aafb4  lea     r11, [rsp+0B8h+var_28]
0x1800aafbc  mov     rbx, [r11+40h]
0x1800aafc0  mov     rbp, [r11+48h]
0x1800aafc4  mov     rsp, r11
0x1800aafc7  pop     r15
0x1800aafc9  pop     r14
0x1800aafcb  pop     r12
0x1800aafcd  pop     rdi
0x1800aafce  pop     rsi
0x1800aafcf  retn
```
