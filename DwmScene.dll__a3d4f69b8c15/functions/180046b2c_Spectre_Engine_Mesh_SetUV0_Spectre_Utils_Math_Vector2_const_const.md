# Spectre::Engine::Mesh::SetUV0(Spectre::Utils::Math::Vector2 const * const)

- ea: `0x180046b2c`
- end: `0x180046bfd`
- name: `?SetUV0@Mesh@Engine@Spectre@@QEAAXQEBUVector2@Math@Utils@3@@Z`
- size: `209`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, const struct Spectre::Utils::Math::Vector2 *const)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014af0`
- `0x18004594c`
- `0x180082ab4`
- `0x180082c74`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x1800449d8`
- `0x180046b2c`
- `0x180046c04`
- `0x1800681a8`

## string_xrefs

- `0x180046b62`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x180046bae`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
void __fastcall Spectre::Engine::Mesh::SetUV0(
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
      "Mesh::SetUV0() -- Modifying mesh buffers apart from MappedResource while it is mapped is not supported.");
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
      "Mesh::SetUV0() -- uvArray must be non-null and contain N elements, where N=Mesh::GetVertexCount()");
    v4 = std::string::string(
           v7,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v4, v5, v6);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  Spectre::Engine::Mesh::SetUV0Internal(this, a2, *((_DWORD *)this + 30));
}

```

## disassembly

```asm
0x180046b2c  push    rbp
0x180046b2e  lea     rbp, [rsp-57h]
0x180046b33  sub     rsp, 0C0h
0x180046b3a  mov     rax, cs:__security_cookie
0x180046b41  xor     rax, rsp
0x180046b44  mov     [rbp+57h+var_10], rax
0x180046b48  cmp     byte ptr [rcx+136h], 0
0x180046b4f  jz      short loc_180046B98
0x180046b51  lea     rdx, aMeshSetuv0Modi; "Mesh::SetUV0() -- Modifying mesh buffer"...
0x180046b58  lea     rcx, [rbp+57h+var_68]
0x180046b5c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046b61  nop
0x180046b62  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046b69  lea     rcx, [rbp+57h+var_88]
0x180046b6d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046b72  mov     [rsp+0C0h+var_A0], 0
0x180046b77  lea     r9, [rbp+57h+var_68]
0x180046b7b  mov     rdx, rax
0x180046b7e  lea     rcx, [rbp+57h+pExceptionObject]
0x180046b82  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180046b87  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180046b8e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046b92  call    _CxxThrowException_0
0x180046b98  test    rdx, rdx
0x180046b9b  jnz     short loc_180046BDF
0x180046b9d  lea     rdx, aMeshSetuv0Uvar; "Mesh::SetUV0() -- uvArray must be non-n"...
0x180046ba4  lea     rcx, [rbp+57h+var_88]
0x180046ba8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046bad  nop
0x180046bae  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046bb5  lea     rcx, [rbp+57h+var_68]
0x180046bb9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046bbe  lea     r9, [rbp+57h+var_88]
0x180046bc2  mov     rdx, rax
0x180046bc5  lea     rcx, [rbp+57h+pExceptionObject]
0x180046bc9  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180046bce  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x180046bd5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046bd9  call    _CxxThrowException_0
0x180046bdf  mov     r8d, [rcx+78h]; unsigned int
0x180046be3  call    ?SetUV0Internal@Mesh@Engine@Spectre@@IEAAXQEBUVector2@Math@Utils@3@I@Z; Spectre::Engine::Mesh::SetUV0Internal(Spectre::Utils::Math::Vector2 const * const,uint)
0x180046be8  mov     rcx, [rbp+57h+var_10]
0x180046bec  xor     rcx, rsp; StackCookie
0x180046bef  call    __security_check_cookie
0x180046bf4  add     rsp, 0C0h
0x180046bfb  pop     rbp
0x180046bfc  retn
```
