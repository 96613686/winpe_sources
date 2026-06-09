# Spectre::Engine::ColorTransform::ImportFormat_BinaryRGB_Base16(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,Spectre::Engine::ColorTransform::LoaderResult &)

- ea: `0x180085d80`
- end: `0x180085fbe`
- name: `?ImportFormat_BinaryRGB_Base16@ColorTransform@Engine@Spectre@@AEBAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAULoaderResult@123@@Z`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800859ac`

## callees

- `0x18000ca90`
- `0x18000d5dc`
- `0x18000dfa2`
- `0x180011f64`
- `0x180012ba8`
- `0x18001e58c`
- `0x180038ddc`
- `0x180084cf0`
- `0x180084ee4`
- `0x18008573c`
- `0x180085d80`
- `0x180086bb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_cbrtf` at `0x180085e3e`
- `api-ms-win-crt-private-l1-1-0!_o_cbrtf` at `0x180085e3e`

## string_xrefs

- `0x180085ddf`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\colortransform.cpp`
- `0x180085e97`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\colortransform.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Spectre::Engine::ColorTransform::ImportFormat_BinaryRGB_Base16(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v5; // kr00_8
  unsigned __int64 v6; // rbx
  int v7; // eax
  int v8; // r8d
  float v9; // xmm0_4
  float v10; // xmm0_4
  float v11; // xmm0_4
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 result; // rax
  int v15; // eax
  int v16; // r8d
  __int64 *v17; // rsi
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdi
  __int64 v20; // rdx
  unsigned int v21; // eax
  _DWORD *v22; // rax
  __int64 v23; // r8
  __int64 v24; // rdx
  _BYTE v25[16]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v26[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-9h] BYREF

  v5 = *(_QWORD *)(a2 + 16);
  v6 = v5 / 6;
  if ( v5 != 6 * (v5 / 6) )
  {
    std::string::string(
      v27,
      "ColorTransform::ImportFormat_BinaryRGB_Base16() -- unexpected data length (not multiple of six characters)");
    v7 = std::string::string(
           v26,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\colortransform.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v7,
      v8,
      (unsigned int)v27,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( (v6 & 0x8000000000000000uLL) != 0LL )
    v9 = (float)(int)((v5 / 6) & 1 | (v5 / 0xC)) + (float)(int)((v5 / 6) & 1 | (v5 / 0xC));
  else
    v9 = (float)(int)v6;
  v10 = cbrtf(v9);
  v11 = floorf(v10);
  v12 = 0;
  if ( v11 >= 9.223372e18 )
  {
    v11 = v11 - 9.223372e18;
    if ( v11 < 9.223372e18 )
      v12 = 0x8000000000000000uLL;
  }
  v13 = v12 + (unsigned int)(int)v11;
  result = v13 * v13 * v13;
  if ( result != v6 )
  {
    std::string::string(v26, "ColorTransform::ImportFormat_BinaryRGB_Base16() -- unexpected data length (not a cube)");
    v15 = std::string::string(
            v27,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\colortransform.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v15,
      v16,
      (unsigned int)v26,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  *(_QWORD *)a3 = v13;
  v17 = (__int64 *)(a3 + 8);
  v18 = (__int64)(*(_QWORD *)(a3 + 16) - *(_QWORD *)(a3 + 8)) >> 4;
  if ( v6 >= v18 )
  {
    if ( v6 <= v18 )
      goto LABEL_18;
    if ( v6 > (__int64)(*(_QWORD *)(a3 + 24) - *(_QWORD *)(a3 + 8)) >> 4 )
    {
      result = std::vector<Spectre::Utils::Math::Color>::_Resize_reallocate<std::_Value_init_tag>(a3 + 8, v5 / 6);
      goto LABEL_18;
    }
    result = std::_Uninitialized_value_construct_n<std::allocator<Spectre::Utils::Math::Color>>(
               *(_QWORD *)(a3 + 16),
               v6 - v18,
               a3 + 8);
  }
  else
  {
    result = *v17 + 16 * v6;
  }
  *(_QWORD *)(a3 + 16) = result;
LABEL_18:
  v19 = 0;
  for ( *(_DWORD *)(a3 + 32) = 0; v19 < v6; ++v19 )
  {
    std::string::substr(a2, v26, 6 * v19, 6);
    v21 = std::stoi(v26, v20, 16);
    v22 = (_DWORD *)Spectre::Utils::Math::Color::FromARGB(v25, v21);
    v23 = 2 * v19;
    v24 = *v17;
    *(_DWORD *)(v24 + 8 * v23) = *v22;
    *(_DWORD *)(v24 + 8 * v23 + 4) = v22[1];
    *(_DWORD *)(v24 + 8 * v23 + 8) = v22[2];
    *(_DWORD *)(v24 + 8 * v23 + 12) = v22[3];
    result = std::string::_Tidy_deallocate(v26);
  }
  return result;
}

```

## disassembly

```asm
0x180085d80  mov     [rsp-8+arg_0], rbx
0x180085d85  push    rbp
0x180085d86  push    rsi
0x180085d87  push    rdi
0x180085d88  push    r14
0x180085d8a  push    r15
0x180085d8c  lea     rbp, [rsp-37h]
0x180085d91  sub     rsp, 0C0h
0x180085d98  mov     rax, cs:__security_cookie
0x180085d9f  xor     rax, rsp
0x180085da2  mov     [rbp+57h+var_28], rax
0x180085da6  mov     r14, r8
0x180085da9  mov     r15, rdx
0x180085dac  mov     rax, 0AAAAAAAAAAAAAAABh
0x180085db6  mul     qword ptr [rdx+10h]
0x180085dba  mov     rbx, rdx
0x180085dbd  shr     rbx, 2
0x180085dc1  lea     rax, [rbx+rbx*2]
0x180085dc5  add     rax, rax
0x180085dc8  cmp     [r15+10h], rax
0x180085dcc  jz      short loc_180085E17
0x180085dce  lea     rdx, aColortransform; "ColorTransform::ImportFormat_BinaryRGB_"...
0x180085dd5  lea     rcx, [rbp+57h+var_80]
0x180085dd9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180085dde  nop
0x180085ddf  lea     rdx, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180085de6  lea     rcx, [rbp+57h+var_A0]
0x180085dea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180085def  xor     edi, edi
0x180085df1  mov     [rsp+0E0h+var_C0], dil
0x180085df6  lea     r9, [rbp+57h+var_80]
0x180085dfa  mov     rdx, rax
0x180085dfd  lea     rcx, [rbp+57h+pExceptionObject]
0x180085e01  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180085e06  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180085e0d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180085e11  call    _CxxThrowException_0
0x180085e17  xorps   xmm0, xmm0
0x180085e1a  test    rbx, rbx
0x180085e1d  js      short loc_180085E26
0x180085e1f  cvtsi2ss xmm0, rbx
0x180085e24  jmp     short loc_180085E3E
0x180085e26  mov     rcx, rbx
0x180085e29  shr     rcx, 1
0x180085e2c  mov     rax, rbx
0x180085e2f  and     eax, 1
0x180085e32  or      rcx, rax
0x180085e35  cvtsi2ss xmm0, rcx
0x180085e3a  addss   xmm0, xmm0; X
0x180085e3e  call    cs:__imp_cbrtf
0x180085e44  call    floorf
0x180085e49  xor     eax, eax
0x180085e4b  movss   xmm1, cs:__real@5f000000
0x180085e53  comiss  xmm0, xmm1
0x180085e56  jb      short loc_180085E6E
0x180085e58  subss   xmm0, xmm1
0x180085e5c  comiss  xmm0, xmm1
0x180085e5f  jnb     short loc_180085E6E
0x180085e61  mov     rcx, 8000000000000000h
0x180085e6b  mov     rax, rcx
0x180085e6e  cvttss2si rcx, xmm0
0x180085e73  add     rcx, rax
0x180085e76  mov     rax, rcx
0x180085e79  imul    rax, rcx
0x180085e7d  imul    rax, rcx
0x180085e81  cmp     rax, rbx
0x180085e84  jz      short loc_180085ECF
0x180085e86  lea     rdx, aColortransform_3; "ColorTransform::ImportFormat_BinaryRGB_"...
0x180085e8d  lea     rcx, [rbp+57h+var_A0]
0x180085e91  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180085e96  nop
0x180085e97  lea     rdx, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180085e9e  lea     rcx, [rbp+57h+var_80]
0x180085ea2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180085ea7  xor     edi, edi
0x180085ea9  mov     [rsp+0E0h+var_C0], dil
0x180085eae  lea     r9, [rbp+57h+var_A0]
0x180085eb2  mov     rdx, rax
0x180085eb5  lea     rcx, [rbp+57h+pExceptionObject]
0x180085eb9  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180085ebe  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180085ec5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180085ec9  call    _CxxThrowException_0
0x180085ecf  mov     [r14], rcx
0x180085ed2  lea     rsi, [r14+8]
0x180085ed6  mov     rcx, [rsi+8]
0x180085eda  sub     rcx, [rsi]
0x180085edd  sar     rcx, 4
0x180085ee1  cmp     rbx, rcx
0x180085ee4  jnb     short loc_180085EF2
0x180085ee6  mov     rax, rbx
0x180085ee9  shl     rax, 4
0x180085eed  add     rax, [rsi]
0x180085ef0  jmp     short loc_180085F20
0x180085ef2  jbe     short loc_180085F24
0x180085ef4  mov     rax, [rsi+10h]
0x180085ef8  sub     rax, [rsi]
0x180085efb  sar     rax, 4
0x180085eff  mov     rdx, rbx
0x180085f02  cmp     rbx, rax
0x180085f05  jbe     short loc_180085F11
0x180085f07  mov     rcx, rsi
0x180085f0a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UColor@Math@Utils@Spectre@@V?$allocator@UColor@Math@Utils@Spectre@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Spectre::Utils::Math::Color>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180085f0f  jmp     short loc_180085F24
0x180085f11  sub     rdx, rcx
0x180085f14  mov     r8, rsi
0x180085f17  mov     rcx, [rsi+8]
0x180085f1b  call    ??$_Uninitialized_value_construct_n@V?$allocator@UColor@Math@Utils@Spectre@@@std@@@std@@YAPEAUColor@Math@Utils@Spectre@@PEAU1234@_KAEAV?$allocator@UColor@Math@Utils@Spectre@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Spectre::Utils::Math::Color>>(Spectre::Utils::Math::Color *,unsigned __int64,std::allocator<Spectre::Utils::Math::Color> &)
0x180085f20  mov     [rsi+8], rax
0x180085f24  xor     edi, edi
0x180085f26  mov     [r14+20h], edi
0x180085f2a  test    rbx, rbx
0x180085f2d  jz      short loc_180085F9B
0x180085f2f  lea     r8, [rdi+rdi*2]
0x180085f33  add     r8, r8
0x180085f36  mov     r9d, 6
0x180085f3c  lea     rdx, [rbp+57h+var_A0]
0x180085f40  mov     rcx, r15
0x180085f43  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x180085f48  nop
0x180085f49  mov     r8d, 10h
0x180085f4f  lea     rcx, [rbp+57h+var_A0]
0x180085f53  call    ?stoi@std@@YAHAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@PEA_KH@Z; std::stoi(std::string const &,unsigned __int64 *,int)
0x180085f58  mov     edx, eax
0x180085f5a  lea     rcx, [rbp+57h+var_B0]
0x180085f5e  call    ?FromARGB@Color@Math@Utils@Spectre@@SA?AU1234@I@Z; Spectre::Utils::Math::Color::FromARGB(uint)
0x180085f63  mov     r8, rdi
0x180085f66  add     r8, r8
0x180085f69  mov     rdx, [rsi]
0x180085f6c  mov     ecx, [rax]
0x180085f6e  mov     [rdx+r8*8], ecx
0x180085f72  mov     ecx, [rax+4]
0x180085f75  mov     [rdx+r8*8+4], ecx
0x180085f7a  mov     ecx, [rax+8]
0x180085f7d  mov     [rdx+r8*8+8], ecx
0x180085f82  mov     eax, [rax+0Ch]
0x180085f85  mov     [rdx+r8*8+0Ch], eax
0x180085f8a  lea     rcx, [rbp+57h+var_A0]
0x180085f8e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180085f93  inc     rdi
0x180085f96  cmp     rdi, rbx
0x180085f99  jb      short loc_180085F2F
0x180085f9b  mov     rcx, [rbp+57h+var_28]
0x180085f9f  xor     rcx, rsp; StackCookie
0x180085fa2  call    __security_check_cookie
0x180085fa7  mov     rbx, [rsp+0E0h+arg_0]
0x180085faf  add     rsp, 0C0h
0x180085fb6  pop     r15
0x180085fb8  pop     r14
0x180085fba  pop     rdi
0x180085fbb  pop     rsi
0x180085fbc  pop     rbp
0x180085fbd  retn
```
