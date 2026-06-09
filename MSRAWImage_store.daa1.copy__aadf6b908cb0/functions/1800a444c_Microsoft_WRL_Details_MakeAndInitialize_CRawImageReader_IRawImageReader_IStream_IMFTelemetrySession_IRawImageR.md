# Microsoft::WRL::Details::MakeAndInitialize<CRawImageReader,IRawImageReader,IStream * &,IMFTelemetrySession * &>(IRawImageReader * *,IStream * &,IMFTelemetrySession * &)

- ea: `0x1800a444c`
- end: `0x1800a4509`
- name: `??$MakeAndInitialize@VCRawImageReader@@UIRawImageReader@@AEAPEAUIStream@@AEAPEAUIMFTelemetrySession@@@Details@WRL@Microsoft@@YAJPEAPEAUIRawImageReader@@AEAPEAUIStream@@AEAPEAUIMFTelemetrySession@@@Z`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800acc40`

## callees

- `0x180002a24`
- `0x180095b58`
- `0x1800a4080`
- `0x1800a444c`
- `0x1800a4e48`
- `0x1800ad270`
- `0x1800ad600`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CRawImageReader,IRawImageReader,IStream * &,IMFTelemetrySession * &>(
        _QWORD *a1,
        struct IStream **a2,
        struct IMFTelemetrySession **a3)
{
  CRawImageReader *v6; // rax
  int v7; // edi
  CRawImageReader *v8; // rbx
  CRawImageReader *v10; // [rsp+50h] [rbp+8h] BYREF
  CRawImageReader *v11; // [rsp+68h] [rbp+20h]

  *a1 = 0;
  v6 = (CRawImageReader *)operator new(0x418u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v6;
  v11 = v6;
  if ( v6 )
  {
    v8 = CRawImageReader::CRawImageReader(v6);
    v11 = v8;
    v10 = 0;
    v7 = CRawImageReader::RuntimeClassInitialize(v8, *a2, *a3);
    if ( v7 >= 0 )
      v7 = Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>>(
             v8,
             &GUID_eac84b1b_aafe_4ffc_8146_cf4ac9209912,
             a1);
    if ( v8 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::Release(v8);
  }
  else
  {
    v7 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(&v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800a444c  push    rsi
0x1800a444e  push    rdi
0x1800a444f  push    r14
0x1800a4451  sub     rsp, 30h
0x1800a4455  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800a445e  mov     [rsp+48h+arg_8], rbx
0x1800a4463  mov     rdi, r8
0x1800a4466  mov     r14, rdx
0x1800a4469  mov     rsi, rcx
0x1800a446c  mov     qword ptr [rcx], 0
0x1800a4473  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a447a  mov     ecx, 418h; unsigned __int64
0x1800a447f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a4484  mov     [rsp+48h+arg_0], rax
0x1800a4489  mov     [rsp+48h+arg_18], rax
0x1800a448e  test    rax, rax
0x1800a4491  jnz     short loc_1800A449A
0x1800a4493  mov     edi, 8007000Eh
0x1800a4498  jmp     short loc_1800A44EE
0x1800a449a  mov     [rsp+48h+var_20], rax
0x1800a449f  mov     rcx, rax; this
0x1800a44a2  call    ??0CRawImageReader@@QEAA@XZ; CRawImageReader::CRawImageReader(void)
0x1800a44a7  mov     rbx, rax
0x1800a44aa  mov     [rsp+48h+arg_18], rax
0x1800a44af  mov     [rsp+48h+arg_0], 0
0x1800a44b8  mov     r8, [rdi]; struct IMFTelemetrySession *
0x1800a44bb  mov     rdx, [r14]; struct IStream *
0x1800a44be  mov     rcx, rax; this
0x1800a44c1  call    ?RuntimeClassInitialize@CRawImageReader@@QEAAJPEAUIStream@@PEAUIMFTelemetrySession@@@Z; CRawImageReader::RuntimeClassInitialize(IStream *,IMFTelemetrySession *)
0x1800a44c6  mov     edi, eax
0x1800a44c8  test    eax, eax
0x1800a44ca  js      short loc_1800A44E0
0x1800a44cc  mov     r8, rsi
0x1800a44cf  lea     rdx, _GUID_eac84b1b_aafe_4ffc_8146_cf4ac9209912
0x1800a44d6  mov     rcx, rbx
0x1800a44d9  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x1800a44de  mov     edi, eax
0x1800a44e0  test    rbx, rbx
0x1800a44e3  jz      short loc_1800A44EE
0x1800a44e5  mov     rcx, rbx
0x1800a44e8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::Release(void)
0x1800a44ed  nop
0x1800a44ee  lea     rcx, [rsp+48h+arg_0]
0x1800a44f3  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(void)
0x1800a44f8  mov     eax, edi
0x1800a44fa  mov     rbx, [rsp+48h+arg_8]
0x1800a44ff  add     rsp, 30h
0x1800a4503  pop     r14
0x1800a4505  pop     rdi
0x1800a4506  pop     rsi
0x1800a4507  retn
```
