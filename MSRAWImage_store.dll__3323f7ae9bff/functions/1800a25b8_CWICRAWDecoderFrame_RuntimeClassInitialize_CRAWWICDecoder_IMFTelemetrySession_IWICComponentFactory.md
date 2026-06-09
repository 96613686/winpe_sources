# CWICRAWDecoderFrame::RuntimeClassInitialize(CRAWWICDecoder *,IMFTelemetrySession *,IWICComponentFactory *)

- ea: `0x1800a25b8`
- end: `0x1800a27c5`
- name: `?RuntimeClassInitialize@CWICRAWDecoderFrame@@QEAAJPEAVCRAWWICDecoder@@PEAUIMFTelemetrySession@@PEAUIWICComponentFactory@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(CWICRAWDecoderFrame *__hidden this, struct CRAWWICDecoder *, struct IMFTelemetrySession *, struct IWICComponentFactory *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800975d0`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x1800967ac`
- `0x18009860c`
- `0x18009874c`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009d58c`
- `0x18009e8b8`
- `0x1800a25b8`
- `0x1800a34f8`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall CWICRAWDecoderFrame::RuntimeClassInitialize(
        CWICRAWDecoderFrame *this,
        struct CRAWWICDecoder *a2,
        struct IMFTelemetrySession *a3,
        struct IWICComponentFactory *a4)
{
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v9; // r14d
  int v10; // ebx
  void ***v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  const char *v15; // r9
  __int64 result; // rax
  _BYTE v17[8]; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-70h] BYREF
  int v19; // [rsp+48h] [rbp-60h]
  __int64 v20; // [rsp+50h] [rbp-58h]
  _DWORD v21[4]; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v20 = -2;
  try
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v17,
      "CWICRAWDecoderFrame::RuntimeClassInitialize",
      28);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 20) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 296LL))(*((_QWORD *)this + 20));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 20) + 280LL))(
                                                              *((_QWORD *)this + 20),
                                                              v21);
      *((_DWORD *)ThreadRelativeContext + 504) = v9;
    }
    v18[0] = "CWICRAWDecoderFrame::RuntimeClassInitialize";
    v18[1] = 0;
    v19 = 15;
    OutputMsg(0, 0xFu, "=>%s", "CWICRAWDecoderFrame::RuntimeClassInitialize");
    Microsoft::WRL::ComPtr<IMFTelemetrySession>::operator=((char *)this + 160, a3);
    v10 = CWICRawMetadataBlockReaderBase::RuntimeClassInitialize(this, a4);
    if ( v10 >= 0 )
    {
      *((_DWORD *)this + 18) = *((_DWORD *)a2 + 40);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 64);
      v13 = *((_QWORD *)a2 + 19);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      v14 = *((_QWORD *)a2 + 19);
      *((_QWORD *)this + 8) = v14;
      v10 = 0;
      *((_QWORD *)this + 21) = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v14 + 24LL))(
                                            v14,
                                            v21);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids, 0, v10);
      }
      v11 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v12 + 499) != v10 )
          CallStackContext::TraceFailure(v12, "CWICRAWDecoderFrame::RuntimeClassInitialize", 30, v10);
      }
    }
    CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v18);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v17);
    result = (unsigned int)v10;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x25,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagewicdecoder\\rawimagedecoderframe.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x1800a25b8  push    rbx
0x1800a25ba  push    rsi
0x1800a25bb  push    rdi
0x1800a25bc  push    r12
0x1800a25be  push    r14
0x1800a25c0  push    r15
0x1800a25c2  sub     rsp, 78h
0x1800a25c6  mov     [rsp+0A8h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800a25cf  mov     rax, cs:__security_cookie
0x1800a25d6  xor     rax, rsp
0x1800a25d9  mov     [rsp+0A8h+var_40], rax
0x1800a25de  mov     r12, r9
0x1800a25e1  mov     r15, r8
0x1800a25e4  mov     rsi, rdx
0x1800a25e7  mov     rdi, rcx
0x1800a25ea  mov     r8d, 1Ch; int
0x1800a25f0  lea     r14, aCwicrawdecoder_7; "CWICRAWDecoderFrame::RuntimeClassInitia"...
0x1800a25f7  mov     rdx, r14; char *
0x1800a25fa  lea     rcx, [rsp+0A8h+var_78]; this
0x1800a25ff  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a2604  nop
0x1800a2605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a260c  cmp     byte ptr [rcx+8], 0
0x1800a2610  jz      short loc_1800A2671
0x1800a2612  cmp     qword ptr [rdi+0A0h], 0
0x1800a261a  jz      short loc_1800A2671
0x1800a261c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a2621  mov     rbx, rax
0x1800a2624  mov     rcx, [rdi+0A0h]
0x1800a262b  mov     rdx, [rcx]
0x1800a262e  mov     rax, [rdx+128h]
0x1800a2635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a263a  mov     r14d, eax
0x1800a263d  mov     rcx, [rdi+0A0h]
0x1800a2644  mov     rdx, [rcx]
0x1800a2647  mov     rax, [rdx+118h]
0x1800a264e  lea     rdx, [rsp+0A8h+var_50]
0x1800a2653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2658  movups  xmm0, xmmword ptr [rax]
0x1800a265b  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800a2663  mov     [rbx+7E0h], r14d
0x1800a266a  lea     r14, aCwicrawdecoder_7; "CWICRAWDecoderFrame::RuntimeClassInitia"...
0x1800a2671  mov     [rsp+0A8h+var_70], r14
0x1800a2676  mov     [rsp+0A8h+var_68], 0
0x1800a267f  mov     edx, 0Fh; unsigned int
0x1800a2684  mov     [rsp+0A8h+var_60], edx
0x1800a2688  mov     r9, r14
0x1800a268b  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x1800a2692  xor     ecx, ecx; unsigned int
0x1800a2694  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x1800a2699  nop
0x1800a269a  lea     rcx, [rdi+0A0h]
0x1800a26a1  mov     rdx, r15
0x1800a26a4  call    ??4?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFTelemetrySession@@@Z; Microsoft::WRL::ComPtr<IMFTelemetrySession>::operator=(IMFTelemetrySession *)
0x1800a26a9  mov     rdx, r12; struct IWICComponentFactory *
0x1800a26ac  mov     rcx, rdi; this
0x1800a26af  call    ?RuntimeClassInitialize@CWICRawMetadataBlockReaderBase@@QEAAJPEAUIWICComponentFactory@@@Z; CWICRawMetadataBlockReaderBase::RuntimeClassInitialize(IWICComponentFactory *)
0x1800a26b4  mov     ebx, eax
0x1800a26b6  test    eax, eax
0x1800a26b8  jns     short loc_1800A2738
0x1800a26ba  lea     rax, WPP_GLOBAL_Control
0x1800a26c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a26c8  cmp     rcx, rax
0x1800a26cb  jz      short loc_1800A26F5
0x1800a26cd  test    byte ptr [rcx+1Ch], 1
0x1800a26d1  jz      short loc_1800A26F5
0x1800a26d3  cmp     byte ptr [rcx+19h], 4
0x1800a26d7  jb      short loc_1800A26F5
0x1800a26d9  mov     edx, 0Ah
0x1800a26de  mov     [rsp+0A8h+var_88], ebx
0x1800a26e2  xor     r9d, r9d
0x1800a26e5  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a26ec  mov     rcx, [rcx+10h]
0x1800a26f0  call    WPP_SF_Dd
0x1800a26f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a26fc  test    rcx, rcx
0x1800a26ff  jnz     short loc_1800A270F
0x1800a2701  lea     rcx, off_1800E5190; this
0x1800a2708  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a270f  cmp     byte ptr [rcx+8], 0
0x1800a2713  jz      short loc_1800A278C
0x1800a2715  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a271a  cmp     [rax+7CCh], ebx
0x1800a2720  jz      short loc_1800A278C
0x1800a2722  mov     r9d, ebx; int
0x1800a2725  mov     r8d, 1Eh; int
0x1800a272b  mov     rdx, r14; char *
0x1800a272e  mov     rcx, rax; this
0x1800a2731  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a2736  jmp     short loc_1800A278C
0x1800a2738  mov     eax, [rsi+0A0h]
0x1800a273e  mov     [rdi+48h], eax
0x1800a2741  lea     rcx, [rdi+40h]
0x1800a2745  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a274a  nop
0x1800a274b  mov     rcx, [rsi+98h]
0x1800a2752  test    rcx, rcx
0x1800a2755  jz      short loc_1800A2764
0x1800a2757  mov     rax, [rcx]
0x1800a275a  mov     rax, [rax+8]
0x1800a275e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2763  nop
0x1800a2764  mov     rcx, [rsi+98h]
0x1800a276b  mov     [rdi+40h], rcx
0x1800a276f  xor     ebx, ebx
0x1800a2771  mov     rax, [rcx]
0x1800a2774  lea     rdx, [rsp+0A8h+var_50]
0x1800a2779  mov     rax, [rax+18h]
0x1800a277d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2782  mov     rcx, [rax]
0x1800a2785  mov     [rdi+0A8h], rcx
0x1800a278c  lea     rcx, [rsp+0A8h+var_70]; this
0x1800a2791  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x1800a2796  nop
0x1800a2797  lea     rcx, [rsp+0A8h+var_78]; this
0x1800a279c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a27a1  mov     eax, ebx
0x1800a27a3  jmp     short loc_1800A27A9
0x1800a27a5  mov     eax, [rsp+0A8h+var_50]
0x1800a27a9  mov     rcx, [rsp+0A8h+var_40]
0x1800a27ae  xor     rcx, rsp; StackCookie
0x1800a27b1  call    __security_check_cookie
0x1800a27b6  add     rsp, 78h
0x1800a27ba  pop     r15
0x1800a27bc  pop     r14
0x1800a27be  pop     r12
0x1800a27c0  pop     rdi
0x1800a27c1  pop     rsi
0x1800a27c2  pop     rbx
0x1800a27c3  retn
```
