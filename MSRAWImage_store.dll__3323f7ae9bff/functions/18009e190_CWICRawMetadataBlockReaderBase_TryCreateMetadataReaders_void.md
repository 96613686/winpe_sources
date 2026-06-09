# CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders(void)

- ea: `0x18009e190`
- end: `0x18009e2aa`
- name: `?TryCreateMetadataReaders@CWICRawMetadataBlockReaderBase@@AEAAJXZ`
- size: `282`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180099e70`
- `0x18009a410`
- `0x18009b4b0`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x1800990d4`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009e190`
- `0x18009e8b8`
- `0x1800a34f8`

## string_xrefs

- `0x18009e1b1`: `CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders(CWICRawMetadataBlockReaderBase *this)
{
  int MetadataReaders; // ebx
  CallStackTracing *v3; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD v6[2]; // [rsp+38h] [rbp-20h] BYREF
  int v7; // [rsp+48h] [rbp-10h]
  char v8; // [rsp+60h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v8,
    "CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders",
    229);
  MetadataReaders = 0;
  v6[0] = "CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders";
  v6[1] = 0;
  v7 = 15;
  OutputMsg(0, 0xFu, "=>%s", "CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders");
  if ( !*((_BYTE *)this + 76) )
  {
    *((_BYTE *)this + 76) = 1;
    MetadataReaders = CWICRawMetadataBlockReaderBase::CreateMetadataReaders(this);
    if ( MetadataReaders < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids,
          0,
          MetadataReaders);
      }
      v3 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v3 = (CallStackTracing *)&off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v3 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v3);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != MetadataReaders )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders",
            234,
            MetadataReaders);
      }
    }
  }
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v6);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v8);
  return (unsigned int)MetadataReaders;
}

```

## disassembly

```asm
0x18009e190  mov     rax, rsp
0x18009e193  push    rdi
0x18009e194  sub     rsp, 50h
0x18009e198  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18009e1a0  mov     [rax+10h], rbx
0x18009e1a4  mov     [rax+18h], rbp
0x18009e1a8  mov     rdi, rcx
0x18009e1ab  mov     r8d, 0E5h; int
0x18009e1b1  lea     rbp, aCwicrawmetadat_10; "CWICRawMetadataBlockReaderBase::TryCrea"...
0x18009e1b8  mov     rdx, rbp; char *
0x18009e1bb  lea     rcx, [rax+8]; this
0x18009e1bf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009e1c4  nop
0x18009e1c5  xor     ebx, ebx
0x18009e1c7  mov     [rsp+58h+var_20], rbp
0x18009e1cc  mov     [rsp+58h+var_18], rbx
0x18009e1d1  lea     edx, [rbx+0Fh]; unsigned int
0x18009e1d4  mov     [rsp+58h+var_10], edx
0x18009e1d8  mov     r9, rbp
0x18009e1db  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x18009e1e2  xor     ecx, ecx; unsigned int
0x18009e1e4  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x18009e1e9  nop
0x18009e1ea  cmp     [rdi+4Ch], bl
0x18009e1ed  jnz     loc_18009E282
0x18009e1f3  mov     byte ptr [rdi+4Ch], 1
0x18009e1f7  mov     rcx, rdi; this
0x18009e1fa  call    ?CreateMetadataReaders@CWICRawMetadataBlockReaderBase@@IEAAJXZ; CWICRawMetadataBlockReaderBase::CreateMetadataReaders(void)
0x18009e1ff  mov     ebx, eax
0x18009e201  test    eax, eax
0x18009e203  jns     short loc_18009E282
0x18009e205  lea     rax, WPP_GLOBAL_Control
0x18009e20c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e213  cmp     rcx, rax
0x18009e216  jz      short loc_18009E240
0x18009e218  test    byte ptr [rcx+1Ch], 1
0x18009e21c  jz      short loc_18009E240
0x18009e21e  cmp     byte ptr [rcx+19h], 4
0x18009e222  jb      short loc_18009E240
0x18009e224  mov     edx, 16h
0x18009e229  mov     [rsp+58h+var_38], ebx
0x18009e22d  xor     r9d, r9d
0x18009e230  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009e237  mov     rcx, [rcx+10h]
0x18009e23b  call    WPP_SF_Dd
0x18009e240  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e247  test    rcx, rcx
0x18009e24a  jnz     short loc_18009E25A
0x18009e24c  lea     rcx, off_1800E5190; this
0x18009e253  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e25a  cmp     byte ptr [rcx+8], 0
0x18009e25e  jz      short loc_18009E282
0x18009e260  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e265  cmp     [rax+7CCh], ebx
0x18009e26b  jz      short loc_18009E282
0x18009e26d  mov     r9d, ebx; int
0x18009e270  mov     r8d, 0EAh; int
0x18009e276  mov     rdx, rbp; char *
0x18009e279  mov     rcx, rax; this
0x18009e27c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e281  nop
0x18009e282  lea     rcx, [rsp+58h+var_20]; this
0x18009e287  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x18009e28c  nop
0x18009e28d  lea     rcx, [rsp+58h+arg_0]; this
0x18009e292  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009e297  mov     eax, ebx
0x18009e299  mov     rbx, [rsp+58h+arg_8]
0x18009e29e  mov     rbp, [rsp+58h+arg_10]
0x18009e2a3  add     rsp, 50h
0x18009e2a7  pop     rdi
0x18009e2a8  retn
```
