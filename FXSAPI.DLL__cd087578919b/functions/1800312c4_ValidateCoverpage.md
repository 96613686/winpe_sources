# ValidateCoverpage

- ea: `0x1800312c4`
- end: `0x180031b14`
- name: `ValidateCoverpage`
- size: `2128`
- prototype: `__int64 __fastcall(unsigned __int16 *, wchar_t *String2, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18001ad28`
- `0x1800254e0`

## callees

- `0x180008374`
- `0x180008438`
- `0x18000abe4`
- `0x18000ac14`
- `0x180016124`
- `0x180021530`
- `0x1800308e0`
- `0x1800312c4`
- `0x180032688`
- `0x180032b8c`
- `0x18003d510`

## import_xrefs

- `msvcrt!wcschr` at `0x1800315e0`
- `msvcrt!wcschr` at `0x1800315e0`
- `msvcrt!_wsplitpath_s` at `0x18003146d`
- `msvcrt!_wsplitpath_s` at `0x18003146d`
- `msvcrt!_wcsicmp` at `0x18003152c`
- `msvcrt!_wcsicmp` at `0x180031594`
- `msvcrt!_wcsicmp` at `0x18003152c`
- `msvcrt!_wcsicmp` at `0x180031594`
- `KERNEL32!GetFileAttributesW` at `0x1800315f6`
- `KERNEL32!GetFileAttributesW` at `0x180031937`
- `KERNEL32!GetFileAttributesW` at `0x18003194f`
- `KERNEL32!GetFileAttributesW` at `0x1800315f6`
- `KERNEL32!GetFileAttributesW` at `0x180031937`
- `KERNEL32!GetFileAttributesW` at `0x18003194f`
- `KERNEL32!CloseHandle` at `0x180031aad`
- `KERNEL32!CloseHandle` at `0x180031aad`
- `KERNEL32!SetLastError` at `0x180031356`
- `KERNEL32!SetLastError` at `0x180031356`
- `KERNEL32!GetLastError` at `0x180031688`
- `KERNEL32!GetLastError` at `0x1800316c1`
- `KERNEL32!GetLastError` at `0x1800316ea`
- `KERNEL32!GetLastError` at `0x18003171f`
- `KERNEL32!GetLastError` at `0x180031743`
- `KERNEL32!GetLastError` at `0x180031770`
- `KERNEL32!GetLastError` at `0x180031a57`
- `KERNEL32!GetLastError` at `0x180031adc`
- `KERNEL32!GetLastError` at `0x180031688`
- `KERNEL32!GetLastError` at `0x1800316c1`
- `KERNEL32!GetLastError` at `0x1800316ea`
- `KERNEL32!GetLastError` at `0x18003171f`
- `KERNEL32!GetLastError` at `0x180031743`
- `KERNEL32!GetLastError` at `0x180031770`
- `KERNEL32!GetLastError` at `0x180031a57`
- `KERNEL32!GetLastError` at `0x180031adc`

## pseudocode

```c
__int64 __fastcall ValidateCoverpage(unsigned __int16 *a1, wchar_t *String2, int a3, unsigned __int16 *a4)
{
  _QWORD *v8; // r10
  DWORD LastError; // ebx
  unsigned int v10; // esi
  __int64 v12; // r14
  wchar_t *v13; // rax
  __int64 v14; // rcx
  unsigned __int16 *v15; // rdx
  __int64 v16; // rbx
  wchar_t *v17; // rcx
  wchar_t *v18; // r8
  __int64 v19; // rdx
  wchar_t *v20; // rax
  __int64 v21; // rcx
  wchar_t *v22; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  DWORD v25; // eax
  __int64 v26; // rdx
  int v27; // eax
  unsigned __int16 v28; // di
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rcx
  wchar_t *v33; // rdx
  __int64 v34; // rdi
  WCHAR *v35; // rax
  WCHAR *v36; // rcx
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  int v39; // eax
  WCHAR *v40; // rcx
  __int64 v41; // rdi
  wchar_t *v42; // rax
  wchar_t *v43; // rcx
  int v44; // eax
  void *File; // rax
  DWORD v46; // eax
  wchar_t FullPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Ext[256]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t String1[264]; // [rsp+670h] [rbp+570h] BYREF
  wchar_t Filename[256]; // [rsp+880h] [rbp+780h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
    goto LABEL_6;
  v12 = 2147483646;
  v13 = FullPath;
  v14 = 2147483646;
  v15 = a1;
  v16 = 260;
  v10 = 1;
  do
  {
    if ( !v14 )
      break;
    if ( !*v15 )
      break;
    *v13++ = *v15++;
    --v14;
    --v16;
  }
  while ( v16 );
  v17 = v13 - 1;
  if ( v16 )
    v17 = v13;
  *v17 = 0;
  if ( !v16 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_d(v8[2], 44, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 122);
    LastError = 122;
    goto LABEL_130;
  }
  LastError = 0;
  if ( a3 != 1 )
    goto LABEL_44;
  if ( _wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u) )
  {
    LastError = 1627;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 1627);
    }
  }
  v18 = Filename;
  v19 = 260;
  v20 = String1;
  v21 = 2147483646;
  do
  {
    if ( !v21 )
      break;
    if ( !*v18 )
      break;
    *v20++ = *v18++;
    --v21;
    --v19;
  }
  while ( v19 );
  v22 = v20 - 1;
  if ( v19 )
    v22 = v20;
  *v22 = 0;
  StringCchCatW(String1, 0x104u, Ext);
  if ( !_wcsicmp(String1, FullPath) )
  {
    if ( !_wcsicmp(Ext, L".lnk") )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_6;
      }
      v24 = 47;
      goto LABEL_38;
    }
LABEL_44:
    if ( wcschr(FullPath, 0x5Cu) )
    {
      if ( GetFileAttributesW(FullPath) == -1 )
      {
        LastError = 2;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
        goto LABEL_7;
      }
      goto LABEL_115;
    }
    if ( a3 )
    {
      if ( String2 && *String2 )
      {
        if ( !(unsigned int)GetServerCpDir(String2, FullPath) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = GetLastError();
            v26 = 50;
LABEL_68:
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v25);
          }
        }
      }
      else if ( !(unsigned int)GetServerCpDir(0, FullPath) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v25 = GetLastError();
          v26 = 49;
          goto LABEL_68;
        }
      }
    }
    else if ( !(unsigned int)GetClientCpDir(FullPath) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = GetLastError();
        v26 = 51;
        goto LABEL_68;
      }
    }
    if ( LastError )
    {
LABEL_70:
      LastError = 2;
      goto LABEL_7;
    }
    v27 = StringCchCatW(FullPath, 0x104u, L"\\");
    v28 = v27;
    if ( v27 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v30 = 52;
      goto LABEL_76;
    }
    v31 = StringCchCatW(FullPath, 0x104u, a1);
    v28 = v31;
    if ( v31 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v30 = 53;
      goto LABEL_76;
    }
    v32 = 2147483646;
    v33 = FullPath;
    v34 = 260;
    v35 = FileName;
    do
    {
      if ( !v32 )
        break;
      if ( !*v33 )
        break;
      *v35++ = *v33++;
      --v32;
      --v34;
    }
    while ( v34 );
    v36 = v35 - 1;
    if ( v34 )
      v36 = v35;
    *v36 = 0;
    if ( !v34 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_95;
      }
      v38 = 54;
LABEL_94:
      WPP_SF_d(v37[2], v38, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 122);
LABEL_95:
      LastError = 122;
      goto LABEL_130;
    }
    v39 = StringCchCatW(FileName, 0x104u, L".cov");
    v28 = v39;
    if ( v39 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v30 = 55;
      goto LABEL_76;
    }
    if ( GetFileAttributesW(FileName) == -1 )
    {
      if ( GetFileAttributesW(FullPath) == -1 )
        goto LABEL_70;
    }
    else
    {
      v40 = FileName;
      v41 = 260;
      v42 = FullPath;
      do
      {
        if ( !v12 )
          break;
        if ( !*v40 )
          break;
        *v42++ = *v40++;
        --v12;
        --v41;
      }
      while ( v41 );
      v43 = v42 - 1;
      if ( v41 )
        v43 = v42;
      *v43 = 0;
      if ( !v41 )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_95;
        }
        v38 = 56;
        goto LABEL_94;
      }
    }
LABEL_115:
    v44 = StringCchCopyW(a4, 0x104u, FullPath);
    v28 = v44;
    if ( v44 >= 0 )
    {
      File = (void *)InternalSafeCreateFile(a4, 0x80000000, 1u, 3u, 128);
      if ( File == (void *)-1LL )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
             && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v46 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v46);
      }
LABEL_130:
      if ( !LastError )
        return v10;
      goto LABEL_7;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_77:
      LastError = v28;
      goto LABEL_130;
    }
    v30 = 57;
LABEL_76:
    WPP_SF_d(v29[2], v30, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v28);
    goto LABEL_77;
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_6;
  }
  v24 = 46;
LABEL_38:
  WPP_SF_S(v23[2], v24, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, FullPath);
LABEL_6:
  LastError = 87;
LABEL_7:
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x1800312c4  mov     [rsp-8+arg_10], rbx
0x1800312c9  push    rbp
0x1800312ca  push    rsi
0x1800312cb  push    rdi
0x1800312cc  push    r12
0x1800312ce  push    r13
0x1800312d0  push    r14
0x1800312d2  push    r15
0x1800312d4  lea     rbp, [rsp-990h]
0x1800312dc  sub     rsp, 0A90h
0x1800312e3  mov     rax, cs:__security_cookie
0x1800312ea  xor     rax, rsp
0x1800312ed  mov     [rbp+9C0h+var_40], rax
0x1800312f4  mov     r13, r9
0x1800312f7  mov     r15d, r8d
0x1800312fa  mov     rdi, rdx
0x1800312fd  mov     r12, rcx
0x180031300  mov     r10, cs:WPP_GLOBAL_Control
0x180031307  lea     r11, WPP_GLOBAL_Control
0x18003130e  cmp     r10, r11
0x180031311  jz      short loc_180031344
0x180031313  test    byte ptr [r10+1Ch], 2
0x180031318  jz      short loc_180031344
0x18003131a  cmp     byte ptr [r10+19h], 5
0x18003131f  jb      short loc_180031344
0x180031321  mov     rcx, [r10+10h]
0x180031325  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x18003132c  mov     edx, 2Bh ; '+'
0x180031331  call    WPP_SF_
0x180031336  mov     r10, cs:WPP_GLOBAL_Control
0x18003133d  lea     r11, WPP_GLOBAL_Control
0x180031344  xor     r9d, r9d; Dir
0x180031347  test    r12, r12
0x18003134a  jnz     short loc_180031392
0x18003134c  mov     ebx, 57h ; 'W'
0x180031351  xor     r15d, r15d
0x180031354  mov     ecx, ebx; dwErrCode
0x180031356  call    cs:__imp_SetLastError
0x18003135d  nop     dword ptr [rax+rax+00h]
0x180031362  mov     esi, r15d
0x180031365  mov     eax, esi
0x180031367  mov     rcx, [rbp+9C0h+var_40]
0x18003136e  xor     rcx, rsp; StackCookie
0x180031371  call    __security_check_cookie
0x180031376  mov     rbx, [rsp+0AC0h+arg_10]
0x18003137e  add     rsp, 0A90h
0x180031385  pop     r15
0x180031387  pop     r14
0x180031389  pop     r13
0x18003138b  pop     r12
0x18003138d  pop     rdi
0x18003138e  pop     rsi
0x18003138f  pop     rbp
0x180031390  retn
0x180031392  mov     r14d, 7FFFFFFEh
0x180031398  lea     rax, [rsp+0AC0h+FullPath]
0x18003139d  mov     ecx, r14d
0x1800313a0  mov     rdx, r12
0x1800313a3  mov     ebx, 104h
0x1800313a8  mov     esi, 1
0x1800313ad  test    rcx, rcx
0x1800313b0  jz      short loc_1800313D0
0x1800313b2  movzx   r8d, word ptr [rdx]
0x1800313b6  test    r8w, r8w
0x1800313ba  jz      short loc_1800313D0
0x1800313bc  mov     [rax], r8w
0x1800313c0  add     rdx, 2
0x1800313c4  add     rax, 2
0x1800313c8  sub     rcx, rsi
0x1800313cb  sub     rbx, rsi
0x1800313ce  jnz     short loc_1800313AD
0x1800313d0  test    rbx, rbx
0x1800313d3  lea     rcx, [rax-2]
0x1800313d7  cmovnz  rcx, rax
0x1800313db  mov     [rcx], r9w
0x1800313df  jnz     short loc_18003142B
0x1800313e1  cmp     r10, r11
0x1800313e4  jz      short loc_180031419
0x1800313e6  test    byte ptr [r10+1Ch], 2
0x1800313eb  jz      short loc_180031419
0x1800313ed  cmp     byte ptr [r10+19h], 2
0x1800313f2  jb      short loc_180031419
0x1800313f4  mov     rcx, [r10+10h]
0x1800313f8  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x1800313ff  mov     rax, rbx
0x180031402  mov     edx, 2Ch ; ','
0x180031407  neg     rax
0x18003140a  sbb     r9d, r9d
0x18003140d  not     r9d
0x180031410  and     r9d, 7Ah
0x180031414  call    WPP_SF_d
0x180031419  neg     rbx
0x18003141c  sbb     ebx, ebx
0x18003141e  not     ebx
0x180031420  and     ebx, 7Ah
0x180031423  xor     r15d, r15d
0x180031426  jmp     loc_180031B07
0x18003142b  mov     ebx, r9d
0x18003142e  cmp     r15d, esi
0x180031431  jnz     loc_1800315D6
0x180031437  mov     ecx, 100h
0x18003143c  lea     rax, [rbp+9C0h+var_650]
0x180031443  mov     [rsp+0AC0h+ExtCount], rcx; ExtCount
0x180031448  xor     r8d, r8d; DriveCount
0x18003144b  mov     [rsp+0AC0h+Ext], rax; Ext
0x180031450  xor     edx, edx; Drive
0x180031452  mov     [rsp+0AC0h+FilenameCount], rcx; FilenameCount
0x180031457  lea     rax, [rbp+9C0h+var_240]
0x18003145e  mov     [rsp+0AC0h+Filename], rax; Filename
0x180031463  lea     rcx, [rsp+0AC0h+FullPath]; FullPath
0x180031468  mov     [rsp+0AC0h+DirCount], r9; DirCount
0x18003146d  call    cs:__imp__wsplitpath_s
0x180031474  nop     dword ptr [rax+rax+00h]
0x180031479  xor     r10d, r10d
0x18003147c  test    eax, eax
0x18003147e  jz      short loc_1800314BE
0x180031480  mov     ebx, 65Bh
0x180031485  mov     rcx, cs:WPP_GLOBAL_Control
0x18003148c  lea     rax, WPP_GLOBAL_Control
0x180031493  cmp     rcx, rax
0x180031496  jz      short loc_1800314BE
0x180031498  test    byte ptr [rcx+1Ch], 2
0x18003149c  jz      short loc_1800314BE
0x18003149e  cmp     byte ptr [rcx+19h], 2
0x1800314a2  jb      short loc_1800314BE
0x1800314a4  mov     rcx, [rcx+10h]
0x1800314a8  lea     edx, [r10+2Dh]
0x1800314ac  mov     r9d, ebx
0x1800314af  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x1800314b6  call    WPP_SF_d
0x1800314bb  xor     r10d, r10d
0x1800314be  mov     r11d, 104h
0x1800314c4  lea     r8, [rbp+9C0h+var_240]
0x1800314cb  mov     edx, r11d
0x1800314ce  lea     rax, [rbp+9C0h+String1]
0x1800314d5  mov     rcx, r14
0x1800314d8  test    rcx, rcx
0x1800314db  jz      short loc_1800314FB
0x1800314dd  movzx   r9d, word ptr [r8]
0x1800314e1  test    r9w, r9w
0x1800314e5  jz      short loc_1800314FB
0x1800314e7  mov     [rax], r9w
0x1800314eb  add     r8, 2
0x1800314ef  add     rax, 2
0x1800314f3  sub     rcx, rsi
0x1800314f6  sub     rdx, rsi
0x1800314f9  jnz     short loc_1800314D8
0x1800314fb  test    rdx, rdx
0x1800314fe  lea     rcx, [rax-2]
0x180031502  lea     r8, [rbp+9C0h+var_650]; unsigned __int16 *
0x180031509  mov     rdx, r11; unsigned __int64
0x18003150c  cmovnz  rcx, rax
0x180031510  mov     [rcx], r10w
0x180031514  lea     rcx, [rbp+9C0h+String1]; unsigned __int16 *
0x18003151b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031520  lea     rdx, [rsp+0AC0h+FullPath]; String2
0x180031525  lea     rcx, [rbp+9C0h+String1]; String1
0x18003152c  call    cs:__imp__wcsicmp
0x180031533  nop     dword ptr [rax+rax+00h]
0x180031538  test    eax, eax
0x18003153a  jz      short loc_180031586
0x18003153c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031543  lea     rax, WPP_GLOBAL_Control
0x18003154a  cmp     rcx, rax
0x18003154d  jz      loc_18003134C
0x180031553  test    byte ptr [rcx+1Ch], 2
0x180031557  jz      loc_18003134C
0x18003155d  cmp     byte ptr [rcx+19h], 2
0x180031561  jb      loc_18003134C
0x180031567  mov     edx, 2Eh ; '.'
0x18003156c  mov     rcx, [rcx+10h]
0x180031570  lea     r9, [rsp+0AC0h+FullPath]
0x180031575  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x18003157c  call    WPP_SF_S
0x180031581  jmp     loc_18003134C
0x180031586  lea     rdx, aLnk; ".lnk"
0x18003158d  lea     rcx, [rbp+9C0h+var_650]; String1
0x180031594  call    cs:__imp__wcsicmp
0x18003159b  nop     dword ptr [rax+rax+00h]
0x1800315a0  test    eax, eax
0x1800315a2  jnz     short loc_1800315D6
0x1800315a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800315ab  lea     rax, WPP_GLOBAL_Control
0x1800315b2  cmp     rcx, rax
0x1800315b5  jz      loc_18003134C
0x1800315bb  test    byte ptr [rcx+1Ch], 2
0x1800315bf  jz      loc_18003134C
0x1800315c5  cmp     byte ptr [rcx+19h], 2
0x1800315c9  jb      loc_18003134C
0x1800315cf  mov     edx, 2Fh ; '/'
0x1800315d4  jmp     short loc_18003156C
0x1800315d6  mov     edx, 5Ch ; '\'; Ch
0x1800315db  lea     rcx, [rsp+0AC0h+FullPath]; Str
0x1800315e0  call    cs:__imp_wcschr
0x1800315e7  nop     dword ptr [rax+rax+00h]
0x1800315ec  test    rax, rax
0x1800315ef  jz      short loc_18003165C
0x1800315f1  lea     rcx, [rsp+0AC0h+FullPath]; lpFileName
0x1800315f6  call    cs:__imp_GetFileAttributesW
0x1800315fd  nop     dword ptr [rax+rax+00h]
0x180031602  or      edi, 0FFFFFFFFh
0x180031605  cmp     eax, edi
0x180031607  jnz     loc_1800319DD
0x18003160d  mov     ebx, 2
0x180031612  mov     rcx, cs:WPP_GLOBAL_Control
0x180031619  lea     rax, WPP_GLOBAL_Control
0x180031620  cmp     rcx, rax
0x180031623  jz      loc_180031351
0x180031629  test    [rcx+1Ch], bl
0x18003162c  jz      loc_180031351
0x180031632  cmp     [rcx+19h], bl
0x180031635  jb      loc_180031351
0x18003163b  mov     rcx, [rcx+10h]
0x18003163f  lea     edx, [rbx+2Eh]
0x180031642  lea     r9, [rsp+0AC0h+FullPath]
0x180031647  mov     dword ptr [rsp+0AC0h+DirCount], ebx
0x18003164b  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x180031652  call    WPP_SF_Sd
0x180031657  jmp     loc_180031351
0x18003165c  test    r15d, r15d
0x18003165f  jz      loc_180031732
0x180031665  xor     r15d, r15d
0x180031668  test    rdi, rdi
0x18003166b  jz      short loc_1800316D6
0x18003166d  cmp     [rdi], r15w
0x180031671  jz      short loc_1800316D6
0x180031673  lea     rdx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x180031678  mov     rcx, rdi; String2
0x18003167b  call    GetServerCpDir
0x180031680  test    eax, eax
0x180031682  jnz     loc_18003179A
0x180031688  call    cs:__imp_GetLastError
0x18003168f  nop     dword ptr [rax+rax+00h]
0x180031694  mov     ebx, eax
0x180031696  mov     rax, cs:WPP_GLOBAL_Control
0x18003169d  lea     rcx, WPP_GLOBAL_Control
0x1800316a4  cmp     rax, rcx
0x1800316a7  jz      loc_18003179A
0x1800316ad  test    byte ptr [rax+1Ch], 2
0x1800316b1  jz      loc_18003179A
0x1800316b7  cmp     byte ptr [rax+19h], 2
0x1800316bb  jb      loc_18003179A
0x1800316c1  call    cs:__imp_GetLastError
0x1800316c8  nop     dword ptr [rax+rax+00h]
0x1800316cd  lea     edx, [r15+32h]
0x1800316d1  jmp     loc_180031780
0x1800316d6  lea     rdx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x1800316db  xor     ecx, ecx; String2
0x1800316dd  call    GetServerCpDir
0x1800316e2  test    eax, eax
0x1800316e4  jnz     loc_18003179A
0x1800316ea  call    cs:__imp_GetLastError
0x1800316f1  nop     dword ptr [rax+rax+00h]
0x1800316f6  mov     ebx, eax
0x1800316f8  mov     rax, cs:WPP_GLOBAL_Control
0x1800316ff  lea     rcx, WPP_GLOBAL_Control
0x180031706  cmp     rax, rcx
0x180031709  jz      loc_18003179A
0x18003170f  test    byte ptr [rax+1Ch], 2
0x180031713  jz      loc_18003179A
0x180031719  cmp     byte ptr [rax+19h], 2
0x18003171d  jb      short loc_18003179A
0x18003171f  call    cs:__imp_GetLastError
0x180031726  nop     dword ptr [rax+rax+00h]
0x18003172b  mov     edx, 31h ; '1'
0x180031730  jmp     short loc_180031780
0x180031732  lea     rcx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x180031737  call    GetClientCpDir
0x18003173c  xor     r15d, r15d
0x18003173f  test    eax, eax
0x180031741  jnz     short loc_18003179A
0x180031743  call    cs:__imp_GetLastError
0x18003174a  nop     dword ptr [rax+rax+00h]
0x18003174f  mov     ebx, eax
0x180031751  mov     rax, cs:WPP_GLOBAL_Control
0x180031758  lea     rcx, WPP_GLOBAL_Control
0x18003175f  cmp     rax, rcx
0x180031762  jz      short loc_18003179A
0x180031764  test    byte ptr [rax+1Ch], 2
0x180031768  jz      short loc_18003179A
0x18003176a  cmp     byte ptr [rax+19h], 2
0x18003176e  jb      short loc_18003179A
0x180031770  call    cs:__imp_GetLastError
0x180031777  nop     dword ptr [rax+rax+00h]
0x18003177c  lea     edx, [r15+33h]
0x180031780  mov     rcx, cs:WPP_GLOBAL_Control
0x180031787  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x18003178e  mov     r9d, eax
0x180031791  mov     rcx, [rcx+10h]
0x180031795  call    WPP_SF_d
0x18003179a  test    ebx, ebx
0x18003179c  jz      short loc_1800317A8
0x18003179e  mov     ebx, 2
0x1800317a3  jmp     loc_180031354
0x1800317a8  lea     r8, SubBlock; "\\"
0x1800317af  mov     edx, 104h; unsigned __int64
0x1800317b4  lea     rcx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x1800317b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800317be  mov     edi, eax
0x1800317c0  test    eax, eax
  ... truncated ...
```
