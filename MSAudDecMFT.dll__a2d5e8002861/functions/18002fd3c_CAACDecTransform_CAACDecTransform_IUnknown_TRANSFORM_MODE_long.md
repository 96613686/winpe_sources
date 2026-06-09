# CAACDecTransform::CAACDecTransform(IUnknown *,TRANSFORM_MODE,long *)

- ea: `0x18002fd3c`
- end: `0x18002fe61`
- name: `??0CAACDecTransform@@QEAA@PEAUIUnknown@@W4TRANSFORM_MODE@@PEAJ@Z`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fcf0`
- `0x180056d60`

## callees

- `0x18002fa18`
- `0x18002fe68`
- `0x180030114`
- `0x18004ac28`

## string_xrefs

- `0x18002fdb2`: `<c:CertificateCollection xmlns="http://www.w3.org/2000/09/xmldsig#" xmlns:c="http://schemas.microsoft.com/DRM/2004/02/cert" c:Version="2.0"><c:Certificate c:Version="2.0" xmlns:c="http://schemas.microsoft.com/DRM/2004/02/cert"><c:Data xmlns="http://schemas.microsoft.com/DRM/2004/02/cert" xmlns:m="http://www.microsoft.com/DRM/2004/11/mslp"><c:PublicKey><KeyValue><RSAKeyValue><Modulus>yqxrWikqMMrwoLa3u47YE4c4kRQN84sy768ldRm9f0UiCkt/wc3MJp4MlRM53fFMX98Ijoy0RhMUqHSP2lg6jrG6R0tErITt028InbKZd5L4Ai8YZN`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAACDecTransform::CAACDecTransform(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  __int64 v7; // rax
  unsigned int v8; // r8d
  unsigned int v10; // [rsp+20h] [rbp-68h]
  unsigned int v11; // [rsp+30h] [rbp-58h]
  unsigned int v12; // [rsp+40h] [rbp-48h]
  unsigned int v13; // [rsp+48h] [rbp-40h]

  _InterlockedIncrement(&CBaseObject::m_cObjects);
  v7 = a1;
  if ( a2 )
    v7 = a2;
  *(_QWORD *)(a1 + 8) = v7;
  *(_DWORD *)(a1 + 16) = 0;
  CMFTSimpleBase::CMFTSimpleBase((CMFTSimpleBase *)(a1 + 24));
  CAACDec::CAACDec((CAACDec *)(a1 + 176));
  CMFSampleProtection::CMFSampleProtection(
    (CMFSampleProtection *)(a1 + 255392),
    g_AACAudDecMFT_CertificateRC4,
    v8,
    &g_AACAudDecMFT_PrivateKeyRC4,
    v10,
    "CHAI",
    v11,
    &g_AACAudDecMFT_PrivateKeyAES128CTR,
    v12,
    v13);
  *(_QWORD *)a1 = &CAACDecTransform::`vftable'{for `CUnknown'};
  *(_QWORD *)(a1 + 24) = &CAACDecTransform::`vftable'{for `CMFTSimpleBase'};
  *(_QWORD *)(a1 + 176) = &CAACDecTransform::`vftable'{for `CAACDec'};
  *(_QWORD *)(a1 + 255392) = &CAACDecTransform::`vftable'{for `CMFSampleProtection'};
  *(_QWORD *)(a1 + 256136) = &CAACDecTransform::`vftable'{for `IMFObjectInformation'};
  *(_QWORD *)(a1 + 256144) = &CAACDecTransform::`vftable'{for `IMFTelemetryComponent'};
  *(_DWORD *)(a1 + 256152) = a3;
  *(_DWORD *)(a1 + 256224) = 0;
  *(_QWORD *)(a1 + 256232) = 0;
  *(_QWORD *)(a1 + 256240) = 0;
  *(_QWORD *)(a1 + 256248) = 0;
  *(_DWORD *)(a1 + 256256) = 0;
  *a4 = CAACDecTransform::Initialize((CAACDecTransform *)a1);
  return a1;
}

```

## disassembly

```asm
0x18002fd3c  mov     [rsp+arg_0], rcx
0x18002fd41  push    rbx
0x18002fd42  push    rbp
0x18002fd43  push    rsi
0x18002fd44  push    rdi
0x18002fd45  push    r14
0x18002fd47  push    r15
0x18002fd49  sub     rsp, 58h
0x18002fd4d  mov     r15, r9
0x18002fd50  mov     ebp, r8d
0x18002fd53  mov     r14, rcx
0x18002fd56  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18002fd5d  mov     rax, rcx
0x18002fd60  test    rdx, rdx
0x18002fd63  cmovnz  rax, rdx
0x18002fd67  mov     [rcx+8], rax
0x18002fd6b  mov     dword ptr [rcx+10h], 0
0x18002fd72  add     rcx, 18h; this
0x18002fd76  call    ??0CMFTSimpleBase@@QEAA@XZ; CMFTSimpleBase::CMFTSimpleBase(void)
0x18002fd7b  nop
0x18002fd7c  lea     rdi, [r14+0B0h]
0x18002fd83  mov     rcx, rdi; this
0x18002fd86  call    ??0CAACDec@@QEAA@XZ; CAACDec::CAACDec(void)
0x18002fd8b  nop
0x18002fd8c  lea     rbx, [r14+3E5A0h]
0x18002fd93  lea     rax, ?g_AACAudDecMFT_PrivateKeyAES128CTR@@3QBEB; uchar const near * const g_AACAudDecMFT_PrivateKeyAES128CTR
0x18002fd9a  mov     [rsp+88h+var_50], rax; unsigned __int8 *
0x18002fd9f  lea     rax, ?g_AACAudDecMFT_CertificateAES128CTR@@3QBEB; "CHAI"
0x18002fda6  mov     [rsp+88h+var_60], rax; unsigned __int8 *
0x18002fdab  lea     r9, ?g_AACAudDecMFT_PrivateKeyRC4@@3QBEB; unsigned __int8 *
0x18002fdb2  lea     rdx, ?g_AACAudDecMFT_CertificateRC4@@3QBEB; "<c:CertificateCollection xmlns=\"http:/"...
0x18002fdb9  mov     rcx, rbx; this
0x18002fdbc  call    ??0CMFSampleProtection@@QEAA@PEBEK0K0K0KK@Z; CMFSampleProtection::CMFSampleProtection(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,ulong)
0x18002fdc1  nop
0x18002fdc2  lea     rax, ??_7CAACDecTransform@@6BCUnknown@@@; const CAACDecTransform::`vftable'{for `CUnknown'}
0x18002fdc9  mov     [r14], rax
0x18002fdcc  lea     rax, ??_7CAACDecTransform@@6BCMFTSimpleBase@@@; const CAACDecTransform::`vftable'{for `CMFTSimpleBase'}
0x18002fdd3  mov     [r14+18h], rax
0x18002fdd7  lea     rax, ??_7CAACDecTransform@@6BCAACDec@@@; const CAACDecTransform::`vftable'{for `CAACDec'}
0x18002fdde  mov     [rdi], rax
0x18002fde1  lea     rax, ??_7CAACDecTransform@@6BCMFSampleProtection@@@; const CAACDecTransform::`vftable'{for `CMFSampleProtection'}
0x18002fde8  mov     [rbx], rax
0x18002fdeb  lea     rax, ??_7CAACDecTransform@@6BIMFObjectInformation@@@; const CAACDecTransform::`vftable'{for `IMFObjectInformation'}
0x18002fdf2  mov     [r14+3E888h], rax
0x18002fdf9  lea     rax, ??_7CAACDecTransform@@6BIMFTelemetryComponent@@@; const CAACDecTransform::`vftable'{for `IMFTelemetryComponent'}
0x18002fe00  mov     [r14+3E890h], rax
0x18002fe07  mov     [r14+3E898h], ebp
0x18002fe0e  mov     dword ptr [r14+3E8E0h], 0
0x18002fe19  mov     qword ptr [r14+3E8E8h], 0
0x18002fe24  mov     qword ptr [r14+3E8F0h], 0
0x18002fe2f  mov     qword ptr [r14+3E8F8h], 0
0x18002fe3a  mov     dword ptr [r14+3E900h], 0
0x18002fe45  mov     rcx, r14; this
0x18002fe48  call    ?Initialize@CAACDecTransform@@QEAAJXZ; CAACDecTransform::Initialize(void)
0x18002fe4d  mov     [r15], eax
0x18002fe50  mov     rax, r14
0x18002fe53  add     rsp, 58h
0x18002fe57  pop     r15
0x18002fe59  pop     r14
0x18002fe5b  pop     rdi
0x18002fe5c  pop     rsi
0x18002fe5d  pop     rbp
0x18002fe5e  pop     rbx
0x18002fe5f  retn
```
