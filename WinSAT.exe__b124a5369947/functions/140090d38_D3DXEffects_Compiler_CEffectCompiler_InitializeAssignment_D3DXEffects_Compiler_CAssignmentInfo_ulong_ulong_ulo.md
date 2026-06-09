# D3DXEffects::Compiler::CEffectCompiler::InitializeAssignment(D3DXEffects::Compiler::CAssignmentInfo *,ulong,ulong,ulong,ulong *,D3DXEffects::Compiler::CData *,D3DXEffects::Compiler::CData *,ulong)

- ea: `0x140090d38`
- end: `0x140091ac7`
- name: `?InitializeAssignment@CEffectCompiler@Compiler@D3DXEffects@@AEAAJPEAVCAssignmentInfo@23@KKKPEAKPEAVCData@23@2K@Z`
- size: `3471`
- prototype: `__int64 __fastcall(D3DXEffects::Compiler::CEffectCompiler *__hidden this, struct D3DXEffects::Compiler::CAssignmentInfo *, unsigned int, unsigned int, unsigned int, unsigned int *, struct D3DXEffects::Compiler::CData *, struct D3DXEffects::Compiler::CData *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400924ac`
- `0x140092d9c`

## callees

- `0x140001abc`
- `0x140003611`
- `0x14008c0e0`
- `0x14008c6e4`
- `0x14008c860`
- `0x14008c960`
- `0x140090d38`
- `0x1400935bc`
- `0x1400a96b4`

## import_xrefs

- `msvcrt!_stricmp` at `0x140091439`
- `msvcrt!_stricmp` at `0x140091439`

## string_xrefs

- `0x14009121f`: `ID3DXEffectCompiler: Unexpected error`
- `0x140091228`: `ID3DXEffectCompiler: Initializer list elements cannot be complex expressions or variables`
- `0x1400914aa`: `ID3DXEffectCompiler: State '%s' does not accept '%s' as a value`
- `0x140091202`: `ID3DXEffectCompiler: Error in type checking`
- `0x14009161e`: `ID3DXEffectCompiler: FVFs must not evaluate to NULL`
- `0x1400914e4`: `ID3DXEffectCompiler: State '%s' accepts only dwords and ids`
- `0x140090e11`: `ID3DXEffectCompiler: State '%s' was assigned an unsupported value`
- `0x140091606`: `ID3DXEffectCompiler: Dword expressions for state '%s' must be evaluate to NULL`
- `0x140091829`: `ID3DXEffectCompiler: Internal error initializing assignment - missing type case`
- `0x1400917e9`: `ID3DXEffectCompiler: Error initializing assignment type`

## pseudocode

```c
__int64 __fastcall D3DXEffects::Compiler::CEffectCompiler::InitializeAssignment(
        D3DXEffects::Compiler::CEffectCompiler *this,
        struct D3DXEffects::Compiler::CAssignmentInfo *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int *a6,
        struct D3DXEffects::Compiler::CData *a7,
        struct D3DXEffects::Compiler::CData *a8,
        unsigned int a9)
{
  __int64 v9; // rsi
  __int64 v10; // r10
  int v11; // ebx
  struct D3DXEffects::Compiler::CAssignmentInfo *v14; // r13
  D3DXEffects::Compiler::CEffectCompiler *v15; // r12
  __int64 v16; // r9
  unsigned __int64 v17; // r8
  int v18; // edi
  int v19; // r10d
  int v20; // ecx
  int v21; // eax
  const struct D3DX9MEMORY::CD3DXNEW *v22; // rdx
  int v23; // ecx
  unsigned __int8 *v24; // rax
  size_t v26; // rbx
  unsigned int v27; // r8d
  unsigned __int8 *v28; // rdx
  _QWORD *v29; // rax
  D3DXEffects::Compiler::CAssignment *v30; // r15
  D3DXEffects::Compiler::CData *v31; // r14
  __int64 v32; // rdx
  int v33; // eax
  size_t v34; // rbx
  int v35; // r10d
  __int64 v36; // rbx
  __int64 v37; // rax
  int v38; // r11d
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  double *v43; // r8
  int v44; // edx
  int v45; // edx
  int v46; // edx
  float v47; // xmm0_4
  __m128i v48; // xmm0
  int v49; // edx
  int v50; // edx
  int v51; // eax
  int v52; // edx
  int v53; // edx
  const char *v54; // r9
  __int64 v55; // rcx
  int v56; // eax
  int v57; // r8d
  int v58; // edx
  int v59; // ecx
  int v60; // eax
  unsigned int v61; // r8d
  unsigned __int8 *v62; // rdx
  unsigned int v63; // esi
  unsigned int v64; // ecx
  __int64 v65; // r14
  _QWORD *v66; // r8
  unsigned int v67; // r12d
  __int64 v68; // rcx
  __int64 v69; // rax
  int v70; // eax
  unsigned int v71; // edx
  int v72; // edi
  int v73; // edi
  int v74; // edi
  bool v75; // zf
  int v76; // edi
  unsigned int v77; // eax
  unsigned int v78; // eax
  bool v79; // zf
  unsigned int v80; // eax
  unsigned int v81; // eax
  unsigned int v82; // eax
  unsigned int v83; // eax
  unsigned int v84; // eax
  unsigned int v85; // edx
  int v86; // edi
  int v87; // edi
  int v88; // edi
  int v89; // edi
  D3DXEffects::Compiler::CData *v90; // rdi
  struct D3DXEffects::Compiler::CData **v91; // r8
  struct D3DXEffects::Compiler::CData **v92; // r8
  struct D3DXEffects::Compiler::CData *v93; // rsi
  unsigned int *v94; // rsi
  __int64 v95; // rdx
  struct D3DXEffects::Compiler::CData **v96; // r8
  unsigned __int8 *Block; // [rsp+58h] [rbp-59h]
  unsigned __int8 v98[4]; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int8 v99[4]; // [rsp+64h] [rbp-4Dh] BYREF
  unsigned __int8 v100[4]; // [rsp+68h] [rbp-49h] BYREF
  unsigned int v101; // [rsp+6Ch] [rbp-45h] BYREF
  unsigned int v102; // [rsp+70h] [rbp-41h]
  struct D3DXEffects::Compiler::CData *v103; // [rsp+78h] [rbp-39h] BYREF
  struct D3DXEffects::Compiler::CData *v104; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int8 v105[4]; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int8 v106[4]; // [rsp+8Ch] [rbp-25h] BYREF
  int v107; // [rsp+90h] [rbp-21h]
  unsigned __int8 v108[4]; // [rsp+94h] [rbp-1Dh] BYREF
  unsigned __int8 v109[8]; // [rsp+98h] [rbp-19h] BYREF
  __int64 v110; // [rsp+A0h] [rbp-11h]
  D3DXEffects::Compiler::CAssignment *v111; // [rsp+A8h] [rbp-9h]
  __int64 v112; // [rsp+B0h] [rbp-1h]
  struct D3DXEffects::Compiler::CAssignmentInfo *v114; // [rsp+100h] [rbp+4Fh] BYREF

  v114 = a2;
  v9 = *(unsigned int *)a2;
  v10 = *((_QWORD *)a2 + 6);
  v11 = 0;
  v103 = 0;
  v104 = 0;
  Block = 0;
  v14 = a2;
  *(_DWORD *)v98 = 0;
  v15 = this;
  v102 = v9;
  while ( v10 )
  {
    if ( (_DWORD)v9 == *(_DWORD *)v10 && (a9 != -1 || *((_DWORD *)a2 + 1) == *(_DWORD *)(v10 + 4)) )
      goto LABEL_152;
    v10 = *(_QWORD *)(v10 + 48);
  }
  v16 = *((_QWORD *)a2 + 1);
  v17 = *((unsigned int *)a2 + 9);
  v18 = *((_DWORD *)a2 + 4);
  v107 = 0;
  v19 = 2;
  v20 = *(_DWORD *)(v16 + 8);
  *(_DWORD *)v109 = *((_DWORD *)a2 + 1);
  *(_DWORD *)v105 = *((_DWORD *)a2 + 5);
  *(_DWORD *)v106 = *((_DWORD *)a2 + 6);
  v21 = *((_DWORD *)a2 + 7);
  v22 = (const struct D3DX9MEMORY::CD3DXNEW *)&g_lvGeneral;
  *(_DWORD *)v108 = v21;
  *(_DWORD *)v99 = v9;
  *(_DWORD *)v100 = v18;
  v101 = v17;
  v110 = v16;
  v23 = v20 - 1;
  if ( v23 )
  {
    if ( v23 != 12 )
    {
      D3DXShader::CTErrors::Error(
        (D3DXEffects::Compiler::CEffectCompiler *)((char *)v15 + 56),
        *((struct D3DXShader::D3DXTOKEN **)v14 + 5),
        0,
        "ID3DXEffectCompiler: State '%s' was assigned an unsupported value",
        *((_QWORD *)&g_lvGeneral + 5 * v9));
LABEL_10:
      v11 = -2147467259;
      goto LABEL_11;
    }
    if ( v18 > 15925248 )
      goto LABEL_23;
    if ( v18 != 15925248 )
    {
      if ( v18 > 11 )
      {
        if ( v18 == 12 || v18 == 13 || v18 == 14 )
          goto LABEL_32;
        if ( (unsigned int)(v18 - 15) > 1 )
          goto LABEL_23;
        ++*((_DWORD *)v15 + 370);
      }
      else
      {
        if ( v18 == 11 )
          goto LABEL_32;
        if ( v18 != 5 && v18 != 6 && v18 != 7 && v18 != 8 && v18 != 9 )
        {
          if ( v18 != 10 )
          {
LABEL_23:
            v26 = v17;
            v24 = (unsigned __int8 *)operator new(v17, (const struct D3DX9MEMORY::CD3DXNEW *)&g_lvGeneral);
            Block = v24;
            if ( !v24 )
            {
LABEL_24:
              v11 = -2147024882;
              goto LABEL_12;
            }
            memset_0(v24, 0, v26);
            v28 = Block;
            v27 = v26;
            goto LABEL_34;
          }
LABEL_32:
          v27 = 4;
          v28 = v98;
LABEL_34:
          v11 = D3DXEffects::Compiler::CData::AddData(a8, v28, v27, &v103);
          if ( v11 < 0 )
            goto LABEL_11;
          goto LABEL_35;
        }
      }
      v11 = D3DXEffects::Compiler::CData::AddData(a8, (unsigned __int8 *)v15 + 1476, 4u, &v103);
      if ( v11 < 0 )
        goto LABEL_11;
      ++*((_DWORD *)v15 + 369);
      LODWORD(v9) = v102;
    }
LABEL_35:
    v29 = operator new(0x38u, v22);
    if ( v29 )
    {
      v29[5] = 0;
      v29[6] = 0;
      v29[4] = 0;
      *((_DWORD *)v29 + 1) = a3;
      v30 = (D3DXEffects::Compiler::CAssignment *)v29;
      *((_DWORD *)v29 + 2) = a4;
      v31 = a8;
      *(_DWORD *)v29 = v9;
      *((_DWORD *)v29 + 3) = a5;
      *((_DWORD *)v29 + 4) = *a6;
      v29[3] = v110;
      goto LABEL_161;
    }
    goto LABEL_10;
  }
  v32 = *(_QWORD *)(v16 + 16);
  if ( !v32 )
  {
    v11 = -2147467259;
    v24 = 0;
    goto LABEL_12;
  }
  v33 = *(_DWORD *)(v32 + 8);
  v30 = 0;
  v111 = 0;
  if ( v33 == 3 )
  {
    if ( *(_DWORD *)(v32 + 32) == 5 || *(_DWORD *)(v32 + 32) == 6 || (unsigned int)(*(_DWORD *)(v32 + 32) - 7) < 2 )
    {
      v31 = a8;
      *(float *)&v114 = *(double *)(v32 + 40);
      v11 = D3DXEffects::Compiler::CData::AddData(a8, (unsigned __int8 *)&v114, 4u, &v103);
      if ( v11 < 0 )
      {
        v24 = 0;
        goto LABEL_12;
      }
      goto LABEL_161;
    }
    v63 = 0;
    v101 = 0;
    v64 = 0;
    while ( v16 )
    {
      if ( *(_DWORD *)(v16 + 8) != 1 )
        goto LABEL_10;
      v65 = *(_QWORD *)(v16 + 16);
      if ( !v65 || *(_DWORD *)(v65 + 8) != 3 )
        goto LABEL_10;
      if ( *(_DWORD *)(v65 + 32) == 2 || *(_DWORD *)(v65 + 32) == 3 || *(_DWORD *)(v65 + 32) == 4 )
      {
        v63 |= *(_DWORD *)(v65 + 40);
      }
      else
      {
        if ( *(_DWORD *)(v65 + 32) != 9 )
        {
          D3DXShader::CTErrors::Error(
            (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
            *((struct D3DXShader::D3DXTOKEN **)v14 + 5),
            0,
            "ID3DXEffectCompiler: State '%s' accepts only dwords and ids",
            *((_QWORD *)&g_lvGeneral + 5 * v102));
          goto LABEL_10;
        }
        if ( !*(_QWORD *)(v65 + 40) )
          goto LABEL_10;
        v66 = (_QWORD *)*((_QWORD *)&g_lvGeneral + 5 * v102 + 4);
        if ( !v66 )
          goto LABEL_143;
        v67 = 0;
        if ( *v66 )
        {
          do
          {
            if ( !_stricmp((const char *)v66[2 * v67], *(const char **)(v65 + 40)) )
              break;
            v66 = (_QWORD *)*((_QWORD *)&g_lvGeneral + 5 * v102 + 4);
            ++v67;
          }
          while ( v66[2 * v67] );
          v14 = v114;
          v16 = v110;
        }
        v68 = *((_QWORD *)&g_lvGeneral + 5 * v102 + 4);
        v69 = 16LL * v67;
        if ( !*(_QWORD *)(v69 + v68) )
        {
LABEL_143:
          D3DXShader::CTErrors::Error(
            (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
            *((struct D3DXShader::D3DXTOKEN **)v14 + 5),
            0,
            "ID3DXEffectCompiler: State '%s' does not accept '%s' as a value",
            *((const char **)&g_lvGeneral + 5 * v102),
            *(const char **)(v65 + 40));
          goto LABEL_10;
        }
        v63 |= *(_DWORD *)(v69 + v68 + 8);
      }
      v16 = *(_QWORD *)(v16 + 24);
      v64 = v63;
      v110 = v16;
      v101 = v63;
    }
    LODWORD(v9) = v102;
    v70 = *((_DWORD *)&g_lvGeneral + 10 * v102 + 7);
    switch ( v70 )
    {
      case 83886080:
        if ( !v64 )
        {
          D3DXShader::CTErrors::Error(
            (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
            *((struct D3DXShader::D3DXTOKEN **)v14 + 5),
            0,
            "ID3DXEffectCompiler: FVFs must not evaluate to NULL");
          goto LABEL_10;
        }
        break;
      case 150994944:
LABEL_169:
        if ( v64 )
        {
          D3DXShader::CTErrors::Error(
            (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
            *((struct D3DXShader::D3DXTOKEN **)v14 + 5),
            0,
            "ID3DXEffectCompiler: Dword expressions for state '%s' must be evaluate to NULL",
            *((_QWORD *)&g_lvGeneral + 5 * v102));
          goto LABEL_10;
        }
        break;
      case 167772160:
        if ( v64 )
        {
          LODWORD(v9) = 0;
          *(_DWORD *)v99 = 0;
          if ( g_lvGeneral )
          {
            v71 = 0;
            do
            {
              if ( *((_DWORD *)&g_lvGeneral + 10 * v71 + 7) == 83886080 )
                break;
              *(_DWORD *)v99 = ++v71;
              LODWORD(v9) = v71;
            }
            while ( *((_QWORD *)&g_lvGeneral + 5 * v71) );
          }
          v107 = 1;
        }
        break;
      case 184549376:
        goto LABEL_169;
      case 234881024:
      case 251658240:
LABEL_152:
        v24 = 0;
        goto LABEL_12;
      default:
        break;
    }
    v31 = a8;
    v11 = D3DXEffects::Compiler::CData::AddData(a8, (unsigned __int8 *)&v101, 4u, &v103);
    if ( v11 < 0 )
      goto LABEL_11;
    v15 = this;
    v30 = v111;
LABEL_161:
    v19 = 2;
    goto LABEL_162;
  }
  if ( v33 != 13 )
  {
    v31 = a8;
LABEL_162:
    if ( v18 > 9 )
    {
      v86 = v18 - 10;
      if ( !v86 )
        goto LABEL_206;
      v87 = v86 - 1;
      if ( !v87 )
        goto LABEL_206;
      v88 = v87 - 1;
      if ( !v88 )
        goto LABEL_206;
      v76 = v88 - 1;
      v75 = v76 == 0;
LABEL_202:
      if ( !v75 )
      {
        v89 = v76 - 1;
        if ( v89 )
        {
          if ( (unsigned int)(v89 - 1) >= 2 )
          {
            D3DXShader::CTErrors::Error(
              (D3DXEffects::Compiler::CEffectCompiler *)((char *)v15 + 56),
              *((struct D3DXShader::D3DXTOKEN **)v14 + 5),
              0,
              "ID3DXEffectCompiler: Internal error initializing assignment - missing type case");
            v11 = -2147467259;
            goto LABEL_232;
          }
        }
      }
LABEL_206:
      LODWORD(v114) = 4;
      v11 = D3DXEffects::Compiler::CData::AddData(v31, v100, 4u, &v104);
      if ( v11 < 0 )
        goto LABEL_232;
      v11 = D3DXEffects::Compiler::CData::AddData(v31, (unsigned __int8 *)&v114, 4u, 0);
      if ( v11 < 0 )
        goto LABEL_232;
      v11 = D3DXEffects::Compiler::CData::AddData(v31, v98, 4u, 0);
      if ( v11 < 0 )
        goto LABEL_232;
      v11 = D3DXEffects::Compiler::CData::AddData(v31, v98, 4u, 0);
      if ( v11 < 0 )
        goto LABEL_232;
      v11 = D3DXEffects::Compiler::CData::AddData(v31, v98, 4u, 0);
      if ( v11 < 0 )
        goto LABEL_232;
      goto LABEL_211;
    }
    if ( v18 == 9 )
      goto LABEL_206;
    if ( !v18 )
    {
      if ( (int)D3DXEffects::Compiler::CEffectCompiler::InitializeType(
                  v15,
                  *(struct D3DXShader::CNode **)(*((_QWORD *)v14 + 1) + 32LL),
                  0,
                  0,
                  0,
                  v31,
                  0,
                  &v104,
                  0) < 0 )
      {
        D3DXShader::CTErrors::Error(
          (D3DXEffects::Compiler::CEffectCompiler *)((char *)v15 + 56),
          *((struct D3DXShader::D3DXTOKEN **)v14 + 5),
          0,
          "ID3DXEffectCompiler: Error initializing assignment type");
        goto LABEL_232;
      }
LABEL_211:
      v90 = a7;
      v11 = D3DXEffects::Compiler::CData::AddData(a7, v99, 4u, 0);
      if ( v11 >= 0 )
      {
        v11 = D3DXEffects::Compiler::CData::AddData(v90, v109, 4u, 0);
        if ( v11 >= 0 )
        {
          v11 = D3DXEffects::Compiler::CData::AddReference(v90, v104, v91);
          if ( v11 >= 0 )
          {
            v93 = v103;
            v11 = D3DXEffects::Compiler::CData::AddReference(v90, v103, v92);
            if ( v11 >= 0 )
            {
              if ( v30 )
              {
                *((_QWORD *)v30 + 6) = v104;
                *((_QWORD *)v30 + 5) = v93;
                *((_QWORD *)v30 + 4) = *((_QWORD *)v15 + 192);
                *((_QWORD *)v15 + 192) = v30;
                v30 = 0;
              }
              v94 = a6;
              ++*a6;
              if ( !v107 )
                goto LABEL_11;
              *(_DWORD *)v100 = 16;
              LODWORD(v114) = 4;
              v11 = D3DXEffects::Compiler::CData::AddData(v31, v100, 4u, &v104);
              if ( v11 >= 0 )
              {
                v11 = D3DXEffects::Compiler::CData::AddData(v31, (unsigned __int8 *)&v114, 4u, 0);
                if ( v11 >= 0 )
                {
                  v11 = D3DXEffects::Compiler::CData::AddData(v31, v98, 4u, 0);
                  if ( v11 >= 0 )
                  {
                    v11 = D3DXEffects::Compiler::CData::AddData(v31, v98, 4u, 0);
                    if ( v11 >= 0 )
                    {
                      v11 = D3DXEffects::Compiler::CData::AddData(v31, v98, 4u, 0);
                      if ( v11 >= 0 )
                      {
                        *(_DWORD *)v99 = 0;
                        if ( g_lvGeneral )
                        {
                          v95 = 0;
                          do
                          {
                            if ( *((_DWORD *)&g_lvGeneral + 10 * v95 + 7) == 167772160 )
                              break;
                            v95 = (unsigned int)(v95 + 1);
                            *(_DWORD *)v99 = v95;
                          }
                          while ( *((_QWORD *)&g_lvGeneral + 5 * v95) );
                        }
                        v11 = D3DXEffects::Compiler::CData::AddData(v90, v99, 4u, 0);
                        if ( v11 >= 0 )
                        {
                          v11 = D3DXEffects::Compiler::CData::AddData(v90, v98, 4u, 0);
                          if ( v11 >= 0 )
                          {
                            v11 = D3DXEffects::Compiler::CData::AddReference(v90, v104, v96);
                            if ( v11 >= 0 )
                            {
                              v11 = D3DXEffects::Compiler::CData::AddData(v90, v98, 4u, 0);
                              if ( v11 >= 0 )
                                ++*v94;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_232:
      if ( v30 )
        D3DXEffects::Compiler::CAssignment::`scalar deleting destructor'(v30, v85);
      goto LABEL_11;
    }
    v72 = v18 - 1;
    if ( v72 )
    {
      v73 = v72 - 1;
      if ( v73 )
      {
        v74 = v73 - 1;
        if ( v74 )
        {
          v76 = v74 - 2;
          v75 = v76 == 0;
          goto LABEL_202;
        }
      }
    }
    v77 = *((_DWORD *)&g_lvGeneral + 10 * (unsigned int)v9 + 7);
    if ( v77 > 0xD000000 )
    {
      v80 = v77 - 218103809;
      v79 = v80 == 0;
    }
    else
    {
      if ( v77 == 218103808 )
        goto LABEL_186;
      v78 = v77 - 201326592;
      if ( !v78 )
        goto LABEL_186;
      v80 = v78 - 1;
      v79 = v80 == 0;
    }
    if ( !v79 )
    {
      v81 = v80 - 1;
      if ( v81 )
      {
        v82 = v81 - 1;
        if ( v82 )
        {
          v83 = v82 - 1;
          if ( v83 )
          {
            v84 = v83 - 65532;
            if ( v84 )
            {
              if ( v84 != 0x10000 )
              {
LABEL_187:
                LODWORD(v114) = v19;
                v11 = D3DXEffects::Compiler::CData::AddData(v31, v100, 4u, &v104);
                if ( v11 < 0 )
                  goto LABEL_232;
                v11 = D3DXEffects::Compiler::CData::AddData(v31, (unsigned __int8 *)&v114, 4u, 0);
                if ( v11 < 0 )
                  goto LABEL_232;
                v11 = D3DXEffects::Compiler::CData::AddData(v31, v98, 4u, 0);
                if ( v11 < 0 )
                  goto LABEL_232;
                v11 = D3DXEffects::Compiler::CData::AddData(v31, v98, 4u, 0);
                if ( v11 < 0 )
                  goto LABEL_232;
                v11 = D3DXEffects::Compiler::CData::AddData(v31, v108, 4u, 0);
                if ( v11 < 0 )
                  goto LABEL_232;
                v11 = D3DXEffects::Compiler::CData::AddData(v31, v105, 4u, 0);
                if ( v11 < 0 )
                  goto LABEL_232;
                v11 = D3DXEffects::Compiler::CData::AddData(v31, v106, 4u, 0);
                if ( v11 < 0 )
                  goto LABEL_232;
                goto LABEL_211;
              }
            }
          }
        }
      }
    }
LABEL_186:
    v19 = 3;
    goto LABEL_187;
  }
  v34 = v17;
  v24 = (unsigned __int8 *)operator new(v17, (const struct D3DX9MEMORY::CD3DXNEW *)v32);
  Block = v24;
  if ( !v24 )
    goto LABEL_24;
  memset_0(v24, 0, v34);
  v35 = 0;
  v36 = *((_QWORD *)v14 + 1);
  while ( v36 )
  {
    if ( *(_DWORD *)(v36 + 8) != 1 )
      goto LABEL_10;
    v37 = *(_QWORD *)(v36 + 16);
    if ( !v37 || *(_DWORD *)(v37 + 8) != 13 )
      goto LABEL_10;
    v38 = 0;
    if ( *(_DWORD *)(v37 + 48) == 5 )
    {
      v39 = *(_QWORD *)(v37 + 56);
      if ( v39 )
      {
        if ( *(_DWORD *)(v39 + 8) == 13 )
        {
          v38 = 1;
          v37 = *(_QWORD *)(v37 + 56);
          if ( !*(_DWORD *)(v39 + 48) )
          {
            do
            {
              v40 = *(_QWORD *)(v37 + 56);
              if ( !v40 )
                break;
              if ( *(_DWORD *)(v40 + 8) != 1 )
                break;
              v41 = *(_QWORD *)(v40 + 16);
              if ( !v41 )
                break;
              if ( *(_DWORD *)(v41 + 8) != 13 )
                break;
              v37 = *(_QWORD *)(v40 + 16);
            }
            while ( !*(_DWORD *)(v41 + 48) );
          }
        }
      }
    }
    if ( *(_DWORD *)(v37 + 48)
      || (v42 = *(_QWORD *)(v37 + 56)) == 0
      || *(_DWORD *)(v42 + 8) != 1
      || (v43 = *(double **)(v42 + 16)) == 0
      || *((_DWORD *)v43 + 2) != 14
      || (v44 = *((_DWORD *)v43 + 8), v44 == 6) )
    {
      v54 = "ID3DXEffectCompiler: Initializer list elements cannot be complex expressions or variables";
      goto LABEL_94;
    }
    switch ( *((_DWORD *)&g_lvGeneral + 10 * v9 + 2) )
    {
      case 1:
        if ( v44 && (v52 = v44 - 1) != 0 && (v53 = v52 - 1) != 0 )
        {
          if ( v53 != 1 )
          {
LABEL_95:
            v54 = "ID3DXEffectCompiler: Unexpected error";
            goto LABEL_94;
          }
          *(_DWORD *)&Block[4 * v35] = v43[5] != 0.0;
        }
        else
        {
          *(_DWORD *)&Block[4 * v35] = *((_DWORD *)v43 + 10) != 0;
        }
        break;
      case 2:
        if ( v44 )
        {
          v49 = v44 - 1;
          if ( v49 && (v50 = v49 - 1) != 0 )
          {
            if ( v50 != 1 )
              goto LABEL_95;
            v51 = (int)v43[5];
          }
          else
          {
            v51 = *((_DWORD *)v43 + 10);
          }
        }
        else
        {
          v51 = *((_DWORD *)v43 + 10) != 0;
        }
        *(_DWORD *)&Block[4 * v35] = v51;
        if ( v38 )
          *(_DWORD *)&Block[4 * v35] = -v51;
        break;
      case 3:
      case 0xF20000:
        if ( v44 )
        {
          v45 = v44 - 1;
          if ( v45 )
          {
            v46 = v45 - 1;
            if ( v46 )
            {
              if ( v46 != 1 )
                goto LABEL_95;
              v47 = v43[5];
            }
            else
            {
              v47 = (float)*((int *)v43 + 10);
            }
            goto LABEL_75;
          }
          v48 = _mm_cvtsi32_si128(*((_DWORD *)v43 + 10));
        }
        else
        {
          v48 = _mm_cvtsi32_si128(*((_DWORD *)v43 + 10) != 0);
        }
        LODWORD(v47) = _mm_cvtepi32_ps(v48).m128_u32[0];
LABEL_75:
        *(float *)&Block[4 * v35] = v47;
        if ( v38 )
          *(_DWORD *)&Block[4 * v35] = LODWORD(v47) ^ _xmm;
        break;
      default:
        v54 = "ID3DXEffectCompiler: Error in type checking";
LABEL_94:
        D3DXShader::CTErrors::Error(
          (D3DXEffects::Compiler::CEffectCompiler *)((char *)v15 + 56),
          *((struct D3DXShader::D3DXTOKEN **)v14 + 5),
          0,
          v54);
        goto LABEL_10;
    }
    v36 = *(_QWORD *)(v36 + 24);
    ++v35;
  }
  if ( *((_DWORD *)&g_lvGeneral + 10 * v9 + 2) == 15859712 )
  {
    v55 = *((_QWORD *)Block + 1);
    v111 = *(D3DXEffects::Compiler::CAssignment **)Block;
    v112 = v55;
    v56 = 255;
    if ( *(float *)&v111 < 1.0 )
    {
      if ( *(float *)&v111 > 0.0 )
        v57 = (int)(float)((float)(*(float *)&v111 * 255.0) + 0.5);
      else
        v57 = 0;
    }
    else
    {
      v57 = 255;
    }
    if ( *((float *)&v111 + 1) < 1.0 )
    {
      if ( *((float *)&v111 + 1) > 0.0 )
        v58 = (int)(float)((float)(*((float *)&v111 + 1) * 255.0) + 0.5);
      else
        v58 = 0;
    }
    else
    {
      v58 = 255;
    }
    if ( *(float *)&v55 < 1.0 )
    {
      if ( *(float *)&v55 > 0.0 )
        v59 = (int)(float)((float)(*(float *)&v55 * 255.0) + 0.5);
      else
        v59 = 0;
    }
    else
    {
      v59 = 255;
    }
    if ( *((float *)&v112 + 1) < 1.0 )
    {
      if ( *((float *)&v112 + 1) > 0.0 )
        v56 = (int)(float)((float)(*((float *)&v112 + 1) * 255.0) + 0.5);
      else
        v56 = 0;
    }
    v18 = 2;
    *(_DWORD *)v100 = 2;
    *(_DWORD *)v105 = 1;
    v60 = (v58 | ((v57 | (v56 << 8)) << 8)) << 8;
    v61 = 4;
    *(_DWORD *)v106 = 1;
    LODWORD(v114) = v59 | v60;
    v62 = (unsigned __int8 *)&v114;
  }
  else
  {
    v61 = v101;
    v62 = Block;
  }
  v11 = D3DXEffects::Compiler::CData::AddData(a8, v62, v61, &v103);
  if ( v11 >= 0 )
  {
    operator delete(Block);
    Block = 0;
    v31 = a8;
    goto LABEL_161;
  }
LABEL_11:
  v24 = Block;
LABEL_12:
  operator delete(v24);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140090d38  mov     rax, rsp
0x140090d3b  mov     [rax+18h], rbx
0x140090d3f  mov     [rax+10h], rdx
0x140090d43  mov     [rax+8], rcx
0x140090d47  push    rbp
0x140090d48  push    rsi
0x140090d49  push    rdi
0x140090d4a  push    r12
0x140090d4c  push    r13
0x140090d4e  push    r14
0x140090d50  push    r15
0x140090d52  lea     rbp, [rax-3Fh]
0x140090d56  sub     rsp, 0B0h
0x140090d5d  mov     esi, [rdx]
0x140090d5f  xor     eax, eax
0x140090d61  mov     r10, [rdx+30h]
0x140090d65  mov     ebx, eax
0x140090d67  mov     [rbp+37h+var_70], rax
0x140090d6b  mov     r14d, r9d
0x140090d6e  mov     [rbp+37h+var_68], rax
0x140090d72  mov     r15d, r8d
0x140090d75  mov     [rbp+37h+Block], rax
0x140090d79  mov     r13, rdx
0x140090d7c  mov     dword ptr [rbp+37h+var_88], eax
0x140090d7f  mov     r12, rcx
0x140090d82  mov     [rbp+37h+var_78], esi
0x140090d85  test    r10, r10
0x140090d88  jz      short loc_140090DB1
0x140090d8a  cmp     esi, [r10]
0x140090d8d  jnz     short loc_140090DAB
0x140090d8f  cmp     [rbp+37h+arg_40], 0FFFFFFFFh
0x140090d96  jnz     loc_140091545
0x140090d9c  mov     eax, [r10+4]
0x140090da0  cmp     [rdx+4], eax
0x140090da3  jz      loc_140091545
0x140090da9  xor     eax, eax
0x140090dab  mov     r10, [r10+30h]
0x140090daf  jmp     short loc_140090D85
0x140090db1  mov     r9, [rdx+8]
0x140090db5  mov     r11d, 4
0x140090dbb  mov     r8d, [rdx+24h]
0x140090dbf  mov     edi, [rdx+10h]
0x140090dc2  mov     [rbp+37h+var_58], eax
0x140090dc5  mov     eax, [rdx+4]
0x140090dc8  lea     r10d, [r11-2]
0x140090dcc  mov     ecx, [r9+8]
0x140090dd0  mov     dword ptr [rbp+37h+var_50], eax
0x140090dd3  mov     eax, [rdx+14h]
0x140090dd6  mov     dword ptr [rbp+37h+var_60], eax
0x140090dd9  mov     eax, [rdx+18h]
0x140090ddc  mov     dword ptr [rbp+37h+var_5C], eax
0x140090ddf  mov     eax, [rdx+1Ch]
0x140090de2  lea     rdx, ?g_lvGeneral@@3QBULValue@@B; struct D3DX9MEMORY::CD3DXNEW *
0x140090de9  mov     dword ptr [rbp+37h+var_54], eax
0x140090dec  mov     dword ptr [rbp+37h+var_84], esi
0x140090def  mov     dword ptr [rbp+37h+var_80], edi
0x140090df2  mov     [rbp+37h+var_7C], r8d
0x140090df6  mov     [rbp+37h+var_48], r9
0x140090dfa  sub     ecx, 1
0x140090dfd  jz      loc_140090F8E
0x140090e03  cmp     ecx, 0Ch
0x140090e06  jz      short loc_140090E5B
0x140090e08  lea     rax, [rsi+rsi*4]
0x140090e0c  lea     rcx, [r12+38h]; this
0x140090e11  lea     r9, aId3dxeffectcom_3; "ID3DXEffectCompiler: State '%s' was ass"...
0x140090e18  mov     rax, [rdx+rax*8]
0x140090e1c  mov     rdx, [r13+28h]; struct D3DXShader::D3DXTOKEN *
0x140090e20  xor     r8d, r8d; unsigned int
0x140090e23  mov     qword ptr [rsp+0E0h+var_C0], rax
0x140090e28  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x140090e2d  mov     ebx, 80004005h
0x140090e32  mov     rax, [rbp+37h+Block]
0x140090e36  mov     rcx, rax; Block
0x140090e39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140090e3e  mov     eax, ebx
0x140090e40  mov     rbx, [rsp+0E0h+arg_10]
0x140090e48  add     rsp, 0B0h
0x140090e4f  pop     r15
0x140090e51  pop     r14
0x140090e53  pop     r13
0x140090e55  pop     r12
0x140090e57  pop     rdi
0x140090e58  pop     rsi
0x140090e59  pop     rbp
0x140090e5a  retn
0x140090e5b  mov     eax, 0F30000h
0x140090e60  cmp     edi, eax
0x140090e62  jg      short loc_140090E95
0x140090e64  jz      loc_140090F33
0x140090e6a  cmp     edi, 0Bh
0x140090e6d  jg      short loc_140090EB0
0x140090e6f  jz      loc_140090EFF
0x140090e75  mov     ecx, edi
0x140090e77  sub     ecx, 5
0x140090e7a  jz      short loc_140090ED3
0x140090e7c  sub     ecx, 1
0x140090e7f  jz      short loc_140090ED3
0x140090e81  sub     ecx, 1
0x140090e84  jz      short loc_140090ED3
0x140090e86  sub     ecx, 1
0x140090e89  jz      short loc_140090ED3
0x140090e8b  sub     ecx, 1
0x140090e8e  jz      short loc_140090ED3
0x140090e90  cmp     ecx, 1
0x140090e93  jz      short loc_140090EFF
0x140090e95  mov     rcx, r8; unsigned __int64
0x140090e98  mov     rbx, r8
0x140090e9b  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140090ea0  mov     [rbp+37h+Block], rax
0x140090ea4  test    rax, rax
0x140090ea7  jnz     short loc_140090F08
0x140090ea9  mov     ebx, 8007000Eh
0x140090eae  jmp     short loc_140090E36
0x140090eb0  mov     ecx, edi
0x140090eb2  sub     ecx, 0Ch
0x140090eb5  jz      short loc_140090EFF
0x140090eb7  sub     ecx, 1
0x140090eba  jz      short loc_140090EFF
0x140090ebc  sub     ecx, 1
0x140090ebf  jz      short loc_140090EFF
0x140090ec1  sub     ecx, 1
0x140090ec4  jz      short loc_140090ECB
0x140090ec6  cmp     ecx, 1
0x140090ec9  jnz     short loc_140090E95
0x140090ecb  inc     dword ptr [r12+5C8h]
0x140090ed3  mov     rcx, [rbp+37h+arg_38]; this
0x140090ed7  lea     rsi, [r12+5C4h]
0x140090edf  mov     rdx, rsi; unsigned __int8 *
0x140090ee2  lea     r9, [rbp+37h+var_70]; struct D3DXEffects::Compiler::CData **
0x140090ee6  mov     r8d, r11d; unsigned int
0x140090ee9  call    ?AddData@CData@Compiler@D3DXEffects@@QEAAJPEAEKPEAPEAV123@@Z; D3DXEffects::Compiler::CData::AddData(uchar *,ulong,D3DXEffects::Compiler::CData * *)
0x140090eee  mov     ebx, eax
0x140090ef0  test    eax, eax
0x140090ef2  js      loc_140090E32
0x140090ef8  inc     dword ptr [rsi]
0x140090efa  mov     esi, [rbp+37h+var_78]
0x140090efd  jmp     short loc_140090F33
0x140090eff  mov     r8d, r11d
0x140090f02  lea     rdx, [rbp+37h+var_88]
0x140090f06  jmp     short loc_140090F1C
0x140090f08  mov     r8, rbx; Size
0x140090f0b  xor     edx, edx; Val
0x140090f0d  mov     rcx, rax; void *
0x140090f10  call    memset_0
0x140090f15  mov     rdx, [rbp+37h+Block]; unsigned __int8 *
0x140090f19  mov     r8d, ebx; unsigned int
0x140090f1c  mov     rcx, [rbp+37h+arg_38]; this
0x140090f20  lea     r9, [rbp+37h+var_70]; struct D3DXEffects::Compiler::CData **
0x140090f24  call    ?AddData@CData@Compiler@D3DXEffects@@QEAAJPEAEKPEAPEAV123@@Z; D3DXEffects::Compiler::CData::AddData(uchar *,ulong,D3DXEffects::Compiler::CData * *)
0x140090f29  mov     ebx, eax
0x140090f2b  test    eax, eax
0x140090f2d  js      loc_140090E32
0x140090f33  mov     ecx, 38h ; '8'; unsigned __int64
0x140090f38  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140090f3d  mov     rcx, rax
0x140090f40  test    rax, rax
0x140090f43  jz      loc_140090E2D
0x140090f49  mov     qword ptr [rax+28h], 0
0x140090f51  mov     qword ptr [rax+30h], 0
0x140090f59  mov     qword ptr [rax+20h], 0
0x140090f61  mov     [rax+4], r15d
0x140090f65  mov     r15, rcx
0x140090f68  mov     [rax+8], r14d
0x140090f6c  mov     r14, [rbp+37h+arg_38]
0x140090f70  mov     [rax], esi
0x140090f72  mov     eax, [rbp+37h+arg_20]
0x140090f75  mov     [rcx+0Ch], eax
0x140090f78  mov     rax, [rbp+37h+arg_28]
0x140090f7c  mov     eax, [rax]
0x140090f7e  mov     [rcx+10h], eax
0x140090f81  mov     rax, [rbp+37h+var_48]
0x140090f85  mov     [rcx+18h], rax
0x140090f89  jmp     loc_1400915B6
0x140090f8e  mov     rdx, [r9+10h]; struct D3DX9MEMORY::CD3DXNEW *
0x140090f92  xor     r14d, r14d
0x140090f95  test    rdx, rdx
0x140090f98  jnz     short loc_140090FA7
0x140090f9a  mov     ebx, 80004005h
0x140090f9f  mov     eax, r14d
0x140090fa2  jmp     loc_140090E36
0x140090fa7  mov     eax, [rdx+8]
0x140090faa  mov     r15, r14
0x140090fad  mov     [rbp+37h+var_40], r14
0x140090fb1  cmp     eax, 3
0x140090fb4  jz      loc_14009136E
0x140090fba  cmp     eax, 0Dh
0x140090fbd  jnz     loc_140091665
0x140090fc3  mov     rcx, r8; unsigned __int64
0x140090fc6  mov     rbx, r8
0x140090fc9  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140090fce  mov     [rbp+37h+Block], rax
0x140090fd2  test    rax, rax
0x140090fd5  jz      loc_140090EA9
0x140090fdb  mov     r8, rbx; Size
0x140090fde  xor     edx, edx; Val
0x140090fe0  mov     rcx, rax; void *
0x140090fe3  call    memset_0
0x140090fe8  movss   xmm2, dword ptr cs:__xmm@80000000800000008000000080000000
0x140090ff0  mov     r10d, r14d
0x140090ff3  mov     rbx, [r13+8]
0x140090ff7  xorps   xmm1, xmm1
0x140090ffa  mov     r9d, 1
0x140091000  test    rbx, rbx
0x140091003  jz      loc_140091231
0x140091009  cmp     [rbx+8], r9d
0x14009100d  jnz     loc_140090E2D
0x140091013  mov     rax, [rbx+10h]
0x140091017  test    rax, rax
0x14009101a  jz      loc_140090E2D
0x140091020  cmp     dword ptr [rax+8], 0Dh
0x140091024  jnz     loc_140090E2D
0x14009102a  cmp     dword ptr [rax+30h], 5
0x14009102e  mov     r11d, r14d
0x140091031  jnz     short loc_140091075
0x140091033  mov     rcx, [rax+38h]
0x140091037  test    rcx, rcx
0x14009103a  jz      short loc_140091075
0x14009103c  cmp     dword ptr [rcx+8], 0Dh
0x140091040  jnz     short loc_140091075
0x140091042  mov     r11d, r9d
0x140091045  mov     rax, rcx
0x140091048  cmp     [rcx+30h], r14d
0x14009104c  jnz     short loc_140091075
0x14009104e  mov     rcx, [rax+38h]
0x140091052  test    rcx, rcx
0x140091055  jz      short loc_140091075
0x140091057  cmp     [rcx+8], r9d
0x14009105b  jnz     short loc_140091075
0x14009105d  mov     rdx, [rcx+10h]
0x140091061  test    rdx, rdx
0x140091064  jz      short loc_140091075
0x140091066  cmp     dword ptr [rdx+8], 0Dh
0x14009106a  jnz     short loc_140091075
0x14009106c  mov     rax, rdx
0x14009106f  cmp     [rdx+30h], r14d
0x140091073  jz      short loc_14009104E
0x140091075  cmp     [rax+30h], r14d
0x140091079  jnz     loc_140091228
0x14009107f  mov     r8, [rax+38h]
0x140091083  test    r8, r8
0x140091086  jz      loc_140091228
0x14009108c  cmp     [r8+8], r9d
0x140091090  jnz     loc_140091228
0x140091096  mov     r8, [r8+10h]
0x14009109a  test    r8, r8
0x14009109d  jz      loc_140091228
0x1400910a3  cmp     dword ptr [r8+8], 0Eh
0x1400910a8  jnz     loc_140091228
0x1400910ae  mov     edx, [r8+20h]
0x1400910b2  cmp     edx, 6
0x1400910b5  jz      loc_140091228
0x1400910bb  lea     rcx, [rsi+rsi*4]
0x1400910bf  lea     r9, ?g_lvGeneral@@3QBULValue@@B; LValue const near * const g_lvGeneral
0x1400910c6  mov     r9d, [r9+rcx*8+8]
0x1400910cb  sub     r9d, 1
0x1400910cf  jz      loc_1400911AB
0x1400910d5  sub     r9d, 1
0x1400910d9  jz      loc_140091162
0x1400910df  sub     r9d, 1
0x1400910e3  jz      short loc_1400910F2
0x1400910e5  cmp     r9d, 0F1FFFDh
0x1400910ec  jnz     loc_140091202
0x1400910f2  test    edx, edx
0x1400910f4  jz      short loc_14009112B
0x1400910f6  sub     edx, 1
0x1400910f9  jz      short loc_140091123
0x1400910fb  sub     edx, 1
0x1400910fe  jz      short loc_140091115
0x140091100  cmp     edx, 1
0x140091103  jnz     loc_14009121F
0x140091109  movsd   xmm0, qword ptr [r8+28h]
0x14009110f  cvtpd2ps xmm0, xmm0
0x140091113  jmp     short loc_14009113C
0x140091115  mov     eax, [r8+28h]
0x140091119  xorps   xmm0, xmm0
0x14009111c  cvtsi2ss xmm0, rax
0x140091121  jmp     short loc_14009113C
0x140091123  movd    xmm0, dword ptr [r8+28h]
0x140091129  jmp     short loc_140091139
0x14009112b  cmp     [r8+28h], r14d
0x14009112f  mov     eax, r14d
0x140091132  setnz   al
0x140091135  movd    xmm0, eax
0x140091139  cvtdq2ps xmm0, xmm0
0x14009113c  mov     r8, [rbp+37h+Block]
0x140091140  mov     eax, r10d
0x140091143  mov     ecx, eax
0x140091145  movss   dword ptr [r8+rcx*4], xmm0
0x14009114b  test    r11d, r11d
0x14009114e  jz      loc_1400911F0
0x140091154  xorps   xmm0, xmm2
0x140091157  movss   dword ptr [r8+rcx*4], xmm0
0x14009115d  jmp     loc_1400911F0
0x140091162  test    edx, edx
0x140091164  jz      short loc_140091187
0x140091166  sub     edx, 1
0x140091169  jz      short loc_140091181
0x14009116b  sub     edx, 1
0x14009116e  jz      short loc_140091181
0x140091170  cmp     edx, 1
  ... truncated ...
```
