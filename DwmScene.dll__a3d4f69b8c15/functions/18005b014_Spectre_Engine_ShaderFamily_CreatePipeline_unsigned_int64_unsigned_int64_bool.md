# Spectre::Engine::ShaderFamily::CreatePipeline(unsigned __int64,unsigned __int64,bool)

- ea: `0x18005b014`
- end: `0x18005b158`
- name: `?CreatePipeline@ShaderFamily@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@_K0_N@Z`
- size: `324`
- prototype: ``
- caller_count: `10`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005afdc`
- `0x18005b160`
- `0x180073cdc`
- `0x1800743c4`
- `0x180075690`
- `0x180076150`
- `0x1800764d0`
- `0x180077560`
- `0x18008d4dc`
- `0x18008e544`

## callees

- `0x180011a68`
- `0x180011f64`
- `0x18001daf4`
- `0x18002ebc8`
- `0x18005a0e8`
- `0x18005a444`
- `0x18005a82c`
- `0x18005b014`
- `0x18007cda0`
- `0x18007cdc8`
- `0x18007e240`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005b0f2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005b0f2`

## string_xrefs

- `0x18005b0aa`: `ShaderFamily::CreatePipeline() -- shaderModel is in invalid state. Pipeline creation must happen during a BeginShaderModel() / EndShaderModel() block.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall Spectre::Engine::ShaderFamily::CreatePipeline(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3,
        __int64 a4,
        char a5)
{
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rax
  _QWORD *v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // r9
  _QWORD *v20; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+38h] [rbp-28h]
  _BYTE v22[32]; // [rsp+40h] [rbp-20h] BYREF
  int v23; // [rsp+90h] [rbp+30h] BYREF
  __int64 *v24; // [rsp+98h] [rbp+38h]

  v24 = a2;
  std::make_shared<Spectre::Engine::ShaderPipeline,Spectre::Engine::ShaderFamily &>(a2, a1);
  v20 = a3;
  v21 = a4;
  v9 = *a2 + 24;
  v10 = *(_QWORD *)(*a2 + 32);
  if ( v10 == *(_QWORD *)(*a2 + 40) )
    std::vector<Spectre::Engine::ShaderOptionFilter>::_Emplace_reallocate<Spectre::Engine::ShaderOptionFilter const &>(
      v9,
      v10,
      &v20);
  else
    std::vector<D3D11_SUBRESOURCE_DATA>::_Emplace_back_with_unused_capacity<D3D11_SUBRESOURCE_DATA const &>(v9, &v20);
  if ( a5 )
  {
    v11 = *a2;
    v12 = std::string::string(v22, &qword_1801687B8);
    Spectre::Engine::ShaderPipeline::SetShaders(v11, v12);
  }
  v23 = *(_DWORD *)(a1 + 552);
  if ( !v23 )
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsNativeRenderer,
      2,
      "ShaderFamily::CreatePipeline() -- shaderModel is in invalid state. Pipeline creation must happen during a BeginSha"
      "derModel() / EndShaderModel() block.");
  v13 = (_QWORD *)(*(_QWORD *)std::map<enum Spectre::Engine::EShaderModel,Spectre::Engine::ShaderFamily::ShaderPipelineCollection>::_Try_emplace<enum Spectre::Engine::EShaderModel const &,>(
                                a1 + 416,
                                v22,
                                &v23)
                 + 40LL);
  if ( v13[1] == 0x7FFFFFFFFFFFFFFLL )
    std::_Xlength_error("list too long");
  v20 = v13;
  v21 = 0;
  v14 = *v13;
  v15 = std::_Allocate<16,std::_Default_allocate_traits>(32);
  std::_Default_allocator_traits<std::allocator<std::_List_node<std::shared_ptr<Spectre::Engine::ShaderPipeline>,void *>>>::construct<std::shared_ptr<Spectre::Engine::ShaderPipeline>,std::shared_ptr<Spectre::Engine::ShaderPipeline> const &>(
    v16,
    v15 + 16,
    a2,
    v15,
    1);
  ++v13[1];
  v17 = *(_QWORD **)(v14 + 8);
  *v18 = v14;
  v18[1] = v17;
  v21 = 0;
  *(_QWORD *)(v14 + 8) = v18;
  *v17 = v18;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Spectre::Engine::ShaderPipeline>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Spectre::Engine::ShaderPipeline>,void *>>>(&v20);
  return a2;
}

```

## disassembly

```asm
0x18005b014  mov     [rsp-28h+arg_8], rdx
0x18005b019  push    rbp
0x18005b01a  push    rbx
0x18005b01b  push    rsi
0x18005b01c  push    rdi
0x18005b01d  push    r14
0x18005b01f  mov     rbp, rsp
0x18005b022  sub     rsp, 60h
0x18005b026  mov     rdi, r9
0x18005b029  mov     rbx, r8
0x18005b02c  mov     rsi, rdx
0x18005b02f  mov     r14, rcx
0x18005b032  mov     [rbp+var_40], 0
0x18005b039  mov     rdx, rcx
0x18005b03c  mov     rcx, rsi
0x18005b03f  call    ??$make_shared@VShaderPipeline@Engine@Spectre@@AEAVShaderFamily@23@@std@@YA?AV?$shared_ptr@VShaderPipeline@Engine@Spectre@@@0@AEAVShaderFamily@Engine@Spectre@@@Z; std::make_shared<Spectre::Engine::ShaderPipeline,Spectre::Engine::ShaderFamily &>(Spectre::Engine::ShaderFamily &)
0x18005b044  mov     [rbp+var_40], 1
0x18005b04b  mov     [rbp+var_30], rbx
0x18005b04f  mov     [rbp+var_28], rdi
0x18005b053  mov     rcx, [rsi]
0x18005b056  add     rcx, 18h
0x18005b05a  mov     rdx, [rcx+8]
0x18005b05e  cmp     rdx, [rcx+10h]
0x18005b062  jz      short loc_18005B06F
0x18005b064  lea     rdx, [rbp+var_30]
0x18005b068  call    ??$_Emplace_back_with_unused_capacity@AEBUD3D11_SUBRESOURCE_DATA@@@?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@std@@AEAAAEAUD3D11_SUBRESOURCE_DATA@@AEBU2@@Z; std::vector<D3D11_SUBRESOURCE_DATA>::_Emplace_back_with_unused_capacity<D3D11_SUBRESOURCE_DATA const &>(D3D11_SUBRESOURCE_DATA const &)
0x18005b06d  jmp     short loc_18005B078
0x18005b06f  lea     r8, [rbp+var_30]
0x18005b073  call    ??$_Emplace_reallocate@AEBVShaderOptionFilter@Engine@Spectre@@@?$vector@VShaderOptionFilter@Engine@Spectre@@V?$allocator@VShaderOptionFilter@Engine@Spectre@@@std@@@std@@AEAAPEAVShaderOptionFilter@Engine@Spectre@@QEAV234@AEBV234@@Z; std::vector<Spectre::Engine::ShaderOptionFilter>::_Emplace_reallocate<Spectre::Engine::ShaderOptionFilter const &>(Spectre::Engine::ShaderOptionFilter * const,Spectre::Engine::ShaderOptionFilter const &)
0x18005b078  cmp     [rbp+arg_20], 0
0x18005b07c  jz      short loc_18005B09C
0x18005b07e  mov     rbx, [rsi]
0x18005b081  lea     rdx, qword_1801687B8
0x18005b088  lea     rcx, [rbp+var_20]
0x18005b08c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005b091  mov     rdx, rax
0x18005b094  mov     rcx, rbx
0x18005b097  call    ?SetShaders@ShaderPipeline@Engine@Spectre@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::ShaderPipeline::SetShaders(std::string)
0x18005b09c  mov     eax, [r14+228h]
0x18005b0a3  mov     [rbp+arg_0], eax
0x18005b0a6  test    eax, eax
0x18005b0a8  jnz     short loc_18005B0C0
0x18005b0aa  lea     r8, aShaderfamilyCr; "ShaderFamily::CreatePipeline() -- shade"...
0x18005b0b1  lea     edx, [rax+2]
0x18005b0b4  lea     rcx, ?gTraceLevelsNativeRenderer@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer
0x18005b0bb  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x18005b0c0  lea     rcx, [r14+1A0h]
0x18005b0c7  lea     r8, [rbp+arg_0]
0x18005b0cb  lea     rdx, [rbp+var_20]
0x18005b0cf  call    ??$_Try_emplace@AEBW4EShaderModel@Engine@Spectre@@$$V@?$map@W4EShaderModel@Engine@Spectre@@UShaderPipelineCollection@ShaderFamily@23@U?$less@W4EShaderModel@Engine@Spectre@@@std@@V?$allocator@U?$pair@$$CBW4EShaderModel@Engine@Spectre@@UShaderPipelineCollection@ShaderFamily@23@@std@@@7@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4EShaderModel@Engine@Spectre@@UShaderPipelineCollection@ShaderFamily@23@@std@@PEAX@std@@_N@1@AEBW4EShaderModel@Engine@Spectre@@@Z; std::map<Spectre::Engine::EShaderModel,Spectre::Engine::ShaderFamily::ShaderPipelineCollection>::_Try_emplace<Spectre::Engine::EShaderModel const &,>(Spectre::Engine::EShaderModel const &)
0x18005b0d4  mov     rdi, [rax]
0x18005b0d7  add     rdi, 28h ; '('
0x18005b0db  mov     rax, 7FFFFFFFFFFFFFFh
0x18005b0e5  cmp     [rdi+8], rax
0x18005b0e9  jnz     short loc_18005B0F9
0x18005b0eb  lea     rcx, aListTooLong; "list too long"
0x18005b0f2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18005b0f9  mov     [rbp+var_30], rdi
0x18005b0fd  mov     [rbp+var_28], 0
0x18005b105  mov     rbx, [rdi]
0x18005b108  mov     ecx, 20h ; ' '
0x18005b10d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005b112  mov     r9, rax
0x18005b115  lea     rdx, [rax+10h]
0x18005b119  mov     r8, rsi
0x18005b11c  call    ??$construct@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@PEAX@std@@@1@QEAV?$shared_ptr@VShaderPipeline@Engine@Spectre@@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::shared_ptr<Spectre::Engine::ShaderPipeline>,void *>>>::construct<std::shared_ptr<Spectre::Engine::ShaderPipeline>,std::shared_ptr<Spectre::Engine::ShaderPipeline> const &>(std::allocator<std::_List_node<std::shared_ptr<Spectre::Engine::ShaderPipeline>,void *>> &,std::shared_ptr<Spectre::Engine::ShaderPipeline> * const,std::shared_ptr<Spectre::Engine::ShaderPipeline> const &)
0x18005b121  nop
0x18005b122  inc     qword ptr [rdi+8]
0x18005b126  mov     rcx, [rbx+8]
0x18005b12a  mov     [r9], rbx
0x18005b12d  mov     [r9+8], rcx
0x18005b131  mov     [rbp+var_28], 0
0x18005b139  mov     [rbx+8], r9
0x18005b13d  mov     [rcx], r9
0x18005b140  lea     rcx, [rbp+var_30]
0x18005b144  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Spectre::Engine::ShaderPipeline>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Spectre::Engine::ShaderPipeline>,void *>>>(void)
0x18005b149  mov     rax, rsi
0x18005b14c  add     rsp, 60h
0x18005b150  pop     r14
0x18005b152  pop     rdi
0x18005b153  pop     rsi
0x18005b154  pop     rbx
0x18005b155  pop     rbp
0x18005b156  retn
```
