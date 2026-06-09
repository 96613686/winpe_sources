# Spectre::Engine::Mesh::SetIndices(ushort const * const)

- ea: `0x18004608c`
- end: `0x18004615d`
- name: `?SetIndices@Mesh@Engine@Spectre@@QEAAXQEBG@Z`
- size: `209`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, const unsigned __int16 *const)`
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
- `0x18004608c`
- `0x18004623c`
- `0x1800681a8`

## string_xrefs

- `0x1800460c2`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x18004610e`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
void __fastcall Spectre::Engine::Mesh::SetIndices(Spectre::Engine::Mesh *this, const unsigned __int16 *a2)
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
0x18004608c  push    rbp
0x18004608e  lea     rbp, [rsp-57h]
0x180046093  sub     rsp, 0C0h
0x18004609a  mov     rax, cs:__security_cookie
0x1800460a1  xor     rax, rsp
0x1800460a4  mov     [rbp+57h+var_10], rax
0x1800460a8  cmp     byte ptr [rcx+136h], 0
0x1800460af  jz      short loc_1800460F8
0x1800460b1  lea     rdx, aMeshSetindices_0; "Mesh::SetIndices() -- Modifying mesh bu"...
0x1800460b8  lea     rcx, [rbp+57h+var_68]
0x1800460bc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800460c1  nop
0x1800460c2  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800460c9  lea     rcx, [rbp+57h+var_88]
0x1800460cd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800460d2  mov     [rsp+0C0h+var_A0], 0
0x1800460d7  lea     r9, [rbp+57h+var_68]
0x1800460db  mov     rdx, rax
0x1800460de  lea     rcx, [rbp+57h+pExceptionObject]
0x1800460e2  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800460e7  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800460ee  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800460f2  call    _CxxThrowException_0
0x1800460f8  test    rdx, rdx
0x1800460fb  jnz     short loc_18004613F
0x1800460fd  lea     rdx, aMeshSetindices; "Mesh::SetIndices() -- indexArray must b"...
0x180046104  lea     rcx, [rbp+57h+var_88]
0x180046108  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004610d  nop
0x18004610e  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046115  lea     rcx, [rbp+57h+var_68]
0x180046119  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004611e  lea     r9, [rbp+57h+var_88]
0x180046122  mov     rdx, rax
0x180046125  lea     rcx, [rbp+57h+pExceptionObject]
0x180046129  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x18004612e  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x180046135  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046139  call    _CxxThrowException_0
0x18004613f  mov     r8d, [rcx+70h]; unsigned int
0x180046143  call    ?SetIndicesInternal@Mesh@Engine@Spectre@@IEAAXQEBGI@Z; Spectre::Engine::Mesh::SetIndicesInternal(ushort const * const,uint)
0x180046148  mov     rcx, [rbp+57h+var_10]
0x18004614c  xor     rcx, rsp; StackCookie
0x18004614f  call    __security_check_cookie
0x180046154  add     rsp, 0C0h
0x18004615b  pop     rbp
0x18004615c  retn
```
