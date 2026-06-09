# Spectre::Engine::ShaderPropertyBlock::SetTextureSampler(Spectre::Engine::ShaderProperty,std::shared_ptr<Spectre::Engine::Sampler>)

- ea: `0x18007c4a8`
- end: `0x18007c635`
- name: `?SetTextureSampler@ShaderPropertyBlock@Engine@Spectre@@QEAAXW4ShaderProperty@23@V?$shared_ptr@VSampler@Engine@Spectre@@@std@@@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007c438`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x18001c6e0`
- `0x180038ddc`
- `0x18004c8d8`
- `0x18007c4a8`

## string_xrefs

- `0x18007c514`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`
- `0x18007c569`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`
- `0x18007c5b7`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Spectre::Engine::ShaderPropertyBlock::SetTextureSampler(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 PropertyName; // rax
  int v9; // ebx
  int v10; // eax
  int v11; // r8d
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  int v17; // r8d
  std::_Ref_count_base *v18; // rcx
  _BYTE v19[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v22[32]; // [rsp+B8h] [rbp+2Fh] BYREF

  v4 = a2;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = *(unsigned __int16 *)(v6 + 2LL * a2 + 128);
  if ( (_WORD)v7 == 0xFFFF )
  {
    PropertyName = Spectre::Engine::ShaderManager::GetPropertyName(*(_QWORD *)(v6 + 1152), v20, v4);
    v9 = std::operator+<char>(v22, "Property does not exist: ", PropertyName);
    v10 = std::string::string(
            v19,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertyblock.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v10,
      v11,
      v9,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v12 = 56 * v7;
  v13 = *(_QWORD *)(v6 + 56);
  if ( *(_DWORD *)(56 * v7 + v13 + 36) != 8 )
  {
    std::string::string(v20, "ShaderPropertyBlock::SetTexture() -- Property is not of type Texture");
    v14 = std::string::string(
            v19,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertyblock.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v14,
      v15,
      (unsigned int)v20,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( *(_DWORD *)(v12 + v13 + 48) == 2 )
  {
    std::string::string(v19, "ShaderPropertyBlock::SetTextureSampler() -- Cannot set the value of an imported property");
    v16 = std::string::string(
            v20,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertyblock.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v16,
      v17,
      (unsigned int)v19,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(
    *(_QWORD *)(a1 + 56) + 8 * (5LL * *(unsigned int *)(v12 + v13 + 40) + 2),
    a3);
  v18 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
}

```

## disassembly

```asm
0x18007c4a8  mov     [rsp-8+arg_18], rbx
0x18007c4ad  push    rbp
0x18007c4ae  lea     rbp, [rsp-57h]
0x18007c4b3  sub     rsp, 0E0h
0x18007c4ba  mov     rax, cs:__security_cookie
0x18007c4c1  xor     rax, rsp
0x18007c4c4  mov     [rbp+57h+var_8], rax
0x18007c4c8  mov     rbx, r8
0x18007c4cb  movzx   r8d, dx
0x18007c4cf  mov     r10, rcx
0x18007c4d2  mov     [rbp+57h+var_A8], rbx
0x18007c4d6  mov     r9, [rcx+10h]
0x18007c4da  movzx   edx, word ptr [r9+r8*2+80h]
0x18007c4e3  mov     eax, 0FFFFh
0x18007c4e8  cmp     dx, ax
0x18007c4eb  jnz     short loc_18007C549
0x18007c4ed  lea     rdx, [rbp+57h+var_80]
0x18007c4f1  mov     rcx, [r9+480h]
0x18007c4f8  call    ?GetPropertyName@ShaderManager@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@23@@Z; Spectre::Engine::ShaderManager::GetPropertyName(Spectre::Engine::ShaderProperty)
0x18007c4fd  nop
0x18007c4fe  mov     r8, rax
0x18007c501  lea     rdx, aPropertyDoesNo; "Property does not exist: "
0x18007c508  lea     rcx, [rbp+57h+var_28]
0x18007c50c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18007c511  mov     rbx, rax
0x18007c514  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007c51b  lea     rcx, [rbp+57h+var_A0]
0x18007c51f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c524  mov     [rsp+0E0h+var_C0], 0
0x18007c529  mov     r9, rbx
0x18007c52c  mov     rdx, rax
0x18007c52f  lea     rcx, [rbp+57h+pExceptionObject]
0x18007c533  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007c538  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007c53f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c543  call    _CxxThrowException_0
0x18007c549  imul    rcx, rdx, 38h ; '8'
0x18007c54d  mov     rax, [r9+38h]
0x18007c551  cmp     dword ptr [rcx+rax+24h], 8
0x18007c556  jz      short loc_18007C59F
0x18007c558  lea     rdx, aShaderproperty_21; "ShaderPropertyBlock::SetTexture() -- Pr"...
0x18007c55f  lea     rcx, [rbp+57h+var_80]
0x18007c563  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c568  nop
0x18007c569  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007c570  lea     rcx, [rbp+57h+var_A0]
0x18007c574  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c579  mov     [rsp+0E0h+var_C0], 0
0x18007c57e  lea     r9, [rbp+57h+var_80]
0x18007c582  mov     rdx, rax
0x18007c585  lea     rcx, [rbp+57h+pExceptionObject]
0x18007c589  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007c58e  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007c595  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c599  call    _CxxThrowException_0
0x18007c59f  cmp     dword ptr [rcx+rax+30h], 2
0x18007c5a4  jnz     short loc_18007C5ED
0x18007c5a6  lea     rdx, aShaderproperty_16; "ShaderPropertyBlock::SetTextureSampler("...
0x18007c5ad  lea     rcx, [rbp+57h+var_A0]
0x18007c5b1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c5b6  nop
0x18007c5b7  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007c5be  lea     rcx, [rbp+57h+var_80]
0x18007c5c2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c5c7  mov     [rsp+0E0h+var_C0], 0
0x18007c5cc  lea     r9, [rbp+57h+var_A0]
0x18007c5d0  mov     rdx, rax
0x18007c5d3  lea     rcx, [rbp+57h+pExceptionObject]
0x18007c5d7  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007c5dc  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007c5e3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c5e7  call    _CxxThrowException_0
0x18007c5ed  mov     eax, [rcx+rax+28h]
0x18007c5f1  lea     rcx, [rax+rax*4]
0x18007c5f5  mov     rax, [r10+38h]
0x18007c5f9  lea     rcx, [rcx+2]
0x18007c5fd  lea     rcx, [rax+rcx*8]
0x18007c601  mov     rdx, rbx
0x18007c604  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x18007c609  nop
0x18007c60a  mov     rcx, [rbx+8]; this
0x18007c60e  test    rcx, rcx
0x18007c611  jz      short loc_18007C618
0x18007c613  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007c618  mov     rcx, [rbp+57h+var_8]
0x18007c61c  xor     rcx, rsp; StackCookie
0x18007c61f  call    __security_check_cookie
0x18007c624  mov     rbx, [rsp+0E0h+arg_18]
0x18007c62c  add     rsp, 0E0h
0x18007c633  pop     rbp
0x18007c634  retn
```
