# Microsoft::WRL::Details::MakeAndInitialize<CWICRawMetadataBlockEnumerator,IEnumUnknown,IWICMetadataBlockReader *,ulong &>(IEnumUnknown * *,IWICMetadataBlockReader * &&,ulong &)

- ea: `0x1800976ac`
- end: `0x1800977ff`
- name: `??$MakeAndInitialize@VCWICRawMetadataBlockEnumerator@@UIEnumUnknown@@PEAUIWICMetadataBlockReader@@AEAK@Details@WRL@Microsoft@@YAJPEAPEAUIEnumUnknown@@$$QEAPEAUIWICMetadataBlockReader@@AEAK@Z`
- size: `339`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180098c20`

## callees

- `0x180002a24`
- `0x180095b58`
- `0x180096010`
- `0x1800970ec`
- `0x1800976ac`
- `0x1800984b8`
- `0x180098be0`
- `0x18009c44c`
- `0x18009d150`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CWICRawMetadataBlockEnumerator,IEnumUnknown,IWICMetadataBlockReader *,unsigned long &>(
        void **a1,
        __int64 *a2,
        int *a3)
{
  CWICRawMetadataBlockEnumerator *v6; // rax
  unsigned int v7; // edi
  CWICRawMetadataBlockEnumerator *v8; // rax
  int v9; // ebp
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // r9
  const struct _GUID *v14; // rdx
  int CanCastTo; // eax
  CWICRawMetadataBlockEnumerator *v17; // [rsp+50h] [rbp+8h] BYREF
  CWICRawMetadataBlockEnumerator *v18; // [rsp+68h] [rbp+20h] BYREF

  *a1 = 0;
  v6 = (CWICRawMetadataBlockEnumerator *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v6;
  v17 = v6;
  if ( v6 )
  {
    v8 = CWICRawMetadataBlockEnumerator::CWICRawMetadataBlockEnumerator(v6);
    v17 = 0;
    Microsoft::WRL::ComPtr<CWICRawMetadataBlockEnumerator>::Attach(&v17, v8);
    v18 = 0;
    v9 = *a3;
    v10 = *a2;
    v11 = (__int64)v17;
    if ( *((_QWORD *)v17 + 12) != v10 )
    {
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      v17 = *(CWICRawMetadataBlockEnumerator **)(v11 + 96);
      *(_QWORD *)(v11 + 96) = v10;
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((__int64 *)&v17);
    }
    *(_DWORD *)(v11 + 88) = v9;
    *a1 = 0;
    if ( (unsigned int)InlineIsEqualGUID(
                         &GUID_00000100_0000_0000_c000_000000000046,
                         &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a1 = (void *)v11;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      v7 = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v12, v13) )
      {
        *a1 = (void *)v11;
        v7 = 0;
      }
      else
      {
        CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v11 + 8), v14, a1);
        v7 = -2147467262;
        if ( CanCastTo == -2147467262 )
          goto LABEL_14;
        v7 = CanCastTo;
        if ( CanCastTo < 0 )
          goto LABEL_14;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 8LL))(*a1);
    }
LABEL_14:
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumUnknown,Microsoft::WRL::FtmBase>::Release(v11);
    goto LABEL_15;
  }
  v7 = -2147024882;
LABEL_15:
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(&v18);
  return v7;
}

```

## disassembly

```asm
0x1800976ac  push    rbp
0x1800976ae  push    rsi
0x1800976af  push    rdi
0x1800976b0  sub     rsp, 30h
0x1800976b4  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800976bd  mov     [rsp+48h+arg_8], rbx
0x1800976c2  mov     rbx, r8
0x1800976c5  mov     rdi, rdx
0x1800976c8  mov     rsi, rcx
0x1800976cb  mov     qword ptr [rcx], 0
0x1800976d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800976d9  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800976de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800976e3  mov     [rsp+48h+arg_18], rax
0x1800976e8  mov     [rsp+48h+arg_0], rax
0x1800976ed  test    rax, rax
0x1800976f0  jnz     short loc_1800976FC
0x1800976f2  mov     edi, 8007000Eh
0x1800976f7  jmp     loc_1800977E5
0x1800976fc  mov     [rsp+48h+var_20], rax
0x180097701  mov     rcx, rax; this
0x180097704  call    ??0CWICRawMetadataBlockEnumerator@@QEAA@XZ; CWICRawMetadataBlockEnumerator::CWICRawMetadataBlockEnumerator(void)
0x180097709  nop
0x18009770a  mov     [rsp+48h+arg_0], 0
0x180097713  mov     rdx, rax
0x180097716  lea     rcx, [rsp+48h+arg_0]
0x18009771b  call    ?Attach@?$ComPtr@VCWICRawMetadataBlockEnumerator@@@WRL@Microsoft@@QEAAXPEAVCWICRawMetadataBlockEnumerator@@@Z; Microsoft::WRL::ComPtr<CWICRawMetadataBlockEnumerator>::Attach(CWICRawMetadataBlockEnumerator *)
0x180097720  mov     [rsp+48h+arg_18], 0
0x180097729  mov     ebp, [rbx]
0x18009772b  mov     rdi, [rdi]
0x18009772e  mov     rbx, [rsp+48h+arg_0]
0x180097733  cmp     [rbx+60h], rdi
0x180097737  jz      short loc_180097765
0x180097739  test    rdi, rdi
0x18009773c  jz      short loc_18009774E
0x18009773e  mov     rax, [rdi]
0x180097741  mov     rcx, rdi
0x180097744  mov     rax, [rax+8]
0x180097748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009774d  nop
0x18009774e  mov     rax, [rbx+60h]
0x180097752  mov     [rsp+48h+arg_0], rax
0x180097757  mov     [rbx+60h], rdi
0x18009775b  lea     rcx, [rsp+48h+arg_0]
0x180097760  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x180097765  mov     [rbx+58h], ebp
0x180097768  mov     qword ptr [rsi], 0
0x18009776f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180097776  lea     r9, _GUID_00000100_0000_0000_c000_000000000046
0x18009777d  mov     rcx, r9
0x180097780  call    InlineIsEqualGUID
0x180097785  test    eax, eax
0x180097787  jnz     short loc_1800977C8
0x180097789  mov     rdx, r9
0x18009778c  call    InlineIsEqualGUID
0x180097791  test    eax, eax
0x180097793  jz      short loc_18009779C
0x180097795  mov     [rsi], rbx
0x180097798  xor     edi, edi
0x18009779a  jmp     short loc_1800977B7
0x18009779c  lea     rcx, [rbx+8]; this
0x1800977a0  mov     r8, rsi; void **
0x1800977a3  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x1800977a8  mov     edi, 80004002h
0x1800977ad  cmp     eax, edi
0x1800977af  jz      short loc_1800977DC
0x1800977b1  mov     edi, eax
0x1800977b3  test    eax, eax
0x1800977b5  js      short loc_1800977DC
0x1800977b7  mov     rcx, [rsi]
0x1800977ba  mov     rax, [rcx]
0x1800977bd  mov     rax, [rax+8]
0x1800977c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800977c6  jmp     short loc_1800977DC
0x1800977c8  mov     [rsi], rbx
0x1800977cb  mov     rax, [rbx]
0x1800977ce  mov     rcx, rbx
0x1800977d1  mov     rax, [rax+8]
0x1800977d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800977da  xor     edi, edi
0x1800977dc  mov     rcx, rbx
0x1800977df  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEnumUnknown@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumUnknown,Microsoft::WRL::FtmBase>::Release(void)
0x1800977e4  nop
0x1800977e5  lea     rcx, [rsp+48h+arg_18]
0x1800977ea  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(void)
0x1800977ef  mov     eax, edi
0x1800977f1  mov     rbx, [rsp+48h+arg_8]
0x1800977f6  add     rsp, 30h
0x1800977fa  pop     rdi
0x1800977fb  pop     rsi
0x1800977fc  pop     rbp
0x1800977fd  retn
```
