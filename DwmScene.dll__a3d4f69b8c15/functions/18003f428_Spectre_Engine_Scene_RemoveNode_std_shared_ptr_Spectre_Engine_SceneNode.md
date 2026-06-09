# Spectre::Engine::Scene::RemoveNode(std::shared_ptr<Spectre::Engine::SceneNode>)

- ea: `0x18003f428`
- end: `0x18003f606`
- name: `?RemoveNode@Scene@Engine@Spectre@@QEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z`
- size: `478`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013b20`
- `0x180015d40`
- `0x180015ec0`
- `0x18003f82c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012df8`
- `0x18002921c`
- `0x180037480`
- `0x180038ddc`
- `0x18003b1d0`
- `0x18003eb80`
- `0x18003ed74`
- `0x18003f428`

## string_xrefs

- `0x18003f471`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f4df`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f54c`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f45f`: `Scene::RemoveNode() - node must not be null`
- `0x18003f4ce`: `Scene::RemoveNode() - node is not in any layer`
- `0x18003f53b`: `Scene::RemoveNode() - the root node of a layer is for internal use by the system and must not be removed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Spectre::Engine::Scene::RemoveNode(__int64 a1, Spectre::Engine::SceneNode **a2)
{
  int v4; // eax
  int v5; // r8d
  __int64 v6; // rax
  __int64 v7; // rbx
  int v8; // eax
  int v9; // r8d
  Spectre::Engine::SceneNode **Parent; // rax
  Spectre::Engine::SceneNode *v11; // r14
  Spectre::Engine::SceneNode *v12; // r15
  int v13; // eax
  int v14; // r8d
  volatile __int32 *v15; // rbx
  __int64 v16; // rdx
  std::_Ref_count_base *v17; // rcx
  volatile __int32 *v18; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v21; // [rsp+48h] [rbp-B8h]
  Spectre::Engine::SceneNode **v22; // [rsp+60h] [rbp-A0h]
  _OWORD v23[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v26[56]; // [rsp+E0h] [rbp-20h] BYREF

  v22 = a2;
  if ( !*a2 )
  {
    std::string::string(v23, "Scene::RemoveNode() - node must not be null");
    v4 = std::string::string(
           &v20,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v4,
      v5,
      (unsigned int)v23,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v6 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v23, a2);
  Spectre::Engine::Scene::GetNodeLayer(a1, &v20, v6);
  v7 = v20;
  if ( !v20 )
  {
    std::string::string(pExceptionObject, "Scene::RemoveNode() - node is not in any layer");
    v8 = std::string::string(
           v24,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)v26,
      v8,
      v9,
      (unsigned int)pExceptionObject,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)v26;
  }
  Parent = (Spectre::Engine::SceneNode **)Spectre::Utils::IConfigurationManager::GetParent(v20, &v18);
  v11 = *a2;
  v12 = *Parent;
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  if ( v11 == v12 )
  {
    std::string::string(
      v24,
      "Scene::RemoveNode() - the root node of a layer is for internal use by the system and must not be removed");
    v13 = std::string::string(
            pExceptionObject,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)v26,
      v13,
      v14,
      (unsigned int)v24,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)v26;
  }
  Spectre::Engine::Lockable::VerifyWriteAccess((Spectre::Engine::Lockable *)(a1 + 16));
  v15 = (volatile __int32 *)(v7 + 76);
  v18 = v15;
  while ( _InterlockedExchange(v15, 1) )
    ;
  v23[0] = 0;
  Spectre::Engine::SceneNode::SetParent(*a2);
  std::_Atomic_storage<long,4>::store(v15, v16, 3);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  v17 = a2[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
}

```

## disassembly

```asm
0x18003f428  mov     [rsp-8+arg_10], rbx
0x18003f42d  push    rbp
0x18003f42e  push    rsi
0x18003f42f  push    rdi
0x18003f430  push    r14
0x18003f432  push    r15
0x18003f434  lea     rbp, [rsp-20h]
0x18003f439  sub     rsp, 120h
0x18003f440  mov     rax, cs:__security_cookie
0x18003f447  xor     rax, rsp
0x18003f44a  mov     [rbp+40h+var_28], rax
0x18003f44e  mov     rdi, rdx
0x18003f451  mov     rsi, rcx
0x18003f454  mov     [rsp+140h+var_E0], rdx
0x18003f459  cmp     qword ptr [rdx], 0
0x18003f45d  jnz     short loc_18003F4A9
0x18003f45f  lea     rdx, aSceneRemovenod; "Scene::RemoveNode() - node must not be "...
0x18003f466  lea     rcx, [rsp+140h+var_D8]
0x18003f46b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f470  nop
0x18003f471  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f478  lea     rcx, [rsp+140h+var_100]
0x18003f47d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f482  mov     [rsp+140h+var_120], 0
0x18003f487  lea     r9, [rsp+140h+var_D8]
0x18003f48c  mov     rdx, rax
0x18003f48f  lea     rcx, [rbp+40h+pExceptionObject]
0x18003f493  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f498  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f49f  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18003f4a3  call    _CxxThrowException_0
0x18003f4a9  lea     rcx, [rsp+140h+var_D8]
0x18003f4ae  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003f4b3  mov     r8, rax
0x18003f4b6  lea     rdx, [rsp+140h+var_100]
0x18003f4bb  mov     rcx, rsi
0x18003f4be  call    ?GetNodeLayer@Scene@Engine@Spectre@@QEBA?AV?$shared_ptr@VSceneLayer@Engine@Spectre@@@std@@V?$shared_ptr@VSceneNode@Engine@Spectre@@@5@@Z; Spectre::Engine::Scene::GetNodeLayer(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f4c3  nop
0x18003f4c4  mov     rbx, [rsp+140h+var_100]
0x18003f4c9  test    rbx, rbx
0x18003f4cc  jnz     short loc_18003F514
0x18003f4ce  lea     rdx, aSceneRemovenod_0; "Scene::RemoveNode() - node is not in an"...
0x18003f4d5  lea     rcx, [rbp+40h+pExceptionObject]
0x18003f4d9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f4de  nop
0x18003f4df  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f4e6  lea     rcx, [rbp+40h+var_B8]
0x18003f4ea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f4ef  mov     [rsp+140h+var_120], bl
0x18003f4f3  lea     r9, [rbp+40h+pExceptionObject]
0x18003f4f7  mov     rdx, rax
0x18003f4fa  lea     rcx, [rbp+40h+var_60]
0x18003f4fe  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f503  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f50a  lea     rcx, [rbp+40h+var_60]; pExceptionObject
0x18003f50e  call    _CxxThrowException_0
0x18003f514  lea     rdx, [rsp+140h+var_110]
0x18003f519  mov     rcx, rbx
0x18003f51c  call    ?GetParent@IConfigurationManager@Utils@Spectre@@QEBA?AV?$shared_ptr@VIConfigurationManager@Utils@Spectre@@@std@@XZ; Spectre::Utils::IConfigurationManager::GetParent(void)
0x18003f521  mov     r14, [rdi]
0x18003f524  mov     r15, [rax]
0x18003f527  mov     rcx, [rsp+140h+var_108]; this
0x18003f52c  test    rcx, rcx
0x18003f52f  jz      short loc_18003F536
0x18003f531  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f536  cmp     r14, r15
0x18003f539  jnz     short loc_18003F582
0x18003f53b  lea     rdx, aSceneRemovenod_1; "Scene::RemoveNode() - the root node of "...
0x18003f542  lea     rcx, [rbp+40h+var_B8]
0x18003f546  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f54b  nop
0x18003f54c  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f553  lea     rcx, [rbp+40h+pExceptionObject]
0x18003f557  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f55c  mov     [rsp+140h+var_120], 0
0x18003f561  lea     r9, [rbp+40h+var_B8]
0x18003f565  mov     rdx, rax
0x18003f568  lea     rcx, [rbp+40h+var_60]
0x18003f56c  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f571  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f578  lea     rcx, [rbp+40h+var_60]; pExceptionObject
0x18003f57c  call    _CxxThrowException_0
0x18003f582  lea     rcx, [rsi+10h]; this
0x18003f586  call    ?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ; Spectre::Engine::Lockable::VerifyWriteAccess(void)
0x18003f58b  add     rbx, 4Ch ; 'L'
0x18003f58f  mov     [rsp+140h+var_110], rbx
0x18003f594  mov     eax, 1
0x18003f599  xchg    eax, [rbx]
0x18003f59b  test    eax, eax
0x18003f59d  jnz     short loc_18003F594
0x18003f59f  xorps   xmm0, xmm0
0x18003f5a2  movdqu  [rsp+140h+var_D8], xmm0
0x18003f5a8  lea     rdx, [rsp+140h+var_D8]
0x18003f5ad  mov     rcx, [rdi]
0x18003f5b0  call    ?SetParent@SceneNode@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::SetParent(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003f5b5  nop
0x18003f5b6  mov     r8d, 3
0x18003f5bc  mov     rcx, rbx
0x18003f5bf  call    ?store@?$_Atomic_storage@J$03@std@@QEAAXJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::store(long,std::memory_order)
0x18003f5c4  nop
0x18003f5c5  mov     rcx, [rsp+140h+var_F8]; this
0x18003f5ca  test    rcx, rcx
0x18003f5cd  jz      short loc_18003F5D5
0x18003f5cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f5d4  nop
0x18003f5d5  mov     rcx, [rdi+8]; this
0x18003f5d9  test    rcx, rcx
0x18003f5dc  jz      short loc_18003F5E3
0x18003f5de  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f5e3  mov     rcx, [rbp+40h+var_28]
0x18003f5e7  xor     rcx, rsp; StackCookie
0x18003f5ea  call    __security_check_cookie
0x18003f5ef  mov     rbx, [rsp+140h+arg_10]
0x18003f5f7  add     rsp, 120h
0x18003f5fe  pop     r15
0x18003f600  pop     r14
0x18003f602  pop     rdi
0x18003f603  pop     rsi
0x18003f604  pop     rbp
0x18003f605  retn
```
