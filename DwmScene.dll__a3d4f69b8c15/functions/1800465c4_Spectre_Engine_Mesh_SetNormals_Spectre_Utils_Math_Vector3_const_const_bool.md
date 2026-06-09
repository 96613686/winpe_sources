# Spectre::Engine::Mesh::SetNormals(Spectre::Utils::Math::Vector3 const * const,bool)

- ea: `0x1800465c4`
- end: `0x180046698`
- name: `?SetNormals@Mesh@Engine@Spectre@@QEAAXQEBUVector3@Math@Utils@3@_N@Z`
- size: `212`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, const struct Spectre::Utils::Math::Vector3 *const, bool)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014af0`
- `0x18004594c`
- `0x180046f00`
- `0x180046f50`
- `0x180082ab4`
- `0x180082c74`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x1800449d8`
- `0x1800465c4`
- `0x1800466a0`
- `0x1800681a8`

## string_xrefs

- `0x1800465fa`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x180046646`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
void __fastcall Spectre::Engine::Mesh::SetNormals(
        Spectre::Engine::Mesh *this,
        const struct Spectre::Utils::Math::Vector3 *a2,
        bool a3)
{
  int v3; // eax
  int v4; // r8d
  __int64 v5; // rax
  __int64 v6; // r8
  _BYTE v7[32]; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp+Fh] BYREF

  if ( *((_BYTE *)this + 310) )
  {
    std::string::string(
      v8,
      "Mesh::SetNormals() -- Modifying mesh buffers apart from MappedResource while it is mapped is not supported.");
    v3 = std::string::string(
           v7,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v3, v4, (unsigned int)v8, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  if ( !a2 )
  {
    std::string::string(
      v7,
      "Mesh::SetNormals() -- normalArray must be non-null and contain N elements, where N=Mesh::GetVertexCount()");
    v5 = std::string::string(
           v8,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v5, v6, v7);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  Spectre::Engine::Mesh::SetNormalsInternal(this, a2, *((_DWORD *)this + 30), a3);
}

```

## disassembly

```asm
0x1800465c4  push    rbp
0x1800465c6  lea     rbp, [rsp-57h]
0x1800465cb  sub     rsp, 0C0h
0x1800465d2  mov     rax, cs:__security_cookie
0x1800465d9  xor     rax, rsp
0x1800465dc  mov     [rbp+57h+var_10], rax
0x1800465e0  cmp     byte ptr [rcx+136h], 0
0x1800465e7  jz      short loc_180046630
0x1800465e9  lea     rdx, aMeshSetnormals_0; "Mesh::SetNormals() -- Modifying mesh bu"...
0x1800465f0  lea     rcx, [rbp+57h+var_68]
0x1800465f4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800465f9  nop
0x1800465fa  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046601  lea     rcx, [rbp+57h+var_88]
0x180046605  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004660a  mov     [rsp+0C0h+var_A0], 0
0x18004660f  lea     r9, [rbp+57h+var_68]
0x180046613  mov     rdx, rax
0x180046616  lea     rcx, [rbp+57h+pExceptionObject]
0x18004661a  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x18004661f  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180046626  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004662a  call    _CxxThrowException_0
0x180046630  test    rdx, rdx
0x180046633  jnz     short loc_180046677
0x180046635  lea     rdx, aMeshSetnormals; "Mesh::SetNormals() -- normalArray must "...
0x18004663c  lea     rcx, [rbp+57h+var_88]
0x180046640  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046645  nop
0x180046646  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004664d  lea     rcx, [rbp+57h+var_68]
0x180046651  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046656  lea     r9, [rbp+57h+var_88]
0x18004665a  mov     rdx, rax
0x18004665d  lea     rcx, [rbp+57h+pExceptionObject]
0x180046661  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180046666  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x18004666d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046671  call    _CxxThrowException_0
0x180046677  mov     r9b, r8b; bool
0x18004667a  mov     r8d, [rcx+78h]; unsigned int
0x18004667e  call    ?SetNormalsInternal@Mesh@Engine@Spectre@@IEAAXQEBUVector3@Math@Utils@3@I_N@Z; Spectre::Engine::Mesh::SetNormalsInternal(Spectre::Utils::Math::Vector3 const * const,uint,bool)
0x180046683  mov     rcx, [rbp+57h+var_10]
0x180046687  xor     rcx, rsp; StackCookie
0x18004668a  call    __security_check_cookie
0x18004668f  add     rsp, 0C0h
0x180046696  pop     rbp
0x180046697  retn
```
