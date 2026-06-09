# CMPEG2AudDecMFT::CMPEG2AudDecMFT(IUnknown *,long *)

- ea: `0x18006bb40`
- end: `0x18006bcd6`
- name: `??0CMPEG2AudDecMFT@@QEAA@PEAUIUnknown@@PEAJ@Z`
- size: `406`
- prototype: `CMPEG2AudDecMFT *__fastcall(CMPEG2AudDecMFT *__hidden this, struct IUnknown *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d050`

## callees

- `0x18002fa18`
- `0x18002fe68`
- `0x18004ced0`
- `0x18006baa4`
- `0x18006bb40`
- `0x18006bcdc`
- `0x18006bffc`
- `0x18006c2c4`
- `0x18006c394`
- `0x18006c754`
- `0x18006c858`
- `0x18006eb84`

## string_xrefs

- `0x18006bbb1`: `<c:CertificateCollection xmlns="http://www.w3.org/2000/09/xmldsig#" xmlns:c="http://schemas.microsoft.com/DRM/2004/02/cert" c:Version="2.0"><c:Certificate c:Version="2.0" xmlns:c="http://schemas.microsoft.com/DRM/2004/02/cert"><c:Data xmlns="http://schemas.microsoft.com/DRM/2004/02/cert" xmlns:m="http://www.microsoft.com/DRM/2004/11/mslp"><c:PublicKey><KeyValue><RSAKeyValue><Modulus>rLVGP31dhWuMiQMhX8SpNs8Kx57p89ONCklGLqQMNcd96H2O2DAsAlvzfxfszou5f/fxLYRum/VsbAxfBcUJJtTVTh4U5AiJutLoefU6G1NT1Drdpx`

## pseudocode

```c
CMPEG2AudDecMFT *__fastcall CMPEG2AudDecMFT::CMPEG2AudDecMFT(CMPEG2AudDecMFT *this, struct IUnknown *a2, int *a3)
{
  unsigned int v5; // r8d
  int LocalBuffer; // ebx
  CMPEGFrameSniffer *v7; // rax
  CMPEGFrameSniffer *v8; // rax
  CMPEGFrameSniffer *v9; // rdi
  unsigned int v10; // edx
  unsigned int v12; // [rsp+20h] [rbp-68h]
  unsigned int v13; // [rsp+30h] [rbp-58h]
  unsigned int v14; // [rsp+40h] [rbp-48h]
  unsigned int v15; // [rsp+48h] [rbp-40h]

  _InterlockedAdd(&CBaseObject::m_cObjects, 1u);
  if ( !a2 )
    a2 = (struct IUnknown *)this;
  *((_QWORD *)this + 1) = a2;
  *((_DWORD *)this + 4) = 0;
  CMFValidatedAttributesImpl<IMFAttributes>::CMFValidatedAttributesImpl<IMFAttributes>((char *)this + 24, a2, a3, a3);
  CMFTSimpleBase::CMFTSimpleBase((CMPEG2AudDecMFT *)((char *)this + 120));
  CMFSampleProtection::CMFSampleProtection(
    (CMPEG2AudDecMFT *)((char *)this + 272),
    g_MPEG2AudDecMFT_CertificateRC4,
    v5,
    &g_MPEG2AudDecMFT_PrivateKeyRC4,
    v12,
    "CHAI",
    v13,
    &g_MPEG2AudDecMFT_PrivateKeyAES128CTR,
    v14,
    v15);
  *((_QWORD *)this + 129) = 0;
  *(_QWORD *)this = &CMPEG2AudDecMFT::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 130) = 0;
  *((_QWORD *)this + 3) = &CMPEG2AudDecMFT::`vftable'{for `CMFValidatedAttributesImpl<IMFAttributes>'};
  *((_QWORD *)this + 15) = &CMPEG2AudDecMFT::`vftable'{for `CMFTSimpleBase'};
  *((_QWORD *)this + 34) = &CMPEG2AudDecMFT::`vftable'{for `CMFSampleProtection'};
  *((_QWORD *)this + 131) = 0;
  *((_QWORD *)this + 132) = 0;
  *((_QWORD *)this + 133) = 0;
  *((_QWORD *)this + 134) = 0;
  *((_DWORD *)this + 270) = 1;
  *((_DWORD *)this + 66) = 0;
  *((_DWORD *)this + 52) = 1;
  LocalBuffer = CMPEG2AudDecMFT::ConfigInputTypes(this);
  if ( LocalBuffer < 0 )
    goto LABEL_14;
  LocalBuffer = CMPEG2AudDecMFT::ConfigOutputTypes(this);
  if ( LocalBuffer < 0 )
    goto LABEL_14;
  LocalBuffer = CMPEG2AudDecMFT::OpenDecoder(this);
  if ( LocalBuffer < 0 )
    goto LABEL_14;
  v7 = (CMPEGFrameSniffer *)operator new(0x538u);
  if ( !v7
    || (v8 = CMPEGFrameSniffer::CMPEGFrameSniffer(
               v7,
               (struct CMFSampleProtection *)(((unsigned __int64)this + 272) & -(__int64)(this != 0))),
        (v9 = v8) == 0) )
  {
    LocalBuffer = -2147024882;
    goto LABEL_14;
  }
  LocalBuffer = CMPEGFrameSniffer::CFrameParser::AllocateLocalBuffer((CMPEGFrameSniffer *)((char *)v8 + 8), 4u);
  if ( LocalBuffer >= 0 )
    LocalBuffer = CMPEGFrameSniffer::CFrameParser::AllocateSamplePropertyQueue(
                    (CMPEGFrameSniffer *)((char *)v9 + 8),
                    4u);
  if ( LocalBuffer < 0 )
  {
    CMPEGFrameSniffer::`scalar deleting destructor'(v9, v10);
LABEL_14:
    *a3 = LocalBuffer;
    return this;
  }
  *((_QWORD *)this + 130) = v9;
  return this;
}

```

## disassembly

```asm
0x18006bb40  push    rbx
0x18006bb42  push    rbp
0x18006bb43  push    rsi
0x18006bb44  push    rdi
0x18006bb45  push    r12
0x18006bb47  push    r14
0x18006bb49  push    r15
0x18006bb4b  sub     rsp, 50h
0x18006bb4f  mov     r15, r8
0x18006bb52  mov     rsi, rcx
0x18006bb55  mov     ebp, 1
0x18006bb5a  lock add cs:?m_cObjects@CBaseObject@@0JA, ebp; long CBaseObject::m_cObjects
0x18006bb61  xor     r12d, r12d
0x18006bb64  mov     r9, r8
0x18006bb67  test    rdx, rdx
0x18006bb6a  cmovz   rdx, rcx
0x18006bb6e  mov     [rcx+8], rdx
0x18006bb72  mov     [rcx+10h], r12d
0x18006bb76  add     rcx, 18h
0x18006bb7a  call    ??0?$CMFValidatedAttributesImpl@UIMFAttributes@@@@QEAA@PEAU_AttributeInfo@@IPEAJH@Z; CMFValidatedAttributesImpl<IMFAttributes>::CMFValidatedAttributesImpl<IMFAttributes>(_AttributeInfo *,uint,long *,int)
0x18006bb7f  lea     rcx, [rsi+78h]; this
0x18006bb83  call    ??0CMFTSimpleBase@@QEAA@XZ; CMFTSimpleBase::CMFTSimpleBase(void)
0x18006bb88  lea     rax, ?g_MPEG2AudDecMFT_PrivateKeyAES128CTR@@3QBEB; uchar const near * const g_MPEG2AudDecMFT_PrivateKeyAES128CTR
0x18006bb8f  mov     [rsp+88h+var_50], rax; unsigned __int8 *
0x18006bb94  lea     r14, [rsi+110h]
0x18006bb9b  lea     rax, ?g_MPEG2AudDecMFT_CertificateAES128CTR@@3QBEB; "CHAI"
0x18006bba2  mov     rcx, r14; this
0x18006bba5  lea     r9, ?g_MPEG2AudDecMFT_PrivateKeyRC4@@3QBEB; unsigned __int8 *
0x18006bbac  mov     [rsp+88h+var_60], rax; unsigned __int8 *
0x18006bbb1  lea     rdx, ?g_MPEG2AudDecMFT_CertificateRC4@@3QBEB; "<c:CertificateCollection xmlns=\"http:/"...
0x18006bbb8  call    ??0CMFSampleProtection@@QEAA@PEBEK0K0K0KK@Z; CMFSampleProtection::CMFSampleProtection(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,ulong)
0x18006bbbd  mov     [rsi+408h], r12
0x18006bbc4  lea     rax, ??_7CMPEG2AudDecMFT@@6BCUnknown@@@; const CMPEG2AudDecMFT::`vftable'{for `CUnknown'}
0x18006bbcb  mov     [rsi], rax
0x18006bbce  mov     rcx, rsi; this
0x18006bbd1  mov     [rsi+410h], r12
0x18006bbd8  lea     rax, ??_7CMPEG2AudDecMFT@@6B?$CMFValidatedAttributesImpl@UIMFAttributes@@@@@; const CMPEG2AudDecMFT::`vftable'{for `CMFValidatedAttributesImpl<IMFAttributes>'}
0x18006bbdf  mov     [rsi+18h], rax
0x18006bbe3  lea     rax, ??_7CMPEG2AudDecMFT@@6BCMFTSimpleBase@@@; const CMPEG2AudDecMFT::`vftable'{for `CMFTSimpleBase'}
0x18006bbea  mov     [rsi+78h], rax
0x18006bbee  lea     rax, ??_7CMPEG2AudDecMFT@@6BCMFSampleProtection@@@; const CMPEG2AudDecMFT::`vftable'{for `CMFSampleProtection'}
0x18006bbf5  mov     [r14], rax
0x18006bbf8  mov     [rsi+418h], r12
0x18006bbff  mov     [rsi+420h], r12
0x18006bc06  mov     [rsi+428h], r12
0x18006bc0d  mov     [rsi+430h], r12
0x18006bc14  mov     [rsi+438h], ebp
0x18006bc1a  mov     [rsi+108h], r12d
0x18006bc21  mov     [rsi+0D0h], ebp
0x18006bc27  call    ?ConfigInputTypes@CMPEG2AudDecMFT@@AEAAJXZ; CMPEG2AudDecMFT::ConfigInputTypes(void)
0x18006bc2c  mov     ebx, eax
0x18006bc2e  test    eax, eax
0x18006bc30  js      loc_18006BCC0
0x18006bc36  mov     rcx, rsi; this
0x18006bc39  call    ?ConfigOutputTypes@CMPEG2AudDecMFT@@AEAAJXZ; CMPEG2AudDecMFT::ConfigOutputTypes(void)
0x18006bc3e  mov     ebx, eax
0x18006bc40  test    eax, eax
0x18006bc42  js      short loc_18006BCC0
0x18006bc44  mov     rcx, rsi; this
0x18006bc47  call    ?OpenDecoder@CMPEG2AudDecMFT@@AEAAJXZ; CMPEG2AudDecMFT::OpenDecoder(void)
0x18006bc4c  mov     ebx, eax
0x18006bc4e  test    eax, eax
0x18006bc50  js      short loc_18006BCC0
0x18006bc52  mov     rax, rsi
0x18006bc55  mov     ecx, 538h; Size
0x18006bc5a  neg     rax
0x18006bc5d  sbb     rbx, rbx
0x18006bc60  and     rbx, r14
0x18006bc63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bc68  test    rax, rax
0x18006bc6b  jz      short loc_18006BCBB
0x18006bc6d  mov     rdx, rbx; struct CMFSampleProtection *
0x18006bc70  mov     rcx, rax; this
0x18006bc73  call    ??0CMPEGFrameSniffer@@IEAA@PEAVCMFSampleProtection@@@Z; CMPEGFrameSniffer::CMPEGFrameSniffer(CMFSampleProtection *)
0x18006bc78  mov     rdi, rax
0x18006bc7b  test    rax, rax
0x18006bc7e  jz      short loc_18006BCBB
0x18006bc80  lea     r14d, [rbp+3]
0x18006bc84  mov     edx, r14d; unsigned int
0x18006bc87  lea     rcx, [rax+8]; this
0x18006bc8b  call    ?AllocateLocalBuffer@CFrameParser@CMPEGFrameSniffer@@QEAAJI@Z; CMPEGFrameSniffer::CFrameParser::AllocateLocalBuffer(uint)
0x18006bc90  mov     ebx, eax
0x18006bc92  test    eax, eax
0x18006bc94  js      short loc_18006BCA4
0x18006bc96  mov     edx, r14d; unsigned int
0x18006bc99  lea     rcx, [rdi+8]; this
0x18006bc9d  call    ?AllocateSamplePropertyQueue@CFrameParser@CMPEGFrameSniffer@@QEAAJI@Z; CMPEGFrameSniffer::CFrameParser::AllocateSamplePropertyQueue(uint)
0x18006bca2  mov     ebx, eax
0x18006bca4  test    ebx, ebx
0x18006bca6  js      short loc_18006BCB1
0x18006bca8  mov     [rsi+410h], rdi
0x18006bcaf  jmp     short loc_18006BCC3
0x18006bcb1  mov     rcx, rdi; this
0x18006bcb4  call    ??_GCMPEGFrameSniffer@@QEAAPEAXI@Z; CMPEGFrameSniffer::`scalar deleting destructor'(uint)
0x18006bcb9  jmp     short loc_18006BCC0
0x18006bcbb  mov     ebx, 8007000Eh
0x18006bcc0  mov     [r15], ebx
0x18006bcc3  mov     rax, rsi
0x18006bcc6  add     rsp, 50h
0x18006bcca  pop     r15
0x18006bccc  pop     r14
0x18006bcce  pop     r12
0x18006bcd0  pop     rdi
0x18006bcd1  pop     rsi
0x18006bcd2  pop     rbp
0x18006bcd3  pop     rbx
0x18006bcd4  retn
```
