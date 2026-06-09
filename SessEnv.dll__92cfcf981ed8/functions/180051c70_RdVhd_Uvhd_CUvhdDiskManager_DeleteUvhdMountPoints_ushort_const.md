# RdVhd::Uvhd::CUvhdDiskManager::DeleteUvhdMountPoints(ushort const *)

- ea: `0x180051c70`
- end: `0x18005201a`
- name: `?DeleteUvhdMountPoints@CUvhdDiskManager@Uvhd@RdVhd@@UEBAJPEBG@Z`
- size: `938`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdDiskManager *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x180050360`

## callees

- `0x180004db0`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x1800327c8`
- `0x18004876c`
- `0x1800488e4`
- `0x180048b28`
- `0x180051c70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f95`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x180051f8b`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x180051f8b`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180051d7c`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180051e06`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180051d7c`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180051e06`

## string_xrefs

- `0x180051ce1`: `szUvhdVolumeGuidPath`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::DeleteUvhdMountPoints(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2)
{
  signed int v3; // ebx
  int v4; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *Buffer; // rax
  DWORD v9; // r10d
  signed int LastError; // eax
  WCHAR *v11; // rax
  DWORD v12; // r10d
  signed int v13; // eax
  const WCHAR *v14; // rax
  const WCHAR *v15; // rsi
  WCHAR v16; // cx
  signed int v17; // eax
  __int64 v18; // rax
  const int *v20; // [rsp+30h] [rbp-30h] BYREF
  int v21; // [rsp+38h] [rbp-28h]
  __int64 v22; // [rsp+3Ch] [rbp-24h]
  int v23; // [rsp+44h] [rbp-1Ch]
  __int64 v24; // [rsp+48h] [rbp-18h]
  int v25; // [rsp+50h] [rbp-10h]
  DWORD cchReturnLength; // [rsp+88h] [rbp+28h] BYREF

  v22 = 128;
  v24 = 0;
  v20 = &CBaseStringT<unsigned short>::`vftable';
  v23 = 0;
  v21 = 0;
  cchReturnLength = 0;
  v25 = 0x8000000;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
        L"szUvhdVolumeGuidPath");
    }
    v3 = -2147024809;
    goto LABEL_65;
  }
  v4 = CBaseStringT<unsigned short>::EnsureSpace(&v20, 260);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v6 = 85;
LABEL_12:
    v7 = (unsigned int)v4;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v7);
    goto LABEL_65;
  }
  CBaseStringT<unsigned short>::GetBufferLength(&v20);
  Buffer = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v20);
  if ( !GetVolumePathNamesForVolumeNameW(a2, Buffer, v9, &cchReturnLength) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError == 234 )
    {
      v4 = CBaseStringT<unsigned short>::EnsureSpace(&v20, cchReturnLength);
      v3 = v4;
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_65;
        }
        v6 = 86;
        goto LABEL_12;
      }
      CBaseStringT<unsigned short>::GetBufferLength(&v20);
      v11 = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v20);
      if ( !GetVolumePathNamesForVolumeNameW(a2, v11, v12, &cchReturnLength) )
      {
        v13 = GetLastError();
        v3 = v13;
        if ( v13 && (v13 & 0xFFFF0000) == 0 )
        {
          if ( v13 > 0 )
            v3 = (unsigned __int16)v13 | 0x80070000;
          v3 = v3 & 0x8000FFFF | 0x504F0000;
        }
        if ( v3 < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_65;
          }
          v6 = 87;
LABEL_32:
          v7 = (unsigned int)v3;
          goto LABEL_13;
        }
      }
    }
    else
    {
      if ( LastError && (LastError & 0xFFFF0000) == 0 )
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v3 = v3 & 0x8000FFFF | 0x50500000;
      }
      if ( v3 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_65;
        }
        v6 = 88;
        goto LABEL_32;
      }
    }
  }
  v4 = CBaseStringT<unsigned short>::SetLength(&v20, cchReturnLength);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v6 = 89;
    goto LABEL_12;
  }
  v14 = (const WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v20);
  v15 = v14;
  if ( !v14 )
  {
    v3 = -796852063;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v6 = 90;
    goto LABEL_32;
  }
  v16 = *v14;
  if ( *v14 )
  {
    do
    {
      if ( v16 != 92 && !DeleteVolumeMountPointW(v15) )
      {
        v17 = GetLastError();
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            91,
            WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
            (unsigned int)v17,
            v17);
        }
      }
      v18 = -1;
      do
        ++v18;
      while ( v15[v18] );
      v15 += v18 + 1;
      v16 = *v15;
    }
    while ( *v15 );
  }
LABEL_65:
  CPathString::~CPathString((CPathString *)&v20);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180051c70  mov     [rsp-18h+arg_0], rbx
0x180051c75  mov     [rsp-18h+arg_10], rsi
0x180051c7a  push    rbp
0x180051c7b  push    rdi
0x180051c7c  push    r14
0x180051c7e  mov     rbp, rsp
0x180051c81  sub     rsp, 60h
0x180051c85  xor     r14d, r14d
0x180051c88  mov     [rbp+var_24], 80h
0x180051c90  lea     rax, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x180051c97  mov     [rbp+var_18], r14
0x180051c9b  mov     [rbp+var_30], rax
0x180051c9f  mov     rdi, rdx
0x180051ca2  mov     [rbp+var_1C], r14d
0x180051ca6  mov     [rbp+var_28], r14d
0x180051caa  mov     [rbp+cchReturnLength], r14d
0x180051cae  mov     [rbp+var_10], 8000000h
0x180051cb5  test    rdx, rdx
0x180051cb8  jnz     short loc_180051CFE
0x180051cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180051cc1  lea     rdi, WPP_GLOBAL_Control
0x180051cc8  cmp     rcx, rdi
0x180051ccb  jz      short loc_180051CF4
0x180051ccd  test    byte ptr [rcx+1Ch], 4
0x180051cd1  jz      short loc_180051CF4
0x180051cd3  cmp     byte ptr [rcx+19h], 2
0x180051cd7  jb      short loc_180051CF4
0x180051cd9  mov     rcx, [rcx+10h]
0x180051cdd  lea     edx, [r14+54h]
0x180051ce1  lea     r9, aSzuvhdvolumegu; "szUvhdVolumeGuidPath"
0x180051ce8  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180051cef  call    WPP_SF_S
0x180051cf4  mov     ebx, 80070057h
0x180051cf9  jmp     loc_180051FFA
0x180051cfe  mov     edx, 104h
0x180051d03  lea     rcx, [rbp+var_30]
0x180051d07  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180051d0c  mov     ebx, eax
0x180051d0e  test    eax, eax
0x180051d10  jns     short loc_180051D5A
0x180051d12  mov     rcx, cs:WPP_GLOBAL_Control
0x180051d19  lea     rdi, WPP_GLOBAL_Control
0x180051d20  cmp     rcx, rdi
0x180051d23  jz      loc_180051FFA
0x180051d29  test    byte ptr [rcx+1Ch], 4
0x180051d2d  jz      loc_180051FFA
0x180051d33  cmp     byte ptr [rcx+19h], 2
0x180051d37  jb      loc_180051FFA
0x180051d3d  mov     edx, 55h ; 'U'
0x180051d42  mov     r9d, eax
0x180051d45  mov     rcx, [rcx+10h]
0x180051d49  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180051d50  call    WPP_SF_d
0x180051d55  jmp     loc_180051FFA
0x180051d5a  lea     rcx, [rbp+var_30]
0x180051d5e  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180051d63  lea     rcx, [rbp+var_30]
0x180051d67  mov     r10d, eax
0x180051d6a  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180051d6f  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180051d73  mov     r8d, r10d; cchBufferLength
0x180051d76  mov     rdx, rax; lpszVolumePathNames
0x180051d79  mov     rcx, rdi; lpszVolumeName
0x180051d7c  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180051d82  test    eax, eax
0x180051d84  jnz     loc_180051EDA
0x180051d8a  call    cs:__imp_GetLastError
0x180051d90  mov     ebx, eax
0x180051d92  cmp     eax, 0EAh
0x180051d97  jnz     loc_180051E80
0x180051d9d  mov     edx, [rbp+cchReturnLength]
0x180051da0  lea     rcx, [rbp+var_30]
0x180051da4  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180051da9  mov     ebx, eax
0x180051dab  test    eax, eax
0x180051dad  jns     short loc_180051DE4
0x180051daf  mov     rcx, cs:WPP_GLOBAL_Control
0x180051db6  lea     rdi, WPP_GLOBAL_Control
0x180051dbd  cmp     rcx, rdi
0x180051dc0  jz      loc_180051FFA
0x180051dc6  test    byte ptr [rcx+1Ch], 4
0x180051dca  jz      loc_180051FFA
0x180051dd0  cmp     byte ptr [rcx+19h], 2
0x180051dd4  jb      loc_180051FFA
0x180051dda  mov     edx, 56h ; 'V'
0x180051ddf  jmp     loc_180051D42
0x180051de4  lea     rcx, [rbp+var_30]
0x180051de8  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180051ded  lea     rcx, [rbp+var_30]
0x180051df1  mov     r10d, eax
0x180051df4  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180051df9  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180051dfd  mov     r8d, r10d; cchBufferLength
0x180051e00  mov     rdx, rax; lpszVolumePathNames
0x180051e03  mov     rcx, rdi; lpszVolumeName
0x180051e06  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180051e0c  test    eax, eax
0x180051e0e  jnz     loc_180051EDA
0x180051e14  call    cs:__imp_GetLastError
0x180051e1a  mov     ebx, eax
0x180051e1c  test    eax, eax
0x180051e1e  jz      short loc_180051E40
0x180051e20  test    eax, 0FFFF0000h
0x180051e25  jnz     short loc_180051E40
0x180051e27  test    eax, eax
0x180051e29  jle     short loc_180051E34
0x180051e2b  movzx   ebx, ax
0x180051e2e  or      ebx, 80070000h
0x180051e34  and     ebx, 0D04FFFFFh
0x180051e3a  or      ebx, 504F0000h
0x180051e40  test    ebx, ebx
0x180051e42  jns     loc_180051EDA
0x180051e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e4f  lea     rdi, WPP_GLOBAL_Control
0x180051e56  cmp     rcx, rdi
0x180051e59  jz      loc_180051FFA
0x180051e5f  test    byte ptr [rcx+1Ch], 4
0x180051e63  jz      loc_180051FFA
0x180051e69  cmp     byte ptr [rcx+19h], 2
0x180051e6d  jb      loc_180051FFA
0x180051e73  mov     edx, 57h ; 'W'
0x180051e78  mov     r9d, ebx
0x180051e7b  jmp     loc_180051D45
0x180051e80  test    eax, eax
0x180051e82  jz      short loc_180051EA4
0x180051e84  test    eax, 0FFFF0000h
0x180051e89  jnz     short loc_180051EA4
0x180051e8b  test    eax, eax
0x180051e8d  jle     short loc_180051E98
0x180051e8f  movzx   ebx, ax
0x180051e92  or      ebx, 80070000h
0x180051e98  and     ebx, 0D050FFFFh
0x180051e9e  or      ebx, 50500000h
0x180051ea4  test    ebx, ebx
0x180051ea6  jns     short loc_180051EDA
0x180051ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180051eaf  lea     rdi, WPP_GLOBAL_Control
0x180051eb6  cmp     rcx, rdi
0x180051eb9  jz      loc_180051FFA
0x180051ebf  test    byte ptr [rcx+1Ch], 4
0x180051ec3  jz      loc_180051FFA
0x180051ec9  cmp     byte ptr [rcx+19h], 2
0x180051ecd  jb      loc_180051FFA
0x180051ed3  mov     edx, 58h ; 'X'
0x180051ed8  jmp     short loc_180051E78
0x180051eda  mov     edx, [rbp+cchReturnLength]
0x180051edd  lea     rcx, [rbp+var_30]
0x180051ee1  call    ?SetLength@?$CBaseStringT@G@@QEAAJK@Z; CBaseStringT<ushort>::SetLength(ulong)
0x180051ee6  mov     ebx, eax
0x180051ee8  test    eax, eax
0x180051eea  jns     short loc_180051F21
0x180051eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180051ef3  lea     rdi, WPP_GLOBAL_Control
0x180051efa  cmp     rcx, rdi
0x180051efd  jz      loc_180051FFA
0x180051f03  test    byte ptr [rcx+1Ch], 4
0x180051f07  jz      loc_180051FFA
0x180051f0d  cmp     byte ptr [rcx+19h], 2
0x180051f11  jb      loc_180051FFA
0x180051f17  mov     edx, 59h ; 'Y'
0x180051f1c  jmp     loc_180051D42
0x180051f21  lea     rcx, [rbp+var_30]
0x180051f25  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180051f2a  mov     rsi, rax
0x180051f2d  test    rax, rax
0x180051f30  jnz     short loc_180051F6A
0x180051f32  mov     ebx, 0D08100A1h
0x180051f37  mov     rcx, cs:WPP_GLOBAL_Control
0x180051f3e  lea     rdi, WPP_GLOBAL_Control
0x180051f45  cmp     rcx, rdi
0x180051f48  jz      loc_180051FFA
0x180051f4e  test    byte ptr [rcx+1Ch], 4
0x180051f52  jz      loc_180051FFA
0x180051f58  cmp     byte ptr [rcx+19h], 2
0x180051f5c  jb      loc_180051FFA
0x180051f62  lea     edx, [rax+5Ah]
0x180051f65  jmp     loc_180051E78
0x180051f6a  movzx   ecx, word ptr [rax]
0x180051f6d  cmp     r14w, cx
0x180051f71  jz      loc_180051FFA
0x180051f77  lea     rdi, WPP_GLOBAL_Control
0x180051f7e  mov     eax, 5Ch ; '\'
0x180051f83  cmp     ax, cx
0x180051f86  jz      short loc_180051FDB
0x180051f88  mov     rcx, rsi; lpszVolumeMountPoint
0x180051f8b  call    cs:__imp_DeleteVolumeMountPointW
0x180051f91  test    eax, eax
0x180051f93  jnz     short loc_180051FDB
0x180051f95  call    cs:__imp_GetLastError
0x180051f9b  test    eax, eax
0x180051f9d  jle     short loc_180051FA7
0x180051f9f  movzx   eax, ax
0x180051fa2  or      eax, 80070000h
0x180051fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180051fae  cmp     rcx, rdi
0x180051fb1  jz      short loc_180051FDB
0x180051fb3  test    byte ptr [rcx+1Ch], 4
0x180051fb7  jz      short loc_180051FDB
0x180051fb9  cmp     byte ptr [rcx+19h], 3
0x180051fbd  jb      short loc_180051FDB
0x180051fbf  mov     rcx, [rcx+10h]
0x180051fc3  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180051fca  mov     edx, 5Bh ; '['
0x180051fcf  mov     [rsp+60h+var_40], eax
0x180051fd3  mov     r9d, eax
0x180051fd6  call    WPP_SF_Dd
0x180051fdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051fdf  inc     rax
0x180051fe2  cmp     [rsi+rax*2], r14w
0x180051fe7  jnz     short loc_180051FDF
0x180051fe9  lea     rsi, [rsi+rax*2]
0x180051fed  add     rsi, 2
0x180051ff1  movzx   ecx, word ptr [rsi]
0x180051ff4  cmp     r14w, cx
0x180051ff8  jnz     short loc_180051F7E
0x180051ffa  lea     rcx, [rbp+var_30]; this
0x180051ffe  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180052003  lea     r11, [rsp+60h+var_s0]
0x180052008  mov     eax, ebx
0x18005200a  mov     rbx, [r11+20h]
0x18005200e  mov     rsi, [r11+30h]
0x180052012  mov     rsp, r11
0x180052015  pop     r14
0x180052017  pop     rdi
0x180052018  pop     rbp
0x180052019  retn
```
