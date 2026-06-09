# CWICRawMetadataBlockReaderBase::GetContainerFormat(_GUID *)

- ea: `0x180099d30`
- end: `0x180099e2d`
- name: `?GetContainerFormat@CWICRawMetadataBlockReaderBase@@UEAAJPEAU_GUID@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180099d10`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x180099d30`
- `0x18009b9e4`
- `0x18009cd18`
- `0x1800a34f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099df5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099df5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099d8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099d8e`

## string_xrefs

- `0x180099d47`: `CWICRawMetadataBlockReaderBase::GetContainerFormat`

## pseudocode

```c
__int64 __fastcall CWICRawMetadataBlockReaderBase::GetContainerFormat(
        CWICRawMetadataBlockReaderBase *this,
        struct _GUID *a2)
{
  unsigned int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  void ***v6; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  int v10; // [rsp+30h] [rbp-18h]
  char v11; // [rsp+50h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v11,
    "CWICRawMetadataBlockReaderBase::GetContainerFormat",
    170);
  v4 = 0;
  v9[0] = "CWICRawMetadataBlockReaderBase::GetContainerFormat";
  v9[1] = 0;
  v10 = 15;
  OutputMsg(0, 0xFu, "=>%s", "CWICRawMetadataBlockReaderBase::GetContainerFormat");
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection(v5);
  if ( a2 )
  {
    *a2 = GUID_ContainerFormatRaw;
  }
  else
  {
    v6 = (void ***)CallStackTracing::s_wpInstance;
    v4 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWICRawMetadataBlockReaderBase::GetContainerFormat",
          173,
          -2147467261);
    }
  }
  LeaveCriticalSection(v5);
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return v4;
}

```

## disassembly

```asm
0x180099d30  mov     rax, rsp
0x180099d33  mov     [rax+10h], rbx
0x180099d37  mov     [rax+18h], rbp
0x180099d3b  mov     [rax+20h], rsi
0x180099d3f  push    rdi
0x180099d40  sub     rsp, 40h
0x180099d44  mov     rsi, rdx
0x180099d47  lea     rbp, aCwicrawmetadat_6; "CWICRawMetadataBlockReaderBase::GetCont"...
0x180099d4e  mov     rbx, rcx
0x180099d51  mov     rdx, rbp; char *
0x180099d54  mov     r8d, 0AAh; int
0x180099d5a  lea     rcx, [rax+8]; this
0x180099d5e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180099d63  xor     edi, edi
0x180099d65  mov     [rsp+48h+var_28], rbp
0x180099d6a  mov     r9, rbp
0x180099d6d  mov     [rsp+48h+var_20], rdi
0x180099d72  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x180099d79  xor     ecx, ecx; unsigned int
0x180099d7b  lea     edx, [rdi+0Fh]; unsigned int
0x180099d7e  mov     [rsp+48h+var_18], edx
0x180099d82  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x180099d87  add     rbx, 10h
0x180099d8b  mov     rcx, rbx; lpCriticalSection
0x180099d8e  call    cs:__imp_EnterCriticalSection
0x180099d95  nop     dword ptr [rax+rax+00h]
0x180099d9a  test    rsi, rsi
0x180099d9d  jnz     short loc_180099DE7
0x180099d9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099da6  mov     edi, 80004003h
0x180099dab  test    rcx, rcx
0x180099dae  jnz     short loc_180099DBE
0x180099db0  lea     rcx, off_1800E5190; this
0x180099db7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099dbe  cmp     byte ptr [rcx+8], 0
0x180099dc2  jz      short loc_180099DF2
0x180099dc4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099dc9  cmp     [rax+7CCh], edi
0x180099dcf  jz      short loc_180099DF2
0x180099dd1  mov     r9d, edi; int
0x180099dd4  mov     r8d, 0ADh; int
0x180099dda  mov     rdx, rbp; char *
0x180099ddd  mov     rcx, rax; this
0x180099de0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099de5  jmp     short loc_180099DF2
0x180099de7  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatRaw.Data1
0x180099dee  movdqu  xmmword ptr [rsi], xmm0
0x180099df2  mov     rcx, rbx; lpCriticalSection
0x180099df5  call    cs:__imp_LeaveCriticalSection
0x180099dfc  nop     dword ptr [rax+rax+00h]
0x180099e01  lea     rcx, [rsp+48h+var_28]; this
0x180099e06  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x180099e0b  lea     rcx, [rsp+48h+arg_0]; this
0x180099e10  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180099e15  mov     rbx, [rsp+48h+arg_8]
0x180099e1a  mov     eax, edi
0x180099e1c  mov     rbp, [rsp+48h+arg_10]
0x180099e21  mov     rsi, [rsp+48h+arg_18]
0x180099e26  add     rsp, 40h
0x180099e2a  pop     rdi
0x180099e2b  retn
```
