# FwCopyRule

- ea: `0x180006230`
- end: `0x180006f45`
- name: `FwCopyRule`
- size: `3349`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180031964`

## callees

- `0x1800042c4`
- `0x180006230`
- `0x180006f50`
- `0x180008a40`
- `0x18001ffd4`

## import_xrefs

- `fwbase!FwAlloc` at `0x18000624b`
- `fwbase!FwAlloc` at `0x18000624b`
- `fwbase!FwArrayCopy` at `0x1800062dd`
- `fwbase!FwArrayCopy` at `0x180006315`
- `fwbase!FwArrayCopy` at `0x18000637b`
- `fwbase!FwArrayCopy` at `0x1800063e7`
- `fwbase!FwArrayCopy` at `0x180006425`
- `fwbase!FwArrayCopy` at `0x180006466`
- `fwbase!FwArrayCopy` at `0x18000649c`
- `fwbase!FwArrayCopy` at `0x1800064d2`
- `fwbase!FwArrayCopy` at `0x180006508`
- `fwbase!FwArrayCopy` at `0x180006558`
- `fwbase!FwArrayCopy` at `0x18000658b`
- `fwbase!FwArrayCopy` at `0x1800065be`
- `fwbase!FwArrayCopy` at `0x1800065f1`
- `fwbase!FwArrayCopy` at `0x1800067c4`
- `fwbase!FwArrayCopy` at `0x18000682f`
- `fwbase!FwArrayCopy` at `0x1800068a8`
- `fwbase!FwArrayCopy` at `0x180006930`
- `fwbase!FwArrayCopy` at `0x1800062dd`
- `fwbase!FwArrayCopy` at `0x180006315`
- `fwbase!FwArrayCopy` at `0x18000637b`
- `fwbase!FwArrayCopy` at `0x1800063e7`
- `fwbase!FwArrayCopy` at `0x180006425`
- `fwbase!FwArrayCopy` at `0x180006466`
- `fwbase!FwArrayCopy` at `0x18000649c`
- `fwbase!FwArrayCopy` at `0x1800064d2`
- `fwbase!FwArrayCopy` at `0x180006508`
- `fwbase!FwArrayCopy` at `0x180006558`
- `fwbase!FwArrayCopy` at `0x18000658b`
- `fwbase!FwArrayCopy` at `0x1800065be`
- `fwbase!FwArrayCopy` at `0x1800065f1`
- `fwbase!FwArrayCopy` at `0x1800067c4`
- `fwbase!FwArrayCopy` at `0x18000682f`
- `fwbase!FwArrayCopy` at `0x1800068a8`
- `fwbase!FwArrayCopy` at `0x180006930`
- `fwbase!FwStringCopy` at `0x180006612`
- `fwbase!FwStringCopy` at `0x180006633`
- `fwbase!FwStringCopy` at `0x18000664e`
- `fwbase!FwStringCopy` at `0x180006669`
- `fwbase!FwStringCopy` at `0x18000668a`
- `fwbase!FwStringCopy` at `0x1800066ab`
- `fwbase!FwStringCopy` at `0x1800066cc`
- `fwbase!FwStringCopy` at `0x1800066ed`
- `fwbase!FwStringCopy` at `0x18000673b`
- `fwbase!FwStringCopy` at `0x18000675c`
- `fwbase!FwStringCopy` at `0x18000677d`
- `fwbase!FwStringCopy` at `0x1800067e5`
- `fwbase!FwStringCopy` at `0x180006850`
- `fwbase!FwStringCopy` at `0x1800068c9`
- `fwbase!FwStringCopy` at `0x1800068e4`
- `fwbase!FwStringCopy` at `0x180006612`
- `fwbase!FwStringCopy` at `0x180006633`
- `fwbase!FwStringCopy` at `0x18000664e`
- `fwbase!FwStringCopy` at `0x180006669`
- `fwbase!FwStringCopy` at `0x18000668a`
- `fwbase!FwStringCopy` at `0x1800066ab`
- `fwbase!FwStringCopy` at `0x1800066cc`
- `fwbase!FwStringCopy` at `0x1800066ed`
- `fwbase!FwStringCopy` at `0x18000673b`
- `fwbase!FwStringCopy` at `0x18000675c`
- `fwbase!FwStringCopy` at `0x18000677d`
- `fwbase!FwStringCopy` at `0x1800067e5`
- `fwbase!FwStringCopy` at `0x180006850`
- `fwbase!FwStringCopy` at `0x1800068c9`
- `fwbase!FwStringCopy` at `0x1800068e4`

## pseudocode

```c
__int64 __fastcall FwCopyRule(__int64 a1, void **a2)
{
  void *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int16 v8; // ax
  int v9; // eax
  LPCOLESTR v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  int v14; // eax
  _DWORD *v15; // r14
  int v16; // eax
  _DWORD *v17; // r14
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 result; // rax
  int v37; // eax
  LPCOLESTR v38; // rcx
  __int64 v39; // rdx
  LPCOLESTR v40; // rcx
  __int64 v41; // rdx
  LPCOLESTR v42; // rcx
  __int64 v43; // rdx

  *a2 = 0;
  v4 = (void *)FwAlloc(504);
  *a2 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v11 = 36;
LABEL_150:
    v12 = v6;
LABEL_151:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v12);
    goto LABEL_48;
  }
  memset_0(v4, 0, 0x1F8u);
  *((_WORD *)*a2 + 4) = *(_WORD *)(a1 + 8);
  *((_WORD *)*a2 + 146) = *(_WORD *)(a1 + 292);
  *((_DWORD *)*a2 + 72) = *(_DWORD *)(a1 + 288);
  *((_DWORD *)*a2 + 10) = *(_DWORD *)(a1 + 40);
  *((_DWORD *)*a2 + 11) = *(_DWORD *)(a1 + 44);
  *((_WORD *)*a2 + 24) = *(_WORD *)(a1 + 48);
  v5 = FwArrayCopy(
         16,
         FwShallowCopySidAndAttributes,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1 + 248,
         (char *)*a2 + 248);
  v6 = v5;
  if ( v5 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v11 = 37;
    v12 = (unsigned int)v5;
    goto LABEL_151;
  }
  v7 = FwArrayCopy(
         4,
         FwCopyPlatform,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1 + 320,
         (char *)*a2 + 320);
  v6 = v7;
  if ( v7 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v11 = 38;
    v12 = (unsigned int)v7;
    goto LABEL_151;
  }
  *((_DWORD *)*a2 + 66) = *(_DWORD *)(a1 + 264);
  v8 = *(_WORD *)(a1 + 48);
  switch ( v8 )
  {
    case 6:
    case 17:
      *((_WORD *)*a2 + 28) = *(_WORD *)(a1 + 56);
      v13 = FwArrayCopy(
              4,
              FwCopyPlatform,
              wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
              a1 + 64,
              (char *)*a2 + 64);
      v6 = v13;
      if ( v13 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_48;
        v11 = 39;
        v12 = (unsigned int)v13;
        goto LABEL_151;
      }
      *((_WORD *)*a2 + 40) = *(_WORD *)(a1 + 80);
      v14 = FwArrayCopy(
              4,
              FwCopyPlatform,
              wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
              a1 + 88,
              (char *)*a2 + 88);
      v6 = v14;
      if ( v14 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_48;
        v11 = 40;
        v12 = (unsigned int)v14;
        goto LABEL_151;
      }
      break;
    case 1:
      v37 = FwArrayCopy(
              4,
              FwCopyPlatform,
              wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
              a1 + 56,
              (char *)*a2 + 56);
      v6 = v37;
      if ( v37 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_48;
        v11 = 41;
        v12 = (unsigned int)v37;
        goto LABEL_151;
      }
      break;
    case 58:
      v9 = FwArrayCopy(
             4,
             FwCopyPlatform,
             wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
             a1 + 56,
             (char *)*a2 + 56);
      v6 = v9;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_48;
        v11 = 42;
        v12 = (unsigned int)v9;
        goto LABEL_151;
      }
      break;
  }
  v15 = *a2;
  v15[26] = *(_DWORD *)(a1 + 104);
  v15[27] = *(_DWORD *)(a1 + 108);
  v16 = FwArrayCopy(
          8,
          FwCopyIPv4SubNet,
          wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
          a1 + 112,
          v15 + 28);
  v6 = v16;
  if ( v16 < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_91;
    v39 = 19;
LABEL_90:
    WPP_SF_d(*((_QWORD *)v38 + 2), v39, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v16);
    goto LABEL_91;
  }
  v16 = FwArrayCopy(
          8,
          FwCopyIPv4SubNet,
          wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
          a1 + 128,
          v15 + 32);
  v6 = v16;
  if ( v16 < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_91;
    v39 = 20;
    goto LABEL_90;
  }
  v16 = FwArrayCopy(
          20,
          FwCopyIPv6SubNet,
          wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
          a1 + 144,
          v15 + 36);
  v6 = v16;
  if ( v16 < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_91;
    v39 = 21;
    goto LABEL_90;
  }
  v16 = FwArrayCopy(
          32,
          FwCopyIPv6Range,
          wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
          a1 + 160,
          v15 + 40);
  v6 = v16;
  if ( v16 >= 0 )
  {
    v17 = (char *)*a2 + 176;
    *v17 = *(_DWORD *)(a1 + 176);
    v17[1] = *(_DWORD *)(a1 + 180);
    v18 = FwArrayCopy(
            8,
            FwCopyIPv4SubNet,
            wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
            a1 + 184,
            v17 + 2);
    v6 = v18;
    if ( v18 < 0 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_104;
      v41 = 19;
    }
    else
    {
      v18 = FwArrayCopy(
              8,
              FwCopyIPv4SubNet,
              wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
              a1 + 200,
              v17 + 6);
      v6 = v18;
      if ( v18 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_104;
        v41 = 20;
      }
      else
      {
        v18 = FwArrayCopy(
                20,
                FwCopyIPv6SubNet,
                wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                a1 + 216,
                v17 + 10);
        v6 = v18;
        if ( v18 >= 0 )
        {
          v18 = FwArrayCopy(
                  32,
                  FwCopyIPv6Range,
                  wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                  a1 + 232,
                  v17 + 14);
          v6 = v18;
          if ( v18 >= 0 )
          {
            v19 = FwStringCopy(*(_QWORD *)(a1 + 272), (char *)*a2 + 272);
            v6 = v19;
            if ( v19 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 45;
              v12 = (unsigned int)v19;
              goto LABEL_151;
            }
            v20 = FwStringCopy(*(_QWORD *)(a1 + 280), (char *)*a2 + 280);
            v6 = v20;
            if ( v20 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 46;
              v12 = (unsigned int)v20;
              goto LABEL_151;
            }
            v21 = FwStringCopy(*(_QWORD *)(a1 + 24), (char *)*a2 + 24);
            v6 = v21;
            if ( v21 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 47;
              v12 = (unsigned int)v21;
              goto LABEL_151;
            }
            v22 = FwStringCopy(*(_QWORD *)(a1 + 32), (char *)*a2 + 32);
            v6 = v22;
            if ( v22 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 48;
              v12 = (unsigned int)v22;
              goto LABEL_151;
            }
            v23 = FwStringCopy(*(_QWORD *)(a1 + 312), (char *)*a2 + 312);
            v6 = v23;
            if ( v23 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 49;
              v12 = (unsigned int)v23;
              goto LABEL_151;
            }
            v24 = FwStringCopy(*(_QWORD *)(a1 + 296), (char *)*a2 + 296);
            v6 = v24;
            if ( v24 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 50;
              v12 = (unsigned int)v24;
              goto LABEL_151;
            }
            v25 = FwStringCopy(*(_QWORD *)(a1 + 304), (char *)*a2 + 304);
            v6 = v25;
            if ( v25 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 51;
              v12 = (unsigned int)v25;
              goto LABEL_151;
            }
            v26 = FwStringCopy(*(_QWORD *)(a1 + 344), (char *)*a2 + 344);
            v6 = v26;
            if ( v26 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 52;
              v12 = (unsigned int)v26;
              goto LABEL_151;
            }
            *((_DWORD *)*a2 + 84) = *(_DWORD *)(a1 + 336);
            *((_DWORD *)*a2 + 88) = *(_DWORD *)(a1 + 352);
            *((_DWORD *)*a2 + 85) = *(_DWORD *)(a1 + 340);
            v27 = FwStringCopy(*(_QWORD *)(a1 + 368), (char *)*a2 + 368);
            v6 = v27;
            if ( v27 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 53;
              v12 = (unsigned int)v27;
              goto LABEL_151;
            }
            v28 = FwStringCopy(*(_QWORD *)(a1 + 376), (char *)*a2 + 376);
            v6 = v28;
            if ( v28 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 54;
              v12 = (unsigned int)v28;
              goto LABEL_151;
            }
            v29 = FwStringCopy(*(_QWORD *)(a1 + 384), (char *)*a2 + 384);
            v6 = v29;
            if ( v29 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 55;
              v12 = (unsigned int)v29;
              goto LABEL_151;
            }
            *((_DWORD *)*a2 + 98) = *(_DWORD *)(a1 + 392);
            v30 = FwArrayCopy(
                    8,
                    FwDeepCopyLPWSTR,
                    wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                    a1 + 400,
                    (char *)*a2 + 400);
            v6 = v30;
            if ( v30 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 56;
              v12 = (unsigned int)v30;
              goto LABEL_151;
            }
            v31 = FwStringCopy(*(_QWORD *)(a1 + 416), (char *)*a2 + 416);
            v6 = v31;
            if ( v31 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 57;
              v12 = (unsigned int)v31;
              goto LABEL_151;
            }
            *((_WORD *)*a2 + 212) = *(_WORD *)(a1 + 424);
            v32 = FwArrayCopy(
                    8,
                    FwDeepCopyLPWSTR,
                    wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                    a1 + 432,
                    (char *)*a2 + 432);
            v6 = v32;
            if ( v32 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 58;
              v12 = (unsigned int)v32;
              goto LABEL_151;
            }
            v33 = FwStringCopy(*(_QWORD *)(a1 + 448), (char *)*a2 + 448);
            v6 = v33;
            if ( v33 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 59;
              v12 = (unsigned int)v33;
              goto LABEL_151;
            }
            *((_DWORD *)*a2 + 114) = *(_DWORD *)(a1 + 456);
            *(_OWORD *)((char *)*a2 + 460) = *(_OWORD *)(a1 + 460);
            v34 = FwArrayCopy(
                    16,
                    FwShallowCopySidAndAttributes,
                    wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                    a1 + 480,
                    (char *)*a2 + 480);
            v6 = v34;
            if ( v34 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 60;
              v12 = (unsigned int)v34;
              goto LABEL_151;
            }
            v35 = FwStringCopy(*(_QWORD *)(a1 + 496), (char *)*a2 + 496);
            v6 = v35;
            if ( v35 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
                goto LABEL_48;
              v11 = 61;
              v12 = (unsigned int)v35;
              goto LABEL_151;
            }
            v6 = FwStringCopy(*(_QWORD *)(a1 + 16), (char *)*a2 + 16);
            if ( (v6 & 0x80000000) == 0 )
            {
              *(_QWORD *)*a2 = 0;
              return v6;
            }
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_48;
            v11 = 62;
            goto LABEL_150;
          }
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v41 = 22;
            goto LABEL_103;
          }
LABEL_104:
          FwEmptyWFAddresses(v17);
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v43 = 44;
            goto LABEL_107;
          }
          goto LABEL_41;
        }
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_104;
        v41 = 21;
      }
    }
LABEL_103:
    WPP_SF_d(*((_QWORD *)v40 + 2), v41, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v18);
    goto LABEL_104;
  }
  v38 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v39 = 22;
    goto LABEL_90;
  }
LABEL_91:
  FwEmptyWFAddresses(v15 + 26);
  v42 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v43 = 43;
LABEL_107:
    WPP_SF_d(*((_QWORD *)v42 + 2), v43, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v6);
  }
LABEL_41:
  if ( (v6 & 0x80000000) == 0 )
    return v6;
LABEL_48:
  FwFreeWFRule(*a2);
  result = v6;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180006230  push    rbx
0x180006232  push    rbp
0x180006233  push    rsi
0x180006234  push    rdi
0x180006235  push    r14
0x180006237  sub     rsp, 30h
0x18000623b  mov     rdi, rcx
0x18000623e  xor     ebp, ebp
0x180006240  mov     ecx, 1F8h
0x180006245  mov     [rdx], rbp
0x180006248  mov     rsi, rdx
0x18000624b  call    cs:__imp_FwAlloc
0x180006251  mov     [rsi], rax
0x180006254  test    rax, rax
0x180006257  jz      loc_180006AF7
0x18000625d  xor     edx, edx; Val
0x18000625f  mov     r8d, 1F8h; Size
0x180006265  mov     rcx, rax; void *
0x180006268  call    memset_0
0x18000626d  movzx   eax, word ptr [rdi+8]
0x180006271  lea     r9, [rdi+0F8h]
0x180006278  mov     rcx, [rsi]
0x18000627b  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180006282  lea     rdx, ?FwShallowCopySidAndAttributes@@YAJPEBXPEAX@Z; FwShallowCopySidAndAttributes(void const *,void *)
0x180006289  mov     [rcx+8], ax
0x18000628d  movzx   eax, word ptr [rdi+124h]
0x180006294  mov     rcx, [rsi]
0x180006297  mov     [rcx+124h], ax
0x18000629e  mov     eax, [rdi+120h]
0x1800062a4  mov     rcx, [rsi]
0x1800062a7  mov     [rcx+120h], eax
0x1800062ad  mov     eax, [rdi+28h]
0x1800062b0  mov     rcx, [rsi]
0x1800062b3  mov     [rcx+28h], eax
0x1800062b6  mov     eax, [rdi+2Ch]
0x1800062b9  mov     rcx, [rsi]
0x1800062bc  mov     [rcx+2Ch], eax
0x1800062bf  mov     rcx, [rsi]
0x1800062c2  movzx   eax, word ptr [rdi+30h]
0x1800062c6  mov     [rcx+30h], ax
0x1800062ca  mov     ecx, 10h
0x1800062cf  mov     rax, [rsi]
0x1800062d2  add     rax, 0F8h
0x1800062d8  mov     [rsp+58h+var_38], rax
0x1800062dd  call    cs:__imp_FwArrayCopy
0x1800062e3  mov     ebx, eax
0x1800062e5  test    eax, eax
0x1800062e7  js      loc_180006A11
0x1800062ed  mov     rax, [rsi]
0x1800062f0  lea     r9, [rdi+140h]
0x1800062f7  add     rax, 140h
0x1800062fd  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180006304  lea     rdx, FwCopyPlatform
0x18000630b  mov     [rsp+58h+var_38], rax
0x180006310  mov     ecx, 4
0x180006315  call    cs:__imp_FwArrayCopy
0x18000631b  mov     ebx, eax
0x18000631d  test    eax, eax
0x18000631f  js      loc_180006966
0x180006325  mov     eax, [rdi+108h]
0x18000632b  mov     rcx, [rsi]
0x18000632e  mov     [rcx+108h], eax
0x180006334  movzx   eax, word ptr [rdi+30h]
0x180006338  cmp     ax, 6
0x18000633c  jz      short loc_1800063B9
0x18000633e  cmp     ax, 11h
0x180006342  jz      short loc_1800063B9
0x180006344  cmp     ax, 1
0x180006348  jz      loc_18000690D
0x18000634e  cmp     ax, 3Ah ; ':'
0x180006352  jnz     loc_180006435
0x180006358  mov     rax, [rsi]
0x18000635b  lea     r9, [rdi+38h]
0x18000635f  add     rax, 38h ; '8'
0x180006363  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18000636a  lea     rdx, FwCopyPlatform
0x180006371  mov     [rsp+58h+var_38], rax
0x180006376  mov     ecx, 4
0x18000637b  call    cs:__imp_FwArrayCopy
0x180006381  mov     ebx, eax
0x180006383  test    eax, eax
0x180006385  jns     loc_180006435
0x18000638b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006392  lea     rdi, WPP_GLOBAL_Control
0x180006399  cmp     rcx, rdi
0x18000639c  jz      loc_18000697D
0x1800063a2  test    byte ptr [rcx+1Ch], 1
0x1800063a6  jz      loc_18000697D
0x1800063ac  mov     edx, 2Ah ; '*'
0x1800063b1  mov     r9d, eax
0x1800063b4  jmp     loc_180006F30
0x1800063b9  mov     rcx, [rsi]
0x1800063bc  lea     r9, [rdi+40h]
0x1800063c0  movzx   eax, word ptr [rdi+38h]
0x1800063c4  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800063cb  lea     rdx, FwCopyPlatform
0x1800063d2  mov     [rcx+38h], ax
0x1800063d6  mov     ecx, 4
0x1800063db  mov     rax, [rsi]
0x1800063de  add     rax, 40h ; '@'
0x1800063e2  mov     [rsp+58h+var_38], rax
0x1800063e7  call    cs:__imp_FwArrayCopy
0x1800063ed  mov     ebx, eax
0x1800063ef  test    eax, eax
0x1800063f1  js      loc_180006995
0x1800063f7  mov     rcx, [rsi]
0x1800063fa  lea     r9, [rdi+58h]
0x1800063fe  movzx   eax, word ptr [rdi+50h]
0x180006402  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180006409  lea     rdx, FwCopyPlatform
0x180006410  mov     [rcx+50h], ax
0x180006414  mov     ecx, 4
0x180006419  mov     rax, [rsi]
0x18000641c  add     rax, 58h ; 'X'
0x180006420  mov     [rsp+58h+var_38], rax
0x180006425  call    cs:__imp_FwArrayCopy
0x18000642b  mov     ebx, eax
0x18000642d  test    eax, eax
0x18000642f  js      loc_180006B3E
0x180006435  mov     eax, [rdi+68h]
0x180006438  lea     r9, [rdi+70h]
0x18000643c  mov     r14, [rsi]
0x18000643f  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180006446  lea     rdx, FwCopyIPv4SubNet
0x18000644d  mov     ecx, 8
0x180006452  mov     [r14+68h], eax
0x180006456  mov     eax, [rdi+6Ch]
0x180006459  mov     [r14+6Ch], eax
0x18000645d  lea     rax, [r14+70h]
0x180006461  mov     [rsp+58h+var_38], rax
0x180006466  call    cs:__imp_FwArrayCopy
0x18000646c  mov     ebx, eax
0x18000646e  test    eax, eax
0x180006470  js      loc_1800069BB
0x180006476  lea     rax, [r14+80h]
0x18000647d  mov     ecx, 8
0x180006482  lea     r9, [rdi+80h]
0x180006489  mov     [rsp+58h+var_38], rax
0x18000648e  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180006495  lea     rdx, FwCopyIPv4SubNet
0x18000649c  call    cs:__imp_FwArrayCopy
0x1800064a2  mov     ebx, eax
0x1800064a4  test    eax, eax
0x1800064a6  js      loc_180006B6C
0x1800064ac  lea     rax, [r14+90h]
0x1800064b3  mov     ecx, 14h
0x1800064b8  lea     r9, [rdi+90h]
0x1800064bf  mov     [rsp+58h+var_38], rax
0x1800064c4  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800064cb  lea     rdx, FwCopyIPv6SubNet
0x1800064d2  call    cs:__imp_FwArrayCopy
0x1800064d8  mov     ebx, eax
0x1800064da  test    eax, eax
0x1800064dc  js      loc_180006B8C
0x1800064e2  lea     rax, [r14+0A0h]
0x1800064e9  mov     ecx, 20h ; ' '
0x1800064ee  lea     r9, [rdi+0A0h]
0x1800064f5  mov     [rsp+58h+var_38], rax
0x1800064fa  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180006501  lea     rdx, FwCopyIPv6Range
0x180006508  call    cs:__imp_FwArrayCopy
0x18000650e  mov     ebx, eax
0x180006510  test    eax, eax
0x180006512  js      loc_180006BAC
0x180006518  mov     eax, [rdi+0B0h]
0x18000651e  lea     r9, [rdi+0B8h]
0x180006525  mov     r14, [rsi]
0x180006528  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18000652f  add     r14, 0B0h
0x180006536  lea     rdx, FwCopyIPv4SubNet
0x18000653d  mov     ecx, 8
0x180006542  mov     [r14], eax
0x180006545  mov     eax, [rdi+0B4h]
0x18000654b  mov     [r14+4], eax
0x18000654f  lea     rax, [r14+8]
0x180006553  mov     [rsp+58h+var_38], rax
0x180006558  call    cs:__imp_FwArrayCopy
0x18000655e  mov     ebx, eax
0x180006560  test    eax, eax
0x180006562  js      loc_1800069E6
0x180006568  lea     rax, [r14+18h]
0x18000656c  mov     ecx, 8
0x180006571  lea     r9, [rdi+0C8h]
0x180006578  mov     [rsp+58h+var_38], rax
0x18000657d  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180006584  lea     rdx, FwCopyIPv4SubNet
0x18000658b  call    cs:__imp_FwArrayCopy
0x180006591  mov     ebx, eax
0x180006593  test    eax, eax
0x180006595  js      loc_180006C0A
0x18000659b  lea     rax, [r14+28h]
0x18000659f  mov     ecx, 14h
0x1800065a4  lea     r9, [rdi+0D8h]
0x1800065ab  mov     [rsp+58h+var_38], rax
0x1800065b0  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800065b7  lea     rdx, FwCopyIPv6SubNet
0x1800065be  call    cs:__imp_FwArrayCopy
0x1800065c4  mov     ebx, eax
0x1800065c6  test    eax, eax
0x1800065c8  js      loc_180006C2A
0x1800065ce  lea     rax, [r14+38h]
0x1800065d2  mov     ecx, 20h ; ' '
0x1800065d7  lea     r9, [rdi+0E8h]
0x1800065de  mov     [rsp+58h+var_38], rax
0x1800065e3  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800065ea  lea     rdx, FwCopyIPv6Range
0x1800065f1  call    cs:__imp_FwArrayCopy
0x1800065f7  mov     ebx, eax
0x1800065f9  test    eax, eax
0x1800065fb  js      loc_180006C4A
0x180006601  mov     rdx, [rsi]
0x180006604  mov     rcx, [rdi+110h]
0x18000660b  add     rdx, 110h
0x180006612  call    cs:__imp_FwStringCopy
0x180006618  mov     ebx, eax
0x18000661a  test    eax, eax
0x18000661c  js      loc_180006CBA
0x180006622  mov     rdx, [rsi]
0x180006625  mov     rcx, [rdi+118h]
0x18000662c  add     rdx, 118h
0x180006633  call    cs:__imp_FwStringCopy
0x180006639  mov     ebx, eax
0x18000663b  test    eax, eax
0x18000663d  js      loc_180006CE8
0x180006643  mov     rdx, [rsi]
0x180006646  mov     rcx, [rdi+18h]
0x18000664a  add     rdx, 18h
0x18000664e  call    cs:__imp_FwStringCopy
0x180006654  mov     ebx, eax
0x180006656  test    eax, eax
0x180006658  js      loc_180006D16
0x18000665e  mov     rdx, [rsi]
0x180006661  mov     rcx, [rdi+20h]
0x180006665  add     rdx, 20h ; ' '
0x180006669  call    cs:__imp_FwStringCopy
0x18000666f  mov     ebx, eax
0x180006671  test    eax, eax
0x180006673  js      loc_180006D44
0x180006679  mov     rdx, [rsi]
0x18000667c  mov     rcx, [rdi+138h]
0x180006683  add     rdx, 138h
0x18000668a  call    cs:__imp_FwStringCopy
0x180006690  mov     ebx, eax
0x180006692  test    eax, eax
0x180006694  js      loc_180006D72
0x18000669a  mov     rdx, [rsi]
0x18000669d  mov     rcx, [rdi+128h]
0x1800066a4  add     rdx, 128h
0x1800066ab  call    cs:__imp_FwStringCopy
0x1800066b1  mov     ebx, eax
0x1800066b3  test    eax, eax
0x1800066b5  js      loc_180006DA0
0x1800066bb  mov     rdx, [rsi]
0x1800066be  mov     rcx, [rdi+130h]
0x1800066c5  add     rdx, 130h
0x1800066cc  call    cs:__imp_FwStringCopy
0x1800066d2  mov     ebx, eax
0x1800066d4  test    eax, eax
0x1800066d6  js      loc_180006DCE
0x1800066dc  mov     rdx, [rsi]
0x1800066df  mov     rcx, [rdi+158h]
0x1800066e6  add     rdx, 158h
0x1800066ed  call    cs:__imp_FwStringCopy
0x1800066f3  mov     ebx, eax
0x1800066f5  test    eax, eax
0x1800066f7  js      loc_180006DFC
0x1800066fd  mov     rcx, [rsi]
0x180006700  mov     eax, [rdi+150h]
0x180006706  mov     [rcx+150h], eax
0x18000670c  mov     rcx, [rsi]
0x18000670f  mov     eax, [rdi+160h]
0x180006715  mov     [rcx+160h], eax
0x18000671b  mov     rcx, [rsi]
0x18000671e  mov     eax, [rdi+154h]
0x180006724  mov     [rcx+154h], eax
0x18000672a  mov     rdx, [rsi]
0x18000672d  mov     rcx, [rdi+170h]
0x180006734  add     rdx, 170h
0x18000673b  call    cs:__imp_FwStringCopy
0x180006741  mov     ebx, eax
0x180006743  test    eax, eax
0x180006745  js      loc_180006AC9
0x18000674b  mov     rdx, [rsi]
0x18000674e  mov     rcx, [rdi+178h]
0x180006755  add     rdx, 178h
0x18000675c  call    cs:__imp_FwStringCopy
0x180006762  mov     ebx, eax
0x180006764  test    eax, eax
0x180006766  js      loc_180006E2A
0x18000676c  mov     rdx, [rsi]
0x18000676f  mov     rcx, [rdi+180h]
0x180006776  add     rdx, 180h
0x18000677d  call    cs:__imp_FwStringCopy
0x180006783  mov     ebx, eax
0x180006785  test    eax, eax
0x180006787  js      loc_180006E58
0x18000678d  mov     rcx, [rsi]
0x180006790  lea     r9, [rdi+190h]
0x180006797  mov     eax, [rdi+188h]
0x18000679d  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
  ... truncated ...
```
