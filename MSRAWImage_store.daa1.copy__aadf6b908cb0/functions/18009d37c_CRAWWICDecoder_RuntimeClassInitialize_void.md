# CRAWWICDecoder::RuntimeClassInitialize(void)

- ea: `0x18009d37c`
- end: `0x18009d586`
- name: `?RuntimeClassInitialize@CRAWWICDecoder@@QEAAJXZ`
- size: `522`
- prototype: `__int64 __fastcall(CRAWWICDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009583c`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009860c`
- `0x18009879c`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009d37c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceFromApp` at `0x18009d48b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceFromApp` at `0x18009d48b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRAWWICDecoder::RuntimeClassInitialize(CRAWWICDecoder *this)
{
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v3; // esi
  int v4; // ebx
  void ***v5; // rcx
  struct CallStackContext *v6; // rax
  const char *v7; // r9
  __int64 result; // rax
  _BYTE v9[4]; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v10[2]; // [rsp+38h] [rbp-50h] BYREF
  int v11; // [rsp+48h] [rbp-40h]
  __int64 v12; // [rsp+50h] [rbp-38h]
  GUID *v13; // [rsp+58h] [rbp-30h] BYREF
  __int128 v14; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v12 = -2;
  try
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v9, "CRAWWICDecoder::RuntimeClassInitialize", 300);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 21) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 296LL))(*((_QWORD *)this + 21));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, GUID **))(**((_QWORD **)this + 21) + 280LL))(
                                                              *((_QWORD *)this + 21),
                                                              &v13);
      *((_DWORD *)ThreadRelativeContext + 504) = v3;
    }
    v10[0] = "CRAWWICDecoder::RuntimeClassInitialize";
    v10[1] = 0;
    v11 = 15;
    OutputMsg(0, 0xFu, "=>%s", "CRAWWICDecoder::RuntimeClassInitialize");
    v14 = 0;
    v13 = &IID_IWICComponentFactory;
    v4 = CoCreateInstanceFromApp(&CLSID_WICImagingFactory2, 0, 1, 0, 1, &v13);
    if ( v4 >= 0 )
    {
      Microsoft::WRL::ComPtr<IWICComponentFactory>::operator=((char *)this + 144, v14);
      if ( (_QWORD)v14 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 16LL))(v14);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids, 0, v4);
      }
      v5 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v5 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v5 + 8) )
      {
        v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
        if ( *((_DWORD *)v6 + 499) != v4 )
          CallStackContext::TraceFailure(v6, "CRAWWICDecoder::RuntimeClassInitialize", 304, v4);
      }
    }
    CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v10);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v9);
    result = (unsigned int)v4;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x137,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagewicdecoder\\rawimagedecoder.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18009d37c  mov     r11, rsp
0x18009d37f  push    r15
0x18009d381  sub     rsp, 80h
0x18009d388  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x18009d390  mov     [r11+10h], rbx
0x18009d394  mov     [r11+18h], rsi
0x18009d398  mov     [r11+20h], rdi
0x18009d39c  mov     rax, cs:__security_cookie
0x18009d3a3  xor     rax, rsp
0x18009d3a6  mov     [rsp+88h+var_18], rax
0x18009d3ab  mov     rdi, rcx
0x18009d3ae  mov     r8d, 12Ch; int
0x18009d3b4  lea     r15, aCrawwicdecoder_7; "CRAWWICDecoder::RuntimeClassInitialize"
0x18009d3bb  mov     rdx, r15; char *
0x18009d3be  lea     rcx, [r11-58h]; this
0x18009d3c2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009d3c7  nop
0x18009d3c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009d3cf  cmp     byte ptr [rcx+8], 0
0x18009d3d3  jz      short loc_18009D42B
0x18009d3d5  cmp     qword ptr [rdi+0A8h], 0
0x18009d3dd  jz      short loc_18009D42B
0x18009d3df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d3e4  mov     rbx, rax
0x18009d3e7  mov     rcx, [rdi+0A8h]
0x18009d3ee  mov     rdx, [rcx]
0x18009d3f1  mov     rax, [rdx+128h]
0x18009d3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d3fd  mov     esi, eax
0x18009d3ff  mov     rcx, [rdi+0A8h]
0x18009d406  mov     rdx, [rcx]
0x18009d409  mov     rax, [rdx+118h]
0x18009d410  lea     rdx, [rsp+88h+var_30]
0x18009d415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d41a  movups  xmm0, xmmword ptr [rax]
0x18009d41d  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x18009d425  mov     [rbx+7E0h], esi
0x18009d42b  mov     [rsp+88h+var_50], r15
0x18009d430  mov     [rsp+88h+var_48], 0
0x18009d439  mov     edx, 0Fh; unsigned int
0x18009d43e  mov     [rsp+88h+var_40], edx
0x18009d442  mov     r9, r15
0x18009d445  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x18009d44c  xor     ecx, ecx; unsigned int
0x18009d44e  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x18009d453  nop
0x18009d454  xorps   xmm0, xmm0
0x18009d457  movdqu  [rsp+88h+var_28], xmm0
0x18009d45d  lea     rax, IID_IWICComponentFactory
0x18009d464  mov     [rsp+88h+var_30], rax
0x18009d469  lea     rax, [rsp+88h+var_30]
0x18009d46e  mov     [rsp+88h+var_60], rax
0x18009d473  mov     esi, 1
0x18009d478  mov     [rsp+88h+var_68], esi
0x18009d47c  xor     r9d, r9d
0x18009d47f  mov     r8d, esi
0x18009d482  xor     edx, edx
0x18009d484  lea     rcx, CLSID_WICImagingFactory2
0x18009d48b  call    cs:__imp_CoCreateInstanceFromApp
0x18009d492  nop     dword ptr [rax+rax+00h]
0x18009d497  mov     ebx, eax
0x18009d499  test    eax, eax
0x18009d49b  jns     short loc_18009D519
0x18009d49d  lea     rax, WPP_GLOBAL_Control
0x18009d4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d4ab  cmp     rcx, rax
0x18009d4ae  jz      short loc_18009D4D6
0x18009d4b0  test    [rcx+1Ch], sil
0x18009d4b4  jz      short loc_18009D4D6
0x18009d4b6  cmp     byte ptr [rcx+19h], 4
0x18009d4ba  jb      short loc_18009D4D6
0x18009d4bc  lea     edx, [rsi+19h]
0x18009d4bf  mov     [rsp+88h+var_68], ebx
0x18009d4c3  xor     r9d, r9d
0x18009d4c6  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009d4cd  mov     rcx, [rcx+10h]
0x18009d4d1  call    WPP_SF_Dd
0x18009d4d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d4dd  test    rcx, rcx
0x18009d4e0  jnz     short loc_18009D4F0
0x18009d4e2  lea     rcx, off_1800E5190; this
0x18009d4e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d4f0  cmp     byte ptr [rcx+8], 0
0x18009d4f4  jz      short loc_18009D541
0x18009d4f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d4fb  cmp     [rax+7CCh], ebx
0x18009d501  jz      short loc_18009D541
0x18009d503  mov     r9d, ebx; int
0x18009d506  mov     r8d, 130h; int
0x18009d50c  mov     rdx, r15; char *
0x18009d50f  mov     rcx, rax; this
0x18009d512  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009d517  jmp     short loc_18009D541
0x18009d519  lea     rcx, [rdi+90h]
0x18009d520  mov     rdx, qword ptr [rsp+88h+var_28]
0x18009d525  call    ??4?$ComPtr@UIWICComponentFactory@@@WRL@Microsoft@@QEAAAEAV012@PEAUIWICComponentFactory@@@Z; Microsoft::WRL::ComPtr<IWICComponentFactory>::operator=(IWICComponentFactory *)
0x18009d52a  mov     rcx, qword ptr [rsp+88h+var_28]
0x18009d52f  test    rcx, rcx
0x18009d532  jz      short loc_18009D541
0x18009d534  mov     rax, [rcx]
0x18009d537  mov     rax, [rax+10h]
0x18009d53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d540  nop
0x18009d541  lea     rcx, [rsp+88h+var_50]; this
0x18009d546  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x18009d54b  nop
0x18009d54c  lea     rcx, [rsp+88h+var_58]; this
0x18009d551  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009d556  mov     eax, ebx
0x18009d558  jmp     short loc_18009D55E
0x18009d55a  mov     eax, [rsp+88h+var_54]
0x18009d55e  mov     rcx, [rsp+88h+var_18]
0x18009d563  xor     rcx, rsp; StackCookie
0x18009d566  call    __security_check_cookie
0x18009d56b  lea     r11, [rsp+88h+var_8]
0x18009d573  mov     rbx, [r11+18h]
0x18009d577  mov     rsi, [r11+20h]
0x18009d57b  mov     rdi, [r11+28h]
0x18009d57f  mov     rsp, r11
0x18009d582  pop     r15
0x18009d584  retn
```
