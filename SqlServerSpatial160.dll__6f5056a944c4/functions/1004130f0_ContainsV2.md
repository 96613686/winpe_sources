# ContainsV2

- ea: `0x1004130f0`
- end: `0x100413c76`
- name: `ContainsV2`
- size: `2950`
- prototype: `__int64 __fastcall(GeoBundle *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x100413050`

## callees

- `0x10040d0c0`
- `0x100410d70`
- `0x100411400`
- `0x100411cb0`
- `0x1004121e0`
- `0x1004130f0`
- `0x100421910`
- `0x100429370`
- `0x100429520`
- `0x100468a30`

## string_xrefs

- `0x1004139e7`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\SqlServerSpatial.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
__int64 __fastcall ContainsV2(GeoBundle *this, __int64 a2, bool *a3)
{
  _QWORD *v5; // rsi
  __int64 v6; // r13
  __int64 v7; // r12
  unsigned __int64 v8; // r15
  __int64 result; // rax
  int PointRelation; // r14d
  __int64 v11; // rdx
  _BYTE *v12; // rcx
  bool *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rcx
  double *v16; // rax
  bool v17; // al
  _QWORD *v18; // rax
  bool v19; // zf
  __int64 v20; // r8
  char v21; // cl
  int v22; // eax
  double v23; // xmm0_8
  unsigned __int64 v24; // rax
  double v25; // xmm0_8
  char v26; // r8
  unsigned __int64 v27; // r11
  char v28; // cl
  char v29; // cl
  __int64 v30; // rbx
  __int64 v31; // rcx
  int v32; // r8d
  _QWORD *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // r10
  double *v36; // rdx
  double v37; // xmm0_8
  unsigned __int64 v38; // rcx
  double v39; // xmm0_8
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rax
  double v42; // xmm0_8
  struct GeoData *v43; // rbx
  char v44; // si
  int v45; // ecx
  __int64 v46; // rdx
  struct GeoData **v47; // rax
  _OWORD *v48; // rcx
  int v49; // edx
  double v50; // xmm1_8
  unsigned __int64 v51; // rcx
  char v52; // al
  bool v53; // al
  double v54; // xmm1_8
  unsigned __int64 v55; // rax
  unsigned __int64 v56; // rbx
  bool *v57; // rcx
  bool *v58; // rcx
  bool *v59; // rcx
  bool *v60; // rcx
  bool *v61; // rcx
  _BOOL8 v62; // [rsp+38h] [rbp-D0h] BYREF
  bool *v63; // [rsp+40h] [rbp-C8h]
  __int64 v64; // [rsp+48h] [rbp-C0h]
  _QWORD *v65; // [rsp+50h] [rbp-B8h]
  __int64 v66; // [rsp+58h] [rbp-B0h] BYREF
  double v67; // [rsp+60h] [rbp-A8h]
  double v68; // [rsp+68h] [rbp-A0h]
  double v69; // [rsp+70h] [rbp-98h]
  __int64 v70; // [rsp+78h] [rbp-90h] BYREF
  double v71; // [rsp+80h] [rbp-88h]
  double v72; // [rsp+88h] [rbp-80h]
  double v73; // [rsp+90h] [rbp-78h]
  _QWORD *v74; // [rsp+98h] [rbp-70h]
  void ***v75; // [rsp+A0h] [rbp-68h]
  __int64 v76[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v77; // [rsp+B8h] [rbp-50h]
  __int64 v78; // [rsp+C8h] [rbp-40h]
  _QWORD *v79; // [rsp+D0h] [rbp-38h]
  _QWORD v80[6]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v81[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v82; // [rsp+118h] [rbp+10h]
  __int128 v83; // [rsp+128h] [rbp+20h]
  _QWORD v84[2]; // [rsp+138h] [rbp+30h] BYREF
  __int128 v85; // [rsp+148h] [rbp+40h]
  __int128 v86; // [rsp+158h] [rbp+50h]
  void **v87; // [rsp+168h] [rbp+60h] BYREF
  int v88; // [rsp+170h] [rbp+68h]
  int v89; // [rsp+1A8h] [rbp+A0h]
  __int64 v90; // [rsp+1ACh] [rbp+A4h]
  __int16 v91; // [rsp+1B4h] [rbp+ACh]
  int v92; // [rsp+1BCh] [rbp+B4h]
  int v93; // [rsp+1C0h] [rbp+B8h]
  int v94; // [rsp+1D8h] [rbp+D0h]
  int v95; // [rsp+1DCh] [rbp+D4h]
  char v96; // [rsp+1E4h] [rbp+DCh]
  char v97; // [rsp+1E5h] [rbp+DDh]
  int v98; // [rsp+1ECh] [rbp+E4h]
  int v99; // [rsp+1F0h] [rbp+E8h]
  int v100; // [rsp+208h] [rbp+100h]
  int v101; // [rsp+20Ch] [rbp+104h]
  char v102; // [rsp+214h] [rbp+10Ch]
  char v103; // [rsp+215h] [rbp+10Dh]

  v78 = -2;
  v63 = a3;
  v5 = (_QWORD *)*((_QWORD *)this + 1);
  v65 = v5;
  v6 = *(_QWORD *)(a2 + 8);
  v7 = 0;
  v8 = 0;
  v64 = 0;
  v68 = DOUBLE_1_797693134862316e308;
  *(double *)&v66 = DOUBLE_1_797693134862316e308;
  v69 = DOUBLE_2_225073858507201eN308;
  v67 = DOUBLE_2_225073858507201eN308;
  v72 = DOUBLE_1_797693134862316e308;
  *(double *)&v70 = DOUBLE_1_797693134862316e308;
  v73 = DOUBLE_2_225073858507201eN308;
  v71 = DOUBLE_2_225073858507201eN308;
  result = GeoBundle::GetBaseBounds(this, &v66);
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    result = GeoBundle::GetBaseBounds(a2, &v70);
    PointRelation = result;
    if ( (int)result < 0 )
    {
LABEL_3:
      _mm_lfence();
      return result;
    }
    if ( *(double *)&v70 <= v71 && v72 <= v73 )
    {
      if ( *(double *)&v66 <= v67
        && v68 <= v69
        && *(double *)&v70 <= v71
        && v72 <= v73
        && *(double *)&v70 >= *(double *)&v66
        && v67 >= v71
        && v72 >= v68
        && v69 >= v73 )
      {
        goto LABEL_19;
      }
      if ( *(int *)(v6 + 56) > 0 )
      {
        v11 = 0;
        v12 = (_BYTE *)(*(_QWORD *)(v6 + 48) + 8LL);
        while ( (unsigned __int8)(*v12 - 8) > 2u )
        {
          ++v11;
          v12 += 12;
          if ( v11 >= *(int *)(v6 + 56) )
            goto LABEL_18;
        }
LABEL_19:
        v14 = *(int *)(v6 + 8);
        if ( (_DWORD)v14 != 1 )
        {
          if ( (unsigned int)GeoData::GetDimension((GeoData *)v6) )
          {
LABEL_38:
            LOBYTE(v62) = 0;
            if ( !*((_DWORD *)v5 + 2) && *(_BYTE *)(v5[6] + 8LL) != 11 )
              goto LABEL_89;
            if ( IsAxisAlignedRectangle((const struct GeoData *)v5) )
            {
              v21 = *(_BYTE *)(*(_QWORD *)(v6 + 48) + 8LL);
              if ( v21 == 3 || v21 == 6 )
              {
                result = RectContains(&v66, v6, v20, &v62);
                PointRelation = result;
                if ( (int)result < 0 )
                  goto LABEL_3;
                v22 = *(_DWORD *)(v6 + 8);
LABEL_45:
                v23 = (double)v22 * 2.56312832;
                v24 = 0;
                v25 = v23 + 2613.0;
                if ( v25 >= 9.223372036854776e18 )
                {
                  v25 = v25 - 9.223372036854776e18;
                  if ( v25 < 9.223372036854776e18 )
                    v24 = 0x8000000000000000uLL;
                }
                v64 = v24 + (unsigned int)(int)v25;
                if ( !PointRelation )
                {
                  v26 = 1;
                  *v63 = v62;
                  goto LABEL_130;
                }
LABEL_89:
                v43 = 0;
                v44 = 0;
                *(double *)&v77 = DOUBLE_1_797693134862316e308;
                *(double *)v76 = DOUBLE_1_797693134862316e308;
                *((double *)&v77 + 1) = DOUBLE_2_225073858507201eN308;
                *(double *)&v76[1] = DOUBLE_2_225073858507201eN308;
                while ( 1 )
                {
                  if ( (*(_BYTE *)this & 4) == 0 )
                    goto LABEL_98;
                  v45 = 0;
                  v46 = 0;
                  if ( v43 && *((int *)this + 20) > 0 )
                  {
                    v47 = (struct GeoData **)*((_QWORD *)this + 7);
                    do
                    {
                      ++v45;
                      ++v46;
                      if ( v43 == *v47 )
                        break;
                      ++v47;
                    }
                    while ( v46 < *((int *)this + 20) );
                  }
                  if ( v45 < *((_DWORD *)this + 20) )
                  {
                    _mm_lfence();
                    v48 = *(_OWORD **)(*((_QWORD *)this + 8) + 8 * v46);
                    *(_OWORD *)v76 = *v48;
                    v77 = v48[1];
                    v44 = *(double *)(*((_QWORD *)this + 9) + 8 * v46) < 0.0;
                    v43 = *(struct GeoData **)(*((_QWORD *)this + 7) + 8 * v46);
                  }
                  else
                  {
LABEL_98:
                    v43 = 0;
                  }
                  v26 = 0;
                  if ( !v43 )
                    break;
                  v96 = 1;
                  result = GetRelation(v43, (struct GeoData *)v6, (__int64)v76, (__int64)&v70);
                  PointRelation = result;
                  if ( (int)result < 0 )
                    goto LABEL_3;
                  v49 = *((_DWORD *)v43 + 2);
                  v50 = (double)*(int *)(v6 + 8) * 18.688
                      + (double)v49 * 43.904
                      + (double)(*(_DWORD *)(v6 + 8) * v49) * 0.00074496;
                  v51 = 0;
                  if ( v50 >= 9.223372036854776e18 )
                  {
                    v50 = v50 - 9.223372036854776e18;
                    if ( v50 < 9.223372036854776e18 )
                      v51 = 0x8000000000000000uLL;
                  }
                  v7 += v51 + (unsigned int)(int)v50;
                  if ( v49 >= *((_DWORD *)v65 + 2) )
                  {
                    if ( g_SOSHost )
                      MEMORY[0] = 0;
                    else
                      (*(void (__fastcall **)(_QWORD, __int64, const char *, const char *, int, _QWORD))(MEMORY[0] + 528LL))(
                        0,
                        1,
                        "gCascade->GetPointCount() < g1.GetPointCount()",
                        "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\SqlServerSpatial.cpp",
                        1438,
                        0);
                  }
                  if ( !PointRelation )
                  {
                    if ( v97 )
                    {
                      if ( v92 >= 0 )
                        v52 = v93 >= 0 && v94 < 0 && v95 < 0;
                      else
                        v52 = 1;
                    }
                    else
                    {
                      v52 = 0;
                    }
                    if ( v44 == v52 )
                    {
                      if ( v97 )
                      {
                        if ( v92 >= 0 )
                          v53 = v93 >= 0 && v94 < 0 && v95 < 0;
                        else
                          v53 = 1;
                      }
                      else
                      {
                        v53 = 0;
                      }
                      *v63 = v53;
                      v26 = 1;
                      break;
                    }
                  }
                }
                v5 = v65;
LABEL_130:
                v54 = (double)*((int *)v5 + 2) * 43.904
                    + (double)*(int *)(v6 + 8) * 18.688
                    + (double)(*(_DWORD *)(v6 + 8) * *((_DWORD *)v5 + 2)) * 0.00074496;
                v55 = 0;
                if ( v54 >= 9.223372036854776e18 )
                {
                  v54 = v54 - 9.223372036854776e18;
                  if ( v54 < 9.223372036854776e18 )
                    v55 = 0x8000000000000000uLL;
                }
                v56 = v55 + (unsigned int)(int)v54;
                v8 += v56;
                if ( !v26 )
                {
                  v102 = 1;
                  result = GetRelation((struct GeoData *)v5, (struct GeoData *)v6, (__int64)&v66, (__int64)&v70);
                  PointRelation = result;
                  if ( (int)result < 0 )
                    goto LABEL_3;
                  v7 += v56;
                  if ( (_DWORD)result == 1 )
                  {
                    v57 = v63;
                    *v63 = 0;
                    v13 = v57;
                  }
                  else if ( v103 )
                  {
                    if ( v98 >= 0 )
                    {
                      if ( v99 >= 0 )
                      {
                        v61 = v63;
                        *v63 = v100 < 0 && v101 < 0;
                        v13 = v61;
                      }
                      else
                      {
                        v60 = v63;
                        *v63 = 0;
                        v13 = v60;
                      }
                    }
                    else
                    {
                      v59 = v63;
                      *v63 = 1;
                      v13 = v59;
                    }
                  }
                  else
                  {
                    v58 = v63;
                    *v63 = 0;
                    v13 = v58;
                  }
                  goto LABEL_35;
                }
                goto LABEL_34;
              }
            }
            if ( IsAxisAlignedRectangle((const struct GeoData *)v6) )
            {
              v28 = *(_BYTE *)(v5[6] + 8LL);
              if ( v28 == 3 || v28 == 6 )
              {
                result = RectRelationCheck<1>(&v70, v5, &v66, &v62);
                PointRelation = result;
                if ( (int)result < 0 )
                  goto LABEL_3;
                v22 = *((_DWORD *)v5 + 2);
                goto LABEL_45;
              }
            }
            v29 = *(_BYTE *)(v5[6] + 8LL);
            if ( v29 != 3 && v29 != 6 || !(_DWORD)v14 && *(_BYTE *)(*(_QWORD *)(v6 + 48) + 8LL) != 11 )
              goto LABEL_89;
            v30 = 0;
            while ( 1 )
            {
              if ( (*(_BYTE *)this & 4) == 0 )
                goto LABEL_71;
              v31 = -1;
              v32 = -1;
              if ( v30 )
              {
                v32 = 0;
                v31 = 0;
                if ( *((int *)this + 20) > 0 )
                {
                  v33 = (_QWORD *)*((_QWORD *)this + 7);
                  do
                  {
                    if ( v30 == *v33 )
                      break;
                    ++v32;
                    ++v31;
                    ++v33;
                  }
                  while ( v31 < *((int *)this + 20) );
                }
              }
              v34 = v31 + 1;
              v35 = *((int *)this + 20);
              if ( v32 + 1 >= (int)v35 )
                break;
              v36 = (double *)(*((_QWORD *)this + 9) + 8 * v34);
              while ( *v36 >= 0.0 )
              {
                ++v34;
                ++v36;
                if ( v34 >= v35 )
                  goto LABEL_70;
              }
              v30 = *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v34);
LABEL_73:
              if ( !v30 )
              {
LABEL_85:
                v41 = 0;
                v42 = (double)*((int *)v5 + 2) * 2.56312832 + 2613.0;
                if ( v42 >= 9.223372036854776e18 )
                {
                  v42 = v42 - 9.223372036854776e18;
                  if ( v42 < 9.223372036854776e18 )
                    v41 = v27;
                }
                v8 = v41 + (unsigned int)(int)v42;
                goto LABEL_89;
              }
              result = RectRelationCheck<1>(&v70, v30, &v66, &v62);
              PointRelation = result;
              if ( (int)result < 0 )
                goto LABEL_3;
              v37 = (double)*(int *)(v30 + 8) * 2.56312832 + 2613.0;
              v38 = 0;
              v27 = 0x8000000000000000uLL;
              if ( v37 >= 9.223372036854776e18 )
              {
                v37 = v37 - 9.223372036854776e18;
                if ( v37 < 9.223372036854776e18 )
                  v38 = 0x8000000000000000uLL;
              }
              v7 += v38 + (unsigned int)(int)v37;
              if ( !(_DWORD)result && v62 )
              {
                v26 = 1;
                *v63 = 1;
                v39 = (double)*((int *)v5 + 2) * 2.56312832 + 2613.0;
                v40 = 0;
                if ( v39 >= 9.223372036854776e18 )
                {
                  v39 = v39 - 9.223372036854776e18;
                  if ( v39 < 9.223372036854776e18 )
                    v40 = 0x8000000000000000uLL;
                }
                v8 = v40 + (unsigned int)(int)v39;
                goto LABEL_130;
              }
            }
LABEL_70:
            if ( v32 >= (int)v35 )
            {
LABEL_71:
              if ( v30 )
                goto LABEL_85;
            }
            v30 = *((_QWORD *)this + 1);
            goto LABEL_73;
          }
          if ( (int)v14 > 1 )
          {
            v15 = 1;
            v16 = (double *)(*(_QWORD *)v6 + 16LL);
            while ( *v16 == **(double **)v6 && v16[1] == *(double *)(*(_QWORD *)v6 + 8LL) )
            {
              ++v15;
              v16 += 2;
              if ( v15 >= v14 )
                goto LABEL_26;
            }
            goto LABEL_38;
          }
        }
LABEL_26:
        if ( *(_BYTE *)(v5[6] + 8LL) != 7 )
        {
          v65 = v80;
          v80[1] = v81;
          v80[2] = 0;
          v80[0] = &CPlanarFlattener::`vftable';
          v80[5] = 0;
          v64 = (__int64)v81;
          v81[0] = &CWorkspaceTransform::`vftable';
          v83 = _xmm;
          v74 = v84;
          v84[1] = 0;
          v84[0] = &CScaleAndShift::`vftable';
          v86 = _xmm;
          v85 = 0;
          v82 = 0;
          v75 = &v87;
          v87 = &CPointRelation::`vftable';
          v88 = 0;
          v89 = 0;
          v90 = 1;
          v91 = 1;
          v81[1] = &v87;
          PointRelation = GetPointRelation(&CPointSink::`vftable', &CGeometrySinkD::`vftable', v5, v80, &v66);
          if ( PointRelation < 0 )
          {
            _mm_lfence();
            v75 = &v87;
            v87 = &IMglGeometrySink::`vftable';
            v74 = v81;
            v65 = v84;
            v84[0] = &IMglGeometrySink::`vftable';
            v81[0] = &IMglGeometrySink::`vftable';
            v64 = (__int64)v80;
            v80[0] = &IMglGeometrySink::`vftable';
            return (unsigned int)PointRelation;
          }
          v17 = BYTE3(v90) && !BYTE4(v90);
          *v63 = v17;
          v64 = *((unsigned int *)v5 + 2) + 2530LL;
          v75 = &v87;
          v87 = &IMglGeometrySink::`vftable';
          v74 = v81;
          v65 = v84;
          v84[0] = &IMglGeometrySink::`vftable';
          v81[0] = &IMglGeometrySink::`vftable';
          v79 = v80;
          v80[0] = &IMglGeometrySink::`vftable';
LABEL_34:
          v13 = v63;
LABEL_35:
          _mm_lfence();
          if ( (*(_BYTE *)this & 4) != 0 )
          {
            v19 = !*v13;
            _mm_lfence();
            v18 = (_QWORD *)*((_QWORD *)this + 11);
            if ( v19 )
            {
              v18[1] += v8;
              *(_QWORD *)(*((_QWORD *)this + 11) + 24LL) += v7;
              v19 = *(_QWORD *)(*((_QWORD *)this + 11) + 24LL) == v7;
            }
            else
            {
              *v18 += v8;
              *(_QWORD *)(*((_QWORD *)this + 11) + 16LL) += v7;
              v19 = *(_QWORD *)(*((_QWORD *)this + 11) + 16LL) == v7;
            }
            if ( v19 && v7 )
            {
              _mm_lfence();
              GeoBundle::UpdateNextCascadeCost(this);
            }
            if ( (*(_BYTE *)this & 4) != 0 )
            {
              _mm_lfence();
              *(_QWORD *)(*((_QWORD *)this + 11) + 32LL) += v64;
            }
          }
          return (unsigned int)PointRelation;
        }
        goto LABEL_38;
      }
    }
LABEL_18:
    v13 = v63;
    *v63 = 0;
    PointRelation = 1;
    goto LABEL_35;
  }
  return result;
}

```

## disassembly

```asm
0x1004130f0  mov     rax, rsp
0x1004130f3  push    rbp
0x1004130f4  push    rsi
0x1004130f5  push    rdi
0x1004130f6  push    r12
0x1004130f8  push    r13
0x1004130fa  push    r14
0x1004130fc  push    r15
0x1004130fe  lea     rbp, [rax-1E8h]
0x100413105  sub     rsp, 2B0h
0x10041310c  mov     [rbp+1E0h+var_220], 0FFFFFFFFFFFFFFFEh
0x100413114  mov     [rax+20h], rbx
0x100413118  movaps  xmmword ptr [rax-48h], xmm6
0x10041311c  movaps  xmmword ptr [rax-58h], xmm7
0x100413120  movaps  xmmword ptr [rax-68h], xmm8
0x100413125  movaps  xmmword ptr [rax-78h], xmm9
0x10041312a  movaps  xmmword ptr [rax-88h], xmm10
0x100413132  movaps  xmmword ptr [rax-98h], xmm11
0x10041313a  movaps  xmmword ptr [rax-0A8h], xmm12
0x100413142  movaps  xmmword ptr [rax-0B8h], xmm13
0x10041314a  movaps  xmmword ptr [rax-0C8h], xmm14
0x100413152  mov     rax, cs:__security_cookie
0x100413159  xor     rax, rsp
0x10041315c  mov     [rbp+1E0h+var_D0], rax
0x100413163  mov     [rsp+2E0h+var_2A8], r8
0x100413168  mov     rbx, rdx
0x10041316b  mov     rdi, rcx
0x10041316e  mov     rsi, [rcx+8]
0x100413172  mov     [rsp+2E0h+var_298], rsi
0x100413177  mov     r13, [rdx+8]
0x10041317b  xor     r12d, r12d
0x10041317e  xor     r15d, r15d
0x100413181  mov     [rsp+2E0h+var_2A0], r12
0x100413186  movsd   xmm9, cs:__real@7fefffffffffffff
0x10041318f  movsd   [rsp+2E0h+var_280], xmm9
0x100413196  movsd   [rsp+2E0h+var_290], xmm9
0x10041319d  movsd   xmm10, cs:__real@0010000000000000
0x1004131a6  movsd   [rsp+2E0h+var_278], xmm10
0x1004131ad  movsd   [rsp+2E0h+var_288], xmm10
0x1004131b4  movsd   [rbp+1E0h+var_260], xmm9
0x1004131ba  movsd   [rsp+2E0h+var_270], xmm9
0x1004131c1  movsd   [rbp+1E0h+var_258], xmm10
0x1004131c7  movsd   [rsp+2E0h+var_268], xmm10
0x1004131ce  lea     rdx, [rsp+2E0h+var_290]
0x1004131d3  call    ?GetBaseBounds@GeoBundle@@QEAAJPEAV?$CMglRect@N@@@Z; GeoBundle::GetBaseBounds(CMglRect<double> *)
0x1004131d8  lfence
0x1004131db  test    eax, eax
0x1004131dd  js      loc_100413C1C
0x1004131e3  lea     rdx, [rsp+2E0h+var_270]
0x1004131e8  mov     rcx, rbx
0x1004131eb  call    ?GetBaseBounds@GeoBundle@@QEAAJPEAV?$CMglRect@N@@@Z; GeoBundle::GetBaseBounds(CMglRect<double> *)
0x1004131f0  mov     r14d, eax
0x1004131f3  test    eax, eax
0x1004131f5  jns     short loc_1004131FF
0x1004131f7  lfence
0x1004131fa  jmp     loc_100413C1C
0x1004131ff  movsd   xmm0, [rsp+2E0h+var_270]
0x100413205  movsd   xmm1, [rsp+2E0h+var_268]
0x10041320b  comisd  xmm0, xmm1
0x10041320f  ja      loc_100413297
0x100413215  movsd   xmm2, [rbp+1E0h+var_260]
0x10041321a  movsd   xmm3, [rbp+1E0h+var_258]
0x10041321f  comisd  xmm2, xmm3
0x100413223  ja      short loc_100413297
0x100413225  movsd   xmm4, [rsp+2E0h+var_290]
0x10041322b  movsd   xmm5, [rsp+2E0h+var_288]
0x100413231  comisd  xmm4, xmm5
0x100413235  ja      short loc_10041326D
0x100413237  movsd   xmm6, [rsp+2E0h+var_280]
0x10041323d  movsd   xmm7, [rsp+2E0h+var_278]
0x100413243  comisd  xmm6, xmm7
0x100413247  ja      short loc_10041326D
0x100413249  comisd  xmm0, xmm1
0x10041324d  ja      short loc_10041326D
0x10041324f  comisd  xmm2, xmm3
0x100413253  ja      short loc_10041326D
0x100413255  comisd  xmm0, xmm4
0x100413259  jb      short loc_10041326D
0x10041325b  comisd  xmm5, xmm1
0x10041325f  jb      short loc_10041326D
0x100413261  comisd  xmm2, xmm6
0x100413265  jb      short loc_10041326D
0x100413267  comisd  xmm7, xmm3
0x10041326b  jnb     short loc_1004132AA
0x10041326d  movsxd  rcx, dword ptr [r13+38h]
0x100413271  test    ecx, ecx
0x100413273  jle     short loc_100413297
0x100413275  mov     rax, [r13+30h]
0x100413279  mov     r8, rcx
0x10041327c  xor     edx, edx
0x10041327e  lea     rcx, [rax+8]
0x100413282  movzx   eax, byte ptr [rcx]
0x100413285  sub     al, 8
0x100413287  cmp     al, 2
0x100413289  jbe     short loc_1004132AA
0x10041328b  inc     rdx
0x10041328e  add     rcx, 0Ch
0x100413292  cmp     rdx, r8
0x100413295  jl      short loc_100413282
0x100413297  mov     rax, [rsp+2E0h+var_2A8]
0x10041329c  mov     [rax], r12b
0x10041329f  mov     r14d, 1
0x1004132a5  jmp     loc_100413541
0x1004132aa  movsxd  rbx, dword ptr [r13+8]
0x1004132ae  cmp     ebx, 1
0x1004132b1  jz      short loc_100413316
0x1004132b3  mov     rcx, r13; this
0x1004132b6  call    ?GetDimension@GeoData@@QEBAHXZ; GeoData::GetDimension(void)
0x1004132bb  test    eax, eax
0x1004132bd  jnz     loc_100413575
0x1004132c3  cmp     ebx, 1
0x1004132c6  jle     short loc_100413316
0x1004132c8  mov     rdx, [r13+0]
0x1004132cc  movsd   xmm1, qword ptr [rdx]
0x1004132d0  lea     ecx, [rax+1]
0x1004132d3  lea     rax, [rdx+10h]
0x1004132d7  nop     word ptr [rax+rax+00000000h]
0x1004132e0  movsd   xmm0, qword ptr [rax]
0x1004132e4  ucomisd xmm0, xmm1
0x1004132e8  jp      loc_100413575
0x1004132ee  jnz     loc_100413575
0x1004132f4  movsd   xmm0, qword ptr [rax+8]
0x1004132f9  ucomisd xmm0, qword ptr [rdx+8]
0x1004132fe  jp      loc_100413575
0x100413304  jnz     loc_100413575
0x10041330a  inc     rcx
0x10041330d  add     rax, 10h
0x100413311  cmp     rcx, rbx
0x100413314  jl      short loc_1004132E0
0x100413316  mov     rax, [r13+0]
0x10041331a  movsd   xmm2, qword ptr [rax+8]
0x10041331f  movsd   xmm3, qword ptr [rax]
0x100413323  mov     rax, [rsi+30h]
0x100413327  cmp     byte ptr [rax+8], 7
0x10041332b  jz      loc_100413575
0x100413331  lea     rax, [rbp+1E0h+var_210]
0x100413335  mov     [rsp+2E0h+var_298], rax
0x10041333a  lea     rbx, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x100413341  mov     [rbp+1E0h+var_210], rbx
0x100413345  lea     rdx, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x10041334c  mov     [rbp+1E0h+var_210], rdx
0x100413350  lea     r13, ??_7CDecorator@@6B@; const CDecorator::`vftable'
0x100413357  mov     [rbp+1E0h+var_210], r13
0x10041335b  lea     rax, [rbp+1E0h+var_1E0]
0x10041335f  mov     [rbp+1E0h+var_208], rax
0x100413363  lea     rax, ??_7CFlattener@@6B@; const CFlattener::`vftable'
0x10041336a  mov     [rbp+1E0h+var_210], rax
0x10041336e  xorps   xmm0, xmm0
0x100413371  movsd   [rbp+1E0h+var_200], xmm0
0x100413376  lea     rax, ??_7CPlanarFlattener@@6B@; const CPlanarFlattener::`vftable'
0x10041337d  mov     [rbp+1E0h+var_210], rax
0x100413381  xor     r8d, r8d
0x100413384  mov     [rbp+1E0h+var_1E8], r8
0x100413388  lea     rax, [rbp+1E0h+var_1E0]
0x10041338c  mov     [rsp+2E0h+var_2A0], rax
0x100413391  mov     [rbp+1E0h+var_1E0], rbx
0x100413395  mov     [rbp+1E0h+var_1E0], rdx
0x100413399  lea     rcx, ??_7CPointSink@@6B@; const CPointSink::`vftable'
0x1004133a0  mov     [rbp+1E0h+var_1E0], rcx
0x1004133a4  mov     [rbp+1E0h+var_1D8], r8
0x1004133a8  lea     rax, ??_7CWorkspaceTransform@@6B@; const CWorkspaceTransform::`vftable'
0x1004133af  mov     [rbp+1E0h+var_1E0], rax
0x1004133b3  movaps  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1004133ba  movaps  [rbp+1E0h+var_1C0], xmm0
0x1004133be  lea     rax, [rbp+1E0h+var_1B0]
0x1004133c2  mov     [rbp+1E0h+var_250], rax
0x1004133c6  mov     [rbp+1E0h+var_1B0], rbx
0x1004133ca  mov     [rbp+1E0h+var_1B0], rdx
0x1004133ce  mov     [rbp+1E0h+var_1B0], rcx
0x1004133d2  mov     [rbp+1E0h+var_1A8], r8
0x1004133d6  lea     rax, ??_7CScaleAndShift@@6B@; const CScaleAndShift::`vftable'
0x1004133dd  mov     [rbp+1E0h+var_1B0], rax
0x1004133e1  movaps  [rbp+1E0h+var_190], xmm0
0x1004133e5  xorps   xmm1, xmm1
0x1004133e8  movaps  [rbp+1E0h+var_1A0], xmm1
0x1004133ec  xorps   xmm0, xmm0
0x1004133ef  movaps  [rbp+1E0h+var_1D0], xmm0
0x1004133f3  lea     rax, [rbp+1E0h+var_180]
0x1004133f7  mov     [rbp+1E0h+var_248], rax
0x1004133fb  mov     [rbp+1E0h+var_180], rbx
0x1004133ff  mov     [rbp+1E0h+var_180], rdx
0x100413403  lea     rax, ??_7CPointRelation@@6B@; const CPointRelation::`vftable'
0x10041340a  mov     [rbp+1E0h+var_180], rax
0x10041340e  mov     [rbp+1E0h+var_178], r8d
0x100413412  mov     [rbp+1E0h+var_140], r8d
0x100413419  mov     [rbp+1E0h+var_13C], 1
0x100413424  mov     [rbp+1E0h+var_134], 1
0x10041342d  lea     rax, [rbp+1E0h+var_180]
0x100413431  mov     [rbp+1E0h+var_1D8], rax
0x100413435  lea     rax, [rsp+2E0h+var_290]
0x10041343a  mov     [rsp+2E0h+var_2C0], rax
0x10041343f  lea     r9, [rbp+1E0h+var_210]
0x100413443  mov     r8, rsi
0x100413446  movaps  xmm1, xmm2
0x100413449  movaps  xmm0, xmm3
0x10041344c  call    ?GetPointRelation@@YAJNNAEBUGeoData@@AEAVCPointRelationModule@@PEBV?$CMglRect@N@@@Z; GetPointRelation(double,double,GeoData const &,CPointRelationModule &,CMglRect<double> const *)
0x100413451  mov     r14d, eax
0x100413454  test    eax, eax
0x100413456  jns     short loc_1004134B7
0x100413458  lfence
0x10041345b  lea     rax, [rbp+1E0h+var_180]
0x10041345f  mov     [rbp+1E0h+var_248], rax
0x100413463  lea     rax, ??_7CPointRelation@@6B@; const CPointRelation::`vftable'
0x10041346a  mov     [rbp+1E0h+var_180], rax
0x10041346e  mov     [rbp+1E0h+var_180], rbx
0x100413472  lea     rax, [rbp+1E0h+var_1E0]
0x100413476  mov     [rbp+1E0h+var_250], rax
0x10041347a  lea     rax, [rbp+1E0h+var_1B0]
0x10041347e  mov     [rsp+2E0h+var_298], rax
0x100413483  mov     [rbp+1E0h+var_1B0], rbx
0x100413487  mov     [rbp+1E0h+var_1E0], rbx
0x10041348b  lea     rax, [rbp+1E0h+var_210]
0x10041348f  mov     [rsp+2E0h+var_2A0], rax
0x100413494  lea     rax, ??_7CPlanarFlattener@@6B@; const CPlanarFlattener::`vftable'
0x10041349b  mov     [rbp+1E0h+var_210], rax
0x10041349f  lea     rax, ??_7CFlattener@@6B@; const CFlattener::`vftable'
0x1004134a6  mov     [rbp+1E0h+var_210], rax
0x1004134aa  mov     [rbp+1E0h+var_210], r13
0x1004134ae  mov     [rbp+1E0h+var_210], rbx
0x1004134b2  jmp     loc_100413C19
0x1004134b7  cmp     byte ptr [rbp+1E0h+var_13C+3], 0
0x1004134be  jz      short loc_1004134CD
0x1004134c0  cmp     byte ptr [rbp+1E0h+var_13C+4], 0
0x1004134c7  jnz     short loc_1004134CD
0x1004134c9  mov     al, 1
0x1004134cb  jmp     short loc_1004134CF
0x1004134cd  xor     al, al
0x1004134cf  mov     rcx, [rsp+2E0h+var_2A8]
0x1004134d4  mov     [rcx], al
0x1004134d6  mov     r9d, [rsi+8]
0x1004134da  add     r9, 9E2h
0x1004134e1  mov     [rsp+2E0h+var_2A0], r9
0x1004134e6  lea     rax, [rbp+1E0h+var_180]
0x1004134ea  mov     [rbp+1E0h+var_248], rax
0x1004134ee  lea     rax, ??_7CPointRelation@@6B@; const CPointRelation::`vftable'
0x1004134f5  mov     [rbp+1E0h+var_180], rax
0x1004134f9  mov     [rbp+1E0h+var_180], rbx
0x1004134fd  lea     rax, [rbp+1E0h+var_1E0]
0x100413501  mov     [rbp+1E0h+var_250], rax
0x100413505  lea     rax, [rbp+1E0h+var_1B0]
0x100413509  mov     [rsp+2E0h+var_298], rax
0x10041350e  mov     [rbp+1E0h+var_1B0], rbx
0x100413512  mov     [rbp+1E0h+var_1E0], rbx
0x100413516  lea     rax, [rbp+1E0h+var_210]
0x10041351a  mov     [rbp+1E0h+var_218], rax
0x10041351e  lea     rax, ??_7CPlanarFlattener@@6B@; const CPlanarFlattener::`vftable'
0x100413525  mov     [rbp+1E0h+var_210], rax
0x100413529  lea     rax, ??_7CFlattener@@6B@; const CFlattener::`vftable'
0x100413530  mov     [rbp+1E0h+var_210], rax
0x100413534  mov     [rbp+1E0h+var_210], r13
0x100413538  mov     [rbp+1E0h+var_210], rbx
0x10041353c  mov     rax, [rsp+2E0h+var_2A8]
0x100413541  lfence
0x100413544  test    byte ptr [rdi], 4
0x100413547  jz      loc_100413C19
0x10041354d  cmp     byte ptr [rax], 0
0x100413550  lfence
0x100413553  mov     rax, [rdi+58h]
0x100413557  jz      loc_100413BDE
0x10041355d  add     [rax], r15
0x100413560  mov     rax, [rdi+58h]
0x100413564  add     [rax+10h], r12
0x100413568  mov     rax, [rdi+58h]
0x10041356c  cmp     [rax+10h], r12
0x100413570  jmp     loc_100413BF2
0x100413575  mov     byte ptr [rsp+2E0h+var_2B0], r12b
0x10041357a  movsd   xmm12, cs:__real@4032b020c49ba5e3
0x100413583  movsd   xmm13, cs:__real@4045f3b645a1cac1
0x10041358c  movsd   xmm14, cs:__real@3f48692d6b1d2f66
0x100413595  xorps   xmm11, xmm11
0x100413599  mov     r11, 8000000000000000h
0x1004135a3  movsd   xmm8, cs:__real@43e0000000000000
0x1004135ac  cmp     [rsi+8], r12d
0x1004135b0  jnz     short loc_1004135C0
0x1004135b2  mov     rax, [rsi+30h]
0x1004135b6  cmp     byte ptr [rax+8], 0Bh
0x1004135ba  jnz     loc_10041386F
0x1004135c0  mov     rcx, rsi; struct GeoData *
0x1004135c3  call    ?IsAxisAlignedRectangle@@YA_NAEBUGeoData@@@Z; IsAxisAlignedRectangle(GeoData const &)
0x1004135c8  test    al, al
0x1004135ca  jz      loc_10041366B
0x1004135d0  mov     rax, [r13+30h]
0x1004135d4  movzx   ecx, byte ptr [rax+8]
0x1004135d8  cmp     cl, 3
0x1004135db  jz      short loc_1004135E6
0x1004135dd  cmp     cl, 6
0x1004135e0  jnz     loc_10041366B
0x1004135e6  lea     r9, [rsp+2E0h+var_2B0]
0x1004135eb  mov     rdx, r13
0x1004135ee  lea     rcx, [rsp+2E0h+var_290]
0x1004135f3  call    ?RectContains@@YAJAEBV?$CMglRect@N@@AEBUGeoData@@0PEA_N@Z; RectContains(CMglRect<double> const &,GeoData const &,CMglRect<double> const &,bool *)
0x1004135f8  mov     r14d, eax
0x1004135fb  test    eax, eax
0x1004135fd  js      loc_1004131F7
0x100413603  mov     eax, [r13+8]
0x100413607  xorps   xmm0, xmm0
0x10041360a  cvtsi2sd xmm0, rax
0x10041360f  mulsd   xmm0, cs:__real@400481496baecfb7
0x100413617  xor     eax, eax
0x100413619  addsd   xmm0, cs:__real@40a46a0000000000
  ... truncated ...
```
