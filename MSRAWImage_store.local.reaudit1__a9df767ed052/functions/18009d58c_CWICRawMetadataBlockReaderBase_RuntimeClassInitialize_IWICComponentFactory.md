# CWICRawMetadataBlockReaderBase::RuntimeClassInitialize(IWICComponentFactory *)

- ea: `0x18009d58c`
- end: `0x18009d721`
- name: `?RuntimeClassInitialize@CWICRawMetadataBlockReaderBase@@QEAAJPEAUIWICComponentFactory@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *__hidden this, struct IWICComponentFactory *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a25b8`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x18009879c`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009d58c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceFromApp` at `0x18009d62f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceFromApp` at `0x18009d62f`

## string_xrefs

- `0x18009d5b4`: `CWICRawMetadataBlockReaderBase::RuntimeClassInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWICRawMetadataBlockReaderBase::RuntimeClassInitialize(
        CWICRawMetadataBlockReaderBase *this,
        struct IWICComponentFactory *a2)
{
  int v4; // ebx
  void ***v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  GUID *v8; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+40h] [rbp-38h]
  _QWORD v10[2]; // [rsp+50h] [rbp-28h] BYREF
  int v11; // [rsp+60h] [rbp-18h]
  char v12; // [rsp+88h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v12,
    "CWICRawMetadataBlockReaderBase::RuntimeClassInitialize",
    146);
  v4 = 0;
  v10[0] = "CWICRawMetadataBlockReaderBase::RuntimeClassInitialize";
  v10[1] = 0;
  v11 = 15;
  OutputMsg(0, 0xFu, "=>%s", "CWICRawMetadataBlockReaderBase::RuntimeClassInitialize");
  if ( a2 )
  {
    Microsoft::WRL::ComPtr<IWICComponentFactory>::operator=((char *)this + 56, a2);
  }
  else
  {
    v9 = 0;
    v8 = &IID_IWICComponentFactory;
    v4 = CoCreateInstanceFromApp(&CLSID_WICImagingFactory2, 0, 1, 0, 1, &v8);
    if ( v4 >= 0 )
    {
      Microsoft::WRL::ComPtr<IWICComponentFactory>::operator=((char *)this + 56, v9);
      if ( (_QWORD)v9 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids, 0, v4);
      }
      v5 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v5 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v5 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CWICRawMetadataBlockReaderBase::RuntimeClassInitialize",
            152,
            v4);
      }
    }
  }
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v10);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18009d58c  mov     rax, rsp
0x18009d58f  push    rdi
0x18009d590  sub     rsp, 70h
0x18009d594  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18009d59c  mov     [rax+8], rbx
0x18009d5a0  mov     [rax+18h], rbp
0x18009d5a4  mov     [rax+20h], rsi
0x18009d5a8  mov     rsi, rdx
0x18009d5ab  mov     rdi, rcx
0x18009d5ae  mov     r8d, 92h; int
0x18009d5b4  lea     rbp, aCwicrawmetadat_7; "CWICRawMetadataBlockReaderBase::Runtime"...
0x18009d5bb  mov     rdx, rbp; char *
0x18009d5be  lea     rcx, [rax+10h]; this
0x18009d5c2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009d5c7  nop
0x18009d5c8  xor     ebx, ebx
0x18009d5ca  mov     [rsp+78h+var_28], rbp
0x18009d5cf  mov     [rsp+78h+var_20], rbx
0x18009d5d4  mov     [rsp+78h+var_18], 0Fh
0x18009d5dc  mov     r9, rbp
0x18009d5df  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x18009d5e6  lea     edx, [rbx+0Fh]; unsigned int
0x18009d5e9  xor     ecx, ecx; unsigned int
0x18009d5eb  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x18009d5f0  nop
0x18009d5f1  test    rsi, rsi
0x18009d5f4  jnz     loc_18009D6E3
0x18009d5fa  xorps   xmm0, xmm0
0x18009d5fd  movdqu  [rsp+78h+var_38], xmm0
0x18009d603  lea     rax, IID_IWICComponentFactory
0x18009d60a  mov     [rsp+78h+var_40], rax
0x18009d60f  lea     rax, [rsp+78h+var_40]
0x18009d614  mov     [rsp+78h+var_50], rax
0x18009d619  lea     esi, [rbx+1]
0x18009d61c  mov     [rsp+78h+var_58], esi
0x18009d620  xor     r9d, r9d
0x18009d623  mov     r8d, esi
0x18009d626  xor     edx, edx
0x18009d628  lea     rcx, CLSID_WICImagingFactory2
0x18009d62f  call    cs:__imp_CoCreateInstanceFromApp
0x18009d636  nop     dword ptr [rax+rax+00h]
0x18009d63b  mov     ebx, eax
0x18009d63d  test    eax, eax
0x18009d63f  jns     short loc_18009D6BD
0x18009d641  lea     rax, WPP_GLOBAL_Control
0x18009d648  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d64f  cmp     rcx, rax
0x18009d652  jz      short loc_18009D67A
0x18009d654  test    [rcx+1Ch], sil
0x18009d658  jz      short loc_18009D67A
0x18009d65a  cmp     byte ptr [rcx+19h], 4
0x18009d65e  jb      short loc_18009D67A
0x18009d660  lea     edx, [rsi+0Eh]
0x18009d663  mov     [rsp+78h+var_58], ebx
0x18009d667  xor     r9d, r9d
0x18009d66a  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009d671  mov     rcx, [rcx+10h]
0x18009d675  call    WPP_SF_Dd
0x18009d67a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d681  test    rcx, rcx
0x18009d684  jnz     short loc_18009D694
0x18009d686  lea     rcx, off_1800E5190; this
0x18009d68d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d694  cmp     byte ptr [rcx+8], 0
0x18009d698  jz      short loc_18009D6F0
0x18009d69a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d69f  cmp     [rax+7CCh], ebx
0x18009d6a5  jz      short loc_18009D6F0
0x18009d6a7  mov     r9d, ebx; int
0x18009d6aa  mov     r8d, 98h; int
0x18009d6b0  mov     rdx, rbp; char *
0x18009d6b3  mov     rcx, rax; this
0x18009d6b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009d6bb  jmp     short loc_18009D6F0
0x18009d6bd  lea     rcx, [rdi+38h]
0x18009d6c1  mov     rdx, qword ptr [rsp+78h+var_38]
0x18009d6c6  call    ??4?$ComPtr@UIWICComponentFactory@@@WRL@Microsoft@@QEAAAEAV012@PEAUIWICComponentFactory@@@Z; Microsoft::WRL::ComPtr<IWICComponentFactory>::operator=(IWICComponentFactory *)
0x18009d6cb  mov     rcx, qword ptr [rsp+78h+var_38]
0x18009d6d0  test    rcx, rcx
0x18009d6d3  jz      short loc_18009D6F0
0x18009d6d5  mov     rax, [rcx]
0x18009d6d8  mov     rax, [rax+10h]
0x18009d6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d6e1  jmp     short loc_18009D6F0
0x18009d6e3  lea     rcx, [rdi+38h]
0x18009d6e7  mov     rdx, rsi
0x18009d6ea  call    ??4?$ComPtr@UIWICComponentFactory@@@WRL@Microsoft@@QEAAAEAV012@PEAUIWICComponentFactory@@@Z; Microsoft::WRL::ComPtr<IWICComponentFactory>::operator=(IWICComponentFactory *)
0x18009d6ef  nop
0x18009d6f0  lea     rcx, [rsp+78h+var_28]; this
0x18009d6f5  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x18009d6fa  nop
0x18009d6fb  lea     rcx, [rsp+78h+arg_8]; this
0x18009d703  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009d708  mov     eax, ebx
0x18009d70a  lea     r11, [rsp+78h+var_8]
0x18009d70f  mov     rbx, [r11+10h]
0x18009d713  mov     rbp, [r11+20h]
0x18009d717  mov     rsi, [r11+28h]
0x18009d71b  mov     rsp, r11
0x18009d71e  pop     rdi
0x18009d71f  retn
```
