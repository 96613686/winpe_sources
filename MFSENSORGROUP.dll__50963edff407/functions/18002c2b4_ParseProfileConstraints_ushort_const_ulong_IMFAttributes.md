# ParseProfileConstraints(ushort const *,ulong *,IMFAttributes * *)

- ea: `0x18002c2b4`
- end: `0x18002cb4c`
- name: `?ParseProfileConstraints@@YAJPEBGPEAKPEAPEAUIMFAttributes@@@Z`
- size: `2200`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, struct IMFAttributes **)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000c388`
- `0x18005c544`
- `0x18005ce7c`

## callees

- `0x180005fa0`
- `0x18000c348`
- `0x18000d1f0`
- `0x18002c2b4`
- `0x18002cff4`
- `0x18002d02c`
- `0x18003f6b8`
- `0x1800459c4`
- `0x180051a1c`
- `0x180077010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c3bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c405`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c47d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c508`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c580`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c665`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c72d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c3bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c405`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c47d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c508`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c580`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c665`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c72d`
- `MFPlat!MFCreateAttributes` at `0x18002c49e`
- `MFPlat!MFCreateAttributes` at `0x18002c5a1`
- `MFPlat!MFCreateAttributes` at `0x18002c690`
- `MFPlat!MFCreateAttributes` at `0x18002c78f`
- `MFPlat!MFCreateAttributes` at `0x18002c49e`
- `MFPlat!MFCreateAttributes` at `0x18002c5a1`
- `MFPlat!MFCreateAttributes` at `0x18002c690`
- `MFPlat!MFCreateAttributes` at `0x18002c78f`

## pseudocode

```c
__int64 __fastcall ParseProfileConstraints(
        const unsigned __int16 *a1,
        unsigned int *a2,
        struct IMFAttributes **a3,
        __int64 a4)
{
  IMFAttributes *v4; // r10
  struct IMFAttributes **v5; // r15
  const unsigned __int16 *NextFilterEntry; // r14
  unsigned int v8; // ebx
  char v9; // r13
  unsigned int v10; // r13d
  unsigned int v11; // r15d
  unsigned int i; // r15d
  HRESULT v13; // eax
  __int64 v14; // r11
  IMFAttributes *v15; // rcx
  char v16; // al
  unsigned int j; // r15d
  __int64 v18; // r11
  IMFAttributes *v19; // rcx
  unsigned int k; // r15d
  unsigned __int64 v21; // r12
  wchar_t *v22; // rdx
  wchar_t *v23; // rax
  __int64 v24; // r9
  IMFAttributes *v25; // rcx
  unsigned int m; // r15d
  __int64 v27; // r12
  unsigned __int64 v28; // r13
  const wchar_t *v29; // rcx
  IMFAttributes *v30; // rcx
  __int64 v31; // rdx
  int v32; // edx
  __int64 v33; // rdx
  __int64 v34; // rdx
  unsigned __int8 v35; // r8
  const GUID *v36; // r8
  unsigned __int8 v38; // [rsp+30h] [rbp-28h]
  char v39; // [rsp+31h] [rbp-27h]
  int v40; // [rsp+34h] [rbp-24h] BYREF
  unsigned int v41; // [rsp+38h] [rbp-20h]
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 v43[2]; // [rsp+48h] [rbp-10h] BYREF
  unsigned __int8 v44; // [rsp+A0h] [rbp+48h]
  char v47; // [rsp+B8h] [rbp+60h]

  v4 = 0;
  v5 = a3;
  ppMFAttributes = 0;
  NextFilterEntry = a1;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 149, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, a1);
    v4 = 0;
  }
  if ( !a2 )
  {
    v8 = -2147467261;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        150,
        &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids,
        0,
        -2147467261);
    goto LABEL_140;
  }
  v41 = 0;
  v8 = 0;
  v39 = 0;
  v9 = 0;
  v47 = 0;
  v44 = 0;
  v38 = 0;
  *a2 = 0;
  if ( v5 )
    *v5 = 0;
  while ( NextFilterEntry && *NextFilterEntry != (_WORD)v4 )
  {
    v10 = v41;
    v43[0] = (unsigned __int64)v4;
    v11 = (unsigned int)v4;
    do
    {
      if ( !(unsigned int)_o__wcsnicmp(NextFilterEntry, (&off_180079DB8)[3 * (int)v11], qword_180079DC0[3 * (int)v11]) )
        v10 |= dword_180079DB0[6 * v11];
      ++v11;
    }
    while ( v11 < 8 );
    v5 = a3;
    v41 = v10;
    v9 = v47;
    if ( a3 )
    {
      if ( !(unsigned int)_o__wcsnicmp(NextFilterEntry, L"eSPProfileH265", 14) )
      {
        if ( !v47 )
        {
          if ( NextFilterEntry[14] == 95 )
          {
            for ( i = 0; i < 0x16; ++i )
            {
              v13 = StringCchLengthW((&off_180079ED0)[2 * (int)i], 0x7FFFFFFFu, v43);
              v8 = v13;
              if ( v13 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_140;
                v31 = 153;
                goto LABEL_78;
              }
              if ( !(unsigned int)_o__wcsnicmp(
                                    NextFilterEntry + 14,
                                    *(_QWORD *)(v14 + 16LL * (int)i + 499408) + 28LL,
                                    v43[0] - 14) )
              {
                v15 = ppMFAttributes;
                if ( !ppMFAttributes )
                {
                  v13 = MFCreateAttributes(&ppMFAttributes, 1u);
                  v8 = v13;
                  if ( v13 < 0 )
                  {
                    if ( !g_wppLevels )
                      goto LABEL_140;
                    v31 = 154;
                    goto LABEL_78;
                  }
                  v15 = ppMFAttributes;
                }
                v13 = ((__int64 (__fastcall *)(IMFAttributes *, const GUID *, _QWORD))v15->lpVtbl->SetUINT32)(
                        v15,
                        &MF_MT_MPEG2_PROFILE,
                        (unsigned int)dword_180079ED8[4 * i]);
                v8 = v13;
                if ( v13 >= 0 )
                {
                  v16 = byte_180079EDC[16 * i];
                  goto LABEL_28;
                }
                if ( g_wppLevels )
                {
                  v31 = 155;
                  goto LABEL_78;
                }
                goto LABEL_140;
              }
            }
            goto LABEL_42;
          }
          if ( byte_18008D62D )
          {
            v32 = 152;
            goto LABEL_81;
          }
          goto LABEL_82;
        }
        if ( byte_18008D62D )
        {
          v33 = 151;
          goto LABEL_85;
        }
        goto LABEL_123;
      }
      if ( (unsigned int)_o__wcsnicmp(NextFilterEntry, L"eSPProfile", 10) )
        goto LABEL_42;
      if ( v47 )
      {
        if ( byte_18008D62D )
        {
          v33 = 156;
LABEL_85:
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v33,
            &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids,
            3222091495LL);
        }
LABEL_123:
        v8 = -1072875801;
      }
      else
      {
        if ( NextFilterEntry[14] == 95 )
        {
          for ( j = 0; j < 0x10; ++j )
          {
            v13 = StringCchLengthW((&off_18007A030)[2 * (int)j], 0x7FFFFFFFu, v43);
            v8 = v13;
            if ( v13 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_140;
              v31 = 158;
              goto LABEL_78;
            }
            if ( !(unsigned int)_o__wcsnicmp(
                                  NextFilterEntry + 14,
                                  *(_QWORD *)(v18 + 16LL * (int)j + 499760) + 20LL,
                                  v43[0] - 10) )
            {
              v19 = ppMFAttributes;
              if ( !ppMFAttributes )
              {
                v13 = MFCreateAttributes(&ppMFAttributes, 1u);
                v8 = v13;
                if ( v13 < 0 )
                {
                  if ( !g_wppLevels )
                    goto LABEL_140;
                  v31 = 159;
                  goto LABEL_78;
                }
                v19 = ppMFAttributes;
              }
              v13 = ((__int64 (__fastcall *)(IMFAttributes *, const GUID *, _QWORD))v19->lpVtbl->SetUINT32)(
                      v19,
                      &MF_MT_MPEG2_PROFILE,
                      (unsigned int)dword_18007A038[4 * j]);
              v8 = v13;
              if ( v13 >= 0 )
              {
                v16 = byte_18007A03C[16 * j];
LABEL_28:
                v47 = 1;
                v44 = v16;
                break;
              }
              if ( !g_wppLevels )
                goto LABEL_140;
              v31 = 160;
              goto LABEL_78;
            }
          }
LABEL_42:
          for ( k = 0; ; ++k )
          {
            if ( k >= 2 )
              goto LABEL_57;
            v21 = 32LL * (int)k;
            v22 = (&off_18008B1C0)[v21 / 8];
            if ( !v22 )
            {
              v8 = -2147024809;
LABEL_104:
              if ( g_wppLevels )
              {
                v34 = 161;
LABEL_106:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v34,
                  &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids,
                  0,
                  -2147024809);
              }
              goto LABEL_140;
            }
            v23 = (&off_18008B1C0)[v21 / 8];
            v24 = 0x7FFFFFFF;
            do
            {
              if ( !*v23 )
                break;
              ++v23;
              --v24;
            }
            while ( v24 );
            v8 = v24 == 0 ? 0x80070057 : 0;
            v43[0] = (0x7FFFFFFF - v24) & -(__int64)(v24 != 0);
            if ( !v24 )
              goto LABEL_104;
            if ( !(unsigned int)_o__wcsnicmp(NextFilterEntry, v22, (0x7FFFFFFF - v24) & -(__int64)(v24 != 0)) )
              break;
          }
          if ( v39 )
          {
            if ( !byte_18008D62D )
              goto LABEL_123;
            v33 = 162;
            goto LABEL_85;
          }
          v25 = ppMFAttributes;
          if ( !ppMFAttributes )
          {
            v13 = MFCreateAttributes(&ppMFAttributes, 1u);
            v8 = v13;
            if ( v13 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_140;
              v31 = 163;
              goto LABEL_78;
            }
            v25 = ppMFAttributes;
          }
          v13 = ((__int64 (__fastcall *)(IMFAttributes *, const GUID *, __int128 *))v25->lpVtbl->SetGUID)(
                  v25,
                  &MF_MT_SUBTYPE,
                  &xmmword_18008B1C8[v21 / 0x10]);
          v8 = v13;
          if ( v13 >= 0 )
          {
            v38 = algn_18008B1D8[v21];
            v39 = 1;
LABEL_57:
            for ( m = 0; ; ++m )
            {
              if ( m >= 3 )
              {
                v9 = v47;
                v5 = a3;
                goto LABEL_71;
              }
              v27 = 4LL * (int)m;
              v13 = StringCchLengthW((&off_180079E70)[v27], 0x7FFFFFFFu, v43);
              v8 = v13;
              if ( v13 < 0 )
                break;
              v28 = v43[0];
              if ( !(unsigned int)_o__wcsnicmp(NextFilterEntry, (&off_180079E70)[v27], v43[0]) )
              {
                v29 = &NextFilterEntry[v28];
                v40 = 0;
                if ( !*v29 )
                {
                  v8 = -2147024809;
                  if ( !g_wppLevels )
                    goto LABEL_140;
                  v34 = 166;
                  goto LABEL_106;
                }
                if ( swscanf_s(v29, L"%u", &v40) != 1 )
                {
                  v8 = -2147024809;
                  if ( !g_wppLevels )
                    goto LABEL_140;
                  v34 = 167;
                  goto LABEL_106;
                }
                v30 = ppMFAttributes;
                v40 *= LODWORD(qword_180079E78[v27 + 2]);
                if ( !ppMFAttributes )
                {
                  v13 = MFCreateAttributes(&ppMFAttributes, 1u);
                  v8 = v13;
                  if ( v13 < 0 )
                  {
                    if ( !g_wppLevels )
                      goto LABEL_140;
                    v31 = 168;
                    goto LABEL_78;
                  }
                  v30 = ppMFAttributes;
                }
                v13 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *))v30->lpVtbl->SetUINT32)(
                        v30,
                        &qword_180079E78[v27]);
                v8 = v13;
                if ( v13 < 0 )
                {
                  if ( !g_wppLevels )
                    goto LABEL_140;
                  v31 = 169;
                  goto LABEL_78;
                }
              }
            }
            if ( !g_wppLevels )
              goto LABEL_140;
            v31 = 165;
            goto LABEL_78;
          }
          if ( !g_wppLevels )
            goto LABEL_140;
          v31 = 164;
LABEL_78:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v13);
          goto LABEL_140;
        }
        if ( byte_18008D62D )
        {
          v32 = 157;
LABEL_81:
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v32,
            (unsigned int)&WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids,
            -2147024809,
            (__int64)NextFilterEntry);
        }
LABEL_82:
        v8 = -2147024809;
      }
      goto LABEL_140;
    }
LABEL_71:
    NextFilterEntry = (const unsigned __int16 *)FindNextFilterEntry(NextFilterEntry, 59);
  }
  LOBYTE(a4) = v39;
  if ( v9 && v39 )
  {
    v35 = v38;
    if ( v38 )
    {
      if ( !v44 )
        goto LABEL_121;
    }
    else if ( v44 )
    {
LABEL_121:
      if ( byte_18008D62D )
        WPP_SF_Ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          170,
          &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids,
          3222091495LL,
          v38,
          v44);
      goto LABEL_123;
    }
  }
  else
  {
    v35 = v38;
  }
  if ( !v5 || !ppMFAttributes )
  {
LABEL_139:
    *a2 = v41;
    goto LABEL_140;
  }
  if ( !v39 )
  {
    if ( v9 )
    {
      v36 = &MFVideoFormat_HEVC;
      if ( !v44 )
        v36 = &MFVideoFormat_H264;
      v13 = ((__int64 (__fastcall *)(IMFAttributes *, const GUID *, const GUID *))ppMFAttributes->lpVtbl->SetGUID)(
              ppMFAttributes,
              &MF_MT_SUBTYPE,
              v36);
      v4 = 0;
      v8 = v13;
      if ( v13 < 0 )
      {
        if ( g_wppLevels )
        {
          v31 = 172;
          goto LABEL_78;
        }
        goto LABEL_140;
      }
    }
    goto LABEL_138;
  }
  if ( v9
    || (v13 = ((__int64 (__fastcall *)(IMFAttributes *, const GUID *, _QWORD, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
                ppMFAttributes,
                &MF_MT_MPEG2_PROFILE,
                v35 != 0 ? 1 : 77,
                a4),
        v4 = 0,
        v8 = v13,
        v13 >= 0) )
  {
LABEL_138:
    *v5 = ppMFAttributes;
    ppMFAttributes = v4;
    goto LABEL_139;
  }
  if ( g_wppLevels )
  {
    v31 = 171;
    goto LABEL_78;
  }
LABEL_140:
  if ( ppMFAttributes )
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  return v8;
}

```

## disassembly

```asm
0x18002c2b4  mov     [rsp-40h+arg_10], r8
0x18002c2b9  mov     [rsp-40h+arg_8], rdx
0x18002c2be  push    rbp
0x18002c2bf  push    rbx
0x18002c2c0  push    rsi
0x18002c2c1  push    rdi
0x18002c2c2  push    r12
0x18002c2c4  push    r13
0x18002c2c6  push    r14
0x18002c2c8  push    r15
0x18002c2ca  mov     rbp, rsp
0x18002c2cd  sub     rsp, 58h
0x18002c2d1  xor     r10d, r10d
0x18002c2d4  mov     r15, r8
0x18002c2d7  mov     [rbp+ppMFAttributes], r10
0x18002c2db  mov     r12, rdx
0x18002c2de  mov     r14, rcx
0x18002c2e1  cmp     cs:byte_18008D62D, 8
0x18002c2e8  jb      short loc_18002C30F
0x18002c2ea  mov     r9, rcx
0x18002c2ed  lea     r8, WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids
0x18002c2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2fb  mov     edx, 95h
0x18002c300  mov     rcx, [rcx+0D8h]
0x18002c307  call    WPP_SF_S
0x18002c30c  xor     r10d, r10d
0x18002c30f  test    r12, r12
0x18002c312  jnz     short loc_18002C353
0x18002c314  mov     ebx, 80004003h
0x18002c319  lea     edi, [r12+1]
0x18002c31e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18002c325  jb      loc_18002CB24
0x18002c32b  mov     edx, 96h
0x18002c330  mov     dword ptr [rsp+58h+var_38], ebx
0x18002c334  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c33b  lea     r8, WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids
0x18002c342  xor     r9d, r9d
0x18002c345  mov     rcx, [rcx+10h]
0x18002c349  call    WPP_SF_qD
0x18002c34e  jmp     loc_18002CB24
0x18002c353  mov     [rbp+var_20], r10d
0x18002c357  mov     ebx, r10d
0x18002c35a  mov     [rbp+var_27], r10b
0x18002c35e  mov     r13b, r10b
0x18002c361  mov     [rbp+arg_18], r10b
0x18002c365  mov     [rbp+arg_0], r10b
0x18002c369  mov     [rbp+var_28], r10b
0x18002c36d  mov     [r12], r10d
0x18002c371  test    r15, r15
0x18002c374  jz      short loc_18002C379
0x18002c376  mov     [r15], r10
0x18002c379  mov     edi, 1
0x18002c37e  test    r14, r14
0x18002c381  jz      loc_18002C9F0
0x18002c387  cmp     [r14], r10w
0x18002c38b  jz      loc_18002C9F0
0x18002c391  mov     r13d, [rbp+var_20]
0x18002c395  lea     rsi, __ImageBase
0x18002c39c  mov     [rbp+var_10], r10
0x18002c3a0  mov     r15d, r10d
0x18002c3a3  movsxd  rax, r15d
0x18002c3a6  mov     rcx, r14
0x18002c3a9  lea     r12, [rax+rax*2]
0x18002c3ad  mov     r8, ds:rva qword_180079DC0[rsi+r12*8]
0x18002c3b5  mov     rdx, ds:rva off_180079DB8[rsi+r12*8]; "DIS" ...
0x18002c3bd  call    cs:__imp__o__wcsnicmp
0x18002c3c3  xor     r10d, r10d
0x18002c3c6  test    eax, eax
0x18002c3c8  jnz     short loc_18002C3D2
0x18002c3ca  or      r13d, ds:rva dword_180079DB0[rsi+r12*8]
0x18002c3d2  add     r15d, edi
0x18002c3d5  cmp     r15d, 8
0x18002c3d9  jb      short loc_18002C3A3
0x18002c3db  mov     r15, [rbp+arg_10]
0x18002c3df  mov     esi, 80070057h
0x18002c3e4  mov     [rbp+var_20], r13d
0x18002c3e8  mov     r13b, [rbp+arg_18]
0x18002c3ec  test    r15, r15
0x18002c3ef  jz      loc_18002C7F4
0x18002c3f5  mov     r8d, 0Eh
0x18002c3fb  lea     rdx, aEspprofileh265_2; "eSPProfileH265"
0x18002c402  mov     rcx, r14
0x18002c405  call    cs:__imp__o__wcsnicmp
0x18002c40b  xor     r10d, r10d
0x18002c40e  test    eax, eax
0x18002c410  jnz     loc_18002C4F8
0x18002c416  test    r13b, r13b
0x18002c419  jnz     loc_18002C886
0x18002c41f  cmp     word ptr [r14+1Ch], 5Fh ; '_'
0x18002c425  jnz     loc_18002C84C
0x18002c42b  mov     r15d, r10d
0x18002c42e  cmp     r15d, 16h
0x18002c432  jnb     loc_18002C5F4
0x18002c438  movsxd  r12, r15d
0x18002c43b  lea     r11, __ImageBase
0x18002c442  add     r12, r12
0x18002c445  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18002c449  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002c44e  mov     rcx, ds:rva off_180079ED0[r11+r12*8]; unsigned __int16 *
0x18002c456  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002c45b  mov     ebx, eax
0x18002c45d  test    eax, eax
0x18002c45f  js      loc_18002C831
0x18002c465  mov     rdx, [r11+r12*8+79ED0h]
0x18002c46d  lea     rcx, [r14+1Ch]
0x18002c471  mov     r8, [rbp+var_10]
0x18002c475  add     rdx, 1Ch
0x18002c479  add     r8, 0FFFFFFFFFFFFFFF2h
0x18002c47d  call    cs:__imp__o__wcsnicmp
0x18002c483  xor     r10d, r10d
0x18002c486  test    eax, eax
0x18002c488  jz      short loc_18002C48F
0x18002c48a  add     r15d, edi
0x18002c48d  jmp     short loc_18002C42E
0x18002c48f  mov     rcx, [rbp+ppMFAttributes]
0x18002c493  test    rcx, rcx
0x18002c496  jnz     short loc_18002C4B2
0x18002c498  mov     edx, edi; cInitialSize
0x18002c49a  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18002c49e  call    cs:__imp_MFCreateAttributes
0x18002c4a4  mov     ebx, eax
0x18002c4a6  test    eax, eax
0x18002c4a8  js      loc_18002C809
0x18002c4ae  mov     rcx, [rbp+ppMFAttributes]
0x18002c4b2  mov     rax, [rcx]
0x18002c4b5  lea     r13, __ImageBase
0x18002c4bc  mov     r8d, ds:rva dword_180079ED8[r13+r12*8]
0x18002c4c4  lea     rdx, MF_MT_MPEG2_PROFILE
0x18002c4cb  mov     rax, [rax+0A8h]
0x18002c4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4d7  xor     r10d, r10d
0x18002c4da  mov     ebx, eax
0x18002c4dc  test    eax, eax
0x18002c4de  js      loc_18002C81D
0x18002c4e4  mov     al, ds:rva byte_180079EDC[r13+r12*8]
0x18002c4ec  mov     [rbp+arg_18], dil
0x18002c4f0  mov     [rbp+arg_0], al
0x18002c4f3  jmp     loc_18002C5FB
0x18002c4f8  mov     r8d, 0Ah
0x18002c4fe  lea     rdx, aEspprofile; "eSPProfile"
0x18002c505  mov     rcx, r14
0x18002c508  call    cs:__imp__o__wcsnicmp
0x18002c50e  xor     r10d, r10d
0x18002c511  test    eax, eax
0x18002c513  jnz     loc_18002C5F4
0x18002c519  test    r13b, r13b
0x18002c51c  jnz     loc_18002C919
0x18002c522  cmp     word ptr [r14+1Ch], 5Fh ; '_'
0x18002c528  jnz     loc_18002C902
0x18002c52e  mov     r15d, r10d
0x18002c531  cmp     r15d, 10h
0x18002c535  jnb     loc_18002C5F4
0x18002c53b  movsxd  r12, r15d
0x18002c53e  lea     r11, __ImageBase
0x18002c545  add     r12, r12
0x18002c548  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18002c54c  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002c551  mov     rcx, ds:rva off_18007A030[r11+r12*8]; unsigned __int16 *
0x18002c559  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002c55e  mov     ebx, eax
0x18002c560  test    eax, eax
0x18002c562  js      loc_18002C8EB
0x18002c568  mov     rdx, [r11+r12*8+7A030h]
0x18002c570  lea     rcx, [r14+1Ch]
0x18002c574  mov     r8, [rbp+var_10]
0x18002c578  add     rdx, 14h
0x18002c57c  add     r8, 0FFFFFFFFFFFFFFF6h
0x18002c580  call    cs:__imp__o__wcsnicmp
0x18002c586  xor     r10d, r10d
0x18002c589  test    eax, eax
0x18002c58b  jz      short loc_18002C592
0x18002c58d  add     r15d, edi
0x18002c590  jmp     short loc_18002C531
0x18002c592  mov     rcx, [rbp+ppMFAttributes]
0x18002c596  test    rcx, rcx
0x18002c599  jnz     short loc_18002C5B5
0x18002c59b  mov     edx, edi; cInitialSize
0x18002c59d  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18002c5a1  call    cs:__imp_MFCreateAttributes
0x18002c5a7  mov     ebx, eax
0x18002c5a9  test    eax, eax
0x18002c5ab  js      loc_18002C8BD
0x18002c5b1  mov     rcx, [rbp+ppMFAttributes]
0x18002c5b5  mov     rax, [rcx]
0x18002c5b8  lea     r13, __ImageBase
0x18002c5bf  mov     r8d, ds:rva dword_18007A038[r13+r12*8]
0x18002c5c7  lea     rdx, MF_MT_MPEG2_PROFILE
0x18002c5ce  mov     rax, [rax+0A8h]
0x18002c5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5da  xor     r10d, r10d
0x18002c5dd  mov     ebx, eax
0x18002c5df  test    eax, eax
0x18002c5e1  js      loc_18002C8D4
0x18002c5e7  mov     al, ds:rva byte_18007A03C[r13+r12*8]
0x18002c5ef  jmp     loc_18002C4EC
0x18002c5f4  lea     r13, __ImageBase
0x18002c5fb  mov     r15d, r10d
0x18002c5fe  cmp     r15d, 2
0x18002c602  jnb     loc_18002C6E0
0x18002c608  movsxd  r12, r15d
0x18002c60b  shl     r12, 5
0x18002c60f  mov     rdx, [r12+r13+8B1C0h]
0x18002c617  test    rdx, rdx
0x18002c61a  jz      loc_18002C979
0x18002c620  mov     ecx, 7FFFFFFFh
0x18002c625  mov     rax, rdx
0x18002c628  mov     r9d, ecx
0x18002c62b  cmp     [rax], r10w
0x18002c62f  jz      short loc_18002C63A
0x18002c631  add     rax, 2
0x18002c635  sub     r9, rdi
0x18002c638  jnz     short loc_18002C62B
0x18002c63a  mov     rax, r9
0x18002c63d  neg     rax
0x18002c640  mov     rax, r9
0x18002c643  sbb     ebx, ebx
0x18002c645  sub     rcx, r9
0x18002c648  not     ebx
0x18002c64a  and     ebx, esi
0x18002c64c  neg     rax
0x18002c64f  sbb     r8, r8
0x18002c652  and     r8, rcx
0x18002c655  mov     [rbp+var_10], r8
0x18002c659  test    r9, r9
0x18002c65c  jz      loc_18002C975
0x18002c662  mov     rcx, r14
0x18002c665  call    cs:__imp__o__wcsnicmp
0x18002c66b  xor     r10d, r10d
0x18002c66e  test    eax, eax
0x18002c670  jz      short loc_18002C677
0x18002c672  add     r15d, edi
0x18002c675  jmp     short loc_18002C5FE
0x18002c677  cmp     [rbp+var_27], r10b
0x18002c67b  jnz     loc_18002C95E
0x18002c681  mov     rcx, [rbp+ppMFAttributes]
0x18002c685  test    rcx, rcx
0x18002c688  jnz     short loc_18002C6A4
0x18002c68a  mov     edx, edi; cInitialSize
0x18002c68c  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18002c690  call    cs:__imp_MFCreateAttributes
0x18002c696  mov     ebx, eax
0x18002c698  test    eax, eax
0x18002c69a  js      loc_18002C930
0x18002c6a0  mov     rcx, [rbp+ppMFAttributes]
0x18002c6a4  mov     rax, [rcx]
0x18002c6a7  lea     r8, rva xmmword_18008B1C8[r13]
0x18002c6ae  add     r8, r12
0x18002c6b1  lea     rdx, MF_MT_SUBTYPE
0x18002c6b8  mov     rax, [rax+0C0h]
0x18002c6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6c4  xor     r10d, r10d
0x18002c6c7  mov     ebx, eax
0x18002c6c9  test    eax, eax
0x18002c6cb  js      loc_18002C947
0x18002c6d1  mov     al, [r12+r13+8B1D8h]
0x18002c6d9  mov     [rbp+var_28], al
0x18002c6dc  mov     [rbp+var_27], dil
0x18002c6e0  mov     r15d, r10d
0x18002c6e3  cmp     r15d, 3
0x18002c6e7  jnb     loc_18002C7EC
0x18002c6ed  movsxd  r12, r15d
0x18002c6f0  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18002c6f4  shl     r12, 5
0x18002c6f8  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002c6fd  mov     rcx, [r12+r13+79E70h]; unsigned __int16 *
0x18002c705  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002c70a  mov     ebx, eax
0x18002c70c  test    eax, eax
0x18002c70e  js      loc_18002C9D9
0x18002c714  mov     r13, [rbp+var_10]
0x18002c718  lea     rdx, __ImageBase
0x18002c71f  mov     rdx, [r12+rdx+79E70h]
0x18002c727  mov     r8, r13
0x18002c72a  mov     rcx, r14
0x18002c72d  call    cs:__imp__o__wcsnicmp
0x18002c733  xor     r10d, r10d
0x18002c736  test    eax, eax
0x18002c738  jnz     loc_18002C7DD
0x18002c73e  lea     rcx, [r14+r13*2]; Buffer
0x18002c742  mov     [rbp+var_24], r10d
0x18002c746  cmp     [rcx], r10w
0x18002c74a  jz      loc_18002C9C3
0x18002c750  lea     r8, [rbp+var_24]
0x18002c754  lea     rdx, aU_0; "%u"
0x18002c75b  call    swscanf_s
0x18002c760  cmp     eax, edi
0x18002c762  jnz     loc_18002C9AD
0x18002c768  mov     r8d, [rbp+var_24]
0x18002c76c  lea     r13, __ImageBase
0x18002c773  imul    r8d, [r12+r13+79E88h]
0x18002c77c  mov     rcx, [rbp+ppMFAttributes]
0x18002c780  mov     [rbp+var_24], r8d
0x18002c784  test    rcx, rcx
0x18002c787  jnz     short loc_18002C7A7
0x18002c789  mov     edx, edi; cInitialSize
0x18002c78b  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18002c78f  call    cs:__imp_MFCreateAttributes
0x18002c795  mov     ebx, eax
0x18002c797  test    eax, eax
0x18002c799  js      loc_18002C996
  ... truncated ...
```
