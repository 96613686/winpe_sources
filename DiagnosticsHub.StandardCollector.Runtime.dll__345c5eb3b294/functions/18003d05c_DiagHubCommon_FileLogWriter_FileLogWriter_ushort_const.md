# DiagHubCommon::FileLogWriter::FileLogWriter(ushort const *)

- ea: `0x18003d05c`
- end: `0x18003d278`
- name: `??0FileLogWriter@DiagHubCommon@@QEAA@PEBG@Z`
- size: `540`
- prototype: `__int64 __fastcall(DiagHubCommon::FileLogWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003da40`

## callees

- `0x180009fa4`
- `0x18000a078`
- `0x18003d05c`
- `0x18003d5d0`
- `0x18003fe08`
- `0x18004b640`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18003d09a`
- `KERNEL32!InitializeCriticalSection` at `0x18003d09a`
- `MSVCP140!??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x18003d0da`
- `MSVCP140!??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x18003d0da`
- `MSVCP140!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18003d211`
- `MSVCP140!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18003d211`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18003d0bb`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18003d0bb`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18003d107`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18003d107`
- `MSVCP140!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x18003d1ac`
- `MSVCP140!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x18003d1ac`
- `MSVCP140!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x18003d152`
- `MSVCP140!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x18003d152`
- `MSVCP140!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18003d197`
- `MSVCP140!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18003d197`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x18003d122`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x18003d16f`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x18003d1c7`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x18003d122`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x18003d16f`
- `MSVCP140!?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ` at `0x18003d1c7`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003d230`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003d230`

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
  size_t v10; // rax
  _OWORD v12[2]; // [rsp+28h] [rbp-50h] BYREF
  DiagHubCommon::FileLogWriter *v13; // [rsp+48h] [rbp-30h]
  char *v14; // [rsp+50h] [rbp-28h]

  v13 = this;
  *(_QWORD *)this = &DiagHubCommon::FileLogWriter::`vftable';
  v4 = (char *)this + 8;
  *(_OWORD *)v4 = 0;
  *((_OWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v4);
  v5 = (char *)this + 48;
  v14 = (char *)this + 48;
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
    v7 = std::basic_streambuf<unsigned short>::getloc((char *)this + 56, v12);
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
    if ( *((_QWORD *)&v12[0] + 1) )
    {
      v9 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v12[0] + 1) + 16LL))(*((_QWORD *)&v12[0] + 1));
      if ( v9 )
        (**v9)(v9, 1);
    }
  }
  else
  {
    std::basic_ios<unsigned short>::setstate(&v5[*(int *)(*(_QWORD *)v5 + 4LL)], 2);
  }
  memset(v12, 0, sizeof(v12));
  v10 = wcslen(L"============= Diagnostics Hub Log =============\n\n");
  std::wstring::_Construct<1,unsigned short const *>(v12, L"============= Diagnostics Hub Log =============\n\n", v10);
  DiagHubCommon::FileLogWriter::Write(this, v12);
  std::wstring::~wstring(v12);
  return this;
}

```

## disassembly

```asm
0x18003d05c  mov     [rsp+arg_10], rbx
0x18003d061  push    rsi
0x18003d062  push    rdi
0x18003d063  push    r14
0x18003d065  sub     rsp, 60h
0x18003d069  mov     rbx, rdx
0x18003d06c  mov     r14, rcx
0x18003d06f  mov     [rsp+78h+var_30], rcx
0x18003d074  mov     [rsp+78h+var_58], 0
0x18003d07c  lea     rax, ??_7FileLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::FileLogWriter::`vftable'
0x18003d083  mov     [rcx], rax
0x18003d086  add     rcx, 8; lpCriticalSection
0x18003d08a  xorps   xmm0, xmm0
0x18003d08d  xor     eax, eax
0x18003d08f  movups  xmmword ptr [rcx], xmm0
0x18003d092  movups  xmmword ptr [rcx+10h], xmm0
0x18003d096  mov     [rcx+20h], rax
0x18003d09a  call    cs:__imp_InitializeCriticalSection
0x18003d0a0  nop
0x18003d0a1  lea     rsi, [r14+30h]
0x18003d0a5  mov     [rsp+78h+var_28], rsi
0x18003d0aa  lea     rax, ??_8?$basic_ofstream@GU?$char_traits@G@std@@@std@@7B@; const std::basic_ofstream<ushort>::`vbtable'
0x18003d0b1  mov     [rsi], rax
0x18003d0b4  lea     rcx, [rsi+0A8h]
0x18003d0bb  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x18003d0c1  nop
0x18003d0c2  mov     [rsp+78h+var_58], 1
0x18003d0ca  lea     rdi, [rsi+8]
0x18003d0ce  xor     r9d, r9d
0x18003d0d1  xor     r8d, r8d
0x18003d0d4  mov     rdx, rdi
0x18003d0d7  mov     rcx, rsi
0x18003d0da  call    cs:__imp_??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_ostream<ushort>::basic_ostream<ushort>(std::basic_streambuf<ushort> *,bool)
0x18003d0e0  nop
0x18003d0e1  mov     rax, [rsi]
0x18003d0e4  movsxd  rcx, dword ptr [rax+4]
0x18003d0e8  lea     rax, ??_7?$basic_ofstream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ofstream<ushort>::`vftable'
0x18003d0ef  mov     [rcx+rsi], rax
0x18003d0f3  mov     rax, [rsi]
0x18003d0f6  movsxd  rcx, dword ptr [rax+4]
0x18003d0fa  lea     edx, [rcx-0A8h]
0x18003d100  mov     [rcx+rsi-4], edx
0x18003d104  mov     rcx, rdi
0x18003d107  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x18003d10d  lea     rax, ??_7?$basic_filebuf@GU?$char_traits@G@std@@@std@@6B@; const std::basic_filebuf<ushort>::`vftable'
0x18003d114  mov     [rdi], rax
0x18003d117  mov     byte ptr [rdi+7Ch], 0
0x18003d11b  mov     byte ptr [rdi+72h], 0
0x18003d11f  mov     rcx, rdi
0x18003d122  call    cs:__imp_?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ; std::basic_streambuf<ushort>::_Init(void)
0x18003d128  mov     qword ptr [rdi+80h], 0
0x18003d133  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)'::`2'::_Stinit
0x18003d13a  mov     [rdi+74h], rax
0x18003d13e  mov     qword ptr [rdi+68h], 0
0x18003d146  mov     edx, 0Ah
0x18003d14b  lea     r8d, [rdx+36h]
0x18003d14f  mov     rcx, rbx
0x18003d152  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x18003d158  mov     rbx, rax
0x18003d15b  test    rax, rax
0x18003d15e  jz      loc_18003D200
0x18003d164  mov     byte ptr [rdi+7Ch], 1
0x18003d168  mov     byte ptr [rdi+72h], 0
0x18003d16c  mov     rcx, rdi
0x18003d16f  call    cs:__imp_?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ; std::basic_streambuf<ushort>::_Init(void)
0x18003d175  mov     [rdi+80h], rbx
0x18003d17c  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)'::`2'::_Stinit
0x18003d183  mov     [rdi+74h], rax
0x18003d187  mov     qword ptr [rdi+68h], 0
0x18003d18f  lea     rdx, [rsp+78h+var_50]
0x18003d194  mov     rcx, rdi
0x18003d197  call    cs:__imp_?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ; std::basic_streambuf<ushort>::getloc(void)
0x18003d19d  nop
0x18003d19e  mov     rcx, rax
0x18003d1a1  call    ??$use_facet@V?$codecvt@GDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@GDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<ushort,char,_Mbstatet>>(std::locale const &)
0x18003d1a6  mov     rbx, rax
0x18003d1a9  mov     rcx, rax
0x18003d1ac  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x18003d1b2  test    al, al
0x18003d1b4  jz      short loc_18003D1C0
0x18003d1b6  mov     qword ptr [rdi+68h], 0
0x18003d1be  jmp     short loc_18003D1CE
0x18003d1c0  mov     [rdi+68h], rbx
0x18003d1c4  mov     rcx, rdi
0x18003d1c7  call    cs:__imp_?_Init@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXXZ; std::basic_streambuf<ushort>::_Init(void)
0x18003d1cd  nop
0x18003d1ce  mov     rcx, qword ptr [rsp+78h+var_50+8]
0x18003d1d3  test    rcx, rcx
0x18003d1d6  jz      short loc_18003D218
0x18003d1d8  mov     rax, [rcx]
0x18003d1db  mov     rax, [rax+10h]
0x18003d1df  call    cs:__guard_dispatch_icall_fptr
0x18003d1e5  mov     rcx, rax
0x18003d1e8  test    rax, rax
0x18003d1eb  jz      short loc_18003D218
0x18003d1ed  mov     rax, [rax]
0x18003d1f0  mov     edx, 1
0x18003d1f5  mov     rax, [rax]
0x18003d1f8  call    cs:__guard_dispatch_icall_fptr
0x18003d1fe  jmp     short loc_18003D218
0x18003d200  mov     rax, [rsi]
0x18003d203  movsxd  rcx, dword ptr [rax+4]
0x18003d207  add     rcx, rsi
0x18003d20a  xor     r8d, r8d
0x18003d20d  lea     edx, [r8+2]
0x18003d211  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x18003d217  nop
0x18003d218  xorps   xmm0, xmm0
0x18003d21b  movups  [rsp+78h+var_50], xmm0
0x18003d220  xorps   xmm1, xmm1
0x18003d223  movdqu  [rsp+78h+var_40], xmm1
0x18003d229  lea     rcx, aDiagnosticsHub_0; "============= Diagnostics Hub Log ====="...
0x18003d230  call    cs:__imp_wcslen
0x18003d236  mov     r8, rax
0x18003d239  lea     rdx, aDiagnosticsHub_0; "============= Diagnostics Hub Log ====="...
0x18003d240  lea     rcx, [rsp+78h+var_50]
0x18003d245  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003d24a  nop
0x18003d24b  lea     rdx, [rsp+78h+var_50]
0x18003d250  mov     rcx, r14
0x18003d253  call    ?Write@FileLogWriter@DiagHubCommon@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DiagHubCommon::FileLogWriter::Write(std::wstring const &)
0x18003d258  nop
0x18003d259  lea     rcx, [rsp+78h+var_50]
0x18003d25e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d263  nop
0x18003d264  mov     rax, r14
0x18003d267  mov     rbx, [rsp+78h+arg_10]
0x18003d26f  add     rsp, 60h
0x18003d273  pop     r14
0x18003d275  pop     rdi
0x18003d276  pop     rsi
0x18003d277  retn
```
