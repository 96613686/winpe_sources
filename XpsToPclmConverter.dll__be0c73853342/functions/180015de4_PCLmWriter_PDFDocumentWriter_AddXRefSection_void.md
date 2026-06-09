# PCLmWriter::PDFDocumentWriter::_AddXRefSection(void)

- ea: `0x180015de4`
- end: `0x18001620f`
- name: `?_AddXRefSection@PDFDocumentWriter@PCLmWriter@@AEAAXXZ`
- size: `1067`
- prototype: `void __fastcall(PCLmWriter::PDFDocumentWriter *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015bf0`

## callees

- `0x1800015f0`
- `0x18000e7c8`
- `0x18000edc0`
- `0x18000efa8`
- `0x18000f3e0`
- `0x18000f41c`
- `0x18000f448`
- `0x1800101cc`
- `0x180010718`
- `0x180012cc0`
- `0x18001397c`
- `0x180013aac`
- `0x180013d40`
- `0x18001496c`
- `0x1800149b0`
- `0x180015de4`
- `0x180016218`
- `0x1800163b0`
- `0x180016580`
- `0x180016704`
- `0x18001cc44`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall PCLmWriter::PDFDocumentWriter::_AddXRefSection(PCLmWriter::PDFDocumentWriter *this)
{
  unsigned int v2; // r15d
  _QWORD *v3; // rdi
  unsigned int v4; // r13d
  _DWORD *v5; // rdx
  __int64 v6; // rax
  char *v7; // rcx
  unsigned int v8; // edi
  __int64 v9; // r13
  unsigned int v10; // r10d
  __int64 *v11; // r11
  __int64 v12; // rsi
  std::_Ref_count_base *v13; // r12
  __int64 v14; // rax
  std::_Ref_count_base *v15; // rsi
  __int64 v16; // rdx
  char *v17; // rcx
  __int64 *v18; // rbx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  std::_Ref_count_base *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  void (__fastcall *v25)(__int64, __int64); // r8
  __int64 v26; // r9
  unsigned int v27; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-A5h]
  std::_Ref_count_base *v29[2]; // [rsp+38h] [rbp-A1h] BYREF
  _DWORD *v30; // [rsp+48h] [rbp-91h] BYREF
  __int64 v31; // [rsp+50h] [rbp-89h]
  __int64 v32; // [rsp+58h] [rbp-81h]
  __int64 v33; // [rsp+60h] [rbp-79h]
  _BYTE v34[16]; // [rsp+68h] [rbp-71h] BYREF
  __int64 v35; // [rsp+78h] [rbp-61h]
  std::_Ref_count_base *v36[2]; // [rsp+80h] [rbp-59h] BYREF
  __int64 v37; // [rsp+90h] [rbp-49h] BYREF
  int v38; // [rsp+98h] [rbp-41h]
  char v39; // [rsp+9Ch] [rbp-3Dh]
  __int16 v40; // [rsp+9Dh] [rbp-3Ch]
  char v41; // [rsp+9Fh] [rbp-3Ah]
  _DWORD v42[3]; // [rsp+A0h] [rbp-39h] BYREF
  char v43; // [rsp+ACh] [rbp-2Dh]
  __int16 v44; // [rsp+ADh] [rbp-2Ch]
  char v45; // [rsp+AFh] [rbp-2Ah]
  _BYTE v46[16]; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-19h]
  char v48[8]; // [rsp+D0h] [rbp-9h] BYREF
  char v49[16]; // [rsp+D8h] [rbp-1h] BYREF

  strcpy(v48, "xref\n");
  strcpy(v49, "trailer\n");
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(&v30);
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v34);
  v2 = 0;
  *(_OWORD *)v36 = 0;
  PCLmWriter::PDFDocumentWriter::_BuildIndex(this, &v30);
  v3 = (_QWORD *)((char *)this + 16);
  (*(void (__fastcall **)(_QWORD, char *, __int64))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), v48, 5);
  v4 = 0;
  v28 = 0;
  v5 = v30;
  if ( (v31 - (__int64)v30) >> 2 )
  {
    do
    {
      v6 = *((_QWORD *)this + 15);
      if ( v6 == *((_QWORD *)this + 16) )
        v6 = *((_QWORD *)this + 16);
      else
        *((_QWORD *)this + 16) = v6;
      if ( !v4 && *v5 == 1 )
      {
        v37 = 0;
        v38 = 0xFFFF;
        v39 = 102;
        v40 = 0;
        v41 = 0;
        v7 = (char *)this + 120;
        if ( v6 == *((_QWORD *)this + 17) )
          std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(v7, v6, &v37);
        else
          std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(v7, &v37);
        v5 = v30;
      }
      v35 = v4;
      v8 = v5[v4];
      v27 = v8;
      v33 = v4 + 1;
      if ( v8 <= v5[v33] + v8 - 1 )
      {
        v9 = v35;
        do
        {
          std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PCLmWriter::IXrefEntry>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>>,0>>::_Find_lower_bound<unsigned int>(
            *((_QWORD *)this + 7),
            v46,
            &v27);
          v12 = v47;
          if ( *(_BYTE *)(v47 + 25) || v10 < *(_DWORD *)(v47 + 32) )
            v12 = *v11;
          v13 = (std::_Ref_count_base *)_RTDynamicCast_0(
                                          *(_QWORD *)(v12 + 40),
                                          0,
                                          &PCLmWriter::IXrefEntry `RTTI Type Descriptor',
                                          &PCLmWriter::IRegularXrefEntry `RTTI Type Descriptor',
                                          0);
          if ( v13 )
          {
            v14 = *(_QWORD *)(v12 + 48);
            if ( v14 )
              _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
            v29[0] = v13;
            v15 = *(std::_Ref_count_base **)(v12 + 48);
            v29[1] = v15;
          }
          else
          {
            *(_OWORD *)v29 = 0;
            v15 = (std::_Ref_count_base *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
            v13 = 0;
          }
          v42[0] = v8;
          v42[1] = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v13 + 16LL))(v13);
          v42[2] = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v13 + 8LL))(v13);
          v43 = 110;
          v44 = 0;
          v45 = 0;
          v16 = *((_QWORD *)this + 16);
          v17 = (char *)this + 120;
          if ( v16 == *((_QWORD *)this + 17) )
            std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(v17, v16, v42);
          else
            std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(v17, v42);
          if ( v8 > v2 )
            v2 = v8;
          if ( v15 )
            std::_Ref_count_base::_Decref(v15);
          v27 = ++v8;
          v5 = v30;
        }
        while ( v8 <= v30[v9] + v30[v33] - 1 );
        v4 = v28;
      }
      v4 += 2;
      v28 = v4;
    }
    while ( v4 < (unsigned __int64)((v31 - (__int64)v5) >> 2) );
    v3 = (_QWORD *)((char *)this + 16);
  }
  PCLmWriter::PDFDocumentWriter::_SortXRef(this);
  PCLmWriter::PDFDocumentWriter::_AppendXRef(this);
  (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*v3 + 24LL))(*v3, v49, 8);
  if ( v2 > 0x7FFFFFFF || (unsigned __int64)((int)v2 + 2147483649LL) > 0xFFFFFFFF )
    PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow();
  PCLmWriter::PDFDocumentWriter::_GetTrailer(this, v34);
  v18 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base **, _QWORD, _QWORD, _DWORD))(**(_QWORD **)this + 16LL))(
                     *(_QWORD *)this,
                     v29,
                     v2 + 1,
                     0,
                     0);
  std::string::string(v46, "/Size");
  v19 = (_QWORD *)std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v34, v46);
  v20 = *v18;
  v21 = v18[1];
  *v18 = 0;
  v18[1] = 0;
  *v19 = v20;
  v22 = (std::_Ref_count_base *)v19[1];
  v19[1] = v21;
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  std::string::_Tidy_deallocate(v46);
  if ( v29[1] )
    std::_Ref_count_base::_Decref(v29[1]);
  v23 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base **, _BYTE *, _QWORD, _DWORD))(**(_QWORD **)this + 40LL))(
          *(_QWORD *)this,
          v29,
          v34,
          0,
          0);
  std::shared_ptr<PCLmWriter::IByteStream>::operator=(v36, v23);
  if ( v29[1] )
    std::_Ref_count_base::_Decref(v29[1]);
  v24 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v29, v3);
  v25(v26, v24);
  if ( v36[1] )
    std::_Ref_count_base::_Decref(v36[1]);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v34,
    v34);
  if ( v30 )
    std::_Deallocate<16>(v30, (v32 - (_QWORD)v30) & 0xFFFFFFFFFFFFFFFCuLL);
}

```

## disassembly

```asm
0x180015de4  push    rbp
0x180015de6  push    rbx
0x180015de7  push    rsi
0x180015de8  push    rdi
0x180015de9  push    r12
0x180015deb  push    r13
0x180015ded  push    r14
0x180015def  push    r15
0x180015df1  lea     rbp, [rsp-1Fh]
0x180015df6  sub     rsp, 0F8h
0x180015dfd  mov     rax, cs:__security_cookie
0x180015e04  xor     rax, rsp
0x180015e07  mov     [rbp+57h+var_48], rax
0x180015e0b  mov     r14, rcx
0x180015e0e  mov     eax, dword ptr cs:aXref; "xref\n"
0x180015e14  mov     dword ptr [rbp+57h+var_60], eax
0x180015e17  movzx   eax, word ptr cs:aXref+4; "\n"
0x180015e1e  mov     word ptr [rbp+57h+var_60+4], ax
0x180015e22  movsd   xmm0, qword ptr cs:aTrailer; "trailer\n"
0x180015e2a  movsd   qword ptr [rbp+57h+var_58], xmm0
0x180015e2f  mov     al, byte ptr cs:aTrailer+8; ""
0x180015e35  mov     [rbp+57h+var_58+8], al
0x180015e38  lea     rcx, [rsp+130h+var_E8]
0x180015e3d  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x180015e42  nop
0x180015e43  lea     rcx, [rbp+57h+var_C8]
0x180015e47  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x180015e4c  nop
0x180015e4d  xor     r12d, r12d
0x180015e50  mov     r15d, r12d
0x180015e53  xorps   xmm0, xmm0
0x180015e56  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x180015e5b  lea     rdx, [rsp+130h+var_E8]
0x180015e60  mov     rcx, r14
0x180015e63  call    ?_BuildIndex@PDFDocumentWriter@PCLmWriter@@AEAAXPEAV?$vector@IV?$allocator@I@std@@@std@@@Z; PCLmWriter::PDFDocumentWriter::_BuildIndex(std::vector<uint> *)
0x180015e68  lea     rdi, [r14+10h]
0x180015e6c  mov     rcx, [rdi]
0x180015e6f  mov     rax, [rcx]
0x180015e72  lea     r8d, [r12+5]
0x180015e77  lea     rdx, [rbp+57h+var_60]
0x180015e7b  mov     rax, [rax+18h]
0x180015e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e84  mov     r13d, r12d
0x180015e87  mov     [rsp+130h+var_FC], r12d
0x180015e8c  mov     rax, [rsp+130h+var_E0]
0x180015e91  mov     rdx, [rsp+130h+var_E8]
0x180015e96  sub     rax, rdx
0x180015e99  sar     rax, 2
0x180015e9d  test    rax, rax
0x180015ea0  jz      loc_180016074
0x180015ea6  lea     rbx, [r14+78h]
0x180015eaa  mov     rax, [rbx]
0x180015ead  cmp     rax, [rbx+8]
0x180015eb1  jz      short loc_180015EB9
0x180015eb3  mov     [rbx+8], rax
0x180015eb7  jmp     short loc_180015EBD
0x180015eb9  mov     rax, [rbx+8]
0x180015ebd  test    r13d, r13d
0x180015ec0  jnz     short loc_180015F08
0x180015ec2  cmp     dword ptr [rdx], 1
0x180015ec5  jnz     short loc_180015F08
0x180015ec7  mov     [rbp+57h+var_A0], 0
0x180015ecf  mov     [rbp+57h+var_98], 0FFFFh
0x180015ed6  mov     [rbp+57h+var_94], 66h ; 'f'
0x180015eda  xor     ecx, ecx
0x180015edc  mov     [rbp+57h+var_93], cx
0x180015ee0  mov     [rbp+57h+var_91], cl
0x180015ee3  mov     rcx, rbx
0x180015ee6  cmp     rax, [rbx+10h]
0x180015eea  jz      short loc_180015EF7
0x180015eec  lea     rdx, [rbp+57h+var_A0]
0x180015ef0  call    ??$_Emplace_back_with_unused_capacity@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAAEAU_XREFENTRY@@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(_XREFENTRY const &)
0x180015ef5  jmp     short loc_180015F03
0x180015ef7  lea     r8, [rbp+57h+var_A0]
0x180015efb  mov     rdx, rax
0x180015efe  call    ??$_Emplace_reallocate@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAPEAU_XREFENTRY@@QEAU2@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(_XREFENTRY * const,_XREFENTRY const &)
0x180015f03  mov     rdx, [rsp+130h+var_E8]
0x180015f08  mov     eax, r13d
0x180015f0b  mov     [rbp+57h+var_B8], rax
0x180015f0f  mov     edi, [rdx+rax*4]
0x180015f12  mov     [rsp+130h+var_100], edi
0x180015f16  mov     r10d, edi
0x180015f19  lea     eax, [r13+1]
0x180015f1d  mov     [rbp+57h+var_D0], rax
0x180015f21  lea     ecx, [rdi-1]
0x180015f24  add     ecx, [rdx+rax*4]
0x180015f27  cmp     edi, ecx
0x180015f29  ja      loc_18001604F
0x180015f2f  mov     r13, [rbp+57h+var_B8]
0x180015f33  mov     r11, [r14+38h]
0x180015f37  lea     r8, [rsp+130h+var_100]
0x180015f3c  lea     rdx, [rbp+57h+var_80]
0x180015f40  mov     rcx, r11
0x180015f43  call    ??$_Find_lower_bound@I@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@1@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PCLmWriter::IXrefEntry>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>,0>>::_Find_lower_bound<uint>(uint const &)
0x180015f48  mov     rsi, [rbp+57h+var_70]
0x180015f4c  cmp     [rsi+19h], r12b
0x180015f50  jnz     short loc_180015F58
0x180015f52  cmp     r10d, [rsi+20h]
0x180015f56  jnb     short loc_180015F5B
0x180015f58  mov     rsi, [r11]
0x180015f5b  mov     [rsp+130h+var_110], r12d
0x180015f60  lea     r9, ??_R0?AVIRegularXrefEntry@PCLmWriter@@@8; PCLmWriter::IRegularXrefEntry `RTTI Type Descriptor'
0x180015f67  lea     r8, ??_R0?AVIXrefEntry@PCLmWriter@@@8; PCLmWriter::IXrefEntry `RTTI Type Descriptor'
0x180015f6e  xor     edx, edx
0x180015f70  mov     rcx, [rsi+28h]
0x180015f74  call    __RTDynamicCast_0
0x180015f79  mov     r12, rax
0x180015f7c  test    rax, rax
0x180015f7f  jz      short loc_180015F9E
0x180015f81  mov     rax, [rsi+30h]
0x180015f85  test    rax, rax
0x180015f88  jz      short loc_180015F8E
0x180015f8a  lock inc dword ptr [rax+8]
0x180015f8e  mov     [rsp+130h+var_F8], r12
0x180015f93  mov     rsi, [rsi+30h]
0x180015f97  mov     [rsp+130h+var_F8+8], rsi
0x180015f9c  jmp     short loc_180015FB9
0x180015f9e  xorps   xmm0, xmm0
0x180015fa1  xorps   xmm1, xmm1
0x180015fa4  movdqu  xmmword ptr [rsp+130h+var_F8], xmm1
0x180015faa  psrldq  xmm0, 8
0x180015faf  movq    rsi, xmm0
0x180015fb4  movq    r12, xmm1
0x180015fb9  mov     [rbp+57h+var_90], edi
0x180015fbc  mov     rax, [r12]
0x180015fc0  mov     rcx, r12
0x180015fc3  mov     rax, [rax+10h]
0x180015fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fcc  mov     [rbp+57h+var_8C], eax
0x180015fcf  mov     rax, [r12]
0x180015fd3  mov     rcx, r12
0x180015fd6  mov     rax, [rax+8]
0x180015fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fdf  mov     [rbp+57h+var_88], eax
0x180015fe2  mov     [rbp+57h+var_84], 6Eh ; 'n'
0x180015fe6  xor     eax, eax
0x180015fe8  mov     [rbp+57h+var_83], ax
0x180015fec  mov     [rbp+57h+var_81], al
0x180015fef  mov     rdx, [rbx+8]
0x180015ff3  mov     rcx, rbx
0x180015ff6  cmp     rdx, [rbx+10h]
0x180015ffa  jz      short loc_180016007
0x180015ffc  lea     rdx, [rbp+57h+var_90]
0x180016000  call    ??$_Emplace_back_with_unused_capacity@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAAEAU_XREFENTRY@@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_back_with_unused_capacity<_XREFENTRY const &>(_XREFENTRY const &)
0x180016005  jmp     short loc_180016010
0x180016007  lea     r8, [rbp+57h+var_90]
0x18001600b  call    ??$_Emplace_reallocate@AEBU_XREFENTRY@@@?$vector@U_XREFENTRY@@V?$allocator@U_XREFENTRY@@@std@@@std@@AEAAPEAU_XREFENTRY@@QEAU2@AEBU2@@Z; std::vector<_XREFENTRY>::_Emplace_reallocate<_XREFENTRY const &>(_XREFENTRY * const,_XREFENTRY const &)
0x180016010  cmp     edi, r15d
0x180016013  cmova   r15d, edi
0x180016017  xor     r12d, r12d
0x18001601a  test    rsi, rsi
0x18001601d  jz      short loc_180016027
0x18001601f  mov     rcx, rsi; this
0x180016022  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016027  inc     edi
0x180016029  mov     [rsp+130h+var_100], edi
0x18001602d  mov     r10d, edi
0x180016030  mov     rdx, [rsp+130h+var_E8]
0x180016035  mov     rax, [rbp+57h+var_D0]
0x180016039  mov     ecx, [rdx+rax*4]
0x18001603c  dec     ecx
0x18001603e  add     ecx, [rdx+r13*4]
0x180016042  cmp     edi, ecx
0x180016044  jbe     loc_180015F33
0x18001604a  mov     r13d, [rsp+130h+var_FC]
0x18001604f  add     r13d, 2
0x180016053  mov     [rsp+130h+var_FC], r13d
0x180016058  mov     rcx, [rsp+130h+var_E0]
0x18001605d  sub     rcx, rdx
0x180016060  sar     rcx, 2
0x180016064  mov     eax, r13d
0x180016067  cmp     rax, rcx
0x18001606a  jb      loc_180015EAA
0x180016070  lea     rdi, [r14+10h]
0x180016074  mov     rcx, r14; this
0x180016077  call    ?_SortXRef@PDFDocumentWriter@PCLmWriter@@AEAAXXZ; PCLmWriter::PDFDocumentWriter::_SortXRef(void)
0x18001607c  mov     rcx, r14; this
0x18001607f  call    ?_AppendXRef@PDFDocumentWriter@PCLmWriter@@AEAAXXZ; PCLmWriter::PDFDocumentWriter::_AppendXRef(void)
0x180016084  mov     rcx, [rdi]
0x180016087  mov     rax, [rcx]
0x18001608a  mov     r8d, 8
0x180016090  lea     rdx, [rbp+57h+var_58]
0x180016094  mov     rax, [rax+18h]
0x180016098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001609d  cmp     r15d, 7FFFFFFFh
0x1800160a4  ja      loc_180016209
0x1800160aa  movsxd  rbx, r15d
0x1800160ad  inc     rbx
0x1800160b0  mov     eax, 80000000h
0x1800160b5  add     rax, rbx
0x1800160b8  mov     ecx, 0FFFFFFFFh
0x1800160bd  cmp     rax, rcx
0x1800160c0  ja      loc_180016209
0x1800160c6  lea     rdx, [rbp+57h+var_C8]
0x1800160ca  mov     rcx, r14
0x1800160cd  call    ?_GetTrailer@PDFDocumentWriter@PCLmWriter@@AEAAXPEAV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@@Z; PCLmWriter::PDFDocumentWriter::_GetTrailer(std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>> *)
0x1800160d2  mov     rcx, [r14]
0x1800160d5  mov     rax, [rcx]
0x1800160d8  mov     r8d, ebx
0x1800160db  mov     [rsp+130h+var_110], r12d
0x1800160e0  xor     r9d, r9d
0x1800160e3  lea     rdx, [rsp+130h+var_F8]
0x1800160e8  mov     rax, [rax+10h]
0x1800160ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160f1  mov     rbx, rax
0x1800160f4  lea     rdx, aSize; "/Size"
0x1800160fb  lea     rcx, [rbp+57h+var_80]
0x1800160ff  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016104  nop
0x180016105  lea     rdx, [rbp+57h+var_80]
0x180016109  lea     rcx, [rbp+57h+var_C8]
0x18001610d  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180016112  mov     rcx, [rbx]
0x180016115  mov     rdx, [rbx+8]
0x180016119  mov     [rbx], r12
0x18001611c  mov     [rbx+8], r12
0x180016120  mov     [rax], rcx
0x180016123  mov     rcx, [rax+8]; this
0x180016127  mov     [rax+8], rdx
0x18001612b  test    rcx, rcx
0x18001612e  jz      short loc_180016136
0x180016130  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016135  nop
0x180016136  lea     rcx, [rbp+57h+var_80]
0x18001613a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001613f  nop
0x180016140  mov     rcx, [rsp+130h+var_F8+8]; this
0x180016145  test    rcx, rcx
0x180016148  jz      short loc_18001614F
0x18001614a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001614f  mov     rcx, [r14]
0x180016152  mov     rax, [rcx]
0x180016155  mov     [rsp+130h+var_110], r12d
0x18001615a  xor     r9d, r9d
0x18001615d  lea     r8, [rbp+57h+var_C8]
0x180016161  lea     rdx, [rsp+130h+var_F8]
0x180016166  mov     rax, [rax+28h]
0x18001616a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001616f  mov     rdx, rax
0x180016172  lea     rcx, [rbp+57h+var_B0]
0x180016176  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x18001617b  mov     rcx, [rsp+130h+var_F8+8]; this
0x180016180  test    rcx, rcx
0x180016183  jz      short loc_18001618A
0x180016185  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001618a  mov     r9, [rbp+57h+var_B0]
0x18001618e  mov     rax, [r9]
0x180016191  mov     r8, [rax+20h]
0x180016195  mov     rdx, rdi
0x180016198  lea     rcx, [rsp+130h+var_F8]
0x18001619d  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x1800161a2  mov     rdx, rax
0x1800161a5  mov     rcx, r9
0x1800161a8  mov     rax, r8
0x1800161ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161b0  nop
0x1800161b1  mov     rcx, [rbp+57h+var_B0+8]; this
0x1800161b5  test    rcx, rcx
0x1800161b8  jz      short loc_1800161C0
0x1800161ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800161bf  nop
0x1800161c0  lea     rdx, [rbp+57h+var_C8]
0x1800161c4  lea     rcx, [rbp+57h+var_C8]
0x1800161c8  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x1800161cd  nop
0x1800161ce  mov     rcx, [rsp+130h+var_E8]
0x1800161d3  test    rcx, rcx
0x1800161d6  jz      short loc_1800161E9
0x1800161d8  mov     rdx, [rsp+130h+var_D8]
0x1800161dd  sub     rdx, rcx
0x1800161e0  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800161e4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800161e9  mov     rcx, [rbp+57h+var_48]
0x1800161ed  xor     rcx, rsp; StackCookie
0x1800161f0  call    __security_check_cookie
0x1800161f5  add     rsp, 0F8h
0x1800161fc  pop     r15
0x1800161fe  pop     r14
0x180016200  pop     r13
0x180016202  pop     r12
0x180016204  pop     rdi
0x180016205  pop     rsi
0x180016206  pop     rbx
0x180016207  pop     rbp
0x180016208  retn
0x180016209  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@PCLmWriter@@@PCLmWriter@@SAXXZ; PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow(void)
```
