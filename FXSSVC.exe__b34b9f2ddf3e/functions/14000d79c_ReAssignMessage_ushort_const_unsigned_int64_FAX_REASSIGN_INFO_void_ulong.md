# ReAssignMessage(ushort const *,unsigned __int64,_FAX_REASSIGN_INFO *,void * *,ulong)

- ea: `0x14000d79c`
- end: `0x14000def7`
- name: `?ReAssignMessage@@YAKPEBG_KPEAU_FAX_REASSIGN_INFO@@PEAPEAXK@Z`
- size: `1883`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int64, unsigned __int16 **, void **, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x14000f700`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140005c6c`
- `0x140007610`
- `0x140008810`
- `0x14000d79c`
- `0x14004edf4`
- `0x1400556ec`
- `0x140065d14`
- `0x140065dbc`
- `0x140067168`
- `0x14006a3a4`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000d850`
- `KERNEL32!GetLastError` at `0x14000daf4`
- `KERNEL32!GetLastError` at `0x14000db5b`
- `KERNEL32!GetLastError` at `0x14000dcb5`
- `KERNEL32!GetLastError` at `0x14000dd13`
- `KERNEL32!GetLastError` at `0x14000ddce`
- `KERNEL32!GetLastError` at `0x14000d850`
- `KERNEL32!GetLastError` at `0x14000daf4`
- `KERNEL32!GetLastError` at `0x14000db5b`
- `KERNEL32!GetLastError` at `0x14000dcb5`
- `KERNEL32!GetLastError` at `0x14000dd13`
- `KERNEL32!GetLastError` at `0x14000ddce`
- `KERNEL32!CloseHandle` at `0x14000dabb`
- `KERNEL32!CloseHandle` at `0x14000dec2`
- `KERNEL32!CloseHandle` at `0x14000dabb`
- `KERNEL32!CloseHandle` at `0x14000dec2`
- `KERNEL32!DeleteFileW` at `0x14000dcfc`
- `KERNEL32!DeleteFileW` at `0x14000ddc4`
- `KERNEL32!DeleteFileW` at `0x14000dcfc`
- `KERNEL32!DeleteFileW` at `0x14000ddc4`
- `KERNEL32!CopyFileW` at `0x14000da65`
- `KERNEL32!CopyFileW` at `0x14000da65`
- `KERNEL32!Sleep` at `0x14000da90`
- `KERNEL32!Sleep` at `0x14000da90`
- `msvcrt!wcschr` at `0x14000d9db`
- `msvcrt!wcschr` at `0x14000d9db`

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
  unsigned __int16 *v40; // [rsp+20h] [rbp-E0h]
  __int64 hObject; // [rsp+40h] [rbp-C0h]
  unsigned int v42; // [rsp+48h] [rbp-B8h]
  void *lpMem; // [rsp+50h] [rbp-B0h]
  WCHAR NewFileName[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v47[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v48[264]; // [rsp+490h] [rbp+390h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  }
  if ( !a5 )
    return 87;
  hObject = InternalSafeCreateFile(lpFileName, 0x80000000, 1u, (__int64)a4, 3u, 0);
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
  ArchiveFolderPath = CFaxArchiving::GetArchiveFolderPath(v9, v8, 0, v48);
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
                                        v47,
                                        (unsigned int)v40);
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
          v40 = v47;
          v37 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", v48);
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
  v42 = 0;
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
    v25 = CFaxArchiving::GetFileNameFromSIDAndMessageID(v17, a4[v21], v24, v47, (unsigned int)v40);
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
    v40 = v47;
    v26 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", v48);
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
      v19 = v42;
      goto LABEL_57;
    }
    Sleep(1u);
    v21 = v42 + 1;
    v42 = v21;
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
      v19 = v42;
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
0x14000d79c  push    rbp
0x14000d79e  push    rbx
0x14000d79f  push    rsi
0x14000d7a0  push    rdi
0x14000d7a1  push    r12
0x14000d7a3  push    r13
0x14000d7a5  push    r14
0x14000d7a7  push    r15
0x14000d7a9  lea     rbp, [rsp-5B8h]
0x14000d7b1  sub     rsp, 6B8h
0x14000d7b8  mov     rax, cs:__security_cookie
0x14000d7bf  xor     rax, rsp
0x14000d7c2  mov     [rbp+5F0h+var_50], rax
0x14000d7c9  mov     [rsp+6F0h+var_698], r9
0x14000d7ce  mov     r12, r8
0x14000d7d1  mov     [rsp+6F0h+var_690], rdx
0x14000d7d6  mov     r14, rcx
0x14000d7d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d7e0  lea     rdi, WPP_GLOBAL_Control
0x14000d7e7  mov     r15b, 4
0x14000d7ea  cmp     rcx, rdi
0x14000d7ed  jz      short loc_14000D810
0x14000d7ef  test    [rcx+1Ch], r15b
0x14000d7f3  jz      short loc_14000D810
0x14000d7f5  cmp     byte ptr [rcx+19h], 5
0x14000d7f9  jb      short loc_14000D810
0x14000d7fb  mov     rcx, [rcx+10h]
0x14000d7ff  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d806  mov     edx, 7Dh ; '}'
0x14000d80b  call    WPP_SF_
0x14000d810  mov     r13d, [rbp+5F0h+arg_20]
0x14000d817  xor     esi, esi
0x14000d819  test    r13d, r13d
0x14000d81c  jnz     short loc_14000D826
0x14000d81e  lea     eax, [rsi+57h]
0x14000d821  jmp     loc_14000DED4
0x14000d826  mov     dword ptr [rsp+6F0h+var_6C8], esi; unsigned __int16 *
0x14000d82a  mov     edx, 80000000h; dwDesiredAccess
0x14000d82f  mov     r8d, 1; dwShareMode
0x14000d835  mov     [rsp+6F0h+var_6D0], 3; unsigned int
0x14000d83d  mov     rcx, r14; lpFileName
0x14000d840  call    InternalSafeCreateFile
0x14000d845  mov     [rsp+6F0h+hObject], rax
0x14000d84a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d84e  jnz     short loc_14000D89D
0x14000d850  call    cs:__imp_GetLastError
0x14000d856  mov     ebx, eax
0x14000d858  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d85f  cmp     rcx, rdi
0x14000d862  jz      loc_14000DED2
0x14000d868  test    [rcx+1Ch], r15b
0x14000d86c  jz      loc_14000DED2
0x14000d872  cmp     byte ptr [rcx+19h], 2
0x14000d876  jb      loc_14000DED2
0x14000d87c  mov     rcx, [rcx+10h]
0x14000d880  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d887  mov     edx, 7Eh ; '~'
0x14000d88c  mov     [rsp+6F0h+var_6D0], eax
0x14000d890  mov     r9, r14
0x14000d893  call    WPP_SF_Sd
0x14000d898  jmp     loc_14000DED2
0x14000d89d  lea     r9, [rbp+5F0h+var_260]; unsigned __int16 *
0x14000d8a4  mov     [rsp+6F0h+lpMem], rsi
0x14000d8a9  xor     r8d, r8d; int
0x14000d8ac  call    ?GetArchiveFolderPath@CFaxArchiving@@QEAAKPEAXHPEAGK1K@Z; CFaxArchiving::GetArchiveFolderPath(void *,int,ushort *,ulong,ushort *,ulong)
0x14000d8b1  mov     ebx, eax
0x14000d8b3  test    eax, eax
0x14000d8b5  jz      short loc_14000D8F8
0x14000d8b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8be  cmp     rcx, rdi
0x14000d8c1  jz      loc_14000DEBA
0x14000d8c7  test    [rcx+1Ch], r15b
0x14000d8cb  jz      loc_14000DEBA
0x14000d8d1  cmp     byte ptr [rcx+19h], 2
0x14000d8d5  jb      loc_14000DEBA
0x14000d8db  mov     edx, 7Fh
0x14000d8e0  mov     r9d, eax
0x14000d8e3  mov     rcx, [rcx+10h]
0x14000d8e7  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d8ee  call    WPP_SF_d
0x14000d8f3  jmp     loc_14000DEBA
0x14000d8f8  mov     ebx, 8
0x14000d8fd  mov     [rsp+6F0h+var_6A8], rsi
0x14000d902  mov     eax, ebx
0x14000d904  mul     r13
0x14000d907  mov     rdi, rax
0x14000d90a  test    rdx, rdx
0x14000d90d  jnz     loc_14000DE7B
0x14000d913  mov     rcx, rax; dwBytes
0x14000d916  call    pMemAlloc
0x14000d91b  mov     [rsp+6F0h+lpMem], rax
0x14000d920  mov     r15, rax
0x14000d923  test    rax, rax
0x14000d926  jnz     short loc_14000D95B
0x14000d928  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d92f  lea     rsi, WPP_GLOBAL_Control
0x14000d936  cmp     rcx, rsi
0x14000d939  jz      loc_14000DEBA
0x14000d93f  test    byte ptr [rcx+1Ch], 4
0x14000d943  jz      loc_14000DEBA
0x14000d949  cmp     byte ptr [rcx+19h], 2
0x14000d94d  jb      loc_14000DEBA
0x14000d953  mov     r9d, edi
0x14000d956  lea     edx, [rbx+79h]
0x14000d959  jmp     short loc_14000D8E3
0x14000d95b  mov     r8, rdi; Size
0x14000d95e  xor     edx, edx; Val
0x14000d960  mov     rcx, rax; void *
0x14000d963  call    memset_0
0x14000d968  mov     rcx, [r12]; unsigned __int16 *
0x14000d96c  call    StringDup
0x14000d971  mov     rsi, rax
0x14000d974  test    rax, rax
0x14000d977  jnz     short loc_14000D9C4
0x14000d979  xor     edi, edi
0x14000d97b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d982  lea     rsi, WPP_GLOBAL_Control
0x14000d989  cmp     rcx, rsi
0x14000d98c  jz      loc_14000DBAB
0x14000d992  test    byte ptr [rcx+1Ch], 4
0x14000d996  jz      loc_14000DBAB
0x14000d99c  cmp     byte ptr [rcx+19h], 2
0x14000d9a0  jb      loc_14000DBAB
0x14000d9a6  mov     r9, [r12]
0x14000d9aa  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d9b1  mov     rcx, [rcx+10h]
0x14000d9b5  mov     edx, 82h
0x14000d9ba  call    WPP_SF_S
0x14000d9bf  jmp     loc_14000DBAB
0x14000d9c4  xor     ebx, ebx
0x14000d9c6  mov     dword ptr [rsp+6F0h+var_6A8], ebx
0x14000d9ca  test    r13d, r13d
0x14000d9cd  jz      loc_14000DAB6
0x14000d9d3  mov     edx, 3Bh ; ';'; Ch
0x14000d9d8  mov     rcx, rsi; Str
0x14000d9db  call    cs:__imp_wcschr
0x14000d9e1  mov     rdi, rax
0x14000d9e4  test    rax, rax
0x14000d9e7  jz      short loc_14000D9EE
0x14000d9e9  xor     ecx, ecx
0x14000d9eb  mov     [rax], cx
0x14000d9ee  call    ?DWORDLONGFromCurrentSystemTime@@YA_KXZ; DWORDLONGFromCurrentSystemTime(void)
0x14000d9f3  mov     rcx, r15; this
0x14000d9f6  mov     [rcx+rbx*8], rax
0x14000d9fa  test    rax, rax
0x14000d9fd  jz      loc_14000DCB5
0x14000da03  mov     r8, rax; unsigned __int64
0x14000da06  lea     r9, [rbp+5F0h+var_470]; unsigned __int16 *
0x14000da0d  mov     rax, [rsp+6F0h+var_698]
0x14000da12  mov     rdx, [rax+rbx*8]; void *
0x14000da16  call    ?GetFileNameFromSIDAndMessageID@CFaxArchiving@@QEAAKPEAX_KPEAGK@Z; CFaxArchiving::GetFileNameFromSIDAndMessageID(void *,unsigned __int64,ushort *,ulong)
0x14000da1b  mov     ebx, eax
0x14000da1d  test    eax, eax
0x14000da1f  jnz     loc_14000DC80
0x14000da25  lea     rax, [rbp+5F0h+var_470]
0x14000da2c  mov     edx, 104h; unsigned __int64
0x14000da31  lea     r9, [rbp+5F0h+var_260]
0x14000da38  mov     qword ptr [rsp+6F0h+var_6D0], rax; unsigned int
0x14000da3d  lea     r8, aSS_0; "%s\\%s"
0x14000da44  lea     rcx, [rsp+6F0h+NewFileName]; unsigned __int16 *
0x14000da49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000da4e  mov     r9d, eax
0x14000da51  test    eax, eax
0x14000da53  js      loc_14000DC28
0x14000da59  lea     r8d, [rbx+1]; bFailIfExists
0x14000da5d  mov     rcx, r14; lpExistingFileName
0x14000da60  lea     rdx, [rsp+6F0h+NewFileName]; lpNewFileName
0x14000da65  call    cs:__imp_CopyFileW
0x14000da6b  test    eax, eax
0x14000da6d  jz      loc_14000DB5B
0x14000da73  mov     r8, rsi; unsigned __int16 *
0x14000da76  lea     rcx, [rsp+6F0h+NewFileName]; unsigned __int16 *
0x14000da7b  mov     rdx, r12; struct _FAX_REASSIGN_INFO *
0x14000da7e  call    ?AddReAssignNTFSStorageProperties@@YAKPEBGPEAU_FAX_REASSIGN_INFO@@0@Z; AddReAssignNTFSStorageProperties(ushort const *,_FAX_REASSIGN_INFO *,ushort const *)
0x14000da83  mov     ebx, eax
0x14000da85  test    eax, eax
0x14000da87  jnz     loc_14000DB1E
0x14000da8d  lea     ecx, [rax+1]; dwMilliseconds
0x14000da90  call    cs:__imp_Sleep
0x14000da96  mov     ebx, dword ptr [rsp+6F0h+var_6A8]
0x14000da9a  lea     rax, [rdi+2]
0x14000da9e  inc     ebx
0x14000daa0  neg     rdi
0x14000daa3  mov     dword ptr [rsp+6F0h+var_6A8], ebx
0x14000daa7  sbb     rsi, rsi
0x14000daaa  and     rsi, rax
0x14000daad  cmp     ebx, r13d
0x14000dab0  jb      loc_14000D9D3
0x14000dab6  mov     rcx, [rsp+6F0h+hObject]; hObject
0x14000dabb  call    cs:__imp_CloseHandle
0x14000dac1  test    eax, eax
0x14000dac3  jnz     loc_14000DCF2
0x14000dac9  mov     rax, cs:WPP_GLOBAL_Control
0x14000dad0  lea     rsi, WPP_GLOBAL_Control
0x14000dad7  cmp     rax, rsi
0x14000dada  jz      loc_14000DCF9
0x14000dae0  test    byte ptr [rax+1Ch], 4
0x14000dae4  jz      loc_14000DCF9
0x14000daea  cmp     byte ptr [rax+19h], 3
0x14000daee  jb      loc_14000DCF9
0x14000daf4  call    cs:__imp_GetLastError
0x14000dafa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db01  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000db08  mov     edx, 88h
0x14000db0d  mov     r9d, eax
0x14000db10  mov     rcx, [rcx+10h]
0x14000db14  call    WPP_SF_d
0x14000db19  jmp     loc_14000DCF9
0x14000db1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db25  lea     r14, WPP_GLOBAL_Control
0x14000db2c  cmp     rcx, r14
0x14000db2f  jz      short loc_14000DB55
0x14000db31  test    byte ptr [rcx+1Ch], 4
0x14000db35  jz      short loc_14000DB55
0x14000db37  cmp     byte ptr [rcx+19h], 2
0x14000db3b  jb      short loc_14000DB55
0x14000db3d  mov     edx, 87h
0x14000db42  mov     rcx, [rcx+10h]
0x14000db46  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000db4d  mov     r9d, eax
0x14000db50  call    WPP_SF_d
0x14000db55  mov     edi, dword ptr [rsp+6F0h+var_6A8]
0x14000db59  jmp     short loc_14000DBB2
0x14000db5b  call    cs:__imp_GetLastError
0x14000db61  mov     ebx, eax
0x14000db63  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db6a  lea     rsi, WPP_GLOBAL_Control
0x14000db71  cmp     rcx, rsi
0x14000db74  jz      short loc_14000DB9A
0x14000db76  test    byte ptr [rcx+1Ch], 4
0x14000db7a  jz      short loc_14000DB9A
0x14000db7c  cmp     byte ptr [rcx+19h], 2
0x14000db80  jb      short loc_14000DB9A
0x14000db82  mov     edx, 86h
0x14000db87  mov     rcx, [rcx+10h]
0x14000db8b  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000db92  mov     r9d, eax
0x14000db95  call    WPP_SF_d
0x14000db9a  mov     r12, [rsp+6F0h+hObject]
0x14000db9f  test    ebx, ebx
0x14000dba1  jz      loc_14000DE19
0x14000dba7  mov     edi, dword ptr [rsp+6F0h+var_6A8]
0x14000dbab  lea     r14, WPP_GLOBAL_Control
0x14000dbb2  mov     r12, [rsp+6F0h+var_698]
0x14000dbb7  lea     esi, [rdi-1]
0x14000dbba  cmp     edi, r13d
0x14000dbbd  cmovnz  esi, edi
0x14000dbc0  xor     edi, edi
0x14000dbc2  mov     r8, [r15+rdi*8]; unsigned __int64
0x14000dbc6  test    r8, r8
0x14000dbc9  jz      loc_14000DE0A
0x14000dbcf  mov     rdx, [r12+rdi*8]; void *
0x14000dbd3  lea     r9, [rbp+5F0h+var_470]; unsigned __int16 *
0x14000dbda  call    ?GetFileNameFromSIDAndMessageID@CFaxArchiving@@QEAAKPEAX_KPEAGK@Z; CFaxArchiving::GetFileNameFromSIDAndMessageID(void *,unsigned __int64,ushort *,ulong)
0x14000dbdf  test    eax, eax
0x14000dbe1  jz      loc_14000DD60
0x14000dbe7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dbee  cmp     rcx, r14
0x14000dbf1  jz      loc_14000DE0A
0x14000dbf7  test    byte ptr [rcx+1Ch], 4
0x14000dbfb  jz      loc_14000DE0A
0x14000dc01  cmp     byte ptr [rcx+19h], 3
0x14000dc05  jb      loc_14000DE0A
0x14000dc0b  mov     rcx, [rcx+10h]
0x14000dc0f  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000dc16  mov     edx, 8Bh
0x14000dc1b  mov     r9d, eax
0x14000dc1e  call    WPP_SF_d
0x14000dc23  jmp     loc_14000DE0A
0x14000dc28  and     eax, 1FFF0000h
0x14000dc2d  movzx   ebx, r9w
0x14000dc31  cmp     eax, 70000h
0x14000dc36  jz      short loc_14000DC3B
0x14000dc38  mov     ebx, r9d
0x14000dc3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc42  lea     rsi, WPP_GLOBAL_Control
0x14000dc49  cmp     rcx, rsi
0x14000dc4c  jz      loc_14000DB9A
0x14000dc52  test    byte ptr [rcx+1Ch], 4
0x14000dc56  jz      loc_14000DB9A
0x14000dc5c  cmp     byte ptr [rcx+19h], 2
0x14000dc60  jb      loc_14000DB9A
0x14000dc66  mov     rcx, [rcx+10h]
0x14000dc6a  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000dc71  mov     edx, 85h
0x14000dc76  call    WPP_SF_d
0x14000dc7b  jmp     loc_14000DB9A
0x14000dc80  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc87  lea     r14, WPP_GLOBAL_Control
0x14000dc8e  cmp     rcx, r14
0x14000dc91  jz      loc_14000DB55
0x14000dc97  test    byte ptr [rcx+1Ch], 4
0x14000dc9b  jz      loc_14000DB55
0x14000dca1  cmp     byte ptr [rcx+19h], 2
0x14000dca5  jb      loc_14000DB55
0x14000dcab  mov     edx, 84h
0x14000dcb0  jmp     loc_14000DB42
0x14000dcb5  call    cs:__imp_GetLastError
0x14000dcbb  mov     ebx, eax
0x14000dcbd  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
