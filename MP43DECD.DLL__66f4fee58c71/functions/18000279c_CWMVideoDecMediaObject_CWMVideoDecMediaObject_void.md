# CWMVideoDecMediaObject::~CWMVideoDecMediaObject(void)

- ea: `0x18000279c`
- end: `0x1800028af`
- name: `??1CWMVideoDecMediaObject@@UEAA@XZ`
- size: `275`
- prototype: `void __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180002918`

## callees

- `0x180001420`
- `0x180002634`
- `0x18000279c`
- `0x180003bb0`
- `0x18001fe18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000287a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000287a`
- `msdmo!MoFreeMediaType` at `0x180002865`
- `msdmo!MoFreeMediaType` at `0x180002865`

## pseudocode

```c
void __fastcall CWMVideoDecMediaObject::~CWMVideoDecMediaObject(CWMVideoDecMediaObject *this, unsigned __int64 a2)
{
  CWMDSPPropImpl *v3; // rdi
  void *v4; // rcx
  void *v5; // rcx
  bool v6; // zf

  *(_QWORD *)this = &CWMVideoDecMediaObject::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  v3 = (CWMVideoDecMediaObject *)((char *)this + 352);
  *((_QWORD *)this + 6) = &CWMVideoDecMediaObject::`vftable'{for `IMediaObject'};
  *((_QWORD *)this + 37) = &CWMVideoDecMediaObject::`vftable'{for `IWMVideoDecoderHurryup'};
  *((_QWORD *)this + 38) = &CWMVideoDecMediaObject::`vftable'{for `IWMSampleExtensionSupport'};
  *((_QWORD *)this + 39) = &CWMVideoDecMediaObject::`vftable'{for `CImplDMOVideoOutputOptimizations'};
  *((_QWORD *)this + 41) = &CWMVideoDecMediaObject::`vftable'{for `CComBase'};
  v4 = (void *)*((_QWORD *)this + 198);
  *(_QWORD *)v3 = &CWMVideoDecMediaObject::`vftable'{for `CWMDSPPropImpl'};
  if ( v4 )
    operator delete(v4, a2);
  *(_OWORD *)((char *)this + 1576) = 0;
  *(_OWORD *)((char *)this + 1592) = 0;
  *((_QWORD *)this + 201) = 0;
  v5 = (void *)*((_QWORD *)this + 58);
  if ( v5 )
    operator delete(v5, a2);
  v6 = *((_DWORD *)this + 14) == 0;
  *((_QWORD *)this + 58) = 0;
  *((_DWORD *)this + 118) = 0;
  if ( !v6 )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 1640));
  CWMVideoDecMediaObject::DeinitDecoder(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 23);
  CWMDSPPropImpl::~CWMDSPPropImpl(v3);
  *((_QWORD *)this + 41) = &CComBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  CWMDSPDMOWMILoggingBase<C1in1outDMO>::~CWMDSPDMOWMILoggingBase<C1in1outDMO>(this);
}

```

## disassembly

```asm
0x18000279c  mov     [rsp+arg_0], rbx
0x1800027a1  push    rdi
0x1800027a2  sub     rsp, 20h
0x1800027a6  lea     rax, ??_7CWMVideoDecMediaObject@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CWMVideoDecMediaObject::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x1800027ad  mov     rbx, rcx
0x1800027b0  mov     [rcx], rax
0x1800027b3  lea     rdi, [rcx+160h]
0x1800027ba  lea     rax, ??_7CWMVideoDecMediaObject@@6BIMediaObject@@@; const CWMVideoDecMediaObject::`vftable'{for `IMediaObject'}
0x1800027c1  mov     [rcx+30h], rax
0x1800027c5  lea     rax, ??_7CWMVideoDecMediaObject@@6BIWMVideoDecoderHurryup@@@; const CWMVideoDecMediaObject::`vftable'{for `IWMVideoDecoderHurryup'}
0x1800027cc  mov     [rcx+128h], rax
0x1800027d3  lea     rax, ??_7CWMVideoDecMediaObject@@6BIWMSampleExtensionSupport@@@; const CWMVideoDecMediaObject::`vftable'{for `IWMSampleExtensionSupport'}
0x1800027da  mov     [rcx+130h], rax
0x1800027e1  lea     rax, ??_7CWMVideoDecMediaObject@@6BCImplDMOVideoOutputOptimizations@@@; const CWMVideoDecMediaObject::`vftable'{for `CImplDMOVideoOutputOptimizations'}
0x1800027e8  mov     [rcx+138h], rax
0x1800027ef  lea     rax, ??_7CWMVideoDecMediaObject@@6BCComBase@@@; const CWMVideoDecMediaObject::`vftable'{for `CComBase'}
0x1800027f6  mov     [rcx+148h], rax
0x1800027fd  lea     rax, ??_7CWMVideoDecMediaObject@@6BCWMDSPPropImpl@@@; const CWMVideoDecMediaObject::`vftable'{for `CWMDSPPropImpl'}
0x180002804  mov     rcx, [rcx+630h]; void *
0x18000280b  mov     [rdi], rax
0x18000280e  test    rcx, rcx
0x180002811  jz      short loc_180002818
0x180002813  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002818  xorps   xmm0, xmm0
0x18000281b  xor     eax, eax
0x18000281d  movups  xmmword ptr [rbx+628h], xmm0
0x180002824  movups  xmmword ptr [rbx+638h], xmm0
0x18000282b  mov     [rbx+648h], rax
0x180002832  mov     rcx, [rbx+1D0h]; void *
0x180002839  test    rcx, rcx
0x18000283c  jz      short loc_180002843
0x18000283e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002843  cmp     dword ptr [rbx+38h], 0
0x180002847  mov     qword ptr [rbx+1D0h], 0
0x180002852  mov     dword ptr [rbx+1D8h], 0
0x18000285c  jz      short loc_18000286B
0x18000285e  lea     rcx, [rbx+668h]; pmt
0x180002865  call    cs:__imp_MoFreeMediaType
0x18000286b  mov     rcx, rbx; this
0x18000286e  call    ?DeinitDecoder@CWMVideoDecMediaObject@@IEAAJXZ; CWMVideoDecMediaObject::DeinitDecoder(void)
0x180002873  lea     rcx, [rbx+398h]; lpCriticalSection
0x18000287a  call    cs:__imp_DeleteCriticalSection
0x180002880  mov     rcx, rdi; this
0x180002883  call    ??1CWMDSPPropImpl@@QEAA@XZ; CWMDSPPropImpl::~CWMDSPPropImpl(void)
0x180002888  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x18000288f  mov     rcx, rbx; this
0x180002892  mov     [rbx+148h], rax
0x180002899  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800028a0  mov     rbx, [rsp+28h+arg_0]
0x1800028a5  add     rsp, 20h
0x1800028a9  pop     rdi
0x1800028aa  jmp     ??1?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@QEAA@XZ; CWMDSPDMOWMILoggingBase<C1in1outDMO>::~CWMDSPDMOWMILoggingBase<C1in1outDMO>(void)
```
