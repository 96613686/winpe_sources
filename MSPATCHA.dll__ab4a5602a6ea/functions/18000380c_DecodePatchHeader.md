# DecodePatchHeader

- ea: `0x18000380c`
- end: `0x1800040c9`
- name: `DecodePatchHeader`
- size: `2237`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, __int64, _DWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180001d10`
- `0x180002720`

## callees

- `0x18000380c`
- `0x180004a04`
- `0x180004a68`
- `0x1800071e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040ae`

## pseudocode

```c
__int64 __fastcall DecodePatchHeader(_DWORD *a1, unsigned int a2, __int64 a3, _DWORD *a4, __int64 *a5)
{
  __int64 result; // rax
  __int64 v7; // r14
  BOOL v8; // r12d
  DWORD v9; // esi
  unsigned int v10; // eax
  unsigned __int16 *v11; // rbx
  unsigned int v12; // edx
  unsigned int v13; // eax
  unsigned __int8 v14; // cl
  int v15; // edx
  unsigned __int16 *v16; // rcx
  int v17; // edx
  int v18; // eax
  _DWORD *v19; // r15
  _DWORD *v20; // rax
  unsigned __int8 v21; // cl
  _DWORD *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r15
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 i; // rax
  __int64 v28; // r15
  __int64 v29; // r12
  __int64 v30; // rax
  int v31; // edx
  unsigned int v32; // ecx
  __int64 v33; // rax
  unsigned int j; // r8d
  __int64 v35; // rax
  __int64 v36; // r8
  int v37; // r9d
  unsigned __int64 v38; // r10
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // r11
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned int k; // edx
  __int64 v44; // rax
  __int64 v45; // rax
  unsigned int v46; // edx
  __int64 v47; // r11
  int v48; // r8d
  int v49; // r9d
  unsigned __int64 v50; // r10
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rcx
  _DWORD *v55; // rdx
  __int64 v56; // rax
  unsigned int m; // edx
  __int64 v58; // rax
  int v59; // r8d
  __int64 v60; // rdx
  int v61; // r9d
  unsigned int *v62; // r8
  unsigned int v63; // eax
  unsigned int v64; // edx
  __int64 v65; // rax
  unsigned int v66; // r9d
  unsigned int v67; // r10d
  __int64 v68; // rdx
  __int64 v69; // rcx
  unsigned __int64 v70; // rcx
  unsigned int v71; // ecx
  int v72; // ecx
  int v73; // [rsp+2Ch] [rbp-BCh] BYREF
  unsigned int v74; // [rsp+30h] [rbp-B8h]
  int v75; // [rsp+34h] [rbp-B4h]
  unsigned int v76; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v77; // [rsp+40h] [rbp-A8h]
  unsigned int v78; // [rsp+48h] [rbp-A0h] BYREF
  int v79; // [rsp+4Ch] [rbp-9Ch] BYREF
  int v80; // [rsp+50h] [rbp-98h] BYREF
  int v81; // [rsp+54h] [rbp-94h] BYREF
  unsigned int v82; // [rsp+58h] [rbp-90h]
  unsigned int *v83; // [rsp+60h] [rbp-88h]
  int v84; // [rsp+68h] [rbp-80h] BYREF
  int v85; // [rsp+6Ch] [rbp-7Ch]
  int v86; // [rsp+70h] [rbp-78h] BYREF
  int v87; // [rsp+74h] [rbp-74h]
  unsigned int v88; // [rsp+78h] [rbp-70h]
  unsigned int v89; // [rsp+7Ch] [rbp-6Ch]
  unsigned int v90; // [rsp+80h] [rbp-68h]
  int v91; // [rsp+84h] [rbp-64h]
  unsigned int v92; // [rsp+88h] [rbp-60h]
  int v93; // [rsp+8Ch] [rbp-5Ch]
  int v94; // [rsp+90h] [rbp-58h]
  BOOL v95; // [rsp+94h] [rbp-54h]
  __int64 v96; // [rsp+98h] [rbp-50h]
  __int64 v97; // [rsp+A0h] [rbp-48h]

  v73 = 0;
  v79 = 0;
  v80 = 0;
  v78 = 0;
  result = SubAllocate(a3, 64);
  v7 = result;
  v97 = result;
  if ( !result )
    return result;
  v8 = 0;
  v9 = -1072807678;
  v75 = -1072807678;
  v10 = *a1;
  *(_DWORD *)v7 = *a1;
  v11 = (unsigned __int16 *)(a1 + 1);
  if ( v10 == 959529296 )
  {
    v15 = *(_DWORD *)v11;
    *(_DWORD *)(v7 + 4) = *(_DWORD *)v11;
    v16 = v11 + 2;
    v11 += 2;
    v17 = v15 ^ 0x800000;
    *(_DWORD *)(v7 + 4) = v17;
    if ( (v17 & 0x3F00FFF8) == 0 )
    {
      if ( v17 >= 0
        || (v18 = *(_DWORD *)v16, *(_DWORD *)(v7 + 8) = *(_DWORD *)v16, v11 = v16 + 2, v16 += 2, (v18 & 0xFFFEFCC0) == 0) )
      {
        if ( (v17 & 0x800000) == 0 )
        {
          *(_DWORD *)(v7 + 24) = *(_DWORD *)v11;
          v11 = v16 + 2;
          v16 += 2;
        }
        v19 = (_DWORD *)(v7 + 16);
        if ( (v17 & 0x40000) == 0 )
        {
          *(_DWORD *)(v7 + 12) = *v11 << 16;
          if ( *(_DWORD *)(v7 + 24) )
          {
            v11 = (unsigned __int16 *)VariableLengthSignedDecode(v16 + 1, &v73);
            *v19 = *(_DWORD *)(v7 + 24) - v73;
          }
          else
          {
            *v19 = *(_DWORD *)(v16 + 1);
            v11 = v16 + 3;
          }
          v16 = v11;
        }
        if ( (*(_DWORD *)(v7 + 4) & 0x400000) == 0 )
        {
          if ( *v19 )
          {
            v11 = (unsigned __int16 *)VariableLengthSignedDecode(v11, &v73);
            *(_DWORD *)(v7 + 20) = *v19 - v73;
          }
          else
          {
            *(_DWORD *)(v7 + 20) = *(_DWORD *)v11;
            v11 = v16 + 2;
          }
        }
        v20 = (_DWORD *)VariableLengthUnsignedDecode(v11, v7 + 28);
        *(_DWORD *)(v7 + 32) = *v20;
        v11 = (unsigned __int16 *)(v20 + 1);
        if ( (*(_DWORD *)(v7 + 8) & 0x10000) != 0 )
        {
          v21 = *(_BYTE *)v11;
          v22 = (_DWORD *)((char *)v20 + 5);
          v11 = (unsigned __int16 *)((char *)v20 + 5);
          if ( v21 > 0x1Fu )
            goto LABEL_73;
          *(_DWORD *)(v7 + 56) = 1 << v21;
        }
        else
        {
          v22 = v20 + 1;
        }
        v23 = *(unsigned __int8 *)v11;
        v92 = v23;
        *(_DWORD *)(v7 + 36) = v23;
        v11 = (unsigned __int16 *)((char *)v22 + 1);
        v24 = (unsigned int)v23;
        v25 = SubAllocate(a3, 72 * v23);
        *(_QWORD *)(v7 + 40) = v25;
        if ( v25 )
        {
          if ( (*(_DWORD *)(v7 + 4) & 0x40000000) == 0
            || (v26 = SubAllocate(a3, 8 * v24), (*(_QWORD *)(v7 + 48) = v26) != 0) )
          {
            for ( i = 0; ; i = (unsigned int)(v91 + 1) )
            {
              v91 = i;
              if ( (unsigned int)i >= v92 )
              {
                v72 = (int)a1;
                v8 = v11 <= (unsigned __int16 *)((char *)a1 + a2);
                v95 = v8;
                goto LABEL_74;
              }
              v96 = i;
              v28 = 9 * i;
              v29 = *(_QWORD *)(v7 + 40);
              v30 = VariableLengthSignedDecode(v11, &v73);
              LODWORD(v11) = v30;
              v31 = v73 + *(_DWORD *)(v7 + 28);
              if ( v31 < 0 )
                break;
              *(_DWORD *)(v29 + 8 * v28 + 8) = v31;
              *(_DWORD *)(v29 + 8 * v28 + 12) = *(_DWORD *)v30;
              v32 = *(unsigned __int8 *)(v30 + 4);
              *(_DWORD *)(v29 + 8 * v28 + 20) = v32;
              v11 = (unsigned __int16 *)(v30 + 5);
              if ( v32 )
              {
                v33 = SubAllocate(a3, 8LL * v32);
                *(_QWORD *)(v29 + 8 * v28 + 24) = v33;
                if ( !v33 )
                  goto LABEL_38;
                LODWORD(v77) = 0;
                for ( j = 0; ; j = v36 + 1 )
                {
                  v74 = j;
                  if ( j >= *(_DWORD *)(v29 + 8 * v28 + 20) )
                    break;
                  v35 = VariableLengthSignedDecode(v11, &v73);
                  v11 = (unsigned __int16 *)VariableLengthUnsignedDecode(v35, &v78);
                  v36 = v74;
                  v37 = v77;
                  *(_DWORD *)(*(_QWORD *)(v29 + 8 * v28 + 24) + 8LL * v74) = v77 + v73;
                  v38 = v78;
                  *(_DWORD *)(*(_QWORD *)(v29 + 8 * v28 + 24) + 8 * v36 + 4) = v78;
                  v39 = *(unsigned int *)(v29 + 8 * v28 + 8);
                  v40 = *(unsigned int *)(*(_QWORD *)(v29 + 8 * v28 + 24) + 8 * v36);
                  if ( v40 > v39 || v38 > v39 - v40 )
                    goto LABEL_72;
                  LODWORD(v77) = v38 + v73 + v37;
                }
              }
              v41 = *(unsigned __int8 *)v11;
              *(_DWORD *)(v29 + 8 * v28 + 32) = v41;
              v11 = (unsigned __int16 *)((char *)v11 + 1);
              if ( (_DWORD)v41 )
              {
                v42 = SubAllocate(a3, 12 * v41);
                *(_QWORD *)(v29 + 8 * v28 + 40) = v42;
                if ( !v42 )
                  goto LABEL_38;
                LODWORD(v77) = 0;
                for ( k = 0; ; k = v46 + 1 )
                {
                  v74 = k;
                  if ( k >= *(_DWORD *)(v29 + 8 * v28 + 32) )
                    break;
                  v44 = VariableLengthSignedDecode(v11, &v73);
                  v45 = VariableLengthSignedDecode(v44, &v79);
                  v11 = (unsigned __int16 *)VariableLengthUnsignedDecode(v45, &v78);
                  v46 = v74;
                  v47 = 3LL * v74;
                  v48 = v77;
                  v49 = v73;
                  *(_DWORD *)(*(_QWORD *)(v29 + 8 * v28 + 40) + 4 * v47) = v77 + v73;
                  *(_DWORD *)(*(_QWORD *)(v29 + 8 * v28 + 40) + 4 * v47 + 8) = v49 + v48 + v79;
                  v50 = v78;
                  *(_DWORD *)(*(_QWORD *)(v29 + 8 * v28 + 40) + 4 * v47 + 4) = v78;
                  v51 = *(unsigned int *)(v29 + 8 * v28 + 8);
                  v52 = *(unsigned int *)(*(_QWORD *)(v29 + 8 * v28 + 40) + 4 * v47);
                  if ( v52 > v51 )
                    goto LABEL_72;
                  if ( v50 > v51 - v52 )
                    goto LABEL_72;
                  v53 = *(unsigned int *)(v7 + 28);
                  v54 = *(unsigned int *)(*(_QWORD *)(v29 + 8 * v28 + 40) + 4 * v47 + 8);
                  if ( v54 > v53 || v50 > v53 - v54 )
                    goto LABEL_72;
                  LODWORD(v77) = v50 + v49 + v48;
                }
              }
              v11 = (unsigned __int16 *)VariableLengthUnsignedDecode(v11, v29 + 48 + 8 * v28);
              if ( *v55 )
              {
                v56 = SubAllocate(a3, 8LL * (unsigned int)*v55);
                *(_QWORD *)(v29 + 8 * v28 + 56) = v56;
                if ( !v56 )
                  goto LABEL_38;
                *(_QWORD *)(v29 + 8 * v28 + 64) = 0;
                LODWORD(v77) = 0;
                v93 = 0;
                LODWORD(v83) = 0;
                v94 = 0;
                for ( m = 0; ; m = v60 + 1 )
                {
                  v74 = m;
                  if ( m >= *(_DWORD *)(v29 + 8 * v28 + 48) )
                    break;
                  v58 = VariableLengthUnsignedDecode(v11, &v80);
                  v11 = (unsigned __int16 *)VariableLengthSignedDecode(v58, &v79);
                  v59 = v80 + v77;
                  LODWORD(v77) = v59;
                  v60 = v74;
                  *(_DWORD *)(*(_QWORD *)(v29 + 8 * v28 + 56) + 8LL * v74) = v59;
                  v61 = v79 + (_DWORD)v83;
                  LODWORD(v83) = v61;
                  *(_DWORD *)(*(_QWORD *)(v29 + 8 * v28 + 56) + 8 * v60 + 4) = v61;
                  v93 = v59;
                  v94 = v61;
                }
              }
              if ( (*(_DWORD *)(v7 + 4) & 0x40000000) != 0 )
              {
                v76 = 0;
                v11 = (unsigned __int16 *)VariableLengthUnsignedDecode(v11, &v76);
                if ( v76 )
                {
                  v89 = 0;
                  v88 = 0;
                  v90 = 0;
                  v85 = 0;
                  v87 = 0;
                  v82 = *(_DWORD *)(v7 + 28);
                  v62 = (unsigned int *)SubAllocate(a3, 12 * (v76 - 1) + 16);
                  v83 = v62;
                  if ( !v62 )
                  {
LABEL_38:
                    v9 = 14;
                    v75 = 14;
                    break;
                  }
                  v63 = v76;
                  *v62 = v76;
                  v64 = 0;
                  v74 = 0;
                  while ( v64 < v63 )
                  {
                    v84 = 0;
                    v86 = 0;
                    v81 = 0;
                    v65 = VariableLengthSignedDecode(v11, &v84);
                    v11 = (unsigned __int16 *)VariableLengthSignedDecode(v65, &v86);
                    v85 += v84;
                    v87 += v86;
                    v88 += v87;
                    v66 = v88;
                    v67 = v85 + v89;
                    v89 = v67;
                    v68 = v74;
                    v69 = 3LL * v74;
                    v62 = v83;
                    v83[v69 + 1] = v67;
                    v62[v69 + 2] = v66;
                    v70 = *(unsigned int *)(v29 + 8 * v28 + 8);
                    if ( v67 > v70 || v66 > v70 - v67 )
                      goto LABEL_72;
                    v77 = 3 * (v68 + 1);
                    if ( (unsigned int)v68 >= v76 - 1 )
                    {
                      v62[3 * v68 + 3] = v82;
                    }
                    else
                    {
                      v11 = (unsigned __int16 *)VariableLengthSignedDecode(v11, &v81);
                      v81 <<= 15;
                      v71 = v81 + v90;
                      v90 = v71;
                      v62 = v83;
                      v83[v77] = v71;
                      v82 -= v71;
                      LODWORD(v68) = v74;
                    }
                    v64 = v68 + 1;
                    v74 = v64;
                    v63 = v76;
                  }
                  *(_QWORD *)(*(_QWORD *)(v7 + 48) + 8 * v96) = v62;
                }
              }
              v11 = (unsigned __int16 *)VariableLengthUnsignedDecode(v11, v29 + 16 + 8 * v28);
            }
LABEL_72:
            v8 = 0;
            goto LABEL_73;
          }
        }
        v9 = 14;
        goto LABEL_10;
      }
    }
  }
  else
  {
    LODWORD(v83) = v10;
    if ( (_WORD)v10 == 16720
      && (v12 = HIWORD(v10), (unsigned __int8)(BYTE2(v10) - 48) <= 9u)
      && (v13 = HIBYTE(v10), (unsigned __int8)(v13 - 48) <= 9u) )
    {
      v14 = v13 + 10 * v12 - 16;
    }
    else
    {
      v14 = 0;
    }
    v80 = 959529296;
    if ( v14 > 0x13u )
    {
      v9 = -1072807677;
LABEL_10:
      v75 = v9;
    }
  }
LABEL_73:
  v72 = (int)a1;
LABEL_74:
  if ( v8 )
  {
    if ( a4 )
      *a4 = (_DWORD)v11 - v72;
    if ( a5 )
      *a5 = v7;
  }
  else
  {
    SetLastError(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x18000380c  mov     rax, rsp
0x18000380f  mov     [rax+20h], r9
0x180003813  mov     [rax+18h], r8
0x180003817  mov     [rax+10h], edx
0x18000381a  mov     [rax+8], rcx
0x18000381e  push    rbx
0x18000381f  push    rsi
0x180003820  push    r12
0x180003822  push    r13
0x180003824  push    r14
0x180003826  push    r15
0x180003828  sub     rsp, 0B8h
0x18000382f  mov     rbx, rcx
0x180003832  mov     [rsp+0E8h+var_BC], 0
0x18000383a  mov     [rsp+0E8h+var_9C], 0
0x180003842  mov     [rsp+0E8h+var_98], 0
0x18000384a  mov     [rsp+0E8h+var_A0], 0
0x180003852  mov     edx, 40h ; '@'
0x180003857  mov     rcx, r8
0x18000385a  call    SubAllocate
0x18000385f  mov     r14, rax
0x180003862  mov     [rsp+0E8h+var_48], rax
0x18000386a  test    rax, rax
0x18000386d  jz      loc_1800040B7
0x180003873  xor     r12d, r12d
0x180003876  mov     [rsp+0E8h+var_C0], r12d
0x18000387b  mov     esi, 0C00E4102h
0x180003880  mov     [rsp+0E8h+var_B4], esi
0x180003884  mov     [rsp+0E8h+var_C8], rbx
0x180003889  mov     eax, [rbx]
0x18000388b  mov     [r14], eax
0x18000388e  add     rbx, 4
0x180003892  mov     [rsp+0E8h+var_C8], rbx
0x180003897  mov     r8d, 39314150h
0x18000389d  cmp     eax, r8d
0x1800038a0  jz      short loc_180003907
0x1800038a2  mov     dword ptr [rsp+0E8h+var_88], r12d
0x1800038a7  mov     dword ptr [rsp+0E8h+var_88], eax
0x1800038ab  cmp     al, 50h ; 'P'
0x1800038ad  jnz     short loc_1800038E1
0x1800038af  mov     ecx, eax
0x1800038b1  shr     ecx, 8
0x1800038b4  cmp     cl, 41h ; 'A'
0x1800038b7  jnz     short loc_1800038E1
0x1800038b9  mov     edx, eax
0x1800038bb  shr     edx, 10h
0x1800038be  lea     ecx, [rdx-30h]
0x1800038c1  cmp     cl, 9
0x1800038c4  ja      short loc_1800038E1
0x1800038c6  shr     eax, 18h
0x1800038c9  lea     ecx, [rax-30h]
0x1800038cc  cmp     cl, 9
0x1800038cf  ja      short loc_1800038E1
0x1800038d1  mov     cl, dl
0x1800038d3  shl     dl, 2
0x1800038d6  add     cl, dl
0x1800038d8  add     cl, cl
0x1800038da  sub     cl, 10h
0x1800038dd  add     cl, al
0x1800038df  jmp     short loc_1800038E3
0x1800038e1  xor     cl, cl
0x1800038e3  mov     [rsp+0E8h+var_98], 0
0x1800038eb  mov     [rsp+0E8h+var_98], r8d
0x1800038f0  cmp     cl, 13h
0x1800038f3  jbe     loc_18000404E
0x1800038f9  mov     esi, 0C00E4103h
0x1800038fe  mov     [rsp+0E8h+var_B4], esi
0x180003902  jmp     loc_18000404E
0x180003907  mov     edx, [rbx]
0x180003909  mov     [r14+4], edx
0x18000390d  lea     rcx, [rbx+4]
0x180003911  mov     rbx, rcx
0x180003914  mov     [rsp+0E8h+var_C8], rcx
0x180003919  mov     r8d, 800000h
0x18000391f  xor     edx, r8d
0x180003922  mov     [r14+4], edx
0x180003926  test    edx, 3F00FFF8h
0x18000392c  jnz     loc_18000404E
0x180003932  test    edx, edx
0x180003934  jns     short loc_180003953
0x180003936  mov     eax, [rcx]
0x180003938  mov     [r14+8], eax
0x18000393c  lea     rbx, [rcx+4]
0x180003940  mov     [rsp+0E8h+var_C8], rbx
0x180003945  mov     rcx, rbx
0x180003948  test    eax, 0FFFEFCC0h
0x18000394d  jnz     loc_18000404E
0x180003953  test    r8d, edx
0x180003956  jnz     short loc_18000396A
0x180003958  mov     eax, [rbx]
0x18000395a  mov     [r14+18h], eax
0x18000395e  lea     rbx, [rcx+4]
0x180003962  mov     [rsp+0E8h+var_C8], rbx
0x180003967  mov     rcx, rbx
0x18000396a  lea     r15, [r14+10h]
0x18000396e  bt      edx, 12h
0x180003972  jb      short loc_1800039C1
0x180003974  movzx   eax, word ptr [rbx]
0x180003977  shl     eax, 10h
0x18000397a  mov     [r14+0Ch], eax
0x18000397e  lea     rbx, [rcx+2]
0x180003982  mov     [rsp+0E8h+var_C8], rbx
0x180003987  cmp     dword ptr [r14+18h], 0
0x18000398c  jz      short loc_1800039B0
0x18000398e  lea     rdx, [rsp+0E8h+var_BC]
0x180003993  mov     rcx, rbx
0x180003996  call    VariableLengthSignedDecode
0x18000399b  mov     rbx, rax
0x18000399e  mov     [rsp+0E8h+var_C8], rax
0x1800039a3  mov     eax, [r14+18h]
0x1800039a7  sub     eax, [rsp+0E8h+var_BC]
0x1800039ab  mov     [r15], eax
0x1800039ae  jmp     short loc_1800039BE
0x1800039b0  mov     eax, [rbx]
0x1800039b2  mov     [r15], eax
0x1800039b5  add     rbx, 4
0x1800039b9  mov     [rsp+0E8h+var_C8], rbx
0x1800039be  mov     rcx, rbx
0x1800039c1  test    dword ptr [r14+4], 400000h
0x1800039c9  jnz     short loc_180003A02
0x1800039cb  cmp     dword ptr [r15], 0
0x1800039cf  jz      short loc_1800039F3
0x1800039d1  lea     rdx, [rsp+0E8h+var_BC]
0x1800039d6  mov     rcx, rbx
0x1800039d9  call    VariableLengthSignedDecode
0x1800039de  mov     rbx, rax
0x1800039e1  mov     [rsp+0E8h+var_C8], rax
0x1800039e6  mov     eax, [r15]
0x1800039e9  sub     eax, [rsp+0E8h+var_BC]
0x1800039ed  mov     [r14+14h], eax
0x1800039f1  jmp     short loc_180003A02
0x1800039f3  mov     eax, [rbx]
0x1800039f5  mov     [r14+14h], eax
0x1800039f9  lea     rbx, [rcx+4]
0x1800039fd  mov     [rsp+0E8h+var_C8], rbx
0x180003a02  lea     rdx, [r14+1Ch]
0x180003a06  mov     rcx, rbx
0x180003a09  call    VariableLengthUnsignedDecode
0x180003a0e  mov     [rsp+0E8h+var_C8], rax
0x180003a13  mov     ecx, [rax]
0x180003a15  mov     [r14+20h], ecx
0x180003a19  lea     rbx, [rax+4]
0x180003a1d  mov     [rsp+0E8h+var_C8], rbx
0x180003a22  test    dword ptr [r14+8], 10000h
0x180003a2a  jz      short loc_180003A54
0x180003a2c  mov     cl, [rbx]
0x180003a2e  lea     rdx, [rbx+1]
0x180003a32  mov     rbx, rdx
0x180003a35  mov     [rsp+0E8h+var_C8], rdx
0x180003a3a  cmp     cl, 1Fh
0x180003a3d  ja      loc_18000404E
0x180003a43  mov     r13d, 1
0x180003a49  mov     eax, r13d
0x180003a4c  shl     eax, cl
0x180003a4e  mov     [r14+38h], eax
0x180003a52  jmp     short loc_180003A5D
0x180003a54  mov     rdx, rbx
0x180003a57  mov     r13d, 1
0x180003a5d  movzx   eax, byte ptr [rbx]
0x180003a60  mov     [rsp+0E8h+var_60], eax
0x180003a67  mov     [r14+24h], eax
0x180003a6b  lea     rbx, [rdx+1]
0x180003a6f  mov     [rsp+0E8h+var_C8], rbx
0x180003a74  mov     r15d, eax
0x180003a77  lea     rdx, [rax+rax*8]
0x180003a7b  shl     rdx, 3
0x180003a7f  mov     rcx, [rsp+0E8h+arg_10]
0x180003a87  call    SubAllocate
0x180003a8c  mov     [r14+28h], rax
0x180003a90  test    rax, rax
0x180003a93  jnz     short loc_180003A9F
0x180003a95  mov     esi, 0Eh
0x180003a9a  jmp     loc_1800038FE
0x180003a9f  test    dword ptr [r14+4], 40000000h
0x180003aa7  jz      short loc_180003AC7
0x180003aa9  lea     rdx, ds:0[r15*8]
0x180003ab1  mov     rcx, [rsp+0E8h+arg_10]
0x180003ab9  call    SubAllocate
0x180003abe  mov     [r14+30h], rax
0x180003ac2  test    rax, rax
0x180003ac5  jz      short loc_180003A95
0x180003ac7  xor     eax, eax
0x180003ac9  mov     [rsp+0E8h+var_64], eax
0x180003ad0  cmp     eax, [rsp+0E8h+var_60]
0x180003ad7  jnb     loc_180004021
0x180003add  mov     [rsp+0E8h+var_50], rax
0x180003ae5  lea     r15, [rax+rax*8]
0x180003ae9  mov     r12, [r14+28h]
0x180003aed  lea     rdx, [rsp+0E8h+var_BC]
0x180003af2  mov     rcx, rbx
0x180003af5  call    VariableLengthSignedDecode
0x180003afa  mov     rbx, rax
0x180003afd  mov     [rsp+0E8h+var_C8], rax
0x180003b02  mov     edx, [r14+1Ch]
0x180003b06  add     edx, [rsp+0E8h+var_BC]
0x180003b0a  js      loc_180004049
0x180003b10  mov     [r12+r15*8+8], edx
0x180003b15  mov     eax, [rax]
0x180003b17  mov     [r12+r15*8+0Ch], eax
0x180003b1c  lea     rax, [rbx+4]
0x180003b20  mov     [rsp+0E8h+var_C8], rax
0x180003b25  movzx   ecx, byte ptr [rax]
0x180003b28  mov     [r12+r15*8+14h], ecx
0x180003b2d  add     rbx, 5
0x180003b31  mov     [rsp+0E8h+var_C8], rbx
0x180003b36  test    ecx, ecx
0x180003b38  jz      loc_180003C0E
0x180003b3e  mov     edx, ecx
0x180003b40  shl     rdx, 3
0x180003b44  mov     rcx, [rsp+0E8h+arg_10]
0x180003b4c  call    SubAllocate
0x180003b51  mov     [r12+r15*8+18h], rax
0x180003b56  test    rax, rax
0x180003b59  jnz     short loc_180003B69
0x180003b5b  mov     esi, 0Eh
0x180003b60  mov     [rsp+0E8h+var_B4], esi
0x180003b64  jmp     loc_180004049
0x180003b69  mov     dword ptr [rsp+0E8h+var_A8], 0
0x180003b71  xor     r8d, r8d
0x180003b74  mov     [rsp+0E8h+var_B8], r8d
0x180003b79  cmp     r8d, [r12+r15*8+14h]
0x180003b7e  jnb     loc_180003C0E
0x180003b84  lea     rdx, [rsp+0E8h+var_BC]
0x180003b89  mov     rcx, rbx
0x180003b8c  call    VariableLengthSignedDecode
0x180003b91  mov     [rsp+0E8h+var_C8], rax
0x180003b96  lea     rdx, [rsp+0E8h+var_A0]
0x180003b9b  mov     rcx, rax
0x180003b9e  call    VariableLengthUnsignedDecode
0x180003ba3  mov     rbx, rax
0x180003ba6  mov     [rsp+0E8h+var_C8], rax
0x180003bab  mov     r8d, [rsp+0E8h+var_B8]
0x180003bb0  mov     r9d, dword ptr [rsp+0E8h+var_A8]
0x180003bb5  mov     ecx, [rsp+0E8h+var_BC]
0x180003bb9  add     ecx, r9d
0x180003bbc  mov     rax, [r12+r15*8+18h]
0x180003bc1  mov     [rax+r8*8], ecx
0x180003bc5  mov     rax, [r12+r15*8+18h]
0x180003bca  mov     r10d, [rsp+0E8h+var_A0]
0x180003bcf  mov     [rax+r8*8+4], r10d
0x180003bd4  mov     ecx, [r12+r15*8+8]
0x180003bd9  mov     rax, [r12+r15*8+18h]
0x180003bde  mov     r11d, [rax+r8*8]
0x180003be2  cmp     r11, rcx
0x180003be5  ja      loc_180004049
0x180003beb  sub     rcx, r11
0x180003bee  cmp     r10, rcx
0x180003bf1  ja      loc_180004049
0x180003bf7  mov     eax, [rsp+0E8h+var_BC]
0x180003bfb  add     eax, r10d
0x180003bfe  add     r9d, eax
0x180003c01  mov     dword ptr [rsp+0E8h+var_A8], r9d
0x180003c06  add     r8d, r13d
0x180003c09  jmp     loc_180003B74
0x180003c0e  movzx   eax, byte ptr [rbx]
0x180003c11  mov     [r12+r15*8+20h], eax
0x180003c16  add     rbx, r13
0x180003c19  mov     [rsp+0E8h+var_C8], rbx
0x180003c1e  test    eax, eax
0x180003c20  jz      loc_180003D39
0x180003c26  lea     rdx, [rax+rax*2]
0x180003c2a  shl     rdx, 2
0x180003c2e  mov     rcx, [rsp+0E8h+arg_10]
0x180003c36  call    SubAllocate
0x180003c3b  mov     [r12+r15*8+28h], rax
0x180003c40  test    rax, rax
0x180003c43  jz      loc_180003B5B
0x180003c49  mov     dword ptr [rsp+0E8h+var_A8], 0
0x180003c51  xor     edx, edx
0x180003c53  mov     [rsp+0E8h+var_B8], edx
0x180003c57  cmp     edx, [r12+r15*8+20h]
0x180003c5c  jnb     loc_180003D39
0x180003c62  lea     rdx, [rsp+0E8h+var_BC]
0x180003c67  mov     rcx, rbx
0x180003c6a  call    VariableLengthSignedDecode
0x180003c6f  mov     [rsp+0E8h+var_C8], rax
0x180003c74  lea     rdx, [rsp+0E8h+var_9C]
0x180003c79  mov     rcx, rax
0x180003c7c  call    VariableLengthSignedDecode
0x180003c81  mov     [rsp+0E8h+var_C8], rax
0x180003c86  lea     rdx, [rsp+0E8h+var_A0]
0x180003c8b  mov     rcx, rax
0x180003c8e  call    VariableLengthUnsignedDecode
0x180003c93  mov     rbx, rax
0x180003c96  mov     [rsp+0E8h+var_C8], rax
0x180003c9b  mov     edx, [rsp+0E8h+var_B8]
0x180003c9f  lea     r11, [rdx+rdx*2]
0x180003ca3  mov     r8d, dword ptr [rsp+0E8h+var_A8]
0x180003ca8  mov     r9d, [rsp+0E8h+var_BC]
0x180003cad  lea     ecx, [r8+r9]
0x180003cb1  mov     rax, [r12+r15*8+28h]
0x180003cb6  mov     [rax+r11*4], ecx
0x180003cba  mov     ecx, [rsp+0E8h+var_9C]
0x180003cbe  add     ecx, r8d
0x180003cc1  add     ecx, r9d
0x180003cc4  mov     rax, [r12+r15*8+28h]
0x180003cc9  mov     [rax+r11*4+8], ecx
0x180003cce  mov     rax, [r12+r15*8+28h]
0x180003cd3  mov     r10d, [rsp+0E8h+var_A0]
0x180003cd8  mov     [rax+r11*4+4], r10d
  ... truncated ...
```
