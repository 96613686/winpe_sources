# CDShowTransGraph::ConnectWrapPin(CDShowTransPin *,IMFMediaType *)

- ea: `0x180027748`
- end: `0x180027a7f`
- name: `?ConnectWrapPin@CDShowTransGraph@@QEAAJPEAVCDShowTransPin@@PEAUIMFMediaType@@@Z`
- size: `823`
- prototype: `int(CDShowTransGraph *__hidden this, struct CDShowTransPin *, struct IMFMediaType *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180026fd0`
- `0x1800273b0`

## callees

- `0x180002820`
- `0x1800052c0`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180027748`
- `0x180032a50`
- `0x180051ce4`
- `0x1800c9010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002780d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800278f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800279b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002780d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800278f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800279b3`
- `MFPlat!MFCreateAMMediaTypeFromMFMediaType` at `0x1800277ea`
- `MFPlat!MFCreateAMMediaTypeFromMFMediaType` at `0x1800277ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDShowTransGraph::ConnectWrapPin(
        CDShowTransGraph *this,
        struct CDShowTransPin *a2,
        struct IMFMediaType *a3)
{
  CallStackTracing *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v16; // ebx
  int v18; // [rsp+30h] [rbp-30h] BYREF
  AM_MEDIA_TYPE *ppAMType[3]; // [rsp+38h] [rbp-28h] BYREF
  GUID guidFormatBlockType; // [rsp+50h] [rbp-10h] BYREF
  char v21; // [rsp+98h] [rbp+38h] BYREF

  v18 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "CDShowTransGraph::ConnectWrapPin", 276);
  ppAMType[1] = 0;
  ppAMType[2] = (AM_MEDIA_TYPE *)&v18;
  ppAMType[0] = 0;
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      26,
      WPP_2e42bf41f4ed337060d7f0c10237b0df_Traceguids,
      this,
      a2,
      *((_DWORD *)a2 + 20));
  guidFormatBlockType = GUID_00000000_0000_0000_0000_000000000000;
  v18 = MFCreateAMMediaTypeFromMFMediaType(a3, &guidFormatBlockType, ppAMType);
  if ( v18 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 3) + 40LL))(*((_QWORD *)a2 + 3));
    (*(void (__fastcall **)(struct CDShowTransPin *, struct IMFMediaType *))(*(_QWORD *)a2 + 24LL))(a2, a3);
    if ( *((_DWORD *)a2 + 20) )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, AM_MEDIA_TYPE *))(**((_QWORD **)a2 + 3) + 24LL))(
              *((_QWORD *)a2 + 3),
              *((_QWORD *)a2 + 7),
              ppAMType[0]);
      if ( v18 < 0 )
      {
        v13 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v13);
          if ( v18 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v18 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransGraph::ConnectWrapPin", 299, v18);
        }
        if ( g_wppLevels )
        {
          v9 = 29;
          goto LABEL_40;
        }
      }
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, AM_MEDIA_TYPE *))(**((_QWORD **)a2 + 7) + 24LL))(
              *((_QWORD *)a2 + 7),
              *((_QWORD *)a2 + 3),
              ppAMType[0]);
      if ( v18 < 0 )
      {
        v10 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v11;
          if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
          {
            v10 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v10 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v10 + 8) )
        {
          v12 = CallStackTracing::GetThreadRelativeContext(v10);
          if ( v18 < 0 && *((_DWORD *)v12 + 499) != v18 )
            CallStackContext::TraceFailure(v12, "CDShowTransGraph::ConnectWrapPin", 295, v18);
        }
        if ( g_wppLevels )
        {
          v9 = 28;
          goto LABEL_40;
        }
      }
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( v18 < 0 && *((_DWORD *)v8 + 499) != v18 )
        CallStackContext::TraceFailure(v8, "CDShowTransGraph::ConnectWrapPin", 286, v18);
    }
    if ( g_wppLevels )
    {
      v9 = 27;
LABEL_40:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_2e42bf41f4ed337060d7f0c10237b0df_Traceguids, this, v18);
    }
  }
  v16 = v18;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return v16;
}

```

## disassembly

```asm
0x180027748  mov     [rsp-18h+arg_0], rbx
0x18002774d  mov     [rsp-18h+arg_8], rsi
0x180027752  push    rbp
0x180027753  push    rdi
0x180027754  push    r14
0x180027756  mov     rbp, rsp
0x180027759  sub     rsp, 60h
0x18002775d  mov     r14, r8
0x180027760  mov     rbx, rdx
0x180027763  mov     rsi, rcx
0x180027766  mov     [rbp+var_30], 0
0x18002776d  mov     r8d, 114h; int
0x180027773  lea     rdx, aCdshowtransgra; "CDShowTransGraph::ConnectWrapPin"
0x18002777a  lea     rcx, [rbp+arg_18]; this
0x18002777e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180027783  nop
0x180027784  mov     [rbp+var_20], 0
0x18002778c  lea     rax, [rbp+var_30]
0x180027790  mov     [rbp+var_18], rax
0x180027794  mov     [rbp+ppAMType], 0
0x18002779c  cmp     cs:byte_1800EACCB, 20h ; ' '
0x1800277a3  jb      short loc_1800277D3
0x1800277a5  mov     edx, 1Ah
0x1800277aa  mov     eax, [rbx+50h]
0x1800277ad  mov     [rsp+60h+var_38], eax
0x1800277b1  mov     [rsp+60h+var_40], rbx
0x1800277b6  mov     r9, rsi
0x1800277b9  lea     r8, WPP_2e42bf41f4ed337060d7f0c10237b0df_Traceguids
0x1800277c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277c7  mov     rcx, [rcx+88h]
0x1800277ce  call    WPP_SF_qqD
0x1800277d3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800277da  movdqu  xmmword ptr [rbp+guidFormatBlockType.Data1], xmm0
0x1800277df  lea     r8, [rbp+ppAMType]; ppAMType
0x1800277e3  lea     rdx, [rbp+guidFormatBlockType]; guidFormatBlockType
0x1800277e7  mov     rcx, r14; pMFType
0x1800277ea  call    cs:__imp_MFCreateAMMediaTypeFromMFMediaType
0x1800277f1  nop     dword ptr [rax+rax+00h]
0x1800277f6  mov     [rbp+var_30], eax
0x1800277f9  test    eax, eax
0x1800277fb  jns     loc_18002789D
0x180027801  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027808  test    rcx, rcx
0x18002780b  jnz     short loc_180027854
0x18002780d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027814  nop     dword ptr [rax+rax+00h]
0x180027819  mov     rcx, rax
0x18002781c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027823  test    rax, rax
0x180027826  jz      short loc_180027846
0x180027828  mov     rax, [rax]
0x18002782b  mov     edx, 7F0h
0x180027830  mov     rax, [rax+8]
0x180027834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027839  test    eax, eax
0x18002783b  jz      short loc_180027846
0x18002783d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027844  jmp     short loc_180027854
0x180027846  lea     rcx, qword_1800EB130; this
0x18002784d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027854  cmp     byte ptr [rcx+8], 0
0x180027858  jz      short loc_180027886
0x18002785a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002785f  mov     r9d, [rbp+var_30]; int
0x180027863  test    r9d, r9d
0x180027866  jns     short loc_180027886
0x180027868  cmp     [rax+7CCh], r9d
0x18002786f  jz      short loc_180027886
0x180027871  mov     r8d, 11Eh; int
0x180027877  lea     rdx, aCdshowtransgra; "CDShowTransGraph::ConnectWrapPin"
0x18002787e  mov     rcx, rax; this
0x180027881  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027886  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002788d  jb      loc_180027A5B
0x180027893  mov     edx, 1Bh
0x180027898  jmp     loc_180027A3A
0x18002789d  mov     rcx, [rbx+18h]
0x1800278a1  mov     rax, [rcx]
0x1800278a4  mov     rax, [rax+28h]
0x1800278a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278ad  mov     rax, [rbx]
0x1800278b0  mov     rdx, r14
0x1800278b3  mov     rcx, rbx
0x1800278b6  mov     rax, [rax+18h]
0x1800278ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278bf  mov     r8, [rbp+ppAMType]
0x1800278c3  cmp     dword ptr [rbx+50h], 0
0x1800278c7  jnz     loc_180027988
0x1800278cd  mov     rcx, [rbx+38h]
0x1800278d1  mov     rax, [rcx]
0x1800278d4  mov     rdx, [rbx+18h]
0x1800278d8  mov     rax, [rax+18h]
0x1800278dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278e1  mov     [rbp+var_30], eax
0x1800278e4  test    eax, eax
0x1800278e6  jns     loc_180027A5B
0x1800278ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800278f3  test    rcx, rcx
0x1800278f6  jnz     short loc_18002793F
0x1800278f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800278ff  nop     dword ptr [rax+rax+00h]
0x180027904  mov     rcx, rax
0x180027907  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002790e  test    rax, rax
0x180027911  jz      short loc_180027931
0x180027913  mov     rax, [rax]
0x180027916  mov     edx, 7F0h
0x18002791b  mov     rax, [rax+8]
0x18002791f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027924  test    eax, eax
0x180027926  jz      short loc_180027931
0x180027928  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002792f  jmp     short loc_18002793F
0x180027931  lea     rcx, qword_1800EB130; this
0x180027938  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002793f  cmp     byte ptr [rcx+8], 0
0x180027943  jz      short loc_180027971
0x180027945  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002794a  mov     r9d, [rbp+var_30]; int
0x18002794e  test    r9d, r9d
0x180027951  jns     short loc_180027971
0x180027953  cmp     [rax+7CCh], r9d
0x18002795a  jz      short loc_180027971
0x18002795c  mov     r8d, 127h; int
0x180027962  lea     rdx, aCdshowtransgra; "CDShowTransGraph::ConnectWrapPin"
0x180027969  mov     rcx, rax; this
0x18002796c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027971  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027978  jb      loc_180027A5B
0x18002797e  mov     edx, 1Ch
0x180027983  jmp     loc_180027A3A
0x180027988  mov     rcx, [rbx+18h]
0x18002798c  mov     rax, [rcx]
0x18002798f  mov     rdx, [rbx+38h]
0x180027993  mov     rax, [rax+18h]
0x180027997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002799c  mov     [rbp+var_30], eax
0x18002799f  test    eax, eax
0x1800279a1  jns     loc_180027A5B
0x1800279a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800279ae  test    rcx, rcx
0x1800279b1  jnz     short loc_1800279FA
0x1800279b3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800279ba  nop     dword ptr [rax+rax+00h]
0x1800279bf  mov     rcx, rax
0x1800279c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800279c9  test    rax, rax
0x1800279cc  jz      short loc_1800279EC
0x1800279ce  mov     rax, [rax]
0x1800279d1  mov     edx, 7F0h
0x1800279d6  mov     rax, [rax+8]
0x1800279da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279df  test    eax, eax
0x1800279e1  jz      short loc_1800279EC
0x1800279e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800279ea  jmp     short loc_1800279FA
0x1800279ec  lea     rcx, qword_1800EB130; this
0x1800279f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800279fa  cmp     byte ptr [rcx+8], 0
0x1800279fe  jz      short loc_180027A2C
0x180027a00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027a05  mov     r9d, [rbp+var_30]; int
0x180027a09  test    r9d, r9d
0x180027a0c  jns     short loc_180027A2C
0x180027a0e  cmp     [rax+7CCh], r9d
0x180027a15  jz      short loc_180027A2C
0x180027a17  mov     r8d, 12Bh; int
0x180027a1d  lea     rdx, aCdshowtransgra; "CDShowTransGraph::ConnectWrapPin"
0x180027a24  mov     rcx, rax; this
0x180027a27  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027a2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027a33  jb      short loc_180027A5B
0x180027a35  mov     edx, 1Dh
0x180027a3a  mov     eax, [rbp+var_30]
0x180027a3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a44  mov     dword ptr [rsp+60h+var_40], eax
0x180027a48  mov     r9, rsi
0x180027a4b  lea     r8, WPP_2e42bf41f4ed337060d7f0c10237b0df_Traceguids
0x180027a52  mov     rcx, [rcx+10h]
0x180027a56  call    WPP_SF_qD
0x180027a5b  mov     ebx, [rbp+var_30]
0x180027a5e  lea     rcx, [rbp+arg_18]; this
0x180027a62  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180027a67  mov     eax, ebx
0x180027a69  lea     r11, [rsp+60h+var_s0]
0x180027a6e  mov     rbx, [r11+20h]
0x180027a72  mov     rsi, [r11+28h]
0x180027a76  mov     rsp, r11
0x180027a79  pop     r14
0x180027a7b  pop     rdi
0x180027a7c  pop     rbp
0x180027a7d  retn
```
