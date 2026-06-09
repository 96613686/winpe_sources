# CWICRawMetadataBlockReaderBase::GetCount(uint *)

- ea: `0x180099e70`
- end: `0x180099ff9`
- name: `?GetCount@CWICRawMetadataBlockReaderBase@@UEAAJPEAI@Z`
- size: `393`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180099e50`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x180099e70`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009e190`
- `0x18009e8b8`
- `0x1800a34f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099fc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099fc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099ed2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099ed2`

## string_xrefs

- `0x180099e86`: `CWICRawMetadataBlockReaderBase::GetCount`

## pseudocode

```c
__int64 __fastcall CWICRawMetadataBlockReaderBase::GetCount(CWICRawMetadataBlockReaderBase *this, unsigned int *a2)
{
  CallStackTracing *v4; // rcx
  int MetadataReaders; // edi
  struct CallStackContext *ThreadRelativeContext; // rax
  int v7; // r8d
  CallStackTracing *v8; // rcx
  _QWORD v10[2]; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+40h] [rbp-28h]
  char v12; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "CWICRawMetadataBlockReaderBase::GetCount", 181);
  v10[0] = "CWICRawMetadataBlockReaderBase::GetCount";
  v11 = 15;
  v10[1] = 0;
  OutputMsg(0, 0xFu, "=>%s", "CWICRawMetadataBlockReaderBase::GetCount");
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    MetadataReaders = CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders(this);
    if ( MetadataReaders >= 0 )
    {
      *a2 = *((_DWORD *)this + 24);
      goto LABEL_19;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids,
        0,
        MetadataReaders);
    }
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != MetadataReaders )
      {
        v7 = 185;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v4 = CallStackTracing::s_wpInstance;
    MetadataReaders = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v4 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
      {
        v7 = 183;
LABEL_7:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWICRawMetadataBlockReaderBase::GetCount",
          v7,
          MetadataReaders);
      }
    }
  }
LABEL_19:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v10);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return (unsigned int)MetadataReaders;
}

```

## disassembly

```asm
0x180099e70  mov     [rsp+arg_8], rbx
0x180099e75  mov     [rsp+arg_10], rsi
0x180099e7a  push    rdi
0x180099e7b  push    r14
0x180099e7d  push    r15
0x180099e7f  sub     rsp, 50h
0x180099e83  mov     r14, rdx
0x180099e86  lea     r15, aCwicrawmetadat_8; "CWICRawMetadataBlockReaderBase::GetCoun"...
0x180099e8d  mov     rsi, rcx
0x180099e90  mov     rdx, r15; char *
0x180099e93  mov     r8d, 0B5h; int
0x180099e99  lea     rcx, [rsp+68h+arg_0]; this
0x180099e9e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180099ea3  mov     edx, 0Fh; unsigned int
0x180099ea8  mov     [rsp+68h+var_38], r15
0x180099ead  mov     r9, r15
0x180099eb0  mov     [rsp+68h+var_28], edx
0x180099eb4  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x180099ebb  mov     [rsp+68h+var_30], 0
0x180099ec4  xor     ecx, ecx; unsigned int
0x180099ec6  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x180099ecb  lea     rbx, [rsi+10h]
0x180099ecf  mov     rcx, rbx; lpCriticalSection
0x180099ed2  call    cs:__imp_EnterCriticalSection
0x180099ed9  nop     dword ptr [rax+rax+00h]
0x180099ede  test    r14, r14
0x180099ee1  jnz     short loc_180099F36
0x180099ee3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099eea  mov     edi, 80004003h
0x180099eef  test    rcx, rcx
0x180099ef2  jnz     short loc_180099F02
0x180099ef4  lea     rcx, off_1800E5190; this
0x180099efb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099f02  cmp     byte ptr [rcx+8], 0
0x180099f06  jz      loc_180099FBD
0x180099f0c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099f11  cmp     [rax+7CCh], edi
0x180099f17  jz      loc_180099FBD
0x180099f1d  mov     r8d, 0B7h; int
0x180099f23  mov     r9d, edi; int
0x180099f26  mov     rdx, r15; char *
0x180099f29  mov     rcx, rax; this
0x180099f2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099f31  jmp     loc_180099FBD
0x180099f36  mov     rcx, rsi; this
0x180099f39  call    ?TryCreateMetadataReaders@CWICRawMetadataBlockReaderBase@@AEAAJXZ; CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders(void)
0x180099f3e  mov     edi, eax
0x180099f40  test    eax, eax
0x180099f42  jns     short loc_180099FB7
0x180099f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180099f4b  lea     rax, WPP_GLOBAL_Control
0x180099f52  cmp     rcx, rax
0x180099f55  jz      short loc_180099F7F
0x180099f57  test    byte ptr [rcx+1Ch], 1
0x180099f5b  jz      short loc_180099F7F
0x180099f5d  cmp     byte ptr [rcx+19h], 4
0x180099f61  jb      short loc_180099F7F
0x180099f63  mov     rcx, [rcx+10h]
0x180099f67  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x180099f6e  mov     edx, 10h
0x180099f73  mov     [rsp+68h+var_48], edi
0x180099f77  xor     r9d, r9d
0x180099f7a  call    WPP_SF_Dd
0x180099f7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099f86  test    rcx, rcx
0x180099f89  jnz     short loc_180099F99
0x180099f8b  lea     rcx, off_1800E5190; this
0x180099f92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099f99  cmp     byte ptr [rcx+8], 0
0x180099f9d  jz      short loc_180099FBD
0x180099f9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099fa4  cmp     [rax+7CCh], edi
0x180099faa  jz      short loc_180099FBD
0x180099fac  mov     r8d, 0B9h
0x180099fb2  jmp     loc_180099F23
0x180099fb7  mov     eax, [rsi+60h]
0x180099fba  mov     [r14], eax
0x180099fbd  mov     rcx, rbx; lpCriticalSection
0x180099fc0  call    cs:__imp_LeaveCriticalSection
0x180099fc7  nop     dword ptr [rax+rax+00h]
0x180099fcc  lea     rcx, [rsp+68h+var_38]; this
0x180099fd1  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x180099fd6  lea     rcx, [rsp+68h+arg_0]; this
0x180099fdb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180099fe0  lea     r11, [rsp+68h+var_18]
0x180099fe5  mov     eax, edi
0x180099fe7  mov     rbx, [r11+28h]
0x180099feb  mov     rsi, [r11+30h]
0x180099fef  mov     rsp, r11
0x180099ff2  pop     r15
0x180099ff4  pop     r14
0x180099ff6  pop     rdi
0x180099ff7  retn
```
