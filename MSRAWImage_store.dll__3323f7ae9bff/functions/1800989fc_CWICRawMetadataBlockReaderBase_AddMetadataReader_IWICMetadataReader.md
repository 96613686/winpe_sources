# CWICRawMetadataBlockReaderBase::AddMetadataReader(IWICMetadataReader *)

- ea: `0x1800989fc`
- end: `0x180098b4c`
- name: `?AddMetadataReader@CWICRawMetadataBlockReaderBase@@IEAAJPEAUIWICMetadataReader@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *__hidden this, struct IWICMetadataReader *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800990d4`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x1800989fc`
- `0x18009b9e4`
- `0x18009c41c`
- `0x18009c44c`
- `0x18009cd18`
- `0x18009e8b8`
- `0x1800a34f8`

## string_xrefs

- `0x180098a24`: `CWICRawMetadataBlockReaderBase::AddMetadataReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWICRawMetadataBlockReaderBase::AddMetadataReader(
        CWICRawMetadataBlockReaderBase *this,
        struct IWICMetadataReader *a2)
{
  unsigned int v4; // edi
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rsi
  _QWORD v9[2]; // [rsp+38h] [rbp-20h] BYREF
  int v10; // [rsp+48h] [rbp-10h]
  struct IWICMetadataReader *v11; // [rsp+60h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v11,
    "CWICRawMetadataBlockReaderBase::AddMetadataReader",
    242);
  v4 = 0;
  v9[0] = "CWICRawMetadataBlockReaderBase::AddMetadataReader";
  v9[1] = 0;
  v10 = 15;
  OutputMsg(0, 0xFu, "=>%s", "CWICRawMetadataBlockReaderBase::AddMetadataReader");
  if ( *((_DWORD *)this + 24) < 2u )
  {
    v7 = *((unsigned int *)this + 24);
    if ( *((struct IWICMetadataReader **)this + v7 + 10) != a2 )
    {
      v11 = a2;
      Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(&v11);
      v11 = (struct IWICMetadataReader *)*((_QWORD *)this + v7 + 10);
      *((_QWORD *)this + v7 + 10) = a2;
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v11);
    }
    ++*((_DWORD *)this + 24);
  }
  else
  {
    v4 = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids,
        0,
        -2147418113);
    }
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWICRawMetadataBlockReaderBase::AddMetadataReader",
          244,
          -2147418113);
    }
  }
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return v4;
}

```

## disassembly

```asm
0x1800989fc  mov     rax, rsp
0x1800989ff  push    rdi
0x180098a00  sub     rsp, 50h
0x180098a04  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180098a0c  mov     [rax+10h], rbx
0x180098a10  mov     [rax+18h], rbp
0x180098a14  mov     [rax+20h], rsi
0x180098a18  mov     rbp, rdx
0x180098a1b  mov     rbx, rcx
0x180098a1e  mov     r8d, 0F2h; int
0x180098a24  lea     rsi, aCwicrawmetadat_3; "CWICRawMetadataBlockReaderBase::AddMeta"...
0x180098a2b  mov     rdx, rsi; char *
0x180098a2e  lea     rcx, [rax+8]; this
0x180098a32  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180098a37  nop
0x180098a38  xor     edi, edi
0x180098a3a  mov     [rsp+58h+var_20], rsi
0x180098a3f  mov     [rsp+58h+var_18], rdi
0x180098a44  lea     edx, [rdi+0Fh]; unsigned int
0x180098a47  mov     [rsp+58h+var_10], edx
0x180098a4b  mov     r9, rsi
0x180098a4e  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x180098a55  xor     ecx, ecx; unsigned int
0x180098a57  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x180098a5c  nop
0x180098a5d  cmp     dword ptr [rbx+60h], 2
0x180098a61  jb      loc_180098AEA
0x180098a67  mov     edi, 8000FFFFh
0x180098a6c  lea     rax, WPP_GLOBAL_Control
0x180098a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180098a7a  cmp     rcx, rax
0x180098a7d  jz      short loc_180098AA7
0x180098a7f  test    byte ptr [rcx+1Ch], 1
0x180098a83  jz      short loc_180098AA7
0x180098a85  cmp     byte ptr [rcx+19h], 4
0x180098a89  jb      short loc_180098AA7
0x180098a8b  mov     edx, 17h
0x180098a90  mov     [rsp+58h+var_38], edi
0x180098a94  xor     r9d, r9d
0x180098a97  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x180098a9e  mov     rcx, [rcx+10h]
0x180098aa2  call    WPP_SF_Dd
0x180098aa7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098aae  test    rcx, rcx
0x180098ab1  jnz     short loc_180098AC1
0x180098ab3  lea     rcx, off_1800E5190; this
0x180098aba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098ac1  cmp     byte ptr [rcx+8], 0
0x180098ac5  jz      short loc_180098B1F
0x180098ac7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098acc  cmp     [rax+7CCh], edi
0x180098ad2  jz      short loc_180098B1F
0x180098ad4  mov     r9d, edi; int
0x180098ad7  mov     r8d, 0F4h; int
0x180098add  mov     rdx, rsi; char *
0x180098ae0  mov     rcx, rax; this
0x180098ae3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098ae8  jmp     short loc_180098B1F
0x180098aea  mov     esi, [rbx+60h]
0x180098aed  cmp     [rbx+rsi*8+50h], rbp
0x180098af2  jz      short loc_180098B1C
0x180098af4  mov     [rsp+58h+arg_0], rbp
0x180098af9  lea     rcx, [rsp+58h+arg_0]
0x180098afe  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x180098b03  mov     rax, [rbx+rsi*8+50h]
0x180098b08  mov     [rsp+58h+arg_0], rax
0x180098b0d  mov     [rbx+rsi*8+50h], rbp
0x180098b12  lea     rcx, [rsp+58h+arg_0]
0x180098b17  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x180098b1c  inc     dword ptr [rbx+60h]
0x180098b1f  lea     rcx, [rsp+58h+var_20]; this
0x180098b24  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x180098b29  nop
0x180098b2a  lea     rcx, [rsp+58h+arg_0]; this
0x180098b2f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180098b34  mov     eax, edi
0x180098b36  mov     rbx, [rsp+58h+arg_8]
0x180098b3b  mov     rbp, [rsp+58h+arg_10]
0x180098b40  mov     rsi, [rsp+58h+arg_18]
0x180098b45  add     rsp, 50h
0x180098b49  pop     rdi
0x180098b4a  retn
```
