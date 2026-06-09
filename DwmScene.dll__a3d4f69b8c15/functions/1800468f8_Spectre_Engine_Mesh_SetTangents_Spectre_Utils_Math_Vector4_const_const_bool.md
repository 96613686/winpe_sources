# Spectre::Engine::Mesh::SetTangents(Spectre::Utils::Math::Vector4 const * const,bool)

- ea: `0x1800468f8`
- end: `0x1800469cc`
- name: `?SetTangents@Mesh@Engine@Spectre@@QEAAXQEBUVector4@Math@Utils@3@_N@Z`
- size: `212`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, const struct Spectre::Utils::Math::Vector4 *const, bool)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014af0`
- `0x18004594c`
- `0x180046f00`
- `0x180046f70`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x1800449d8`
- `0x1800468f8`
- `0x1800469d4`
- `0x1800681a8`

## string_xrefs

- `0x18004692e`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x18004697a`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
void __fastcall Spectre::Engine::Mesh::SetTangents(
        Spectre::Engine::Mesh *this,
        const struct Spectre::Utils::Math::Vector4 *a2,
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
      "Mesh::SetTangents() -- Modifying mesh buffers apart from MappedResource while it is mapped is not supported.");
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
      "Mesh::SetTangents() -- tangentArray must be non-null and contain N elements, where N=Mesh::GetVertexCount()");
    v5 = std::string::string(
           v8,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v5, v6, v7);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  Spectre::Engine::Mesh::SetTangentsInternal(this, a2, *((_DWORD *)this + 30), a3);
}

```

## disassembly

```asm
0x1800468f8  push    rbp
0x1800468fa  lea     rbp, [rsp-57h]
0x1800468ff  sub     rsp, 0C0h
0x180046906  mov     rax, cs:__security_cookie
0x18004690d  xor     rax, rsp
0x180046910  mov     [rbp+57h+var_10], rax
0x180046914  cmp     byte ptr [rcx+136h], 0
0x18004691b  jz      short loc_180046964
0x18004691d  lea     rdx, aMeshSettangent_0; "Mesh::SetTangents() -- Modifying mesh b"...
0x180046924  lea     rcx, [rbp+57h+var_68]
0x180046928  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004692d  nop
0x18004692e  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046935  lea     rcx, [rbp+57h+var_88]
0x180046939  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004693e  mov     [rsp+0C0h+var_A0], 0
0x180046943  lea     r9, [rbp+57h+var_68]
0x180046947  mov     rdx, rax
0x18004694a  lea     rcx, [rbp+57h+pExceptionObject]
0x18004694e  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180046953  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x18004695a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004695e  call    _CxxThrowException_0
0x180046964  test    rdx, rdx
0x180046967  jnz     short loc_1800469AB
0x180046969  lea     rdx, aMeshSettangent; "Mesh::SetTangents() -- tangentArray mus"...
0x180046970  lea     rcx, [rbp+57h+var_88]
0x180046974  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046979  nop
0x18004697a  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046981  lea     rcx, [rbp+57h+var_68]
0x180046985  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004698a  lea     r9, [rbp+57h+var_88]
0x18004698e  mov     rdx, rax
0x180046991  lea     rcx, [rbp+57h+pExceptionObject]
0x180046995  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x18004699a  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x1800469a1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800469a5  call    _CxxThrowException_0
0x1800469ab  mov     r9b, r8b; bool
0x1800469ae  mov     r8d, [rcx+78h]; unsigned int
0x1800469b2  call    ?SetTangentsInternal@Mesh@Engine@Spectre@@IEAAXQEBUVector4@Math@Utils@3@I_N@Z; Spectre::Engine::Mesh::SetTangentsInternal(Spectre::Utils::Math::Vector4 const * const,uint,bool)
0x1800469b7  mov     rcx, [rbp+57h+var_10]
0x1800469bb  xor     rcx, rsp; StackCookie
0x1800469be  call    __security_check_cookie
0x1800469c3  add     rsp, 0C0h
0x1800469ca  pop     rbp
0x1800469cb  retn
```
