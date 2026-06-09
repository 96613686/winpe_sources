# PCLmWriter::PDFDocumentWriter::_SortXRef(void)

- ea: `0x180016704`
- end: `0x1800168c9`
- name: `?_SortXRef@PDFDocumentWriter@PCLmWriter@@AEAAXXZ`
- size: `453`
- prototype: `void __fastcall(PCLmWriter::PDFDocumentWriter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015de4`

## callees

- `0x1800015f0`
- `0x18000edc0`
- `0x18000f448`
- `0x18001397c`
- `0x180013aac`
- `0x180014204`
- `0x180016704`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PCLmWriter::PDFDocumentWriter::_SortXRef(
        PCLmWriter::PDFDocumentWriter *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v5; // rdi
  int v6; // r15d
  int v7; // r14d
  __int64 v8; // rsi
  _DWORD *v9; // rbx
  _DWORD *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  _DWORD *v13; // [rsp+20h] [rbp-50h] BYREF
  __int64 v14; // [rsp+28h] [rbp-48h]
  __int64 v15; // [rsp+30h] [rbp-40h]
  __int128 v16; // [rsp+40h] [rbp-30h]
  __int128 v17; // [rsp+50h] [rbp-20h] BYREF

  v5 = (_QWORD *)((char *)this + 120);
  LOBYTE(a4) = 0;
  std::_Sort_unchecked<_XREFENTRY *,std::less<void>>(
    *((_QWORD *)this + 15),
    *((_QWORD *)this + 16),
    (__int64)(*((_QWORD *)this + 16) - *((_QWORD *)this + 15)) >> 4,
    a4);
  v6 = 0;
  v7 = 0;
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(&v13);
  LODWORD(v8) = 0;
  v9 = (_DWORD *)*v5;
  LODWORD(v17) = *(_DWORD *)*v5;
  *(_QWORD *)((char *)&v17 + 4) = 0;
  BYTE12(v17) = 100;
  *(_WORD *)((char *)&v17 + 13) = 0;
  HIBYTE(v17) = 0;
  if ( v14 == v15 )
    std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(&v13, v14, &v17);
  else
    std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(&v13, &v17);
  while ( v9 != *((_DWORD **)this + 16) )
  {
    if ( *v9 != v6 + 1 && *v9 )
    {
      v13[4 * (unsigned int)v8 + 1] = v7;
      v7 = 0;
      v8 = (v14 - (__int64)v13) >> 4;
      LODWORD(v16) = *v9;
      *(_QWORD *)((char *)&v16 + 4) = 0;
      BYTE12(v16) = 100;
      *(_WORD *)((char *)&v16 + 13) = 0;
      HIBYTE(v16) = 0;
      v17 = v16;
      if ( v14 == v15 )
        std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(&v13, v14, &v17);
      else
        std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(&v13, &v17);
    }
    if ( v14 == v15 )
      std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(&v13, v14, v9);
    else
      std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(&v13, v9);
    v6 = *v9;
    v9 += 4;
    ++v7;
  }
  v13[4 * (unsigned int)v8 + 1] = v7;
  if ( v5 == &v13 )
  {
    v12 = v15;
    v10 = v13;
  }
  else
  {
    v10 = (_DWORD *)*v5;
    *v5 = v13;
    v13 = v10;
    v11 = v5[1];
    v5[1] = v14;
    v14 = v11;
    v12 = v5[2];
    v5[2] = v15;
    v15 = v12;
  }
  if ( v10 )
    std::_Deallocate<16>(v10, (v12 - (_QWORD)v10) & 0xFFFFFFFFFFFFFFF0uLL);
}

```

## disassembly

```asm
0x180016704  mov     [rsp-28h+arg_8], rbx
0x180016709  mov     [rsp-28h+arg_10], rsi
0x18001670e  push    rbp
0x18001670f  push    rdi
0x180016710  push    r13
0x180016712  push    r14
0x180016714  push    r15
0x180016716  mov     rbp, rsp
0x180016719  sub     rsp, 70h
0x18001671d  mov     rax, cs:__security_cookie
0x180016724  xor     rax, rsp
0x180016727  mov     [rbp+var_10], rax
0x18001672b  mov     r13, rcx
0x18001672e  mov     rdx, [rcx+80h]
0x180016735  lea     rdi, [rcx+78h]
0x180016739  xor     r9b, r9b
0x18001673c  mov     r8, rdx
0x18001673f  sub     r8, [rdi]
0x180016742  sar     r8, 4
0x180016746  mov     rcx, [rdi]
0x180016749  call    ??$_Sort_unchecked@PEAU_XREFENTRY@@U?$less@X@std@@@std@@YAXPEAU_XREFENTRY@@0_JU?$less@X@0@@Z; std::_Sort_unchecked<_XREFENTRY *,std::less<void>>(_XREFENTRY *,_XREFENTRY *,__int64,std::less<void>)
0x18001674e  xor     r15d, r15d
0x180016751  xor     r14d, r14d
0x180016754  lea     rcx, [rbp+var_50]
0x180016758  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x18001675d  nop
0x18001675e  xor     esi, esi
0x180016760  mov     rbx, [rdi]
0x180016763  mov     eax, [rbx]
0x180016765  mov     dword ptr [rbp+var_20], eax
0x180016768  mov     qword ptr [rbp+var_20+4], rsi
0x18001676c  mov     byte ptr [rbp+var_20+0Ch], 64h ; 'd'
0x180016770  xor     eax, eax
0x180016772  mov     word ptr [rbp+var_20+0Dh], ax
0x180016776  mov     byte ptr [rbp+var_20+0Fh], al
0x180016779  mov     rdx, [rbp+var_48]
0x18001677d  lea     rcx, [rbp+var_50]
0x180016781  cmp     rdx, [rbp+var_40]
0x180016785  jz      short loc_180016792
0x180016787  lea     rdx, [rbp+var_20]
0x18001678b  call    ??$_Emplace_back_with_unused_capacity@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAAEAU_XREFENTRY@@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(_XREFENTRY const &)
0x180016790  jmp     short loc_18001679B
0x180016792  lea     r8, [rbp+var_20]
0x180016796  call    ??$_Emplace_reallocate@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAPEAU_XREFENTRY@@QEAU2@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(_XREFENTRY * const,_XREFENTRY const &)
0x18001679b  cmp     rbx, [r13+80h]
0x1800167a2  jz      loc_180016841
0x1800167a8  lea     eax, [r15+1]
0x1800167ac  cmp     [rbx], eax
0x1800167ae  jz      short loc_180016812
0x1800167b0  cmp     dword ptr [rbx], 0
0x1800167b3  jz      short loc_180016812
0x1800167b5  mov     ecx, esi
0x1800167b7  add     rcx, rcx
0x1800167ba  mov     rax, [rbp+var_50]
0x1800167be  mov     [rax+rcx*8+4], r14d
0x1800167c3  xor     r14d, r14d
0x1800167c6  mov     rdx, [rbp+var_48]
0x1800167ca  mov     rsi, rdx
0x1800167cd  sub     rsi, [rbp+var_50]
0x1800167d1  sar     rsi, 4
0x1800167d5  mov     eax, [rbx]
0x1800167d7  mov     dword ptr [rbp+var_30], eax
0x1800167da  mov     qword ptr [rbp+var_30+4], r14
0x1800167de  mov     byte ptr [rbp+var_30+0Ch], 64h ; 'd'
0x1800167e2  xor     eax, eax
0x1800167e4  mov     word ptr [rbp+var_30+0Dh], ax
0x1800167e8  mov     byte ptr [rbp+var_30+0Fh], al
0x1800167eb  movaps  xmm0, [rbp+var_30]
0x1800167ef  movdqa  [rbp+var_20], xmm0
0x1800167f4  lea     rcx, [rbp+var_50]
0x1800167f8  cmp     rdx, [rbp+var_40]
0x1800167fc  jz      short loc_180016809
0x1800167fe  lea     rdx, [rbp+var_20]
0x180016802  call    ??$_Emplace_back_with_unused_capacity@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAAEAU_XREFENTRY@@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(_XREFENTRY const &)
0x180016807  jmp     short loc_180016812
0x180016809  lea     r8, [rbp+var_20]
0x18001680d  call    ??$_Emplace_reallocate@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAPEAU_XREFENTRY@@QEAU2@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(_XREFENTRY * const,_XREFENTRY const &)
0x180016812  mov     rdx, [rbp+var_48]
0x180016816  lea     rcx, [rbp+var_50]
0x18001681a  cmp     rdx, [rbp+var_40]
0x18001681e  jz      short loc_18001682A
0x180016820  mov     rdx, rbx
0x180016823  call    ??$_Emplace_back_with_unused_capacity@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAAEAU_XREFENTRY@@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(_XREFENTRY const &)
0x180016828  jmp     short loc_180016832
0x18001682a  mov     r8, rbx
0x18001682d  call    ??$_Emplace_reallocate@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAPEAU_XREFENTRY@@QEAU2@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(_XREFENTRY * const,_XREFENTRY const &)
0x180016832  mov     r15d, [rbx]
0x180016835  add     rbx, 10h
0x180016839  inc     r14d
0x18001683c  jmp     loc_18001679B
0x180016841  mov     ecx, esi
0x180016843  add     rcx, rcx
0x180016846  mov     rax, [rbp+var_50]
0x18001684a  mov     [rax+rcx*8+4], r14d
0x18001684f  lea     rax, [rbp+var_50]
0x180016853  cmp     rdi, rax
0x180016856  jz      short loc_180016888
0x180016858  mov     r8, [rdi]
0x18001685b  mov     rax, [rbp+var_50]
0x18001685f  mov     [rdi], rax
0x180016862  mov     [rbp+var_50], r8
0x180016866  mov     rcx, [rdi+8]
0x18001686a  mov     rax, [rbp+var_48]
0x18001686e  mov     [rdi+8], rax
0x180016872  mov     [rbp+var_48], rcx
0x180016876  mov     rdx, [rdi+10h]
0x18001687a  mov     rax, [rbp+var_40]
0x18001687e  mov     [rdi+10h], rax
0x180016882  mov     [rbp+var_40], rdx
0x180016886  jmp     short loc_180016890
0x180016888  mov     rdx, [rbp+var_40]
0x18001688c  mov     r8, [rbp+var_50]
0x180016890  test    r8, r8
0x180016893  jz      short loc_1800168A4
0x180016895  sub     rdx, r8
0x180016898  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001689c  mov     rcx, r8
0x18001689f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800168a4  mov     rcx, [rbp+var_10]
0x1800168a8  xor     rcx, rsp; StackCookie
0x1800168ab  call    __security_check_cookie
0x1800168b0  lea     r11, [rsp+70h+var_s0]
0x1800168b5  mov     rbx, [r11+38h]
0x1800168b9  mov     rsi, [r11+40h]
0x1800168bd  mov     rsp, r11
0x1800168c0  pop     r15
0x1800168c2  pop     r14
0x1800168c4  pop     r13
0x1800168c6  pop     rdi
0x1800168c7  pop     rbp
0x1800168c8  retn
```
