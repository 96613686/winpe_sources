# Spectre::Engine::ShaderPropertyBlock::ReadPropertyValueElements(Spectre::Engine::ShaderProperty,Spectre::Engine::ShaderPropertyType,uint)

- ea: `0x18007be20`
- end: `0x18007bf8b`
- name: `?ReadPropertyValueElements@ShaderPropertyBlock@Engine@Spectre@@AEBAPEBTValueElement@ShaderPropertyLayout@23@W4ShaderProperty@23@W4ShaderPropertyType@23@I@Z`
- size: `363`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007bfcc`
- `0x18007c000`
- `0x18007c094`
- `0x18007c0cc`
- `0x18007c14c`
- `0x18007c1f8`
- `0x18007c63c`
- `0x18007c698`
- `0x180091320`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x18001c6e0`
- `0x180038ddc`
- `0x18004c8d8`
- `0x18007be20`

## string_xrefs

- `0x18007be89`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`
- `0x18007bede`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`
- `0x18007bf2c`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Spectre::Engine::ShaderPropertyBlock::ReadPropertyValueElements(
        __int64 a1,
        unsigned __int16 a2,
        int a3)
{
  __int64 v3; // r10
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 PropertyName; // rax
  int v8; // ebx
  int v9; // eax
  int v10; // r8d
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  int v14; // r8d
  int v15; // eax
  int v16; // r8d
  _BYTE v18[32]; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v21[32]; // [rsp+B0h] [rbp+27h] BYREF

  v3 = a2;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = *(unsigned __int16 *)(v5 + 2 * v3 + 128);
  if ( (_WORD)v6 == 0xFFFF )
  {
    PropertyName = Spectre::Engine::ShaderManager::GetPropertyName(*(_QWORD *)(v5 + 1152), v19, (unsigned __int16)v3);
    v8 = std::operator+<char>(v21, "Property not found in block: ", PropertyName);
    v9 = std::string::string(
           v18,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertyblock.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v9,
      v10,
      v8,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v11 = 56 * v6;
  v12 = *(_QWORD *)(v5 + 56);
  if ( *(_DWORD *)(v11 + v12 + 36) != a3 )
  {
    std::string::string(v19, "Property is not of type the correct type");
    v13 = std::string::string(
            v18,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertyblock.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v13,
      v14,
      (unsigned int)v19,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( *(_DWORD *)(v11 + v12 + 48) == 2 )
  {
    std::string::string(v18, "Property is imported so cannot be modified");
    v15 = std::string::string(
            v19,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shader"
            "propertyblock.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v15,
      v16,
      (unsigned int)v18,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  return *(_QWORD *)(a1 + 32) + 4LL * *(unsigned int *)(v11 + v12 + 40);
}

```

## disassembly

```asm
0x18007be20  mov     [rsp-8+arg_10], rbx
0x18007be25  push    rbp
0x18007be26  lea     rbp, [rsp-57h]
0x18007be2b  sub     rsp, 0E0h
0x18007be32  mov     rax, cs:__security_cookie
0x18007be39  xor     rax, rsp
0x18007be3c  mov     [rbp+57h+var_10], rax
0x18007be40  movzx   r10d, dx
0x18007be44  mov     rdx, rcx
0x18007be47  mov     r9, [rcx+10h]
0x18007be4b  movzx   ecx, word ptr [r9+r10*2+80h]
0x18007be54  mov     eax, 0FFFFh
0x18007be59  cmp     cx, ax
0x18007be5c  jnz     short loc_18007BEBE
0x18007be5e  movzx   r8d, r10w
0x18007be62  lea     rdx, [rbp+57h+var_88]
0x18007be66  mov     rcx, [r9+480h]
0x18007be6d  call    ?GetPropertyName@ShaderManager@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@23@@Z; Spectre::Engine::ShaderManager::GetPropertyName(Spectre::Engine::ShaderProperty)
0x18007be72  nop
0x18007be73  mov     r8, rax
0x18007be76  lea     rdx, aPropertyNotFou; "Property not found in block: "
0x18007be7d  lea     rcx, [rbp+57h+var_30]
0x18007be81  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18007be86  mov     rbx, rax
0x18007be89  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007be90  lea     rcx, [rbp+57h+var_A8]
0x18007be94  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007be99  mov     [rsp+0E0h+var_C0], 0
0x18007be9e  mov     r9, rbx
0x18007bea1  mov     rdx, rax
0x18007bea4  lea     rcx, [rbp+57h+pExceptionObject]
0x18007bea8  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007bead  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007beb4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007beb8  call    _CxxThrowException_0
0x18007bebe  imul    rcx, 38h ; '8'
0x18007bec2  mov     rax, [r9+38h]
0x18007bec6  cmp     [rcx+rax+24h], r8d
0x18007becb  jz      short loc_18007BF14
0x18007becd  lea     rdx, aPropertyIsNotO; "Property is not of type the correct typ"...
0x18007bed4  lea     rcx, [rbp+57h+var_88]
0x18007bed8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007bedd  nop
0x18007bede  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007bee5  lea     rcx, [rbp+57h+var_A8]
0x18007bee9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007beee  mov     [rsp+0E0h+var_C0], 0
0x18007bef3  lea     r9, [rbp+57h+var_88]
0x18007bef7  mov     rdx, rax
0x18007befa  lea     rcx, [rbp+57h+pExceptionObject]
0x18007befe  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007bf03  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007bf0a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007bf0e  call    _CxxThrowException_0
0x18007bf14  cmp     dword ptr [rcx+rax+30h], 2
0x18007bf19  jnz     short loc_18007BF62
0x18007bf1b  lea     rdx, aPropertyIsImpo; "Property is imported so cannot be modif"...
0x18007bf22  lea     rcx, [rbp+57h+var_A8]
0x18007bf26  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007bf2b  nop
0x18007bf2c  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007bf33  lea     rcx, [rbp+57h+var_88]
0x18007bf37  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007bf3c  mov     [rsp+0E0h+var_C0], 0
0x18007bf41  lea     r9, [rbp+57h+var_A8]
0x18007bf45  mov     rdx, rax
0x18007bf48  lea     rcx, [rbp+57h+pExceptionObject]
0x18007bf4c  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007bf51  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007bf58  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007bf5c  call    _CxxThrowException_0
0x18007bf62  mov     ecx, [rcx+rax+28h]
0x18007bf66  mov     rax, [rdx+20h]
0x18007bf6a  lea     rax, [rax+rcx*4]
0x18007bf6e  mov     rcx, [rbp+57h+var_10]
0x18007bf72  xor     rcx, rsp; StackCookie
0x18007bf75  call    __security_check_cookie
0x18007bf7a  mov     rbx, [rsp+0E0h+arg_10]
0x18007bf82  add     rsp, 0E0h
0x18007bf89  pop     rbp
0x18007bf8a  retn
```
