# CPrintCoreHelperPS::SetOptionInternal(char const *,char const *,CPrintCoreConfig *)

- ea: `0x18002d220`
- end: `0x18002d81f`
- name: `?SetOptionInternal@CPrintCoreHelperPS@@MEAAJPEBD0PEAVCPrintCoreConfig@@@Z`
- size: `1535`
- prototype: `__int64 __fastcall(CPrintCoreHelperPS *__hidden this, const char *, const char *, struct CPrintCoreConfig *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18002be24`
- `0x18002c3e8`
- `0x18002c484`
- `0x18002d220`
- `0x180032250`
- `0x180032cb0`
- `0x180032d10`
- `0x18005c404`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall CPrintCoreHelperPS::SetOptionInternal(
        CPrintCoreHelperPS *this,
        const char *a2,
        const char *a3,
        struct CPrintCoreConfig *a4)
{
  __int64 v8; // rax
  __int64 v9; // rdx
  char near **v10; // rcx
  int v11; // r9d
  int v12; // r8d
  char near **v13; // rcx
  int v14; // r10d
  int v15; // r9d
  char near **v16; // rax
  int v17; // r8d
  int v18; // edx
  CPrintCoreHelperPS *v19; // rcx
  __int64 v20; // rdi
  struct _UIINFO *UIInfo; // rax
  char near **v23; // rax
  int v24; // edx
  int v25; // r8d
  char near **v26; // rsi
  char near **v27; // rax
  int v28; // edx
  int v29; // ecx
  char near **v30; // rax
  int v31; // edx
  int v32; // ecx
  char near **v33; // rax
  int v34; // edx
  int v35; // ecx
  char near **v36; // rax
  int v37; // edx
  int v38; // ecx
  __int64 v39; // rax
  __int64 v40; // rbp
  unsigned int v41; // edi
  struct _UIINFO *v42; // rax
  unsigned int v43; // edi
  int v44; // r15d
  char near **v45; // rcx
  int v46; // r8d
  int v47; // r9d
  struct _UIINFO *v48; // rbp
  struct CPrintCoreConfig *v49; // r14
  unsigned int v50; // ecx
  _DWORD *v51; // r8
  unsigned int v52; // r9d
  __int64 v53; // r10
  __int64 v54; // r11
  unsigned int v55; // eax
  __int64 v56; // rcx
  int v57; // ecx
  __int64 v58; // rdx
  struct _UIINFO *v59; // rdi
  struct CPrintCoreConfig *v60; // rsi
  unsigned int v61; // ecx
  __int64 v62; // r9
  __int64 v63; // rcx
  _DWORD *v64; // r9
  unsigned int v65; // ecx
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rcx
  unsigned int v69[18]; // [rsp+20h] [rbp-48h] BYREF

  if ( !strcmp((const char *)&kstrPSOrientation, a2) )
  {
    if ( (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 1) != 0 )
    {
      v8 = *((_QWORD *)a4 + 2);
      if ( !v8 )
        v8 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a4 + 1) + 48LL))(*(_QWORD *)a4);
      v9 = *(unsigned __int16 *)(v8 + 68);
      v10 = &kstrPSOrientRotatedLandscape;
      do
      {
        v11 = *((unsigned __int8 *)v10 + a3 - (const char *)&kstrPSOrientRotatedLandscape);
        v12 = *(unsigned __int8 *)v10 - v11;
        if ( v12 )
          break;
        v10 = (char near **)((char *)v10 + 1);
      }
      while ( v11 );
      if ( !v12 )
      {
        *(_DWORD *)(v8 + 72) |= 1u;
        *(_WORD *)(v8 + 76) = 2;
        *(_DWORD *)(v9 + v8 + 4) |= 0x200u;
        return 0;
      }
      v13 = &kstrPSOrientLandscape;
      do
      {
        v14 = *((unsigned __int8 *)v13 + a3 - (const char *)&kstrPSOrientLandscape);
        v15 = *(unsigned __int8 *)v13 - v14;
        if ( v15 )
          break;
        v13 = (char near **)((char *)v13 + 1);
      }
      while ( v14 );
      if ( !v15 )
      {
        *(_WORD *)(v8 + 76) = 2;
LABEL_17:
        *(_DWORD *)(v8 + 72) |= 1u;
        *(_DWORD *)(v9 + v8 + 4) &= ~0x200u;
        return 0;
      }
      if ( !strcmp((const char *)&kstrPSOrientPortrait, a3) )
      {
        *(_WORD *)(v8 + 76) = 1;
        goto LABEL_17;
      }
    }
    return 2147500037LL;
  }
  v16 = &kstrPSCustomPageSize;
  do
  {
    v17 = *((unsigned __int8 *)v16 + a2 - (const char *)&kstrPSCustomPageSize);
    v18 = *(unsigned __int8 *)v16 - v17;
    if ( v18 )
      break;
    v16 = (char near **)((char *)v16 + 1);
  }
  while ( v17 );
  if ( !v18 )
  {
    if ( (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 1) != 0
      && CPrintCoreHelperPS::BIsCustomPageSizeSupported(v19, a4) )
    {
      v20 = *((_QWORD *)a4 + 2);
      if ( !v20 )
        v20 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a4 + 1) + 48LL))(*(_QWORD *)a4);
      UIInfo = CPrintCoreConfig::GetUIInfo(a4);
      if ( (unsigned int)BPSWriteCustomPageSize(UIInfo, v20, a3) )
      {
        *(_WORD *)(v20 + 78) = 0x7FFF;
        *(_DWORD *)(v20 + 72) |= 2u;
        return 0;
      }
    }
    return 2147500037LL;
  }
  if ( (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 4) == 0 )
    goto LABEL_80;
  v69[0] = 0;
  v23 = &kstrPSJobTimeout;
  do
  {
    v24 = *((unsigned __int8 *)v23 + a2 - (const char *)&kstrPSJobTimeout);
    v25 = *(unsigned __int8 *)v23 - v24;
    if ( v25 )
      break;
    v23 = (char near **)((char *)v23 + 1);
  }
  while ( v24 );
  if ( v25 )
  {
    v27 = &kstrPSMaxBMPFontSize;
    do
    {
      v28 = *((unsigned __int8 *)v27 + a2 - (const char *)&kstrPSMaxBMPFontSize);
      v29 = *(unsigned __int8 *)v27 - v28;
      if ( v29 )
        break;
      v27 = (char near **)((char *)v27 + 1);
    }
    while ( v28 );
    if ( !v29 )
    {
      v26 = &kstrPSMaxBMPFontSize;
      goto LABEL_55;
    }
    v30 = &kstrPSWaitTimeout;
    do
    {
      v31 = *((unsigned __int8 *)v30 + a2 - (const char *)&kstrPSWaitTimeout);
      v32 = *(unsigned __int8 *)v30 - v31;
      if ( v32 )
        break;
      v30 = (char near **)((char *)v30 + 1);
    }
    while ( v31 );
    if ( !v32 )
    {
      v26 = &kstrPSWaitTimeout;
      goto LABEL_55;
    }
    v33 = &kstrPSMinOutlineFont;
    do
    {
      v34 = *((unsigned __int8 *)v33 + a2 - (const char *)&kstrPSMinOutlineFont);
      v35 = *(unsigned __int8 *)v33 - v34;
      if ( v35 )
        break;
      v33 = (char near **)((char *)v33 + 1);
    }
    while ( v34 );
    if ( !v35 )
    {
      v26 = &kstrPSMinOutlineFont;
      goto LABEL_55;
    }
    v36 = &kstrPSMemory;
    do
    {
      v37 = *((unsigned __int8 *)v36 + a2 - (const char *)&kstrPSMemory);
      v38 = *(unsigned __int8 *)v36 - v37;
      if ( v38 )
        break;
      v36 = (char near **)((char *)v36 + 1);
    }
    while ( v37 );
    if ( !v38 )
    {
      v26 = &kstrPSMemory;
      goto LABEL_55;
    }
LABEL_80:
    v44 = CPrintAbstractHelper::SetOptionInternal(this, a2, a3, a4);
    if ( v44 >= 0 )
    {
      v45 = &kstrPSPagesPerSheet;
      do
      {
        v46 = *((unsigned __int8 *)v45 + a2 - (const char *)&kstrPSPagesPerSheet);
        v47 = *(unsigned __int8 *)v45 - v46;
        if ( v47 )
          break;
        v45 = (char near **)((char *)v45 + 1);
      }
      while ( v46 );
      if ( !v47 && !strcmp((const char *)&kstrPSNUpBooklet, a3) )
      {
        v48 = CPrintCoreConfig::GetUIInfo(a4);
        v49 = *((_QWORD *)a4 + 2)
            ? (struct CPrintCoreConfig *)((char *)a4 + 28)
            : (struct CPrintCoreConfig *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a4 + 1) + 8LL))(
                                           *(_QWORD *)a4,
                                           0);
        (**((void (__fastcall ***)(_QWORD))a4 + 1))(*(_QWORD *)a4);
        v50 = *((_DWORD *)v48 + 54);
        if ( v50 )
        {
          v51 = (_DWORD *)(*((_QWORD *)v48 + 41) + v50);
          if ( v51 )
          {
            v52 = v51[13];
            v53 = *((_QWORD *)v48 + 41);
            v54 = (unsigned int)((v50 - (unsigned __int64)*((unsigned int *)v48 + 8)) / 0x54);
            v55 = *((unsigned __int8 *)v49 + 2 * v54);
            if ( v55 >= v52 || (v56 = v53 + v51[14] + v51[12] * v55) == 0 || *(_DWORD *)(v56 + 56) == 1 )
            {
              v57 = 0;
              if ( v52 )
              {
                while ( 1 )
                {
                  v58 = v53 + (unsigned int)(v51[14] + v51[12] * v57);
                  if ( v58 )
                  {
                    if ( *(_DWORD *)(v58 + 56) != 1 )
                      break;
                  }
                  if ( ++v57 >= v52 )
                    goto LABEL_100;
                }
                *((_BYTE *)v49 + 2 * v54) = v57;
              }
            }
          }
        }
      }
LABEL_100:
      if ( !strcmp_0("Duplex", a2) )
      {
        v59 = CPrintCoreConfig::GetUIInfo(a4);
        v60 = *((_QWORD *)a4 + 2)
            ? (struct CPrintCoreConfig *)((char *)a4 + 28)
            : (struct CPrintCoreConfig *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a4 + 1) + 8LL))(
                                           *(_QWORD *)a4,
                                           0);
        (**((void (__fastcall ***)(_QWORD))a4 + 1))(*(_QWORD *)a4);
        v61 = *((_DWORD *)v59 + 54);
        if ( v61 )
        {
          v62 = v61;
          v63 = *((_QWORD *)v59 + 41);
          v64 = (_DWORD *)(v63 + v62);
          if ( v64 )
          {
            v65 = *((unsigned __int8 *)v60
                  + 2 * (unsigned int)(((unsigned __int64)v64 - *((unsigned int *)v59 + 8) - v63) / 0x54));
            v66 = v65 >= v64[13] ? 0LL : *((_QWORD *)v59 + 41) + v64[14] + v64[12] * v65;
            if ( *(_DWORD *)(v66 + 56) == 1 )
            {
              v67 = *((_QWORD *)a4 + 2);
              if ( !v67 )
                v67 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a4 + 1) + 48LL))(*(_QWORD *)a4);
              v68 = *(unsigned __int16 *)(v67 + 68);
              if ( *(_DWORD *)(v68 + v67 + 136) == 6 )
                *(_DWORD *)(v68 + v67 + 136) = 1;
            }
          }
        }
      }
    }
    return (unsigned int)v44;
  }
  v26 = &kstrPSJobTimeout;
LABEL_55:
  if ( !PReadUnsignedInt(a3, 1, v69, &kstrPSWaitTimeout) )
    return 2147500037LL;
  if ( *(_QWORD *)a4 )
  {
    v39 = (*(__int64 (**)(void))(*((_QWORD *)a4 + 1) + 40LL))();
    v40 = v39;
    if ( v39 )
    {
      v41 = v69[0];
      if ( &kstrPSJobTimeout == v26 && v69[0] <= 0x7FFFFFFF )
      {
        *(_DWORD *)(v39 + 12) = v69[0];
        return 0;
      }
      if ( &kstrPSMaxBMPFontSize == v26 && v69[0] <= 0x7FA4 )
      {
        *(_WORD *)(v39 + 22) = v69[0];
        return 0;
      }
      if ( &kstrPSWaitTimeout == v26 && v69[0] <= 0x7FFFFFFF )
      {
        *(_DWORD *)(v39 + 16) = v69[0];
        return 0;
      }
      if ( &kstrPSMinOutlineFont == v26 && v69[0] <= 0x7FA4 )
      {
        *(_WORD *)(v39 + 20) = v69[0];
        return 0;
      }
      if ( &kstrPSMemory != v26 || v69[0] > 0x1FFFFF )
        return 2147500037LL;
      v42 = CPrintCoreConfig::GetUIInfo(a4);
      v43 = v41 << 10;
      if ( v42 )
      {
        if ( *((_DWORD *)v42 + 20) == 1 )
        {
          if ( v43 < 0x2B000 )
            return 2147500037LL;
        }
        else if ( *((_DWORD *)v42 + 20) != 2 || v43 < 0x3E400 )
        {
          return 2147500037LL;
        }
        *(_DWORD *)(v40 + 8) = v43;
        return 0;
      }
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18002d220  push    rbx
0x18002d222  push    rbp
0x18002d223  push    rsi
0x18002d224  push    rdi
0x18002d225  push    r13
0x18002d227  push    r14
0x18002d229  push    r15
0x18002d22b  sub     rsp, 30h
0x18002d22f  mov     rbx, r9
0x18002d232  lea     rax, ?kstrPSOrientation@@3PADA; "%Orientation"
0x18002d239  mov     r9, rdx
0x18002d23c  mov     rbp, r8
0x18002d23f  sub     r9, rax
0x18002d242  mov     rdi, rdx
0x18002d245  mov     rsi, rcx
0x18002d248  mov     r13d, 1
0x18002d24e  movzx   r8d, byte ptr [rax]
0x18002d252  movzx   edx, byte ptr [rax+r9]
0x18002d257  sub     r8d, edx
0x18002d25a  jnz     short loc_18002D263
0x18002d25c  add     rax, r13
0x18002d25f  test    edx, edx
0x18002d261  jnz     short loc_18002D24E
0x18002d263  test    r8d, r8d
0x18002d266  jnz     loc_18002D344
0x18002d26c  mov     rcx, rbx; this
0x18002d26f  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002d274  test    r13b, al
0x18002d277  jz      loc_18002D5A4
0x18002d27d  mov     rax, [rbx+10h]
0x18002d281  test    rax, rax
0x18002d284  jnz     short loc_18002D296
0x18002d286  mov     rax, [rbx+8]
0x18002d28a  mov     rcx, [rbx]
0x18002d28d  mov     rax, [rax+30h]
0x18002d291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d296  movzx   edx, word ptr [rax+44h]
0x18002d29a  lea     rcx, ?kstrPSOrientRotatedLandscape@@3PADA; "RotatedLandscape"
0x18002d2a1  mov     r10, rbp
0x18002d2a4  sub     r10, rcx
0x18002d2a7  movzx   r8d, byte ptr [rcx]
0x18002d2ab  movzx   r9d, byte ptr [rcx+r10]
0x18002d2b0  sub     r8d, r9d
0x18002d2b3  jnz     short loc_18002D2BD
0x18002d2b5  add     rcx, r13
0x18002d2b8  test    r9d, r9d
0x18002d2bb  jnz     short loc_18002D2A7
0x18002d2bd  test    r8d, r8d
0x18002d2c0  jnz     short loc_18002D2D7
0x18002d2c2  or      [rax+48h], r13d
0x18002d2c6  mov     word ptr [rax+4Ch], 2
0x18002d2cc  bts     dword ptr [rdx+rax+4], 9
0x18002d2d2  jmp     loc_18002D3D3
0x18002d2d7  lea     rcx, ?kstrPSOrientLandscape@@3PADA; "Landscape"
0x18002d2de  mov     r8, rbp
0x18002d2e1  sub     r8, rcx
0x18002d2e4  movzx   r9d, byte ptr [rcx]
0x18002d2e8  movzx   r10d, byte ptr [rcx+r8]
0x18002d2ed  sub     r9d, r10d
0x18002d2f0  jnz     short loc_18002D2FA
0x18002d2f2  add     rcx, r13
0x18002d2f5  test    r10d, r10d
0x18002d2f8  jnz     short loc_18002D2E4
0x18002d2fa  test    r9d, r9d
0x18002d2fd  jnz     short loc_18002D307
0x18002d2ff  mov     word ptr [rax+4Ch], 2
0x18002d305  jmp     short loc_18002D335
0x18002d307  lea     rcx, ?kstrPSOrientPortrait@@3PADA; "Portrait"
0x18002d30e  sub     rbp, rcx
0x18002d311  movzx   r8d, byte ptr [rcx]
0x18002d315  movzx   r9d, byte ptr [rcx+rbp]
0x18002d31a  sub     r8d, r9d
0x18002d31d  jnz     short loc_18002D327
0x18002d31f  add     rcx, r13
0x18002d322  test    r9d, r9d
0x18002d325  jnz     short loc_18002D311
0x18002d327  test    r8d, r8d
0x18002d32a  jnz     loc_18002D5A4
0x18002d330  mov     [rax+4Ch], r13w
0x18002d335  or      [rax+48h], r13d
0x18002d339  btr     dword ptr [rdx+rax+4], 9
0x18002d33f  jmp     loc_18002D3D3
0x18002d344  lea     rax, ?kstrPSCustomPageSize@@3PADA; "%CustomPageSize"
0x18002d34b  mov     rcx, rdi
0x18002d34e  sub     rcx, rax
0x18002d351  movzx   edx, byte ptr [rax]
0x18002d354  movzx   r8d, byte ptr [rax+rcx]
0x18002d359  sub     edx, r8d
0x18002d35c  jnz     short loc_18002D366
0x18002d35e  add     rax, r13
0x18002d361  test    r8d, r8d
0x18002d364  jnz     short loc_18002D351
0x18002d366  mov     rcx, rbx; this
0x18002d369  test    edx, edx
0x18002d36b  jnz     short loc_18002D3DA
0x18002d36d  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002d372  test    r13b, al
0x18002d375  jz      loc_18002D5A4
0x18002d37b  mov     rdx, rbx; struct CPrintCoreConfig *
0x18002d37e  call    ?BIsCustomPageSizeSupported@CPrintCoreHelperPS@@AEAAHPEAVCPrintCoreConfig@@@Z; CPrintCoreHelperPS::BIsCustomPageSizeSupported(CPrintCoreConfig *)
0x18002d383  test    eax, eax
0x18002d385  jz      loc_18002D5A4
0x18002d38b  mov     rdi, [rbx+10h]
0x18002d38f  test    rdi, rdi
0x18002d392  jnz     short loc_18002D3A7
0x18002d394  mov     rax, [rbx+8]
0x18002d398  mov     rcx, [rbx]
0x18002d39b  mov     rax, [rax+30h]
0x18002d39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3a4  mov     rdi, rax
0x18002d3a7  mov     rcx, rbx; this
0x18002d3aa  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002d3af  mov     rcx, rax
0x18002d3b2  mov     r8, rbp
0x18002d3b5  mov     rdx, rdi
0x18002d3b8  call    BPSWriteCustomPageSize
0x18002d3bd  test    eax, eax
0x18002d3bf  jz      loc_18002D5A4
0x18002d3c5  mov     ecx, 2
0x18002d3ca  mov     word ptr [rdi+4Eh], 7FFFh
0x18002d3d0  or      [rdi+48h], ecx
0x18002d3d3  xor     eax, eax
0x18002d3d5  jmp     loc_18002D810
0x18002d3da  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002d3df  test    al, 4
0x18002d3e1  jz      loc_18002D5D2
0x18002d3e7  lea     r14, ?kstrPSJobTimeout@@3PADA; "%JobTimeout"
0x18002d3ee  mov     [rsp+68h+var_48], 0
0x18002d3f6  mov     rcx, rdi
0x18002d3f9  mov     rax, r14
0x18002d3fc  sub     rcx, r14
0x18002d3ff  movzx   r8d, byte ptr [rax]
0x18002d403  movzx   edx, byte ptr [rax+rcx]
0x18002d407  sub     r8d, edx
0x18002d40a  jnz     short loc_18002D413
0x18002d40c  add     rax, r13
0x18002d40f  test    edx, edx
0x18002d411  jnz     short loc_18002D3FF
0x18002d413  lea     r15, ?kstrPSMaxBMPFontSize@@3PADA; "%MaxFontSizeAsBitmap"
0x18002d41a  lea     r9, ?kstrPSWaitTimeout@@3PADA; "%WaitTimeout"
0x18002d421  lea     r10, ?kstrPSMinOutlineFont@@3PADA; "%MinFontSizeAsOutline"
0x18002d428  lea     r11, ?kstrPSMemory@@3PADA; "%PSMemory"
0x18002d42f  test    r8d, r8d
0x18002d432  jnz     short loc_18002D43C
0x18002d434  mov     rsi, r14
0x18002d437  jmp     loc_18002D4D2
0x18002d43c  mov     r8, rdi
0x18002d43f  mov     rax, r15
0x18002d442  sub     r8, r15
0x18002d445  movzx   ecx, byte ptr [rax]
0x18002d448  movzx   edx, byte ptr [rax+r8]
0x18002d44d  sub     ecx, edx
0x18002d44f  jnz     short loc_18002D458
0x18002d451  add     rax, r13
0x18002d454  test    edx, edx
0x18002d456  jnz     short loc_18002D445
0x18002d458  test    ecx, ecx
0x18002d45a  jnz     short loc_18002D461
0x18002d45c  mov     rsi, r15
0x18002d45f  jmp     short loc_18002D4D2
0x18002d461  mov     r8, rdi
0x18002d464  mov     rax, r9
0x18002d467  sub     r8, r9
0x18002d46a  movzx   ecx, byte ptr [rax]
0x18002d46d  movzx   edx, byte ptr [rax+r8]
0x18002d472  sub     ecx, edx
0x18002d474  jnz     short loc_18002D47D
0x18002d476  add     rax, r13
0x18002d479  test    edx, edx
0x18002d47b  jnz     short loc_18002D46A
0x18002d47d  test    ecx, ecx
0x18002d47f  jnz     short loc_18002D486
0x18002d481  mov     rsi, r9
0x18002d484  jmp     short loc_18002D4D2
0x18002d486  mov     r8, rdi
0x18002d489  mov     rax, r10
0x18002d48c  sub     r8, r10
0x18002d48f  movzx   ecx, byte ptr [rax]
0x18002d492  movzx   edx, byte ptr [rax+r8]
0x18002d497  sub     ecx, edx
0x18002d499  jnz     short loc_18002D4A2
0x18002d49b  add     rax, r13
0x18002d49e  test    edx, edx
0x18002d4a0  jnz     short loc_18002D48F
0x18002d4a2  test    ecx, ecx
0x18002d4a4  jnz     short loc_18002D4AB
0x18002d4a6  mov     rsi, r10
0x18002d4a9  jmp     short loc_18002D4D2
0x18002d4ab  mov     r8, rdi
0x18002d4ae  mov     rax, r11
0x18002d4b1  sub     r8, r11
0x18002d4b4  movzx   ecx, byte ptr [rax]
0x18002d4b7  movzx   edx, byte ptr [rax+r8]
0x18002d4bc  sub     ecx, edx
0x18002d4be  jnz     short loc_18002D4C7
0x18002d4c0  add     rax, r13
0x18002d4c3  test    edx, edx
0x18002d4c5  jnz     short loc_18002D4B4
0x18002d4c7  test    ecx, ecx
0x18002d4c9  jnz     loc_18002D5D2
0x18002d4cf  mov     rsi, r11
0x18002d4d2  lea     r8, [rsp+68h+var_48]
0x18002d4d7  mov     edx, r13d
0x18002d4da  mov     rcx, rbp
0x18002d4dd  call    PReadUnsignedInt
0x18002d4e2  test    rax, rax
0x18002d4e5  jz      loc_18002D5A4
0x18002d4eb  mov     rcx, [rbx]
0x18002d4ee  test    rcx, rcx
0x18002d4f1  jz      loc_18002D5C8
0x18002d4f7  mov     rax, [rbx+8]
0x18002d4fb  mov     rax, [rax+28h]
0x18002d4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d504  mov     rbp, rax
0x18002d507  test    rax, rax
0x18002d50a  jz      loc_18002D5C8
0x18002d510  mov     edi, [rsp+68h+var_48]
0x18002d514  mov     ecx, 7FFFFFFFh
0x18002d519  cmp     r14, rsi
0x18002d51c  jnz     short loc_18002D52A
0x18002d51e  cmp     edi, ecx
0x18002d520  ja      short loc_18002D52A
0x18002d522  mov     [rax+0Ch], edi
0x18002d525  jmp     loc_18002D3D3
0x18002d52a  mov     eax, 7FA4h
0x18002d52f  cmp     r15, rsi
0x18002d532  jnz     short loc_18002D541
0x18002d534  cmp     edi, eax
0x18002d536  ja      short loc_18002D541
0x18002d538  mov     [rbp+16h], di
0x18002d53c  jmp     loc_18002D3D3
0x18002d541  lea     rdx, ?kstrPSWaitTimeout@@3PADA; "%WaitTimeout"
0x18002d548  cmp     rdx, rsi
0x18002d54b  jnz     short loc_18002D559
0x18002d54d  cmp     edi, ecx
0x18002d54f  ja      short loc_18002D559
0x18002d551  mov     [rbp+10h], edi
0x18002d554  jmp     loc_18002D3D3
0x18002d559  lea     rcx, ?kstrPSMinOutlineFont@@3PADA; "%MinFontSizeAsOutline"
0x18002d560  cmp     rcx, rsi
0x18002d563  jnz     short loc_18002D572
0x18002d565  cmp     edi, eax
0x18002d567  ja      short loc_18002D572
0x18002d569  mov     [rbp+14h], di
0x18002d56d  jmp     loc_18002D3D3
0x18002d572  lea     rax, ?kstrPSMemory@@3PADA; "%PSMemory"
0x18002d579  cmp     rax, rsi
0x18002d57c  jnz     short loc_18002D5A4
0x18002d57e  cmp     edi, 1FFFFFh
0x18002d584  ja      short loc_18002D5A4
0x18002d586  mov     rcx, rbx; this
0x18002d589  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002d58e  shl     edi, 0Ah
0x18002d591  test    rax, rax
0x18002d594  jz      short loc_18002D5C8
0x18002d596  cmp     [rax+50h], r13d
0x18002d59a  jnz     short loc_18002D5AE
0x18002d59c  cmp     edi, 2B000h
0x18002d5a2  jnb     short loc_18002D5C0
0x18002d5a4  mov     eax, 80004005h
0x18002d5a9  jmp     loc_18002D810
0x18002d5ae  mov     ecx, 2
0x18002d5b3  cmp     [rax+50h], ecx
0x18002d5b6  jnz     short loc_18002D5A4
0x18002d5b8  cmp     edi, 3E400h
0x18002d5be  jb      short loc_18002D5A4
0x18002d5c0  mov     [rbp+8], edi
0x18002d5c3  jmp     loc_18002D3D3
0x18002d5c8  mov     eax, 8000FFFFh
0x18002d5cd  jmp     loc_18002D810
0x18002d5d2  mov     r9, rbx; struct CPrintCoreConfig *
0x18002d5d5  mov     r8, rbp; char *
0x18002d5d8  mov     rdx, rdi; char *
0x18002d5db  mov     rcx, rsi; this
0x18002d5de  call    ?SetOptionInternal@CPrintAbstractHelper@@MEAAJPEBD0PEAVCPrintCoreConfig@@@Z; CPrintAbstractHelper::SetOptionInternal(char const *,char const *,CPrintCoreConfig *)
0x18002d5e3  mov     r15d, eax
0x18002d5e6  test    eax, eax
0x18002d5e8  js      loc_18002D80D
0x18002d5ee  lea     rcx, ?kstrPSPagesPerSheet@@3PADA; "%PagePerSheet"
0x18002d5f5  mov     rdx, rdi
0x18002d5f8  sub     rdx, rcx
0x18002d5fb  movzx   r9d, byte ptr [rcx]
0x18002d5ff  movzx   r8d, byte ptr [rcx+rdx]
0x18002d604  sub     r9d, r8d
0x18002d607  jnz     short loc_18002D611
0x18002d609  add     rcx, r13
0x18002d60c  test    r8d, r8d
0x18002d60f  jnz     short loc_18002D5FB
0x18002d611  mov     r14, 8618618618618619h
0x18002d61b  test    r9d, r9d
0x18002d61e  jnz     loc_18002D727
0x18002d624  lea     rax, ?kstrPSNUpBooklet@@3PADA; "Booklet"
0x18002d62b  sub     rbp, rax
0x18002d62e  movzx   ecx, byte ptr [rax]
0x18002d631  movzx   edx, byte ptr [rax+rbp]
0x18002d635  sub     ecx, edx
0x18002d637  jnz     short loc_18002D640
0x18002d639  add     rax, r13
0x18002d63c  test    edx, edx
0x18002d63e  jnz     short loc_18002D62E
  ... truncated ...
```
