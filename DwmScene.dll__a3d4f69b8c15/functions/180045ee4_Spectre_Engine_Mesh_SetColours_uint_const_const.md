# Spectre::Engine::Mesh::SetColours(uint const * const)

- ea: `0x180045ee4`
- end: `0x180045fb5`
- name: `?SetColours@Mesh@Engine@Spectre@@QEAAXQEBI@Z`
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
- `0x180045ee4`
- `0x180045fbc`
- `0x1800681a8`

## string_xrefs

- `0x180045f1a`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x180045f66`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Spectre::Engine::Mesh::SetColours(Spectre::Engine::Mesh *this, const unsigned int *a2)
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
      "Mesh::SetColours() -- Modifying mesh buffers apart from MappedResource while it is mapped is not supported.");
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
      "Mesh::SetColours() -- colorArray must be non-null and contain N elements, where N=Mesh::GetVertexCount()");
    v4 = std::string::string(
           v7,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v4, v5, v6);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  Spectre::Engine::Mesh::SetColoursInternal(this, a2, *((_DWORD *)this + 30));
}

```

## disassembly

```asm
0x180045ee4  push    rbp
0x180045ee6  lea     rbp, [rsp-57h]
0x180045eeb  sub     rsp, 0C0h
0x180045ef2  mov     rax, cs:__security_cookie
0x180045ef9  xor     rax, rsp
0x180045efc  mov     [rbp+57h+var_10], rax
0x180045f00  cmp     byte ptr [rcx+136h], 0
0x180045f07  jz      short loc_180045F50
0x180045f09  lea     rdx, aMeshSetcolours_0; "Mesh::SetColours() -- Modifying mesh bu"...
0x180045f10  lea     rcx, [rbp+57h+var_68]
0x180045f14  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045f19  nop
0x180045f1a  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180045f21  lea     rcx, [rbp+57h+var_88]
0x180045f25  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045f2a  mov     [rsp+0C0h+var_A0], 0
0x180045f2f  lea     r9, [rbp+57h+var_68]
0x180045f33  mov     rdx, rax
0x180045f36  lea     rcx, [rbp+57h+pExceptionObject]
0x180045f3a  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180045f3f  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180045f46  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045f4a  call    _CxxThrowException_0
0x180045f50  test    rdx, rdx
0x180045f53  jnz     short loc_180045F97
0x180045f55  lea     rdx, aMeshSetcolours; "Mesh::SetColours() -- colorArray must b"...
0x180045f5c  lea     rcx, [rbp+57h+var_88]
0x180045f60  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045f65  nop
0x180045f66  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180045f6d  lea     rcx, [rbp+57h+var_68]
0x180045f71  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045f76  lea     r9, [rbp+57h+var_88]
0x180045f7a  mov     rdx, rax
0x180045f7d  lea     rcx, [rbp+57h+pExceptionObject]
0x180045f81  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180045f86  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x180045f8d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045f91  call    _CxxThrowException_0
0x180045f97  mov     r8d, [rcx+78h]; unsigned int
0x180045f9b  call    ?SetColoursInternal@Mesh@Engine@Spectre@@IEAAXQEBII@Z; Spectre::Engine::Mesh::SetColoursInternal(uint const * const,uint)
0x180045fa0  mov     rcx, [rbp+57h+var_10]
0x180045fa4  xor     rcx, rsp; StackCookie
0x180045fa7  call    __security_check_cookie
0x180045fac  add     rsp, 0C0h
0x180045fb3  pop     rbp
0x180045fb4  retn
```
