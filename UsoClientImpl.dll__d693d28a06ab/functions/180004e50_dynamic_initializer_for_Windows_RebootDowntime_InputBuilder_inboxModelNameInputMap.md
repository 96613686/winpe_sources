# _dynamic_initializer_for__Windows::RebootDowntime::InputBuilder::inboxModelNameInputMap__

- ea: `0x180004e50`
- end: `0x1800052f9`
- name: `_dynamic_initializer_for__Windows::RebootDowntime::InputBuilder::inboxModelNameInputMap__`
- size: `1193`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004e50`
- `0x180009380`
- `0x18000a1f8`
- `0x180019208`
- `0x1800338a4`
- `0x180033b00`
- `0x1800344b8`
- `0x180053604`
- `0x180054a40`
- `0x180054b0c`
- `0x180056568`
- `0x1800569e8`

## string_xrefs

- `0x180004eba`: `numDriverUpdates`
- `0x180005091`: `numDriverUpdates`
- `0x180004eea`: `numOtherUpdates`
- `0x1800050b4`: `numOtherUpdates`
- `0x180004ffa`: `InstallFlowType`
- `0x180004f72`: `totalOtherUpdatesSizeInBytes`
- `0x18000511e`: `totalOtherUpdatesSizeInBytes`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
int dynamic_initializer_for__Windows::RebootDowntime::InputBuilder::inboxModelNameInputMap__()
{
  _QWORD *v0; // rax
  __int64 v1; // rcx
  char *v2; // rbx
  _OWORD *v4; // [rsp+28h] [rbp-E0h] BYREF
  _BYTE v5[40]; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v6[4]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v7[24]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v8[24]; // [rsp+90h] [rbp-78h] BYREF
  _OWORD v9[2]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v10[2]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v11[2]; // [rsp+E8h] [rbp-20h] BYREF
  _OWORD v12[2]; // [rsp+108h] [rbp+0h] BYREF
  _OWORD v13[2]; // [rsp+128h] [rbp+20h] BYREF
  _OWORD v14[2]; // [rsp+148h] [rbp+40h] BYREF
  _OWORD v15[2]; // [rsp+168h] [rbp+60h] BYREF
  _OWORD v16[2]; // [rsp+188h] [rbp+80h] BYREF
  _OWORD v17[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  _OWORD v18[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  _OWORD v19[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  _OWORD v20[2]; // [rsp+208h] [rbp+100h] BYREF
  _OWORD v21[2]; // [rsp+228h] [rbp+120h] BYREF
  _OWORD v22[2]; // [rsp+248h] [rbp+140h] BYREF
  _OWORD v23[2]; // [rsp+268h] [rbp+160h] BYREF
  _BYTE v24[32]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v25[24]; // [rsp+2A8h] [rbp+1A0h] BYREF
  _BYTE v26[32]; // [rsp+2C0h] [rbp+1B8h] BYREF
  _BYTE v27[24]; // [rsp+2E0h] [rbp+1D8h] BYREF
  char v28; // [rsp+2F8h] [rbp+1F0h] BYREF

  memset(v6, 0, sizeof(v6));
  std::wstring::_Construct<1,wchar_t const *>(v6);
  memset(v16, 0, sizeof(v16));
  std::wstring::_Construct<1,wchar_t const *>(v16);
  memset(v17, 0, sizeof(v17));
  std::wstring::_Construct<1,wchar_t const *>(v17);
  memset(v18, 0, sizeof(v18));
  std::wstring::_Construct<1,wchar_t const *>(v18);
  memset(v19, 0, sizeof(v19));
  std::wstring::_Construct<1,wchar_t const *>(v19);
  memset(v20, 0, sizeof(v20));
  std::wstring::_Construct<1,wchar_t const *>(v20);
  memset(v21, 0, sizeof(v21));
  std::wstring::_Construct<1,wchar_t const *>(v21);
  memset(v22, 0, sizeof(v22));
  std::wstring::_Construct<1,wchar_t const *>(v22);
  memset(v23, 0, sizeof(v23));
  std::wstring::_Construct<1,wchar_t const *>(v23);
  v4 = v16;
  *(_QWORD *)v5 = v24;
  std::vector<std::wstring>::vector<std::wstring>(v8, &v4);
  std::wstring::wstring(v24, v6);
  std::vector<std::wstring>::vector<std::wstring>(v25, v8);
  memset(&v5[8], 0, 32);
  std::wstring::_Construct<1,wchar_t const *>(&v5[8]);
  memset(v9, 0, sizeof(v9));
  std::wstring::_Construct<1,wchar_t const *>(v9);
  memset(v10, 0, sizeof(v10));
  std::wstring::_Construct<1,wchar_t const *>(v10);
  memset(v11, 0, sizeof(v11));
  std::wstring::_Construct<1,wchar_t const *>(v11);
  memset(v12, 0, sizeof(v12));
  std::wstring::_Construct<1,wchar_t const *>(v12);
  memset(v13, 0, sizeof(v13));
  std::wstring::_Construct<1,wchar_t const *>(v13);
  memset(v14, 0, sizeof(v14));
  std::wstring::_Construct<1,wchar_t const *>(v14);
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,wchar_t const *>(v15);
  v4 = v9;
  *(_QWORD *)v5 = v16;
  std::vector<std::wstring>::vector<std::wstring>(v7, &v4);
  std::wstring::wstring(v26, &v5[8]);
  std::vector<std::wstring>::vector<std::wstring>(v27, v7);
  Windows::RebootDowntime::InputBuilder::inboxModelNameInputMap = 0;
  qword_18009FED8 = 0;
  qword_18009FEE0 = 0;
  v0 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(72);
  *v0 = v0;
  v0[1] = v0;
  qword_18009FED8 = (__int64)v0;
  qword_18009FEE8 = 0;
  xmmword_18009FEF0 = 0;
  qword_18009FF00 = 7;
  qword_18009FF08 = 8;
  Windows::RebootDowntime::InputBuilder::inboxModelNameInputMap = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,DecisionOperator>>>>>>::_Assign_grow(
    &qword_18009FEE8,
    16,
    v0);
  v2 = v24;
  do
  {
    std::_Hash<std::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::emplace<std::pair<std::wstring const,std::vector<std::wstring>> const &>(
      v1,
      &v4,
      v2);
    v2 += 56;
  }
  while ( v2 != &v28 );
  `eh vector destructor iterator'(
    v24,
    0x38u,
    2u,
    std::pair<std::wstring const,std::vector<std::wstring>>::~pair<std::wstring const,std::vector<std::wstring>>);
  std::vector<std::wstring>::_Tidy(v7);
  `eh vector destructor iterator'(v9, 0x20u, 7u, std::wstring::~wstring);
  std::wstring::~wstring(&v5[8]);
  std::vector<std::wstring>::_Tidy(v8);
  `eh vector destructor iterator'(v16, 0x20u, 8u, std::wstring::~wstring);
  std::wstring::~wstring(v6);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::RebootDowntime::InputBuilder::inboxModelNameInputMap__);
}

```

## disassembly

```asm
0x180004e50  mov     rax, rsp
0x180004e53  mov     [rax+8], rbx
0x180004e57  mov     [rax+10h], rsi
0x180004e5b  mov     [rax+18h], rdi
0x180004e5f  push    rbp
0x180004e60  push    r14
0x180004e62  push    r15
0x180004e64  lea     rbp, [rax-208h]
0x180004e6b  sub     rsp, 2F0h
0x180004e72  xorps   xmm0, xmm0
0x180004e75  movups  [rsp+300h+var_2B8+8], xmm0
0x180004e7a  xorps   xmm1, xmm1
0x180004e7d  movdqu  [rsp+300h+var_2A8+8], xmm1
0x180004e83  mov     r14d, 16h
0x180004e89  mov     r8d, r14d
0x180004e8c  lea     rdx, aRebootdowntime; "RebootDowntimeEstimate"
0x180004e93  lea     rcx, [rsp+300h+var_2B8+8]
0x180004e98  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004e9d  nop
0x180004e9e  xorps   xmm0, xmm0
0x180004ea1  movups  [rbp+200h+var_180], xmm0
0x180004ea8  xorps   xmm1, xmm1
0x180004eab  movdqa  [rbp+200h+var_170], xmm1
0x180004eb3  lea     r15d, [r14-6]
0x180004eb7  mov     r8d, r15d
0x180004eba  lea     rdx, aNumdriverupdat; "numDriverUpdates"
0x180004ec1  lea     rcx, [rbp+200h+var_180]
0x180004ec8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004ecd  nop
0x180004ece  xorps   xmm0, xmm0
0x180004ed1  movups  [rbp+200h+var_160], xmm0
0x180004ed8  xorps   xmm1, xmm1
0x180004edb  movdqa  [rbp+200h+var_150], xmm1
0x180004ee3  lea     edi, [r14-7]
0x180004ee7  mov     r8d, edi
0x180004eea  lea     rdx, aNumotherupdate; "numOtherUpdates"
0x180004ef1  lea     rcx, [rbp+200h+var_160]
0x180004ef8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004efd  nop
0x180004efe  xorps   xmm0, xmm0
0x180004f01  movups  [rbp+200h+var_140], xmm0
0x180004f08  xorps   xmm1, xmm1
0x180004f0b  movdqa  [rbp+200h+var_130], xmm1
0x180004f13  lea     r8d, [r14-3]
0x180004f17  lea     rdx, aTotallcusizein; "totalLCUSizeInBytes"
0x180004f1e  lea     rcx, [rbp+200h+var_140]
0x180004f25  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004f2a  nop
0x180004f2b  xorps   xmm0, xmm0
0x180004f2e  movups  [rbp+200h+var_120], xmm0
0x180004f35  xorps   xmm1, xmm1
0x180004f38  movdqa  [rbp+200h+var_110], xmm1
0x180004f40  mov     r8d, r14d
0x180004f43  lea     rdx, aTotaldriversiz; "totalDriverSizeInBytes"
0x180004f4a  lea     rcx, [rbp+200h+var_120]
0x180004f51  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004f56  nop
0x180004f57  xorps   xmm0, xmm0
0x180004f5a  movups  [rbp+200h+var_100], xmm0
0x180004f61  xorps   xmm1, xmm1
0x180004f64  movdqa  [rbp+200h+var_F0], xmm1
0x180004f6c  lea     ebx, [rdi+0Dh]
0x180004f6f  mov     r8d, ebx
0x180004f72  lea     rdx, aTotalotherupda; "totalOtherUpdatesSizeInBytes"
0x180004f79  lea     rcx, [rbp+200h+var_100]
0x180004f80  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004f85  nop
0x180004f86  xorps   xmm0, xmm0
0x180004f89  movups  [rbp+200h+var_E0], xmm0
0x180004f90  xorps   xmm1, xmm1
0x180004f93  movdqa  [rbp+200h+var_D0], xmm1
0x180004f9b  lea     esi, [rdi-5]
0x180004f9e  mov     r8d, esi
0x180004fa1  lea     rdx, aIsaconline; "isACOnline"
0x180004fa8  lea     rcx, [rbp+200h+var_E0]
0x180004faf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004fb4  nop
0x180004fb5  xorps   xmm0, xmm0
0x180004fb8  movups  [rbp+200h+var_C0], xmm0
0x180004fbf  xorps   xmm1, xmm1
0x180004fc2  movdqa  [rbp+200h+var_B0], xmm1
0x180004fca  lea     r8d, [r14-10h]
0x180004fce  lea     rdx, aHasekb; "hasEKB"
0x180004fd5  lea     rcx, [rbp+200h+var_C0]
0x180004fdc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004fe1  nop
0x180004fe2  xorps   xmm0, xmm0
0x180004fe5  movups  [rbp+200h+var_A0], xmm0
0x180004fec  xorps   xmm1, xmm1
0x180004fef  movdqa  [rbp+200h+var_90], xmm1
0x180004ff7  mov     r8d, edi
0x180004ffa  lea     rdx, aInstallflowtyp; "InstallFlowType"
0x180005001  lea     rcx, [rbp+200h+var_A0]
0x180005008  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000500d  nop
0x18000500e  lea     rax, [rbp+200h+var_180]
0x180005015  mov     [rsp+300h+var_2E0], rax
0x18000501a  lea     rax, [rbp+200h+var_80]
0x180005021  mov     qword ptr [rsp+300h+var_2D8], rax
0x180005026  lea     rdx, [rsp+300h+var_2E0]
0x18000502b  lea     rcx, [rbp+200h+var_278]
0x18000502f  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@AEBV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x180005034  nop
0x180005035  lea     rdx, [rsp+300h+var_2B8+8]
0x18000503a  lea     rcx, [rbp+200h+var_80]
0x180005041  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180005046  nop
0x180005047  lea     rdx, [rbp+200h+var_278]
0x18000504b  lea     rcx, [rbp+200h+var_60]
0x180005052  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180005057  nop
0x180005058  xorps   xmm0, xmm0
0x18000505b  movups  [rsp+300h+var_2D8+8], xmm0
0x180005060  xorps   xmm1, xmm1
0x180005063  movdqu  [rsp+300h+var_2C8+8], xmm1
0x180005069  lea     r8d, [r14-0Ah]
0x18000506d  lea     rdx, aFuinboxmodel; "FUInboxModel"
0x180005074  lea     rcx, [rsp+300h+var_2D8+8]
0x180005079  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000507e  nop
0x18000507f  xorps   xmm0, xmm0
0x180005082  movups  [rbp+200h+var_260], xmm0
0x180005086  xorps   xmm1, xmm1
0x180005089  movdqa  [rbp+200h+var_250], xmm1
0x18000508e  mov     r8d, r15d
0x180005091  lea     rdx, aNumdriverupdat; "numDriverUpdates"
0x180005098  lea     rcx, [rbp+200h+var_260]
0x18000509c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800050a1  nop
0x1800050a2  xorps   xmm0, xmm0
0x1800050a5  movups  [rbp+200h+var_240], xmm0
0x1800050a9  xorps   xmm1, xmm1
0x1800050ac  movdqa  [rbp+200h+var_230], xmm1
0x1800050b1  mov     r8d, edi
0x1800050b4  lea     rdx, aNumotherupdate; "numOtherUpdates"
0x1800050bb  lea     rcx, [rbp+200h+var_240]
0x1800050bf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800050c4  nop
0x1800050c5  xorps   xmm0, xmm0
0x1800050c8  movups  [rbp+200h+var_220], xmm0
0x1800050cc  xorps   xmm1, xmm1
0x1800050cf  movdqa  [rbp+200h+var_210], xmm1
0x1800050d4  lea     r8d, [r14-4]
0x1800050d8  lea     rdx, aTotalfusizeinb; "totalFuSizeInBytes"
0x1800050df  lea     rcx, [rbp+200h+var_220]
0x1800050e3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800050e8  nop
0x1800050e9  xorps   xmm0, xmm0
0x1800050ec  movups  [rbp+200h+var_200], xmm0
0x1800050f0  xorps   xmm1, xmm1
0x1800050f3  movdqa  [rbp+200h+var_1F0], xmm1
0x1800050f8  mov     r8d, r14d
0x1800050fb  lea     rdx, aTotaldriversiz; "totalDriverSizeInBytes"
0x180005102  lea     rcx, [rbp+200h+var_200]
0x180005106  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000510b  nop
0x18000510c  xorps   xmm0, xmm0
0x18000510f  movups  [rbp+200h+var_1E0], xmm0
0x180005113  xorps   xmm1, xmm1
0x180005116  movdqa  [rbp+200h+var_1D0], xmm1
0x18000511b  mov     r8d, ebx
0x18000511e  lea     rdx, aTotalotherupda; "totalOtherUpdatesSizeInBytes"
0x180005125  lea     rcx, [rbp+200h+var_1E0]
0x180005129  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000512e  nop
0x18000512f  xorps   xmm0, xmm0
0x180005132  movups  [rbp+200h+var_1C0], xmm0
0x180005136  xorps   xmm1, xmm1
0x180005139  movdqa  [rbp+200h+var_1B0], xmm1
0x18000513e  lea     r8d, [r14-2]
0x180005142  lea     rdx, aMajorbuilddiff; "majorBuildDifference"
0x180005149  lea     rcx, [rbp+200h+var_1C0]
0x18000514d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005152  nop
0x180005153  xorps   xmm0, xmm0
0x180005156  movups  [rbp+200h+var_1A0], xmm0
0x18000515a  xorps   xmm1, xmm1
0x18000515d  movdqa  [rbp+200h+var_190], xmm1
0x180005162  mov     r8d, esi
0x180005165  lea     rdx, aIsaconline; "isACOnline"
0x18000516c  lea     rcx, [rbp+200h+var_1A0]
0x180005170  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005175  nop
0x180005176  lea     rax, [rbp+200h+var_260]
0x18000517a  mov     [rsp+300h+var_2E0], rax
0x18000517f  lea     rax, [rbp+200h+var_180]
0x180005186  mov     qword ptr [rsp+300h+var_2D8], rax
0x18000518b  lea     rdx, [rsp+300h+var_2E0]
0x180005190  lea     rcx, [rsp+300h+var_290]
0x180005195  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@AEBV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x18000519a  nop
0x18000519b  lea     rdx, [rsp+300h+var_2D8+8]
0x1800051a0  lea     rcx, [rbp+200h+var_48]
0x1800051a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800051ac  nop
0x1800051ad  lea     rdx, [rsp+300h+var_290]
0x1800051b2  lea     rcx, [rbp+200h+var_28]
0x1800051b9  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800051be  nop
0x1800051bf  mov     cs:?inboxModelNameInputMap@InputBuilder@RebootDowntime@Windows@@0V?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@@std@@B, 0; std::unordered_map<std::wstring,std::vector<std::wstring>> const Windows::RebootDowntime::InputBuilder::inboxModelNameInputMap
0x1800051c9  xor     ebx, ebx
0x1800051cb  mov     cs:qword_18009FED8, rbx
0x1800051d2  mov     cs:qword_18009FEE0, rbx
0x1800051d9  lea     ecx, [rdi+39h]
0x1800051dc  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800051e1  mov     [rax], rax
0x1800051e4  mov     [rax+8], rax
0x1800051e8  mov     cs:qword_18009FED8, rax
0x1800051ef  mov     cs:qword_18009FEE8, rbx
0x1800051f6  xorps   xmm0, xmm0
0x1800051f9  movdqa  cs:xmmword_18009FEF0, xmm0
0x180005201  lea     edi, [rsi-3]
0x180005204  mov     cs:qword_18009FF00, rdi
0x18000520b  lea     esi, [rbx+8]
0x18000520e  mov     cs:qword_18009FF08, rsi
0x180005215  mov     cs:?inboxModelNameInputMap@InputBuilder@RebootDowntime@Windows@@0V?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@@std@@B, 3F800000h; std::unordered_map<std::wstring,std::vector<std::wstring>> const Windows::RebootDowntime::InputBuilder::inboxModelNameInputMap
0x18000521f  mov     r8, rax
0x180005222  mov     edx, r15d
0x180005225  lea     rcx, qword_18009FEE8
0x18000522c  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDecisionOperator@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDecisionOperator@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,DecisionOperator>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,DecisionOperator>>>>)
0x180005231  nop
0x180005232  lea     rbx, [rbp+200h+var_80]
0x180005239  mov     r8, rbx
0x18000523c  lea     rdx, [rsp+300h+var_2E0]
0x180005241  call    ??$emplace@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@1@@Z
0x180005246  add     rbx, 38h ; '8'
0x18000524a  lea     rax, [rbp+200h+var_10]
0x180005251  cmp     rbx, rax
0x180005254  jnz     short loc_180005239
0x180005256  lea     r9, ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@QEAA@XZ; void (*)(void *)
0x18000525d  mov     edx, 38h ; '8'; unsigned __int64
0x180005262  lea     r8d, [rdx-36h]; unsigned __int64
0x180005266  lea     rcx, [rbp+200h+var_80]; void *
0x18000526d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180005272  nop
0x180005273  lea     rcx, [rsp+300h+var_290]
0x180005278  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000527d  nop
0x18000527e  lea     r9, ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; void (*)(void *)
0x180005285  mov     r8, rdi; unsigned __int64
0x180005288  mov     ebx, 20h ; ' '
0x18000528d  mov     edx, ebx; unsigned __int64
0x18000528f  lea     rcx, [rbp+200h+var_260]; void *
0x180005293  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180005298  nop
0x180005299  lea     rcx, [rsp+300h+var_2D8+8]; void *
0x18000529e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800052a3  nop
0x1800052a4  lea     rcx, [rbp+200h+var_278]
0x1800052a8  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800052ad  nop
0x1800052ae  lea     r9, ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; void (*)(void *)
0x1800052b5  mov     r8, rsi; unsigned __int64
0x1800052b8  mov     edx, ebx; unsigned __int64
0x1800052ba  lea     rcx, [rbp+200h+var_180]; void *
0x1800052c1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800052c6  nop
0x1800052c7  lea     rcx, [rsp+300h+var_2B8+8]; void *
0x1800052cc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800052d1  lea     rcx, _dynamic_atexit_destructor_for__Windows__RebootDowntime__InputBuilder__inboxModelNameInputMap__
0x1800052d8  lea     r11, [rsp+300h+var_10]
0x1800052e0  mov     rbx, [r11+20h]
0x1800052e4  mov     rsi, [r11+28h]
0x1800052e8  mov     rdi, [r11+30h]
0x1800052ec  mov     rsp, r11
0x1800052ef  pop     r15
0x1800052f1  pop     r14
0x1800052f3  pop     rbp
0x1800052f4  jmp     atexit
```
