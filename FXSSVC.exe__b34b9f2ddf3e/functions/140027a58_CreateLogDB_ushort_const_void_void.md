# CreateLogDB(ushort const *,void * *,void * *)

- ea: `0x140027a58`
- end: `0x140027f78`
- name: `?CreateLogDB@@YAKPEBGPEAPEAX1@Z`
- size: `1312`
- prototype: `__int64 __fastcall(unsigned __int16 *, void **, void **)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001e140`
- `0x14002af68`

## callees

- `0x140001b8c`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140027a58`
- `0x140027f80`
- `0x14002ab88`
- `0x14002b058`
- `0x140065df8`
- `0x14006a3a4`
- `0x14006e160`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140027c15`
- `KERNEL32!GetLastError` at `0x140027c66`
- `KERNEL32!GetLastError` at `0x140027cb5`
- `KERNEL32!GetLastError` at `0x140027e8f`
- `KERNEL32!GetLastError` at `0x140027f0b`
- `KERNEL32!GetLastError` at `0x140027c15`
- `KERNEL32!GetLastError` at `0x140027c66`
- `KERNEL32!GetLastError` at `0x140027cb5`
- `KERNEL32!GetLastError` at `0x140027e8f`
- `KERNEL32!GetLastError` at `0x140027f0b`
- `KERNEL32!CloseHandle` at `0x140027bf3`
- `KERNEL32!CloseHandle` at `0x140027c44`
- `KERNEL32!CloseHandle` at `0x140027c93`
- `KERNEL32!CloseHandle` at `0x140027bf3`
- `KERNEL32!CloseHandle` at `0x140027c44`
- `KERNEL32!CloseHandle` at `0x140027c93`
- `KERNEL32!WriteFile` at `0x140027efd`
- `KERNEL32!WriteFile` at `0x140027efd`

## pseudocode

```c
__int64 __fastcall CreateLogDB(unsigned __int16 *a1, void **a2, void **a3)
{
  unsigned int v4; // eax
  unsigned int v5; // r12d
  unsigned int valid; // eax
  struct _SECURITY_ATTRIBUTES *v8; // r9
  DWORD v9; // r12d
  unsigned int LogFile; // eax
  struct _SECURITY_ATTRIBUTES *v11; // r9
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  __int64 File; // r13
  DWORD LastError; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  __int64 v18; // rdx
  CMapDeviceId *v19; // rcx
  int v20; // eax
  unsigned __int16 *v21; // r8
  int v22; // eax
  __int64 v23; // r9
  int v24; // r13d
  void **v25; // rdx
  DWORD v26; // eax
  __int64 v27; // rax
  ULONG lpOverlapped; // [rsp+20h] [rbp-2E8h]
  ULONG lpOverlappeda; // [rsp+20h] [rbp-2E8h]
  ULONG v30; // [rsp+28h] [rbp-2E0h]
  ULONG v31; // [rsp+28h] [rbp-2E0h]
  unsigned int v32; // [rsp+40h] [rbp-2C8h]
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-2C4h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-2B8h] BYREF
  DWORD dwShareMode[2]; // [rsp+58h] [rbp-2B0h] BYREF
  void **v36; // [rsp+60h] [rbp-2A8h]
  void **v37; // [rsp+68h] [rbp-2A0h]
  exception *v38; // [rsp+70h] [rbp-298h] BYREF
  void *Block[2]; // [rsp+78h] [rbp-290h] BYREF
  __int64 v40; // [rsp+88h] [rbp-280h]
  unsigned __int64 v41; // [rsp+90h] [rbp-278h]
  DWORD v42; // [rsp+98h] [rbp-270h]
  unsigned __int16 v43[18]; // [rsp+9Ch] [rbp-26Ch] BYREF
  WCHAR FileName[264]; // [rsp+C0h] [rbp-248h] BYREF

  v36 = a3;
  v37 = a2;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  *(_QWORD *)dwShareMode = -1;
  hObject = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  v41 = 7;
  v40 = 0;
  LOWORD(Block[0]) = 0;
  if ( !g_fLogStringTableInit )
  {
    v4 = InitializeLoggingStringTables();
    v5 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v4);
      }
      return v5;
    }
    g_fLogStringTableInit = 1;
  }
  valid = IsValidFaxFolder(a1);
  v5 = valid;
  if ( valid )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        (_DWORD)a1,
        valid);
    }
    return v5;
  }
  v9 = 0;
  LogFile = (unsigned int)CreateLogFile(0, (ACCESS_MASK)a1, (DWORD)dwShareMode, v8, lpOverlapped, v30);
  v32 = LogFile;
  if ( LogFile )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    v13 = 30;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LogFile);
LABEL_24:
    File = -1;
    goto LABEL_25;
  }
  LogFile = (unsigned int)CreateLogFile((LPCWSTR)1, (ACCESS_MASK)a1, (DWORD)&hObject, v11, lpOverlappeda, v31);
  v32 = LogFile;
  if ( LogFile )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    v13 = 31;
    goto LABEL_23;
  }
  *v37 = *(void **)dwShareMode;
  *v36 = hObject;
  v22 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a1, L"schema.ini");
  v24 = v22;
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        (unsigned int)v22);
    }
    if ( (v24 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v24;
    else
      v9 = v24;
    goto LABEL_44;
  }
  File = InternalSafeCreateFile(FileName, 0x40000000u, 0, v23, 2u, 128);
  v36 = (void **)File;
  if ( File == -1 )
  {
    v17 = GetLastError();
    v9 = v17;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_44;
    }
    v18 = 33;
    goto LABEL_43;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    GetSchemaFileText(Block);
    v25 = Block;
    if ( v41 >= 8 )
      v25 = (void **)Block[0];
    if ( !WriteFile((HANDLE)File, v25, 2 * v40, &NumberOfBytesWritten, 0) )
    {
      v26 = GetLastError();
      v9 = v26;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v26);
      }
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', &v38) )
    {
      v32 = 14;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v38 + 8LL))(v38);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v27);
      }
      File = (__int64)v36;
      v9 = 0;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_140027F55);
LABEL_25:
      if ( hObject != (HANDLE)-1LL
        && !CloseHandle(hObject)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
      }
      if ( *(_QWORD *)dwShareMode != -1
        && !CloseHandle(*(HANDLE *)dwShareMode)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v16);
      }
      if ( File == -1 )
        goto LABEL_44;
    }
  }
  if ( CloseHandle((HANDLE)File)
    || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_44;
  }
  v17 = GetLastError();
  v18 = 38;
  v19 = WPP_GLOBAL_Control;
LABEL_43:
  WPP_SF_d(*((_QWORD *)v19 + 2), v18, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v17);
LABEL_44:
  if ( v9 )
  {
    v42 = v9;
    v43[0] = 0;
    v20 = StringCchPrintfW(v43, 0xCu, L"%ld", v9);
    v21 = v43;
    if ( v20 < 0 )
      v21 = 0;
    ((void (__fastcall *)(__int64, __int64, __int64, __int64, WCHAR *, unsigned __int16 *))FaxLog)(
      1,
      2,
      2,
      2147515725LL,
      FileName,
      v21);
  }
  if ( v41 >= 8 )
    operator delete(Block[0]);
  return v32;
}

```

## disassembly

```asm
0x140027a58  push    rbx
0x140027a5a  push    r12
0x140027a5c  push    r13
0x140027a5e  push    r14
0x140027a60  push    r15
0x140027a62  sub     rsp, 2E0h
0x140027a69  mov     rax, cs:__security_cookie
0x140027a70  xor     rax, rsp
0x140027a73  mov     [rsp+308h+var_38], rax
0x140027a7b  mov     [rsp+308h+var_2A8], r8
0x140027a80  mov     [rsp+308h+var_2A0], rdx
0x140027a85  mov     r13, rcx
0x140027a88  lea     r14, WPP_GLOBAL_Control
0x140027a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a96  cmp     rcx, r14
0x140027a99  jz      short loc_140027ABC
0x140027a9b  test    byte ptr [rcx+1Ch], 4
0x140027a9f  jz      short loc_140027ABC
0x140027aa1  cmp     byte ptr [rcx+19h], 5
0x140027aa5  jb      short loc_140027ABC
0x140027aa7  mov     edx, 1Bh
0x140027aac  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027ab3  mov     rcx, [rcx+10h]
0x140027ab7  call    WPP_SF_
0x140027abc  or      r15, 0FFFFFFFFFFFFFFFFh
0x140027ac0  mov     qword ptr [rsp+308h+dwShareMode], r15
0x140027ac5  mov     [rsp+308h+hObject], r15
0x140027aca  xor     ebx, ebx
0x140027acc  mov     [rsp+308h+NumberOfBytesWritten], ebx
0x140027ad0  mov     [rsp+308h+var_278], 7
0x140027adc  mov     [rsp+308h+var_280], rbx
0x140027ae4  mov     word ptr [rsp+308h+Block], bx
0x140027ae9  cmp     cs:?g_fLogStringTableInit@@3HA, ebx; int g_fLogStringTableInit
0x140027aef  jnz     short loc_140027B53
0x140027af1  call    ?InitializeLoggingStringTables@@YAKXZ; InitializeLoggingStringTables(void)
0x140027af6  mov     r12d, eax
0x140027af9  test    eax, eax
0x140027afb  jz      short loc_140027B49
0x140027afd  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b04  cmp     rcx, r14
0x140027b07  jz      short loc_140027B2C
0x140027b09  test    byte ptr [rcx+1Ch], 4
0x140027b0d  jz      short loc_140027B2C
0x140027b0f  cmp     byte ptr [rcx+19h], 2
0x140027b13  jb      short loc_140027B2C
0x140027b15  lea     edx, [rbx+1Ch]
0x140027b18  mov     r9d, eax
0x140027b1b  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027b22  mov     rcx, [rcx+10h]
0x140027b26  call    WPP_SF_d
0x140027b2b  nop
0x140027b2c  cmp     [rsp+308h+var_278], 8
0x140027b35  jb      short loc_140027B41
0x140027b37  mov     rcx, [rsp+308h+Block]; Block
0x140027b3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140027b41  mov     eax, r12d
0x140027b44  jmp     loc_140027D5B
0x140027b49  mov     cs:?g_fLogStringTableInit@@3HA, 1; int g_fLogStringTableInit
0x140027b53  mov     rcx, r13; unsigned __int16 *
0x140027b56  call    IsValidFaxFolder
0x140027b5b  mov     r12d, eax
0x140027b5e  test    eax, eax
0x140027b60  jz      short loc_140027B98
0x140027b62  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b69  cmp     rcx, r14
0x140027b6c  jz      short loc_140027B2C
0x140027b6e  test    byte ptr [rcx+1Ch], 4
0x140027b72  jz      short loc_140027B2C
0x140027b74  cmp     byte ptr [rcx+19h], 2
0x140027b78  jb      short loc_140027B2C
0x140027b7a  mov     edx, 1Dh
0x140027b7f  mov     dword ptr [rsp+308h+lpOverlapped], eax
0x140027b83  mov     r9, r13
0x140027b86  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027b8d  mov     rcx, [rcx+10h]
0x140027b91  call    WPP_SF_Sd
0x140027b96  jmp     short loc_140027B2C
0x140027b98  mov     r12d, ebx
0x140027b9b  lea     r8, [rsp+308h+dwShareMode]; dwShareMode
0x140027ba0  mov     rdx, r13; fDesiredAccess
0x140027ba3  xor     ecx, ecx; pszLogFileName
0x140027ba5  call    CreateLogFile
0x140027baa  mov     [rsp+308h+var_2C8], eax
0x140027bae  test    eax, eax
0x140027bb0  jz      loc_140027D7C
0x140027bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140027bbd  cmp     rcx, r14
0x140027bc0  jz      short loc_140027BE6
0x140027bc2  test    byte ptr [rcx+1Ch], 4
0x140027bc6  jz      short loc_140027BE6
0x140027bc8  cmp     byte ptr [rcx+19h], 2
0x140027bcc  jb      short loc_140027BE6
0x140027bce  mov     edx, 1Eh
0x140027bd3  mov     r9d, eax
0x140027bd6  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027bdd  mov     rcx, [rcx+10h]
0x140027be1  call    WPP_SF_d
0x140027be6  mov     r13, r15
0x140027be9  mov     rcx, [rsp+308h+hObject]; hObject
0x140027bee  cmp     rcx, r15
0x140027bf1  jz      short loc_140027C3A
0x140027bf3  call    cs:__imp_CloseHandle
0x140027bf9  test    eax, eax
0x140027bfb  jnz     short loc_140027C3A
0x140027bfd  mov     rax, cs:WPP_GLOBAL_Control
0x140027c04  cmp     rax, r14
0x140027c07  jz      short loc_140027C3A
0x140027c09  test    byte ptr [rax+1Ch], 4
0x140027c0d  jz      short loc_140027C3A
0x140027c0f  cmp     byte ptr [rax+19h], 2
0x140027c13  jb      short loc_140027C3A
0x140027c15  call    cs:__imp_GetLastError
0x140027c1b  mov     edx, 24h ; '$'
0x140027c20  mov     r9d, eax
0x140027c23  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c31  mov     rcx, [rcx+10h]
0x140027c35  call    WPP_SF_d
0x140027c3a  mov     rcx, qword ptr [rsp+308h+dwShareMode]; hObject
0x140027c3f  cmp     rcx, r15
0x140027c42  jz      short loc_140027C8B
0x140027c44  call    cs:__imp_CloseHandle
0x140027c4a  test    eax, eax
0x140027c4c  jnz     short loc_140027C8B
0x140027c4e  mov     rax, cs:WPP_GLOBAL_Control
0x140027c55  cmp     rax, r14
0x140027c58  jz      short loc_140027C8B
0x140027c5a  test    byte ptr [rax+1Ch], 4
0x140027c5e  jz      short loc_140027C8B
0x140027c60  cmp     byte ptr [rax+19h], 2
0x140027c64  jb      short loc_140027C8B
0x140027c66  call    cs:__imp_GetLastError
0x140027c6c  mov     edx, 25h ; '%'
0x140027c71  mov     r9d, eax
0x140027c74  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c82  mov     rcx, [rcx+10h]
0x140027c86  call    WPP_SF_d
0x140027c8b  cmp     r13, r15
0x140027c8e  jz      short loc_140027CDA
0x140027c90  mov     rcx, r13; hObject
0x140027c93  call    cs:__imp_CloseHandle
0x140027c99  test    eax, eax
0x140027c9b  jnz     short loc_140027CDA
0x140027c9d  mov     rax, cs:WPP_GLOBAL_Control
0x140027ca4  cmp     rax, r14
0x140027ca7  jz      short loc_140027CDA
0x140027ca9  test    byte ptr [rax+1Ch], 4
0x140027cad  jz      short loc_140027CDA
0x140027caf  cmp     byte ptr [rax+19h], 2
0x140027cb3  jb      short loc_140027CDA
0x140027cb5  call    cs:__imp_GetLastError
0x140027cbb  mov     edx, 26h ; '&'
0x140027cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140027cc7  mov     r9d, eax
0x140027cca  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027cd1  mov     rcx, [rcx+10h]
0x140027cd5  call    WPP_SF_d
0x140027cda  test    r12d, r12d
0x140027cdd  jz      short loc_140027D42
0x140027cdf  mov     [rsp+308h+var_270], r12d
0x140027ce7  mov     [rsp+308h+var_26C], bx
0x140027cef  mov     r9d, r12d
0x140027cf2  lea     r8, aLd; "%ld"
0x140027cf9  mov     edx, 0Ch; unsigned __int64
0x140027cfe  lea     rcx, [rsp+308h+var_26C]; unsigned __int16 *
0x140027d06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140027d0b  lea     r8, [rsp+308h+var_26C]
0x140027d13  test    eax, eax
0x140027d15  cmovs   r8, rbx
0x140027d19  mov     qword ptr [rsp+308h+var_2E0], r8
0x140027d1e  lea     rax, [rsp+308h+FileName]
0x140027d26  mov     [rsp+308h+lpOverlapped], rax
0x140027d2b  mov     edx, 2
0x140027d30  lea     ecx, [rdx-1]
0x140027d33  mov     r9d, 80007D4Dh
0x140027d39  mov     r8d, edx
0x140027d3c  call    FaxLog
0x140027d41  nop
0x140027d42  cmp     [rsp+308h+var_278], 8
0x140027d4b  jb      short loc_140027D57
0x140027d4d  mov     rcx, [rsp+308h+Block]; Block
0x140027d52  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140027d57  mov     eax, [rsp+308h+var_2C8]
0x140027d5b  mov     rcx, [rsp+308h+var_38]
0x140027d63  xor     rcx, rsp; StackCookie
0x140027d66  call    __security_check_cookie
0x140027d6b  add     rsp, 2E0h
0x140027d72  pop     r15
0x140027d74  pop     r14
0x140027d76  pop     r13
0x140027d78  pop     r12
0x140027d7a  pop     rbx
0x140027d7b  retn
0x140027d7c  lea     r8, [rsp+308h+hObject]; dwShareMode
0x140027d81  mov     rdx, r13; fDesiredAccess
0x140027d84  mov     ecx, 1; pszLogFileName
0x140027d89  call    CreateLogFile
0x140027d8e  mov     [rsp+308h+var_2C8], eax
0x140027d92  test    eax, eax
0x140027d94  jz      short loc_140027DC4
0x140027d96  mov     rcx, cs:WPP_GLOBAL_Control
0x140027d9d  cmp     rcx, r14
0x140027da0  jz      loc_140027BE6
0x140027da6  test    byte ptr [rcx+1Ch], 4
0x140027daa  jz      loc_140027BE6
0x140027db0  cmp     byte ptr [rcx+19h], 2
0x140027db4  jb      loc_140027BE6
0x140027dba  mov     edx, 1Fh
0x140027dbf  jmp     loc_140027BD3
0x140027dc4  mov     rax, qword ptr [rsp+308h+dwShareMode]
0x140027dc9  mov     rcx, [rsp+308h+var_2A0]
0x140027dce  mov     [rcx], rax
0x140027dd1  mov     rax, [rsp+308h+hObject]
0x140027dd6  mov     rcx, [rsp+308h+var_2A8]
0x140027ddb  mov     [rcx], rax
0x140027dde  lea     rax, aSchemaIni; "schema.ini"
0x140027de5  mov     [rsp+308h+lpOverlapped], rax
0x140027dea  mov     r9, r13
0x140027ded  lea     r8, aSS_0; "%s\\%s"
0x140027df4  mov     edx, 104h; unsigned __int64
0x140027df9  lea     rcx, [rsp+308h+FileName]; unsigned __int16 *
0x140027e01  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140027e06  mov     r13d, eax
0x140027e09  test    eax, eax
0x140027e0b  jns     short loc_140027E5D
0x140027e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027e14  cmp     rcx, r14
0x140027e17  jz      short loc_140027E3D
0x140027e19  test    byte ptr [rcx+1Ch], 4
0x140027e1d  jz      short loc_140027E3D
0x140027e1f  cmp     byte ptr [rcx+19h], 2
0x140027e23  jb      short loc_140027E3D
0x140027e25  mov     edx, 20h ; ' '
0x140027e2a  mov     r9d, eax
0x140027e2d  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027e34  mov     rcx, [rcx+10h]
0x140027e38  call    WPP_SF_d
0x140027e3d  mov     eax, r13d
0x140027e40  and     eax, 1FFF0000h
0x140027e45  cmp     eax, 70000h
0x140027e4a  jnz     short loc_140027E55
0x140027e4c  movzx   r12d, r13w
0x140027e50  jmp     loc_140027CDA
0x140027e55  mov     r12d, r13d
0x140027e58  jmp     loc_140027CDA
0x140027e5d  mov     [rsp+308h+var_2E0], 80h; int
0x140027e65  mov     dword ptr [rsp+308h+lpOverlapped], 2; DWORD
0x140027e6d  xor     r8d, r8d; dwShareMode
0x140027e70  mov     edx, 40000000h; dwDesiredAccess
0x140027e75  lea     rcx, [rsp+308h+FileName]; lpFileName
0x140027e7d  call    InternalSafeCreateFile
0x140027e82  mov     r13, rax
0x140027e85  mov     [rsp+308h+var_2A8], rax
0x140027e8a  cmp     rax, r15
0x140027e8d  jnz     short loc_140027EC6
0x140027e8f  call    cs:__imp_GetLastError
0x140027e95  mov     r12d, eax
0x140027e98  mov     rcx, cs:WPP_GLOBAL_Control
0x140027e9f  cmp     rcx, r14
0x140027ea2  jz      loc_140027CDA
0x140027ea8  test    byte ptr [rcx+1Ch], 4
0x140027eac  jz      loc_140027CDA
0x140027eb2  cmp     byte ptr [rcx+19h], 2
0x140027eb6  jb      loc_140027CDA
0x140027ebc  mov     edx, 21h ; '!'
0x140027ec1  jmp     loc_140027CC7
0x140027ec6  lea     rcx, [rsp+308h+Block]; Src
0x140027ecb  call    GetSchemaFileText
0x140027ed0  nop
0x140027ed1  mov     r8d, dword ptr [rsp+308h+var_280]
0x140027ed9  lea     rdx, [rsp+308h+Block]
0x140027ede  cmp     [rsp+308h+var_278], 8
0x140027ee7  cmovnb  rdx, [rsp+308h+Block]; lpBuffer
0x140027eed  add     r8d, r8d; nNumberOfBytesToWrite
0x140027ef0  mov     [rsp+308h+lpOverlapped], rbx; lpOverlapped
0x140027ef5  lea     r9, [rsp+308h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140027efa  mov     rcx, r13; hFile
0x140027efd  call    cs:__imp_WriteFile
0x140027f03  test    eax, eax
0x140027f05  jnz     loc_140027C90
0x140027f0b  call    cs:__imp_GetLastError
0x140027f11  mov     r12d, eax
0x140027f14  mov     rcx, cs:WPP_GLOBAL_Control
0x140027f1b  cmp     rcx, r14
0x140027f1e  jz      loc_140027C90
0x140027f24  test    byte ptr [rcx+1Ch], 4
0x140027f28  jz      loc_140027C90
0x140027f2e  cmp     byte ptr [rcx+19h], 2
0x140027f32  jb      loc_140027C90
0x140027f38  mov     edx, 23h ; '#'
0x140027f3d  mov     r9d, eax
0x140027f40  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027f47  mov     rcx, [rcx+10h]
0x140027f4b  call    WPP_SF_d
0x140027f50  jmp     loc_140027C90
0x140027f55  lea     r14, WPP_GLOBAL_Control
0x140027f5c  or      r15, 0FFFFFFFFFFFFFFFFh
0x140027f60  xor     ebx, ebx
0x140027f62  mov     eax, [rsp+308h+var_2C8]
  ... truncated ...
```
