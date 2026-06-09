# CreateLegacyVirtualDevices

- ea: `0x1400499f4`
- end: `0x14004a357`
- name: `CreateLegacyVirtualDevices`
- size: `2403`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004a434`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140004e68`
- `0x140024850`
- `0x140025980`
- `0x1400499f4`
- `0x14004a690`
- `0x14004e750`
- `0x14004e8ac`
- `0x140065d14`
- `0x140065dbc`
- `0x140065df8`
- `0x140067168`
- `0x14007e2f8`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140049b1a`
- `KERNEL32!GetLastError` at `0x140049c54`
- `KERNEL32!GetLastError` at `0x140049c75`
- `KERNEL32!GetLastError` at `0x140049fde`
- `KERNEL32!GetLastError` at `0x14004a00b`
- `KERNEL32!GetLastError` at `0x14004a13c`
- `KERNEL32!GetLastError` at `0x14004a169`
- `KERNEL32!GetLastError` at `0x14004a19b`
- `KERNEL32!GetLastError` at `0x14004a1c8`
- `KERNEL32!GetLastError` at `0x14004a229`
- `KERNEL32!GetLastError` at `0x140049b1a`
- `KERNEL32!GetLastError` at `0x140049c54`
- `KERNEL32!GetLastError` at `0x140049c75`
- `KERNEL32!GetLastError` at `0x140049fde`
- `KERNEL32!GetLastError` at `0x14004a00b`
- `KERNEL32!GetLastError` at `0x14004a13c`
- `KERNEL32!GetLastError` at `0x14004a169`
- `KERNEL32!GetLastError` at `0x14004a19b`
- `KERNEL32!GetLastError` at `0x14004a1c8`
- `KERNEL32!GetLastError` at `0x14004a229`
- `KERNEL32!SetLastError` at `0x14004a0ca`
- `KERNEL32!SetLastError` at `0x14004a0ca`

## pseudocode

```c
__int64 __fastcall CreateLegacyVirtualDevices(__int64 a1, unsigned __int16 **a2, __int64 a3, _DWORD *a4)
{
  unsigned int v6; // ebx
  DWORD v7; // r14d
  char LastError; // al
  _QWORD *v9; // r13
  CMapDeviceId *v10; // rcx
  DWORD_PTR i; // rsi
  _QWORD *v12; // rax
  DWORD v13; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // r12d
  __int64 v17; // rax
  unsigned int v18; // esi
  unsigned __int16 *v19; // rax
  int v20; // eax
  DWORD v21; // esi
  __int64 v22; // r13
  unsigned int v23; // r8d
  __int64 v24; // r11
  __int64 v25; // rdx
  unsigned __int16 *v26; // rax
  __int64 v27; // r10
  int v28; // ecx
  int v29; // r9d
  DWORD v30; // eax
  int v31; // eax
  void *v32; // rax
  __int64 v33; // rsi
  __int64 v34; // rax
  unsigned __int16 **v35; // rdx
  int v36; // eax
  __int64 v37; // rax
  DWORD v38; // eax
  int v39; // r8d
  int v40; // edx
  int v41; // eax
  __int64 *v42; // rax
  int v43; // eax
  bool v44; // zf
  DWORD v46; // eax
  unsigned int j; // esi
  __int64 *v48; // rax
  __int64 v49; // rcx
  _QWORD *v50; // rax
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // [rsp+20h] [rbp-1E8h]
  unsigned int v54; // [rsp+50h] [rbp-1B8h] BYREF
  _QWORD *v55; // [rsp+58h] [rbp-1B0h]
  unsigned int v56; // [rsp+60h] [rbp-1A8h] BYREF
  __int64 v57; // [rsp+68h] [rbp-1A0h]
  int v58; // [rsp+70h] [rbp-198h] BYREF
  int v59; // [rsp+78h] [rbp-190h]
  unsigned __int16 **v60; // [rsp+80h] [rbp-188h]
  __int64 v61; // [rsp+88h] [rbp-180h]
  unsigned __int16 **v62; // [rsp+90h] [rbp-178h]
  _DWORD *v63; // [rsp+98h] [rbp-170h]
  __int64 v64; // [rsp+A0h] [rbp-168h]
  __int64 v65; // [rsp+A8h] [rbp-160h]
  unsigned __int16 **v66; // [rsp+B0h] [rbp-158h]
  _DWORD *v67; // [rsp+B8h] [rbp-150h]
  _WORD v68[128]; // [rsp+C0h] [rbp-148h] BYREF

  v63 = a4;
  v61 = a3;
  v62 = a2;
  v64 = a1;
  v66 = a2;
  v65 = a1;
  v60 = a2;
  v57 = a3;
  v67 = a4;
  v6 = 0;
  v54 = 0;
  memset_0(v68, 0, sizeof(v68));
  v56 = 0;
  v55 = 0;
  v7 = 0;
  v59 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  *a4 = 0;
  if ( !(*(unsigned int (__fastcall **)(unsigned int *, _WORD *, unsigned int *, HANDLE, __int64))(a3 + 2224))(
          &v54,
          v68,
          &v56,
          g_TapiCompletionPort,
          2147483650LL) )
  {
    v7 = 1;
    v59 = 1;
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
  if ( !v54 )
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
  if ( v54 <= 0x100 )
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v54);
      v10 = WPP_GLOBAL_Control;
    }
    v54 = 256;
  }
  if ( v56 - 1 > 0xFFFE )
  {
    v7 = 1;
    if ( v10 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 2u )
      WPP_SF_Sd(*((_QWORD *)v10 + 2), 113, (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, a3 + 64, v56);
    goto LABEL_121;
  }
  for ( i = g_TapiLinesListHead; (DWORD_PTR *)i != &g_TapiLinesListHead; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 24) >= v56 && *(_DWORD *)(i + 24) <= v56 + v54 )
    {
      v7 = 1;
      FaxLog(1, 1, 2, 3221257569LL, a3 + 64);
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SlS(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, a3 + 64, v56, *(_QWORD *)(i + 40) + 64LL);
      }
      goto LABEL_121;
    }
  }
  v12 = (_QWORD *)pMemAlloc(8LL * v54);
  v9 = v12;
  v55 = v12;
  if ( !v12 )
  {
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = GetLastError();
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v54, v13);
    }
    goto LABEL_122;
  }
  memset_0(v12, 0, 8LL * v54);
  if ( v54 )
  {
    v16 = 0;
    while ( 1 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v68[v17] );
      v18 = 2 * v17 + 18;
      v19 = (unsigned __int16 *)pMemAlloc(v18);
      v57 = (__int64)v19;
      if ( !v19 )
      {
        v46 = GetLastError();
        v7 = v46;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v46);
        }
        goto LABEL_121;
      }
      LODWORD(v53) = v16;
      v20 = StringCbPrintfW(v19, v18, L"%s%d", v68, v53);
      v21 = v20;
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117,
            &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
            (unsigned int)v20);
        }
        v9 = v55;
        if ( (v21 & 0x1FFF0000) == 0x70000 )
          v7 = (unsigned __int16)v21;
        else
          v7 = v21;
        goto LABEL_122;
      }
      v22 = 0;
      if ( *(_DWORD *)(v64 + 40) )
      {
        v23 = 0;
        v24 = *(_QWORD *)(v64 + 32);
        while ( 1 )
        {
          v25 = v24 + 88LL * v23;
          if ( *(_DWORD *)(v25 + 60) == 1 )
          {
            v26 = *(unsigned __int16 **)(v25 + 72);
            v27 = v61 + 1624 - (_QWORD)v26;
            do
            {
              v28 = *(unsigned __int16 *)((char *)v26 + v27);
              v29 = *v26 - v28;
              if ( v29 )
                break;
              ++v26;
            }
            while ( v28 );
            if ( !v29 && *(_DWORD *)v25 == v16 + v56 )
              break;
          }
          if ( ++v23 >= *(_DWORD *)(v64 + 40) )
            goto LABEL_52;
        }
        v22 = v24 + 88LL * v23;
      }
LABEL_52:
      if ( v22 )
      {
        v31 = *(_DWORD *)(v22 + 64);
      }
      else
      {
        v58 = v16 + v56;
        v53 = v61 + 1624;
        v30 = RegAddNewFaxDevice((char *)g_pFaxConfig + 112, &v58, v57);
        v7 = v30;
        if ( v30 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v30);
          }
          goto LABEL_121;
        }
        v31 = v58;
      }
      v58 = v31;
      v32 = (void *)pMemAlloc(0xC0u);
      v33 = (__int64)v32;
      if ( !v32 )
      {
        v7 = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v38 = GetLastError();
          v40 = 119;
          goto LABEL_97;
        }
        goto LABEL_121;
      }
      memset_0(v32, 0, 0xC0u);
      v55[*v63] = v33;
      *(_DWORD *)(v33 + 16) = 1162758476;
      *(_DWORD *)(v33 + 20) = v16;
      *(_DWORD *)(v33 + 28) = v16 + v56;
      *(_DWORD *)(v33 + 24) = v58;
      *(_DWORD *)(v33 + 32) = 0;
      *(_QWORD *)(v33 + 40) = v61;
      *(_QWORD *)(v33 + 56) = v57;
      *(_DWORD *)(v33 + 104) = 0;
      *(_DWORD *)(v33 + 72) = 537919488;
      if ( v22 )
      {
        *(_QWORD *)(v33 + 88) = StringDup(*(unsigned __int16 **)(v22 + 24));
        *(_QWORD *)(v33 + 96) = StringDup(*(unsigned __int16 **)(v22 + 32));
        v34 = StringDup(*(unsigned __int16 **)(v22 + 48));
        *(_QWORD *)(v33 + 64) = v34;
        if ( *(_QWORD *)(v22 + 24) && !*(_QWORD *)(v33 + 88)
          || *(_QWORD *)(v22 + 32) && !*(_QWORD *)(v33 + 96)
          || *(_QWORD *)(v22 + 48) && !v34 )
        {
          v7 = GetLastError();
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v38 = GetLastError();
            v40 = 120;
            goto LABEL_97;
          }
          goto LABEL_121;
        }
        v35 = v60;
      }
      else
      {
        *(_QWORD *)(v33 + 88) = StringDup(*v62);
        v37 = StringDup(v60[1]);
        *(_QWORD *)(v33 + 96) = v37;
        *(_QWORD *)(v33 + 64) = 0;
        if ( *v62 && !*(_QWORD *)(v33 + 88) || (v35 = v60, v60[1]) && !v37 )
        {
          v7 = GetLastError();
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v38 = GetLastError();
            v40 = 121;
LABEL_97:
            WPP_SF_ldS(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, v39, v38, v16, v57);
          }
LABEL_121:
          v9 = v55;
LABEL_122:
          if ( v9 )
          {
            for ( j = 0; j < v54; ++j )
            {
              v48 = (__int64 *)v9[j];
              if ( v48 )
              {
                v49 = *v48;
                v50 = (_QWORD *)v48[1];
                *v50 = v49;
                *(_QWORD *)(v49 + 8) = v50;
                *(_QWORD *)v9[j] = 0;
                *(_QWORD *)(v9[j] + 8LL) = 0;
                v51 = v9[j];
                if ( (*(_BYTE *)(v51 + 76) & 3) != 0 || (v52 = 0, *(_DWORD *)(v51 + 24) == g_dwManualAnswerDeviceId) )
                  v52 = 1;
                if ( v52 == 1 )
                  --g_dwDeviceEnabledCount;
                FreeTapiLine((struct _LINE_INFO *)v51);
              }
            }
          }
          *v63 = 0;
          break;
        }
      }
      if ( v22 )
        v36 = *(_DWORD *)(v22 + 20);
      else
        v36 = 1;
      *(_DWORD *)(v33 + 108) = v36;
      *(_DWORD *)(v33 + 112) = 0;
      *(_DWORD *)(v33 + 164) = 0;
      *(_QWORD *)(v33 + 80) = 0;
      *(_QWORD *)(v33 + 176) = 0;
      *(_DWORD *)(v33 + 184) = v22 != 0 ? 4 : 1;
      if ( v22 )
        v41 = *(_DWORD *)(v22 + 16);
      else
        v41 = *((_DWORD *)v35 + 7) | 4;
      *(_DWORD *)(v33 + 76) = v41;
      v42 = (__int64 *)qword_1400A1748;
      *(_QWORD *)v33 = &g_TapiLinesListHead;
      *(_QWORD *)(v33 + 8) = v42;
      *v42 = v33;
      qword_1400A1748 = v33;
      ++*v63;
      if ( (*(_BYTE *)(v33 + 76) & 3) != 0 || (v43 = 0, *(_DWORD *)(v33 + 24) == g_dwManualAnswerDeviceId) )
        v43 = 1;
      if ( v43 == 1 )
        ++g_dwDeviceEnabledCount;
      if ( ++v16 >= v54 )
      {
        v9 = v55;
        break;
      }
    }
  }
  pMemFree(v9);
  v44 = v7 == 0;
  if ( v7 )
  {
    SetLastError(v7);
    v44 = v7 == 0;
  }
  LOBYTE(v6) = v44;
  return v6;
}

```

## disassembly

```asm
0x1400499f4  push    rbx
0x1400499f6  push    rsi
0x1400499f7  push    rdi
0x1400499f8  push    r12
0x1400499fa  push    r13
0x1400499fc  push    r14
0x1400499fe  push    r15
0x140049a00  sub     rsp, 1D0h
0x140049a07  mov     rax, cs:__security_cookie
0x140049a0e  xor     rax, rsp
0x140049a11  mov     [rsp+208h+var_48], rax
0x140049a19  mov     r12, r9
0x140049a1c  mov     [rsp+208h+var_170], r9
0x140049a24  mov     r13, r8
0x140049a27  mov     [rsp+208h+var_180], r8
0x140049a2f  mov     [rsp+208h+var_178], rdx
0x140049a37  mov     [rsp+208h+var_168], rcx
0x140049a3f  mov     [rsp+208h+var_158], rdx
0x140049a47  mov     [rsp+208h+var_160], rcx
0x140049a4f  mov     [rsp+208h+var_188], rdx
0x140049a57  mov     [rsp+208h+var_1A0], r8
0x140049a5c  mov     [rsp+208h+var_150], r9
0x140049a64  xor     ebx, ebx
0x140049a66  mov     [rsp+208h+var_1B8], ebx
0x140049a6a  xor     edx, edx; Val
0x140049a6c  mov     r8d, 100h; Size
0x140049a72  lea     rcx, [rsp+208h+var_148]; void *
0x140049a7a  call    memset_0
0x140049a7f  mov     [rsp+208h+var_1A8], ebx
0x140049a83  mov     [rsp+208h+var_1B0], rbx
0x140049a88  mov     r14d, ebx
0x140049a8b  mov     [rsp+208h+var_190], ebx
0x140049a8f  lea     r15, WPP_GLOBAL_Control
0x140049a96  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a9d  cmp     rcx, r15
0x140049aa0  jz      short loc_140049AC1
0x140049aa2  test    byte ptr [rcx+1Ch], 4
0x140049aa6  jz      short loc_140049AC1
0x140049aa8  cmp     byte ptr [rcx+19h], 5
0x140049aac  jb      short loc_140049AC1
0x140049aae  lea     edx, [rbx+6Eh]
0x140049ab1  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x140049ab8  mov     rcx, [rcx+10h]
0x140049abc  call    WPP_SF_
0x140049ac1  mov     [r12], ebx
0x140049ac5  mov     eax, 80000002h
0x140049aca  mov     [rsp+208h+var_1E8], rax
0x140049acf  mov     r9, cs:?g_TapiCompletionPort@@3PEAXEA; void * g_TapiCompletionPort
0x140049ad6  lea     r8, [rsp+208h+var_1A8]
0x140049adb  lea     rdx, [rsp+208h+var_148]
0x140049ae3  lea     rcx, [rsp+208h+var_1B8]
0x140049ae8  mov     rax, [r13+8B0h]
0x140049aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049af4  test    eax, eax
0x140049af6  jnz     short loc_140049B4A
0x140049af8  lea     edi, [rax+1]
0x140049afb  mov     r14d, edi
0x140049afe  mov     [rsp+208h+var_190], edi
0x140049b02  mov     rax, cs:WPP_GLOBAL_Control
0x140049b09  cmp     rax, r15
0x140049b0c  jz      short loc_140049B42
0x140049b0e  test    byte ptr [rax+1Ch], 4
0x140049b12  jz      short loc_140049B42
0x140049b14  cmp     byte ptr [rax+19h], 2
0x140049b18  jb      short loc_140049B42
0x140049b1a  call    cs:__imp_GetLastError
0x140049b20  lea     r9, [r13+40h]
0x140049b24  lea     edx, [rdi+6Eh]
0x140049b27  mov     dword ptr [rsp+208h+var_1E8], eax
0x140049b2b  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x140049b32  mov     rcx, cs:WPP_GLOBAL_Control
0x140049b39  mov     rcx, [rcx+10h]
0x140049b3d  call    WPP_SF_Sd
0x140049b42  mov     r13, rbx
0x140049b45  jmp     loc_14004A2DF
0x140049b4a  jmp     short loc_140049B9C
0x140049b4c  xor     ebx, ebx
0x140049b4e  lea     r15, WPP_GLOBAL_Control
0x140049b55  mov     [rsp+208h+var_1B0], rbx
0x140049b5a  mov     r14d, [rsp+208h+var_190]
0x140049b5f  mov     rax, [rsp+208h+var_160]
0x140049b67  mov     [rsp+208h+var_168], rax
0x140049b6f  mov     r13, [rsp+208h+var_1A0]
0x140049b74  mov     [rsp+208h+var_180], r13
0x140049b7c  mov     rax, [rsp+208h+var_158]
0x140049b84  mov     [rsp+208h+var_178], rax
0x140049b8c  mov     rax, [rsp+208h+var_150]
0x140049b94  mov     [rsp+208h+var_170], rax
0x140049b9c  mov     r9d, [rsp+208h+var_1B8]
0x140049ba1  test    r9d, r9d
0x140049ba4  jz      loc_14004A2A7
0x140049baa  cmp     r9d, 100h
0x140049bb1  jbe     short loc_140049BF1
0x140049bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140049bba  cmp     rcx, r15
0x140049bbd  jz      short loc_140049BE7
0x140049bbf  test    byte ptr [rcx+1Ch], 4
0x140049bc3  jz      short loc_140049BE7
0x140049bc5  cmp     byte ptr [rcx+19h], 5
0x140049bc9  jb      short loc_140049BE7
0x140049bcb  mov     edx, 70h ; 'p'
0x140049bd0  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x140049bd7  mov     rcx, [rcx+10h]
0x140049bdb  call    WPP_SF_d
0x140049be0  mov     rcx, cs:WPP_GLOBAL_Control
0x140049be7  mov     [rsp+208h+var_1B8], 100h
0x140049bef  jmp     short loc_140049BF8
0x140049bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x140049bf8  mov     r8d, [rsp+208h+var_1A8]
0x140049bfd  lea     eax, [r8-1]
0x140049c01  cmp     eax, 0FFFEh
0x140049c06  ja      loc_14004A270
0x140049c0c  mov     rsi, cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140049c13  lea     rdx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140049c1a  jmp     short loc_140049C31
0x140049c1c  cmp     [rsi+18h], r8d
0x140049c20  jb      short loc_140049C2E
0x140049c22  mov     ecx, [rsp+208h+var_1B8]
0x140049c26  add     ecx, r8d
0x140049c29  cmp     [rsi+18h], ecx
0x140049c2c  jbe     short loc_140049CA9
0x140049c2e  mov     rsi, [rsi]
0x140049c31  cmp     rsi, rdx
0x140049c34  jnz     short loc_140049C1C
0x140049c36  mov     ecx, [rsp+208h+var_1B8]
0x140049c3a  shl     rcx, 3; dwBytes
0x140049c3e  call    pMemAlloc
0x140049c43  mov     r13, rax
0x140049c46  mov     [rsp+208h+var_1B0], rax
0x140049c4b  test    rax, rax
0x140049c4e  jnz     loc_140049D24
0x140049c54  call    cs:__imp_GetLastError
0x140049c5a  mov     r14d, eax
0x140049c5d  mov     rax, cs:WPP_GLOBAL_Control
0x140049c64  cmp     rax, r15
0x140049c67  jz      short loc_140049C9F
0x140049c69  test    byte ptr [rax+1Ch], 4
0x140049c6d  jz      short loc_140049C9F
0x140049c6f  cmp     byte ptr [rax+19h], 2
0x140049c73  jb      short loc_140049C9F
0x140049c75  call    cs:__imp_GetLastError
0x140049c7b  lea     edx, [r13+73h]
0x140049c7f  mov     dword ptr [rsp+208h+var_1E8], eax
0x140049c83  mov     r9d, [rsp+208h+var_1B8]
0x140049c88  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x140049c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140049c96  mov     rcx, [rcx+10h]
0x140049c9a  call    WPP_SF_dd
0x140049c9f  mov     edi, 1
0x140049ca4  jmp     loc_14004A2DF
0x140049ca9  mov     edi, 1
0x140049cae  mov     r14d, edi
0x140049cb1  lea     r12, [r13+40h]
0x140049cb5  mov     rax, [rsi+28h]
0x140049cb9  add     rax, 40h ; '@'
0x140049cbd  mov     [rsp+208h+var_1E0], rax
0x140049cc2  mov     [rsp+208h+var_1E8], r12
0x140049cc7  mov     r9d, 0C0007D61h
0x140049ccd  lea     r8d, [rdi+1]
0x140049cd1  mov     edx, edi
0x140049cd3  mov     ecx, edi
0x140049cd5  call    FaxLog
0x140049cda  mov     rcx, cs:WPP_GLOBAL_Control
0x140049ce1  cmp     rcx, r15
0x140049ce4  jz      loc_14004A2DA
0x140049cea  test    byte ptr [rcx+1Ch], 4
0x140049cee  jz      loc_14004A2DA
0x140049cf4  cmp     byte ptr [rcx+19h], 2
0x140049cf8  jb      loc_14004A2DA
0x140049cfe  mov     rax, [rsi+28h]
0x140049d02  add     rax, 40h ; '@'
0x140049d06  mov     [rsp+208h+var_1E0], rax
0x140049d0b  mov     eax, [rsp+208h+var_1A8]
0x140049d0f  mov     dword ptr [rsp+208h+var_1E8], eax
0x140049d13  mov     r9, r12
0x140049d16  mov     rcx, [rcx+10h]
0x140049d1a  call    WPP_SF_SlS
0x140049d1f  jmp     loc_14004A2DA
0x140049d24  mov     r8d, [rsp+208h+var_1B8]
0x140049d29  shl     r8, 3; Size
0x140049d2d  xor     edx, edx; Val
0x140049d2f  mov     rcx, rax; void *
0x140049d32  call    memset_0
0x140049d37  cmp     [rsp+208h+var_1B8], ebx
0x140049d3b  jbe     loc_14004A0BA
0x140049d41  mov     r12d, ebx
0x140049d44  mov     edi, 1
0x140049d49  lea     rcx, [rsp+208h+var_148]
0x140049d51  or      rax, 0FFFFFFFFFFFFFFFFh
0x140049d55  inc     rax
0x140049d58  cmp     [rcx+rax*2], bx
0x140049d5c  jnz     short loc_140049D55
0x140049d5e  lea     eax, ds:12h[rax*2]
0x140049d65  mov     esi, eax
0x140049d67  mov     ecx, eax; dwBytes
0x140049d69  call    pMemAlloc
0x140049d6e  mov     [rsp+208h+var_1A0], rax
0x140049d73  test    rax, rax
0x140049d76  jz      loc_14004A229
0x140049d7c  mov     dword ptr [rsp+208h+var_1E8], r12d
0x140049d81  lea     r9, [rsp+208h+var_148]
0x140049d89  lea     r8, aSD; "%s%d"
0x140049d90  mov     edx, esi; unsigned __int64
0x140049d92  mov     rcx, rax; unsigned __int16 *
0x140049d95  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140049d9a  mov     esi, eax
0x140049d9c  test    eax, eax
0x140049d9e  js      loc_14004A1D5
0x140049da4  mov     r13, rbx
0x140049da7  mov     rax, [rsp+208h+var_168]
0x140049daf  mov     rsi, [rsp+208h+var_180]
0x140049db7  cmp     [rax+28h], ebx
0x140049dba  jbe     short loc_140049E1C
0x140049dbc  mov     r8d, ebx
0x140049dbf  mov     r11, [rax+20h]
0x140049dc3  mov     eax, r8d
0x140049dc6  imul    rdx, rax, 58h ; 'X'
0x140049dca  add     rdx, r11
0x140049dcd  cmp     [rdx+3Ch], edi
0x140049dd0  jnz     short loc_140049E06
0x140049dd2  lea     r10, [rsi+658h]
0x140049dd9  mov     rax, [rdx+48h]
0x140049ddd  sub     r10, rax
0x140049de0  movzx   r9d, word ptr [rax]
0x140049de4  movzx   ecx, word ptr [rax+r10]
0x140049de9  sub     r9d, ecx
0x140049dec  jnz     short loc_140049DF6
0x140049dee  add     rax, 2
0x140049df2  test    ecx, ecx
0x140049df4  jnz     short loc_140049DE0
0x140049df6  test    r9d, r9d
0x140049df9  jnz     short loc_140049E06
0x140049dfb  mov     ecx, [rsp+208h+var_1A8]
0x140049dff  add     ecx, r12d
0x140049e02  cmp     [rdx], ecx
0x140049e04  jz      short loc_140049E19
0x140049e06  add     r8d, edi
0x140049e09  mov     rax, [rsp+208h+var_168]
0x140049e11  cmp     r8d, [rax+28h]
0x140049e15  jb      short loc_140049DC3
0x140049e17  jmp     short loc_140049E1C
0x140049e19  mov     r13, rdx
0x140049e1c  test    r13, r13
0x140049e1f  jnz     short loc_140049E97
0x140049e21  mov     edx, [rsp+208h+var_1A8]
0x140049e25  add     edx, r12d
0x140049e28  mov     [rsp+208h+var_198], edx
0x140049e2c  mov     r9, [rsp+208h+var_188]
0x140049e34  mov     eax, [r9+1Ch]
0x140049e38  or      eax, 4
0x140049e3b  lea     r8, [rsi+658h]
0x140049e42  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140049e49  add     rcx, 70h ; 'p'
0x140049e4d  mov     [rsp+208h+var_1C0], edi
0x140049e51  mov     [rsp+208h+var_1C8], eax
0x140049e55  mov     [rsp+208h+var_1D0], edx
0x140049e59  mov     rax, [r9+8]
0x140049e5d  mov     [rsp+208h+var_1D8], rax
0x140049e62  mov     rax, [rsp+208h+var_178]
0x140049e6a  mov     rax, [rax]
0x140049e6d  mov     [rsp+208h+var_1E0], rax
0x140049e72  mov     [rsp+208h+var_1E8], r8
0x140049e77  mov     r8, [rsp+208h+var_1A0]
0x140049e7c  lea     rdx, [rsp+208h+var_198]
0x140049e81  call    RegAddNewFaxDevice
0x140049e86  mov     r14d, eax
0x140049e89  test    eax, eax
0x140049e8b  jnz     loc_14004A0FB
0x140049e91  mov     eax, [rsp+208h+var_198]
0x140049e95  jmp     short loc_140049E9B
0x140049e97  mov     eax, [r13+40h]
0x140049e9b  mov     [rsp+208h+var_198], eax
0x140049e9f  mov     ecx, 0C0h; dwBytes
0x140049ea4  call    pMemAlloc
0x140049ea9  mov     rsi, rax
0x140049eac  test    rax, rax
0x140049eaf  jz      loc_14004A19B
0x140049eb5  xor     edx, edx; Val
0x140049eb7  mov     r8d, 0C0h; Size
0x140049ebd  mov     rcx, rax; void *
0x140049ec0  call    memset_0
0x140049ec5  mov     rcx, [rsp+208h+var_170]
0x140049ecd  mov     eax, [rcx]
0x140049ecf  mov     rcx, [rsp+208h+var_1B0]
0x140049ed4  mov     [rcx+rax*8], rsi
0x140049ed8  mov     dword ptr [rsi+10h], 454E494Ch
0x140049edf  mov     [rsi+14h], r12d
0x140049ee3  mov     ecx, [rsp+208h+var_1A8]
0x140049ee7  add     ecx, r12d
0x140049eea  mov     [rsi+1Ch], ecx
0x140049eed  mov     eax, [rsp+208h+var_198]
0x140049ef1  mov     [rsi+18h], eax
0x140049ef4  mov     [rsi+20h], ebx
0x140049ef7  mov     rax, [rsp+208h+var_180]
0x140049eff  mov     [rsi+28h], rax
0x140049f03  mov     rax, [rsp+208h+var_1A0]
0x140049f08  mov     [rsi+38h], rax
0x140049f0c  mov     [rsi+68h], ebx
0x140049f0f  mov     dword ptr [rsi+48h], 20100000h
0x140049f16  test    r13, r13
  ... truncated ...
```
