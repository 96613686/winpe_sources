# Microsoft::WRL::Details::MakeAndInitialize<CWICRawMetadataBlockEnumerator,IEnumUnknown,CWICRawMetadataBlockReaderBase *>(IEnumUnknown * *,CWICRawMetadataBlockReaderBase * &&)

- ea: `0x180097808`
- end: `0x180097950`
- name: `??$MakeAndInitialize@VCWICRawMetadataBlockEnumerator@@UIEnumUnknown@@PEAVCWICRawMetadataBlockReaderBase@@@Details@WRL@Microsoft@@YAJPEAPEAUIEnumUnknown@@$$QEAPEAVCWICRawMetadataBlockReaderBase@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18009a410`

## callees

- `0x180002a24`
- `0x180095b58`
- `0x180096010`
- `0x1800970ec`
- `0x180097808`
- `0x1800984b8`
- `0x180098be0`
- `0x18009c44c`
- `0x18009d150`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CWICRawMetadataBlockEnumerator,IEnumUnknown,CWICRawMetadataBlockReaderBase *>(
        void **a1,
        __int64 *a2)
{
  CWICRawMetadataBlockEnumerator *v4; // rax
  unsigned int v5; // edi
  CWICRawMetadataBlockEnumerator *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // r9
  const struct _GUID *v11; // rdx
  int CanCastTo; // eax
  CWICRawMetadataBlockEnumerator *v14; // [rsp+50h] [rbp+8h] BYREF
  CWICRawMetadataBlockEnumerator *v15; // [rsp+60h] [rbp+18h] BYREF
  CWICRawMetadataBlockEnumerator *v16; // [rsp+68h] [rbp+20h]

  *a1 = 0;
  v4 = (CWICRawMetadataBlockEnumerator *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v4;
  v14 = v4;
  if ( v4 )
  {
    v16 = v4;
    v6 = CWICRawMetadataBlockEnumerator::CWICRawMetadataBlockEnumerator(v4);
    v14 = 0;
    Microsoft::WRL::ComPtr<CWICRawMetadataBlockEnumerator>::Attach(&v14, v6);
    v15 = 0;
    v7 = *a2;
    v8 = (__int64)v14;
    if ( *((_QWORD *)v14 + 12) != v7 )
    {
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      v14 = *(CWICRawMetadataBlockEnumerator **)(v8 + 96);
      *(_QWORD *)(v8 + 96) = v7;
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((__int64 *)&v14);
    }
    *(_DWORD *)(v8 + 88) = 0;
    *a1 = 0;
    if ( (unsigned int)InlineIsEqualGUID(
                         &GUID_00000100_0000_0000_c000_000000000046,
                         &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a1 = (void *)v8;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      v5 = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v9, v10) )
      {
        *a1 = (void *)v8;
        v5 = 0;
      }
      else
      {
        CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v8 + 8), v11, a1);
        v5 = -2147467262;
        if ( CanCastTo == -2147467262 )
          goto LABEL_14;
        v5 = CanCastTo;
        if ( CanCastTo < 0 )
          goto LABEL_14;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 8LL))(*a1);
    }
LABEL_14:
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumUnknown,Microsoft::WRL::FtmBase>::Release(v8);
    goto LABEL_15;
  }
  v5 = -2147024882;
LABEL_15:
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(&v15);
  return v5;
}

```

## disassembly

```asm
0x180097808  push    rbx
0x18009780a  push    rsi
0x18009780b  push    rdi
0x18009780c  sub     rsp, 30h
0x180097810  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180097819  mov     rdi, rdx
0x18009781c  mov     rsi, rcx
0x18009781f  mov     qword ptr [rcx], 0
0x180097826  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009782d  mov     ecx, 68h ; 'h'; unsigned __int64
0x180097832  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180097837  mov     [rsp+48h+arg_10], rax
0x18009783c  mov     [rsp+48h+arg_0], rax
0x180097841  test    rax, rax
0x180097844  jnz     short loc_180097850
0x180097846  mov     edi, 8007000Eh
0x18009784b  jmp     loc_18009793B
0x180097850  mov     [rsp+48h+arg_18], rax
0x180097855  mov     rcx, rax; this
0x180097858  call    ??0CWICRawMetadataBlockEnumerator@@QEAA@XZ; CWICRawMetadataBlockEnumerator::CWICRawMetadataBlockEnumerator(void)
0x18009785d  nop
0x18009785e  mov     [rsp+48h+arg_0], 0
0x180097867  mov     rdx, rax
0x18009786a  lea     rcx, [rsp+48h+arg_0]
0x18009786f  call    ?Attach@?$ComPtr@VCWICRawMetadataBlockEnumerator@@@WRL@Microsoft@@QEAAXPEAVCWICRawMetadataBlockEnumerator@@@Z; Microsoft::WRL::ComPtr<CWICRawMetadataBlockEnumerator>::Attach(CWICRawMetadataBlockEnumerator *)
0x180097874  mov     [rsp+48h+arg_10], 0
0x18009787d  mov     rdi, [rdi]
0x180097880  mov     rbx, [rsp+48h+arg_0]
0x180097885  cmp     [rbx+60h], rdi
0x180097889  jz      short loc_1800978B7
0x18009788b  test    rdi, rdi
0x18009788e  jz      short loc_1800978A0
0x180097890  mov     rax, [rdi]
0x180097893  mov     rcx, rdi
0x180097896  mov     rax, [rax+8]
0x18009789a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009789f  nop
0x1800978a0  mov     rax, [rbx+60h]
0x1800978a4  mov     [rsp+48h+arg_0], rax
0x1800978a9  mov     [rbx+60h], rdi
0x1800978ad  lea     rcx, [rsp+48h+arg_0]
0x1800978b2  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800978b7  mov     dword ptr [rbx+58h], 0
0x1800978be  mov     qword ptr [rsi], 0
0x1800978c5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800978cc  lea     r9, _GUID_00000100_0000_0000_c000_000000000046
0x1800978d3  mov     rcx, r9
0x1800978d6  call    InlineIsEqualGUID
0x1800978db  test    eax, eax
0x1800978dd  jnz     short loc_18009791E
0x1800978df  mov     rdx, r9
0x1800978e2  call    InlineIsEqualGUID
0x1800978e7  test    eax, eax
0x1800978e9  jz      short loc_1800978F2
0x1800978eb  mov     [rsi], rbx
0x1800978ee  xor     edi, edi
0x1800978f0  jmp     short loc_18009790D
0x1800978f2  lea     rcx, [rbx+8]; this
0x1800978f6  mov     r8, rsi; void **
0x1800978f9  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x1800978fe  mov     edi, 80004002h
0x180097903  cmp     eax, edi
0x180097905  jz      short loc_180097932
0x180097907  mov     edi, eax
0x180097909  test    eax, eax
0x18009790b  js      short loc_180097932
0x18009790d  mov     rcx, [rsi]
0x180097910  mov     rax, [rcx]
0x180097913  mov     rax, [rax+8]
0x180097917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009791c  jmp     short loc_180097932
0x18009791e  mov     [rsi], rbx
0x180097921  mov     rax, [rbx]
0x180097924  mov     rcx, rbx
0x180097927  mov     rax, [rax+8]
0x18009792b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097930  xor     edi, edi
0x180097932  mov     rcx, rbx
0x180097935  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEnumUnknown@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumUnknown,Microsoft::WRL::FtmBase>::Release(void)
0x18009793a  nop
0x18009793b  lea     rcx, [rsp+48h+arg_10]
0x180097940  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(void)
0x180097945  mov     eax, edi
0x180097947  add     rsp, 30h
0x18009794b  pop     rdi
0x18009794c  pop     rsi
0x18009794d  pop     rbx
0x18009794e  retn
```
