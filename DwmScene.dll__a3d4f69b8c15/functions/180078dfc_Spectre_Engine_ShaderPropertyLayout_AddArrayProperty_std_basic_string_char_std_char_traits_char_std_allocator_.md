# Spectre::Engine::ShaderPropertyLayout::AddArrayProperty(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,Spectre::Engine::ShaderPropertyType,uint)

- ea: `0x180078dfc`
- end: `0x1800791ca`
- name: `?AddArrayProperty@ShaderPropertyLayout@Engine@Spectre@@QEAA?AW4ShaderProperty@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderPropertyType@23@I@Z`
- size: `974`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18004386c`
- `0x180043d70`
- `0x180075690`
- `0x180076b70`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180012ba8`
- `0x180018318`
- `0x18001c630`
- `0x18001c720`
- `0x180038ddc`
- `0x18004bfc0`
- `0x180078208`
- `0x180078580`
- `0x1800786e0`
- `0x18007872c`
- `0x180078dfc`
- `0x180079710`
- `0x180079e1c`

## string_xrefs

- `0x180079134`: `' is already defined`
- `0x180078e51`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180078eb8`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180078f32`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180078f81`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180078ffd`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x18007914a`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180079192`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180078ea6`: `ShaderPropertyLayout::AddArrayProperty() -- property block already has maximum number of properties`
- `0x180078e3f`: `ShaderPropertyLayout::AddArrayProperty() -- properties can only be added during declaration phase before EndDeclaration()`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Spectre::Engine::ShaderPropertyLayout::AddArrayProperty(
        Spectre::Engine::ShaderPropertyLayout *this,
        __int64 a2,
        unsigned int a3,
        unsigned int a4)
{
  int v8; // eax
  int v9; // r8d
  _QWORD *v10; // rdi
  int v11; // eax
  int v12; // r8d
  __int64 v13; // r15
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  int v17; // r8d
  __int64 v18; // r13
  int v19; // eax
  int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r14
  __int64 v24; // r8
  unsigned __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v28; // rax
  int v29; // ebx
  int v30; // eax
  int v31; // r8d
  int v32; // eax
  int v33; // r8d
  unsigned int v34; // [rsp+30h] [rbp-D0h]
  _BYTE v36[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v39[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v40; // [rsp+D8h] [rbp-28h]
  __int16 v41; // [rsp+DAh] [rbp-26h]
  unsigned int v42; // [rsp+DCh] [rbp-24h]
  int v43; // [rsp+E0h] [rbp-20h]
  unsigned int v44; // [rsp+E4h] [rbp-1Ch]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  _BYTE v46[56]; // [rsp+F0h] [rbp-10h] BYREF

  if ( *((_DWORD *)this + 292) )
  {
    std::string::string(
      v36,
      "ShaderPropertyLayout::AddArrayProperty() -- properties can only be added during declaration phase before EndDeclaration()");
    v8 = std::string::string(
           v37,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v8,
      v9,
      (unsigned int)v36,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( !*(_QWORD *)(a2 + 16) )
  {
    std::string::string(v37, "ShaderPropertyLayout::AddArrayProperty() -- property cannot have an empty name");
    v32 = std::string::string(
            v36,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)v46,
      v32,
      v33,
      (unsigned int)v37,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)v46;
  }
  v10 = (_QWORD *)((char *)this + 56);
  if ( *((_QWORD *)this + 8) - *((_QWORD *)this + 7) == 28672 )
  {
    std::string::string(
      v37,
      "ShaderPropertyLayout::AddArrayProperty() -- property block already has maximum number of properties");
    v11 = std::string::string(
            v36,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v11,
      v12,
      (unsigned int)v37,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v13 = (unsigned __int16)Spectre::Engine::ShaderManager::AddProperty(*((_QWORD *)this + 144));
  if ( *((_WORD *)this + v13 + 64) != 0xFFFF )
  {
    v28 = std::operator+<char>(v37, "ShaderPropertyLayout::AddArrayProperty() -- variable '", a2);
    v29 = std::operator+<char>(pExceptionObject, v28, "' is already defined");
    v30 = std::string::string(
            v36,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v46, v30, v31, v29, 0);
    throw (Spectre::Engine::EngineInvalidArgException *)v46;
  }
  if ( a3 != 5 && a3 != 7 )
  {
    std::string::string(
      v37,
      "ShaderPropertyLayout::AddArrayProperty() -- Only Vector4 and Matrix arrays are currently supported");
    v14 = std::string::string(
            v36,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v14,
      v15,
      (unsigned int)v37,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( a4 <= 1 )
  {
    std::string::string(
      v37,
      "ShaderPropertyLayout::AddArrayProperty() -- Array size must be more than 1. For arrays of size 1 use AddProperty instead");
    v16 = std::string::string(
            v36,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v16,
      v17,
      (unsigned int)v37,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  Spectre::Engine::ShaderPropertyLayout::AlignBuffer(this);
  v18 = (__int64)(*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) >> 2;
  v34 = v18 + a4 * Spectre::Engine::ShaderPropertyLayout::GetTypeSizeInElements(a3);
  if ( v34 > 0x4064 )
  {
    std::string::string(
      v37,
      "ShaderPropertyLayout::AddArrayProperty() -- Array extends property block past maximum capacity");
    v19 = std::string::string(
            v36,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v19,
      v20,
      (unsigned int)v37,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  std::string::string(v39, a2);
  v40 = v13;
  v41 = 0;
  v42 = a3;
  v43 = v18;
  v44 = a4;
  v45 = 0;
  v22 = v10[1];
  v23 = 0x6DB6DB6DB6DB6DB7LL * ((v22 - *v10) >> 3);
  if ( v22 == v10[2] )
  {
    std::vector<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>::_Emplace_reallocate<Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(
      v10,
      v22,
      v39);
  }
  else
  {
    std::_Default_allocator_traits<std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>>::construct<Spectre::Engine::ShaderPropertyLayout::PropertyInfo,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(
      v21,
      v22,
      v39);
    v10[1] += 56LL;
  }
  *((_WORD *)this + v13 + 64) = v23;
  v24 = *((_QWORD *)this + 10);
  v25 = (*((_QWORD *)this + 11) - v24) >> 2;
  if ( v34 < v25 )
  {
    v26 = v24 + 4LL * v34;
LABEL_23:
    *((_QWORD *)this + 11) = v26;
    goto LABEL_24;
  }
  if ( v34 > v25 )
  {
    if ( v34 <= (unsigned __int64)((*((_QWORD *)this + 12) - v24) >> 2) )
    {
      v26 = std::_Uninitialized_value_construct_n<std::allocator<Spectre::Engine::ShaderPropertyLayout::ValueElement>>(
              *((_QWORD *)this + 11),
              v34 - v25,
              (char *)this + 80);
      goto LABEL_23;
    }
    std::vector<Spectre::Engine::ShaderPropertyLayout::ValueElement>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 80);
  }
LABEL_24:
  std::string::_Tidy_deallocate(v39);
  return (unsigned __int16)v13;
}

```

## disassembly

```asm
0x180078dfc  push    rbp
0x180078dfe  push    rbx
0x180078dff  push    rsi
0x180078e00  push    rdi
0x180078e01  push    r12
0x180078e03  push    r13
0x180078e05  push    r14
0x180078e07  push    r15
0x180078e09  lea     rbp, [rsp-38h]
0x180078e0e  sub     rsp, 138h
0x180078e15  mov     rax, cs:__security_cookie
0x180078e1c  xor     rax, rsp
0x180078e1f  mov     [rbp+70h+var_48], rax
0x180078e23  mov     ebx, r9d
0x180078e26  mov     [rsp+170h+var_138], ebx
0x180078e2a  mov     r14d, r8d
0x180078e2d  mov     r12, rdx
0x180078e30  mov     rsi, rcx
0x180078e33  xor     r13d, r13d
0x180078e36  cmp     [rcx+490h], r13d
0x180078e3d  jz      short loc_180078E89
0x180078e3f  lea     rdx, aShaderproperty_5; "ShaderPropertyLayout::AddArrayProperty("...
0x180078e46  lea     rcx, [rsp+170h+var_130]
0x180078e4b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078e50  nop
0x180078e51  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180078e58  lea     rcx, [rsp+170h+var_110]
0x180078e5d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078e62  mov     [rsp+170h+var_150], r13b
0x180078e67  lea     r9, [rsp+170h+var_130]
0x180078e6c  mov     rdx, rax
0x180078e6f  lea     rcx, [rbp+70h+pExceptionObject]
0x180078e73  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180078e78  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180078e7f  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180078e83  call    _CxxThrowException_0
0x180078e89  cmp     [rdx+10h], r13
0x180078e8d  jz      loc_180079180
0x180078e93  lea     rdi, [rcx+38h]
0x180078e97  mov     rax, [rdi+8]
0x180078e9b  sub     rax, [rdi]
0x180078e9e  cmp     rax, 7000h
0x180078ea4  jnz     short loc_180078EF0
0x180078ea6  lea     rdx, aShaderproperty_18; "ShaderPropertyLayout::AddArrayProperty("...
0x180078ead  lea     rcx, [rsp+170h+var_110]
0x180078eb2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078eb7  nop
0x180078eb8  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180078ebf  lea     rcx, [rsp+170h+var_130]
0x180078ec4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078ec9  mov     [rsp+170h+var_150], r13b
0x180078ece  lea     r9, [rsp+170h+var_110]
0x180078ed3  mov     rdx, rax
0x180078ed6  lea     rcx, [rbp+70h+pExceptionObject]
0x180078eda  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180078edf  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180078ee6  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180078eea  call    _CxxThrowException_0
0x180078ef0  mov     rcx, [rcx+480h]
0x180078ef7  call    ?AddProperty@ShaderManager@Engine@Spectre@@QEAA?AW4ShaderProperty@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::ShaderManager::AddProperty(std::string const &)
0x180078efc  movzx   r15d, ax
0x180078f00  mov     eax, 0FFFFh
0x180078f05  cmp     [rsi+r15*2+80h], ax
0x180078f0e  jnz     loc_18007911F
0x180078f14  cmp     r14d, 5
0x180078f18  jz      short loc_180078F6A
0x180078f1a  cmp     r14d, 7
0x180078f1e  jz      short loc_180078F6A
0x180078f20  lea     rdx, aShaderproperty_20; "ShaderPropertyLayout::AddArrayProperty("...
0x180078f27  lea     rcx, [rsp+170h+var_110]
0x180078f2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078f31  nop
0x180078f32  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180078f39  lea     rcx, [rsp+170h+var_130]
0x180078f3e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078f43  mov     [rsp+170h+var_150], r13b
0x180078f48  lea     r9, [rsp+170h+var_110]
0x180078f4d  mov     rdx, rax
0x180078f50  lea     rcx, [rbp+70h+pExceptionObject]
0x180078f54  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180078f59  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180078f60  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180078f64  call    _CxxThrowException_0
0x180078f6a  cmp     ebx, 1
0x180078f6d  ja      short loc_180078FB9
0x180078f6f  lea     rdx, aShaderproperty_8; "ShaderPropertyLayout::AddArrayProperty("...
0x180078f76  lea     rcx, [rsp+170h+var_110]
0x180078f7b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078f80  nop
0x180078f81  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180078f88  lea     rcx, [rsp+170h+var_130]
0x180078f8d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078f92  mov     [rsp+170h+var_150], r13b
0x180078f97  lea     r9, [rsp+170h+var_110]
0x180078f9c  mov     rdx, rax
0x180078f9f  lea     rcx, [rbp+70h+pExceptionObject]
0x180078fa3  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180078fa8  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180078faf  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180078fb3  call    _CxxThrowException_0
0x180078fb9  mov     rcx, rsi; this
0x180078fbc  call    ?AlignBuffer@ShaderPropertyLayout@Engine@Spectre@@AEAAXXZ; Spectre::Engine::ShaderPropertyLayout::AlignBuffer(void)
0x180078fc1  lea     rbx, [rsi+50h]
0x180078fc5  mov     r13, [rbx+8]
0x180078fc9  sub     r13, [rbx]
0x180078fcc  sar     r13, 2
0x180078fd0  mov     ecx, r14d
0x180078fd3  call    ?GetTypeSizeInElements@ShaderPropertyLayout@Engine@Spectre@@SAIW4ShaderPropertyType@23@@Z; Spectre::Engine::ShaderPropertyLayout::GetTypeSizeInElements(Spectre::Engine::ShaderPropertyType)
0x180078fd8  imul    eax, [rsp+170h+var_138]
0x180078fdd  add     eax, r13d
0x180078fe0  mov     [rsp+170h+var_140], eax
0x180078fe4  cmp     eax, 4064h
0x180078fe9  jbe     short loc_180079035
0x180078feb  lea     rdx, aShaderproperty_2; "ShaderPropertyLayout::AddArrayProperty("...
0x180078ff2  lea     rcx, [rsp+170h+var_110]
0x180078ff7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078ffc  nop
0x180078ffd  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180079004  lea     rcx, [rsp+170h+var_130]
0x180079009  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007900e  mov     [rsp+170h+var_150], 0
0x180079013  lea     r9, [rsp+170h+var_110]
0x180079018  mov     rdx, rax
0x18007901b  lea     rcx, [rbp+70h+pExceptionObject]
0x18007901f  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180079024  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007902b  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x18007902f  call    _CxxThrowException_0
0x180079035  mov     rdx, r12
0x180079038  lea     rcx, [rbp+70h+var_B8]
0x18007903c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180079041  mov     [rbp+70h+var_98], r15w
0x180079046  xor     eax, eax
0x180079048  mov     [rbp+70h+var_96], ax
0x18007904c  mov     [rbp+70h+var_94], r14d
0x180079050  mov     [rbp+70h+var_90], r13d
0x180079054  mov     eax, [rsp+170h+var_138]
0x180079058  mov     [rbp+70h+var_8C], eax
0x18007905b  mov     [rbp+70h+var_88], 0
0x180079063  mov     rdx, [rdi+8]
0x180079067  mov     r14, rdx
0x18007906a  sub     r14, [rdi]
0x18007906d  sar     r14, 3
0x180079071  mov     rax, 6DB6DB6DB6DB6DB7h
0x18007907b  imul    r14, rax
0x18007907f  lea     r8, [rbp+70h+var_B8]
0x180079083  cmp     rdx, [rdi+10h]
0x180079087  jz      short loc_180079095
0x180079089  call    ??$construct@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@AEBU1234@@?$_Default_allocator_traits@V?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@SAXAEAV?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@1@QEAUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@AEBU3456@@Z; std::_Default_allocator_traits<std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>>::construct<Spectre::Engine::ShaderPropertyLayout::PropertyInfo,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(std::allocator<Spectre::Engine::ShaderPropertyLayout::PropertyInfo> &,Spectre::Engine::ShaderPropertyLayout::PropertyInfo * const,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &)
0x18007908e  add     qword ptr [rdi+8], 38h ; '8'
0x180079093  jmp     short loc_18007909D
0x180079095  mov     rcx, rdi
0x180079098  call    ??$_Emplace_reallocate@AEBUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@?$vector@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@V?$allocator@UPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@AEAAPEAUPropertyInfo@ShaderPropertyLayout@Engine@Spectre@@QEAU2345@AEBU2345@@Z; std::vector<Spectre::Engine::ShaderPropertyLayout::PropertyInfo>::_Emplace_reallocate<Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &>(Spectre::Engine::ShaderPropertyLayout::PropertyInfo * const,Spectre::Engine::ShaderPropertyLayout::PropertyInfo const &)
0x18007909d  mov     [rsi+r15*2+80h], r14w
0x1800790a6  mov     edx, [rsp+170h+var_140]
0x1800790aa  mov     r8, [rbx]
0x1800790ad  mov     rcx, [rbx+8]
0x1800790b1  sub     rcx, r8
0x1800790b4  sar     rcx, 2
0x1800790b8  cmp     rdx, rcx
0x1800790bb  jnb     short loc_1800790C3
0x1800790bd  lea     rax, [r8+rdx*4]
0x1800790c1  jmp     short loc_1800790EE
0x1800790c3  jbe     short loc_1800790F2
0x1800790c5  mov     rax, [rbx+10h]
0x1800790c9  sub     rax, r8
0x1800790cc  sar     rax, 2
0x1800790d0  cmp     rdx, rax
0x1800790d3  jbe     short loc_1800790DF
0x1800790d5  mov     rcx, rbx
0x1800790d8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@TValueElement@ShaderPropertyLayout@Engine@Spectre@@V?$allocator@TValueElement@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Spectre::Engine::ShaderPropertyLayout::ValueElement>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800790dd  jmp     short loc_1800790F2
0x1800790df  sub     rdx, rcx
0x1800790e2  mov     r8, rbx
0x1800790e5  mov     rcx, [rbx+8]
0x1800790e9  call    ??$_Uninitialized_value_construct_n@V?$allocator@TValueElement@ShaderPropertyLayout@Engine@Spectre@@@std@@@std@@YAPEATValueElement@ShaderPropertyLayout@Engine@Spectre@@PEAT1234@_KAEAV?$allocator@TValueElement@ShaderPropertyLayout@Engine@Spectre@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Spectre::Engine::ShaderPropertyLayout::ValueElement>>(Spectre::Engine::ShaderPropertyLayout::ValueElement *,unsigned __int64,std::allocator<Spectre::Engine::ShaderPropertyLayout::ValueElement> &)
0x1800790ee  mov     [rbx+8], rax
0x1800790f2  lea     rcx, [rbp+70h+var_B8]
0x1800790f6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800790fb  movzx   eax, r15w
0x1800790ff  mov     rcx, [rbp+70h+var_48]
0x180079103  xor     rcx, rsp; StackCookie
0x180079106  call    __security_check_cookie
0x18007910b  add     rsp, 138h
0x180079112  pop     r15
0x180079114  pop     r14
0x180079116  pop     r13
0x180079118  pop     r12
0x18007911a  pop     rdi
0x18007911b  pop     rsi
0x18007911c  pop     rbx
0x18007911d  pop     rbp
0x18007911e  retn
0x18007911f  mov     r8, r12
0x180079122  lea     rdx, aShaderproperty_29; "ShaderPropertyLayout::AddArrayProperty("...
0x180079129  lea     rcx, [rsp+170h+var_110]
0x18007912e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180079133  nop
0x180079134  lea     r8, aIsAlreadyDefin; "' is already defined"
0x18007913b  mov     rdx, rax
0x18007913e  lea     rcx, [rbp+70h+pExceptionObject]
0x180079142  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180079147  mov     rbx, rax
0x18007914a  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180079151  lea     rcx, [rsp+170h+var_130]
0x180079156  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007915b  mov     [rsp+170h+var_150], r13b
0x180079160  mov     r9, rbx
0x180079163  mov     rdx, rax
0x180079166  lea     rcx, [rbp+70h+var_80]
0x18007916a  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007916f  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180079176  lea     rcx, [rbp+70h+var_80]; pExceptionObject
0x18007917a  call    _CxxThrowException_0
0x180079180  lea     rdx, aShaderproperty_3; "ShaderPropertyLayout::AddArrayProperty("...
0x180079187  lea     rcx, [rsp+170h+var_110]
0x18007918c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180079191  nop
0x180079192  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180079199  lea     rcx, [rsp+170h+var_130]
0x18007919e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800791a3  mov     [rsp+170h+var_150], r13b
0x1800791a8  lea     r9, [rsp+170h+var_110]
0x1800791ad  mov     rdx, rax
0x1800791b0  lea     rcx, [rbp+70h+var_80]
0x1800791b4  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x1800791b9  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x1800791c0  lea     rcx, [rbp+70h+var_80]; pExceptionObject
0x1800791c4  call    _CxxThrowException_0
```
