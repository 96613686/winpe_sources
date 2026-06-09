# DiagHubCommon::FileLogWriter::FileLogWriter(ushort const *)

- ea: `0x14000993c`
- end: `0x140009b4e`
- name: `??0FileLogWriter@DiagHubCommon@@QEAA@PEBG@Z`
- size: `530`
- prototype: `__int64 __fastcall(DiagHubCommon::FileLogWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000a42c`

## callees

- `0x140003010`
- `0x140003088`
- `0x14000993c`
- `0x140009f00`
- `0x14000d304`
- `0x140014c70`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000997a`
- `KERNEL32!InitializeCriticalSection` at `0x14000997a`
- `MSVCP140!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140009af1`
- `MSVCP140!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140009af1`
- `MSVCP140!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x140009a8c`
- `MSVCP140!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x140009a8c`
- `MSVCP140!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x140009a32`
- `MSVCP140!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x140009a32`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1400099e7`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1400099e7`
- `MSVCP140!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x140009a77`
- `MSVCP140!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x140009a77`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x140009a02`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x140009a4f`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x140009aa7`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x140009a02`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x140009a4f`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x140009aa7`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000999b`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000999b`
- `MSVCP140!??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1400099ba`
- `MSVCP140!??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1400099ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
DiagHubCommon::FileLogWriter *__fastcall DiagHubCommon::FileLogWriter::FileLogWriter(
        DiagHubCommon::FileLogWriter *this,
        const unsigned __int16 *a2)
{
  char *v4; // rcx
  char *v5; // rsi
  struct _iobuf *v6; // rbx
  __int64 v7; // rax
  std::codecvt_base *v8; // rbx
  void (__fastcall ***v9)(_QWORD, __int64); // rax
  _OWORD v11[2]; // [rsp+28h] [rbp-50h] BYREF
  DiagHubCommon::FileLogWriter *v12; // [rsp+48h] [rbp-30h]
  char *v13; // [rsp+50h] [rbp-28h]

  v12 = this;
  *(_QWORD *)this = &DiagHubCommon::FileLogWriter::`vftable';
  v4 = (char *)this + 8;
  *(_OWORD *)v4 = 0;
  *((_OWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v4);
  v5 = (char *)this + 48;
  v13 = (char *)this + 48;
  *((_QWORD *)this + 6) = &std::basic_ofstream<unsigned short>::`vbtable';
  std::basic_ios<unsigned short>::basic_ios<unsigned short>((char *)this + 216);
  std::basic_ostream<unsigned short>::basic_ostream<unsigned short>((char *)this + 48, (char *)this + 56, 0, 0);
  *(_QWORD *)&v5[*(int *)(*(_QWORD *)v5 + 4LL)] = &std::basic_ofstream<unsigned short>::`vftable';
  *(_DWORD *)&v5[*(int *)(*(_QWORD *)v5 + 4LL) - 4] = *(_DWORD *)(*(_QWORD *)v5 + 4LL) - 168;
  std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>((char *)this + 56);
  *((_QWORD *)this + 7) = &std::basic_filebuf<unsigned short>::`vftable';
  *((_BYTE *)this + 180) = 0;
  *((_BYTE *)this + 170) = 0;
  std::basic_streambuf<unsigned short>::_Init((char *)this + 56);
  *((_QWORD *)this + 23) = 0;
  *(_QWORD *)((char *)this + 172) = `std::basic_filebuf<unsigned short>::_Init'::`2'::_Stinit;
  *((_QWORD *)this + 20) = 0;
  v6 = std::_Fiopen(a2, 10, 64);
  if ( v6 )
  {
    *((_BYTE *)this + 180) = 1;
    *((_BYTE *)this + 170) = 0;
    std::basic_streambuf<unsigned short>::_Init((char *)this + 56);
    *((_QWORD *)this + 23) = v6;
    *(_QWORD *)((char *)this + 172) = `std::basic_filebuf<unsigned short>::_Init'::`2'::_Stinit;
    *((_QWORD *)this + 20) = 0;
    v7 = std::basic_streambuf<unsigned short>::getloc((char *)this + 56, v11);
    v8 = (std::codecvt_base *)std::use_facet<std::codecvt<unsigned short,char,_Mbstatet>>(v7);
    if ( std::codecvt_base::always_noconv(v8) )
    {
      *((_QWORD *)this + 20) = 0;
    }
    else
    {
      *((_QWORD *)this + 20) = v8;
      std::basic_streambuf<unsigned short>::_Init((char *)this + 56);
    }
    if ( *((_QWORD *)&v11[0] + 1) )
    {
      v9 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v11[0] + 1) + 16LL))(*((_QWORD *)&v11[0] + 1));
      if ( v9 )
        (**v9)(v9, 1);
    }
  }
  else
  {
    std::basic_ios<unsigned short>::setstate(&v5[*(int *)(*(_QWORD *)v5 + 4LL)], 2);
  }
  memset(v11, 0, sizeof(v11));
  std::wstring::_Construct<1,unsigned short const *>(v11, L"============= Diagnostics Hub Log =============\n\n", 49);
  DiagHubCommon::FileLogWriter::Write(this, v11);
  std::wstring::~wstring(v11);
  return this;
}

```

## disassembly

```asm
0x14000993c  mov     [rsp+arg_10], rbx
0x140009941  push    rsi
0x140009942  push    rdi
0x140009943  push    r14
0x140009945  sub     rsp, 60h
0x140009949  mov     rbx, rdx
0x14000994c  mov     r14, rcx
0x14000994f  mov     [rsp+78h+var_30], rcx
0x140009954  mov     [rsp+78h+var_58], 0
0x14000995c  lea     rax, ??_7FileLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::FileLogWriter::`vftable'
0x140009963  mov     [rcx], rax
0x140009966  add     rcx, 8; lpCriticalSection
0x14000996a  xorps   xmm0, xmm0
0x14000996d  xor     eax, eax
0x14000996f  movups  xmmword ptr [rcx], xmm0
0x140009972  movups  xmmword ptr [rcx+10h], xmm0
0x140009976  mov     [rcx+20h], rax
0x14000997a  call    cs:__imp_InitializeCriticalSection
0x140009980  nop
0x140009981  lea     rsi, [r14+30h]
0x140009985  mov     [rsp+78h+var_28], rsi
0x14000998a  lea     rax, ??_8?$basic_ofstream@GU?$char_traits@G@std@@@std@@7B@; const std::basic_ofstream<ushort>::`vbtable'
0x140009991  mov     [rsi], rax
0x140009994  lea     rcx, [rsi+0A8h]
0x14000999b  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x1400099a1  nop
0x1400099a2  mov     [rsp+78h+var_58], 1
0x1400099aa  lea     rdi, [rsi+8]
0x1400099ae  xor     r9d, r9d
0x1400099b1  xor     r8d, r8d
0x1400099b4  mov     rdx, rdi
0x1400099b7  mov     rcx, rsi
0x1400099ba  call    cs:__imp_??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_ostream<ushort>::basic_ostream<ushort>(std::basic_streambuf<ushort> *,bool)
0x1400099c0  nop
0x1400099c1  mov     rax, [rsi]
0x1400099c4  movsxd  rcx, dword ptr [rax+4]
0x1400099c8  lea     rax, ??_7?$basic_ofstream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ofstream<ushort>::`vftable'
0x1400099cf  mov     [rcx+rsi], rax
0x1400099d3  mov     rax, [rsi]
0x1400099d6  movsxd  rcx, dword ptr [rax+4]
0x1400099da  lea     edx, [rcx-0A8h]
0x1400099e0  mov     [rcx+rsi-4], edx
0x1400099e4  mov     rcx, rdi
0x1400099e7  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x1400099ed  lea     rax, ??_7?$basic_filebuf@GU?$char_traits@G@std@@@std@@6B@; const std::basic_filebuf<ushort>::`vftable'
0x1400099f4  mov     [rdi], rax
0x1400099f7  mov     byte ptr [rdi+7Ch], 0
0x1400099fb  mov     byte ptr [rdi+72h], 0
0x1400099ff  mov     rcx, rdi
0x140009a02  call    cs:__imp_?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ; std::basic_streambuf<ushort>::_Init(void)
0x140009a08  mov     qword ptr [rdi+80h], 0
0x140009a13  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)'::`2'::_Stinit
0x140009a1a  mov     [rdi+74h], rax
0x140009a1e  mov     qword ptr [rdi+68h], 0
0x140009a26  mov     edx, 0Ah
0x140009a2b  lea     r8d, [rdx+36h]
0x140009a2f  mov     rcx, rbx
0x140009a32  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x140009a38  mov     rbx, rax
0x140009a3b  test    rax, rax
0x140009a3e  jz      loc_140009AE0
0x140009a44  mov     byte ptr [rdi+7Ch], 1
0x140009a48  mov     byte ptr [rdi+72h], 0
0x140009a4c  mov     rcx, rdi
0x140009a4f  call    cs:__imp_?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ; std::basic_streambuf<ushort>::_Init(void)
0x140009a55  mov     [rdi+80h], rbx
0x140009a5c  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)'::`2'::_Stinit
0x140009a63  mov     [rdi+74h], rax
0x140009a67  mov     qword ptr [rdi+68h], 0
0x140009a6f  lea     rdx, [rsp+78h+var_50]
0x140009a74  mov     rcx, rdi
0x140009a77  call    cs:__imp_?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ; std::basic_streambuf<ushort>::getloc(void)
0x140009a7d  nop
0x140009a7e  mov     rcx, rax
0x140009a81  call    ??$use_facet@V?$codecvt@GDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@GDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<ushort,char,_Mbstatet>>(std::locale const &)
0x140009a86  mov     rbx, rax
0x140009a89  mov     rcx, rax
0x140009a8c  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x140009a92  test    al, al
0x140009a94  jz      short loc_140009AA0
0x140009a96  mov     qword ptr [rdi+68h], 0
0x140009a9e  jmp     short loc_140009AAE
0x140009aa0  mov     [rdi+68h], rbx
0x140009aa4  mov     rcx, rdi
0x140009aa7  call    cs:__imp_?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ; std::basic_streambuf<ushort>::_Init(void)
0x140009aad  nop
0x140009aae  mov     rcx, qword ptr [rsp+78h+var_50+8]
0x140009ab3  test    rcx, rcx
0x140009ab6  jz      short loc_140009AF8
0x140009ab8  mov     rax, [rcx]
0x140009abb  mov     rax, [rax+10h]
0x140009abf  call    cs:__guard_dispatch_icall_fptr
0x140009ac5  mov     rcx, rax
0x140009ac8  test    rax, rax
0x140009acb  jz      short loc_140009AF8
0x140009acd  mov     rax, [rax]
0x140009ad0  mov     edx, 1
0x140009ad5  mov     rax, [rax]
0x140009ad8  call    cs:__guard_dispatch_icall_fptr
0x140009ade  jmp     short loc_140009AF8
0x140009ae0  mov     rax, [rsi]
0x140009ae3  movsxd  rcx, dword ptr [rax+4]
0x140009ae7  add     rcx, rsi
0x140009aea  xor     r8d, r8d
0x140009aed  lea     edx, [r8+2]
0x140009af1  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x140009af7  nop
0x140009af8  xorps   xmm0, xmm0
0x140009afb  movups  [rsp+78h+var_50], xmm0
0x140009b00  xorps   xmm1, xmm1
0x140009b03  movdqu  [rsp+78h+var_40], xmm1
0x140009b09  mov     r8d, 31h ; '1'
0x140009b0f  lea     rdx, aDiagnosticsHub_0; "============= Diagnostics Hub Log ====="...
0x140009b16  lea     rcx, [rsp+78h+var_50]
0x140009b1b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140009b20  nop
0x140009b21  lea     rdx, [rsp+78h+var_50]
0x140009b26  mov     rcx, r14
0x140009b29  call    ?Write@FileLogWriter@DiagHubCommon@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DiagHubCommon::FileLogWriter::Write(std::wstring const &)
0x140009b2e  nop
0x140009b2f  lea     rcx, [rsp+78h+var_50]
0x140009b34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009b39  nop
0x140009b3a  mov     rax, r14
0x140009b3d  mov     rbx, [rsp+78h+arg_10]
0x140009b45  add     rsp, 60h
0x140009b49  pop     r14
0x140009b4b  pop     rdi
0x140009b4c  pop     rsi
0x140009b4d  retn
```
