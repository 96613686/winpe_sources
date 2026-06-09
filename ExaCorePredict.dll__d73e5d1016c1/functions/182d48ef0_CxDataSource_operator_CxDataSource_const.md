# CxDataSource::operator==(CxDataSource const &)

- ea: `0x182d48ef0`
- end: `0x182d49258`
- name: `??8CxDataSource@@QEBA_NAEBV0@@Z`
- size: `872`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x1815b2170`
- `0x1815c1d30`
- `0x182d48e80`

## callees

- `0x1815adbd0`
- `0x1815cd850`
- `0x182d47eb0`
- `0x182d480d0`
- `0x182d482f0`
- `0x182d48510`
- `0x182d48ef0`
- `0x1830501a0`
- `0x1830eae30`
- `0x1831057e0`
- `0x183105cd0`

## import_xrefs

- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x182d4903b`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x182d491dc`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x182d4903b`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x182d491dc`
- `MSVCP140!?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A` at `0x182d48fd3`
- `MSVCP140!?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A` at `0x182d49174`

## string_xrefs

- `0x182d48f9c`: `m_llNumRowsOrBlocksPerRead`
- `0x182d4910e`: `m_svOrigColumnNamesToRead`
- `0x182d49137`: `m_svNewColumnNamesToRead`
- `0x182d48f95`: `rObj.m_llNumRowsOrBlocksPerRead`
- `0x182d49107`: `rObj.m_svOrigColumnNamesToRead`
- `0x182d49130`: `rObj.m_svNewColumnNamesToRead`

## pseudocode

```c
char __fastcall CxDataSource::operator==(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  char v5; // bl
  char v6; // di
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  char v13; // bl
  char v14; // bl
  char v15; // bl
  char v16; // bl
  char v17; // bl
  char v18; // bl
  char v19; // di
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax

  v4 = TestScalarEquality<enum CxDataSourceType>(a1 + 16, a2 + 16, "m_dataSourceType", "rObj.m_dataSourceType") & 1;
  LOBYTE(v4) = TestScalarEquality<enum CxDataSplitType>(a1 + 20, a2 + 20, "m_dataSplitType", "rObj.m_dataSplitType")
             & v4;
  LOBYTE(v4) = TestScalarEquality<__int64>(a1 + 24, a2 + 24, "m_llStartRowOrBlock", "rObj.m_llStartRowOrBlock") & v4;
  LOBYTE(v4) = TestScalarEquality<__int64>(a1 + 32, a2 + 32, "m_llNumRowsOrBlocks", "rObj.m_llNumRowsOrBlocks") & v4;
  v5 = TestScalarEquality<__int64>(a1 + 40, a2 + 40, "m_llNumRowsOrBlocksPerRead", "rObj.m_llNumRowsOrBlocksPerRead")
     & v4;
  if ( (unsigned __int8)StringUIntMapMap::operator==(a1 + 88, a2 + 88) )
  {
    v6 = 1;
  }
  else
  {
    if ( GetDisplayFlag() )
    {
      v7 = std::operator<<<std::char_traits<char>>(*(_QWORD *)&std::cout, "Testing equality of ");
      v8 = std::operator<<<std::char_traits<char>>(v7, "StringUIntMapMap");
      v9 = std::operator<<<std::char_traits<char>>(v8, " ");
      v10 = std::operator<<<std::char_traits<char>>(v9, "m_factorInfoMapMap");
      v11 = std::operator<<<std::char_traits<char>>(v10, " and ");
      v12 = std::operator<<<std::char_traits<char>>(v11, "rObj.m_factorInfoMapMap");
      std::ostream::operator<<(v12, std::endl<char,std::char_traits<char>>);
      ULongLongUIntMap::Display(a1 + 88, "m_factorInfoMapMap", 1);
      ULongLongUIntMap::Display(a2 + 88, "rObj.m_factorInfoMapMap", 1);
    }
    v6 = 0;
  }
  v13 = v6
      & TestVarEquality(
          (const struct Var *)(a1 + 96),
          (const struct Var *)(a2 + 96),
          "m_svDontFactorizeTheseColumns",
          "rObj.m_svDontFactorizeTheseColumns",
          0.000001)
      & v5;
  v14 = TestScalarEquality<enum CxVarType>(a1 + 104, a2 + 104, "m_defaultColumnVarType", "rObj.m_defaultColumnVarType")
      & v13;
  v15 = TestScalarEquality<enum CxVarType>(
          a1 + 108,
          a2 + 108,
          "m_defaultNumericVarType",
          "rObj.m_defaultNumericVarType")
      & v14;
  v16 = TestVarEquality(
          (const struct Var *)(a1 + 112),
          (const struct Var *)(a2 + 112),
          "m_svColumnsWithOnlyMissingsDetected",
          "rObj.m_svColumnsWithOnlyMissingsDetected",
          0.000001)
      & v15;
  v17 = TestVarEquality(
          (const struct Var *)(a1 + 120),
          (const struct Var *)(a2 + 120),
          "m_svOrigColumnNamesToRead",
          "rObj.m_svOrigColumnNamesToRead",
          0.000001)
      & v16;
  v18 = TestVarEquality(
          (const struct Var *)(a1 + 128),
          (const struct Var *)(a2 + 128),
          "m_svNewColumnNamesToRead",
          "rObj.m_svNewColumnNamesToRead",
          0.000001)
      & v17;
  if ( (unsigned __int8)StringUIntMapMap::operator==(a1 + 136, a2 + 136) )
  {
    v19 = 1;
  }
  else
  {
    if ( GetDisplayFlag() )
    {
      v20 = std::operator<<<std::char_traits<char>>(*(_QWORD *)&std::cout, "Testing equality of ");
      v21 = std::operator<<<std::char_traits<char>>(v20, "StringUIntMapMap");
      v22 = std::operator<<<std::char_traits<char>>(v21, " ");
      v23 = std::operator<<<std::char_traits<char>>(v22, "m_newFactorInfoMapMap");
      v24 = std::operator<<<std::char_traits<char>>(v23, " and ");
      v25 = std::operator<<<std::char_traits<char>>(v24, "rObj.m_newFactorInfoMapMap");
      std::ostream::operator<<(v25, std::endl<char,std::char_traits<char>>);
      ULongLongUIntMap::Display(a1 + 136, "m_newFactorInfoMapMap", 1);
      ULongLongUIntMap::Display(a2 + 136, "rObj.m_newFactorInfoMapMap", 1);
    }
    v19 = 0;
  }
  return v18
       & v19
       & TestScalarEquality<enum CxFileSystemType>(a1 + 200, a2 + 200, "m_fileSysType", "rObj.m_fileSysType");
}

```

## disassembly

```asm
0x182d48ef0  mov     [rsp+arg_0], rbx
0x182d48ef5  mov     [rsp+arg_8], rbp
0x182d48efa  mov     [rsp+arg_10], rsi
0x182d48eff  mov     [rsp+arg_18], rdi
0x182d48f04  push    r14
0x182d48f06  sub     rsp, 40h
0x182d48f0a  mov     rsi, rdx
0x182d48f0d  movaps  [rsp+48h+var_18], xmm6
0x182d48f12  mov     rbp, rcx
0x182d48f15  lea     r9, aRobjMDatasourc; "rObj.m_dataSourceType"
0x182d48f1c  add     rdx, 10h
0x182d48f20  lea     r8, aMDatasourcetyp; "m_dataSourceType"
0x182d48f27  add     rcx, 10h
0x182d48f2b  call    ??$TestScalarEquality@W4CxDataSourceType@@@@YA_NAEBW4CxDataSourceType@@0PEBD1@Z; TestScalarEquality<CxDataSourceType>(CxDataSourceType const &,CxDataSourceType const &,char const *,char const *)
0x182d48f30  movzx   ebx, al
0x182d48f33  lea     rdx, [rsi+14h]
0x182d48f37  lea     rcx, [rbp+14h]
0x182d48f3b  and     bl, 1
0x182d48f3e  lea     r9, aRobjMDatasplit; "rObj.m_dataSplitType"
0x182d48f45  lea     r8, aMDatasplittype; "m_dataSplitType"
0x182d48f4c  call    ??$TestScalarEquality@W4CxDataSplitType@@@@YA_NAEBW4CxDataSplitType@@0PEBD1@Z; TestScalarEquality<CxDataSplitType>(CxDataSplitType const &,CxDataSplitType const &,char const *,char const *)
0x182d48f51  lea     rdx, [rsi+18h]
0x182d48f55  and     bl, al
0x182d48f57  lea     rcx, [rbp+18h]
0x182d48f5b  lea     r9, aRobjMLlstartro; "rObj.m_llStartRowOrBlock"
0x182d48f62  lea     r8, aMLlstartroworb; "m_llStartRowOrBlock"
0x182d48f69  call    ??$TestScalarEquality@_J@@YA_NAEB_J0PEBD1@Z; TestScalarEquality<__int64>(__int64 const &,__int64 const &,char const *,char const *)
0x182d48f6e  lea     rdx, [rsi+20h]
0x182d48f72  and     bl, al
0x182d48f74  lea     rcx, [rbp+20h]
0x182d48f78  lea     r9, aRobjMLlnumrows; "rObj.m_llNumRowsOrBlocks"
0x182d48f7f  lea     r8, aMLlnumrowsorbl; "m_llNumRowsOrBlocks"
0x182d48f86  call    ??$TestScalarEquality@_J@@YA_NAEB_J0PEBD1@Z; TestScalarEquality<__int64>(__int64 const &,__int64 const &,char const *,char const *)
0x182d48f8b  lea     rdx, [rsi+28h]
0x182d48f8f  and     bl, al
0x182d48f91  lea     rcx, [rbp+28h]
0x182d48f95  lea     r9, aRobjMLlnumrows_0; "rObj.m_llNumRowsOrBlocksPerRead"
0x182d48f9c  lea     r8, aMLlnumrowsorbl_0; "m_llNumRowsOrBlocksPerRead"
0x182d48fa3  call    ??$TestScalarEquality@_J@@YA_NAEB_J0PEBD1@Z; TestScalarEquality<__int64>(__int64 const &,__int64 const &,char const *,char const *)
0x182d48fa8  lea     rdi, [rsi+58h]
0x182d48fac  and     bl, al
0x182d48fae  mov     rdx, rdi
0x182d48fb1  lea     rcx, [rbp+58h]
0x182d48fb5  call    ??8StringUIntMapMap@@QEBA_NAEBV0@@Z; StringUIntMapMap::operator==(StringUIntMapMap const &)
0x182d48fba  test    al, al
0x182d48fbc  jz      short loc_182D48FC6
0x182d48fbe  mov     dil, 1
0x182d48fc1  jmp     loc_182D4906E
0x182d48fc6  call    ?GetDisplayFlag@@YA_NXZ; GetDisplayFlag(void)
0x182d48fcb  cmp     al, 1
0x182d48fcd  jnz     loc_182D4906C
0x182d48fd3  mov     rcx, cs:__imp_?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A; std::ostream std::cout
0x182d48fda  lea     rdx, aTestingEqualit_0; "Testing equality of "
0x182d48fe1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d48fe6  mov     rcx, rax
0x182d48fe9  lea     rdx, aStringuintmapm; "StringUIntMapMap"
0x182d48ff0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d48ff5  mov     rcx, rax
0x182d48ff8  lea     rdx, asc_18330FE50; " "
0x182d48fff  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d49004  mov     rcx, rax
0x182d49007  lea     rdx, aMFactorinfomap; "m_factorInfoMapMap"
0x182d4900e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d49013  mov     rcx, rax
0x182d49016  lea     rdx, aAnd_1; " and "
0x182d4901d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d49022  mov     rcx, rax
0x182d49025  lea     rdx, aRobjMFactorinf; "rObj.m_factorInfoMapMap"
0x182d4902c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d49031  mov     rcx, rax
0x182d49034  lea     rdx, ??$endl@DU?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@@Z; std::endl<char,std::char_traits<char>>(std::ostream &)
0x182d4903b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::ostream::operator<<(std::ostream & (*)(std::ostream &))
0x182d49041  mov     r8d, 1
0x182d49047  lea     rdx, aMFactorinfomap; "m_factorInfoMapMap"
0x182d4904e  lea     rcx, [rbp+58h]
0x182d49052  call    ?Display@ULongLongUIntMap@@QEBAXPEBDW4CxDisplayOptions@@@Z; ULongLongUIntMap::Display(char const *,CxDisplayOptions)
0x182d49057  mov     r8d, 1
0x182d4905d  lea     rdx, aRobjMFactorinf; "rObj.m_factorInfoMapMap"
0x182d49064  mov     rcx, rdi
0x182d49067  call    ?Display@ULongLongUIntMap@@QEBAXPEBDW4CxDisplayOptions@@@Z; ULongLongUIntMap::Display(char const *,CxDisplayOptions)
0x182d4906c  xor     edi, edi
0x182d4906e  movsd   xmm6, cs:__real@3eb0c6f7a0b5ed8d
0x182d49076  lea     rdx, [rsi+60h]; struct Var *
0x182d4907a  lea     rcx, [rbp+60h]; struct Var *
0x182d4907e  movsd   [rsp+48h+var_28], xmm6; double
0x182d49084  lea     r9, aRobjMSvdontfac; "rObj.m_svDontFactorizeTheseColumns"
0x182d4908b  lea     r8, aMSvdontfactori; "m_svDontFactorizeTheseColumns"
0x182d49092  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x182d49097  and     al, dil
0x182d4909a  lea     rdx, [rsi+68h]
0x182d4909e  lea     rcx, [rbp+68h]
0x182d490a2  and     bl, al
0x182d490a4  lea     r9, aRobjMDefaultco; "rObj.m_defaultColumnVarType"
0x182d490ab  lea     r8, aMDefaultcolumn; "m_defaultColumnVarType"
0x182d490b2  call    ??$TestScalarEquality@W4CxVarType@@@@YA_NAEBW4CxVarType@@0PEBD1@Z; TestScalarEquality<CxVarType>(CxVarType const &,CxVarType const &,char const *,char const *)
0x182d490b7  lea     rdx, [rsi+6Ch]
0x182d490bb  and     bl, al
0x182d490bd  lea     rcx, [rbp+6Ch]
0x182d490c1  lea     r9, aRobjMDefaultnu; "rObj.m_defaultNumericVarType"
0x182d490c8  lea     r8, aMDefaultnumeri; "m_defaultNumericVarType"
0x182d490cf  call    ??$TestScalarEquality@W4CxVarType@@@@YA_NAEBW4CxVarType@@0PEBD1@Z; TestScalarEquality<CxVarType>(CxVarType const &,CxVarType const &,char const *,char const *)
0x182d490d4  lea     rdx, [rsi+70h]; struct Var *
0x182d490d8  movsd   [rsp+48h+var_28], xmm6; double
0x182d490de  lea     rcx, [rbp+70h]; struct Var *
0x182d490e2  and     bl, al
0x182d490e4  lea     r9, aRobjMSvcolumns; "rObj.m_svColumnsWithOnlyMissingsDetecte"...
0x182d490eb  lea     r8, aMSvcolumnswith; "m_svColumnsWithOnlyMissingsDetected"
0x182d490f2  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x182d490f7  lea     rdx, [rsi+78h]; struct Var *
0x182d490fb  movsd   [rsp+48h+var_28], xmm6; double
0x182d49101  lea     rcx, [rbp+78h]; struct Var *
0x182d49105  and     bl, al
0x182d49107  lea     r9, aRobjMSvorigcol; "rObj.m_svOrigColumnNamesToRead"
0x182d4910e  lea     r8, aMSvorigcolumnn; "m_svOrigColumnNamesToRead"
0x182d49115  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x182d4911a  lea     rdx, [rsi+80h]; struct Var *
0x182d49121  movsd   [rsp+48h+var_28], xmm6; double
0x182d49127  lea     rcx, [rbp+80h]; struct Var *
0x182d4912e  and     bl, al
0x182d49130  lea     r9, aRobjMSvnewcolu; "rObj.m_svNewColumnNamesToRead"
0x182d49137  lea     r8, aMSvnewcolumnna; "m_svNewColumnNamesToRead"
0x182d4913e  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x182d49143  lea     rdi, [rsi+88h]
0x182d4914a  and     bl, al
0x182d4914c  mov     rdx, rdi
0x182d4914f  lea     rcx, [rbp+88h]
0x182d49156  call    ??8StringUIntMapMap@@QEBA_NAEBV0@@Z; StringUIntMapMap::operator==(StringUIntMapMap const &)
0x182d4915b  test    al, al
0x182d4915d  jz      short loc_182D49167
0x182d4915f  mov     dil, 1
0x182d49162  jmp     loc_182D49212
0x182d49167  call    ?GetDisplayFlag@@YA_NXZ; GetDisplayFlag(void)
0x182d4916c  cmp     al, 1
0x182d4916e  jnz     loc_182D49210
0x182d49174  mov     rcx, cs:__imp_?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A; std::ostream std::cout
0x182d4917b  lea     rdx, aTestingEqualit_0; "Testing equality of "
0x182d49182  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d49187  mov     rcx, rax
0x182d4918a  lea     rdx, aStringuintmapm; "StringUIntMapMap"
0x182d49191  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d49196  mov     rcx, rax
0x182d49199  lea     rdx, asc_18330FE50; " "
0x182d491a0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d491a5  mov     rcx, rax
0x182d491a8  lea     rdx, aMNewfactorinfo; "m_newFactorInfoMapMap"
0x182d491af  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d491b4  mov     rcx, rax
0x182d491b7  lea     rdx, aAnd_1; " and "
0x182d491be  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d491c3  mov     rcx, rax
0x182d491c6  lea     rdx, aRobjMNewfactor; "rObj.m_newFactorInfoMapMap"
0x182d491cd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x182d491d2  mov     rcx, rax
0x182d491d5  lea     rdx, ??$endl@DU?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@@Z; std::endl<char,std::char_traits<char>>(std::ostream &)
0x182d491dc  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::ostream::operator<<(std::ostream & (*)(std::ostream &))
0x182d491e2  mov     r8d, 1
0x182d491e8  lea     rdx, aMNewfactorinfo; "m_newFactorInfoMapMap"
0x182d491ef  lea     rcx, [rbp+88h]
0x182d491f6  call    ?Display@ULongLongUIntMap@@QEBAXPEBDW4CxDisplayOptions@@@Z; ULongLongUIntMap::Display(char const *,CxDisplayOptions)
0x182d491fb  mov     r8d, 1
0x182d49201  lea     rdx, aRobjMNewfactor; "rObj.m_newFactorInfoMapMap"
0x182d49208  mov     rcx, rdi
0x182d4920b  call    ?Display@ULongLongUIntMap@@QEBAXPEBDW4CxDisplayOptions@@@Z; ULongLongUIntMap::Display(char const *,CxDisplayOptions)
0x182d49210  xor     edi, edi
0x182d49212  lea     rdx, [rsi+0C8h]
0x182d49219  lea     rcx, [rbp+0C8h]
0x182d49220  lea     r9, aRobjMFilesysty; "rObj.m_fileSysType"
0x182d49227  lea     r8, aMFilesystype; "m_fileSysType"
0x182d4922e  call    ??$TestScalarEquality@W4CxFileSystemType@@@@YA_NAEBW4CxFileSystemType@@0PEBD1@Z; TestScalarEquality<CxFileSystemType>(CxFileSystemType const &,CxFileSystemType const &,char const *,char const *)
0x182d49233  mov     rbp, [rsp+48h+arg_8]
0x182d49238  and     al, dil
0x182d4923b  mov     rsi, [rsp+48h+arg_10]
0x182d49240  and     al, bl
0x182d49242  mov     rbx, [rsp+48h+arg_0]
0x182d49247  mov     rdi, [rsp+48h+arg_18]
0x182d4924c  movaps  xmm6, [rsp+48h+var_18]
0x182d49251  add     rsp, 40h
0x182d49255  pop     r14
0x182d49257  retn
```
