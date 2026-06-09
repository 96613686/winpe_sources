# PCLmWriter::PDFContentBuilder::SetTransform(PCLmWriter::PDF_MATRIX const &)

- ea: `0x180017d98`
- end: `0x180018065`
- name: `?SetTransform@PDFContentBuilder@PCLmWriter@@QEAAXAEBUPDF_MATRIX@2@@Z`
- size: `717`
- prototype: `void __fastcall(PCLmWriter::PDFContentBuilder *__hidden this, const struct PCLmWriter::PDF_MATRIX *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180017c6c`

## callees

- `0x1800015f0`
- `0x180010718`
- `0x180011b4c`
- `0x18001769c`
- `0x1800176c0`
- `0x180017704`
- `0x18001a61c`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall PCLmWriter::PDFContentBuilder::SetTransform(
        PCLmWriter::PDFContentBuilder *this,
        const struct PCLmWriter::PDF_MATRIX *a2)
{
  __int64 v3; // r12
  __int64 v4; // rdx
  __int64 v5; // r15
  __int64 v6; // rdx
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rax
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
  _BYTE v27[32]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v28[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v29[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v30[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v33[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v34[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v35[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v36[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v37[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v38[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v39[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v40[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v41[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v42[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v43[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v44[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v45[32]; // [rsp+260h] [rbp+160h] BYREF

  v3 = PCLmWriter::CharHelper::ToString(v45, a2, 6);
  v5 = PCLmWriter::CharHelper::ToString(v44, v4, 6);
  v7 = PCLmWriter::CharHelper::ToString(v43, v6, 6);
  v9 = PCLmWriter::CharHelper::ToString(v42, v8, 6);
  v11 = PCLmWriter::CharHelper::ToString(v41, v10, 6);
  v13 = PCLmWriter::CharHelper::ToString(v40, v12, 6);
  v14 = std::operator+<char>(v39, this, "\n");
  v15 = std::operator+<char>(v38, v14, v13);
  v16 = std::operator+<char>(v37, v15, " ");
  v17 = std::operator+<char>(v36, v16, v11);
  v18 = std::operator+<char>(v35, v17, " ");
  v19 = std::operator+<char>(v34, v18, v9);
  v20 = std::operator+<char>(v33, v19, " ");
  v21 = std::operator+<char>(v32, v20, v7);
  v22 = std::operator+<char>(v31, v21, " ");
  v23 = std::operator+<char>(v30, v22, v5);
  v24 = std::operator+<char>(v29, v23, " ");
  v25 = std::operator+<char>(v28, v24, v3);
  v26 = std::operator+<char>(v27, v25, " cm");
  std::string::operator=(this, v26);
  std::string::_Tidy_deallocate(v27);
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
  std::string::_Tidy_deallocate(v39);
  std::string::_Tidy_deallocate(v40);
  std::string::_Tidy_deallocate(v41);
  std::string::_Tidy_deallocate(v42);
  std::string::_Tidy_deallocate(v43);
  std::string::_Tidy_deallocate(v44);
  std::string::_Tidy_deallocate(v45);
}

```

## disassembly

```asm
0x180017d98  mov     [rsp-8+arg_10], rbx
0x180017d9d  push    rbp
0x180017d9e  push    rsi
0x180017d9f  push    rdi
0x180017da0  push    r12
0x180017da2  push    r13
0x180017da4  push    r14
0x180017da6  push    r15
0x180017da8  lea     rbp, [rsp-190h]
0x180017db0  sub     rsp, 290h
0x180017db7  mov     rax, cs:__security_cookie
0x180017dbe  xor     rax, rsp
0x180017dc1  mov     [rbp+1C0h+var_40], rax
0x180017dc8  mov     rbx, rdx
0x180017dcb  mov     r13, rcx
0x180017dce  movss   xmm1, dword ptr [rdx+14h]
0x180017dd3  cvtps2pd xmm1, xmm1
0x180017dd6  mov     edi, 6
0x180017ddb  mov     r8d, edi
0x180017dde  lea     rcx, [rbp+1C0h+var_60]
0x180017de5  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180017dea  mov     r12, rax
0x180017ded  movss   xmm1, dword ptr [rbx+10h]
0x180017df2  cvtps2pd xmm1, xmm1
0x180017df5  mov     r8d, edi
0x180017df8  lea     rcx, [rbp+1C0h+var_80]
0x180017dff  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180017e04  mov     r15, rax
0x180017e07  movss   xmm1, dword ptr [rbx+0Ch]
0x180017e0c  cvtps2pd xmm1, xmm1
0x180017e0f  mov     r8d, edi
0x180017e12  lea     rcx, [rbp+1C0h+var_A0]
0x180017e19  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180017e1e  mov     r14, rax
0x180017e21  movss   xmm1, dword ptr [rbx+8]
0x180017e26  cvtps2pd xmm1, xmm1
0x180017e29  mov     r8d, edi
0x180017e2c  lea     rcx, [rbp+1C0h+var_C0]
0x180017e33  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180017e38  mov     rsi, rax
0x180017e3b  movss   xmm1, dword ptr [rbx+4]
0x180017e40  cvtps2pd xmm1, xmm1
0x180017e43  mov     r8d, edi
0x180017e46  lea     rcx, [rbp+1C0h+var_E0]
0x180017e4d  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180017e52  mov     rdi, rax
0x180017e55  movss   xmm1, dword ptr [rbx]
0x180017e59  cvtps2pd xmm1, xmm1
0x180017e5c  mov     r8d, 6
0x180017e62  lea     rcx, [rbp+1C0h+var_100]
0x180017e69  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180017e6e  mov     rbx, rax
0x180017e71  lea     r8, asc_1800257D0; "\n"
0x180017e78  mov     rdx, r13
0x180017e7b  lea     rcx, [rbp+1C0h+var_120]
0x180017e82  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180017e87  nop
0x180017e88  mov     r8, rbx
0x180017e8b  mov     rdx, rax
0x180017e8e  lea     rcx, [rbp+1C0h+var_140]
0x180017e95  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180017e9a  nop
0x180017e9b  lea     rbx, asc_1800257D8; " "
0x180017ea2  mov     r8, rbx
0x180017ea5  mov     rdx, rax
0x180017ea8  lea     rcx, [rbp+1C0h+var_160]
0x180017eac  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180017eb1  nop
0x180017eb2  mov     r8, rdi
0x180017eb5  mov     rdx, rax
0x180017eb8  lea     rcx, [rbp+1C0h+var_180]
0x180017ebc  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180017ec1  nop
0x180017ec2  mov     r8, rbx
0x180017ec5  mov     rdx, rax
0x180017ec8  lea     rcx, [rbp+1C0h+var_1A0]
0x180017ecc  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180017ed1  nop
0x180017ed2  mov     r8, rsi
0x180017ed5  mov     rdx, rax
0x180017ed8  lea     rcx, [rbp+1C0h+var_1C0]
0x180017edc  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180017ee1  nop
0x180017ee2  mov     r8, rbx
0x180017ee5  mov     rdx, rax
0x180017ee8  lea     rcx, [rbp+1C0h+var_1E0]
0x180017eec  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180017ef1  nop
0x180017ef2  mov     r8, r14
0x180017ef5  mov     rdx, rax
0x180017ef8  lea     rcx, [rbp+1C0h+var_200]
0x180017efc  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180017f01  nop
0x180017f02  mov     r8, rbx
0x180017f05  mov     rdx, rax
0x180017f08  lea     rcx, [rbp+1C0h+var_220]
0x180017f0c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180017f11  nop
0x180017f12  mov     r8, r15
0x180017f15  mov     rdx, rax
0x180017f18  lea     rcx, [rbp+1C0h+var_240]
0x180017f1c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180017f21  nop
0x180017f22  mov     r8, rbx
0x180017f25  mov     rdx, rax
0x180017f28  lea     rcx, [rsp+2C0h+var_260]
0x180017f2d  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180017f32  nop
0x180017f33  mov     r8, r12
0x180017f36  mov     rdx, rax
0x180017f39  lea     rcx, [rsp+2C0h+var_280]
0x180017f3e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180017f43  nop
0x180017f44  lea     r8, aCm; " cm"
0x180017f4b  mov     rdx, rax
0x180017f4e  lea     rcx, [rsp+2C0h+var_2A0]
0x180017f53  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180017f58  mov     rdx, rax
0x180017f5b  mov     rcx, r13
0x180017f5e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180017f63  lea     rcx, [rsp+2C0h+var_2A0]
0x180017f68  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017f6d  nop
0x180017f6e  lea     rcx, [rsp+2C0h+var_280]
0x180017f73  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017f78  nop
0x180017f79  lea     rcx, [rsp+2C0h+var_260]
0x180017f7e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017f83  nop
0x180017f84  lea     rcx, [rbp+1C0h+var_240]
0x180017f88  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017f8d  nop
0x180017f8e  lea     rcx, [rbp+1C0h+var_220]
0x180017f92  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017f97  nop
0x180017f98  lea     rcx, [rbp+1C0h+var_200]
0x180017f9c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017fa1  nop
0x180017fa2  lea     rcx, [rbp+1C0h+var_1E0]
0x180017fa6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017fab  nop
0x180017fac  lea     rcx, [rbp+1C0h+var_1C0]
0x180017fb0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017fb5  nop
0x180017fb6  lea     rcx, [rbp+1C0h+var_1A0]
0x180017fba  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017fbf  nop
0x180017fc0  lea     rcx, [rbp+1C0h+var_180]
0x180017fc4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017fc9  nop
0x180017fca  lea     rcx, [rbp+1C0h+var_160]
0x180017fce  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017fd3  nop
0x180017fd4  lea     rcx, [rbp+1C0h+var_140]
0x180017fdb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017fe0  nop
0x180017fe1  lea     rcx, [rbp+1C0h+var_120]
0x180017fe8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017fed  nop
0x180017fee  lea     rcx, [rbp+1C0h+var_100]
0x180017ff5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017ffa  nop
0x180017ffb  lea     rcx, [rbp+1C0h+var_E0]
0x180018002  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018007  nop
0x180018008  lea     rcx, [rbp+1C0h+var_C0]
0x18001800f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018014  nop
0x180018015  lea     rcx, [rbp+1C0h+var_A0]
0x18001801c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018021  nop
0x180018022  lea     rcx, [rbp+1C0h+var_80]
0x180018029  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001802e  nop
0x18001802f  lea     rcx, [rbp+1C0h+var_60]
0x180018036  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001803b  mov     rcx, [rbp+1C0h+var_40]
0x180018042  xor     rcx, rsp; StackCookie
0x180018045  call    __security_check_cookie
0x18001804a  mov     rbx, [rsp+2C0h+arg_10]
0x180018052  add     rsp, 290h
0x180018059  pop     r15
0x18001805b  pop     r14
0x18001805d  pop     r13
0x18001805f  pop     r12
0x180018061  pop     rdi
0x180018062  pop     rsi
0x180018063  pop     rbp
0x180018064  retn
```
