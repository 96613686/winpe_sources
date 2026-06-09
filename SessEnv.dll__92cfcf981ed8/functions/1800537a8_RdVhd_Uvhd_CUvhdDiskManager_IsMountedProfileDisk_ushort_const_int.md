# RdVhd::Uvhd::CUvhdDiskManager::IsMountedProfileDisk(ushort const *,int *)

- ea: `0x1800537a8`
- end: `0x180053d13`
- name: `?IsMountedProfileDisk@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBGPEAH@Z`
- size: `1387`
- prototype: `int(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180053d20`

## callees

- `0x180004db0`
- `0x18003114c`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x1800327c8`
- `0x180032808`
- `0x180048414`
- `0x1800488e4`
- `0x180048b28`
- `0x1800537a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ace`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180053a36`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180053ac0`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180053a36`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180053ac0`
- `USERENV!GetProfilesDirectoryW` at `0x18005391a`
- `USERENV!GetProfilesDirectoryW` at `0x18005391a`

## string_xrefs

- `0x180053848`: `szUvhdVolumeGuidPath`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::IsMountedProfileDisk(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        int *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  int v8; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v9; // rcx
  __int64 v10; // rdx
  WCHAR *Buffer; // rax
  signed int LastError; // eax
  WCHAR *v13; // rax
  DWORD v14; // r10d
  signed int v15; // eax
  WCHAR *v16; // rax
  DWORD v17; // r10d
  signed int v18; // eax
  _WORD *v19; // rdi
  __int64 v20; // rax
  const int *v22; // [rsp+20h] [rbp-49h] BYREF
  int v23; // [rsp+28h] [rbp-41h]
  __int64 v24; // [rsp+2Ch] [rbp-3Dh]
  int v25; // [rsp+34h] [rbp-35h]
  __int64 v26; // [rsp+38h] [rbp-31h]
  int v27; // [rsp+40h] [rbp-29h]
  void **v28; // [rsp+48h] [rbp-21h] BYREF
  int v29; // [rsp+50h] [rbp-19h]
  __int64 v30; // [rsp+54h] [rbp-15h]
  int v31; // [rsp+5Ch] [rbp-Dh]
  __int64 v32; // [rsp+60h] [rbp-9h]
  int v33; // [rsp+68h] [rbp-1h]
  void **v34; // [rsp+70h] [rbp+7h] BYREF
  int v35; // [rsp+78h] [rbp+Fh]
  __int64 v36; // [rsp+7Ch] [rbp+13h]
  int v37; // [rsp+84h] [rbp+1Bh]
  __int64 v38; // [rsp+88h] [rbp+1Fh]
  int v39; // [rsp+90h] [rbp+27h]
  DWORD cchReturnLength; // [rsp+D0h] [rbp+67h] BYREF
  int v41; // [rsp+D4h] [rbp+6Bh]
  DWORD cchSize; // [rsp+D8h] [rbp+6Fh] BYREF

  v41 = HIDWORD(this);
  v24 = 128;
  v26 = 0;
  v22 = &CBaseStringT<unsigned short>::`vftable';
  v25 = 0;
  v28 = &CPathString::`vftable';
  v27 = 0x8000000;
  v23 = 0;
  cchReturnLength = 0;
  v30 = 128;
  v32 = 0;
  v31 = 0;
  v33 = 0x8000000;
  v29 = 0;
  cchSize = 0;
  if ( !a2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 190;
    v7 = L"szUvhdVolumeGuidPath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v5 + 2), v6, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v7);
LABEL_7:
    v8 = -2147024809;
    goto LABEL_90;
  }
  if ( !a3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 191;
    v7 = L"pfProfileDisk";
    goto LABEL_6;
  }
  *a3 = 0;
  v8 = CBaseStringT<unsigned short>::EnsureSpace(&v28, 260);
  if ( v8 >= 0 )
  {
    cchSize = CBaseStringT<unsigned short>::GetBufferLength(&v28);
    Buffer = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v28);
    if ( GetProfilesDirectoryW(Buffer, &cchSize) )
      goto LABEL_30;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v8 = v8 & 0x8000FFFF | 0x50460000;
    }
    if ( v8 >= 0 )
    {
LABEL_30:
      v8 = CBaseStringT<unsigned short>::SetLength(&v28);
      if ( v8 >= 0 )
      {
        v8 = CBaseStringT<unsigned short>::EnsureSpace(&v22, 260);
        if ( v8 >= 0 )
        {
          CBaseStringT<unsigned short>::GetBufferLength(&v22);
          v13 = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v22);
          if ( !GetVolumePathNamesForVolumeNameW(a2, v13, v14, &cchReturnLength) )
          {
            v15 = GetLastError();
            v8 = v15;
            if ( v15 == 234 )
            {
              v8 = CBaseStringT<unsigned short>::EnsureSpace(&v22, cchReturnLength);
              if ( v8 < 0 )
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v10 = 196;
                  goto LABEL_18;
                }
                goto LABEL_90;
              }
              CBaseStringT<unsigned short>::GetBufferLength(&v22);
              v16 = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v22);
              if ( !GetVolumePathNamesForVolumeNameW(a2, v16, v17, &cchReturnLength) )
              {
                v18 = GetLastError();
                v8 = v18;
                if ( v18 && (v18 & 0xFFFF0000) == 0 )
                {
                  if ( v18 > 0 )
                    v8 = (unsigned __int16)v18 | 0x80070000;
                  v8 = v8 & 0x8000FFFF | 0x504F0000;
                }
                if ( v8 < 0 )
                {
                  v9 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v10 = 197;
                    goto LABEL_18;
                  }
                  goto LABEL_90;
                }
              }
            }
            else
            {
              if ( v15 && (v15 & 0xFFFF0000) == 0 )
              {
                if ( v15 > 0 )
                  v8 = (unsigned __int16)v15 | 0x80070000;
                v8 = v8 & 0x8000FFFF | 0x50500000;
              }
              if ( v8 < 0 )
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v10 = 198;
                  goto LABEL_18;
                }
                goto LABEL_90;
              }
            }
          }
          v8 = CBaseStringT<unsigned short>::SetLength(&v22, cchReturnLength);
          if ( v8 >= 0 )
          {
            v19 = (_WORD *)CBaseStringT<unsigned short>::GetBuffer(&v22);
            if ( v19 )
            {
              while ( 1 )
              {
                if ( !*v19 )
                  goto LABEL_90;
                v36 = 128;
                v38 = 0;
                v37 = 0;
                v39 = 0x8000000;
                v34 = &CPathString::`vftable';
                v35 = 0;
                v8 = CBaseStringT<unsigned short>::Append((__int64)&v34, (__int64)v19);
                if ( v8 < 0 )
                  break;
                if ( (unsigned int)CPathString::StartsWith((CPathString *)&v34, (const struct CPathString *)&v28, 1) )
                {
                  *a3 = 1;
LABEL_89:
                  CPathString::~CPathString((CPathString *)&v34);
                  goto LABEL_90;
                }
                v20 = -1;
                do
                  ++v20;
                while ( v19[v20] );
                v19 += v20 + 1;
                CPathString::~CPathString((CPathString *)&v34);
              }
              if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  201,
                  WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
                  (unsigned int)v8);
              }
              goto LABEL_89;
            }
            v8 = -796852063;
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v10 = 200;
              goto LABEL_18;
            }
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v10 = 199;
              goto LABEL_18;
            }
          }
          goto LABEL_90;
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 195;
          goto LABEL_18;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 194;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 193;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 192;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, (unsigned int)v8);
    }
  }
LABEL_90:
  CPathString::~CPathString((CPathString *)&v28);
  CPathString::~CPathString((CPathString *)&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800537a8  mov     [rsp-8+arg_10], rbx
0x1800537ad  mov     qword ptr [rsp-8+cchReturnLength], rcx
0x1800537b2  push    rbp
0x1800537b3  push    rsi
0x1800537b4  push    rdi
0x1800537b5  push    r12
0x1800537b7  push    r14
0x1800537b9  lea     rbp, [rsp-37h]
0x1800537be  sub     rsp, 0A0h
0x1800537c5  xor     r14d, r14d
0x1800537c8  mov     [rbp+57h+var_94], 80h
0x1800537d0  lea     rax, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x1800537d7  mov     [rbp+57h+var_88], r14
0x1800537db  mov     ecx, 8000000h
0x1800537e0  mov     [rbp+57h+var_A0], rax
0x1800537e4  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x1800537eb  mov     [rbp+57h+var_8C], r14d
0x1800537ef  mov     [rbp+57h+var_78], rax
0x1800537f3  mov     rsi, r8
0x1800537f6  mov     rdi, rdx
0x1800537f9  mov     [rbp+57h+var_80], ecx
0x1800537fc  mov     [rbp+57h+var_98], r14d
0x180053800  mov     [rbp+57h+cchReturnLength], r14d
0x180053804  mov     [rbp+57h+var_6C], 80h
0x18005380c  mov     [rbp+57h+var_60], r14
0x180053810  mov     [rbp+57h+var_64], r14d
0x180053814  mov     [rbp+57h+var_58], ecx
0x180053817  mov     [rbp+57h+var_70], r14d
0x18005381b  mov     [rbp+57h+cchSize], r14d
0x18005381f  test    rdx, rdx
0x180053822  jnz     short loc_180053869
0x180053824  mov     rcx, cs:WPP_GLOBAL_Control
0x18005382b  lea     rax, WPP_GLOBAL_Control
0x180053832  cmp     rcx, rax
0x180053835  jz      short loc_18005385F
0x180053837  test    byte ptr [rcx+1Ch], 4
0x18005383b  jz      short loc_18005385F
0x18005383d  cmp     byte ptr [rcx+19h], 2
0x180053841  jb      short loc_18005385F
0x180053843  mov     edx, 0BEh
0x180053848  lea     r9, aSzuvhdvolumegu; "szUvhdVolumeGuidPath"
0x18005384f  mov     rcx, [rcx+10h]
0x180053853  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x18005385a  call    WPP_SF_S
0x18005385f  mov     ebx, 80070057h
0x180053864  jmp     loc_180053CE8
0x180053869  test    rsi, rsi
0x18005386c  jnz     short loc_18005389B
0x18005386e  mov     rcx, cs:WPP_GLOBAL_Control
0x180053875  lea     rax, WPP_GLOBAL_Control
0x18005387c  cmp     rcx, rax
0x18005387f  jz      short loc_18005385F
0x180053881  test    byte ptr [rcx+1Ch], 4
0x180053885  jz      short loc_18005385F
0x180053887  cmp     byte ptr [rcx+19h], 2
0x18005388b  jb      short loc_18005385F
0x18005388d  mov     edx, 0BFh
0x180053892  lea     r9, aPfprofiledisk; "pfProfileDisk"
0x180053899  jmp     short loc_18005384F
0x18005389b  mov     r12d, 104h
0x1800538a1  mov     [r8], r14d
0x1800538a4  mov     edx, r12d
0x1800538a7  lea     rcx, [rbp+57h+var_78]
0x1800538ab  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x1800538b0  mov     ebx, eax
0x1800538b2  test    eax, eax
0x1800538b4  jns     short loc_1800538FE
0x1800538b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538bd  lea     rax, WPP_GLOBAL_Control
0x1800538c4  cmp     rcx, rax
0x1800538c7  jz      loc_180053CE8
0x1800538cd  test    byte ptr [rcx+1Ch], 4
0x1800538d1  jz      loc_180053CE8
0x1800538d7  cmp     byte ptr [rcx+19h], 2
0x1800538db  jb      loc_180053CE8
0x1800538e1  lea     edx, [r12-44h]
0x1800538e6  mov     rcx, [rcx+10h]
0x1800538ea  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800538f1  mov     r9d, ebx
0x1800538f4  call    WPP_SF_d
0x1800538f9  jmp     loc_180053CE8
0x1800538fe  lea     rcx, [rbp+57h+var_78]
0x180053902  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180053907  lea     rcx, [rbp+57h+var_78]
0x18005390b  mov     [rbp+57h+cchSize], eax
0x18005390e  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180053913  mov     rcx, rax; lpProfileDir
0x180053916  lea     rdx, [rbp+57h+cchSize]; lpcchSize
0x18005391a  call    cs:__imp_GetProfilesDirectoryW
0x180053920  test    eax, eax
0x180053922  jnz     short loc_180053989
0x180053924  call    cs:__imp_GetLastError
0x18005392a  mov     ebx, eax
0x18005392c  test    eax, eax
0x18005392e  jz      short loc_180053950
0x180053930  test    eax, 0FFFF0000h
0x180053935  jnz     short loc_180053950
0x180053937  test    eax, eax
0x180053939  jle     short loc_180053944
0x18005393b  movzx   ebx, ax
0x18005393e  or      ebx, 80070000h
0x180053944  and     ebx, 0D046FFFFh
0x18005394a  or      ebx, 50460000h
0x180053950  test    ebx, ebx
0x180053952  jns     short loc_180053989
0x180053954  mov     rcx, cs:WPP_GLOBAL_Control
0x18005395b  lea     rax, WPP_GLOBAL_Control
0x180053962  cmp     rcx, rax
0x180053965  jz      loc_180053CE8
0x18005396b  test    byte ptr [rcx+1Ch], 4
0x18005396f  jz      loc_180053CE8
0x180053975  cmp     byte ptr [rcx+19h], 2
0x180053979  jb      loc_180053CE8
0x18005397f  mov     edx, 0C1h
0x180053984  jmp     loc_1800538E6
0x180053989  lea     rcx, [rbp+57h+var_78]
0x18005398d  call    ?SetLength@?$CBaseStringT@G@@QEAAJXZ; CBaseStringT<ushort>::SetLength(void)
0x180053992  mov     ebx, eax
0x180053994  test    eax, eax
0x180053996  jns     short loc_1800539CD
0x180053998  mov     rcx, cs:WPP_GLOBAL_Control
0x18005399f  lea     rax, WPP_GLOBAL_Control
0x1800539a6  cmp     rcx, rax
0x1800539a9  jz      loc_180053CE8
0x1800539af  test    byte ptr [rcx+1Ch], 4
0x1800539b3  jz      loc_180053CE8
0x1800539b9  cmp     byte ptr [rcx+19h], 2
0x1800539bd  jb      loc_180053CE8
0x1800539c3  mov     edx, 0C2h
0x1800539c8  jmp     loc_1800538E6
0x1800539cd  mov     edx, r12d
0x1800539d0  lea     rcx, [rbp+57h+var_A0]
0x1800539d4  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x1800539d9  mov     ebx, eax
0x1800539db  test    eax, eax
0x1800539dd  jns     short loc_180053A14
0x1800539df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539e6  lea     rax, WPP_GLOBAL_Control
0x1800539ed  cmp     rcx, rax
0x1800539f0  jz      loc_180053CE8
0x1800539f6  test    byte ptr [rcx+1Ch], 4
0x1800539fa  jz      loc_180053CE8
0x180053a00  cmp     byte ptr [rcx+19h], 2
0x180053a04  jb      loc_180053CE8
0x180053a0a  mov     edx, 0C3h
0x180053a0f  jmp     loc_1800538E6
0x180053a14  lea     rcx, [rbp+57h+var_A0]
0x180053a18  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180053a1d  lea     rcx, [rbp+57h+var_A0]
0x180053a21  mov     r10d, eax
0x180053a24  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180053a29  lea     r9, [rbp+57h+cchReturnLength]; lpcchReturnLength
0x180053a2d  mov     r8d, r10d; cchBufferLength
0x180053a30  mov     rdx, rax; lpszVolumePathNames
0x180053a33  mov     rcx, rdi; lpszVolumeName
0x180053a36  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180053a3c  test    eax, eax
0x180053a3e  jnz     loc_180053B94
0x180053a44  call    cs:__imp_GetLastError
0x180053a4a  mov     ebx, eax
0x180053a4c  cmp     eax, 0EAh
0x180053a51  jnz     loc_180053B37
0x180053a57  mov     edx, [rbp+57h+cchReturnLength]
0x180053a5a  lea     rcx, [rbp+57h+var_A0]
0x180053a5e  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180053a63  mov     ebx, eax
0x180053a65  test    eax, eax
0x180053a67  jns     short loc_180053A9E
0x180053a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a70  lea     rax, WPP_GLOBAL_Control
0x180053a77  cmp     rcx, rax
0x180053a7a  jz      loc_180053CE8
0x180053a80  test    byte ptr [rcx+1Ch], 4
0x180053a84  jz      loc_180053CE8
0x180053a8a  cmp     byte ptr [rcx+19h], 2
0x180053a8e  jb      loc_180053CE8
0x180053a94  mov     edx, 0C4h
0x180053a99  jmp     loc_1800538E6
0x180053a9e  lea     rcx, [rbp+57h+var_A0]
0x180053aa2  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180053aa7  lea     rcx, [rbp+57h+var_A0]
0x180053aab  mov     r10d, eax
0x180053aae  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180053ab3  lea     r9, [rbp+57h+cchReturnLength]; lpcchReturnLength
0x180053ab7  mov     r8d, r10d; cchBufferLength
0x180053aba  mov     rdx, rax; lpszVolumePathNames
0x180053abd  mov     rcx, rdi; lpszVolumeName
0x180053ac0  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180053ac6  test    eax, eax
0x180053ac8  jnz     loc_180053B94
0x180053ace  call    cs:__imp_GetLastError
0x180053ad4  mov     ebx, eax
0x180053ad6  test    eax, eax
0x180053ad8  jz      short loc_180053AFA
0x180053ada  test    eax, 0FFFF0000h
0x180053adf  jnz     short loc_180053AFA
0x180053ae1  test    eax, eax
0x180053ae3  jle     short loc_180053AEE
0x180053ae5  movzx   ebx, ax
0x180053ae8  or      ebx, 80070000h
0x180053aee  and     ebx, 0D04FFFFFh
0x180053af4  or      ebx, 504F0000h
0x180053afa  test    ebx, ebx
0x180053afc  jns     loc_180053B94
0x180053b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b09  lea     rax, WPP_GLOBAL_Control
0x180053b10  cmp     rcx, rax
0x180053b13  jz      loc_180053CE8
0x180053b19  test    byte ptr [rcx+1Ch], 4
0x180053b1d  jz      loc_180053CE8
0x180053b23  cmp     byte ptr [rcx+19h], 2
0x180053b27  jb      loc_180053CE8
0x180053b2d  mov     edx, 0C5h
0x180053b32  jmp     loc_1800538E6
0x180053b37  test    eax, eax
0x180053b39  jz      short loc_180053B5B
0x180053b3b  test    eax, 0FFFF0000h
0x180053b40  jnz     short loc_180053B5B
0x180053b42  test    eax, eax
0x180053b44  jle     short loc_180053B4F
0x180053b46  movzx   ebx, ax
0x180053b49  or      ebx, 80070000h
0x180053b4f  and     ebx, 0D050FFFFh
0x180053b55  or      ebx, 50500000h
0x180053b5b  test    ebx, ebx
0x180053b5d  jns     short loc_180053B94
0x180053b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b66  lea     rax, WPP_GLOBAL_Control
0x180053b6d  cmp     rcx, rax
0x180053b70  jz      loc_180053CE8
0x180053b76  test    byte ptr [rcx+1Ch], 4
0x180053b7a  jz      loc_180053CE8
0x180053b80  cmp     byte ptr [rcx+19h], 2
0x180053b84  jb      loc_180053CE8
0x180053b8a  mov     edx, 0C6h
0x180053b8f  jmp     loc_1800538E6
0x180053b94  mov     edx, [rbp+57h+cchReturnLength]
0x180053b97  lea     rcx, [rbp+57h+var_A0]
0x180053b9b  call    ?SetLength@?$CBaseStringT@G@@QEAAJK@Z; CBaseStringT<ushort>::SetLength(ulong)
0x180053ba0  mov     ebx, eax
0x180053ba2  test    eax, eax
0x180053ba4  jns     short loc_180053BDB
0x180053ba6  mov     rcx, cs:WPP_GLOBAL_Control
0x180053bad  lea     rax, WPP_GLOBAL_Control
0x180053bb4  cmp     rcx, rax
0x180053bb7  jz      loc_180053CE8
0x180053bbd  test    byte ptr [rcx+1Ch], 4
0x180053bc1  jz      loc_180053CE8
0x180053bc7  cmp     byte ptr [rcx+19h], 2
0x180053bcb  jb      loc_180053CE8
0x180053bd1  mov     edx, 0C7h
0x180053bd6  jmp     loc_1800538E6
0x180053bdb  lea     rcx, [rbp+57h+var_A0]
0x180053bdf  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180053be4  mov     rdi, rax
0x180053be7  test    rax, rax
0x180053bea  jnz     short loc_180053C26
0x180053bec  mov     ebx, 0D08100A1h
0x180053bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180053bf8  lea     rax, WPP_GLOBAL_Control
0x180053bff  cmp     rcx, rax
0x180053c02  jz      loc_180053CE8
0x180053c08  test    byte ptr [rcx+1Ch], 4
0x180053c0c  jz      loc_180053CE8
0x180053c12  cmp     byte ptr [rcx+19h], 2
0x180053c16  jb      loc_180053CE8
0x180053c1c  mov     edx, 0C8h
0x180053c21  jmp     loc_1800538E6
0x180053c26  lea     r12, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180053c2d  cmp     r14w, [rdi]
0x180053c31  jz      loc_180053CE8
0x180053c37  mov     rdx, rdi
0x180053c3a  mov     [rbp+57h+var_44], 80h
0x180053c42  lea     rcx, [rbp+57h+var_50]
0x180053c46  mov     [rbp+57h+var_38], r14
0x180053c4a  mov     [rbp+57h+var_3C], r14d
0x180053c4e  mov     [rbp+57h+var_30], 8000000h
0x180053c55  mov     [rbp+57h+var_50], r12
0x180053c59  mov     [rbp+57h+var_48], r14d
0x180053c5d  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x180053c62  mov     ebx, eax
0x180053c64  test    eax, eax
0x180053c66  js      short loc_180053CA8
0x180053c68  mov     r8d, 1; int
0x180053c6e  lea     rdx, [rbp+57h+var_78]; struct CPathString *
0x180053c72  lea     rcx, [rbp+57h+var_50]; this
0x180053c76  call    ?StartsWith@CPathString@@QEBAHAEBV1@H@Z; CPathString::StartsWith(CPathString const &,int)
0x180053c7b  test    eax, eax
0x180053c7d  jnz     short loc_180053CA0
0x180053c7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053c83  inc     rax
0x180053c86  cmp     [rdi+rax*2], r14w
0x180053c8b  jnz     short loc_180053C83
0x180053c8d  lea     rdi, [rdi+rax*2]
0x180053c91  add     rdi, 2
0x180053c95  lea     rcx, [rbp+57h+var_50]; this
0x180053c99  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180053c9e  jmp     short loc_180053C2D
0x180053ca0  mov     dword ptr [rsi], 1
0x180053ca6  jmp     short loc_180053CDF
  ... truncated ...
```
