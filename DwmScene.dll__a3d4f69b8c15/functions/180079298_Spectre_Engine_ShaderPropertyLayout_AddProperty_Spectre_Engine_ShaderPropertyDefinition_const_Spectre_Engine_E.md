# Spectre::Engine::ShaderPropertyLayout::AddProperty(Spectre::Engine::ShaderPropertyDefinition const &,Spectre::Engine::EShaderPropertyLinkage)

- ea: `0x180079298`
- end: `0x18007970a`
- name: `?AddProperty@ShaderPropertyLayout@Engine@Spectre@@QEAA?AW4ShaderProperty@23@AEBUShaderPropertyDefinition@23@W4EShaderPropertyLinkage@23@@Z`
- size: `1138`
- prototype: ``
- caller_count: `7`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x1800424a8`
- `0x180043e00`
- `0x180075690`
- `0x180076150`
- `0x180076b70`
- `0x1800791d0`
- `0x18007b970`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012ba8`
- `0x180018318`
- `0x18001c630`
- `0x18001c720`
- `0x180038ddc`
- `0x18004bfc0`
- `0x18004c640`
- `0x18006ad4c`
- `0x180078160`
- `0x180078208`
- `0x180078358`
- `0x180078580`
- `0x1800786e0`
- `0x18007872c`
- `0x180079298`
- `0x180079710`
- `0x180079ab4`
- `0x180079e1c`
- `0x18007a184`
- `0x18007b970`
- `0x18007bcc4`

## string_xrefs

- `0x180079385`: `ShaderPropertyLayout::AddProperty() -- property block already has maximum number of properties`
- `0x180079407`: `' is already defined`
- `0x1800792e9`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180079339`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180079396`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x18007941e`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Spectre::Engine::ShaderPropertyLayout::AddProperty(__int64 a1, __int64 a2, int a3)
{
  int v6; // eax
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  _QWORD *v10; // rdi
  int v11; // eax
  int v12; // r8d
  unsigned int v13; // r13d
  __int64 v14; // r12
  __int64 v15; // rax
  int v16; // ebx
  int v17; // eax
  int v18; // r8d
  _QWORD *GlobalProperties; // rax
  __int64 v20; // r14
  __int64 v21; // rax
  unsigned __int64 v22; // r14
  __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned __int64 v25; // r14
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v34; // [rsp+38h] [rbp-C8h]
  _OWORD pExceptionObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v36; // [rsp+60h] [rbp-A0h]
  unsigned int v37; // [rsp+64h] [rbp-9Ch]
  int v38; // [rsp+68h] [rbp-98h]
  int v39; // [rsp+6Ch] [rbp-94h]
  int v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+74h] [rbp-8Ch]
  _BYTE v42[32]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v43; // [rsp+98h] [rbp-68h]
  __int16 v44; // [rsp+9Ah] [rbp-66h]
  int v45; // [rsp+9Ch] [rbp-64h]
  int v46; // [rsp+A0h] [rbp-60h]
  int v47; // [rsp+A4h] [rbp-5Ch]
  int v48; // [rsp+A8h] [rbp-58h]
  int v49; // [rsp+ACh] [rbp-54h]
  _BYTE v50[8]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v51; // [rsp+B8h] [rbp-48h]
  _BYTE v52[56]; // [rsp+D0h] [rbp-30h] BYREF

  if ( *(_DWORD *)(a1 + 1168) )
  {
    std::string::string(
      v42,
      "ShaderPropertyLayout::AddProperty() -- property can only be added while the layout is in declaration phase");
    v6 = std::string::string(
           v50,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v6,
      v7,
      (unsigned int)v42,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( !*(_QWORD *)(a2 + 16) )
  {
    std::string::string(v50, "ShaderPropertyLayout::AddProperty() -- property cannot have an empty name");
    v8 = std::string::string(
           v42,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v8,
      v9,
      (unsigned int)v50,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v10 = (_QWORD *)(a1 + 56);
  if ( *(_QWORD *)(a1 + 64) - *(_QWORD *)(a1 + 56) == 28672 )
  {
    std::string::string(
      v50,
      "ShaderPropertyLayout::AddProperty() -- property block already has maximum number of properties");
    v11 = std::string::string(
            v42,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v11,
      v12,
      (unsigned int)v50,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v13 = *(_DWORD *)(a2 + 32);
  v14 = (unsigned __int16)Spectre::Engine::ShaderManager::AddProperty(*(_QWORD *)(a1 + 1152));
  if ( *(_WORD *)(a1 + 2 * v14 + 128) != 0xFFFF )
  {
    v15 = std::operator+<char>(v50, "ShaderPropertyLayout::AddProperty() -- variable '", a2);
    v16 = std::operator+<char>(pExceptionObject, v15, "' is already defined");
    v17 = std::string::string(
            v42,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v52, v17, v18, v16, 0);
    throw (Spectre::Engine::EngineInvalidArgException *)v52;
  }
  if ( a3 == 1 )
  {
    GlobalProperties = (_QWORD *)Spectre::Engine::ShaderManager::GetGlobalProperties(*(_QWORD *)(a1 + 1152), v50);
    Spectre::Engine::ShaderPropertyBlock::GetLayout(*GlobalProperties, &v33);
    if ( v51 )
      std::_Ref_count_base::_Decref(v51);
    v20 = v33;
    if ( v33 != a1 )
    {
      if ( *(_WORD *)(v20 + 2LL * (unsigned __int16)Spectre::Engine::ShaderPropertyLayout::FindProperty(v33, a2) + 128) == 0xFFFF )
        Spectre::Engine::ShaderPropertyBlock::ExtendLayoutWithProperty(
          *(_QWORD *)(*(_QWORD *)(a1 + 1152) + 18648LL),
          a2);
      *(_BYTE *)(a1 + 1241) = 1;
      a3 = 2;
    }
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
  }
  if ( v13 == 8 )
  {
    v21 = *(_QWORD *)(a1 + 112);
    v22 = 0xCCCCCCCCCCCCCCCDuLL * ((v21 - *(_QWORD *)(a1 + 104)) >> 3);
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v36 = v22;
    v37 = 0;
    if ( v21 == *(_QWORD *)(a1 + 120) )
    {
      std::vector<Spectre::Engine::ShaderPropertyLayout::TextureElement>::_Emplace_reallocate<Spectre::Engine::ShaderPropertyLayout::TextureElement const &>(
        a1 + 104,
        v21,
        pExceptionObject);
    }
    else
    {
      std::_Construct_in_place<Spectre::Engine::ShaderPropertyLayout::TextureElement,Spectre::Engine::ShaderPropertyLayout::TextureElement const &>(
        v21,
        pExceptionObject);
      *(_QWORD *)(a1 + 112) += 40LL;
    }
    *(_WORD *)(a1 + 2 * v14 + 128) = 28087 * ((__int64)(v10[1] - *v10) >> 3);
    std::string::string(v42, a2);
    v43 = v14;
    v44 = 0;
    v45 = 8;
    v46 = v22;
    v47 = 0;
    v48 = a3;
    v49 = 0;
    v24 = v10[1];
    if ( v24 == v10[2] )
    {
      std::vector<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>::_Emplace_reallocate<Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(
        v10,
        v24,
        v42);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>>::construct<Spectre::Engine::ShaderPropertyLayout::PropertyInfo,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(
        v23,
        v24,
        v42);
      v10[1] += 56LL;
    }
    std::string::_Tidy_deallocate(v42);
    std::pair<std::shared_ptr<Spectre::Engine::SceneNode>,std::shared_ptr<Spectre::Engine::Mesh>>::~pair<std::shared_ptr<Spectre::Engine::SceneNode>,std::shared_ptr<Spectre::Engine::Mesh>>(pExceptionObject);
    goto LABEL_37;
  }
  Spectre::Engine::ShaderPropertyLayout::AlignBuffer((Spectre::Engine::ShaderPropertyLayout *)a1);
  v25 = (__int64)(*(_QWORD *)(a1 + 88) - *(_QWORD *)(a1 + 80)) >> 2;
  v26 = (unsigned int)v25 + (unsigned int)Spectre::Engine::ShaderPropertyLayout::GetTypeSizeInElements(v13);
  if ( (unsigned int)v26 < v25 )
  {
    v29 = v28 + 4 * v26;
LABEL_32:
    *(_QWORD *)(v27 + 8) = v29;
    goto LABEL_33;
  }
  if ( (unsigned int)v26 > v25 )
  {
    if ( (unsigned int)v26 <= (unsigned __int64)((*(_QWORD *)(v27 + 16) - v28) >> 2) )
    {
      v29 = std::_Uninitialized_value_construct_n<std::allocator<Spectre::Engine::ShaderPropertyLayout::ValueElement>>(
              *(_QWORD *)(v27 + 8),
              (unsigned int)v26 - v25,
              v27);
      goto LABEL_32;
    }
    std::vector<Spectre::Engine::ShaderPropertyLayout::ValueElement>::_Resize_reallocate<std::_Value_init_tag>(v27);
  }
LABEL_33:
  *(_WORD *)(a1 + 2 * v14 + 128) = 28087 * ((__int64)(v10[1] - *v10) >> 3);
  std::string::string(pExceptionObject, a2);
  v36 = (unsigned __int16)v14;
  v37 = v13;
  v38 = v25;
  v39 = 1;
  v40 = a3;
  v41 = 0;
  v31 = v10[1];
  if ( v31 == v10[2] )
  {
    std::vector<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>::_Emplace_reallocate<Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(
      v10,
      v31,
      pExceptionObject);
  }
  else
  {
    std::_Default_allocator_traits<std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>>::construct<Spectre::Engine::ShaderPropertyLayout::PropertyInfo,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(
      v30,
      v31,
      pExceptionObject);
    v10[1] += 56LL;
  }
  std::string::_Tidy_deallocate(pExceptionObject);
LABEL_37:
  *(_BYTE *)(a1 + 1240) |= a3 == 2;
  Spectre::Engine::ShaderPropertyLayout::SetPropertyDefaultFromDefinition(a1, (unsigned __int16)v14, a2);
  return (unsigned __int16)v14;
}

```

## disassembly

```asm
0x180079298  mov     [rsp-8+arg_18], rbx
0x18007929d  push    rbp
0x18007929e  push    rsi
0x18007929f  push    rdi
0x1800792a0  push    r12
0x1800792a2  push    r13
0x1800792a4  push    r14
0x1800792a6  push    r15
0x1800792a8  lea     rbp, [rsp-10h]
0x1800792ad  sub     rsp, 110h
0x1800792b4  mov     rax, cs:__security_cookie
0x1800792bb  xor     rax, rsp
0x1800792be  mov     [rbp+40h+var_38], rax
0x1800792c2  mov     r15d, r8d
0x1800792c5  mov     rsi, rdx
0x1800792c8  mov     rbx, rcx
0x1800792cb  xor     r14d, r14d
0x1800792ce  cmp     [rcx+490h], r14d
0x1800792d5  jz      short loc_180079322
0x1800792d7  lea     rdx, aShaderproperty_0; "ShaderPropertyLayout::AddProperty() -- "...
0x1800792de  lea     rcx, [rsp+140h+var_C8]
0x1800792e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800792e8  nop
0x1800792e9  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800792f0  lea     rcx, [rbp+40h+var_90]
0x1800792f4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800792f9  mov     [rsp+140h+var_120], r14b
0x1800792fe  lea     r9, [rsp+140h+var_C8]
0x180079303  mov     rdx, rax
0x180079306  lea     rcx, [rsp+140h+pExceptionObject]
0x18007930b  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180079310  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180079317  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18007931c  call    _CxxThrowException_0
0x180079322  cmp     [rdx+10h], r14
0x180079326  jnz     short loc_180079372
0x180079328  lea     rdx, aShaderproperty_11; "ShaderPropertyLayout::AddProperty() -- "...
0x18007932f  lea     rcx, [rbp+40h+var_90]
0x180079333  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180079338  nop
0x180079339  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180079340  lea     rcx, [rsp+140h+var_C8]
0x180079345  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007934a  mov     [rsp+140h+var_120], r14b
0x18007934f  lea     r9, [rbp+40h+var_90]
0x180079353  mov     rdx, rax
0x180079356  lea     rcx, [rsp+140h+pExceptionObject]
0x18007935b  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180079360  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180079367  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18007936c  call    _CxxThrowException_0
0x180079372  lea     rdi, [rcx+38h]
0x180079376  mov     rax, [rdi+8]
0x18007937a  sub     rax, [rdi]
0x18007937d  cmp     rax, 7000h
0x180079383  jnz     short loc_1800793CF
0x180079385  lea     rdx, aShaderproperty_7; "ShaderPropertyLayout::AddProperty() -- "...
0x18007938c  lea     rcx, [rbp+40h+var_90]
0x180079390  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180079395  nop
0x180079396  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007939d  lea     rcx, [rsp+140h+var_C8]
0x1800793a2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800793a7  mov     [rsp+140h+var_120], r14b
0x1800793ac  lea     r9, [rbp+40h+var_90]
0x1800793b0  mov     rdx, rax
0x1800793b3  lea     rcx, [rsp+140h+pExceptionObject]
0x1800793b8  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x1800793bd  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x1800793c4  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x1800793c9  call    _CxxThrowException_0
0x1800793cf  mov     r13d, [rdx+20h]
0x1800793d3  mov     rcx, [rcx+480h]
0x1800793da  call    ?AddProperty@ShaderManager@Engine@Spectre@@QEAA?AW4ShaderProperty@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::ShaderManager::AddProperty(std::string const &)
0x1800793df  movzx   r12d, ax
0x1800793e3  mov     ecx, 0FFFFh
0x1800793e8  cmp     [rbx+r12*2+80h], cx
0x1800793f1  jz      short loc_180079454
0x1800793f3  mov     r8, rsi
0x1800793f6  lea     rdx, aShaderproperty; "ShaderPropertyLayout::AddProperty() -- "...
0x1800793fd  lea     rcx, [rbp+40h+var_90]
0x180079401  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180079406  nop
0x180079407  lea     r8, aIsAlreadyDefin; "' is already defined"
0x18007940e  mov     rdx, rax
0x180079411  lea     rcx, [rsp+140h+pExceptionObject]
0x180079416  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18007941b  mov     rbx, rax
0x18007941e  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180079425  lea     rcx, [rsp+140h+var_C8]
0x18007942a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007942f  mov     [rsp+140h+var_120], r14b
0x180079434  mov     r9, rbx
0x180079437  mov     rdx, rax
0x18007943a  lea     rcx, [rbp+40h+var_70]
0x18007943e  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180079443  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007944a  lea     rcx, [rbp+40h+var_70]; pExceptionObject
0x18007944e  call    _CxxThrowException_0
0x180079454  cmp     r15d, 1
0x180079458  jnz     loc_1800794E4
0x18007945e  lea     rdx, [rbp+40h+var_90]
0x180079462  mov     rcx, [rbx+480h]
0x180079469  call    ?GetGlobalProperties@ShaderManager@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderPropertyBlock@Engine@Spectre@@@std@@XZ; Spectre::Engine::ShaderManager::GetGlobalProperties(void)
0x18007946e  lea     rdx, [rsp+140h+var_110]
0x180079473  mov     rcx, [rax]
0x180079476  call    ?GetLayout@ShaderPropertyBlock@Engine@Spectre@@QEBA?AV?$shared_ptr@VShaderPropertyLayout@Engine@Spectre@@@std@@XZ; Spectre::Engine::ShaderPropertyBlock::GetLayout(void)
0x18007947b  nop
0x18007947c  mov     rcx, [rbp+40h+var_88]; this
0x180079480  test    rcx, rcx
0x180079483  jz      short loc_18007948A
0x180079485  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007948a  mov     r14, [rsp+140h+var_110]
0x18007948f  cmp     r14, rbx
0x180079492  jz      short loc_1800794D5
0x180079494  mov     rdx, rsi
0x180079497  mov     rcx, r14
0x18007949a  call    ?FindProperty@ShaderPropertyLayout@Engine@Spectre@@QEBA?AW4ShaderProperty@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::ShaderPropertyLayout::FindProperty(std::string const &)
0x18007949f  movzx   ecx, ax
0x1800794a2  mov     eax, 0FFFFh
0x1800794a7  cmp     [r14+rcx*2+80h], ax
0x1800794b0  jnz     short loc_1800794C8
0x1800794b2  mov     rcx, [rbx+480h]
0x1800794b9  mov     rdx, rsi
0x1800794bc  mov     rcx, [rcx+48D8h]
0x1800794c3  call    ?ExtendLayoutWithProperty@ShaderPropertyBlock@Engine@Spectre@@AEAA?AW4ShaderProperty@23@AEBUShaderPropertyDefinition@23@W4EShaderPropertyLinkage@23@@Z; Spectre::Engine::ShaderPropertyBlock::ExtendLayoutWithProperty(Spectre::Engine::ShaderPropertyDefinition const &,Spectre::Engine::EShaderPropertyLinkage)
0x1800794c8  mov     byte ptr [rbx+4D9h], 1
0x1800794cf  mov     r15d, 2
0x1800794d5  mov     rcx, [rsp+140h+var_108]; this
0x1800794da  test    rcx, rcx
0x1800794dd  jz      short loc_1800794E4
0x1800794df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800794e4  cmp     r13d, 8
0x1800794e8  jnz     loc_1800795E0
0x1800794ee  mov     rax, [rbx+70h]
0x1800794f2  mov     r14, rax
0x1800794f5  sub     r14, [rbx+68h]
0x1800794f9  sar     r14, 3
0x1800794fd  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180079507  imul    r14, rcx
0x18007950b  xorps   xmm0, xmm0
0x18007950e  movdqu  [rsp+140h+pExceptionObject], xmm0
0x180079514  xorps   xmm1, xmm1
0x180079517  movdqu  [rsp+140h+var_F0], xmm1
0x18007951d  mov     [rsp+140h+var_E0], r14d
0x180079522  xor     ecx, ecx
0x180079524  mov     [rsp+140h+var_DC], ecx
0x180079528  cmp     rax, [rbx+78h]
0x18007952c  jz      short loc_180079542
0x18007952e  lea     rdx, [rsp+140h+pExceptionObject]
0x180079533  mov     rcx, rax
0x180079536  call    ??$_Construct_in_place@UTextureElement@ShaderPropertyLayout@Engine@Spectre@@AEBU1234@@std@@YAXAEAUTextureElement@ShaderPropertyLayout@Engine@Spectre@@AEBU1234@@Z; std::_Construct_in_place<Spectre::Engine::ShaderPropertyLayout::TextureElement,Spectre::Engine::ShaderPropertyLayout::TextureElement const &>(Spectre::Engine::ShaderPropertyLayout::TextureElement &,Spectre::Engine::ShaderPropertyLayout::TextureElement const &)
0x18007953b  add     qword ptr [rbx+70h], 28h ; '('
0x180079540  jmp     short loc_180079553
0x180079542  lea     r8, [rsp+140h+pExceptionObject]
0x180079547  mov     rdx, rax
0x18007954a  lea     rcx, [rbx+68h]
0x18007954e  call    ??$_Emplace_reallocate@AEBUTextureElement@ShaderPropertyLayout@Engine@Spectre@@@?$vector@UTextureElement@ShaderPropertyLayout@Engine@Spectre@@V?$allocator@UTextureElement@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@AEAAPEAUTextureElement@ShaderPropertyLayout@Engine@Spectre@@QEAU2345@AEBU2345@@Z; std::vector<Spectre::Engine::ShaderPropertyLayout::TextureElement>::_Emplace_reallocate<Spectre::Engine::ShaderPropertyLayout::TextureElement const &>(Spectre::Engine::ShaderPropertyLayout::TextureElement * const,Spectre::Engine::ShaderPropertyLayout::TextureElement const &)
0x180079553  mov     rax, [rdi+8]
0x180079557  sub     rax, [rdi]
0x18007955a  sar     rax, 3
0x18007955e  mov     rcx, 6DB6DB6DB6DB6DB7h
0x180079568  imul    rax, rcx
0x18007956c  mov     [rbx+r12*2+80h], ax
0x180079575  mov     rdx, rsi
0x180079578  lea     rcx, [rsp+140h+var_C8]
0x18007957d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180079582  mov     [rbp+40h+var_A8], r12w
0x180079587  xor     eax, eax
0x180079589  mov     [rbp+40h+var_A6], ax
0x18007958d  mov     [rbp+40h+var_A4], 8
0x180079594  mov     [rbp+40h+var_A0], r14d
0x180079598  mov     [rbp+40h+var_9C], eax
0x18007959b  mov     [rbp+40h+var_98], r15d
0x18007959f  mov     [rbp+40h+var_94], eax
0x1800795a2  mov     rdx, [rdi+8]
0x1800795a6  lea     r8, [rsp+140h+var_C8]
0x1800795ab  cmp     rdx, [rdi+10h]
0x1800795af  jz      short loc_1800795BD
0x1800795b1  call    ??$construct@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@AEBU1234@@?$_Default_allocator_traits@V?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@SAXAEAV?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@1@QEAUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@AEBU3456@@Z; std::_Default_allocator_traits<std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>>::construct<Spectre::Engine::ShaderPropertyLayout::PropertyInfo,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo> &,Spectre::Engine::ShaderPropertyLayout::PropertyInfo * const,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &)
0x1800795b6  add     qword ptr [rdi+8], 38h ; '8'
0x1800795bb  jmp     short loc_1800795C6
0x1800795bd  mov     rcx, rdi
0x1800795c0  call    ??$_Emplace_reallocate@AEBUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@?$vector@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@V?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@AEAAPEAUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@QEAU2345@AEBU2345@@Z; std::vector<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>::_Emplace_reallocate<Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(Spectre::Engine::ShaderPropertyLayout::PropertyInfo * const,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &)
0x1800795c5  nop
0x1800795c6  lea     rcx, [rsp+140h+var_C8]
0x1800795cb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800795d0  nop
0x1800795d1  lea     rcx, [rsp+140h+pExceptionObject]
0x1800795d6  call    ??1?$pair@V?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@V?$shared_ptr@VMesh@Engine@Spectre@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<Spectre::Engine::SceneNode>,std::shared_ptr<Spectre::Engine::Mesh>>::~pair<std::shared_ptr<Spectre::Engine::SceneNode>,std::shared_ptr<Spectre::Engine::Mesh>>(void)
0x1800795db  jmp     loc_1800796C3
0x1800795e0  mov     rcx, rbx; this
0x1800795e3  call    ?AlignBuffer@ShaderPropertyLayout@Engine@Spectre@@AEAAXXZ; Spectre::Engine::ShaderPropertyLayout::AlignBuffer(void)
0x1800795e8  lea     r8, [rbx+50h]
0x1800795ec  mov     r9, [r8]
0x1800795ef  mov     r14, [r8+8]
0x1800795f3  sub     r14, r9
0x1800795f6  sar     r14, 2
0x1800795fa  mov     ecx, r13d
0x1800795fd  call    ?GetTypeSizeInElements@ShaderPropertyLayout@Engine@Spectre@@SAIW4ShaderPropertyType@23@@Z; Spectre::Engine::ShaderPropertyLayout::GetTypeSizeInElements(Spectre::Engine::ShaderPropertyType)
0x180079602  add     eax, r14d
0x180079605  mov     edx, eax
0x180079607  cmp     rdx, r14
0x18007960a  jnb     short loc_180079612
0x18007960c  lea     rax, [r9+rax*4]
0x180079610  jmp     short loc_18007963A
0x180079612  jbe     short loc_18007963E
0x180079614  mov     rax, [r8+10h]
0x180079618  sub     rax, r9
0x18007961b  sar     rax, 2
0x18007961f  cmp     rdx, rax
0x180079622  jbe     short loc_18007962E
0x180079624  mov     rcx, r8
0x180079627  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@TValueElement@ShaderPropertyLayout@Engine@Spectre@@V?$allocator@TValueElement@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Spectre::Engine::ShaderPropertyLayout::ValueElement>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18007962c  jmp     short loc_18007963E
0x18007962e  sub     rdx, r14
0x180079631  mov     rcx, [r8+8]
0x180079635  call    ??$_Uninitialized_value_construct_n@V?$allocator@TValueElement@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@YAPEATValueElement@ShaderPropertyLayout@Engine@Spectre@@PEAT1234@_KAEAV?$allocator@TValueElement@ShaderPropertyLayout@Engine@Spectre@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Spectre::Engine::ShaderPropertyLayout::ValueElement>>(Spectre::Engine::ShaderPropertyLayout::ValueElement *,unsigned __int64,std::allocator<Spectre::Engine::ShaderPropertyLayout::ValueElement> &)
0x18007963a  mov     [r8+8], rax
0x18007963e  mov     rax, [rdi+8]
0x180079642  sub     rax, [rdi]
0x180079645  sar     rax, 3
0x180079649  mov     rcx, 6DB6DB6DB6DB6DB7h
0x180079653  imul    rax, rcx
0x180079657  mov     [rbx+r12*2+80h], ax
0x180079660  mov     rdx, rsi
0x180079663  lea     rcx, [rsp+140h+pExceptionObject]
0x180079668  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18007966d  mov     word ptr [rsp+140h+var_E0], r12w
0x180079673  xor     eax, eax
0x180079675  mov     word ptr [rsp+140h+var_E0+2], ax
0x18007967a  mov     [rsp+140h+var_DC], r13d
0x18007967f  mov     [rsp+140h+var_D8], r14d
0x180079684  mov     [rsp+140h+var_D4], 1
0x18007968c  mov     [rsp+140h+var_D0], r15d
0x180079691  mov     [rsp+140h+var_CC], eax
0x180079695  mov     rdx, [rdi+8]
0x180079699  lea     r8, [rsp+140h+pExceptionObject]
0x18007969e  cmp     rdx, [rdi+10h]
0x1800796a2  jz      short loc_1800796B0
0x1800796a4  call    ??$construct@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@AEBU1234@@?$_Default_allocator_traits@V?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@SAXAEAV?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@1@QEAUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@AEBU3456@@Z; std::_Default_allocator_traits<std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>>::construct<Spectre::Engine::ShaderPropertyLayout::PropertyInfo,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo> &,Spectre::Engine::ShaderPropertyLayout::PropertyInfo * const,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &)
0x1800796a9  add     qword ptr [rdi+8], 38h ; '8'
0x1800796ae  jmp     short loc_1800796B9
0x1800796b0  mov     rcx, rdi
0x1800796b3  call    ??$_Emplace_reallocate@AEBUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@?$vector@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@V?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@AEAAPEAUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@QEAU2345@AEBU2345@@Z; std::vector<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>::_Emplace_reallocate<Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(Spectre::Engine::ShaderPropertyLayout::PropertyInfo * const,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &)
0x1800796b8  nop
0x1800796b9  lea     rcx, [rsp+140h+pExceptionObject]
0x1800796be  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800796c3  cmp     r15d, 2
0x1800796c7  setz    al
0x1800796ca  or      [rbx+4D8h], al
0x1800796d0  mov     r8, rsi
0x1800796d3  movzx   edx, r12w
0x1800796d7  mov     rcx, rbx
0x1800796da  call    ?SetPropertyDefaultFromDefinition@ShaderPropertyLayout@Engine@Spectre@@AEAAXW4ShaderProperty@23@AEBUShaderPropertyDefinition@23@@Z; Spectre::Engine::ShaderPropertyLayout::SetPropertyDefaultFromDefinition(Spectre::Engine::ShaderProperty,Spectre::Engine::ShaderPropertyDefinition const &)
0x1800796df  movzx   eax, r12w
0x1800796e3  mov     rcx, [rbp+40h+var_38]
0x1800796e7  xor     rcx, rsp; StackCookie
0x1800796ea  call    __security_check_cookie
0x1800796ef  mov     rbx, [rsp+140h+arg_18]
0x1800796f7  add     rsp, 110h
0x1800796fe  pop     r15
0x180079700  pop     r14
0x180079702  pop     r13
0x180079704  pop     r12
0x180079706  pop     rdi
0x180079707  pop     rsi
0x180079708  pop     rbp
0x180079709  retn
```
