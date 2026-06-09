# Spectre::Engine::Engine::CreateDeviceInternal(std::shared_ptr<Spectre::Engine::RenderDevice> const &)

- ea: `0x180031820`
- end: `0x180031cbb`
- name: `?CreateDeviceInternal@Engine@1Spectre@@IEAAXAEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z`
- size: `1179`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800167f4`
- `0x180016918`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x1800120ec`
- `0x180012ba8`
- `0x180012cd0`
- `0x180012df8`
- `0x180014a3c`
- `0x180016324`
- `0x18001d578`
- `0x18001daf4`
- `0x180024420`
- `0x180025b4c`
- `0x180025ba0`
- `0x180028f40`
- `0x180028f78`
- `0x18002921c`
- `0x18002c664`
- `0x18002c8dc`
- `0x18002e7fc`
- `0x18002ec4c`
- `0x180031820`
- `0x180031cc4`
- `0x18003293c`
- `0x18003316c`
- `0x1800341d8`
- `0x1800343b4`
- `0x180052efc`
- `0x18005319c`
- `0x18005ad30`
- `0x1800681a8`
- `0x1800e7010`

## string_xrefs

- `0x180031c61`: `RenderDevice startup duration to attach complete: %8.3fms`
- `0x1800318d2`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x1800318c1`: `This Engine instance cannot create multiple devices because it was created with option General.EngineDeviceMode==Single.`
- `0x180031948`: `Engine::CreateDevice() -- attaching device id %u -- %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Spectre::Engine::Engine::CreateDeviceInternal(
        Spectre::Engine::Engine *this,
        Spectre::Engine::RenderDevice **a2)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // r14
  int v6; // eax
  int v7; // r8d
  __int64 v8; // rax
  const char *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r8
  _BYTE *v12; // rbx
  __int64 Output; // rax
  __int64 *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // r8
  std::_Ref_count_base *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r8
  std::_Ref_count_base *v23; // rcx
  unsigned __int64 i; // rbx
  _QWORD *v25; // rbx
  _QWORD *v26; // r14
  void ***v27; // rdx
  Spectre::Engine::RenderDevice *v28; // rbx
  std::_Ref_count_base *v29; // rcx
  double v30; // xmm0_8
  _BYTE *v32; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v33; // [rsp+38h] [rbp-C8h]
  std::_Ref_count_base *v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v36; // [rsp+58h] [rbp-A8h]
  _BYTE v37[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v38[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v40[32]; // [rsp+A0h] [rbp-60h] BYREF
  void **v41; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[48]; // [rsp+C8h] [rbp-38h] BYREF
  void ***v43; // [rsp+F8h] [rbp-8h]
  _BYTE pExceptionObject[56]; // [rsp+100h] [rbp+0h] BYREF

  Spectre::Engine::Lockable::GetExclusiveLock((char *)this + 8, v38);
  Spectre::Engine::Lockable::GetExclusiveLock((char *)this + 1104, v37);
  Spectre::Engine::Lockable::VerifyWriteAccess((Spectre::Engine::RenderDevice *)((char *)*a2 + 24));
  if ( !*((_DWORD *)this + 138)
    && !(*(unsigned __int8 (__fastcall **)(Spectre::Engine::RenderDevice *))(*(_QWORD *)*a2 + 32LL))(*a2) )
  {
    v4 = (_QWORD *)*((_QWORD *)this + 11);
    v5 = (_QWORD *)*((_QWORD *)this + 12);
    while ( v4 != v5 )
    {
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 32LL))(*v4) )
      {
        std::string::string(
          v40,
          "This Engine instance cannot create multiple devices because it was created with option General.EngineDeviceMode==Single.");
        v6 = std::string::string(
               v39,
               "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp");
        Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v6, v7, (unsigned int)v40, 0);
        throw (Spectre::Engine::EngineException *)pExceptionObject;
      }
      v4 += 2;
    }
  }
  Trace::LevelSettingsWrapper::Output(
    &gTraceLevelsNativeRenderer_Engine,
    3,
    "-----------------------------------------------------------------------------------");
  v8 = Spectre::Utils::LexicalCast<std::string,std::wstring>(v39, (char *)*a2 + 80);
  v9 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v8);
  Trace::LevelSettingsWrapper::Output(
    &gTraceLevelsNativeRenderer_Engine,
    3,
    "Engine::CreateDevice() -- attaching device id %u -- %s",
    *((_DWORD *)*a2 + 61),
    v9);
  std::string::_Tidy_deallocate(v39);
  if ( Spectre::Engine::RenderDevice::GetOutputCount(*a2) )
  {
    Spectre::Engine::Engine::CreateDisplay(this, &v32, v10, 0);
    *(_OWORD *)v34 = 0;
    Spectre::Engine::Engine::GetCamera(this, &v35, v11, v34);
    if ( v35 )
      Spectre::Engine::Display::AddCamera(v32, &v35);
    if ( v36 )
      std::_Ref_count_base::_Decref(v36);
    v12 = v32;
    Output = Spectre::Engine::RenderDevice::GetOutput(*a2, &v35, 0);
    Spectre::Engine::Display::AttachOutput(v12, Output);
    if ( v36 )
      std::_Ref_count_base::_Decref(v36);
    std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(&v35, a2);
    std::map<std::weak_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::Display>,std::owner_less<std::weak_ptr<Spectre::Engine::RenderDevice>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>>>::_Try_emplace<std::weak_ptr<Spectre::Engine::RenderDevice>,>(
      (char *)this + 184,
      v39,
      &v35);
    v14 = (__int64 *)std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
                       v34,
                       &v32);
    v15 = *v14;
    *v14 = *(_QWORD *)(v16 + 48);
    *(_QWORD *)(v16 + 48) = v15;
    v17 = v14[1];
    v14[1] = *(_QWORD *)(v16 + 56);
    *(_QWORD *)(v16 + 56) = v17;
    if ( v34[1] )
      std::_Ref_count_base::_Decref(v34[1]);
    if ( v36 )
      std::_Ref_count_base::_Decwref(v36);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
  }
  Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Engine *)((char *)this + 112));
  std::vector<std::shared_ptr<Spectre::Engine::RenderDevice>>::emplace_back<std::shared_ptr<Spectre::Engine::RenderDevice> const &>(
    (char *)this + 88,
    a2);
  std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(&v32);
  Spectre::Engine::Engine::ProcessNewResources(this);
  v18 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v40, a2);
  v35 = v18;
  v20 = **(std::_Ref_count_base ***)(v19 + 18560);
  v34[0] = v20;
  while ( !*((_BYTE *)v20 + 25) )
  {
    v21 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            v39,
            v18);
    Spectre::Engine::ShaderFamily::AttachDevice(v22, v21);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::DeviceConstantBuffer>>>>,std::_Iterator_base0>::operator++(v34);
    v20 = v34[0];
  }
  v23 = *(std::_Ref_count_base **)(v18 + 8);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  for ( i = 0; i < (__int64)(*((_QWORD *)this + 112) - *((_QWORD *)this + 111)) >> 4; ++i )
  {
    Spectre::Engine::Engine::GetResourceByIndex(this, &v32, i);
    if ( v32 && (v32[40] & 2) != 0 )
      (*(void (__fastcall **)(_BYTE *, Spectre::Engine::RenderDevice **))(*(_QWORD *)v32 + 16LL))(v32, a2);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
  }
  std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(&v32, a2);
  v43 = 0;
  v41 = &std::_Func_impl_no_alloc<_lambda_991510985cb39e07691d1fb2432ec0d9_,void,std::shared_ptr<Spectre::Engine::Component> const &>::`vftable';
  std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v42, &v32);
  v43 = &v41;
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  v25 = (_QWORD *)*((_QWORD *)this + 88);
  v26 = (_QWORD *)*((_QWORD *)this + 89);
  while ( v25 != v26 )
  {
    Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Mutex *)(*v25 + 16LL));
    Spectre::Engine::Scene::ForEachComponent<Spectre::Engine::Component>(*v25, &v41);
    std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v39);
    v25 += 2;
  }
  if ( v43 )
  {
    v27 = &v41;
    LOBYTE(v27) = v43 != &v41;
    ((void (__fastcall *)(void ***, void ***))(*v43)[4])(v43, v27);
  }
  v28 = *a2;
  std::chrono::steady_clock::now(v34);
  v29 = v34[0];
  *((std::_Ref_count_base **)v28 + 55) = v34[0];
  v30 = Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>((char *)v29 - *((_QWORD *)v28 + 53));
  Trace::LevelSettingsWrapper::Output(
    &gTraceLevelsNativeRenderer_Renderer,
    3,
    "RenderDevice startup duration to attach complete: %8.3fms",
    *(float *)&v30);
  Spectre::Engine::Engine::PrintDevices(this);
  std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v37);
  return std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v38);
}

```

## disassembly

```asm
0x180031820  mov     [rsp-8+arg_10], rbx
0x180031825  mov     [rsp-8+arg_18], rsi
0x18003182a  push    rbp
0x18003182b  push    rdi
0x18003182c  push    r14
0x18003182e  lea     rbp, [rsp-40h]
0x180031833  sub     rsp, 140h
0x18003183a  mov     rax, cs:__security_cookie
0x180031841  xor     rax, rsp
0x180031844  mov     [rbp+50h+var_18], rax
0x180031848  mov     rsi, rdx
0x18003184b  mov     rdi, rcx
0x18003184e  add     rcx, 8
0x180031852  lea     rdx, [rsp+150h+var_E0]
0x180031857  call    ?GetExclusiveLock@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLock(void)
0x18003185c  nop
0x18003185d  lea     rcx, [rdi+450h]
0x180031864  lea     rdx, [rsp+150h+var_F0]
0x180031869  call    ?GetExclusiveLock@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLock(void)
0x18003186e  nop
0x18003186f  mov     rcx, [rsi]
0x180031872  add     rcx, 18h; this
0x180031876  call    ?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ; Spectre::Engine::Lockable::VerifyWriteAccess(void)
0x18003187b  cmp     dword ptr [rdi+228h], 0
0x180031882  jnz     loc_180031908
0x180031888  mov     rcx, [rsi]
0x18003188b  mov     rax, [rcx]
0x18003188e  mov     rax, [rax+20h]
0x180031892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031897  test    al, al
0x180031899  jnz     short loc_180031908
0x18003189b  mov     rbx, [rdi+58h]
0x18003189f  mov     r14, [rdi+60h]
0x1800318a3  cmp     rbx, r14
0x1800318a6  jz      short loc_180031908
0x1800318a8  mov     rcx, [rbx]
0x1800318ab  mov     rax, [rcx]
0x1800318ae  mov     rax, [rax+20h]
0x1800318b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318b7  test    al, al
0x1800318b9  jz      short loc_1800318C1
0x1800318bb  add     rbx, 10h
0x1800318bf  jmp     short loc_1800318A3
0x1800318c1  lea     rdx, aThisEngineInst; "This Engine instance cannot create mult"...
0x1800318c8  lea     rcx, [rbp+50h+var_B0]
0x1800318cc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800318d1  nop
0x1800318d2  lea     rdx, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800318d9  lea     rcx, [rbp+50h+var_D0]
0x1800318dd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800318e2  mov     byte ptr [rsp+150h+var_130], 0
0x1800318e7  lea     r9, [rbp+50h+var_B0]
0x1800318eb  mov     rdx, rax
0x1800318ee  lea     rcx, [rbp+50h+pExceptionObject]
0x1800318f2  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800318f7  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800318fe  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180031902  call    _CxxThrowException_0
0x180031908  lea     r8, asc_18016A2B0; "---------------------------------------"...
0x18003190f  mov     edx, 3
0x180031914  lea     rcx, ?gTraceLevelsNativeRenderer_Engine@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer_Engine
0x18003191b  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180031920  mov     rdx, [rsi]
0x180031923  add     rdx, 50h ; 'P'
0x180031927  lea     rcx, [rbp+50h+var_D0]
0x18003192b  call    ??$LexicalCast@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Utils@Spectre@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Spectre::Utils::LexicalCast<std::string,std::wstring>(std::wstring const &)
0x180031930  nop
0x180031931  mov     rcx, rax
0x180031934  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180031939  mov     r9, [rsi]
0x18003193c  mov     [rsp+150h+var_130], rax
0x180031941  mov     r9d, [r9+0F4h]
0x180031948  lea     r8, aEngineCreatede; "Engine::CreateDevice() -- attaching dev"...
0x18003194f  mov     edx, 3
0x180031954  lea     rcx, ?gTraceLevelsNativeRenderer_Engine@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer_Engine
0x18003195b  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180031960  nop
0x180031961  lea     rcx, [rbp+50h+var_D0]
0x180031965  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003196a  mov     rcx, [rsi]; this
0x18003196d  call    ?GetOutputCount@RenderDevice@Engine@Spectre@@QEBAIXZ; Spectre::Engine::RenderDevice::GetOutputCount(void)
0x180031972  test    eax, eax
0x180031974  jz      loc_180031A81
0x18003197a  xor     r9d, r9d
0x18003197d  lea     rdx, [rsp+150h+var_120]
0x180031982  mov     rcx, rdi
0x180031985  call    ?CreateDisplay@Engine@1Spectre@@QEAA?AV?$shared_ptr@VDisplay@Engine@Spectre@@@std@@W4RefreshPolicy@Display@12@W4RenderingMode@612@@Z; Spectre::Engine::Engine::CreateDisplay(Spectre::Engine::Display::RefreshPolicy,Spectre::Engine::Display::RenderingMode)
0x18003198a  nop
0x18003198b  xorps   xmm0, xmm0
0x18003198e  movdqu  xmmword ptr [rsp+150h+var_110], xmm0
0x180031994  lea     r9, [rsp+150h+var_110]
0x180031999  lea     rdx, [rsp+150h+var_100]
0x18003199e  mov     rcx, rdi
0x1800319a1  call    ?GetCamera@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCamera@Engine@Spectre@@@std@@_KV?$shared_ptr@VScene@Engine@Spectre@@@4@@Z; Spectre::Engine::Engine::GetCamera(unsigned __int64,std::shared_ptr<Spectre::Engine::Scene>)
0x1800319a6  nop
0x1800319a7  cmp     [rsp+150h+var_100], 0
0x1800319ad  jz      short loc_1800319BF
0x1800319af  lea     rdx, [rsp+150h+var_100]
0x1800319b4  mov     rcx, [rsp+150h+var_120]
0x1800319b9  call    ?AddCamera@Display@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VCamera@Engine@Spectre@@@std@@@Z; Spectre::Engine::Display::AddCamera(std::shared_ptr<Spectre::Engine::Camera> const &)
0x1800319be  nop
0x1800319bf  mov     rcx, [rsp+150h+var_F8]; this
0x1800319c4  test    rcx, rcx
0x1800319c7  jz      short loc_1800319CE
0x1800319c9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800319ce  mov     rbx, [rsp+150h+var_120]
0x1800319d3  xor     r8d, r8d
0x1800319d6  lea     rdx, [rsp+150h+var_100]
0x1800319db  mov     rcx, [rsi]
0x1800319de  call    ?GetOutput@RenderDevice@Engine@Spectre@@QEBA?AV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@std@@I@Z; Spectre::Engine::RenderDevice::GetOutput(uint)
0x1800319e3  nop
0x1800319e4  mov     rdx, rax
0x1800319e7  mov     rcx, rbx
0x1800319ea  call    ?AttachOutput@Display@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@std@@@Z; Spectre::Engine::Display::AttachOutput(std::shared_ptr<Spectre::Engine::IRenderOutput> const &)
0x1800319ef  nop
0x1800319f0  mov     rcx, [rsp+150h+var_F8]; this
0x1800319f5  test    rcx, rcx
0x1800319f8  jz      short loc_1800319FF
0x1800319fa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800319ff  mov     rdx, rsi
0x180031a02  lea     rcx, [rsp+150h+var_100]
0x180031a07  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180031a0c  nop
0x180031a0d  lea     rcx, [rdi+0B8h]
0x180031a14  lea     r8, [rsp+150h+var_100]
0x180031a19  lea     rdx, [rbp+50h+var_D0]
0x180031a1d  call    ??$_Try_emplace@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@$$V@?$map@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@U?$owner_less@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@V?$allocator@U?$pair@$$CBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$weak_ptr@VRenderDevice@Engine@Spectre@@@1@@Z; std::map<std::weak_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::Display>,std::owner_less<std::weak_ptr<Spectre::Engine::RenderDevice>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>>>::_Try_emplace<std::weak_ptr<Spectre::Engine::RenderDevice>,>(std::weak_ptr<Spectre::Engine::RenderDevice> &&)
0x180031a22  mov     r8, [rax]
0x180031a25  lea     rdx, [rsp+150h+var_120]
0x180031a2a  lea     rcx, [rsp+150h+var_110]
0x180031a2f  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180031a34  mov     rdx, [rax]
0x180031a37  mov     rcx, [r8+30h]
0x180031a3b  mov     [rax], rcx
0x180031a3e  mov     [r8+30h], rdx
0x180031a42  mov     rdx, [rax+8]
0x180031a46  mov     rcx, [r8+38h]
0x180031a4a  mov     [rax+8], rcx
0x180031a4e  mov     [r8+38h], rdx
0x180031a52  mov     rcx, [rsp+150h+var_110+8]; this
0x180031a57  test    rcx, rcx
0x180031a5a  jz      short loc_180031A62
0x180031a5c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031a61  nop
0x180031a62  mov     rcx, [rsp+150h+var_F8]; this
0x180031a67  test    rcx, rcx
0x180031a6a  jz      short loc_180031A72
0x180031a6c  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180031a71  nop
0x180031a72  mov     rcx, [rsp+150h+var_118]; this
0x180031a77  test    rcx, rcx
0x180031a7a  jz      short loc_180031A81
0x180031a7c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031a81  lea     rcx, [rdi+70h]; this
0x180031a85  lea     rdx, [rsp+150h+var_120]
0x180031a8a  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x180031a8f  nop
0x180031a90  lea     rcx, [rdi+58h]
0x180031a94  mov     rdx, rsi
0x180031a97  call    ??$emplace_back@AEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@?$vector@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VRenderDevice@Engine@Spectre@@@1@AEBV21@@Z; std::vector<std::shared_ptr<Spectre::Engine::RenderDevice>>::emplace_back<std::shared_ptr<Spectre::Engine::RenderDevice> const &>(std::shared_ptr<Spectre::Engine::RenderDevice> const &)
0x180031a9c  nop
0x180031a9d  lea     rcx, [rsp+150h+var_120]
0x180031aa2  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x180031aa7  mov     rcx, rdi; this
0x180031aaa  call    ?ProcessNewResources@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::ProcessNewResources(void)
0x180031aaf  mov     r8, [rdi+200h]
0x180031ab6  mov     rdx, rsi
0x180031ab9  lea     rcx, [rbp+50h+var_B0]
0x180031abd  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180031ac2  mov     rbx, rax
0x180031ac5  mov     [rsp+150h+var_100], rax
0x180031aca  mov     rcx, [r8+4880h]
0x180031ad1  mov     rcx, [rcx]
0x180031ad4  mov     [rsp+150h+var_110], rcx
0x180031ad9  cmp     byte ptr [rcx+19h], 0
0x180031add  jnz     short loc_180031B0B
0x180031adf  mov     r8, [rcx+40h]
0x180031ae3  mov     rdx, rbx
0x180031ae6  lea     rcx, [rbp+50h+var_D0]
0x180031aea  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180031aef  mov     rdx, rax
0x180031af2  mov     rcx, r8
0x180031af5  call    ?AttachDevice@ShaderFamily@Engine@Spectre@@QEAAXV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z; Spectre::Engine::ShaderFamily::AttachDevice(std::shared_ptr<Spectre::Engine::RenderDevice>)
0x180031afa  lea     rcx, [rsp+150h+var_110]
0x180031aff  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceConstantBuffer@Engine@Spectre@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::DeviceConstantBuffer>>>>,std::_Iterator_base0>::operator++(void)
0x180031b04  mov     rcx, [rsp+150h+var_110]
0x180031b09  jmp     short loc_180031AD9
0x180031b0b  mov     rcx, [rbx+8]; this
0x180031b0f  test    rcx, rcx
0x180031b12  jz      short loc_180031B19
0x180031b14  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031b19  xor     ebx, ebx
0x180031b1b  mov     rax, [rdi+380h]
0x180031b22  sub     rax, [rdi+378h]
0x180031b29  sar     rax, 4
0x180031b2d  test    rax, rax
0x180031b30  jz      short loc_180031B8C
0x180031b32  mov     r8, rbx
0x180031b35  lea     rdx, [rsp+150h+var_120]
0x180031b3a  mov     rcx, rdi
0x180031b3d  call    ?GetResourceByIndex@Engine@1Spectre@@QEAA?AV?$shared_ptr@VRendererResource@Engine@Spectre@@@std@@_K@Z; Spectre::Engine::Engine::GetResourceByIndex(unsigned __int64)
0x180031b42  nop
0x180031b43  mov     rcx, [rsp+150h+var_120]
0x180031b48  test    rcx, rcx
0x180031b4b  jz      short loc_180031B63
0x180031b4d  test    byte ptr [rcx+28h], 2
0x180031b51  jz      short loc_180031B63
0x180031b53  mov     rax, [rcx]
0x180031b56  mov     rdx, rsi
0x180031b59  mov     rax, [rax+10h]
0x180031b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b62  nop
0x180031b63  mov     rcx, [rsp+150h+var_118]; this
0x180031b68  test    rcx, rcx
0x180031b6b  jz      short loc_180031B72
0x180031b6d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031b72  inc     rbx
0x180031b75  mov     rax, [rdi+380h]
0x180031b7c  sub     rax, [rdi+378h]
0x180031b83  sar     rax, 4
0x180031b87  cmp     rbx, rax
0x180031b8a  jb      short loc_180031B32
0x180031b8c  mov     rdx, rsi
0x180031b8f  lea     rcx, [rsp+150h+var_120]
0x180031b94  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180031b99  mov     [rbp+50h+var_58], 0
0x180031ba1  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_991510985cb39e07691d1fb2432ec0d9_@@XAEBV?$shared_ptr@VComponent@Engine@Spectre@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_991510985cb39e07691d1fb2432ec0d9_,void,std::shared_ptr<Spectre::Engine::Component> const &>::`vftable'
0x180031ba8  mov     [rbp+50h+var_90], rax
0x180031bac  lea     rdx, [rsp+150h+var_120]
0x180031bb1  lea     rcx, [rbp+50h+var_88]
0x180031bb5  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180031bba  lea     rcx, [rbp+50h+var_90]
0x180031bbe  mov     [rbp+50h+var_58], rcx
0x180031bc2  mov     rcx, [rsp+150h+var_118]; this
0x180031bc7  test    rcx, rcx
0x180031bca  jz      short loc_180031BD1
0x180031bcc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031bd1  mov     rbx, [rdi+2C0h]
0x180031bd8  mov     r14, [rdi+2C8h]
0x180031bdf  jmp     short loc_180031C0C
0x180031be1  mov     rcx, [rbx]
0x180031be4  add     rcx, 10h; this
0x180031be8  lea     rdx, [rbp+50h+var_D0]
0x180031bec  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x180031bf1  nop
0x180031bf2  lea     rdx, [rbp+50h+var_90]
0x180031bf6  mov     rcx, [rbx]
0x180031bf9  call    ??$ForEachComponent@VComponent@Engine@Spectre@@@Scene@Engine@Spectre@@QEAAXAEBV?$function@$$A6AXAEBV?$shared_ptr@VComponent@Engine@Spectre@@@std@@@Z@std@@@Z; Spectre::Engine::Scene::ForEachComponent<Spectre::Engine::Component>(std::function<void (std::shared_ptr<Spectre::Engine::Component> const &)> const &)
0x180031bfe  nop
0x180031bff  lea     rcx, [rbp+50h+var_D0]
0x180031c03  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x180031c08  add     rbx, 10h
0x180031c0c  cmp     rbx, r14
0x180031c0f  jnz     short loc_180031BE1
0x180031c11  mov     rcx, [rbp+50h+var_58]
0x180031c15  test    rcx, rcx
0x180031c18  jz      short loc_180031C30
0x180031c1a  mov     rax, [rcx]
0x180031c1d  lea     rdx, [rbp+50h+var_90]
0x180031c21  cmp     rcx, rdx
0x180031c24  setnz   dl
0x180031c27  mov     rax, [rax+20h]
0x180031c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c30  mov     rbx, [rsi]
0x180031c33  lea     rcx, [rsp+150h+var_110]
0x180031c38  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180031c3d  mov     rcx, [rsp+150h+var_110]
0x180031c42  mov     [rbx+1B8h], rcx
0x180031c49  sub     rcx, [rbx+1A8h]
0x180031c50  call    ??$GetDurationMilliseconds@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Engine@Spectre@@YAMV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z; Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>>)
0x180031c55  xorps   xmm3, xmm3
0x180031c58  cvtss2sd xmm3, xmm0
0x180031c5c  movq    r9, xmm3
0x180031c61  lea     r8, aRenderdeviceSt_1; "RenderDevice startup duration to attach"...
0x180031c68  mov     edx, 3
0x180031c6d  lea     rcx, ?gTraceLevelsNativeRenderer_Renderer@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer_Renderer
0x180031c74  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180031c79  mov     rcx, rdi; this
0x180031c7c  call    ?PrintDevices@Engine@1Spectre@@QEAAXXZ; Spectre::Engine::Engine::PrintDevices(void)
0x180031c81  nop
0x180031c82  lea     rcx, [rsp+150h+var_F0]
0x180031c87  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x180031c8c  nop
0x180031c8d  lea     rcx, [rsp+150h+var_E0]
0x180031c92  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x180031c97  mov     rcx, [rbp+50h+var_18]
0x180031c9b  xor     rcx, rsp; StackCookie
0x180031c9e  call    __security_check_cookie
0x180031ca3  lea     r11, [rsp+150h+var_10]
0x180031cab  mov     rbx, [r11+30h]
0x180031caf  mov     rsi, [r11+38h]
0x180031cb3  mov     rsp, r11
0x180031cb6  pop     r14
0x180031cb8  pop     rdi
0x180031cb9  pop     rbp
0x180031cba  retn
```
