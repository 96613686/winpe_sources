# Spectre::Transcoder::StlBinaryParser::ParseStream(std::shared_ptr<std::basic_istream<char,std::char_traits<char>>>)

- ea: `0x180371cb0`
- end: `0x1803720c7`
- name: `?ParseStream@StlBinaryParser@Transcoder@Spectre@@QEAA?AV?$shared_ptr@VAsset3D@Transcoder@Spectre@@@std@@V?$shared_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@@5@@Z`
- size: `1047`
- prototype: `__int64 *__fastcall(__int64, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1803493d0`

## callees

- `0x1800153c0`
- `0x180015770`
- `0x1800271c0`
- `0x180039e40`
- `0x1801cd320`
- `0x1801d6b50`
- `0x18020bd60`
- `0x180351310`
- `0x180371cb0`
- `0x1803720d0`
- `0x180372500`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039f8e0`
- `0x18039f910`
- `0x180493760`
- `0x180494040`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180371dd1`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180371dd1`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z` at `0x180371fe2`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z` at `0x180371ffd`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z` at `0x180371fe2`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z` at `0x180371ffd`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180371d0e`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180371d2a`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180371d0e`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180371d2a`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180371cfe`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180371d1d`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180371d9f`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180371cfe`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180371d1d`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180371d9f`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x180371d4c`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x180371d4c`

## string_xrefs

- `0x180372095`: `Cannot read the triangle number`

## pseudocode

```c
__int64 *__fastcall Spectre::Transcoder::StlBinaryParser::ParseStream(__int64 a1, __int64 *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  __int64 v7; // r12
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rcx
  Spectre::Transcoder::UpdateReporter *v11; // rcx
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  _DWORD *v14; // rax
  _DWORD *v15; // rbx
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rdi
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int128 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v25; // [rsp+50h] [rbp-B0h]
  _QWORD *v26; // [rsp+58h] [rbp-A8h]
  __int128 v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h]
  _BYTE pExceptionObject[80]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v30; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v31; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v32; // [rsp+E0h] [rbp-20h]
  __int128 v33; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v34; // [rsp+108h] [rbp+8h]
  _BYTE v35[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v36[240]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v37[400]; // [rsp+210h] [rbp+110h] BYREF

  v25 = a2;
  v26 = a3;
  std::istream::seekg(*a3, 0, 0);
  v6 = *a3;
  std::istream::tellg(*a3, &v33);
  std::istream::seekg(v6, 0, 2);
  std::istream::tellg(v6, &v31);
  v27 = v33;
  v28 = v34;
  std::istream::seekg(v6, &v27);
  v7 = v32 + v31;
  if ( (unsigned __int64)(v32 + v31) < 0x86 )
  {
    std::string::string(&v31, "The file contains no data.");
    Spectre::Utils::SpectreException::SpectreException(pExceptionObject, &v31, 0);
    throw (Spectre::Utils::SpectreException *)pExceptionObject;
  }
  v23 = 0;
  v8 = a3[1];
  if ( v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    v8 = a3[1];
  }
  *(_QWORD *)&v23 = *a3;
  *((_QWORD *)&v23 + 1) = v8;
  std::istream::seekg(v23, 80, 0);
  if ( *(_DWORD *)(*(int *)(*(_QWORD *)v23 + 4LL) + (_QWORD)v23 + 16LL) )
  {
    std::string::string(&v31, "Cannot seek past the header");
    Spectre::Utils::SpectreException::SpectreException(pExceptionObject, &v31, 0);
    throw (Spectre::Utils::SpectreException *)pExceptionObject;
  }
  v30 = 0;
  std::istream::read(v23, &v30, 4);
  if ( *(_QWORD *)(v23 + 8) != 4 )
  {
    std::string::string(&v31, "Cannot read the triangle number");
    Spectre::Utils::SpectreException::SpectreException(pExceptionObject, &v31, 0);
    throw (Spectre::Utils::SpectreException *)pExceptionObject;
  }
  v9 = v30;
  std::shared_ptr<std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>>::~shared_ptr<std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>>(&v23);
  if ( 50 * v9 + 84 != v7 )
  {
    std::shared_ptr<Spectre::Utils::ITelemetryTraceLogger>::__autoclassinit2(v35, 248);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(
      v35,
      1);
    v19 = std::operator<<<std::char_traits<char>>(v36, "The file does not have the expected size. Expected: ");
    v20 = std::ostream::operator<<(v19, 50 * v9 + 84);
    v21 = std::operator<<<std::char_traits<char>>(v20, " Actual: ");
    std::ostream::operator<<(v21, v7);
    v22 = std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v35, &v31);
    Spectre::Utils::SpectreException::SpectreException(pExceptionObject, v22, 0);
    throw (Spectre::Utils::SpectreException *)pExceptionObject;
  }
  memset_0(v37, 0, sizeof(v37));
  v24 = 0;
  v10 = a3[1];
  if ( v10 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    v10 = a3[1];
  }
  *(_QWORD *)&v24 = *a3;
  *((_QWORD *)&v24 + 1) = v10;
  Spectre::Transcoder::StlBinaryParser::ReadGeometry(a1, v37, &v24, (unsigned int)v9, &v23, 0);
  v11 = *(Spectre::Transcoder::UpdateReporter **)(a1 + 8);
  if ( v11 )
    Spectre::Transcoder::UpdateReporter::ReportCompletedParsing(v11, 1.0);
  *(_OWORD *)a2 = 0;
  v12 = operator new(0x1C8u);
  v13 = v12;
  if ( v12 )
  {
    *(_OWORD *)v12 = 0;
    v12[2] = 1;
    v12[3] = 1;
    *(_QWORD *)v12 = &std::_Ref_count_obj2<Spectre::Transcoder::Asset3D>::`vftable';
    Spectre::Transcoder::Asset3D::Asset3D((Spectre::Transcoder::Asset3D *)(v12 + 4));
  }
  else
  {
    v13 = 0;
  }
  *(_OWORD *)a2 = 0;
  *a2 = (__int64)(v13 + 4);
  a2[1] = (__int64)v13;
  v14 = operator new(0xC0u);
  v15 = v14;
  if ( v14 )
  {
    *(_OWORD *)v14 = 0;
    v14[2] = 1;
    v14[3] = 1;
    *(_QWORD *)v14 = &std::_Ref_count_obj2<Spectre::Transcoder::Mesh>::`vftable';
    Spectre::Transcoder::Mesh::Mesh(v14 + 4, v37);
  }
  else
  {
    v15 = 0;
  }
  v16 = *a2;
  *(_QWORD *)(v16 + 216) = v15 + 4;
  v17 = *(volatile signed __int32 **)(v16 + 224);
  *(_QWORD *)(v16 + 224) = v15;
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  Spectre::Transcoder::Geometry::~Geometry((Spectre::Transcoder::Geometry *)v37);
  std::shared_ptr<std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>>::~shared_ptr<std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>>(a3);
  return a2;
}

```

## disassembly

```asm
0x180371cb0  push    rbp
0x180371cb2  push    rbx
0x180371cb3  push    rsi
0x180371cb4  push    rdi
0x180371cb5  push    r12
0x180371cb7  push    r14
0x180371cb9  push    r15
0x180371cbb  lea     rbp, [rsp-2B0h]
0x180371cc3  sub     rsp, 3B0h
0x180371cca  mov     rax, cs:__security_cookie
0x180371cd1  xor     rax, rsp
0x180371cd4  mov     [rbp+2E0h+var_40], rax
0x180371cdb  mov     rsi, r8
0x180371cde  mov     r14, rdx
0x180371ce1  mov     r15, rcx
0x180371ce4  mov     [rsp+3E0h+var_390], rdx
0x180371ce9  mov     [rsp+3E0h+var_388], r8
0x180371cee  mov     [rsp+3E0h+var_3B8], 0
0x180371cf6  xor     r8d, r8d
0x180371cf9  xor     edx, edx
0x180371cfb  mov     rcx, [rsi]
0x180371cfe  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x180371d04  mov     rbx, [rsi]
0x180371d07  lea     rdx, [rbp+2E0h+var_2E8]
0x180371d0b  mov     rcx, rbx
0x180371d0e  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x180371d14  xor     edx, edx
0x180371d16  lea     r8d, [rdx+2]
0x180371d1a  mov     rcx, rbx
0x180371d1d  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x180371d23  lea     rdx, [rbp+2E0h+var_308]
0x180371d27  mov     rcx, rbx
0x180371d2a  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x180371d30  movups  xmm0, [rbp+2E0h+var_2E8]
0x180371d34  movaps  [rsp+3E0h+var_380], xmm0
0x180371d39  movsd   xmm1, [rbp+2E0h+var_2D8]
0x180371d3e  movsd   [rsp+3E0h+var_370], xmm1
0x180371d44  lea     rdx, [rsp+3E0h+var_380]
0x180371d49  mov     rcx, rbx
0x180371d4c  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x180371d52  mov     r12, [rbp+2E0h+var_308]
0x180371d56  add     r12, [rbp+2E0h+var_300]
0x180371d5a  cmp     r12, 86h
0x180371d61  jb      loc_180372031
0x180371d67  xorps   xmm0, xmm0
0x180371d6a  movdqu  [rsp+3E0h+var_3B0], xmm0
0x180371d70  mov     rax, [rsi+8]
0x180371d74  test    rax, rax
0x180371d77  jz      short loc_180371D81
0x180371d79  lock inc dword ptr [rax+8]
0x180371d7d  mov     rax, [rsi+8]
0x180371d81  mov     rcx, [rsi]
0x180371d84  mov     qword ptr [rsp+3E0h+var_3B0], rcx
0x180371d89  mov     qword ptr [rsp+3E0h+var_3B0+8], rax
0x180371d8e  lea     rax, [rsp+3E0h+var_3B0]
0x180371d93  mov     [rsp+3E0h+var_3C0], rax
0x180371d98  xor     r8d, r8d
0x180371d9b  lea     edx, [r8+50h]
0x180371d9f  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x180371da5  mov     r9, qword ptr [rsp+3E0h+var_3B0]
0x180371daa  mov     rax, [r9]
0x180371dad  movsxd  rcx, dword ptr [rax+4]
0x180371db1  cmp     dword ptr [rcx+r9+10h], 0
0x180371db7  jnz     loc_180372063
0x180371dbd  mov     [rbp+2E0h+var_310], 0
0x180371dc4  mov     r8d, 4
0x180371dca  lea     rdx, [rbp+2E0h+var_310]
0x180371dce  mov     rcx, r9
0x180371dd1  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x180371dd7  mov     rax, qword ptr [rsp+3E0h+var_3B0]
0x180371ddc  cmp     qword ptr [rax+8], 4
0x180371de1  jnz     loc_180372095
0x180371de7  mov     edi, [rbp+2E0h+var_310]
0x180371dea  lea     rcx, [rsp+3E0h+var_3B0]; void *
0x180371def  call    ??1?$shared_ptr@V?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>>::~shared_ptr<std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>>(void)
0x180371df4  imul    rbx, rdi, 32h ; '2'
0x180371df8  add     rbx, 54h ; 'T'
0x180371dfc  cmp     rbx, r12
0x180371dff  jnz     loc_180371FAF
0x180371e05  xor     edx, edx; Val
0x180371e07  mov     r8d, 190h; Size
0x180371e0d  lea     rcx, [rbp+2E0h+var_1D0]; void *
0x180371e14  call    memset_0
0x180371e19  xorps   xmm0, xmm0
0x180371e1c  movdqu  [rsp+3E0h+var_3A0], xmm0
0x180371e22  mov     rcx, [rsi+8]
0x180371e26  test    rcx, rcx
0x180371e29  jz      short loc_180371E33
0x180371e2b  lock inc dword ptr [rcx+8]
0x180371e2f  mov     rcx, [rsi+8]
0x180371e33  mov     rax, [rsi]
0x180371e36  mov     qword ptr [rsp+3E0h+var_3A0], rax
0x180371e3b  mov     qword ptr [rsp+3E0h+var_3A0+8], rcx
0x180371e40  mov     r9d, edi
0x180371e43  lea     r8, [rsp+3E0h+var_3A0]
0x180371e48  lea     rdx, [rbp+2E0h+var_1D0]
0x180371e4f  mov     rcx, r15
0x180371e52  call    ?ReadGeometry@StlBinaryParser@Transcoder@Spectre@@AEAA?AVGeometry@23@V?$shared_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@@std@@I@Z; Spectre::Transcoder::StlBinaryParser::ReadGeometry(std::shared_ptr<std::istream>,uint)
0x180371e57  nop
0x180371e58  mov     rcx, [r15+8]; this
0x180371e5c  test    rcx, rcx
0x180371e5f  jz      short loc_180371E6E
0x180371e61  movss   xmm1, cs:__real@3f800000; float
0x180371e69  call    ?ReportCompletedParsing@UpdateReporter@Transcoder@Spectre@@QEAAXM@Z; Spectre::Transcoder::UpdateReporter::ReportCompletedParsing(float)
0x180371e6e  xorps   xmm0, xmm0
0x180371e71  movups  xmmword ptr [r14], xmm0
0x180371e75  mov     ecx, 1C8h; Size
0x180371e7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180371e7f  mov     rbx, rax
0x180371e82  mov     [rsp+3E0h+var_3C0], rax
0x180371e87  test    rax, rax
0x180371e8a  jz      short loc_180371EB5
0x180371e8c  xorps   xmm0, xmm0
0x180371e8f  movups  xmmword ptr [rax], xmm0
0x180371e92  mov     dword ptr [rax+8], 1
0x180371e99  mov     dword ptr [rax+0Ch], 1
0x180371ea0  lea     rax, ??_7?$_Ref_count_obj2@VAsset3D@Transcoder@Spectre@@@std@@6B@; const std::_Ref_count_obj2<Spectre::Transcoder::Asset3D>::`vftable'
0x180371ea7  mov     [rbx], rax
0x180371eaa  lea     rcx, [rbx+10h]; this
0x180371eae  call    ??0Asset3D@Transcoder@Spectre@@QEAA@XZ; Spectre::Transcoder::Asset3D::Asset3D(void)
0x180371eb3  jmp     short loc_180371EB7
0x180371eb5  xor     ebx, ebx
0x180371eb7  xorps   xmm0, xmm0
0x180371eba  movups  xmmword ptr [r14], xmm0
0x180371ebe  lea     rax, [rbx+10h]
0x180371ec2  mov     [r14], rax
0x180371ec5  mov     [r14+8], rbx
0x180371ec9  mov     [rsp+3E0h+var_3B8], 3
0x180371ed1  mov     ecx, 0C0h; Size
0x180371ed6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180371edb  mov     rbx, rax
0x180371ede  mov     [rsp+3E0h+var_3C0], rax
0x180371ee3  test    rax, rax
0x180371ee6  jz      short loc_180371F18
0x180371ee8  xorps   xmm0, xmm0
0x180371eeb  movups  xmmword ptr [rax], xmm0
0x180371eee  mov     dword ptr [rax+8], 1
0x180371ef5  mov     dword ptr [rax+0Ch], 1
0x180371efc  lea     rax, ??_7?$_Ref_count_obj2@VMesh@Transcoder@Spectre@@@std@@6B@; const std::_Ref_count_obj2<Spectre::Transcoder::Mesh>::`vftable'
0x180371f03  mov     [rbx], rax
0x180371f06  lea     rcx, [rbx+10h]
0x180371f0a  lea     rdx, [rbp+2E0h+var_1D0]
0x180371f11  call    ??0Mesh@Transcoder@Spectre@@QEAA@$$QEAVGeometry@12@@Z; Spectre::Transcoder::Mesh::Mesh(Spectre::Transcoder::Geometry &&)
0x180371f16  jmp     short loc_180371F1A
0x180371f18  xor     ebx, ebx
0x180371f1a  lea     rax, [rbx+10h]
0x180371f1e  mov     rcx, [r14]
0x180371f21  mov     [rcx+0D8h], rax
0x180371f28  mov     rdi, [rcx+0E0h]
0x180371f2f  mov     [rcx+0E0h], rbx
0x180371f36  test    rdi, rdi
0x180371f39  jz      short loc_180371F76
0x180371f3b  mov     ebx, 0FFFFFFFFh
0x180371f40  mov     eax, ebx
0x180371f42  lock xadd [rdi+8], eax
0x180371f47  cmp     eax, 1
0x180371f4a  jnz     short loc_180371F76
0x180371f4c  mov     rax, [rdi]
0x180371f4f  mov     rcx, rdi
0x180371f52  mov     rax, [rax]
0x180371f55  call    cs:__guard_dispatch_icall_fptr
0x180371f5b  lock xadd [rdi+0Ch], ebx
0x180371f60  cmp     ebx, 1
0x180371f63  jnz     short loc_180371F76
0x180371f65  mov     rdx, [rdi]
0x180371f68  mov     rcx, rdi
0x180371f6b  mov     rax, [rdx+8]
0x180371f6f  call    cs:__guard_dispatch_icall_fptr
0x180371f75  nop
0x180371f76  lea     rcx, [rbp+2E0h+var_1D0]; this
0x180371f7d  call    ??1Geometry@Transcoder@Spectre@@UEAA@XZ; Spectre::Transcoder::Geometry::~Geometry(void)
0x180371f82  nop
0x180371f83  mov     rcx, rsi; void *
0x180371f86  call    ??1?$shared_ptr@V?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>>::~shared_ptr<std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>>(void)
0x180371f8b  mov     rax, r14
0x180371f8e  mov     rcx, [rbp+2E0h+var_40]
0x180371f95  xor     rcx, rsp; StackCookie
0x180371f98  call    __security_check_cookie
0x180371f9d  add     rsp, 3B0h
0x180371fa4  pop     r15
0x180371fa6  pop     r14
0x180371fa8  pop     r12
0x180371faa  pop     rdi
0x180371fab  pop     rsi
0x180371fac  pop     rbx
0x180371fad  pop     rbp
0x180371fae  retn
0x180371faf  mov     edx, 0F8h
0x180371fb4  lea     rcx, [rbp+2E0h+var_2D0]
0x180371fb8  call    ?__autoclassinit2@?$shared_ptr@VITelemetryTraceLogger@Utils@Spectre@@@std@@QEAAX_K@Z; std::shared_ptr<Spectre::Utils::ITelemetryTraceLogger>::__autoclassinit2(unsigned __int64)
0x180371fbd  mov     edx, 1
0x180371fc2  lea     rcx, [rbp+2E0h+var_2D0]
0x180371fc6  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180371fcb  nop
0x180371fcc  lea     rdx, aTheFileDoesNot; "The file does not have the expected siz"...
0x180371fd3  lea     rcx, [rbp+2E0h+var_2C0]
0x180371fd7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180371fdc  mov     rcx, rax
0x180371fdf  mov     rdx, rbx
0x180371fe2  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z; std::ostream::operator<<(unsigned __int64)
0x180371fe8  mov     rcx, rax
0x180371feb  lea     rdx, aActual; " Actual: "
0x180371ff2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180371ff7  mov     rcx, rax
0x180371ffa  mov     rdx, r12
0x180371ffd  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z; std::ostream::operator<<(unsigned __int64)
0x180372003  lea     rdx, [rbp+2E0h+var_308]
0x180372007  lea     rcx, [rbp+2E0h+var_2D0]
0x18037200b  call    ?str@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x180372010  nop
0x180372011  xor     r8d, r8d
0x180372014  mov     rdx, rax
0x180372017  lea     rcx, [rbp+2E0h+pExceptionObject]
0x18037201b  call    ??0SpectreException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreException::SpectreException(std::string const &,bool)
0x180372020  lea     rdx, _TI3?AUSpectreException@Utils@Spectre@@; pThrowInfo
0x180372027  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x18037202b  call    _CxxThrowException_0
0x180372031  lea     rdx, aTheFileContain; "The file contains no data."
0x180372038  lea     rcx, [rbp+2E0h+var_308]
0x18037203c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180372041  nop
0x180372042  xor     r8d, r8d
0x180372045  lea     rdx, [rbp+2E0h+var_308]
0x180372049  lea     rcx, [rbp+2E0h+pExceptionObject]
0x18037204d  call    ??0SpectreException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreException::SpectreException(std::string const &,bool)
0x180372052  lea     rdx, _TI3?AUSpectreException@Utils@Spectre@@; pThrowInfo
0x180372059  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x18037205d  call    _CxxThrowException_0
0x180372063  lea     rdx, aCannotSeekPast; "Cannot seek past the header"
0x18037206a  lea     rcx, [rbp+2E0h+var_308]
0x18037206e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180372073  nop
0x180372074  xor     r8d, r8d
0x180372077  lea     rdx, [rbp+2E0h+var_308]
0x18037207b  lea     rcx, [rbp+2E0h+pExceptionObject]
0x18037207f  call    ??0SpectreException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreException::SpectreException(std::string const &,bool)
0x180372084  lea     rdx, _TI3?AUSpectreException@Utils@Spectre@@; pThrowInfo
0x18037208b  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x18037208f  call    _CxxThrowException_0
0x180372095  lea     rdx, aCannotReadTheT; "Cannot read the triangle number"
0x18037209c  lea     rcx, [rbp+2E0h+var_308]
0x1803720a0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1803720a5  nop
0x1803720a6  xor     r8d, r8d
0x1803720a9  lea     rdx, [rbp+2E0h+var_308]
0x1803720ad  lea     rcx, [rbp+2E0h+pExceptionObject]
0x1803720b1  call    ??0SpectreException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreException::SpectreException(std::string const &,bool)
0x1803720b6  lea     rdx, _TI3?AUSpectreException@Utils@Spectre@@; pThrowInfo
0x1803720bd  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x1803720c1  call    _CxxThrowException_0
```
