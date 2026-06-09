# Spectre::Engine::ShaderPropertyLayout::CreateBlock(void)

- ea: `0x18007978c`
- end: `0x180079902`
- name: `?CreateBlock@ShaderPropertyLayout@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderPropertyBlock@Engine@Spectre@@@std@@XZ`
- size: `374`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18004176c`
- `0x180048180`
- `0x18004d400`
- `0x18005b4d4`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180013664`
- `0x18001c290`
- `0x180038ddc`
- `0x180040a6c`
- `0x18004c640`
- `0x18007816c`
- `0x18007978c`
- `0x18007baf0`

## string_xrefs

- `0x1800797df`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x1800797ce`: `ShaderPropertyLayout::CreateBlock() -- layout declaration must be complete before a property block can be created.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Spectre::Engine::ShaderPropertyBlock **__fastcall Spectre::Engine::ShaderPropertyLayout::CreateBlock(
        __int64 a1,
        Spectre::Engine::ShaderPropertyBlock **a2)
{
  int v4; // eax
  int v5; // r8d
  __int64 v6; // rdi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  Spectre::Engine::ShaderPropertyBlock *v9; // rdi
  std::_Ref_count_base *v10; // rcx
  _QWORD *GlobalProperties; // [rsp+38h] [rbp-61h]
  _BYTE v13[8]; // [rsp+40h] [rbp-59h] BYREF
  std::_Ref_count_base *v14; // [rsp+48h] [rbp-51h]
  Spectre::Engine::ShaderPropertyBlock **v15; // [rsp+50h] [rbp-49h]
  _BYTE v16[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v17[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+98h] [rbp-1h] BYREF

  v15 = a2;
  if ( *(_DWORD *)(a1 + 1168) != 1 )
  {
    std::string::string(
      v17,
      "ShaderPropertyLayout::CreateBlock() -- layout declaration must be complete before a property block can be created.");
    v4 = std::string::string(
           v16,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v4,
      v5,
      (unsigned int)v17,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v6 = std::enable_shared_from_this<Spectre::Engine::Component>::shared_from_this(a1, v13);
  v7 = operator new(0xA8u);
  v8 = v7;
  if ( v7 )
  {
    *(_OWORD *)v7 = 0;
    v7[2] = 1;
    v7[3] = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<Spectre::Engine::ShaderPropertyBlock>::`vftable';
    std::_Construct_in_place<Spectre::Engine::ShaderPropertyBlock,std::shared_ptr<Spectre::Engine::ShaderPropertyLayout>>(
      v7 + 4,
      v6);
  }
  else
  {
    v8 = 0;
  }
  *a2 = (Spectre::Engine::ShaderPropertyBlock *)(v8 + 4);
  a2[1] = (Spectre::Engine::ShaderPropertyBlock *)v8;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  if ( *(_BYTE *)(a1 + 1241) )
  {
    v9 = *a2;
    GlobalProperties = (_QWORD *)Spectre::Engine::ShaderManager::GetGlobalProperties(*(_QWORD *)(a1 + 1152), v13);
    std::shared_ptr<Spectre::Engine::Light>::operator=((char *)v9 + 112, GlobalProperties);
    *((_DWORD *)v9 + 26) = *(_DWORD *)(*GlobalProperties + 80LL) - 1;
    Spectre::Engine::ShaderPropertyBlock::FlushImportedProperties(v9);
    v10 = (std::_Ref_count_base *)GlobalProperties[1];
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
  }
  return a2;
}

```

## disassembly

```asm
0x18007978c  mov     [rsp-8+arg_10], rbx
0x180079791  mov     [rsp-8+arg_18], rsi
0x180079796  push    rbp
0x180079797  push    rdi
0x180079798  push    r14
0x18007979a  lea     rbp, [rsp-47h]
0x18007979f  sub     rsp, 0E0h
0x1800797a6  mov     rax, cs:__security_cookie
0x1800797ad  xor     rax, rsp
0x1800797b0  mov     [rbp+57h+var_20], rax
0x1800797b4  mov     rsi, rdx
0x1800797b7  mov     r14, rcx
0x1800797ba  mov     [rbp+57h+var_A0], rdx
0x1800797be  mov     [rbp+57h+var_C0], 0
0x1800797c5  cmp     dword ptr [rcx+490h], 1
0x1800797cc  jz      short loc_180079815
0x1800797ce  lea     rdx, aShaderproperty_4; "ShaderPropertyLayout::CreateBlock() -- "...
0x1800797d5  lea     rcx, [rbp+57h+var_78]
0x1800797d9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800797de  nop
0x1800797df  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800797e6  lea     rcx, [rbp+57h+var_98]
0x1800797ea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800797ef  mov     [rsp+0F0h+var_D0], 0
0x1800797f4  lea     r9, [rbp+57h+var_78]
0x1800797f8  mov     rdx, rax
0x1800797fb  lea     rcx, [rbp+57h+pExceptionObject]
0x1800797ff  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180079804  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007980b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007980f  call    _CxxThrowException_0
0x180079815  lea     rdx, [rbp+57h+var_B0]
0x180079819  call    ?shared_from_this@?$enable_shared_from_this@VComponent@Engine@Spectre@@@std@@QEAA?AV?$shared_ptr@VComponent@Engine@Spectre@@@2@XZ; std::enable_shared_from_this<Spectre::Engine::Component>::shared_from_this(void)
0x18007981e  mov     rdi, rax
0x180079821  mov     ecx, 0A8h; unsigned __int64
0x180079826  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007982b  mov     rbx, rax
0x18007982e  mov     [rbp+57h+var_B8], rax
0x180079832  test    rax, rax
0x180079835  jz      short loc_180079863
0x180079837  xorps   xmm0, xmm0
0x18007983a  movups  xmmword ptr [rax], xmm0
0x18007983d  mov     dword ptr [rax+8], 1
0x180079844  mov     dword ptr [rax+0Ch], 1
0x18007984b  lea     rax, ??_7?$_Ref_count_obj2@VShaderPropertyBlock@Engine@Spectre@@@std@@6B@; const std::_Ref_count_obj2<Spectre::Engine::ShaderPropertyBlock>::`vftable'
0x180079852  mov     [rbx], rax
0x180079855  lea     rcx, [rbx+10h]
0x180079859  mov     rdx, rdi
0x18007985c  call    ??$_Construct_in_place@VShaderPropertyBlock@Engine@Spectre@@V?$shared_ptr@VShaderPropertyLayout@Engine@Spectre@@@std@@@std@@YAXAEAVShaderPropertyBlock@Engine@Spectre@@$$QEAV?$shared_ptr@VShaderPropertyLayout@Engine@Spectre@@@0@@Z; std::_Construct_in_place<Spectre::Engine::ShaderPropertyBlock,std::shared_ptr<Spectre::Engine::ShaderPropertyLayout>>(Spectre::Engine::ShaderPropertyBlock &,std::shared_ptr<Spectre::Engine::ShaderPropertyLayout> &&)
0x180079861  jmp     short loc_180079865
0x180079863  xor     ebx, ebx
0x180079865  lea     rax, [rbx+10h]
0x180079869  mov     [rsi], rax
0x18007986c  mov     [rsi+8], rbx
0x180079870  mov     [rbp+57h+var_C0], 5
0x180079877  mov     rcx, [rbp+57h+var_A8]; this
0x18007987b  test    rcx, rcx
0x18007987e  jz      short loc_180079885
0x180079880  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180079885  cmp     byte ptr [r14+4D9h], 0
0x18007988d  jz      short loc_1800798DA
0x18007988f  mov     rdi, [rsi]
0x180079892  lea     rdx, [rbp+57h+var_B0]
0x180079896  mov     rcx, [r14+480h]
0x18007989d  call    ?GetGlobalProperties@ShaderManager@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderPropertyBlock@Engine@Spectre@@@std@@XZ; Spectre::Engine::ShaderManager::GetGlobalProperties(void)
0x1800798a2  mov     rbx, rax
0x1800798a5  mov     [rbp+57h+var_B8], rax
0x1800798a9  lea     rcx, [rdi+70h]
0x1800798ad  mov     rdx, rax
0x1800798b0  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x1800798b5  mov     rdx, [rbx]
0x1800798b8  mov     r8d, [rdx+50h]
0x1800798bc  dec     r8d
0x1800798bf  mov     [rdi+68h], r8d
0x1800798c3  mov     rcx, rdi; this
0x1800798c6  call    ?FlushImportedProperties@ShaderPropertyBlock@Engine@Spectre@@AEAAXXZ; Spectre::Engine::ShaderPropertyBlock::FlushImportedProperties(void)
0x1800798cb  nop
0x1800798cc  mov     rcx, [rbx+8]; this
0x1800798d0  test    rcx, rcx
0x1800798d3  jz      short loc_1800798DA
0x1800798d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800798da  mov     rax, rsi
0x1800798dd  mov     rcx, [rbp+57h+var_20]
0x1800798e1  xor     rcx, rsp; StackCookie
0x1800798e4  call    __security_check_cookie
0x1800798e9  lea     r11, [rsp+0F0h+var_10]
0x1800798f1  mov     rbx, [r11+30h]
0x1800798f5  mov     rsi, [r11+38h]
0x1800798f9  mov     rsp, r11
0x1800798fc  pop     r14
0x1800798fe  pop     rdi
0x1800798ff  pop     rbp
0x180079900  retn
```
