# Windows::ChangeTracking::CChangeMonitorResults::GetChangeAt(uint)

- ea: `0x1800e13a0`
- end: `0x1800e1781`
- name: `?GetChangeAt@CChangeMonitorResults@ChangeTracking@Windows@@UEAA?AV?$shared_ptr@USChange@ChangeTracking@Windows@@@std@@I@Z`
- size: `993`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops`

## callees

- `0x180012120`
- `0x180012318`
- `0x18006f6d8`
- `0x1800afb78`
- `0x1800dbbb0`
- `0x1800dfbcc`
- `0x1800e1260`
- `0x1800e13a0`
- `0x1800e2374`
- `0x1801244c0`
- `0x1801244f0`
- `0x18015551c`
- `0x180241010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e1447`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e14d5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e1695`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e16c7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e1743`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e1447`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e14d5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e1695`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e16c7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800e1743`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Windows::ChangeTracking::CChangeMonitorResults::GetChangeAt(__int64 a1, _QWORD *a2, unsigned int a3)
{
  int v5; // eax
  HRESULT v6; // eax
  int v7; // eax
  HRESULT v8; // eax
  std::_Ref_count_base *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  __int64 FileNameFromStream; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  unsigned int pv; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh]
  void *v23; // [rsp+38h] [rbp-C8h] BYREF
  char *v24; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v25; // [rsp+48h] [rbp-B8h]
  _QWORD *v26; // [rsp+50h] [rbp-B0h]
  int v27[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+80h] [rbp-80h] BYREF
  char v31; // [rsp+84h] [rbp-7Ch]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int128 v33; // [rsp+98h] [rbp-68h]
  __int128 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int128 v36; // [rsp+C0h] [rbp-40h]
  __int128 v37; // [rsp+D0h] [rbp-30h]
  __int128 v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  v26 = a2;
  *a2 = 0;
  a2[1] = 0;
  v22 = 1;
  if ( a3 >= *(_DWORD *)(a1 + 48) )
    return a2;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 40LL))(
         *(_QWORD *)(a1 + 8),
         *(_QWORD *)(a1 + 56) + 4LL * a3,
         0,
         0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF86,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
      (const char *)(unsigned int)v5,
      v20);
  pv = 0;
  v6 = IStream_Read(*(IStream **)(a1 + 8), &pv, 4u);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
      (const char *)(unsigned int)v6,
      v20);
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 40LL))(
         *(_QWORD *)(a1 + 8),
         pv,
         0,
         0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8C,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
      (const char *)(unsigned int)v7,
      v20);
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v8 = IStream_Read(*(IStream **)(a1 + 8), &v30, 0x78u);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
      (const char *)(unsigned int)v8,
      v20);
  v23 = operator new(0x108u);
  v9 = (std::_Ref_count_base *)std::_Ref_count_obj2<Windows::ChangeTracking::SChange>::_Ref_count_obj2<Windows::ChangeTracking::SChange>(v23);
  v22 = 3;
  v24 = (char *)v9 + 16;
  v25 = v9;
  std::shared_ptr<Windows::ChangeTracking::SChange>::operator=(a2, &v24);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  v10 = *a2;
  *(_OWORD *)(v10 + 32) = v32;
  *(_OWORD *)(v10 + 48) = v33;
  *(_OWORD *)(v10 + 64) = v34;
  *(_QWORD *)(v10 + 80) = v35;
  v11 = *a2;
  *(_OWORD *)(v11 + 160) = v36;
  *(_OWORD *)(v11 + 176) = v37;
  *(_OWORD *)(v11 + 192) = v38;
  *(_QWORD *)(v11 + 208) = v39;
  *(_BYTE *)(*a2 + 152LL) = v31;
  v12 = v30;
  if ( (v30 & 1) != 0 )
  {
    FileNameFromStream = Windows::ChangeTracking::CChangeMonitorResults::_ReadFileNameFromStream(a1, v27);
    std::wstring::operator=(*a2, FileNameFromStream);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v27);
  }
  else
  {
    if ( (v35 & 0x4000000) == 0 )
      goto LABEL_17;
    v30 |= 1u;
    std::wstring::operator=(*a2, a1 + 16);
  }
  v12 = v30;
LABEL_17:
  if ( (v12 & 4) != 0 )
  {
    v14 = Windows::ChangeTracking::CChangeMonitorResults::_ReadFileNameFromStream(a1, v27);
    std::wstring::operator=(*a2 + 216LL, v14);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v27);
LABEL_21:
    LOBYTE(v12) = v30;
    goto LABEL_22;
  }
  if ( (v39 & 0x4000000) != 0 )
  {
    v30 = v12 | 4;
    std::wstring::operator=(*a2 + 216LL, a1 + 16);
    goto LABEL_21;
  }
LABEL_22:
  if ( (v12 & 2) != 0 )
  {
    v15 = Windows::ChangeTracking::CChangeMonitorResults::_ReadFileNameFromStream(a1, v27);
    std::wstring::operator=(*a2 + 88LL, v15);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v27);
    LOBYTE(v12) = v30;
  }
  if ( (v12 & 8) != 0 )
  {
    LODWORD(v23) = 0;
    v16 = IStream_Read(*(IStream **)(a1 + 8), (void *)(*a2 + 144LL), 8u);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFAF,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
        (const char *)(unsigned int)v16,
        v20);
    v17 = IStream_Read(*(IStream **)(a1 + 8), &v23, 4u);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFB0,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
        (const char *)(unsigned int)v17,
        v20);
    *(_QWORD *)v27 = 0;
    v28 = 0;
    v29 = 0;
    std::vector<Windows::ChangeTracking::SUnchangedRange>::insert(
      *a2 + 120LL,
      &v24,
      *(_QWORD *)(*a2 + 128LL),
      (unsigned int)v23);
    v18 = IStream_Read(*(IStream **)(a1 + 8), *(void **)(*a2 + 120LL), 24 * (_DWORD)v23);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFB3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
        (const char *)(unsigned int)v18,
        (int)v27);
  }
  return a2;
}

```

## disassembly

```asm
0x1800e13a0  push    rbp
0x1800e13a2  push    rbx
0x1800e13a3  push    rdi
0x1800e13a4  lea     rbp, [rsp-10h]
0x1800e13a9  sub     rsp, 110h
0x1800e13b0  mov     rax, cs:__security_cookie
0x1800e13b7  xor     rax, rsp
0x1800e13ba  mov     [rbp+20h+var_20], rax
0x1800e13be  mov     rbx, rdx
0x1800e13c1  mov     rdi, rcx
0x1800e13c4  mov     [rsp+120h+var_D0], rdx
0x1800e13c9  mov     [rsp+120h+var_EC], 0
0x1800e13d1  mov     qword ptr [rdx], 0
0x1800e13d8  mov     qword ptr [rdx+8], 0
0x1800e13e0  mov     [rsp+120h+var_EC], 1
0x1800e13e8  cmp     r8d, [rcx+30h]
0x1800e13ec  jnb     loc_1800E1766
0x1800e13f2  mov     rcx, [rcx+8]
0x1800e13f6  mov     edx, r8d
0x1800e13f9  mov     rax, [rdi+38h]
0x1800e13fd  lea     rdx, [rax+rdx*4]
0x1800e1401  mov     rax, [rcx]
0x1800e1404  xor     r9d, r9d
0x1800e1407  xor     r8d, r8d
0x1800e140a  mov     rax, [rax+28h]
0x1800e140e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1413  mov     rcx, [rbp+28h]; this
0x1800e1417  test    eax, eax
0x1800e1419  jns     short loc_1800E1430
0x1800e141b  mov     r9d, eax; char *
0x1800e141e  lea     r8, aOnecoreuapBase_214; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1425  mov     edx, 0F86h; void *
0x1800e142a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1430  mov     [rsp+120h+pv], 0
0x1800e1438  mov     r8d, 4; cb
0x1800e143e  lea     rdx, [rsp+120h+pv]; pv
0x1800e1443  mov     rcx, [rdi+8]; pstm
0x1800e1447  call    cs:__imp_IStream_Read
0x1800e144d  mov     rcx, [rbp+28h]; this
0x1800e1451  test    eax, eax
0x1800e1453  jns     short loc_1800E146A
0x1800e1455  mov     r9d, eax; char *
0x1800e1458  lea     r8, aOnecoreuapBase_214; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e145f  mov     edx, 0F89h; void *
0x1800e1464  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e146a  mov     edx, [rsp+120h+pv]
0x1800e146e  mov     rcx, [rdi+8]
0x1800e1472  mov     rax, [rcx]
0x1800e1475  xor     r9d, r9d
0x1800e1478  xor     r8d, r8d
0x1800e147b  mov     rax, [rax+28h]
0x1800e147f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1484  mov     rcx, [rbp+28h]; this
0x1800e1488  test    eax, eax
0x1800e148a  jns     short loc_1800E14A1
0x1800e148c  mov     r9d, eax; char *
0x1800e148f  lea     r8, aOnecoreuapBase_214; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1496  mov     edx, 0F8Ch; void *
0x1800e149b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e14a1  xorps   xmm0, xmm0
0x1800e14a4  xor     eax, eax
0x1800e14a6  movups  [rbp+20h+var_98], xmm0
0x1800e14aa  movups  [rbp+20h+var_88], xmm0
0x1800e14ae  movups  [rbp+20h+var_78], xmm0
0x1800e14b2  mov     [rbp+20h+var_68], rax
0x1800e14b6  xorps   xmm1, xmm1
0x1800e14b9  movups  [rbp+20h+var_60], xmm1
0x1800e14bd  movups  [rbp+20h+var_50], xmm1
0x1800e14c1  movups  [rbp+20h+var_40], xmm1
0x1800e14c5  mov     [rbp+20h+var_30], rax
0x1800e14c9  lea     r8d, [rax+78h]; cb
0x1800e14cd  lea     rdx, [rbp+20h+var_A0]; pv
0x1800e14d1  mov     rcx, [rdi+8]; pstm
0x1800e14d5  call    cs:__imp_IStream_Read
0x1800e14db  mov     rcx, [rbp+28h]; this
0x1800e14df  test    eax, eax
0x1800e14e1  jns     short loc_1800E14F8
0x1800e14e3  mov     r9d, eax; char *
0x1800e14e6  lea     r8, aOnecoreuapBase_214; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e14ed  mov     edx, 0F8Fh; void *
0x1800e14f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e14f8  mov     ecx, 108h; Size
0x1800e14fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e1502  mov     [rsp+120h+var_E8], rax
0x1800e1507  mov     rcx, rax
0x1800e150a  call    ??$?0$$V@?$_Ref_count_obj2@USChange@ChangeTracking@Windows@@@std@@QEAA@XZ; std::_Ref_count_obj2<Windows::ChangeTracking::SChange>::_Ref_count_obj2<Windows::ChangeTracking::SChange>(void)
0x1800e150f  mov     rdx, rax
0x1800e1512  mov     [rsp+120h+var_EC], 3
0x1800e151a  add     rax, 10h
0x1800e151e  mov     [rsp+120h+var_E0], rax
0x1800e1523  mov     [rsp+120h+var_D8], rdx
0x1800e1528  lea     rdx, [rsp+120h+var_E0]
0x1800e152d  mov     rcx, rbx
0x1800e1530  call    ??4?$shared_ptr@USChange@ChangeTracking@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::ChangeTracking::SChange>::operator=(std::shared_ptr<Windows::ChangeTracking::SChange> &&)
0x1800e1535  mov     rcx, [rsp+120h+var_D8]; this
0x1800e153a  test    rcx, rcx
0x1800e153d  jz      short loc_1800E1544
0x1800e153f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e1544  mov     rax, [rbx]
0x1800e1547  movups  xmm0, [rbp+20h+var_98]
0x1800e154b  movups  xmmword ptr [rax+20h], xmm0
0x1800e154f  movups  xmm1, [rbp+20h+var_88]
0x1800e1553  movups  xmmword ptr [rax+30h], xmm1
0x1800e1557  movups  xmm0, [rbp+20h+var_78]
0x1800e155b  movups  xmmword ptr [rax+40h], xmm0
0x1800e155f  movsd   xmm1, [rbp+20h+var_68]
0x1800e1564  movsd   qword ptr [rax+50h], xmm1
0x1800e1569  mov     rax, [rbx]
0x1800e156c  movaps  xmm0, [rbp+20h+var_60]
0x1800e1570  movups  xmmword ptr [rax+0A0h], xmm0
0x1800e1577  movaps  xmm1, [rbp+20h+var_50]
0x1800e157b  movups  xmmword ptr [rax+0B0h], xmm1
0x1800e1582  movaps  xmm0, [rbp+20h+var_40]
0x1800e1586  movups  xmmword ptr [rax+0C0h], xmm0
0x1800e158d  movsd   xmm1, [rbp+20h+var_30]
0x1800e1592  movsd   qword ptr [rax+0D0h], xmm1
0x1800e159a  mov     rcx, [rbx]
0x1800e159d  mov     al, [rbp+20h+var_9C]
0x1800e15a0  mov     [rcx+98h], al
0x1800e15a6  mov     eax, [rbp+20h+var_A0]
0x1800e15a9  test    al, 1
0x1800e15ab  jz      short loc_1800E15D1
0x1800e15ad  lea     rdx, [rsp+120h+var_C8]
0x1800e15b2  mov     rcx, rdi
0x1800e15b5  call    ?_ReadFileNameFromStream@CChangeMonitorResults@ChangeTracking@Windows@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Windows::ChangeTracking::CChangeMonitorResults::_ReadFileNameFromStream(void)
0x1800e15ba  mov     rdx, rax
0x1800e15bd  mov     rcx, [rbx]
0x1800e15c0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e15c5  lea     rcx, [rsp+120h+var_C8]; this
0x1800e15ca  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800e15cf  jmp     short loc_1800E15EC
0x1800e15d1  test    dword ptr [rbp+20h+var_68], 4000000h
0x1800e15d8  jz      short loc_1800E15EF
0x1800e15da  or      eax, 1
0x1800e15dd  mov     [rbp+20h+var_A0], eax
0x1800e15e0  lea     rdx, [rdi+10h]
0x1800e15e4  mov     rcx, [rbx]
0x1800e15e7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800e15ec  mov     eax, [rbp+20h+var_A0]
0x1800e15ef  test    al, 4
0x1800e15f1  jz      short loc_1800E161E
0x1800e15f3  lea     rdx, [rsp+120h+var_C8]
0x1800e15f8  mov     rcx, rdi
0x1800e15fb  call    ?_ReadFileNameFromStream@CChangeMonitorResults@ChangeTracking@Windows@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Windows::ChangeTracking::CChangeMonitorResults::_ReadFileNameFromStream(void)
0x1800e1600  mov     rcx, [rbx]
0x1800e1603  add     rcx, 0D8h
0x1800e160a  mov     rdx, rax
0x1800e160d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e1612  lea     rcx, [rsp+120h+var_C8]; this
0x1800e1617  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800e161c  jmp     short loc_1800E1640
0x1800e161e  test    dword ptr [rbp+20h+var_30], 4000000h
0x1800e1625  jz      short loc_1800E1643
0x1800e1627  or      eax, 4
0x1800e162a  mov     [rbp+20h+var_A0], eax
0x1800e162d  lea     rdx, [rdi+10h]
0x1800e1631  mov     rcx, [rbx]
0x1800e1634  add     rcx, 0D8h
0x1800e163b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800e1640  mov     eax, [rbp+20h+var_A0]
0x1800e1643  test    al, 2
0x1800e1645  jz      short loc_1800E1670
0x1800e1647  lea     rdx, [rsp+120h+var_C8]
0x1800e164c  mov     rcx, rdi
0x1800e164f  call    ?_ReadFileNameFromStream@CChangeMonitorResults@ChangeTracking@Windows@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Windows::ChangeTracking::CChangeMonitorResults::_ReadFileNameFromStream(void)
0x1800e1654  mov     rcx, [rbx]
0x1800e1657  add     rcx, 58h ; 'X'
0x1800e165b  mov     rdx, rax
0x1800e165e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e1663  lea     rcx, [rsp+120h+var_C8]; this
0x1800e1668  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800e166d  mov     eax, [rbp+20h+var_A0]
0x1800e1670  mov     r8d, 8; cb
0x1800e1676  test    r8b, al
0x1800e1679  jz      loc_1800E1766
0x1800e167f  mov     dword ptr [rsp+120h+var_E8], 0
0x1800e1687  mov     rdx, [rbx]
0x1800e168a  add     rdx, 90h; pv
0x1800e1691  mov     rcx, [rdi+8]; pstm
0x1800e1695  call    cs:__imp_IStream_Read
0x1800e169b  test    eax, eax
0x1800e169d  jns     short loc_1800E16B8
0x1800e169f  mov     rcx, [rbp+28h]; this
0x1800e16a3  mov     r9d, eax; char *
0x1800e16a6  lea     r8, aOnecoreuapBase_214; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e16ad  mov     edx, 0FAFh; void *
0x1800e16b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e16b8  mov     r8d, 4; cb
0x1800e16be  lea     rdx, [rsp+120h+var_E8]; pv
0x1800e16c3  mov     rcx, [rdi+8]; pstm
0x1800e16c7  call    cs:__imp_IStream_Read
0x1800e16cd  test    eax, eax
0x1800e16cf  jns     short loc_1800E16EA
0x1800e16d1  mov     rcx, [rbp+28h]; this
0x1800e16d5  mov     r9d, eax; char *
0x1800e16d8  lea     r8, aOnecoreuapBase_214; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e16df  mov     edx, 0FB0h; void *
0x1800e16e4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e16ea  mov     qword ptr [rsp+120h+var_C8], 0
0x1800e16f3  mov     [rsp+120h+var_C0], 0
0x1800e16fc  mov     [rsp+120h+var_B8], 0
0x1800e1705  mov     r8, [rbx]
0x1800e1708  mov     r9d, dword ptr [rsp+120h+var_E8]
0x1800e170d  lea     rcx, [r8+78h]
0x1800e1711  lea     rax, [rsp+120h+var_C8]
0x1800e1716  mov     qword ptr [rsp+120h+var_100], rax; int
0x1800e171b  mov     r8, [r8+80h]
0x1800e1722  lea     rdx, [rsp+120h+var_E0]
0x1800e1727  call    ?insert@?$vector@USUnchangedRange@ChangeTracking@Windows@@V?$allocator@USUnchangedRange@ChangeTracking@Windows@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USUnchangedRange@ChangeTracking@Windows@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@USUnchangedRange@ChangeTracking@Windows@@@std@@@std@@@2@_KAEBUSUnchangedRange@ChangeTracking@Windows@@@Z; std::vector<Windows::ChangeTracking::SUnchangedRange>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Windows::ChangeTracking::SUnchangedRange>>>,unsigned __int64,Windows::ChangeTracking::SUnchangedRange const &)
0x1800e172c  mov     eax, dword ptr [rsp+120h+var_E8]
0x1800e1730  lea     r8d, [rax+rax*2]
0x1800e1734  shl     r8d, 3; cb
0x1800e1738  mov     rdx, [rbx]
0x1800e173b  mov     rdx, [rdx+78h]; pv
0x1800e173f  mov     rcx, [rdi+8]; pstm
0x1800e1743  call    cs:__imp_IStream_Read
0x1800e1749  test    eax, eax
0x1800e174b  jns     short loc_1800E1766
0x1800e174d  mov     rcx, [rbp+28h]; this
0x1800e1751  mov     r9d, eax; char *
0x1800e1754  lea     r8, aOnecoreuapBase_214; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e175b  mov     edx, 0FB3h; void *
0x1800e1760  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1766  mov     rax, rbx
0x1800e1769  mov     rcx, [rbp+20h+var_20]
0x1800e176d  xor     rcx, rsp; StackCookie
0x1800e1770  call    __security_check_cookie
0x1800e1775  add     rsp, 110h
0x1800e177c  pop     rdi
0x1800e177d  pop     rbx
0x1800e177e  pop     rbp
0x1800e177f  retn
```
