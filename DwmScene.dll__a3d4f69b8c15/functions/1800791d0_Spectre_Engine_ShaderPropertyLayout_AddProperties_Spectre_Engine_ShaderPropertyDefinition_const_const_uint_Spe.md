# Spectre::Engine::ShaderPropertyLayout::AddProperties(Spectre::Engine::ShaderPropertyDefinition const * const,uint,Spectre::Engine::EShaderPropertyLinkage)

- ea: `0x1800791d0`
- end: `0x18007928f`
- name: `?AddProperties@ShaderPropertyLayout@Engine@Spectre@@QEAAXQEBUShaderPropertyDefinition@23@IW4EShaderPropertyLinkage@23@@Z`
- size: `191`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800424a8`
- `0x180043310`
- `0x18004386c`
- `0x180043e00`
- `0x180075690`
- `0x1800764d0`
- `0x180076b70`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180038ddc`
- `0x1800791d0`
- `0x180079298`

## string_xrefs

- `0x180079217`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180079205`: `ShaderPropertyLayout::AddProperties() -- properties can only be added during declaration phase before EndDeclaration()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::ShaderPropertyLayout::AddProperties(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  int v8; // eax
  int v9; // r8d
  unsigned int i; // ebx
  _BYTE v11[32]; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-90h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-70h] BYREF

  if ( *(_DWORD *)(a1 + 1168) )
  {
    std::string::string(
      v12,
      "ShaderPropertyLayout::AddProperties() -- properties can only be added during declaration phase before EndDeclaration()");
    v8 = std::string::string(
           v11,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v8,
      v9,
      (unsigned int)v12,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  for ( i = 0; i < a3; ++i )
    Spectre::Engine::ShaderPropertyLayout::AddProperty(a1, a2 + ((unsigned __int64)i << 6), a4);
}

```

## disassembly

```asm
0x1800791d0  push    rbx
0x1800791d2  push    rbp
0x1800791d3  push    rsi
0x1800791d4  push    rdi
0x1800791d5  push    r14
0x1800791d7  sub     rsp, 0C0h
0x1800791de  mov     rax, cs:__security_cookie
0x1800791e5  xor     rax, rsp
0x1800791e8  mov     [rsp+0E8h+var_38], rax
0x1800791f0  mov     r14d, r9d
0x1800791f3  mov     edi, r8d
0x1800791f6  mov     rbp, rdx
0x1800791f9  mov     rsi, rcx
0x1800791fc  cmp     dword ptr [rcx+490h], 0
0x180079203  jz      short loc_180079251
0x180079205  lea     rdx, aShaderproperty_17; "ShaderPropertyLayout::AddProperties() -"...
0x18007920c  lea     rcx, [rsp+0E8h+var_90]
0x180079211  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180079216  nop
0x180079217  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007921e  lea     rcx, [rsp+0E8h+var_B0]
0x180079223  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180079228  mov     [rsp+0E8h+var_C8], 0
0x18007922d  lea     r9, [rsp+0E8h+var_90]
0x180079232  mov     rdx, rax
0x180079235  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18007923a  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007923f  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180079246  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18007924b  call    _CxxThrowException_0
0x180079251  xor     ebx, ebx
0x180079253  test    edi, edi
0x180079255  jz      short loc_180079271
0x180079257  mov     edx, ebx
0x180079259  shl     rdx, 6
0x18007925d  add     rdx, rbp
0x180079260  mov     r8d, r14d
0x180079263  mov     rcx, rsi
0x180079266  call    ?AddProperty@ShaderPropertyLayout@Engine@Spectre@@QEAA?AW4ShaderProperty@23@AEBUShaderPropertyDefinition@23@W4EShaderPropertyLinkage@23@@Z; Spectre::Engine::ShaderPropertyLayout::AddProperty(Spectre::Engine::ShaderPropertyDefinition const &,Spectre::Engine::EShaderPropertyLinkage)
0x18007926b  inc     ebx
0x18007926d  cmp     ebx, edi
0x18007926f  jb      short loc_180079257
0x180079271  mov     rcx, [rsp+0E8h+var_38]
0x180079279  xor     rcx, rsp; StackCookie
0x18007927c  call    __security_check_cookie
0x180079281  add     rsp, 0C0h
0x180079288  pop     r14
0x18007928a  pop     rdi
0x18007928b  pop     rsi
0x18007928c  pop     rbp
0x18007928d  pop     rbx
0x18007928e  retn
```
