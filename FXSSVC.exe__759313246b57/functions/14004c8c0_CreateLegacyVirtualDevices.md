# CreateLegacyVirtualDevices

- ea: `0x14004c8c0`
- end: `0x14004d26a`
- name: `CreateLegacyVirtualDevices`
- size: `2474`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004d358`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140004fe4`
- `0x1400259bc`
- `0x140026c14`
- `0x14004c8c0`
- `0x14004d5c4`
- `0x1400519a0`
- `0x140051b0c`
- `0x1400698ec`
- `0x14006998c`
- `0x1400699d0`
- `0x14006af2c`
- `0x140083540`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004c9e6`
- `KERNEL32!GetLastError` at `0x14004cb2a`
- `KERNEL32!GetLastError` at `0x14004cb51`
- `KERNEL32!GetLastError` at `0x14004cec0`
- `KERNEL32!GetLastError` at `0x14004cef3`
- `KERNEL32!GetLastError` at `0x14004d031`
- `KERNEL32!GetLastError` at `0x14004d064`
- `KERNEL32!GetLastError` at `0x14004d09c`
- `KERNEL32!GetLastError` at `0x14004d0cf`
- `KERNEL32!GetLastError` at `0x14004d136`
- `KERNEL32!GetLastError` at `0x14004c9e6`
- `KERNEL32!GetLastError` at `0x14004cb2a`
- `KERNEL32!GetLastError` at `0x14004cb51`
- `KERNEL32!GetLastError` at `0x14004cec0`
- `KERNEL32!GetLastError` at `0x14004cef3`
- `KERNEL32!GetLastError` at `0x14004d031`
- `KERNEL32!GetLastError` at `0x14004d064`
- `KERNEL32!GetLastError` at `0x14004d09c`
- `KERNEL32!GetLastError` at `0x14004d0cf`
- `KERNEL32!GetLastError` at `0x14004d136`
- `KERNEL32!SetLastError` at `0x14004cfb8`
- `KERNEL32!SetLastError` at `0x14004cfb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CreateLegacyVirtualDevices(__int64 a1, unsigned __int16 **a2, __int64 a3, _DWORD *a4)
{
  unsigned int v6; // ebx
  DWORD v7; // r14d
  char LastError; // al
  _QWORD *v9; // r13
  CMapDeviceId *v10; // rcx
  DWORD_PTR i; // rsi
  _QWORD *v12; // rax
  int v13; // edx
  int v14; // r8d
  int v15; // r12d
  __int64 v16; // rax
  unsigned int v17; // esi
  unsigned __int16 *v18; // rax
  int v19; // eax
  DWORD v20; // esi
  __int64 v21; // r13
  unsigned int v22; // r8d
  __int64 v23; // r11
  __int64 v24; // rdx
  unsigned __int16 *v25; // rax
  __int64 v26; // r10
  int v27; // ecx
  int v28; // r9d
  DWORD v29; // eax
  int v30; // eax
  void *v31; // rax
  __int64 v32; // rsi
  unsigned __int16 *v33; // rax
  unsigned __int16 **v34; // rdx
  int v35; // eax
  unsigned __int16 *v36; // rax
  DWORD v37; // eax
  int v38; // r8d
  int v39; // edx
  int v40; // eax
  __int64 *v41; // rax
  int v42; // eax
  bool v43; // zf
  DWORD v45; // eax
  unsigned int j; // esi
  __int64 *v47; // rax
  __int64 v48; // rcx
  _QWORD *v49; // rax
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // [rsp+20h] [rbp-1E8h]
  unsigned int v53; // [rsp+50h] [rbp-1B8h] BYREF
  _QWORD *v54; // [rsp+58h] [rbp-1B0h]
  unsigned int v55; // [rsp+60h] [rbp-1A8h] BYREF
  __int64 v56; // [rsp+68h] [rbp-1A0h]
  int v57; // [rsp+70h] [rbp-198h] BYREF
  int v58; // [rsp+78h] [rbp-190h]
  unsigned __int16 **v59; // [rsp+80h] [rbp-188h]
  __int64 v60; // [rsp+88h] [rbp-180h]
  unsigned __int16 **v61; // [rsp+90h] [rbp-178h]
  _DWORD *v62; // [rsp+98h] [rbp-170h]
  __int64 v63; // [rsp+A0h] [rbp-168h]
  __int64 v64; // [rsp+A8h] [rbp-160h]
  unsigned __int16 **v65; // [rsp+B0h] [rbp-158h]
  _DWORD *v66; // [rsp+B8h] [rbp-150h]
  _WORD v67[128]; // [rsp+C0h] [rbp-148h] BYREF

  v62 = a4;
  v60 = a3;
  v61 = a2;
  v63 = a1;
  v65 = a2;
  v64 = a1;
  v59 = a2;
  v56 = a3;
  v66 = a4;
  v6 = 0;
  v53 = 0;
  memset_0(v67, 0, sizeof(v67));
  v55 = 0;
  v54 = 0;
  v7 = 0;
  v58 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  *a4 = 0;
  if ( !(*(unsigned int (__fastcall **)(unsigned int *, _WORD *, unsigned int *, HANDLE, __int64))(a3 + 2224))(
          &v53,
          v67,
          &v55,
          g_TapiCompletionPort,
          2147483650LL) )
  {
    v7 = 1;
    v58 = 1;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        111,
        (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        a3 + 64,
        LastError);
    }
    v9 = 0;
    goto LABEL_122;
  }
  if ( !v53 )
  {
    v7 = 1;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
    }
    goto LABEL_121;
  }
  if ( v53 <= 0x100 )
  {
    v10 = WPP_GLOBAL_Control;
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v53);
      v10 = WPP_GLOBAL_Control;
    }
    v53 = 256;
  }
  if ( v55 - 1 > 0xFFFE )
  {
    v7 = 1;
    if ( v10 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 2u )
      WPP_SF_Sd(*((_QWORD *)v10 + 2), 113, (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, a3 + 64, v55);
    goto LABEL_121;
  }
  for ( i = g_TapiLinesListHead; (DWORD_PTR *)i != &g_TapiLinesListHead; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 24) >= v55 && *(_DWORD *)(i + 24) <= v55 + v53 )
    {
      v7 = 1;
      FaxLog(1, 1, 2, 3221257569LL);
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SlS(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, a3 + 64, v55, *(_QWORD *)(i + 40) + 64LL);
      }
      goto LABEL_121;
    }
  }
  v12 = (_QWORD *)pMemAlloc(8LL * v53);
  v9 = v12;
  v54 = v12;
  if ( !v12 )
  {
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      GetLastError();
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
    }
    goto LABEL_122;
  }
  memset_0(v12, 0, 8LL * v53);
  if ( v53 )
  {
    v15 = 0;
    while ( 1 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v67[v16] );
      v17 = 2 * v16 + 18;
      v18 = (unsigned __int16 *)pMemAlloc(v17);
      v56 = (__int64)v18;
      if ( !v18 )
      {
        v45 = GetLastError();
        v7 = v45;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v45);
        }
        goto LABEL_121;
      }
      LODWORD(v52) = v15;
      v19 = StringCbPrintfW(v18, v17, L"%s%d", v67, v52);
      v20 = v19;
      if ( v19 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117,
            &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
            (unsigned int)v19);
        }
        v9 = v54;
        if ( (v20 & 0x1FFF0000) == 0x70000 )
          v7 = (unsigned __int16)v20;
        else
          v7 = v20;
        goto LABEL_122;
      }
      v21 = 0;
      if ( *(_DWORD *)(v63 + 40) )
      {
        v22 = 0;
        v23 = *(_QWORD *)(v63 + 32);
        while ( 1 )
        {
          v24 = v23 + 88LL * v22;
          if ( *(_DWORD *)(v24 + 60) == 1 )
          {
            v25 = *(unsigned __int16 **)(v24 + 72);
            v26 = v60 + 1624 - (_QWORD)v25;
            do
            {
              v27 = *(unsigned __int16 *)((char *)v25 + v26);
              v28 = *v25 - v27;
              if ( v28 )
                break;
              ++v25;
            }
            while ( v27 );
            if ( !v28 && *(_DWORD *)v24 == v15 + v55 )
              break;
          }
          if ( ++v22 >= *(_DWORD *)(v63 + 40) )
            goto LABEL_52;
        }
        v21 = v23 + 88LL * v22;
      }
LABEL_52:
      if ( v21 )
      {
        v30 = *(_DWORD *)(v21 + 64);
      }
      else
      {
        v57 = v15 + v55;
        v52 = v60 + 1624;
        v29 = RegAddNewFaxDevice((char *)g_pFaxConfig + 112, &v57, v56);
        v7 = v29;
        if ( v29 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v29);
          }
          goto LABEL_121;
        }
        v30 = v57;
      }
      v57 = v30;
      v31 = (void *)pMemAlloc(0xC0u);
      v32 = (__int64)v31;
      if ( !v31 )
      {
        v7 = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v37 = GetLastError();
          v39 = 119;
          goto LABEL_97;
        }
        goto LABEL_121;
      }
      memset_0(v31, 0, 0xC0u);
      v54[*v62] = v32;
      *(_DWORD *)(v32 + 16) = 1162758476;
      *(_DWORD *)(v32 + 20) = v15;
      *(_DWORD *)(v32 + 28) = v15 + v55;
      *(_DWORD *)(v32 + 24) = v57;
      *(_DWORD *)(v32 + 32) = 0;
      *(_QWORD *)(v32 + 40) = v60;
      *(_QWORD *)(v32 + 56) = v56;
      *(_DWORD *)(v32 + 104) = 0;
      *(_DWORD *)(v32 + 72) = 537919488;
      if ( v21 )
      {
        *(_QWORD *)(v32 + 88) = StringDup(*(unsigned __int16 **)(v21 + 24));
        *(_QWORD *)(v32 + 96) = StringDup(*(unsigned __int16 **)(v21 + 32));
        v33 = StringDup(*(unsigned __int16 **)(v21 + 48));
        *(_QWORD *)(v32 + 64) = v33;
        if ( *(_QWORD *)(v21 + 24) && !*(_QWORD *)(v32 + 88)
          || *(_QWORD *)(v21 + 32) && !*(_QWORD *)(v32 + 96)
          || *(_QWORD *)(v21 + 48) && !v33 )
        {
          v7 = GetLastError();
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v37 = GetLastError();
            v39 = 120;
            goto LABEL_97;
          }
          goto LABEL_121;
        }
        v34 = v59;
      }
      else
      {
        *(_QWORD *)(v32 + 88) = StringDup(*v61);
        v36 = StringDup(v59[1]);
        *(_QWORD *)(v32 + 96) = v36;
        *(_QWORD *)(v32 + 64) = 0;
        if ( *v61 && !*(_QWORD *)(v32 + 88) || (v34 = v59, v59[1]) && !v36 )
        {
          v7 = GetLastError();
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v37 = GetLastError();
            v39 = 121;
LABEL_97:
            WPP_SF_ldS(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, v38, v37, v15, v56);
          }
LABEL_121:
          v9 = v54;
LABEL_122:
          if ( v9 )
          {
            for ( j = 0; j < v53; ++j )
            {
              v47 = (__int64 *)v9[j];
              if ( v47 )
              {
                v48 = *v47;
                v49 = (_QWORD *)v47[1];
                *v49 = v48;
                *(_QWORD *)(v48 + 8) = v49;
                *(_QWORD *)v9[j] = 0;
                *(_QWORD *)(v9[j] + 8LL) = 0;
                v50 = v9[j];
                if ( (*(_BYTE *)(v50 + 76) & 3) != 0 || (v51 = 0, *(_DWORD *)(v50 + 24) == g_dwManualAnswerDeviceId) )
                  v51 = 1;
                if ( v51 == 1 )
                  --g_dwDeviceEnabledCount;
                FreeTapiLine((struct _LINE_INFO *)v50);
              }
            }
          }
          *v62 = 0;
          break;
        }
      }
      if ( v21 )
        v35 = *(_DWORD *)(v21 + 20);
      else
        v35 = 1;
      *(_DWORD *)(v32 + 108) = v35;
      *(_DWORD *)(v32 + 112) = 0;
      *(_DWORD *)(v32 + 164) = 0;
      *(_QWORD *)(v32 + 80) = 0;
      *(_QWORD *)(v32 + 176) = 0;
      *(_DWORD *)(v32 + 184) = v21 != 0 ? 4 : 1;
      if ( v21 )
        v40 = *(_DWORD *)(v21 + 16);
      else
        v40 = *((_DWORD *)v34 + 7) | 4;
      *(_DWORD *)(v32 + 76) = v40;
      v41 = (__int64 *)qword_1400A7740;
      *(_QWORD *)v32 = &g_TapiLinesListHead;
      *(_QWORD *)(v32 + 8) = v41;
      *v41 = v32;
      qword_1400A7740 = v32;
      ++*v62;
      if ( (*(_BYTE *)(v32 + 76) & 3) != 0 || (v42 = 0, *(_DWORD *)(v32 + 24) == g_dwManualAnswerDeviceId) )
        v42 = 1;
      if ( v42 == 1 )
        ++g_dwDeviceEnabledCount;
      if ( ++v15 >= v53 )
      {
        v9 = v54;
        break;
      }
    }
  }
  pMemFree(v9);
  v43 = v7 == 0;
  if ( v7 )
  {
    SetLastError(v7);
    v43 = v7 == 0;
  }
  LOBYTE(v6) = v43;
  return v6;
}

```

## disassembly

```asm
0x14004c8c0  push    rbx
0x14004c8c2  push    rsi
0x14004c8c3  push    rdi
0x14004c8c4  push    r12
0x14004c8c6  push    r13
0x14004c8c8  push    r14
0x14004c8ca  push    r15
0x14004c8cc  sub     rsp, 1D0h
0x14004c8d3  mov     rax, cs:__security_cookie
0x14004c8da  xor     rax, rsp
0x14004c8dd  mov     [rsp+208h+var_48], rax
0x14004c8e5  mov     r12, r9
0x14004c8e8  mov     [rsp+208h+var_170], r9
0x14004c8f0  mov     r13, r8
0x14004c8f3  mov     [rsp+208h+var_180], r8
0x14004c8fb  mov     [rsp+208h+var_178], rdx
0x14004c903  mov     [rsp+208h+var_168], rcx
0x14004c90b  mov     [rsp+208h+var_158], rdx
0x14004c913  mov     [rsp+208h+var_160], rcx
0x14004c91b  mov     [rsp+208h+var_188], rdx
0x14004c923  mov     [rsp+208h+var_1A0], r8
0x14004c928  mov     [rsp+208h+var_150], r9
0x14004c930  xor     ebx, ebx
0x14004c932  mov     [rsp+208h+var_1B8], ebx
0x14004c936  xor     edx, edx; Val
0x14004c938  mov     r8d, 100h; Size
0x14004c93e  lea     rcx, [rsp+208h+var_148]; void *
0x14004c946  call    memset_0
0x14004c94b  mov     [rsp+208h+var_1A8], ebx
0x14004c94f  mov     [rsp+208h+var_1B0], rbx
0x14004c954  mov     r14d, ebx
0x14004c957  mov     [rsp+208h+var_190], ebx
0x14004c95b  lea     r15, WPP_GLOBAL_Control
0x14004c962  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c969  cmp     rcx, r15
0x14004c96c  jz      short loc_14004C98D
0x14004c96e  test    byte ptr [rcx+1Ch], 4
0x14004c972  jz      short loc_14004C98D
0x14004c974  cmp     byte ptr [rcx+19h], 5
0x14004c978  jb      short loc_14004C98D
0x14004c97a  lea     edx, [rbx+6Eh]
0x14004c97d  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004c984  mov     rcx, [rcx+10h]
0x14004c988  call    WPP_SF_
0x14004c98d  mov     [r12], ebx
0x14004c991  mov     eax, 80000002h
0x14004c996  mov     [rsp+208h+var_1E8], rax
0x14004c99b  mov     r9, cs:?g_TapiCompletionPort@@3PEAXEA; void * g_TapiCompletionPort
0x14004c9a2  lea     r8, [rsp+208h+var_1A8]
0x14004c9a7  lea     rdx, [rsp+208h+var_148]
0x14004c9af  lea     rcx, [rsp+208h+var_1B8]
0x14004c9b4  mov     rax, [r13+8B0h]
0x14004c9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c9c0  test    eax, eax
0x14004c9c2  jnz     short loc_14004CA1C
0x14004c9c4  lea     edi, [rax+1]
0x14004c9c7  mov     r14d, edi
0x14004c9ca  mov     [rsp+208h+var_190], edi
0x14004c9ce  mov     rax, cs:WPP_GLOBAL_Control
0x14004c9d5  cmp     rax, r15
0x14004c9d8  jz      short loc_14004CA14
0x14004c9da  test    byte ptr [rax+1Ch], 4
0x14004c9de  jz      short loc_14004CA14
0x14004c9e0  cmp     byte ptr [rax+19h], 2
0x14004c9e4  jb      short loc_14004CA14
0x14004c9e6  call    cs:__imp_GetLastError
0x14004c9ed  nop     dword ptr [rax+rax+00h]
0x14004c9f2  lea     r9, [r13+40h]
0x14004c9f6  lea     edx, [rdi+6Eh]
0x14004c9f9  mov     dword ptr [rsp+208h+var_1E8], eax
0x14004c9fd  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004ca04  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ca0b  mov     rcx, [rcx+10h]
0x14004ca0f  call    WPP_SF_Sd
0x14004ca14  mov     r13, rbx
0x14004ca17  jmp     loc_14004D1F2
0x14004ca1c  jmp     short loc_14004CA6E
0x14004ca1e  xor     ebx, ebx
0x14004ca20  lea     r15, WPP_GLOBAL_Control
0x14004ca27  mov     [rsp+208h+var_1B0], rbx
0x14004ca2c  mov     r14d, [rsp+208h+var_190]
0x14004ca31  mov     rax, [rsp+208h+var_160]
0x14004ca39  mov     [rsp+208h+var_168], rax
0x14004ca41  mov     r13, [rsp+208h+var_1A0]
0x14004ca46  mov     [rsp+208h+var_180], r13
0x14004ca4e  mov     rax, [rsp+208h+var_158]
0x14004ca56  mov     [rsp+208h+var_178], rax
0x14004ca5e  mov     rax, [rsp+208h+var_150]
0x14004ca66  mov     [rsp+208h+var_170], rax
0x14004ca6e  mov     r9d, [rsp+208h+var_1B8]
0x14004ca73  test    r9d, r9d
0x14004ca76  jz      loc_14004D1BA
0x14004ca7c  cmp     r9d, 100h
0x14004ca83  jbe     short loc_14004CAC3
0x14004ca85  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ca8c  cmp     rcx, r15
0x14004ca8f  jz      short loc_14004CAB9
0x14004ca91  test    byte ptr [rcx+1Ch], 4
0x14004ca95  jz      short loc_14004CAB9
0x14004ca97  cmp     byte ptr [rcx+19h], 5
0x14004ca9b  jb      short loc_14004CAB9
0x14004ca9d  mov     edx, 70h ; 'p'
0x14004caa2  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004caa9  mov     rcx, [rcx+10h]
0x14004caad  call    WPP_SF_d
0x14004cab2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cab9  mov     [rsp+208h+var_1B8], 100h
0x14004cac1  jmp     short loc_14004CACA
0x14004cac3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004caca  mov     r8d, [rsp+208h+var_1A8]
0x14004cacf  lea     eax, [r8-1]
0x14004cad3  cmp     eax, 0FFFEh
0x14004cad8  ja      loc_14004D183
0x14004cade  mov     rsi, cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14004cae5  lea     rdx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14004caec  jmp     short loc_14004CB07
0x14004caee  cmp     [rsi+18h], r8d
0x14004caf2  jb      short loc_14004CB04
0x14004caf4  mov     ecx, [rsp+208h+var_1B8]
0x14004caf8  add     ecx, r8d
0x14004cafb  cmp     [rsi+18h], ecx
0x14004cafe  jbe     loc_14004CB8B
0x14004cb04  mov     rsi, [rsi]
0x14004cb07  cmp     rsi, rdx
0x14004cb0a  jnz     short loc_14004CAEE
0x14004cb0c  mov     ecx, [rsp+208h+var_1B8]
0x14004cb10  shl     rcx, 3; dwBytes
0x14004cb14  call    pMemAlloc
0x14004cb19  mov     r13, rax
0x14004cb1c  mov     [rsp+208h+var_1B0], rax
0x14004cb21  test    rax, rax
0x14004cb24  jnz     loc_14004CC06
0x14004cb2a  call    cs:__imp_GetLastError
0x14004cb31  nop     dword ptr [rax+rax+00h]
0x14004cb36  mov     r14d, eax
0x14004cb39  mov     rax, cs:WPP_GLOBAL_Control
0x14004cb40  cmp     rax, r15
0x14004cb43  jz      short loc_14004CB81
0x14004cb45  test    byte ptr [rax+1Ch], 4
0x14004cb49  jz      short loc_14004CB81
0x14004cb4b  cmp     byte ptr [rax+19h], 2
0x14004cb4f  jb      short loc_14004CB81
0x14004cb51  call    cs:__imp_GetLastError
0x14004cb58  nop     dword ptr [rax+rax+00h]
0x14004cb5d  lea     edx, [r13+73h]
0x14004cb61  mov     dword ptr [rsp+208h+var_1E8], eax
0x14004cb65  mov     r9d, [rsp+208h+var_1B8]
0x14004cb6a  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004cb71  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cb78  mov     rcx, [rcx+10h]
0x14004cb7c  call    WPP_SF_dd
0x14004cb81  mov     edi, 1
0x14004cb86  jmp     loc_14004D1F2
0x14004cb8b  mov     edi, 1
0x14004cb90  mov     r14d, edi
0x14004cb93  lea     r12, [r13+40h]
0x14004cb97  mov     rax, [rsi+28h]
0x14004cb9b  add     rax, 40h ; '@'
0x14004cb9f  mov     [rsp+208h+var_1E0], rax
0x14004cba4  mov     [rsp+208h+var_1E8], r12
0x14004cba9  mov     r9d, 0C0007D61h
0x14004cbaf  lea     r8d, [rdi+1]
0x14004cbb3  mov     edx, edi
0x14004cbb5  mov     ecx, edi
0x14004cbb7  call    FaxLog
0x14004cbbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cbc3  cmp     rcx, r15
0x14004cbc6  jz      loc_14004D1ED
0x14004cbcc  test    byte ptr [rcx+1Ch], 4
0x14004cbd0  jz      loc_14004D1ED
0x14004cbd6  cmp     byte ptr [rcx+19h], 2
0x14004cbda  jb      loc_14004D1ED
0x14004cbe0  mov     rax, [rsi+28h]
0x14004cbe4  add     rax, 40h ; '@'
0x14004cbe8  mov     [rsp+208h+var_1E0], rax
0x14004cbed  mov     eax, [rsp+208h+var_1A8]
0x14004cbf1  mov     dword ptr [rsp+208h+var_1E8], eax
0x14004cbf5  mov     r9, r12
0x14004cbf8  mov     rcx, [rcx+10h]
0x14004cbfc  call    WPP_SF_SlS
0x14004cc01  jmp     loc_14004D1ED
0x14004cc06  mov     r8d, [rsp+208h+var_1B8]
0x14004cc0b  shl     r8, 3; Size
0x14004cc0f  xor     edx, edx; Val
0x14004cc11  mov     rcx, rax; void *
0x14004cc14  call    memset_0
0x14004cc19  cmp     [rsp+208h+var_1B8], ebx
0x14004cc1d  jbe     loc_14004CFA8
0x14004cc23  mov     r12d, ebx
0x14004cc26  mov     edi, 1
0x14004cc2b  lea     rcx, [rsp+208h+var_148]
0x14004cc33  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004cc37  inc     rax
0x14004cc3a  cmp     [rcx+rax*2], bx
0x14004cc3e  jnz     short loc_14004CC37
0x14004cc40  lea     eax, ds:12h[rax*2]
0x14004cc47  mov     esi, eax
0x14004cc49  mov     ecx, eax; dwBytes
0x14004cc4b  call    pMemAlloc
0x14004cc50  mov     [rsp+208h+var_1A0], rax
0x14004cc55  test    rax, rax
0x14004cc58  jz      loc_14004D136
0x14004cc5e  mov     dword ptr [rsp+208h+var_1E8], r12d
0x14004cc63  lea     r9, [rsp+208h+var_148]
0x14004cc6b  lea     r8, aSD; "%s%d"
0x14004cc72  mov     edx, esi; unsigned __int64
0x14004cc74  mov     rcx, rax; unsigned __int16 *
0x14004cc77  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004cc7c  mov     esi, eax
0x14004cc7e  test    eax, eax
0x14004cc80  js      loc_14004D0E2
0x14004cc86  mov     r13, rbx
0x14004cc89  mov     rax, [rsp+208h+var_168]
0x14004cc91  mov     rsi, [rsp+208h+var_180]
0x14004cc99  cmp     [rax+28h], ebx
0x14004cc9c  jbe     short loc_14004CCFE
0x14004cc9e  mov     r8d, ebx
0x14004cca1  mov     r11, [rax+20h]
0x14004cca5  mov     eax, r8d
0x14004cca8  imul    rdx, rax, 58h ; 'X'
0x14004ccac  add     rdx, r11
0x14004ccaf  cmp     [rdx+3Ch], edi
0x14004ccb2  jnz     short loc_14004CCE8
0x14004ccb4  lea     r10, [rsi+658h]
0x14004ccbb  mov     rax, [rdx+48h]
0x14004ccbf  sub     r10, rax
0x14004ccc2  movzx   r9d, word ptr [rax]
0x14004ccc6  movzx   ecx, word ptr [rax+r10]
0x14004cccb  sub     r9d, ecx
0x14004ccce  jnz     short loc_14004CCD8
0x14004ccd0  add     rax, 2
0x14004ccd4  test    ecx, ecx
0x14004ccd6  jnz     short loc_14004CCC2
0x14004ccd8  test    r9d, r9d
0x14004ccdb  jnz     short loc_14004CCE8
0x14004ccdd  mov     ecx, [rsp+208h+var_1A8]
0x14004cce1  add     ecx, r12d
0x14004cce4  cmp     [rdx], ecx
0x14004cce6  jz      short loc_14004CCFB
0x14004cce8  add     r8d, edi
0x14004cceb  mov     rax, [rsp+208h+var_168]
0x14004ccf3  cmp     r8d, [rax+28h]
0x14004ccf7  jb      short loc_14004CCA5
0x14004ccf9  jmp     short loc_14004CCFE
0x14004ccfb  mov     r13, rdx
0x14004ccfe  test    r13, r13
0x14004cd01  jnz     short loc_14004CD79
0x14004cd03  mov     edx, [rsp+208h+var_1A8]
0x14004cd07  add     edx, r12d
0x14004cd0a  mov     [rsp+208h+var_198], edx
0x14004cd0e  mov     r9, [rsp+208h+var_188]
0x14004cd16  mov     eax, [r9+1Ch]
0x14004cd1a  or      eax, 4
0x14004cd1d  lea     r8, [rsi+658h]
0x14004cd24  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14004cd2b  add     rcx, 70h ; 'p'
0x14004cd2f  mov     [rsp+208h+var_1C0], edi
0x14004cd33  mov     [rsp+208h+var_1C8], eax
0x14004cd37  mov     [rsp+208h+var_1D0], edx
0x14004cd3b  mov     rax, [r9+8]
0x14004cd3f  mov     [rsp+208h+var_1D8], rax
0x14004cd44  mov     rax, [rsp+208h+var_178]
0x14004cd4c  mov     rax, [rax]
0x14004cd4f  mov     [rsp+208h+var_1E0], rax
0x14004cd54  mov     [rsp+208h+var_1E8], r8
0x14004cd59  mov     r8, [rsp+208h+var_1A0]
0x14004cd5e  lea     rdx, [rsp+208h+var_198]
0x14004cd63  call    RegAddNewFaxDevice
0x14004cd68  mov     r14d, eax
0x14004cd6b  test    eax, eax
0x14004cd6d  jnz     loc_14004CFF0
0x14004cd73  mov     eax, [rsp+208h+var_198]
0x14004cd77  jmp     short loc_14004CD7D
0x14004cd79  mov     eax, [r13+40h]
0x14004cd7d  mov     [rsp+208h+var_198], eax
0x14004cd81  mov     ecx, 0C0h; dwBytes
0x14004cd86  call    pMemAlloc
0x14004cd8b  mov     rsi, rax
0x14004cd8e  test    rax, rax
0x14004cd91  jz      loc_14004D09C
0x14004cd97  xor     edx, edx; Val
0x14004cd99  mov     r8d, 0C0h; Size
0x14004cd9f  mov     rcx, rax; void *
0x14004cda2  call    memset_0
0x14004cda7  mov     rcx, [rsp+208h+var_170]
0x14004cdaf  mov     eax, [rcx]
0x14004cdb1  mov     rcx, [rsp+208h+var_1B0]
0x14004cdb6  mov     [rcx+rax*8], rsi
0x14004cdba  mov     dword ptr [rsi+10h], 454E494Ch
0x14004cdc1  mov     [rsi+14h], r12d
0x14004cdc5  mov     ecx, [rsp+208h+var_1A8]
0x14004cdc9  add     ecx, r12d
0x14004cdcc  mov     [rsi+1Ch], ecx
0x14004cdcf  mov     eax, [rsp+208h+var_198]
0x14004cdd3  mov     [rsi+18h], eax
0x14004cdd6  mov     [rsi+20h], ebx
0x14004cdd9  mov     rax, [rsp+208h+var_180]
0x14004cde1  mov     [rsi+28h], rax
0x14004cde5  mov     rax, [rsp+208h+var_1A0]
0x14004cdea  mov     [rsi+38h], rax
  ... truncated ...
```
