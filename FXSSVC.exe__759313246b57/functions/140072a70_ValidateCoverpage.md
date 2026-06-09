# ValidateCoverpage

- ea: `0x140072a70`
- end: `0x140073229`
- name: `ValidateCoverpage`
- size: `1977`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14002f530`

## callees

- `0x140004b70`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x14000cae8`
- `0x14006e124`
- `0x140072a70`
- `0x140078b10`
- `0x14007900c`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140072ddc`
- `KERNEL32!GetLastError` at `0x140072e0d`
- `KERNEL32!GetLastError` at `0x140072e2e`
- `KERNEL32!GetLastError` at `0x140072e5b`
- `KERNEL32!GetLastError` at `0x140073138`
- `KERNEL32!GetLastError` at `0x1400731bd`
- `KERNEL32!GetLastError` at `0x140072ddc`
- `KERNEL32!GetLastError` at `0x140072e0d`
- `KERNEL32!GetLastError` at `0x140072e2e`
- `KERNEL32!GetLastError` at `0x140072e5b`
- `KERNEL32!GetLastError` at `0x140073138`
- `KERNEL32!GetLastError` at `0x1400731bd`
- `KERNEL32!SetLastError` at `0x1400731ee`
- `KERNEL32!SetLastError` at `0x1400731ee`
- `KERNEL32!CloseHandle` at `0x14007318e`
- `KERNEL32!CloseHandle` at `0x14007318e`
- `KERNEL32!GetFileAttributesW` at `0x140072d5d`
- `KERNEL32!GetFileAttributesW` at `0x14007301a`
- `KERNEL32!GetFileAttributesW` at `0x140073032`
- `KERNEL32!GetFileAttributesW` at `0x140072d5d`
- `KERNEL32!GetFileAttributesW` at `0x14007301a`
- `KERNEL32!GetFileAttributesW` at `0x140073032`
- `msvcrt!wcschr` at `0x140072d47`
- `msvcrt!wcschr` at `0x140072d47`
- `msvcrt!_wcsicmp` at `0x140072c93`
- `msvcrt!_wcsicmp` at `0x140072cfb`
- `msvcrt!_wcsicmp` at `0x140072c93`
- `msvcrt!_wcsicmp` at `0x140072cfb`
- `msvcrt!_wsplitpath_s` at `0x140072bd6`
- `msvcrt!_wsplitpath_s` at `0x140072bd6`

## pseudocode

```c
__int64 __fastcall ValidateCoverpage(unsigned __int16 *a1, __int64 a2, int a3, unsigned __int16 *a4)
{
  CMapDeviceId *v7; // r10
  DWORD LastError; // ebx
  __int64 v9; // r14
  wchar_t *v10; // rax
  __int64 v11; // rcx
  unsigned __int16 *v12; // rdx
  __int64 v13; // rbx
  unsigned int v14; // esi
  wchar_t *v15; // rcx
  wchar_t *v16; // r8
  __int64 v17; // rdx
  wchar_t *v18; // rax
  __int64 v19; // rcx
  wchar_t *v20; // rcx
  CMapDeviceId *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rdx
  int v26; // eax
  unsigned __int16 v27; // di
  CMapDeviceId *v28; // rcx
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rcx
  wchar_t *v32; // rdx
  __int64 v33; // rdi
  WCHAR *v34; // rax
  WCHAR *v35; // rcx
  CMapDeviceId *v36; // rcx
  __int64 v37; // rdx
  int v38; // eax
  WCHAR *v39; // rcx
  __int64 v40; // rdi
  wchar_t *v41; // rax
  wchar_t *v42; // rcx
  int v43; // eax
  void *File; // rax
  DWORD v45; // eax
  wchar_t FullPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Ext[256]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t String1[264]; // [rsp+670h] [rbp+570h] BYREF
  wchar_t Filename[256]; // [rsp+880h] [rbp+780h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
    goto LABEL_6;
  v9 = 2147483646;
  v10 = FullPath;
  v11 = 2147483646;
  v12 = a1;
  v13 = 260;
  v14 = 1;
  do
  {
    if ( !v11 )
      break;
    if ( !*v12 )
      break;
    *v10++ = *v12++;
    --v11;
    --v13;
  }
  while ( v13 );
  v15 = v10 - 1;
  if ( v13 )
    v15 = v10;
  *v15 = 0;
  if ( !v13 )
  {
    if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v7 + 2), 44, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 122);
    goto LABEL_18;
  }
  LastError = 0;
  if ( a3 == 1 )
  {
    if ( _wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u) )
    {
      LastError = 1627;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 1627);
      }
    }
    v16 = Filename;
    v17 = 260;
    v18 = String1;
    v19 = 2147483646;
    do
    {
      if ( !v19 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v19;
      --v17;
    }
    while ( v17 );
    v20 = v18 - 1;
    if ( v17 )
      v20 = v18;
    *v20 = 0;
    StringCchCatW(String1, 0x104u, Ext);
    if ( _wcsicmp(String1, FullPath) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_6;
      }
      v22 = 46;
LABEL_36:
      WPP_SF_S(*((_QWORD *)v21 + 2), v22, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, FullPath);
LABEL_6:
      LastError = 87;
LABEL_122:
      SetLastError(LastError);
      return 0;
    }
    if ( !_wcsicmp(Ext, L".lnk") )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_6;
      }
      v22 = 47;
      goto LABEL_36;
    }
  }
  if ( !wcschr(FullPath, 0x5Cu) )
  {
    if ( a3 )
    {
      if ( !(unsigned int)GetServerCpDir(v23, FullPath) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v24 = GetLastError();
          v25 = 49;
LABEL_59:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v24);
        }
      }
    }
    else if ( !(unsigned int)GetClientCpDir(FullPath) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = GetLastError();
        v25 = 51;
        goto LABEL_59;
      }
    }
    if ( LastError )
      goto LABEL_61;
    v26 = StringCchCatW(FullPath, 0x104u, L"\\");
    v27 = v26;
    if ( v26 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_68;
      }
      v29 = 52;
      goto LABEL_67;
    }
    v30 = StringCchCatW(FullPath, 0x104u, a1);
    v27 = v30;
    if ( v30 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_68;
      }
      v29 = 53;
      goto LABEL_67;
    }
    v31 = 2147483646;
    v32 = FullPath;
    v33 = 260;
    v34 = FileName;
    do
    {
      if ( !v31 )
        break;
      if ( !*v32 )
        break;
      *v34++ = *v32++;
      --v31;
      --v33;
    }
    while ( v33 );
    v35 = v34 - 1;
    if ( v33 )
      v35 = v34;
    *v35 = 0;
    if ( v33 )
    {
      v38 = StringCchCatW(FileName, 0x104u, L".cov");
      v27 = v38;
      if ( v38 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v29 = 55;
        goto LABEL_67;
      }
      if ( GetFileAttributesW(FileName) == -1 )
      {
        if ( GetFileAttributesW(FullPath) != -1 )
          goto LABEL_106;
LABEL_61:
        LastError = 2;
        goto LABEL_122;
      }
      v39 = FileName;
      v40 = 260;
      v41 = FullPath;
      do
      {
        if ( !v9 )
          break;
        if ( !*v39 )
          break;
        *v41++ = *v39++;
        --v9;
        --v40;
      }
      while ( v40 );
      v42 = v41 - 1;
      if ( v40 )
        v42 = v41;
      *v42 = 0;
      if ( v40 )
        goto LABEL_106;
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_18:
        LastError = 122;
        goto LABEL_121;
      }
      v37 = 56;
    }
    else
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      v37 = 54;
    }
    WPP_SF_d(*((_QWORD *)v36 + 2), v37, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 122);
    goto LABEL_18;
  }
  if ( GetFileAttributesW(FullPath) == -1 )
  {
    LastError = 2;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
        (unsigned int)FullPath,
        2);
    }
    goto LABEL_122;
  }
LABEL_106:
  v43 = StringCchCopyW(a4, 0x104u, FullPath);
  v27 = v43;
  if ( v43 < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v29 = 57;
LABEL_67:
    WPP_SF_d(*((_QWORD *)v28 + 2), v29, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v27);
LABEL_68:
    LastError = v27;
    goto LABEL_121;
  }
  File = (void *)InternalSafeCreateFile(a4, 0x80000000, 1u, 3u, 128);
  if ( File == (void *)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
        (_DWORD)a4,
        LastError);
    }
  }
  else if ( !CloseHandle(File)
         && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v45 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v45);
  }
LABEL_121:
  if ( LastError )
    goto LABEL_122;
  return v14;
}

```

## disassembly

```asm
0x140072a70  mov     [rsp-8+arg_8], rbx
0x140072a75  push    rbp
0x140072a76  push    rsi
0x140072a77  push    rdi
0x140072a78  push    r12
0x140072a7a  push    r13
0x140072a7c  push    r14
0x140072a7e  push    r15
0x140072a80  lea     rbp, [rsp-990h]
0x140072a88  sub     rsp, 0A90h
0x140072a8f  mov     rax, cs:__security_cookie
0x140072a96  xor     rax, rsp
0x140072a99  mov     [rbp+9C0h+var_40], rax
0x140072aa0  mov     r12, r9
0x140072aa3  mov     edi, r8d
0x140072aa6  mov     r15, rcx
0x140072aa9  mov     r10, cs:WPP_GLOBAL_Control
0x140072ab0  lea     r11, WPP_GLOBAL_Control
0x140072ab7  mov     r13d, 2
0x140072abd  cmp     r10, r11
0x140072ac0  jz      short loc_140072AF1
0x140072ac2  test    [r10+1Ch], r13b
0x140072ac6  jz      short loc_140072AF1
0x140072ac8  cmp     byte ptr [r10+19h], 5
0x140072acd  jb      short loc_140072AF1
0x140072acf  mov     rcx, [r10+10h]
0x140072ad3  lea     edx, [r13+29h]
0x140072ad7  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140072ade  call    WPP_SF_
0x140072ae3  mov     r10, cs:WPP_GLOBAL_Control
0x140072aea  lea     r11, WPP_GLOBAL_Control
0x140072af1  xor     r9d, r9d; Dir
0x140072af4  test    r15, r15
0x140072af7  jnz     short loc_140072B03
0x140072af9  mov     ebx, 57h ; 'W'
0x140072afe  jmp     loc_1400731EC
0x140072b03  mov     r14d, 7FFFFFFEh
0x140072b09  lea     rax, [rsp+0AC0h+FullPath]
0x140072b0e  mov     ecx, r14d
0x140072b11  mov     rdx, r15
0x140072b14  mov     ebx, 104h
0x140072b19  mov     esi, 1
0x140072b1e  test    rcx, rcx
0x140072b21  jz      short loc_140072B3F
0x140072b23  movzx   r8d, word ptr [rdx]
0x140072b27  test    r8w, r8w
0x140072b2b  jz      short loc_140072B3F
0x140072b2d  mov     [rax], r8w
0x140072b31  add     rdx, r13
0x140072b34  add     rax, r13
0x140072b37  sub     rcx, rsi
0x140072b3a  sub     rbx, rsi
0x140072b3d  jnz     short loc_140072B1E
0x140072b3f  test    rbx, rbx
0x140072b42  lea     rcx, [rax-2]
0x140072b46  cmovnz  rcx, rax
0x140072b4a  mov     [rcx], r9w
0x140072b4e  jnz     short loc_140072B95
0x140072b50  cmp     r10, r11
0x140072b53  jz      short loc_140072B86
0x140072b55  test    [r10+1Ch], r13b
0x140072b59  jz      short loc_140072B86
0x140072b5b  cmp     [r10+19h], r13b
0x140072b5f  jb      short loc_140072B86
0x140072b61  mov     rcx, [r10+10h]
0x140072b65  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140072b6c  mov     rax, rbx
0x140072b6f  mov     edx, 2Ch ; ','
0x140072b74  neg     rax
0x140072b77  sbb     r9d, r9d
0x140072b7a  not     r9d
0x140072b7d  and     r9d, 7Ah
0x140072b81  call    WPP_SF_d
0x140072b86  neg     rbx
0x140072b89  sbb     ebx, ebx
0x140072b8b  not     ebx
0x140072b8d  and     ebx, 7Ah
0x140072b90  jmp     loc_1400731E8
0x140072b95  mov     ebx, r9d
0x140072b98  cmp     edi, esi
0x140072b9a  jnz     loc_140072D3D
0x140072ba0  mov     ecx, 100h
0x140072ba5  lea     rax, [rbp+9C0h+var_650]
0x140072bac  mov     [rsp+0AC0h+ExtCount], rcx; ExtCount
0x140072bb1  xor     r8d, r8d; DriveCount
0x140072bb4  mov     [rsp+0AC0h+Ext], rax; Ext
0x140072bb9  xor     edx, edx; Drive
0x140072bbb  mov     [rsp+0AC0h+FilenameCount], rcx; FilenameCount
0x140072bc0  lea     rax, [rbp+9C0h+var_240]
0x140072bc7  mov     [rsp+0AC0h+Filename], rax; Filename
0x140072bcc  lea     rcx, [rsp+0AC0h+FullPath]; FullPath
0x140072bd1  mov     [rsp+0AC0h+DirCount], r9; DirCount
0x140072bd6  call    cs:__imp__wsplitpath_s
0x140072bdd  nop     dword ptr [rax+rax+00h]
0x140072be2  xor     r10d, r10d
0x140072be5  test    eax, eax
0x140072be7  jz      short loc_140072C27
0x140072be9  mov     ebx, 65Bh
0x140072bee  mov     rcx, cs:WPP_GLOBAL_Control
0x140072bf5  lea     rax, WPP_GLOBAL_Control
0x140072bfc  cmp     rcx, rax
0x140072bff  jz      short loc_140072C27
0x140072c01  test    [rcx+1Ch], r13b
0x140072c05  jz      short loc_140072C27
0x140072c07  cmp     [rcx+19h], r13b
0x140072c0b  jb      short loc_140072C27
0x140072c0d  mov     rcx, [rcx+10h]
0x140072c11  lea     edx, [r10+2Dh]
0x140072c15  mov     r9d, ebx
0x140072c18  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140072c1f  call    WPP_SF_d
0x140072c24  xor     r10d, r10d
0x140072c27  mov     r11d, 104h
0x140072c2d  lea     r8, [rbp+9C0h+var_240]
0x140072c34  mov     edx, r11d
0x140072c37  lea     rax, [rbp+9C0h+String1]
0x140072c3e  mov     rcx, r14
0x140072c41  test    rcx, rcx
0x140072c44  jz      short loc_140072C62
0x140072c46  movzx   r9d, word ptr [r8]
0x140072c4a  test    r9w, r9w
0x140072c4e  jz      short loc_140072C62
0x140072c50  mov     [rax], r9w
0x140072c54  add     r8, r13
0x140072c57  add     rax, r13
0x140072c5a  sub     rcx, rsi
0x140072c5d  sub     rdx, rsi
0x140072c60  jnz     short loc_140072C41
0x140072c62  test    rdx, rdx
0x140072c65  lea     rcx, [rax-2]
0x140072c69  lea     r8, [rbp+9C0h+var_650]; unsigned __int16 *
0x140072c70  mov     rdx, r11; unsigned __int64
0x140072c73  cmovnz  rcx, rax
0x140072c77  mov     [rcx], r10w
0x140072c7b  lea     rcx, [rbp+9C0h+String1]; unsigned __int16 *
0x140072c82  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140072c87  lea     rdx, [rsp+0AC0h+FullPath]; String2
0x140072c8c  lea     rcx, [rbp+9C0h+String1]; String1
0x140072c93  call    cs:__imp__wcsicmp
0x140072c9a  nop     dword ptr [rax+rax+00h]
0x140072c9f  test    eax, eax
0x140072ca1  jz      short loc_140072CED
0x140072ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x140072caa  lea     rax, WPP_GLOBAL_Control
0x140072cb1  cmp     rcx, rax
0x140072cb4  jz      loc_140072AF9
0x140072cba  test    [rcx+1Ch], r13b
0x140072cbe  jz      loc_140072AF9
0x140072cc4  cmp     [rcx+19h], r13b
0x140072cc8  jb      loc_140072AF9
0x140072cce  mov     edx, 2Eh ; '.'
0x140072cd3  mov     rcx, [rcx+10h]
0x140072cd7  lea     r9, [rsp+0AC0h+FullPath]
0x140072cdc  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140072ce3  call    WPP_SF_S
0x140072ce8  jmp     loc_140072AF9
0x140072ced  lea     rdx, aLnk; ".lnk"
0x140072cf4  lea     rcx, [rbp+9C0h+var_650]; String1
0x140072cfb  call    cs:__imp__wcsicmp
0x140072d02  nop     dword ptr [rax+rax+00h]
0x140072d07  test    eax, eax
0x140072d09  jnz     short loc_140072D3D
0x140072d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140072d12  lea     rax, WPP_GLOBAL_Control
0x140072d19  cmp     rcx, rax
0x140072d1c  jz      loc_140072AF9
0x140072d22  test    [rcx+1Ch], r13b
0x140072d26  jz      loc_140072AF9
0x140072d2c  cmp     [rcx+19h], r13b
0x140072d30  jb      loc_140072AF9
0x140072d36  mov     edx, 2Fh ; '/'
0x140072d3b  jmp     short loc_140072CD3
0x140072d3d  mov     edx, 5Ch ; '\'; Ch
0x140072d42  lea     rcx, [rsp+0AC0h+FullPath]; Str
0x140072d47  call    cs:__imp_wcschr
0x140072d4e  nop     dword ptr [rax+rax+00h]
0x140072d53  test    rax, rax
0x140072d56  jz      short loc_140072DC6
0x140072d58  lea     rcx, [rsp+0AC0h+FullPath]; lpFileName
0x140072d5d  call    cs:__imp_GetFileAttributesW
0x140072d64  nop     dword ptr [rax+rax+00h]
0x140072d69  or      edi, 0FFFFFFFFh
0x140072d6c  cmp     eax, edi
0x140072d6e  jnz     loc_1400730C1
0x140072d74  mov     ebx, r13d
0x140072d77  mov     rcx, cs:WPP_GLOBAL_Control
0x140072d7e  lea     rax, WPP_GLOBAL_Control
0x140072d85  cmp     rcx, rax
0x140072d88  jz      loc_1400731EC
0x140072d8e  test    [rcx+1Ch], r13b
0x140072d92  jz      loc_1400731EC
0x140072d98  cmp     [rcx+19h], r13b
0x140072d9c  jb      loc_1400731EC
0x140072da2  mov     rcx, [rcx+10h]
0x140072da6  lea     r9, [rsp+0AC0h+FullPath]
0x140072dab  mov     edx, 30h ; '0'
0x140072db0  mov     dword ptr [rsp+0AC0h+DirCount], r13d
0x140072db5  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140072dbc  call    WPP_SF_Sd
0x140072dc1  jmp     loc_1400731EC
0x140072dc6  test    edi, edi
0x140072dc8  jz      short loc_140072E20
0x140072dca  lea     rdx, [rsp+0AC0h+FullPath]
0x140072dcf  call    GetServerCpDir
0x140072dd4  test    eax, eax
0x140072dd6  jnz     loc_140072E86
0x140072ddc  call    cs:__imp_GetLastError
0x140072de3  nop     dword ptr [rax+rax+00h]
0x140072de8  mov     ebx, eax
0x140072dea  mov     rax, cs:WPP_GLOBAL_Control
0x140072df1  lea     rcx, WPP_GLOBAL_Control
0x140072df8  cmp     rax, rcx
0x140072dfb  jz      loc_140072E86
0x140072e01  test    [rax+1Ch], r13b
0x140072e05  jz      short loc_140072E86
0x140072e07  cmp     [rax+19h], r13b
0x140072e0b  jb      short loc_140072E86
0x140072e0d  call    cs:__imp_GetLastError
0x140072e14  nop     dword ptr [rax+rax+00h]
0x140072e19  mov     edx, 31h ; '1'
0x140072e1e  jmp     short loc_140072E6C
0x140072e20  lea     rcx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x140072e25  call    GetClientCpDir
0x140072e2a  test    eax, eax
0x140072e2c  jnz     short loc_140072E86
0x140072e2e  call    cs:__imp_GetLastError
0x140072e35  nop     dword ptr [rax+rax+00h]
0x140072e3a  mov     ebx, eax
0x140072e3c  mov     rax, cs:WPP_GLOBAL_Control
0x140072e43  lea     rcx, WPP_GLOBAL_Control
0x140072e4a  cmp     rax, rcx
0x140072e4d  jz      short loc_140072E86
0x140072e4f  test    [rax+1Ch], r13b
0x140072e53  jz      short loc_140072E86
0x140072e55  cmp     [rax+19h], r13b
0x140072e59  jb      short loc_140072E86
0x140072e5b  call    cs:__imp_GetLastError
0x140072e62  nop     dword ptr [rax+rax+00h]
0x140072e67  mov     edx, 33h ; '3'
0x140072e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140072e73  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140072e7a  mov     r9d, eax
0x140072e7d  mov     rcx, [rcx+10h]
0x140072e81  call    WPP_SF_d
0x140072e86  test    ebx, ebx
0x140072e88  jz      short loc_140072E92
0x140072e8a  mov     ebx, r13d
0x140072e8d  jmp     loc_1400731EC
0x140072e92  lea     r8, SubBlock; "\\"
0x140072e99  mov     edx, 104h; unsigned __int64
0x140072e9e  lea     rcx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x140072ea3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140072ea8  mov     edi, eax
0x140072eaa  test    eax, eax
0x140072eac  jns     short loc_140072EEE
0x140072eae  mov     rcx, cs:WPP_GLOBAL_Control
0x140072eb5  lea     rax, WPP_GLOBAL_Control
0x140072ebc  cmp     rcx, rax
0x140072ebf  jz      short loc_140072EE6
0x140072ec1  test    [rcx+1Ch], r13b
0x140072ec5  jz      short loc_140072EE6
0x140072ec7  cmp     [rcx+19h], r13b
0x140072ecb  jb      short loc_140072EE6
0x140072ecd  mov     edx, 34h ; '4'
0x140072ed2  mov     rcx, [rcx+10h]
0x140072ed6  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140072edd  movzx   r9d, di
0x140072ee1  call    WPP_SF_d
0x140072ee6  movzx   ebx, di
0x140072ee9  jmp     loc_1400731E8
0x140072eee  mov     r8, r15; unsigned __int16 *
0x140072ef1  lea     rcx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x140072ef6  mov     r15d, 104h
0x140072efc  mov     edx, r15d; unsigned __int64
0x140072eff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140072f04  xor     r9d, r9d
0x140072f07  mov     edi, eax
0x140072f09  test    eax, eax
0x140072f0b  jns     short loc_140072F32
0x140072f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140072f14  lea     rax, WPP_GLOBAL_Control
0x140072f1b  cmp     rcx, rax
0x140072f1e  jz      short loc_140072EE6
0x140072f20  test    [rcx+1Ch], r13b
0x140072f24  jz      short loc_140072EE6
0x140072f26  cmp     [rcx+19h], r13b
0x140072f2a  jb      short loc_140072EE6
0x140072f2c  lea     edx, [r9+35h]
0x140072f30  jmp     short loc_140072ED2
0x140072f32  mov     rcx, r14
0x140072f35  lea     rdx, [rsp+0AC0h+FullPath]
0x140072f3a  mov     rdi, r15
0x140072f3d  lea     rax, [rbp+9C0h+FileName]
0x140072f44  test    rcx, rcx
0x140072f47  jz      short loc_140072F65
0x140072f49  movzx   r8d, word ptr [rdx]
0x140072f4d  test    r8w, r8w
0x140072f51  jz      short loc_140072F65
0x140072f53  mov     [rax], r8w
0x140072f57  add     rdx, r13
  ... truncated ...
```
