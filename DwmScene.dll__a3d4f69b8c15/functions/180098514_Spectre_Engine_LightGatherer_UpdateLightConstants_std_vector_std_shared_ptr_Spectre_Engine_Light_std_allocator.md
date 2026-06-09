# Spectre::Engine::LightGatherer::UpdateLightConstants(std::vector<std::shared_ptr<Spectre::Engine::Light>,std::allocator<std::shared_ptr<Spectre::Engine::Light>>> const &,std::unique_ptr<Spectre::Engine::LightConstants,std::function<void (Spectre::Engine::LightConstants *)>> const &)

- ea: `0x180098514`
- end: `0x180098cbe`
- name: `?UpdateLightConstants@LightGatherer@Engine@Spectre@@CA?AV?$array@V?$shared_ptr@$$CBVShadowMapCamera@Engine@Spectre@@@std@@$02@std@@AEBV?$vector@V?$shared_ptr@VLight@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VLight@Engine@Spectre@@@std@@@2@@5@AEBV?$unique_ptr@ULightConstants@Engine@Spectre@@V?$function@$$A6AXPEAULightConstants@Engine@Spectre@@@Z@std@@@5@@Z`
- size: `1962`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180098328`

## callees

- `0x18000d5b8`
- `0x18000d600`
- `0x18000df24`
- `0x18001128c`
- `0x180012c58`
- `0x180012df8`
- `0x180038e70`
- `0x18003a280`
- `0x18003a444`
- `0x18003a600`
- `0x18003ae38`
- `0x180057238`
- `0x180058bac`
- `0x18005d1f8`
- `0x180098514`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_cbrtf` at `0x18009867f`
- `api-ms-win-crt-private-l1-1-0!_o_cbrtf` at `0x18009867f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char *__fastcall Spectre::Engine::LightGatherer::UpdateLightConstants(char *a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rdi
  unsigned int v7; // xmm12_4
  __int64 v8; // rbx
  __int64 v9; // r14
  __m128 si128; // xmm8
  __m128 v11; // xmm11
  unsigned int v12; // esi
  __m128 v13; // xmm0
  __m128 v14; // xmm0
  __m128 v15; // xmm6
  __m128 v16; // xmm15
  __m128 v17; // xmm10
  unsigned __int32 v18; // xmm13_4
  __int32 v19; // xmm14_4
  int v20; // ecx
  __m128 v21; // xmm7
  __int64 v22; // rcx
  __int64 v23; // r10
  __int64 v24; // rax
  float v25; // xmm8_4
  __m128 v26; // xmm2
  __m128 v27; // xmm0
  float v28; // xmm3_4
  float v29; // xmm0_4
  float v30; // xmm12_4
  __m128 v31; // xmm0
  __m128 v32; // xmm6
  __m128 v33; // xmm2
  __m128 v34; // xmm3
  __m128 v35; // xmm0
  __m128 v36; // xmm3
  __int64 v37; // rcx
  __int64 v38; // rax
  __m128 v39; // xmm1
  __m128 v40; // xmm0
  __m128 v41; // xmm1
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 *v46; // rax
  __int64 v47; // rcx
  std::_Ref_count_base *v48; // rdx
  std::_Ref_count_base **v49; // rsi
  std::_Ref_count_base *v50; // rcx
  __int64 v51; // rbx
  std::_Ref_count_base *v52; // r13
  unsigned __int64 v53; // rsi
  _OWORD *TransformMatrix; // rax
  __int64 v55; // r10
  _OWORD *v56; // rax
  __int64 v57; // rcx
  __int128 v58; // xmm1
  __int128 v59; // xmm2
  __int128 v60; // xmm3
  float v61; // xmm1_4
  float v62; // xmm4_4
  int v63; // xmm0_4
  int v64; // eax
  float v65; // xmm3_4
  int v66; // xmm5_4
  float v67; // xmm2_4
  __int64 v68; // rcx
  __int64 v69; // rax
  __int64 v70; // r8
  __int64 v71; // rdx
  unsigned __int64 v73; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v74; // [rsp+40h] [rbp-C8h]
  __int32 v75; // [rsp+48h] [rbp-C0h] BYREF
  __int32 v76; // [rsp+4Ch] [rbp-BCh]
  __int64 v77; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v78; // [rsp+58h] [rbp-B0h]
  float v79; // [rsp+60h] [rbp-A8h]
  int v80; // [rsp+68h] [rbp-A0h]
  unsigned __int32 v81; // [rsp+6Ch] [rbp-9Ch]
  float v82; // [rsp+70h] [rbp-98h] BYREF
  float v83; // [rsp+74h] [rbp-94h]
  __int64 v84; // [rsp+78h] [rbp-90h]
  unsigned __int64 v85; // [rsp+80h] [rbp-88h]
  unsigned __int64 v86; // [rsp+8Ch] [rbp-7Ch]
  unsigned __int64 v87; // [rsp+98h] [rbp-70h]
  __int64 v88; // [rsp+A8h] [rbp-60h] BYREF
  std::_Ref_count_base *v89; // [rsp+B0h] [rbp-58h]
  __int64 v90; // [rsp+B8h] [rbp-50h] BYREF
  std::_Ref_count_base *v91; // [rsp+C0h] [rbp-48h]
  __int64 v92; // [rsp+C8h] [rbp-40h] BYREF
  std::_Ref_count_base *v93; // [rsp+D0h] [rbp-38h]
  __int64 v94; // [rsp+D8h] [rbp-30h] BYREF
  std::_Ref_count_base *v95; // [rsp+E0h] [rbp-28h]
  __int64 v96; // [rsp+E8h] [rbp-20h] BYREF
  std::_Ref_count_base *v97; // [rsp+F0h] [rbp-18h]
  __int64 v98; // [rsp+F8h] [rbp-10h]
  _OWORD v99[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v100; // [rsp+128h] [rbp+20h]
  __int128 v101; // [rsp+138h] [rbp+30h]
  char v102[8]; // [rsp+148h] [rbp+40h] BYREF
  std::_Ref_count_base *v103; // [rsp+150h] [rbp+48h]
  __int64 v104; // [rsp+158h] [rbp+50h]
  std::_Ref_count_base *v105; // [rsp+160h] [rbp+58h]

  v3 = a2;
  `eh vector constructor iterator'(
    a1,
    0x10u,
    3u,
    std::shared_ptr<Spectre::Engine::VertexBuffer>::shared_ptr<Spectre::Engine::VertexBuffer>,
    std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>);
  v80 = 1;
  v5 = (__int64)(v3[1] - *v3) >> 4;
  v6 = 0;
  if ( v5 > 3 )
  {
    v5 = 3;
LABEL_4:
    v7 = _xmm;
    while ( 1 )
    {
      v8 = 16 * v6;
      std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
        &v96,
        16 * v6 + *v3);
      v9 = v96;
      si128 = _mm_mul_ps(
                _mm_shuffle_ps((__m128)*(unsigned int *)(v96 + 104), (__m128)*(unsigned int *)(v96 + 104), 0),
                (__m128)_mm_loadu_si128((const __m128i *)(v96 + 88)));
      if ( !*(_BYTE *)(v96 + 72) )
        si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
      v11 = (__m128)*(unsigned int *)(v96 + 116);
      v12 = *(_DWORD *)(v96 + 120);
      std::weak_ptr<Spectre::Engine::RenderDevice>::lock(v96 + 56, &v88);
      Spectre::Engine::SceneNode::GetWorldScale(v88, &v82);
      if ( v89 )
        std::_Ref_count_base::_Decref(v89);
      v13 = (__m128)LODWORD(v83);
      v13.m128_f32[0] = (float)(v83 * v82) * *(float *)&v84;
      v14 = _mm_and_ps(v13, (__m128)_xmm);
      v14.m128_f32[0] = cbrtf(v14.m128_f32[0]);
      v15 = v14;
      v81 = v14.m128_i32[0];
      std::weak_ptr<Spectre::Engine::RenderDevice>::lock(v9 + 56, &v90);
      Spectre::Engine::SceneNode::GetWorldPosition(v90, &v75);
      if ( v91 )
        std::_Ref_count_base::_Decref(v91);
      std::weak_ptr<Spectre::Engine::RenderDevice>::lock(v9 + 56, &v92);
      Spectre::Engine::SceneNode::GetWorldTransformMatrix(v92, v99);
      LODWORD(v73) = v100 ^ v7;
      HIDWORD(v73) = DWORD1(v100) ^ v7;
      LOBYTE(v74) = BYTE8(v100) ^ v7;
      *(_WORD *)((char *)&v74 + 1) = (DWORD2(v100) ^ v7) >> 8;
      HIBYTE(v74) = (DWORD2(v100) ^ v7) >> 24;
      if ( v93 )
        std::_Ref_count_base::_Decref(v93);
      Spectre::Utils::Math::Vector3::Normalize((Spectre::Utils::Math::Vector3 *)&v73);
      v16 = (__m128)v74;
      if ( v12 == 2 )
      {
        v17 = _mm_sub_ps((__m128)0LL, _mm_movelh_ps((__m128)v73, (__m128)v74));
        v85 = v17.m128_u64[0];
        v18 = _mm_shuffle_ps(v17, v17, 170).m128_u32[0];
        v75 = v17.m128_i32[0];
        v19 = v17.m128_i32[1];
        v76 = v17.m128_i32[1];
        LODWORD(v77) = v18;
      }
      else
      {
        v18 = v77;
        v19 = v76;
        v17.m128_i32[0] = v75;
      }
      v20 = *(_DWORD *)(v9 + 108);
      if ( !v20 )
      {
        if ( v12 == 2 )
          goto LABEL_22;
        v20 = 2;
      }
      v21 = 0;
      if ( v12 < 2 )
      {
        switch ( v20 )
        {
          case 1:
            v21 = (__m128)LODWORD(FLOAT_0_079577468);
            break;
          case 2:
            v21 = (__m128)LODWORD(FLOAT_1_0);
            break;
          case 4:
            v21 = v11;
            v21.m128_f32[0] = v11.m128_f32[0] * v11.m128_f32[0];
            break;
        }
      }
      else if ( v12 == 2 )
      {
        if ( v20 != 3 )
        {
          if ( v20 == 4 )
          {
            v29 = FLOAT_0_001;
            if ( v11.m128_f32[0] >= 0.001 )
              v29 = v11.m128_f32[0];
            v21 = (__m128)LODWORD(FLOAT_1_0);
            v21.m128_f32[0] = (float)(1.0 - cosf(v29)) * 6.2831855;
          }
          goto LABEL_23;
        }
LABEL_22:
        v21 = (__m128)LODWORD(FLOAT_1_0);
        goto LABEL_23;
      }
      if ( v12 == 1 )
      {
        v30 = *(float *)(v9 + 112);
        if ( v30 < 1.0 )
          v30 = FLOAT_1_0;
        v31 = (__m128)LODWORD(FLOAT_0_0099999998);
        v31.m128_f32[0] = o_log2f_0(0.0099999998);
        v32 = _mm_xor_ps(v31, (__m128)_xmm);
        v32.m128_f32[0] = v32.m128_f32[0] / (float)(1.0 - cosf((float)(v30 * 0.017453292) * 0.5));
        v33 = _mm_sub_ps((__m128)0LL, _mm_movelh_ps((__m128)v73, v16));
        v98 = 0;
        v34 = 0;
        v34.m128_u64[0] = v33.m128_u64[0];
        v35 = 0;
        v35.m128_f32[0] = _mm_shuffle_ps(v33, v33, 170).m128_f32[0];
        v36 = _mm_mul_ps(_mm_movelh_ps(v34, v35), _mm_shuffle_ps(v32, v32, 0));
        v86 = v36.m128_u64[0];
        v37 = 2 * (v6 + 25);
        v23 = a3;
        v38 = *(_QWORD *)(a3 + 64);
        *(_DWORD *)(v38 + 8 * v37) = v36.m128_i32[0];
        *(_DWORD *)(v38 + 8 * v37 + 4) = HIDWORD(v86);
        *(_DWORD *)(v38 + 8 * v37 + 8) = _mm_shuffle_ps(v36, v36, 170).m128_u32[0];
        v7 = _xmm;
        *(_DWORD *)(v38 + 8 * v37 + 12) = v32.m128_i32[0] ^ _xmm;
        v15 = (__m128)v81;
        goto LABEL_24;
      }
LABEL_23:
      v22 = 2 * (v6 + 25);
      v23 = a3;
      v24 = *(_QWORD *)(a3 + 64);
      *(_QWORD *)(v24 + 8 * v22) = 0;
      *(_QWORD *)(v24 + 8 * v22 + 8) = 0;
LABEL_24:
      LODWORD(v78) = si128.m128_i32[0];
      HIDWORD(v78) = _mm_shuffle_ps(si128, si128, 85).m128_u32[0];
      LODWORD(v25) = _mm_shuffle_ps(si128, si128, 170).m128_u32[0];
      v79 = v25;
      v26.m128_u64[0] = v78;
      if ( v12 == 2 )
      {
        v28 = 0.0;
      }
      else
      {
        v27 = v15;
        v27.m128_f32[0] = v15.m128_f32[0] * v15.m128_f32[0];
        v26 = _mm_mul_ps(_mm_movelh_ps((__m128)v78, (__m128)LODWORD(v79)), _mm_shuffle_ps(v27, v27, 0));
        v78 = v26.m128_u64[0];
        LODWORD(v25) = _mm_shuffle_ps(v26, v26, 170).m128_u32[0];
        v28 = FLOAT_1_0;
      }
      v39 = 0;
      v39.m128_u64[0] = v26.m128_u64[0];
      v40 = 0;
      v40.m128_f32[0] = v25;
      v41 = _mm_mul_ps(_mm_movelh_ps(v39, v40), _mm_shuffle_ps(v21, v21, 0));
      v87 = v41.m128_u64[0];
      v42 = 2 * (v6 + 28);
      v43 = *(_QWORD *)(v23 + 64);
      *(_DWORD *)(v43 + 8 * v42) = v41.m128_i32[0];
      *(_DWORD *)(v43 + 8 * v42 + 4) = HIDWORD(v87);
      *(_DWORD *)(v43 + 8 * v42 + 8) = _mm_shuffle_ps(v41, v41, 170).m128_u32[0];
      *(float *)(v43 + 8 * v42 + 12) = v28;
      v44 = 2 * (v6 + 22);
      v45 = *(_QWORD *)(v23 + 64);
      *(_DWORD *)(v45 + 8 * v44) = v17.m128_i32[0];
      *(_DWORD *)(v45 + 8 * v44 + 4) = v19;
      *(_DWORD *)(v45 + 8 * v44 + 8) = v18;
      *(float *)(v45 + 8 * v44 + 12) = v11.m128_f32[0] * v15.m128_f32[0];
      if ( v6 < 3 )
      {
        if ( *(_QWORD *)&a1[v8] )
        {
          v49 = (std::_Ref_count_base **)&a1[v8 + 8];
        }
        else
        {
          std::weak_ptr<Spectre::Engine::RenderDevice>::lock(v9 + 56, &v94);
          v46 = (__int64 *)Spectre::Engine::SceneNode::GetComponent<Spectre::Engine::ShadowMapCamera>(v94, v102);
          v47 = *v46;
          v48 = (std::_Ref_count_base *)v46[1];
          *v46 = 0;
          v46[1] = 0;
          *(_QWORD *)&a1[v8] = v47;
          v49 = (std::_Ref_count_base **)&a1[v8 + 8];
          v50 = *v49;
          *v49 = v48;
          if ( v50 )
            std::_Ref_count_base::_Decref(v50);
          if ( v103 )
            std::_Ref_count_base::_Decref(v103);
          if ( v95 )
            std::_Ref_count_base::_Decref(v95);
        }
        if ( *v49 )
          _InterlockedIncrement((volatile signed __int32 *)*v49 + 2);
        v51 = *(_QWORD *)&a1[v8];
        v104 = v51;
        v52 = *v49;
        v105 = *v49;
        if ( v51 )
        {
          v53 = v6 << 6;
          if ( *(_BYTE *)(v9 + 124) )
          {
            TransformMatrix = (_OWORD *)Spectre::Engine::Camera::GetTransformMatrix(v51, 0, 2);
            v99[0] = *TransformMatrix;
            v99[1] = TransformMatrix[1];
            v100 = TransformMatrix[2];
            v101 = TransformMatrix[3];
            Spectre::Utils::Math::Matrix::Transpose(
              (Spectre::Utils::Math::Matrix *)v99,
              (struct Spectre::Utils::Math::Matrix *)(v53 + *(_QWORD *)(a3 + 64)));
          }
          else
          {
            v56 = (_OWORD *)Spectre::Utils::Math::Matrix::Matrix(
                              (Spectre::Utils::Math::Matrix *)v99,
                              (const struct Spectre::Utils::Math::Vector4 *)&Spectre::Utils::Math::Vector4::Zero,
                              (const struct Spectre::Utils::Math::Vector4 *)&Spectre::Utils::Math::Vector4::Zero,
                              (const struct Spectre::Utils::Math::Vector4 *)&Spectre::Utils::Math::Vector4::Zero,
                              (const struct Spectre::Utils::Math::Vector4 *)&Spectre::Utils::Math::Vector4::Zero);
            v57 = *(_QWORD *)(v55 + 64);
            v58 = v56[1];
            v59 = v56[2];
            v60 = v56[3];
            *(_OWORD *)(v53 + v57) = *v56;
            *(_OWORD *)(v53 + v57 + 16) = v58;
            *(_OWORD *)(v53 + v57 + 32) = v59;
            *(_OWORD *)(v53 + v57 + 48) = v60;
          }
          v61 = 1.0 / (float)*(int *)(v51 + 1940);
          if ( *(_BYTE *)(v51 + 1952) )
            v62 = FLOAT_1_0;
          else
            v62 = 0.0;
          v63 = *(_DWORD *)(v51 + 1948);
          v64 = *(_DWORD *)(v51 + 316);
          if ( v64 == 2 || v64 == 4 )
            v63 ^= v7;
          if ( *(_DWORD *)(v51 + 1960) == 1 )
            v65 = FLOAT_1_0;
          else
            v65 = 0.0;
          v66 = *(_DWORD *)(v51 + 1968);
          if ( *(_BYTE *)(v9 + 72) && *(_BYTE *)(v9 + 124) )
            v67 = FLOAT_1_0;
          else
            v67 = 0.0;
          v68 = 2 * (v6 + 31);
          v69 = *(_QWORD *)(v55 + 64);
          *(float *)(v69 + 8 * v68) = v61;
          *(float *)(v69 + 8 * v68 + 4) = v61;
          *(float *)(v69 + 8 * v68 + 8) = v62;
          *(_DWORD *)(v69 + 8 * v68 + 12) = v63;
          v70 = 2 * (v6 + 34);
          v71 = *(_QWORD *)(v55 + 64);
          *(_DWORD *)(v71 + 8 * v70) = *(_DWORD *)(v51 + 1956);
          *(float *)(v71 + 8 * v70 + 4) = v65;
          *(_DWORD *)(v71 + 8 * v70 + 8) = v66;
          *(float *)(v71 + 8 * v70 + 12) = v67;
        }
        if ( v52 )
          std::_Ref_count_base::_Decref(v52);
      }
      if ( v97 )
        std::_Ref_count_base::_Decref(v97);
      ++v6;
      v3 = a2;
      if ( v6 >= v5 )
        return a1;
    }
  }
  if ( v5 )
    goto LABEL_4;
  return a1;
}

```

## disassembly

```asm
0x180098514  mov     rax, rsp
0x180098517  mov     [rax+18h], r8
0x18009851b  mov     [rax+10h], rdx
0x18009851f  mov     [rax+8], rcx
0x180098523  push    rbp
0x180098524  push    rbx
0x180098525  push    rsi
0x180098526  push    rdi
0x180098527  push    r12
0x180098529  push    r13
0x18009852b  push    r14
0x18009852d  push    r15
0x18009852f  lea     rbp, [rax-148h]
0x180098536  sub     rsp, 208h
0x18009853d  movaps  xmmword ptr [rax-58h], xmm6
0x180098541  movaps  xmmword ptr [rax-68h], xmm7
0x180098545  movaps  xmmword ptr [rax-78h], xmm8
0x18009854a  movaps  xmmword ptr [rax-88h], xmm9
0x180098552  movaps  xmmword ptr [rax-98h], xmm10
0x18009855a  movaps  xmmword ptr [rax-0A8h], xmm11
0x180098562  movaps  xmmword ptr [rax-0B8h], xmm12
0x18009856a  movaps  xmmword ptr [rax-0C8h], xmm13
0x180098572  movaps  xmmword ptr [rax-0D8h], xmm14
0x18009857a  movaps  xmmword ptr [rax-0E8h], xmm15
0x180098582  mov     rsi, rdx
0x180098585  mov     r12, rcx
0x180098588  mov     [rsp+240h+var_1E0], 0
0x180098590  lea     rax, ??1?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@QEAA@XZ; std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(void)
0x180098597  mov     [rsp+240h+var_220], rax; void (*)(void *)
0x18009859c  lea     r9, ??0?$shared_ptr@VVertexBuffer@Engine@Spectre@@@std@@QEAA@XZ; void (*)(void *)
0x1800985a3  mov     ebx, 3
0x1800985a8  mov     r8d, ebx; unsigned __int64
0x1800985ab  lea     edx, [rbx+0Dh]; unsigned __int64
0x1800985ae  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800985b3  nop
0x1800985b4  mov     [rsp+240h+var_1E0], 1
0x1800985bc  mov     r15, [rsi+8]
0x1800985c0  sub     r15, [rsi]
0x1800985c3  sar     r15, 4
0x1800985c7  xor     edi, edi
0x1800985c9  cmp     r15, rbx
0x1800985cc  jbe     short loc_1800985D3
0x1800985ce  mov     r15d, ebx
0x1800985d1  jmp     short loc_1800985DC
0x1800985d3  test    r15, r15
0x1800985d6  jz      loc_180098C67
0x1800985dc  movss   xmm9, cs:__real@3f800000
0x1800985e5  movss   xmm12, dword ptr cs:__xmm@80000000800000008000000080000000
0x1800985ee  mov     rbx, rdi
0x1800985f1  shl     rbx, 4
0x1800985f5  mov     rdx, [rsi]
0x1800985f8  add     rdx, rbx
0x1800985fb  lea     rcx, [rbp+140h+var_160]
0x1800985ff  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180098604  nop
0x180098605  mov     r14, [rbp+140h+var_160]
0x180098609  movdqu  xmm0, xmmword ptr [r14+58h]
0x18009860f  movss   xmm8, dword ptr [r14+68h]
0x180098615  shufps  xmm8, xmm8, 0
0x18009861a  mulps   xmm8, xmm0
0x18009861e  cmp     byte ptr [r14+48h], 0
0x180098623  jnz     short loc_18009862E
0x180098625  movdqa  xmm8, cs:__xmm@3f800000000000000000000000000000
0x18009862e  movss   xmm11, dword ptr [r14+74h]
0x180098634  mov     esi, [r14+78h]
0x180098638  lea     r13, [r14+38h]
0x18009863c  lea     rdx, [rbp+140h+var_1A0]
0x180098640  mov     rcx, r13
0x180098643  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x180098648  nop
0x180098649  lea     rdx, [rsp+240h+var_1D8]
0x18009864e  mov     rcx, [rbp+140h+var_1A0]
0x180098652  call    ?GetWorldScale@SceneNode@Engine@Spectre@@QEBA?AUVector3@Math@Utils@3@XZ; Spectre::Engine::SceneNode::GetWorldScale(void)
0x180098657  nop
0x180098658  mov     rcx, [rbp+140h+var_198]; this
0x18009865c  test    rcx, rcx
0x18009865f  jz      short loc_180098666
0x180098661  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180098666  movss   xmm0, [rsp+240h+var_1D4]
0x18009866c  mulss   xmm0, [rsp+240h+var_1D8]
0x180098672  mulss   xmm0, dword ptr [rsp+240h+var_1D0]
0x180098678  andps   xmm0, cs:__xmm@7fffffff7fffffff7fffffff7fffffff; X
0x18009867f  call    cs:__imp_cbrtf
0x180098685  movaps  xmm6, xmm0
0x180098688  movss   [rsp+240h+var_1DC], xmm0
0x18009868e  lea     rdx, [rbp+140h+var_190]
0x180098692  mov     rcx, r13
0x180098695  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x18009869a  nop
0x18009869b  lea     rdx, [rsp+240h+var_200]
0x1800986a0  mov     rcx, [rbp+140h+var_190]
0x1800986a4  call    ?GetWorldPosition@SceneNode@Engine@Spectre@@QEBA?AUVector3@Math@Utils@3@XZ; Spectre::Engine::SceneNode::GetWorldPosition(void)
0x1800986a9  nop
0x1800986aa  mov     rcx, [rbp+140h+var_188]; this
0x1800986ae  test    rcx, rcx
0x1800986b1  jz      short loc_1800986B8
0x1800986b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800986b8  lea     rdx, [rbp+140h+var_180]
0x1800986bc  mov     rcx, r13
0x1800986bf  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800986c4  nop
0x1800986c5  lea     rdx, [rbp+140h+var_140]
0x1800986c9  mov     rcx, [rbp+140h+var_180]
0x1800986cd  call    ?GetWorldTransformMatrix@SceneNode@Engine@Spectre@@QEBA?AUMatrix@Math@Utils@3@XZ; Spectre::Engine::SceneNode::GetWorldTransformMatrix(void)
0x1800986d2  movss   xmm0, dword ptr [rbp+140h+var_120+8]
0x1800986d7  xorps   xmm0, xmm12
0x1800986db  movss   [rbp+140h+arg_18], xmm0
0x1800986e3  movss   xmm1, dword ptr [rbp+140h+var_120]
0x1800986e8  xorps   xmm1, xmm12
0x1800986ec  movss   [rsp+240h+var_210], xmm1
0x1800986f2  movss   xmm0, dword ptr [rbp+140h+var_120+4]
0x1800986f7  xorps   xmm0, xmm12
0x1800986fb  movss   [rsp+240h+var_20C], xmm0
0x180098701  mov     al, byte ptr [rbp+140h+arg_18]
0x180098707  mov     byte ptr [rsp+240h+var_208], al
0x18009870b  movzx   eax, word ptr [rbp+140h+arg_18+1]
0x180098712  mov     word ptr [rsp+240h+var_208+1], ax
0x180098717  mov     al, byte ptr [rbp+140h+arg_18+3]
0x18009871d  mov     byte ptr [rsp+240h+var_208+3], al
0x180098721  mov     rcx, [rbp+140h+var_178]; this
0x180098725  test    rcx, rcx
0x180098728  jz      short loc_18009872F
0x18009872a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009872f  lea     rcx, [rsp+240h+var_210]; this
0x180098734  call    ?Normalize@Vector3@Math@Utils@Spectre@@QEAAXXZ; Spectre::Utils::Math::Vector3::Normalize(void)
0x180098739  movss   xmm15, [rsp+240h+var_208]
0x180098740  mov     r8d, 2
0x180098746  cmp     esi, r8d
0x180098749  jnz     short loc_180098794
0x18009874b  movsd   xmm1, qword ptr [rsp+240h+var_210]
0x180098751  movlhps xmm1, xmm15
0x180098755  xorps   xmm10, xmm10
0x180098759  subps   xmm10, xmm1
0x18009875d  mov     [rsp+240h+var_1C8], 0
0x180098766  movsd   [rsp+240h+var_1C8], xmm10
0x18009876d  movaps  xmm13, xmm10
0x180098771  shufps  xmm13, xmm10, 0AAh
0x180098776  movss   [rsp+240h+var_200], xmm10
0x18009877d  movss   xmm14, dword ptr [rsp+240h+var_1C8+4]
0x180098784  movss   [rsp+240h+var_1FC], xmm14
0x18009878b  movss   dword ptr [rsp+240h+var_1F8], xmm13
0x180098792  jmp     short loc_1800987A9
0x180098794  movss   xmm13, dword ptr [rsp+240h+var_1F8]
0x18009879b  movss   xmm14, [rsp+240h+var_1FC]
0x1800987a2  movss   xmm10, [rsp+240h+var_200]
0x1800987a9  mov     ecx, [r14+6Ch]
0x1800987ad  test    ecx, ecx
0x1800987af  jnz     short loc_1800987B9
0x1800987b1  cmp     esi, r8d
0x1800987b4  jz      short loc_1800987E1
0x1800987b6  mov     ecx, r8d
0x1800987b9  xorps   xmm7, xmm7
0x1800987bc  mov     edx, esi
0x1800987be  test    esi, esi
0x1800987c0  jz      loc_1800988A1
0x1800987c6  sub     edx, 1
0x1800987c9  jz      loc_1800988A1
0x1800987cf  cmp     edx, 1
0x1800987d2  jnz     loc_1800988C9
0x1800987d8  cmp     ecx, 3
0x1800987db  jnz     loc_18009886C
0x1800987e1  movaps  xmm7, xmm9
0x1800987e5  lea     rcx, [rdi+19h]
0x1800987e9  add     rcx, rcx
0x1800987ec  mov     r10, [rbp+140h+arg_10]
0x1800987f3  mov     rax, [r10+40h]
0x1800987f7  mov     qword ptr [rax+rcx*8], 0
0x1800987ff  mov     qword ptr [rax+rcx*8+8], 0
0x180098808  movss   [rsp+240h+var_1F0], xmm8
0x18009880f  movaps  xmm0, xmm8
0x180098813  shufps  xmm0, xmm8, 55h ; 'U'
0x180098818  movss   [rsp+240h+var_1EC], xmm0
0x18009881e  shufps  xmm8, xmm8, 0AAh
0x180098823  movss   [rsp+240h+var_1E8], xmm8
0x18009882a  movsd   xmm2, qword ptr [rsp+240h+var_1F0]
0x180098830  cmp     esi, 2
0x180098833  jz      loc_1800989B1
0x180098839  movss   xmm1, [rsp+240h+var_1E8]
0x18009883f  movlhps xmm2, xmm1
0x180098842  movaps  xmm0, xmm6
0x180098845  mulss   xmm0, xmm6
0x180098849  shufps  xmm0, xmm0, 0
0x18009884d  mulps   xmm2, xmm0
0x180098850  movsd   qword ptr [rsp+240h+var_1F0], xmm2
0x180098856  movaps  xmm8, xmm2
0x18009885a  shufps  xmm8, xmm2, 0AAh
0x18009885f  movaps  xmm8, xmm8
0x180098863  movaps  xmm3, xmm9
0x180098867  jmp     loc_1800989B4
0x18009886c  cmp     ecx, 4
0x18009886f  jnz     loc_1800987E5
0x180098875  movss   xmm0, cs:__real@3a83126f
0x18009887d  comiss  xmm0, xmm11
0x180098881  ja      short loc_180098887
0x180098883  movaps  xmm0, xmm11; X
0x180098887  call    cosf
0x18009888c  movaps  xmm7, xmm9
0x180098890  subss   xmm7, xmm0
0x180098894  mulss   xmm7, cs:__real@40c90fdb
0x18009889c  jmp     loc_1800987E5
0x1800988a1  cmp     ecx, 1
0x1800988a4  jnz     short loc_1800988B0
0x1800988a6  movss   xmm7, cs:__real@3da2f983
0x1800988ae  jmp     short loc_1800988C9
0x1800988b0  cmp     ecx, r8d
0x1800988b3  jnz     short loc_1800988BB
0x1800988b5  movaps  xmm7, xmm9
0x1800988b9  jmp     short loc_1800988C9
0x1800988bb  cmp     ecx, 4
0x1800988be  jnz     short loc_1800988C9
0x1800988c0  movaps  xmm7, xmm11
0x1800988c4  mulss   xmm7, xmm11
0x1800988c9  cmp     esi, 1
0x1800988cc  jnz     loc_1800987E5
0x1800988d2  movss   xmm12, dword ptr [r14+70h]
0x1800988d8  comiss  xmm9, xmm12
0x1800988dc  jbe     short loc_1800988E2
0x1800988de  movaps  xmm12, xmm9
0x1800988e2  movss   xmm0, cs:__real@3c23d70a; X
0x1800988ea  call    _o_log2f_0
0x1800988ef  movaps  xmm6, xmm0
0x1800988f2  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x1800988f9  mulss   xmm12, cs:__real@3c8efa35
0x180098902  mulss   xmm12, cs:__real@3f000000
0x18009890b  movaps  xmm0, xmm12; X
0x18009890f  call    cosf
0x180098914  movaps  xmm1, xmm9
0x180098918  subss   xmm1, xmm0
0x18009891c  divss   xmm6, xmm1
0x180098920  movsd   xmm1, qword ptr [rsp+240h+var_210]
0x180098926  movlhps xmm1, xmm15
0x18009892a  xorps   xmm2, xmm2
0x18009892d  subps   xmm2, xmm1
0x180098930  mov     [rbp+140h+var_150], 0
0x180098938  movaps  xmm1, xmm2
0x18009893b  shufps  xmm1, xmm2, 0AAh
0x18009893f  xorps   xmm3, xmm3
0x180098942  movsd   xmm3, xmm2
0x180098946  xorps   xmm0, xmm0
0x180098949  movss   xmm0, xmm1
0x18009894d  movlhps xmm3, xmm0
0x180098950  movaps  xmm0, xmm6
0x180098953  shufps  xmm0, xmm0, 0
0x180098957  mulps   xmm3, xmm0
0x18009895a  mov     [rbp+140h+var_1BC], 0
0x180098962  movsd   [rbp+140h+var_1BC], xmm3
0x180098967  lea     rcx, [rdi+19h]
0x18009896b  add     rcx, rcx
0x18009896e  mov     r10, [rbp+140h+arg_10]
0x180098975  mov     rax, [r10+40h]
0x180098979  movss   dword ptr [rax+rcx*8], xmm3
0x18009897e  movss   xmm0, dword ptr [rbp+140h+var_1BC+4]
0x180098983  movss   dword ptr [rax+rcx*8+4], xmm0
0x180098989  shufps  xmm3, xmm3, 0AAh
0x18009898d  movss   dword ptr [rax+rcx*8+8], xmm3
0x180098993  movss   xmm12, dword ptr cs:__xmm@80000000800000008000000080000000
0x18009899c  xorps   xmm6, xmm12
0x1800989a0  movss   dword ptr [rax+rcx*8+0Ch], xmm6
0x1800989a6  movss   xmm6, [rsp+240h+var_1DC]
0x1800989ac  jmp     loc_180098808
0x1800989b1  xorps   xmm3, xmm3
0x1800989b4  xorps   xmm1, xmm1
0x1800989b7  movsd   xmm1, xmm2
0x1800989bb  xorps   xmm0, xmm0
0x1800989be  movss   xmm0, xmm8
0x1800989c3  movlhps xmm1, xmm0
0x1800989c6  shufps  xmm7, xmm7, 0
0x1800989ca  mulps   xmm1, xmm7
0x1800989cd  mov     [rbp+140h+var_1B0], 0
0x1800989d5  movsd   [rbp+140h+var_1B0], xmm1
0x1800989da  lea     rcx, [rdi+1Ch]
0x1800989de  add     rcx, rcx
0x1800989e1  mov     rax, [r10+40h]
0x1800989e5  movss   dword ptr [rax+rcx*8], xmm1
0x1800989ea  movss   xmm0, dword ptr [rbp+140h+var_1B0+4]
0x1800989ef  movss   dword ptr [rax+rcx*8+4], xmm0
0x1800989f5  shufps  xmm1, xmm1, 0AAh
0x1800989f9  movss   dword ptr [rax+rcx*8+8], xmm1
0x1800989ff  movss   dword ptr [rax+rcx*8+0Ch], xmm3
0x180098a05  lea     rdx, [rdi+16h]
0x180098a09  add     rdx, rdx
0x180098a0c  mov     rax, [r10+40h]
0x180098a10  movss   dword ptr [rax+rdx*8], xmm10
0x180098a16  movss   dword ptr [rax+rdx*8+4], xmm14
0x180098a1d  movss   dword ptr [rax+rdx*8+8], xmm13
0x180098a24  mulss   xmm11, xmm6
0x180098a29  movss   dword ptr [rax+rdx*8+0Ch], xmm11
0x180098a30  cmp     rdi, 3
0x180098a34  jnb     loc_180098C46
0x180098a3a  cmp     qword ptr [rbx+r12], 0
0x180098a3f  jnz     short loc_180098AB3
0x180098a41  lea     rdx, [rbp+140h+var_170]
0x180098a45  mov     rcx, r13
0x180098a48  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x180098a4d  nop
0x180098a4e  lea     rdx, [rbp+140h+var_100]
0x180098a52  mov     rcx, [rbp+140h+var_170]
0x180098a56  call    ??$GetComponent@VShadowMapCamera@Engine@Spectre@@@SceneNode@Engine@Spectre@@QEBA?AV?$shared_ptr@VShadowMapCamera@Engine@Spectre@@@std@@XZ; Spectre::Engine::SceneNode::GetComponent<Spectre::Engine::ShadowMapCamera>(void)
0x180098a5b  mov     rcx, [rax]
0x180098a5e  mov     rdx, [rax+8]
  ... truncated ...
```
