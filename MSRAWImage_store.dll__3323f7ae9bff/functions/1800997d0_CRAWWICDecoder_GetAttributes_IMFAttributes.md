# CRAWWICDecoder::GetAttributes(IMFAttributes * *)

- ea: `0x1800997d0`
- end: `0x180099a12`
- name: `?GetAttributes@CRAWWICDecoder@@UEAAJPEAPEAUIMFAttributes@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(CRAWWICDecoder *__hidden this, struct IMFAttributes **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x1800967ac`
- `0x18009860c`
- `0x1800997d0`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180099927`
- `MFPlat!MFCreateAttributes` at `0x180099927`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRAWWICDecoder::GetAttributes(CRAWWICDecoder *this, struct IMFAttributes **a2)
{
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v5; // r14d
  HRESULT v6; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  int v9; // r8d
  CallStackTracing *v10; // rcx
  __int64 v11; // rcx
  const char *v12; // r9
  __int64 result; // rax
  _BYTE v14[4]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]
  _QWORD v16[2]; // [rsp+40h] [rbp-38h] BYREF
  int v17; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v15 = -2;
  try
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v14, "CRAWWICDecoder::GetAttributes", 515);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 16) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 296LL))(*((_QWORD *)this + 16));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 16) + 280LL))(
                                                              *((_QWORD *)this + 16),
                                                              v16);
      *((_DWORD *)ThreadRelativeContext + 504) = v5;
    }
    v16[0] = "CRAWWICDecoder::GetAttributes";
    v16[1] = 0;
    v17 = 15;
    OutputMsg(0, 0xFu, "=>%s", "CRAWWICDecoder::GetAttributes");
    if ( a2 )
    {
      if ( *((_QWORD *)this + 19)
        || (Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 152),
            v6 = MFCreateAttributes((IMFAttributes **)this + 19, 2u),
            v6 >= 0) )
      {
        v11 = *((_QWORD *)this + 19);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
        *a2 = (struct IMFAttributes *)*((_QWORD *)this + 19);
        v6 = 0;
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids, 0, v6);
      }
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)&off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v10 + 8) || (v8 = CallStackTracing::GetThreadRelativeContext(v10), *((_DWORD *)v8 + 499) == v6) )
      {
LABEL_26:
        CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v16);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v14);
        return (unsigned int)v6;
      }
      v9 = 519;
    }
    else
    {
      v6 = -2147467261;
      v7 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)&off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v7 + 8) )
        goto LABEL_26;
      v8 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)v8 + 499) == -2147467261 )
        goto LABEL_26;
      v9 = 516;
    }
    CallStackContext::TraceFailure(v8, "CRAWWICDecoder::GetAttributes", v9, v6);
    goto LABEL_26;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x20C,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagewicdecoder\\rawimagedecoder.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800997d0  mov     r11, rsp
0x1800997d3  push    rdi
0x1800997d4  push    r12
0x1800997d6  push    r14
0x1800997d8  sub     rsp, 60h
0x1800997dc  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x1800997e4  mov     [r11+18h], rbx
0x1800997e8  mov     [r11+20h], rsi
0x1800997ec  mov     rax, cs:__security_cookie
0x1800997f3  xor     rax, rsp
0x1800997f6  mov     [rsp+78h+var_20], rax
0x1800997fb  mov     rsi, rdx
0x1800997fe  mov     rdi, rcx
0x180099801  mov     r8d, 203h; int
0x180099807  lea     r12, aCrawwicdecoder_11; "CRAWWICDecoder::GetAttributes"
0x18009980e  mov     rdx, r12; char *
0x180099811  lea     rcx, [r11-48h]; this
0x180099815  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009981a  nop
0x18009981b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180099822  cmp     byte ptr [rcx+8], 0
0x180099826  jz      short loc_180099880
0x180099828  cmp     qword ptr [rdi+80h], 0
0x180099830  jz      short loc_180099880
0x180099832  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099837  mov     rbx, rax
0x18009983a  mov     rcx, [rdi+80h]
0x180099841  mov     rdx, [rcx]
0x180099844  mov     rax, [rdx+128h]
0x18009984b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099850  mov     r14d, eax
0x180099853  mov     rcx, [rdi+80h]
0x18009985a  mov     rdx, [rcx]
0x18009985d  mov     rax, [rdx+118h]
0x180099864  lea     rdx, [rsp+78h+var_38]
0x180099869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009986e  movups  xmm0, xmmword ptr [rax]
0x180099871  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x180099879  mov     [rbx+7E0h], r14d
0x180099880  mov     [rsp+78h+var_38], r12
0x180099885  mov     [rsp+78h+var_30], 0
0x18009988e  mov     edx, 0Fh; unsigned int
0x180099893  mov     [rsp+78h+var_28], edx
0x180099897  mov     r9, r12
0x18009989a  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x1800998a1  xor     ecx, ecx; unsigned int
0x1800998a3  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x1800998a8  nop
0x1800998a9  test    rsi, rsi
0x1800998ac  jnz     short loc_180099901
0x1800998ae  mov     ebx, 80004003h
0x1800998b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800998ba  test    rcx, rcx
0x1800998bd  jnz     short loc_1800998CD
0x1800998bf  lea     rcx, off_1800E5190; this
0x1800998c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800998cd  cmp     byte ptr [rcx+8], 0
0x1800998d1  jz      loc_1800999D1
0x1800998d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800998dc  cmp     [rax+7CCh], ebx
0x1800998e2  jz      loc_1800999D1
0x1800998e8  mov     r8d, 204h; int
0x1800998ee  mov     r9d, ebx; int
0x1800998f1  mov     rdx, r12; char *
0x1800998f4  mov     rcx, rax; this
0x1800998f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800998fc  jmp     loc_1800999D1
0x180099901  cmp     qword ptr [rdi+98h], 0
0x180099909  jnz     loc_1800999AC
0x18009990f  lea     rcx, [rdi+98h]
0x180099916  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009991b  mov     edx, 2; cInitialSize
0x180099920  lea     rcx, [rdi+98h]; ppMFAttributes
0x180099927  call    cs:__imp_MFCreateAttributes
0x18009992e  nop     dword ptr [rax+rax+00h]
0x180099933  mov     ebx, eax
0x180099935  test    eax, eax
0x180099937  jns     short loc_1800999AC
0x180099939  lea     rax, WPP_GLOBAL_Control
0x180099940  mov     rcx, cs:WPP_GLOBAL_Control
0x180099947  cmp     rcx, rax
0x18009994a  jz      short loc_180099974
0x18009994c  test    byte ptr [rcx+1Ch], 1
0x180099950  jz      short loc_180099974
0x180099952  cmp     byte ptr [rcx+19h], 4
0x180099956  jb      short loc_180099974
0x180099958  mov     edx, 25h ; '%'
0x18009995d  mov     [rsp+78h+var_58], ebx
0x180099961  xor     r9d, r9d
0x180099964  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009996b  mov     rcx, [rcx+10h]
0x18009996f  call    WPP_SF_Dd
0x180099974  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009997b  test    rcx, rcx
0x18009997e  jnz     short loc_18009998E
0x180099980  lea     rcx, off_1800E5190; this
0x180099987  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009998e  cmp     byte ptr [rcx+8], 0
0x180099992  jz      short loc_1800999D1
0x180099994  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099999  cmp     [rax+7CCh], ebx
0x18009999f  jz      short loc_1800999D1
0x1800999a1  mov     r8d, 207h
0x1800999a7  jmp     loc_1800998EE
0x1800999ac  mov     rcx, [rdi+98h]
0x1800999b3  test    rcx, rcx
0x1800999b6  jz      short loc_1800999C5
0x1800999b8  mov     rax, [rcx]
0x1800999bb  mov     rax, [rax+8]
0x1800999bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800999c4  nop
0x1800999c5  mov     rax, [rdi+98h]
0x1800999cc  mov     [rsi], rax
0x1800999cf  xor     ebx, ebx
0x1800999d1  lea     rcx, [rsp+78h+var_38]; this
0x1800999d6  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x1800999db  nop
0x1800999dc  lea     rcx, [rsp+78h+var_48]; this
0x1800999e1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800999e6  mov     eax, ebx
0x1800999e8  jmp     short loc_1800999EE
0x1800999ea  mov     eax, [rsp+78h+var_44]
0x1800999ee  mov     rcx, [rsp+78h+var_20]
0x1800999f3  xor     rcx, rsp; StackCookie
0x1800999f6  call    __security_check_cookie
0x1800999fb  lea     r11, [rsp+78h+var_18]
0x180099a00  mov     rbx, [r11+30h]
0x180099a04  mov     rsi, [r11+38h]
0x180099a08  mov     rsp, r11
0x180099a0b  pop     r14
0x180099a0d  pop     r12
0x180099a0f  pop     rdi
0x180099a10  retn
```
