# Spectre::Engine::MeshInstance::Render(std::shared_ptr<Spectre::Engine::CommandList> const &,unsigned __int64,std::shared_ptr<Spectre::Engine::Camera const> const &)

- ea: `0x1800492b0`
- end: `0x180049749`
- name: `?Render@MeshInstance@Engine@Spectre@@UEBAXAEBV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@_KAEBV?$shared_ptr@$$CBVCamera@Engine@Spectre@@@5@@Z`
- size: `1177`
- prototype: `__int64 __fastcall(Spectre::Engine::MeshInstance *this)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008c630`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x180012ba8`
- `0x18001c60c`
- `0x18001c630`
- `0x18001c674`
- `0x180025f5c`
- `0x180030cd4`
- `0x180036ecc`
- `0x1800377bc`
- `0x180039f60`
- `0x18003a600`
- `0x18003c398`
- `0x1800409a8`
- `0x18004151c`
- `0x180041a20`
- `0x180045a2c`
- `0x1800488b0`
- `0x180048a70`
- `0x1800492b0`
- `0x180049750`
- `0x18005b690`
- `0x18007b13c`
- `0x180094f14`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x180049466`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x180049466`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall Spectre::Engine::MeshInstance::Render(
        Spectre::Engine::MeshInstance *this,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // r15d
  int v8; // ecx
  __int64 GpuProfiler; // rax
  __int64 v10; // r15
  _QWORD *SceneNode; // rax
  __int64 Name; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  _QWORD *v17; // rax
  char v18; // r12
  unsigned __int64 i; // r14
  void (__fastcall ***v20)(_QWORD); // rbx
  __int64 v21; // r13
  _QWORD *Extension; // rax
  __int64 v23; // r15
  __int64 v24; // r12
  Spectre::Engine::ShaderPropertyBlock *v25; // rcx
  char v26; // dl
  __int64 v27; // rcx
  __m128 v28; // xmm5
  unsigned int v29; // xmm6_4
  __m128 v30; // xmm7
  __int64 v31; // rcx
  Spectre::Engine::ShaderPropertyBlock *v32; // rcx
  Spectre::Engine::ShaderPropertyBlock *v33; // rcx
  Spectre::Engine::ShaderPropertyBlock *v34; // rcx
  char v35; // [rsp+30h] [rbp-D0h]
  void (__fastcall ***v36)(_QWORD); // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v40; // [rsp+58h] [rbp-A8h]
  _BYTE v41[8]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v42; // [rsp+68h] [rbp-98h]
  std::_Ref_count_base *v43[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v45; // [rsp+88h] [rbp-78h]
  _BYTE v46[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v47[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v48[64]; // [rsp+E0h] [rbp-20h] BYREF

  v5 = a3;
  v38 = a3;
  v8 = *(_DWORD *)(*(_QWORD *)a4 + 440LL);
  if ( (v8 & 0x10000) != 0 && (v8 & 0x800000) != 0 )
    Spectre::Engine::MeshInstance::RenderSymbols(this);
  *(_OWORD *)v43 = 0;
  if ( (*(_DWORD *)(*(_QWORD *)a4 + 440LL) & 0x4000000) != 0 )
  {
    GpuProfiler = Spectre::Engine::CommandList::GetGpuProfiler(*a2, &v36);
    std::weak_ptr<Spectre::Engine::GpuProfiler>::lock(GpuProfiler, &v39);
    if ( v37 )
      std::_Ref_count_base::_Decwref(v37);
    v10 = v39;
    if ( v39 )
    {
      SceneNode = (_QWORD *)Spectre::Engine::Component::GetSceneNode(this, v41);
      Name = Spectre::Engine::SceneNode::GetName(*SceneNode, v48);
      v13 = std::operator+<char>(v47, *(_QWORD *)a4 + 24LL, "_");
      v14 = std::operator+<char>(v46, v13, Name);
      v15 = std::operator+<char>(&v44, v14, "_Render");
      v16 = Spectre::Engine::GpuProfiler::BeginTimeSpanMarker(v10, &v36, v15, a2);
      std::weak_ptr<Spectre::Engine::RendererResource>::operator=(v43, v16);
      if ( v37 )
        std::_Ref_count_base::_Decwref(v37);
      std::string::_Tidy_deallocate(&v44);
      std::string::_Tidy_deallocate(v46);
      std::string::_Tidy_deallocate(v47);
      std::string::_Tidy_deallocate(v48);
      if ( v42 )
        std::_Ref_count_base::_Decref(v42);
    }
    if ( v40 )
      std::_Ref_count_base::_Decref(v40);
    v5 = v38;
  }
  v17 = (_QWORD *)Spectre::Engine::Component::GetSceneNode(this, v41);
  Spectre::Engine::SceneNode::GetWorldTransformMatrix(*v17, v48);
  DirectX::XMMatrixDeterminant();
  v18 = (unsigned int)_o__fdsign() != 0;
  v35 = v18;
  if ( v42 )
    std::_Ref_count_base::_Decref(v42);
  for ( i = 0; i < 0x2E8BA2E8BA2E8BA3LL * ((__int64)(*((_QWORD *)this + 14) - *((_QWORD *)this + 13)) >> 3); ++i )
  {
    if ( Spectre::Engine::MeshInstance::IsMaterialEnabled(this, i) && (i >= 0x20 || ((1 << i) & dword_180236980) != 0) )
    {
      Spectre::Engine::MeshInstance::GetMaterial(this, &v36, i);
      v20 = v36;
      if ( v36 )
      {
        Spectre::Engine::Material::ApplyState((_DWORD)v36, (unsigned int)&v44, v5, (_DWORD)a2, v18);
        v21 = v44;
        if ( !Spectre::Engine::VertexLayoutBase::VertexLayoutDesc::IsEmpty((Spectre::Engine::VertexLayoutBase::VertexLayoutDesc *)(v44 + 128)) )
        {
          Spectre::Engine::FrameBuffer::GetTexture(v20, &v39);
          if ( v39 )
          {
            Extension = (_QWORD *)Spectre::Engine::ShaderFamily::GetExtension(v39, v41);
            (*(void (__fastcall **)(_QWORD, Spectre::Engine::MeshInstance *, unsigned __int64))(*(_QWORD *)*Extension
                                                                                              + 48LL))(
              *Extension,
              this,
              i);
            if ( v42 )
              std::_Ref_count_base::_Decref(v42);
            v23 = 88 * i;
            v24 = *((_QWORD *)this + 13);
            v25 = *(Spectre::Engine::ShaderPropertyBlock **)(88 * i + v24 + 24);
            if ( v25 )
              Spectre::Engine::ShaderPropertyBlock::ApplyState(v25);
            v26 = *((_BYTE *)this + 168);
            v27 = *(_QWORD *)(*a2 + 96LL);
            if ( v26 != *(_BYTE *)(v27 + 14532) )
            {
              *(_BYTE *)(v27 + 14532) = v26;
              *(_BYTE *)(v27 + 14533) = 1;
            }
            v28 = (__m128)*((unsigned int *)this + 44);
            v29 = *((_DWORD *)this + 45);
            v30 = (__m128)*((unsigned int *)this + 46);
            v31 = *(_QWORD *)(*a2 + 96LL);
            if ( _mm_movemask_ps(
                   _mm_cmpneq_ps(
                     _mm_movelh_ps(
                       _mm_unpacklo_ps((__m128)*((unsigned int *)this + 43), v28),
                       _mm_unpacklo_ps((__m128)v29, v30)),
                     *(__m128 *)(v31 + 14516))) )
            {
              *(_DWORD *)(v31 + 14516) = *((_DWORD *)this + 43);
              *(_DWORD *)(v31 + 14520) = v28.m128_i32[0];
              *(_DWORD *)(v31 + 14524) = v29;
              *(_DWORD *)(v31 + 14528) = v30.m128_i32[0];
              *(_BYTE *)(v31 + 14533) = 1;
            }
            v32 = *(Spectre::Engine::ShaderPropertyBlock **)(v23 + v24 + 40);
            if ( v32 )
              Spectre::Engine::ShaderPropertyBlock::ApplyState(v32);
            v33 = *(Spectre::Engine::ShaderPropertyBlock **)(v23 + v24 + 56);
            if ( v33 )
              Spectre::Engine::ShaderPropertyBlock::ApplyState(v33);
            v34 = *(Spectre::Engine::ShaderPropertyBlock **)(v23 + v24 + 72);
            if ( v34 )
              Spectre::Engine::ShaderPropertyBlock::ApplyState(v34);
            Spectre::Engine::Mesh::Render(*((_QWORD *)this + 11), a2, *(_QWORD *)(v21 + 136));
            v5 = v38;
            v18 = v35;
          }
          if ( v40 )
            std::_Ref_count_base::_Decref(v40);
        }
        if ( v45 )
          std::_Ref_count_base::_Decref(v45);
      }
      if ( v37 )
        std::_Ref_count_base::_Decref(v37);
    }
  }
  std::weak_ptr<Spectre::Engine::GpuProfiler>::lock(v43, &v36);
  if ( v36 )
    (**v36)(v36);
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
  if ( v43[1] )
    std::_Ref_count_base::_Decwref(v43[1]);
}

```

## disassembly

```asm
0x1800492b0  mov     rax, rsp
0x1800492b3  push    rbp
0x1800492b4  push    rbx
0x1800492b5  push    rsi
0x1800492b6  push    rdi
0x1800492b7  push    r12
0x1800492b9  push    r13
0x1800492bb  push    r14
0x1800492bd  push    r15
0x1800492bf  lea     rbp, [rsp-58h]
0x1800492c4  sub     rsp, 158h
0x1800492cb  movaps  xmmword ptr [rax-58h], xmm6
0x1800492cf  movaps  xmmword ptr [rax-68h], xmm7
0x1800492d3  mov     rax, cs:__security_cookie
0x1800492da  xor     rax, rsp
0x1800492dd  mov     [rbp+90h+var_70], rax
0x1800492e1  mov     r14, r9
0x1800492e4  mov     r15, r8
0x1800492e7  mov     [rsp+190h+var_148], r8
0x1800492ec  mov     rsi, rdx
0x1800492ef  mov     rdi, rcx
0x1800492f2  mov     rax, [r9]
0x1800492f5  mov     ecx, [rax+1B8h]
0x1800492fb  bt      ecx, 10h
0x1800492ff  jnb     short loc_18004930F
0x180049301  bt      ecx, 17h
0x180049305  jnb     short loc_18004930F
0x180049307  mov     rcx, rdi; this
0x18004930a  call    ?RenderSymbols@MeshInstance@Engine@Spectre@@EEBAXAEBV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@_KAEBV?$shared_ptr@$$CBVCamera@Engine@Spectre@@@5@@Z; Spectre::Engine::MeshInstance::RenderSymbols(std::shared_ptr<Spectre::Engine::CommandList> const &,unsigned __int64,std::shared_ptr<Spectre::Engine::Camera const> const &)
0x18004930f  xorps   xmm0, xmm0
0x180049312  movdqu  xmmword ptr [rsp+190h+var_120], xmm0
0x180049318  mov     rax, [r14]
0x18004931b  test    dword ptr [rax+1B8h], 4000000h
0x180049325  jz      loc_180049438
0x18004932b  lea     rdx, [rsp+190h+var_158]
0x180049330  mov     rcx, [rsi]
0x180049333  call    ?GetGpuProfiler@CommandList@Engine@Spectre@@QEBA?BV?$weak_ptr@VGpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::CommandList::GetGpuProfiler(void)
0x180049338  lea     rdx, [rsp+190h+var_140]
0x18004933d  mov     rcx, rax
0x180049340  call    ?lock@?$weak_ptr@VGpuProfiler@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VGpuProfiler@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::GpuProfiler>::lock(void)
0x180049345  nop
0x180049346  mov     rcx, [rsp+190h+var_150]; this
0x18004934b  test    rcx, rcx
0x18004934e  jz      short loc_180049355
0x180049350  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180049355  mov     r15, [rsp+190h+var_140]
0x18004935a  test    r15, r15
0x18004935d  jz      loc_180049424
0x180049363  lea     rdx, [rsp+190h+var_130]
0x180049368  mov     rcx, rdi
0x18004936b  call    ?GetSceneNode@Component@Engine@Spectre@@QEBA?AV?$shared_ptr@$$CBVSceneNode@Engine@Spectre@@@std@@XZ; Spectre::Engine::Component::GetSceneNode(void)
0x180049370  nop
0x180049371  lea     rdx, [rbp+90h+var_B0]
0x180049375  mov     rcx, [rax]
0x180049378  call    ?GetName@SceneNode@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Spectre::Engine::SceneNode::GetName(void)
0x18004937d  mov     rbx, rax
0x180049380  mov     rdx, [r14]
0x180049383  add     rdx, 18h
0x180049387  lea     r8, asc_180173D68; "_"
0x18004938e  lea     rcx, [rbp+90h+var_D0]
0x180049392  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180049397  nop
0x180049398  mov     r8, rbx
0x18004939b  mov     rdx, rax
0x18004939e  lea     rcx, [rbp+90h+var_F0]
0x1800493a2  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1800493a7  nop
0x1800493a8  lea     r8, aRender; "_Render"
0x1800493af  mov     rdx, rax
0x1800493b2  lea     rcx, [rbp+90h+var_110]
0x1800493b6  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800493bb  nop
0x1800493bc  mov     r9, rsi
0x1800493bf  mov     r8, rax
0x1800493c2  lea     rdx, [rsp+190h+var_158]
0x1800493c7  mov     rcx, r15
0x1800493ca  call    ?BeginTimeSpanMarker@GpuProfiler@Engine@Spectre@@QEAA?AV?$weak_ptr@VITimeSpanMarker@GpuProfilerFrame@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@AEBV?$shared_ptr@VCommandList@Engine@Spectre@@@5@@Z; Spectre::Engine::GpuProfiler::BeginTimeSpanMarker(std::string const &,std::shared_ptr<Spectre::Engine::CommandList> const &)
0x1800493cf  mov     rdx, rax
0x1800493d2  lea     rcx, [rsp+190h+var_120]
0x1800493d7  call    ??4?$weak_ptr@VRendererResource@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::weak_ptr<Spectre::Engine::RendererResource>::operator=(std::weak_ptr<Spectre::Engine::RendererResource> &&)
0x1800493dc  mov     rcx, [rsp+190h+var_150]; this
0x1800493e1  test    rcx, rcx
0x1800493e4  jz      short loc_1800493EC
0x1800493e6  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800493eb  nop
0x1800493ec  lea     rcx, [rbp+90h+var_110]
0x1800493f0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800493f5  nop
0x1800493f6  lea     rcx, [rbp+90h+var_F0]
0x1800493fa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800493ff  nop
0x180049400  lea     rcx, [rbp+90h+var_D0]
0x180049404  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180049409  nop
0x18004940a  lea     rcx, [rbp+90h+var_B0]
0x18004940e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180049413  nop
0x180049414  mov     rcx, [rsp+190h+var_128]; this
0x180049419  test    rcx, rcx
0x18004941c  jz      short loc_180049424
0x18004941e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049423  nop
0x180049424  mov     rcx, [rsp+190h+var_138]; this
0x180049429  test    rcx, rcx
0x18004942c  jz      short loc_180049433
0x18004942e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049433  mov     r15, [rsp+190h+var_148]
0x180049438  lea     rdx, [rsp+190h+var_130]
0x18004943d  mov     rcx, rdi
0x180049440  call    ?GetSceneNode@Component@Engine@Spectre@@QEBA?AV?$shared_ptr@$$CBVSceneNode@Engine@Spectre@@@std@@XZ; Spectre::Engine::Component::GetSceneNode(void)
0x180049445  nop
0x180049446  lea     rdx, [rbp+90h+var_B0]
0x18004944a  mov     rcx, [rax]
0x18004944d  call    ?GetWorldTransformMatrix@SceneNode@Engine@Spectre@@QEBA?AUMatrix@Math@Utils@3@XZ; Spectre::Engine::SceneNode::GetWorldTransformMatrix(void)
0x180049452  movups  xmm0, xmmword ptr [rax]
0x180049455  movups  xmm1, xmmword ptr [rax+10h]
0x180049459  movups  xmm2, xmmword ptr [rax+20h]
0x18004945d  movups  xmm3, xmmword ptr [rax+30h]
0x180049461  call    ?XMMatrixDeterminant@DirectX@@YQ?AT__m128@@UXMMATRIX@1@@Z; DirectX::XMMatrixDeterminant(DirectX::XMMATRIX)
0x180049466  call    cs:__imp__o__fdsign
0x18004946c  test    eax, eax
0x18004946e  setnz   r12b
0x180049472  mov     [rsp+190h+var_160], r12b
0x180049477  mov     rcx, [rsp+190h+var_128]; this
0x18004947c  test    rcx, rcx
0x18004947f  jz      short loc_180049486
0x180049481  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049486  xor     r14d, r14d
0x180049489  mov     rax, [rdi+70h]
0x18004948d  sub     rax, [rdi+68h]
0x180049491  sar     rax, 3
0x180049495  mov     r13, 2E8BA2E8BA2E8BA3h
0x18004949f  imul    rax, r13
0x1800494a3  test    rax, rax
0x1800494a6  jz      loc_1800496D6
0x1800494ac  mov     rdx, r14; unsigned __int64
0x1800494af  mov     rcx, rdi; this
0x1800494b2  call    ?IsMaterialEnabled@MeshInstance@Engine@Spectre@@QEBA_N_K@Z; Spectre::Engine::MeshInstance::IsMaterialEnabled(unsigned __int64)
0x1800494b7  test    al, al
0x1800494b9  jz      loc_1800496BA
0x1800494bf  cmp     r14, 20h ; ' '
0x1800494c3  jnb     short loc_1800494DB
0x1800494c5  mov     rcx, r14
0x1800494c8  mov     eax, 1
0x1800494cd  shl     eax, cl
0x1800494cf  test    cs:dword_180236980, eax
0x1800494d5  jz      loc_1800496BA
0x1800494db  mov     r8, r14
0x1800494de  lea     rdx, [rsp+190h+var_158]
0x1800494e3  mov     rcx, rdi
0x1800494e6  call    ?GetMaterial@MeshInstance@Engine@Spectre@@QEBA?AV?$shared_ptr@VMaterial@Engine@Spectre@@@std@@_K@Z; Spectre::Engine::MeshInstance::GetMaterial(unsigned __int64)
0x1800494eb  nop
0x1800494ec  mov     rbx, [rsp+190h+var_158]
0x1800494f1  test    rbx, rbx
0x1800494f4  jz      loc_1800496AB
0x1800494fa  mov     [rsp+190h+var_170], r12b
0x1800494ff  mov     r9, rsi
0x180049502  mov     r8, r15
0x180049505  lea     rdx, [rbp+90h+var_110]
0x180049509  mov     rcx, rbx
0x18004950c  call    ?ApplyState@Material@Engine@Spectre@@QEAA?AU?$pair@V?$shared_ptr@VShaderPipeline@Engine@Spectre@@@std@@VShaderTypeGroup@Engine@Spectre@@@std@@_KAEBV?$shared_ptr@VCommandList@Engine@Spectre@@@5@_N@Z; Spectre::Engine::Material::ApplyState(unsigned __int64,std::shared_ptr<Spectre::Engine::CommandList> const &,bool)
0x180049511  nop
0x180049512  mov     r13, [rbp+90h+var_110]
0x180049516  lea     rcx, [r13+80h]; this
0x18004951d  call    ?IsEmpty@VertexLayoutDesc@VertexLayoutBase@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::VertexLayoutBase::VertexLayoutDesc::IsEmpty(void)
0x180049522  test    al, al
0x180049524  jnz     loc_180049693
0x18004952a  lea     rdx, [rsp+190h+var_140]
0x18004952f  mov     rcx, rbx
0x180049532  call    ?GetTexture@FrameBuffer@Engine@Spectre@@QEBA?AV?$shared_ptr@VTexture@Engine@Spectre@@@std@@XZ; Spectre::Engine::FrameBuffer::GetTexture(void)
0x180049537  nop
0x180049538  mov     rcx, [rsp+190h+var_140]
0x18004953d  test    rcx, rcx
0x180049540  jz      loc_180049683
0x180049546  lea     rdx, [rsp+190h+var_130]
0x18004954b  call    ?GetExtension@ShaderFamily@Engine@Spectre@@QEBA?AV?$shared_ptr@VIShaderExtension@Engine@Spectre@@@std@@XZ; Spectre::Engine::ShaderFamily::GetExtension(void)
0x180049550  nop
0x180049551  mov     rcx, [rax]
0x180049554  mov     rax, [rcx]
0x180049557  mov     r8, r14
0x18004955a  mov     rdx, rdi
0x18004955d  mov     rax, [rax+30h]
0x180049561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049566  nop
0x180049567  mov     rcx, [rsp+190h+var_128]; this
0x18004956c  test    rcx, rcx
0x18004956f  jz      short loc_180049576
0x180049571  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049576  imul    r15, r14, 58h ; 'X'
0x18004957a  mov     r12, [rdi+68h]
0x18004957e  mov     ebx, [rbp+90h+var_100]
0x180049581  mov     rcx, [r15+r12+18h]
0x180049586  test    rcx, rcx
0x180049589  jz      short loc_180049596
0x18004958b  mov     r8d, ebx
0x18004958e  mov     rdx, rsi
0x180049591  call    ?ApplyState@ShaderPropertyBlock@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@VShaderTypeGroup@23@@Z; Spectre::Engine::ShaderPropertyBlock::ApplyState(std::shared_ptr<Spectre::Engine::CommandList> const &,Spectre::Engine::ShaderTypeGroup)
0x180049596  mov     dl, [rdi+0A8h]
0x18004959c  mov     rax, [rsi]
0x18004959f  mov     rcx, [rax+60h]
0x1800495a3  cmp     dl, [rcx+38C4h]
0x1800495a9  jz      short loc_1800495B8
0x1800495ab  mov     [rcx+38C4h], dl
0x1800495b1  mov     byte ptr [rcx+38C5h], 1
0x1800495b8  movss   xmm4, dword ptr [rdi+0ACh]
0x1800495c0  movss   xmm5, dword ptr [rdi+0B0h]
0x1800495c8  movss   xmm6, dword ptr [rdi+0B4h]
0x1800495d0  movss   xmm7, dword ptr [rdi+0B8h]
0x1800495d8  mov     rax, [rsi]
0x1800495db  mov     rcx, [rax+60h]
0x1800495df  movaps  xmm2, xmm6
0x1800495e2  movaps  xmm3, xmm4
0x1800495e5  unpcklps xmm2, xmm7
0x1800495e8  unpcklps xmm3, xmm5
0x1800495eb  movlhps xmm3, xmm2
0x1800495ee  movups  xmm0, xmmword ptr [rcx+38B4h]
0x1800495f5  cmpneqps xmm3, xmm0
0x1800495f9  movmskps eax, xmm3
0x1800495fc  test    eax, eax
0x1800495fe  jz      short loc_180049627
0x180049600  movss   dword ptr [rcx+38B4h], xmm4
0x180049608  movss   dword ptr [rcx+38B8h], xmm5
0x180049610  movss   dword ptr [rcx+38BCh], xmm6
0x180049618  movss   dword ptr [rcx+38C0h], xmm7
0x180049620  mov     byte ptr [rcx+38C5h], 1
0x180049627  mov     rcx, [r15+r12+28h]
0x18004962c  test    rcx, rcx
0x18004962f  jz      short loc_18004963C
0x180049631  mov     r8d, ebx
0x180049634  mov     rdx, rsi
0x180049637  call    ?ApplyState@ShaderPropertyBlock@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@VShaderTypeGroup@23@@Z; Spectre::Engine::ShaderPropertyBlock::ApplyState(std::shared_ptr<Spectre::Engine::CommandList> const &,Spectre::Engine::ShaderTypeGroup)
0x18004963c  mov     rcx, [r15+r12+38h]
0x180049641  test    rcx, rcx
0x180049644  jz      short loc_180049651
0x180049646  mov     r8d, ebx
0x180049649  mov     rdx, rsi
0x18004964c  call    ?ApplyState@ShaderPropertyBlock@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@VShaderTypeGroup@23@@Z; Spectre::Engine::ShaderPropertyBlock::ApplyState(std::shared_ptr<Spectre::Engine::CommandList> const &,Spectre::Engine::ShaderTypeGroup)
0x180049651  mov     rcx, [r15+r12+48h]
0x180049656  test    rcx, rcx
0x180049659  jz      short loc_180049666
0x18004965b  mov     r8d, ebx
0x18004965e  mov     rdx, rsi
0x180049661  call    ?ApplyState@ShaderPropertyBlock@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@VShaderTypeGroup@23@@Z; Spectre::Engine::ShaderPropertyBlock::ApplyState(std::shared_ptr<Spectre::Engine::CommandList> const &,Spectre::Engine::ShaderTypeGroup)
0x180049666  mov     r8, [r13+88h]
0x18004966d  mov     rdx, rsi
0x180049670  mov     rcx, [rdi+58h]
0x180049674  call    ?Render@Mesh@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@_K@Z; Spectre::Engine::Mesh::Render(std::shared_ptr<Spectre::Engine::CommandList> const &,unsigned __int64)
0x180049679  mov     r15, [rsp+190h+var_148]
0x18004967e  mov     r12b, [rsp+190h+var_160]
0x180049683  mov     rcx, [rsp+190h+var_138]; this
0x180049688  test    rcx, rcx
0x18004968b  jz      short loc_180049693
0x18004968d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049692  nop
0x180049693  mov     rcx, [rbp+90h+var_108]; this
0x180049697  test    rcx, rcx
0x18004969a  jz      short loc_1800496A1
0x18004969c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800496a1  mov     r13, 2E8BA2E8BA2E8BA3h
0x1800496ab  mov     rcx, [rsp+190h+var_150]; this
0x1800496b0  test    rcx, rcx
0x1800496b3  jz      short loc_1800496BA
0x1800496b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800496ba  inc     r14
0x1800496bd  mov     rax, [rdi+70h]
0x1800496c1  sub     rax, [rdi+68h]
0x1800496c5  sar     rax, 3
0x1800496c9  imul    rax, r13
0x1800496cd  cmp     r14, rax
0x1800496d0  jb      loc_1800494AC
0x1800496d6  lea     rdx, [rsp+190h+var_158]
0x1800496db  lea     rcx, [rsp+190h+var_120]
0x1800496e0  call    ?lock@?$weak_ptr@VGpuProfiler@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VGpuProfiler@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::GpuProfiler>::lock(void)
0x1800496e5  nop
0x1800496e6  mov     rcx, [rsp+190h+var_158]
0x1800496eb  test    rcx, rcx
0x1800496ee  jz      short loc_1800496FC
0x1800496f0  mov     rax, [rcx]
0x1800496f3  mov     rax, [rax]
0x1800496f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496fb  nop
0x1800496fc  mov     rcx, [rsp+190h+var_150]; this
0x180049701  test    rcx, rcx
0x180049704  jz      short loc_18004970C
0x180049706  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004970b  nop
0x18004970c  mov     rcx, [rsp+190h+var_120+8]; this
0x180049711  test    rcx, rcx
0x180049714  jz      short loc_18004971B
0x180049716  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18004971b  mov     rcx, [rbp+90h+var_70]
0x18004971f  xor     rcx, rsp; StackCookie
0x180049722  call    __security_check_cookie
0x180049727  lea     r11, [rsp+190h+var_38]
0x18004972f  movaps  xmm6, xmmword ptr [r11-18h]
0x180049734  movaps  xmm7, xmmword ptr [r11-28h]
0x180049739  mov     rsp, r11
0x18004973c  pop     r15
0x18004973e  pop     r14
0x180049740  pop     r13
  ... truncated ...
```
