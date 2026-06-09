# Spectre::Engine::Scene::CreateLayer(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x18003e32c`
- end: `0x18003e5a1`
- name: `?CreateLayer@Scene@Engine@Spectre@@QEAA?AV?$shared_ptr@VSceneLayer@Engine@Spectre@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18003ed98`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012ba8`
- `0x180012df8`
- `0x180013568`
- `0x1800142d0`
- `0x180014554`
- `0x18001c290`
- `0x18001c630`
- `0x18001c6e0`
- `0x18002921c`
- `0x18002c8dc`
- `0x180038ddc`
- `0x18003bf44`
- `0x18003cd50`
- `0x18003cd8c`
- `0x18003e32c`
- `0x18003e640`
- `0x18003eaac`
- `0x18003f2a8`

## string_xrefs

- `0x18003e3e2`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003e3cc`: ` already exists`
- `0x18003e3ba`: `Scene::CreateLayer() - a layer with ID `

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall Spectre::Engine::Scene::CreateLayer(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ebx
  int v11; // eax
  int v12; // r8d
  __int64 v13; // rax
  Spectre::Engine::SceneNode *v14; // rdi
  _DWORD *v15; // rax
  _DWORD *v16; // rbx
  __int64 *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rax
  std::_Ref_count_base *v20; // rax
  std::_Ref_count_base *v21; // rcx
  __int64 v22; // rax
  _BYTE v24[32]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  Spectre::Engine::SceneNode *v27; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v28; // [rsp+78h] [rbp-88h]
  _BYTE v29[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[32]; // [rsp+108h] [rbp+8h] BYREF

  v25 = a2;
  v26 = a3;
  Spectre::Engine::Lockable::VerifyWriteAccess((Spectre::Engine::Lockable *)(a1 + 16));
  v6 = std::wstring::wstring(v24, a3);
  v7 = *(_QWORD *)Spectre::Engine::Scene::GetLayer(a1, &v27, v6);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  if ( v7 )
  {
    v8 = Spectre::Utils::LexicalCast<std::string,std::wstring>(v30, a3);
    v9 = std::operator+<char>(&v27, "Scene::CreateLayer() - a layer with ID ", v8);
    v10 = std::operator+<char>(v32, v9, " already exists");
    v11 = std::string::string(
            v24,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v11,
      v12,
      v10,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  Spectre::Engine::Scene::CreateNodeInternal(a1, &v27, &Spectre::Engine::Scene::RootNodeID);
  v13 = Spectre::Utils::LexicalCast<std::string,std::wstring>(v30, a3);
  std::operator+<char>(v29, "LayerRoot:", v13);
  std::string::_Tidy_deallocate(v30);
  v14 = v27;
  std::string::operator=((char *)v27 + 400, v29);
  v15 = operator new(0x78u);
  v16 = v15;
  if ( v15 )
  {
    *(_OWORD *)v15 = 0;
    v15[2] = 1;
    v15[3] = 1;
    *(_QWORD *)v15 = &std::_Ref_count_obj2<Spectre::Engine::SceneLayer>::`vftable';
    std::_Construct_in_place<Spectre::Engine::SceneLayer,std::wstring &,std::shared_ptr<Spectre::Engine::SceneNode> &>(
      v15 + 4,
      a3,
      &v27);
    v14 = v27;
  }
  else
  {
    v16 = 0;
  }
  *a2 = v16 + 4;
  a2[1] = v16;
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Spectre::Engine::SceneLayer>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Spectre::Engine::SceneLayer>>>,0>>::_Emplace<std::wstring &,std::shared_ptr<Spectre::Engine::SceneLayer> &>(
    a1 + 88,
    v24,
    a3,
    a2);
  v17 = (__int64 *)std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
                     v24,
                     a2);
  Spectre::Engine::SceneNode::VerifyWriteAccess(v14);
  v18 = v17[1];
  if ( v18 )
  {
    v19 = *v17;
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 12));
  }
  else
  {
    v19 = 0;
    v18 = 0;
  }
  *((_QWORD *)v14 + 11) = v19;
  v20 = (std::_Ref_count_base *)*((_QWORD *)v14 + 12);
  *((_QWORD *)v14 + 12) = v18;
  if ( v20 )
    std::_Ref_count_base::_Decwref(v20);
  v21 = (std::_Ref_count_base *)v17[1];
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  v22 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          v24,
          &v27);
  Spectre::Engine::Scene::RegisterNode(a1, v22);
  std::string::_Tidy_deallocate(v29);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  std::wstring::_Tidy_deallocate(a3);
  return a2;
}

```

## disassembly

```asm
0x18003e32c  mov     [rsp-8+arg_18], rbx
0x18003e331  push    rbp
0x18003e332  push    rsi
0x18003e333  push    rdi
0x18003e334  push    r14
0x18003e336  push    r15
0x18003e338  lea     rbp, [rsp-30h]
0x18003e33d  sub     rsp, 130h
0x18003e344  mov     rax, cs:__security_cookie
0x18003e34b  xor     rax, rsp
0x18003e34e  mov     [rbp+50h+var_28], rax
0x18003e352  mov     rsi, r8
0x18003e355  mov     r14, rdx
0x18003e358  mov     r15, rcx
0x18003e35b  mov     [rsp+150h+var_F0], rdx
0x18003e360  mov     [rsp+150h+var_E8], r8
0x18003e365  mov     [rsp+150h+var_118], 0
0x18003e36d  add     rcx, 10h; this
0x18003e371  call    ?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ; Spectre::Engine::Lockable::VerifyWriteAccess(void)
0x18003e376  mov     rdx, rsi
0x18003e379  lea     rcx, [rsp+150h+var_110]
0x18003e37e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003e383  mov     r8, rax
0x18003e386  lea     rdx, [rsp+150h+var_E0]
0x18003e38b  mov     rcx, r15
0x18003e38e  call    ?GetLayer@Scene@Engine@Spectre@@QEBA?AV?$shared_ptr@VSceneLayer@Engine@Spectre@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Spectre::Engine::Scene::GetLayer(std::wstring)
0x18003e393  mov     rbx, [rax]
0x18003e396  mov     rcx, [rsp+150h+var_D8]; this
0x18003e39b  test    rcx, rcx
0x18003e39e  jz      short loc_18003E3A5
0x18003e3a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e3a5  test    rbx, rbx
0x18003e3a8  jz      short loc_18003E418
0x18003e3aa  mov     rdx, rsi
0x18003e3ad  lea     rcx, [rbp+50h+var_A0]
0x18003e3b1  call    ??$LexicalCast@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Utils@Spectre@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Spectre::Utils::LexicalCast<std::string,std::wstring>(std::wstring const &)
0x18003e3b6  nop
0x18003e3b7  mov     r8, rax
0x18003e3ba  lea     rdx, aSceneCreatelay; "Scene::CreateLayer() - a layer with ID "
0x18003e3c1  lea     rcx, [rsp+150h+var_E0]
0x18003e3c6  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18003e3cb  nop
0x18003e3cc  lea     r8, aAlreadyExists; " already exists"
0x18003e3d3  mov     rdx, rax
0x18003e3d6  lea     rcx, [rbp+50h+var_48]
0x18003e3da  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18003e3df  mov     rbx, rax
0x18003e3e2  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003e3e9  lea     rcx, [rsp+150h+var_110]
0x18003e3ee  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e3f3  mov     [rsp+150h+var_130], 0
0x18003e3f8  mov     r9, rbx
0x18003e3fb  mov     rdx, rax
0x18003e3fe  lea     rcx, [rbp+50h+pExceptionObject]
0x18003e402  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003e407  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003e40e  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x18003e412  call    _CxxThrowException_0
0x18003e418  lea     r8, ?RootNodeID@Scene@Engine@Spectre@@2_KB; unsigned __int64 const Spectre::Engine::Scene::RootNodeID
0x18003e41f  lea     rdx, [rsp+150h+var_E0]
0x18003e424  mov     rcx, r15
0x18003e427  call    ?CreateNodeInternal@Scene@Engine@Spectre@@AEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@AEB_K@Z; Spectre::Engine::Scene::CreateNodeInternal(unsigned __int64 const &)
0x18003e42c  nop
0x18003e42d  mov     rdx, rsi
0x18003e430  lea     rcx, [rbp+50h+var_A0]
0x18003e434  call    ??$LexicalCast@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Utils@Spectre@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Spectre::Utils::LexicalCast<std::string,std::wstring>(std::wstring const &)
0x18003e439  nop
0x18003e43a  mov     r8, rax
0x18003e43d  lea     rdx, aLayerroot; "LayerRoot:"
0x18003e444  lea     rcx, [rbp+50h+var_C0]
0x18003e448  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18003e44d  nop
0x18003e44e  lea     rcx, [rbp+50h+var_A0]
0x18003e452  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003e457  mov     rdi, [rsp+150h+var_E0]
0x18003e45c  lea     rcx, [rdi+190h]
0x18003e463  lea     rdx, [rbp+50h+var_C0]
0x18003e467  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x18003e46c  mov     ecx, 78h ; 'x'; unsigned __int64
0x18003e471  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e476  mov     rbx, rax
0x18003e479  mov     [rsp+150h+var_120], rax
0x18003e47e  test    rax, rax
0x18003e481  jz      short loc_18003E4B9
0x18003e483  xorps   xmm0, xmm0
0x18003e486  movups  xmmword ptr [rax], xmm0
0x18003e489  mov     dword ptr [rax+8], 1
0x18003e490  mov     dword ptr [rax+0Ch], 1
0x18003e497  lea     rax, ??_7?$_Ref_count_obj2@VSceneLayer@Engine@Spectre@@@std@@6B@; const std::_Ref_count_obj2<Spectre::Engine::SceneLayer>::`vftable'
0x18003e49e  mov     [rbx], rax
0x18003e4a1  lea     rcx, [rbx+10h]
0x18003e4a5  lea     r8, [rsp+150h+var_E0]
0x18003e4aa  mov     rdx, rsi
0x18003e4ad  call    ??$_Construct_in_place@VSceneLayer@Engine@Spectre@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VSceneNode@Engine@Spectre@@@5@@std@@YAXAEAVSceneLayer@Engine@Spectre@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAV?$shared_ptr@VSceneNode@Engine@Spectre@@@0@@Z; std::_Construct_in_place<Spectre::Engine::SceneLayer,std::wstring &,std::shared_ptr<Spectre::Engine::SceneNode> &>(Spectre::Engine::SceneLayer &,std::wstring &,std::shared_ptr<Spectre::Engine::SceneNode> &)
0x18003e4b2  mov     rdi, [rsp+150h+var_E0]
0x18003e4b7  jmp     short loc_18003E4BB
0x18003e4b9  xor     ebx, ebx
0x18003e4bb  lea     rax, [rbx+10h]
0x18003e4bf  mov     [r14], rax
0x18003e4c2  mov     [r14+8], rbx
0x18003e4c6  mov     [rsp+150h+var_118], 3
0x18003e4ce  lea     rcx, [r15+58h]
0x18003e4d2  mov     r9, r14
0x18003e4d5  mov     r8, rsi
0x18003e4d8  lea     rdx, [rsp+150h+var_110]
0x18003e4dd  call    ??$_Emplace@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VSceneLayer@Engine@Spectre@@@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VSceneLayer@Engine@Spectre@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VSceneLayer@Engine@Spectre@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VSceneLayer@Engine@Spectre@@@2@@std@@PEAX@std@@_N@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAV?$shared_ptr@VSceneLayer@Engine@Spectre@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Spectre::Engine::SceneLayer>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Spectre::Engine::SceneLayer>>>,0>>::_Emplace<std::wstring &,std::shared_ptr<Spectre::Engine::SceneLayer> &>(std::wstring &,std::shared_ptr<Spectre::Engine::SceneLayer> &)
0x18003e4e2  mov     rdx, r14
0x18003e4e5  lea     rcx, [rsp+150h+var_110]
0x18003e4ea  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003e4ef  mov     rbx, rax
0x18003e4f2  mov     [rsp+150h+var_120], rax
0x18003e4f7  mov     rcx, rdi; this
0x18003e4fa  call    ?VerifyWriteAccess@SceneNode@Engine@Spectre@@QEBAXXZ; Spectre::Engine::SceneNode::VerifyWriteAccess(void)
0x18003e4ff  mov     rcx, [rbx+8]
0x18003e503  test    rcx, rcx
0x18003e506  jz      short loc_18003E511
0x18003e508  mov     rax, [rbx]
0x18003e50b  lock inc dword ptr [rcx+0Ch]
0x18003e50f  jmp     short loc_18003E515
0x18003e511  xor     eax, eax
0x18003e513  xor     ecx, ecx
0x18003e515  mov     [rdi+58h], rax
0x18003e519  mov     rax, [rdi+60h]
0x18003e51d  mov     [rdi+60h], rcx
0x18003e521  test    rax, rax
0x18003e524  jz      short loc_18003E52F
0x18003e526  mov     rcx, rax; this
0x18003e529  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18003e52e  nop
0x18003e52f  mov     rcx, [rbx+8]; this
0x18003e533  test    rcx, rcx
0x18003e536  jz      short loc_18003E53D
0x18003e538  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e53d  lea     rdx, [rsp+150h+var_E0]
0x18003e542  lea     rcx, [rsp+150h+var_110]
0x18003e547  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003e54c  mov     rdx, rax
0x18003e54f  mov     rcx, r15
0x18003e552  call    ?RegisterNode@Scene@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::Scene::RegisterNode(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003e557  nop
0x18003e558  lea     rcx, [rbp+50h+var_C0]
0x18003e55c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003e561  nop
0x18003e562  mov     rcx, [rsp+150h+var_D8]; this
0x18003e567  test    rcx, rcx
0x18003e56a  jz      short loc_18003E572
0x18003e56c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e571  nop
0x18003e572  mov     rcx, rsi
0x18003e575  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e57a  mov     rax, r14
0x18003e57d  mov     rcx, [rbp+50h+var_28]
0x18003e581  xor     rcx, rsp; StackCookie
0x18003e584  call    __security_check_cookie
0x18003e589  mov     rbx, [rsp+150h+arg_18]
0x18003e591  add     rsp, 130h
0x18003e598  pop     r15
0x18003e59a  pop     r14
0x18003e59c  pop     rdi
0x18003e59d  pop     rsi
0x18003e59e  pop     rbp
0x18003e59f  retn
```
