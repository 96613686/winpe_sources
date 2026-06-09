# Spectre::Engine::ColorTransform::ImportFormat_IridasLook(std::basic_istringstream<char,std::char_traits<char>,std::allocator<char>> &,Spectre::Engine::ColorTransform::LoaderResult &)

- ea: `0x18008637c`
- end: `0x1800867e4`
- name: `?ImportFormat_IridasLook@ColorTransform@Engine@Spectre@@AEBAXAEAV?$basic_istringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAULoaderResult@123@@Z`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800859ac`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18000e8d0`
- `0x180011f64`
- `0x180012ba8`
- `0x180014530`
- `0x180014a3c`
- `0x180018318`
- `0x18001ce2c`
- `0x18001e46c`
- `0x18001e4c4`
- `0x18001e58c`
- `0x18001f7d8`
- `0x180038ddc`
- `0x18004d870`
- `0x180084b34`
- `0x180084cf0`
- `0x180084df4`
- `0x180084ee4`
- `0x18008637c`
- `0x180086a30`
- `0x180086bb0`

## import_xrefs

- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18008642c`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18008666c`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18008642c`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18008666c`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180086610`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180086610`

## string_xrefs

- `0x1800866ab`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\colortransform.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Spectre::Engine::ColorTransform::ImportFormat_IridasLook(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // r13
  __int64 v4; // r15
  unsigned __int64 v5; // rdi
  int v6; // ebx
  char v7; // si
  char v8; // r12
  char v9; // r14
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  unsigned __int64 v27; // rsi
  unsigned __int64 v28; // rbx
  __int64 v29; // rax
  char v30; // al
  __int64 v31; // rax
  int v32; // eax
  int v33; // r8d
  __int64 *v34; // rbx
  unsigned __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r9
  unsigned __int64 v38; // rdx
  __int64 v39; // r8
  int v40; // xmm1_4
  int v41; // xmm0_4
  __int64 v42; // rcx
  char v44; // [rsp+30h] [rbp-D0h]
  _BYTE v45[3]; // [rsp+31h] [rbp-CFh] BYREF
  int v46; // [rsp+34h] [rbp-CCh]
  _BYTE v47[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE *v48; // [rsp+40h] [rbp-C0h]
  __int64 v49; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v50; // [rsp+50h] [rbp-B0h]
  _BYTE *v51; // [rsp+58h] [rbp-A8h]
  __int64 v52; // [rsp+60h] [rbp-A0h]
  _QWORD *v53; // [rsp+68h] [rbp-98h]
  _BYTE *v54; // [rsp+70h] [rbp-90h]
  _BYTE v55[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v56[16]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v57; // [rsp+A8h] [rbp-58h]
  _BYTE v58[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v59[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v60; // [rsp+E8h] [rbp-18h]
  _BYTE v61[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v62[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+138h] [rbp+38h] BYREF

  v3 = (_QWORD *)a3;
  v53 = (_QWORD *)a3;
  v52 = a2;
  v4 = 0;
  v5 = 0;
  LOBYTE(v6) = 0;
  v7 = 0;
  v44 = 0;
  v8 = 0;
  v9 = 0;
  *(_DWORD *)(a3 + 32) = 0;
  std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(&v49);
  std::string::string(v59, "<size>");
  std::string::string(v62, "<data>");
  std::string::string(v61, "</data>");
  std::string::string(v56);
  v10 = std::getline<char,std::char_traits<char>,std::allocator<char>>(v52, v56);
  if ( !(unsigned __int8)std::ios_base::operator bool(v10 + *(int *)(*(_QWORD *)v10 + 4LL)) )
    goto LABEL_40;
  do
  {
    if ( v57 )
    {
      if ( v9 )
        goto LABEL_27;
      v11 = std::_String_val<std::_Simple_types<char>>::_Myptr(v56);
      if ( *(_BYTE *)(v11 + v12 - 1) == 13 )
        std::string::resize(v56, v12 - 1);
      v13 = std::_String_val<std::_Simple_types<char>>::_Myptr(v56);
      v17 = std::_Traits_find_first_not_of<std::char_traits<char>>(v13, v14, v15, v16, 2);
      std::string::erase(v56, v18, v17);
      v19 = std::_String_val<std::_Simple_types<char>>::_Myptr(v56);
      v6 = (unsigned __int8)v6;
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v19, v57, "<LUT>", 5) )
        v6 = 1;
      v46 = v6;
      if ( (_BYTE)v6 )
      {
        v54 = v58;
        v20 = std::string::string(v58, v59);
        v21 = std::string::string(v55, v56);
        if ( (unsigned __int8)Spectre::Engine::_anonymous_namespace_::StringBegins(v21, v20) )
        {
          std::string::substr(v56, pExceptionObject, v60 + 1, -1);
          v4 = (int)std::stoi(pExceptionObject, v22, 10);
          v5 = v4 * v4 * v4;
          v7 = 1;
          v44 = 1;
          std::string::_Tidy_deallocate(pExceptionObject);
        }
      }
      if ( v7
        && (v48 = v55,
            v23 = std::string::string(v55, v62),
            v24 = std::string::string(v58, v56),
            (unsigned __int8)Spectre::Engine::_anonymous_namespace_::StringBegins(v24, v23)) )
      {
        v8 = 1;
      }
      else if ( v8 )
      {
        v48 = v55;
        v25 = std::string::string(v55, v61);
        v26 = std::string::string(v58, v56);
        if ( (unsigned __int8)Spectre::Engine::_anonymous_namespace_::StringBegins(v26, v25) )
        {
          v9 = 1;
        }
        else
        {
          v27 = v57 >> 1;
          v28 = 0;
          if ( v57 >> 1 )
          {
            do
            {
              v29 = std::_String_val<std::_Simple_types<char>>::_Myptr(v56);
              v47[0] = *(_BYTE *)(v29 + 2 * v28);
              v47[1] = *(_BYTE *)(v29 + 2 * v28 + 1);
              v47[2] = 0;
              v30 = _o_strtoul(v47, 0, 16);
              v45[0] = v30;
              if ( v50 == v51 )
                std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(&v49, v50, v45);
              else
                *v50++ = v30;
              ++v28;
            }
            while ( v28 < v27 );
            v3 = v53;
          }
          v7 = v44;
        }
      }
      LOBYTE(v6) = v46;
    }
    v31 = std::getline<char,std::char_traits<char>,std::allocator<char>>(v52, v56);
  }
  while ( (unsigned __int8)std::ios_base::operator bool(v31 + *(int *)(*(_QWORD *)v31 + 4LL)) );
  if ( !v9 )
    goto LABEL_40;
LABEL_27:
  if ( &v50[-v49] != (_BYTE *)(12 * v5) )
  {
    std::string::string(v58, "ColorTransform::ImportFormat_IridasLook() -- unexpected data layout in LOOK file");
    v32 = std::string::string(
            v55,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\colortransform.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v32,
      v33,
      (unsigned int)v58,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v34 = v3 + 1;
  v35 = (__int64)(v3[2] - v3[1]) >> 4;
  if ( v5 >= v35 )
  {
    if ( v5 <= v35 )
      goto LABEL_36;
    if ( v5 > (__int64)(v3[3] - v3[1]) >> 4 )
    {
      std::vector<Spectre::Utils::Math::Color>::_Resize_reallocate<std::_Value_init_tag>(v3 + 1, v5);
      goto LABEL_36;
    }
    v36 = std::_Uninitialized_value_construct_n<std::allocator<Spectre::Utils::Math::Color>>(v3[2], v5 - v35, v3 + 1);
  }
  else
  {
    v36 = *v34 + 16 * v5;
  }
  v3[2] = v36;
LABEL_36:
  if ( v5 )
  {
    v37 = v49;
    v38 = 0;
    v39 = *v34;
    do
    {
      v40 = *(_DWORD *)(v37 + 12 * v38 + 8);
      v41 = *(_DWORD *)(v37 + 12 * v38 + 4);
      v42 = 2 * v38;
      *(_DWORD *)(v39 + 8 * v42) = *(_DWORD *)(v37 + 12 * v38);
      *(_DWORD *)(v39 + 8 * v42 + 4) = v41;
      *(_DWORD *)(v39 + 8 * v42 + 8) = v40;
      *(_DWORD *)(v39 + 8 * v42 + 12) = 1065353216;
      ++v38;
    }
    while ( v38 < v5 );
    v3 = v53;
  }
LABEL_40:
  *v3 = v4;
  std::string::_Tidy_deallocate(v56);
  std::string::_Tidy_deallocate(v61);
  std::string::_Tidy_deallocate(v62);
  std::string::_Tidy_deallocate(v59);
  return std::vector<unsigned char>::_Tidy(&v49);
}

```

## disassembly

```asm
0x18008637c  mov     [rsp-8+arg_0], rbx
0x180086381  push    rbp
0x180086382  push    rsi
0x180086383  push    rdi
0x180086384  push    r12
0x180086386  push    r13
0x180086388  push    r14
0x18008638a  push    r15
0x18008638c  lea     rbp, [rsp-80h]
0x180086391  sub     rsp, 180h
0x180086398  mov     rax, cs:__security_cookie
0x18008639f  xor     rax, rsp
0x1800863a2  mov     [rbp+0B0h+var_40], rax
0x1800863a6  mov     r13, r8
0x1800863a9  mov     [rsp+1B0h+var_148], r8
0x1800863ae  mov     [rsp+1B0h+var_150], rdx
0x1800863b3  xor     r15d, r15d
0x1800863b6  xor     edi, edi
0x1800863b8  xor     bl, bl
0x1800863ba  xor     sil, sil
0x1800863bd  mov     [rsp+1B0h+var_180], sil
0x1800863c2  xor     r12b, r12b
0x1800863c5  xor     r14b, r14b
0x1800863c8  mov     [r8+20h], edi
0x1800863cc  lea     rcx, [rsp+1B0h+var_168]; void *
0x1800863d1  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x1800863d6  nop
0x1800863d7  lea     rdx, aSize; "<size>"
0x1800863de  lea     rcx, [rbp+0B0h+var_D8]
0x1800863e2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800863e7  nop
0x1800863e8  lea     rdx, aData; "<data>"
0x1800863ef  lea     rcx, [rbp+0B0h+var_98]
0x1800863f3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800863f8  nop
0x1800863f9  lea     rdx, aData_0; "</data>"
0x180086400  lea     rcx, [rbp+0B0h+var_B8]
0x180086404  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180086409  nop
0x18008640a  lea     rcx, [rbp+0B0h+var_118]; void *
0x18008640e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180086413  nop
0x180086414  lea     rdx, [rbp+0B0h+var_118]
0x180086418  mov     rcx, [rsp+1B0h+var_150]
0x18008641d  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@AEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &,std::string &)
0x180086422  mov     rcx, [rax]
0x180086425  movsxd  rcx, dword ptr [rcx+4]
0x180086429  add     rcx, rax
0x18008642c  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x180086432  test    al, al
0x180086434  jz      loc_180086787
0x18008643a  mov     rdx, [rbp+0B0h+var_108]
0x18008643e  test    rdx, rdx
0x180086441  jz      loc_180086654
0x180086447  test    r14b, r14b
0x18008644a  jnz     loc_180086683
0x180086450  lea     rcx, [rbp+0B0h+var_118]
0x180086454  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180086459  cmp     byte ptr [rax+rdx-1], 0Dh
0x18008645e  jnz     short loc_180086470
0x180086460  dec     rdx
0x180086463  lea     rcx, [rbp+0B0h+var_118]
0x180086467  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x18008646c  mov     rdx, [rbp+0B0h+var_108]
0x180086470  lea     rcx, [rbp+0B0h+var_118]
0x180086474  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180086479  mov     rcx, rax
0x18008647c  mov     [rsp+1B0h+var_190], 2
0x180086485  call    ??$_Traits_find_first_not_of@U?$char_traits@D@std@@@std@@YA_KQEBD_K101@Z; std::_Traits_find_first_not_of<std::char_traits<char>>(char const * const,unsigned __int64,unsigned __int64,char const * const,unsigned __int64)
0x18008648a  mov     r8, rax
0x18008648d  lea     rcx, [rbp+0B0h+var_118]
0x180086491  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x180086496  lea     rcx, [rbp+0B0h+var_118]
0x18008649a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18008649f  mov     rcx, rax
0x1800864a2  mov     r9d, 5
0x1800864a8  lea     r8, aLut; "<LUT>"
0x1800864af  mov     rdx, [rbp+0B0h+var_108]
0x1800864b3  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800864b8  movzx   ebx, bl
0x1800864bb  test    al, al
0x1800864bd  mov     eax, 1
0x1800864c2  cmovnz  ebx, eax
0x1800864c5  mov     [rsp+1B0h+var_17C], ebx
0x1800864c9  test    bl, bl
0x1800864cb  jz      short loc_18008654B
0x1800864cd  lea     rax, [rbp+0B0h+var_F8]
0x1800864d1  mov     [rsp+1B0h+var_140], rax
0x1800864d6  lea     rdx, [rbp+0B0h+var_D8]
0x1800864da  lea     rcx, [rbp+0B0h+var_F8]
0x1800864de  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800864e3  mov     rbx, rax
0x1800864e6  lea     rdx, [rbp+0B0h+var_118]
0x1800864ea  lea     rcx, [rsp+1B0h+var_138]
0x1800864ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800864f4  nop
0x1800864f5  mov     rdx, rbx
0x1800864f8  mov     rcx, rax
0x1800864fb  call    Spectre__Engine___anonymous_namespace___StringBegins
0x180086500  test    al, al
0x180086502  jz      short loc_18008654B
0x180086504  mov     r8, [rbp+0B0h+var_C8]
0x180086508  inc     r8
0x18008650b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008650f  lea     rdx, [rbp+0B0h+pExceptionObject]
0x180086513  lea     rcx, [rbp+0B0h+var_118]
0x180086517  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x18008651c  nop
0x18008651d  mov     r8d, 0Ah
0x180086523  lea     rcx, [rbp+0B0h+pExceptionObject]
0x180086527  call    ?stoi@std@@YAHAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@PEA_KH@Z; std::stoi(std::string const &,unsigned __int64 *,int)
0x18008652c  movsxd  r15, eax
0x18008652f  mov     rdi, r15
0x180086532  imul    rdi, r15
0x180086536  imul    rdi, r15
0x18008653a  mov     sil, 1
0x18008653d  mov     [rsp+1B0h+var_180], sil
0x180086542  lea     rcx, [rbp+0B0h+pExceptionObject]
0x180086546  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18008654b  test    sil, sil
0x18008654e  jz      short loc_180086590
0x180086550  lea     rax, [rsp+1B0h+var_138]
0x180086555  mov     [rsp+1B0h+var_170], rax
0x18008655a  lea     rdx, [rbp+0B0h+var_98]
0x18008655e  lea     rcx, [rsp+1B0h+var_138]
0x180086563  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180086568  mov     rbx, rax
0x18008656b  lea     rdx, [rbp+0B0h+var_118]
0x18008656f  lea     rcx, [rbp+0B0h+var_F8]
0x180086573  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180086578  nop
0x180086579  mov     rdx, rbx
0x18008657c  mov     rcx, rax
0x18008657f  call    Spectre__Engine___anonymous_namespace___StringBegins
0x180086584  test    al, al
0x180086586  jz      short loc_180086590
0x180086588  mov     r12b, 1
0x18008658b  jmp     loc_180086650
0x180086590  test    r12b, r12b
0x180086593  jz      loc_180086650
0x180086599  lea     rax, [rsp+1B0h+var_138]
0x18008659e  mov     [rsp+1B0h+var_170], rax
0x1800865a3  lea     rdx, [rbp+0B0h+var_B8]
0x1800865a7  lea     rcx, [rsp+1B0h+var_138]
0x1800865ac  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800865b1  mov     rbx, rax
0x1800865b4  lea     rdx, [rbp+0B0h+var_118]
0x1800865b8  lea     rcx, [rbp+0B0h+var_F8]
0x1800865bc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800865c1  nop
0x1800865c2  mov     rdx, rbx
0x1800865c5  mov     rcx, rax
0x1800865c8  call    Spectre__Engine___anonymous_namespace___StringBegins
0x1800865cd  test    al, al
0x1800865cf  jz      short loc_1800865D6
0x1800865d1  mov     r14b, 1
0x1800865d4  jmp     short loc_180086650
0x1800865d6  mov     rsi, [rbp+0B0h+var_108]
0x1800865da  shr     rsi, 1
0x1800865dd  mov     ebx, 0
0x1800865e2  jz      short loc_18008664B
0x1800865e4  lea     r13d, [rbx+1]
0x1800865e8  lea     rcx, [rbp+0B0h+var_118]
0x1800865ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800865f1  mov     cl, [rax+rbx*2]
0x1800865f4  mov     [rsp+1B0h+var_178], cl
0x1800865f8  mov     al, [rax+rbx*2+1]
0x1800865fc  mov     [rsp+1B0h+var_177], al
0x180086600  mov     [rsp+1B0h+var_176], 0
0x180086605  xor     edx, edx
0x180086607  lea     r8d, [rdx+10h]
0x18008660b  lea     rcx, [rsp+1B0h+var_178]
0x180086610  call    cs:__imp__o_strtoul
0x180086616  mov     [rsp+1B0h+var_17F], al
0x18008661a  mov     rdx, [rsp+1B0h+var_160]
0x18008661f  cmp     rdx, [rsp+1B0h+var_158]
0x180086624  jz      short loc_18008662F
0x180086626  mov     [rdx], al
0x180086628  add     [rsp+1B0h+var_160], r13
0x18008662d  jmp     short loc_18008663E
0x18008662f  lea     r8, [rsp+1B0h+var_17F]
0x180086634  lea     rcx, [rsp+1B0h+var_168]
0x180086639  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x18008663e  add     rbx, r13
0x180086641  cmp     rbx, rsi
0x180086644  jb      short loc_1800865E8
0x180086646  mov     r13, [rsp+1B0h+var_148]
0x18008664b  mov     sil, [rsp+1B0h+var_180]
0x180086650  mov     ebx, [rsp+1B0h+var_17C]
0x180086654  lea     rdx, [rbp+0B0h+var_118]
0x180086658  mov     rcx, [rsp+1B0h+var_150]
0x18008665d  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@AEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &,std::string &)
0x180086662  mov     rcx, [rax]
0x180086665  movsxd  rcx, dword ptr [rcx+4]
0x180086669  add     rcx, rax
0x18008666c  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x180086672  test    al, al
0x180086674  jnz     loc_18008643A
0x18008667a  test    r14b, r14b
0x18008667d  jz      loc_180086787
0x180086683  mov     rcx, [rsp+1B0h+var_160]
0x180086688  sub     rcx, [rsp+1B0h+var_168]
0x18008668d  lea     rax, [rdi+rdi*2]
0x180086691  shl     rax, 2
0x180086695  cmp     rcx, rax
0x180086698  jz      short loc_1800866E2
0x18008669a  lea     rdx, aColortransform_1; "ColorTransform::ImportFormat_IridasLook"...
0x1800866a1  lea     rcx, [rbp+0B0h+var_F8]
0x1800866a5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800866aa  nop
0x1800866ab  lea     rdx, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800866b2  lea     rcx, [rsp+1B0h+var_138]
0x1800866b7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800866bc  mov     byte ptr [rsp+1B0h+var_190], 0
0x1800866c1  lea     r9, [rbp+0B0h+var_F8]
0x1800866c5  mov     rdx, rax
0x1800866c8  lea     rcx, [rbp+0B0h+pExceptionObject]
0x1800866cc  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x1800866d1  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x1800866d8  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1800866dc  call    _CxxThrowException_0
0x1800866e2  lea     rbx, [r13+8]
0x1800866e6  mov     rcx, [rbx+8]
0x1800866ea  sub     rcx, [rbx]
0x1800866ed  sar     rcx, 4
0x1800866f1  cmp     rdi, rcx
0x1800866f4  jnb     short loc_180086702
0x1800866f6  mov     rax, rdi
0x1800866f9  shl     rax, 4
0x1800866fd  add     rax, [rbx]
0x180086700  jmp     short loc_180086730
0x180086702  jbe     short loc_180086734
0x180086704  mov     rax, [rbx+10h]
0x180086708  sub     rax, [rbx]
0x18008670b  sar     rax, 4
0x18008670f  mov     rdx, rdi
0x180086712  cmp     rdi, rax
0x180086715  jbe     short loc_180086721
0x180086717  mov     rcx, rbx
0x18008671a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UColor@Math@Utils@Spectre@@V?$allocator@UColor@Math@Utils@Spectre@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Spectre::Utils::Math::Color>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18008671f  jmp     short loc_180086734
0x180086721  sub     rdx, rcx
0x180086724  mov     r8, rbx
0x180086727  mov     rcx, [rbx+8]
0x18008672b  call    ??$_Uninitialized_value_construct_n@V?$allocator@UColor@Math@Utils@Spectre@@@std@@@std@@YAPEAUColor@Math@Utils@Spectre@@PEAU1234@_KAEAV?$allocator@UColor@Math@Utils@Spectre@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Spectre::Utils::Math::Color>>(Spectre::Utils::Math::Color *,unsigned __int64,std::allocator<Spectre::Utils::Math::Color> &)
0x180086730  mov     [rbx+8], rax
0x180086734  test    rdi, rdi
0x180086737  jz      short loc_180086787
0x180086739  mov     r9, [rsp+1B0h+var_168]
0x18008673e  xor     edx, edx
0x180086740  mov     r8, [rbx]
0x180086743  lea     rax, [rdx+rdx*2]
0x180086747  movss   xmm1, dword ptr [r9+rax*4+8]
0x18008674e  movss   xmm0, dword ptr [r9+rax*4+4]
0x180086755  mov     rcx, rdx
0x180086758  add     rcx, rcx
0x18008675b  mov     eax, [r9+rax*4]
0x18008675f  mov     [r8+rcx*8], eax
0x180086763  movss   dword ptr [r8+rcx*8+4], xmm0
0x18008676a  movss   dword ptr [r8+rcx*8+8], xmm1
0x180086771  mov     dword ptr [r8+rcx*8+0Ch], 3F800000h
0x18008677a  inc     rdx
0x18008677d  cmp     rdx, rdi
0x180086780  jb      short loc_180086743
0x180086782  mov     r13, [rsp+1B0h+var_148]
0x180086787  mov     [r13+0], r15
0x18008678b  lea     rcx, [rbp+0B0h+var_118]
0x18008678f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180086794  nop
0x180086795  lea     rcx, [rbp+0B0h+var_B8]
0x180086799  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18008679e  nop
0x18008679f  lea     rcx, [rbp+0B0h+var_98]
0x1800867a3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800867a8  nop
0x1800867a9  lea     rcx, [rbp+0B0h+var_D8]
0x1800867ad  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800867b2  nop
0x1800867b3  lea     rcx, [rsp+1B0h+var_168]
0x1800867b8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800867bd  mov     rcx, [rbp+0B0h+var_40]
0x1800867c1  xor     rcx, rsp; StackCookie
0x1800867c4  call    __security_check_cookie
0x1800867c9  mov     rbx, [rsp+1B0h+arg_0]
0x1800867d1  add     rsp, 180h
0x1800867d8  pop     r15
0x1800867da  pop     r14
0x1800867dc  pop     r13
0x1800867de  pop     r12
0x1800867e0  pop     rdi
0x1800867e1  pop     rsi
0x1800867e2  pop     rbp
0x1800867e3  retn
```
