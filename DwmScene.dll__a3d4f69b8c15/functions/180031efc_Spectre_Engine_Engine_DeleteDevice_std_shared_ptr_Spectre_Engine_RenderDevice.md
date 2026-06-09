# Spectre::Engine::Engine::DeleteDevice(std::shared_ptr<Spectre::Engine::RenderDevice> &&)

- ea: `0x180031efc`
- end: `0x180032499`
- name: `?DeleteDevice@Engine@1Spectre@@QEAAX$$QEAV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z`
- size: `1437`
- prototype: `__int64 __fastcall(Spectre::Engine::Engine *this)`
- caller_count: `2`
- callee_count: `36`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033c10`
- `0x1800345ec`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x1800120ec`
- `0x1800121f4`
- `0x180012ba8`
- `0x180012df8`
- `0x180014a3c`
- `0x180016324`
- `0x18001d578`
- `0x18001daf4`
- `0x1800258e8`
- `0x180025b4c`
- `0x180025ba0`
- `0x1800264d8`
- `0x180028e3c`
- `0x180028f40`
- `0x180028f78`
- `0x1800290f8`
- `0x18002a5dc`
- `0x18002c8dc`
- `0x18002db64`
- `0x18002e7fc`
- `0x180031efc`
- `0x1800324a0`
- `0x1800324f0`
- `0x180032da0`
- `0x180033794`
- `0x18003384c`
- `0x1800341d8`
- `0x180034544`
- `0x180034dc8`
- `0x180036a9c`
- `0x18004c4d0`
- `0x18007bca8`
- `0x1800e7010`

## string_xrefs

- `0x180031fe8`: `Engine::DeleteDevice() -- removing device id %u -- %s`
- `0x180032030`: `Engine::DeleteDevice() -- device is not attached to this engine`
- `0x18003242b`: `Engine::DeleteDevice() -- completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Spectre::Engine::Engine::DeleteDevice(Spectre::Engine::Engine *this, __int64 *a2)
{
  __int64 v3; // rsi
  std::_Ref_count_base *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  const char *v8; // rax
  _QWORD *i; // rax
  std::_Ref_count_base *v10; // rcx
  unsigned int v11; // r12d
  unsigned int OutputCount; // r15d
  unsigned int j; // r14d
  std::_Ref_count_base *v14; // rbx
  char *v15; // r14
  __int64 v16; // rdx
  _BOOL8 v17; // rbx
  _QWORD *v18; // rax
  char v19; // r9
  std::_Ref_count_base *v20; // r8
  std::_Ref_count_base *v21; // rax
  std::_Ref_count_base *v22; // rcx
  std::_Ref_count_base *v23; // rdx
  std::_Ref_count_base *k; // rbx
  __int64 v25; // rax
  unsigned int m; // ebx
  __int64 v27; // rax
  Spectre::Engine::ShaderPropertyBlock **v28; // rbx
  __int64 v29; // r14
  __int64 v30; // rsi
  __int64 v31; // r14
  __int64 n; // rbx
  std::_Ref_count_base *v33; // rcx
  std::_Ref_count_base *v34[2]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v35; // [rsp+40h] [rbp-59h] BYREF
  std::_Ref_count_base *v36; // [rsp+48h] [rbp-51h]
  __int64 v37; // [rsp+50h] [rbp-49h] BYREF
  std::_Ref_count_base *v38; // [rsp+58h] [rbp-41h]
  _BYTE v39[8]; // [rsp+60h] [rbp-39h] BYREF
  std::_Ref_count_base *v40; // [rsp+68h] [rbp-31h]
  _BYTE v41[16]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v42[16]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v43[32]; // [rsp+98h] [rbp-1h] BYREF

  v37 = *a2;
  v3 = v37;
  v4 = (std::_Ref_count_base *)a2[1];
  v38 = v4;
  *a2 = 0;
  a2[1] = 0;
  *(_OWORD *)v34 = 0;
  v5 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         &v35,
         &v37);
  Spectre::Engine::Engine::InvokeCallback(this, 8, v5, v34);
  Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Engine *)((char *)this + 8));
  Spectre::Engine::Lockable::GetExclusiveLock((char *)this + 1104, v41);
  v6 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         v34,
         &v37);
  Spectre::Engine::Engine::SendDevicePerformanceTelemetry(this, v6);
  Trace::LevelSettingsWrapper::Output(
    &gTraceLevelsNativeRenderer_Engine,
    3,
    "-----------------------------------------------------------------------------------");
  v7 = Spectre::Utils::LexicalCast<std::string,std::wstring>(v43, v3 + 80);
  v8 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v7);
  Trace::LevelSettingsWrapper::Output(
    &gTraceLevelsNativeRenderer_Engine,
    3,
    "Engine::DeleteDevice() -- removing device id %u -- %s",
    *(_DWORD *)(v3 + 244),
    v8);
  std::string::_Tidy_deallocate(v43);
  Spectre::Engine::Lockable::GetSharedLockIfNecessary((Spectre::Engine::Engine *)((char *)this + 112));
  if ( *(Spectre::Engine::Engine **)(v3 + 3984) == this )
  {
    for ( i = (_QWORD *)*((_QWORD *)this + 11); i != *((_QWORD **)this + 12); i += 2 )
    {
      if ( *i == v3 )
      {
        std::shared_lock<Spectre::Engine::Mutex>::~shared_lock<Spectre::Engine::Mutex>(v34);
        Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Mutex *)(v3 + 24));
        v11 = *(_DWORD *)(v3 + 244);
        OutputCount = Spectre::Engine::RenderDevice::GetOutputCount((Spectre::Engine::RenderDevice *)v3);
        for ( j = 0; j < OutputCount; ++j )
        {
          Spectre::Engine::RenderDevice::GetOutput(v3, v34, j);
          v14 = v34[0];
          Spectre::Engine::Lockable::GetExclusiveLock((char *)v34[0] + 8, v39);
          (*(void (__fastcall **)(std::_Ref_count_base *, __int64 *))(*(_QWORD *)v14 + 320LL))(v14, &v35);
          (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v14 + 360LL))(v14, 0);
          std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v35);
          std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v39);
          if ( v34[1] )
            std::_Ref_count_base::_Decref(v34[1]);
        }
        std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v34, &v37);
        v15 = (char *)this + 184;
        v16 = *(_QWORD *)(std::_Tree<std::_Tmap_traits<std::weak_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::Display>,std::owner_less<std::weak_ptr<Spectre::Engine::RenderDevice>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>>,0>>::_Find_lower_bound<std::weak_ptr<Spectre::Engine::RenderDevice>>(
                            (char *)this + 184,
                            v39,
                            v34)
                        + 16);
        v17 = !*(_BYTE *)(v16 + 25) && v34[1] >= (std::_Ref_count_base *)*(_QWORD *)(v16 + 40);
        if ( v34[1] )
          std::_Ref_count_base::_Decwref(v34[1]);
        if ( v17 )
        {
          std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v34, &v37);
          v18 = (_QWORD *)std::map<std::weak_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::Display>,std::owner_less<std::weak_ptr<Spectre::Engine::RenderDevice>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>>>::_Try_emplace<std::weak_ptr<Spectre::Engine::RenderDevice>,>(
                            (char *)this + 184,
                            v39,
                            v34);
          std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            &v35,
            *v18 + 48LL);
          if ( v34[1] )
            std::_Ref_count_base::_Decwref(v34[1]);
          std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v39, &v37);
          v20 = *(std::_Ref_count_base **)v15;
          v21 = *(std::_Ref_count_base **)(*(_QWORD *)v15 + 8LL);
          v22 = v21;
          v23 = *(std::_Ref_count_base **)v15;
          for ( k = v40; *((_BYTE *)v22 + 25) == v19; v22 = *(std::_Ref_count_base **)v22 )
          {
            if ( *((_QWORD *)v22 + 5) >= (unsigned __int64)v40 )
            {
              if ( *((_BYTE *)v23 + 25) != v19 && (unsigned __int64)v40 < *((_QWORD *)v22 + 5) )
                v23 = v22;
              v20 = v22;
            }
            else
            {
              v22 = (std::_Ref_count_base *)((char *)v22 + 16);
            }
          }
          if ( *((_BYTE *)v23 + 25) == v19 )
            v21 = *(std::_Ref_count_base **)v23;
          while ( *((_BYTE *)v21 + 25) == v19 )
          {
            if ( (unsigned __int64)v40 >= *((_QWORD *)v21 + 5) )
            {
              v21 = (std::_Ref_count_base *)*((_QWORD *)v21 + 2);
            }
            else
            {
              v23 = v21;
              v21 = *(std::_Ref_count_base **)v21;
            }
          }
          v34[0] = v20;
          v34[1] = v23;
          std::_Tree<std::_Tmap_traits<std::weak_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::Display>,std::owner_less<std::weak_ptr<Spectre::Engine::RenderDevice>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>>,0>>::_Erase(
            (char *)this + 184,
            v34);
          if ( k )
            std::_Ref_count_base::_Decwref(k);
          Spectre::Engine::Engine::DeleteDisplay(this, &v35);
          if ( v36 )
            std::_Ref_count_base::_Decref(v36);
        }
        v25 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
                v39,
                &v37);
        Spectre::Engine::Engine::DetachDevice(this, v25);
        if ( *(_BYTE *)(v3 + 3976) )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
        for ( m = 0; m < OutputCount; ++m )
        {
          Spectre::Engine::RenderDevice::GetOutput(v3, v34, m);
          (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v34[0] + 176LL))(v34[0]);
          if ( v34[1] )
            std::_Ref_count_base::_Decref(v34[1]);
        }
        v27 = **(_QWORD **)(*((_QWORD *)this + 64) + 18560LL);
        v35 = v27;
        while ( !*(_BYTE *)(v27 + 25) )
        {
          v28 = (Spectre::Engine::ShaderPropertyBlock **)(*(_QWORD *)(v27 + 64) + 256LL);
          v29 = *(_QWORD *)(v27 + 64) + 416LL;
          while ( v28 != (Spectre::Engine::ShaderPropertyBlock **)v29 )
          {
            if ( *v28 )
              Spectre::Engine::ShaderPropertyBlock::FlushState(*v28);
            v28 += 2;
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::DeviceConstantBuffer>>>>,std::_Iterator_base0>::operator++(&v35);
          v27 = v35;
        }
        Spectre::Engine::ShaderManager::DetachDevice(*((_QWORD *)this + 64), v11);
        while ( Spectre::Engine::RenderDevice::GetOutputCount((Spectre::Engine::RenderDevice *)v3) )
        {
          Spectre::Engine::RenderDevice::GetOutput(v3, v34, 0);
          Spectre::Engine::RenderDevice::DeleteOutput(v3, v34);
          if ( v34[1] )
            std::_Ref_count_base::_Decref(v34[1]);
        }
        if ( *(_BYTE *)(v3 + 3976) )
          Spectre::Engine::RenderDevice::Shutdown((Spectre::Engine::RenderDevice *)v3);
        std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v43);
        Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Engine *)((char *)this + 112));
        v30 = *((_QWORD *)this + 11) + 16LL * (unsigned int)Spectre::Engine::Engine::GetDeviceIndex(this);
        v31 = *((_QWORD *)this + 12);
        for ( n = v30 + 16; n != v31; n += 16 )
        {
          std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(v30, n);
          v30 += 16;
        }
        v33 = *(std::_Ref_count_base **)(*((_QWORD *)this + 12) - 8LL);
        if ( v33 )
          std::_Ref_count_base::_Decref(v33);
        *((_QWORD *)this + 12) -= 16LL;
        std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v43);
        *(_OWORD *)v34 = 0;
        std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(&v37, v34);
        if ( v34[1] )
          std::_Ref_count_base::_Decref(v34[1]);
        Trace::LevelSettingsWrapper::Output(
          &gTraceLevelsNativeRenderer_Engine,
          3,
          "Engine::DeleteDevice() -- completed");
        Trace::LevelSettingsWrapper::Output(
          &gTraceLevelsNativeRenderer_Engine,
          3,
          "-----------------------------------------------------------------------------------");
        Spectre::Engine::Engine::PrintDevices(this);
        Spectre::Engine::Engine::RemoveExpiredResources(this);
        Spectre::Engine::Engine::LogInstanceCounts(this);
        std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v41);
        std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v42);
        v10 = v38;
        if ( !v38 )
          return;
        goto LABEL_8;
      }
    }
  }
  Trace::LevelSettingsWrapper::Output(
    &gTraceLevelsNativeRenderer_Engine,
    3,
    "Engine::DeleteDevice() -- device is not attached to this engine");
  std::shared_lock<Spectre::Engine::Mutex>::~shared_lock<Spectre::Engine::Mutex>(v34);
  std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v41);
  std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v42);
  if ( v4 )
  {
    v10 = v4;
LABEL_8:
    std::_Ref_count_base::_Decref(v10);
  }
}

```

## disassembly

```asm
0x180031efc  mov     [rsp-8+arg_10], rbx
0x180031f01  push    rbp
0x180031f02  push    rsi
0x180031f03  push    rdi
0x180031f04  push    r12
0x180031f06  push    r13
0x180031f08  push    r14
0x180031f0a  push    r15
0x180031f0c  lea     rbp, [rsp-27h]
0x180031f11  sub     rsp, 0C0h
0x180031f18  mov     rax, cs:__security_cookie
0x180031f1f  xor     rax, rsp
0x180031f22  mov     [rbp+57h+var_38], rax
0x180031f26  mov     rdi, rcx
0x180031f29  mov     rsi, [rdx]
0x180031f2c  mov     [rbp+57h+var_A0], rsi
0x180031f30  mov     rbx, [rdx+8]
0x180031f34  mov     [rbp+57h+var_98], rbx
0x180031f38  mov     qword ptr [rdx], 0
0x180031f3f  mov     qword ptr [rdx+8], 0
0x180031f47  xorps   xmm0, xmm0
0x180031f4a  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180031f4f  lea     rdx, [rbp+57h+var_A0]
0x180031f53  lea     rcx, [rbp+57h+var_B0]
0x180031f57  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180031f5c  lea     r9, [rbp+57h+var_C0]
0x180031f60  mov     r8, rax
0x180031f63  mov     edx, 8
0x180031f68  mov     rcx, rdi
0x180031f6b  call    ?InvokeCallback@Engine@1Spectre@@IEAAXW4ESpectreNativeRenderCallbackType@12@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z; Spectre::Engine::Engine::InvokeCallback(Spectre::Engine::ESpectreNativeRenderCallbackType,std::shared_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::IRenderOutput>)
0x180031f70  lea     rcx, [rdi+8]; this
0x180031f74  lea     rdx, [rbp+57h+var_68]
0x180031f78  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x180031f7d  nop
0x180031f7e  lea     rcx, [rdi+450h]
0x180031f85  lea     rdx, [rbp+57h+var_78]
0x180031f89  call    ?GetExclusiveLock@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLock(void)
0x180031f8e  nop
0x180031f8f  lea     rdx, [rbp+57h+var_A0]
0x180031f93  lea     rcx, [rbp+57h+var_C0]
0x180031f97  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180031f9c  mov     rdx, rax
0x180031f9f  mov     rcx, rdi
0x180031fa2  call    ?SendDevicePerformanceTelemetry@Engine@1Spectre@@IEAAXV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z; Spectre::Engine::Engine::SendDevicePerformanceTelemetry(std::shared_ptr<Spectre::Engine::RenderDevice>)
0x180031fa7  lea     r8, asc_18016A2B0; "---------------------------------------"...
0x180031fae  mov     r14d, 3
0x180031fb4  mov     edx, r14d
0x180031fb7  lea     r15, ?gTraceLevelsNativeRenderer_Engine@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer_Engine
0x180031fbe  mov     rcx, r15
0x180031fc1  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180031fc6  lea     rdx, [rsi+50h]
0x180031fca  lea     rcx, [rbp+57h+var_58]
0x180031fce  call    ??$LexicalCast@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Utils@Spectre@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Spectre::Utils::LexicalCast<std::string,std::wstring>(std::wstring const &)
0x180031fd3  nop
0x180031fd4  mov     rcx, rax
0x180031fd7  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180031fdc  mov     [rsp+0F0h+var_D0], rax
0x180031fe1  mov     r9d, [rsi+0F4h]
0x180031fe8  lea     r8, aEngineDeletede; "Engine::DeleteDevice() -- removing devi"...
0x180031fef  mov     edx, r14d
0x180031ff2  mov     rcx, r15
0x180031ff5  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180031ffa  nop
0x180031ffb  lea     rcx, [rbp+57h+var_58]
0x180031fff  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180032004  lea     rdx, [rbp+57h+var_C0]
0x180032008  lea     rcx, [rdi+70h]; this
0x18003200c  call    ?GetSharedLockIfNecessary@Lockable@Engine@Spectre@@QEBA?AV?$shared_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetSharedLockIfNecessary(void)
0x180032011  nop
0x180032012  cmp     [rsi+0F90h], rdi
0x180032019  jnz     short loc_180032030
0x18003201b  mov     rax, [rdi+58h]
0x18003201f  jmp     short loc_18003202A
0x180032021  cmp     [rax], rsi
0x180032024  jz      short loc_180032095
0x180032026  add     rax, 10h
0x18003202a  cmp     rax, [rdi+60h]
0x18003202e  jnz     short loc_180032021
0x180032030  lea     r8, aEngineDeletede_1; "Engine::DeleteDevice() -- device is not"...
0x180032037  mov     edx, r14d
0x18003203a  mov     rcx, r15
0x18003203d  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180032042  nop
0x180032043  lea     rcx, [rbp+57h+var_C0]
0x180032047  call    ??1?$shared_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::shared_lock<Spectre::Engine::Mutex>::~shared_lock<Spectre::Engine::Mutex>(void)
0x18003204c  nop
0x18003204d  lea     rcx, [rbp+57h+var_78]
0x180032051  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x180032056  nop
0x180032057  lea     rcx, [rbp+57h+var_68]
0x18003205b  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x180032060  nop
0x180032061  test    rbx, rbx
0x180032064  jz      short loc_18003206E
0x180032066  mov     rcx, rbx; this
0x180032069  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003206e  mov     rcx, [rbp+57h+var_38]
0x180032072  xor     rcx, rsp; StackCookie
0x180032075  call    __security_check_cookie
0x18003207a  mov     rbx, [rsp+0F0h+arg_10]
0x180032082  add     rsp, 0C0h
0x180032089  pop     r15
0x18003208b  pop     r14
0x18003208d  pop     r13
0x18003208f  pop     r12
0x180032091  pop     rdi
0x180032092  pop     rsi
0x180032093  pop     rbp
0x180032094  retn
0x180032095  lea     rcx, [rbp+57h+var_C0]
0x180032099  call    ??1?$shared_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::shared_lock<Spectre::Engine::Mutex>::~shared_lock<Spectre::Engine::Mutex>(void)
0x18003209e  lea     rcx, [rsi+18h]; this
0x1800320a2  lea     rdx, [rbp+57h+var_58]
0x1800320a6  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x1800320ab  nop
0x1800320ac  mov     r12d, [rsi+0F4h]
0x1800320b3  mov     rcx, rsi; this
0x1800320b6  call    ?GetOutputCount@RenderDevice@Engine@Spectre@@QEBAIXZ; Spectre::Engine::RenderDevice::GetOutputCount(void)
0x1800320bb  mov     r15d, eax
0x1800320be  xor     r14d, r14d
0x1800320c1  test    eax, eax
0x1800320c3  jz      short loc_18003213D
0x1800320c5  mov     r8d, r14d
0x1800320c8  lea     rdx, [rbp+57h+var_C0]
0x1800320cc  mov     rcx, rsi
0x1800320cf  call    ?GetOutput@RenderDevice@Engine@Spectre@@QEBA?AV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@std@@I@Z; Spectre::Engine::RenderDevice::GetOutput(uint)
0x1800320d4  nop
0x1800320d5  mov     rbx, [rbp+57h+var_C0]
0x1800320d9  lea     rcx, [rbx+8]
0x1800320dd  lea     rdx, [rbp+57h+var_90]
0x1800320e1  call    ?GetExclusiveLock@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLock(void)
0x1800320e6  nop
0x1800320e7  mov     rax, [rbx]
0x1800320ea  lea     rdx, [rbp+57h+var_B0]
0x1800320ee  mov     rcx, rbx
0x1800320f1  mov     rax, [rax+140h]
0x1800320f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320fd  nop
0x1800320fe  mov     rax, [rbx]
0x180032101  xor     edx, edx
0x180032103  mov     rcx, rbx
0x180032106  mov     rax, [rax+168h]
0x18003210d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032112  nop
0x180032113  lea     rcx, [rbp+57h+var_B0]
0x180032117  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18003211c  nop
0x18003211d  lea     rcx, [rbp+57h+var_90]
0x180032121  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x180032126  nop
0x180032127  mov     rcx, [rbp+57h+var_C0+8]; this
0x18003212b  test    rcx, rcx
0x18003212e  jz      short loc_180032135
0x180032130  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032135  inc     r14d
0x180032138  cmp     r14d, r15d
0x18003213b  jb      short loc_1800320C5
0x18003213d  lea     rdx, [rbp+57h+var_A0]
0x180032141  lea     rcx, [rbp+57h+var_C0]
0x180032145  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x18003214a  lea     r14, [rdi+0B8h]
0x180032151  lea     r8, [rbp+57h+var_C0]
0x180032155  lea     rdx, [rbp+57h+var_90]
0x180032159  mov     rcx, r14
0x18003215c  call    ??$_Find_lower_bound@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@@?$_Tree@V?$_Tmap_traits@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@U?$owner_less@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@V?$allocator@U?$pair@$$CBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@@std@@PEAX@std@@@1@AEBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@1@@Z; std::_Tree<std::_Tmap_traits<std::weak_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::Display>,std::owner_less<std::weak_ptr<Spectre::Engine::RenderDevice>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>>,0>>::_Find_lower_bound<std::weak_ptr<Spectre::Engine::RenderDevice>>(std::weak_ptr<Spectre::Engine::RenderDevice> const &)
0x180032161  mov     rdx, [rax+10h]
0x180032165  mov     rcx, [rbp+57h+var_C0+8]; this
0x180032169  cmp     byte ptr [rdx+19h], 0
0x18003216d  jnz     short loc_18003217C
0x18003216f  cmp     rcx, [rdx+28h]
0x180032173  jb      short loc_18003217C
0x180032175  mov     ebx, 1
0x18003217a  jmp     short loc_18003217E
0x18003217c  xor     ebx, ebx
0x18003217e  test    rcx, rcx
0x180032181  jz      short loc_180032188
0x180032183  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180032188  test    rbx, rbx
0x18003218b  jz      loc_18003227C
0x180032191  lea     rdx, [rbp+57h+var_A0]
0x180032195  lea     rcx, [rbp+57h+var_C0]
0x180032199  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x18003219e  nop
0x18003219f  lea     r8, [rbp+57h+var_C0]
0x1800321a3  lea     rdx, [rbp+57h+var_90]
0x1800321a7  mov     rcx, r14
0x1800321aa  call    ??$_Try_emplace@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@$$V@?$map@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@U?$owner_less@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@V?$allocator@U?$pair@$$CBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$weak_ptr@VRenderDevice@Engine@Spectre@@@1@@Z; std::map<std::weak_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::Display>,std::owner_less<std::weak_ptr<Spectre::Engine::RenderDevice>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>>>::_Try_emplace<std::weak_ptr<Spectre::Engine::RenderDevice>,>(std::weak_ptr<Spectre::Engine::RenderDevice> &&)
0x1800321af  mov     rdx, [rax]
0x1800321b2  add     rdx, 30h ; '0'
0x1800321b6  lea     rcx, [rbp+57h+var_B0]
0x1800321ba  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800321bf  nop
0x1800321c0  mov     rcx, [rbp+57h+var_C0+8]; this
0x1800321c4  xor     r9d, r9d
0x1800321c7  test    rcx, rcx
0x1800321ca  jz      short loc_1800321D4
0x1800321cc  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800321d1  xor     r9d, r9d
0x1800321d4  lea     rdx, [rbp+57h+var_A0]
0x1800321d8  lea     rcx, [rbp+57h+var_90]
0x1800321dc  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x1800321e1  mov     r8, [r14]
0x1800321e4  mov     rax, [r8+8]
0x1800321e8  mov     rcx, rax
0x1800321eb  mov     rdx, r8
0x1800321ee  mov     rbx, [rbp+57h+var_88]
0x1800321f2  cmp     [rax+19h], r9b
0x1800321f6  jnz     short loc_18003221E
0x1800321f8  cmp     [rcx+28h], rbx
0x1800321fc  jnb     short loc_180032204
0x1800321fe  add     rcx, 10h
0x180032202  jmp     short loc_180032215
0x180032204  cmp     [rdx+19h], r9b
0x180032208  jz      short loc_180032212
0x18003220a  cmp     rbx, [rcx+28h]
0x18003220e  cmovb   rdx, rcx
0x180032212  mov     r8, rcx
0x180032215  mov     rcx, [rcx]
0x180032218  cmp     [rcx+19h], r9b
0x18003221c  jz      short loc_1800321F8
0x18003221e  cmp     [rdx+19h], r9b
0x180032222  jnz     short loc_18003223B
0x180032224  mov     rax, [rdx]
0x180032227  jmp     short loc_18003223B
0x180032229  cmp     rbx, [rax+28h]
0x18003222d  jnb     short loc_180032237
0x18003222f  mov     rdx, rax
0x180032232  mov     rax, [rax]
0x180032235  jmp     short loc_18003223B
0x180032237  mov     rax, [rax+10h]
0x18003223b  cmp     [rax+19h], r9b
0x18003223f  jz      short loc_180032229
0x180032241  mov     [rbp+57h+var_C0], r8
0x180032245  mov     [rbp+57h+var_C0+8], rdx
0x180032249  lea     rdx, [rbp+57h+var_C0]
0x18003224d  mov     rcx, r14
0x180032250  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@U?$owner_less@V?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@V?$allocator@U?$pair@$$CBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VDisplay@Engine@Spectre@@@2@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<std::weak_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::Display>,std::owner_less<std::weak_ptr<Spectre::Engine::RenderDevice>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>,void *> *,std::_Tree_node<std::pair<std::weak_ptr<Spectre::Engine::RenderDevice> const,std::shared_ptr<Spectre::Engine::Display>>,void *> *>)
0x180032255  test    rbx, rbx
0x180032258  jz      short loc_180032262
0x18003225a  mov     rcx, rbx; this
0x18003225d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180032262  lea     rdx, [rbp+57h+var_B0]
0x180032266  mov     rcx, rdi
0x180032269  call    ?DeleteDisplay@Engine@1Spectre@@QEAAX$$QEAV?$shared_ptr@VDisplay@Engine@Spectre@@@std@@@Z; Spectre::Engine::Engine::DeleteDisplay(std::shared_ptr<Spectre::Engine::Display> &&)
0x18003226e  mov     rcx, [rbp+57h+var_A8]; this
0x180032272  test    rcx, rcx
0x180032275  jz      short loc_18003227C
0x180032277  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003227c  lea     rdx, [rbp+57h+var_A0]
0x180032280  lea     rcx, [rbp+57h+var_90]
0x180032284  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180032289  mov     rdx, rax
0x18003228c  mov     rcx, rdi
0x18003228f  call    ?DetachDevice@Engine@1Spectre@@QEAAXV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z; Spectre::Engine::Engine::DetachDevice(std::shared_ptr<Spectre::Engine::RenderDevice>)
0x180032294  cmp     byte ptr [rsi+0F88h], 0
0x18003229b  jz      short loc_1800322AC
0x18003229d  mov     rax, [rsi]
0x1800322a0  mov     rcx, rsi
0x1800322a3  mov     rax, [rax+8]
0x1800322a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322ac  xor     ebx, ebx
0x1800322ae  test    r15d, r15d
0x1800322b1  jz      short loc_1800322EC
0x1800322b3  mov     r8d, ebx
0x1800322b6  lea     rdx, [rbp+57h+var_C0]
0x1800322ba  mov     rcx, rsi
0x1800322bd  call    ?GetOutput@RenderDevice@Engine@Spectre@@QEBA?AV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@std@@I@Z; Spectre::Engine::RenderDevice::GetOutput(uint)
0x1800322c2  nop
0x1800322c3  mov     rcx, [rbp+57h+var_C0]
0x1800322c7  mov     rax, [rcx]
0x1800322ca  mov     rax, [rax+0B0h]
0x1800322d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322d6  nop
0x1800322d7  mov     rcx, [rbp+57h+var_C0+8]; this
0x1800322db  test    rcx, rcx
0x1800322de  jz      short loc_1800322E5
0x1800322e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800322e5  inc     ebx
0x1800322e7  cmp     ebx, r15d
0x1800322ea  jb      short loc_1800322B3
0x1800322ec  mov     rax, [rdi+200h]
0x1800322f3  mov     rax, [rax+4880h]
0x1800322fa  mov     rax, [rax]
0x1800322fd  mov     [rbp+57h+var_B0], rax
0x180032301  cmp     byte ptr [rax+19h], 0
0x180032305  jnz     short loc_180032340
0x180032307  mov     rbx, [rax+40h]
0x18003230b  add     rbx, 100h
0x180032312  lea     r14, [rbx+0A0h]
0x180032319  jmp     short loc_18003232C
0x18003231b  mov     rcx, [rbx]; this
0x18003231e  test    rcx, rcx
0x180032321  jz      short loc_180032328
0x180032323  call    ?FlushState@ShaderPropertyBlock@Engine@Spectre@@QEAAXXZ; Spectre::Engine::ShaderPropertyBlock::FlushState(void)
0x180032328  add     rbx, 10h
0x18003232c  cmp     rbx, r14
0x18003232f  jnz     short loc_18003231B
0x180032331  lea     rcx, [rbp+57h+var_B0]
0x180032335  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceConstantBuffer@Engine@Spectre@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::DeviceConstantBuffer>>>>,std::_Iterator_base0>::operator++(void)
0x18003233a  mov     rax, [rbp+57h+var_B0]
  ... truncated ...
```
