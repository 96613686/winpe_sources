# Spectre::Engine::ShaderFamily::CreateMaterial(void)

- ea: `0x18005adf8`
- end: `0x18005afd5`
- name: `?CreateMaterial@ShaderFamily@Engine@Spectre@@QEAA?AV?$shared_ptr@VMaterial@Engine@Spectre@@@std@@XZ`
- size: `477`
- prototype: ``
- caller_count: `5`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180018f20`
- `0x180060c60`
- `0x18006b588`
- `0x18008b0f0`
- `0x180091154`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x1800120ec`
- `0x180012d98`
- `0x180012df8`
- `0x180016324`
- `0x180028d0c`
- `0x1800293c0`
- `0x180038ddc`
- `0x180040a6c`
- `0x18004176c`
- `0x180059af8`
- `0x180059e30`
- `0x18005adf8`

## string_xrefs

- `0x18005ae34`: `ShaderFamily::CreateMaterial() -- materials cannot be created until shader family declaration is complete`
- `0x18005ae45`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderfamily.cpp`
- `0x18005af9f`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderfamily.cpp`
- `0x18005af8e`: `ShaderFamily::CreateMaterial() -- materials cannot be created until valid material layout is specified (non-null and complete)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Spectre::Engine::ShaderFamily::CreateMaterial(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  int v5; // r8d
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  int v10; // eax
  int v11; // r8d
  _BYTE v12[8]; // [rsp+38h] [rbp-61h] BYREF
  std::_Ref_count_base *v13; // [rsp+40h] [rbp-59h]
  __int64 v14; // [rsp+48h] [rbp-51h] BYREF
  std::_Ref_count_base *v15; // [rsp+50h] [rbp-49h]
  _BYTE v16[32]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD *v17; // [rsp+78h] [rbp-21h]
  _BYTE v18[8]; // [rsp+80h] [rbp-19h] BYREF
  std::_Ref_count_base *v19; // [rsp+88h] [rbp-11h]
  _BYTE pExceptionObject[56]; // [rsp+A0h] [rbp+7h] BYREF

  v17 = a2;
  if ( *(_DWORD *)(a1 + 432) != 1 )
  {
    std::string::string(
      v18,
      "ShaderFamily::CreateMaterial() -- materials cannot be created until shader family declaration is complete");
    v4 = std::string::string(
           v16,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderfamily.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v4,
      v5,
      (unsigned int)v18,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
    &v14,
    a1 + 128);
  if ( !v14 || *(_DWORD *)(v14 + 1168) != 1 )
  {
    std::string::string(
      v18,
      "ShaderFamily::CreateMaterial() -- materials cannot be created until valid material layout is specified (non-null and complete)");
    v10 = std::string::string(
            v16,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderfamily.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v10,
      v11,
      (unsigned int)v18,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  Spectre::Engine::Engine::CreateResource<Spectre::Engine::Material,>(*(_QWORD *)(*(_QWORD *)(a1 + 440) + 18688LL), a2);
  v6 = *a2;
  if ( *a2 )
  {
    v7 = std::enable_shared_from_this<Spectre::Engine::Component>::shared_from_this(a1, v12);
    Spectre::Engine::Material::AttachShaderFamily(v6, v7);
    std::unique_lock<Spectre::Engine::Mutex>::unique_lock<Spectre::Engine::Mutex>(v18, a1 + 472);
    std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v12, a2);
    std::_Tree<std::_Tset_traits<std::weak_ptr<Spectre::Engine::Material>,std::owner_less<std::weak_ptr<Spectre::Engine::Material>>,std::allocator<std::weak_ptr<Spectre::Engine::Material>>,0>>::_Emplace<std::weak_ptr<Spectre::Engine::Material>>(
      a1 + 480,
      v16,
      v12);
    if ( v13 )
      std::_Ref_count_base::_Decwref(v13);
    std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v18);
  }
  v8 = std::enable_shared_from_this<Spectre::Engine::Scene>::shared_from_this(*a2 + 96LL, v18);
  std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(*a2 + 216LL, v8);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  return a2;
}

```

## disassembly

```asm
0x18005adf8  mov     [rsp-8+arg_10], rbx
0x18005adfd  push    rbp
0x18005adfe  push    rsi
0x18005adff  push    rdi
0x18005ae00  lea     rbp, [rsp-47h]
0x18005ae05  sub     rsp, 0E0h
0x18005ae0c  mov     rax, cs:__security_cookie
0x18005ae13  xor     rax, rsp
0x18005ae16  mov     [rbp+57h+var_18], rax
0x18005ae1a  mov     rbx, rdx
0x18005ae1d  mov     rdi, rcx
0x18005ae20  mov     [rbp+57h+var_78], rdx
0x18005ae24  mov     [rbp+57h+var_C0], 0
0x18005ae2b  cmp     dword ptr [rcx+1B0h], 1
0x18005ae32  jz      short loc_18005AE7B
0x18005ae34  lea     rdx, aShaderfamilyCr_2; "ShaderFamily::CreateMaterial() -- mater"...
0x18005ae3b  lea     rcx, [rbp+57h+var_70]
0x18005ae3f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005ae44  nop
0x18005ae45  lea     rdx, aOnecoreuapWind_45; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18005ae4c  lea     rcx, [rbp+57h+var_98]
0x18005ae50  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005ae55  mov     [rsp+0F0h+var_D0], 0
0x18005ae5a  lea     r9, [rbp+57h+var_70]
0x18005ae5e  mov     rdx, rax
0x18005ae61  lea     rcx, [rbp+57h+pExceptionObject]
0x18005ae65  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18005ae6a  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18005ae71  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005ae75  call    _CxxThrowException_0
0x18005ae7b  lea     rdx, [rcx+80h]
0x18005ae82  lea     rcx, [rbp+57h+var_A8]
0x18005ae86  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18005ae8b  nop
0x18005ae8c  mov     rax, [rbp+57h+var_A8]
0x18005ae90  test    rax, rax
0x18005ae93  jz      loc_18005AF8E
0x18005ae99  cmp     dword ptr [rax+490h], 1
0x18005aea0  jnz     loc_18005AF8E
0x18005aea6  mov     rcx, [rdi+1B8h]
0x18005aead  mov     rdx, rbx
0x18005aeb0  mov     rcx, [rcx+4900h]
0x18005aeb7  call    ??$CreateResource@VMaterial@Engine@Spectre@@$$V@Engine@0Spectre@@QEAA?AV?$shared_ptr@VMaterial@Engine@Spectre@@@std@@W4ResourceDevicePolicy@01@@Z; Spectre::Engine::Engine::CreateResource<Spectre::Engine::Material,>(Spectre::Engine::ResourceDevicePolicy)
0x18005aebc  mov     [rbp+57h+var_C0], 3
0x18005aec3  mov     rsi, [rbx]
0x18005aec6  test    rsi, rsi
0x18005aec9  jz      short loc_18005AF2D
0x18005aecb  lea     rdx, [rbp+57h+var_B8]
0x18005aecf  mov     rcx, rdi
0x18005aed2  call    ?shared_from_this@?$enable_shared_from_this@VComponent@Engine@Spectre@@@std@@QEAA?AV?$shared_ptr@VComponent@Engine@Spectre@@@2@XZ; std::enable_shared_from_this<Spectre::Engine::Component>::shared_from_this(void)
0x18005aed7  mov     rdx, rax
0x18005aeda  mov     rcx, rsi
0x18005aedd  call    ?AttachShaderFamily@Material@Engine@Spectre@@AEAAXV?$shared_ptr@VShaderFamily@Engine@Spectre@@@std@@@Z; Spectre::Engine::Material::AttachShaderFamily(std::shared_ptr<Spectre::Engine::ShaderFamily>)
0x18005aee2  lea     rdx, [rdi+1D8h]
0x18005aee9  lea     rcx, [rbp+57h+var_70]
0x18005aeed  call    ??0?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@AEAVMutex@Engine@Spectre@@@Z; std::unique_lock<Spectre::Engine::Mutex>::unique_lock<Spectre::Engine::Mutex>(Spectre::Engine::Mutex &)
0x18005aef2  nop
0x18005aef3  mov     rdx, rbx
0x18005aef6  lea     rcx, [rbp+57h+var_B8]
0x18005aefa  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x18005aeff  nop
0x18005af00  lea     rcx, [rdi+1E0h]
0x18005af07  lea     r8, [rbp+57h+var_B8]
0x18005af0b  lea     rdx, [rbp+57h+var_98]
0x18005af0f  call    ??$_Emplace@V?$weak_ptr@VMaterial@Engine@Spectre@@@std@@@?$_Tree@V?$_Tset_traits@V?$weak_ptr@VMaterial@Engine@Spectre@@@std@@U?$owner_less@V?$weak_ptr@VMaterial@Engine@Spectre@@@std@@@2@V?$allocator@V?$weak_ptr@VMaterial@Engine@Spectre@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$weak_ptr@VMaterial@Engine@Spectre@@@std@@PEAX@std@@_N@1@$$QEAV?$weak_ptr@VMaterial@Engine@Spectre@@@1@@Z; std::_Tree<std::_Tset_traits<std::weak_ptr<Spectre::Engine::Material>,std::owner_less<std::weak_ptr<Spectre::Engine::Material>>,std::allocator<std::weak_ptr<Spectre::Engine::Material>>,0>>::_Emplace<std::weak_ptr<Spectre::Engine::Material>>(std::weak_ptr<Spectre::Engine::Material> &&)
0x18005af14  nop
0x18005af15  mov     rcx, [rbp+57h+var_B0]; this
0x18005af19  test    rcx, rcx
0x18005af1c  jz      short loc_18005AF24
0x18005af1e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18005af23  nop
0x18005af24  lea     rcx, [rbp+57h+var_70]
0x18005af28  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x18005af2d  mov     rcx, [rbx]
0x18005af30  add     rcx, 60h ; '`'
0x18005af34  lea     rdx, [rbp+57h+var_70]
0x18005af38  call    ?shared_from_this@?$enable_shared_from_this@VScene@Engine@Spectre@@@std@@QEAA?AV?$shared_ptr@VScene@Engine@Spectre@@@2@XZ; std::enable_shared_from_this<Spectre::Engine::Scene>::shared_from_this(void)
0x18005af3d  mov     rcx, [rbx]
0x18005af40  add     rcx, 0D8h
0x18005af47  mov     rdx, rax
0x18005af4a  call    ??$?4VMaterial@Engine@Spectre@@$0A@@?$weak_ptr@VMaterial@Engine@Spectre@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VMaterial@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(std::shared_ptr<Spectre::Engine::Material> const &)
0x18005af4f  mov     rcx, [rbp+57h+var_68]; this
0x18005af53  test    rcx, rcx
0x18005af56  jz      short loc_18005AF5E
0x18005af58  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005af5d  nop
0x18005af5e  mov     rcx, [rbp+57h+var_A0]; this
0x18005af62  test    rcx, rcx
0x18005af65  jz      short loc_18005AF6C
0x18005af67  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005af6c  mov     rax, rbx
0x18005af6f  mov     rcx, [rbp+57h+var_18]
0x18005af73  xor     rcx, rsp; StackCookie
0x18005af76  call    __security_check_cookie
0x18005af7b  mov     rbx, [rsp+0F0h+arg_10]
0x18005af83  add     rsp, 0E0h
0x18005af8a  pop     rdi
0x18005af8b  pop     rsi
0x18005af8c  pop     rbp
0x18005af8d  retn
0x18005af8e  lea     rdx, aShaderfamilyCr_1; "ShaderFamily::CreateMaterial() -- mater"...
0x18005af95  lea     rcx, [rbp+57h+var_70]
0x18005af99  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005af9e  nop
0x18005af9f  lea     rdx, aOnecoreuapWind_45; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18005afa6  lea     rcx, [rbp+57h+var_98]
0x18005afaa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005afaf  mov     [rsp+0F0h+var_D0], 0
0x18005afb4  lea     r9, [rbp+57h+var_70]
0x18005afb8  mov     rdx, rax
0x18005afbb  lea     rcx, [rbp+57h+pExceptionObject]
0x18005afbf  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18005afc4  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18005afcb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005afcf  call    _CxxThrowException_0
```
