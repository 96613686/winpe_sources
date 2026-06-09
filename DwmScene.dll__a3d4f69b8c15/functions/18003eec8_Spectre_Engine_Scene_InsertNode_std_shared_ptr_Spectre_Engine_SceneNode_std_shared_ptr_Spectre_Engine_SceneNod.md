# Spectre::Engine::Scene::InsertNode(std::shared_ptr<Spectre::Engine::SceneNode>,std::shared_ptr<Spectre::Engine::SceneNode>)

- ea: `0x18003eec8`
- end: `0x18003f18a`
- name: `?InsertNode@Scene@Engine@Spectre@@QEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@0@Z`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f82c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012df8`
- `0x180013760`
- `0x180013798`
- `0x18002921c`
- `0x180037480`
- `0x180038ddc`
- `0x18003b1d0`
- `0x18003eb80`
- `0x18003eec8`

## string_xrefs

- `0x18003ef13`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003ef61`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003efca`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f055`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003ef50`: `Scene::InsertNode() - new parent must not be null (to remove a node from the scene graph use RemoveNode() instead`
- `0x18003efb9`: `Scene::InsertNode() - node must not be already attached to a scene (to insert this node into the parents scene use RemoveNode() first`
- `0x18003f044`: `Scene::InsertNode() - the node must not already be in a layer.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Spectre::Engine::Scene::InsertNode(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  int v6; // eax
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  __int64 v10; // r14
  int v11; // eax
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  int v16; // r8d
  volatile __int32 *v17; // rbx
  __int64 v18; // r14
  Spectre::Engine::SceneNode *v19; // r8
  __int64 v20; // rdx
  Spectre::Engine::SceneNode *v21; // r8
  std::_Ref_count_base *v22; // rcx
  std::_Ref_count_base *v23; // rcx
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v27; // [rsp+68h] [rbp-98h]
  _QWORD *v28; // [rsp+80h] [rbp-80h]
  _QWORD *v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v31; // [rsp+98h] [rbp-68h]
  _BYTE pExceptionObject[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[56]; // [rsp+E8h] [rbp-18h] BYREF

  v28 = a2;
  v29 = a3;
  if ( !*a2 )
  {
    std::string::string(&v30, "Scene::InsertNode() - node must not be null");
    v6 = std::string::string(
           &v26,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v6,
      v7,
      (unsigned int)&v30,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( !*a3 )
  {
    std::string::string(
      &v30,
      "Scene::InsertNode() - new parent must not be null (to remove a node from the scene graph use RemoveNode() instead");
    v8 = std::string::string(
           &v26,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v8,
      v9,
      (unsigned int)&v30,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v10 = *(_QWORD *)Spectre::Engine::SceneNode::GetScene(*a2, &v26);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  if ( v10 )
  {
    std::string::string(
      &v30,
      "Scene::InsertNode() - node must not be already attached to a scene (to insert this node into the parents scene use"
      " RemoveNode() first");
    v11 = std::string::string(
            &v26,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v11,
      v12,
      (unsigned int)&v30,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v13 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v25, a2);
  Spectre::Engine::Scene::GetNodeLayer(a1, &v26, v13);
  v14 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          &v24,
          a3);
  Spectre::Engine::Scene::GetNodeLayer(a1, &v30, v14);
  if ( v26 )
  {
    std::string::string(pExceptionObject, "Scene::InsertNode() - the node must not already be in a layer.");
    v15 = std::string::string(
            v25,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)v33,
      v15,
      v16,
      (unsigned int)pExceptionObject,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)v33;
  }
  Spectre::Engine::Lockable::VerifyWriteAccess((Spectre::Engine::Lockable *)(a1 + 16));
  if ( v30 )
  {
    v17 = (volatile __int32 *)(v30 + 76);
    v24 = v30 + 76;
    while ( _InterlockedExchange(v17, 1) )
      ;
    v18 = *(_QWORD *)Spectre::Engine::SceneNode::GetParent(*a2, v25);
    if ( v25[1] )
      std::_Ref_count_base::_Decref(v25[1]);
    if ( v18 )
    {
      *(_OWORD *)v25 = 0;
      Spectre::Engine::SceneNode::SetParent((Spectre::Engine::SceneNode *)*a2);
    }
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v25, a3);
    Spectre::Engine::SceneNode::SetParent(v19);
    std::_Atomic_storage<long,4>::store(v17, v20, 3);
  }
  else
  {
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v25, a3);
    Spectre::Engine::SceneNode::SetParent(v21);
  }
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  v22 = (std::_Ref_count_base *)a2[1];
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  v23 = (std::_Ref_count_base *)a3[1];
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
}

```

## disassembly

```asm
0x18003eec8  push    rbp
0x18003eeca  push    rbx
0x18003eecb  push    rsi
0x18003eecc  push    rdi
0x18003eecd  push    r14
0x18003eecf  lea     rbp, [rsp-30h]
0x18003eed4  sub     rsp, 130h
0x18003eedb  mov     rax, cs:__security_cookie
0x18003eee2  xor     rax, rsp
0x18003eee5  mov     [rbp+50h+var_30], rax
0x18003eee9  mov     rsi, r8
0x18003eeec  mov     rdi, rdx
0x18003eeef  mov     rbx, rcx
0x18003eef2  mov     [rbp+50h+var_D0], rdx
0x18003eef6  mov     [rbp+50h+var_C8], r8
0x18003eefa  mov     rcx, [rdx]
0x18003eefd  test    rcx, rcx
0x18003ef00  jnz     short loc_18003EF4A
0x18003ef02  lea     rdx, aSceneInsertnod_1; "Scene::InsertNode() - node must not be "...
0x18003ef09  lea     rcx, [rbp+50h+var_C0]
0x18003ef0d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003ef12  nop
0x18003ef13  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003ef1a  lea     rcx, [rsp+150h+var_F0]
0x18003ef1f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003ef24  mov     [rsp+150h+var_130], 0
0x18003ef29  lea     r9, [rbp+50h+var_C0]
0x18003ef2d  mov     rdx, rax
0x18003ef30  lea     rcx, [rbp+50h+pExceptionObject]
0x18003ef34  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003ef39  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003ef40  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x18003ef44  call    _CxxThrowException_0
0x18003ef4a  cmp     qword ptr [r8], 0
0x18003ef4e  jnz     short loc_18003EF98
0x18003ef50  lea     rdx, aSceneInsertnod; "Scene::InsertNode() - new parent must n"...
0x18003ef57  lea     rcx, [rbp+50h+var_C0]
0x18003ef5b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003ef60  nop
0x18003ef61  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003ef68  lea     rcx, [rsp+150h+var_F0]
0x18003ef6d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003ef72  mov     [rsp+150h+var_130], 0
0x18003ef77  lea     r9, [rbp+50h+var_C0]
0x18003ef7b  mov     rdx, rax
0x18003ef7e  lea     rcx, [rbp+50h+pExceptionObject]
0x18003ef82  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003ef87  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003ef8e  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x18003ef92  call    _CxxThrowException_0
0x18003ef98  lea     rdx, [rsp+150h+var_F0]
0x18003ef9d  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x18003efa2  mov     r14, [rax]
0x18003efa5  mov     rcx, [rsp+150h+var_E8]; this
0x18003efaa  test    rcx, rcx
0x18003efad  jz      short loc_18003EFB4
0x18003efaf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003efb4  test    r14, r14
0x18003efb7  jz      short loc_18003F001
0x18003efb9  lea     rdx, aSceneInsertnod_2; "Scene::InsertNode() - node must not be "...
0x18003efc0  lea     rcx, [rbp+50h+var_C0]
0x18003efc4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003efc9  nop
0x18003efca  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003efd1  lea     rcx, [rsp+150h+var_F0]
0x18003efd6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003efdb  mov     [rsp+150h+var_130], 0
0x18003efe0  lea     r9, [rbp+50h+var_C0]
0x18003efe4  mov     rdx, rax
0x18003efe7  lea     rcx, [rbp+50h+pExceptionObject]
0x18003efeb  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003eff0  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003eff7  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x18003effb  call    _CxxThrowException_0
0x18003f001  mov     rdx, rdi
0x18003f004  lea     rcx, [rsp+150h+var_110]
0x18003f009  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003f00e  mov     r8, rax
0x18003f011  lea     rdx, [rsp+150h+var_F0]
0x18003f016  mov     rcx, rbx
0x18003f019  call    ?GetNodeLayer@Scene@Engine@Spectre@@QEBA?AV?$shared_ptr@VSceneLayer@Engine@Spectre@@@std@@V?$shared_ptr@VSceneNode@Engine@Spectre@@@5@@Z; Spectre::Engine::Scene::GetNodeLayer(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f01e  nop
0x18003f01f  mov     rdx, rsi
0x18003f022  lea     rcx, [rsp+150h+var_120]
0x18003f027  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003f02c  mov     r8, rax
0x18003f02f  lea     rdx, [rbp+50h+var_C0]
0x18003f033  mov     rcx, rbx
0x18003f036  call    ?GetNodeLayer@Scene@Engine@Spectre@@QEBA?AV?$shared_ptr@VSceneLayer@Engine@Spectre@@@std@@V?$shared_ptr@VSceneNode@Engine@Spectre@@@5@@Z; Spectre::Engine::Scene::GetNodeLayer(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f03b  nop
0x18003f03c  cmp     [rsp+150h+var_F0], 0
0x18003f042  jz      short loc_18003F08C
0x18003f044  lea     rdx, aSceneInsertnod_0; "Scene::InsertNode() - the node must not"...
0x18003f04b  lea     rcx, [rbp+50h+pExceptionObject]
0x18003f04f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f054  nop
0x18003f055  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f05c  lea     rcx, [rsp+150h+var_110]
0x18003f061  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f066  mov     [rsp+150h+var_130], 0
0x18003f06b  lea     r9, [rbp+50h+pExceptionObject]
0x18003f06f  mov     rdx, rax
0x18003f072  lea     rcx, [rbp+50h+var_68]
0x18003f076  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f07b  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f082  lea     rcx, [rbp+50h+var_68]; pExceptionObject
0x18003f086  call    _CxxThrowException_0
0x18003f08c  lea     rcx, [rbx+10h]; this
0x18003f090  call    ?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ; Spectre::Engine::Lockable::VerifyWriteAccess(void)
0x18003f095  mov     rbx, [rbp+50h+var_C0]
0x18003f099  test    rbx, rbx
0x18003f09c  jz      short loc_18003F118
0x18003f09e  add     rbx, 4Ch ; 'L'
0x18003f0a2  mov     [rsp+150h+var_120], rbx
0x18003f0a7  mov     eax, 1
0x18003f0ac  xchg    eax, [rbx]
0x18003f0ae  test    eax, eax
0x18003f0b0  jnz     short loc_18003F0A7
0x18003f0b2  lea     rdx, [rsp+150h+var_110]
0x18003f0b7  mov     rcx, [rdi]
0x18003f0ba  call    ?GetParent@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetParent(void)
0x18003f0bf  mov     r14, [rax]
0x18003f0c2  mov     rcx, [rsp+150h+var_110+8]; this
0x18003f0c7  test    rcx, rcx
0x18003f0ca  jz      short loc_18003F0D1
0x18003f0cc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f0d1  test    r14, r14
0x18003f0d4  jz      short loc_18003F0EC
0x18003f0d6  xorps   xmm0, xmm0
0x18003f0d9  movdqu  xmmword ptr [rsp+150h+var_110], xmm0
0x18003f0df  lea     rdx, [rsp+150h+var_110]
0x18003f0e4  mov     rcx, [rdi]
0x18003f0e7  call    ?SetParent@SceneNode@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::SetParent(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f0ec  mov     r8, [rdi]
0x18003f0ef  mov     rdx, rsi
0x18003f0f2  lea     rcx, [rsp+150h+var_110]
0x18003f0f7  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003f0fc  mov     rdx, rax
0x18003f0ff  mov     rcx, r8
0x18003f102  call    ?SetParent@SceneNode@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::SetParent(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f107  nop
0x18003f108  mov     r8d, 3
0x18003f10e  mov     rcx, rbx
0x18003f111  call    ?store@?$_Atomic_storage@J$03@std@@QEAAXJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::store(long,std::memory_order)
0x18003f116  jmp     short loc_18003F134
0x18003f118  mov     r8, [rdi]
0x18003f11b  mov     rdx, rsi
0x18003f11e  lea     rcx, [rsp+150h+var_110]
0x18003f123  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003f128  mov     rdx, rax
0x18003f12b  mov     rcx, r8
0x18003f12e  call    ?SetParent@SceneNode@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::SetParent(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f133  nop
0x18003f134  mov     rcx, [rbp+50h+var_B8]; this
0x18003f138  test    rcx, rcx
0x18003f13b  jz      short loc_18003F143
0x18003f13d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f142  nop
0x18003f143  mov     rcx, [rsp+150h+var_E8]; this
0x18003f148  test    rcx, rcx
0x18003f14b  jz      short loc_18003F153
0x18003f14d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f152  nop
0x18003f153  mov     rcx, [rdi+8]; this
0x18003f157  test    rcx, rcx
0x18003f15a  jz      short loc_18003F162
0x18003f15c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f161  nop
0x18003f162  mov     rcx, [rsi+8]; this
0x18003f166  test    rcx, rcx
0x18003f169  jz      short loc_18003F170
0x18003f16b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f170  mov     rcx, [rbp+50h+var_30]
0x18003f174  xor     rcx, rsp; StackCookie
0x18003f177  call    __security_check_cookie
0x18003f17c  add     rsp, 130h
0x18003f183  pop     r14
0x18003f185  pop     rdi
0x18003f186  pop     rsi
0x18003f187  pop     rbx
0x18003f188  pop     rbp
0x18003f189  retn
```
