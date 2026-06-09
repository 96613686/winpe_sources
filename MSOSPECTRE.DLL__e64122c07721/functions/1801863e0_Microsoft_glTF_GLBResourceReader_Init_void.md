# Microsoft::glTF::GLBResourceReader::Init(void)

- ea: `0x1801863e0`
- end: `0x180186964`
- name: `?Init@GLBResourceReader@glTF@Microsoft@@AEAAXXZ`
- size: `1412`
- prototype: `void __fastcall(Microsoft::glTF::GLBResourceReader *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801856d0`

## callees

- `0x180015770`
- `0x18001ebf0`
- `0x180021570`
- `0x180027ff0`
- `0x180029b60`
- `0x180029bd0`
- `0x180029f10`
- `0x18002b810`
- `0x18008f520`
- `0x180184d40`
- `0x1801863e0`
- `0x180186970`
- `0x1801872c0`
- `0x18039e5b0`
- `0x18039ebb0`
- `0x18039f8e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180186488`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1801864b2`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1801864dc`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1801865cc`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180186488`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1801864b2`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1801864dc`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1801865cc`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180186428`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180186449`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18018667a`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180186428`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180186449`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18018667a`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180186438`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180186438`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x180186473`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x18018658f`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x180186473`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x18018658f`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x180186536`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x180186536`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18018662d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18018662d`

## string_xrefs

- `0x180186727`: `Cannot read the binary data`
- `0x180186748`: `Cannot read the binary data`
- `0x180186908`: `Cannot read the binary data`
- `0x1801866f2`: `Cannot read the magic number`
- `0x18018679e`: `JSON chunk should appear first`
- `0x1801866b7`: `File length does not match sum of length of component chunks`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::glTF::GLBResourceReader::Init(Microsoft::glTF::GLBResourceReader *this)
{
  _DWORD *v2; // rax
  int v3; // edi
  __int64 v4; // rbx
  __int64 v5; // rbx
  unsigned int v6; // ebx
  unsigned int v7; // r14d
  __int64 v8; // rdi
  void **v9; // rdx
  void *v10; // rcx
  unsigned int v11; // ebx
  int v12; // edi
  _QWORD *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned int v24; // [rsp+20h] [rbp-E0h] BYREF
  char Str1[4]; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int v26; // [rsp+28h] [rbp-D8h] BYREF
  int v27; // [rsp+2Ch] [rbp-D4h]
  __int128 v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h]
  __int128 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h]
  _OWORD v32[2]; // [rsp+70h] [rbp-90h]
  __int128 v33; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h]
  _BYTE v35[24]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v36[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v37[24]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v38[24]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v39[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v40[24]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v41[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v42[24]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v43[24]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v44[24]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v46[24]; // [rsp+1B8h] [rbp+B8h] BYREF
  char v47[24]; // [rsp+1D0h] [rbp+D0h] BYREF
  void *Block[3]; // [rsp+1E8h] [rbp+E8h] BYREF
  unsigned __int64 v49; // [rsp+200h] [rbp+100h]
  _BYTE v50[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v51[32]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v52[32]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v53[32]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v54[32]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v55[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  char v56[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  char v57[32]; // [rsp+2E8h] [rbp+1E8h] BYREF
  char v58[32]; // [rsp+308h] [rbp+208h] BYREF
  char v59[32]; // [rsp+328h] [rbp+228h] BYREF
  char v60[32]; // [rsp+348h] [rbp+248h] BYREF
  char v61[32]; // [rsp+368h] [rbp+268h] BYREF
  char v62[32]; // [rsp+388h] [rbp+288h] BYREF
  char v63[32]; // [rsp+3A8h] [rbp+2A8h] BYREF
  char v64[32]; // [rsp+3C8h] [rbp+2C8h] BYREF
  char v65[32]; // [rsp+3E8h] [rbp+2E8h] BYREF

  v27 = 0;
  std::istream::tellg(*((_QWORD *)this + 6), &v28);
  std::istream::seekg(*((_QWORD *)this + 6), 0, 2);
  v2 = (_DWORD *)std::istream::tellg(*((_QWORD *)this + 6), v46);
  v3 = *v2 + v2[2];
  v30 = v28;
  v31 = v29;
  std::istream::seekg(*((_QWORD *)this + 6), &v30);
  std::istream::read(*((_QWORD *)this + 6), Str1, 4);
  v4 = *((_QWORD *)this + 6);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v4 + 4LL) + v4 + 16) & 6) != 0 )
  {
    std::string::string(v50, "Cannot read the magic number");
    Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(v35, v50);
    throw (Microsoft::glTF::InvalidGLTFException *)v35;
  }
  std::istream::read(*((_QWORD *)this + 6), &v26, 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v4 + 4LL) + v4 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v36, "Cannot read the binary data");
    throw (std::runtime_error *)v36;
  }
  v5 = *((_QWORD *)this + 6);
  std::istream::read(v5, &v24, 4);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v5 + 4LL) + v5 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v37, "Cannot read the binary data");
    throw (std::runtime_error *)v37;
  }
  v6 = v24;
  if ( v3 != v24 )
  {
    std::string::string(v51, "File-reported file length does not match actual file length");
    Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(v38, v51);
    throw (Microsoft::glTF::InvalidGLTFException *)v38;
  }
  v7 = Microsoft::glTF::StreamUtils::ReadBinary<unsigned int>(*((_QWORD *)this + 6));
  if ( !(unsigned __int8)sub_180186970("JSON", *((_QWORD *)this + 6)) )
  {
    std::string::string(v52, "JSON chunk should appear first");
    Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(v39, v52);
    throw (Microsoft::glTF::InvalidGLTFException *)v39;
  }
  if ( strncmp(Str1, "glTF", 4u) )
  {
    std::string::string(v53, "Cannot find GLB magic bytes");
    Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(v40, v53);
    throw (Microsoft::glTF::InvalidGLTFException *)v40;
  }
  if ( v26 != 2 )
  {
    v14 = std::to_string(v56, v26);
    v15 = std::operator+<char>(v57, "Unsupported GLB Version: ", v14);
    Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(v41, v15);
    throw (Microsoft::glTF::InvalidGLTFException *)v41;
  }
  _mm_lfence();
  if ( v6 < v7 + 20 )
  {
    v16 = std::to_string(v58);
    v17 = std::to_string(v59, v7);
    v18 = std::to_string(v60, v24);
    v19 = std::operator+<char>(v61, "File length ", v18);
    v20 = std::operator+<char>(v62, v19, " less than content length ");
    v21 = std::operator+<char>(v63, v20, v17);
    v22 = std::operator+<char>(v64, v21, " plus header length ");
    v23 = std::operator+<char>(v65, v22, v16);
    Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(v42, v23);
    throw (Microsoft::glTF::InvalidGLTFException *)v42;
  }
  v8 = *((_QWORD *)this + 6);
  v32[0] = 0x14u;
  v33 = 0x14u;
  v34 = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)((char *)v32 + 8), *(__m128d *)((char *)v32 + 8));
  std::istream::seekg(v8, &v33);
  std::string::string(Block, v7, 0);
  v27 = 1;
  v9 = Block;
  if ( v49 >= 0x10 )
    v9 = (void **)Block[0];
  std::istream::read(v8, v9, v7);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v8 + 4LL) + v8 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v43, "Cannot read the binary data");
    throw (std::runtime_error *)v43;
  }
  std::string::operator=((char *)this + 16, Block);
  if ( v49 >= 0x10 )
  {
    v10 = Block[0];
    if ( v49 + 1 >= 0x1000 )
    {
      v10 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v10);
  }
  v11 = v24;
  if ( v24 != v7 + 20 )
  {
    v12 = Microsoft::glTF::StreamUtils::ReadBinary<unsigned int>(*((_QWORD *)this + 6));
    if ( !(unsigned __int8)sub_180186970("BIN", *((_QWORD *)this + 6)) )
    {
      std::string::string(v54, "Binary chunk should appear second");
      Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(v44, v54);
      throw (Microsoft::glTF::InvalidGLTFException *)v44;
    }
    if ( v12 + v7 + 28 != v11 )
    {
      std::string::string(v55, "File length does not match sum of length of component chunks");
      Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(pExceptionObject, v55);
      throw (Microsoft::glTF::InvalidGLTFException *)pExceptionObject;
    }
    v13 = (_QWORD *)std::istream::tellg(*((_QWORD *)this + 6), v47);
    *((_QWORD *)this + 8) = *v13 + v13[1];
  }
}

```

## disassembly

```asm
0x1801863e0  mov     [rsp-8+arg_8], rbx
0x1801863e5  mov     [rsp-8+arg_10], rsi
0x1801863ea  mov     [rsp-8+arg_18], rdi
0x1801863ef  push    rbp
0x1801863f0  push    r14
0x1801863f2  push    r15
0x1801863f4  lea     rbp, [rsp-310h]
0x1801863fc  sub     rsp, 410h
0x180186403  mov     rax, cs:__security_cookie
0x18018640a  xor     rax, rsp
0x18018640d  mov     [rbp+320h+var_18], rax
0x180186414  mov     rsi, rcx
0x180186417  mov     [rsp+420h+var_3F4], 0
0x18018641f  lea     rdx, [rsp+420h+var_3F0]
0x180186424  mov     rcx, [rcx+30h]
0x180186428  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x18018642e  xor     edx, edx
0x180186430  lea     r8d, [rdx+2]
0x180186434  mov     rcx, [rsi+30h]
0x180186438  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18018643e  lea     rdx, [rbp+320h+var_268]
0x180186445  mov     rcx, [rsi+30h]
0x180186449  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x18018644f  mov     edi, [rax+8]
0x180186452  add     edi, [rax]
0x180186454  movups  xmm0, [rsp+420h+var_3F0]
0x180186459  movaps  [rsp+420h+var_3D0], xmm0
0x18018645e  movsd   xmm1, [rsp+420h+var_3E0]
0x180186464  movsd   [rsp+420h+var_3C0], xmm1
0x18018646a  lea     rdx, [rsp+420h+var_3D0]
0x18018646f  mov     rcx, [rsi+30h]
0x180186473  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x180186479  mov     r8d, 4
0x18018647f  lea     rdx, [rsp+420h+Str1]
0x180186484  mov     rcx, [rsi+30h]
0x180186488  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18018648e  mov     rbx, [rsi+30h]
0x180186492  mov     rax, [rbx]
0x180186495  movsxd  rcx, dword ptr [rax+4]
0x180186499  test    byte ptr [rcx+rbx+10h], 6
0x18018649e  jnz     loc_1801866F2
0x1801864a4  mov     r8d, 4
0x1801864aa  lea     rdx, [rsp+420h+var_3F8]
0x1801864af  mov     rcx, rbx
0x1801864b2  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1801864b8  mov     rax, [rbx]
0x1801864bb  movsxd  rcx, dword ptr [rax+4]
0x1801864bf  test    byte ptr [rcx+rbx+10h], 6
0x1801864c4  jnz     loc_180186727
0x1801864ca  mov     rbx, [rsi+30h]
0x1801864ce  mov     r8d, 4
0x1801864d4  lea     rdx, [rsp+420h+var_400]
0x1801864d9  mov     rcx, rbx
0x1801864dc  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1801864e2  mov     rax, [rbx]
0x1801864e5  movsxd  rcx, dword ptr [rax+4]
0x1801864e9  test    byte ptr [rcx+rbx+10h], 6
0x1801864ee  jnz     loc_180186748
0x1801864f4  mov     ebx, [rsp+420h+var_400]
0x1801864f8  cmp     edi, ebx
0x1801864fa  jnz     loc_180186769
0x180186500  mov     rcx, [rsi+30h]
0x180186504  call    ??$ReadBinary@I@StreamUtils@glTF@Microsoft@@SAIAEAV?$basic_istream@DU?$char_traits@D@std@@@std@@@Z; Microsoft::glTF::StreamUtils::ReadBinary<uint>(std::istream &)
0x180186509  mov     r14d, eax
0x18018650c  mov     rdx, [rsi+30h]
0x180186510  lea     rcx, aJson; "JSON"
0x180186517  call    sub_180186970
0x18018651c  test    al, al
0x18018651e  jz      loc_18018679E
0x180186524  mov     r8d, 4; MaxCount
0x18018652a  lea     rdx, aGltf_1; "glTF"
0x180186531  lea     rcx, [rsp+420h+Str1]; Str1
0x180186536  call    cs:__imp_strncmp
0x18018653c  test    eax, eax
0x18018653e  jnz     loc_1801867D3
0x180186544  mov     edx, [rsp+420h+var_3F8]
0x180186548  cmp     edx, 2
0x18018654b  jnz     loc_180186808
0x180186551  lea     r15d, [r14+14h]
0x180186555  lfence
0x180186558  cmp     ebx, r15d
0x18018655b  jb      loc_180186849
0x180186561  mov     rdi, [rsi+30h]
0x180186565  mov     qword ptr [rsp+420h+var_3B0], 14h
0x18018656e  xorps   xmm1, xmm1
0x180186571  movups  xmmword ptr [rsp+420h+var_3B0+8], xmm1
0x180186576  movups  xmm0, xmmword ptr [rsp+420h+var_3B0]
0x18018657b  movaps  [rbp+320h+var_390], xmm0
0x18018657f  unpckhpd xmm1, xmm1
0x180186583  movsd   [rbp+320h+var_380], xmm1
0x180186588  lea     rdx, [rbp+320h+var_390]
0x18018658c  mov     rcx, rdi
0x18018658f  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x180186595  xor     r8d, r8d
0x180186598  mov     edx, r14d
0x18018659b  lea     rcx, [rbp+320h+Block]
0x1801865a2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x1801865a7  mov     [rsp+420h+var_3F4], 1
0x1801865af  lea     rdx, [rbp+320h+Block]
0x1801865b6  cmp     [rbp+320h+var_220], 10h
0x1801865be  cmovnb  rdx, [rbp+320h+Block]
0x1801865c6  mov     r8d, r14d
0x1801865c9  mov     rcx, rdi
0x1801865cc  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1801865d2  mov     rax, [rdi]
0x1801865d5  movsxd  rcx, dword ptr [rax+4]
0x1801865d9  test    byte ptr [rcx+rdi+10h], 6
0x1801865de  jnz     loc_180186908
0x1801865e4  lea     rcx, [rsi+10h]
0x1801865e8  lea     rdx, [rbp+320h+Block]
0x1801865ef  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1801865f4  nop
0x1801865f5  mov     rdx, [rbp+320h+var_220]
0x1801865fc  cmp     rdx, 10h
0x180186600  jb      short loc_180186639
0x180186602  inc     rdx
0x180186605  mov     rcx, [rbp+320h+Block]; Block
0x18018660c  mov     rax, rcx
0x18018660f  cmp     rdx, 1000h
0x180186616  jb      short loc_180186634
0x180186618  add     rdx, 27h ; '''
0x18018661c  mov     rcx, [rcx-8]
0x180186620  sub     rax, rcx
0x180186623  add     rax, 0FFFFFFFFFFFFFFF8h
0x180186627  cmp     rax, 1Fh
0x18018662b  jbe     short loc_180186634
0x18018662d  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180186634  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180186639  mov     ebx, [rsp+420h+var_400]
0x18018663d  cmp     ebx, r15d
0x180186640  jz      short loc_18018668B
0x180186642  mov     rcx, [rsi+30h]
0x180186646  call    ??$ReadBinary@I@StreamUtils@glTF@Microsoft@@SAIAEAV?$basic_istream@DU?$char_traits@D@std@@@std@@@Z; Microsoft::glTF::StreamUtils::ReadBinary<uint>(std::istream &)
0x18018664b  mov     edi, eax
0x18018664d  mov     rdx, [rsi+30h]
0x180186651  lea     rcx, aBin_0; "BIN"
0x180186658  call    sub_180186970
0x18018665d  test    al, al
0x18018665f  jz      loc_180186929
0x180186665  lea     eax, [r14+1Ch]
0x180186669  add     eax, edi
0x18018666b  cmp     eax, ebx
0x18018666d  jnz     short loc_1801866B7
0x18018666f  lea     rdx, [rbp+320h+var_250]
0x180186676  mov     rcx, [rsi+30h]
0x18018667a  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x180186680  mov     rcx, [rax+8]
0x180186684  add     rcx, [rax]
0x180186687  mov     [rsi+40h], rcx
0x18018668b  mov     rcx, [rbp+320h+var_18]
0x180186692  xor     rcx, rsp; StackCookie
0x180186695  call    __security_check_cookie
0x18018669a  lea     r11, [rsp+420h+var_10]
0x1801866a2  mov     rbx, [r11+28h]
0x1801866a6  mov     rsi, [r11+30h]
0x1801866aa  mov     rdi, [r11+38h]
0x1801866ae  mov     rsp, r11
0x1801866b1  pop     r15
0x1801866b3  pop     r14
0x1801866b5  pop     rbp
0x1801866b6  retn
0x1801866b7  lea     rdx, aFileLengthDoes; "File length does not match sum of lengt"...
0x1801866be  lea     rcx, [rbp+320h+var_178]
0x1801866c5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801866ca  nop
0x1801866cb  lea     rdx, [rbp+320h+var_178]
0x1801866d2  lea     rcx, [rbp+320h+pExceptionObject]
0x1801866d9  call    ??0InvalidGLTFException@glTF@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(std::string const &)
0x1801866de  lea     rdx, _TI4?AVInvalidGLTFException@glTF@Microsoft@@; pThrowInfo
0x1801866e5  lea     rcx, [rbp+320h+pExceptionObject]; pExceptionObject
0x1801866ec  call    _CxxThrowException_0
0x1801866f2  lea     rdx, aCannotReadTheM; "Cannot read the magic number"
0x1801866f9  lea     rcx, [rbp+320h+var_218]
0x180186700  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180186705  nop
0x180186706  lea     rdx, [rbp+320h+var_218]
0x18018670d  lea     rcx, [rbp+320h+var_370]
0x180186711  call    ??0InvalidGLTFException@glTF@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(std::string const &)
0x180186716  lea     rdx, _TI4?AVInvalidGLTFException@glTF@Microsoft@@; pThrowInfo
0x18018671d  lea     rcx, [rbp+320h+var_370]; pExceptionObject
0x180186721  call    _CxxThrowException_0
0x180186727  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x18018672e  lea     rcx, [rbp+320h+var_358]; this
0x180186732  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180186737  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18018673e  lea     rcx, [rbp+320h+var_358]; pExceptionObject
0x180186742  call    _CxxThrowException_0
0x180186748  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x18018674f  lea     rcx, [rbp+320h+var_340]; this
0x180186753  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180186758  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18018675f  lea     rcx, [rbp+320h+var_340]; pExceptionObject
0x180186763  call    _CxxThrowException_0
0x180186769  lea     rdx, aFileReportedFi; "File-reported file length does not matc"...
0x180186770  lea     rcx, [rbp+320h+var_1F8]
0x180186777  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18018677c  nop
0x18018677d  lea     rdx, [rbp+320h+var_1F8]
0x180186784  lea     rcx, [rbp+320h+var_328]
0x180186788  call    ??0InvalidGLTFException@glTF@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(std::string const &)
0x18018678d  lea     rdx, _TI4?AVInvalidGLTFException@glTF@Microsoft@@; pThrowInfo
0x180186794  lea     rcx, [rbp+320h+var_328]; pExceptionObject
0x180186798  call    _CxxThrowException_0
0x18018679e  lea     rdx, aJsonChunkShoul; "JSON chunk should appear first"
0x1801867a5  lea     rcx, [rbp+320h+var_1D8]
0x1801867ac  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801867b1  nop
0x1801867b2  lea     rdx, [rbp+320h+var_1D8]
0x1801867b9  lea     rcx, [rbp+320h+var_310]
0x1801867bd  call    ??0InvalidGLTFException@glTF@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(std::string const &)
0x1801867c2  lea     rdx, _TI4?AVInvalidGLTFException@glTF@Microsoft@@; pThrowInfo
0x1801867c9  lea     rcx, [rbp+320h+var_310]; pExceptionObject
0x1801867cd  call    _CxxThrowException_0
0x1801867d3  lea     rdx, aCannotFindGlbM; "Cannot find GLB magic bytes"
0x1801867da  lea     rcx, [rbp+320h+var_1B8]
0x1801867e1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801867e6  nop
0x1801867e7  lea     rdx, [rbp+320h+var_1B8]
0x1801867ee  lea     rcx, [rbp+320h+var_2F8]
0x1801867f2  call    ??0InvalidGLTFException@glTF@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(std::string const &)
0x1801867f7  lea     rdx, _TI4?AVInvalidGLTFException@glTF@Microsoft@@; pThrowInfo
0x1801867fe  lea     rcx, [rbp+320h+var_2F8]; pExceptionObject
0x180186802  call    _CxxThrowException_0
0x180186808  lea     rcx, [rbp+320h+var_158]
0x18018680f  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@I@Z; std::to_string(uint)
0x180186814  nop
0x180186815  mov     r8, rax
0x180186818  lea     rdx, aUnsupportedGlb; "Unsupported GLB Version: "
0x18018681f  lea     rcx, [rbp+320h+var_138]
0x180186826  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18018682b  nop
0x18018682c  mov     rdx, rax
0x18018682f  lea     rcx, [rbp+320h+var_2E0]
0x180186833  call    ??0InvalidGLTFException@glTF@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(std::string const &)
0x180186838  lea     rdx, _TI4?AVInvalidGLTFException@glTF@Microsoft@@; pThrowInfo
0x18018683f  lea     rcx, [rbp+320h+var_2E0]; pExceptionObject
0x180186843  call    _CxxThrowException_0
0x180186849  mov     edx, 14h
0x18018684e  lea     rcx, [rbp+320h+var_118]; void *
0x180186855  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@J@Z; std::to_string(long)
0x18018685a  mov     rdi, rax
0x18018685d  mov     edx, r14d
0x180186860  lea     rcx, [rbp+320h+var_F8]
0x180186867  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@I@Z; std::to_string(uint)
0x18018686c  mov     rbx, rax
0x18018686f  mov     edx, [rsp+420h+var_400]
0x180186873  lea     rcx, [rbp+320h+var_D8]
0x18018687a  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@I@Z; std::to_string(uint)
0x18018687f  nop
0x180186880  mov     r8, rax
0x180186883  lea     rdx, aFileLength; "File length "
0x18018688a  lea     rcx, [rbp+320h+var_B8]
0x180186891  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180186896  nop
0x180186897  lea     r8, aLessThanConten; " less than content length "
0x18018689e  mov     rdx, rax
0x1801868a1  lea     rcx, [rbp+320h+var_98]
0x1801868a8  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1801868ad  nop
0x1801868ae  mov     r8, rbx
0x1801868b1  mov     rdx, rax
0x1801868b4  lea     rcx, [rbp+320h+var_78]
0x1801868bb  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1801868c0  nop
0x1801868c1  lea     r8, aPlusHeaderLeng; " plus header length "
0x1801868c8  mov     rdx, rax
0x1801868cb  lea     rcx, [rbp+320h+var_58]
0x1801868d2  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1801868d7  nop
0x1801868d8  mov     r8, rdi
0x1801868db  mov     rdx, rax
0x1801868de  lea     rcx, [rbp+320h+var_38]
0x1801868e5  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1801868ea  nop
0x1801868eb  mov     rdx, rax
0x1801868ee  lea     rcx, [rbp+320h+var_2C8]
0x1801868f2  call    ??0InvalidGLTFException@glTF@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(std::string const &)
0x1801868f7  lea     rdx, _TI4?AVInvalidGLTFException@glTF@Microsoft@@; pThrowInfo
0x1801868fe  lea     rcx, [rbp+320h+var_2C8]; pExceptionObject
0x180186902  call    _CxxThrowException_0
0x180186908  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x18018690f  lea     rcx, [rbp+320h+var_2B0]; this
0x180186913  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180186918  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18018691f  lea     rcx, [rbp+320h+var_2B0]; pExceptionObject
0x180186923  call    _CxxThrowException_0
0x180186929  lea     rdx, aBinaryChunkSho; "Binary chunk should appear second"
0x180186930  lea     rcx, [rbp+320h+var_198]
0x180186937  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18018693c  nop
0x18018693d  lea     rdx, [rbp+320h+var_198]
0x180186944  lea     rcx, [rbp+320h+var_298]
0x18018694b  call    ??0InvalidGLTFException@glTF@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::InvalidGLTFException::InvalidGLTFException(std::string const &)
0x180186950  lea     rdx, _TI4?AVInvalidGLTFException@glTF@Microsoft@@; pThrowInfo
0x180186957  lea     rcx, [rbp+320h+var_298]; pExceptionObject
0x18018695e  call    _CxxThrowException_0
```
