# Spectre::Engine::Mesh::ReserveDynamic(uint,uint,Spectre::Engine::MeshTopology,uint)

- ea: `0x180045ca0`
- end: `0x180045edc`
- name: `?ReserveDynamic@Mesh@Engine@Spectre@@QEAAXIIW4MeshTopology@23@I@Z`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800458a8`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x1800286b4`
- `0x1800449d8`
- `0x180045ca0`
- `0x180045fbc`
- `0x18004623c`
- `0x1800462ec`
- `0x180046474`
- `0x1800466a0`
- `0x18004683c`
- `0x1800469d4`
- `0x180046c04`
- `0x180046d94`

## string_xrefs

- `0x180045cf9`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x180045d44`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x180045eab`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x180045ce8`: `Mesh::ReserveDynamic() -- this mesh instance is already dynamic -- ReserveDynamic() must be called only once`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Spectre::Engine::Mesh::ReserveDynamic(unsigned int *a1, int a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  unsigned int v11; // r10d
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // r8
  _BYTE v15[32]; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-19h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp+7h] BYREF

  if ( !(_DWORD)a3 || !a2 )
  {
    std::string::string(v15, "Mesh::ReserveDynamic() -- vertex capacity and index capacity must not be zero");
    v13 = std::string::string(
            v16,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v13, v14, v15);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  if ( a1[76] == 2 )
  {
    std::string::string(
      v16,
      "Mesh::ReserveDynamic() -- this mesh instance is already dynamic -- ReserveDynamic() must be called only once");
    v6 = std::string::string(
           v15,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v6, v7, v16);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  if ( (a5 & 0x100) == 0 )
  {
    std::string::string(v15, "Mesh::ReserveDynamic() -- dynamic mesh vertex format must include position");
    v8 = std::string::string(
           v16,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(pExceptionObject, v8, v9, v15);
    throw (Spectre::Engine::EngineInvalidPointerException *)pExceptionObject;
  }
  a1[76] = 2;
  LOBYTE(a3) = 1;
  Spectre::Engine::RendererResource::SetOption(a1, 4, a3);
  *(_DWORD *)(v10 + 292) = a5;
  *(_DWORD *)(v10 + 296) = a5;
  *(_DWORD *)(v10 + 124) = v11;
  *(_DWORD *)(v10 + 120) = v11;
  *(_DWORD *)(v10 + 116) = v12;
  *(_DWORD *)(v10 + 112) = v12;
  *(_WORD *)(v10 + 308) = 0;
  Spectre::Engine::Mesh::SetPositionsInternal((Spectre::Engine::Mesh *)v10, 0, v11);
  if ( (a5 & 0x80u) != 0 )
    Spectre::Engine::Mesh::SetColoursInternal((Spectre::Engine::Mesh *)a1, 0, a1[31]);
  if ( (a5 & 1) != 0 )
    Spectre::Engine::Mesh::SetUV0Internal((Spectre::Engine::Mesh *)a1, 0, a1[31]);
  if ( (a5 & 2) != 0 )
    Spectre::Engine::Mesh::SetUV1Internal((Spectre::Engine::Mesh *)a1, 0, a1[31]);
  if ( (a5 & 0x10000000) != 0 )
  {
    a1[72] = 1;
    Spectre::Engine::Mesh::SetIndicesInternal((Spectre::Engine::Mesh *)a1, 0, a1[29]);
  }
  else if ( (a5 & 0x40) != 0 )
  {
    a1[72] = 0;
    Spectre::Engine::Mesh::SetIndicesInternal((Spectre::Engine::Mesh *)a1, 0, a1[29]);
  }
  if ( (a5 & 0x10) != 0 )
    Spectre::Engine::Mesh::SetNormalsInternal((Spectre::Engine::Mesh *)a1, 0, a1[31], 0);
  if ( (a5 & 0x20) != 0 )
    Spectre::Engine::Mesh::SetTangentsInternal((Spectre::Engine::Mesh *)a1, 0, a1[31], 0);
  if ( (a5 & 0x400) != 0 )
    Spectre::Engine::Mesh::SetJointDataInternal((Spectre::Engine::Mesh *)a1, 0, 0, a1[31]);
}

```

## disassembly

```asm
0x180045ca0  mov     [rsp-8+arg_8], rbx
0x180045ca5  mov     [rsp-8+arg_10], rdi
0x180045caa  push    rbp
0x180045cab  lea     rbp, [rsp-4Fh]
0x180045cb0  sub     rsp, 0C0h
0x180045cb7  mov     rax, cs:__security_cookie
0x180045cbe  xor     rax, rsp
0x180045cc1  mov     [rbp+4Fh+var_10], rax
0x180045cc5  mov     r10d, r8d
0x180045cc8  mov     r9d, edx
0x180045ccb  mov     rbx, rcx
0x180045cce  test    r8d, r8d
0x180045cd1  jz      loc_180045E9A
0x180045cd7  test    edx, edx
0x180045cd9  jz      loc_180045E9A
0x180045cdf  cmp     dword ptr [rcx+130h], 2
0x180045ce6  jnz     short loc_180045D2A
0x180045ce8  lea     rdx, aMeshReservedyn; "Mesh::ReserveDynamic() -- this mesh ins"...
0x180045cef  lea     rcx, [rbp+4Fh+var_68]
0x180045cf3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045cf8  nop
0x180045cf9  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180045d00  lea     rcx, [rbp+4Fh+var_88]
0x180045d04  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045d09  lea     r9, [rbp+4Fh+var_68]
0x180045d0d  mov     rdx, rax
0x180045d10  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180045d14  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180045d19  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x180045d20  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180045d24  call    _CxxThrowException_0
0x180045d2a  mov     edi, [rbp+4Fh+arg_20]
0x180045d2d  bt      edi, 8
0x180045d31  jb      short loc_180045D75
0x180045d33  lea     rdx, aMeshReservedyn_1; "Mesh::ReserveDynamic() -- dynamic mesh "...
0x180045d3a  lea     rcx, [rbp+4Fh+var_88]
0x180045d3e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045d43  nop
0x180045d44  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180045d4b  lea     rcx, [rbp+4Fh+var_68]
0x180045d4f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045d54  lea     r9, [rbp+4Fh+var_88]
0x180045d58  mov     rdx, rax
0x180045d5b  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180045d5f  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180045d64  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x180045d6b  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180045d6f  call    _CxxThrowException_0
0x180045d75  mov     dword ptr [rcx+130h], 2
0x180045d7f  mov     r8b, 1
0x180045d82  mov     edx, 4
0x180045d87  call    ?SetOption@RendererResource@Engine@Spectre@@QEAAXW4EResourceOption@123@_N@Z; Spectre::Engine::RendererResource::SetOption(Spectre::Engine::RendererResource::EResourceOption,bool)
0x180045d8c  mov     [rcx+124h], edi
0x180045d92  mov     [rcx+128h], edi
0x180045d98  mov     [rcx+7Ch], r10d
0x180045d9c  mov     [rcx+78h], r10d
0x180045da0  mov     [rcx+74h], r9d
0x180045da4  mov     [rcx+70h], r9d
0x180045da8  xor     eax, eax
0x180045daa  mov     [rcx+134h], ax
0x180045db1  mov     r8d, r10d; unsigned int
0x180045db4  xor     edx, edx; struct Spectre::Utils::Math::Vector3 *
0x180045db6  call    ?SetPositionsInternal@Mesh@Engine@Spectre@@IEAAXQEBUVector3@Math@Utils@3@I@Z; Spectre::Engine::Mesh::SetPositionsInternal(Spectre::Utils::Math::Vector3 const * const,uint)
0x180045dbb  test    dil, dil
0x180045dbe  jns     short loc_180045DCE
0x180045dc0  mov     r8d, [rbx+7Ch]; unsigned int
0x180045dc4  xor     edx, edx; unsigned int *
0x180045dc6  mov     rcx, rbx; this
0x180045dc9  call    ?SetColoursInternal@Mesh@Engine@Spectre@@IEAAXQEBII@Z; Spectre::Engine::Mesh::SetColoursInternal(uint const * const,uint)
0x180045dce  test    dil, 1
0x180045dd2  jz      short loc_180045DE2
0x180045dd4  mov     r8d, [rbx+7Ch]; unsigned int
0x180045dd8  xor     edx, edx; struct Spectre::Utils::Math::Vector2 *
0x180045dda  mov     rcx, rbx; this
0x180045ddd  call    ?SetUV0Internal@Mesh@Engine@Spectre@@IEAAXQEBUVector2@Math@Utils@3@I@Z; Spectre::Engine::Mesh::SetUV0Internal(Spectre::Utils::Math::Vector2 const * const,uint)
0x180045de2  test    dil, 2
0x180045de6  jz      short loc_180045DF6
0x180045de8  mov     r8d, [rbx+7Ch]; unsigned int
0x180045dec  xor     edx, edx; struct Spectre::Utils::Math::Vector2 *
0x180045dee  mov     rcx, rbx; this
0x180045df1  call    ?SetUV1Internal@Mesh@Engine@Spectre@@IEAAXQEBUVector2@Math@Utils@3@I@Z; Spectre::Engine::Mesh::SetUV1Internal(Spectre::Utils::Math::Vector2 const * const,uint)
0x180045df6  bt      edi, 1Ch
0x180045dfa  jnb     short loc_180045E16
0x180045dfc  mov     dword ptr [rbx+120h], 1
0x180045e06  mov     r8d, [rbx+74h]; unsigned int
0x180045e0a  xor     edx, edx; unsigned int *
0x180045e0c  mov     rcx, rbx; this
0x180045e0f  call    ?SetIndicesInternal@Mesh@Engine@Spectre@@IEAAXQEBII@Z; Spectre::Engine::Mesh::SetIndicesInternal(uint const * const,uint)
0x180045e14  jmp     short loc_180045E34
0x180045e16  test    dil, 40h
0x180045e1a  jz      short loc_180045E34
0x180045e1c  mov     dword ptr [rbx+120h], 0
0x180045e26  mov     r8d, [rbx+74h]; unsigned int
0x180045e2a  xor     edx, edx; unsigned __int16 *
0x180045e2c  mov     rcx, rbx; this
0x180045e2f  call    ?SetIndicesInternal@Mesh@Engine@Spectre@@IEAAXQEBGI@Z; Spectre::Engine::Mesh::SetIndicesInternal(ushort const * const,uint)
0x180045e34  test    dil, 10h
0x180045e38  jz      short loc_180045E4B
0x180045e3a  xor     r9d, r9d; bool
0x180045e3d  mov     r8d, [rbx+7Ch]; unsigned int
0x180045e41  xor     edx, edx; struct Spectre::Utils::Math::Vector3 *
0x180045e43  mov     rcx, rbx; this
0x180045e46  call    ?SetNormalsInternal@Mesh@Engine@Spectre@@IEAAXQEBUVector3@Math@Utils@3@I_N@Z; Spectre::Engine::Mesh::SetNormalsInternal(Spectre::Utils::Math::Vector3 const * const,uint,bool)
0x180045e4b  test    dil, 20h
0x180045e4f  jz      short loc_180045E62
0x180045e51  xor     r9d, r9d; bool
0x180045e54  mov     r8d, [rbx+7Ch]; unsigned int
0x180045e58  xor     edx, edx; struct Spectre::Utils::Math::Vector4 *
0x180045e5a  mov     rcx, rbx; this
0x180045e5d  call    ?SetTangentsInternal@Mesh@Engine@Spectre@@IEAAXQEBUVector4@Math@Utils@3@I_N@Z; Spectre::Engine::Mesh::SetTangentsInternal(Spectre::Utils::Math::Vector4 const * const,uint,bool)
0x180045e62  bt      edi, 0Ah
0x180045e66  jnb     short loc_180045E79
0x180045e68  mov     r9d, [rbx+7Ch]; unsigned int
0x180045e6c  xor     r8d, r8d; unsigned int *
0x180045e6f  xor     edx, edx; unsigned int *
0x180045e71  mov     rcx, rbx; this
0x180045e74  call    ?SetJointDataInternal@Mesh@Engine@Spectre@@IEAAXQEBI0I@Z; Spectre::Engine::Mesh::SetJointDataInternal(uint const * const,uint const * const,uint)
0x180045e79  mov     rcx, [rbp+4Fh+var_10]
0x180045e7d  xor     rcx, rsp; StackCookie
0x180045e80  call    __security_check_cookie
0x180045e85  lea     r11, [rsp+0C0h+var_s0]
0x180045e8d  mov     rbx, [r11+18h]
0x180045e91  mov     rdi, [r11+20h]
0x180045e95  mov     rsp, r11
0x180045e98  pop     rbp
0x180045e99  retn
0x180045e9a  lea     rdx, aMeshReservedyn_0; "Mesh::ReserveDynamic() -- vertex capaci"...
0x180045ea1  lea     rcx, [rbp+4Fh+var_88]
0x180045ea5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045eaa  nop
0x180045eab  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180045eb2  lea     rcx, [rbp+4Fh+var_68]
0x180045eb6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045ebb  lea     r9, [rbp+4Fh+var_88]
0x180045ebf  mov     rdx, rax
0x180045ec2  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180045ec6  call    ??0EngineInvalidPointerException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidPointerException::EngineInvalidPointerException(std::string,int,std::string const &,bool)
0x180045ecb  lea     rdx, _TI5?AUEngineInvalidPointerException@Engine@Spectre@@; pThrowInfo
0x180045ed2  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180045ed6  call    _CxxThrowException_0
```
