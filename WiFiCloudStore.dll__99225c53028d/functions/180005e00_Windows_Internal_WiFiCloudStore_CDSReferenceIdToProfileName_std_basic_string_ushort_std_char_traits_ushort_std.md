# Windows::Internal::WiFiCloudStore::CDSReferenceIdToProfileName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180005e00`
- end: `0x1800062af`
- name: `?CDSReferenceIdToProfileName@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z`
- size: `1199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001314c`
- `0x1800211b0`

## callees

- `0x180005e00`
- `0x1800067b0`
- `0x1800069e0`
- `0x180020390`
- `0x18002079c`
- `0x180025308`
- `0x1800277f0`
- `0x180027e28`
- `0x18002a030`
- `0x18002a400`
- `0x18002a8dc`
- `0x18002bb01`
- `0x18002e2d0`
- `0x180034948`
- `0x18003cc2c`

## import_xrefs

- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800060a7`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800060a7`
- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000613c`
- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000613c`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x180005fb4`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x180005fb4`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180006147`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180006147`
- `msvcp_win!?setp@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG0@Z` at `0x180006129`
- `msvcp_win!?setp@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG0@Z` at `0x180006129`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180006151`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180006151`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x180005f63`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x180005f63`
- `msvcp_win!?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800060c9`
- `msvcp_win!?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800060e2`
- `msvcp_win!?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800060c9`
- `msvcp_win!?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800060e2`
- `msvcp_win!?egptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800061eb`
- `msvcp_win!?egptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800061eb`
- `msvcp_win!?setg@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG00@Z` at `0x180006119`
- `msvcp_win!?setg@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG00@Z` at `0x180006119`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800060bb`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800060bb`
- `msvcp_win!??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x180005f80`
- `msvcp_win!??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x180005f80`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEAI@Z` at `0x180006029`
- `msvcp_win!??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEAI@Z` at `0x180006029`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180005fd3`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180005fd3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000623c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000623c`

## string_xrefs

- `0x180006223`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
unsigned __int64 *__fastcall Windows::Internal::WiFiCloudStore::CDSReferenceIdToProfileName(
        unsigned __int64 *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // r15
  unsigned int v4; // edx
  void **v5; // rcx
  int v6; // r13d
  unsigned __int64 v7; // r12
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rsi
  __int64 v10; // rbx
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  size_t v13; // rcx
  unsigned __int64 v14; // r15
  unsigned __int64 i; // rsi
  __int64 v16; // rbx
  _QWORD *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r8
  __int16 v20; // r9
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rdx
  _QWORD *v23; // rcx
  _WORD *v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // rbx
  void *v27; // rax
  void *v29; // rbx
  void *v30; // rbx
  void *v31; // rax
  int v32; // [rsp+24h] [rbp-DCh] BYREF
  unsigned __int64 v33; // [rsp+28h] [rbp-D8h] BYREF
  void *v34[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v35[2]; // [rsp+40h] [rbp-C0h] BYREF
  int *v36; // [rsp+50h] [rbp-B0h] BYREF
  void **v37; // [rsp+58h] [rbp-A8h] BYREF
  char v38[96]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-40h]
  int v40; // [rsp+C8h] [rbp-38h]
  _BYTE v41[104]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 *v42; // [rsp+140h] [rbp+40h]
  void *v43; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int64 v44; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v2 = a2;
  v33 = a2;
  v42 = a1;
  if ( (*(_BYTE *)(a2 + 16) & 3) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      (const char *)0x80070057LL,
      0);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  std::wstring::_Construct_empty(a1);
  v6 = 1;
  v7 = *(_QWORD *)(v2 + 16) >> 2;
  v8 = (unsigned __int64)v5[2];
  if ( v8 <= v7 )
  {
    v9 = (unsigned __int64)v5[3];
    if ( v9 != v7 )
    {
      if ( v9 < v7 )
      {
        v10 = 0x7FFFFFFFFFFFFFFELL;
        if ( 0x7FFFFFFFFFFFFFFELL - v8 < v7 - v8 )
          std::_Xlength_error("string too long");
        v11 = v9 >> 1;
        if ( v9 > 0x7FFFFFFFFFFFFFFELL - (v9 >> 1) )
        {
          v13 = -2;
        }
        else
        {
          v10 = v9 + v11;
          if ( (v7 | 7) >= v9 + v11 )
            v10 = v7 | 7;
          v12 = v10 + 1;
          if ( (unsigned __int64)(v10 + 1) > 0x7FFFFFFFFFFFFFFFLL )
            std::_Throw_bad_array_new_length();
          v13 = 2 * v12;
          if ( !(2 * v12) )
          {
            v14 = v4;
LABEL_12:
            a1[2] = v7;
            a1[3] = v10;
            if ( v9 > 7 )
            {
              v30 = (void *)*a1;
              _lambda_7f96eb1dcf99da5daec8c2467d2d5499_::operator()(v14, *a1, v8);
              std::_Deallocate<16>(v30, 2 * v9 + 2);
            }
            else
            {
              _lambda_7f96eb1dcf99da5daec8c2467d2d5499_::operator()(v14, a1, v8);
            }
            *a1 = v14;
            a1[2] = v8;
            v2 = v33;
            goto LABEL_15;
          }
        }
        if ( v13 < 0x1000 )
          v31 = operator new(v13);
        else
          v31 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v13);
        v14 = (unsigned __int64)v31;
        goto LABEL_12;
      }
      if ( v9 > 7 && v7 <= 7 )
      {
        v29 = *v5;
        memcpy_0(v5, *v5, 2 * v8 + 2);
        std::_Deallocate<16>(v29, 2 * a1[3] + 2);
        a1[3] = 7;
      }
    }
  }
LABEL_15:
  for ( i = 0; i < v7; ++i )
  {
    v32 = 0;
    v35[0] = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_istream<unsigned short>'};
    v36 = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_ostream<unsigned short>'};
    std::basic_ios<unsigned short>::basic_ios<unsigned short>(v41);
    v6 |= 2u;
    std::basic_iostream<unsigned short>::basic_iostream<unsigned short>(v35, &v37, 0);
    *(_QWORD *)((char *)v35 + *(int *)(v35[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
    *(_DWORD *)((char *)&v34[1] + *(int *)(v35[0] + 4LL) + 4) = *(_DWORD *)(v35[0] + 4LL) - 152;
    std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>(&v37);
    v37 = &std::basic_stringbuf<unsigned short>::`vftable';
    v39 = 0;
    v40 = 0;
    v16 = std::basic_ostream<unsigned short>::operator<<(&v36, std::hex);
    v17 = (_QWORD *)std::wstring::substr(v2, &v43, 4 * i, 4);
    v18 = v17[2];
    if ( v17[3] > 7u )
      v17 = (_QWORD *)*v17;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v16, v17, v18);
    if ( v44 > 7 )
      std::_Deallocate<16>(v43, 2 * v44 + 2);
    std::basic_istream<unsigned short>::operator>>(v35, &v32);
    v20 = v32;
    v21 = a1[2];
    v22 = a1[3];
    if ( v21 >= v22 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
        a1,
        v22,
        v19,
        (unsigned __int16)v32);
    }
    else
    {
      a1[2] = v21 + 1;
      if ( v22 <= 7 )
        v23 = a1;
      else
        v23 = (_QWORD *)*a1;
      v24 = (_WORD *)v23 + v21;
      *v24 = v20;
      v24[1] = 0;
    }
    *(_QWORD *)((char *)v35 + *(int *)(v35[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
    *(_DWORD *)((char *)&v34[1] + *(int *)(v35[0] + 4LL) + 4) = *(_DWORD *)(v35[0] + 4LL) - 152;
    v37 = &std::basic_stringbuf<unsigned short>::`vftable';
    if ( (v40 & 1) != 0 )
    {
      if ( std::basic_streambuf<unsigned short>::pptr(&v37) )
        v25 = std::basic_streambuf<unsigned short>::epptr(&v37);
      else
        v25 = std::basic_streambuf<unsigned short>::egptr(&v37);
      v26 = 2 * ((v25 - std::basic_streambuf<unsigned short>::eback(&v37)) >> 1);
      v33 = v26;
      v27 = (void *)std::basic_streambuf<unsigned short>::eback(&v37);
      v34[0] = v27;
      if ( v26 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(v34, &v33);
        v27 = v34[0];
      }
      operator delete(v27);
    }
    std::basic_streambuf<unsigned short>::setg(&v37, 0, 0, 0);
    std::basic_streambuf<unsigned short>::setp(&v37, 0, 0);
    v39 = 0;
    v40 &= ~1u;
    std::basic_streambuf<unsigned short>::~basic_streambuf<unsigned short,std::char_traits<unsigned short>>(&v37);
    std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v38);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v41);
  }
  return a1;
}

```

## disassembly

```asm
0x180005e00  mov     [rsp-8+arg_10], rbx
0x180005e05  push    rbp
0x180005e06  push    rsi
0x180005e07  push    rdi
0x180005e08  push    r12
0x180005e0a  push    r13
0x180005e0c  push    r14
0x180005e0e  push    r15
0x180005e10  lea     rbp, [rsp-70h]
0x180005e15  sub     rsp, 170h
0x180005e1c  mov     rax, cs:__security_cookie
0x180005e23  xor     rax, rsp
0x180005e26  mov     [rbp+0A0h+var_38], rax
0x180005e2a  mov     r15, rdx
0x180005e2d  mov     [rsp+1A0h+var_178], rdx
0x180005e32  mov     rdi, rcx
0x180005e35  mov     [rbp+0A0h+var_60], rcx
0x180005e39  xor     edx, edx
0x180005e3b  mov     [rsp+1A0h+var_180], edx; int
0x180005e3f  test    byte ptr [r15+10h], 3
0x180005e44  jnz     loc_180006216
0x180005e4a  xorps   xmm0, xmm0
0x180005e4d  movups  xmmword ptr [rcx], xmm0
0x180005e50  mov     [rcx+10h], rdx
0x180005e54  mov     [rcx+18h], rdx
0x180005e58  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180005e5d  mov     r13d, 1
0x180005e63  mov     [rsp+1A0h+var_180], r13d
0x180005e68  mov     r12, [r15+10h]
0x180005e6c  shr     r12, 2
0x180005e70  mov     r14, [rcx+10h]
0x180005e74  cmp     r14, r12
0x180005e77  ja      loc_180005F29
0x180005e7d  mov     rsi, [rcx+18h]
0x180005e81  cmp     rsi, r12
0x180005e84  jz      loc_180005F29
0x180005e8a  jnb     loc_1800061A3
0x180005e90  mov     rcx, r12
0x180005e93  sub     rcx, r14
0x180005e96  mov     rbx, 7FFFFFFFFFFFFFFEh
0x180005ea0  mov     rax, rbx
0x180005ea3  sub     rax, r14
0x180005ea6  cmp     rax, rcx
0x180005ea9  jb      loc_180006235
0x180005eaf  mov     rcx, rsi
0x180005eb2  shr     rcx, 1
0x180005eb5  mov     rax, rbx
0x180005eb8  sub     rax, rcx
0x180005ebb  cmp     rsi, rax
0x180005ebe  ja      loc_180006243
0x180005ec4  mov     rax, r12
0x180005ec7  or      rax, 7
0x180005ecb  lea     rbx, [rsi+rcx]
0x180005ecf  cmp     rax, rbx
0x180005ed2  cmovnb  rbx, rax
0x180005ed6  lea     rax, [rbx+1]
0x180005eda  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180005ee4  cmp     rax, rcx
0x180005ee7  ja      loc_18000625A
0x180005eed  lea     rcx, [rax+rax]
0x180005ef1  test    rcx, rcx
0x180005ef4  jnz     loc_18000624A
0x180005efa  mov     r15d, edx
0x180005efd  mov     [rdi+10h], r12
0x180005f01  mov     [rdi+18h], rbx
0x180005f05  mov     r8, r14
0x180005f08  mov     rcx, r15
0x180005f0b  cmp     rsi, 7
0x180005f0f  ja      loc_1800061F6
0x180005f15  mov     rdx, rdi
0x180005f18  call    ??R_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@SA@QEAGQEBG_K@Z; _lambda_7f96eb1dcf99da5daec8c2467d2d5499_::operator()(ushort * const,ushort const * const,unsigned __int64)
0x180005f1d  mov     [rdi], r15
0x180005f20  mov     [rdi+10h], r14
0x180005f24  mov     r15, [rsp+1A0h+var_178]
0x180005f29  xor     r14d, r14d
0x180005f2c  mov     esi, r14d
0x180005f2f  test    r12, r12
0x180005f32  jz      loc_180006171
0x180005f38  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_istream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_istream<ushort>'}
0x180005f3f  lea     rcx, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_ostream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_ostream<ushort>'}
0x180005f46  lea     rbx, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x180005f4d  nop     dword ptr [rax]
0x180005f50  mov     [rsp+1A0h+var_17C], r14d
0x180005f55  mov     [rsp+1A0h+var_160], rax
0x180005f5a  mov     [rsp+1A0h+var_150], rcx
0x180005f5f  lea     rcx, [rbp+0A0h+var_C8]
0x180005f63  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x180005f69  nop
0x180005f6a  or      r13d, 2
0x180005f6e  mov     [rsp+1A0h+var_180], r13d
0x180005f73  xor     r8d, r8d
0x180005f76  lea     rdx, [rsp+1A0h+var_148]
0x180005f7b  lea     rcx, [rsp+1A0h+var_160]
0x180005f80  call    cs:__imp_??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z; std::basic_iostream<ushort>::basic_iostream<ushort>(std::basic_streambuf<ushort> *)
0x180005f86  nop
0x180005f87  mov     rax, [rsp+1A0h+var_160]
0x180005f8c  movsxd  rcx, dword ptr [rax+4]
0x180005f90  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180005f97  mov     [rsp+rcx+1A0h+var_160], rax
0x180005f9c  mov     rax, [rsp+1A0h+var_160]
0x180005fa1  movsxd  rcx, dword ptr [rax+4]
0x180005fa5  lea     edx, [rcx-98h]
0x180005fab  mov     [rsp+rcx+1A0h+var_164], edx
0x180005faf  lea     rcx, [rsp+1A0h+var_148]
0x180005fb4  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x180005fba  mov     [rsp+1A0h+var_148], rbx
0x180005fbf  mov     [rbp+0A0h+var_E0], r14
0x180005fc3  mov     [rbp+0A0h+var_D8], r14d
0x180005fc7  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180005fce  lea     rcx, [rsp+1A0h+var_150]
0x180005fd3  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180005fd9  mov     rbx, rax
0x180005fdc  lea     r8, ds:0[rsi*4]
0x180005fe4  mov     r9d, 4
0x180005fea  lea     rdx, [rbp+0A0h+var_58]
0x180005fee  mov     rcx, r15
0x180005ff1  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180005ff6  nop
0x180005ff7  mov     r8, [rax+10h]
0x180005ffb  cmp     qword ptr [rax+18h], 7
0x180006000  jbe     short loc_180006005
0x180006002  mov     rax, [rax]
0x180006005  mov     rdx, rax
0x180006008  mov     rcx, rbx
0x18000600b  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180006010  nop
0x180006011  mov     rdx, [rbp+0A0h+var_40]
0x180006015  cmp     rdx, 7
0x180006019  ja      loc_18000626D
0x18000601f  lea     rdx, [rsp+1A0h+var_17C]
0x180006024  lea     rcx, [rsp+1A0h+var_160]
0x180006029  call    cs:__imp_??5?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@AEAI@Z; std::basic_istream<ushort>::operator>>(uint &)
0x18000602f  movzx   r9d, word ptr [rsp+1A0h+var_17C]
0x180006035  mov     rax, [rdi+10h]
0x180006039  mov     rdx, [rdi+18h]
0x18000603d  cmp     rax, rdx
0x180006040  jnb     loc_180006283
0x180006046  lea     rcx, [rax+1]
0x18000604a  mov     [rdi+10h], rcx
0x18000604e  cmp     rdx, 7
0x180006052  jbe     loc_18000619B
0x180006058  mov     rcx, [rdi]
0x18000605b  lea     rcx, [rcx+rax*2]
0x18000605f  mov     [rcx], r9w
0x180006063  mov     [rcx+2], r14w
0x180006068  mov     rax, [rsp+1A0h+var_160]
0x18000606d  movsxd  rcx, dword ptr [rax+4]
0x180006071  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180006078  mov     [rsp+rcx+1A0h+var_160], rax
0x18000607d  mov     rax, [rsp+1A0h+var_160]
0x180006082  movsxd  rcx, dword ptr [rax+4]
0x180006086  lea     edx, [rcx-98h]
0x18000608c  mov     [rsp+rcx+1A0h+var_164], edx
0x180006090  lea     rbx, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x180006097  mov     [rsp+1A0h+var_148], rbx
0x18000609c  test    byte ptr [rbp+0A0h+var_D8], 1
0x1800060a0  jz      short loc_18000610C
0x1800060a2  lea     rcx, [rsp+1A0h+var_148]
0x1800060a7  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x1800060ad  lea     rcx, [rsp+1A0h+var_148]
0x1800060b2  test    rax, rax
0x1800060b5  jz      loc_1800061EB
0x1800060bb  call    cs:__imp_?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::epptr(void)
0x1800060c1  mov     rbx, rax
0x1800060c4  lea     rcx, [rsp+1A0h+var_148]
0x1800060c9  call    cs:__imp_?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::eback(void)
0x1800060cf  sub     rbx, rax
0x1800060d2  sar     rbx, 1
0x1800060d5  add     rbx, rbx
0x1800060d8  mov     [rsp+1A0h+var_178], rbx
0x1800060dd  lea     rcx, [rsp+1A0h+var_148]
0x1800060e2  call    cs:__imp_?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::eback(void)
0x1800060e8  mov     [rsp+1A0h+var_170], rax
0x1800060ed  cmp     rbx, 1000h
0x1800060f4  jnb     loc_180006290
0x1800060fa  mov     rdx, rbx; unsigned __int64
0x1800060fd  mov     rcx, rax; void *
0x180006100  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006105  lea     rbx, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x18000610c  xor     r9d, r9d
0x18000610f  xor     r8d, r8d
0x180006112  xor     edx, edx
0x180006114  lea     rcx, [rsp+1A0h+var_148]
0x180006119  call    cs:__imp_?setg@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG00@Z; std::basic_streambuf<ushort>::setg(ushort *,ushort *,ushort *)
0x18000611f  xor     r8d, r8d
0x180006122  xor     edx, edx
0x180006124  lea     rcx, [rsp+1A0h+var_148]
0x180006129  call    cs:__imp_?setp@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG0@Z; std::basic_streambuf<ushort>::setp(ushort *,ushort *)
0x18000612f  mov     [rbp+0A0h+var_E0], r14
0x180006133  and     [rbp+0A0h+var_D8], 0FFFFFFFEh
0x180006137  lea     rcx, [rsp+1A0h+var_148]
0x18000613c  call    cs:__imp_??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_streambuf<ushort>::~basic_streambuf<ushort,std::char_traits<ushort>>(void)
0x180006142  lea     rcx, [rsp+1A0h+var_140]
0x180006147  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x18000614d  lea     rcx, [rbp+0A0h+var_C8]
0x180006151  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180006157  inc     rsi
0x18000615a  cmp     rsi, r12
0x18000615d  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_istream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_istream<ushort>'}
0x180006164  lea     rcx, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_ostream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_ostream<ushort>'}
0x18000616b  jb      loc_180005F50
0x180006171  mov     rax, rdi
0x180006174  mov     rcx, [rbp+0A0h+var_38]
0x180006178  xor     rcx, rsp; StackCookie
0x18000617b  call    __security_check_cookie
0x180006180  mov     rbx, [rsp+1A0h+arg_10]
0x180006188  add     rsp, 170h
0x18000618f  pop     r15
0x180006191  pop     r14
0x180006193  pop     r13
0x180006195  pop     r12
0x180006197  pop     rdi
0x180006198  pop     rsi
0x180006199  pop     rbp
0x18000619a  retn
0x18000619b  mov     rcx, rdi
0x18000619e  jmp     loc_18000605B
0x1800061a3  cmp     rsi, 7
0x1800061a7  jbe     loc_180005F29
0x1800061ad  cmp     r12, 7
0x1800061b1  ja      loc_180005F29
0x1800061b7  mov     rbx, [rcx]
0x1800061ba  lea     r8, ds:2[r14*2]; Size
0x1800061c2  mov     rdx, rbx; Src
0x1800061c5  call    memcpy_0
0x1800061ca  mov     rdx, [rdi+18h]
0x1800061ce  lea     rdx, ds:2[rdx*2]
0x1800061d6  mov     rcx, rbx
0x1800061d9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800061de  mov     qword ptr [rdi+18h], 7
0x1800061e6  jmp     loc_180005F29
0x1800061eb  call    cs:__imp_?egptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::egptr(void)
0x1800061f1  jmp     loc_1800060C1
0x1800061f6  mov     rbx, [rdi]
0x1800061f9  mov     rdx, rbx
0x1800061fc  call    ??R_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@SA@QEAGQEBG_K@Z; _lambda_7f96eb1dcf99da5daec8c2467d2d5499_::operator()(ushort * const,ushort const * const,unsigned __int64)
0x180006201  lea     rdx, ds:2[rsi*2]
0x180006209  mov     rcx, rbx
0x18000620c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006211  jmp     loc_180005F1D
0x180006216  mov     rcx, [rbp+0A8h]; this
0x18000621d  mov     r9d, 80070057h; char *
0x180006223  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18000622a  mov     edx, 0E0h; void *
0x18000622f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180006235  lea     rcx, aStringTooLong; "string too long"
0x18000623c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180006243  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x18000624a  cmp     rcx, 1000h
0x180006251  jb      short loc_180006260
0x180006253  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180006258  jmp     short loc_180006265
0x18000625a  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180006260  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006265  mov     r15, rax
0x180006268  jmp     loc_180005EFD
0x18000626d  lea     rdx, ds:2[rdx*2]
0x180006275  mov     rcx, [rbp+0A0h+var_58]
0x180006279  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000627e  jmp     loc_18000601F
0x180006283  mov     rcx, rdi
0x180006286  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18000628b  jmp     loc_180006068
0x180006290  lea     rdx, [rsp+1A0h+var_178]; unsigned __int64 *
0x180006295  lea     rcx, [rsp+1A0h+var_170]; void **
0x18000629a  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000629f  mov     rax, [rsp+1A0h+var_170]
0x1800062a4  mov     rbx, [rsp+1A0h+var_178]
0x1800062a9  jmp     loc_1800060FA
```
