# PCLmWriter::PDFDocumentWriter::WritePDFObjects(std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>> const &)

- ea: `0x1800159d0`
- end: `0x180015b63`
- name: `?WritePDFObjects@PDFDocumentWriter@PCLmWriter@@QEAAXAEBV?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@@Z`
- size: `403`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180010290`
- `0x180014a14`
- `0x1800152f4`

## callees

- `0x1800015f0`
- `0x18000e7c8`
- `0x1800101cc`
- `0x180013780`
- `0x180014538`
- `0x1800159d0`
- `0x1800168d0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall PCLmWriter::PDFDocumentWriter::WritePDFObjects(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 v4; // rbp
  unsigned __int64 result; // rax
  _QWORD *v6; // r13
  __int64 v7; // rsi
  void (__fastcall *v8)(__int64, _BYTE *, _QWORD, _QWORD); // rdi
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  void (__fastcall *v14)(__int64, _QWORD *); // r8
  __int64 v15; // r9
  int v16; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-90h] BYREF
  std::_Ref_count_base *v18; // [rsp+40h] [rbp-88h]
  __int64 v19; // [rsp+48h] [rbp-80h] BYREF
  __int128 v20; // [rsp+58h] [rbp-70h]
  _BYTE v21[16]; // [rsp+68h] [rbp-60h] BYREF
  __int64 v22; // [rsp+78h] [rbp-50h] BYREF

  v20 = 0;
  v4 = 0;
  result = (__int64)(a2[1] - *a2) >> 4;
  if ( result )
  {
    v6 = a1 + 2;
    do
    {
      v7 = *a1;
      v8 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)*a1 + 96LL);
      v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6) + 1;
      v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(16 * v4 + *a2) + 24LL))(*(_QWORD *)(16 * v4 + *a2));
      v8(v7, v17, v10, v9);
      v11 = a1[7];
      v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(16 * v4 + *a2) + 16LL))(*(_QWORD *)(16 * v4 + *a2));
      v12 = (_QWORD *)std::map<unsigned int,std::shared_ptr<PCLmWriter::IXrefEntry>>::_Try_emplace<unsigned int,>(
                        v11,
                        v21,
                        &v16);
      std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(*v12 + 40LL, v17);
      PCLmWriter::PDFDocumentWriter::_WriteObjectStartTag((__int64)a1, (_QWORD *)(16 * v4 + *a2));
      v13 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v19, v6);
      v14(v15, v13);
      v22 = 0x6A626F646E650ALL;
      (*(void (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v6 + 24LL))(*v6, &v22, 7);
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
      ++v4;
      result = (__int64)(a2[1] - *a2) >> 4;
    }
    while ( v4 < result );
  }
  return result;
}

```

## disassembly

```asm
0x1800159d0  mov     [rsp+arg_10], rbx
0x1800159d5  push    rbp
0x1800159d6  push    rsi
0x1800159d7  push    rdi
0x1800159d8  push    r12
0x1800159da  push    r13
0x1800159dc  push    r14
0x1800159de  push    r15
0x1800159e0  sub     rsp, 90h
0x1800159e7  mov     rax, cs:__security_cookie
0x1800159ee  xor     rax, rsp
0x1800159f1  mov     [rsp+0C8h+var_48], rax
0x1800159f9  mov     r15, rdx
0x1800159fc  mov     r12, rcx
0x1800159ff  xorps   xmm0, xmm0
0x180015a02  movdqu  [rsp+0C8h+var_70], xmm0
0x180015a08  xor     ebp, ebp
0x180015a0a  mov     rax, [rdx+8]
0x180015a0e  sub     rax, [rdx]
0x180015a11  sar     rax, 4
0x180015a15  test    rax, rax
0x180015a18  jz      loc_180015B38
0x180015a1e  lea     r13, [rcx+10h]
0x180015a22  mov     rsi, [r12]
0x180015a26  mov     rax, [rsi]
0x180015a29  mov     rdi, [rax+60h]
0x180015a2d  mov     rcx, [r13+0]
0x180015a31  mov     rax, [rcx]
0x180015a34  mov     rax, [rax+10h]
0x180015a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a3d  lea     ebx, [rax+1]
0x180015a40  mov     r14, rbp
0x180015a43  shl     r14, 4
0x180015a47  mov     rdx, [r15]
0x180015a4a  mov     rcx, [r14+rdx]
0x180015a4e  mov     rdx, [rcx]
0x180015a51  mov     rax, [rdx+18h]
0x180015a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a5a  mov     r9d, ebx
0x180015a5d  mov     r8d, eax
0x180015a60  lea     rdx, [rsp+0C8h+var_90]
0x180015a65  mov     rcx, rsi
0x180015a68  mov     rax, rdi
0x180015a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a70  nop
0x180015a71  mov     rbx, [r12+38h]
0x180015a76  mov     rax, [r15]
0x180015a79  mov     rcx, [r14+rax]
0x180015a7d  mov     rax, [rcx]
0x180015a80  mov     rax, [rax+10h]
0x180015a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a89  mov     [rsp+0C8h+var_98], eax
0x180015a8d  lea     r8, [rsp+0C8h+var_98]
0x180015a92  lea     rdx, [rsp+0C8h+var_60]
0x180015a97  mov     rcx, rbx
0x180015a9a  call    ??$_Try_emplace@I$$V@?$map@IV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@_N@1@$$QEAI@Z; std::map<uint,std::shared_ptr<PCLmWriter::IXrefEntry>>::_Try_emplace<uint,>(uint &&)
0x180015a9f  mov     rcx, [rax]
0x180015aa2  add     rcx, 28h ; '('
0x180015aa6  lea     rdx, [rsp+0C8h+var_90]
0x180015aab  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180015ab0  mov     rdx, [r15]
0x180015ab3  add     rdx, r14
0x180015ab6  mov     rcx, r12
0x180015ab9  call    ?_WriteObjectStartTag@PDFDocumentWriter@PCLmWriter@@AEAAXAEBV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@Z; PCLmWriter::PDFDocumentWriter::_WriteObjectStartTag(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180015abe  mov     rax, [r15]
0x180015ac1  mov     r9, [r14+rax]
0x180015ac5  mov     rax, [r9]
0x180015ac8  mov     r8, [rax+20h]
0x180015acc  mov     rdx, r13
0x180015acf  lea     rcx, [rsp+0C8h+var_80]
0x180015ad4  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180015ad9  mov     rdx, rax
0x180015adc  mov     rcx, r9
0x180015adf  mov     rax, r8
0x180015ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ae7  mov     rax, 6A626F646E650Ah
0x180015af1  mov     [rsp+0C8h+var_50], rax
0x180015af6  mov     rcx, [r13+0]
0x180015afa  mov     rax, [rcx]
0x180015afd  mov     r8d, 7
0x180015b03  lea     rdx, [rsp+0C8h+var_50]
0x180015b08  mov     rax, [rax+18h]
0x180015b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b11  nop
0x180015b12  mov     rcx, [rsp+0C8h+var_88]; this
0x180015b17  test    rcx, rcx
0x180015b1a  jz      short loc_180015B21
0x180015b1c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015b21  inc     rbp
0x180015b24  mov     rax, [r15+8]
0x180015b28  sub     rax, [r15]
0x180015b2b  sar     rax, 4
0x180015b2f  cmp     rbp, rax
0x180015b32  jb      loc_180015A22
0x180015b38  mov     rcx, [rsp+0C8h+var_48]
0x180015b40  xor     rcx, rsp; StackCookie
0x180015b43  call    __security_check_cookie
0x180015b48  mov     rbx, [rsp+0C8h+arg_10]
0x180015b50  add     rsp, 90h
0x180015b57  pop     r15
0x180015b59  pop     r14
0x180015b5b  pop     r13
0x180015b5d  pop     r12
0x180015b5f  pop     rdi
0x180015b60  pop     rsi
0x180015b61  pop     rbp
0x180015b62  retn
```
