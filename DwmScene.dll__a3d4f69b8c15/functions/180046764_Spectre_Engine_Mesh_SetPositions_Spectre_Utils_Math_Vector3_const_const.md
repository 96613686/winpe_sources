# Spectre::Engine::Mesh::SetPositions(Spectre::Utils::Math::Vector3 const * const)

- ea: `0x180046764`
- end: `0x180046835`
- name: `?SetPositions@Mesh@Engine@Spectre@@QEAAXQEBUVector3@Math@Utils@3@@Z`
- size: `209`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, const struct Spectre::Utils::Math::Vector3 *const)`
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
- `0x180046764`
- `0x18004683c`
- `0x1800681a8`

## string_xrefs

- `0x18004679a`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x1800467e6`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
void __fastcall Spectre::Engine::Mesh::SetPositions(
        Spectre::Engine::Mesh *this,
        const struct Spectre::Utils::Math::Vector3 *a2)
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
      "Mesh::SetPositions() -- Modifying mesh buffers apart from MappedResource while it is mapped is not supported.");
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
      "Mesh::SetPositions() -- positionArray must be non-null and contain N elements, where N=Mesh::GetVertexCount()");
    v4 = std::string::string(
           v7,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v4, v5, v6);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  Spectre::Engine::Mesh::SetPositionsInternal(this, a2, *((_DWORD *)this + 30));
}

```

## disassembly

```asm
0x180046764  push    rbp
0x180046766  lea     rbp, [rsp-57h]
0x18004676b  sub     rsp, 0C0h
0x180046772  mov     rax, cs:__security_cookie
0x180046779  xor     rax, rsp
0x18004677c  mov     [rbp+57h+var_10], rax
0x180046780  cmp     byte ptr [rcx+136h], 0
0x180046787  jz      short loc_1800467D0
0x180046789  lea     rdx, aMeshSetpositio_0; "Mesh::SetPositions() -- Modifying mesh "...
0x180046790  lea     rcx, [rbp+57h+var_68]
0x180046794  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046799  nop
0x18004679a  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800467a1  lea     rcx, [rbp+57h+var_88]
0x1800467a5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800467aa  mov     [rsp+0C0h+var_A0], 0
0x1800467af  lea     r9, [rbp+57h+var_68]
0x1800467b3  mov     rdx, rax
0x1800467b6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800467ba  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800467bf  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800467c6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800467ca  call    _CxxThrowException_0
0x1800467d0  test    rdx, rdx
0x1800467d3  jnz     short loc_180046817
0x1800467d5  lea     rdx, aMeshSetpositio; "Mesh::SetPositions() -- positionArray m"...
0x1800467dc  lea     rcx, [rbp+57h+var_88]
0x1800467e0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800467e5  nop
0x1800467e6  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800467ed  lea     rcx, [rbp+57h+var_68]
0x1800467f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800467f6  lea     r9, [rbp+57h+var_88]
0x1800467fa  mov     rdx, rax
0x1800467fd  lea     rcx, [rbp+57h+pExceptionObject]
0x180046801  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180046806  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x18004680d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046811  call    _CxxThrowException_0
0x180046817  mov     r8d, [rcx+78h]; unsigned int
0x18004681b  call    ?SetPositionsInternal@Mesh@Engine@Spectre@@IEAAXQEBUVector3@Math@Utils@3@I@Z; Spectre::Engine::Mesh::SetPositionsInternal(Spectre::Utils::Math::Vector3 const * const,uint)
0x180046820  mov     rcx, [rbp+57h+var_10]
0x180046824  xor     rcx, rsp; StackCookie
0x180046827  call    __security_check_cookie
0x18004682c  add     rsp, 0C0h
0x180046833  pop     rbp
0x180046834  retn
```
