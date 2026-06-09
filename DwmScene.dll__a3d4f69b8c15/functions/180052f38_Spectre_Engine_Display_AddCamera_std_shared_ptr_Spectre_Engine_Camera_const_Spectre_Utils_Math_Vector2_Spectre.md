# Spectre::Engine::Display::AddCamera(std::shared_ptr<Spectre::Engine::Camera> const &,Spectre::Utils::Math::Vector2,Spectre::Utils::Math::Vector2,Spectre::Engine::Camera::EViewportMode)

- ea: `0x180052f38`
- end: `0x180053193`
- name: `?AddCamera@Display@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VCamera@Engine@Spectre@@@std@@UVector2@Math@Utils@3@1W4EViewportMode@Camera@23@@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180052efc`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012c58`
- `0x180012c88`
- `0x1800131f8`
- `0x180013798`
- `0x180016324`
- `0x180052740`
- `0x180052b00`
- `0x180052f38`
- `0x180053374`
- `0x1800681a8`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18005315b`
- `msvcp_win!_Mtx_unlock` at `0x18005315b`

## string_xrefs

- `0x180052fff`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\display.cpp`
- `0x180053093`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\display.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall Spectre::Engine::Display::AddCamera(_QWORD *a1, _QWORD *a2, __int64 a3, __int64 a4, int a5)
{
  char v9; // bl
  struct _Mtx_internal_imp_t *v10; // r12
  char v11; // di
  bool v12; // si
  int v13; // eax
  int v14; // r8d
  _QWORD *Scene; // rax
  __int64 v16; // r11
  int v17; // eax
  int v18; // r8d
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v22; // [rsp+38h] [rbp-D0h] BYREF
  std::_Ref_count_base *v23; // [rsp+40h] [rbp-C8h]
  __int64 v24; // [rsp+48h] [rbp-C0h] BYREF
  std::_Ref_count_base *v25; // [rsp+50h] [rbp-B8h]
  _QWORD *v26; // [rsp+58h] [rbp-B0h]
  _BYTE v27[32]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+80h] [rbp-88h] BYREF
  std::_Ref_count_base *v29; // [rsp+88h] [rbp-80h]
  _BYTE pExceptionObject[56]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v31[56]; // [rsp+D8h] [rbp-30h] BYREF

  v9 = 0;
  v10 = (struct _Mtx_internal_imp_t *)(a1 + 16);
  v26 = a1 + 16;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 16));
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(*a2 + 56LL, &v24);
  v11 = 1;
  v12 = 1;
  if ( v24 )
  {
    v9 = 1;
    if ( *(_QWORD *)Spectre::Engine::SceneNode::GetScene(v24, &v28) )
      v12 = 0;
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    if ( v29 )
      std::_Ref_count_base::_Decref(v29);
  }
  if ( v12 )
  {
    std::string::string(&v28, "Cameras added to Displays must be attached to a scene.");
    v13 = std::string::string(
            v27,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\display.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v13, v14, (unsigned int)&v28, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  Spectre::Engine::Display::GetSceneLockless(a1, &v28);
  if ( !v28 || (Scene = (_QWORD *)Spectre::Engine::SceneNode::GetScene(v24, &v22), v9 |= 2u, *Scene == v16) )
    v11 = 0;
  if ( (v9 & 2) != 0 && v23 )
    std::_Ref_count_base::_Decref(v23);
  if ( v11 )
  {
    std::string::string(pExceptionObject, "Displays require that all cameras be in the same scene.");
    v17 = std::string::string(
            v27,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\display.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)v31, v17, v18, (unsigned int)pExceptionObject, 0);
    throw (Spectre::Engine::EngineException *)v31;
  }
  v19 = a1[6];
  if ( v19 == a1[7] )
  {
    std::vector<std::shared_ptr<Spectre::Engine::ShaderPipeline>>::_Emplace_reallocate<std::shared_ptr<Spectre::Engine::ShaderPipeline> const &>(
      a1 + 5,
      a1[6],
      a2);
  }
  else
  {
    std::_Construct_in_place<std::shared_ptr<Spectre::Engine::ResourceLoadedFnc>,std::shared_ptr<Spectre::Engine::ResourceLoadedFnc> const &>(
      v19,
      a2);
    a1[6] += 16LL;
  }
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(&v22, a2);
  v20 = *(_QWORD *)std::map<std::weak_ptr<Spectre::Engine::Camera>,Spectre::Engine::Display::CameraViewport,std::owner_less<std::weak_ptr<Spectre::Engine::Camera>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::Camera> const,Spectre::Engine::Display::CameraViewport>>>::_Try_emplace<std::weak_ptr<Spectre::Engine::Camera>,>(
                     a1 + 11,
                     v27,
                     &v22);
  *(_QWORD *)(v20 + 48) = a3;
  *(_QWORD *)(v20 + 56) = a4;
  *(_DWORD *)(v20 + 64) = a5;
  if ( v23 )
    std::_Ref_count_base::_Decwref(v23);
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  return _Mtx_unlock(v10);
}

```

## disassembly

```asm
0x180052f38  mov     rax, rsp
0x180052f3b  mov     [rax+18h], rbx
0x180052f3f  mov     [rax+20h], rsi
0x180052f43  push    rbp
0x180052f44  push    rdi
0x180052f45  push    r12
0x180052f47  push    r13
0x180052f49  push    r14
0x180052f4b  lea     rbp, [rax-58h]
0x180052f4f  sub     rsp, 130h
0x180052f56  movaps  xmmword ptr [rax-38h], xmm6
0x180052f5a  movaps  xmmword ptr [rax-48h], xmm7
0x180052f5e  mov     rax, cs:__security_cookie
0x180052f65  xor     rax, rsp
0x180052f68  mov     [rbp+50h+var_48], rax
0x180052f6c  mov     r14, rdx
0x180052f6f  mov     r13, rcx
0x180052f72  movq    xmm6, r9
0x180052f77  movq    xmm7, r8
0x180052f7c  xor     ebx, ebx
0x180052f7e  mov     dword ptr [rsp+150h+var_100], ebx
0x180052f82  lea     r12, [rcx+80h]
0x180052f89  mov     [rsp+150h+var_100], r12
0x180052f8e  mov     rcx, r12; this
0x180052f91  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180052f96  nop
0x180052f97  mov     rcx, [r14]
0x180052f9a  add     rcx, 38h ; '8'
0x180052f9e  lea     rdx, [rsp+150h+var_110]
0x180052fa3  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x180052fa8  nop
0x180052fa9  lea     edi, [rbx+1]
0x180052fac  cmp     [rsp+150h+var_110], rbx
0x180052fb1  jz      short loc_180052FCF
0x180052fb3  lea     rdx, [rsp+150h+var_D8]
0x180052fb8  mov     rcx, [rsp+150h+var_110]
0x180052fbd  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x180052fc2  mov     ebx, edi
0x180052fc4  cmp     qword ptr [rax], 0
0x180052fc8  jz      short loc_180052FCF
0x180052fca  xor     sil, sil
0x180052fcd  jmp     short loc_180052FD2
0x180052fcf  mov     sil, dil
0x180052fd2  test    dil, bl
0x180052fd5  jz      short loc_180052FE8
0x180052fd7  and     ebx, 0FFFFFFFEh
0x180052fda  mov     rcx, [rbp+50h+var_D0]; this
0x180052fde  test    rcx, rcx
0x180052fe1  jz      short loc_180052FE8
0x180052fe3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180052fe8  test    sil, sil
0x180052feb  jz      short loc_180053037
0x180052fed  lea     rdx, aCamerasAddedTo; "Cameras added to Displays must be attac"...
0x180052ff4  lea     rcx, [rsp+150h+var_D8]
0x180052ff9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180052ffe  nop
0x180052fff  lea     rdx, aOnecoreuapWind_44; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180053006  lea     rcx, [rsp+150h+var_F8]
0x18005300b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180053010  mov     [rsp+150h+var_130], 0
0x180053015  lea     r9, [rsp+150h+var_D8]
0x18005301a  mov     rdx, rax
0x18005301d  lea     rcx, [rbp+50h+pExceptionObject]
0x180053021  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180053026  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x18005302d  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180053031  call    _CxxThrowException_0
0x180053037  lea     rdx, [rsp+150h+var_D8]
0x18005303c  mov     rcx, r13
0x18005303f  call    ?GetSceneLockless@Display@Engine@Spectre@@AEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::Display::GetSceneLockless(void)
0x180053044  nop
0x180053045  mov     r11, [rsp+150h+var_D8]
0x18005304a  test    r11, r11
0x18005304d  jz      short loc_180053066
0x18005304f  lea     rdx, [rsp+150h+var_120]
0x180053054  mov     rcx, [rsp+150h+var_110]
0x180053059  call    ?GetScene@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VScene@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetScene(void)
0x18005305e  or      ebx, 2
0x180053061  cmp     [rax], r11
0x180053064  jnz     short loc_180053069
0x180053066  xor     dil, dil
0x180053069  test    bl, 2
0x18005306c  jz      short loc_18005307D
0x18005306e  mov     rcx, [rsp+150h+var_118]; this
0x180053073  test    rcx, rcx
0x180053076  jz      short loc_18005307D
0x180053078  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005307d  test    dil, dil
0x180053080  jz      short loc_1800530CA
0x180053082  lea     rdx, aDisplaysRequir; "Displays require that all cameras be in"...
0x180053089  lea     rcx, [rbp+50h+pExceptionObject]
0x18005308d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180053092  nop
0x180053093  lea     rdx, aOnecoreuapWind_44; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18005309a  lea     rcx, [rsp+150h+var_F8]
0x18005309f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800530a4  mov     [rsp+150h+var_130], 0
0x1800530a9  lea     r9, [rbp+50h+pExceptionObject]
0x1800530ad  mov     rdx, rax
0x1800530b0  lea     rcx, [rbp+50h+var_80]
0x1800530b4  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800530b9  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800530c0  lea     rcx, [rbp+50h+var_80]; pExceptionObject
0x1800530c4  call    _CxxThrowException_0
0x1800530ca  mov     rcx, [r13+30h]
0x1800530ce  cmp     rcx, [r13+38h]
0x1800530d2  jz      short loc_1800530E3
0x1800530d4  mov     rdx, r14
0x1800530d7  call    ??$_Construct_in_place@V?$shared_ptr@VResourceLoadedFnc@Engine@Spectre@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VResourceLoadedFnc@Engine@Spectre@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<Spectre::Engine::ResourceLoadedFnc>,std::shared_ptr<Spectre::Engine::ResourceLoadedFnc> const &>(std::shared_ptr<Spectre::Engine::ResourceLoadedFnc> &,std::shared_ptr<Spectre::Engine::ResourceLoadedFnc> const &)
0x1800530dc  add     qword ptr [r13+30h], 10h
0x1800530e1  jmp     short loc_1800530F2
0x1800530e3  mov     r8, r14
0x1800530e6  mov     rdx, rcx
0x1800530e9  lea     rcx, [r13+28h]
0x1800530ed  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@@?$vector@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VShaderPipeline@Engine@Spectre@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Spectre::Engine::ShaderPipeline>>::_Emplace_reallocate<std::shared_ptr<Spectre::Engine::ShaderPipeline> const &>(std::shared_ptr<Spectre::Engine::ShaderPipeline> * const,std::shared_ptr<Spectre::Engine::ShaderPipeline> const &)
0x1800530f2  mov     rdx, r14
0x1800530f5  lea     rcx, [rsp+150h+var_120]
0x1800530fa  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x1800530ff  nop
0x180053100  lea     rcx, [r13+58h]
0x180053104  lea     r8, [rsp+150h+var_120]
0x180053109  lea     rdx, [rsp+150h+var_F8]
0x18005310e  call    ??$_Try_emplace@V?$weak_ptr@VCamera@Engine@Spectre@@@std@@$$V@?$map@V?$weak_ptr@VCamera@Engine@Spectre@@@std@@UCameraViewport@Display@Engine@Spectre@@U?$owner_less@V?$weak_ptr@VCamera@Engine@Spectre@@@std@@@2@V?$allocator@U?$pair@$$CBV?$weak_ptr@VCamera@Engine@Spectre@@@std@@UCameraViewport@Display@Engine@Spectre@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$weak_ptr@VCamera@Engine@Spectre@@@std@@UCameraViewport@Display@Engine@Spectre@@@std@@PEAX@std@@_N@1@$$QEAV?$weak_ptr@VCamera@Engine@Spectre@@@1@@Z; std::map<std::weak_ptr<Spectre::Engine::Camera>,Spectre::Engine::Display::CameraViewport,std::owner_less<std::weak_ptr<Spectre::Engine::Camera>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::Camera> const,Spectre::Engine::Display::CameraViewport>>>::_Try_emplace<std::weak_ptr<Spectre::Engine::Camera>,>(std::weak_ptr<Spectre::Engine::Camera> &&)
0x180053113  mov     rcx, [rax]
0x180053116  movsd   qword ptr [rcx+30h], xmm7
0x18005311b  movsd   qword ptr [rcx+38h], xmm6
0x180053120  mov     eax, [rbp+50h+arg_20]
0x180053126  mov     [rcx+40h], eax
0x180053129  mov     rcx, [rsp+150h+var_118]; this
0x18005312e  test    rcx, rcx
0x180053131  jz      short loc_180053139
0x180053133  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180053138  nop
0x180053139  mov     rcx, [rbp+50h+var_D0]; this
0x18005313d  test    rcx, rcx
0x180053140  jz      short loc_180053148
0x180053142  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053147  nop
0x180053148  mov     rcx, [rsp+150h+var_108]; this
0x18005314d  test    rcx, rcx
0x180053150  jz      short loc_180053158
0x180053152  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053157  nop
0x180053158  mov     rcx, r12; _Mtx_t
0x18005315b  call    cs:__imp__Mtx_unlock
0x180053161  mov     rcx, [rbp+50h+var_48]
0x180053165  xor     rcx, rsp; StackCookie
0x180053168  call    __security_check_cookie
0x18005316d  lea     r11, [rsp+150h+var_20]
0x180053175  mov     rbx, [r11+40h]
0x180053179  mov     rsi, [r11+48h]
0x18005317d  movaps  xmm6, xmmword ptr [r11-10h]
0x180053182  movaps  xmm7, xmmword ptr [r11-20h]
0x180053187  mov     rsp, r11
0x18005318a  pop     r14
0x18005318c  pop     r13
0x18005318e  pop     r12
0x180053190  pop     rdi
0x180053191  pop     rbp
0x180053192  retn
```
