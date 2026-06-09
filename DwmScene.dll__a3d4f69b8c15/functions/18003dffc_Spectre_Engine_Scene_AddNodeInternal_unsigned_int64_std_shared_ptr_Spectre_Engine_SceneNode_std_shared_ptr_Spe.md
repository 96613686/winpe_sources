# Spectre::Engine::Scene::AddNodeInternal(unsigned __int64,std::shared_ptr<Spectre::Engine::SceneNode>,std::shared_ptr<Spectre::Engine::SceneLayer> const &)

- ea: `0x18003dffc`
- end: `0x18003e20c`
- name: `?AddNodeInternal@Scene@Engine@Spectre@@AEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@_KV45@AEBV?$shared_ptr@VSceneLayer@Engine@Spectre@@@5@@Z`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003dcf0`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x180012df8`
- `0x18002921c`
- `0x180037480`
- `0x180038ddc`
- `0x18003b1d0`
- `0x18003cac0`
- `0x18003dffc`
- `0x18003e640`
- `0x18003ed74`
- `0x180040494`

## string_xrefs

- `0x18003e0c1`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003e1d6`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003e1c5`: `Node id already exists`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Spectre::Engine::SceneNode **__fastcall Spectre::Engine::Scene::AddNodeInternal(
        __int64 a1,
        Spectre::Engine::SceneNode **a2,
        unsigned __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  unsigned __int64 v6; // rbx
  __int64 Parent; // rax
  volatile signed __int64 *v10; // rcx
  volatile __int64 *v11; // rcx
  int v12; // eax
  int v13; // r8d
  volatile __int32 *v14; // rbx
  Spectre::Engine::SceneNode *v15; // rdi
  __int64 v16; // rdx
  std::_Ref_count_base *v17; // rcx
  int v19; // eax
  int v20; // r8d
  _QWORD v21[2]; // [rsp+30h] [rbp-91h] BYREF
  _QWORD v22[3]; // [rsp+40h] [rbp-81h] BYREF
  Spectre::Engine::SceneNode *v23; // [rsp+58h] [rbp-69h] BYREF
  std::_Ref_count_base *v24; // [rsp+60h] [rbp-61h]
  _BYTE v25[32]; // [rsp+78h] [rbp-49h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+98h] [rbp-29h] BYREF

  v6 = a3;
  v21[0] = a3;
  v22[2] = a4;
  Spectre::Engine::Lockable::VerifyWriteAccess((Spectre::Engine::Lockable *)(a1 + 16));
  if ( !*a4 )
  {
    Parent = Spectre::Utils::IConfigurationManager::GetParent(*a5, &v23);
    std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(a4, Parent);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
  }
  v10 = (volatile signed __int64 *)(a1 + 72);
  if ( v6 == -1 )
  {
    v6 = _InterlockedExchangeAdd64(v10, 1u);
    v21[0] = v6;
  }
  else if ( v6 >= std::_Atomic_storage<unsigned __int64,8>::load(v10) )
  {
    _InterlockedExchange64(v11, v6 + 1);
  }
  if ( v6 == -1 )
  {
    std::string::string(v25, "Run out of available IDs");
    v12 = std::string::string(
            &v23,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v12,
      v13,
      (unsigned int)v25,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<Spectre::Engine::SceneNode>>>,0>>::find(
                    a1 + 120,
                    v22,
                    v21) != *(_QWORD *)(a1 + 128) )
  {
    std::string::string(&v23, "Node id already exists");
    v19 = std::string::string(
            v25,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v19,
      v20,
      (unsigned int)&v23,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( *a4 )
  {
    v14 = (volatile __int32 *)(*a5 + 76LL);
    v22[0] = v14;
    while ( _InterlockedExchange(v14, 1) )
      ;
    Spectre::Engine::Scene::CreateNodeInternal(a1, &v23, v21);
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v21, a4);
    v15 = v23;
    Spectre::Engine::SceneNode::SetParent(v23);
    *(_BYTE *)(*a5 + 72LL) = 1;
    *a2 = v15;
    a2[1] = v24;
    std::_Atomic_storage<long,4>::store(v14, v16, 3);
  }
  else
  {
    *a2 = 0;
    a2[1] = 0;
  }
  v17 = (std::_Ref_count_base *)a4[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  return a2;
}

```

## disassembly

```asm
0x18003dffc  push    rbp
0x18003dffe  push    rbx
0x18003dfff  push    rsi
0x18003e000  push    rdi
0x18003e001  push    r12
0x18003e003  push    r14
0x18003e005  push    r15
0x18003e007  lea     rbp, [rsp-1Fh]
0x18003e00c  sub     rsp, 0E0h
0x18003e013  mov     rax, cs:__security_cookie
0x18003e01a  xor     rax, rsp
0x18003e01d  mov     [rbp+4Fh+var_40], rax
0x18003e021  mov     rsi, r9
0x18003e024  mov     rbx, r8
0x18003e027  mov     r14, rdx
0x18003e02a  mov     rdi, rcx
0x18003e02d  mov     [rsp+110h+var_E0], rdx
0x18003e032  mov     [rsp+110h+var_E0], rbx
0x18003e037  mov     [rbp+4Fh+var_C0], r9
0x18003e03b  mov     r12, [rbp+4Fh+arg_20]
0x18003e03f  add     rcx, 10h; this
0x18003e043  call    ?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ; Spectre::Engine::Lockable::VerifyWriteAccess(void)
0x18003e048  cmp     qword ptr [rsi], 0
0x18003e04c  jnz     short loc_18003E074
0x18003e04e  lea     rdx, [rbp+4Fh+var_B8]
0x18003e052  mov     rcx, [r12]
0x18003e056  call    ?GetParent@IConfigurationManager@Utils@Spectre@@QEBA?AV?$shared_ptr@VIConfigurationManager@Utils@Spectre@@@std@@XZ; Spectre::Utils::IConfigurationManager::GetParent(void)
0x18003e05b  mov     rdx, rax
0x18003e05e  mov     rcx, rsi
0x18003e061  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x18003e066  mov     rcx, [rbp+4Fh+var_B0]; this
0x18003e06a  test    rcx, rcx
0x18003e06d  jz      short loc_18003E074
0x18003e06f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e074  lea     rcx, [rdi+48h]
0x18003e078  mov     r15d, 1
0x18003e07e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003e082  jnz     short loc_18003E099
0x18003e084  mov     ebx, r15d
0x18003e087  lock xadd [rcx], rbx
0x18003e08c  dec     rbx
0x18003e08f  add     rbx, r15
0x18003e092  mov     [rsp+110h+var_E0], rbx
0x18003e097  jmp     short loc_18003E0AA
0x18003e099  call    ?load@?$_Atomic_storage@_K$07@std@@QEBA_KW4memory_order@2@@Z; std::_Atomic_storage<unsigned __int64,8>::load(std::memory_order)
0x18003e09e  cmp     rbx, rax
0x18003e0a1  jb      short loc_18003E0AA
0x18003e0a3  lea     rax, [rbx+1]
0x18003e0a7  xchg    rax, [rcx]
0x18003e0aa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003e0ae  jnz     short loc_18003E0F7
0x18003e0b0  lea     rdx, aRunOutOfAvaila; "Run out of available IDs"
0x18003e0b7  lea     rcx, [rbp+4Fh+var_98]
0x18003e0bb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e0c0  nop
0x18003e0c1  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003e0c8  lea     rcx, [rbp+4Fh+var_B8]
0x18003e0cc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e0d1  mov     [rsp+110h+var_F0], 0
0x18003e0d6  lea     r9, [rbp+4Fh+var_98]
0x18003e0da  mov     rdx, rax
0x18003e0dd  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18003e0e1  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003e0e6  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003e0ed  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18003e0f1  call    _CxxThrowException_0
0x18003e0f7  lea     rcx, [rdi+78h]
0x18003e0fb  lea     r8, [rsp+110h+var_E0]
0x18003e100  lea     rdx, [rsp+110h+var_D0]
0x18003e105  call    ?find@?$_Hash@V?$_Umap_traits@_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KV?$weak_ptr@VSceneNode@Engine@Spectre@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<Spectre::Engine::SceneNode>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<Spectre::Engine::SceneNode>>>,0>>::find(unsigned __int64 const &)
0x18003e10a  mov     rcx, [rdi+80h]
0x18003e111  cmp     [rax], rcx
0x18003e114  jnz     loc_18003E1C5
0x18003e11a  cmp     qword ptr [rsi], 0
0x18003e11e  jz      short loc_18003E187
0x18003e120  mov     rbx, [r12]
0x18003e124  add     rbx, 4Ch ; 'L'
0x18003e128  mov     [rsp+110h+var_D0], rbx
0x18003e12d  mov     eax, r15d
0x18003e130  xchg    eax, [rbx]
0x18003e132  test    eax, eax
0x18003e134  jnz     short loc_18003E12D
0x18003e136  lea     r8, [rsp+110h+var_E0]
0x18003e13b  lea     rdx, [rbp+4Fh+var_B8]
0x18003e13f  mov     rcx, rdi
0x18003e142  call    ?CreateNodeInternal@Scene@Engine@Spectre@@AEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@AEB_K@Z; Spectre::Engine::Scene::CreateNodeInternal(unsigned __int64 const &)
0x18003e147  nop
0x18003e148  mov     rdx, rsi
0x18003e14b  lea     rcx, [rsp+110h+var_E0]
0x18003e150  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003e155  mov     rdx, rax
0x18003e158  mov     rdi, [rbp+4Fh+var_B8]
0x18003e15c  mov     rcx, rdi
0x18003e15f  call    ?SetParent@SceneNode@Engine@Spectre@@AEAAXV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::SetParent(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003e164  mov     rax, [r12]
0x18003e168  xchg    r15b, [rax+48h]
0x18003e16c  mov     [r14], rdi
0x18003e16f  mov     rax, [rbp+4Fh+var_B0]
0x18003e173  mov     [r14+8], rax
0x18003e177  mov     r8d, 3
0x18003e17d  mov     rcx, rbx
0x18003e180  call    ?store@?$_Atomic_storage@J$03@std@@QEAAXJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::store(long,std::memory_order)
0x18003e185  jmp     short loc_18003E196
0x18003e187  mov     qword ptr [r14], 0
0x18003e18e  mov     qword ptr [r14+8], 0
0x18003e196  mov     rcx, [rsi+8]; this
0x18003e19a  test    rcx, rcx
0x18003e19d  jz      short loc_18003E1A4
0x18003e19f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e1a4  mov     rax, r14
0x18003e1a7  mov     rcx, [rbp+4Fh+var_40]
0x18003e1ab  xor     rcx, rsp; StackCookie
0x18003e1ae  call    __security_check_cookie
0x18003e1b3  add     rsp, 0E0h
0x18003e1ba  pop     r15
0x18003e1bc  pop     r14
0x18003e1be  pop     r12
0x18003e1c0  pop     rdi
0x18003e1c1  pop     rsi
0x18003e1c2  pop     rbx
0x18003e1c3  pop     rbp
0x18003e1c4  retn
0x18003e1c5  lea     rdx, aNodeIdAlreadyE; "Node id already exists"
0x18003e1cc  lea     rcx, [rbp+4Fh+var_B8]
0x18003e1d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e1d5  nop
0x18003e1d6  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003e1dd  lea     rcx, [rbp+4Fh+var_98]
0x18003e1e1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e1e6  mov     [rsp+110h+var_F0], 0
0x18003e1eb  lea     r9, [rbp+4Fh+var_B8]
0x18003e1ef  mov     rdx, rax
0x18003e1f2  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18003e1f6  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003e1fb  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003e202  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18003e206  call    _CxxThrowException_0
```
