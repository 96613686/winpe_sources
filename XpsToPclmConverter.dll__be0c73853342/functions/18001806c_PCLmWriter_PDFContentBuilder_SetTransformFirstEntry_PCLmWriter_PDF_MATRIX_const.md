# PCLmWriter::PDFContentBuilder::SetTransformFirstEntry(PCLmWriter::PDF_MATRIX const &)

- ea: `0x18001806c`
- end: `0x18001832b`
- name: `?SetTransformFirstEntry@PDFContentBuilder@PCLmWriter@@QEAAXAEBUPDF_MATRIX@2@@Z`
- size: `703`
- prototype: `void __fastcall(PCLmWriter::PDFContentBuilder *__hidden this, const struct PCLmWriter::PDF_MATRIX *)`
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
- `0x18001769c`
- `0x1800176c0`
- `0x1800177e0`
- `0x18001a61c`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall PCLmWriter::PDFContentBuilder::SetTransformFirstEntry(
        PCLmWriter::PDFContentBuilder *this,
        const struct PCLmWriter::PDF_MATRIX *a2)
{
  __int64 v3; // r12
  __int64 v4; // rdx
  __int64 v5; // r15
  __int64 v6; // rdx
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  _BYTE v27[32]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v28[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v29[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v32[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v33[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v34[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v35[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v36[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v37[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v38[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v39[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v40[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v41[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v42[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v43[32]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v44[32]; // [rsp+248h] [rbp+148h] BYREF

  v3 = PCLmWriter::CharHelper::ToString(v44, a2, 6);
  v5 = PCLmWriter::CharHelper::ToString(v43, v4, 6);
  v7 = PCLmWriter::CharHelper::ToString(v42, v6, 6);
  v9 = PCLmWriter::CharHelper::ToString(v41, v8, 6);
  v11 = PCLmWriter::CharHelper::ToString(v40, v10, 6);
  PCLmWriter::CharHelper::ToString(v39, v12, 6);
  v13 = std::_String_val<std::_Simple_types<char>>::_Myptr(this);
  v15 = std::string::_Insert<char>(v14, v14, v13, *((_QWORD *)this + 2));
  std::string::string(v27, v15);
  v16 = std::operator+<char>(v38, v27, " ");
  v17 = std::operator+<char>(v37, v16, v11);
  v18 = std::operator+<char>(v36, v17, " ");
  v19 = std::operator+<char>(v35, v18, v9);
  v20 = std::operator+<char>(v34, v19, " ");
  v21 = std::operator+<char>(v33, v20, v7);
  v22 = std::operator+<char>(v32, v21, " ");
  v23 = std::operator+<char>(v31, v22, v5);
  v24 = std::operator+<char>(v30, v23, " ");
  v25 = std::operator+<char>(v29, v24, v3);
  v26 = std::operator+<char>(v28, v25, " cm");
  std::string::operator=(this, v26);
  std::string::_Tidy_deallocate(v28);
  std::string::_Tidy_deallocate(v29);
  std::string::_Tidy_deallocate(v30);
  std::string::_Tidy_deallocate(v31);
  std::string::_Tidy_deallocate(v32);
  std::string::_Tidy_deallocate(v33);
  std::string::_Tidy_deallocate(v34);
  std::string::_Tidy_deallocate(v35);
  std::string::_Tidy_deallocate(v36);
  std::string::_Tidy_deallocate(v37);
  std::string::_Tidy_deallocate(v38);
  std::string::_Tidy_deallocate(v27);
  std::string::_Tidy_deallocate(v39);
  std::string::_Tidy_deallocate(v40);
  std::string::_Tidy_deallocate(v41);
  std::string::_Tidy_deallocate(v42);
  std::string::_Tidy_deallocate(v43);
  std::string::_Tidy_deallocate(v44);
}

```

## disassembly

```asm
0x18001806c  mov     [rsp-8+arg_10], rbx
0x180018071  push    rbp
0x180018072  push    rsi
0x180018073  push    rdi
0x180018074  push    r12
0x180018076  push    r13
0x180018078  push    r14
0x18001807a  push    r15
0x18001807c  lea     rbp, [rsp-170h]
0x180018084  sub     rsp, 270h
0x18001808b  mov     rax, cs:__security_cookie
0x180018092  xor     rax, rsp
0x180018095  mov     [rbp+1A0h+var_38], rax
0x18001809c  mov     rsi, rdx
0x18001809f  mov     r13, rcx
0x1800180a2  movss   xmm1, dword ptr [rdx+14h]
0x1800180a7  cvtps2pd xmm1, xmm1
0x1800180aa  mov     ebx, 6
0x1800180af  mov     r8d, ebx
0x1800180b2  lea     rcx, [rbp+1A0h+var_58]
0x1800180b9  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x1800180be  mov     r12, rax
0x1800180c1  movss   xmm1, dword ptr [rsi+10h]
0x1800180c6  cvtps2pd xmm1, xmm1
0x1800180c9  mov     r8d, ebx
0x1800180cc  lea     rcx, [rbp+1A0h+var_78]
0x1800180d3  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x1800180d8  mov     r15, rax
0x1800180db  movss   xmm1, dword ptr [rsi+0Ch]
0x1800180e0  cvtps2pd xmm1, xmm1
0x1800180e3  mov     r8d, ebx
0x1800180e6  lea     rcx, [rbp+1A0h+var_98]
0x1800180ed  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x1800180f2  mov     r14, rax
0x1800180f5  movss   xmm1, dword ptr [rsi+8]
0x1800180fa  cvtps2pd xmm1, xmm1
0x1800180fd  mov     r8d, ebx
0x180018100  lea     rcx, [rbp+1A0h+var_B8]
0x180018107  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x18001810c  mov     rdi, rax
0x18001810f  movss   xmm1, dword ptr [rsi+4]
0x180018114  cvtps2pd xmm1, xmm1
0x180018117  mov     r8d, ebx
0x18001811a  lea     rcx, [rbp+1A0h+var_D8]
0x180018121  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180018126  mov     rbx, rax
0x180018129  movss   xmm1, dword ptr [rsi]
0x18001812d  cvtps2pd xmm1, xmm1
0x180018130  mov     r8d, 6
0x180018136  lea     rcx, [rbp+1A0h+var_F8]
0x18001813d  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180018142  mov     rdx, rax
0x180018145  mov     rcx, r13
0x180018148  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001814d  mov     r9, [r13+10h]
0x180018151  mov     r8, rax
0x180018154  mov     rcx, rdx
0x180018157  call    ??$_Insert@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KQEBD0@Z; std::string::_Insert<char>(unsigned __int64,char const * const,unsigned __int64)
0x18001815c  mov     rdx, rax
0x18001815f  lea     rcx, [rsp+2A0h+var_278]
0x180018164  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180018169  nop
0x18001816a  lea     rsi, asc_1800257D8; " "
0x180018171  mov     r8, rsi
0x180018174  lea     rdx, [rsp+2A0h+var_278]
0x180018179  lea     rcx, [rbp+1A0h+var_118]
0x180018180  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180018185  nop
0x180018186  mov     r8, rbx
0x180018189  mov     rdx, rax
0x18001818c  lea     rcx, [rbp+1A0h+var_138]
0x180018190  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180018195  nop
0x180018196  mov     r8, rsi
0x180018199  mov     rdx, rax
0x18001819c  lea     rcx, [rbp+1A0h+var_158]
0x1800181a0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800181a5  nop
0x1800181a6  mov     r8, rdi
0x1800181a9  mov     rdx, rax
0x1800181ac  lea     rcx, [rbp+1A0h+var_178]
0x1800181b0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1800181b5  nop
0x1800181b6  mov     r8, rsi
0x1800181b9  mov     rdx, rax
0x1800181bc  lea     rcx, [rbp+1A0h+var_198]
0x1800181c0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800181c5  nop
0x1800181c6  mov     r8, r14
0x1800181c9  mov     rdx, rax
0x1800181cc  lea     rcx, [rbp+1A0h+var_1B8]
0x1800181d0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1800181d5  nop
0x1800181d6  mov     r8, rsi
0x1800181d9  mov     rdx, rax
0x1800181dc  lea     rcx, [rbp+1A0h+var_1D8]
0x1800181e0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800181e5  nop
0x1800181e6  mov     r8, r15
0x1800181e9  mov     rdx, rax
0x1800181ec  lea     rcx, [rbp+1A0h+var_1F8]
0x1800181f0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1800181f5  nop
0x1800181f6  mov     r8, rsi
0x1800181f9  mov     rdx, rax
0x1800181fc  lea     rcx, [rbp+1A0h+var_218]
0x180018200  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180018205  nop
0x180018206  mov     r8, r12
0x180018209  mov     rdx, rax
0x18001820c  lea     rcx, [rsp+2A0h+var_238]
0x180018211  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180018216  nop
0x180018217  lea     r8, aCm; " cm"
0x18001821e  mov     rdx, rax
0x180018221  lea     rcx, [rsp+2A0h+var_258]
0x180018226  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18001822b  mov     rdx, rax
0x18001822e  mov     rcx, r13
0x180018231  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180018236  lea     rcx, [rsp+2A0h+var_258]
0x18001823b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018240  nop
0x180018241  lea     rcx, [rsp+2A0h+var_238]
0x180018246  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001824b  nop
0x18001824c  lea     rcx, [rbp+1A0h+var_218]
0x180018250  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018255  nop
0x180018256  lea     rcx, [rbp+1A0h+var_1F8]
0x18001825a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001825f  nop
0x180018260  lea     rcx, [rbp+1A0h+var_1D8]
0x180018264  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018269  nop
0x18001826a  lea     rcx, [rbp+1A0h+var_1B8]
0x18001826e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018273  nop
0x180018274  lea     rcx, [rbp+1A0h+var_198]
0x180018278  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001827d  nop
0x18001827e  lea     rcx, [rbp+1A0h+var_178]
0x180018282  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018287  nop
0x180018288  lea     rcx, [rbp+1A0h+var_158]
0x18001828c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018291  nop
0x180018292  lea     rcx, [rbp+1A0h+var_138]
0x180018296  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001829b  nop
0x18001829c  lea     rcx, [rbp+1A0h+var_118]
0x1800182a3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800182a8  nop
0x1800182a9  lea     rcx, [rsp+2A0h+var_278]
0x1800182ae  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800182b3  nop
0x1800182b4  lea     rcx, [rbp+1A0h+var_F8]
0x1800182bb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800182c0  nop
0x1800182c1  lea     rcx, [rbp+1A0h+var_D8]
0x1800182c8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800182cd  nop
0x1800182ce  lea     rcx, [rbp+1A0h+var_B8]
0x1800182d5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800182da  nop
0x1800182db  lea     rcx, [rbp+1A0h+var_98]
0x1800182e2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800182e7  nop
0x1800182e8  lea     rcx, [rbp+1A0h+var_78]
0x1800182ef  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800182f4  nop
0x1800182f5  lea     rcx, [rbp+1A0h+var_58]
0x1800182fc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018301  mov     rcx, [rbp+1A0h+var_38]
0x180018308  xor     rcx, rsp; StackCookie
0x18001830b  call    __security_check_cookie
0x180018310  mov     rbx, [rsp+2A0h+arg_10]
0x180018318  add     rsp, 270h
0x18001831f  pop     r15
0x180018321  pop     r14
0x180018323  pop     r13
0x180018325  pop     r12
0x180018327  pop     rdi
0x180018328  pop     rsi
0x180018329  pop     rbp
0x18001832a  retn
```
