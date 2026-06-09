# D3DCommon::ERR(ushort,...)

- ea: `0x18000f774`
- end: `0x18000f8d5`
- name: `?ERR@D3DCommon@@YAXGZZ`
- size: `353`
- prototype: `void(D3DCommon *__hidden this, unsigned __int16, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000f638`

## callees

- `0x180002144`
- `0x180004020`
- `0x1800043f0`
- `0x180008490`
- `0x18000ee78`
- `0x18000ef28`
- `0x18000f0e8`
- `0x18000f774`
- `0x18000f8dc`
- `0x18002aa70`
- `0x18002f2e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f80f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f80f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void D3DCommon::ERR(D3DCommon *this, __int64 a2, ...)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  _QWORD *v6; // [rsp+20h] [rbp-58h] BYREF
  __int64 v7; // [rsp+28h] [rbp-50h] BYREF
  _QWORD v8[3]; // [rsp+30h] [rbp-48h] BYREF
  void **v9; // [rsp+48h] [rbp-30h] BYREF
  __int16 v10; // [rsp+50h] [rbp-28h]
  HMODULE ModuleHandleW; // [rsp+58h] [rbp-20h]
  __int64 v12; // [rsp+60h] [rbp-18h]
  __int64 v13; // [rsp+68h] [rbp-10h]
  __int16 v14; // [rsp+80h] [rbp+8h]
  __int64 v15; // [rsp+88h] [rbp+10h] BYREF

  v14 = (__int16)this;
  v15 = a2;
  v8[1] = -2;
  try
  {
    v2 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v7 = v2;
    if ( v2 )
      v2 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v2,
             1024);
    v8[0] = v2;
    v3 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v7 = v3;
    if ( v3 )
      v3 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v3,
             1024);
    v6 = (_QWORD *)v3;
    v4 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v7 = v4;
    if ( v4 )
      v4 = mlib::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>(v4);
    v7 = v4;
    v9 = &mlib::MUILoader::`vftable';
    v10 = v14;
    ModuleHandleW = GetModuleHandleW(0);
    v12 = 0;
    v13 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator=(
      v8,
      &v9);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spfva(
      &v6,
      *(_QWORD *)(v8[0] + 24LL),
      &v15);
    mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::transcode_from(&v7, v6[3], *v6);
    Log_Text_F((__int64)"base\\winsat\\d3d\\dx9misc.cpp", 1035, *(const char **)(v7 + 24));
    if ( D3DCommon::g_phStdOut )
    {
      v5 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             D3DCommon::g_phStdOut + 240,
             &v6);
      std::endl(v5);
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v7);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v6);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v8);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18000f774  mov     rax, rsp
0x18000f777  mov     [rax+8], cx
0x18000f77b  mov     [rax+10h], rdx
0x18000f77f  mov     [rax+18h], r8
0x18000f783  mov     [rax+20h], r9
0x18000f787  sub     rsp, 78h
0x18000f78b  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18000f793  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x18000f798  mov     [rsp+78h+var_50], rax
0x18000f79d  test    rax, rax
0x18000f7a0  jz      short loc_18000F7B0
0x18000f7a2  mov     edx, 400h
0x18000f7a7  mov     rcx, rax
0x18000f7aa  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x18000f7af  nop
0x18000f7b0  mov     [rsp+78h+var_48], rax
0x18000f7b5  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x18000f7ba  mov     [rsp+78h+var_50], rax
0x18000f7bf  test    rax, rax
0x18000f7c2  jz      short loc_18000F7D2
0x18000f7c4  mov     edx, 400h
0x18000f7c9  mov     rcx, rax
0x18000f7cc  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x18000f7d1  nop
0x18000f7d2  mov     [rsp+78h+var_58], rax
0x18000f7d7  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x18000f7dc  mov     [rsp+78h+var_50], rax
0x18000f7e1  test    rax, rax
0x18000f7e4  jz      short loc_18000F7EF
0x18000f7e6  mov     rcx, rax
0x18000f7e9  call    ??0?$mstring_buf@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@AEAA@_KAEBV?$allocator@D@std@@@Z; mlib::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>(unsigned __int64,std::allocator<char> const &)
0x18000f7ee  nop
0x18000f7ef  mov     [rsp+78h+var_50], rax
0x18000f7f4  lea     rax, ??_7MUILoader@mlib@@6B@; const mlib::MUILoader::`vftable'
0x18000f7fb  mov     [rsp+78h+var_30], rax
0x18000f800  movzx   eax, [rsp+78h+arg_0]
0x18000f808  mov     [rsp+78h+var_28], ax
0x18000f80d  xor     ecx, ecx; lpModuleName
0x18000f80f  call    cs:__imp_GetModuleHandleW
0x18000f816  nop     dword ptr [rax+rax+00h]
0x18000f81b  mov     [rsp+78h+var_20], rax
0x18000f820  and     [rsp+78h+var_18], 0
0x18000f826  and     [rsp+78h+var_10], 0
0x18000f82c  lea     rdx, [rsp+78h+var_30]
0x18000f831  lea     rcx, [rsp+78h+var_48]
0x18000f836  call    ??4?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV01@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator=(mlib::MSInitializer const &)
0x18000f83b  lea     r8, [rsp+78h+arg_8]
0x18000f843  mov     rax, [rsp+78h+var_48]
0x18000f848  mov     rdx, [rax+18h]
0x18000f84c  lea     rcx, [rsp+78h+var_58]
0x18000f851  call    ?spfva@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGPEAD@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spfva(ushort const *,char *)
0x18000f856  mov     rax, [rsp+78h+var_58]
0x18000f85b  mov     r8, [rax]
0x18000f85e  mov     rdx, [rax+18h]
0x18000f862  lea     rcx, [rsp+78h+var_50]
0x18000f867  call    ?transcode_from@?$fundamental_string@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@QEAAKPEBG_K@Z; mlib::fundamental_string<char,mlib::m_traits<char>,std::allocator<char>>::transcode_from(ushort const *,unsigned __int64)
0x18000f86c  mov     rax, [rsp+78h+var_50]
0x18000f871  mov     r8, [rax+18h]
0x18000f875  mov     edx, 40Bh
0x18000f87a  lea     rcx, aBaseWinsatD3dD; "base\\winsat\\d3d\\dx9misc.cpp"
0x18000f881  call    Log_Text_F
0x18000f886  mov     rcx, cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x18000f88d  test    rcx, rcx
0x18000f890  jz      short loc_18000F8AC
0x18000f892  add     rcx, 0F0h
0x18000f899  lea     rdx, [rsp+78h+var_58]
0x18000f89e  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x18000f8a3  mov     rcx, rax
0x18000f8a6  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x18000f8ab  nop
0x18000f8ac  lea     rcx, [rsp+78h+var_50]
0x18000f8b1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000f8b6  nop
0x18000f8b7  lea     rcx, [rsp+78h+var_58]
0x18000f8bc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000f8c1  nop
0x18000f8c2  lea     rcx, [rsp+78h+var_48]
0x18000f8c7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000f8cc  nop
0x18000f8cd  jmp     short $+2
0x18000f8cf  add     rsp, 78h
0x18000f8d3  retn
```
