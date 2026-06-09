# Microsoft::WRL::Details::MakeAndInitialize<CWICRAWDecoderFrame,CWICRAWDecoderFrame,CRAWWICDecoder *,IMFTelemetrySession *,IWICComponentFactory *>(CWICRAWDecoderFrame * *,CRAWWICDecoder * &&,IMFTelemetrySession * &&,IWICComponentFactory * &&)

- ea: `0x1800975d0`
- end: `0x1800976a3`
- name: `??$MakeAndInitialize@VCWICRAWDecoderFrame@@V1@PEAVCRAWWICDecoder@@PEAUIMFTelemetrySession@@PEAUIWICComponentFactory@@@Details@WRL@Microsoft@@YAJPEAPEAVCWICRAWDecoderFrame@@$$QEAPEAVCRAWWICDecoder@@$$QEAPEAUIMFTelemetrySession@@$$QEAPEAUIWICComponentFactory@@@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18009a900`

## callees

- `0x180002a24`
- `0x180095b58`
- `0x1800975d0`
- `0x180098404`
- `0x18009c44c`
- `0x1800a25b8`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CWICRAWDecoderFrame,CWICRAWDecoderFrame,CRAWWICDecoder *,IMFTelemetrySession *,IWICComponentFactory *>(
        CWICRAWDecoderFrame **a1,
        struct CRAWWICDecoder **a2,
        struct IMFTelemetrySession **a3,
        struct IWICComponentFactory **a4)
{
  CWICRAWDecoderFrame *v8; // rax
  int v9; // edi
  CWICRAWDecoderFrame *v10; // rbx
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF
  CWICRAWDecoderFrame *v13; // [rsp+50h] [rbp+8h] BYREF

  v12[1] = -2;
  *a1 = 0;
  v8 = (CWICRAWDecoderFrame *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v12[0] = v8;
  if ( v8 )
  {
    v10 = CWICRAWDecoderFrame::CWICRAWDecoderFrame(v8);
    v13 = v10;
    v12[0] = 0;
    v9 = CWICRAWDecoderFrame::RuntimeClassInitialize(v10, *a2, *a3, *a4);
    if ( v9 >= 0 )
    {
      if ( v10 )
        (*(void (__fastcall **)(CWICRAWDecoderFrame *))(*(_QWORD *)v10 + 8LL))(v10);
      *a1 = v10;
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((__int64 *)&v13);
      v9 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((__int64 *)&v13);
    }
  }
  else
  {
    v9 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800975d0  push    rdi
0x1800975d2  push    r14
0x1800975d4  push    r15
0x1800975d6  sub     rsp, 30h
0x1800975da  mov     [rsp+48h+var_20], 0FFFFFFFFFFFFFFFEh
0x1800975e3  mov     [rsp+48h+arg_8], rbx
0x1800975e8  mov     [rsp+48h+arg_10], rsi
0x1800975ed  mov     rdi, r9
0x1800975f0  mov     r14, r8
0x1800975f3  mov     r15, rdx
0x1800975f6  mov     rsi, rcx
0x1800975f9  mov     qword ptr [rcx], 0
0x180097600  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180097607  mov     ecx, 0B0h; unsigned __int64
0x18009760c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180097611  mov     [rsp+48h+var_28], rax
0x180097616  test    rax, rax
0x180097619  jnz     short loc_180097622
0x18009761b  mov     edi, 8007000Eh
0x180097620  jmp     short loc_180097682
0x180097622  mov     rcx, rax; this
0x180097625  call    ??0CWICRAWDecoderFrame@@QEAA@XZ; CWICRAWDecoderFrame::CWICRAWDecoderFrame(void)
0x18009762a  mov     rbx, rax
0x18009762d  mov     [rsp+48h+arg_0], rax
0x180097632  mov     [rsp+48h+var_28], 0
0x18009763b  mov     r9, [rdi]; struct IWICComponentFactory *
0x18009763e  mov     r8, [r14]; struct IMFTelemetrySession *
0x180097641  mov     rdx, [r15]; struct CRAWWICDecoder *
0x180097644  mov     rcx, rax; this
0x180097647  call    ?RuntimeClassInitialize@CWICRAWDecoderFrame@@QEAAJPEAVCRAWWICDecoder@@PEAUIMFTelemetrySession@@PEAUIWICComponentFactory@@@Z; CWICRAWDecoderFrame::RuntimeClassInitialize(CRAWWICDecoder *,IMFTelemetrySession *,IWICComponentFactory *)
0x18009764c  mov     edi, eax
0x18009764e  test    eax, eax
0x180097650  jns     short loc_18009765E
0x180097652  lea     rcx, [rsp+48h+arg_0]
0x180097657  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x18009765c  jmp     short loc_180097682
0x18009765e  test    rbx, rbx
0x180097661  jz      short loc_180097673
0x180097663  mov     rax, [rbx]
0x180097666  mov     rcx, rbx
0x180097669  mov     rax, [rax+8]
0x18009766d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097672  nop
0x180097673  mov     [rsi], rbx
0x180097676  lea     rcx, [rsp+48h+arg_0]
0x18009767b  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x180097680  xor     edi, edi
0x180097682  lea     rcx, [rsp+48h+var_28]
0x180097687  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(void)
0x18009768c  mov     eax, edi
0x18009768e  mov     rbx, [rsp+48h+arg_8]
0x180097693  mov     rsi, [rsp+48h+arg_10]
0x180097698  add     rsp, 30h
0x18009769c  pop     r15
0x18009769e  pop     r14
0x1800976a0  pop     rdi
0x1800976a1  retn
```
