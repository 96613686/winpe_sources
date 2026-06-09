# CDShowTransform::UpdateOutputPins(void)

- ea: `0x180027e1c`
- end: `0x180028165`
- name: `?UpdateOutputPins@CDShowTransform@@IEAAJXZ`
- size: `841`
- prototype: `__int64 __fastcall(CDShowTransform *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026fd0`
- `0x1800273b0`
- `0x180027a88`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180027e1c`
- `0x18002816c`
- `0x1800284ec`
- `0x180028bd0`
- `0x180032a50`
- `0x180041ab0`
- `0x1800514f0`
- `0x180051a50`
- `0x180051ce4`
- `0x180073d0c`
- `0x180074b18`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027e84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002809a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027e84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002809a`

## string_xrefs

- `0x180027e51`: `CDShowTransform::UpdateOutputPins`
- `0x180027ee4`: `CDShowTransform::UpdateOutputPins`
- `0x180027fb9`: `CDShowTransform::UpdateOutputPins`
- `0x1800280fd`: `CDShowTransform::UpdateOutputPins`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDShowTransform::UpdateOutputPins(CDShowTransform *this)
{
  CDShowTransform *v1; // r13
  unsigned __int64 v2; // rdi
  _QWORD *v3; // r15
  int updated; // esi
  CallStackTracing *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  unsigned __int64 v12; // r14
  char *v13; // rbx
  CDShowTransformIOBase *v14; // rax
  CDShowTransformIOBase *v15; // r12
  struct CDShowTransPin *v16; // rbx
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v20; // [rsp+30h] [rbp-68h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-58h]
  __int64 v23; // [rsp+48h] [rbp-50h]
  int v24; // [rsp+50h] [rbp-48h]
  CDShowTransformIOBase *v26; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v27; // [rsp+B0h] [rbp+18h]
  CDShowTransformIOBase *v28; // [rsp+B8h] [rbp+20h] BYREF

  v1 = this;
  v2 = 0;
  v3 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v26, "CDShowTransform::UpdateOutputPins", 616);
  updated = CDShowTransGraph::UpdateWrapFilters(*((CDShowTransGraph **)v1 + 28));
  if ( updated >= 0 )
  {
    updated = CDShowTransGraph::GetWrapPins(*((_QWORD *)v1 + 28), 1, &v21);
    if ( updated >= 0 )
    {
      v12 = 0;
      v27 = 0;
      v3 = v21;
      while ( v12 < v22 )
      {
        v13 = (char *)v1 + 192;
        if ( !CDShowTransformPinArrayTraits::FindPin<CDShowTransformOutput>(v3[v12], (char *)v1 + 192) )
        {
          v14 = (CDShowTransformIOBase *)operator new(0x40u);
          v15 = v14;
          v26 = v14;
          if ( v14 )
          {
            v16 = (struct CDShowTransPin *)v3[v12];
            CDShowTransformIOBase::CDShowTransformIOBase(v14, v16);
            *(_QWORD *)v15 = &CDShowTransformOutput::`vftable';
            *((_QWORD *)v15 + 7) = v16;
            v13 = (char *)v1 + 192;
          }
          else
          {
            v15 = 0;
          }
          v28 = v15;
          if ( !v15 )
          {
            updated = -2147024882;
            v17 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v18;
              if ( v18
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
              {
                v17 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v17 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v17 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v17);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CDShowTransform::UpdateOutputPins",
                  628,
                  -2147024882);
            }
            if ( g_wppLevels )
            {
              v8 = 42;
              goto LABEL_12;
            }
            break;
          }
          try
          {
            ATL::CAtlArray<CDShowTransformInput *,ATL::CElementTraits<CDShowTransformInput *>>::Add(v13, &v28);
          }
          catch ( ATL::CAtlException v20 )
          {
            LODWORD(v26) = v20;
            v2 = 0;
            v1 = this;
            updated = v20;
            v3 = v21;
            v12 = v27;
          }
        }
        v27 = ++v12;
      }
    }
    else
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v10 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext(v10);
        if ( *((_DWORD *)v11 + 499) != updated )
          CallStackContext::TraceFailure(v11, "CDShowTransform::UpdateOutputPins", 618, updated);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          &WPP_4424637dafd93ac8aa68a350a9714af2_Traceguids,
          v1,
          updated);
      v3 = v21;
    }
  }
  else
  {
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)v7 + 499) != updated )
        CallStackContext::TraceFailure(v7, "CDShowTransform::UpdateOutputPins", 616, updated);
    }
    if ( g_wppLevels )
    {
      v8 = 40;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_4424637dafd93ac8aa68a350a9714af2_Traceguids, v1, updated);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  if ( v3 )
  {
    if ( v22 )
    {
      do
        ATL::CComPtrBase<IMemInputPin>::~CComPtrBase<IMemInputPin>(&v3[v2++]);
      while ( v2 < v22 );
    }
    free(v3);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180027e1c  mov     rax, rsp
0x180027e1f  mov     [rax+8], rcx
0x180027e23  push    rbx
0x180027e24  push    rsi
0x180027e25  push    rdi
0x180027e26  push    r12
0x180027e28  push    r13
0x180027e2a  push    r14
0x180027e2c  push    r15
0x180027e2e  sub     rsp, 60h
0x180027e32  mov     r13, rcx
0x180027e35  xor     edi, edi
0x180027e37  mov     r15d, edi
0x180027e3a  mov     [rax-60h], rdi
0x180027e3e  mov     [rax-58h], rdi
0x180027e42  mov     [rax-50h], rdi
0x180027e46  mov     [rax-48h], edi
0x180027e49  mov     ebx, 268h
0x180027e4e  mov     r8d, ebx; int
0x180027e51  lea     rdx, aCdshowtransfor_8; "CDShowTransform::UpdateOutputPins"
0x180027e58  lea     rcx, [rax+10h]; this
0x180027e5c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180027e61  nop
0x180027e62  mov     rcx, [r13+0E0h]; this
0x180027e69  call    ?UpdateWrapFilters@CDShowTransGraph@@QEAAJXZ; CDShowTransGraph::UpdateWrapFilters(void)
0x180027e6e  mov     esi, eax
0x180027e70  test    eax, eax
0x180027e72  jns     loc_180027F69
0x180027e78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027e7f  test    rcx, rcx
0x180027e82  jnz     short loc_180027ECB
0x180027e84  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027e8b  nop     dword ptr [rax+rax+00h]
0x180027e90  mov     rcx, rax
0x180027e93  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027e9a  test    rax, rax
0x180027e9d  jz      short loc_180027EBD
0x180027e9f  mov     rax, [rax]
0x180027ea2  mov     edx, 7F0h
0x180027ea7  mov     rax, [rax+8]
0x180027eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eb0  test    eax, eax
0x180027eb2  jz      short loc_180027EBD
0x180027eb4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ebb  jmp     short loc_180027ECB
0x180027ebd  lea     rcx, qword_1800EB130; this
0x180027ec4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ecb  cmp     [rcx+8], dil
0x180027ecf  jz      short loc_180027EF3
0x180027ed1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027ed6  cmp     [rax+7CCh], esi
0x180027edc  jz      short loc_180027EF3
0x180027ede  mov     r9d, esi; int
0x180027ee1  mov     r8d, ebx; int
0x180027ee4  lea     rdx, aCdshowtransfor_8; "CDShowTransform::UpdateOutputPins"
0x180027eeb  mov     rcx, rax; this
0x180027eee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027ef3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027efa  jb      short loc_180027F20
0x180027efc  mov     edx, 28h ; '('
0x180027f01  mov     [rsp+98h+var_78], esi
0x180027f05  mov     r9, r13
0x180027f08  lea     r8, WPP_4424637dafd93ac8aa68a350a9714af2_Traceguids
0x180027f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f16  mov     rcx, [rcx+10h]
0x180027f1a  call    WPP_SF_qD
0x180027f1f  nop
0x180027f20  lea     rcx, [rsp+98h+arg_8]; this
0x180027f28  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180027f2d  nop
0x180027f2e  test    r15, r15
0x180027f31  jz      short loc_180027F56
0x180027f33  cmp     [rsp+98h+var_58], rdi
0x180027f38  jbe     short loc_180027F4D
0x180027f3a  lea     rcx, [r15+rdi*8]
0x180027f3e  call    ??1?$CComPtrBase@UIMemInputPin@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMemInputPin>::~CComPtrBase<IMemInputPin>(void)
0x180027f43  inc     rdi
0x180027f46  cmp     rdi, [rsp+98h+var_58]
0x180027f4b  jb      short loc_180027F3A
0x180027f4d  mov     rcx, r15; Block
0x180027f50  call    free
0x180027f55  nop
0x180027f56  mov     eax, esi
0x180027f58  add     rsp, 60h
0x180027f5c  pop     r15
0x180027f5e  pop     r14
0x180027f60  pop     r13
0x180027f62  pop     r12
0x180027f64  pop     rdi
0x180027f65  pop     rsi
0x180027f66  pop     rbx
0x180027f67  retn
0x180027f69  lea     r8, [rsp+98h+var_60]
0x180027f6e  mov     edx, 1
0x180027f73  mov     rcx, [r13+0E0h]
0x180027f7a  call    ?GetWrapPins@CDShowTransGraph@@QEAAJW4_PinDirection@@AEAV?$CObjectArray@VCDShowTransPin@@@@@Z; CDShowTransGraph::GetWrapPins(_PinDirection,CObjectArray<CDShowTransPin> &)
0x180027f7f  mov     esi, eax
0x180027f81  test    eax, eax
0x180027f83  jns     short loc_180027FFE
0x180027f85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f8c  test    rcx, rcx
0x180027f8f  jnz     short loc_180027F9D
0x180027f91  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180027f96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180027f9d  cmp     [rcx+8], dil
0x180027fa1  jz      short loc_180027FC8
0x180027fa3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027fa8  cmp     [rax+7CCh], esi
0x180027fae  jz      short loc_180027FC8
0x180027fb0  mov     r9d, esi; int
0x180027fb3  mov     r8d, 26Ah; int
0x180027fb9  lea     rdx, aCdshowtransfor_8; "CDShowTransform::UpdateOutputPins"
0x180027fc0  mov     rcx, rax; this
0x180027fc3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027fc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027fcf  jb      short loc_180027FF4
0x180027fd1  mov     edx, 29h ; ')'
0x180027fd6  mov     [rsp+98h+var_78], esi
0x180027fda  mov     r9, r13
0x180027fdd  lea     r8, WPP_4424637dafd93ac8aa68a350a9714af2_Traceguids
0x180027fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027feb  mov     rcx, [rcx+10h]
0x180027fef  call    WPP_SF_qD
0x180027ff4  mov     r15, [rsp+98h+var_60]
0x180027ff9  jmp     loc_180027F20
0x180027ffe  mov     r14, rdi
0x180028001  mov     [rsp+98h+arg_10], rdi
0x180028009  mov     r15, [rsp+98h+var_60]
0x18002800e  cmp     r14, [rsp+98h+var_58]
0x180028013  jnb     loc_180027F20
0x180028019  lea     rbx, [r13+0C0h]
0x180028020  mov     rdx, rbx
0x180028023  mov     rcx, [r15+r14*8]
0x180028027  call    ??$FindPin@VCDShowTransformOutput@@@CDShowTransformPinArrayTraits@@SAPEAVCDShowTransformOutput@@PEAVCDShowTransPin@@AEAV?$CAtlArray@PEAVCDShowTransformOutput@@V?$CElementTraits@PEAVCDShowTransformOutput@@@ATL@@@ATL@@@Z; CDShowTransformPinArrayTraits::FindPin<CDShowTransformOutput>(CDShowTransPin *,ATL::CAtlArray<CDShowTransformOutput *,ATL::CElementTraits<CDShowTransformOutput *>> &)
0x18002802c  test    rax, rax
0x18002802f  jnz     loc_180028154
0x180028035  lea     ecx, [rax+40h]; Size
0x180028038  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002803d  mov     r12, rax
0x180028040  mov     [rsp+98h+arg_8], rax
0x180028048  test    rax, rax
0x18002804b  jz      short loc_180028075
0x18002804d  mov     rbx, [r15+r14*8]
0x180028051  mov     rdx, rbx; struct CDShowTransPin *
0x180028054  mov     rcx, rax; this
0x180028057  call    ??0CDShowTransformIOBase@@QEAA@PEAVCDShowTransPin@@@Z; CDShowTransformIOBase::CDShowTransformIOBase(CDShowTransPin *)
0x18002805c  lea     rax, ??_7CDShowTransformOutput@@6B@; const CDShowTransformOutput::`vftable'
0x180028063  mov     [r12], rax
0x180028067  mov     [r12+38h], rbx
0x18002806c  lea     rbx, [r13+0C0h]
0x180028073  jmp     short loc_180028078
0x180028075  mov     r12, rdi
0x180028078  mov     [rsp+98h+arg_18], r12
0x180028080  test    r12, r12
0x180028083  jnz     loc_180028123
0x180028089  mov     esi, 8007000Eh
0x18002808e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180028095  test    rcx, rcx
0x180028098  jnz     short loc_1800280E1
0x18002809a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800280a1  nop     dword ptr [rax+rax+00h]
0x1800280a6  mov     rcx, rax
0x1800280a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800280b0  test    rax, rax
0x1800280b3  jz      short loc_1800280D3
0x1800280b5  mov     rax, [rax]
0x1800280b8  mov     edx, 7F0h
0x1800280bd  mov     rax, [rax+8]
0x1800280c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280c6  test    eax, eax
0x1800280c8  jz      short loc_1800280D3
0x1800280ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800280d1  jmp     short loc_1800280E1
0x1800280d3  lea     rcx, qword_1800EB130; this
0x1800280da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800280e1  cmp     [rcx+8], dil
0x1800280e5  jz      short loc_18002810C
0x1800280e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800280ec  cmp     [rax+7CCh], esi
0x1800280f2  jz      short loc_18002810C
0x1800280f4  mov     r9d, esi; int
0x1800280f7  mov     r8d, 274h; int
0x1800280fd  lea     rdx, aCdshowtransfor_8; "CDShowTransform::UpdateOutputPins"
0x180028104  mov     rcx, rax; this
0x180028107  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002810c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028113  jb      loc_180027F20
0x180028119  mov     edx, 2Ah ; '*'
0x18002811e  jmp     loc_180027F01
0x180028123  lea     rdx, [rsp+98h+arg_18]
0x18002812b  mov     rcx, rbx
0x18002812e  call    ?Add@?$CAtlArray@PEAVCDShowTransformInput@@V?$CElementTraits@PEAVCDShowTransformInput@@@ATL@@@ATL@@QEAA_KAEBQEAVCDShowTransformInput@@@Z; ATL::CAtlArray<CDShowTransformInput *,ATL::CElementTraits<CDShowTransformInput *>>::Add(CDShowTransformInput * const &)
0x180028133  nop
0x180028134  jmp     short loc_180028154
0x180028136  xor     edi, edi
0x180028138  mov     r13, [rsp+98h+arg_0]
0x180028140  mov     esi, dword ptr [rsp+98h+arg_8]
0x180028147  mov     r15, [rsp+98h+var_60]
0x18002814c  mov     r14, [rsp+98h+arg_10]
0x180028154  inc     r14
0x180028157  mov     [rsp+98h+arg_10], r14
0x18002815f  jmp     loc_18002800E
```
