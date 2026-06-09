# Spectre::Engine::ShaderPropertyBlock::GetTexture(Spectre::Engine::ShaderProperty)

- ea: `0x18007bce8`
- end: `0x18007be17`
- name: `?GetTexture@ShaderPropertyBlock@Engine@Spectre@@QEBA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@W4ShaderProperty@23@@Z`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180041f9c`
- `0x18006b410`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180012df8`
- `0x18001c6e0`
- `0x180038ddc`
- `0x18004c8d8`
- `0x18007bce8`

## string_xrefs

- `0x18007bd54`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`
- `0x18007bda9`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Spectre::Engine::ShaderPropertyBlock::GetTexture(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r10
  __int64 v5; // rdx
  __int64 PropertyName; // rax
  int v7; // ebx
  int v8; // eax
  int v9; // r8d
  __int64 v10; // rax
  int v11; // eax
  int v12; // r8d
  __int64 v13; // r9
  _BYTE v15[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v18[32]; // [rsp+B8h] [rbp+2Fh] BYREF

  v4 = *(_QWORD *)(a1 + 16);
  v5 = *(unsigned __int16 *)(v4 + 2LL * (unsigned __int16)a3 + 128);
  if ( (_WORD)v5 == 0xFFFF )
  {
    PropertyName = Spectre::Engine::ShaderManager::GetPropertyName(*(_QWORD *)(v4 + 1152), v16, a3);
    v7 = std::operator+<char>(v18, "Property does not exist: ", PropertyName);
    v8 = std::string::string(
           v15,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertyblock.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)pExceptionObject, v8, v9, v7, 0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v10 = *(_QWORD *)(v4 + 56);
  if ( *(_DWORD *)(56 * v5 + v10 + 36) != 8 )
  {
    std::string::string(v16, "ShaderPropertyBlock::GetTexture() -- Property is not of type Texture");
    v11 = std::string::string(
            v15,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertyblock.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v11,
      v12,
      (unsigned int)v16,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
    a2,
    *(_QWORD *)(a1 + 56) + 40LL * *(unsigned int *)(56 * v5 + v10 + 40));
  return v13;
}

```

## disassembly

```asm
0x18007bce8  mov     [rsp-8+arg_18], rbx
0x18007bced  push    rbp
0x18007bcee  lea     rbp, [rsp-57h]
0x18007bcf3  sub     rsp, 0E0h
0x18007bcfa  mov     rax, cs:__security_cookie
0x18007bd01  xor     rax, rsp
0x18007bd04  mov     [rbp+57h+var_8], rax
0x18007bd08  mov     r9, rdx
0x18007bd0b  mov     r11, rcx
0x18007bd0e  mov     [rbp+57h+var_B0], rdx
0x18007bd12  mov     r10, [rcx+10h]
0x18007bd16  movzx   eax, r8w
0x18007bd1a  movzx   edx, word ptr [r10+rax*2+80h]
0x18007bd23  mov     eax, 0FFFFh
0x18007bd28  cmp     dx, ax
0x18007bd2b  jnz     short loc_18007BD89
0x18007bd2d  lea     rdx, [rbp+57h+var_80]
0x18007bd31  mov     rcx, [r10+480h]
0x18007bd38  call    ?GetPropertyName@ShaderManager@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@23@@Z; Spectre::Engine::ShaderManager::GetPropertyName(Spectre::Engine::ShaderProperty)
0x18007bd3d  nop
0x18007bd3e  mov     r8, rax
0x18007bd41  lea     rdx, aPropertyDoesNo; "Property does not exist: "
0x18007bd48  lea     rcx, [rbp+57h+var_28]
0x18007bd4c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18007bd51  mov     rbx, rax
0x18007bd54  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007bd5b  lea     rcx, [rbp+57h+var_A0]
0x18007bd5f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007bd64  mov     [rsp+0E0h+var_C0], 0
0x18007bd69  mov     r9, rbx
0x18007bd6c  mov     rdx, rax
0x18007bd6f  lea     rcx, [rbp+57h+pExceptionObject]
0x18007bd73  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007bd78  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007bd7f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007bd83  call    _CxxThrowException_0
0x18007bd89  imul    rcx, rdx, 38h ; '8'
0x18007bd8d  mov     rax, [r10+38h]
0x18007bd91  cmp     dword ptr [rcx+rax+24h], 8
0x18007bd96  jz      short loc_18007BDDF
0x18007bd98  lea     rdx, aShaderproperty_27; "ShaderPropertyBlock::GetTexture() -- Pr"...
0x18007bd9f  lea     rcx, [rbp+57h+var_80]
0x18007bda3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007bda8  nop
0x18007bda9  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007bdb0  lea     rcx, [rbp+57h+var_A0]
0x18007bdb4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007bdb9  mov     [rsp+0E0h+var_C0], 0
0x18007bdbe  lea     r9, [rbp+57h+var_80]
0x18007bdc2  mov     rdx, rax
0x18007bdc5  lea     rcx, [rbp+57h+pExceptionObject]
0x18007bdc9  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007bdce  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007bdd5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007bdd9  call    _CxxThrowException_0
0x18007bddf  mov     ecx, [rcx+rax+28h]
0x18007bde3  lea     rdx, [rcx+rcx*4]
0x18007bde7  mov     rcx, [r11+38h]
0x18007bdeb  lea     rdx, [rcx+rdx*8]
0x18007bdef  mov     rcx, r9
0x18007bdf2  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18007bdf7  mov     rax, r9
0x18007bdfa  mov     rcx, [rbp+57h+var_8]
0x18007bdfe  xor     rcx, rsp; StackCookie
0x18007be01  call    __security_check_cookie
0x18007be06  mov     rbx, [rsp+0E0h+arg_18]
0x18007be0e  add     rsp, 0E0h
0x18007be15  pop     rbp
0x18007be16  retn
```
