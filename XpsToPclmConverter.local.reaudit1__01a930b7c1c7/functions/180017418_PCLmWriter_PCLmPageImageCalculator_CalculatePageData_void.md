# PCLmWriter::PCLmPageImageCalculator::_CalculatePageData(void)

- ea: `0x180017418`
- end: `0x18001761a`
- name: `?_CalculatePageData@PCLmPageImageCalculator@PCLmWriter@@AEAAXXZ`
- size: `514`
- prototype: `void __fastcall(PCLmWriter::PCLmPageImageCalculator *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180017350`

## callees

- `0x1800015f0`
- `0x18000f3e0`
- `0x180010718`
- `0x18001079c`
- `0x1800112f0`
- `0x1800113c4`
- `0x180011b4c`
- `0x180011bfc`
- `0x180013644`
- `0x18001583c`
- `0x180016a6c`
- `0x180016c14`
- `0x180017418`
- `0x18001f010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180017532`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180017532`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PCLmWriter::PCLmPageImageCalculator::_CalculatePageData(PCLmWriter::PCLmPageImageCalculator *this)
{
  unsigned int v2; // r14d
  int v3; // esi
  unsigned int v4; // edi
  unsigned int v5; // r15d
  __m128i si128; // xmm7
  unsigned int v7; // edx
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11[4]; // [rsp+28h] [rbp-E0h] BYREF
  char v12[8]; // [rsp+38h] [rbp-D0h] BYREF
  char v13[232]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v14[32]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v15; // [rsp+148h] [rbp+40h]
  __int64 v16; // [rsp+150h] [rbp+48h]
  __m128i v17; // [rsp+158h] [rbp+50h]
  unsigned int v18; // [rsp+168h] [rbp+60h]
  int v19; // [rsp+16Ch] [rbp+64h]
  _BYTE v20[32]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v21[32]; // [rsp+198h] [rbp+90h] BYREF

  *((float *)this + 8) = 72.0 / (float)*((int *)this + 14);
  *((float *)this + 11) = 72.0 / (float)*((int *)this + 15);
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 40LL))(*((_QWORD *)this + 3));
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3));
  v4 = v2;
  std::string::string(v21, "/Image");
  v5 = 0;
  if ( v2 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      std::string::string(v14);
      v15 = 0;
      v16 = 1065353216;
      v17 = si128;
      v15 = *(_QWORD *)PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(*((_QWORD *)this + 8), v11);
      std::ostringstream::ostringstream(v12);
      std::operator<<<char>(v12, v21);
      std::ostream::operator<<(v12, v5++);
      v18 = v2 - v4;
      v7 = *((_DWORD *)this + 20);
      v8 = v4;
      if ( v4 > v7 )
        v8 = *((_DWORD *)this + 20);
      v19 = v8;
      v4 = v7 < v4 ? v4 - v7 : 0;
      std::stringbuf::str(v13, v20);
      std::string::operator=(v14, v20);
      std::string::_Tidy_deallocate(v20);
      *(float *)&v16 = (float)v3;
      *(float *)&v17.m128i_i32[1] = (float)v19;
      *(float *)&v17.m128i_i32[3] = (float)(int)v4;
      v10 = *((_QWORD *)this + 1);
      if ( v10 == *((_QWORD *)this + 2) )
      {
        std::vector<PCLmWriter::PDFImageData>::_Emplace_reallocate<PCLmWriter::PDFImageData const &>(this, v10, v14);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<PCLmWriter::PDFImageData>>::construct<PCLmWriter::PDFImageData,PCLmWriter::PDFImageData const &>(
          v9,
          v10,
          v14);
        *((_QWORD *)this + 1) += 72LL;
      }
      std::ostringstream::`vbase destructor'(v12);
      std::string::_Tidy_deallocate(v14);
    }
    while ( v4 );
  }
  std::string::_Tidy_deallocate(v21);
}

```

## disassembly

```asm
0x180017418  mov     rax, rsp
0x18001741b  push    rbp
0x18001741c  push    rbx
0x18001741d  push    rsi
0x18001741e  push    rdi
0x18001741f  push    r14
0x180017421  push    r15
0x180017423  lea     rbp, [rax-118h]
0x18001742a  sub     rsp, 1E8h
0x180017431  movaps  xmmword ptr [rax-48h], xmm6
0x180017435  movaps  xmmword ptr [rax-58h], xmm7
0x180017439  mov     rax, cs:__security_cookie
0x180017440  xor     rax, rsp
0x180017443  mov     [rbp+110h+var_60], rax
0x18001744a  mov     rbx, rcx
0x18001744d  mov     eax, [rcx+38h]
0x180017450  xorps   xmm1, xmm1
0x180017453  cvtsi2ss xmm1, rax
0x180017458  movss   xmm2, cs:__real@42900000
0x180017460  movaps  xmm0, xmm2
0x180017463  divss   xmm0, xmm1
0x180017467  movss   dword ptr [rcx+20h], xmm0
0x18001746c  mov     eax, [rcx+3Ch]
0x18001746f  xorps   xmm1, xmm1
0x180017472  cvtsi2ss xmm1, rax
0x180017477  divss   xmm2, xmm1
0x18001747b  movss   dword ptr [rcx+2Ch], xmm2
0x180017480  mov     rcx, [rcx+18h]
0x180017484  mov     rax, [rcx]
0x180017487  mov     rax, [rax+28h]
0x18001748b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017490  mov     r14d, eax
0x180017493  mov     rcx, [rbx+18h]
0x180017497  mov     rdx, [rcx]
0x18001749a  mov     rax, [rdx+20h]
0x18001749e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174a3  mov     esi, eax
0x1800174a5  mov     edi, r14d
0x1800174a8  lea     rdx, aImage; "/Image"
0x1800174af  lea     rcx, [rbp+110h+var_80]
0x1800174b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800174bb  nop
0x1800174bc  xor     r15d, r15d
0x1800174bf  test    r14d, r14d
0x1800174c2  jz      loc_1800175E1
0x1800174c8  xorps   xmm6, xmm6
0x1800174cb  cvtsi2ss xmm6, rsi
0x1800174d0  movdqa  xmm7, cs:__xmm@00000000000000003f80000000000000
0x1800174d8  lea     rcx, [rbp+110h+var_F0]
0x1800174dc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800174e1  mov     [rbp+110h+var_D0], 0
0x1800174e9  mov     [rbp+110h+var_C8], 3F800000h
0x1800174f1  movaps  [rbp+110h+var_C0], xmm7
0x1800174f5  lea     rdx, [rsp+210h+var_1F0]
0x1800174fa  mov     rcx, [rbx+40h]
0x1800174fe  call    ?GenerateObjectIdentifier@PDFDocumentWriter@PCLmWriter@@QEAA?AU?$pair@II@std@@XZ; PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(void)
0x180017503  mov     ecx, [rax]
0x180017505  mov     dword ptr [rbp+110h+var_D0], ecx
0x180017508  mov     eax, [rax+4]
0x18001750b  mov     dword ptr [rbp+110h+var_D0+4], eax
0x18001750e  lea     rcx, [rsp+210h+var_1E0]
0x180017513  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180017518  nop
0x180017519  lea     rdx, [rbp+110h+var_80]
0x180017520  lea     rcx, [rsp+210h+var_1E0]
0x180017525  call    ??$?6DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<<char>(std::ostream &,std::string const &)
0x18001752a  mov     edx, r15d
0x18001752d  lea     rcx, [rsp+210h+var_1E0]
0x180017532  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180017538  inc     r15d
0x18001753b  mov     eax, r14d
0x18001753e  sub     eax, edi
0x180017540  mov     [rbp+110h+var_B0], eax
0x180017543  mov     edx, [rbx+50h]
0x180017546  mov     eax, edi
0x180017548  cmp     edi, edx
0x18001754a  cmova   eax, edx
0x18001754d  mov     [rbp+110h+var_AC], eax
0x180017550  mov     ecx, edi
0x180017552  sub     ecx, edx
0x180017554  cmp     edx, edi
0x180017556  sbb     eax, eax
0x180017558  and     eax, ecx
0x18001755a  mov     edi, eax
0x18001755c  lea     rdx, [rbp+110h+var_A0]
0x180017560  lea     rcx, [rsp+210h+var_1D8]
0x180017565  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18001756a  lea     rdx, [rbp+110h+var_A0]
0x18001756e  lea     rcx, [rbp+110h+var_F0]
0x180017572  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180017577  lea     rcx, [rbp+110h+var_A0]
0x18001757b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017580  movss   dword ptr [rbp+110h+var_C8], xmm6
0x180017585  mov     eax, [rbp+110h+var_AC]
0x180017588  xorps   xmm0, xmm0
0x18001758b  cvtsi2ss xmm0, rax
0x180017590  movss   dword ptr [rbp+110h+var_C0+4], xmm0
0x180017595  xorps   xmm1, xmm1
0x180017598  cvtsi2ss xmm1, rdi
0x18001759d  movss   dword ptr [rbp+110h+var_C0+0Ch], xmm1
0x1800175a2  mov     rdx, [rbx+8]
0x1800175a6  lea     r8, [rbp+110h+var_F0]
0x1800175aa  cmp     rdx, [rbx+10h]
0x1800175ae  jz      short loc_1800175BC
0x1800175b0  call    ??$construct@UPDFImageData@PCLmWriter@@AEBU12@@?$_Default_allocator_traits@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@SAXAEAV?$allocator@UPDFImageData@PCLmWriter@@@1@QEAUPDFImageData@PCLmWriter@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<PCLmWriter::PDFImageData>>::construct<PCLmWriter::PDFImageData,PCLmWriter::PDFImageData const &>(std::allocator<PCLmWriter::PDFImageData> &,PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData const &)
0x1800175b5  add     qword ptr [rbx+8], 48h ; 'H'
0x1800175ba  jmp     short loc_1800175C5
0x1800175bc  mov     rcx, rbx
0x1800175bf  call    ??$_Emplace_reallocate@AEBUPDFImageData@PCLmWriter@@@?$vector@UPDFImageData@PCLmWriter@@V?$allocator@UPDFImageData@PCLmWriter@@@std@@@std@@AEAAPEAUPDFImageData@PCLmWriter@@QEAU23@AEBU23@@Z; std::vector<PCLmWriter::PDFImageData>::_Emplace_reallocate<PCLmWriter::PDFImageData const &>(PCLmWriter::PDFImageData * const,PCLmWriter::PDFImageData const &)
0x1800175c4  nop
0x1800175c5  lea     rcx, [rsp+210h+var_1E0]
0x1800175ca  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x1800175cf  nop
0x1800175d0  lea     rcx, [rbp+110h+var_F0]
0x1800175d4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800175d9  test    edi, edi
0x1800175db  jnz     loc_1800174D8
0x1800175e1  lea     rcx, [rbp+110h+var_80]
0x1800175e8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800175ed  mov     rcx, [rbp+110h+var_60]
0x1800175f4  xor     rcx, rsp; StackCookie
0x1800175f7  call    __security_check_cookie
0x1800175fc  lea     r11, [rsp+210h+var_28]
0x180017604  movaps  xmm6, xmmword ptr [r11-18h]
0x180017609  movaps  xmm7, xmmword ptr [r11-28h]
0x18001760e  mov     rsp, r11
0x180017611  pop     r15
0x180017613  pop     r14
0x180017615  pop     rdi
0x180017616  pop     rsi
0x180017617  pop     rbx
0x180017618  pop     rbp
0x180017619  retn
```
