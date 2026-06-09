# PCLmWriter::PDFContentBuilder::DrawImage(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,PCLmWriter::PDF_MATRIX const &)

- ea: `0x180017c6c`
- end: `0x180017d92`
- name: `?DrawImage@PDFContentBuilder@PCLmWriter@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUPDF_MATRIX@2@@Z`
- size: `294`
- prototype: `__int64 __fastcall(PCLmWriter::PDFContentBuilder *this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000fe14`

## callees

- `0x1800015f0`
- `0x180010618`
- `0x180010718`
- `0x18001138c`
- `0x180011b4c`
- `0x1800176c0`
- `0x180017704`
- `0x180017770`
- `0x180017d98`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PCLmWriter::PDFContentBuilder::DrawImage(
        PCLmWriter::PDFContentBuilder *this,
        __int64 a2,
        const struct PCLmWriter::PDF_MATRIX *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  _BYTE v13[32]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp+17h] BYREF

  v6 = std::operator+<char>(v13, this, "\nq");
  std::string::operator=(this, v6);
  std::string::_Tidy_deallocate(v13);
  PCLmWriter::PDFContentBuilder::SetTransform(this, a3);
  std::operator+<char>(v14, this, "\n");
  v7 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  v9 = std::string::_Append<char>(v8, v7, *(_QWORD *)(a2 + 16));
  std::string::string(v13, v9);
  v10 = std::operator+<char>(v15, v13, " Do");
  std::string::operator=(this, v10);
  std::string::_Tidy_deallocate(v15);
  std::string::_Tidy_deallocate(v13);
  std::string::_Tidy_deallocate(v14);
  v11 = std::operator+<char>(v14, this, " Q");
  std::string::operator=(this, v11);
  std::string::_Tidy_deallocate(v14);
  return std::string::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x180017c6c  mov     [rsp-8+arg_18], rbx
0x180017c71  push    rbp
0x180017c72  push    rsi
0x180017c73  push    rdi
0x180017c74  lea     rbp, [rsp-47h]
0x180017c79  sub     rsp, 0A0h
0x180017c80  mov     rax, cs:__security_cookie
0x180017c87  xor     rax, rsp
0x180017c8a  mov     [rbp+57h+var_20], rax
0x180017c8e  mov     rbx, r8
0x180017c91  mov     rsi, rdx
0x180017c94  mov     rdi, rcx
0x180017c97  mov     [rbp+57h+var_88], rdx
0x180017c9b  lea     r8, aQ; "\nq"
0x180017ca2  mov     rdx, rcx
0x180017ca5  lea     rcx, [rbp+57h+var_80]
0x180017ca9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180017cae  mov     rdx, rax
0x180017cb1  mov     rcx, rdi
0x180017cb4  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180017cb9  lea     rcx, [rbp+57h+var_80]
0x180017cbd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017cc2  mov     rdx, rbx; struct PCLmWriter::PDF_MATRIX *
0x180017cc5  mov     rcx, rdi; this
0x180017cc8  call    ?SetTransform@PDFContentBuilder@PCLmWriter@@QEAAXAEBUPDF_MATRIX@2@@Z; PCLmWriter::PDFContentBuilder::SetTransform(PCLmWriter::PDF_MATRIX const &)
0x180017ccd  lea     r8, asc_1800257D0; "\n"
0x180017cd4  mov     rdx, rdi
0x180017cd7  lea     rcx, [rbp+57h+var_60]
0x180017cdb  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180017ce0  mov     r9, rax
0x180017ce3  mov     rcx, rsi
0x180017ce6  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180017ceb  mov     r8, [rsi+10h]
0x180017cef  mov     rdx, rax
0x180017cf2  mov     rcx, r9
0x180017cf5  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180017cfa  mov     rdx, rax
0x180017cfd  lea     rcx, [rbp+57h+var_80]
0x180017d01  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180017d06  nop
0x180017d07  lea     r8, aDo; " Do"
0x180017d0e  lea     rdx, [rbp+57h+var_80]
0x180017d12  lea     rcx, [rbp+57h+var_40]
0x180017d16  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180017d1b  mov     rdx, rax
0x180017d1e  mov     rcx, rdi
0x180017d21  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180017d26  lea     rcx, [rbp+57h+var_40]
0x180017d2a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017d2f  nop
0x180017d30  lea     rcx, [rbp+57h+var_80]
0x180017d34  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017d39  nop
0x180017d3a  lea     rcx, [rbp+57h+var_60]
0x180017d3e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017d43  lea     r8, aQ_0; " Q"
0x180017d4a  mov     rdx, rdi
0x180017d4d  lea     rcx, [rbp+57h+var_60]
0x180017d51  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180017d56  mov     rdx, rax
0x180017d59  mov     rcx, rdi
0x180017d5c  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180017d61  lea     rcx, [rbp+57h+var_60]
0x180017d65  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017d6a  nop
0x180017d6b  mov     rcx, rsi
0x180017d6e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017d73  mov     rcx, [rbp+57h+var_20]
0x180017d77  xor     rcx, rsp; StackCookie
0x180017d7a  call    __security_check_cookie
0x180017d7f  mov     rbx, [rsp+0B0h+arg_18]
0x180017d87  add     rsp, 0A0h
0x180017d8e  pop     rdi
0x180017d8f  pop     rsi
0x180017d90  pop     rbp
0x180017d91  retn
```
