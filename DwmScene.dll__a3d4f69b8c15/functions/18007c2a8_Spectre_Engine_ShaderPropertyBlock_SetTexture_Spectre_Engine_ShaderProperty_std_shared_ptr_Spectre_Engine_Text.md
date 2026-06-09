# Spectre::Engine::ShaderPropertyBlock::SetTexture(Spectre::Engine::ShaderProperty,std::shared_ptr<Spectre::Engine::Texture>)

- ea: `0x18007c2a8`
- end: `0x18007c431`
- name: `?SetTexture@ShaderPropertyBlock@Engine@Spectre@@QEAAXW4ShaderProperty@23@V?$shared_ptr@VTexture@Engine@Spectre@@@std@@@Z`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007c238`
- `0x18008f2c0`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x18001c6e0`
- `0x180038ddc`
- `0x18004c8d8`
- `0x18007c2a8`

## string_xrefs

- `0x18007c314`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`
- `0x18007c369`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`
- `0x18007c3b7`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Spectre::Engine::ShaderPropertyBlock::SetTexture(__int64 a1, unsigned __int16 a2, __int64 a3)
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
    std::string::string(v19, "ShaderPropertyBlock::SetTexture() -- Cannot set the value of an imported property");
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
    *(_QWORD *)(a1 + 56) + 40LL * *(unsigned int *)(v12 + v13 + 40),
    a3);
  v18 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
}

```

## disassembly

```asm
0x18007c2a8  mov     [rsp-8+arg_18], rbx
0x18007c2ad  push    rbp
0x18007c2ae  lea     rbp, [rsp-57h]
0x18007c2b3  sub     rsp, 0E0h
0x18007c2ba  mov     rax, cs:__security_cookie
0x18007c2c1  xor     rax, rsp
0x18007c2c4  mov     [rbp+57h+var_8], rax
0x18007c2c8  mov     rbx, r8
0x18007c2cb  movzx   r8d, dx
0x18007c2cf  mov     r10, rcx
0x18007c2d2  mov     [rbp+57h+var_A8], rbx
0x18007c2d6  mov     r9, [rcx+10h]
0x18007c2da  movzx   edx, word ptr [r9+r8*2+80h]
0x18007c2e3  mov     eax, 0FFFFh
0x18007c2e8  cmp     dx, ax
0x18007c2eb  jnz     short loc_18007C349
0x18007c2ed  lea     rdx, [rbp+57h+var_80]
0x18007c2f1  mov     rcx, [r9+480h]
0x18007c2f8  call    ?GetPropertyName@ShaderManager@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@23@@Z; Spectre::Engine::ShaderManager::GetPropertyName(Spectre::Engine::ShaderProperty)
0x18007c2fd  nop
0x18007c2fe  mov     r8, rax
0x18007c301  lea     rdx, aPropertyDoesNo; "Property does not exist: "
0x18007c308  lea     rcx, [rbp+57h+var_28]
0x18007c30c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18007c311  mov     rbx, rax
0x18007c314  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007c31b  lea     rcx, [rbp+57h+var_A0]
0x18007c31f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c324  mov     [rsp+0E0h+var_C0], 0
0x18007c329  mov     r9, rbx
0x18007c32c  mov     rdx, rax
0x18007c32f  lea     rcx, [rbp+57h+pExceptionObject]
0x18007c333  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007c338  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007c33f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c343  call    _CxxThrowException_0
0x18007c349  imul    rcx, rdx, 38h ; '8'
0x18007c34d  mov     rax, [r9+38h]
0x18007c351  cmp     dword ptr [rcx+rax+24h], 8
0x18007c356  jz      short loc_18007C39F
0x18007c358  lea     rdx, aShaderproperty_21; "ShaderPropertyBlock::SetTexture() -- Pr"...
0x18007c35f  lea     rcx, [rbp+57h+var_80]
0x18007c363  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c368  nop
0x18007c369  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007c370  lea     rcx, [rbp+57h+var_A0]
0x18007c374  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c379  mov     [rsp+0E0h+var_C0], 0
0x18007c37e  lea     r9, [rbp+57h+var_80]
0x18007c382  mov     rdx, rax
0x18007c385  lea     rcx, [rbp+57h+pExceptionObject]
0x18007c389  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007c38e  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007c395  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c399  call    _CxxThrowException_0
0x18007c39f  cmp     dword ptr [rcx+rax+30h], 2
0x18007c3a4  jnz     short loc_18007C3ED
0x18007c3a6  lea     rdx, aShaderproperty_6; "ShaderPropertyBlock::SetTexture() -- Ca"...
0x18007c3ad  lea     rcx, [rbp+57h+var_A0]
0x18007c3b1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c3b6  nop
0x18007c3b7  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007c3be  lea     rcx, [rbp+57h+var_80]
0x18007c3c2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007c3c7  mov     [rsp+0E0h+var_C0], 0
0x18007c3cc  lea     r9, [rbp+57h+var_A0]
0x18007c3d0  mov     rdx, rax
0x18007c3d3  lea     rcx, [rbp+57h+pExceptionObject]
0x18007c3d7  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007c3dc  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007c3e3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c3e7  call    _CxxThrowException_0
0x18007c3ed  mov     eax, [rcx+rax+28h]
0x18007c3f1  lea     rcx, [rax+rax*4]
0x18007c3f5  mov     rax, [r10+38h]
0x18007c3f9  lea     rcx, [rax+rcx*8]
0x18007c3fd  mov     rdx, rbx
0x18007c400  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x18007c405  nop
0x18007c406  mov     rcx, [rbx+8]; this
0x18007c40a  test    rcx, rcx
0x18007c40d  jz      short loc_18007C414
0x18007c40f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007c414  mov     rcx, [rbp+57h+var_8]
0x18007c418  xor     rcx, rsp; StackCookie
0x18007c41b  call    __security_check_cookie
0x18007c420  mov     rbx, [rsp+0E0h+arg_18]
0x18007c428  add     rsp, 0E0h
0x18007c42f  pop     rbp
0x18007c430  retn
```
