# Spectre::Engine::ShaderFamily::CreatePipelines(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x18005b160`
- end: `0x18005b2f4`
- name: `?CreatePipelines@ShaderFamily@Engine@Spectre@@QEAA?AV?$vector@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@@2@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@_K111@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180075690`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18000e8d0`
- `0x18001128c`
- `0x180011c50`
- `0x180011f64`
- `0x180012ba8`
- `0x180018318`
- `0x18002d21c`
- `0x180038ddc`
- `0x18005b014`
- `0x18005b160`
- `0x18007e2dc`

## string_xrefs

- `0x18005b2bd`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderfamily.cpp`
- `0x18005b2ac`: `ShaderFamily::CreatePipelines() -- Combination basis options must not be part of required or excluded set`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Spectre::Engine::ShaderFamily::CreatePipelines(
        int a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v8; // r10d
  int v9; // r11d
  __int64 v10; // r12
  __int64 Pipeline; // rax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  int v17; // eax
  int v18; // r8d
  int v19; // [rsp+38h] [rbp-C8h]
  char v21; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h]
  _BYTE v25[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+B8h] [rbp-48h] BYREF

  v19 = a4;
  v24 = a3;
  if ( (a4 & a6) != 0 )
  {
    std::string::string(
      v25,
      "ShaderFamily::CreatePipelines() -- Combination basis options must not be part of required or excluded set");
    v17 = std::string::string(
            v23,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderfamily.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v17,
      v18,
      (unsigned int)v25,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(a2);
  v10 = 0;
  do
  {
    Pipeline = Spectre::Engine::ShaderFamily::CreatePipeline(
                 v9,
                 (unsigned int)&v21,
                 (unsigned int)v10 | v8,
                 (unsigned int)a6 & ~(_DWORD)v10,
                 0);
    v12 = a2[1];
    if ( v12 == a2[2] )
      std::vector<std::shared_ptr<Spectre::Engine::ShaderPipeline>>::_Emplace_reallocate<std::shared_ptr<Spectre::Engine::ShaderPipeline>>(
        a2,
        v12,
        Pipeline);
    else
      std::vector<std::shared_ptr<Spectre::Engine::ImageProcessingEffect>>::_Emplace_back_with_unused_capacity<std::shared_ptr<Spectre::Engine::ImageProcessingEffect>>(
        a2,
        Pipeline);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    v13 = *(_QWORD *)(a2[1] - 16LL);
    v14 = std::string::string(v25, &qword_1801687B8);
    v15 = std::string::string(v23, a3);
    Spectre::Engine::ShaderPipeline::SetShaders(v13, v15, v10, v14);
    v10 = a6 & ((~a6 | v10) + 1);
    v8 = v19;
    v9 = a1;
  }
  while ( v10 );
  std::string::_Tidy_deallocate(a3);
  return a2;
}

```

## disassembly

```asm
0x18005b160  push    rbp
0x18005b162  push    rbx
0x18005b163  push    rsi
0x18005b164  push    rdi
0x18005b165  push    r12
0x18005b167  push    r13
0x18005b169  push    r14
0x18005b16b  push    r15
0x18005b16d  lea     rbp, [rsp-8]
0x18005b172  sub     rsp, 108h
0x18005b179  mov     rax, cs:__security_cookie
0x18005b180  xor     rax, rsp
0x18005b183  mov     [rbp+40h+var_50], rax
0x18005b187  mov     r10, r9
0x18005b18a  mov     [rsp+140h+var_108], r9
0x18005b18f  mov     r14, r8
0x18005b192  mov     rsi, rdx
0x18005b195  mov     r11, rcx
0x18005b198  mov     [rsp+140h+var_100], rcx
0x18005b19d  mov     [rsp+140h+var_F0], rdx
0x18005b1a2  mov     [rbp+40h+var_B0], r8
0x18005b1a6  mov     [rsp+140h+var_110], 0
0x18005b1ae  mov     r15, [rbp+40h+arg_28]
0x18005b1b2  test    r15, r9
0x18005b1b5  jnz     loc_18005B2AC
0x18005b1bb  mov     rcx, rdx; void *
0x18005b1be  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x18005b1c3  mov     [rsp+140h+var_110], 1
0x18005b1cb  xor     r12d, r12d
0x18005b1ce  mov     r13, r15
0x18005b1d1  not     r13
0x18005b1d4  mov     r9, r12
0x18005b1d7  not     r9
0x18005b1da  and     r9, r15
0x18005b1dd  mov     r8, r10
0x18005b1e0  or      r8, r12
0x18005b1e3  mov     [rsp+140h+var_120], 0
0x18005b1e8  lea     rdx, [rsp+140h+var_E0]
0x18005b1ed  mov     rcx, r11
0x18005b1f0  call    ?CreatePipeline@ShaderFamily@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@_K0_N@Z; Spectre::Engine::ShaderFamily::CreatePipeline(unsigned __int64,unsigned __int64,bool)
0x18005b1f5  nop
0x18005b1f6  mov     rdx, [rsi+8]
0x18005b1fa  mov     rcx, rsi
0x18005b1fd  cmp     rdx, [rsi+10h]
0x18005b201  jz      short loc_18005B20D
0x18005b203  mov     rdx, rax
0x18005b206  call    ??$_Emplace_back_with_unused_capacity@V?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@std@@@?$vector@V?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@std@@@2@@std@@AEAAAEAV?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@1@$$QEAV21@@Z; std::vector<std::shared_ptr<Spectre::Engine::ImageProcessingEffect>>::_Emplace_back_with_unused_capacity<std::shared_ptr<Spectre::Engine::ImageProcessingEffect>>(std::shared_ptr<Spectre::Engine::ImageProcessingEffect> &&)
0x18005b20b  jmp     short loc_18005B216
0x18005b20d  mov     r8, rax
0x18005b210  call    ??$_Emplace_reallocate@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@@?$vector@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VShaderPipeline@Engine@Spectre@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<Spectre::Engine::ShaderPipeline>>::_Emplace_reallocate<std::shared_ptr<Spectre::Engine::ShaderPipeline>>(std::shared_ptr<Spectre::Engine::ShaderPipeline> * const,std::shared_ptr<Spectre::Engine::ShaderPipeline> &&)
0x18005b215  nop
0x18005b216  mov     rcx, [rsp+140h+var_D8]; this
0x18005b21b  test    rcx, rcx
0x18005b21e  jz      short loc_18005B225
0x18005b220  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005b225  mov     rax, [rsi+8]
0x18005b229  mov     rdi, [rax-10h]
0x18005b22d  lea     rax, [rbp+40h+var_A8]
0x18005b231  mov     [rsp+140h+var_E8], rax
0x18005b236  lea     rdx, qword_1801687B8
0x18005b23d  lea     rcx, [rbp+40h+var_A8]
0x18005b241  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005b246  mov     rbx, rax
0x18005b249  mov     rdx, r14
0x18005b24c  lea     rcx, [rsp+140h+var_D0]
0x18005b251  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18005b256  nop
0x18005b257  mov     r9, rbx
0x18005b25a  mov     r8, r12
0x18005b25d  mov     rdx, rax
0x18005b260  mov     rcx, rdi
0x18005b263  call    ?SetShaders@ShaderPipeline@Engine@Spectre@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K0@Z; Spectre::Engine::ShaderPipeline::SetShaders(std::string,unsigned __int64,std::string)
0x18005b268  or      r12, r13
0x18005b26b  inc     r12
0x18005b26e  and     r12, r15
0x18005b271  mov     r10, [rsp+140h+var_108]
0x18005b276  mov     r11, [rsp+140h+var_100]
0x18005b27b  jnz     loc_18005B1D4
0x18005b281  mov     rcx, r14
0x18005b284  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005b289  mov     rax, rsi
0x18005b28c  mov     rcx, [rbp+40h+var_50]
0x18005b290  xor     rcx, rsp; StackCookie
0x18005b293  call    __security_check_cookie
0x18005b298  add     rsp, 108h
0x18005b29f  pop     r15
0x18005b2a1  pop     r14
0x18005b2a3  pop     r13
0x18005b2a5  pop     r12
0x18005b2a7  pop     rdi
0x18005b2a8  pop     rsi
0x18005b2a9  pop     rbx
0x18005b2aa  pop     rbp
0x18005b2ab  retn
0x18005b2ac  lea     rdx, aShaderfamilyCr_0; "ShaderFamily::CreatePipelines() -- Comb"...
0x18005b2b3  lea     rcx, [rbp+40h+var_A8]
0x18005b2b7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005b2bc  nop
0x18005b2bd  lea     rdx, aOnecoreuapWind_45; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18005b2c4  lea     rcx, [rsp+140h+var_D0]
0x18005b2c9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005b2ce  mov     [rsp+140h+var_120], 0
0x18005b2d3  lea     r9, [rbp+40h+var_A8]
0x18005b2d7  mov     rdx, rax
0x18005b2da  lea     rcx, [rbp+40h+pExceptionObject]
0x18005b2de  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18005b2e3  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18005b2ea  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18005b2ee  call    _CxxThrowException_0
```
