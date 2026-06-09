# std::vector<PCLmWriter::PDFImageData,std::allocator<PCLmWriter::PDFImageData>>::_Emplace_reallocate<PCLmWriter::PDFImageData const &>(PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData const &)

- ea: `0x180016a6c`
- end: `0x180016bc9`
- name: `??$_Emplace_reallocate@AEBUPDFImageData@PCLmWriter@@@?$vector@UPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@AEAAPEAUPDFImageData@PCLmWriter@@QEAU23@AEBU23@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180017418`

## callees

- `0x18000ea34`
- `0x18001068c`
- `0x180010770`
- `0x180016a6c`
- `0x180016bd0`
- `0x180016c14`
- `0x180016d64`
- `0x180017620`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::vector<PCLmWriter::PDFImageData>::_Emplace_reallocate<PCLmWriter::PDFImageData const &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r15
  unsigned __int64 v7; // rax
  __int64 v8; // rbx
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  __int64 v13; // rsi
  unsigned __int64 v14; // rdx
  __int64 v15; // r15
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  _QWORD v20[2]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v21; // [rsp+30h] [rbp-68h]
  __int64 v22; // [rsp+38h] [rbp-60h]
  __int64 v23; // [rsp+40h] [rbp-58h]

  v6 = *a1;
  v7 = 0x8E38E38E38E38E39uLL * ((a1[1] - *a1) >> 3);
  v8 = 0x38E38E38E38E38ELL;
  if ( v7 == 0x38E38E38E38E38ELL )
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Xlength();
  v9 = v7 + 1;
  v10 = 0x8E38E38E38E38E39uLL * ((a1[2] - v6) >> 3);
  if ( v10 <= 0x38E38E38E38E38ELL - (v10 >> 1) )
  {
    v11 = (v10 >> 1) + v10;
    v12 = v9;
    if ( v11 >= v9 )
      v12 = v11;
    if ( v12 > 0x38E38E38E38E38ELL )
      std::_Throw_bad_array_new_length();
    v8 = v12;
  }
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(72 * v8);
  v14 = (__int64)((unsigned __int128)((a2 - v6) * (__int128)0xE38E38E38E38E39LL) >> 64) >> 2;
  v15 = v13 + 72 * ((a2 - v6) / 72);
  v20[0] = a1;
  v20[1] = v13;
  v21 = v8;
  v23 = v15 + 72;
  std::_Default_allocator_traits<std::allocator<PCLmWriter::PDFImageData>>::construct<PCLmWriter::PDFImageData,PCLmWriter::PDFImageData const &>(
    9 * ((v14 >> 63) + v14),
    v13 + 72 * ((v14 >> 63) + v14),
    a3);
  v22 = v15;
  v16 = a1[1];
  v17 = v13;
  v18 = *a1;
  if ( a2 != v16 )
  {
    std::_Uninitialized_move<PCLmWriter::PDFImageData *>(v18, a2, v13);
    v22 = v13;
    v17 = v15 + 72;
    v16 = a1[1];
    v18 = a2;
  }
  std::_Uninitialized_move<PCLmWriter::PDFImageData *>(v18, v16, v17);
  std::vector<PCLmWriter::PDFImageData>::_Change_array(a1, v13, v9, v8, v20[0], 0, v21, v22, v23);
  std::vector<PCLmWriter::PDFImageData>::_Reallocation_guard::~_Reallocation_guard(v20);
  return v15;
}

```

## disassembly

```asm
0x180016a6c  push    rbx
0x180016a6e  push    rbp
0x180016a6f  push    rsi
0x180016a70  push    rdi
0x180016a71  push    r12
0x180016a73  push    r13
0x180016a75  push    r14
0x180016a77  push    r15
0x180016a79  sub     rsp, 58h
0x180016a7d  mov     r13, r8
0x180016a80  mov     r14, rdx
0x180016a83  mov     rdi, rcx
0x180016a86  mov     r15, [rcx]
0x180016a89  mov     rax, [rcx+8]
0x180016a8d  sub     rax, r15
0x180016a90  sar     rax, 3
0x180016a94  mov     rdx, 8E38E38E38E38E39h
0x180016a9e  imul    rax, rdx
0x180016aa2  mov     rbx, 38E38E38E38E38Eh
0x180016aac  cmp     rax, rbx
0x180016aaf  jz      loc_180016BC3
0x180016ab5  lea     rbp, [rax+1]
0x180016ab9  mov     rcx, [rcx+10h]
0x180016abd  sub     rcx, r15
0x180016ac0  sar     rcx, 3
0x180016ac4  imul    rcx, rdx
0x180016ac8  mov     rdx, rcx
0x180016acb  shr     rdx, 1
0x180016ace  mov     rax, rbx
0x180016ad1  sub     rax, rdx
0x180016ad4  cmp     rcx, rax
0x180016ad7  ja      short loc_180016AF3
0x180016ad9  lea     rax, [rdx+rcx]
0x180016add  mov     rcx, rbp
0x180016ae0  cmp     rax, rbp
0x180016ae3  cmovnb  rcx, rax
0x180016ae7  cmp     rcx, rbx
0x180016aea  ja      loc_180016BBD
0x180016af0  mov     rbx, rcx
0x180016af3  lea     rcx, [rbx+rbx*8]
0x180016af7  shl     rcx, 3
0x180016afb  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180016b00  mov     rsi, rax
0x180016b03  mov     rcx, r14
0x180016b06  sub     rcx, r15
0x180016b09  mov     rax, 0E38E38E38E38E39h
0x180016b13  imul    rcx
0x180016b16  sar     rdx, 2
0x180016b1a  mov     rcx, rdx
0x180016b1d  shr     rcx, 3Fh
0x180016b21  add     rdx, rcx
0x180016b24  lea     rcx, [rdx+rdx*8]
0x180016b28  lea     r15, [rsi+rcx*8]
0x180016b2c  lea     r12, [r15+48h]
0x180016b30  mov     [rsp+98h+var_78], rdi
0x180016b35  mov     [rsp+98h+var_70], rsi
0x180016b3a  mov     [rsp+98h+var_68], rbx
0x180016b3f  mov     [rsp+98h+var_60], r12
0x180016b44  mov     [rsp+98h+var_58], r12
0x180016b49  mov     r8, r13
0x180016b4c  mov     rdx, r15
0x180016b4f  call    ??$construct@UPDFImageData@PCLmWriter@@AEBU12@@?$_Default_allocator_traits@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@SAXAEAV?$allocator@UPDFImageData@PCLmWriter@@@1@QEAUPDFImageData@PCLmWriter@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<PCLmWriter::PDFImageData>>::construct<PCLmWriter::PDFImageData,PCLmWriter::PDFImageData const &>(std::allocator<PCLmWriter::PDFImageData> &,PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData const &)
0x180016b54  mov     [rsp+98h+var_60], r15
0x180016b59  mov     rdx, [rdi+8]
0x180016b5d  mov     r8, rsi
0x180016b60  mov     rcx, [rdi]
0x180016b63  cmp     r14, rdx
0x180016b66  jz      short loc_180016B7F
0x180016b68  mov     rdx, r14
0x180016b6b  call    ??$_Uninitialized_move@PEAUPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAPEAUPDFImageData@PCLmWriter@@QEAU12@0PEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z; std::_Uninitialized_move<PCLmWriter::PDFImageData *>(PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData *,std::allocator<PCLmWriter::PDFImageData> &)
0x180016b70  mov     [rsp+98h+var_60], rsi
0x180016b75  mov     r8, r12
0x180016b78  mov     rdx, [rdi+8]
0x180016b7c  mov     rcx, r14
0x180016b7f  call    ??$_Uninitialized_move@PEAUPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@YAPEAUPDFImageData@PCLmWriter@@QEAU12@0PEAU12@AEAV?$allocator@UPDFImageData@PCLmWriter@@@0@@Z; std::_Uninitialized_move<PCLmWriter::PDFImageData *>(PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData *,std::allocator<PCLmWriter::PDFImageData> &)
0x180016b84  mov     [rsp+98h+var_70], 0
0x180016b8d  mov     r9, rbx
0x180016b90  mov     r8, rbp
0x180016b93  mov     rdx, rsi
0x180016b96  mov     rcx, rdi
0x180016b99  call    ?_Change_array@?$vector@UPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@AEAAXQEAUPDFImageData@PCLmWriter@@_K1@Z; std::vector<PCLmWriter::PDFImageData>::_Change_array(PCLmWriter::PDFImageData * const,unsigned __int64,unsigned __int64)
0x180016b9e  nop
0x180016b9f  lea     rcx, [rsp+98h+var_78]
0x180016ba4  call    ??1_Reallocation_guard@?$vector@UPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@QEAA@XZ; std::vector<PCLmWriter::PDFImageData>::_Reallocation_guard::~_Reallocation_guard(void)
0x180016ba9  mov     rax, r15
0x180016bac  add     rsp, 58h
0x180016bb0  pop     r15
0x180016bb2  pop     r14
0x180016bb4  pop     r13
0x180016bb6  pop     r12
0x180016bb8  pop     rdi
0x180016bb9  pop     rsi
0x180016bba  pop     rbp
0x180016bbb  pop     rbx
0x180016bbc  retn
0x180016bbd  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180016bc3  call    ?_Xlength@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Xlength(void)
```
