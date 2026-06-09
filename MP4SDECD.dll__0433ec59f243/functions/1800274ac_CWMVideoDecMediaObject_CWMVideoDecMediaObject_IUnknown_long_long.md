# CWMVideoDecMediaObject::CWMVideoDecMediaObject(IUnknown *,long *,long)

- ea: `0x1800274ac`
- end: `0x1800277e4`
- name: `??0CWMVideoDecMediaObject@@QEAA@PEAUIUnknown@@PEAJJ@Z`
- size: `824`
- prototype: `CWMVideoDecMediaObject *(CWMVideoDecMediaObject *__hidden this, struct IUnknown *, int *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180028030`
- `0x18002c460`

## callees

- `0x1800274ac`
- `0x1800277ec`
- `0x180028bc0`
- `0x180028f74`
- `0x18002b394`
- `0x180046010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180027779`
- `MFPlat!MFCreateAttributes` at `0x180027779`
- `msdmo!MoInitMediaType` at `0x180027711`
- `msdmo!MoInitMediaType` at `0x180027711`

## pseudocode

```c
CWMVideoDecMediaObject *__fastcall CWMVideoDecMediaObject::CWMVideoDecMediaObject(
        CWMVideoDecMediaObject *this,
        struct IUnknown *a2,
        int *a3,
        int a4)
{
  const struct _WMDSPPropInfo *v8; // rdx
  unsigned int v9; // r8d
  struct IUnknown *v10; // rax
  GUID **v11; // r9
  unsigned int v12; // edx
  unsigned int v13; // r8d
  GUID *v14; // rcx
  HRESULT v15; // eax
  const struct _GUID *v17; // [rsp+20h] [rbp-58h]
  const struct _GUID *v18; // [rsp+28h] [rbp-50h]

  CWMDSPDMOWMILoggingBase<C1in1outDMO>::CWMDSPDMOWMILoggingBase<C1in1outDMO>();
  *(_QWORD *)this = &CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  *((_QWORD *)this + 6) = &CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `IMediaObject'};
  CImplDMOVideoOutputOptimizations::CImplDMOVideoOutputOptimizations((CWMVideoDecMediaObject *)((char *)this + 328));
  _InterlockedAdd(&g_cActiveObjects, 1u);
  *((_QWORD *)this + 43) = &CComBase::`vftable';
  v10 = (struct IUnknown *)((char *)this + 344);
  if ( a2 )
    v10 = a2;
  *((_QWORD *)this + 44) = v10;
  *((_DWORD *)this + 90) = 0;
  CWMDSPPropImpl::CWMDSPPropImpl((CWMVideoDecMediaObject *)((char *)this + 368), v8, v9, a3, v17, v18);
  *((_DWORD *)this + 312) = a4;
  *(_QWORD *)this = &CWMVideoDecMediaObject::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  v11 = off_180059020;
  *((_DWORD *)this + 324) = 100;
  *((_QWORD *)this + 6) = &CWMVideoDecMediaObject::`vftable'{for `IMediaObject'};
  v12 = 0;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 39) = &CWMVideoDecMediaObject::`vftable'{for `IWMVideoDecoderHurryup'};
  *((_QWORD *)this + 40) = &CWMVideoDecMediaObject::`vftable'{for `IWMSampleExtensionSupport'};
  *((_QWORD *)this + 41) = &CWMVideoDecMediaObject::`vftable'{for `CImplDMOVideoOutputOptimizations'};
  *((_QWORD *)this + 43) = &CWMVideoDecMediaObject::`vftable'{for `CComBase'};
  *((_QWORD *)this + 46) = &CWMVideoDecMediaObject::`vftable'{for `CWMDSPPropImpl'};
  *((_QWORD *)this + 57) = &CWMVideoDecMediaObject::`vftable'{for `ICodecAPI'};
  *((_QWORD *)this + 58) = &CWMVideoDecMediaObject::`vftable'{for `IDMOQualityControl'};
  *((_QWORD *)this + 59) = &CWMVideoDecMediaObject::`vftable'{for `IMFQualityAdvise2'};
  *((_QWORD *)this + 60) = &CWMVideoDecMediaObject::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 61) = &CWMVideoDecMediaObject::`vftable'{for `IMFRateControl'};
  *((_QWORD *)this + 62) = &CWMVideoDecMediaObject::`vftable'{for `IMFRateSupport'};
  v13 = a4 != 0 ? 2 : 11;
  *((_DWORD *)this + 328) = v13;
  *((_DWORD *)this + 129) = v13;
  if ( !a4 )
    v11 = off_1800590A0;
  *((_DWORD *)this + 128) = v13;
  *((_QWORD *)this + 163) = v11;
  do
  {
    v14 = v11[v12];
    if ( v14->Data1 == 842094158 )
    {
      *((_DWORD *)this + 128) = v12;
    }
    else if ( v14->Data1 == 842094169 )
    {
      *((_DWORD *)this + 129) = v12;
    }
    ++v12;
  }
  while ( v12 < v13 );
  *((_QWORD *)this + 65) = 1;
  *((_DWORD *)this + 145) = -1;
  *((_DWORD *)this + 158) = -1;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *(_QWORD *)((char *)this + 564) = 0;
  *(_QWORD *)((char *)this + 572) = 0;
  *((_DWORD *)this + 146) = 0;
  *((_DWORD *)this + 147) = 1;
  *((_QWORD *)this + 74) = 1;
  *((_BYTE *)this + 600) = 0;
  *(_QWORD *)((char *)this + 604) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_DWORD *)this + 159) = 0;
  *((_QWORD *)this + 144) = 0;
  *(_QWORD *)((char *)this + 1252) = 0;
  *((_DWORD *)this + 315) = 0;
  *((_QWORD *)this + 159) = 0;
  *((_QWORD *)this + 160) = 0;
  *((_QWORD *)this + 161) = 0;
  MoInitMediaType((DMO_MEDIA_TYPE *)((char *)this + 1160), 0);
  *((_BYTE *)this + 43) = 1;
  memset_0((char *)this + 1320, 0, 0xB0u);
  memset_0((char *)this + 1496, 0, 0xB0u);
  memset_0((char *)this + 1672, 0, 0xB0u);
  *((_QWORD *)this + 231) = 1;
  *((_QWORD *)this + 232) = 0;
  *((_DWORD *)this + 466) = 1065353216;
  v15 = MFCreateAttributes((IMFAttributes **)this + 234, 1u);
  if ( !*((_QWORD *)this + 234)
    || (v15 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD))(**((_QWORD **)this + 234) + 168LL))(
                *((_QWORD *)this + 234),
                &GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4,
                0),
        v15 < 0)
    || (v15 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD))(**((_QWORD **)this + 234) + 168LL))(
                *((_QWORD *)this + 234),
                &GUID_fb5d2347_4dd8_4509_aed0_db5fa9aa93f4,
                *((unsigned int *)this + 324)),
        v15 < 0) )
  {
    if ( a3 )
      *a3 = v15;
  }
  return this;
}

```

## disassembly

```asm
0x1800274ac  push    rbx
0x1800274ae  push    rbp
0x1800274af  push    rsi
0x1800274b0  push    rdi
0x1800274b1  push    r12
0x1800274b3  push    r13
0x1800274b5  push    r14
0x1800274b7  push    r15
0x1800274b9  sub     rsp, 38h
0x1800274bd  mov     ebp, r9d
0x1800274c0  mov     r15, r8
0x1800274c3  mov     rbx, rdx
0x1800274c6  mov     r14, rcx
0x1800274c9  call    ??0?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@QEAA@KW4_MFWMI_OBJECT_TYPE@@@Z; CWMDSPDMOWMILoggingBase<C1in1outDMO>::CWMDSPDMOWMILoggingBase<C1in1outDMO>(ulong,_MFWMI_OBJECT_TYPE)
0x1800274ce  lea     rax, ??_7?$CSecureDMO@V?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x1800274d5  mov     [r14], rax
0x1800274d8  lea     rsi, [r14+148h]
0x1800274df  lea     rax, ??_7?$CSecureDMO@V?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@@@6BIMediaObject@@@; const CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `IMediaObject'}
0x1800274e6  mov     rcx, rsi; this
0x1800274e9  mov     [r14+30h], rax
0x1800274ed  call    ??0CImplDMOVideoOutputOptimizations@@QEAA@XZ; CImplDMOVideoOutputOptimizations::CImplDMOVideoOutputOptimizations(void)
0x1800274f2  lea     rdi, [r14+158h]
0x1800274f9  mov     r13d, 1
0x1800274ff  lock add cs:?g_cActiveObjects@@3JC, r13d; long volatile g_cActiveObjects
0x180027507  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x18002750e  xor     r12d, r12d
0x180027511  mov     [rdi], rax
0x180027514  test    rbx, rbx
0x180027517  mov     rax, rdi
0x18002751a  mov     r9, r15; int *
0x18002751d  cmovnz  rax, rbx
0x180027521  lea     rbx, [r14+170h]
0x180027528  mov     [rdi+8], rax
0x18002752c  mov     rcx, rbx; this
0x18002752f  mov     [rdi+10h], r12d
0x180027533  call    ??0CWMDSPPropImpl@@QEAA@PEBU_WMDSPPropInfo@@KPEAJPEBU_GUID@@2@Z; CWMDSPPropImpl::CWMDSPPropImpl(_WMDSPPropInfo const *,ulong,long *,_GUID const *,_GUID const *)
0x180027538  lea     rax, ??_7CWMVideoDecMediaObject@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CWMVideoDecMediaObject::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x18002753f  mov     [r14+4E0h], ebp
0x180027546  mov     [r14], rax
0x180027549  lea     r9, off_180059020
0x180027550  lea     rax, ??_7CWMVideoDecMediaObject@@6BIMediaObject@@@; const CWMVideoDecMediaObject::`vftable'{for `IMediaObject'}
0x180027557  mov     dword ptr [r14+510h], 64h ; 'd'
0x180027562  mov     [r14+30h], rax
0x180027566  mov     edx, r12d
0x180027569  lea     rax, ??_7CWMVideoDecMediaObject@@6BIWMVideoDecoderHurryup@@@; const CWMVideoDecMediaObject::`vftable'{for `IWMVideoDecoderHurryup'}
0x180027570  mov     [r14+1F8h], r12
0x180027577  mov     [r14+138h], rax
0x18002757e  lea     rax, ??_7CWMVideoDecMediaObject@@6BIWMSampleExtensionSupport@@@; const CWMVideoDecMediaObject::`vftable'{for `IWMSampleExtensionSupport'}
0x180027585  mov     [r14+140h], rax
0x18002758c  lea     rax, ??_7CWMVideoDecMediaObject@@6BCImplDMOVideoOutputOptimizations@@@; const CWMVideoDecMediaObject::`vftable'{for `CImplDMOVideoOutputOptimizations'}
0x180027593  mov     [rsi], rax
0x180027596  lea     rax, ??_7CWMVideoDecMediaObject@@6BCComBase@@@; const CWMVideoDecMediaObject::`vftable'{for `CComBase'}
0x18002759d  mov     [rdi], rax
0x1800275a0  lea     rax, ??_7CWMVideoDecMediaObject@@6BCWMDSPPropImpl@@@; const CWMVideoDecMediaObject::`vftable'{for `CWMDSPPropImpl'}
0x1800275a7  mov     [rbx], rax
0x1800275aa  lea     rax, ??_7CWMVideoDecMediaObject@@6BICodecAPI@@@; const CWMVideoDecMediaObject::`vftable'{for `ICodecAPI'}
0x1800275b1  mov     [r14+1C8h], rax
0x1800275b8  lea     rax, ??_7CWMVideoDecMediaObject@@6BIDMOQualityControl@@@; const CWMVideoDecMediaObject::`vftable'{for `IDMOQualityControl'}
0x1800275bf  mov     [r14+1D0h], rax
0x1800275c6  lea     rax, ??_7CWMVideoDecMediaObject@@6BIMFQualityAdvise2@@@; const CWMVideoDecMediaObject::`vftable'{for `IMFQualityAdvise2'}
0x1800275cd  mov     [r14+1D8h], rax
0x1800275d4  lea     rax, ??_7CWMVideoDecMediaObject@@6BIMFGetService@@@; const CWMVideoDecMediaObject::`vftable'{for `IMFGetService'}
0x1800275db  mov     [r14+1E0h], rax
0x1800275e2  lea     rax, ??_7CWMVideoDecMediaObject@@6BIMFRateControl@@@; const CWMVideoDecMediaObject::`vftable'{for `IMFRateControl'}
0x1800275e9  mov     [r14+1E8h], rax
0x1800275f0  lea     rax, ??_7CWMVideoDecMediaObject@@6BIMFRateSupport@@@; const CWMVideoDecMediaObject::`vftable'{for `IMFRateSupport'}
0x1800275f7  mov     [r14+1F0h], rax
0x1800275fe  mov     eax, ebp
0x180027600  neg     eax
0x180027602  lea     rax, off_1800590A0
0x180027609  sbb     r8d, r8d
0x18002760c  and     r8d, 0FFFFFFF7h
0x180027610  add     r8d, 0Bh
0x180027614  test    ebp, ebp
0x180027616  mov     [r14+520h], r8d
0x18002761d  mov     [r14+204h], r8d
0x180027624  cmovz   r9, rax
0x180027628  mov     [r14+200h], r8d
0x18002762f  mov     [r14+518h], r9
0x180027636  mov     eax, edx
0x180027638  mov     rcx, [r9+rax*8]
0x18002763c  cmp     dword ptr [rcx], 3231564Eh
0x180027642  jnz     short loc_18002764D
0x180027644  mov     [r14+200h], edx
0x18002764b  jmp     short loc_18002765C
0x18002764d  cmp     dword ptr [rcx], 32315659h
0x180027653  jnz     short loc_18002765C
0x180027655  mov     [r14+204h], edx
0x18002765c  add     edx, r13d
0x18002765f  cmp     edx, r8d
0x180027662  jb      short loc_180027636
0x180027664  or      eax, 0FFFFFFFFh
0x180027667  mov     [r14+208h], r13
0x18002766e  lea     rcx, [r14+488h]; pmt
0x180027675  mov     [r14+244h], eax
0x18002767c  xor     edx, edx; cbFormat
0x18002767e  mov     [r14+278h], eax
0x180027685  mov     [r14+210h], r12
0x18002768c  mov     [r14+218h], r12
0x180027693  mov     [r14+220h], r12
0x18002769a  mov     [r14+228h], r12
0x1800276a1  mov     [r14+234h], r12
0x1800276a8  mov     [r14+23Ch], r12
0x1800276af  mov     [r14+248h], r12d
0x1800276b6  mov     [r14+24Ch], r13d
0x1800276bd  mov     [r14+250h], r13
0x1800276c4  mov     [r14+258h], r12b
0x1800276cb  mov     [r14+25Ch], r12
0x1800276d2  mov     [r14+268h], r12
0x1800276d9  mov     [r14+270h], r12
0x1800276e0  mov     [r14+27Ch], r12d
0x1800276e7  mov     [r14+480h], r12
0x1800276ee  mov     [r14+4E4h], r12
0x1800276f5  mov     [r14+4ECh], r12d
0x1800276fc  mov     [r14+4F8h], r12
0x180027703  mov     [r14+500h], r12
0x18002770a  mov     [r14+508h], r12
0x180027711  call    cs:__imp_MoInitMediaType
0x180027717  mov     ebx, 0B0h
0x18002771c  mov     [r14+2Bh], r13b
0x180027720  mov     r8d, ebx; Size
0x180027723  lea     rcx, [r14+528h]; void *
0x18002772a  xor     edx, edx; Val
0x18002772c  call    memset_0
0x180027731  lea     rcx, [r14+5D8h]; void *
0x180027738  mov     r8d, ebx; Size
0x18002773b  xor     edx, edx; Val
0x18002773d  call    memset_0
0x180027742  lea     rcx, [r14+688h]; void *
0x180027749  mov     r8d, ebx; Size
0x18002774c  xor     edx, edx; Val
0x18002774e  call    memset_0
0x180027753  lea     rbx, [r14+750h]
0x18002775a  mov     [r14+738h], r13
0x180027761  mov     rcx, rbx; ppMFAttributes
0x180027764  mov     [r14+740h], r12
0x18002776b  mov     edx, r13d; cInitialSize
0x18002776e  mov     dword ptr [r14+748h], 3F800000h
0x180027779  call    cs:__imp_MFCreateAttributes
0x18002777f  mov     rcx, [rbx]
0x180027782  test    rcx, rcx
0x180027785  jz      short loc_1800277C8
0x180027787  mov     rax, [rcx]
0x18002778a  lea     rdx, _GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4
0x180027791  xor     r8d, r8d
0x180027794  mov     rax, [rax+0A8h]
0x18002779b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277a0  test    eax, eax
0x1800277a2  js      short loc_1800277C8
0x1800277a4  mov     rcx, [rbx]
0x1800277a7  lea     rdx, _GUID_fb5d2347_4dd8_4509_aed0_db5fa9aa93f4
0x1800277ae  mov     r8d, [r14+510h]
0x1800277b5  mov     rax, [rcx]
0x1800277b8  mov     rax, [rax+0A8h]
0x1800277bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277c4  test    eax, eax
0x1800277c6  jns     short loc_1800277D0
0x1800277c8  test    r15, r15
0x1800277cb  jz      short loc_1800277D0
0x1800277cd  mov     [r15], eax
0x1800277d0  mov     rax, r14
0x1800277d3  add     rsp, 38h
0x1800277d7  pop     r15
0x1800277d9  pop     r14
0x1800277db  pop     r13
0x1800277dd  pop     r12
0x1800277df  pop     rdi
0x1800277e0  pop     rsi
0x1800277e1  pop     rbp
0x1800277e2  pop     rbx
0x1800277e3  retn
```
