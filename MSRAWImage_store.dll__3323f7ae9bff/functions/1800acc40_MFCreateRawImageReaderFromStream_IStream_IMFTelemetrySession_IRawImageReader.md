# MFCreateRawImageReaderFromStream(IStream *,IMFTelemetrySession *,IRawImageReader * *)

- ea: `0x1800acc40`
- end: `0x1800acd5a`
- name: `?MFCreateRawImageReaderFromStream@@YAJPEAUIStream@@PEAUIMFTelemetrySession@@PEAPEAUIRawImageReader@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct IStream *, struct IMFTelemetrySession *, struct IRawImageReader **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009c120`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a444c`
- `0x1800acc40`

## string_xrefs

- `0x1800acc65`: `MFCreateRawImageReaderFromStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MFCreateRawImageReaderFromStream(
        struct IStream *a1,
        struct IMFTelemetrySession *a2,
        struct IRawImageReader **a3)
{
  int v4; // ebx
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD v8[2]; // [rsp+38h] [rbp-20h] BYREF
  int v9; // [rsp+48h] [rbp-10h]
  struct IStream *v10; // [rsp+60h] [rbp+8h] BYREF
  struct IMFTelemetrySession *v11; // [rsp+68h] [rbp+10h] BYREF
  char v12; // [rsp+78h] [rbp+20h] BYREF

  v11 = a2;
  v10 = a1;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "MFCreateRawImageReaderFromStream", 167);
  v8[0] = "MFCreateRawImageReaderFromStream";
  v8[1] = 0;
  v9 = 15;
  OutputMsg(0, 0xFu, "=>%s", "MFCreateRawImageReaderFromStream");
  v4 = Microsoft::WRL::Details::MakeAndInitialize<CRawImageReader,IRawImageReader,IStream * &,IMFTelemetrySession * &>(
         a3,
         &v10,
         &v11);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, 0, v4);
    }
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFCreateRawImageReaderFromStream", 168, v4);
    }
  }
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v8);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800acc40  mov     rax, rsp
0x1800acc43  mov     [rax+10h], rdx
0x1800acc47  mov     [rax+8], rcx
0x1800acc4b  push    rdi
0x1800acc4c  sub     rsp, 50h
0x1800acc50  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800acc58  mov     [rax+18h], rbx
0x1800acc5c  mov     rbx, r8
0x1800acc5f  mov     r8d, 0A7h; int
0x1800acc65  lea     rdi, aMfcreaterawima; "MFCreateRawImageReaderFromStream"
0x1800acc6c  mov     rdx, rdi; char *
0x1800acc6f  lea     rcx, [rax+20h]; this
0x1800acc73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800acc78  nop
0x1800acc79  mov     [rsp+58h+var_20], rdi
0x1800acc7e  mov     [rsp+58h+var_18], 0
0x1800acc87  mov     edx, 0Fh; unsigned int
0x1800acc8c  mov     [rsp+58h+var_10], edx
0x1800acc90  mov     r9, rdi
0x1800acc93  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x1800acc9a  xor     ecx, ecx; unsigned int
0x1800acc9c  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x1800acca1  nop
0x1800acca2  lea     r8, [rsp+58h+arg_8]
0x1800acca7  lea     rdx, [rsp+58h+arg_0]
0x1800accac  mov     rcx, rbx
0x1800accaf  call    ??$MakeAndInitialize@VCRawImageReader@@UIRawImageReader@@AEAPEAUIStream@@AEAPEAUIMFTelemetrySession@@@Details@WRL@Microsoft@@YAJPEAPEAUIRawImageReader@@AEAPEAUIStream@@AEAPEAUIMFTelemetrySession@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CRawImageReader,IRawImageReader,IStream * &,IMFTelemetrySession * &>(IRawImageReader * *,IStream * &,IMFTelemetrySession * &)
0x1800accb4  mov     ebx, eax
0x1800accb6  test    eax, eax
0x1800accb8  jns     short loc_1800ACD37
0x1800accba  lea     rax, WPP_GLOBAL_Control
0x1800accc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800accc8  cmp     rcx, rax
0x1800acccb  jz      short loc_1800ACCF5
0x1800acccd  test    byte ptr [rcx+1Ch], 1
0x1800accd1  jz      short loc_1800ACCF5
0x1800accd3  cmp     byte ptr [rcx+19h], 4
0x1800accd7  jb      short loc_1800ACCF5
0x1800accd9  mov     edx, 0Ch
0x1800accde  mov     [rsp+58h+var_38], ebx
0x1800acce2  xor     r9d, r9d
0x1800acce5  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800accec  mov     rcx, [rcx+10h]
0x1800accf0  call    WPP_SF_Dd
0x1800accf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800accfc  test    rcx, rcx
0x1800accff  jnz     short loc_1800ACD0F
0x1800acd01  lea     rcx, off_1800E5190; this
0x1800acd08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acd0f  cmp     byte ptr [rcx+8], 0
0x1800acd13  jz      short loc_1800ACD37
0x1800acd15  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800acd1a  cmp     [rax+7CCh], ebx
0x1800acd20  jz      short loc_1800ACD37
0x1800acd22  mov     r9d, ebx; int
0x1800acd25  mov     r8d, 0A8h; int
0x1800acd2b  mov     rdx, rdi; char *
0x1800acd2e  mov     rcx, rax; this
0x1800acd31  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800acd36  nop
0x1800acd37  lea     rcx, [rsp+58h+var_20]; this
0x1800acd3c  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x1800acd41  nop
0x1800acd42  lea     rcx, [rsp+58h+arg_18]; this
0x1800acd47  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800acd4c  mov     eax, ebx
0x1800acd4e  mov     rbx, [rsp+58h+arg_10]
0x1800acd53  add     rsp, 50h
0x1800acd57  pop     rdi
0x1800acd58  retn
```
