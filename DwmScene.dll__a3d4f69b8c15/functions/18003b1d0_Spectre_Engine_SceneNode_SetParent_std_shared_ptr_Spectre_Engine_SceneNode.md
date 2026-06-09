# Spectre::Engine::SceneNode::SetParent(std::shared_ptr<Spectre::Engine::SceneNode>)

- ea: `0x18003b1d0`
- end: `0x18003b533`
- name: `?SetParent@SceneNode@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z`
- size: `867`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039294`
- `0x18003dffc`
- `0x18003eec8`
- `0x18003f428`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x180012d98`
- `0x180012df8`
- `0x180013760`
- `0x180013798`
- `0x1800293c0`
- `0x180038ddc`
- `0x1800396ac`
- `0x18003a0c0`
- `0x18003aea0`
- `0x18003b1d0`
- `0x18003bbf8`
- `0x18003bcac`
- `0x18003bd40`
- `0x18003bf44`
- `0x18003e6e0`
- `0x18003f2a8`

## string_xrefs

- `0x18003b230`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scenenode.cpp`
- `0x18003b298`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scenenode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Spectre::Engine::SceneNode::SetParent(Spectre::Engine::SceneNode *this, _QWORD *a2)
{
  int v4; // eax
  int v5; // r8d
  __int64 v6; // rax
  int v7; // eax
  int v8; // r8d
  bool v9; // r15
  char v10; // r12
  __int64 Scene; // rax
  std::_Ref_count_base *v12; // r14
  __int64 NextInTree; // rax
  _QWORD *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  std::_Ref_count_base *v18; // rcx
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v20; // [rsp+38h] [rbp-C8h]
  Spectre::Engine::SceneNode *v21; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v22; // [rsp+48h] [rbp-B8h]
  std::_Ref_count_base *v23; // [rsp+58h] [rbp-A8h]
  std::_Ref_count_base *v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v25; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v28; // [rsp+88h] [rbp-78h]
  _BYTE v29[8]; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v30; // [rsp+98h] [rbp-68h]
  _QWORD *v31; // [rsp+B0h] [rbp-50h]
  _BYTE v32[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v33[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+E8h] [rbp-18h] BYREF

  v31 = a2;
  Spectre::Engine::SceneNode::VerifyWriteAccess(this);
  std::enable_shared_from_this<Spectre::Engine::Scene>::shared_from_this((char *)this + 8, &v21);
  if ( !*((_QWORD *)this + 46) )
  {
    std::string::string(
      v33,
      "SceneNode::SetParent() -- Unique ID zero is reserved for root-level nodes -- this node must not be given a parent.");
    v4 = std::string::string(
           v29,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scenenode.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v4,
      v5,
      (unsigned int)v33,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( *a2 )
  {
    v6 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
           &v27,
           a2);
    if ( (unsigned __int8)Spectre::Engine::SceneNode::TreeContains(this, v6) )
    {
      std::string::string(
        v33,
        "SceneNode::SetParent() -- A node's parent cannot be set to node that is within the node's own tree (cyclic graph prohibited).");
      v7 = std::string::string(
             v29,
             "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scenenode.cpp");
      Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
        (unsigned int)pExceptionObject,
        v7,
        v8,
        (unsigned int)v33,
        0);
      throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
    }
  }
  Spectre::Engine::SceneNode::GetParent(this, &v27);
  Spectre::Engine::SceneNode::GetScene(this, &v25);
  *(_OWORD *)v24 = 0;
  v9 = 0;
  v10 = 0;
  if ( v27 )
  {
    v9 = *a2 == 0;
  }
  else
  {
    if ( !*a2 )
      goto LABEL_12;
    v10 = 1;
  }
  if ( v27 )
    Spectre::Engine::SceneNode::RemoveChild(v27, &v21);
LABEL_12:
  if ( *a2 )
  {
    Spectre::Engine::SceneNode::AddChild(*a2, &v21);
    Scene = Spectre::Engine::SceneNode::GetScene(*a2, &v19);
    std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(v24, Scene);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
  }
  std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>((char *)this + 56, a2);
  v12 = v24[0];
  if ( v25 != v24[0] )
  {
    Spectre::Engine::SceneNode::TryDetachFromScene(this);
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(&v19, &v21);
    while ( v19 )
    {
      std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(v19 + 72, v24);
      NextInTree = Spectre::Engine::SceneNode::GetNextInTree(v21);
      std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(&v19, NextInTree);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
    }
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    Spectre::Engine::SceneNode::TryAttachToScene(this);
  }
  std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(&v19, &v21);
  while ( v19 )
  {
    if ( v10 && v12 )
    {
      v14 = (_QWORD *)std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
                        v32,
                        &v19);
      Spectre::Engine::Scene::RegisterNode((__int64)v12, v14);
    }
    if ( v9 && v25 )
    {
      v15 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
              v33,
              &v19);
      Spectre::Engine::Scene::DeregisterNode(v25, v15);
    }
    v16 = Spectre::Engine::SceneNode::GetNextInTree(v21);
    std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(&v19, v16);
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
  }
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  v17 = _InterlockedIncrement64(&Spectre::Engine::SceneNode::s_sharedTransformUpdateID);
  *((_QWORD *)this + 26) = v17;
  if ( v17 < *((_QWORD *)this + 27) )
    v17 = *((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = v17;
  if ( v24[1] )
    std::_Ref_count_base::_Decref(v24[1]);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  v18 = (std::_Ref_count_base *)a2[1];
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
}

```

## disassembly

```asm
0x18003b1d0  mov     [rsp-8+arg_10], rbx
0x18003b1d5  push    rbp
0x18003b1d6  push    rdi
0x18003b1d7  push    r12
0x18003b1d9  push    r14
0x18003b1db  push    r15
0x18003b1dd  lea     rbp, [rsp-30h]
0x18003b1e2  sub     rsp, 130h
0x18003b1e9  mov     rax, cs:__security_cookie
0x18003b1f0  xor     rax, rsp
0x18003b1f3  mov     [rbp+50h+var_30], rax
0x18003b1f7  mov     rdi, rdx
0x18003b1fa  mov     rbx, rcx
0x18003b1fd  mov     [rbp+50h+var_A0], rdx
0x18003b201  call    ?VerifyWriteAccess@SceneNode@Engine@Spectre@@QEBAXXZ; Spectre::Engine::SceneNode::VerifyWriteAccess(void)
0x18003b206  lea     rcx, [rbx+8]
0x18003b20a  lea     rdx, [rsp+150h+var_110]
0x18003b20f  call    ?shared_from_this@?$enable_shared_from_this@VScene@Engine@Spectre@@@std@@QEAA?AV?$shared_ptr@VScene@Engine@Spectre@@@2@XZ; std::enable_shared_from_this<Spectre::Engine::Scene>::shared_from_this(void)
0x18003b214  nop
0x18003b215  cmp     qword ptr [rbx+170h], 0
0x18003b21d  jnz     short loc_18003B266
0x18003b21f  lea     rdx, aScenenodeSetpa; "SceneNode::SetParent() -- Unique ID zer"...
0x18003b226  lea     rcx, [rbp+50h+var_88]
0x18003b22a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b22f  nop
0x18003b230  lea     rdx, aOnecoreuapWind_43; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003b237  lea     rcx, [rbp+50h+var_C0]
0x18003b23b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b240  mov     [rsp+150h+var_130], 0
0x18003b245  lea     r9, [rbp+50h+var_88]
0x18003b249  mov     rdx, rax
0x18003b24c  lea     rcx, [rbp+50h+pExceptionObject]
0x18003b250  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003b255  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003b25c  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x18003b260  call    _CxxThrowException_0
0x18003b266  cmp     qword ptr [rdi], 0
0x18003b26a  jz      short loc_18003B2CE
0x18003b26c  mov     rdx, rdi
0x18003b26f  lea     rcx, [rbp+50h+var_D0]
0x18003b273  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003b278  mov     rdx, rax
0x18003b27b  mov     rcx, rbx
0x18003b27e  call    ?TreeContains@SceneNode@Engine@Spectre@@AEAA_NV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::TreeContains(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003b283  test    al, al
0x18003b285  jz      short loc_18003B2CE
0x18003b287  lea     rdx, aScenenodeSetpa_0; "SceneNode::SetParent() -- A node's pare"...
0x18003b28e  lea     rcx, [rbp+50h+var_88]
0x18003b292  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b297  nop
0x18003b298  lea     rdx, aOnecoreuapWind_43; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003b29f  lea     rcx, [rbp+50h+var_C0]
0x18003b2a3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b2a8  mov     [rsp+150h+var_130], 0
0x18003b2ad  lea     r9, [rbp+50h+var_88]
0x18003b2b1  mov     rdx, rax
0x18003b2b4  lea     rcx, [rbp+50h+pExceptionObject]
0x18003b2b8  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003b2bd  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003b2c4  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x18003b2c8  call    _CxxThrowException_0
0x18003b2ce  lea     rdx, [rbp+50h+var_D0]
0x18003b2d2  mov     rcx, rbx
0x18003b2d5  call    ?GetParent@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetParent(void)
0x18003b2da  nop
0x18003b2db  lea     rdx, [rsp+150h+var_E0]
0x18003b2e0  mov     rcx, rbx
0x18003b2e3  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x18003b2e8  nop
0x18003b2e9  xorps   xmm0, xmm0
0x18003b2ec  movdqu  xmmword ptr [rsp+150h+var_F0], xmm0
0x18003b2f2  xor     r15b, r15b
0x18003b2f5  xor     r12b, r12b
0x18003b2f8  mov     rcx, [rbp+50h+var_D0]
0x18003b2fc  test    rcx, rcx
0x18003b2ff  jz      short loc_18003B30C
0x18003b301  cmp     qword ptr [rdi], 0
0x18003b305  jnz     short loc_18003B315
0x18003b307  mov     r15b, 1
0x18003b30a  jmp     short loc_18003B315
0x18003b30c  cmp     qword ptr [rdi], 0
0x18003b310  jz      short loc_18003B324
0x18003b312  mov     r12b, 1
0x18003b315  test    rcx, rcx
0x18003b318  jz      short loc_18003B324
0x18003b31a  lea     rdx, [rsp+150h+var_110]
0x18003b31f  call    ?RemoveChild@SceneNode@Engine@Spectre@@AEAAXAEBV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::RemoveChild(std::shared_ptr<Spectre::Engine::SceneNode> const &)
0x18003b324  mov     rcx, [rdi]
0x18003b327  test    rcx, rcx
0x18003b32a  jz      short loc_18003B35F
0x18003b32c  lea     rdx, [rsp+150h+var_110]
0x18003b331  call    ?AddChild@SceneNode@Engine@Spectre@@AEAAXAEBV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::AddChild(std::shared_ptr<Spectre::Engine::SceneNode> const &)
0x18003b336  lea     rdx, [rsp+150h+var_120]
0x18003b33b  mov     rcx, [rdi]
0x18003b33e  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x18003b343  mov     rdx, rax
0x18003b346  lea     rcx, [rsp+150h+var_F0]
0x18003b34b  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x18003b350  mov     rcx, [rsp+150h+var_118]; this
0x18003b355  test    rcx, rcx
0x18003b358  jz      short loc_18003B35F
0x18003b35a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b35f  lea     rcx, [rbx+38h]
0x18003b363  mov     rdx, rdi
0x18003b366  call    ??$?4VMaterial@Engine@Spectre@@$0A@@?$weak_ptr@VMaterial@Engine@Spectre@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VMaterial@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(std::shared_ptr<Spectre::Engine::Material> const &)
0x18003b36b  mov     r14, [rsp+150h+var_F0]
0x18003b370  cmp     [rsp+150h+var_E0], r14
0x18003b375  jz      short loc_18003B3F0
0x18003b377  mov     rcx, rbx; this
0x18003b37a  call    ?TryDetachFromScene@SceneNode@Engine@Spectre@@AEAAXXZ; Spectre::Engine::SceneNode::TryDetachFromScene(void)
0x18003b37f  lea     rdx, [rsp+150h+var_110]
0x18003b384  lea     rcx, [rsp+150h+var_120]
0x18003b389  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003b38e  nop
0x18003b38f  mov     rcx, [rsp+150h+var_120]
0x18003b394  test    rcx, rcx
0x18003b397  jz      short loc_18003B3D9
0x18003b399  add     rcx, 48h ; 'H'
0x18003b39d  lea     rdx, [rsp+150h+var_F0]
0x18003b3a2  call    ??$?4VMaterial@Engine@Spectre@@$0A@@?$weak_ptr@VMaterial@Engine@Spectre@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VMaterial@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(std::shared_ptr<Spectre::Engine::Material> const &)
0x18003b3a7  lea     r8, [rsp+150h+var_120]
0x18003b3ac  lea     rdx, [rsp+150h+var_100]
0x18003b3b1  mov     rcx, [rsp+150h+var_110]; this
0x18003b3b6  call    ?GetNextInTree@SceneNode@Engine@Spectre@@QEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@AEBV45@@Z; Spectre::Engine::SceneNode::GetNextInTree(std::shared_ptr<Spectre::Engine::SceneNode> const &)
0x18003b3bb  mov     rdx, rax
0x18003b3be  lea     rcx, [rsp+150h+var_120]
0x18003b3c3  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x18003b3c8  mov     rcx, [rsp+150h+var_F8]; this
0x18003b3cd  test    rcx, rcx
0x18003b3d0  jz      short loc_18003B38F
0x18003b3d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b3d7  jmp     short loc_18003B38F
0x18003b3d9  mov     rcx, [rsp+150h+var_118]; this
0x18003b3de  test    rcx, rcx
0x18003b3e1  jz      short loc_18003B3E8
0x18003b3e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b3e8  mov     rcx, rbx; this
0x18003b3eb  call    ?TryAttachToScene@SceneNode@Engine@Spectre@@AEAAXXZ; Spectre::Engine::SceneNode::TryAttachToScene(void)
0x18003b3f0  lea     rdx, [rsp+150h+var_110]
0x18003b3f5  lea     rcx, [rsp+150h+var_120]
0x18003b3fa  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003b3ff  nop
0x18003b400  cmp     [rsp+150h+var_120], 0
0x18003b406  jz      short loc_18003B486
0x18003b408  test    r12b, r12b
0x18003b40b  jz      short loc_18003B42B
0x18003b40d  test    r14, r14
0x18003b410  jz      short loc_18003B42B
0x18003b412  lea     rdx, [rsp+150h+var_120]
0x18003b417  lea     rcx, [rbp+50h+var_98]
0x18003b41b  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003b420  mov     rdx, rax
0x18003b423  mov     rcx, r14
0x18003b426  call    ?RegisterNode@Scene@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::Scene::RegisterNode(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003b42b  test    r15b, r15b
0x18003b42e  jz      short loc_18003B453
0x18003b430  cmp     [rsp+150h+var_E0], 0
0x18003b436  jz      short loc_18003B453
0x18003b438  lea     rdx, [rsp+150h+var_120]
0x18003b43d  lea     rcx, [rbp+50h+var_88]
0x18003b441  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003b446  mov     rdx, rax
0x18003b449  mov     rcx, [rsp+150h+var_E0]
0x18003b44e  call    ?DeregisterNode@Scene@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::Scene::DeregisterNode(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003b453  lea     r8, [rsp+150h+var_120]
0x18003b458  lea     rdx, [rbp+50h+var_C0]
0x18003b45c  mov     rcx, [rsp+150h+var_110]; this
0x18003b461  call    ?GetNextInTree@SceneNode@Engine@Spectre@@QEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@AEBV45@@Z; Spectre::Engine::SceneNode::GetNextInTree(std::shared_ptr<Spectre::Engine::SceneNode> const &)
0x18003b466  mov     rdx, rax
0x18003b469  lea     rcx, [rsp+150h+var_120]
0x18003b46e  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x18003b473  mov     rcx, [rbp+50h+var_B8]; this
0x18003b477  test    rcx, rcx
0x18003b47a  jz      short loc_18003B400
0x18003b47c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b481  jmp     loc_18003B400
0x18003b486  mov     rcx, [rsp+150h+var_118]; this
0x18003b48b  test    rcx, rcx
0x18003b48e  jz      short loc_18003B495
0x18003b490  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b495  mov     ecx, 1
0x18003b49a  lock xadd cs:?s_sharedTransformUpdateID@SceneNode@Engine@Spectre@@0U?$atomic@_K@std@@A, rcx; std::atomic<unsigned __int64> Spectre::Engine::SceneNode::s_sharedTransformUpdateID
0x18003b4a3  inc     rcx
0x18003b4a6  mov     [rbx+0D0h], rcx
0x18003b4ad  mov     rax, [rbx+0D8h]
0x18003b4b4  cmp     rcx, rax
0x18003b4b7  cmovb   rcx, rax
0x18003b4bb  mov     [rbx+0D8h], rcx
0x18003b4c2  mov     rcx, [rsp+150h+var_F0+8]; this
0x18003b4c7  test    rcx, rcx
0x18003b4ca  jz      short loc_18003B4D2
0x18003b4cc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b4d1  nop
0x18003b4d2  mov     rcx, [rsp+150h+var_D8]; this
0x18003b4d7  test    rcx, rcx
0x18003b4da  jz      short loc_18003B4E2
0x18003b4dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b4e1  nop
0x18003b4e2  mov     rcx, [rbp+50h+var_C8]; this
0x18003b4e6  test    rcx, rcx
0x18003b4e9  jz      short loc_18003B4F1
0x18003b4eb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b4f0  nop
0x18003b4f1  mov     rcx, [rsp+150h+var_108]; this
0x18003b4f6  test    rcx, rcx
0x18003b4f9  jz      short loc_18003B501
0x18003b4fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b500  nop
0x18003b501  mov     rcx, [rdi+8]; this
0x18003b505  test    rcx, rcx
0x18003b508  jz      short loc_18003B50F
0x18003b50a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b50f  mov     rcx, [rbp+50h+var_30]
0x18003b513  xor     rcx, rsp; StackCookie
0x18003b516  call    __security_check_cookie
0x18003b51b  mov     rbx, [rsp+150h+arg_10]
0x18003b523  add     rsp, 130h
0x18003b52a  pop     r15
0x18003b52c  pop     r14
0x18003b52e  pop     r12
0x18003b530  pop     rdi
0x18003b531  pop     rbp
0x18003b532  retn
```
