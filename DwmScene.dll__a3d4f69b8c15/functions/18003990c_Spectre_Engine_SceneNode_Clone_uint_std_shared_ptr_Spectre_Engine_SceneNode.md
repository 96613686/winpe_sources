# Spectre::Engine::SceneNode::Clone(uint,std::shared_ptr<Spectre::Engine::SceneNode>)

- ea: `0x18003990c`
- end: `0x180039ce1`
- name: `?Clone@SceneNode@Engine@Spectre@@QEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@IV45@@Z`
- size: `981`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180013b20`
- `0x180015ec0`
- `0x18003990c`

## callees

- `0x18000ca90`
- `0x18000d4ae`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x180012df8`
- `0x180013760`
- `0x180013798`
- `0x180014554`
- `0x18001c630`
- `0x18001c6e0`
- `0x18001e694`
- `0x180038ddc`
- `0x1800394c8`
- `0x180039748`
- `0x18003990c`
- `0x18003b658`
- `0x18003bf04`
- `0x18003ddf8`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180039b8e`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180039b8e`

## string_xrefs

- `0x1800399f7`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scenenode.cpp`
- `0x180039c09`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scenenode.cpp`
- `0x180039bb4`: `SceneNode::Clone() -- component type `

## pseudocode

```c
// Hidden C++ exception states: #wind=11
Spectre::Engine::SceneNode **__fastcall Spectre::Engine::SceneNode::Clone(
        __int64 a1,
        Spectre::Engine::SceneNode **a2,
        unsigned int a3,
        _QWORD *a4)
{
  __int64 Parent; // rax
  __int64 v9; // r10
  __int64 Scene; // rax
  int v11; // eax
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // r10
  _QWORD *v16; // r14
  _QWORD *v17; // r12
  __int64 v18; // rax
  void (__fastcall *v19)(__int64, std::_Ref_count_base **, __int64 *, __int64); // r10
  __int64 v20; // r11
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // eax
  int v29; // r8d
  __int64 v30; // r14
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // r10
  std::_Ref_count_base *v34; // rcx
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+38h] [rbp-C8h]
  int v38; // [rsp+40h] [rbp-C0h]
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v42; // [rsp+68h] [rbp-98h]
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v44; // [rsp+78h] [rbp-88h]
  _BYTE v45[32]; // [rsp+80h] [rbp-80h] BYREF
  Spectre::Engine::SceneNode **v46; // [rsp+A0h] [rbp-60h]
  _QWORD *v47; // [rsp+A8h] [rbp-58h]
  _BYTE v48[32]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v49[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v51[56]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v52[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v53[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v54[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v55[32]; // [rsp+1C0h] [rbp+C0h] BYREF

  v46 = a2;
  v47 = a4;
  v38 = 0;
  Spectre::Engine::SceneNode::VerifyReadAccess((Spectre::Engine::SceneNode *)a1);
  if ( !*a4 )
  {
    Parent = Spectre::Engine::SceneNode::GetParent(a1, &v43);
    std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(a4, Parent);
    if ( v44 )
      std::_Ref_count_base::_Decref(v44);
  }
  Spectre::Engine::SceneNode::GetScene(a1, &v43);
  Spectre::Engine::SceneNode::GetScene(*a4, &v41);
  v9 = v41;
  if ( !v41 )
  {
    Scene = Spectre::Engine::SceneNode::GetScene(a1, v49);
    std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(&v41, Scene);
    if ( v49[1] )
      std::_Ref_count_base::_Decref(v49[1]);
    v9 = v41;
  }
  if ( *(_QWORD *)(v9 + 104) != *(_QWORD *)(v43 + 104) )
  {
    std::string::string(v49, "SceneNode::Clone() -- source and target scenes must belong to the same engine");
    v11 = std::string::string(
            v45,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scenenode.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v11,
      v12,
      (unsigned int)v49,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v13 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v49, a4);
  Spectre::Engine::Scene::AddNode(v15, a2, v14, v13);
  v38 = 1;
  *((_QWORD *)*a2 + 56) = *(_QWORD *)(a1 + 448);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::operator=(
    (char *)*a2 + 432,
    a1 + 432);
  std::string::operator=((char *)*a2 + 400, a1 + 400);
  v39 = *(_QWORD *)(a1 + 172);
  v40 = *(_DWORD *)(a1 + 180);
  *(_OWORD *)v49 = *(_OWORD *)(a1 + 156);
  v36 = *(_QWORD *)(a1 + 144);
  v37 = *(_DWORD *)(a1 + 152);
  Spectre::Engine::SceneNode::SetTransform(*a2, &v36, v49, &v39);
  if ( (a3 & 2) != 0 )
  {
    LODWORD(v36) = a3;
    Spectre::Engine::SceneNode::VerifyReadAccess((Spectre::Engine::SceneNode *)a1);
    v16 = *(_QWORD **)(a1 + 376);
    v17 = *(_QWORD **)(a1 + 384);
    while ( v16 != v17 )
    {
      v18 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
              v45,
              a2);
      v19(v20, v49, &v36, v18);
      if ( v49[0] )
      {
        Spectre::Engine::SceneNode::AddComponentInternal(*a2);
      }
      else if ( (a3 & 0x10000) == 0 )
      {
        v21 = *v16;
        v22 = __RTtypeid(*v16);
        v23 = _std_type_info_name(v22 + 8, &__type_info_root_node);
        v24 = std::string::string(v52, v23);
        v25 = std::operator+<char>(v53, "SceneNode::Clone() -- component type ", v24);
        v26 = std::operator+<char>(v54, v25, " with name ");
        v27 = std::operator+<char>(v55, v26, v21 + 24);
        LODWORD(v21) = std::operator+<char>(pExceptionObject, v27, " could not be cloned");
        v28 = std::string::string(
                v48,
                "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scenenode.cpp");
        Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v51, v28, v29, v21, 1);
        throw (Spectre::Engine::EngineInvalidArgException *)v51;
      }
      if ( v49[1] )
        std::_Ref_count_base::_Decref(v49[1]);
      v16 += 2;
    }
  }
  if ( (a3 & 1) != 0 )
  {
    Spectre::Engine::SceneNode::VerifyReadAccess((Spectre::Engine::SceneNode *)a1);
    v30 = *(_QWORD *)(a1 + 32);
    v31 = *(_QWORD *)(a1 + 40);
    while ( v30 != v31 )
    {
      v32 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
              v45,
              a2);
      Spectre::Engine::SceneNode::Clone(v33, v49, a3, v32);
      if ( v49[1] )
        std::_Ref_count_base::_Decref(v49[1]);
      v30 += 16;
    }
  }
  if ( v42 )
    std::_Ref_count_base::_Decref(v42);
  if ( v44 )
    std::_Ref_count_base::_Decref(v44);
  v34 = (std::_Ref_count_base *)a4[1];
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  return a2;
}

```

## disassembly

```asm
0x18003990c  push    rbp
0x18003990e  push    rbx
0x18003990f  push    rsi
0x180039910  push    rdi
0x180039911  push    r12
0x180039913  push    r14
0x180039915  push    r15
0x180039917  lea     rbp, [rsp-0F0h]
0x18003991f  sub     rsp, 1F0h
0x180039926  mov     rax, cs:__security_cookie
0x18003992d  xor     rax, rsp
0x180039930  mov     [rbp+120h+var_40], rax
0x180039937  mov     rsi, r9
0x18003993a  mov     r15d, r8d
0x18003993d  mov     rdi, rdx
0x180039940  mov     rbx, rcx
0x180039943  mov     [rbp+120h+var_180], rdx
0x180039947  mov     [rbp+120h+var_178], r9
0x18003994b  mov     [rsp+220h+var_1E0], 0
0x180039953  call    ?VerifyReadAccess@SceneNode@Engine@Spectre@@QEBAXXZ; Spectre::Engine::SceneNode::VerifyReadAccess(void)
0x180039958  cmp     qword ptr [rsi], 0
0x18003995c  jnz     short loc_180039985
0x18003995e  lea     rdx, [rsp+220h+var_1B0]
0x180039963  mov     rcx, rbx
0x180039966  call    ?GetParent@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetParent(void)
0x18003996b  mov     rdx, rax
0x18003996e  mov     rcx, rsi
0x180039971  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x180039976  mov     rcx, [rsp+220h+var_1A8]; this
0x18003997b  test    rcx, rcx
0x18003997e  jz      short loc_180039985
0x180039980  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039985  lea     rdx, [rsp+220h+var_1B0]
0x18003998a  mov     rcx, rbx
0x18003998d  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x180039992  nop
0x180039993  lea     rdx, [rsp+220h+var_1C0]
0x180039998  mov     rcx, [rsi]
0x18003999b  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x1800399a0  nop
0x1800399a1  mov     r10, [rsp+220h+var_1C0]
0x1800399a6  test    r10, r10
0x1800399a9  jnz     short loc_1800399D7
0x1800399ab  lea     rdx, [rbp+120h+var_150]
0x1800399af  mov     rcx, rbx
0x1800399b2  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x1800399b7  mov     rdx, rax
0x1800399ba  lea     rcx, [rsp+220h+var_1C0]
0x1800399bf  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x1800399c4  mov     rcx, [rbp+120h+var_150+8]; this
0x1800399c8  test    rcx, rcx
0x1800399cb  jz      short loc_1800399D2
0x1800399cd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800399d2  mov     r10, [rsp+220h+var_1C0]
0x1800399d7  mov     rcx, [rsp+220h+var_1B0]
0x1800399dc  mov     rax, [rcx+68h]
0x1800399e0  cmp     [r10+68h], rax
0x1800399e4  jz      short loc_180039A2D
0x1800399e6  lea     rdx, aScenenodeClone; "SceneNode::Clone() -- source and target"...
0x1800399ed  lea     rcx, [rbp+120h+var_150]
0x1800399f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800399f6  nop
0x1800399f7  lea     rdx, aOnecoreuapWind_43; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800399fe  lea     rcx, [rbp+120h+var_1A0]
0x180039a02  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039a07  mov     [rsp+220h+var_200], 0
0x180039a0c  lea     r9, [rbp+120h+var_150]
0x180039a10  mov     rdx, rax
0x180039a13  lea     rcx, [rbp+120h+pExceptionObject]
0x180039a17  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180039a1c  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180039a23  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x180039a27  call    _CxxThrowException_0
0x180039a2d  cmp     r10, rcx
0x180039a30  setz    cl
0x180039a33  bt      r15d, 11h
0x180039a38  jb      short loc_180039A47
0x180039a3a  test    cl, cl
0x180039a3c  jnz     short loc_180039A47
0x180039a3e  mov     r8, [rbx+170h]
0x180039a45  jmp     short loc_180039A4B
0x180039a47  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039a4b  mov     rdx, rsi
0x180039a4e  lea     rcx, [rbp+120h+var_150]
0x180039a52  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180039a57  mov     r9, rax
0x180039a5a  mov     rdx, rdi
0x180039a5d  mov     rcx, r10
0x180039a60  call    ?AddNode@Scene@Engine@Spectre@@QEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@_KV45@@Z; Spectre::Engine::Scene::AddNode(unsigned __int64,std::shared_ptr<Spectre::Engine::SceneNode>)
0x180039a65  mov     [rsp+220h+var_1E0], 1
0x180039a6d  mov     rcx, [rdi]
0x180039a70  mov     rax, [rbx+1C0h]
0x180039a77  mov     [rcx+1C0h], rax
0x180039a7e  lea     rdx, [rbx+1B0h]
0x180039a85  mov     rcx, [rdi]
0x180039a88  add     rcx, 1B0h
0x180039a8f  call    ??4?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::operator=(std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>> const &)
0x180039a94  lea     rdx, [rbx+190h]
0x180039a9b  mov     rcx, [rdi]
0x180039a9e  add     rcx, 190h
0x180039aa5  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x180039aaa  movsd   xmm0, qword ptr [rbx+0ACh]
0x180039ab2  movsd   [rsp+220h+var_1D0], xmm0
0x180039ab8  mov     eax, [rbx+0B4h]
0x180039abe  mov     [rsp+220h+var_1C8], eax
0x180039ac2  movups  xmm0, xmmword ptr [rbx+9Ch]
0x180039ac9  movdqu  xmmword ptr [rbp+120h+var_150], xmm0
0x180039ace  movsd   xmm1, qword ptr [rbx+90h]
0x180039ad6  movsd   [rsp+220h+var_1F0], xmm1
0x180039adc  mov     eax, [rbx+98h]
0x180039ae2  mov     [rsp+220h+var_1E8], eax
0x180039ae6  lea     r9, [rsp+220h+var_1D0]
0x180039aeb  lea     r8, [rbp+120h+var_150]
0x180039aef  lea     rdx, [rsp+220h+var_1F0]
0x180039af4  mov     rcx, [rdi]
0x180039af7  call    ?SetTransform@SceneNode@Engine@Spectre@@QEAAXUVector3@Math@Utils@3@UQuaternion@563@0@Z; Spectre::Engine::SceneNode::SetTransform(Spectre::Utils::Math::Vector3,Spectre::Utils::Math::Quaternion,Spectre::Utils::Math::Vector3)
0x180039afc  test    r15b, 2
0x180039b00  jz      loc_180039C3E
0x180039b06  mov     dword ptr [rsp+220h+var_1F0], r15d
0x180039b0b  mov     rcx, rbx; this
0x180039b0e  call    ?VerifyReadAccess@SceneNode@Engine@Spectre@@QEBAXXZ; Spectre::Engine::SceneNode::VerifyReadAccess(void)
0x180039b13  mov     r14, [rbx+178h]
0x180039b1a  mov     r12, [rbx+180h]
0x180039b21  cmp     r14, r12
0x180039b24  jz      loc_180039C3E
0x180039b2a  mov     r11, [r14]
0x180039b2d  mov     rax, [r11]
0x180039b30  mov     r10, [rax+50h]
0x180039b34  mov     rdx, rdi
0x180039b37  lea     rcx, [rbp+120h+var_1A0]
0x180039b3b  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180039b40  mov     r9, rax
0x180039b43  lea     r8, [rsp+220h+var_1F0]
0x180039b48  lea     rdx, [rbp+120h+var_150]
0x180039b4c  mov     rcx, r11
0x180039b4f  mov     rax, r10
0x180039b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b57  nop
0x180039b58  cmp     [rbp+120h+var_150], 0
0x180039b5d  jz      short loc_180039B6D
0x180039b5f  lea     rdx, [rbp+120h+var_150]
0x180039b63  mov     rcx, [rdi]
0x180039b66  call    ?AddComponentInternal@SceneNode@Engine@Spectre@@AEAA_NAEBV?$shared_ptr@VComponent@Engine@Spectre@@@std@@@Z; Spectre::Engine::SceneNode::AddComponentInternal(std::shared_ptr<Spectre::Engine::Component> const &)
0x180039b6b  jmp     short loc_180039B74
0x180039b6d  bt      r15d, 10h
0x180039b72  jnb     short loc_180039B88
0x180039b74  mov     rcx, [rbp+120h+var_150+8]; this
0x180039b78  test    rcx, rcx
0x180039b7b  jz      short loc_180039B82
0x180039b7d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039b82  add     r14, 10h
0x180039b86  jmp     short loc_180039B21
0x180039b88  mov     rbx, [r14]
0x180039b8b  mov     rcx, rbx
0x180039b8e  call    cs:__imp___RTtypeid
0x180039b94  lea     rcx, [rax+8]
0x180039b98  lea     rdx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x180039b9f  call    __std_type_info_name
0x180039ba4  mov     rdx, rax
0x180039ba7  lea     rcx, [rbp+120h+var_C0]
0x180039bab  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039bb0  nop
0x180039bb1  mov     r8, rax
0x180039bb4  lea     rdx, aScenenodeClone_0; "SceneNode::Clone() -- component type "
0x180039bbb  lea     rcx, [rbp+120h+var_A0]
0x180039bc2  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180039bc7  nop
0x180039bc8  lea     r8, aWithName; " with name "
0x180039bcf  mov     rdx, rax
0x180039bd2  lea     rcx, [rbp+120h+var_80]
0x180039bd9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180039bde  nop
0x180039bdf  lea     r8, [rbx+18h]
0x180039be3  mov     rdx, rax
0x180039be6  lea     rcx, [rbp+120h+var_60]
0x180039bed  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180039bf2  nop
0x180039bf3  lea     r8, aCouldNotBeClon; " could not be cloned"
0x180039bfa  mov     rdx, rax
0x180039bfd  lea     rcx, [rbp+120h+pExceptionObject]
0x180039c01  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180039c06  mov     rbx, rax
0x180039c09  lea     rdx, aOnecoreuapWind_43; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180039c10  lea     rcx, [rbp+120h+var_170]
0x180039c14  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039c19  mov     [rsp+220h+var_200], 1
0x180039c1e  mov     r9, rbx
0x180039c21  mov     rdx, rax
0x180039c24  lea     rcx, [rbp+120h+var_F8]
0x180039c28  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180039c2d  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180039c34  lea     rcx, [rbp+120h+var_F8]; pExceptionObject
0x180039c38  call    _CxxThrowException_0
0x180039c3e  test    r15b, 1
0x180039c42  jz      short loc_180039C8E
0x180039c44  mov     rcx, rbx; this
0x180039c47  call    ?VerifyReadAccess@SceneNode@Engine@Spectre@@QEBAXXZ; Spectre::Engine::SceneNode::VerifyReadAccess(void)
0x180039c4c  mov     r14, [rbx+20h]
0x180039c50  mov     rbx, [rbx+28h]
0x180039c54  jmp     short loc_180039C89
0x180039c56  mov     r10, [r14]
0x180039c59  mov     rdx, rdi
0x180039c5c  lea     rcx, [rbp+120h+var_1A0]
0x180039c60  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180039c65  mov     r9, rax
0x180039c68  mov     r8d, r15d
0x180039c6b  lea     rdx, [rbp+120h+var_150]
0x180039c6f  mov     rcx, r10
0x180039c72  call    ?Clone@SceneNode@Engine@Spectre@@QEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@IV45@@Z; Spectre::Engine::SceneNode::Clone(uint,std::shared_ptr<Spectre::Engine::SceneNode>)
0x180039c77  mov     rcx, [rbp+120h+var_150+8]; this
0x180039c7b  test    rcx, rcx
0x180039c7e  jz      short loc_180039C85
0x180039c80  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039c85  add     r14, 10h
0x180039c89  cmp     r14, rbx
0x180039c8c  jnz     short loc_180039C56
0x180039c8e  mov     rcx, [rsp+220h+var_1B8]; this
0x180039c93  test    rcx, rcx
0x180039c96  jz      short loc_180039C9E
0x180039c98  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039c9d  nop
0x180039c9e  mov     rcx, [rsp+220h+var_1A8]; this
0x180039ca3  test    rcx, rcx
0x180039ca6  jz      short loc_180039CAE
0x180039ca8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039cad  nop
0x180039cae  mov     rcx, [rsi+8]; this
0x180039cb2  test    rcx, rcx
0x180039cb5  jz      short loc_180039CBC
0x180039cb7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039cbc  mov     rax, rdi
0x180039cbf  mov     rcx, [rbp+120h+var_40]
0x180039cc6  xor     rcx, rsp; StackCookie
0x180039cc9  call    __security_check_cookie
0x180039cce  add     rsp, 1F0h
0x180039cd5  pop     r15
0x180039cd7  pop     r14
0x180039cd9  pop     r12
0x180039cdb  pop     rdi
0x180039cdc  pop     rsi
0x180039cdd  pop     rbx
0x180039cde  pop     rbp
0x180039cdf  retn
```
