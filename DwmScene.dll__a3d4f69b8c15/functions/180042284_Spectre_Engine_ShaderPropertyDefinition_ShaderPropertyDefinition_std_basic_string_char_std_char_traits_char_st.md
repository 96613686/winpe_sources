# Spectre::Engine::ShaderPropertyDefinition::ShaderPropertyDefinition(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,Spectre::Engine::ShaderPropertyType,int)

- ea: `0x180042284`
- end: `0x18004236a`
- name: `??0ShaderPropertyDefinition@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderPropertyType@12@H@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180043310`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180012ba8`
- `0x18001d0e4`
- `0x180038ddc`
- `0x180042054`
- `0x180042284`

## string_xrefs

- `0x1800422fa`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\Inc\NativeRenderer\Resources\ShaderDefinitions.h`
- `0x1800422e8`: `Shader integer has default value is outside the currently supported range (must be exactly representable as float).`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Spectre::Engine::ShaderPropertyDefinition::ShaderPropertyDefinition(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // r8d
  _DWORD v9[4]; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v10; // [rsp+40h] [rbp-A8h]
  _BYTE v11[32]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v12; // [rsp+70h] [rbp-78h]
  _BYTE v13[32]; // [rsp+78h] [rbp-70h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+98h] [rbp-50h] BYREF

  v10 = a1;
  v12 = a2;
  std::string::string();
  *(_DWORD *)(v4 + 32) = 1;
  v9[0] = 0;
  std::vector<float>::vector<float>(v4 + 40, v5, v9);
  if ( (int)**(float **)(a1 + 40) )
  {
    std::string::string(
      v13,
      "Shader integer has default value is outside the currently supported range (must be exactly representable as float).");
    v6 = std::string::string(
           v11,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\Inc\\NativeRenderer\\Re"
           "sources\\ShaderDefinitions.h");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v6,
      v7,
      (unsigned int)v13,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  std::string::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x180042284  mov     [rsp+arg_10], rbx
0x180042289  mov     [rsp+arg_18], rsi
0x18004228e  push    rdi
0x18004228f  sub     rsp, 0E0h
0x180042296  mov     rax, cs:__security_cookie
0x18004229d  xor     rax, rsp
0x1800422a0  mov     [rsp+0E8h+var_18], rax
0x1800422a8  mov     rsi, rdx
0x1800422ab  mov     rdi, rcx
0x1800422ae  mov     [rsp+0E8h+var_A8], rcx
0x1800422b3  mov     [rsp+0E8h+var_78], rdx
0x1800422b8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x1800422bd  nop
0x1800422be  mov     dword ptr [rcx+20h], 1
0x1800422c5  mov     [rsp+0E8h+var_B8], 0
0x1800422cd  lea     r8, [rsp+0E8h+var_B8]
0x1800422d2  add     rcx, 28h ; '('
0x1800422d6  call    ??$?0V?$allocator@M@std@@$0A@@?$vector@MV?$allocator@M@std@@@std@@QEAA@_KAEBMAEBV?$allocator@M@1@@Z; std::vector<float>::vector<float>(unsigned __int64,float const &,std::allocator<float> const &)
0x1800422db  nop
0x1800422dc  mov     rax, [rdi+28h]
0x1800422e0  cvttss2si ecx, dword ptr [rax]
0x1800422e4  test    ecx, ecx
0x1800422e6  jz      short loc_18004233A
0x1800422e8  lea     rdx, aShaderIntegerH; "Shader integer has default value is out"...
0x1800422ef  lea     rcx, [rsp+0E8h+var_70]
0x1800422f4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800422f9  nop
0x1800422fa  lea     rdx, aOnecoreuapWind_55; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180042301  lea     rcx, [rsp+0E8h+var_98]
0x180042306  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004230b  mov     [rsp+0E8h+var_C8], 0
0x180042310  lea     r9, [rsp+0E8h+var_70]
0x180042315  mov     rdx, rax
0x180042318  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180042320  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180042325  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004232c  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180042334  call    _CxxThrowException_0
0x18004233a  mov     rcx, rsi
0x18004233d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180042342  mov     rax, rdi
0x180042345  mov     rcx, [rsp+0E8h+var_18]
0x18004234d  xor     rcx, rsp; StackCookie
0x180042350  call    __security_check_cookie
0x180042355  lea     r11, [rsp+0E8h+var_8]
0x18004235d  mov     rbx, [r11+20h]
0x180042361  mov     rsi, [r11+28h]
0x180042365  mov     rsp, r11
0x180042368  pop     rdi
0x180042369  retn
```
