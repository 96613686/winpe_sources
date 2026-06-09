# CRawImageReader::ReportLibrawDataeError(char const *,int)

- ea: `0x1800ad4b4`
- end: `0x1800ad5fa`
- name: `?ReportLibrawDataeError@CRawImageReader@@AEAAXPEBDH@Z`
- size: `326`
- prototype: `void __fastcall(CRawImageReader *__hidden this, const char *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800af770`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x1800ad4b4`
- `0x1800b0018`
- `0x1800b4010`

## string_xrefs

- `0x1800ad4ed`: `CRawImageReader::ReportLibrawDataeError`
- `0x1800ad56e`: `CRawImageReader::ReportLibrawDataeError`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRawImageReader::ReportLibrawDataeError(CRawImageReader *this, const char *a2, char a3)
{
  int *v6; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v8; // ebx
  int v9; // edx
  int v10; // r8d
  const char *v11; // rax
  int v12; // [rsp+20h] [rbp-68h]
  _BYTE v13[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v14; // [rsp+38h] [rbp-50h]
  _BYTE v15[32]; // [rsp+40h] [rbp-48h] BYREF

  v14 = -2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v13, "CRawImageReader::ReportLibrawDataeError", 1125);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v15);
    *((_DWORD *)ThreadRelativeContext + 504) = v8;
  }
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v15,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & -(__int64)(this != 0)),
    "CRawImageReader::ReportLibrawDataeError",
    v6,
    v12);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v11 = "No file name";
    if ( a2 )
      v11 = a2;
    WPP_SF_Dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *((_DWORD *)this + 14), (__int64)v11, a3);
  }
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v15);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
}

```

## disassembly

```asm
0x1800ad4b4  mov     r11, rsp
0x1800ad4b7  push    rsi
0x1800ad4b8  push    rdi
0x1800ad4b9  push    r14
0x1800ad4bb  sub     rsp, 70h
0x1800ad4bf  mov     qword ptr [r11-50h], 0FFFFFFFFFFFFFFFEh
0x1800ad4c7  mov     [r11+18h], rbx
0x1800ad4cb  mov     [r11+20h], rbp
0x1800ad4cf  mov     rax, cs:__security_cookie
0x1800ad4d6  xor     rax, rsp
0x1800ad4d9  mov     [rsp+88h+var_28], rax
0x1800ad4de  mov     r14d, r8d
0x1800ad4e1  mov     rbp, rdx
0x1800ad4e4  mov     rsi, rcx
0x1800ad4e7  mov     r8d, 465h; int
0x1800ad4ed  lea     rdx, aCrawimagereade_11; "CRawImageReader::ReportLibrawDataeError"
0x1800ad4f4  lea     rcx, [r11-58h]; this
0x1800ad4f8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ad4fd  nop
0x1800ad4fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ad505  cmp     byte ptr [rcx+8], 0
0x1800ad509  jz      short loc_1800AD561
0x1800ad50b  cmp     qword ptr [rsi+110h], 0
0x1800ad513  jz      short loc_1800AD561
0x1800ad515  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ad51a  mov     rdi, rax
0x1800ad51d  mov     rcx, [rsi+110h]
0x1800ad524  mov     rdx, [rcx]
0x1800ad527  mov     rax, [rdx+128h]
0x1800ad52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad533  mov     ebx, eax
0x1800ad535  mov     rcx, [rsi+110h]
0x1800ad53c  mov     rdx, [rcx]
0x1800ad53f  mov     rax, [rdx+118h]
0x1800ad546  lea     rdx, [rsp+88h+var_48]
0x1800ad54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad550  movups  xmm0, xmmword ptr [rax]
0x1800ad553  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ad55b  mov     [rdi+7E0h], ebx
0x1800ad561  lea     rbx, [rsi+38h]
0x1800ad565  neg     rsi
0x1800ad568  sbb     rdx, rdx
0x1800ad56b  and     rdx, rbx; struct CTraceBase *
0x1800ad56e  lea     r8, aCrawimagereade_11; "CRawImageReader::ReportLibrawDataeError"
0x1800ad575  lea     rcx, [rsp+88h+var_48]; this
0x1800ad57a  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ad57f  lea     rax, WPP_GLOBAL_Control
0x1800ad586  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad58d  cmp     rcx, rax
0x1800ad590  jz      short loc_1800AD5C2
0x1800ad592  test    byte ptr [rcx+1Ch], 1
0x1800ad596  jz      short loc_1800AD5C2
0x1800ad598  cmp     byte ptr [rcx+19h], 4
0x1800ad59c  jb      short loc_1800AD5C2
0x1800ad59e  lea     rax, aNoFileName; "No file name"
0x1800ad5a5  test    rbp, rbp
0x1800ad5a8  cmovnz  rax, rbp
0x1800ad5ac  mov     [rsp+88h+var_60], r14d
0x1800ad5b1  mov     [rsp+88h+var_68], rax
0x1800ad5b6  mov     r9d, [rbx]
0x1800ad5b9  mov     rcx, [rcx+10h]
0x1800ad5bd  call    WPP_SF_Dsd
0x1800ad5c2  lea     rcx, [rsp+88h+var_48]; this
0x1800ad5c7  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ad5cc  nop
0x1800ad5cd  lea     rcx, [rsp+88h+var_58]; this
0x1800ad5d2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ad5d7  mov     rcx, [rsp+88h+var_28]
0x1800ad5dc  xor     rcx, rsp; StackCookie
0x1800ad5df  call    __security_check_cookie
0x1800ad5e4  lea     r11, [rsp+88h+var_18]
0x1800ad5e9  mov     rbx, [r11+30h]
0x1800ad5ed  mov     rbp, [r11+38h]
0x1800ad5f1  mov     rsp, r11
0x1800ad5f4  pop     r14
0x1800ad5f6  pop     rdi
0x1800ad5f7  pop     rsi
0x1800ad5f8  retn
```
