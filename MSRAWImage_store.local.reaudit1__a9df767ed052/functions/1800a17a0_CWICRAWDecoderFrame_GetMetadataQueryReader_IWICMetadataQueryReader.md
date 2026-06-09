# CWICRAWDecoderFrame::GetMetadataQueryReader(IWICMetadataQueryReader * *)

- ea: `0x1800a17a0`
- end: `0x1800a1aa9`
- name: `?GetMetadataQueryReader@CWICRAWDecoderFrame@@UEAAJPEAPEAUIWICMetadataQueryReader@@@Z`
- size: `777`
- prototype: `__int64 __fastcall(CWICRAWDecoderFrame *__hidden this, struct IWICMetadataQueryReader **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009860c`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009cd18`
- `0x18009e8b8`
- `0x1800a17a0`
- `0x1800a34f8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1a59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1a59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a187c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a187c`

## string_xrefs

- `0x1800a17d9`: `CWICRAWDecoderFrame::GetMetadataQueryReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWICRAWDecoderFrame::GetMetadataQueryReader(
        CWICRAWDecoderFrame *this,
        struct IWICMetadataQueryReader **a2)
{
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v5; // edi
  int v6; // edi
  void ***v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 (__fastcall *v9)(char *, GUID *, __int64 *); // rdi
  void ***v10; // rcx
  struct CallStackContext *v11; // rax
  void ***v12; // rcx
  struct CallStackContext *v13; // rax
  const char *v14; // r9
  __int64 result; // rax
  _BYTE v16[8]; // [rsp+30h] [rbp-78h] BYREF
  __int64 v17; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-68h] BYREF
  int v19; // [rsp+50h] [rbp-58h]
  __int64 v20; // [rsp+58h] [rbp-50h]
  char *v21; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v20 = -2;
  try
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v16,
      "CWICRAWDecoderFrame::GetMetadataQueryReader",
      45);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 6) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 296LL))(*((_QWORD *)this + 6));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(**((_QWORD **)this + 6) + 280LL))(
                                                              *((_QWORD *)this + 6),
                                                              &v21);
      *((_DWORD *)ThreadRelativeContext + 504) = v5;
    }
    v18[0] = "CWICRAWDecoderFrame::GetMetadataQueryReader";
    v18[1] = 0;
    v19 = 15;
    OutputMsg(0, 0xFu, "=>%s", "CWICRAWDecoderFrame::GetMetadataQueryReader");
    v21 = (char *)this - 96;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 96));
    if ( a2 )
    {
      *a2 = 0;
      v17 = 0;
      v9 = (__int64 (__fastcall *)(char *, GUID *, __int64 *))**((_QWORD **)this - 14);
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v17);
      v6 = v9((char *)this - 112, &GUID_feaa2a8d_b3f3_43e4_b25c_d1de990a1ae1, &v17);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IWICMetadataQueryReader **))(**((_QWORD **)this - 7)
                                                                                           + 256LL))(
               *((_QWORD *)this - 7),
               v17,
               a2);
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids, 0, v6);
          }
          v12 = (void ***)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v12 = &off_1800E5190;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
          }
          if ( *((_BYTE *)v12 + 8) )
          {
            v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
            if ( *((_DWORD *)v13 + 499) != v6 )
              CallStackContext::TraceFailure(v13, "CWICRAWDecoderFrame::GetMetadataQueryReader", 53, v6);
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids, 0, v6);
        }
        v10 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v10 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v10 + 8) )
        {
          v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
          if ( *((_DWORD *)v11 + 499) != v6 )
            CallStackContext::TraceFailure(v11, "CWICRAWDecoderFrame::GetMetadataQueryReader", 52, v6);
        }
      }
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v17);
    }
    else
    {
      v6 = -2147467261;
      v7 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)v8 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v8, "CWICRAWDecoderFrame::GetMetadataQueryReader", 48, -2147467261);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this - 96));
    CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v18);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v16);
    result = (unsigned int)v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x39,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagewicdecoder\\rawimagedecoderframe.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800a17a0  mov     r11, rsp
0x1800a17a3  push    rsi
0x1800a17a4  push    rdi
0x1800a17a5  push    r13
0x1800a17a7  push    r14
0x1800a17a9  push    r15
0x1800a17ab  sub     rsp, 80h
0x1800a17b2  mov     qword ptr [r11-50h], 0FFFFFFFFFFFFFFFEh
0x1800a17ba  mov     [r11+18h], rbx
0x1800a17be  mov     rax, cs:__security_cookie
0x1800a17c5  xor     rax, rsp
0x1800a17c8  mov     [rsp+0A8h+var_38], rax
0x1800a17cd  mov     r15, rdx
0x1800a17d0  mov     r14, rcx
0x1800a17d3  mov     r8d, 2Dh ; '-'; int
0x1800a17d9  lea     r13, aCwicrawdecoder_4; "CWICRAWDecoderFrame::GetMetadataQueryRe"...
0x1800a17e0  mov     rdx, r13; char *
0x1800a17e3  lea     rcx, [r11-78h]; this
0x1800a17e7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a17ec  nop
0x1800a17ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a17f4  cmp     byte ptr [rcx+8], 0
0x1800a17f8  jz      short loc_1800A1847
0x1800a17fa  cmp     qword ptr [r14+30h], 0
0x1800a17ff  jz      short loc_1800A1847
0x1800a1801  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1806  mov     rbx, rax
0x1800a1809  mov     rcx, [r14+30h]
0x1800a180d  mov     rdx, [rcx]
0x1800a1810  mov     rax, [rdx+128h]
0x1800a1817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a181c  mov     edi, eax
0x1800a181e  mov     rcx, [r14+30h]
0x1800a1822  mov     rdx, [rcx]
0x1800a1825  mov     rax, [rdx+118h]
0x1800a182c  lea     rdx, [rsp+0A8h+var_48]
0x1800a1831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1836  movups  xmm0, xmmword ptr [rax]
0x1800a1839  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800a1841  mov     [rbx+7E0h], edi
0x1800a1847  mov     [rsp+0A8h+var_68], r13
0x1800a184c  mov     [rsp+0A8h+var_60], 0
0x1800a1855  mov     edx, 0Fh; unsigned int
0x1800a185a  mov     [rsp+0A8h+var_58], edx
0x1800a185e  mov     r9, r13
0x1800a1861  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x1800a1868  xor     ecx, ecx; unsigned int
0x1800a186a  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x1800a186f  nop
0x1800a1870  lea     rbx, [r14-60h]
0x1800a1874  mov     [rsp+0A8h+var_48], rbx
0x1800a1879  mov     rcx, rbx; lpCriticalSection
0x1800a187c  call    cs:__imp_EnterCriticalSection
0x1800a1883  nop     dword ptr [rax+rax+00h]
0x1800a1888  nop
0x1800a1889  test    r15, r15
0x1800a188c  jnz     short loc_1800A18E1
0x1800a188e  mov     edi, 80004003h
0x1800a1893  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a189a  test    rcx, rcx
0x1800a189d  jnz     short loc_1800A18AD
0x1800a189f  lea     rcx, off_1800E5190; this
0x1800a18a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a18ad  cmp     byte ptr [rcx+8], 0
0x1800a18b1  jz      loc_1800A1A56
0x1800a18b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a18bc  cmp     [rax+7CCh], edi
0x1800a18c2  jz      loc_1800A1A56
0x1800a18c8  mov     r9d, edi; int
0x1800a18cb  mov     r8d, 30h ; '0'; int
0x1800a18d1  mov     rdx, r13; char *
0x1800a18d4  mov     rcx, rax; this
0x1800a18d7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a18dc  jmp     loc_1800A1A56
0x1800a18e1  mov     qword ptr [r15], 0
0x1800a18e8  mov     [rsp+0A8h+var_70], 0
0x1800a18f1  mov     rax, [r14-70h]
0x1800a18f5  mov     rdi, [rax]
0x1800a18f8  lea     rcx, [rsp+0A8h+var_70]
0x1800a18fd  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a1902  lea     r8, [rsp+0A8h+var_70]
0x1800a1907  lea     rdx, _GUID_feaa2a8d_b3f3_43e4_b25c_d1de990a1ae1
0x1800a190e  lea     rcx, [r14-70h]
0x1800a1912  mov     rax, rdi
0x1800a1915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a191a  mov     edi, eax
0x1800a191c  test    eax, eax
0x1800a191e  jns     loc_1800A19AD
0x1800a1924  lea     rax, WPP_GLOBAL_Control
0x1800a192b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1932  cmp     rcx, rax
0x1800a1935  jz      short loc_1800A195F
0x1800a1937  test    byte ptr [rcx+1Ch], 1
0x1800a193b  jz      short loc_1800A195F
0x1800a193d  cmp     byte ptr [rcx+19h], 4
0x1800a1941  jb      short loc_1800A195F
0x1800a1943  mov     edx, 0Ch
0x1800a1948  mov     [rsp+0A8h+var_88], edi
0x1800a194c  xor     r9d, r9d
0x1800a194f  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a1956  mov     rcx, [rcx+10h]
0x1800a195a  call    WPP_SF_Dd
0x1800a195f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1966  test    rcx, rcx
0x1800a1969  jnz     short loc_1800A1979
0x1800a196b  lea     rcx, off_1800E5190; this
0x1800a1972  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1979  cmp     byte ptr [rcx+8], 0
0x1800a197d  jz      loc_1800A1A4B
0x1800a1983  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1988  cmp     [rax+7CCh], edi
0x1800a198e  jz      loc_1800A1A4B
0x1800a1994  mov     r9d, edi; int
0x1800a1997  mov     r8d, 34h ; '4'; int
0x1800a199d  mov     rdx, r13; char *
0x1800a19a0  mov     rcx, rax; this
0x1800a19a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a19a8  jmp     loc_1800A1A4B
0x1800a19ad  mov     rcx, [r14-38h]
0x1800a19b1  mov     rax, [rcx]
0x1800a19b4  mov     r8, r15
0x1800a19b7  mov     rdx, [rsp+0A8h+var_70]
0x1800a19bc  mov     rax, [rax+100h]
0x1800a19c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a19c8  mov     edi, eax
0x1800a19ca  test    eax, eax
0x1800a19cc  jns     short loc_1800A1A4B
0x1800a19ce  lea     rax, WPP_GLOBAL_Control
0x1800a19d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a19dc  cmp     rcx, rax
0x1800a19df  jz      short loc_1800A1A09
0x1800a19e1  test    byte ptr [rcx+1Ch], 1
0x1800a19e5  jz      short loc_1800A1A09
0x1800a19e7  cmp     byte ptr [rcx+19h], 4
0x1800a19eb  jb      short loc_1800A1A09
0x1800a19ed  mov     edx, 0Dh
0x1800a19f2  mov     [rsp+0A8h+var_88], edi
0x1800a19f6  xor     r9d, r9d
0x1800a19f9  lea     r8, WPP_84b1ab63a72c33758566b4fd7a583c4d_Traceguids
0x1800a1a00  mov     rcx, [rcx+10h]
0x1800a1a04  call    WPP_SF_Dd
0x1800a1a09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a10  test    rcx, rcx
0x1800a1a13  jnz     short loc_1800A1A23
0x1800a1a15  lea     rcx, off_1800E5190; this
0x1800a1a1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a23  cmp     byte ptr [rcx+8], 0
0x1800a1a27  jz      short loc_1800A1A4B
0x1800a1a29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1a2e  cmp     [rax+7CCh], edi
0x1800a1a34  jz      short loc_1800A1A4B
0x1800a1a36  mov     r9d, edi; int
0x1800a1a39  mov     r8d, 35h ; '5'; int
0x1800a1a3f  mov     rdx, r13; char *
0x1800a1a42  mov     rcx, rax; this
0x1800a1a45  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1a4a  nop
0x1800a1a4b  lea     rcx, [rsp+0A8h+var_70]
0x1800a1a50  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a1a55  nop
0x1800a1a56  mov     rcx, rbx; lpCriticalSection
0x1800a1a59  call    cs:__imp_LeaveCriticalSection
0x1800a1a60  nop     dword ptr [rax+rax+00h]
0x1800a1a65  nop
0x1800a1a66  lea     rcx, [rsp+0A8h+var_68]; this
0x1800a1a6b  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x1800a1a70  nop
0x1800a1a71  lea     rcx, [rsp+0A8h+var_78]; this
0x1800a1a76  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a1a7b  mov     eax, edi
0x1800a1a7d  jmp     short loc_1800A1A83
0x1800a1a7f  mov     eax, dword ptr [rsp+0A8h+var_70]
0x1800a1a83  mov     rcx, [rsp+0A8h+var_38]
0x1800a1a88  xor     rcx, rsp; StackCookie
0x1800a1a8b  call    __security_check_cookie
0x1800a1a90  mov     rbx, [rsp+0A8h+arg_10]
0x1800a1a98  add     rsp, 80h
0x1800a1a9f  pop     r15
0x1800a1aa1  pop     r14
0x1800a1aa3  pop     r13
0x1800a1aa5  pop     rdi
0x1800a1aa6  pop     rsi
0x1800a1aa7  retn
```
