# sub_1800CFAF0

- ea: `0x1800cfaf0`
- end: `0x1800d04f9`
- name: `sub_1800CFAF0`
- size: `2569`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: ``

## callers

- `0x18009eca0`

## callees

- `0x180073f30`
- `0x180098d54`
- `0x180098e08`
- `0x180098e44`
- `0x180098ea4`
- `0x1800a99b8`
- `0x1800a9a2c`
- `0x1800ae0f0`
- `0x1800bc3c0`
- `0x1800bc44c`
- `0x1800bc790`
- `0x1800c7ba0`
- `0x1800cd2a8`
- `0x1800cecc4`
- `0x1800cf4b4`
- `0x1800cfaf0`
- `0x1800d054c`
- `0x1800d1598`
- `0x1800d17e8`
- `0x1800d2a50`
- `0x1800d2c98`
- `0x1800d2d50`
- `0x1801d4f70`
- `0x1801d5188`
- `0x1801d6c50`

## import_xrefs

- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800cfda3`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800cfda3`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800d0065`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800d0065`

## string_xrefs

- `0x1800d031a`: `.TempBogusIndexName`
- `0x1800d03b7`: `.TempBogusIndexName`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall sub_1800CFAF0(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        _WORD *a4,
        int a5,
        __int64 a6,
        _WORD *a7,
        int a8,
        unsigned __int8 *a9,
        int a10,
        int a11,
        int a12,
        char a13,
        int *a14)
{
  __int64 v17; // r15
  __int64 v18; // r11
  __int64 v19; // r13
  int v20; // ecx
  int v21; // eax
  int v22; // ebx
  __int64 v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r9
  int v27; // edx
  int v28; // ecx
  __int64 v29; // r8
  __int64 v30; // r13
  __int64 v31; // rax
  __int64 v32; // r12
  int v33; // edi
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rdx
  _DWORD *v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rbx
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rdx
  int v47; // eax
  __int64 v48; // r8
  _DWORD *v49; // rcx
  __int64 v50; // r9
  __int64 v51; // rdx
  __int64 v52; // r13
  __int64 v53; // rcx
  __int64 v54; // rax
  unsigned __int64 v55; // rdx
  __int64 v56; // r8
  unsigned __int64 v57; // rcx
  __int64 v58; // rcx
  unsigned __int8 (__fastcall *v59)(__int64); // rdi
  char v60; // bl
  __int64 v61; // r13
  int v62; // ebx
  int v63; // eax
  int *v64; // rdi
  __int64 v65; // r9
  __int64 v66; // rcx
  int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // rax
  bool v70; // zf
  __int64 v71; // r8
  __int64 v72; // rcx
  int v73; // eax
  _DWORD *v74; // rcx
  __int64 v75; // r9
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r8
  __int64 v79; // rcx
  int v80; // eax
  __int64 v81; // rdx
  _DWORD *v82; // rcx
  __int64 v83; // r10
  __int64 v84; // r8
  char v85; // al
  __int64 v86; // r8
  char v87; // cl
  char v88; // dl
  __int64 v89; // rdi
  __int64 v90; // rbx
  __int64 v91; // rdx
  __int64 v92; // rcx
  _WORD *v93; // r8
  __int64 v94; // rbx
  __int64 result; // rax
  _WORD *v96; // [rsp+20h] [rbp-C1h]
  char v97; // [rsp+50h] [rbp-91h]
  int v98; // [rsp+54h] [rbp-8Dh] BYREF
  __int64 v99; // [rsp+58h] [rbp-89h]
  __int64 v100; // [rsp+60h] [rbp-81h]
  __int64 v101; // [rsp+68h] [rbp-79h]
  int v102; // [rsp+70h] [rbp-71h]
  __int64 v103; // [rsp+78h] [rbp-69h]
  __int64 v104; // [rsp+80h] [rbp-61h]
  __int64 v105; // [rsp+88h] [rbp-59h]
  _WORD *v106; // [rsp+90h] [rbp-51h]
  void (__fastcall ***v107)(_QWORD, __int64); // [rsp+98h] [rbp-49h]
  __int64 v108; // [rsp+A0h] [rbp-41h]
  __int64 v109; // [rsp+A8h] [rbp-39h] BYREF
  int v110; // [rsp+B0h] [rbp-31h]
  int v111; // [rsp+B4h] [rbp-2Dh]
  int v112; // [rsp+B8h] [rbp-29h]
  int v113; // [rsp+C8h] [rbp-19h]

  v103 = a2;
  v106 = a7;
  v108 = a1;
  ++*(_DWORD *)(a1 + 164);
  v97 = 0;
  v17 = 0;
  v100 = 0;
  v99 = 0;
  v107 = 0;
  v101 = 0;
  v104 = *(_QWORD *)(a2 + 16);
  sub_1800D2D50(a1, 1, a14);
  if ( (*(_BYTE *)a14 & 8) == 0 )
  {
    sub_1800D17E8(a1, a14);
    if ( (*(_BYTE *)a14 & 8) == 0 )
    {
      sub_1800BC3C0(v104, 1, a14);
      if ( (*(_BYTE *)a14 & 8) == 0 )
      {
        v97 = 1;
        if ( !(unsigned int)sub_180073F30(v104 + 184, a1) )
          sub_1800D2C98(a1, v18);
      }
    }
  }
  if ( (*(_BYTE *)a14 & 8) != 0 )
  {
    v19 = v103;
  }
  else
  {
    *a9 &= 1u;
    a9[1] = a9[1] & 0xF8 | 1;
    v96 = a4;
    v19 = v103;
    v99 = sub_1800CECC4(a1, v103, a3, a9, v96, 0, 0, a14, 1);
  }
  v20 = *a14;
  LOBYTE(v21) = *a14;
  if ( (v21 & 8) == 0 && a10 == 1 )
  {
    v22 = 0;
    v23 = 0;
    do
    {
      v24 = *(_QWORD *)(v99 + 16);
      LOBYTE(v21) = v20;
      if ( v22 >= *(_DWORD *)(v24 + 48) )
        break;
      v25 = *(int *)(v23 + *(_QWORD *)(v24 + 40));
      if ( (unsigned int)v25 >= 0x100 )
        v26 = 0;
      else
        v26 = *(_QWORD *)(a1 + 8 * v25 + 264);
      if ( (*(_BYTE *)(v26 + 46) & 2) != 0 || (*(_BYTE *)(v26 + 46) & 4) != 0 )
        sub_180098E44((_DWORD)a14, -1048, -8235, *(_QWORD *)(v26 + 8), 0);
      ++v22;
      v23 += 8;
      v21 = *a14;
      v20 = *a14;
    }
    while ( (*a14 & 8) == 0 );
    v17 = 0;
    v19 = v103;
  }
  if ( (v21 & 8) != 0 )
  {
    v30 = v101;
  }
  else
  {
    sub_1800CD2A8(a1, v19);
    v27 = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 376LL);
    v28 = *(_DWORD *)(a1 + 8);
    v109 = *(_QWORD *)a1;
    v110 = v28;
    v111 = v27;
    v112 = -1;
    if ( a6 )
    {
      v29 = -1;
      do
        ++v29;
      while ( *(_WORD *)(a6 + 2 * v29) );
    }
    else
    {
      LODWORD(v29) = 0;
    }
    if ( (unsigned int)sub_1800C7BA0(&v109, a6, (unsigned int)(2 * v29)) )
    {
      v31 = sub_1800AE0F0(v19, a6, 2, (_DWORD)a14, 0, 0);
      v107 = (void (__fastcall ***)(_QWORD, __int64))v31;
      if ( (*(_BYTE *)a14 & 8) != 0 )
      {
        v30 = 0;
      }
      else
      {
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 120LL))(v31);
        v101 = v30;
      }
    }
    else
    {
      v30 = a1;
      v101 = a1;
    }
  }
  v32 = 0;
  if ( (*(_BYTE *)a14 & 8) != 0 )
  {
LABEL_93:
    v61 = v99;
    goto LABEL_94;
  }
  v33 = 0;
  if ( v106 && *v106 )
  {
    v102 = 0;
    v34 = Mso20Win32Client_52497(16, 2);
    v105 = v34;
    if ( v34 )
    {
      v35 = 10;
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 48) + 120LL) == 1 )
        v35 = 255;
      v32 = sub_1800A99B8(v34, v35, (__int64)a14);
    }
    if ( v32 )
      v102 = 1;
    else
      sub_180098E08(a14, 4294966285LL);
    if ( (*(_BYTE *)a14 & 8) == 0 )
    {
      sub_1800D2A50(v30, v106, v32, 0, 0, a14);
      if ( (*(_BYTE *)a14 & 1) == 0 && a14[1] == -1406 )
        sub_180098EA4(a14, 4294965892LL);
      if ( (*(_BYTE *)a14 & 8) == 0 )
      {
        v36 = v99;
        if ( *(_DWORD *)(v32 + 8) == *(_DWORD *)(*(_QWORD *)(v99 + 16) + 48LL) )
        {
LABEL_51:
          if ( (*(_BYTE *)a14 & 8) == 0 )
          {
            if ( v30 == a1 )
            {
              v37 = *(_QWORD *)(v36 + 16);
              v38 = *(_DWORD *)(v32 + 8);
              if ( v38 == *(_DWORD *)(v37 + 48) )
              {
                v39 = 0;
                if ( v38 <= 0 )
                {
LABEL_58:
                  sub_180098E08(a14, 4294965889LL);
                }
                else
                {
                  v40 = *(_DWORD **)(v37 + 40);
                  v41 = *(_QWORD *)v32 - (_QWORD)v40;
                  while ( *(_DWORD *)((char *)v40 + v41) == *v40 )
                  {
                    ++v39;
                    v40 += 2;
                    if ( v39 >= *(int *)(v32 + 8) )
                      goto LABEL_58;
                  }
                }
              }
            }
            if ( (*(_BYTE *)a14 & 8) == 0 && !a13 )
            {
              v42 = 0;
              while ( 1 )
              {
                v43 = v33;
                v44 = v42;
                ++v33;
                ++v42;
                if ( v43 < 0
                  || v43 >= *(_DWORD *)(v30 + 28)
                  || (v45 = *(int *)(v30 + 4 * v44 + 2560), (_DWORD)v45 == -1) )
                {
                  v17 = 0;
                }
                else
                {
                  v17 = *(_QWORD *)(v30 + 8 * v45 + 2304);
                }
                v100 = v17;
                if ( !v17 )
                  break;
                v46 = *(_QWORD *)(v17 + 16);
                v47 = *(_DWORD *)(v32 + 8);
                if ( v47 == *(_DWORD *)(v46 + 48) )
                {
                  v48 = 0;
                  if ( v47 <= 0 )
                  {
LABEL_73:
                    if ( *(_DWORD *)(v46 + 32) )
                    {
                      if ( (*(_BYTE *)(v46 + 5) & 1) != 0 )
                      {
                        sub_180098D54(a14);
                        *a14 = 1;
                        v98 = 0;
                        v51 = *(_QWORD *)(v99 + 16);
                        if ( *(int *)(v51 + 48) > 0 )
                        {
                          v52 = 0;
                          while ( 1 )
                          {
                            v53 = *(_QWORD *)(*(_QWORD *)(v17 + 16) + 40LL);
                            v54 = *(_QWORD *)(v51 + 40);
                            if ( *(int *)(v53 + v52) < 0 || (v55 = *(int *)(v53 + v52), v55 > 0xFF) )
                              v56 = 0;
                            else
                              v56 = *(_QWORD *)(v101 + 8 * v55 + 264);
                            if ( *(int *)(v54 + v52) < 0 || (v57 = *(int *)(v54 + v52), v57 > 0xFF) )
                              v58 = 0;
                            else
                              v58 = *(_QWORD *)(a1 + 8 * v57 + 264);
                            v105 = v58;
                            v59 = *(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v58 + 40LL);
                            v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 40LL))(v56);
                            if ( v60 != v59(v105) )
                              break;
                            ++v98;
                            v52 += 8;
                            v51 = *(_QWORD *)(v99 + 16);
                            if ( v98 >= *(_DWORD *)(v51 + 48) )
                              goto LABEL_90;
                          }
                          sub_180098E08(a14, 4294963736LL);
                          v17 = 0;
                          v100 = 0;
                        }
                        break;
                      }
                      sub_180098E08(a14, 4294965774LL);
                    }
                  }
                  else
                  {
                    v49 = *(_DWORD **)(v46 + 40);
                    v50 = *(_QWORD *)v32 - (_QWORD)v49;
                    while ( *(_DWORD *)((char *)v49 + v50) == *v49 )
                    {
                      ++v48;
                      v49 += 2;
                      if ( v48 >= *(int *)(v32 + 8) )
                        goto LABEL_73;
                    }
                  }
                }
              }
            }
          }
LABEL_90:
          if ( v102 && v32 )
          {
            sub_1800A9A2C((_QWORD *)v32);
            Mso20Win32Client_53248(v32);
          }
          goto LABEL_93;
        }
        sub_180098E08(a14, 4294966293LL);
      }
    }
    v36 = v99;
    goto LABEL_51;
  }
  v66 = 0;
  do
  {
    v67 = v33;
    v68 = v66;
    ++v33;
    ++v66;
    if ( v67 < 0 || v67 >= *(_DWORD *)(v30 + 28) || (v69 = *(int *)(v30 + 4 * v68 + 2560), (_DWORD)v69 == -1) )
      v17 = 0;
    else
      v17 = *(_QWORD *)(v30 + 8 * v69 + 2304);
    v100 = v17;
    if ( !v17 )
    {
      sub_180098E08(a14, 4294965892LL);
      goto LABEL_93;
    }
  }
  while ( (*(_BYTE *)(v17 + 60) & 1) == 0 );
  v70 = v30 == a1;
  v61 = v99;
  if ( v70 )
  {
    v71 = *(_QWORD *)(v17 + 16);
    v72 = *(_QWORD *)(v99 + 16);
    v73 = *(_DWORD *)(v71 + 48);
    if ( v73 == *(_DWORD *)(v72 + 48) )
    {
      if ( v73 <= 0 )
      {
LABEL_123:
        sub_180098E08(a14, 4294965889LL);
        v17 = 0;
        v100 = 0;
      }
      else
      {
        v74 = *(_DWORD **)(v72 + 40);
        v75 = *(int *)(v71 + 48);
        v76 = 0;
        v77 = *(_QWORD *)(v71 + 40) - (_QWORD)v74;
        while ( *(_DWORD *)((char *)v74 + v77) == *v74 )
        {
          ++v76;
          v74 += 2;
          if ( v76 >= v75 )
            goto LABEL_123;
        }
      }
    }
  }
LABEL_94:
  if ( (*(_BYTE *)a14 & 8) == 0 )
  {
    if ( !v17 && !a13 )
      sub_180098E08(a14, 4294965774LL);
    if ( (*(_BYTE *)a14 & 8) == 0
      && !a13
      && ((*(_BYTE *)(*(_QWORD *)(v17 + 16) + 5LL) ^ *(_BYTE *)(*(_QWORD *)(v61 + 16) + 5LL)) & 0x80u) != 0 )
    {
      sub_180098E08(a14, 4294965774LL);
    }
  }
  if ( (*(_BYTE *)a14 & 8) != 0 )
    goto LABEL_147;
  v62 = 0;
  v63 = *(_DWORD *)(a1 + 28);
  if ( v63 > 0 )
  {
    v64 = (int *)(a1 + 2560);
    do
    {
      if ( v62 < 0 || v62 >= v63 || *v64 == -1 )
        v65 = 0;
      else
        v65 = *(_QWORD *)(a1 + 8LL * *v64 + 2304);
      if ( *(_BYTE *)(v65 + 61) == 2 && *(_DWORD *)(v65 + 68) == *(_DWORD *)(v101 + 56) )
      {
        v78 = *(_QWORD *)(v65 + 16);
        v79 = *(_QWORD *)(v61 + 16);
        v80 = *(_DWORD *)(v78 + 48);
        if ( v80 == *(_DWORD *)(v79 + 48) )
        {
          v81 = 0;
          if ( v80 <= 0 )
          {
LABEL_133:
            if ( *(_DWORD *)(v65 + 72) != 4 && a10 != 4 && *(_DWORD *)(v65 + 72) != a10
              || *(_DWORD *)(v65 + 76) != 4 && a11 != 4 && *(_DWORD *)(v65 + 76) != a11 )
            {
              sub_180098E44((_DWORD)a14, -1528, -8302, *(_QWORD *)v65, 0);
            }
          }
          else
          {
            v82 = *(_DWORD **)(v79 + 40);
            v83 = *(int *)(v78 + 48);
            v84 = *(_QWORD *)(v78 + 40) - (_QWORD)v82;
            while ( *(_DWORD *)((char *)v82 + v84) == *v82 )
            {
              ++v81;
              v82 += 2;
              if ( v81 >= v83 )
                goto LABEL_133;
            }
          }
        }
      }
      ++v62;
      ++v64;
      v63 = *(_DWORD *)(a1 + 28);
    }
    while ( v62 < v63 );
    v17 = v100;
  }
  if ( (*(_BYTE *)a14 & 8) != 0 )
  {
LABEL_147:
    v90 = v101;
    v89 = v103;
  }
  else
  {
    LOWORD(v98) = 0;
    if ( a13 )
    {
      v85 = BYTE1(v98) & 0xF8 | 1;
    }
    else
    {
      v86 = *(_QWORD *)(v17 + 16);
      LOBYTE(v98) = *(_BYTE *)(v86 + 5) & 1 | (2 * (*(_BYTE *)(v86 + 5) & 0xCE));
      v87 = BYTE1(v98) & 0xFE | (*(_BYTE *)(v86 + 5) >> 7);
      v88 = v87 ^ (v87 ^ (2 * *(_BYTE *)(v86 + 6))) & 2;
      v85 = v88 ^ (v88 ^ (2 * *(_BYTE *)(v86 + 6))) & 4;
    }
    BYTE1(v98) = v85;
    v89 = v103;
    v90 = v101;
    v17 = sub_1800CECC4(v101, v103, L".TempBogusIndexName", (unsigned __int8 *)&v98, v106, 0, 0, a14, 2);
  }
  if ( (*(_BYTE *)a14 & 8) == 0 )
  {
    v91 = 2;
    v92 = *(unsigned int *)(v17 + 56);
    LODWORD(v109) = 7471150;
    if ( (_DWORD)v92 )
    {
      v93 = (_WORD *)&v109 + 2;
      do
      {
        if ( (unsigned int)v91 >= 0xA )
          break;
        *v93 = (v92 & 0xF) + 65;
        v91 = (unsigned int)(v91 + 1);
        ++v93;
        v92 = (unsigned int)((int)v92 >> 4);
      }
      while ( (_DWORD)v92 );
    }
    if ( (unsigned __int64)(int)v91 >= 0xA )
    {
      HIWORD(v112) = 0;
    }
    else
    {
      if ( (unsigned __int64)(2LL * (int)v91) >= 0x14 )
        sub_1801D5188(v92, v91);
      *((_WORD *)&v109 + (int)v91) = 0;
    }
    sub_1800CF4B4(v90, v89, (__int64)L".TempBogusIndexName", &v109, a14, 0);
    if ( (*(_BYTE *)a14 & 8) == 0 )
    {
      *(_BYTE *)(v17 + 61) = 1;
      *(_DWORD *)(v17 + 68) = *(_DWORD *)(a1 + 56);
      *(_DWORD *)(v17 + 64) = *(_DWORD *)(v61 + 56);
      *(_DWORD *)(v17 + 72) = a10;
      *(_DWORD *)(v17 + 76) = a11;
      *(_DWORD *)(v17 + 80) = 1;
      *(_BYTE *)(v61 + 61) = (a13 != 0) + 2;
      *(_DWORD *)(v61 + 68) = *(_DWORD *)(v90 + 56);
      *(_DWORD *)(v61 + 64) = *(_DWORD *)(v17 + 56);
      *(_DWORD *)(v61 + 72) = a10;
      *(_DWORD *)(v61 + 76) = a11;
      *(_DWORD *)(v61 + 80) = 1;
      if ( (*(_BYTE *)a14 & 8) == 0 )
        sub_1800D054C(a1, v89, v90, v17, v61, (__int64)a14);
    }
  }
  if ( v97 )
  {
    v94 = v104;
    if ( (*(_BYTE *)a14 & 8) != 0 || (sub_1800BC44C(v104, a14, 0), (*(_BYTE *)a14 & 8) != 0) )
    {
      LODWORD(v109) = 1;
      v113 = 0;
      sub_1800BC790(v94, &v109, 0);
      if ( (v109 & 0xFFFFFFFE) != 0 )
        sub_180098D54(&v109);
    }
    else if ( v107 )
    {
      (**v107)(v107, 1);
    }
  }
  result = sub_1800D1598(a1, v89);
  --*(_DWORD *)(a1 + 164);
  return result;
}

```

## disassembly

```asm
0x1800cfaf0  push    rbp
0x1800cfaf2  push    rbx
0x1800cfaf3  push    rsi
0x1800cfaf4  push    rdi
0x1800cfaf5  push    r12
0x1800cfaf7  push    r13
0x1800cfaf9  push    r14
0x1800cfafb  push    r15
0x1800cfafd  lea     rbp, [rsp-7]
0x1800cfb02  sub     rsp, 0E8h
0x1800cfb09  mov     rax, cs:__security_cookie
0x1800cfb10  xor     rax, rsp
0x1800cfb13  mov     [rbp+3Fh+var_50], rax
0x1800cfb17  mov     r13, r9
0x1800cfb1a  mov     rdi, r8
0x1800cfb1d  mov     [rbp+3Fh+var_A8], rdx
0x1800cfb21  mov     r14, rcx
0x1800cfb24  mov     rbx, [rbp+3Fh+arg_40]
0x1800cfb2b  mov     rsi, [rbp+3Fh+arg_68]
0x1800cfb32  mov     r12, [rbp+3Fh+arg_28]
0x1800cfb36  mov     rcx, [rbp+3Fh+arg_30]
0x1800cfb3a  mov     [rbp+3Fh+var_90], rcx
0x1800cfb3e  mov     [rbp+3Fh+var_80], r14
0x1800cfb42  inc     dword ptr [r14+0A4h]
0x1800cfb49  xor     ecx, ecx
0x1800cfb4b  mov     [rsp+120h+var_D0], cl
0x1800cfb4f  mov     r15d, ecx
0x1800cfb52  mov     [rsp+120h+var_C0], rcx
0x1800cfb57  mov     [rsp+120h+var_C8], rcx
0x1800cfb5c  mov     [rbp+3Fh+var_88], rcx
0x1800cfb60  mov     [rbp+3Fh+var_B8], rcx
0x1800cfb64  mov     rax, [rdx+10h]
0x1800cfb68  mov     [rbp+3Fh+var_A0], rax
0x1800cfb6c  mov     r8, rsi
0x1800cfb6f  lea     edx, [rcx+1]
0x1800cfb72  mov     rcx, r14
0x1800cfb75  call    sub_1800D2D50
0x1800cfb7a  test    byte ptr [rsi], 8
0x1800cfb7d  jnz     short loc_1800CFBCD
0x1800cfb7f  mov     rdx, rsi
0x1800cfb82  mov     rcx, r14
0x1800cfb85  call    sub_1800D17E8
0x1800cfb8a  test    byte ptr [rsi], 8
0x1800cfb8d  jnz     short loc_1800CFBCD
0x1800cfb8f  mov     r8, rsi
0x1800cfb92  lea     edx, [r15+1]
0x1800cfb96  mov     rcx, [rbp+3Fh+var_A0]
0x1800cfb9a  call    sub_1800BC3C0
0x1800cfb9f  test    byte ptr [rsi], 8
0x1800cfba2  jnz     short loc_1800CFBCD
0x1800cfba4  mov     [rsp+120h+var_D0], 1
0x1800cfba9  mov     r11, [rbp+3Fh+var_A0]
0x1800cfbad  lea     rcx, [r11+0B8h]
0x1800cfbb4  mov     rdx, r14
0x1800cfbb7  call    sub_180073F30
0x1800cfbbc  xor     ecx, ecx
0x1800cfbbe  test    eax, eax
0x1800cfbc0  jnz     short loc_1800CFBCF
0x1800cfbc2  mov     rdx, r11
0x1800cfbc5  mov     rcx, r14
0x1800cfbc8  call    sub_1800D2C98
0x1800cfbcd  xor     ecx, ecx
0x1800cfbcf  test    byte ptr [rsi], 8
0x1800cfbd2  jnz     short loc_1800CFC18
0x1800cfbd4  and     byte ptr [rbx], 1
0x1800cfbd7  mov     al, [rbx+1]
0x1800cfbda  and     al, 0F9h
0x1800cfbdc  or      al, 1
0x1800cfbde  mov     [rbx+1], al
0x1800cfbe1  mov     [rsp+120h+var_E0], 1
0x1800cfbe9  mov     [rsp+120h+var_E8], rsi
0x1800cfbee  mov     [rsp+120h+var_F0], ecx
0x1800cfbf2  mov     [rsp+120h+var_F8], rcx
0x1800cfbf7  mov     [rsp+120h+var_100], r13
0x1800cfbfc  mov     r9, rbx
0x1800cfbff  mov     r8, rdi
0x1800cfc02  mov     r13, [rbp+3Fh+var_A8]
0x1800cfc06  mov     rdx, r13
0x1800cfc09  mov     rcx, r14
0x1800cfc0c  call    sub_1800CECC4
0x1800cfc11  mov     [rsp+120h+var_C8], rax
0x1800cfc16  jmp     short loc_1800CFC1C
0x1800cfc18  mov     r13, [rbp+3Fh+var_A8]
0x1800cfc1c  mov     ecx, [rsi]
0x1800cfc1e  mov     eax, ecx
0x1800cfc20  mov     r8d, 0FFh
0x1800cfc26  test    cl, 8
0x1800cfc29  jnz     loc_1800CFCBF
0x1800cfc2f  cmp     [rbp+3Fh+arg_48], 1
0x1800cfc36  jnz     loc_1800CFCBF
0x1800cfc3c  xor     r13d, r13d
0x1800cfc3f  mov     ebx, r13d
0x1800cfc42  mov     edi, r13d
0x1800cfc45  mov     r15, [rsp+120h+var_C8]
0x1800cfc4a  mov     rdx, [r15+10h]
0x1800cfc4e  mov     eax, ecx
0x1800cfc50  cmp     ebx, [rdx+30h]
0x1800cfc53  jge     short loc_1800CFCB8
0x1800cfc55  mov     rax, [rdx+28h]
0x1800cfc59  movsxd  rcx, dword ptr [rdi+rax]
0x1800cfc5d  test    ecx, ecx
0x1800cfc5f  js      short loc_1800CFC70
0x1800cfc61  cmp     ecx, r8d
0x1800cfc64  ja      short loc_1800CFC70
0x1800cfc66  mov     r9, [r14+rcx*8+108h]
0x1800cfc6e  jmp     short loc_1800CFC73
0x1800cfc70  mov     r9, r13
0x1800cfc73  movzx   ecx, byte ptr [r9+2Eh]
0x1800cfc78  mov     eax, ecx
0x1800cfc7a  shr     eax, 1
0x1800cfc7c  test    al, 1
0x1800cfc7e  jnz     short loc_1800CFC88
0x1800cfc80  shr     ecx, 2
0x1800cfc83  test    cl, 1
0x1800cfc86  jz      short loc_1800CFCAA
0x1800cfc88  mov     [rsp+120h+var_100], r13
0x1800cfc8d  mov     r9, [r9+8]
0x1800cfc91  mov     edx, 0FFFFFBE8h
0x1800cfc96  mov     r8d, 0FFFFDFD5h
0x1800cfc9c  mov     rcx, rsi
0x1800cfc9f  call    sub_180098E44
0x1800cfca4  mov     r8d, 0FFh
0x1800cfcaa  inc     ebx
0x1800cfcac  add     rdi, 8
0x1800cfcb0  mov     eax, [rsi]
0x1800cfcb2  mov     ecx, eax
0x1800cfcb4  test    al, 8
0x1800cfcb6  jz      short loc_1800CFC4A
0x1800cfcb8  mov     r15, r13
0x1800cfcbb  mov     r13, [rbp+3Fh+var_A8]
0x1800cfcbf  test    al, 8
0x1800cfcc1  jnz     loc_1800CFD68
0x1800cfcc7  mov     rdx, r13
0x1800cfcca  mov     rcx, r14
0x1800cfccd  call    sub_1800CD2A8
0x1800cfcd2  mov     rax, [r14+30h]
0x1800cfcd6  mov     edx, [rax+178h]
0x1800cfcdc  mov     ecx, [r14+8]
0x1800cfce0  mov     rax, [r14]
0x1800cfce3  mov     [rbp+3Fh+var_78], rax
0x1800cfce7  mov     [rbp+3Fh+var_70], ecx
0x1800cfcea  mov     [rbp+3Fh+var_6C], edx
0x1800cfced  mov     [rbp+3Fh+var_68], 0FFFFFFFFh
0x1800cfcf4  xor     ebx, ebx
0x1800cfcf6  test    r12, r12
0x1800cfcf9  jz      short loc_1800CFD0B
0x1800cfcfb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800cfcff  inc     r8
0x1800cfd02  cmp     [r12+r8*2], bx
0x1800cfd07  jnz     short loc_1800CFCFF
0x1800cfd09  jmp     short loc_1800CFD0E
0x1800cfd0b  mov     r8d, ebx
0x1800cfd0e  add     r8d, r8d
0x1800cfd11  mov     rdx, r12
0x1800cfd14  lea     rcx, [rbp+3Fh+var_78]
0x1800cfd18  call    sub_1800C7BA0
0x1800cfd1d  test    eax, eax
0x1800cfd1f  jnz     short loc_1800CFD2A
0x1800cfd21  mov     r13, r14
0x1800cfd24  mov     [rbp+3Fh+var_B8], r14
0x1800cfd28  jmp     short loc_1800CFD71
0x1800cfd2a  mov     dword ptr [rsp+120h+var_F8], ebx
0x1800cfd2e  mov     byte ptr [rsp+120h+var_100], bl
0x1800cfd32  mov     r9, rsi
0x1800cfd35  mov     r8d, 2
0x1800cfd3b  mov     rdx, r12
0x1800cfd3e  mov     rcx, r13
0x1800cfd41  call    sub_1800AE0F0
0x1800cfd46  mov     rcx, rax
0x1800cfd49  mov     [rbp+3Fh+var_88], rax
0x1800cfd4d  test    byte ptr [rsi], 8
0x1800cfd50  jnz     short loc_1800CFD6E
0x1800cfd52  mov     rax, [rax]
0x1800cfd55  mov     rax, [rax+78h]
0x1800cfd59  call    cs:__guard_dispatch_icall_fptr
0x1800cfd5f  mov     r13, rax
0x1800cfd62  mov     [rbp+3Fh+var_B8], rax
0x1800cfd66  jmp     short loc_1800CFD71
0x1800cfd68  mov     r13, [rbp+3Fh+var_B8]
0x1800cfd6c  jmp     short loc_1800CFD71
0x1800cfd6e  mov     r13, rbx
0x1800cfd71  xor     r12d, r12d
0x1800cfd74  test    byte ptr [rsi], 8
0x1800cfd77  jnz     loc_1800D006E
0x1800cfd7d  mov     edi, r12d
0x1800cfd80  mov     rbx, [rbp+3Fh+var_90]
0x1800cfd84  test    rbx, rbx
0x1800cfd87  jz      loc_1800D0114
0x1800cfd8d  cmp     [rbx], r12w
0x1800cfd91  jz      loc_1800D0114
0x1800cfd97  mov     [rbp+3Fh+var_B0], r12d
0x1800cfd9b  lea     edx, [r12+2]
0x1800cfda0  lea     ecx, [rdx+0Eh]
0x1800cfda3  call    cs:Mso20Win32Client_52497
0x1800cfda9  mov     rcx, rax
0x1800cfdac  mov     [rbp+3Fh+var_98], rax
0x1800cfdb0  test    rax, rax
0x1800cfdb3  jz      short loc_1800CFDD5
0x1800cfdb5  mov     rax, [r14+30h]
0x1800cfdb9  lea     edx, [r12+0Ah]
0x1800cfdbe  cmp     dword ptr [rax+78h], 1
0x1800cfdc2  mov     eax, 0FFh
0x1800cfdc7  cmovz   edx, eax
0x1800cfdca  mov     r8, rsi
0x1800cfdcd  call    sub_1800A99B8
0x1800cfdd2  mov     r12, rax
0x1800cfdd5  xor     eax, eax
0x1800cfdd7  test    r12, r12
0x1800cfdda  jnz     short loc_1800CFDED
0x1800cfddc  mov     edx, 0FFFFFC0Dh
0x1800cfde1  mov     rcx, rsi
0x1800cfde4  call    sub_180098E08
0x1800cfde9  xor     eax, eax
0x1800cfdeb  jmp     short loc_1800CFDF4
0x1800cfded  mov     [rbp+3Fh+var_B0], 1
0x1800cfdf4  test    byte ptr [rsi], 8
0x1800cfdf7  jnz     short loc_1800CFE53
0x1800cfdf9  mov     [rsp+120h+var_F8], rsi
0x1800cfdfe  mov     byte ptr [rsp+120h+var_100], al
0x1800cfe02  xor     r9d, r9d
0x1800cfe05  mov     r8, r12
0x1800cfe08  mov     rdx, rbx
0x1800cfe0b  mov     rcx, r13
0x1800cfe0e  call    sub_1800D2A50
0x1800cfe13  test    byte ptr [rsi], 1
0x1800cfe16  jnz     short loc_1800CFE2E
0x1800cfe18  cmp     dword ptr [rsi+4], 0FFFFFA82h
0x1800cfe1f  jnz     short loc_1800CFE2E
0x1800cfe21  mov     edx, 0FFFFFA84h
0x1800cfe26  mov     rcx, rsi
0x1800cfe29  call    sub_180098EA4
0x1800cfe2e  test    byte ptr [rsi], 8
0x1800cfe31  jnz     short loc_1800CFE53
0x1800cfe33  mov     rdx, [rsp+120h+var_C8]
0x1800cfe38  mov     rax, [rdx+10h]
0x1800cfe3c  mov     ecx, [rax+30h]
0x1800cfe3f  cmp     [r12+8], ecx
0x1800cfe44  jz      short loc_1800CFE58
0x1800cfe46  mov     edx, 0FFFFFC15h
0x1800cfe4b  mov     rcx, rsi
0x1800cfe4e  call    sub_180098E08
0x1800cfe53  mov     rdx, [rsp+120h+var_C8]
0x1800cfe58  test    byte ptr [rsi], 8
0x1800cfe5b  jnz     loc_1800D004C
0x1800cfe61  cmp     r13, r14
0x1800cfe64  jnz     short loc_1800CFEA9
0x1800cfe66  mov     rcx, [rdx+10h]
0x1800cfe6a  movsxd  rax, dword ptr [r12+8]
0x1800cfe6f  cmp     eax, [rcx+30h]
0x1800cfe72  jnz     short loc_1800CFEA9
0x1800cfe74  xor     edx, edx
0x1800cfe76  test    eax, eax
0x1800cfe78  jle     short loc_1800CFE9C
0x1800cfe7a  mov     rcx, [rcx+28h]
0x1800cfe7e  mov     r9, rax
0x1800cfe81  mov     r8, [r12]
0x1800cfe85  sub     r8, rcx
0x1800cfe88  mov     eax, [rcx]
0x1800cfe8a  cmp     [rcx+r8], eax
0x1800cfe8e  jnz     short loc_1800CFEA9
0x1800cfe90  inc     rdx
0x1800cfe93  add     rcx, 8
0x1800cfe97  cmp     rdx, r9
0x1800cfe9a  jl      short loc_1800CFE88
0x1800cfe9c  mov     edx, 0FFFFFA81h
0x1800cfea1  mov     rcx, rsi
0x1800cfea4  call    sub_180098E08
0x1800cfea9  test    byte ptr [rsi], 8
0x1800cfeac  jnz     loc_1800D004C
0x1800cfeb2  xor     r9d, r9d
0x1800cfeb5  cmp     [rbp+3Fh+arg_60], r9b
0x1800cfebc  jnz     loc_1800D004F
0x1800cfec2  mov     ebx, r9d
0x1800cfec5  jmp     short loc_1800CFECA
0x1800cfec7  xor     r9d, r9d
0x1800cfeca  mov     eax, edi
0x1800cfecc  mov     rcx, rbx
0x1800cfecf  inc     edi
0x1800cfed1  inc     rbx
0x1800cfed4  test    eax, eax
0x1800cfed6  js      short loc_1800CFEF5
0x1800cfed8  cmp     eax, [r13+1Ch]
0x1800cfedc  jge     short loc_1800CFEF5
0x1800cfede  movsxd  rax, dword ptr [r13+rcx*4+0A00h]
0x1800cfee6  cmp     eax, 0FFFFFFFFh
0x1800cfee9  jz      short loc_1800CFEF5
0x1800cfeeb  mov     r15, [r13+rax*8+900h]
0x1800cfef3  jmp     short loc_1800CFEF8
0x1800cfef5  mov     r15, r9
0x1800cfef8  mov     [rsp+120h+var_C0], r15
0x1800cfefd  test    r15, r15
0x1800cff00  jz      loc_1800D004F
0x1800cff06  mov     rdx, [r15+10h]
0x1800cff0a  movsxd  rax, dword ptr [r12+8]
0x1800cff0f  cmp     eax, [rdx+30h]
0x1800cff12  jnz     short loc_1800CFECA
0x1800cff14  mov     r8, r9
0x1800cff17  test    eax, eax
0x1800cff19  jle     short loc_1800CFF40
0x1800cff1b  mov     rcx, [rdx+28h]
  ... truncated ...
```
