# Spectre::Engine::Mesh::SetUV1(Spectre::Utils::Math::Vector2 const * const)

- ea: `0x180046cbc`
- end: `0x180046d8d`
- name: `?SetUV1@Mesh@Engine@Spectre@@QEAAXQEBUVector2@Math@Utils@3@@Z`
- size: `209`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, const struct Spectre::Utils::Math::Vector2 *const)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014af0`
- `0x18004594c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x1800449d8`
- `0x180046cbc`
- `0x180046d94`
- `0x1800681a8`

## string_xrefs

- `0x180046cf2`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x180046d3e`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
void __fastcall Spectre::Engine::Mesh::SetUV1(
        Spectre::Engine::Mesh *this,
        const struct Spectre::Utils::Math::Vector2 *a2)
{
  int v2; // eax
  int v3; // r8d
  __int64 v4; // rax
  __int64 v5; // r8
  _BYTE v6[32]; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v7[32]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp+Fh] BYREF

  if ( *((_BYTE *)this + 310) )
  {
    std::string::string(
      v7,
      "Mesh::SetUV1() -- Modifying mesh buffers apart from MappedResource while it is mapped is not supported.");
    v2 = std::string::string(
           v6,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v2, v3, (unsigned int)v7, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  if ( !a2 )
  {
    std::string::string(
      v6,
      "Mesh::SetUV1() -- uvArray must be non-null and contain N elements, where N=Mesh::GetVertexCount()");
    v4 = std::string::string(
           v7,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v4, v5, v6);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  Spectre::Engine::Mesh::SetUV1Internal(this, a2, *((_DWORD *)this + 30));
}

```

## disassembly

```asm
0x180046cbc  push    rbp
0x180046cbe  lea     rbp, [rsp-57h]
0x180046cc3  sub     rsp, 0C0h
0x180046cca  mov     rax, cs:__security_cookie
0x180046cd1  xor     rax, rsp
0x180046cd4  mov     [rbp+57h+var_10], rax
0x180046cd8  cmp     byte ptr [rcx+136h], 0
0x180046cdf  jz      short loc_180046D28
0x180046ce1  lea     rdx, aMeshSetuv1Modi; "Mesh::SetUV1() -- Modifying mesh buffer"...
0x180046ce8  lea     rcx, [rbp+57h+var_68]
0x180046cec  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046cf1  nop
0x180046cf2  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046cf9  lea     rcx, [rbp+57h+var_88]
0x180046cfd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046d02  mov     [rsp+0C0h+var_A0], 0
0x180046d07  lea     r9, [rbp+57h+var_68]
0x180046d0b  mov     rdx, rax
0x180046d0e  lea     rcx, [rbp+57h+pExceptionObject]
0x180046d12  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180046d17  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180046d1e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046d22  call    _CxxThrowException_0
0x180046d28  test    rdx, rdx
0x180046d2b  jnz     short loc_180046D6F
0x180046d2d  lea     rdx, aMeshSetuv1Uvar; "Mesh::SetUV1() -- uvArray must be non-n"...
0x180046d34  lea     rcx, [rbp+57h+var_88]
0x180046d38  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046d3d  nop
0x180046d3e  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046d45  lea     rcx, [rbp+57h+var_68]
0x180046d49  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046d4e  lea     r9, [rbp+57h+var_88]
0x180046d52  mov     rdx, rax
0x180046d55  lea     rcx, [rbp+57h+pExceptionObject]
0x180046d59  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180046d5e  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x180046d65  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046d69  call    _CxxThrowException_0
0x180046d6f  mov     r8d, [rcx+78h]; unsigned int
0x180046d73  call    ?SetUV1Internal@Mesh@Engine@Spectre@@IEAAXQEBUVector2@Math@Utils@3@I@Z; Spectre::Engine::Mesh::SetUV1Internal(Spectre::Utils::Math::Vector2 const * const,uint)
0x180046d78  mov     rcx, [rbp+57h+var_10]
0x180046d7c  xor     rcx, rsp; StackCookie
0x180046d7f  call    __security_check_cookie
0x180046d84  add     rsp, 0C0h
0x180046d8b  pop     rbp
0x180046d8c  retn
```
