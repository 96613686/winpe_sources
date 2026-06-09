# sub_1804B5AAC

- ea: `0x1804b5aac`
- end: `0x1804b65a1`
- name: `sub_1804B5AAC`
- size: `2805`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180678854`

## callees

- `0x18000e80c`
- `0x18000f930`
- `0x180063178`
- `0x1801538e8`
- `0x1801b1c30`
- `0x1802771a0`
- `0x180279050`
- `0x180288e0c`
- `0x180307580`
- `0x180394f50`
- `0x1804816c4`
- `0x1804b5aac`
- `0x1804b65a4`
- `0x1804b6cf8`
- `0x1804b6f40`
- `0x1804b6f84`
- `0x1804ba564`
- `0x1807e4b64`
- `0x1807e5278`

## import_xrefs

- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1804b5c0e`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1804b5c0e`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x1804b6491`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x1804b6491`
- `Mso20Win32Client!__imp_Mso20Win32Client_53248` at `0x1804b64de`
- `Mso20Win32Client!__imp_Mso20Win32Client_53248` at `0x1804b64de`
- `OLEAUT32!VariantInit` at `0x1804b5d9a`
- `OLEAUT32!VariantInit` at `0x1804b5d9a`
- `OLEAUT32!__imp_VariantClear` at `0x1804b607e`
- `OLEAUT32!__imp_VariantClear` at `0x1804b64a0`
- `OLEAUT32!__imp_VariantClear` at `0x1804b607e`
- `OLEAUT32!__imp_VariantClear` at `0x1804b64a0`
- `OLEAUT32!SafeArrayAccessData` at `0x1804b60d6`
- `OLEAUT32!SafeArrayAccessData` at `0x1804b60d6`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1804b614a`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1804b614a`

## pseudocode

```c
__int64 __fastcall sub_1804B5AAC(_QWORD *a1, __int64 **a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  int v7; // r12d
  __int64 **v8; // r15
  __int64 v9; // r13
  HRESULT v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 *v17; // r14
  __int64 v18; // rax
  __int64 (__fastcall *v19)(__int64); // rbx
  _QWORD *v20; // r11
  __int64 v21; // r10
  int v22; // r14d
  int v23; // edi
  unsigned int v24; // r15d
  int v25; // eax
  int v26; // eax
  int v27; // r15d
  int v28; // r13d
  int v29; // eax
  int v30; // r12d
  int v31; // r14d
  __int128 v32; // xmm8
  int *v33; // rax
  int v34; // ecx
  unsigned int v35; // r8d
  unsigned int v36; // r9d
  unsigned int v37; // r10d
  unsigned int v38; // r11d
  __int64 v39; // rax
  int v40; // r15d
  bool v41; // zf
  int i; // ebx
  int v43; // xmm6_4
  int v44; // xmm7_4
  __int64 v45; // rcx
  __int64 v46; // rax
  int v47; // r12d
  unsigned int v48; // r14d
  __int64 v49; // rdi
  __int64 v50; // rdx
  float v51; // xmm8_4
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rdx
  int v55; // r8d
  float v56; // xmm1_4
  float v57; // xmm8_4
  unsigned int v58; // edx
  float v59; // xmm0_4
  float v60; // xmm0_4
  __int64 v61; // [rsp+30h] [rbp-178h] BYREF
  __int64 v62; // [rsp+38h] [rbp-170h] BYREF
  _QWORD v63[2]; // [rsp+40h] [rbp-168h] BYREF
  __int128 v64; // [rsp+50h] [rbp-158h] BYREF
  int v65; // [rsp+60h] [rbp-148h]
  __int64 *v66; // [rsp+68h] [rbp-140h] BYREF
  __int64 v67; // [rsp+70h] [rbp-138h] BYREF
  __int64 v68; // [rsp+78h] [rbp-130h] BYREF
  int v69; // [rsp+80h] [rbp-128h] BYREF
  int v70; // [rsp+84h] [rbp-124h]
  __int64 v71; // [rsp+88h] [rbp-120h] BYREF
  unsigned int v72; // [rsp+90h] [rbp-118h]
  unsigned int v73; // [rsp+94h] [rbp-114h]
  __int128 v74; // [rsp+A0h] [rbp-108h] BYREF
  __int128 v75; // [rsp+B0h] [rbp-F8h] BYREF
  int v76; // [rsp+C0h] [rbp-E8h]
  int v77; // [rsp+C4h] [rbp-E4h]
  int v78; // [rsp+C8h] [rbp-E0h]
  int v79; // [rsp+CCh] [rbp-DCh]
  __int64 v80; // [rsp+D0h] [rbp-D8h]
  _DWORD v81[2]; // [rsp+D8h] [rbp-D0h] BYREF
  void *ppvData; // [rsp+E0h] [rbp-C8h] BYREF
  int v83; // [rsp+E8h] [rbp-C0h] BYREF
  int v84; // [rsp+ECh] [rbp-BCh]
  int v85; // [rsp+F0h] [rbp-B8h]
  int v86; // [rsp+F4h] [rbp-B4h]
  VARIANTARG pvarg; // [rsp+F8h] [rbp-B0h] BYREF
  __int64 (__fastcall **v88)(); // [rsp+110h] [rbp-98h] BYREF
  char v89[8]; // [rsp+118h] [rbp-90h] BYREF
  __int128 v90[5]; // [rsp+120h] [rbp-88h] BYREF

  v8 = a2;
  v9 = a3;
  if ( *(_DWORD *)(a3 + 8) < 2u )
    return 1;
  LOBYTE(v7) = 0;
  v65 = v7;
  v69 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a2 + 56))(*a2, &v69);
  v67 = 0;
  v14 = oart_53449(v13, v12);
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 200LL))(v14, 126) )
  {
    v62 = 0;
    LOBYTE(v15) = sub_1804B6F84(v8) ^ 1;
    v11 = oart_36802(&v62, v15);
    if ( v11 >= 0 )
    {
      v16 = v62;
      v17 = *v8;
      v11 = 0;
      if ( *v8 && v62 )
      {
        v18 = *v17;
        v63[0] = 0;
        v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *))(v18 + 144))(v17, 0, v63);
        if ( v11 < 0
          || (v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v16 + 192LL))(v16, v17, v63[0]),
              v11 < 0) )
        {
          Mso20Win32Client_7228(1903850598);
        }
        if ( v63[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v63[0] + 16LL))(v63[0]);
        v16 = v62;
      }
      if ( v11 < 0 )
        goto LABEL_17;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 56LL))(v16, &v67);
      if ( v11 >= 0 )
      {
        v19 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v67 + 168LL);
        sub_180307580(*(_QWORD *)(a7 + 8));
        sub_180307580(*v20);
        v11 = v19(v21);
      }
    }
    v16 = v62;
LABEL_17:
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_20;
  }
  oart_55874_0(&v67, *v8);
LABEL_20:
  v66 = 0;
  if ( v11 >= 0 )
  {
    v66 = 0;
    v11 = sub_1804B6CF8(&v66);
  }
  sub_1804BA564(&v75, v67);
  v90[0] = v75;
  v22 = v69 - 1;
LABEL_23:
  v70 = v22;
  if ( v11 >= 0 && v22 >= 0 )
  {
    v71 = 0;
    v23 = 0;
    v72 = 0;
    v73 = 0x80000000;
    v63[0] = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v67 + 96LL))(v67, (unsigned int)v22, v63);
    v62 = 0;
    if ( v11 >= 0 )
      v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(**v8 + 96))(*v8, (unsigned int)v22, &v62);
    VariantInit(&pvarg);
    ppvData = 0;
    v24 = 0;
    while ( v11 >= 0 && v24 < *(_DWORD *)(v9 + 8) - 1 )
    {
      v25 = sub_1801538E8(v9, v24);
      sub_1804B65A4((unsigned int)&v74, v25, a4, a5, a6);
      LODWORD(v61) = v24 + 1;
      v26 = sub_1801538E8(v9, v24 + 1);
      sub_1804B65A4((unsigned int)&v83, v26, a4, a5, a6);
      v78 = (v85 - v83) / 2 + v83;
      v79 = v84 + (v86 - v84) / 2;
      v27 = v74;
      v76 = (DWORD2(v74) - (int)v74) / 2 + v74;
      v77 = DWORD1(v74) + (HIDWORD(v74) - DWORD1(v74)) / 2;
      LODWORD(v80) = v78 - v76;
      HIDWORD(v80) = v79 - v77;
      v68 = v80;
      v28 = (int)sqrt((double)((int)v80 * (int)v80 + (v79 - v77) * (v79 - v77)));
      sub_180307580(a4);
      v30 = 3 * v29 / 2;
      if ( v30 < 1 )
        v30 = 1;
      v31 = 0;
      v32 = v74;
      while ( v31 <= v28 )
      {
        v64 = v32;
        v81[0] = v31;
        v81[1] = v28;
        v33 = (int *)sub_180394F50(&v68, v89, v81);
        v34 = *v33;
        LODWORD(v64) = *v33 + v27;
        DWORD1(v64) += v33[1];
        DWORD2(v64) += v34;
        HIDWORD(v64) += v33[1];
        if ( v31 < v28 && v31 + v30 > v28 )
          v30 = v28 - v31;
        if ( (unsigned __int8)sub_1801B1C30(&v64, v90) )
        {
          if ( v11 >= 0 )
          {
            v39 = *v66;
            *(_QWORD *)&v75 = __PAIR64__(v36, v35);
            *((_QWORD *)&v75 + 1) = __PAIR64__(v38, v37);
            v11 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v39 + 128))(v66, &v75);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, VARIANTARG *))(*(_QWORD *)v63[0] + 176LL))(
                      v63[0],
                      v66,
                      &pvarg);
              if ( v11 >= 0 )
              {
                v40 = *(_DWORD *)(pvarg.llVal + 24);
                v41 = v40 == 0;
                if ( v40 > 0 )
                {
                  if ( (unsigned __int8)sub_1807E4B64(&v62) )
                  {
                    VariantClear(&pvarg);
                    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, VARIANTARG *))(*(_QWORD *)v63[0] + 176LL))(
                            v63[0],
                            v66,
                            &pvarg);
                    if ( v11 < 0 )
                      v40 = 0;
                    else
                      v40 = *(_DWORD *)(pvarg.llVal + 24);
                  }
                  v41 = v40 == 0;
                }
                if ( !v41 )
                {
                  v11 = SafeArrayAccessData(pvarg.parray, &ppvData);
                  if ( v11 >= 0 )
                  {
                    for ( i = 0; i < v40; i += 2 )
                    {
                      v43 = *((_DWORD *)ppvData + i);
                      v44 = *((_DWORD *)ppvData + i + 1);
                      sub_18000F930(&v71, 8, sub_18000FA20);
                      v45 = v72;
                      v46 = v71;
                      v23 = ++v72;
                      *(_DWORD *)(v71 + 8 * v45) = v43;
                      *(_DWORD *)(v46 + 8 * v45 + 4) = v44;
                    }
                    v11 = SafeArrayUnaccessData(pvarg.parray);
                  }
                }
                v27 = v74;
              }
            }
          }
        }
        v31 += v30;
      }
      v24 = v61;
      v9 = a3;
    }
    v47 = (unsigned __int8)v65;
    if ( v23 )
      v47 = 1;
    v65 = v47;
    v88 = off_180A97708;
    sub_180288E0C(&v71, 8, sub_18000FA20, &v88);
    v48 = v72;
    LODWORD(v68) = v72 - 1;
    v49 = v71;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( (int)v68 < 0 )
        {
LABEL_100:
          VariantClear(&pvarg);
          if ( v62 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          if ( v63[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v63[0] + 16LL))(v63[0]);
          if ( v49 )
            Mso20Win32Client_53248(v49);
          v22 = v70 - 1;
          v8 = a2;
          LOBYTE(v7) = v65;
          v9 = a3;
          goto LABEL_23;
        }
        LODWORD(v61) = 0;
        LODWORD(v64) = 0;
        sub_1807E5278(&v71, &v61, &v64, &v68);
        v51 = *(float *)&v61;
        if ( *(float *)&v61 < 0.0 )
          break;
        if ( *(float *)&v64 < 0.0 )
        {
          v52 = 0;
          v61 = 0;
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v62 + 208LL))(v62, v50, &v61);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 112LL))(*a1, v61);
              if ( v11 >= 0 )
                v11 = sub_1804816C4(v62);
            }
            v52 = v61;
          }
          goto LABEL_97;
        }
LABEL_70:
        if ( *(float *)&v61 >= 0.0 )
        {
          *(_QWORD *)&v64 = 0;
          v53 = 0;
          v61 = 0;
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v62 + 208LL))(v62, v50, &v64);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v62 + 208LL))(v62, v54, &v61);
              if ( v11 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 112LL))(*a1, v61);
                if ( v11 >= 0 )
                {
                  v11 = sub_1804816C4(v62);
                  if ( v11 >= 0 )
                    v11 = sub_1804816C4(v64);
                }
              }
            }
            v53 = v61;
          }
          v55 = (int)v51;
          v56 = (float)(int)v51;
          v57 = v51 - v56;
          if ( v11 >= 0 && v57 > 0.0 )
          {
            v58 = v68;
            if ( (int)v68 >= 0 )
            {
              while ( v58 < v48 )
              {
                v59 = *(float *)(v49 + 8LL * v58);
                if ( (int)v59 == v55 )
                  *(float *)(v49 + 8LL * v58) = (float)((float)(v59 - v56) / v57) + v56;
                v60 = *(float *)(v49 + 8LL * v58 + 4);
                if ( (int)v60 == v55 )
                  *(float *)(v49 + 8LL * v58 + 4) = (float)((float)(v60 - v56) / v57) + v56;
                if ( (--v58 & 0x80000000) != 0 )
                {
                  v53 = v61;
                  goto LABEL_94;
                }
              }
              Mso20Win32Client_21217(512304278, 0);
              goto LABEL_100;
            }
          }
LABEL_94:
          if ( v53 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          v52 = v64;
        }
        else
        {
          v52 = 0;
          v61 = 0;
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v62 + 208LL))(v62, v50, &v61);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 112LL))(*a1, v62);
              if ( v11 >= 0 )
                v11 = sub_1804816C4(v61);
            }
            v52 = v61;
          }
        }
LABEL_97:
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      if ( *(float *)&v64 >= 0.0 )
        goto LABEL_70;
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 112LL))(*a1, v62);
    }
  }
  if ( (_BYTE)v7 )
  {
    if ( v66 )
      (*(void (**)(void))(*v66 + 16))();
    if ( v67 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    return (unsigned int)v11;
  }
  else
  {
    if ( v66 )
      (*(void (**)(void))(*v66 + 16))();
    if ( v67 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    return 1;
  }
}

```

## disassembly

```asm
0x1804b5aac  mov     r11, rsp
0x1804b5aaf  mov     [r11+20h], r9
0x1804b5ab3  mov     [r11+18h], r8
0x1804b5ab7  mov     [r11+10h], rdx
0x1804b5abb  mov     [r11+8], rcx
0x1804b5abf  push    rbx
0x1804b5ac0  push    rsi
0x1804b5ac1  push    rdi
0x1804b5ac2  push    r12
0x1804b5ac4  push    r13
0x1804b5ac6  push    r14
0x1804b5ac8  push    r15
0x1804b5aca  sub     rsp, 170h
0x1804b5ad1  movaps  xmmword ptr [r11-48h], xmm6
0x1804b5ad6  movaps  xmmword ptr [r11-58h], xmm7
0x1804b5adb  movaps  xmmword ptr [r11-68h], xmm8
0x1804b5ae0  movaps  xmmword ptr [r11-78h], xmm9
0x1804b5ae5  mov     r15, rdx
0x1804b5ae8  mov     eax, 2
0x1804b5aed  mov     r13, r8
0x1804b5af0  cmp     [r8+8], eax
0x1804b5af4  jnb     short loc_1804B5B00
0x1804b5af6  mov     eax, 1
0x1804b5afb  jmp     loc_1804B6576
0x1804b5b00  xor     r12b, r12b
0x1804b5b03  mov     [rsp+1A8h+var_148], r12d
0x1804b5b08  mov     [rsp+1A8h+var_128], 0
0x1804b5b13  mov     rcx, [rdx]
0x1804b5b16  mov     rax, [rcx]
0x1804b5b19  lea     rdx, [rsp+1A8h+var_128]
0x1804b5b21  mov     rax, [rax+38h]
0x1804b5b25  call    cs:__guard_dispatch_icall_fptr
0x1804b5b2b  mov     ebx, eax
0x1804b5b2d  mov     [rsp+1A8h+var_138], 0
0x1804b5b36  call    oart_53449
0x1804b5b3b  mov     r8, rax
0x1804b5b3e  mov     rcx, [rax]
0x1804b5b41  mov     rax, [rcx+0C8h]
0x1804b5b48  mov     edx, 7Eh ; '~'
0x1804b5b4d  mov     rcx, r8
0x1804b5b50  call    cs:__guard_dispatch_icall_fptr
0x1804b5b56  test    al, al
0x1804b5b58  jz      loc_1804B5CAF
0x1804b5b5e  mov     [rsp+1A8h+var_170], 0
0x1804b5b67  mov     rcx, r15
0x1804b5b6a  call    sub_1804B6F84
0x1804b5b6f  mov     bl, al
0x1804b5b71  mov     esi, 1
0x1804b5b76  xor     bl, sil
0x1804b5b79  mov     rcx, [rsp+1A8h+var_170]
0x1804b5b7e  test    rcx, rcx
0x1804b5b81  jz      short loc_1804B5B90
0x1804b5b83  mov     rax, [rcx]
0x1804b5b86  mov     rax, [rax+10h]
0x1804b5b8a  call    cs:__guard_dispatch_icall_fptr
0x1804b5b90  mov     [rsp+1A8h+var_170], 0
0x1804b5b99  mov     dl, bl
0x1804b5b9b  lea     rcx, [rsp+1A8h+var_170]
0x1804b5ba0  call    oart_36802
0x1804b5ba5  mov     ebx, eax
0x1804b5ba7  test    eax, eax
0x1804b5ba9  js      loc_1804B5C93
0x1804b5baf  mov     rdi, [rsp+1A8h+var_170]
0x1804b5bb4  mov     r14, [r15]
0x1804b5bb7  xor     ebx, ebx
0x1804b5bb9  test    r14, r14
0x1804b5bbc  jz      short loc_1804B5C30
0x1804b5bbe  test    rdi, rdi
0x1804b5bc1  jz      short loc_1804B5C30
0x1804b5bc3  mov     rax, [r14]
0x1804b5bc6  mov     [rsp+1A8h+var_168], rbx
0x1804b5bcb  lea     r8, [rsp+1A8h+var_168]
0x1804b5bd0  xor     edx, edx
0x1804b5bd2  mov     rcx, r14
0x1804b5bd5  mov     rax, [rax+90h]
0x1804b5bdc  call    cs:__guard_dispatch_icall_fptr
0x1804b5be2  mov     ebx, eax
0x1804b5be4  test    eax, eax
0x1804b5be6  js      short loc_1804B5C09
0x1804b5be8  mov     rax, [rdi]
0x1804b5beb  mov     r8, [rsp+1A8h+var_168]
0x1804b5bf0  mov     rdx, r14
0x1804b5bf3  mov     rcx, rdi
0x1804b5bf6  mov     rax, [rax+0C0h]
0x1804b5bfd  call    cs:__guard_dispatch_icall_fptr
0x1804b5c03  mov     ebx, eax
0x1804b5c05  test    eax, eax
0x1804b5c07  jns     short loc_1804B5C14
0x1804b5c09  mov     ecx, 717A7466h
0x1804b5c0e  call    cs:Mso20Win32Client_7228
0x1804b5c14  mov     rcx, [rsp+1A8h+var_168]
0x1804b5c19  test    rcx, rcx
0x1804b5c1c  jz      short loc_1804B5C2B
0x1804b5c1e  mov     rax, [rcx]
0x1804b5c21  mov     rax, [rax+10h]
0x1804b5c25  call    cs:__guard_dispatch_icall_fptr
0x1804b5c2b  mov     rdi, [rsp+1A8h+var_170]
0x1804b5c30  test    ebx, ebx
0x1804b5c32  js      short loc_1804B5C98
0x1804b5c34  mov     rax, [rdi]
0x1804b5c37  lea     rdx, [rsp+1A8h+var_138]
0x1804b5c3c  mov     rcx, rdi
0x1804b5c3f  mov     rax, [rax+38h]
0x1804b5c43  call    cs:__guard_dispatch_icall_fptr
0x1804b5c49  mov     ebx, eax
0x1804b5c4b  test    eax, eax
0x1804b5c4d  js      short loc_1804B5C93
0x1804b5c4f  mov     r10, [rsp+1A8h+var_138]
0x1804b5c54  mov     rax, [r10]
0x1804b5c57  mov     rbx, [rax+0A8h]
0x1804b5c5e  mov     r11, [rsp+1A8h+arg_30]
0x1804b5c66  mov     rcx, [r11+8]
0x1804b5c6a  call    sub_180307580
0x1804b5c6f  movd    xmm2, eax
0x1804b5c73  cvtdq2ps xmm2, xmm2
0x1804b5c76  mov     rcx, [r11]
0x1804b5c79  call    sub_180307580
0x1804b5c7e  movd    xmm1, eax
0x1804b5c82  cvtdq2ps xmm1, xmm1
0x1804b5c85  mov     rcx, r10
0x1804b5c88  mov     rax, rbx
0x1804b5c8b  call    cs:__guard_dispatch_icall_fptr
0x1804b5c91  mov     ebx, eax
0x1804b5c93  mov     rdi, [rsp+1A8h+var_170]
0x1804b5c98  test    rdi, rdi
0x1804b5c9b  jz      short loc_1804B5CC1
0x1804b5c9d  mov     rax, [rdi]
0x1804b5ca0  mov     rcx, rdi
0x1804b5ca3  mov     rax, [rax+10h]
0x1804b5ca7  call    cs:__guard_dispatch_icall_fptr
0x1804b5cad  jmp     short loc_1804B5CC1
0x1804b5caf  mov     rdx, [r15]
0x1804b5cb2  lea     rcx, [rsp+1A8h+var_138]
0x1804b5cb7  call    oart_55874_0
0x1804b5cbc  mov     esi, 1
0x1804b5cc1  mov     [rsp+1A8h+var_140], 0
0x1804b5cca  test    ebx, ebx
0x1804b5ccc  js      short loc_1804B5CE3
0x1804b5cce  mov     [rsp+1A8h+var_140], 0
0x1804b5cd7  lea     rcx, [rsp+1A8h+var_140]
0x1804b5cdc  call    sub_1804B6CF8
0x1804b5ce1  mov     ebx, eax
0x1804b5ce3  mov     rdx, [rsp+1A8h+var_138]
0x1804b5ce8  lea     rcx, [rsp+1A8h+var_F8]
0x1804b5cf0  call    sub_1804BA564
0x1804b5cf5  movaps  xmm0, [rsp+1A8h+var_F8]
0x1804b5cfd  movdqa  [rsp+1A8h+var_88], xmm0
0x1804b5d06  mov     r14d, [rsp+1A8h+var_128]
0x1804b5d0e  dec     r14d
0x1804b5d11  xorps   xmm9, xmm9
0x1804b5d15  mov     [rsp+1A8h+var_124], r14d
0x1804b5d1d  test    ebx, ebx
0x1804b5d1f  js      loc_1804B6509
0x1804b5d25  test    r14d, r14d
0x1804b5d28  js      loc_1804B6509
0x1804b5d2e  mov     [rsp+1A8h+var_120], 0
0x1804b5d3a  xor     edi, edi
0x1804b5d3c  mov     [rsp+1A8h+var_118], edi
0x1804b5d43  mov     [rsp+1A8h+var_114], 80000000h
0x1804b5d4e  mov     [rsp+1A8h+var_168], rdi
0x1804b5d53  mov     rcx, [rsp+1A8h+var_138]
0x1804b5d58  mov     rax, [rcx]
0x1804b5d5b  lea     r8, [rsp+1A8h+var_168]
0x1804b5d60  mov     edx, r14d
0x1804b5d63  mov     rax, [rax+60h]
0x1804b5d67  call    cs:__guard_dispatch_icall_fptr
0x1804b5d6d  mov     ebx, eax
0x1804b5d6f  mov     [rsp+1A8h+var_170], rdi
0x1804b5d74  test    eax, eax
0x1804b5d76  js      short loc_1804B5D92
0x1804b5d78  mov     rcx, [r15]
0x1804b5d7b  mov     rax, [rcx]
0x1804b5d7e  lea     r8, [rsp+1A8h+var_170]
0x1804b5d83  mov     edx, r14d
0x1804b5d86  mov     rax, [rax+60h]
0x1804b5d8a  call    cs:__guard_dispatch_icall_fptr
0x1804b5d90  mov     ebx, eax
0x1804b5d92  lea     rcx, [rsp+1A8h+pvarg]; pvarg
0x1804b5d9a  call    cs:VariantInit
0x1804b5da0  mov     [rsp+1A8h+ppvData], 0
0x1804b5dac  xor     r15d, r15d
0x1804b5daf  nop
0x1804b5db0  test    ebx, ebx
0x1804b5db2  js      loc_1804B6174
0x1804b5db8  mov     eax, [r13+8]
0x1804b5dbc  sub     eax, esi
0x1804b5dbe  cmp     r15d, eax
0x1804b5dc1  jnb     loc_1804B6174
0x1804b5dc7  mov     edx, r15d
0x1804b5dca  mov     rcx, r13
0x1804b5dcd  call    sub_1801538E8
0x1804b5dd2  mov     rdx, rax
0x1804b5dd5  mov     r14, [rsp+1A8h+arg_28]
0x1804b5ddd  mov     [rsp+1A8h+var_188], r14
0x1804b5de2  mov     r9, [rsp+1A8h+arg_20]
0x1804b5dea  mov     r12, [rsp+1A8h+arg_18]
0x1804b5df2  mov     r8, r12
0x1804b5df5  lea     rcx, [rsp+1A8h+var_108]
0x1804b5dfd  call    sub_1804B65A4
0x1804b5e02  lea     edx, [r15+1]
0x1804b5e06  mov     dword ptr [rsp+1A8h+var_178], edx
0x1804b5e0a  mov     rcx, r13
0x1804b5e0d  call    sub_1801538E8
0x1804b5e12  mov     rdx, rax
0x1804b5e15  mov     [rsp+1A8h+var_188], r14
0x1804b5e1a  mov     r9, [rsp+1A8h+arg_20]
0x1804b5e22  mov     r8, r12
0x1804b5e25  lea     rcx, [rsp+1A8h+var_C0]
0x1804b5e2d  call    sub_1804B65A4
0x1804b5e32  mov     eax, [rsp+1A8h+var_B4]
0x1804b5e39  sub     eax, [rsp+1A8h+var_BC]
0x1804b5e40  cdq
0x1804b5e41  mov     r14d, 2
0x1804b5e47  idiv    r14d
0x1804b5e4a  mov     r8d, eax
0x1804b5e4d  add     r8d, [rsp+1A8h+var_BC]
0x1804b5e55  mov     eax, [rsp+1A8h+var_B8]
0x1804b5e5c  mov     ecx, [rsp+1A8h+var_C0]
0x1804b5e63  sub     eax, ecx
0x1804b5e65  cdq
0x1804b5e66  idiv    r14d
0x1804b5e69  lea     r9d, [rax+rcx]
0x1804b5e6d  mov     dword ptr [rsp+1A8h+var_E0], r9d
0x1804b5e75  mov     dword ptr [rsp+1A8h+var_E0+4], r8d
0x1804b5e7d  mov     eax, dword ptr [rsp+1A8h+var_108+0Ch]
0x1804b5e84  sub     eax, dword ptr [rsp+1A8h+var_108+4]
0x1804b5e8b  cdq
0x1804b5e8c  idiv    r14d
0x1804b5e8f  mov     r8d, eax
0x1804b5e92  add     r8d, dword ptr [rsp+1A8h+var_108+4]
0x1804b5e9a  mov     eax, dword ptr [rsp+1A8h+var_108+8]
0x1804b5ea1  mov     r15d, dword ptr [rsp+1A8h+var_108]
0x1804b5ea9  sub     eax, r15d
0x1804b5eac  cdq
0x1804b5ead  idiv    r14d
0x1804b5eb0  lea     ecx, [rax+r15]
0x1804b5eb4  mov     dword ptr [rsp+1A8h+var_E8], ecx
0x1804b5ebb  mov     dword ptr [rsp+1A8h+var_E8+4], r8d
0x1804b5ec3  sub     r9d, ecx
0x1804b5ec6  mov     dword ptr [rsp+1A8h+var_D8], r9d
0x1804b5ece  mov     rax, [rsp+1A8h+var_E8]
0x1804b5ed6  shr     rax, 20h
0x1804b5eda  mov     rcx, [rsp+1A8h+var_E0]
0x1804b5ee2  shr     rcx, 20h
0x1804b5ee6  sub     ecx, eax
0x1804b5ee8  mov     dword ptr [rsp+1A8h+var_D8+4], ecx
0x1804b5eef  mov     rax, [rsp+1A8h+var_D8]
0x1804b5ef7  mov     [rsp+1A8h+var_130], rax
0x1804b5efc  shr     rax, 20h
0x1804b5f00  imul    eax, eax
0x1804b5f03  imul    r9d, r9d
0x1804b5f07  add     eax, r9d
0x1804b5f0a  movd    xmm0, eax
0x1804b5f0e  cvtdq2pd xmm0, xmm0; X
0x1804b5f12  call    sqrt
0x1804b5f17  cvttsd2si r13d, xmm0
0x1804b5f1c  mov     rcx, r12
0x1804b5f1f  call    sub_180307580
0x1804b5f24  lea     eax, [rax+rax*2]
0x1804b5f27  cdq
0x1804b5f28  idiv    r14d
0x1804b5f2b  mov     r12d, eax
0x1804b5f2e  cmp     eax, esi
0x1804b5f30  cmovl   r12d, esi
0x1804b5f34  xor     r14d, r14d
0x1804b5f37  movaps  xmm8, [rsp+1A8h+var_108]
0x1804b5f40  cmp     r14d, r13d
0x1804b5f43  jg      loc_1804B6162
0x1804b5f49  movdqa  [rsp+1A8h+var_158], xmm8
0x1804b5f50  mov     [rsp+1A8h+var_D0], r14d
0x1804b5f58  mov     [rsp+1A8h+var_CC], r13d
0x1804b5f60  lea     r8, [rsp+1A8h+var_D0]
0x1804b5f68  lea     rdx, [rsp+1A8h+var_90]
0x1804b5f70  lea     rcx, [rsp+1A8h+var_130]
0x1804b5f75  call    sub_180394F50
0x1804b5f7a  mov     ecx, [rax]
0x1804b5f7c  lea     r8d, [rcx+r15]
0x1804b5f80  mov     dword ptr [rsp+1A8h+var_158], r8d
0x1804b5f85  mov     r9d, dword ptr [rsp+1A8h+var_158+4]
0x1804b5f8a  add     r9d, [rax+4]
0x1804b5f8e  mov     dword ptr [rsp+1A8h+var_158+4], r9d
0x1804b5f93  mov     r10d, dword ptr [rsp+1A8h+var_158+8]
0x1804b5f98  add     r10d, ecx
0x1804b5f9b  mov     dword ptr [rsp+1A8h+var_158+8], r10d
0x1804b5fa0  mov     r11d, dword ptr [rsp+1A8h+var_158+0Ch]
0x1804b5fa5  add     r11d, [rax+4]
0x1804b5fa9  mov     dword ptr [rsp+1A8h+var_158+0Ch], r11d
0x1804b5fae  cmp     r14d, r13d
0x1804b5fb1  jge     short loc_1804B5FC2
0x1804b5fb3  lea     eax, [r14+r12]
0x1804b5fb7  cmp     eax, r13d
0x1804b5fba  jle     short loc_1804B5FC2
0x1804b5fbc  mov     r12d, r13d
0x1804b5fbf  sub     r12d, r14d
0x1804b5fc2  lea     rdx, [rsp+1A8h+var_88]
0x1804b5fca  lea     rcx, [rsp+1A8h+var_158]
0x1804b5fcf  call    sub_1801B1C30
0x1804b5fd4  test    al, al
0x1804b5fd6  jz      loc_1804B615A
0x1804b5fdc  test    ebx, ebx
  ... truncated ...
```
