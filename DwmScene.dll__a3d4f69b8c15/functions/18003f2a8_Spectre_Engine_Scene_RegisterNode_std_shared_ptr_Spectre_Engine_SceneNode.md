# Spectre::Engine::Scene::RegisterNode(std::shared_ptr<Spectre::Engine::SceneNode>)

- ea: `0x18003f2a8`
- end: `0x18003f420`
- name: `?RegisterNode@Scene@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003b1d0`
- `0x18003e32c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180016324`
- `0x180038ddc`
- `0x18003d38c`
- `0x18003f2a8`
- `0x180040494`

## string_xrefs

- `0x18003f2ed`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f361`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003f350`: `Scene::RegisterNode() - node id already exists`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Spectre::Engine::Scene::RegisterNode(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  int v5; // eax
  int v6; // r8d
  int v7; // eax
  int v8; // r8d
  std::_Ref_count_base *v9; // rcx
  _QWORD v10[2]; // [rsp+30h] [rbp-69h] BYREF
  std::_Ref_count_base *v11; // [rsp+40h] [rbp-59h]
  _QWORD *v12; // [rsp+50h] [rbp-49h]
  __int64 v13; // [rsp+58h] [rbp-41h] BYREF
  std::_Ref_count_base *v14; // [rsp+60h] [rbp-39h]
  _QWORD v15[4]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+98h] [rbp-1h] BYREF

  v12 = a2;
  v4 = *a2;
  if ( !*a2 )
  {
    std::string::string(&v13, "Scene::RegisterNode() - node must not be null");
    v5 = std::string::string(
           v10,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v5,
      v6,
      (unsigned int)&v13,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( *(_QWORD *)(v4 + 368) )
  {
    v15[0] = *(_QWORD *)(v4 + 368);
    if ( *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<Spectre::Engine::SceneNode>>>,0>>::find(
                      a1 + 120,
                      &v13,
                      v15) != *(_QWORD *)(a1 + 128) )
    {
      std::string::string(v15, "Scene::RegisterNode() - node id already exists");
      v7 = std::string::string(
             v10,
             "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
      Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
        (unsigned int)pExceptionObject,
        v7,
        v8,
        (unsigned int)v15,
        0);
      throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
    }
  }
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(&v13, a2);
  v10[0] = *(_QWORD *)(*a2 + 368LL);
  v10[1] = v13;
  v11 = v14;
  v13 = 0;
  v14 = 0;
  std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<Spectre::Engine::SceneNode>>>,0>>::emplace<std::pair<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>>>(
    a1 + 120,
    v15,
    v10);
  if ( v11 )
    std::_Ref_count_base::_Decwref(v11);
  v9 = (std::_Ref_count_base *)a2[1];
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
}

```

## disassembly

```asm
0x18003f2a8  mov     [rsp-8+arg_10], rbx
0x18003f2ad  push    rbp
0x18003f2ae  push    rsi
0x18003f2af  push    rdi
0x18003f2b0  lea     rbp, [rsp-47h]
0x18003f2b5  sub     rsp, 0E0h
0x18003f2bc  mov     rax, cs:__security_cookie
0x18003f2c3  xor     rax, rsp
0x18003f2c6  mov     [rbp+57h+var_20], rax
0x18003f2ca  mov     rbx, rdx
0x18003f2cd  mov     rsi, rcx
0x18003f2d0  mov     [rbp+57h+var_A0], rdx
0x18003f2d4  mov     rax, [rdx]
0x18003f2d7  test    rax, rax
0x18003f2da  jnz     short loc_18003F323
0x18003f2dc  lea     rdx, aSceneRegistern_0; "Scene::RegisterNode() - node must not b"...
0x18003f2e3  lea     rcx, [rbp+57h+var_98]
0x18003f2e7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f2ec  nop
0x18003f2ed  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f2f4  lea     rcx, [rbp+57h+var_C0]
0x18003f2f8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f2fd  mov     [rsp+0F0h+var_D0], 0
0x18003f302  lea     r9, [rbp+57h+var_98]
0x18003f306  mov     rdx, rax
0x18003f309  lea     rcx, [rbp+57h+pExceptionObject]
0x18003f30d  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f312  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f319  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003f31d  call    _CxxThrowException_0
0x18003f323  mov     rcx, [rax+170h]
0x18003f32a  test    rcx, rcx
0x18003f32d  jz      short loc_18003F397
0x18003f32f  mov     [rbp+57h+var_78], rcx
0x18003f333  lea     r8, [rbp+57h+var_78]
0x18003f337  lea     rdx, [rbp+57h+var_98]
0x18003f33b  lea     rcx, [rsi+78h]
0x18003f33f  call    ?find@?$_Hash@V?$_Umap_traits@_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<Spectre::Engine::SceneNode>>>,0>>::find(unsigned __int64 const &)
0x18003f344  mov     rcx, [rsi+80h]
0x18003f34b  cmp     [rax], rcx
0x18003f34e  jz      short loc_18003F397
0x18003f350  lea     rdx, aSceneRegistern; "Scene::RegisterNode() - node id already"...
0x18003f357  lea     rcx, [rbp+57h+var_78]
0x18003f35b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f360  nop
0x18003f361  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003f368  lea     rcx, [rbp+57h+var_C0]
0x18003f36c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003f371  mov     [rsp+0F0h+var_D0], 0
0x18003f376  lea     r9, [rbp+57h+var_78]
0x18003f37a  mov     rdx, rax
0x18003f37d  lea     rcx, [rbp+57h+pExceptionObject]
0x18003f381  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003f386  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003f38d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003f391  call    _CxxThrowException_0
0x18003f397  mov     rdx, rbx
0x18003f39a  lea     rcx, [rbp+57h+var_98]
0x18003f39e  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x18003f3a3  nop
0x18003f3a4  mov     rax, [rbx]
0x18003f3a7  mov     rdx, [rax+170h]
0x18003f3ae  mov     [rbp+57h+var_C0], rdx
0x18003f3b2  mov     rax, [rbp+57h+var_98]
0x18003f3b6  mov     [rbp+57h+var_B8], rax
0x18003f3ba  mov     rax, [rbp+57h+var_90]
0x18003f3be  mov     [rbp+57h+var_B0], rax
0x18003f3c2  mov     [rbp+57h+var_98], 0
0x18003f3ca  mov     [rbp+57h+var_90], 0
0x18003f3d2  lea     r8, [rbp+57h+var_C0]
0x18003f3d6  lea     rdx, [rbp+57h+var_78]
0x18003f3da  lea     rcx, [rsi+78h]
0x18003f3de  call    ??$emplace@U?$pair@_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@@std@@@?$_Hash@V?$_Umap_traits@_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<Spectre::Engine::SceneNode>>>,0>>::emplace<std::pair<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>>>(std::pair<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>> &&)
0x18003f3e3  nop
0x18003f3e4  mov     rcx, [rbp+57h+var_B0]; this
0x18003f3e8  test    rcx, rcx
0x18003f3eb  jz      short loc_18003F3F3
0x18003f3ed  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18003f3f2  nop
0x18003f3f3  mov     rcx, [rbx+8]; this
0x18003f3f7  test    rcx, rcx
0x18003f3fa  jz      short loc_18003F401
0x18003f3fc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f401  mov     rcx, [rbp+57h+var_20]
0x18003f405  xor     rcx, rsp; StackCookie
0x18003f408  call    __security_check_cookie
0x18003f40d  mov     rbx, [rsp+0F0h+arg_10]
0x18003f415  add     rsp, 0E0h
0x18003f41c  pop     rdi
0x18003f41d  pop     rsi
0x18003f41e  pop     rbp
0x18003f41f  retn
```
