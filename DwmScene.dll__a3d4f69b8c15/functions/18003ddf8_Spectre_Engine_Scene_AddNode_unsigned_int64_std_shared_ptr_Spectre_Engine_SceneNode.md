# Spectre::Engine::Scene::AddNode(unsigned __int64,std::shared_ptr<Spectre::Engine::SceneNode>)

- ea: `0x18003ddf8`
- end: `0x18003df47`
- name: `?AddNode@Scene@Engine@Spectre@@QEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@_KV45@@Z`
- size: `335`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180015a30`
- `0x180018df0`
- `0x18003990c`
- `0x18003df50`
- `0x180060c60`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012df8`
- `0x180038ddc`
- `0x18003dcf0`
- `0x18003ddf8`
- `0x18003eb80`

## string_xrefs

- `0x18003de43`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`
- `0x18003de90`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\scene.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Spectre::Engine::Scene::AddNode(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  int v5; // esi
  int v8; // eax
  int v9; // r8d
  int v10; // eax
  int v11; // r8d
  __int64 v12; // rax
  __int64 v13; // rax
  std::_Ref_count_base *v14; // rcx
  _BYTE v16[24]; // [rsp+30h] [rbp-69h] BYREF
  _QWORD *v17; // [rsp+48h] [rbp-51h]
  _BYTE v18[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v19[8]; // [rsp+70h] [rbp-29h] BYREF
  std::_Ref_count_base *v20; // [rsp+78h] [rbp-21h]
  _BYTE pExceptionObject[56]; // [rsp+90h] [rbp-9h] BYREF

  v5 = a3;
  v17 = a4;
  if ( !a3 )
  {
    std::string::string(v19, "Scene::AddNode() -- Unique ID zero is reserved for root-level layer nodes.");
    v8 = std::string::string(
           v18,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v8,
      v9,
      (unsigned int)v19,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  if ( !*a4 )
  {
    std::string::string(v19, "Scene::AddNode() -- A non-null parent must be specified.");
    v10 = std::string::string(
            v18,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\scene.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v10,
      v11,
      (unsigned int)v19,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v12 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v18, a4);
  Spectre::Engine::Scene::GetNodeLayer(a1, v19, v12);
  v13 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          v16,
          v19);
  Spectre::Engine::Scene::AddNode(a1, a2, v5, *(_QWORD *)(*a4 + 368LL), v13);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  v14 = (std::_Ref_count_base *)a4[1];
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  return a2;
}

```

## disassembly

```asm
0x18003ddf8  push    rbp
0x18003ddfa  push    rbx
0x18003ddfb  push    rsi
0x18003ddfc  push    rdi
0x18003ddfd  push    r14
0x18003ddff  lea     rbp, [rsp-37h]
0x18003de04  sub     rsp, 0D0h
0x18003de0b  mov     rax, cs:__security_cookie
0x18003de12  xor     rax, rsp
0x18003de15  mov     [rbp+57h+var_28], rax
0x18003de19  mov     rbx, r9
0x18003de1c  mov     rsi, r8
0x18003de1f  mov     rdi, rdx
0x18003de22  mov     r14, rcx
0x18003de25  mov     [rbp+57h+var_A8], rdx
0x18003de29  mov     [rbp+57h+var_A8], rbx
0x18003de2d  test    r8, r8
0x18003de30  jnz     short loc_18003DE79
0x18003de32  lea     rdx, aSceneAddnodeUn; "Scene::AddNode() -- Unique ID zero is r"...
0x18003de39  lea     rcx, [rbp+57h+var_80]
0x18003de3d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003de42  nop
0x18003de43  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003de4a  lea     rcx, [rbp+57h+var_A0]
0x18003de4e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003de53  mov     byte ptr [rsp+0F0h+var_D0], sil
0x18003de58  lea     r9, [rbp+57h+var_80]
0x18003de5c  mov     rdx, rax
0x18003de5f  lea     rcx, [rbp+57h+pExceptionObject]
0x18003de63  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003de68  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003de6f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003de73  call    _CxxThrowException_0
0x18003de79  cmp     qword ptr [r9], 0
0x18003de7d  jnz     short loc_18003DEC6
0x18003de7f  lea     rdx, aSceneAddnodeAN; "Scene::AddNode() -- A non-null parent m"...
0x18003de86  lea     rcx, [rbp+57h+var_80]
0x18003de8a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003de8f  nop
0x18003de90  lea     rdx, aOnecoreuapWind_21; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003de97  lea     rcx, [rbp+57h+var_A0]
0x18003de9b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003dea0  mov     byte ptr [rsp+0F0h+var_D0], 0
0x18003dea5  lea     r9, [rbp+57h+var_80]
0x18003dea9  mov     rdx, rax
0x18003deac  lea     rcx, [rbp+57h+pExceptionObject]
0x18003deb0  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18003deb5  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18003debc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003dec0  call    _CxxThrowException_0
0x18003dec6  mov     rdx, rbx
0x18003dec9  lea     rcx, [rbp+57h+var_A0]
0x18003decd  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003ded2  mov     r8, rax
0x18003ded5  lea     rdx, [rbp+57h+var_80]
0x18003ded9  mov     rcx, r14
0x18003dedc  call    ?GetNodeLayer@Scene@Engine@Spectre@@QEBA?AV?$shared_ptr@VSceneLayer@Engine@Spectre@@@std@@V?$shared_ptr@VSceneNode@Engine@Spectre@@@5@@Z; Spectre::Engine::Scene::GetNodeLayer(std::shared_ptr<Spectre::Engine::SceneNode>)
0x18003dee1  nop
0x18003dee2  lea     rdx, [rbp+57h+var_80]
0x18003dee6  lea     rcx, [rbp+57h+var_C0]
0x18003deea  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003deef  mov     r9, [rbx]
0x18003def2  mov     [rsp+0F0h+var_D0], rax
0x18003def7  mov     r9, [r9+170h]
0x18003defe  mov     r8, rsi
0x18003df01  mov     rdx, rdi
0x18003df04  mov     rcx, r14
0x18003df07  call    ?AddNode@Scene@Engine@Spectre@@QEAA?AV?$shared_ptr@VSceneNode@Engine@Spectre@@@std@@_K0V?$shared_ptr@VSceneLayer@Engine@Spectre@@@5@@Z; Spectre::Engine::Scene::AddNode(unsigned __int64,unsigned __int64,std::shared_ptr<Spectre::Engine::SceneLayer>)
0x18003df0c  nop
0x18003df0d  mov     rcx, [rbp+57h+var_78]; this
0x18003df11  test    rcx, rcx
0x18003df14  jz      short loc_18003DF1C
0x18003df16  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003df1b  nop
0x18003df1c  mov     rcx, [rbx+8]; this
0x18003df20  test    rcx, rcx
0x18003df23  jz      short loc_18003DF2A
0x18003df25  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003df2a  mov     rax, rdi
0x18003df2d  mov     rcx, [rbp+57h+var_28]
0x18003df31  xor     rcx, rsp; StackCookie
0x18003df34  call    __security_check_cookie
0x18003df39  add     rsp, 0D0h
0x18003df40  pop     r14
0x18003df42  pop     rdi
0x18003df43  pop     rsi
0x18003df44  pop     rbx
0x18003df45  pop     rbp
0x18003df46  retn
```
