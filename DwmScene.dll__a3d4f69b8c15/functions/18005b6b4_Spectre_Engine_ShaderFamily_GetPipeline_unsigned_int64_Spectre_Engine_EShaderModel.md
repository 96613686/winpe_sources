# Spectre::Engine::ShaderFamily::GetPipeline(unsigned __int64,Spectre::Engine::EShaderModel)

- ea: `0x18005b6b4`
- end: `0x18005b852`
- name: `?GetPipeline@ShaderFamily@Engine@Spectre@@QEBA?AV?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@_KW4EShaderModel@23@@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18004151c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011d8c`
- `0x180011f64`
- `0x1800121f4`
- `0x180012df8`
- `0x180013664`
- `0x180038ddc`
- `0x18004a81c`
- `0x18005a0e8`
- `0x18005b6b4`

## string_xrefs

- `0x18005b6f7`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderfamily.cpp`
- `0x18005b6e6`: `ShaderFamily::GetPipeline() -- shader family declaration must be complete before pipelines can be accessed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Spectre::Engine::ShaderFamily::GetPipeline(__int64 a1, _QWORD *a2, __int64 a3, int a4)
{
  int v5; // eax
  int v6; // r8d
  _QWORD *v7; // rax
  __int64 v8; // r11
  _QWORD *v9; // rdx
  _QWORD *v10; // rcx
  _QWORD *i; // rax
  _QWORD *v12; // rdi
  __int64 v13; // rdx
  _QWORD *v14; // r9
  _QWORD *v15; // r8
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  unsigned __int64 v19; // [rsp+30h] [rbp-69h] BYREF
  int v20; // [rsp+38h] [rbp-61h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v22[16]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v23; // [rsp+68h] [rbp-31h]
  _BYTE v24[32]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+98h] [rbp-1h] BYREF

  v19 = (unsigned __int64)a2;
  v20 = a4;
  if ( *(_DWORD *)(a1 + 432) != 1 )
  {
    std::string::string(
      v24,
      "ShaderFamily::GetPipeline() -- shader family declaration must be complete before pipelines can be accessed");
    v5 = std::string::string(
           v22,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderfamily.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v5,
      v6,
      (unsigned int)v24,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v19 = a3 & *(_QWORD *)(a1 + 64);
  v7 = (_QWORD *)std::map<enum Spectre::Engine::EShaderModel,Spectre::Engine::ShaderFamily::ShaderPipelineCollection>::_Try_emplace<enum Spectre::Engine::EShaderModel const &,>(
                   a1 + 416,
                   v24,
                   &v20);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::function<std::shared_ptr<Spectre::Engine::RendererResource> (void)>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::function<std::shared_ptr<Spectre::Engine::RendererResource> (void)>>>,0>>::_Find_lower_bound<unsigned __int64>(
    *v7 + 56LL,
    v22,
    &v19);
  if ( *(_BYTE *)(v23 + 25) || v19 < *(_QWORD *)(v23 + 32) || v23 == *(_QWORD *)(v8 + 56) )
  {
    v10 = *(_QWORD **)(v8 + 40);
    for ( i = (_QWORD *)*v10; i != v10; i = (_QWORD *)*i )
    {
      v12 = i + 2;
      v13 = i[2];
      v14 = *(_QWORD **)(v13 + 32);
      v15 = *(_QWORD **)(v13 + 24);
      if ( v15 == v14 )
      {
LABEL_16:
        v16 = (_QWORD *)std::map<unsigned char const *,std::shared_ptr<Spectre::Engine::Shader>>::_Try_emplace<unsigned char const * const &,>(
                          v8 + 56,
                          v21,
                          &v19);
        std::shared_ptr<Spectre::Engine::Light>::operator=(*v16 + 40LL, v12);
        v9 = v12;
        goto LABEL_7;
      }
      while ( v15 != v14 )
      {
        if ( (v19 & *v15) == *v15 && (v19 & v15[1]) == 0 )
          goto LABEL_16;
        v15 += 2;
      }
    }
    *(_OWORD *)v21 = 0;
    v17 = (_QWORD *)std::map<unsigned char const *,std::shared_ptr<Spectre::Engine::Shader>>::_Try_emplace<unsigned char const * const &,>(
                      v8 + 56,
                      v22,
                      &v19);
    std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(*v17 + 40LL, v21);
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
    *a2 = 0;
    a2[1] = 0;
  }
  else
  {
    v9 = (_QWORD *)(v23 + 40);
LABEL_7:
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(a2, v9);
  }
  return a2;
}

```

## disassembly

```asm
0x18005b6b4  push    rbp
0x18005b6b6  push    rbx
0x18005b6b7  push    rdi
0x18005b6b8  lea     rbp, [rsp-47h]
0x18005b6bd  sub     rsp, 0E0h
0x18005b6c4  mov     rax, cs:__security_cookie
0x18005b6cb  xor     rax, rsp
0x18005b6ce  mov     [rbp+57h+var_20], rax
0x18005b6d2  mov     rbx, rdx
0x18005b6d5  mov     [rbp+57h+var_C0], rdx
0x18005b6d9  mov     [rbp+57h+var_B8], r9d
0x18005b6dd  cmp     dword ptr [rcx+1B0h], 1
0x18005b6e4  jz      short loc_18005B72D
0x18005b6e6  lea     rdx, aShaderfamilyGe; "ShaderFamily::GetPipeline() -- shader f"...
0x18005b6ed  lea     rcx, [rbp+57h+var_78]
0x18005b6f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005b6f6  nop
0x18005b6f7  lea     rdx, aOnecoreuapWind_45; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18005b6fe  lea     rcx, [rbp+57h+var_98]
0x18005b702  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005b707  mov     [rsp+0F0h+var_D0], 0
0x18005b70c  lea     r9, [rbp+57h+var_78]
0x18005b710  mov     rdx, rax
0x18005b713  lea     rcx, [rbp+57h+pExceptionObject]
0x18005b717  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18005b71c  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18005b723  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005b727  call    _CxxThrowException_0
0x18005b72d  mov     rax, [rcx+40h]
0x18005b731  and     rax, r8
0x18005b734  mov     [rbp+57h+var_C0], rax
0x18005b738  add     rcx, 1A0h
0x18005b73f  lea     r8, [rbp+57h+var_B8]
0x18005b743  lea     rdx, [rbp+57h+var_78]
0x18005b747  call    ??$_Try_emplace@AEBW4EShaderModel@Engine@Spectre@@$$V@?$map@W4EShaderModel@Engine@Spectre@@UShaderPipelineCollection@ShaderFamily@23@U?$less@W4EShaderModel@Engine@Spectre@@@std@@V?$allocator@U?$pair@$$CBW4EShaderModel@Engine@Spectre@@UShaderPipelineCollection@ShaderFamily@23@@std@@@7@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4EShaderModel@Engine@Spectre@@UShaderPipelineCollection@ShaderFamily@23@@std@@PEAX@std@@_N@1@AEBW4EShaderModel@Engine@Spectre@@@Z; std::map<Spectre::Engine::EShaderModel,Spectre::Engine::ShaderFamily::ShaderPipelineCollection>::_Try_emplace<Spectre::Engine::EShaderModel const &,>(Spectre::Engine::EShaderModel const &)
0x18005b74c  mov     r11, [rax]
0x18005b74f  lea     r8, [rbp+57h+var_C0]
0x18005b753  lea     rdx, [rbp+57h+var_98]
0x18005b757  lea     rcx, [r11+38h]
0x18005b75b  call    ??$_Find_lower_bound@_K@?$_Tree@V?$_Tmap_traits@_KV?$function@$$A6A?AV?$shared_ptr@VRendererResource@Engine@Spectre@@@std@@XZ@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$function@$$A6A?AV?$shared_ptr@VRendererResource@Engine@Spectre@@@std@@XZ@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_KV?$function@$$A6A?AV?$shared_ptr@VRendererResource@Engine@Spectre@@@std@@XZ@std@@@std@@PEAX@std@@@1@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::function<std::shared_ptr<Spectre::Engine::RendererResource> (void)>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::function<std::shared_ptr<Spectre::Engine::RendererResource> (void)>>>,0>>::_Find_lower_bound<unsigned __int64>(unsigned __int64 const &)
0x18005b760  mov     r10, [rbp+57h+var_C0]
0x18005b764  mov     rdx, [rbp+57h+var_88]
0x18005b768  cmp     byte ptr [rdx+19h], 0
0x18005b76c  jnz     short loc_18005B78B
0x18005b76e  cmp     r10, [rdx+20h]
0x18005b772  jb      short loc_18005B78B
0x18005b774  cmp     rdx, [r11+38h]
0x18005b778  jz      short loc_18005B78B
0x18005b77a  add     rdx, 28h ; '('
0x18005b77e  mov     rcx, rbx
0x18005b781  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18005b786  jmp     loc_18005B838
0x18005b78b  mov     rcx, [r11+28h]
0x18005b78f  mov     rax, [rcx]
0x18005b792  cmp     rax, rcx
0x18005b795  jz      short loc_18005B7F1
0x18005b797  lea     rdi, [rax+10h]
0x18005b79b  mov     rdx, [rdi]
0x18005b79e  mov     r9, [rdx+20h]
0x18005b7a2  mov     r8, [rdx+18h]
0x18005b7a6  cmp     r8, r9
0x18005b7a9  jz      short loc_18005B7CC
0x18005b7ab  cmp     r8, r9
0x18005b7ae  jz      short loc_18005B7C7
0x18005b7b0  mov     rdx, [r8]
0x18005b7b3  and     rdx, r10
0x18005b7b6  cmp     rdx, [r8]
0x18005b7b9  jnz     short loc_18005B7C1
0x18005b7bb  test    [r8+8], r10
0x18005b7bf  jz      short loc_18005B7CC
0x18005b7c1  add     r8, 10h
0x18005b7c5  jmp     short loc_18005B7AB
0x18005b7c7  mov     rax, [rax]
0x18005b7ca  jmp     short loc_18005B792
0x18005b7cc  lea     rcx, [r11+38h]
0x18005b7d0  lea     r8, [rbp+57h+var_C0]
0x18005b7d4  lea     rdx, [rbp+57h+var_B0]
0x18005b7d8  call    ??$_Try_emplace@AEBQEBE$$V@?$map@PEBEV?$shared_ptr@VShader@Engine@Spectre@@@std@@U?$less@PEBE@2@V?$allocator@U?$pair@QEBEV?$shared_ptr@VShader@Engine@Spectre@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEBEV?$shared_ptr@VShader@Engine@Spectre@@@std@@@std@@PEAX@std@@_N@1@AEBQEBE@Z; std::map<uchar const *,std::shared_ptr<Spectre::Engine::Shader>>::_Try_emplace<uchar const * const &,>(uchar const * const &)
0x18005b7dd  mov     rcx, [rax]
0x18005b7e0  add     rcx, 28h ; '('
0x18005b7e4  mov     rdx, rdi
0x18005b7e7  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x18005b7ec  mov     rdx, rdi
0x18005b7ef  jmp     short loc_18005B77E
0x18005b7f1  xorps   xmm0, xmm0
0x18005b7f4  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x18005b7f9  lea     rcx, [r11+38h]
0x18005b7fd  lea     r8, [rbp+57h+var_C0]
0x18005b801  lea     rdx, [rbp+57h+var_98]
0x18005b805  call    ??$_Try_emplace@AEBQEBE$$V@?$map@PEBEV?$shared_ptr@VShader@Engine@Spectre@@@std@@U?$less@PEBE@2@V?$allocator@U?$pair@QEBEV?$shared_ptr@VShader@Engine@Spectre@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEBEV?$shared_ptr@VShader@Engine@Spectre@@@std@@@std@@PEAX@std@@_N@1@AEBQEBE@Z; std::map<uchar const *,std::shared_ptr<Spectre::Engine::Shader>>::_Try_emplace<uchar const * const &,>(uchar const * const &)
0x18005b80a  mov     rcx, [rax]
0x18005b80d  add     rcx, 28h ; '('
0x18005b811  lea     rdx, [rbp+57h+var_B0]
0x18005b815  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x18005b81a  nop
0x18005b81b  mov     rcx, [rbp+57h+var_B0+8]; this
0x18005b81f  test    rcx, rcx
0x18005b822  jz      short loc_18005B829
0x18005b824  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005b829  mov     qword ptr [rbx], 0
0x18005b830  mov     qword ptr [rbx+8], 0
0x18005b838  mov     rax, rbx
0x18005b83b  mov     rcx, [rbp+57h+var_20]
0x18005b83f  xor     rcx, rsp; StackCookie
0x18005b842  call    __security_check_cookie
0x18005b847  add     rsp, 0E0h
0x18005b84e  pop     rdi
0x18005b84f  pop     rbx
0x18005b850  pop     rbp
0x18005b851  retn
```
