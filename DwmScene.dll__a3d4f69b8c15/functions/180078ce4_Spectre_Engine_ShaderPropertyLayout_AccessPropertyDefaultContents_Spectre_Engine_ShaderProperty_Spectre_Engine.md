# Spectre::Engine::ShaderPropertyLayout::AccessPropertyDefaultContents(Spectre::Engine::ShaderProperty,Spectre::Engine::ShaderPropertyType)

- ea: `0x180078ce4`
- end: `0x180078df5`
- name: `?AccessPropertyDefaultContents@ShaderPropertyLayout@Engine@Spectre@@AEAAPEATValueElement@123@W4ShaderProperty@23@W4ShaderPropertyType@23@@Z`
- size: `273`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180043e00`
- `0x18007a184`
- `0x18007a440`
- `0x18007a470`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x18001c6e0`
- `0x180027ea4`
- `0x180038ddc`
- `0x180078ce4`

## string_xrefs

- `0x180078d21`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180078d8f`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Spectre::Engine::ShaderPropertyLayout::AccessPropertyDefaultContents(
        __int64 a1,
        unsigned __int16 a2)
{
  int v3; // eax
  int v4; // r8d
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // ebx
  int v8; // eax
  int v9; // r8d
  _BYTE v11[32]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v14[56]; // [rsp+B0h] [rbp+17h] BYREF

  if ( *(_DWORD *)(a1 + 1168) )
  {
    std::string::string(
      v11,
      "ShaderPropertyLayout::SetPropertyDefault() -- cannot set property defaults after calling ShaderPropertyLayout::EndDeclaration()");
    v3 = std::string::string(
           v12,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v3,
      v4,
      (unsigned int)v11,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v5 = *(unsigned __int16 *)(a1 + 2LL * a2 + 128);
  if ( (_WORD)v5 == 0xFFFF )
  {
    v6 = std::to_string(v12, a2);
    v7 = std::operator+<char>(
           pExceptionObject,
           "ShaderPropertyLayout::SetPropertyDefault() -- property layout does not have a property with the specified ID ",
           v6);
    v8 = std::string::string(
           v11,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v14, v8, v9, v7, 0);
    throw (Spectre::Engine::EngineInvalidArgException *)v14;
  }
  return *(_QWORD *)(a1 + 80) + 4LL * *(unsigned int *)(56 * v5 + *(_QWORD *)(a1 + 56) + 40);
}

```

## disassembly

```asm
0x180078ce4  mov     [rsp-8+arg_0], rbx
0x180078ce9  push    rbp
0x180078cea  lea     rbp, [rsp-57h]
0x180078cef  sub     rsp, 0F0h
0x180078cf6  mov     rax, cs:__security_cookie
0x180078cfd  xor     rax, rsp
0x180078d00  mov     [rbp+57h+var_8], rax
0x180078d04  mov     r8, rcx
0x180078d07  cmp     dword ptr [rcx+490h], 0
0x180078d0e  jz      short loc_180078D57
0x180078d10  lea     rdx, aShaderproperty_9; "ShaderPropertyLayout::SetPropertyDefaul"...
0x180078d17  lea     rcx, [rbp+57h+var_B8]
0x180078d1b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078d20  nop
0x180078d21  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180078d28  lea     rcx, [rbp+57h+var_98]
0x180078d2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078d31  mov     [rsp+0F0h+var_D0], 0
0x180078d36  lea     r9, [rbp+57h+var_B8]
0x180078d3a  mov     rdx, rax
0x180078d3d  lea     rcx, [rbp+57h+pExceptionObject]
0x180078d41  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180078d46  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180078d4d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180078d51  call    _CxxThrowException_0
0x180078d57  movzx   eax, dx
0x180078d5a  movzx   ecx, word ptr [rcx+rax*2+80h]
0x180078d62  mov     eax, 0FFFFh
0x180078d67  cmp     cx, ax
0x180078d6a  jnz     short loc_180078DC4
0x180078d6c  movzx   edx, dx
0x180078d6f  lea     rcx, [rbp+57h+var_98]
0x180078d73  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@J@Z; std::to_string(long)
0x180078d78  nop
0x180078d79  mov     r8, rax
0x180078d7c  lea     rdx, aShaderproperty_25; "ShaderPropertyLayout::SetPropertyDefaul"...
0x180078d83  lea     rcx, [rbp+57h+pExceptionObject]
0x180078d87  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180078d8c  mov     rbx, rax
0x180078d8f  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180078d96  lea     rcx, [rbp+57h+var_B8]
0x180078d9a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180078d9f  mov     [rsp+0F0h+var_D0], 0
0x180078da4  mov     r9, rbx
0x180078da7  mov     rdx, rax
0x180078daa  lea     rcx, [rbp+57h+var_40]
0x180078dae  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180078db3  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180078dba  lea     rcx, [rbp+57h+var_40]; pExceptionObject
0x180078dbe  call    _CxxThrowException_0
0x180078dc4  imul    rcx, 38h ; '8'
0x180078dc8  mov     rax, [r8+38h]
0x180078dcc  mov     edx, [rcx+rax+28h]
0x180078dd0  mov     rax, [r8+50h]
0x180078dd4  lea     rax, [rax+rdx*4]
0x180078dd8  mov     rcx, [rbp+57h+var_8]
0x180078ddc  xor     rcx, rsp; StackCookie
0x180078ddf  call    __security_check_cookie
0x180078de4  mov     rbx, [rsp+0F0h+arg_0]
0x180078dec  add     rsp, 0F0h
0x180078df3  pop     rbp
0x180078df4  retn
```
