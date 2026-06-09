# Spectre::Engine::Mesh::SetIndices(uint const * const)

- ea: `0x180046164`
- end: `0x180046235`
- name: `?SetIndices@Mesh@Engine@Spectre@@QEAAXQEBI@Z`
- size: `209`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, const unsigned int *const)`
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
- `0x180046164`
- `0x1800462ec`
- `0x1800681a8`

## string_xrefs

- `0x18004619a`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x1800461e6`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
void __fastcall Spectre::Engine::Mesh::SetIndices(Spectre::Engine::Mesh *this, const unsigned int *a2)
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
      "Mesh::SetIndices() -- Modifying mesh buffers apart from MappedResource while it is mapped is not supported.");
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
      "Mesh::SetIndices() -- indexArray must be non-null and contain N elements, where N=Mesh::GetIndexCount()");
    v4 = std::string::string(
           v7,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v4, v5, v6);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  Spectre::Engine::Mesh::SetIndicesInternal(this, a2, *((_DWORD *)this + 28));
}

```

## disassembly

```asm
0x180046164  push    rbp
0x180046166  lea     rbp, [rsp-57h]
0x18004616b  sub     rsp, 0C0h
0x180046172  mov     rax, cs:__security_cookie
0x180046179  xor     rax, rsp
0x18004617c  mov     [rbp+57h+var_10], rax
0x180046180  cmp     byte ptr [rcx+136h], 0
0x180046187  jz      short loc_1800461D0
0x180046189  lea     rdx, aMeshSetindices_0; "Mesh::SetIndices() -- Modifying mesh bu"...
0x180046190  lea     rcx, [rbp+57h+var_68]
0x180046194  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180046199  nop
0x18004619a  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800461a1  lea     rcx, [rbp+57h+var_88]
0x1800461a5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800461aa  mov     [rsp+0C0h+var_A0], 0
0x1800461af  lea     r9, [rbp+57h+var_68]
0x1800461b3  mov     rdx, rax
0x1800461b6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800461ba  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800461bf  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800461c6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800461ca  call    _CxxThrowException_0
0x1800461d0  test    rdx, rdx
0x1800461d3  jnz     short loc_180046217
0x1800461d5  lea     rdx, aMeshSetindices; "Mesh::SetIndices() -- indexArray must b"...
0x1800461dc  lea     rcx, [rbp+57h+var_88]
0x1800461e0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800461e5  nop
0x1800461e6  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800461ed  lea     rcx, [rbp+57h+var_68]
0x1800461f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800461f6  lea     r9, [rbp+57h+var_88]
0x1800461fa  mov     rdx, rax
0x1800461fd  lea     rcx, [rbp+57h+pExceptionObject]
0x180046201  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180046206  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x18004620d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046211  call    _CxxThrowException_0
0x180046217  mov     r8d, [rcx+70h]; unsigned int
0x18004621b  call    ?SetIndicesInternal@Mesh@Engine@Spectre@@IEAAXQEBII@Z; Spectre::Engine::Mesh::SetIndicesInternal(uint const * const,uint)
0x180046220  mov     rcx, [rbp+57h+var_10]
0x180046224  xor     rcx, rsp; StackCookie
0x180046227  call    __security_check_cookie
0x18004622c  add     rsp, 0C0h
0x180046233  pop     rbp
0x180046234  retn
```
