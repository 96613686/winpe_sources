# CWMVideoDecMediaObject::~CWMVideoDecMediaObject(void)

- ea: `0x180002858`
- end: `0x18000296b`
- name: `??1CWMVideoDecMediaObject@@UEAA@XZ`
- size: `275`
- prototype: `void __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800029d8`

## callees

- `0x180001450`
- `0x1800026f0`
- `0x180002858`
- `0x180003c70`
- `0x18001fed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002936`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002936`
- `msdmo!MoFreeMediaType` at `0x180002921`
- `msdmo!MoFreeMediaType` at `0x180002921`

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
0x180002858  mov     [rsp+arg_0], rbx
0x18000285d  push    rdi
0x18000285e  sub     rsp, 20h
0x180002862  lea     rax, ??_7CWMVideoDecMediaObject@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CWMVideoDecMediaObject::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x180002869  mov     rbx, rcx
0x18000286c  mov     [rcx], rax
0x18000286f  lea     rdi, [rcx+160h]
0x180002876  lea     rax, ??_7CWMVideoDecMediaObject@@6BIMediaObject@@@; const CWMVideoDecMediaObject::`vftable'{for `IMediaObject'}
0x18000287d  mov     [rcx+30h], rax
0x180002881  lea     rax, ??_7CWMVideoDecMediaObject@@6BIWMVideoDecoderHurryup@@@; const CWMVideoDecMediaObject::`vftable'{for `IWMVideoDecoderHurryup'}
0x180002888  mov     [rcx+128h], rax
0x18000288f  lea     rax, ??_7CWMVideoDecMediaObject@@6BIWMSampleExtensionSupport@@@; const CWMVideoDecMediaObject::`vftable'{for `IWMSampleExtensionSupport'}
0x180002896  mov     [rcx+130h], rax
0x18000289d  lea     rax, ??_7CWMVideoDecMediaObject@@6BCImplDMOVideoOutputOptimizations@@@; const CWMVideoDecMediaObject::`vftable'{for `CImplDMOVideoOutputOptimizations'}
0x1800028a4  mov     [rcx+138h], rax
0x1800028ab  lea     rax, ??_7CWMVideoDecMediaObject@@6BCComBase@@@; const CWMVideoDecMediaObject::`vftable'{for `CComBase'}
0x1800028b2  mov     [rcx+148h], rax
0x1800028b9  lea     rax, ??_7CWMVideoDecMediaObject@@6BCWMDSPPropImpl@@@; const CWMVideoDecMediaObject::`vftable'{for `CWMDSPPropImpl'}
0x1800028c0  mov     rcx, [rcx+630h]; void *
0x1800028c7  mov     [rdi], rax
0x1800028ca  test    rcx, rcx
0x1800028cd  jz      short loc_1800028D4
0x1800028cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800028d4  xorps   xmm0, xmm0
0x1800028d7  xor     eax, eax
0x1800028d9  movups  xmmword ptr [rbx+628h], xmm0
0x1800028e0  movups  xmmword ptr [rbx+638h], xmm0
0x1800028e7  mov     [rbx+648h], rax
0x1800028ee  mov     rcx, [rbx+1D0h]; void *
0x1800028f5  test    rcx, rcx
0x1800028f8  jz      short loc_1800028FF
0x1800028fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800028ff  cmp     dword ptr [rbx+38h], 0
0x180002903  mov     qword ptr [rbx+1D0h], 0
0x18000290e  mov     dword ptr [rbx+1D8h], 0
0x180002918  jz      short loc_180002927
0x18000291a  lea     rcx, [rbx+668h]; pmt
0x180002921  call    cs:__imp_MoFreeMediaType
0x180002927  mov     rcx, rbx; this
0x18000292a  call    ?DeinitDecoder@CWMVideoDecMediaObject@@IEAAJXZ; CWMVideoDecMediaObject::DeinitDecoder(void)
0x18000292f  lea     rcx, [rbx+398h]; lpCriticalSection
0x180002936  call    cs:__imp_DeleteCriticalSection
0x18000293c  mov     rcx, rdi; this
0x18000293f  call    ??1CWMDSPPropImpl@@QEAA@XZ; CWMDSPPropImpl::~CWMDSPPropImpl(void)
0x180002944  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x18000294b  mov     rcx, rbx; this
0x18000294e  mov     [rbx+148h], rax
0x180002955  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18000295c  mov     rbx, [rsp+28h+arg_0]
0x180002961  add     rsp, 20h
0x180002965  pop     rdi
0x180002966  jmp     ??1?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@QEAA@XZ; CWMDSPDMOWMILoggingBase<C1in1outDMO>::~CWMDSPDMOWMILoggingBase<C1in1outDMO>(void)
```
