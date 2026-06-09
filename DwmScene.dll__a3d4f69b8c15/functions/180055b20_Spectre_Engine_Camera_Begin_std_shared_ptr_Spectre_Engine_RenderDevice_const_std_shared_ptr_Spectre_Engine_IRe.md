# Spectre::Engine::Camera::Begin(std::shared_ptr<Spectre::Engine::RenderDevice> const &,std::shared_ptr<Spectre::Engine::IRenderOutput> const &)

- ea: `0x180055b20`
- end: `0x180056469`
- name: `?Begin@Camera@Engine@Spectre@@MEBAXAEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@AEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z`
- size: `2377`
- prototype: `__int64 __fastcall(Spectre::Engine::Component *this)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001128c`
- `0x180014a3c`
- `0x18001daf4`
- `0x180037b38`
- `0x18003a280`
- `0x18003a600`
- `0x1800409a8`
- `0x18004d1f4`
- `0x18004d210`
- `0x18004d278`
- `0x180055b20`
- `0x180057128`
- `0x18005716c`
- `0x1800571f4`
- `0x180057238`
- `0x1800572bc`
- `0x180057394`
- `0x180058bac`
- `0x180078050`
- `0x18007c1c0`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055d49`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055d64`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055dc2`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055dd6`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055dea`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055dfe`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055f7b`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055f94`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055fa6`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055fbf`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055d49`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055d64`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055dc2`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055dd6`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055dea`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055dfe`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055f7b`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055f94`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055fa6`
- `api-ms-win-crt-private-l1-1-0!_o_roundf` at `0x180055fbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Spectre::Engine::Camera::Begin(Spectre::Engine::Component *this, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rbx
  _QWORD *v6; // r14
  _QWORD *v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // rax
  float v10; // xmm6_4
  float v11; // xmm0_4
  __int64 v12; // rax
  __m128i si128; // xmm14
  __m128 v14; // xmm9
  __m128 v15; // xmm10
  unsigned __int64 v16; // rcx
  __int128 v17; // xmm0
  __m128i v18; // xmm6
  char v19; // bl
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  __m128 v23; // xmm2
  __m128 v24; // xmm4
  float v25; // xmm11_4
  double v26; // xmm1_8
  __m128 v27; // xmm2
  __m128 v28; // xmm3
  float v29; // xmm10_4
  __m128 v30; // xmm0
  __m128 v31; // xmm1
  __m128 v32; // xmm0
  __m128 v33; // xmm2
  __m128 v34; // xmm0
  float v35; // xmm9_4
  float v36; // xmm13_4
  int v37; // edx
  const char *v38; // rax
  const char *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rbx
  _QWORD *SceneNode; // rax
  _QWORD *v43; // rax
  __m128 v44; // xmm2
  __m128 v45; // xmm6
  unsigned __int32 v46; // xmm9_4
  __m128i *TransformMatrix; // rax
  _BYTE v48[20]; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v49; // [rsp+5Ch] [rbp-ACh]
  __int128 v50; // [rsp+68h] [rbp-A0h] BYREF
  std::_Ref_count_base *v51[2]; // [rsp+78h] [rbp-90h] BYREF
  __m128i v52; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v53; // [rsp+98h] [rbp-70h] BYREF
  std::_Ref_count_base *v54; // [rsp+A0h] [rbp-68h]
  __m128i v55; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v56; // [rsp+B8h] [rbp-50h]
  __m128i v57; // [rsp+C8h] [rbp-40h]
  __m128i v58; // [rsp+D8h] [rbp-30h]
  __m128i v59; // [rsp+E8h] [rbp-20h] BYREF
  __m128i v60; // [rsp+F8h] [rbp-10h]
  __m128i v61; // [rsp+108h] [rbp+0h]
  __m128i v62; // [rsp+118h] [rbp+10h]
  __int128 v63; // [rsp+128h] [rbp+20h]
  char v64; // [rsp+138h] [rbp+30h]
  unsigned __int64 v65; // [rsp+208h] [rbp+100h] BYREF
  unsigned __int64 v66; // [rsp+220h] [rbp+118h]

  Spectre::Engine::Camera::GetCommandList(this, &v53, a2);
  if ( (*((_BYTE *)this + 440) & 1) != 0 )
  {
    v5 = *((_QWORD *)Spectre::Engine::Component::GetEngine(this) + 64);
    if ( *((_QWORD *)this + 25) )
    {
      v50 = 0;
      Spectre::Engine::ShaderManager::SetGlobalTexture(v5, (char *)this + 184, &v50);
    }
    if ( *((_QWORD *)this + 29) )
    {
      v50 = 0;
      Spectre::Engine::ShaderManager::SetGlobalTexture(v5, (char *)this + 216, &v50);
    }
    if ( *((_QWORD *)this + 33) )
    {
      v55 = (__m128i)Spectre::Utils::Math::Matrix::Identity;
      v56 = (__m128i)xmmword_180169180;
      v57 = (__m128i)xmmword_180169190;
      v58 = (__m128i)xmmword_1801691A0;
      Spectre::Engine::ShaderManager::SetGlobalMatrix(v5, (char *)this + 248, &v55);
    }
  }
  v6 = (_QWORD *)((char *)this + 152);
  if ( *((_QWORD *)this + 17) || *v6 )
  {
    v7 = v53;
    Spectre::Engine::CommandList::SetRenderTarget(v53, (char *)this + 136, (char *)this + 152);
  }
  else
  {
    v7 = v53;
    v8 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base **))(*(_QWORD *)*a3 + 40LL))(*a3, v51);
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a3 + 32LL))(*a3, &v50);
    Spectre::Engine::CommandList::SetRenderTarget(v7, v9, v8);
    if ( *((_QWORD *)&v50 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v50 + 1));
    if ( v51[1] )
      std::_Ref_count_base::_Decref(v51[1]);
    v10 = (float)(*(int (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 88LL))(*a3);
    v11 = (float)(*(int (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 80LL))(*a3);
    v12 = v7[12];
    *(_QWORD *)(v12 + 14544) = 0;
    *(float *)(v12 + 14552) = v11;
    *(float *)(v12 + 14556) = v10;
    *(_DWORD *)(v12 + 14560) = 0;
    *(_DWORD *)(v12 + 14564) = 1065353216;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v52 = si128;
  Spectre::Engine::Camera::GetActiveRenderTargetSize(this, &v65);
  *(_QWORD *)&v50 = 0;
  v14 = (__m128)(unsigned int)v65;
  DWORD2(v50) = (int)_o_roundf();
  v15 = (__m128)HIDWORD(v65);
  HIDWORD(v50) = (int)_o_roundf();
  v64 = 0;
  v16 = (unsigned __int64)Spectre::Utils::Optional<Spectre::Engine::ScissorRect>::Valid
      & -(__int64)(*((_BYTE *)this + 388) != 0);
  if ( v16 )
  {
    v17 = *(_OWORD *)((char *)this + 372);
    v63 = v17;
    v64 = 1;
  }
  else
  {
    v17 = v63;
  }
  if ( v16 )
  {
    *(_OWORD *)v51 = v17;
  }
  else
  {
    Spectre::Engine::Camera::GetViewportActive(this);
    LODWORD(v51[0]) = (int)_o_roundf();
    HIDWORD(v51[0]) = (int)_o_roundf();
    LODWORD(v51[1]) = (int)_o_roundf();
    HIDWORD(v51[1]) = (int)_o_roundf();
  }
  v18 = *(__m128i *)Spectre::Engine::ScissorRect::Intersect(v48, v51, &v50);
  *(__m128i *)v51 = v18;
  v19 = 0;
  Spectre::Engine::Camera::GetViewportActive(this);
  v22 = v7[12];
  if ( (*((_DWORD *)this + 110) & 0x1000000) != 0 )
  {
    *(_QWORD *)(v22 + 14544) = 0;
    *(_DWORD *)(v22 + 14552) = v14.m128_i32[0];
    *(_DWORD *)(v22 + 14556) = v15.m128_i32[0];
    v23 = (__m128)*(unsigned int *)&v48[8];
    *(_DWORD *)(v22 + 14560) = *(_DWORD *)&v48[8];
    v24 = (__m128)v49;
    *(_DWORD *)(v22 + 14564) = v49;
    if ( v14.m128_f32[0] == 0.0 || v15.m128_f32[0] == 0.0 )
      v19 = 1;
    v25 = *(float *)v48;
    v26 = *(double *)_mm_movelh_ps((__m128)*(unsigned __int64 *)v48, v23).m128_u64;
    v27 = 0;
    v27.m128_u64[0] = _mm_unpacklo_ps(v14, v15).m128_u64[0];
    v28 = 0;
    *(double *)v28.m128_u64 = v26;
    v29 = *(float *)&v48[12];
    v30 = 0;
    v30.m128_u64[0] = _mm_movelh_ps((__m128)*(unsigned __int64 *)&v48[12], v24).m128_u64[0];
    v31 = 0;
    v31.m128_u64[0] = _mm_div_ps(v30, v27).m128_u64[0];
    v32 = 0;
    v32.m128_u64[0] = _mm_div_ps(v28, v27).m128_u64[0];
    v65 = _mm_sub_ps(v31, v32).m128_u64[0];
    v33 = _mm_add_ps(v32, v31);
    v34 = 0;
    v34.m128_u64[0] = _mm_unpacklo_ps((__m128)LODWORD(FLOAT_1_0), (__m128)LODWORD(FLOAT_1_0)).m128_u64[0];
    v66 = _mm_sub_ps(v33, v34).m128_u64[0];
    v52.m128i_i64[0] = v65;
    v52.m128i_i32[2] = v66;
    v52.m128i_i32[3] = HIDWORD(v66) ^ _xmm;
    LODWORD(v50) = (int)_o_roundf();
    v35 = *(float *)&v48[4];
    DWORD1(v50) = (int)_o_roundf();
    DWORD2(v50) = (int)_o_roundf();
    v36 = *(float *)&v48[16];
    HIDWORD(v50) = (int)_o_roundf();
    Spectre::Engine::ScissorRect::Intersect(v48, v51, &v50);
    *(_OWORD *)(v7[12] + 14632LL) = *(_OWORD *)v48;
    si128 = v52;
  }
  else
  {
    v25 = *(float *)v48;
    *(_DWORD *)(v22 + 14544) = *(_DWORD *)v48;
    v35 = *(float *)&v48[4];
    *(_DWORD *)(v22 + 14548) = *(_DWORD *)&v48[4];
    v29 = *(float *)&v48[12];
    *(float *)(v22 + 14552) = *(float *)&v48[12] - v25;
    v36 = *(float *)&v48[16];
    *(float *)(v22 + 14556) = *(float *)&v48[16] - v35;
    *(_DWORD *)(v22 + 14560) = *(_DWORD *)&v48[8];
    *(_DWORD *)(v22 + 14564) = v49;
    *(__m128i *)(v7[12] + 14632LL) = v18;
  }
  v37 = (_mm_cvtsi128_si32(_mm_srli_si128(v18, 8)) - _mm_cvtsi128_si32(v18))
      * (_mm_cvtsi128_si32(_mm_srli_si128(v18, 12)) - _mm_cvtsi128_si32(_mm_srli_si128(v18, 4)));
  if ( v25 == v29 || v35 == v36 )
    v19 = 1;
  if ( !v37 )
  {
    v38 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)this + 24);
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsNativeRenderer_Camera,
      4,
      "Warning: camera '%s' scissor rectangle is empty -- no pixels will be rendered",
      v38);
  }
  if ( v19 )
  {
    v39 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)this + 24);
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsNativeRenderer_Camera,
      4,
      "Warning: camera '%s' viewport rectangle is empty -- no pixels will be rendered",
      v39);
  }
  if ( (*((_BYTE *)this + 465) & 1) != 0 && *((_QWORD *)this + 17) )
  {
    v40 = *v7;
    *(_OWORD *)v48 = *(_OWORD *)((char *)this + 296);
    (*(void (__fastcall **)(_QWORD *, char *, _BYTE *))(v40 + 88))(v7, (char *)this + 136, v48);
  }
  LOBYTE(v20) = *((_BYTE *)this + 465);
  if ( (v20 & 6) != 0 && *v6 )
  {
    LOBYTE(v21) = (v20 & 4) != 0;
    LOBYTE(v20) = (v20 & 2) != 0;
    (*(void (__fastcall **)(_QWORD *, char *, __int64, __int64, _DWORD, _BYTE))(*v7 + 104LL))(
      v7,
      (char *)this + 152,
      v20,
      v21,
      *((_DWORD *)this + 78),
      *((_BYTE *)this + 464));
  }
  v41 = *((_QWORD *)Spectre::Engine::Component::GetEngine(this) + 64);
  SceneNode = (_QWORD *)Spectre::Engine::Component::GetSceneNode(this, v48);
  Spectre::Engine::SceneNode::GetWorldPosition(*SceneNode, &v52);
  if ( *(_QWORD *)&v48[8] )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v48[8]);
  v51[0] = (std::_Ref_count_base *)v52.m128i_i64[0];
  v51[1] = (std::_Ref_count_base *)(v52.m128i_u32[2] | 0x3F80000000000000LL);
  if ( *((_DWORD *)this + 79) == 3 )
  {
    v43 = (_QWORD *)Spectre::Engine::Component::GetSceneNode(this, v48);
    Spectre::Engine::SceneNode::GetWorldTransformMatrix(*v43, &v59);
    LODWORD(v65) = v61.m128i_i32[2] ^ _xmm;
    v52.m128i_i8[8] = v61.m128i_i8[8] ^ _xmm;
    *(__int16 *)((char *)&v52.m128i_i16[4] + 1) = (v61.m128i_i32[2] ^ (unsigned int)_xmm) >> 8;
    v52.m128i_i8[11] = (v61.m128i_i32[2] ^ (unsigned int)_xmm) >> 24;
    v44 = 0;
    v44.m128_u64[0] = _mm_unpacklo_ps(
                        _mm_xor_ps((__m128)v61.m128i_u32[0], (__m128)_xmm),
                        _mm_xor_ps((__m128)v61.m128i_u32[1], (__m128)_xmm)).m128_u64[0];
    v45 = _mm_sub_ps((__m128)0LL, _mm_movelh_ps(v44, (__m128)v52.m128i_u32[2]));
    v52.m128i_i64[0] = v45.m128_u64[0];
    v46 = _mm_shuffle_ps(v45, v45, 170).m128_u32[0];
    if ( *(_QWORD *)&v48[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v48[8]);
    v51[0] = (std::_Ref_count_base *)v45.m128_u64[0];
    v51[1] = (std::_Ref_count_base *)v46;
  }
  *(_OWORD *)v48 = *(_OWORD *)v51;
  Spectre::Engine::ShaderManager::SetGlobalVector4(v41, Spectre::Engine::ShaderConstants::kView_CameraPosition, v48);
  *(__m128i *)v48 = si128;
  Spectre::Engine::ShaderManager::SetGlobalVector4(v41, Spectre::Engine::ShaderConstants::kView_SoftwareViewport, v48);
  Spectre::Engine::ShaderPropertyBlock::SetScalar(
    *(_QWORD *)(v41 + 18648),
    Spectre::Engine::ShaderConstants::kView_UseConservativeAlphaMaskForDepthOnly);
  v55 = _mm_load_si128((const __m128i *)&_xmm);
  v56 = _mm_load_si128((const __m128i *)&_xmm);
  v57 = _mm_load_si128((const __m128i *)&_xmm);
  v58 = _mm_load_si128((const __m128i *)&_xmm);
  TransformMatrix = (__m128i *)Spectre::Engine::Camera::GetTransformMatrix(this, 0, 2);
  v59 = *TransformMatrix;
  v60 = TransformMatrix[1];
  v61 = TransformMatrix[2];
  v62 = TransformMatrix[3];
  Spectre::Utils::Math::Matrix::Transpose(
    (Spectre::Utils::Math::Matrix *)&v59,
    (struct Spectre::Utils::Math::Matrix *)&v55);
  v59 = v55;
  v60 = v56;
  v61 = v57;
  v62 = v58;
  Spectre::Engine::ShaderManager::SetGlobalMatrix(
    v41,
    Spectre::Engine::ShaderConstants::kView_ViewProjectionMatrix,
    &v59);
  Spectre::Engine::Camera::GetRenderTargetSize(this, &v65);
  *(_QWORD *)&v50 = v65;
  *((float *)&v50 + 2) = 1.0 / *(float *)&v65;
  *((float *)&v50 + 3) = 1.0 / *((float *)&v65 + 1);
  *(_OWORD *)v48 = v50;
  Spectre::Engine::ShaderManager::SetGlobalVector4(
    v41,
    Spectre::Engine::ShaderConstants::kPipeline_RenderTargetSize,
    v48);
  if ( v54 )
    std::_Ref_count_base::_Decref(v54);
}

```

## disassembly

```asm
0x180055b20  mov     rax, rsp
0x180055b23  mov     [rax+10h], rbx
0x180055b27  push    rbp
0x180055b28  push    rsi
0x180055b29  push    rdi
0x180055b2a  push    r12
0x180055b2c  push    r13
0x180055b2e  push    r14
0x180055b30  push    r15
0x180055b32  lea     rbp, [rax-0F8h]
0x180055b39  sub     rsp, 1C0h
0x180055b40  movaps  xmmword ptr [rax-48h], xmm6
0x180055b44  movaps  xmmword ptr [rax-58h], xmm7
0x180055b48  movaps  xmmword ptr [rax-68h], xmm8
0x180055b4d  movaps  xmmword ptr [rax-78h], xmm9
0x180055b52  movaps  xmmword ptr [rax-88h], xmm10
0x180055b5a  movaps  xmmword ptr [rax-98h], xmm11
0x180055b62  movaps  xmmword ptr [rax-0A8h], xmm13
0x180055b6a  movaps  xmmword ptr [rax-0B8h], xmm14
0x180055b72  mov     r12, r8
0x180055b75  mov     rdi, rcx
0x180055b78  mov     r8, rdx
0x180055b7b  lea     rdx, [rbp+0F0h+var_160]
0x180055b7f  call    ?GetCommandList@Camera@Engine@Spectre@@QEBA?AV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@AEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@5@@Z; Spectre::Engine::Camera::GetCommandList(std::shared_ptr<Spectre::Engine::RenderDevice> const &)
0x180055b84  nop
0x180055b85  xor     r13d, r13d
0x180055b88  test    byte ptr [rdi+1B8h], 1
0x180055b8f  jz      loc_180055C31
0x180055b95  mov     rcx, rdi; this
0x180055b98  call    ?GetEngine@Component@Engine@Spectre@@QEBAPEAV223@XZ; Spectre::Engine::Component::GetEngine(void)
0x180055b9d  mov     rbx, [rax+200h]
0x180055ba4  lea     rdx, [rdi+0B8h]
0x180055bab  cmp     [rdx+10h], r13
0x180055baf  jz      short loc_180055BC8
0x180055bb1  xorps   xmm0, xmm0
0x180055bb4  movdqu  [rsp+1F0h+var_198+8], xmm0
0x180055bba  lea     r8, [rsp+1F0h+var_198+8]
0x180055bbf  mov     rcx, rbx
0x180055bc2  call    ?SetGlobalTexture@ShaderManager@Engine@Spectre@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$shared_ptr@VTexture@Engine@Spectre@@@5@@Z; Spectre::Engine::ShaderManager::SetGlobalTexture(std::string const &,std::shared_ptr<Spectre::Engine::Texture> const &)
0x180055bc7  nop
0x180055bc8  lea     rdx, [rdi+0D8h]
0x180055bcf  cmp     [rdx+10h], r13
0x180055bd3  jz      short loc_180055BEC
0x180055bd5  xorps   xmm0, xmm0
0x180055bd8  movdqu  [rsp+1F0h+var_198+8], xmm0
0x180055bde  lea     r8, [rsp+1F0h+var_198+8]
0x180055be3  mov     rcx, rbx
0x180055be6  call    ?SetGlobalTexture@ShaderManager@Engine@Spectre@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$shared_ptr@VTexture@Engine@Spectre@@@5@@Z; Spectre::Engine::ShaderManager::SetGlobalTexture(std::string const &,std::shared_ptr<Spectre::Engine::Texture> const &)
0x180055beb  nop
0x180055bec  lea     rdx, [rdi+0F8h]
0x180055bf3  cmp     [rdx+10h], r13
0x180055bf7  jz      short loc_180055C31
0x180055bf9  movups  xmm0, cs:?Identity@Matrix@Math@Utils@Spectre@@2U1234@B; Spectre::Utils::Math::Matrix const Spectre::Utils::Math::Matrix::Identity
0x180055c00  movaps  [rbp+0F0h+var_150], xmm0
0x180055c04  movups  xmm1, cs:xmmword_180169180
0x180055c0b  movaps  [rbp+0F0h+var_140], xmm1
0x180055c0f  movups  xmm0, cs:xmmword_180169190
0x180055c16  movaps  [rbp+0F0h+var_130], xmm0
0x180055c1a  movups  xmm1, cs:xmmword_1801691A0
0x180055c21  movaps  [rbp+0F0h+var_120], xmm1
0x180055c25  lea     r8, [rbp+0F0h+var_150]
0x180055c29  mov     rcx, rbx
0x180055c2c  call    ?SetGlobalMatrix@ShaderManager@Engine@Spectre@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UMatrix@Math@Utils@3@@Z; Spectre::Engine::ShaderManager::SetGlobalMatrix(std::string const &,Spectre::Utils::Math::Matrix)
0x180055c31  lea     r15, [rdi+88h]
0x180055c38  lea     r14, [rdi+98h]
0x180055c3f  cmp     [r15], r13
0x180055c42  jnz     short loc_180055C49
0x180055c44  cmp     [r14], r13
0x180055c47  jz      short loc_180055C60
0x180055c49  mov     r8, r14
0x180055c4c  mov     rdx, r15
0x180055c4f  mov     rsi, [rbp+0F0h+var_160]
0x180055c53  mov     rcx, rsi
0x180055c56  call    ?SetRenderTarget@CommandList@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VFrameBuffer@Engine@Spectre@@@std@@AEBV?$shared_ptr@VDepthBuffer@Engine@Spectre@@@5@@Z; Spectre::Engine::CommandList::SetRenderTarget(std::shared_ptr<Spectre::Engine::FrameBuffer> const &,std::shared_ptr<Spectre::Engine::DepthBuffer> const &)
0x180055c5b  jmp     loc_180055D1A
0x180055c60  mov     rsi, [rbp+0F0h+var_160]
0x180055c64  mov     rcx, [r12]
0x180055c68  mov     rax, [rcx]
0x180055c6b  lea     rdx, [rsp+1F0h+var_188+8]
0x180055c70  mov     rax, [rax+28h]
0x180055c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c79  mov     rbx, rax
0x180055c7c  mov     rcx, [r12]
0x180055c80  mov     rdx, [rcx]
0x180055c83  mov     rax, [rdx+20h]
0x180055c87  lea     rdx, [rsp+1F0h+var_198+8]
0x180055c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c91  nop
0x180055c92  mov     r8, rbx
0x180055c95  mov     rdx, rax
0x180055c98  mov     rcx, rsi
0x180055c9b  call    ?SetRenderTarget@CommandList@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VFrameBuffer@Engine@Spectre@@@std@@AEBV?$shared_ptr@VDepthBuffer@Engine@Spectre@@@5@@Z; Spectre::Engine::CommandList::SetRenderTarget(std::shared_ptr<Spectre::Engine::FrameBuffer> const &,std::shared_ptr<Spectre::Engine::DepthBuffer> const &)
0x180055ca0  nop
0x180055ca1  mov     rcx, [rsp+1F0h+var_188]; this
0x180055ca6  test    rcx, rcx
0x180055ca9  jz      short loc_180055CB1
0x180055cab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180055cb0  nop
0x180055cb1  mov     rcx, [rsp+1F0h+var_178]; this
0x180055cb6  test    rcx, rcx
0x180055cb9  jz      short loc_180055CC0
0x180055cbb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180055cc0  mov     rcx, [r12]
0x180055cc4  mov     rax, [rcx]
0x180055cc7  mov     rax, [rax+58h]
0x180055ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cd0  movd    xmm6, eax
0x180055cd4  cvtdq2ps xmm6, xmm6
0x180055cd7  mov     rcx, [r12]
0x180055cdb  mov     rax, [rcx]
0x180055cde  mov     rax, [rax+50h]
0x180055ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ce7  movd    xmm0, eax
0x180055ceb  cvtdq2ps xmm0, xmm0
0x180055cee  mov     rax, [rsi+60h]
0x180055cf2  mov     [rax+38D0h], r13
0x180055cf9  movss   dword ptr [rax+38D8h], xmm0
0x180055d01  movss   dword ptr [rax+38DCh], xmm6
0x180055d09  mov     [rax+38E0h], r13d
0x180055d10  mov     dword ptr [rax+38E4h], 3F800000h
0x180055d1a  movdqa  xmm14, cs:__xmm@00000000000000003f8000003f800000
0x180055d23  movups  [rbp+0F0h+var_170], xmm14
0x180055d28  lea     rdx, [rbp+0F0h+arg_0]
0x180055d2f  mov     rcx, rdi
0x180055d32  call    ?GetActiveRenderTargetSize@Camera@Engine@Spectre@@IEBA?AUVector2@Math@Utils@3@XZ; Spectre::Engine::Camera::GetActiveRenderTargetSize(void)
0x180055d37  mov     qword ptr [rsp+1F0h+var_198+8], r13
0x180055d3c  movss   xmm9, dword ptr [rbp+0F0h+arg_0]
0x180055d45  movaps  xmm0, xmm9
0x180055d49  call    cs:__imp__o_roundf
0x180055d4f  cvttss2si eax, xmm0
0x180055d53  mov     dword ptr [rsp+1F0h+var_188], eax
0x180055d57  movss   xmm10, dword ptr [rbp+0F0h+arg_0+4]
0x180055d60  movaps  xmm0, xmm10
0x180055d64  call    cs:__imp__o_roundf
0x180055d6a  cvttss2si eax, xmm0
0x180055d6e  mov     dword ptr [rsp+1F0h+var_188+4], eax
0x180055d72  mov     [rbp+0F0h+var_C0], r13b
0x180055d76  mov     al, [rdi+184h]
0x180055d7c  neg     al
0x180055d7e  sbb     rcx, rcx
0x180055d81  lea     rax, ?Valid@?$Optional@UScissorRect@Engine@Spectre@@@Utils@Spectre@@QEBA_NXZ; Spectre::Utils::Optional<Spectre::Engine::ScissorRect>::Valid(void)
0x180055d88  and     rcx, rax
0x180055d8b  jz      short loc_180055D9E
0x180055d8d  movups  xmm0, xmmword ptr [rdi+174h]
0x180055d94  movups  [rbp+0F0h+var_D0], xmm0
0x180055d98  mov     [rbp+0F0h+var_C0], 1
0x180055d9c  jmp     short loc_180055DA2
0x180055d9e  movups  xmm0, [rbp+0F0h+var_D0]
0x180055da2  test    rcx, rcx
0x180055da5  jz      short loc_180055DAF
0x180055da7  movdqu  xmmword ptr [rsp+1F0h+var_188+8], xmm0
0x180055dad  jmp     short loc_180055E0C
0x180055daf  lea     rdx, [rsp+1F0h+var_1B8+8]
0x180055db4  mov     rcx, rdi; this
0x180055db7  call    ?GetViewportActive@Camera@Engine@Spectre@@IEBA?AU?$ViewportBounds@UVector3@Math@Utils@Spectre@@@123@XZ; Spectre::Engine::Camera::GetViewportActive(void)
0x180055dbc  movss   xmm0, dword ptr [rsp+1F0h+var_1B8+8]
0x180055dc2  call    cs:__imp__o_roundf
0x180055dc8  cvttss2si eax, xmm0
0x180055dcc  mov     dword ptr [rsp+1F0h+var_188+8], eax
0x180055dd0  movss   xmm0, dword ptr [rsp+1F0h+var_1B8+0Ch]
0x180055dd6  call    cs:__imp__o_roundf
0x180055ddc  cvttss2si eax, xmm0
0x180055de0  mov     dword ptr [rsp+1F0h+var_188+0Ch], eax
0x180055de4  movss   xmm0, dword ptr [rsp+1F0h+var_1A8+4]
0x180055dea  call    cs:__imp__o_roundf
0x180055df0  cvttss2si eax, xmm0
0x180055df4  mov     dword ptr [rsp+1F0h+var_178], eax
0x180055df8  movss   xmm0, [rsp+1F0h+var_1A0]
0x180055dfe  call    cs:__imp__o_roundf
0x180055e04  cvttss2si eax, xmm0
0x180055e08  mov     dword ptr [rsp+1F0h+var_178+4], eax
0x180055e0c  lea     r8, [rsp+1F0h+var_198+8]
0x180055e11  lea     rdx, [rsp+1F0h+var_188+8]
0x180055e16  lea     rcx, [rsp+1F0h+var_1B8+8]
0x180055e1b  call    ?Intersect@ScissorRect@Engine@Spectre@@SA?AU123@AEBU123@0@Z; Spectre::Engine::ScissorRect::Intersect(Spectre::Engine::ScissorRect const &,Spectre::Engine::ScissorRect const &)
0x180055e20  movups  xmm6, xmmword ptr [rax]
0x180055e23  movups  xmmword ptr [rsp+1F0h+var_188+8], xmm6
0x180055e28  mov     bl, r13b
0x180055e2b  lea     rdx, [rsp+1F0h+var_1B8+8]
0x180055e30  mov     rcx, rdi; this
0x180055e33  call    ?GetViewportActive@Camera@Engine@Spectre@@IEBA?AU?$ViewportBounds@UVector3@Math@Utils@Spectre@@@123@XZ; Spectre::Engine::Camera::GetViewportActive(void)
0x180055e38  xorps   xmm8, xmm8
0x180055e3c  movss   xmm7, cs:__real@3f800000
0x180055e44  mov     rax, [rsi+60h]
0x180055e48  test    dword ptr [rdi+1B8h], 1000000h
0x180055e52  jz      loc_180055FF9
0x180055e58  mov     [rax+38D0h], r13
0x180055e5f  movss   dword ptr [rax+38D8h], xmm9
0x180055e68  movss   dword ptr [rax+38DCh], xmm10
0x180055e71  movss   xmm2, dword ptr [rsp+1F0h+var_1A8]
0x180055e77  movss   dword ptr [rax+38E0h], xmm2
0x180055e7f  movss   xmm4, [rsp+1F0h+var_19C]
0x180055e85  movss   dword ptr [rax+38E4h], xmm4
0x180055e8d  ucomiss xmm9, xmm8
0x180055e91  jp      short loc_180055E95
0x180055e93  jz      short loc_180055E9D
0x180055e95  ucomiss xmm10, xmm8
0x180055e99  jp      short loc_180055E9F
0x180055e9b  jnz     short loc_180055E9F
0x180055e9d  mov     bl, 1
0x180055e9f  movsd   xmm11, qword ptr [rsp+1F0h+var_1B8+8]
0x180055ea6  movaps  xmm1, xmm11
0x180055eaa  movlhps xmm1, xmm2
0x180055ead  unpcklps xmm9, xmm10
0x180055eb1  xorps   xmm2, xmm2
0x180055eb4  movsd   xmm2, xmm9
0x180055eb9  mov     [rbp+0F0h+arg_0], 0
0x180055ec4  xorps   xmm3, xmm3
0x180055ec7  movsd   xmm3, xmm1
0x180055ecb  divps   xmm3, xmm2
0x180055ece  movsd   xmm10, [rsp+1F0h+var_1A8+4]
0x180055ed5  movaps  xmm1, xmm10
0x180055ed9  movlhps xmm1, xmm4
0x180055edc  mov     [rbp+0F0h+arg_0], 0
0x180055ee7  xorps   xmm0, xmm0
0x180055eea  movsd   xmm0, xmm1
0x180055eee  divps   xmm0, xmm2
0x180055ef1  xorps   xmm1, xmm1
0x180055ef4  movsd   xmm1, xmm0
0x180055ef8  xorps   xmm0, xmm0
0x180055efb  movsd   xmm0, xmm3
0x180055eff  mov     [rbp+0F0h+arg_0], 0
0x180055f0a  movaps  xmm3, xmm1
0x180055f0d  subps   xmm3, xmm0
0x180055f10  movsd   [rbp+0F0h+arg_0], xmm3
0x180055f18  mov     [rbp+0F0h+arg_18], 0
0x180055f23  addps   xmm0, xmm1
0x180055f26  mov     [rbp+0F0h+arg_18], 0
0x180055f31  movaps  xmm2, xmm0
0x180055f34  movaps  xmm1, xmm7
0x180055f37  unpcklps xmm1, xmm7
0x180055f3a  xorps   xmm0, xmm0
0x180055f3d  movsd   xmm0, xmm1
0x180055f41  subps   xmm2, xmm0
0x180055f44  movsd   [rbp+0F0h+arg_18], xmm2
0x180055f4c  movss   xmm0, dword ptr [rbp+0F0h+arg_0+4]
0x180055f54  movss   dword ptr [rbp+0F0h+var_170], xmm3
0x180055f59  movss   dword ptr [rbp+0F0h+var_170+4], xmm0
0x180055f5e  movss   dword ptr [rbp+0F0h+var_170+8], xmm2
0x180055f63  movss   xmm0, dword ptr [rbp+0F0h+arg_18+4]
0x180055f6b  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180055f72  movss   dword ptr [rbp+0F0h+var_170+0Ch], xmm0
0x180055f77  movaps  xmm0, xmm11
0x180055f7b  call    cs:__imp__o_roundf
0x180055f81  cvttss2si eax, xmm0
0x180055f85  mov     dword ptr [rsp+1F0h+var_198+8], eax
0x180055f89  movss   xmm9, dword ptr [rsp+1F0h+var_1B8+0Ch]
0x180055f90  movaps  xmm0, xmm9
0x180055f94  call    cs:__imp__o_roundf
0x180055f9a  cvttss2si eax, xmm0
0x180055f9e  mov     dword ptr [rsp+1F0h+var_198+0Ch], eax
0x180055fa2  movaps  xmm0, xmm10
0x180055fa6  call    cs:__imp__o_roundf
0x180055fac  cvttss2si eax, xmm0
0x180055fb0  mov     dword ptr [rsp+1F0h+var_188], eax
0x180055fb4  movss   xmm13, [rsp+1F0h+var_1A0]
0x180055fbb  movaps  xmm0, xmm13
0x180055fbf  call    cs:__imp__o_roundf
0x180055fc5  cvttss2si eax, xmm0
0x180055fc9  mov     dword ptr [rsp+1F0h+var_188+4], eax
0x180055fcd  lea     r8, [rsp+1F0h+var_198+8]
0x180055fd2  lea     rdx, [rsp+1F0h+var_188+8]
0x180055fd7  lea     rcx, [rsp+1F0h+var_1B8+8]
0x180055fdc  call    ?Intersect@ScissorRect@Engine@Spectre@@SA?AU123@AEBU123@0@Z; Spectre::Engine::ScissorRect::Intersect(Spectre::Engine::ScissorRect const &,Spectre::Engine::ScissorRect const &)
0x180055fe1  movaps  xmm0, [rsp+1F0h+var_1B8+8]
0x180055fe6  mov     rax, [rsi+60h]
0x180055fea  movdqu  xmmword ptr [rax+3928h], xmm0
0x180055ff2  movups  xmm14, [rbp+0F0h+var_170]
0x180055ff7  jmp     short loc_180056071
0x180055ff9  movss   xmm11, dword ptr [rsp+1F0h+var_1B8+8]
0x180056000  movss   dword ptr [rax+38D0h], xmm11
0x180056009  movss   xmm9, dword ptr [rsp+1F0h+var_1B8+0Ch]
0x180056010  movss   dword ptr [rax+38D4h], xmm9
0x180056019  movss   xmm10, dword ptr [rsp+1F0h+var_1A8+4]
0x180056020  movaps  xmm0, xmm10
0x180056024  subss   xmm0, xmm11
0x180056029  movss   dword ptr [rax+38D8h], xmm0
0x180056031  movss   xmm13, [rsp+1F0h+var_1A0]
0x180056038  movaps  xmm1, xmm13
0x18005603c  subss   xmm1, xmm9
0x180056041  movss   dword ptr [rax+38DCh], xmm1
0x180056049  movss   xmm0, dword ptr [rsp+1F0h+var_1A8]
0x18005604f  movss   dword ptr [rax+38E0h], xmm0
0x180056057  movss   xmm1, [rsp+1F0h+var_19C]
0x18005605d  movss   dword ptr [rax+38E4h], xmm1
0x180056065  mov     rax, [rsi+60h]
0x180056069  movdqu  xmmword ptr [rax+3928h], xmm6
0x180056071  movdqa  xmm0, xmm6
0x180056075  movdqa  xmm1, xmm6
0x180056079  psrldq  xmm0, 0Ch
0x18005607e  psrldq  xmm1, 4
0x180056083  movd    edx, xmm0
0x180056087  movd    eax, xmm1
0x18005608b  movdqa  xmm0, xmm6
0x18005608f  sub     edx, eax
0x180056091  psrldq  xmm0, 8
0x180056096  movd    eax, xmm6
0x18005609a  movd    ecx, xmm0
0x18005609e  sub     ecx, eax
0x1800560a0  imul    edx, ecx
  ... truncated ...
```
