# Spectre::Engine::MeshInstance::CloneInternal(std::shared_ptr<Spectre::Engine::Component>,uint const &)

- ea: `0x180048460`
- end: `0x1800486a3`
- name: `?CloneInternal@MeshInstance@Engine@Spectre@@EEBAXV?$shared_ptr@VComponent@Engine@Spectre@@@std@@AEBI@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180048380`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012df8`
- `0x180013664`
- `0x1800150fc`
- `0x1800293c0`
- `0x1800475a4`
- `0x180047a48`
- `0x180048460`
- `0x180077f70`

## string_xrefs

- `0x1800484c5`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\meshinstance.cpp`
- `0x18004853e`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\meshinstance.cpp`
- `0x180048592`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\meshinstance.cpp`
- `0x1800485ec`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\meshinstance.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Spectre::Engine::MeshInstance::CloneInternal(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // r8
  std::_Ref_count_base *v16; // rcx
  __int64 v17; // [rsp+38h] [rbp-61h] BYREF
  std::_Ref_count_base *v18; // [rsp+40h] [rbp-59h]
  __int64 v19; // [rsp+48h] [rbp-51h]
  _BYTE v20[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+90h] [rbp-9h] BYREF

  v19 = a2;
  v6 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(&v17, a2);
  Spectre::Engine::Component::CloneInternal(a1, v6);
  std::dynamic_pointer_cast<Spectre::Engine::MeshInstance,Spectre::Engine::Component>(&v17, a2);
  if ( (*a3 & 8) != 0 )
  {
    std::string::string(
      v21,
      "MeshInstance::CloneInternal() -- material cloning not yet supported (reserved for future use)");
    v7 = std::string::string(
           v20,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\meshinstance.cpp");
    Spectre::Engine::EngineNotImplException::EngineNotImplException(pExceptionObject, v7, v8, v21);
    throw (Spectre::Engine::EngineNotImplException *)pExceptionObject;
  }
  v9 = v17;
  if ( v17 + 104 != a1 + 104 )
    std::vector<Spectre::Engine::MeshInstance::MaterialInfo>::_Assign_counted_range<Spectre::Engine::MeshInstance::MaterialInfo *>(
      v17 + 104,
      *(_QWORD *)(a1 + 104),
      0x2E8BA2E8BA2E8BA3LL * ((__int64)(*(_QWORD *)(a1 + 112) - *(_QWORD *)(a1 + 104)) >> 3));
  if ( (*a3 & 4) != 0 )
  {
    std::string::string(
      v20,
      "MeshInstance::CloneInternal() -- mesh cloning not yet supported (reserved for future use)");
    v10 = std::string::string(
            v21,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\meshinstance.cpp");
    Spectre::Engine::EngineNotImplException::EngineNotImplException(pExceptionObject, v10, v11, v20);
    throw (Spectre::Engine::EngineNotImplException *)pExceptionObject;
  }
  std::shared_ptr<Spectre::Engine::Light>::operator=(v9 + 88, a1 + 88);
  if ( (*a3 & 0x10) != 0 )
  {
    std::string::string(
      v20,
      "MeshInstance::CloneInternal() -- skinning controller cloning not yet supported (reserved for future use)");
    v12 = std::string::string(
            v21,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\meshinstance.cpp");
    Spectre::Engine::EngineNotImplException::EngineNotImplException(pExceptionObject, v12, v13, v20);
    throw (Spectre::Engine::EngineNotImplException *)pExceptionObject;
  }
  std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(v9 + 136, a1 + 136);
  if ( (*a3 & 0x20) != 0 )
  {
    std::string::string(
      v20,
      "MeshInstance::CloneInternal() -- morph controller cloning not yet supported (reserved for future use)");
    v14 = std::string::string(
            v21,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\meshinstance.cpp");
    Spectre::Engine::EngineNotImplException::EngineNotImplException(pExceptionObject, v14, v15, v20);
    throw (Spectre::Engine::EngineNotImplException *)pExceptionObject;
  }
  std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(v9 + 152, a1 + 152);
  *(_BYTE *)(v9 + 168) = *(_BYTE *)(a1 + 168);
  *(_DWORD *)(v9 + 172) = *(_DWORD *)(a1 + 172);
  *(_DWORD *)(v9 + 176) = *(_DWORD *)(a1 + 176);
  *(_DWORD *)(v9 + 180) = *(_DWORD *)(a1 + 180);
  *(_DWORD *)(v9 + 184) = *(_DWORD *)(a1 + 184);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v16 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
}

```

## disassembly

```asm
0x180048460  push    rbp
0x180048462  push    rbx
0x180048463  push    rsi
0x180048464  push    rdi
0x180048465  push    r14
0x180048467  lea     rbp, [rsp-37h]
0x18004846c  sub     rsp, 0D0h
0x180048473  mov     rax, cs:__security_cookie
0x18004847a  xor     rax, rsp
0x18004847d  mov     [rbp+57h+var_28], rax
0x180048481  mov     rsi, r8
0x180048484  mov     r14, rdx
0x180048487  mov     rdi, rcx
0x18004848a  mov     [rbp+57h+var_A8], rdx
0x18004848e  lea     rcx, [rbp+57h+var_B8]
0x180048492  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180048497  mov     rdx, rax
0x18004849a  mov     rcx, rdi
0x18004849d  call    ?CloneInternal@Component@Engine@Spectre@@MEBAXV?$shared_ptr@VComponent@Engine@Spectre@@@std@@AEBI@Z; Spectre::Engine::Component::CloneInternal(std::shared_ptr<Spectre::Engine::Component>,uint const &)
0x1800484a2  mov     rdx, r14
0x1800484a5  lea     rcx, [rbp+57h+var_B8]
0x1800484a9  call    ??$dynamic_pointer_cast@VMeshInstance@Engine@Spectre@@VComponent@23@@std@@YA?AV?$shared_ptr@VMeshInstance@Engine@Spectre@@@0@AEBV?$shared_ptr@VComponent@Engine@Spectre@@@0@@Z; std::dynamic_pointer_cast<Spectre::Engine::MeshInstance,Spectre::Engine::Component>(std::shared_ptr<Spectre::Engine::Component> const &)
0x1800484ae  nop
0x1800484af  test    byte ptr [rsi], 8
0x1800484b2  jz      short loc_1800484F6
0x1800484b4  lea     rdx, aMeshinstanceCl_1; "MeshInstance::CloneInternal() -- materi"...
0x1800484bb  lea     rcx, [rbp+57h+var_80]
0x1800484bf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800484c4  nop
0x1800484c5  lea     rdx, aOnecoreuapWind_49; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800484cc  lea     rcx, [rbp+57h+var_A0]
0x1800484d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800484d5  lea     r9, [rbp+57h+var_80]
0x1800484d9  mov     rdx, rax
0x1800484dc  lea     rcx, [rbp+57h+pExceptionObject]
0x1800484e0  call    ??0EngineNotImplException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineNotImplException::EngineNotImplException(std::string,int,std::string const &,bool)
0x1800484e5  lea     rdx, _TI5?AUEngineNotImplException@Engine@Spectre@@; pThrowInfo
0x1800484ec  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800484f0  call    _CxxThrowException_0
0x1800484f6  lea     rdx, [rdi+68h]
0x1800484fa  mov     rbx, [rbp+57h+var_B8]
0x1800484fe  lea     rcx, [rbx+68h]
0x180048502  cmp     rcx, rdx
0x180048505  jz      short loc_180048528
0x180048507  mov     r8, [rdx+8]
0x18004850b  sub     r8, [rdx]
0x18004850e  sar     r8, 3
0x180048512  mov     rax, 2E8BA2E8BA2E8BA3h
0x18004851c  imul    r8, rax
0x180048520  mov     rdx, [rdx]
0x180048523  call    ??$_Assign_counted_range@PEAUMaterialInfo@MeshInstance@Engine@Spectre@@@?$vector@UMaterialInfo@MeshInstance@Engine@Spectre@@V?$allocator@UMaterialInfo@MeshInstance@Engine@Spectre@@@std@@@std@@AEAAXPEAUMaterialInfo@MeshInstance@Engine@Spectre@@_K@Z; std::vector<Spectre::Engine::MeshInstance::MaterialInfo>::_Assign_counted_range<Spectre::Engine::MeshInstance::MaterialInfo *>(Spectre::Engine::MeshInstance::MaterialInfo *,unsigned __int64)
0x180048528  test    byte ptr [rsi], 4
0x18004852b  jz      short loc_18004856F
0x18004852d  lea     rdx, aMeshinstanceCl; "MeshInstance::CloneInternal() -- mesh c"...
0x180048534  lea     rcx, [rbp+57h+var_A0]
0x180048538  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004853d  nop
0x18004853e  lea     rdx, aOnecoreuapWind_49; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180048545  lea     rcx, [rbp+57h+var_80]
0x180048549  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004854e  lea     r9, [rbp+57h+var_A0]
0x180048552  mov     rdx, rax
0x180048555  lea     rcx, [rbp+57h+pExceptionObject]
0x180048559  call    ??0EngineNotImplException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineNotImplException::EngineNotImplException(std::string,int,std::string const &,bool)
0x18004855e  lea     rdx, _TI5?AUEngineNotImplException@Engine@Spectre@@; pThrowInfo
0x180048565  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180048569  call    _CxxThrowException_0
0x18004856f  lea     rdx, [rdi+58h]
0x180048573  lea     rcx, [rbx+58h]
0x180048577  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x18004857c  test    byte ptr [rsi], 10h
0x18004857f  jz      short loc_1800485C3
0x180048581  lea     rdx, aMeshinstanceCl_2; "MeshInstance::CloneInternal() -- skinni"...
0x180048588  lea     rcx, [rbp+57h+var_A0]
0x18004858c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180048591  nop
0x180048592  lea     rdx, aOnecoreuapWind_49; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180048599  lea     rcx, [rbp+57h+var_80]
0x18004859d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800485a2  lea     r9, [rbp+57h+var_A0]
0x1800485a6  mov     rdx, rax
0x1800485a9  lea     rcx, [rbp+57h+pExceptionObject]
0x1800485ad  call    ??0EngineNotImplException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineNotImplException::EngineNotImplException(std::string,int,std::string const &,bool)
0x1800485b2  lea     rdx, _TI5?AUEngineNotImplException@Engine@Spectre@@; pThrowInfo
0x1800485b9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800485bd  call    _CxxThrowException_0
0x1800485c3  lea     rdx, [rdi+88h]
0x1800485ca  lea     rcx, [rbx+88h]
0x1800485d1  call    ??$?4VMaterial@Engine@Spectre@@$0A@@?$weak_ptr@VMaterial@Engine@Spectre@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VMaterial@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(std::shared_ptr<Spectre::Engine::Material> const &)
0x1800485d6  test    byte ptr [rsi], 20h
0x1800485d9  jz      short loc_18004861D
0x1800485db  lea     rdx, aMeshinstanceCl_0; "MeshInstance::CloneInternal() -- morph "...
0x1800485e2  lea     rcx, [rbp+57h+var_A0]
0x1800485e6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800485eb  nop
0x1800485ec  lea     rdx, aOnecoreuapWind_49; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800485f3  lea     rcx, [rbp+57h+var_80]
0x1800485f7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800485fc  lea     r9, [rbp+57h+var_A0]
0x180048600  mov     rdx, rax
0x180048603  lea     rcx, [rbp+57h+pExceptionObject]
0x180048607  call    ??0EngineNotImplException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineNotImplException::EngineNotImplException(std::string,int,std::string const &,bool)
0x18004860c  lea     rdx, _TI5?AUEngineNotImplException@Engine@Spectre@@; pThrowInfo
0x180048613  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180048617  call    _CxxThrowException_0
0x18004861d  lea     rdx, [rdi+98h]
0x180048624  lea     rcx, [rbx+98h]
0x18004862b  call    ??$?4VMaterial@Engine@Spectre@@$0A@@?$weak_ptr@VMaterial@Engine@Spectre@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VMaterial@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Material>::operator=<Spectre::Engine::Material,0>(std::shared_ptr<Spectre::Engine::Material> const &)
0x180048630  mov     al, [rdi+0A8h]
0x180048636  mov     [rbx+0A8h], al
0x18004863c  mov     eax, [rdi+0ACh]
0x180048642  mov     [rbx+0ACh], eax
0x180048648  mov     eax, [rdi+0B0h]
0x18004864e  mov     [rbx+0B0h], eax
0x180048654  mov     eax, [rdi+0B4h]
0x18004865a  mov     [rbx+0B4h], eax
0x180048660  mov     eax, [rdi+0B8h]
0x180048666  mov     [rbx+0B8h], eax
0x18004866c  mov     rcx, [rbp+57h+var_B0]; this
0x180048670  test    rcx, rcx
0x180048673  jz      short loc_18004867B
0x180048675  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004867a  nop
0x18004867b  mov     rcx, [r14+8]; this
0x18004867f  test    rcx, rcx
0x180048682  jz      short loc_180048689
0x180048684  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180048689  mov     rcx, [rbp+57h+var_28]
0x18004868d  xor     rcx, rsp; StackCookie
0x180048690  call    __security_check_cookie
0x180048695  add     rsp, 0D0h
0x18004869c  pop     r14
0x18004869e  pop     rdi
0x18004869f  pop     rsi
0x1800486a0  pop     rbx
0x1800486a1  pop     rbp
0x1800486a2  retn
```
