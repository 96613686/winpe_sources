# CRawImageReader::GetSession(IMFTelemetrySession * *)

- ea: `0x1800ab470`
- end: `0x1800ab59f`
- name: `?GetSession@CRawImageReader@@UEAAJPEAPEAUIMFTelemetrySession@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, struct IMFTelemetrySession **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009c41c`
- `0x1800ab470`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab55e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab55e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab532`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab532`

## string_xrefs

- `0x1800ab492`: `CRawImageReader::GetSession`
- `0x1800ab517`: `CRawImageReader::GetSession`

## pseudocode

```c
__int64 __fastcall CRawImageReader::GetSession(CRawImageReader *this, struct IMFTelemetrySession **a2)
{
  int *v4; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  __int128 v7; // xmm0
  int v9; // [rsp+20h] [rbp-58h]
  _BYTE v10[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v11[32]; // [rsp+38h] [rbp-40h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v10, "CRawImageReader::GetSession", 832);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 33) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 296LL))(*((_QWORD *)this + 33));
    v7 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 33) + 280LL))(
                      *((_QWORD *)this + 33),
                      v11);
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
    *((_OWORD *)ThreadRelativeContext + 125) = v7;
  }
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v11,
    (struct CTraceBase *)(((unsigned __int64)this + 48)
                        & ((unsigned __int128)-(__int128)((unsigned __int64)this - 8) >> 64)),
    "CRawImageReader::GetSession",
    v4,
    v9);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *a2 = 0;
  Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef((char *)this + 264);
  *a2 = (struct IMFTelemetrySession *)*((_QWORD *)this + 33);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v11);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v10);
  return 0;
}

```

## disassembly

```asm
0x1800ab470  mov     [rsp+arg_10], rbx
0x1800ab475  push    rsi
0x1800ab476  push    rdi
0x1800ab477  push    r14
0x1800ab479  sub     rsp, 60h
0x1800ab47d  mov     rax, cs:__security_cookie
0x1800ab484  xor     rax, rsp
0x1800ab487  mov     [rsp+78h+var_20], rax
0x1800ab48c  mov     r14, rdx
0x1800ab48f  mov     rsi, rcx
0x1800ab492  lea     rdx, aCrawimagereade_27; "CRawImageReader::GetSession"
0x1800ab499  mov     r8d, 340h; int
0x1800ab49f  lea     rcx, [rsp+78h+var_48]; this
0x1800ab4a4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ab4a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab4b0  cmp     byte ptr [rcx+8], 0
0x1800ab4b4  jz      short loc_1800AB50C
0x1800ab4b6  cmp     qword ptr [rsi+108h], 0
0x1800ab4be  jz      short loc_1800AB50C
0x1800ab4c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab4c5  mov     rcx, [rsi+108h]
0x1800ab4cc  mov     rdi, rax
0x1800ab4cf  mov     rdx, [rcx]
0x1800ab4d2  mov     rax, [rdx+128h]
0x1800ab4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab4de  mov     rcx, [rsi+108h]
0x1800ab4e5  mov     ebx, eax
0x1800ab4e7  mov     rdx, [rcx]
0x1800ab4ea  mov     rax, [rdx+118h]
0x1800ab4f1  lea     rdx, [rsp+78h+var_40]
0x1800ab4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab4fb  movups  xmm0, xmmword ptr [rax]
0x1800ab4fe  mov     [rdi+7E0h], ebx
0x1800ab504  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ab50c  lea     rcx, [rsi+30h]
0x1800ab510  lea     rax, [rsi-8]
0x1800ab514  neg     rax
0x1800ab517  lea     r8, aCrawimagereade_27; "CRawImageReader::GetSession"
0x1800ab51e  sbb     rdx, rdx
0x1800ab521  and     rdx, rcx; struct CTraceBase *
0x1800ab524  lea     rcx, [rsp+78h+var_40]; this
0x1800ab529  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ab52e  lea     rcx, [rsi+38h]; lpCriticalSection
0x1800ab532  call    cs:__imp_EnterCriticalSection
0x1800ab539  nop     dword ptr [rax+rax+00h]
0x1800ab53e  lea     rbx, [rsi+108h]
0x1800ab545  mov     qword ptr [r14], 0
0x1800ab54c  mov     rcx, rbx
0x1800ab54f  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x1800ab554  mov     rax, [rbx]
0x1800ab557  lea     rcx, [rsi+38h]; lpCriticalSection
0x1800ab55b  mov     [r14], rax
0x1800ab55e  call    cs:__imp_LeaveCriticalSection
0x1800ab565  nop     dword ptr [rax+rax+00h]
0x1800ab56a  lea     rcx, [rsp+78h+var_40]; this
0x1800ab56f  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ab574  lea     rcx, [rsp+78h+var_48]; this
0x1800ab579  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ab57e  xor     eax, eax
0x1800ab580  mov     rcx, [rsp+78h+var_20]
0x1800ab585  xor     rcx, rsp; StackCookie
0x1800ab588  call    __security_check_cookie
0x1800ab58d  mov     rbx, [rsp+78h+arg_10]
0x1800ab595  add     rsp, 60h
0x1800ab599  pop     r14
0x1800ab59b  pop     rdi
0x1800ab59c  pop     rsi
0x1800ab59d  retn
```
