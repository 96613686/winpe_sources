# ReAssignMessage(ushort const *,unsigned __int64,_FAX_REASSIGN_INFO *,void * *,ulong)

- ea: `0x14000de90`
- end: `0x14000e63a`
- name: `?ReAssignMessage@@YAKPEBG_KPEAU_FAX_REASSIGN_INFO@@PEAPEAXK@Z`
- size: `1962`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int64, unsigned __int16 **, void **, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x14000fee0`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x140005df8`
- `0x1400078ec`
- `0x140008bfc`
- `0x14000de90`
- `0x140052088`
- `0x140058c18`
- `0x1400698ec`
- `0x14006998c`
- `0x14006af2c`
- `0x14006e124`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000df44`
- `KERNEL32!GetLastError` at `0x14000e206`
- `KERNEL32!GetLastError` at `0x14000e273`
- `KERNEL32!GetLastError` at `0x14000e3d3`
- `KERNEL32!GetLastError` at `0x14000e43d`
- `KERNEL32!GetLastError` at `0x14000e504`
- `KERNEL32!GetLastError` at `0x14000df44`
- `KERNEL32!GetLastError` at `0x14000e206`
- `KERNEL32!GetLastError` at `0x14000e273`
- `KERNEL32!GetLastError` at `0x14000e3d3`
- `KERNEL32!GetLastError` at `0x14000e43d`
- `KERNEL32!GetLastError` at `0x14000e504`
- `KERNEL32!CloseHandle` at `0x14000e1c7`
- `KERNEL32!CloseHandle` at `0x14000e5fe`
- `KERNEL32!CloseHandle` at `0x14000e1c7`
- `KERNEL32!CloseHandle` at `0x14000e5fe`
- `KERNEL32!DeleteFileW` at `0x14000e420`
- `KERNEL32!DeleteFileW` at `0x14000e4f4`
- `KERNEL32!DeleteFileW` at `0x14000e420`
- `KERNEL32!DeleteFileW` at `0x14000e4f4`
- `KERNEL32!CopyFileW` at `0x14000e165`
- `KERNEL32!CopyFileW` at `0x14000e165`
- `KERNEL32!Sleep` at `0x14000e196`
- `KERNEL32!Sleep` at `0x14000e196`
- `msvcrt!wcschr` at `0x14000e0d5`
- `msvcrt!wcschr` at `0x14000e0d5`

## pseudocode

```c
__int64 __fastcall ReAssignMessage(
        LPCWSTR lpFileName,
        unsigned __int64 a2,
        unsigned __int16 **a3,
        void **a4,
        unsigned int a5)
{
  void *v8; // rdx
  CFaxArchiving *v9; // rcx
  DWORD LastError; // eax
  unsigned int v11; // ebx
  unsigned int ArchiveFolderPath; // eax
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  void *v16; // rax
  CFaxArchiving *v17; // r15
  const wchar_t *v18; // rsi
  unsigned int v19; // edi
  CMapDeviceId *v20; // rcx
  __int64 v21; // rbx
  wchar_t *v22; // rax
  wchar_t *v23; // rdi
  unsigned __int64 v24; // rax
  unsigned int v25; // eax
  int v26; // eax
  DWORD v27; // eax
  __int64 v28; // rdx
  DWORD v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r12
  unsigned int v32; // esi
  __int64 v33; // rdi
  unsigned __int64 v34; // r8
  unsigned int FileNameFromSIDAndMessageID; // eax
  DWORD v36; // eax
  int v37; // eax
  char v38; // al
  unsigned int EventsForReAssign; // eax
  unsigned int v40; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v41; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v42; // [rsp+28h] [rbp-D8h]
  unsigned int v43; // [rsp+30h] [rbp-D0h]
  __int64 hObject; // [rsp+40h] [rbp-C0h]
  unsigned int v45; // [rsp+48h] [rbp-B8h]
  void *lpMem; // [rsp+50h] [rbp-B0h]
  WCHAR NewFileName[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v50[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v51[264]; // [rsp+490h] [rbp+390h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  }
  if ( !a5 )
    return 87;
  hObject = InternalSafeCreateFile(lpFileName, 0x80000000, 1u, 3u, 0);
  if ( hObject == -1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
        (_DWORD)lpFileName,
        LastError);
    }
    return v11;
  }
  lpMem = 0;
  ArchiveFolderPath = CFaxArchiving::GetArchiveFolderPath(v9, v8, 0, v51, v40, v42, v43);
  v11 = ArchiveFolderPath;
  if ( ArchiveFolderPath )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_110;
    }
    v14 = 127;
    v15 = ArchiveFolderPath;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v15);
LABEL_110:
    v31 = hObject;
    goto LABEL_111;
  }
  v11 = 8;
  if ( !is_mul_ok(a5, 8u) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, 2147942934LL);
    }
    v11 = 534;
    goto LABEL_110;
  }
  v16 = (void *)pMemAlloc(8LL * a5);
  lpMem = v16;
  v17 = (CFaxArchiving *)v16;
  if ( !v16 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_110;
    }
    v15 = 8 * a5;
    v14 = 129;
    goto LABEL_17;
  }
  memset_0(v16, 0, 8LL * a5);
  v18 = (const wchar_t *)StringDup(*a3);
  if ( !v18 )
  {
    v19 = 0;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, *a3);
    }
LABEL_57:
    v32 = v19 - 1;
    if ( v19 != a5 )
      v32 = v19;
    v33 = 0;
    do
    {
      v34 = *((_QWORD *)v17 + v33);
      if ( v34 )
      {
        FileNameFromSIDAndMessageID = CFaxArchiving::GetFileNameFromSIDAndMessageID(
                                        v20,
                                        a4[v33],
                                        v34,
                                        v50,
                                        (unsigned int)v41);
        if ( FileNameFromSIDAndMessageID )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              139,
              &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
              FileNameFromSIDAndMessageID);
          }
        }
        else
        {
          v41 = v50;
          v37 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", v51);
          if ( v37 >= 0 )
          {
            if ( !DeleteFileW(NewFileName) )
            {
              v38 = GetLastError();
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  141,
                  (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
                  (unsigned int)NewFileName,
                  v38);
              }
            }
          }
          else
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                140,
                &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
                (unsigned int)v37);
            }
          }
        }
      }
      v33 = (unsigned int)(v33 + 1);
    }
    while ( (unsigned int)v33 <= v32 );
    v31 = hObject;
    goto LABEL_97;
  }
  v21 = 0;
  v45 = 0;
  do
  {
    v22 = wcschr(v18, 0x3Bu);
    v23 = v22;
    if ( v22 )
      *v22 = 0;
    v24 = DWORDLONGFromCurrentSystemTime();
    *((_QWORD *)v17 + v21) = v24;
    if ( !v24 )
    {
      v29 = GetLastError();
      v11 = v29;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = 131;
LABEL_53:
        WPP_SF_d(*((_QWORD *)v20 + 2), v30, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v29);
      }
LABEL_54:
      v31 = hObject;
      goto LABEL_55;
    }
    v25 = CFaxArchiving::GetFileNameFromSIDAndMessageID(v17, a4[v21], v24, v50, (unsigned int)v41);
    v11 = v25;
    if ( v25 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_48;
      }
      v28 = 132;
      goto LABEL_47;
    }
    v41 = v50;
    v26 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", v51);
    if ( v26 < 0 )
    {
      v11 = (unsigned __int16)v26;
      if ( (v26 & 0x1FFF0000) != 0x70000 )
        v11 = v26;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          133,
          &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
          (unsigned int)v26);
      }
      goto LABEL_54;
    }
    if ( !CopyFileW(lpFileName, NewFileName, v11 + 1) )
    {
      v29 = GetLastError();
      v11 = v29;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = 134;
        goto LABEL_53;
      }
      goto LABEL_54;
    }
    v25 = AddReAssignNTFSStorageProperties(NewFileName, (struct _FAX_REASSIGN_INFO *)a3, v18);
    v11 = v25;
    if ( v25 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_48;
      }
      v28 = 135;
LABEL_47:
      WPP_SF_d(*((_QWORD *)v20 + 2), v28, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v25);
LABEL_48:
      v19 = v45;
      goto LABEL_57;
    }
    Sleep(1u);
    v21 = v45 + 1;
    v45 = v21;
    v18 = (const wchar_t *)((unsigned __int64)(v23 + 1) & ((unsigned __int128)-(__int128)(unsigned __int64)v23 >> 64));
  }
  while ( (unsigned int)v21 < a5 );
  if ( !CloseHandle((HANDLE)hObject)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v27 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v27);
  }
  if ( DeleteFileW(lpFileName) )
  {
    EventsForReAssign = CreateEventsForReAssign(a2, (unsigned __int64 *)v17, a4, a5);
    v11 = EventsForReAssign;
    if ( EventsForReAssign )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          138,
          &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
          EventsForReAssign);
      }
      v11 = 0;
    }
  }
  else
  {
    v31 = -1;
    hObject = -1;
    v36 = GetLastError();
    v11 = v36;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
        (_DWORD)lpFileName,
        v36);
    }
LABEL_55:
    if ( v11 )
    {
      v19 = v45;
      goto LABEL_57;
    }
LABEL_97:
    if ( v31 != -1 )
LABEL_111:
      CloseHandle((HANDLE)v31);
  }
  pMemFree(lpMem);
  return v11;
}

```

## disassembly

```asm
0x14000de90  push    rbp
0x14000de92  push    rbx
0x14000de93  push    rsi
0x14000de94  push    rdi
0x14000de95  push    r12
0x14000de97  push    r13
0x14000de99  push    r14
0x14000de9b  push    r15
0x14000de9d  lea     rbp, [rsp-5B8h]
0x14000dea5  sub     rsp, 6B8h
0x14000deac  mov     rax, cs:__security_cookie
0x14000deb3  xor     rax, rsp
0x14000deb6  mov     [rbp+5F0h+var_50], rax
0x14000debd  mov     [rsp+6F0h+var_698], r9
0x14000dec2  mov     r12, r8
0x14000dec5  mov     [rsp+6F0h+var_690], rdx
0x14000deca  mov     r14, rcx
0x14000decd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ded4  lea     rdi, WPP_GLOBAL_Control
0x14000dedb  mov     r15b, 4
0x14000dede  cmp     rcx, rdi
0x14000dee1  jz      short loc_14000DF04
0x14000dee3  test    [rcx+1Ch], r15b
0x14000dee7  jz      short loc_14000DF04
0x14000dee9  cmp     byte ptr [rcx+19h], 5
0x14000deed  jb      short loc_14000DF04
0x14000deef  mov     rcx, [rcx+10h]
0x14000def3  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000defa  mov     edx, 7Dh ; '}'
0x14000deff  call    WPP_SF_
0x14000df04  mov     r13d, [rbp+5F0h+arg_20]
0x14000df0b  xor     esi, esi
0x14000df0d  test    r13d, r13d
0x14000df10  jnz     short loc_14000DF1A
0x14000df12  lea     eax, [rsi+57h]
0x14000df15  jmp     loc_14000E616
0x14000df1a  mov     dword ptr [rsp+6F0h+var_6C8], esi; unsigned __int16 *
0x14000df1e  mov     edx, 80000000h; dwDesiredAccess
0x14000df23  mov     r8d, 1; dwShareMode
0x14000df29  mov     [rsp+6F0h+var_6D0], 3; unsigned int
0x14000df31  mov     rcx, r14; lpFileName
0x14000df34  call    InternalSafeCreateFile
0x14000df39  mov     [rsp+6F0h+hObject], rax
0x14000df3e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000df42  jnz     short loc_14000DF97
0x14000df44  call    cs:__imp_GetLastError
0x14000df4b  nop     dword ptr [rax+rax+00h]
0x14000df50  mov     ebx, eax
0x14000df52  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df59  cmp     rcx, rdi
0x14000df5c  jz      loc_14000E614
0x14000df62  test    [rcx+1Ch], r15b
0x14000df66  jz      loc_14000E614
0x14000df6c  cmp     byte ptr [rcx+19h], 2
0x14000df70  jb      loc_14000E614
0x14000df76  mov     rcx, [rcx+10h]
0x14000df7a  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000df81  mov     edx, 7Eh ; '~'
0x14000df86  mov     [rsp+6F0h+var_6D0], eax
0x14000df8a  mov     r9, r14
0x14000df8d  call    WPP_SF_Sd
0x14000df92  jmp     loc_14000E614
0x14000df97  lea     r9, [rbp+5F0h+var_260]; unsigned __int16 *
0x14000df9e  mov     [rsp+6F0h+lpMem], rsi
0x14000dfa3  xor     r8d, r8d; int
0x14000dfa6  call    ?GetArchiveFolderPath@CFaxArchiving@@QEAAKPEAXHPEAGK1K@Z; CFaxArchiving::GetArchiveFolderPath(void *,int,ushort *,ulong,ushort *,ulong)
0x14000dfab  mov     ebx, eax
0x14000dfad  test    eax, eax
0x14000dfaf  jz      short loc_14000DFF2
0x14000dfb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfb8  cmp     rcx, rdi
0x14000dfbb  jz      loc_14000E5F6
0x14000dfc1  test    [rcx+1Ch], r15b
0x14000dfc5  jz      loc_14000E5F6
0x14000dfcb  cmp     byte ptr [rcx+19h], 2
0x14000dfcf  jb      loc_14000E5F6
0x14000dfd5  mov     edx, 7Fh
0x14000dfda  mov     r9d, eax
0x14000dfdd  mov     rcx, [rcx+10h]
0x14000dfe1  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000dfe8  call    WPP_SF_d
0x14000dfed  jmp     loc_14000E5F6
0x14000dff2  mov     ebx, 8
0x14000dff7  mov     [rsp+6F0h+var_6A8], rsi
0x14000dffc  mov     eax, ebx
0x14000dffe  mul     r13
0x14000e001  mov     rdi, rax
0x14000e004  test    rdx, rdx
0x14000e007  jnz     loc_14000E5B7
0x14000e00d  mov     rcx, rax; dwBytes
0x14000e010  call    pMemAlloc
0x14000e015  mov     [rsp+6F0h+lpMem], rax
0x14000e01a  mov     r15, rax
0x14000e01d  test    rax, rax
0x14000e020  jnz     short loc_14000E055
0x14000e022  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e029  lea     rsi, WPP_GLOBAL_Control
0x14000e030  cmp     rcx, rsi
0x14000e033  jz      loc_14000E5F6
0x14000e039  test    byte ptr [rcx+1Ch], 4
0x14000e03d  jz      loc_14000E5F6
0x14000e043  cmp     byte ptr [rcx+19h], 2
0x14000e047  jb      loc_14000E5F6
0x14000e04d  mov     r9d, edi
0x14000e050  lea     edx, [rbx+79h]
0x14000e053  jmp     short loc_14000DFDD
0x14000e055  mov     r8, rdi; Size
0x14000e058  xor     edx, edx; Val
0x14000e05a  mov     rcx, rax; void *
0x14000e05d  call    memset_0
0x14000e062  mov     rcx, [r12]; unsigned __int16 *
0x14000e066  call    StringDup
0x14000e06b  mov     rsi, rax
0x14000e06e  test    rax, rax
0x14000e071  jnz     short loc_14000E0BE
0x14000e073  xor     edi, edi
0x14000e075  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e07c  lea     rsi, WPP_GLOBAL_Control
0x14000e083  cmp     rcx, rsi
0x14000e086  jz      loc_14000E2C9
0x14000e08c  test    byte ptr [rcx+1Ch], 4
0x14000e090  jz      loc_14000E2C9
0x14000e096  cmp     byte ptr [rcx+19h], 2
0x14000e09a  jb      loc_14000E2C9
0x14000e0a0  mov     r9, [r12]
0x14000e0a4  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000e0ab  mov     rcx, [rcx+10h]
0x14000e0af  mov     edx, 82h
0x14000e0b4  call    WPP_SF_S
0x14000e0b9  jmp     loc_14000E2C9
0x14000e0be  xor     ebx, ebx
0x14000e0c0  mov     dword ptr [rsp+6F0h+var_6A8], ebx
0x14000e0c4  test    r13d, r13d
0x14000e0c7  jz      loc_14000E1C2
0x14000e0cd  mov     edx, 3Bh ; ';'; Ch
0x14000e0d2  mov     rcx, rsi; Str
0x14000e0d5  call    cs:__imp_wcschr
0x14000e0dc  nop     dword ptr [rax+rax+00h]
0x14000e0e1  mov     rdi, rax
0x14000e0e4  test    rax, rax
0x14000e0e7  jz      short loc_14000E0EE
0x14000e0e9  xor     ecx, ecx
0x14000e0eb  mov     [rax], cx
0x14000e0ee  call    ?DWORDLONGFromCurrentSystemTime@@YA_KXZ; DWORDLONGFromCurrentSystemTime(void)
0x14000e0f3  mov     rcx, r15; this
0x14000e0f6  mov     [rcx+rbx*8], rax
0x14000e0fa  test    rax, rax
0x14000e0fd  jz      loc_14000E3D3
0x14000e103  mov     r8, rax; unsigned __int64
0x14000e106  lea     r9, [rbp+5F0h+var_470]; unsigned __int16 *
0x14000e10d  mov     rax, [rsp+6F0h+var_698]
0x14000e112  mov     rdx, [rax+rbx*8]; void *
0x14000e116  call    ?GetFileNameFromSIDAndMessageID@CFaxArchiving@@QEAAKPEAX_KPEAGK@Z; CFaxArchiving::GetFileNameFromSIDAndMessageID(void *,unsigned __int64,ushort *,ulong)
0x14000e11b  mov     ebx, eax
0x14000e11d  test    eax, eax
0x14000e11f  jnz     loc_14000E39E
0x14000e125  lea     rax, [rbp+5F0h+var_470]
0x14000e12c  mov     edx, 104h; unsigned __int64
0x14000e131  lea     r9, [rbp+5F0h+var_260]
0x14000e138  mov     qword ptr [rsp+6F0h+var_6D0], rax; unsigned int
0x14000e13d  lea     r8, aSS_0; "%s\\%s"
0x14000e144  lea     rcx, [rsp+6F0h+NewFileName]; unsigned __int16 *
0x14000e149  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e14e  mov     r9d, eax
0x14000e151  test    eax, eax
0x14000e153  js      loc_14000E346
0x14000e159  lea     r8d, [rbx+1]; bFailIfExists
0x14000e15d  mov     rcx, r14; lpExistingFileName
0x14000e160  lea     rdx, [rsp+6F0h+NewFileName]; lpNewFileName
0x14000e165  call    cs:__imp_CopyFileW
0x14000e16c  nop     dword ptr [rax+rax+00h]
0x14000e171  test    eax, eax
0x14000e173  jz      loc_14000E273
0x14000e179  mov     r8, rsi; unsigned __int16 *
0x14000e17c  lea     rcx, [rsp+6F0h+NewFileName]; unsigned __int16 *
0x14000e181  mov     rdx, r12; struct _FAX_REASSIGN_INFO *
0x14000e184  call    ?AddReAssignNTFSStorageProperties@@YAKPEBGPEAU_FAX_REASSIGN_INFO@@0@Z; AddReAssignNTFSStorageProperties(ushort const *,_FAX_REASSIGN_INFO *,ushort const *)
0x14000e189  mov     ebx, eax
0x14000e18b  test    eax, eax
0x14000e18d  jnz     loc_14000E236
0x14000e193  lea     ecx, [rax+1]; dwMilliseconds
0x14000e196  call    cs:__imp_Sleep
0x14000e19d  nop     dword ptr [rax+rax+00h]
0x14000e1a2  mov     ebx, dword ptr [rsp+6F0h+var_6A8]
0x14000e1a6  lea     rax, [rdi+2]
0x14000e1aa  inc     ebx
0x14000e1ac  neg     rdi
0x14000e1af  mov     dword ptr [rsp+6F0h+var_6A8], ebx
0x14000e1b3  sbb     rsi, rsi
0x14000e1b6  and     rsi, rax
0x14000e1b9  cmp     ebx, r13d
0x14000e1bc  jb      loc_14000E0CD
0x14000e1c2  mov     rcx, [rsp+6F0h+hObject]; hObject
0x14000e1c7  call    cs:__imp_CloseHandle
0x14000e1ce  nop     dword ptr [rax+rax+00h]
0x14000e1d3  test    eax, eax
0x14000e1d5  jnz     loc_14000E416
0x14000e1db  mov     rax, cs:WPP_GLOBAL_Control
0x14000e1e2  lea     rsi, WPP_GLOBAL_Control
0x14000e1e9  cmp     rax, rsi
0x14000e1ec  jz      loc_14000E41D
0x14000e1f2  test    byte ptr [rax+1Ch], 4
0x14000e1f6  jz      loc_14000E41D
0x14000e1fc  cmp     byte ptr [rax+19h], 3
0x14000e200  jb      loc_14000E41D
0x14000e206  call    cs:__imp_GetLastError
0x14000e20d  nop     dword ptr [rax+rax+00h]
0x14000e212  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e219  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000e220  mov     edx, 88h
0x14000e225  mov     r9d, eax
0x14000e228  mov     rcx, [rcx+10h]
0x14000e22c  call    WPP_SF_d
0x14000e231  jmp     loc_14000E41D
0x14000e236  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e23d  lea     r14, WPP_GLOBAL_Control
0x14000e244  cmp     rcx, r14
0x14000e247  jz      short loc_14000E26D
0x14000e249  test    byte ptr [rcx+1Ch], 4
0x14000e24d  jz      short loc_14000E26D
0x14000e24f  cmp     byte ptr [rcx+19h], 2
0x14000e253  jb      short loc_14000E26D
0x14000e255  mov     edx, 87h
0x14000e25a  mov     rcx, [rcx+10h]
0x14000e25e  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000e265  mov     r9d, eax
0x14000e268  call    WPP_SF_d
0x14000e26d  mov     edi, dword ptr [rsp+6F0h+var_6A8]
0x14000e271  jmp     short loc_14000E2D0
0x14000e273  call    cs:__imp_GetLastError
0x14000e27a  nop     dword ptr [rax+rax+00h]
0x14000e27f  mov     ebx, eax
0x14000e281  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e288  lea     rsi, WPP_GLOBAL_Control
0x14000e28f  cmp     rcx, rsi
0x14000e292  jz      short loc_14000E2B8
0x14000e294  test    byte ptr [rcx+1Ch], 4
0x14000e298  jz      short loc_14000E2B8
0x14000e29a  cmp     byte ptr [rcx+19h], 2
0x14000e29e  jb      short loc_14000E2B8
0x14000e2a0  mov     edx, 86h
0x14000e2a5  mov     rcx, [rcx+10h]
0x14000e2a9  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000e2b0  mov     r9d, eax
0x14000e2b3  call    WPP_SF_d
0x14000e2b8  mov     r12, [rsp+6F0h+hObject]
0x14000e2bd  test    ebx, ebx
0x14000e2bf  jz      loc_14000E555
0x14000e2c5  mov     edi, dword ptr [rsp+6F0h+var_6A8]
0x14000e2c9  lea     r14, WPP_GLOBAL_Control
0x14000e2d0  mov     r12, [rsp+6F0h+var_698]
0x14000e2d5  lea     esi, [rdi-1]
0x14000e2d8  cmp     edi, r13d
0x14000e2db  cmovnz  esi, edi
0x14000e2de  xor     edi, edi
0x14000e2e0  mov     r8, [r15+rdi*8]; unsigned __int64
0x14000e2e4  test    r8, r8
0x14000e2e7  jz      loc_14000E546
0x14000e2ed  mov     rdx, [r12+rdi*8]; void *
0x14000e2f1  lea     r9, [rbp+5F0h+var_470]; unsigned __int16 *
0x14000e2f8  call    ?GetFileNameFromSIDAndMessageID@CFaxArchiving@@QEAAKPEAX_KPEAGK@Z; CFaxArchiving::GetFileNameFromSIDAndMessageID(void *,unsigned __int64,ushort *,ulong)
0x14000e2fd  test    eax, eax
0x14000e2ff  jz      loc_14000E490
0x14000e305  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e30c  cmp     rcx, r14
0x14000e30f  jz      loc_14000E546
0x14000e315  test    byte ptr [rcx+1Ch], 4
0x14000e319  jz      loc_14000E546
0x14000e31f  cmp     byte ptr [rcx+19h], 3
0x14000e323  jb      loc_14000E546
0x14000e329  mov     rcx, [rcx+10h]
0x14000e32d  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000e334  mov     edx, 8Bh
0x14000e339  mov     r9d, eax
0x14000e33c  call    WPP_SF_d
0x14000e341  jmp     loc_14000E546
0x14000e346  and     eax, 1FFF0000h
0x14000e34b  movzx   ebx, r9w
0x14000e34f  cmp     eax, 70000h
0x14000e354  jz      short loc_14000E359
0x14000e356  mov     ebx, r9d
0x14000e359  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e360  lea     rsi, WPP_GLOBAL_Control
0x14000e367  cmp     rcx, rsi
0x14000e36a  jz      loc_14000E2B8
0x14000e370  test    byte ptr [rcx+1Ch], 4
0x14000e374  jz      loc_14000E2B8
0x14000e37a  cmp     byte ptr [rcx+19h], 2
0x14000e37e  jb      loc_14000E2B8
0x14000e384  mov     rcx, [rcx+10h]
0x14000e388  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000e38f  mov     edx, 85h
0x14000e394  call    WPP_SF_d
0x14000e399  jmp     loc_14000E2B8
0x14000e39e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e3a5  lea     r14, WPP_GLOBAL_Control
0x14000e3ac  cmp     rcx, r14
0x14000e3af  jz      loc_14000E26D
0x14000e3b5  test    byte ptr [rcx+1Ch], 4
0x14000e3b9  jz      loc_14000E26D
  ... truncated ...
```
