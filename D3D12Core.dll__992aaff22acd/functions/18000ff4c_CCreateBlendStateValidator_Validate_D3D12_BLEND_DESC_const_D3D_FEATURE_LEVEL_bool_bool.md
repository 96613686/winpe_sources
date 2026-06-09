# CCreateBlendStateValidator::Validate(D3D12_BLEND_DESC const *,D3D_FEATURE_LEVEL,bool,bool)

- ea: `0x18000ff4c`
- end: `0x180010495`
- name: `?Validate@CCreateBlendStateValidator@@QEAAJPEBUD3D12_BLEND_DESC@@W4D3D_FEATURE_LEVEL@@_N2@Z`
- size: `1353`
- prototype: `__int64 __fastcall(CCreateBlendStateValidator *__hidden this, const struct D3D12_BLEND_DESC *, enum D3D_FEATURE_LEVEL, bool, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fa78`

## callees

- `0x18000ff4c`
- `0x18002ef50`

## string_xrefs

- `0x1800101eb`: `SrcBlend[ %d ] does not equal SrcBlend[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.`
- `0x18001025c`: `DestBlend[ %d ] does not equal DestBlend[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.`
- `0x1800103b4`: `DestBlendAlpha[ %d ] does not equal DestBlendAlpha[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.`
- `0x180010420`: `BlendOpAlpha[ %d ] does not equal BlendOpAlpha[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.`
- `0x180010441`: `RenderTargetWriteMask[ %d ] can only have the least significant 4 bits set. Value provided is 0x%x.`
- `0x180010477`: `LogicOpEnable cannot be set true on the current device.`
- `0x1800102c8`: `BlendOp[ %d ] does not equal BlendOp[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.`
- `0x180010337`: `SrcBlendAlpha[ %d ] does not equal SrcBlendAlpha[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.`
- `0x180231e86`: `LogicOpEnable and IndependentBlendEnable cannot both be set to true.`
- `0x180231ea6`: `LogicOpEnable and BlendEnable cannot both be set to true.`

## pseudocode

```c
__int64 __fastcall CCreateBlendStateValidator::Validate(
        CCreateBlendStateValidator *this,
        const struct D3D12_BLEND_DESC *a2,
        int a3,
        char a4,
        bool a5)
{
  int v5; // ebx
  int v6; // r15d
  char v7; // r13
  _DWORD *v8; // rdi
  __int64 v10; // rsi
  const struct D3D12_BLEND_DESC *v11; // r14
  char *v12; // rbp
  int v14; // edx
  _DWORD *v15; // r14
  int v16; // eax
  char v17; // di
  int v18; // edx
  int v19; // edx
  char v20; // di
  int v21; // edx
  const char *v22; // r8
  const char *v23; // r8
  int v24; // edx
  bool v25; // zf
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  __int64 v31; // [rsp+20h] [rbp-48h]
  char v32; // [rsp+70h] [rbp+8h]

  v5 = 0;
  v6 = 0;
  v7 = 0;
  v32 = 0;
  v8 = 0;
  v10 = 0;
  v11 = a2;
  while ( (unsigned int)v10 < (v11->IndependentBlendEnable ? 8 : 1) )
  {
    v12 = (char *)v11 + 40 * v10;
    if ( !*((_DWORD *)v12 + 2) )
      goto LABEL_4;
    v14 = *((_DWORD *)v12 + 4);
    v15 = v12 + 8;
    v16 = v10;
    if ( v8 )
    {
      v16 = v6;
      v15 = v8;
    }
    v17 = 0;
    v6 = v16;
    if ( v14 <= 10 )
    {
      if ( v14 != 10
        && v14 != 1
        && v14 != 2
        && v14 != 3
        && v14 != 4
        && v14 != 5
        && v14 != 6
        && v14 != 7
        && (unsigned int)(v14 - 8) >= 2 )
      {
LABEL_102:
        ++v5;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          111,
          "SrcBlend[ %d ] has an unrecognized value (0x%x), which is not a member of D3D11_BLEND.",
          v10,
          v14);
      }
    }
    else if ( v14 != 11 && v14 != 14 && v14 != 15 )
    {
      if ( v14 == 16 || v14 == 17 || v14 == 18 || v14 == 19 )
      {
        if ( (_DWORD)v10 )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            111,
            "SrcBlend[ %d ] is trying to use a dual source blending operation, value (0x%x), which is not valid for any o"
            "ther render target slot other than 0.",
            v10,
            v14);
        }
        v17 = 1;
        v7 = 1;
      }
      else
      {
        if ( (unsigned int)(v14 - 20) > 1 )
          goto LABEL_102;
        if ( !a5 )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            1349,
            "Alpha blend factor is not supported on this device.");
        }
      }
    }
    if ( a3 <= 40960 && *((_DWORD *)v12 + 4) != v15[2] )
    {
      ++v5;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        111,
        "SrcBlend[ %d ] does not equal SrcBlend[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel returns"
        " D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.",
        v10,
        v6);
    }
    v18 = *((_DWORD *)v12 + 5);
    if ( v18 <= 10 )
    {
      if ( v18 != 10
        && v18 != 1
        && v18 != 2
        && v18 != 3
        && v18 != 4
        && v18 != 5
        && v18 != 6
        && v18 != 7
        && (unsigned int)(v18 - 8) >= 2 )
      {
LABEL_117:
        ++v5;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          112,
          "DestBlend[ %d ] has an unrecognized value (0x%x), which is not a member of D3D11_BLEND.",
          v10,
          v18);
      }
    }
    else if ( v18 != 11 && v18 != 14 && v18 != 15 )
    {
      if ( v18 == 16 || v18 == 17 || v18 == 18 || v18 == 19 )
      {
        if ( (_DWORD)v10 )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            112,
            "DestBlend[ %d ] is trying to use a dual source blending operation, value (0x%x), which is not valid for any "
            "other render target slot other than 0.",
            v10,
            v18);
        }
        v17 = 1;
        v7 = 1;
      }
      else
      {
        if ( (unsigned int)(v18 - 20) > 1 )
          goto LABEL_117;
        if ( !a5 )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            1349,
            "Alpha blend factor is not supported on this device.");
        }
      }
    }
    if ( a3 <= 40960 && *((_DWORD *)v12 + 5) != v15[3] )
    {
      ++v5;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        112,
        "DestBlend[ %d ] does not equal DestBlend[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel retur"
        "ns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.",
        v10,
        v6);
    }
    if ( *((_DWORD *)v12 + 6) != 1 && *((_DWORD *)v12 + 6) != 2 && *((_DWORD *)v12 + 6) != 3 )
    {
      if ( (unsigned int)(*((_DWORD *)v12 + 6) - 4) < 2 )
      {
        if ( v17 )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            113,
            "MIN or MAX are invalid for BlendOp when Dual-Source blending.");
        }
      }
      else
      {
        ++v5;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          113,
          "BlendOp[ %d ] has an unrecognized value (0x%x), which is not a member of D3D11_BLEND_OP.",
          v10,
          *((_DWORD *)v12 + 6));
      }
    }
    if ( a3 <= 40960 && *((_DWORD *)v12 + 6) != v15[4] )
    {
      ++v5;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        113,
        "BlendOp[ %d ] does not equal BlendOp[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel returns D"
        "3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.",
        v10,
        v6);
    }
    v19 = *((_DWORD *)v12 + 7);
    v20 = 0;
    if ( v19 <= 10 )
    {
      if ( v19 == 10 )
        goto LABEL_138;
      if ( v19 != 1 && v19 != 2 )
      {
        if ( v19 == 3 || v19 == 4 )
          goto LABEL_138;
        if ( v19 != 5 && v19 != 6 && v19 != 7 && v19 != 8 )
        {
          if ( v19 == 9 )
LABEL_138:
            v23 = "SrcBlendAlpha[ %d ] is trying to use a D3D11_BLEND value (0x%x) that manipulates color, which is invalid.";
          else
LABEL_132:
            v23 = "SrcBlendAlpha[ %d ] has an unrecognized value (0x%x), which is not a member of D3D11_BLEND.";
          LODWORD(v31) = *((_DWORD *)v12 + 7);
          ++v5;
          TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 114, v23, (unsigned int)v10, v31);
        }
      }
    }
    else if ( v19 != 11 && v19 != 14 && v19 != 15 )
    {
      if ( v19 == 16 || v19 == 17 )
        goto LABEL_138;
      if ( v19 == 18 || v19 == 19 )
      {
        if ( (_DWORD)v10 )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            114,
            "SrcBlendAlpha[ %d ] is trying to use a dual source blending operation, value (0x%x), which is not valid for "
            "any other render target slot other than 0.",
            v10,
            v19);
        }
        v20 = 1;
        v32 = 1;
      }
      else
      {
        if ( (unsigned int)(v19 - 20) > 1 )
          goto LABEL_132;
        if ( !a5 )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            1349,
            "Alpha blend factor is not supported on this device.");
        }
      }
    }
    if ( a3 <= 40960 && *((_DWORD *)v12 + 7) != v15[5] )
    {
      ++v5;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        114,
        "SrcBlendAlpha[ %d ] does not equal SrcBlendAlpha[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLev"
        "el returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.",
        v10,
        v6);
    }
    v21 = *((_DWORD *)v12 + 8);
    if ( v21 <= 10 )
    {
      if ( v21 != 10 )
      {
        if ( v21 == 1 || v21 == 2 )
          goto LABEL_34;
        if ( v21 != 3 && v21 != 4 )
        {
          if ( v21 == 5 || v21 == 6 || v21 == 7 || v21 == 8 )
            goto LABEL_34;
          if ( v21 != 9 )
            goto LABEL_150;
        }
      }
    }
    else
    {
      if ( v21 == 11 || v21 == 14 || v21 == 15 )
        goto LABEL_34;
      if ( v21 != 16 && v21 != 17 )
      {
        if ( v21 == 18 || v21 == 19 )
        {
          if ( (_DWORD)v10 )
          {
            ++v5;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              115,
              "DestBlendAlpha[ %d ] is trying to use a dual source blending operation, value (0x%x), which is not valid f"
              "or any other render target slot other than 0.",
              v10,
              v21);
          }
          v20 = 1;
          v32 = 1;
          goto LABEL_34;
        }
        if ( (unsigned int)(v21 - 20) <= 1 )
        {
          if ( !a5 )
          {
            ++v5;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              1349,
              "Alpha blend factor is not supported on this device.");
          }
          goto LABEL_34;
        }
LABEL_150:
        v22 = "DestBlendAlpha[ %d ] has an unrecognized value (0x%x), which is not a member of D3D11_BLEND.";
        goto LABEL_151;
      }
    }
    v22 = "DestBlendAlpha[ %d ] is trying to use a D3D11_BLEND value (0x%x) that manipulates color, which is invalid.";
LABEL_151:
    LODWORD(v31) = *((_DWORD *)v12 + 8);
    ++v5;
    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 115, v22, (unsigned int)v10, v31);
LABEL_34:
    if ( a3 <= 40960 && *((_DWORD *)v12 + 8) != v15[6] )
    {
      ++v5;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        115,
        "DestBlendAlpha[ %d ] does not equal DestBlendAlpha[ %d ] and D3D10.1 hardware is not supported. When GetFeatureL"
        "evel returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.",
        v10,
        v6);
    }
    if ( *((_DWORD *)v12 + 9) != 1 && *((_DWORD *)v12 + 9) != 2 && *((_DWORD *)v12 + 9) != 3 )
    {
      if ( (unsigned int)(*((_DWORD *)v12 + 9) - 4) < 2 )
      {
        if ( v20 )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            116,
            "MIN or MAX are invalid for BlendOpAlpha when Dual-Source blending.");
        }
      }
      else
      {
        ++v5;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          116,
          "BlendOpAlpha[ %d ] has an unrecognized value (0x%x), which is not a member of D3D11_BLEND_OP.",
          v10,
          *((_DWORD *)v12 + 9));
      }
    }
    if ( a3 <= 40960 && *((_DWORD *)v12 + 9) != v15[7] )
    {
      ++v5;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        116,
        "BlendOpAlpha[ %d ] does not equal BlendOpAlpha[ %d ] and D3D10.1 hardware is not supported. When GetFeatureLevel"
        " returns D3D_FEATURE_LEVEL_10_0 or less, any enabled render target blending must use the same blending configuration.",
        v10,
        v6);
    }
    if ( (_DWORD)v10 && (v7 || v32) )
    {
      ++v5;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        v7 != 0 ? 113 : 116,
        "Dual-source color blending cannot be used when BlendEnable is set for a RenderTarget above 0.Specifically, to us"
        "e Dual-source color blending, it must only be used on RenderTarget 0 with BlendEnable set only on RenderTarget 0.");
    }
    v8 = v15;
    v11 = a2;
LABEL_4:
    if ( (v12[44] & 0xF0) != 0 )
    {
      ++v5;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        117,
        "RenderTargetWriteMask[ %d ] can only have the least significant 4 bits set. Value provided is 0x%x.",
        v10,
        (unsigned __int8)v12[44]);
    }
    if ( *((_DWORD *)v12 + 3) )
    {
      if ( !a4 )
      {
        ++v5;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          403,
          "LogicOpEnable cannot be set true on the current device.");
      }
      if ( v11->IndependentBlendEnable )
      {
        ++v5;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          403,
          "LogicOpEnable and IndependentBlendEnable cannot both be set to true.");
      }
      if ( *((_DWORD *)v12 + 2) )
      {
        ++v5;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          403,
          "LogicOpEnable and BlendEnable cannot both be set to true.");
      }
      v24 = *((_DWORD *)v12 + 10);
      if ( v24 > 8 )
      {
        v25 = v24 == 9;
        v26 = v24 - 9;
      }
      else
      {
        if ( v24 == 8 || !v24 )
          goto LABEL_7;
        v26 = v24 - 1;
        v25 = v24 == 1;
      }
      if ( !v25 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 )
          {
            v29 = v28 - 1;
            if ( v29 )
            {
              v30 = v29 - 1;
              if ( v30 )
              {
                if ( (unsigned int)(v30 - 1) >= 2 )
                {
                  ++v5;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    403,
                    "LogicOp[ %d ] has an unrecognized value (0x%x), which is not a member of D3D11_LOGIC_OP.",
                    v10,
                    v24);
                }
              }
            }
          }
        }
      }
    }
LABEL_7:
    v10 = (unsigned int)(v10 + 1);
  }
  return v5 != 0 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x18000ff4c  mov     rax, rsp
0x18000ff4f  mov     [rax+18h], rbx
0x18000ff53  mov     [rax+20h], r9b
0x18000ff57  mov     [rax+10h], rdx
0x18000ff5b  mov     [rax+8], rcx
0x18000ff5f  push    rbp
0x18000ff60  push    rsi
0x18000ff61  push    rdi
0x18000ff62  push    r12
0x18000ff64  push    r13
0x18000ff66  push    r14
0x18000ff68  push    r15
0x18000ff6a  sub     rsp, 30h
0x18000ff6e  xor     ebx, ebx
0x18000ff70  xor     r15d, r15d
0x18000ff73  xor     r13b, r13b
0x18000ff76  mov     [rsp+68h+arg_0], bl
0x18000ff7a  xor     edi, edi
0x18000ff7c  mov     r12d, r8d
0x18000ff7f  xor     esi, esi
0x18000ff81  mov     r14, rdx
0x18000ff84  mov     eax, [r14+4]
0x18000ff88  neg     eax
0x18000ff8a  sbb     ecx, ecx
0x18000ff8c  and     ecx, 7
0x18000ff8f  inc     ecx
0x18000ff91  cmp     esi, ecx
0x18000ff93  jnb     short loc_18000FFBB
0x18000ff95  lea     rcx, [rsi+rsi*4]
0x18000ff99  lea     rbp, [r14+rcx*8]
0x18000ff9d  cmp     dword ptr [rbp+8], 0
0x18000ffa1  jnz     short loc_18000FFDC
0x18000ffa3  test    byte ptr [rbp+2Ch], 0F0h
0x18000ffa7  jnz     loc_18001043D
0x18000ffad  cmp     dword ptr [rbp+0Ch], 0
0x18000ffb1  jnz     loc_180010467
0x18000ffb7  inc     esi
0x18000ffb9  jmp     short loc_18000FF84
0x18000ffbb  neg     ebx
0x18000ffbd  mov     rbx, [rsp+68h+arg_10]
0x18000ffc5  sbb     eax, eax
0x18000ffc7  and     eax, 80070057h
0x18000ffcc  add     rsp, 30h
0x18000ffd0  pop     r15
0x18000ffd2  pop     r14
0x18000ffd4  pop     r13
0x18000ffd6  pop     r12
0x18000ffd8  pop     rdi
0x18000ffd9  pop     rsi
0x18000ffda  pop     rbp
0x18000ffdb  retn
0x18000ffdc  mov     edx, [rbp+10h]
0x18000ffdf  lea     r14, [rbp+8]
0x18000ffe3  test    rdi, rdi
0x18000ffe6  mov     eax, esi
0x18000ffe8  cmovnz  eax, r15d
0x18000ffec  cmovnz  r14, rdi
0x18000fff0  xor     dil, dil
0x18000fff3  mov     r15d, eax
0x18000fff6  cmp     edx, 0Ah
0x18000fff9  jle     loc_180231B0C
0x18000ffff  mov     ecx, edx
0x180010001  sub     ecx, 0Bh
0x180010004  jz      short loc_180010014
0x180010006  sub     ecx, 3
0x180010009  jz      short loc_180010014
0x18001000b  sub     ecx, 1
0x18001000e  jnz     loc_180010199
0x180010014  cmp     r12d, 0A000h
0x18001001b  jle     loc_1800101D4
0x180010021  mov     edx, [rbp+14h]
0x180010024  cmp     edx, 0Ah
0x180010027  jle     loc_180231BEA
0x18001002d  mov     ecx, edx
0x18001002f  sub     ecx, 0Bh
0x180010032  jz      short loc_180010042
0x180010034  sub     ecx, 3
0x180010037  jz      short loc_180010042
0x180010039  sub     ecx, 1
0x18001003c  jnz     loc_180010139
0x180010042  cmp     r12d, 0A000h
0x180010049  jle     loc_180010245
0x18001004f  mov     edx, [rbp+18h]
0x180010052  mov     ecx, edx
0x180010054  sub     ecx, 1
0x180010057  jz      short loc_180010067
0x180010059  sub     ecx, 1
0x18001005c  jz      short loc_180010067
0x18001005e  sub     ecx, 1
0x180010061  jnz     loc_180010279
0x180010067  cmp     r12d, 0A000h
0x18001006e  jle     loc_1800102B1
0x180010074  mov     edx, [rbp+1Ch]
0x180010077  xor     dil, dil
0x18001007a  cmp     edx, 0Ah
0x18001007d  jle     loc_180231CC1
0x180010083  mov     ecx, edx
0x180010085  sub     ecx, 0Bh
0x180010088  jz      short loc_180010098
0x18001008a  sub     ecx, 3
0x18001008d  jz      short loc_180010098
0x18001008f  sub     ecx, 1
0x180010092  jnz     loc_1800102E5
0x180010098  cmp     r12d, 0A000h
0x18001009f  jle     loc_180010320
0x1800100a5  mov     edx, [rbp+20h]
0x1800100a8  cmp     edx, 0Ah
0x1800100ab  jle     loc_180231DA6
0x1800100b1  mov     ecx, edx
0x1800100b3  sub     ecx, 0Bh
0x1800100b6  jz      short loc_1800100C6
0x1800100b8  sub     ecx, 3
0x1800100bb  jz      short loc_1800100C6
0x1800100bd  sub     ecx, 1
0x1800100c0  jnz     loc_180010164
0x1800100c6  cmp     r12d, 0A000h
0x1800100cd  jle     loc_18001039D
0x1800100d3  mov     edx, [rbp+24h]
0x1800100d6  mov     ecx, edx
0x1800100d8  sub     ecx, 1
0x1800100db  jz      short loc_1800100EB
0x1800100dd  sub     ecx, 1
0x1800100e0  jz      short loc_1800100EB
0x1800100e2  sub     ecx, 1
0x1800100e5  jnz     loc_1800103D1
0x1800100eb  cmp     r12d, 0A000h
0x1800100f2  jle     loc_180010409
0x1800100f8  test    esi, esi
0x1800100fa  jnz     short loc_180010109
0x1800100fc  mov     rdi, r14
0x1800100ff  mov     r14, [rsp+68h+arg_8]
0x180010104  jmp     loc_18000FFA3
0x180010109  test    r13b, r13b
0x18001010c  jnz     short loc_180010115
0x18001010e  cmp     [rsp+68h+arg_0], r13b
0x180010113  jz      short loc_1800100FC
0x180010115  inc     ebx
0x180010117  lea     r8, aDualSourceColo; "Dual-source color blending cannot be us"...
0x18001011e  mov     al, r13b
0x180010121  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180010128  neg     al
0x18001012a  sbb     edx, edx
0x18001012c  and     edx, 0FFFFFFFDh
0x18001012f  add     edx, 74h ; 't'
0x180010132  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180010137  jmp     short loc_1800100FC
0x180010139  sub     ecx, 1
0x18001013c  jz      short loc_180010151
0x18001013e  sub     ecx, 1
0x180010141  jz      short loc_180010151
0x180010143  sub     ecx, 1
0x180010146  jz      short loc_180010151
0x180010148  sub     ecx, 1
0x18001014b  jnz     loc_180010208
0x180010151  test    esi, esi
0x180010153  jnz     loc_18001021F
0x180010159  mov     dil, 1
0x18001015c  mov     r13b, dil
0x18001015f  jmp     loc_180010042
0x180010164  sub     ecx, 1
0x180010167  jz      loc_180010391
0x18001016d  sub     ecx, 1
0x180010170  jz      loc_180010391
0x180010176  sub     ecx, 1
0x180010179  jz      short loc_180010184
0x18001017b  sub     ecx, 1
0x18001017e  jnz     loc_180010354
0x180010184  test    esi, esi
0x180010186  jnz     loc_18001036B
0x18001018c  mov     dil, 1
0x18001018f  mov     [rsp+68h+arg_0], dil
0x180010194  jmp     loc_1800100C6
0x180010199  sub     ecx, 1
0x18001019c  jz      loc_180231BBA
0x1800101a2  sub     ecx, 1
0x1800101a5  jz      loc_180231BBA
0x1800101ab  sub     ecx, 1
0x1800101ae  jz      loc_180231BBA
0x1800101b4  sub     ecx, 1
0x1800101b7  jz      loc_180231BBA
0x1800101bd  sub     ecx, 1
0x1800101c0  jz      loc_180231B8C
0x1800101c6  cmp     ecx, 1
0x1800101c9  jnz     loc_180231B65
0x1800101cf  jmp     loc_180231B8C
0x1800101d4  mov     eax, [r14+8]
0x1800101d8  cmp     [rbp+10h], eax
0x1800101db  jz      loc_180010021
0x1800101e1  inc     ebx
0x1800101e3  mov     dword ptr [rsp+68h+var_48], r15d
0x1800101e8  mov     r9d, esi
0x1800101eb  lea     r8, aSrcblendDDoesN; "SrcBlend[ %d ] does not equal SrcBlend["...
0x1800101f2  mov     edx, 6Fh ; 'o'
0x1800101f7  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x1800101fe  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180010203  jmp     loc_180010021
0x180010208  sub     ecx, 1
0x18001020b  jz      loc_180231C6A
0x180010211  cmp     ecx, 1
0x180010214  jnz     loc_180231C43
0x18001021a  jmp     loc_180231C6A
0x18001021f  mov     dword ptr [rsp+68h+var_48], edx
0x180010223  lea     r8, aDestblendDIsTr; "DestBlend[ %d ] is trying to use a dual"...
0x18001022a  mov     edx, 70h ; 'p'
0x18001022f  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180010236  inc     ebx
0x180010238  mov     r9d, esi
0x18001023b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180010240  jmp     loc_180010159
0x180010245  mov     eax, [r14+0Ch]
0x180010249  cmp     [rbp+14h], eax
0x18001024c  jz      loc_18001004F
0x180010252  inc     ebx
0x180010254  mov     dword ptr [rsp+68h+var_48], r15d
0x180010259  mov     r9d, esi
0x18001025c  lea     r8, aDestblendDDoes; "DestBlend[ %d ] does not equal DestBlen"...
0x180010263  mov     edx, 70h ; 'p'
0x180010268  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x18001026f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180010274  jmp     loc_18001004F
0x180010279  sub     ecx, 1
0x18001027c  jz      loc_180231C98
0x180010282  cmp     ecx, 1
0x180010285  jz      loc_180231C98
0x18001028b  mov     dword ptr [rsp+68h+var_48], edx
0x18001028f  lea     r8, aBlendopDHasAnU; "BlendOp[ %d ] has an unrecognized value"...
0x180010296  mov     edx, 71h ; 'q'
0x18001029b  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x1800102a2  inc     ebx
0x1800102a4  mov     r9d, esi
0x1800102a7  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800102ac  jmp     loc_180010067
0x1800102b1  mov     eax, [r14+10h]
0x1800102b5  cmp     [rbp+18h], eax
0x1800102b8  jz      loc_180010074
0x1800102be  inc     ebx
0x1800102c0  mov     dword ptr [rsp+68h+var_48], r15d
0x1800102c5  mov     r9d, esi
0x1800102c8  lea     r8, aBlendopDDoesNo; "BlendOp[ %d ] does not equal BlendOp[ %"...
0x1800102cf  mov     edx, 71h ; 'q'
0x1800102d4  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x1800102db  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800102e0  jmp     loc_180010074
0x1800102e5  sub     ecx, 1
0x1800102e8  jz      loc_180231D7F
0x1800102ee  sub     ecx, 1
0x1800102f1  jz      loc_180231D7F
0x1800102f7  sub     ecx, 1
0x1800102fa  jz      loc_180231D4D
0x180010300  sub     ecx, 1
0x180010303  jz      loc_180231D4D
0x180010309  sub     ecx, 1
0x18001030c  jz      loc_180231D1F
0x180010312  cmp     ecx, 1
0x180010315  jnz     loc_180231D16
0x18001031b  jmp     loc_180231D1F
0x180010320  mov     eax, [r14+14h]
0x180010324  cmp     [rbp+1Ch], eax
0x180010327  jz      loc_1800100A5
0x18001032d  inc     ebx
0x18001032f  mov     dword ptr [rsp+68h+var_48], r15d
0x180010334  mov     r9d, esi
0x180010337  lea     r8, aSrcblendalphaD_0; "SrcBlendAlpha[ %d ] does not equal SrcB"...
0x18001033e  mov     edx, 72h ; 'r'
0x180010343  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x18001034a  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18001034f  jmp     loc_1800100A5
0x180010354  sub     ecx, 1
0x180010357  jz      loc_180231E26
0x18001035d  cmp     ecx, 1
0x180010360  jnz     loc_180231DFF
0x180010366  jmp     loc_180231E26
0x18001036b  mov     dword ptr [rsp+68h+var_48], edx
0x18001036f  lea     r8, aDestblendalpha_3; "DestBlendAlpha[ %d ] is trying to use a"...
0x180010376  mov     edx, 73h ; 's'
0x18001037b  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180010382  inc     ebx
0x180010384  mov     r9d, esi
0x180010387  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18001038c  jmp     loc_18001018C
0x180010391  lea     r8, aDestblendalpha_1; "DestBlendAlpha[ %d ] is trying to use a"...
0x180010398  jmp     loc_180231E06
0x18001039d  mov     eax, [r14+18h]
0x1800103a1  cmp     [rbp+20h], eax
0x1800103a4  jz      loc_1800100D3
0x1800103aa  inc     ebx
0x1800103ac  mov     dword ptr [rsp+68h+var_48], r15d
0x1800103b1  mov     r9d, esi
0x1800103b4  lea     r8, aDestblendalpha_2; "DestBlendAlpha[ %d ] does not equal Des"...
0x1800103bb  mov     edx, 73h ; 's'
0x1800103c0  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x1800103c7  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800103cc  jmp     loc_1800100D3
0x1800103d1  sub     ecx, 1
0x1800103d4  jz      loc_180231E54
0x1800103da  cmp     ecx, 1
0x1800103dd  jz      loc_180231E54
0x1800103e3  mov     dword ptr [rsp+68h+var_48], edx
0x1800103e7  lea     r8, aBlendopalphaDH; "BlendOpAlpha[ %d ] has an unrecognized "...
0x1800103ee  mov     edx, 74h ; 't'
  ... truncated ...
```
