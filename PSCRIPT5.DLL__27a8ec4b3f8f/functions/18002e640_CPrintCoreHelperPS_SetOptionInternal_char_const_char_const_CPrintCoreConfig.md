# CPrintCoreHelperPS::SetOptionInternal(char const *,char const *,CPrintCoreConfig *)

- ea: `0x18002e640`
- end: `0x18002ec40`
- name: `?SetOptionInternal@CPrintCoreHelperPS@@MEAAJPEBD0PEAVCPrintCoreConfig@@@Z`
- size: `1536`
- prototype: `__int64 __fastcall(CPrintCoreHelperPS *this, const char *, char *, struct CPrintCoreConfig *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18002d220`
- `0x18002d814`
- `0x18002d8a4`
- `0x18002e640`
- `0x1800338b0`
- `0x180034320`
- `0x180034384`
- `0x18005e094`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintCoreHelperPS::SetOptionInternal(
        CPrintCoreHelperPS *this,
        const char *a2,
        char *a3,
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
        v11 = *((unsigned __int8 *)v10 + a3 - (char *)&kstrPSOrientRotatedLandscape);
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
        v14 = *((unsigned __int8 *)v13 + a3 - (char *)&kstrPSOrientLandscape);
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
      && (unsigned int)CPrintCoreHelperPS::BIsCustomPageSizeSupported(v19, a4) )
    {
      v20 = *((_QWORD *)a4 + 2);
      if ( !v20 )
        v20 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a4 + 1) + 48LL))(*(_QWORD *)a4);
      UIInfo = CPrintCoreConfig::GetUIInfo(a4);
      if ( (unsigned int)BPSWriteCustomPageSize((__int64)UIInfo, v20, (__int64)a3) )
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
  if ( !PReadUnsignedInt(a3, 1, v69) )
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
0x18002e640  push    rbx
0x18002e642  push    rbp
0x18002e643  push    rsi
0x18002e644  push    rdi
0x18002e645  push    r13
0x18002e647  push    r14
0x18002e649  push    r15
0x18002e64b  sub     rsp, 30h
0x18002e64f  mov     rbx, r9
0x18002e652  lea     rax, ?kstrPSOrientation@@3PADA; "%Orientation"
0x18002e659  mov     r9, rdx
0x18002e65c  mov     rbp, r8
0x18002e65f  sub     r9, rax
0x18002e662  mov     rdi, rdx
0x18002e665  mov     rsi, rcx
0x18002e668  mov     r13d, 1
0x18002e66e  movzx   r8d, byte ptr [rax]
0x18002e672  movzx   edx, byte ptr [rax+r9]
0x18002e677  sub     r8d, edx
0x18002e67a  jnz     short loc_18002E683
0x18002e67c  add     rax, r13
0x18002e67f  test    edx, edx
0x18002e681  jnz     short loc_18002E66E
0x18002e683  test    r8d, r8d
0x18002e686  jnz     loc_18002E764
0x18002e68c  mov     rcx, rbx; this
0x18002e68f  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002e694  test    r13b, al
0x18002e697  jz      loc_18002E9C4
0x18002e69d  mov     rax, [rbx+10h]
0x18002e6a1  test    rax, rax
0x18002e6a4  jnz     short loc_18002E6B6
0x18002e6a6  mov     rax, [rbx+8]
0x18002e6aa  mov     rcx, [rbx]
0x18002e6ad  mov     rax, [rax+30h]
0x18002e6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6b6  movzx   edx, word ptr [rax+44h]
0x18002e6ba  lea     rcx, ?kstrPSOrientRotatedLandscape@@3PADA; "RotatedLandscape"
0x18002e6c1  mov     r10, rbp
0x18002e6c4  sub     r10, rcx
0x18002e6c7  movzx   r8d, byte ptr [rcx]
0x18002e6cb  movzx   r9d, byte ptr [rcx+r10]
0x18002e6d0  sub     r8d, r9d
0x18002e6d3  jnz     short loc_18002E6DD
0x18002e6d5  add     rcx, r13
0x18002e6d8  test    r9d, r9d
0x18002e6db  jnz     short loc_18002E6C7
0x18002e6dd  test    r8d, r8d
0x18002e6e0  jnz     short loc_18002E6F7
0x18002e6e2  or      [rax+48h], r13d
0x18002e6e6  mov     word ptr [rax+4Ch], 2
0x18002e6ec  bts     dword ptr [rdx+rax+4], 9
0x18002e6f2  jmp     loc_18002E7F3
0x18002e6f7  lea     rcx, ?kstrPSOrientLandscape@@3PADA; "Landscape"
0x18002e6fe  mov     r8, rbp
0x18002e701  sub     r8, rcx
0x18002e704  movzx   r9d, byte ptr [rcx]
0x18002e708  movzx   r10d, byte ptr [rcx+r8]
0x18002e70d  sub     r9d, r10d
0x18002e710  jnz     short loc_18002E71A
0x18002e712  add     rcx, r13
0x18002e715  test    r10d, r10d
0x18002e718  jnz     short loc_18002E704
0x18002e71a  test    r9d, r9d
0x18002e71d  jnz     short loc_18002E727
0x18002e71f  mov     word ptr [rax+4Ch], 2
0x18002e725  jmp     short loc_18002E755
0x18002e727  lea     rcx, ?kstrPSOrientPortrait@@3PADA; "Portrait"
0x18002e72e  sub     rbp, rcx
0x18002e731  movzx   r8d, byte ptr [rcx]
0x18002e735  movzx   r9d, byte ptr [rcx+rbp]
0x18002e73a  sub     r8d, r9d
0x18002e73d  jnz     short loc_18002E747
0x18002e73f  add     rcx, r13
0x18002e742  test    r9d, r9d
0x18002e745  jnz     short loc_18002E731
0x18002e747  test    r8d, r8d
0x18002e74a  jnz     loc_18002E9C4
0x18002e750  mov     [rax+4Ch], r13w
0x18002e755  or      [rax+48h], r13d
0x18002e759  btr     dword ptr [rdx+rax+4], 9
0x18002e75f  jmp     loc_18002E7F3
0x18002e764  lea     rax, ?kstrPSCustomPageSize@@3PADA; "%CustomPageSize"
0x18002e76b  mov     rcx, rdi
0x18002e76e  sub     rcx, rax
0x18002e771  movzx   edx, byte ptr [rax]
0x18002e774  movzx   r8d, byte ptr [rax+rcx]
0x18002e779  sub     edx, r8d
0x18002e77c  jnz     short loc_18002E786
0x18002e77e  add     rax, r13
0x18002e781  test    r8d, r8d
0x18002e784  jnz     short loc_18002E771
0x18002e786  mov     rcx, rbx; this
0x18002e789  test    edx, edx
0x18002e78b  jnz     short loc_18002E7FA
0x18002e78d  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002e792  test    r13b, al
0x18002e795  jz      loc_18002E9C4
0x18002e79b  mov     rdx, rbx; struct CPrintCoreConfig *
0x18002e79e  call    ?BIsCustomPageSizeSupported@CPrintCoreHelperPS@@AEAAHPEAVCPrintCoreConfig@@@Z; CPrintCoreHelperPS::BIsCustomPageSizeSupported(CPrintCoreConfig *)
0x18002e7a3  test    eax, eax
0x18002e7a5  jz      loc_18002E9C4
0x18002e7ab  mov     rdi, [rbx+10h]
0x18002e7af  test    rdi, rdi
0x18002e7b2  jnz     short loc_18002E7C7
0x18002e7b4  mov     rax, [rbx+8]
0x18002e7b8  mov     rcx, [rbx]
0x18002e7bb  mov     rax, [rax+30h]
0x18002e7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7c4  mov     rdi, rax
0x18002e7c7  mov     rcx, rbx; this
0x18002e7ca  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e7cf  mov     rcx, rax
0x18002e7d2  mov     r8, rbp
0x18002e7d5  mov     rdx, rdi
0x18002e7d8  call    BPSWriteCustomPageSize
0x18002e7dd  test    eax, eax
0x18002e7df  jz      loc_18002E9C4
0x18002e7e5  mov     ecx, 2
0x18002e7ea  mov     word ptr [rdi+4Eh], 7FFFh
0x18002e7f0  or      [rdi+48h], ecx
0x18002e7f3  xor     eax, eax
0x18002e7f5  jmp     loc_18002EC30
0x18002e7fa  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002e7ff  test    al, 4
0x18002e801  jz      loc_18002E9F2
0x18002e807  lea     r14, ?kstrPSJobTimeout@@3PADA; "%JobTimeout"
0x18002e80e  mov     [rsp+68h+var_48], 0
0x18002e816  mov     rcx, rdi
0x18002e819  mov     rax, r14
0x18002e81c  sub     rcx, r14
0x18002e81f  movzx   r8d, byte ptr [rax]
0x18002e823  movzx   edx, byte ptr [rax+rcx]
0x18002e827  sub     r8d, edx
0x18002e82a  jnz     short loc_18002E833
0x18002e82c  add     rax, r13
0x18002e82f  test    edx, edx
0x18002e831  jnz     short loc_18002E81F
0x18002e833  lea     r15, ?kstrPSMaxBMPFontSize@@3PADA; "%MaxFontSizeAsBitmap"
0x18002e83a  lea     r9, ?kstrPSWaitTimeout@@3PADA; "%WaitTimeout"
0x18002e841  lea     r10, ?kstrPSMinOutlineFont@@3PADA; "%MinFontSizeAsOutline"
0x18002e848  lea     r11, ?kstrPSMemory@@3PADA; "%PSMemory"
0x18002e84f  test    r8d, r8d
0x18002e852  jnz     short loc_18002E85C
0x18002e854  mov     rsi, r14
0x18002e857  jmp     loc_18002E8F2
0x18002e85c  mov     r8, rdi
0x18002e85f  mov     rax, r15
0x18002e862  sub     r8, r15
0x18002e865  movzx   ecx, byte ptr [rax]
0x18002e868  movzx   edx, byte ptr [rax+r8]
0x18002e86d  sub     ecx, edx
0x18002e86f  jnz     short loc_18002E878
0x18002e871  add     rax, r13
0x18002e874  test    edx, edx
0x18002e876  jnz     short loc_18002E865
0x18002e878  test    ecx, ecx
0x18002e87a  jnz     short loc_18002E881
0x18002e87c  mov     rsi, r15
0x18002e87f  jmp     short loc_18002E8F2
0x18002e881  mov     r8, rdi
0x18002e884  mov     rax, r9
0x18002e887  sub     r8, r9
0x18002e88a  movzx   ecx, byte ptr [rax]
0x18002e88d  movzx   edx, byte ptr [rax+r8]
0x18002e892  sub     ecx, edx
0x18002e894  jnz     short loc_18002E89D
0x18002e896  add     rax, r13
0x18002e899  test    edx, edx
0x18002e89b  jnz     short loc_18002E88A
0x18002e89d  test    ecx, ecx
0x18002e89f  jnz     short loc_18002E8A6
0x18002e8a1  mov     rsi, r9
0x18002e8a4  jmp     short loc_18002E8F2
0x18002e8a6  mov     r8, rdi
0x18002e8a9  mov     rax, r10
0x18002e8ac  sub     r8, r10
0x18002e8af  movzx   ecx, byte ptr [rax]
0x18002e8b2  movzx   edx, byte ptr [rax+r8]
0x18002e8b7  sub     ecx, edx
0x18002e8b9  jnz     short loc_18002E8C2
0x18002e8bb  add     rax, r13
0x18002e8be  test    edx, edx
0x18002e8c0  jnz     short loc_18002E8AF
0x18002e8c2  test    ecx, ecx
0x18002e8c4  jnz     short loc_18002E8CB
0x18002e8c6  mov     rsi, r10
0x18002e8c9  jmp     short loc_18002E8F2
0x18002e8cb  mov     r8, rdi
0x18002e8ce  mov     rax, r11
0x18002e8d1  sub     r8, r11
0x18002e8d4  movzx   ecx, byte ptr [rax]
0x18002e8d7  movzx   edx, byte ptr [rax+r8]
0x18002e8dc  sub     ecx, edx
0x18002e8de  jnz     short loc_18002E8E7
0x18002e8e0  add     rax, r13
0x18002e8e3  test    edx, edx
0x18002e8e5  jnz     short loc_18002E8D4
0x18002e8e7  test    ecx, ecx
0x18002e8e9  jnz     loc_18002E9F2
0x18002e8ef  mov     rsi, r11
0x18002e8f2  lea     r8, [rsp+68h+var_48]
0x18002e8f7  mov     edx, r13d
0x18002e8fa  mov     rcx, rbp
0x18002e8fd  call    PReadUnsignedInt
0x18002e902  test    rax, rax
0x18002e905  jz      loc_18002E9C4
0x18002e90b  mov     rcx, [rbx]
0x18002e90e  test    rcx, rcx
0x18002e911  jz      loc_18002E9E8
0x18002e917  mov     rax, [rbx+8]
0x18002e91b  mov     rax, [rax+28h]
0x18002e91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e924  mov     rbp, rax
0x18002e927  test    rax, rax
0x18002e92a  jz      loc_18002E9E8
0x18002e930  mov     edi, [rsp+68h+var_48]
0x18002e934  mov     ecx, 7FFFFFFFh
0x18002e939  cmp     r14, rsi
0x18002e93c  jnz     short loc_18002E94A
0x18002e93e  cmp     edi, ecx
0x18002e940  ja      short loc_18002E94A
0x18002e942  mov     [rax+0Ch], edi
0x18002e945  jmp     loc_18002E7F3
0x18002e94a  mov     eax, 7FA4h
0x18002e94f  cmp     r15, rsi
0x18002e952  jnz     short loc_18002E961
0x18002e954  cmp     edi, eax
0x18002e956  ja      short loc_18002E961
0x18002e958  mov     [rbp+16h], di
0x18002e95c  jmp     loc_18002E7F3
0x18002e961  lea     rdx, ?kstrPSWaitTimeout@@3PADA; "%WaitTimeout"
0x18002e968  cmp     rdx, rsi
0x18002e96b  jnz     short loc_18002E979
0x18002e96d  cmp     edi, ecx
0x18002e96f  ja      short loc_18002E979
0x18002e971  mov     [rbp+10h], edi
0x18002e974  jmp     loc_18002E7F3
0x18002e979  lea     rcx, ?kstrPSMinOutlineFont@@3PADA; "%MinFontSizeAsOutline"
0x18002e980  cmp     rcx, rsi
0x18002e983  jnz     short loc_18002E992
0x18002e985  cmp     edi, eax
0x18002e987  ja      short loc_18002E992
0x18002e989  mov     [rbp+14h], di
0x18002e98d  jmp     loc_18002E7F3
0x18002e992  lea     rax, ?kstrPSMemory@@3PADA; "%PSMemory"
0x18002e999  cmp     rax, rsi
0x18002e99c  jnz     short loc_18002E9C4
0x18002e99e  cmp     edi, 1FFFFFh
0x18002e9a4  ja      short loc_18002E9C4
0x18002e9a6  mov     rcx, rbx; this
0x18002e9a9  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e9ae  shl     edi, 0Ah
0x18002e9b1  test    rax, rax
0x18002e9b4  jz      short loc_18002E9E8
0x18002e9b6  cmp     [rax+50h], r13d
0x18002e9ba  jnz     short loc_18002E9CE
0x18002e9bc  cmp     edi, 2B000h
0x18002e9c2  jnb     short loc_18002E9E0
0x18002e9c4  mov     eax, 80004005h
0x18002e9c9  jmp     loc_18002EC30
0x18002e9ce  mov     ecx, 2
0x18002e9d3  cmp     [rax+50h], ecx
0x18002e9d6  jnz     short loc_18002E9C4
0x18002e9d8  cmp     edi, 3E400h
0x18002e9de  jb      short loc_18002E9C4
0x18002e9e0  mov     [rbp+8], edi
0x18002e9e3  jmp     loc_18002E7F3
0x18002e9e8  mov     eax, 8000FFFFh
0x18002e9ed  jmp     loc_18002EC30
0x18002e9f2  mov     r9, rbx; struct CPrintCoreConfig *
0x18002e9f5  mov     r8, rbp; char *
0x18002e9f8  mov     rdx, rdi; char *
0x18002e9fb  mov     rcx, rsi; this
0x18002e9fe  call    ?SetOptionInternal@CPrintAbstractHelper@@MEAAJPEBD0PEAVCPrintCoreConfig@@@Z; CPrintAbstractHelper::SetOptionInternal(char const *,char const *,CPrintCoreConfig *)
0x18002ea03  mov     r15d, eax
0x18002ea06  test    eax, eax
0x18002ea08  js      loc_18002EC2D
0x18002ea0e  lea     rcx, ?kstrPSPagesPerSheet@@3PADA; "%PagePerSheet"
0x18002ea15  mov     rdx, rdi
0x18002ea18  sub     rdx, rcx
0x18002ea1b  movzx   r9d, byte ptr [rcx]
0x18002ea1f  movzx   r8d, byte ptr [rcx+rdx]
0x18002ea24  sub     r9d, r8d
0x18002ea27  jnz     short loc_18002EA31
0x18002ea29  add     rcx, r13
0x18002ea2c  test    r8d, r8d
0x18002ea2f  jnz     short loc_18002EA1B
0x18002ea31  mov     r14, 8618618618618619h
0x18002ea3b  test    r9d, r9d
0x18002ea3e  jnz     loc_18002EB47
0x18002ea44  lea     rax, ?kstrPSNUpBooklet@@3PADA; "Booklet"
0x18002ea4b  sub     rbp, rax
0x18002ea4e  movzx   ecx, byte ptr [rax]
0x18002ea51  movzx   edx, byte ptr [rax+rbp]
0x18002ea55  sub     ecx, edx
0x18002ea57  jnz     short loc_18002EA60
0x18002ea59  add     rax, r13
0x18002ea5c  test    edx, edx
0x18002ea5e  jnz     short loc_18002EA4E
  ... truncated ...
```
