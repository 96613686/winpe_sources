# arrow::util::internal::_anonymous_namespace_::GZipCodec::MaxCompressedLen

- ea: `0x1800e1600`
- end: `0x1800e193e`
- name: `arrow::util::internal::_anonymous_namespace_::GZipCodec::MaxCompressedLen`
- size: `830`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180012090`
- `0x18001b360`
- `0x18001bdb0`
- `0x18001f8c0`
- `0x18009a5b0`
- `0x1800dc8f0`
- `0x1800dca00`
- `0x1800e10f0`
- `0x1800e1600`
- `0x1802a1400`
- `0x1802f0fb0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1800e16f1`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\util\compression_zlib.cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::GZipCodec::MaxCompressedLen(
        __int64 a1,
        unsigned int a2)
{
  char v4; // di
  arrow::Status::State *v5; // rax
  arrow::Status::State *v6; // rbx
  arrow::Status::State *v7; // rsi
  __int64 v8; // rax
  _QWORD *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r8
  unsigned __int64 v19; // rdx
  _BYTE *v20; // rcx
  char v22[8]; // [rsp+28h] [rbp-90h] BYREF
  arrow::Status::State *v23; // [rsp+30h] [rbp-88h]
  __int64 v24; // [rsp+38h] [rbp-80h] BYREF
  arrow::Status::State *v25; // [rsp+40h] [rbp-78h]
  __int64 v26; // [rsp+48h] [rbp-70h]
  arrow::Status::State *v27; // [rsp+50h] [rbp-68h]
  _BYTE v28[24]; // [rsp+58h] [rbp-60h] BYREF
  _BYTE *v29; // [rsp+70h] [rbp-48h] BYREF
  unsigned __int64 v30; // [rsp+88h] [rbp-30h]

  v26 = -2;
  v4 = 0;
  if ( !*(_BYTE *)(a1 + 100) )
  {
    arrow::util::internal::_anonymous_namespace_::GZipCodec::InitCompressor(a1, &v24);
    if ( v25 )
    {
      v5 = (arrow::Status::State *)operator new(0x38u);
      v6 = v5;
      v27 = v5;
      if ( v5 )
      {
        v7 = v25;
        *(_BYTE *)v5 = *(_BYTE *)v25;
        std::string::string((char *)v5 + 8, (char *)v7 + 8);
        *((_QWORD *)v6 + 5) = 0;
        *((_QWORD *)v6 + 6) = 0;
        v8 = *((_QWORD *)v7 + 6);
        if ( v8 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
          v4 = 0;
        }
        *((_QWORD *)v6 + 5) = *((_QWORD *)v7 + 5);
        *((_QWORD *)v6 + 6) = *((_QWORD *)v7 + 6);
      }
      else
      {
        v6 = 0;
      }
      v23 = v6;
    }
    else
    {
      v23 = 0;
    }
    if ( v23 )
    {
      v9 = (_QWORD *)arrow::Status::ToString(v22, &v29);
      v10 = arrow::util::ArrowLog::ArrowLog(
              v28,
              "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\util\\compression_zlib.cc",
              421,
              3);
      v4 = 3;
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
      {
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        std::operator<<<std::char_traits<char>>(v11, " Check failed: _s.ok() ");
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
      {
        v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        std::operator<<<std::char_traits<char>>(v12, "Operation failed: ");
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
      {
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        std::operator<<<std::char_traits<char>>(v13, "s");
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
      {
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        std::operator<<<std::char_traits<char>>(v14, "\n");
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        std::operator<<<std::char_traits<char>>(v15, "Bad status");
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
      {
        v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        std::operator<<<std::char_traits<char>>(v16, ": ");
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
      {
        v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        v18 = v9[2];
        if ( v9[3] >= 0x10u )
          v9 = (_QWORD *)*v9;
        std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v17, v9, v18);
      }
    }
    if ( (v4 & 2) != 0 )
    {
      v4 &= ~2u;
      arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v28);
    }
    if ( (v4 & 1) != 0 && v30 >= 0x10 )
    {
      v19 = v30 + 1;
      v20 = v29;
      if ( v30 + 1 >= 0x1000 )
      {
        v19 = v30 + 40;
        v20 = (_BYTE *)*((_QWORD *)v29 - 1);
        if ( (unsigned __int64)(v29 - v20 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v20, v19);
    }
    if ( v23 )
      arrow::Status::State::`scalar deleting destructor'(v23, 1u);
    if ( v25 )
      arrow::Status::State::`scalar deleting destructor'(v25, 1u);
  }
  return (unsigned int)deflateBound(a1 + 8, a2) + 12LL;
}

```

## disassembly

```asm
0x1800e1600  mov     r11, rsp
0x1800e1603  push    rsi
0x1800e1604  push    rdi
0x1800e1605  push    r14
0x1800e1607  sub     rsp, 0A0h
0x1800e160e  mov     qword ptr [r11-70h], 0FFFFFFFFFFFFFFFEh
0x1800e1616  mov     [r11+18h], rbx
0x1800e161a  mov     [r11+20h], rbp
0x1800e161e  mov     rax, cs:__security_cookie
0x1800e1625  xor     rax, rsp
0x1800e1628  mov     [rsp+0B8h+var_28], rax
0x1800e1630  mov     r14, rdx
0x1800e1633  mov     rbp, rcx
0x1800e1636  xor     edi, edi
0x1800e1638  mov     [rsp+0B8h+var_98], edi
0x1800e163c  cmp     [rcx+64h], dil
0x1800e1640  jnz     loc_1800E18FE
0x1800e1646  lea     rdx, [r11-80h]
0x1800e164a  call    arrow__util__internal___anonymous_namespace___GZipCodec__InitCompressor
0x1800e164f  nop
0x1800e1650  cmp     [rsp+0B8h+var_78], rdi
0x1800e1655  jnz     short loc_1800E165E
0x1800e1657  mov     [rsp+0B8h+var_88], rdi
0x1800e165c  jmp     short loc_1800E16BF
0x1800e165e  mov     ecx, 38h ; '8'; Size
0x1800e1663  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e1668  mov     rbx, rax
0x1800e166b  mov     [rsp+0B8h+var_68], rax
0x1800e1670  test    rax, rax
0x1800e1673  jz      short loc_1800E16B7
0x1800e1675  mov     rsi, [rsp+0B8h+var_78]
0x1800e167a  movzx   ecx, byte ptr [rsi]
0x1800e167d  mov     [rax], cl
0x1800e167f  lea     rdx, [rsi+8]
0x1800e1683  lea     rcx, [rax+8]
0x1800e1687  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800e168c  mov     [rbx+28h], rdi
0x1800e1690  mov     [rbx+30h], rdi
0x1800e1694  mov     rax, [rsi+30h]
0x1800e1698  test    rax, rax
0x1800e169b  jz      short loc_1800E16A5
0x1800e169d  lock inc dword ptr [rax+8]
0x1800e16a1  mov     edi, [rsp+0B8h+var_98]
0x1800e16a5  mov     rax, [rsi+28h]
0x1800e16a9  mov     [rbx+28h], rax
0x1800e16ad  mov     rax, [rsi+30h]
0x1800e16b1  mov     [rbx+30h], rax
0x1800e16b5  jmp     short loc_1800E16BA
0x1800e16b7  mov     rbx, rdi
0x1800e16ba  mov     [rsp+0B8h+var_88], rbx
0x1800e16bf  cmp     [rsp+0B8h+var_88], 0
0x1800e16c5  jz      loc_1800E187E
0x1800e16cb  lea     rdx, [rsp+0B8h+var_48]
0x1800e16d0  lea     rcx, [rsp+0B8h+var_90]
0x1800e16d5  call    ?ToString@Status@arrow@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; arrow::Status::ToString(void)
0x1800e16da  mov     rsi, rax
0x1800e16dd  mov     [rsp+0B8h+var_98], 1
0x1800e16e5  mov     r9d, 3
0x1800e16eb  mov     r8d, 1A5h
0x1800e16f1  lea     rdx, aCSourceSrcSubm_7; "c:\\source\\src\\submodules\\apache\\ar"...
0x1800e16f8  lea     rcx, [rsp+0B8h+var_60]
0x1800e16fd  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x1800e1702  mov     rbx, rax
0x1800e1705  mov     edi, 3
0x1800e170a  mov     [rsp+0B8h+var_98], edi
0x1800e170e  mov     rcx, [rax]
0x1800e1711  mov     rax, [rcx+8]
0x1800e1715  mov     rcx, rbx
0x1800e1718  call    cs:__guard_dispatch_icall_fptr
0x1800e171e  test    al, al
0x1800e1720  jz      short loc_1800E1741
0x1800e1722  mov     rax, [rbx]
0x1800e1725  mov     rcx, rbx
0x1800e1728  mov     rax, [rax+10h]
0x1800e172c  call    cs:__guard_dispatch_icall_fptr
0x1800e1732  mov     rcx, rax
0x1800e1735  lea     rdx, aCheckFailedSOk; " Check failed: _s.ok() "
0x1800e173c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e1741  mov     rax, [rbx]
0x1800e1744  mov     rcx, rbx
0x1800e1747  mov     rax, [rax+8]
0x1800e174b  call    cs:__guard_dispatch_icall_fptr
0x1800e1751  test    al, al
0x1800e1753  jz      short loc_1800E1774
0x1800e1755  mov     rax, [rbx]
0x1800e1758  mov     rcx, rbx
0x1800e175b  mov     rax, [rax+10h]
0x1800e175f  call    cs:__guard_dispatch_icall_fptr
0x1800e1765  mov     rcx, rax
0x1800e1768  lea     rdx, aOperationFaile; "Operation failed: "
0x1800e176f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e1774  mov     rax, [rbx]
0x1800e1777  mov     rcx, rbx
0x1800e177a  mov     rax, [rax+8]
0x1800e177e  call    cs:__guard_dispatch_icall_fptr
0x1800e1784  test    al, al
0x1800e1786  jz      short loc_1800E17A7
0x1800e1788  mov     rax, [rbx]
0x1800e178b  mov     rcx, rbx
0x1800e178e  mov     rax, [rax+10h]
0x1800e1792  call    cs:__guard_dispatch_icall_fptr
0x1800e1798  mov     rcx, rax
0x1800e179b  lea     rdx, aS_1; "s"
0x1800e17a2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e17a7  mov     rax, [rbx]
0x1800e17aa  mov     rcx, rbx
0x1800e17ad  mov     rax, [rax+8]
0x1800e17b1  call    cs:__guard_dispatch_icall_fptr
0x1800e17b7  test    al, al
0x1800e17b9  jz      short loc_1800E17DA
0x1800e17bb  mov     rax, [rbx]
0x1800e17be  mov     rcx, rbx
0x1800e17c1  mov     rax, [rax+10h]
0x1800e17c5  call    cs:__guard_dispatch_icall_fptr
0x1800e17cb  mov     rcx, rax
0x1800e17ce  lea     rdx, asc_180379770; "\n"
0x1800e17d5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e17da  mov     rax, [rbx]
0x1800e17dd  mov     rcx, rbx
0x1800e17e0  mov     rax, [rax+8]
0x1800e17e4  call    cs:__guard_dispatch_icall_fptr
0x1800e17ea  test    al, al
0x1800e17ec  jz      short loc_1800E180D
0x1800e17ee  mov     rax, [rbx]
0x1800e17f1  mov     rcx, rbx
0x1800e17f4  mov     rax, [rax+10h]
0x1800e17f8  call    cs:__guard_dispatch_icall_fptr
0x1800e17fe  mov     rcx, rax
0x1800e1801  lea     rdx, aBadStatus; "Bad status"
0x1800e1808  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e180d  mov     rax, [rbx]
0x1800e1810  mov     rcx, rbx
0x1800e1813  mov     rax, [rax+8]
0x1800e1817  call    cs:__guard_dispatch_icall_fptr
0x1800e181d  test    al, al
0x1800e181f  jz      short loc_1800E1840
0x1800e1821  mov     rax, [rbx]
0x1800e1824  mov     rcx, rbx
0x1800e1827  mov     rax, [rax+10h]
0x1800e182b  call    cs:__guard_dispatch_icall_fptr
0x1800e1831  mov     rcx, rax
0x1800e1834  lea     rdx, asc_180374348; ": "
0x1800e183b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e1840  mov     rax, [rbx]
0x1800e1843  mov     rcx, rbx
0x1800e1846  mov     rax, [rax+8]
0x1800e184a  call    cs:__guard_dispatch_icall_fptr
0x1800e1850  test    al, al
0x1800e1852  jz      short loc_1800E187E
0x1800e1854  mov     rax, [rbx]
0x1800e1857  mov     rcx, rbx
0x1800e185a  mov     rax, [rax+10h]
0x1800e185e  call    cs:__guard_dispatch_icall_fptr
0x1800e1864  mov     r8, [rsi+10h]
0x1800e1868  cmp     qword ptr [rsi+18h], 10h
0x1800e186d  jb      short loc_1800E1872
0x1800e186f  mov     rsi, [rsi]
0x1800e1872  mov     rdx, rsi
0x1800e1875  mov     rcx, rax
0x1800e1878  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800e187d  nop
0x1800e187e  test    dil, 2
0x1800e1882  jz      short loc_1800E1892
0x1800e1884  and     edi, 0FFFFFFFDh
0x1800e1887  lea     rcx, [rsp+0B8h+var_60]; this
0x1800e188c  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x1800e1891  nop
0x1800e1892  test    dil, 1
0x1800e1896  jz      short loc_1800E18D5
0x1800e1898  mov     rdx, [rsp+0B8h+var_30]
0x1800e18a0  cmp     rdx, 10h
0x1800e18a4  jb      short loc_1800E18D5
0x1800e18a6  inc     rdx
0x1800e18a9  mov     rcx, [rsp+0B8h+var_48]
0x1800e18ae  mov     rax, rcx
0x1800e18b1  cmp     rdx, 1000h
0x1800e18b8  jb      short loc_1800E18CF
0x1800e18ba  add     rdx, 27h ; '''; unsigned __int64
0x1800e18be  mov     rcx, [rcx-8]; void *
0x1800e18c2  sub     rax, rcx
0x1800e18c5  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e18c9  cmp     rax, 1Fh
0x1800e18cd  ja      short loc_1800E1938
0x1800e18cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e18d4  nop
0x1800e18d5  mov     rcx, [rsp+0B8h+var_88]; this
0x1800e18da  test    rcx, rcx
0x1800e18dd  jz      short loc_1800E18EA
0x1800e18df  mov     edx, 1; unsigned int
0x1800e18e4  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e18e9  nop
0x1800e18ea  mov     rcx, [rsp+0B8h+var_78]; this
0x1800e18ef  test    rcx, rcx
0x1800e18f2  jz      short loc_1800E18FE
0x1800e18f4  mov     edx, 1; unsigned int
0x1800e18f9  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e18fe  lea     rcx, [rbp+8]
0x1800e1902  mov     edx, r14d
0x1800e1905  call    deflateBound
0x1800e190a  mov     eax, eax
0x1800e190c  add     rax, 0Ch
0x1800e1910  mov     rcx, [rsp+0B8h+var_28]
0x1800e1918  xor     rcx, rsp; StackCookie
0x1800e191b  call    __security_check_cookie
0x1800e1920  lea     r11, [rsp+0B8h+var_18]
0x1800e1928  mov     rbx, [r11+30h]
0x1800e192c  mov     rbp, [r11+38h]
0x1800e1930  mov     rsp, r11
0x1800e1933  pop     r14
0x1800e1935  pop     rdi
0x1800e1936  pop     rsi
0x1800e1937  retn
0x1800e1938  call    _invalid_parameter_noinfo_noreturn
```
