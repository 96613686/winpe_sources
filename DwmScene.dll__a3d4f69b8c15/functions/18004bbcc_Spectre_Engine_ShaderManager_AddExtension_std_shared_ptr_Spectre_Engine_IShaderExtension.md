# Spectre::Engine::ShaderManager::AddExtension(std::shared_ptr<Spectre::Engine::IShaderExtension>)

- ea: `0x18004bbcc`
- end: `0x18004be8a`
- name: `?AddExtension@ShaderManager@Engine@Spectre@@QEAAXV?$shared_ptr@VIShaderExtension@Engine@Spectre@@@std@@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800333b8`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x1800120ec`
- `0x180012ba8`
- `0x180012df8`
- `0x180014280`
- `0x180018318`
- `0x18001c630`
- `0x18001c720`
- `0x18001ca64`
- `0x18001cbec`
- `0x180028f40`
- `0x180034d7c`
- `0x180038ddc`
- `0x18004a914`
- `0x18004bbcc`
- `0x18004cda0`
- `0x18005ad30`
- `0x18005b9c8`

## string_xrefs

- `0x18004bc15`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004bcda`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004bcb3`: `ShaderManager::AddExtension() -- Extension with name '`
- `0x18004bcc4`: `' is already installed`
- `0x18004bc04`: `ShaderManager::AddExtension() -- Extension passed to function cannot be null`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Spectre::Engine::ShaderManager::AddExtension(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdx
  int v5; // eax
  int v6; // r8d
  __int64 v7; // r14
  __int64 v8; // rdi
  __int64 v9; // rcx
  bool v10; // di
  __int64 v11; // rax
  int v12; // ebx
  int v13; // eax
  int v14; // r8d
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  std::_Ref_count_base *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // edi
  __int64 v22; // rdx
  __int64 v23; // rax
  std::_Ref_count_base *v24; // rcx
  _BYTE v25[16]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h]
  _QWORD *v31; // [rsp+80h] [rbp-80h]
  _BYTE v32[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v33[32]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 pExceptionObject; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v35; // [rsp+D0h] [rbp-30h]
  _BYTE v36[56]; // [rsp+100h] [rbp+0h] BYREF

  v31 = a2;
  v4 = *a2;
  if ( !v4 )
  {
    std::string::string(v32, "ShaderManager::AddExtension() -- Extension passed to function cannot be null");
    v5 = std::string::string(
           v25,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)&pExceptionObject,
      v5,
      v6,
      (unsigned int)v32,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)&pExceptionObject;
  }
  std::string::string(v33, v4 + 24);
  v7 = std::string::string(v32, v33);
  std::_Tree<std::_Tmap_traits<std::string,enum Spectre::Engine::ShaderProperty,std::less<std::string>,std::allocator<std::pair<std::string const,enum Spectre::Engine::ShaderProperty>>,0>>::_Find_lower_bound<std::string>(
    a1 + 18592,
    v25,
    v7);
  v8 = v26;
  v10 = !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::string,Trace::LevelSettings *,std::less<std::string>,std::allocator<std::pair<std::string const,Trace::LevelSettings *>>,0>>::_Lower_bound_duplicate<std::string>(
                            v9,
                            v26,
                            v7)
     || v8 == *(_QWORD *)(a1 + 18592);
  std::string::_Tidy_deallocate(v7);
  if ( !v10 )
  {
    v11 = std::operator+<char>(v32, "ShaderManager::AddExtension() -- Extension with name '", v33);
    v12 = std::operator+<char>(&pExceptionObject, v11, "' is already installed");
    v13 = std::string::string(
            v25,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v36, v13, v14, v12, 0);
    throw (Spectre::Engine::EngineInvalidArgException *)v36;
  }
  Spectre::Engine::IShaderExtension::OnInstall(*a2, *(_QWORD *)(a1 + 18688), a1, a1 + 18664);
  v15 = *(_QWORD *)std::map<std::string,std::shared_ptr<Spectre::Engine::ShaderFamily>>::_Try_emplace<std::string const &,>(
                     a1 + 18592,
                     v25,
                     v33);
  v16 = *a2;
  v17 = a2[1];
  *a2 = 0;
  a2[1] = 0;
  *(_QWORD *)(v15 + 64) = v16;
  v18 = *(std::_Ref_count_base **)(v15 + 72);
  *(_QWORD *)(v15 + 72) = v17;
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v19 = std::string::string(v25, v33);
  Spectre::Engine::ShaderManager::GetShaderFamily(a1, &pExceptionObject, v19);
  Spectre::Engine::Engine::SafeGetDeviceList(*(_QWORD *)(a1 + 18688), &v29);
  v20 = v29;
  if ( (v30 - v29) >> 4 )
  {
    v21 = 0;
    v22 = 0;
    do
    {
      std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
        &v27,
        v20 + 16 * v22);
      if ( *(_DWORD *)(v27 + 244) )
      {
        Spectre::Engine::Lockable::GetExclusiveLock(v27 + 24, v25);
        v23 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
                v32,
                &v27);
        Spectre::Engine::ShaderFamily::AttachDevice(pExceptionObject, v23);
        std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v25);
      }
      if ( v28 )
        std::_Ref_count_base::_Decref(v28);
      ++v21;
      v20 = v29;
      v22 = v21;
    }
    while ( v21 < (unsigned __int64)((v30 - v29) >> 4) );
  }
  std::vector<std::shared_ptr<Spectre::Engine::LightProbe>>::_Tidy(&v29);
  if ( v35 )
    std::_Ref_count_base::_Decref(v35);
  std::string::_Tidy_deallocate(v33);
  v24 = (std::_Ref_count_base *)a2[1];
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
}

```

## disassembly

```asm
0x18004bbcc  mov     [rsp-8+arg_10], rbx
0x18004bbd1  push    rbp
0x18004bbd2  push    rsi
0x18004bbd3  push    rdi
0x18004bbd4  push    r14
0x18004bbd6  push    r15
0x18004bbd8  lea     rbp, [rsp-40h]
0x18004bbdd  sub     rsp, 140h
0x18004bbe4  mov     rax, cs:__security_cookie
0x18004bbeb  xor     rax, rsp
0x18004bbee  mov     [rbp+60h+var_28], rax
0x18004bbf2  mov     rbx, rdx
0x18004bbf5  mov     rsi, rcx
0x18004bbf8  mov     [rbp+60h+var_E0], rdx
0x18004bbfc  mov     rdx, [rdx]
0x18004bbff  test    rdx, rdx
0x18004bc02  jnz     short loc_18004BC4C
0x18004bc04  lea     rdx, aShadermanagerA_0; "ShaderManager::AddExtension() -- Extens"...
0x18004bc0b  lea     rcx, [rbp+60h+var_D8]
0x18004bc0f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004bc14  nop
0x18004bc15  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004bc1c  lea     rcx, [rsp+160h+var_128]
0x18004bc21  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004bc26  mov     [rsp+160h+var_140], 0
0x18004bc2b  lea     r9, [rbp+60h+var_D8]
0x18004bc2f  mov     rdx, rax
0x18004bc32  lea     rcx, [rbp+60h+pExceptionObject]
0x18004bc36  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004bc3b  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004bc42  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18004bc46  call    _CxxThrowException_0
0x18004bc4c  add     rdx, 18h
0x18004bc50  lea     rcx, [rbp+60h+var_B8]
0x18004bc54  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18004bc59  nop
0x18004bc5a  lea     rdx, [rbp+60h+var_B8]
0x18004bc5e  lea     rcx, [rbp+60h+var_D8]
0x18004bc62  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18004bc67  mov     r14, rax
0x18004bc6a  lea     r15, [rsi+48A0h]
0x18004bc71  mov     r8, rax
0x18004bc74  lea     rdx, [rsp+160h+var_128]
0x18004bc79  mov     rcx, r15
0x18004bc7c  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@Engine@Spectre@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@Engine@Spectre@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@Engine@Spectre@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,Spectre::Engine::ShaderProperty,std::less<std::string>,std::allocator<std::pair<std::string const,Spectre::Engine::ShaderProperty>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18004bc81  mov     r8, r14
0x18004bc84  mov     rdi, [rsp+160h+var_118]
0x18004bc89  mov     rdx, rdi
0x18004bc8c  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVLevelSettings@Trace@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVLevelSettings@Trace@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVLevelSettings@Trace@@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,Trace::LevelSettings *,std::less<std::string>,std::allocator<std::pair<std::string const,Trace::LevelSettings *>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,Trace::LevelSettings *>,void *> * const,std::string const &)
0x18004bc91  test    al, al
0x18004bc93  jz      short loc_18004BC9F
0x18004bc95  cmp     rdi, [r15]
0x18004bc98  jz      short loc_18004BC9F
0x18004bc9a  xor     dil, dil
0x18004bc9d  jmp     short loc_18004BCA2
0x18004bc9f  mov     dil, 1
0x18004bca2  mov     rcx, r14
0x18004bca5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004bcaa  test    dil, dil
0x18004bcad  jnz     short loc_18004BD10
0x18004bcaf  lea     r8, [rbp+60h+var_B8]
0x18004bcb3  lea     rdx, aShadermanagerA; "ShaderManager::AddExtension() -- Extens"...
0x18004bcba  lea     rcx, [rbp+60h+var_D8]
0x18004bcbe  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18004bcc3  nop
0x18004bcc4  lea     r8, aIsAlreadyInsta; "' is already installed"
0x18004bccb  mov     rdx, rax
0x18004bcce  lea     rcx, [rbp+60h+pExceptionObject]
0x18004bcd2  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18004bcd7  mov     rbx, rax
0x18004bcda  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004bce1  lea     rcx, [rsp+160h+var_128]
0x18004bce6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004bceb  mov     [rsp+160h+var_140], dil
0x18004bcf0  mov     r9, rbx
0x18004bcf3  mov     rdx, rax
0x18004bcf6  lea     rcx, [rbp+60h+var_60]
0x18004bcfa  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004bcff  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004bd06  lea     rcx, [rbp+60h+var_60]; pExceptionObject
0x18004bd0a  call    _CxxThrowException_0
0x18004bd10  lea     r9, [rsi+48E8h]
0x18004bd17  mov     r8, rsi
0x18004bd1a  mov     rdx, [rsi+4900h]
0x18004bd21  mov     rcx, [rbx]
0x18004bd24  call    ?OnInstall@IShaderExtension@Engine@Spectre@@QEAAXPEAV223@PEAVShaderManager@23@AEBV?$vector@W4EShaderModel@Engine@Spectre@@V?$allocator@W4EShaderModel@Engine@Spectre@@@std@@@std@@@Z; Spectre::Engine::IShaderExtension::OnInstall(Spectre::Engine::Engine *,Spectre::Engine::ShaderManager *,std::vector<Spectre::Engine::EShaderModel> const &)
0x18004bd29  lea     r8, [rbp+60h+var_B8]
0x18004bd2d  lea     rdx, [rsp+160h+var_128]
0x18004bd32  mov     rcx, r15
0x18004bd35  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderFamily@Engine@Spectre@@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderFamily@Engine@Spectre@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderFamily@Engine@Spectre@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::shared_ptr<Spectre::Engine::ShaderFamily>>::_Try_emplace<std::string const &,>(std::string const &)
0x18004bd3a  mov     r8, [rax]
0x18004bd3d  mov     rax, [rbx]
0x18004bd40  mov     rdx, [rbx+8]
0x18004bd44  mov     qword ptr [rbx], 0
0x18004bd4b  mov     qword ptr [rbx+8], 0
0x18004bd53  mov     [r8+40h], rax
0x18004bd57  mov     rcx, [r8+48h]; this
0x18004bd5b  mov     [r8+48h], rdx
0x18004bd5f  test    rcx, rcx
0x18004bd62  jz      short loc_18004BD69
0x18004bd64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004bd69  lea     rdx, [rbp+60h+var_B8]
0x18004bd6d  lea     rcx, [rsp+160h+var_128]
0x18004bd72  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18004bd77  mov     r8, rax
0x18004bd7a  lea     rdx, [rbp+60h+pExceptionObject]
0x18004bd7e  mov     rcx, rsi
0x18004bd81  call    ?GetShaderFamily@ShaderManager@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderFamily@Engine@Spectre@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Spectre::Engine::ShaderManager::GetShaderFamily(std::string)
0x18004bd86  nop
0x18004bd87  lea     rdx, [rsp+160h+var_F8]
0x18004bd8c  mov     rcx, [rsi+4900h]
0x18004bd93  call    ?SafeGetDeviceList@Engine@1Spectre@@QEAA?AV?$vector@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@@std@@XZ; Spectre::Engine::Engine::SafeGetDeviceList(void)
0x18004bd98  nop
0x18004bd99  mov     rcx, [rsp+160h+var_F8]
0x18004bd9e  mov     rax, [rsp+160h+var_F0]
0x18004bda3  sub     rax, rcx
0x18004bda6  sar     rax, 4
0x18004bdaa  test    rax, rax
0x18004bdad  jz      loc_18004BE35
0x18004bdb3  xor     edi, edi
0x18004bdb5  xor     edx, edx
0x18004bdb7  shl     rdx, 4
0x18004bdbb  add     rdx, rcx
0x18004bdbe  lea     rcx, [rsp+160h+var_108]
0x18004bdc3  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18004bdc8  nop
0x18004bdc9  mov     rcx, [rsp+160h+var_108]
0x18004bdce  cmp     dword ptr [rcx+0F4h], 0
0x18004bdd5  jz      short loc_18004BE0C
0x18004bdd7  add     rcx, 18h
0x18004bddb  lea     rdx, [rsp+160h+var_128]
0x18004bde0  call    ?GetExclusiveLock@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLock(void)
0x18004bde5  nop
0x18004bde6  lea     rdx, [rsp+160h+var_108]
0x18004bdeb  lea     rcx, [rbp+60h+var_D8]
0x18004bdef  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18004bdf4  mov     rdx, rax
0x18004bdf7  mov     rcx, [rbp+60h+pExceptionObject]
0x18004bdfb  call    ?AttachDevice@ShaderFamily@Engine@Spectre@@QEAAXV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z; Spectre::Engine::ShaderFamily::AttachDevice(std::shared_ptr<Spectre::Engine::RenderDevice>)
0x18004be00  nop
0x18004be01  lea     rcx, [rsp+160h+var_128]
0x18004be06  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x18004be0b  nop
0x18004be0c  mov     rcx, [rsp+160h+var_100]; this
0x18004be11  test    rcx, rcx
0x18004be14  jz      short loc_18004BE1B
0x18004be16  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004be1b  inc     edi
0x18004be1d  mov     rcx, [rsp+160h+var_F8]
0x18004be22  mov     edx, edi
0x18004be24  mov     rax, [rsp+160h+var_F0]
0x18004be29  sub     rax, rcx
0x18004be2c  sar     rax, 4
0x18004be30  cmp     rdx, rax
0x18004be33  jb      short loc_18004BDB7
0x18004be35  lea     rcx, [rsp+160h+var_F8]
0x18004be3a  call    ?_Tidy@?$vector@V?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Spectre::Engine::LightProbe>>::_Tidy(void)
0x18004be3f  nop
0x18004be40  mov     rcx, [rbp+60h+var_90]; this
0x18004be44  test    rcx, rcx
0x18004be47  jz      short loc_18004BE4F
0x18004be49  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004be4e  nop
0x18004be4f  lea     rcx, [rbp+60h+var_B8]
0x18004be53  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004be58  nop
0x18004be59  mov     rcx, [rbx+8]; this
0x18004be5d  test    rcx, rcx
0x18004be60  jz      short loc_18004BE67
0x18004be62  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004be67  mov     rcx, [rbp+60h+var_28]
0x18004be6b  xor     rcx, rsp; StackCookie
0x18004be6e  call    __security_check_cookie
0x18004be73  mov     rbx, [rsp+160h+arg_10]
0x18004be7b  add     rsp, 140h
0x18004be82  pop     r15
0x18004be84  pop     r14
0x18004be86  pop     rdi
0x18004be87  pop     rsi
0x18004be88  pop     rbp
0x18004be89  retn
```
