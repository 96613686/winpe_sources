# Spectre::Engine::Camera::RenderEffects(std::shared_ptr<Spectre::Engine::RenderDevice> const &,std::shared_ptr<Spectre::Engine::IRenderOutput> const &)

- ea: `0x1800575e4`
- end: `0x1800578be`
- name: `?RenderEffects@Camera@Engine@Spectre@@IEAAXAEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@AEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180057548`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18000e87c`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012ba8`
- `0x180012df8`
- `0x180013240`
- `0x18001c674`
- `0x18001f2bc`
- `0x180025f5c`
- `0x18002921c`
- `0x18002fadc`
- `0x180030700`
- `0x180038ddc`
- `0x1800575e4`
- `0x18006b058`
- `0x18006c0f4`
- `0x180095fac`
- `0x180096060`
- `0x1800e7010`

## string_xrefs

- `0x18005770c`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\camera.cpp`
- `0x18005775f`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\camera.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall Spectre::Engine::Camera::RenderEffects(__int64 a1, __int64 *a2, _QWORD *a3)
{
  __int64 v6; // rsi
  char result; // al
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rbx
  int v12; // eax
  int v13; // r8d
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  __int128 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  _BYTE v21[8]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v26; // [rsp+78h] [rbp-88h]
  _BYTE v27[8]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v28; // [rsp+88h] [rbp-78h]
  _BYTE v29[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v32[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v33[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+118h] [rbp+18h] BYREF

  v6 = a1 + 1696;
  result = type_info::operator==(*(_QWORD *)(a1 + 1696), (__int64)&std::nullptr_t `RTTI Type Descriptor');
  if ( !result )
  {
    std::operator+<char>(v33, a1 + 24, " effect");
    v8 = *a2;
    Spectre::Engine::Lockable::VerifyWriteAccess((Spectre::Engine::Lockable *)(v8 + 24));
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
      v27,
      v8 + 272);
    Spectre::Engine::GpuProfilerScope::GpuProfilerScope(v30, v27, v33);
    v9 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a3 + 200LL))(*a3, v21);
    Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v31, v9, v33);
    if ( v22 )
      std::_Ref_count_base::_Decwref(v22);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 152LL))(*a3);
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(&v23, v10);
    Spectre::Engine::ImageProcessingManager::GetEffects(v23, &v19, v6);
    v11 = (_QWORD *)v19;
    if ( (_QWORD)v19 != *((_QWORD *)&v19 + 1) )
    {
      if ( (unsigned __int64)((__int64)(*((_QWORD *)&v19 + 1) - v19) >> 4) > 1 )
      {
        std::string::string(v32, "Camera::RenderEffects() -- only one effect per output is currently supported");
        v12 = std::string::string(
                v29,
                "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\camera.cpp");
        Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
          (unsigned int)pExceptionObject,
          v12,
          v13,
          (unsigned int)v32,
          0);
        throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
      }
      if ( *(_DWORD *)(*(_QWORD *)v19 + 176LL) != 1 )
      {
        std::string::string(v32, "Camera::RenderEffects() -- effect must have local scope to be rendered by a camera");
        v14 = std::string::string(
                v29,
                "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\camera.cpp");
        Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
          (unsigned int)pExceptionObject,
          v14,
          v15,
          (unsigned int)v32,
          0);
        throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
      }
      if ( *(_BYTE *)(*(_QWORD *)v19 + 136LL) )
      {
        std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          &v25,
          a1 + 136);
        Spectre::Engine::FrameBuffer::GetTexture(v25, v32);
        v16 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
                v29,
                v11);
        Spectre::Engine::ImageProcessingManager::ApplyCameraEffect(v23, (unsigned int)v21, (_DWORD)a3, v16, v17);
        if ( v26 )
          std::_Ref_count_base::_Decref(v26);
        v18 = *(_QWORD *)(a1 + 1760);
        if ( v18 )
          (*(void (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v18 + 16LL))(v18, *v11, v21);
        if ( v22 )
          std::_Ref_count_base::_Decref(v22);
      }
    }
    if ( (_QWORD)v19 )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<Spectre::Engine::IRenderOutput>>>(v19, *((_QWORD *)&v19 + 1));
      std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF0uLL);
      v19 = 0;
      v20 = 0;
    }
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v31);
    Spectre::Engine::GpuProfilerScope::~GpuProfilerScope((Spectre::Engine::GpuProfilerScope *)v30);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    return std::string::_Tidy_deallocate(v33);
  }
  return result;
}

```

## disassembly

```asm
0x1800575e4  push    rbp
0x1800575e6  push    rbx
0x1800575e7  push    rsi
0x1800575e8  push    rdi
0x1800575e9  push    r14
0x1800575eb  lea     rbp, [rsp-60h]
0x1800575f0  sub     rsp, 160h
0x1800575f7  mov     rax, cs:__security_cookie
0x1800575fe  xor     rax, rsp
0x180057601  mov     [rbp+80h+var_30], rax
0x180057605  mov     r14, r8
0x180057608  mov     rbx, rdx
0x18005760b  mov     rdi, rcx
0x18005760e  lea     rsi, [rcx+6A0h]
0x180057615  lea     rdx, ??_R0$$T@8; std::nullptr_t `RTTI Type Descriptor'
0x18005761c  mov     rcx, [rsi]
0x18005761f  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x180057624  test    al, al
0x180057626  jnz     loc_1800578A4
0x18005762c  lea     rdx, [rdi+18h]
0x180057630  lea     r8, aEffect; " effect"
0x180057637  lea     rcx, [rbp+80h+var_88]
0x18005763b  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180057640  nop
0x180057641  mov     rbx, [rbx]
0x180057644  lea     rcx, [rbx+18h]; this
0x180057648  call    ?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ; Spectre::Engine::Lockable::VerifyWriteAccess(void)
0x18005764d  lea     rdx, [rbx+110h]
0x180057654  lea     rcx, [rbp+80h+var_100]
0x180057658  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18005765d  nop
0x18005765e  lea     r8, [rbp+80h+var_88]
0x180057662  lea     rdx, [rbp+80h+var_100]
0x180057666  lea     rcx, [rbp+80h+var_D0]
0x18005766a  call    ??0GpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::GpuProfilerScope::GpuProfilerScope(std::shared_ptr<Spectre::Engine::CommandList> const &,std::string const &)
0x18005766f  nop
0x180057670  mov     rcx, [r14]
0x180057673  mov     rax, [rcx]
0x180057676  lea     rdx, [rsp+180h+var_130]
0x18005767b  mov     rax, [rax+0C8h]
0x180057682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057687  nop
0x180057688  lea     r8, [rbp+80h+var_88]
0x18005768c  mov     rdx, rax
0x18005768f  lea     rcx, [rbp+80h+var_C0]
0x180057693  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180057698  nop
0x180057699  mov     rcx, [rsp+180h+var_128]; this
0x18005769e  test    rcx, rcx
0x1800576a1  jz      short loc_1800576A8
0x1800576a3  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800576a8  mov     rcx, [r14]
0x1800576ab  mov     rax, [rcx]
0x1800576ae  mov     rax, [rax+98h]
0x1800576b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576ba  mov     rdx, rax
0x1800576bd  lea     rcx, [rsp+180h+var_120]
0x1800576c2  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800576c7  nop
0x1800576c8  mov     r8, rsi
0x1800576cb  lea     rdx, [rsp+180h+var_148]
0x1800576d0  mov     rcx, [rsp+180h+var_120]
0x1800576d5  call    ?GetEffects@ImageProcessingManager@Engine@Spectre@@QEBA?AV?$vector@V?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@std@@@2@@std@@AEBVtype_index@5@@Z; Spectre::Engine::ImageProcessingManager::GetEffects(std::type_index const &)
0x1800576da  nop
0x1800576db  mov     rax, qword ptr [rsp+180h+var_148+8]
0x1800576e0  mov     rbx, qword ptr [rsp+180h+var_148]
0x1800576e5  cmp     rbx, rax
0x1800576e8  jz      loc_18005782C
0x1800576ee  sub     rax, rbx
0x1800576f1  sar     rax, 4
0x1800576f5  cmp     rax, 1
0x1800576f9  jbe     short loc_180057742
0x1800576fb  lea     rdx, aCameraRenderef; "Camera::RenderEffects() -- only one eff"...
0x180057702  lea     rcx, [rbp+80h+var_A8]
0x180057706  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005770b  nop
0x18005770c  lea     rdx, aOnecoreuapWind_42; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180057713  lea     rcx, [rbp+80h+var_F0]
0x180057717  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005771c  mov     byte ptr [rsp+180h+var_160], 0
0x180057721  lea     r9, [rbp+80h+var_A8]
0x180057725  mov     rdx, rax
0x180057728  lea     rcx, [rbp+80h+pExceptionObject]
0x18005772c  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180057731  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180057738  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18005773c  call    _CxxThrowException_0
0x180057742  mov     rax, [rbx]
0x180057745  cmp     dword ptr [rax+0B0h], 1
0x18005774c  jz      short loc_180057795
0x18005774e  lea     rdx, aCameraRenderef_0; "Camera::RenderEffects() -- effect must "...
0x180057755  lea     rcx, [rbp+80h+var_A8]
0x180057759  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005775e  nop
0x18005775f  lea     rdx, aOnecoreuapWind_42; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180057766  lea     rcx, [rbp+80h+var_F0]
0x18005776a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005776f  mov     byte ptr [rsp+180h+var_160], 0
0x180057774  lea     r9, [rbp+80h+var_A8]
0x180057778  mov     rdx, rax
0x18005777b  lea     rcx, [rbp+80h+pExceptionObject]
0x18005777f  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180057784  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18005778b  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18005778f  call    _CxxThrowException_0
0x180057795  cmp     byte ptr [rax+88h], 0
0x18005779c  jz      loc_18005782C
0x1800577a2  lea     rdx, [rdi+88h]
0x1800577a9  lea     rcx, [rsp+180h+var_110]
0x1800577ae  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800577b3  nop
0x1800577b4  lea     rdx, [rbp+80h+var_A8]
0x1800577b8  mov     rcx, [rsp+180h+var_110]
0x1800577bd  call    ?GetTexture@FrameBuffer@Engine@Spectre@@QEBA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@XZ; Spectre::Engine::FrameBuffer::GetTexture(void)
0x1800577c2  mov     r9, rax
0x1800577c5  mov     rdx, rbx
0x1800577c8  lea     rcx, [rbp+80h+var_F0]
0x1800577cc  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800577d1  mov     [rsp+180h+var_160], r9
0x1800577d6  mov     r9, rax
0x1800577d9  mov     r8, r14
0x1800577dc  lea     rdx, [rsp+180h+var_130]
0x1800577e1  mov     rcx, [rsp+180h+var_120]
0x1800577e6  call    ?ApplyCameraEffect@ImageProcessingManager@Engine@Spectre@@QEBA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@AEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@V?$shared_ptr@VImageProcessingEffect@Engine@Spectre@@@5@V45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Spectre::Engine::ImageProcessingManager::ApplyCameraEffect(std::shared_ptr<Spectre::Engine::IRenderOutput> const &,std::shared_ptr<Spectre::Engine::ImageProcessingEffect>,std::shared_ptr<Spectre::Engine::Texture>,std::string const &)
0x1800577eb  nop
0x1800577ec  mov     rcx, [rsp+180h+var_108]; this
0x1800577f1  test    rcx, rcx
0x1800577f4  jz      short loc_1800577FB
0x1800577f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800577fb  mov     rcx, [rdi+6E0h]
0x180057802  test    rcx, rcx
0x180057805  jz      short loc_18005781C
0x180057807  mov     rax, [rcx]
0x18005780a  lea     r8, [rsp+180h+var_130]
0x18005780f  mov     rdx, [rbx]
0x180057812  mov     rax, [rax+10h]
0x180057816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005781b  nop
0x18005781c  mov     rcx, [rsp+180h+var_128]; this
0x180057821  test    rcx, rcx
0x180057824  jz      short loc_18005782C
0x180057826  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005782b  nop
0x18005782c  mov     rcx, qword ptr [rsp+180h+var_148]
0x180057831  test    rcx, rcx
0x180057834  jz      short loc_180057868
0x180057836  mov     rdx, qword ptr [rsp+180h+var_148+8]
0x18005783b  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Spectre::Engine::IRenderOutput>>>(std::shared_ptr<Spectre::Engine::IRenderOutput> *,std::shared_ptr<Spectre::Engine::IRenderOutput> * const,std::allocator<std::shared_ptr<Spectre::Engine::IRenderOutput>> &)
0x180057840  mov     rcx, qword ptr [rsp+180h+var_148]
0x180057845  mov     rdx, [rsp+180h+var_138]
0x18005784a  sub     rdx, rcx
0x18005784d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180057851  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180057856  xorps   xmm0, xmm0
0x180057859  movdqu  [rsp+180h+var_148], xmm0
0x18005785f  mov     [rsp+180h+var_138], 0
0x180057868  mov     rcx, [rsp+180h+var_118]; this
0x18005786d  test    rcx, rcx
0x180057870  jz      short loc_180057878
0x180057872  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180057877  nop
0x180057878  lea     rcx, [rbp+80h+var_C0]; this
0x18005787c  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180057881  nop
0x180057882  lea     rcx, [rbp+80h+var_D0]; this
0x180057886  call    ??1GpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::GpuProfilerScope::~GpuProfilerScope(void)
0x18005788b  nop
0x18005788c  mov     rcx, [rbp+80h+var_F8]; this
0x180057890  test    rcx, rcx
0x180057893  jz      short loc_18005789B
0x180057895  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005789a  nop
0x18005789b  lea     rcx, [rbp+80h+var_88]
0x18005789f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800578a4  mov     rcx, [rbp+80h+var_30]
0x1800578a8  xor     rcx, rsp; StackCookie
0x1800578ab  call    __security_check_cookie
0x1800578b0  add     rsp, 160h
0x1800578b7  pop     r14
0x1800578b9  pop     rdi
0x1800578ba  pop     rsi
0x1800578bb  pop     rbx
0x1800578bc  pop     rbp
0x1800578bd  retn
```
