# Spectre::Engine::Scene::SetNodeParent(std::shared_ptr<Spectre::Engine::SceneNode>,std::shared_ptr<Spectre::Engine::SceneNode>)

- ea: `0x18003f82c`
- end: `0x18003fa03`
- name: `?SetNodeParent@Scene@Engine@Spectre@@QEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@0@Z`
- size: `471`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013b20`
- `0x180015ec0`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012df8`
- `0x180013798`
- `0x180038ddc`
- `0x18003eec8`
- `0x18003f428`
- `0x18003f82c`

## string_xrefs

- `0x18003f87a`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f8c9`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f94f`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f8b8`: `Scene::SetNodeParent() - new parent must not be null  (to remove a node from the scene graph use RemoveNode() instead`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Spectre::Engine::Scene::SetNodeParent(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  int v6; // eax
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  __int64 v10; // rsi
  __int64 *v11; // r11
  __int64 v12; // r14
  int v13; // eax
  int v14; // r8d
  Spectre::Engine::SceneNode **v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r8
  std::_Ref_count_base *v18; // rcx
  std::_Ref_count_base *v19; // rcx
  _BYTE v20[8]; // [rsp+30h] [rbp-69h] BYREF
  std::_Ref_count_base *v21; // [rsp+38h] [rbp-61h]
  _BYTE v22[32]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD *v23; // [rsp+60h] [rbp-39h]
  _QWORD *v24; // [rsp+68h] [rbp-31h]
  _BYTE v25[8]; // [rsp+70h] [rbp-29h] BYREF
  std::_Ref_count_base *v26; // [rsp+78h] [rbp-21h]
  _BYTE pExceptionObject[56]; // [rsp+90h] [rbp-9h] BYREF

  v23 = a2;
  v24 = a3;
  if ( !*a2 )
  {
    std::string::string(v25, "Scene::SetNodeParent() - node must not be null");
    v6 = std::string::string(
           v22,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v6,
      v7,
      (unsigned int)v25,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( !*a3 )
  {
    std::string::string(
      v25,
      "Scene::SetNodeParent() - new parent must not be null  (to remove a node from the scene graph use RemoveNode() instead");
    v8 = std::string::string(
           v22,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v8,
      v9,
      (unsigned int)v25,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  Spectre::Engine::SceneNode::GetScene(*a3, v25);
  v10 = *(_QWORD *)Spectre::Engine::SceneNode::GetScene(*a2, v20);
  v12 = *v11;
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  if ( v10 != v12 )
  {
    std::string::string(v25, "Scene::SetNodeParent() - both nodes must belong to the same scene");
    v13 = std::string::string(
            v22,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v13,
      v14,
      (unsigned int)v25,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v15 = (Spectre::Engine::SceneNode **)std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
                                         v25,
                                         a2);
  Spectre::Engine::Scene::RemoveNode(a1, v15);
  std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v25, a3);
  v16 = (_QWORD *)std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
                    v22,
                    a2);
  Spectre::Engine::Scene::InsertNode(a1, v16, v17);
  v18 = (std::_Ref_count_base *)a2[1];
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v19 = (std::_Ref_count_base *)a3[1];
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
}

```

## disassembly

```asm
0x18003f82c  mov     [rsp-8+arg_18], rbx
0x18003f831  push    rbp
0x18003f832  push    rsi
0x18003f833  push    rdi
0x18003f834  push    r14
0x18003f836  push    r15
0x18003f838  lea     rbp, [rsp-37h]
0x18003f83d  sub     rsp, 0D0h
0x18003f844  mov     rax, cs:__security_cookie
0x18003f84b  xor     rax, rsp
0x18003f84e  mov     [rbp+57h+var_28], rax
0x18003f852  mov     rbx, r8
0x18003f855  mov     rdi, rdx
0x18003f858  mov     r15, rcx
0x18003f85b  mov     [rbp+57h+var_90], rdx
0x18003f85f  mov     [rbp+57h+var_88], rbx
0x18003f863  cmp     qword ptr [rdx], 0
0x18003f867  jnz     short loc_18003F8B0
0x18003f869  lea     rdx, aSceneSetnodepa; "Scene::SetNodeParent() - node must not "...
0x18003f870  lea     rcx, [rbp+57h+var_80]
0x18003f874  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f879  nop
0x18003f87a  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f881  lea     rcx, [rbp+57h+var_B0]
0x18003f885  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f88a  mov     [rsp+0F0h+var_D0], 0
0x18003f88f  lea     r9, [rbp+57h+var_80]
0x18003f893  mov     rdx, rax
0x18003f896  lea     rcx, [rbp+57h+pExceptionObject]
0x18003f89a  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f89f  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f8a6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003f8aa  call    _CxxThrowException_0
0x18003f8b0  mov     rcx, [r8]
0x18003f8b3  test    rcx, rcx
0x18003f8b6  jnz     short loc_18003F8FF
0x18003f8b8  lea     rdx, aSceneSetnodepa_0; "Scene::SetNodeParent() - new parent mus"...
0x18003f8bf  lea     rcx, [rbp+57h+var_80]
0x18003f8c3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f8c8  nop
0x18003f8c9  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f8d0  lea     rcx, [rbp+57h+var_B0]
0x18003f8d4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f8d9  mov     [rsp+0F0h+var_D0], 0
0x18003f8de  lea     r9, [rbp+57h+var_80]
0x18003f8e2  mov     rdx, rax
0x18003f8e5  lea     rcx, [rbp+57h+pExceptionObject]
0x18003f8e9  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f8ee  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f8f5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003f8f9  call    _CxxThrowException_0
0x18003f8ff  lea     rdx, [rbp+57h+var_80]
0x18003f903  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x18003f908  mov     r11, rax
0x18003f90b  lea     rdx, [rbp+57h+var_C0]
0x18003f90f  mov     rcx, [rdi]
0x18003f912  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x18003f917  mov     rsi, [rax]
0x18003f91a  mov     r14, [r11]
0x18003f91d  mov     rcx, [rbp+57h+var_B8]; this
0x18003f921  test    rcx, rcx
0x18003f924  jz      short loc_18003F92B
0x18003f926  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f92b  mov     rcx, [rbp+57h+var_78]; this
0x18003f92f  test    rcx, rcx
0x18003f932  jz      short loc_18003F939
0x18003f934  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f939  cmp     rsi, r14
0x18003f93c  jz      short loc_18003F985
0x18003f93e  lea     rdx, aSceneSetnodepa_1; "Scene::SetNodeParent() - both nodes mus"...
0x18003f945  lea     rcx, [rbp+57h+var_80]
0x18003f949  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f94e  nop
0x18003f94f  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f956  lea     rcx, [rbp+57h+var_B0]
0x18003f95a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f95f  mov     [rsp+0F0h+var_D0], 0
0x18003f964  lea     r9, [rbp+57h+var_80]
0x18003f968  mov     rdx, rax
0x18003f96b  lea     rcx, [rbp+57h+pExceptionObject]
0x18003f96f  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f974  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f97b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003f97f  call    _CxxThrowException_0
0x18003f985  mov     rdx, rdi
0x18003f988  lea     rcx, [rbp+57h+var_80]
0x18003f98c  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003f991  mov     rdx, rax
0x18003f994  mov     rcx, r15
0x18003f997  call    ?RemoveNode@Scene@Engine@Spectre@@QEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::Scene::RemoveNode(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f99c  mov     rdx, rbx
0x18003f99f  lea     rcx, [rbp+57h+var_80]
0x18003f9a3  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003f9a8  mov     r8, rax
0x18003f9ab  mov     rdx, rdi
0x18003f9ae  lea     rcx, [rbp+57h+var_B0]
0x18003f9b2  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003f9b7  mov     rdx, rax
0x18003f9ba  mov     rcx, r15
0x18003f9bd  call    ?InsertNode@Scene@Engine@Spectre@@QEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@0@Z; Spectre::Engine::Scene::InsertNode(std::shared_ptr<Spectre::Engine::SceneNode>,std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f9c2  nop
0x18003f9c3  mov     rcx, [rdi+8]; this
0x18003f9c7  test    rcx, rcx
0x18003f9ca  jz      short loc_18003F9D2
0x18003f9cc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f9d1  nop
0x18003f9d2  mov     rcx, [rbx+8]; this
0x18003f9d6  test    rcx, rcx
0x18003f9d9  jz      short loc_18003F9E0
0x18003f9db  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f9e0  mov     rcx, [rbp+57h+var_28]
0x18003f9e4  xor     rcx, rsp; StackCookie
0x18003f9e7  call    __security_check_cookie
0x18003f9ec  mov     rbx, [rsp+0F0h+arg_18]
0x18003f9f4  add     rsp, 0D0h
0x18003f9fb  pop     r15
0x18003f9fd  pop     r14
0x18003f9ff  pop     rdi
0x18003fa00  pop     rsi
0x18003fa01  pop     rbp
0x18003fa02  retn
```
