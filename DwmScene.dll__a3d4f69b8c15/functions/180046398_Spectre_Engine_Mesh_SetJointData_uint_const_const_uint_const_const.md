# Spectre::Engine::Mesh::SetJointData(uint const * const,uint const * const)

- ea: `0x180046398`
- end: `0x18004646e`
- name: `?SetJointData@Mesh@Engine@Spectre@@QEAAXQEBI0@Z`
- size: `214`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, const unsigned int *const, const unsigned int *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004594c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x1800449d8`
- `0x180046398`
- `0x180046474`
- `0x1800681a8`

## string_xrefs

- `0x1800463ce`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x18004643d`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Spectre::Engine::Mesh::SetJointData(
        Spectre::Engine::Mesh *this,
        const unsigned int *a2,
        const unsigned int *a3)
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
      "Mesh::SetJointData() -- Modifying mesh buffers apart from MappedResource while it is mapped is not supported.");
    v3 = std::string::string(
           v7,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v3, v4, (unsigned int)v8, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  if ( !a2 || !a3 )
  {
    std::string::string(
      v7,
      "Mesh::SetJointData() -- jointWeightArray and jointIndexArray must be non-null and contain N elements, where N=Mesh"
      "::GetVertexCount()");
    v5 = std::string::string(
           v8,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v5, v6, v7);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  Spectre::Engine::Mesh::SetJointDataInternal(this, a2, a3, *((_DWORD *)this + 30));
}

```

## disassembly

```asm
0x180046398  push    rbp
0x18004639a  lea     rbp, [rsp-57h]
0x18004639f  sub     rsp, 0C0h
0x1800463a6  mov     rax, cs:__security_cookie
0x1800463ad  xor     rax, rsp
0x1800463b0  mov     [rbp+57h+var_10], rax
0x1800463b4  cmp     byte ptr [rcx+136h], 0
0x1800463bb  jz      short loc_180046404
0x1800463bd  lea     rdx, aMeshSetjointda_0; "Mesh::SetJointData() -- Modifying mesh "...
0x1800463c4  lea     rcx, [rbp+57h+var_68]
0x1800463c8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800463cd  nop
0x1800463ce  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800463d5  lea     rcx, [rbp+57h+var_88]
0x1800463d9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800463de  mov     [rsp+0C0h+var_A0], 0
0x1800463e3  lea     r9, [rbp+57h+var_68]
0x1800463e7  mov     rdx, rax
0x1800463ea  lea     rcx, [rbp+57h+pExceptionObject]
0x1800463ee  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800463f3  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800463fa  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800463fe  call    _CxxThrowException_0
0x180046404  test    rdx, rdx
0x180046407  jz      short loc_18004642C
0x180046409  test    r8, r8
0x18004640c  jz      short loc_18004642C
0x18004640e  mov     r9d, [rcx+78h]; unsigned int
0x180046412  call    ?SetJointDataInternal@Mesh@Engine@Spectre@@IEAAXQEBI0I@Z; Spectre::Engine::Mesh::SetJointDataInternal(uint const * const,uint const * const,uint)
0x180046417  mov     rcx, [rbp+57h+var_10]
0x18004641b  xor     rcx, rsp; StackCookie
0x18004641e  call    __security_check_cookie
0x180046423  add     rsp, 0C0h
0x18004642a  pop     rbp
0x18004642b  retn
0x18004642c  lea     rdx, aMeshSetjointda; "Mesh::SetJointData() -- jointWeightArra"...
0x180046433  lea     rcx, [rbp+57h+var_88]
0x180046437  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004643c  nop
0x18004643d  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180046444  lea     rcx, [rbp+57h+var_68]
0x180046448  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004644d  lea     r9, [rbp+57h+var_88]
0x180046451  mov     rdx, rax
0x180046454  lea     rcx, [rbp+57h+pExceptionObject]
0x180046458  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x18004645d  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x180046464  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180046468  call    _CxxThrowException_0
```
