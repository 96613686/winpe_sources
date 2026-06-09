# CWICRawMetadataBlockReaderBase::GetEnumerator(IEnumUnknown * *)

- ea: `0x18009a410`
- end: `0x18009a626`
- name: `?GetEnumerator@CWICRawMetadataBlockReaderBase@@UEAAJPEAPEAUIEnumUnknown@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *__hidden this, struct IEnumUnknown **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18009a3f0`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x180097808`
- `0x18009860c`
- `0x18009a410`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009e190`
- `0x18009e8b8`
- `0x1800a34f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a5ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a5ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a471`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a471`

## string_xrefs

- `0x18009a425`: `CWICRawMetadataBlockReaderBase::GetEnumerator`

## pseudocode

```c
__int64 __fastcall CWICRawMetadataBlockReaderBase::GetEnumerator(
        CWICRawMetadataBlockReaderBase *this,
        struct IEnumUnknown **a2)
{
  void ***v4; // rcx
  unsigned int v5; // edi
  struct CallStackContext *ThreadRelativeContext; // rax
  int v7; // r8d
  int MetadataReaders; // eax
  void ***v9; // rcx
  int v10; // eax
  void ***v11; // rcx
  _QWORD v13[2]; // [rsp+30h] [rbp-38h] BYREF
  int v14; // [rsp+40h] [rbp-28h]
  CWICRawMetadataBlockReaderBase *v15; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v15,
    "CWICRawMetadataBlockReaderBase::GetEnumerator",
    214);
  v13[0] = "CWICRawMetadataBlockReaderBase::GetEnumerator";
  v14 = 15;
  v13[1] = 0;
  OutputMsg(0, 0xFu, "=>%s", "CWICRawMetadataBlockReaderBase::GetEnumerator");
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    *a2 = 0;
    MetadataReaders = CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders(this);
    v5 = MetadataReaders;
    if ( MetadataReaders >= 0 )
    {
      v15 = this;
      v10 = Microsoft::WRL::Details::MakeAndInitialize<CWICRawMetadataBlockEnumerator,IEnumUnknown,CWICRawMetadataBlockReaderBase *>((void **)a2);
      v5 = v10;
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids, 0, v10);
        }
        v11 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v11 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
          {
            v7 = 222;
            goto LABEL_27;
          }
        }
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
          20,
          &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids,
          0,
          MetadataReaders);
      }
      v9 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        {
          v7 = 220;
          goto LABEL_27;
        }
      }
    }
  }
  else
  {
    v4 = (void ***)CallStackTracing::s_wpInstance;
    v5 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v4 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
      {
        v7 = 217;
LABEL_27:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWICRawMetadataBlockReaderBase::GetEnumerator", v7, v5);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v13);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
  return v5;
}

```

## disassembly

```asm
0x18009a410  mov     [rsp+arg_8], rbx
0x18009a415  mov     [rsp+arg_10], rbp
0x18009a41a  push    rsi
0x18009a41b  push    rdi
0x18009a41c  push    r15
0x18009a41e  sub     rsp, 50h
0x18009a422  mov     rsi, rdx
0x18009a425  lea     r15, aCwicrawmetadat_2; "CWICRawMetadataBlockReaderBase::GetEnum"...
0x18009a42c  mov     rbp, rcx
0x18009a42f  mov     rdx, r15; char *
0x18009a432  mov     r8d, 0D6h; int
0x18009a438  lea     rcx, [rsp+68h+arg_0]; this
0x18009a43d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009a442  mov     edx, 0Fh; unsigned int
0x18009a447  mov     [rsp+68h+var_38], r15
0x18009a44c  mov     r9, r15
0x18009a44f  mov     [rsp+68h+var_28], edx
0x18009a453  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x18009a45a  mov     [rsp+68h+var_30], 0
0x18009a463  xor     ecx, ecx; unsigned int
0x18009a465  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x18009a46a  lea     rbx, [rbp+10h]
0x18009a46e  mov     rcx, rbx; lpCriticalSection
0x18009a471  call    cs:__imp_EnterCriticalSection
0x18009a478  nop     dword ptr [rax+rax+00h]
0x18009a47d  test    rsi, rsi
0x18009a480  jnz     short loc_18009A4C7
0x18009a482  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a489  mov     edi, 80004003h
0x18009a48e  test    rcx, rcx
0x18009a491  jnz     short loc_18009A4A1
0x18009a493  lea     rcx, off_1800E5190; this
0x18009a49a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a4a1  cmp     byte ptr [rcx+8], 0
0x18009a4a5  jz      loc_18009A5EB
0x18009a4ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009a4b0  cmp     [rax+7CCh], edi
0x18009a4b6  jz      loc_18009A5EB
0x18009a4bc  mov     r8d, 0D9h
0x18009a4c2  jmp     loc_18009A5DD
0x18009a4c7  mov     rcx, rbp; this
0x18009a4ca  mov     qword ptr [rsi], 0
0x18009a4d1  call    ?TryCreateMetadataReaders@CWICRawMetadataBlockReaderBase@@AEAAJXZ; CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders(void)
0x18009a4d6  mov     edi, eax
0x18009a4d8  test    eax, eax
0x18009a4da  jns     short loc_18009A557
0x18009a4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a4e3  lea     rdx, WPP_GLOBAL_Control
0x18009a4ea  cmp     rcx, rdx
0x18009a4ed  jz      short loc_18009A517
0x18009a4ef  test    byte ptr [rcx+1Ch], 1
0x18009a4f3  jz      short loc_18009A517
0x18009a4f5  cmp     byte ptr [rcx+19h], 4
0x18009a4f9  jb      short loc_18009A517
0x18009a4fb  mov     rcx, [rcx+10h]
0x18009a4ff  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009a506  mov     edx, 14h
0x18009a50b  mov     [rsp+68h+var_48], eax
0x18009a50f  xor     r9d, r9d
0x18009a512  call    WPP_SF_Dd
0x18009a517  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a51e  test    rcx, rcx
0x18009a521  jnz     short loc_18009A531
0x18009a523  lea     rcx, off_1800E5190; this
0x18009a52a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a531  cmp     byte ptr [rcx+8], 0
0x18009a535  jz      loc_18009A5EB
0x18009a53b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009a540  cmp     [rax+7CCh], edi
0x18009a546  jz      loc_18009A5EB
0x18009a54c  mov     r8d, 0DCh
0x18009a552  jmp     loc_18009A5DD
0x18009a557  lea     rdx, [rsp+68h+arg_0]
0x18009a55c  mov     [rsp+68h+arg_0], rbp
0x18009a561  mov     rcx, rsi; void **
0x18009a564  call    ??$MakeAndInitialize@VCWICRawMetadataBlockEnumerator@@UIEnumUnknown@@PEAVCWICRawMetadataBlockReaderBase@@@Details@WRL@Microsoft@@YAJPEAPEAUIEnumUnknown@@$$QEAPEAVCWICRawMetadataBlockReaderBase@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CWICRawMetadataBlockEnumerator,IEnumUnknown,CWICRawMetadataBlockReaderBase *>(IEnumUnknown * *,CWICRawMetadataBlockReaderBase * &&)
0x18009a569  mov     edi, eax
0x18009a56b  test    eax, eax
0x18009a56d  jns     short loc_18009A5EB
0x18009a56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a576  lea     rdx, WPP_GLOBAL_Control
0x18009a57d  cmp     rcx, rdx
0x18009a580  jz      short loc_18009A5AA
0x18009a582  test    byte ptr [rcx+1Ch], 1
0x18009a586  jz      short loc_18009A5AA
0x18009a588  cmp     byte ptr [rcx+19h], 4
0x18009a58c  jb      short loc_18009A5AA
0x18009a58e  mov     rcx, [rcx+10h]
0x18009a592  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009a599  mov     edx, 15h
0x18009a59e  mov     [rsp+68h+var_48], eax
0x18009a5a2  xor     r9d, r9d
0x18009a5a5  call    WPP_SF_Dd
0x18009a5aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a5b1  test    rcx, rcx
0x18009a5b4  jnz     short loc_18009A5C4
0x18009a5b6  lea     rcx, off_1800E5190; this
0x18009a5bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a5c4  cmp     byte ptr [rcx+8], 0
0x18009a5c8  jz      short loc_18009A5EB
0x18009a5ca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009a5cf  cmp     [rax+7CCh], edi
0x18009a5d5  jz      short loc_18009A5EB
0x18009a5d7  mov     r8d, 0DEh; int
0x18009a5dd  mov     r9d, edi; int
0x18009a5e0  mov     rdx, r15; char *
0x18009a5e3  mov     rcx, rax; this
0x18009a5e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009a5eb  mov     rcx, rbx; lpCriticalSection
0x18009a5ee  call    cs:__imp_LeaveCriticalSection
0x18009a5f5  nop     dword ptr [rax+rax+00h]
0x18009a5fa  lea     rcx, [rsp+68h+var_38]; this
0x18009a5ff  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x18009a604  lea     rcx, [rsp+68h+arg_0]; this
0x18009a609  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009a60e  lea     r11, [rsp+68h+var_18]
0x18009a613  mov     eax, edi
0x18009a615  mov     rbx, [r11+28h]
0x18009a619  mov     rbp, [r11+30h]
0x18009a61d  mov     rsp, r11
0x18009a620  pop     r15
0x18009a622  pop     rdi
0x18009a623  pop     rsi
0x18009a624  retn
```
