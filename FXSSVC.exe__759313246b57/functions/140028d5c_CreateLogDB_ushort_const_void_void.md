# CreateLogDB(ushort const *,void * *,void * *)

- ea: `0x140028d5c`
- end: `0x1400292b3`
- name: `?CreateLogDB@@YAKPEBGPEAPEAX1@Z`
- size: `1367`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, void **)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001ee40`
- `0x14002c380`

## callees

- `0x140001bac`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140028d5c`
- `0x1400292bc`
- `0x14002bfa0`
- `0x14002c488`
- `0x1400699d0`
- `0x14006e124`
- `0x140072490`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140028f1f`
- `KERNEL32!GetLastError` at `0x140028f7c`
- `KERNEL32!GetLastError` at `0x140028fd7`
- `KERNEL32!GetLastError` at `0x1400291b8`
- `KERNEL32!GetLastError` at `0x140029240`
- `KERNEL32!GetLastError` at `0x140028f1f`
- `KERNEL32!GetLastError` at `0x140028f7c`
- `KERNEL32!GetLastError` at `0x140028fd7`
- `KERNEL32!GetLastError` at `0x1400291b8`
- `KERNEL32!GetLastError` at `0x140029240`
- `KERNEL32!CloseHandle` at `0x140028ef7`
- `KERNEL32!CloseHandle` at `0x140028f54`
- `KERNEL32!CloseHandle` at `0x140028faf`
- `KERNEL32!CloseHandle` at `0x140028ef7`
- `KERNEL32!CloseHandle` at `0x140028f54`
- `KERNEL32!CloseHandle` at `0x140028faf`
- `KERNEL32!WriteFile` at `0x14002922c`
- `KERNEL32!WriteFile` at `0x14002922c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateLogDB(unsigned __int16 *a1, void **a2, void **a3)
{
  DWORD v4; // eax
  DWORD v5; // r12d
  DWORD valid; // eax
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
  __int64 v21; // r9
  int v22; // r13d
  void **v23; // rdx
  DWORD v24; // eax
  __int64 v25; // rax
  ULONG lpOverlapped; // [rsp+20h] [rbp-2E8h]
  ULONG lpOverlappeda; // [rsp+20h] [rbp-2E8h]
  ULONG v28; // [rsp+28h] [rbp-2E0h]
  ULONG v29; // [rsp+28h] [rbp-2E0h]
  unsigned int v30; // [rsp+40h] [rbp-2C8h]
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-2C4h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-2B8h] BYREF
  DWORD dwShareMode[2]; // [rsp+58h] [rbp-2B0h] BYREF
  void **v34; // [rsp+60h] [rbp-2A8h]
  void **v35; // [rsp+68h] [rbp-2A0h]
  exception *v36; // [rsp+70h] [rbp-298h] BYREF
  void *Block[2]; // [rsp+78h] [rbp-290h] BYREF
  __int64 v38; // [rsp+88h] [rbp-280h]
  unsigned __int64 v39; // [rsp+90h] [rbp-278h]
  DWORD v40; // [rsp+98h] [rbp-270h]
  unsigned __int16 v41[18]; // [rsp+9Ch] [rbp-26Ch] BYREF
  WCHAR FileName[264]; // [rsp+C0h] [rbp-248h] BYREF

  v34 = a3;
  v35 = a2;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  *(_QWORD *)dwShareMode = -1;
  hObject = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  v39 = 7;
  v38 = 0;
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
  LogFile = (unsigned int)CreateLogFile(0, (ACCESS_MASK)a1, (DWORD)dwShareMode, v8, lpOverlapped, v28);
  v30 = LogFile;
  if ( LogFile )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 30;
LABEL_23:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LogFile);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  LogFile = (unsigned int)CreateLogFile((LPCWSTR)1, (ACCESS_MASK)a1, (DWORD)&hObject, v11, lpOverlappeda, v29);
  v30 = LogFile;
  if ( LogFile )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 31;
      goto LABEL_23;
    }
LABEL_24:
    File = -1;
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
    goto LABEL_38;
  }
  *v35 = *(void **)dwShareMode;
  *v34 = hObject;
  v20 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a1, L"schema.ini");
  v22 = v20;
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        (unsigned int)v20);
    }
    if ( (v22 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v22;
    else
      v9 = v22;
    goto LABEL_44;
  }
  File = InternalSafeCreateFile(FileName, 0x40000000u, 0, v21, 2u, 128);
  v34 = (void **)File;
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
  try
  {
    GetSchemaFileText(Block);
    v23 = Block;
    if ( v39 >= 8 )
      v23 = (void **)Block[0];
    if ( !WriteFile((HANDLE)File, v23, 2 * v38, &NumberOfBytesWritten, 0) )
    {
      v24 = GetLastError();
      v9 = v24;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v24);
      }
    }
  }
  catch ( exception *v36 )
  {
    v30 = 14;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v36 + 8LL))(v36);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v25);
    }
    File = (__int64)v34;
    v9 = 0;
    goto LABEL_25;
  }
LABEL_38:
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
    v40 = v9;
    v41[0] = 0;
    StringCchPrintfW(v41, 0xCu, L"%ld", v9);
    FaxLog(1u, 2u, 2u, 0x80007D4D, (char)FileName);
  }
  if ( v39 >= 8 )
    operator delete(Block[0]);
  return v30;
}

```

## disassembly

```asm
0x140028d5c  push    rbx
0x140028d5e  push    r12
0x140028d60  push    r13
0x140028d62  push    r14
0x140028d64  push    r15
0x140028d66  sub     rsp, 2E0h
0x140028d6d  mov     rax, cs:__security_cookie
0x140028d74  xor     rax, rsp
0x140028d77  mov     [rsp+308h+var_38], rax
0x140028d7f  mov     [rsp+308h+var_2A8], r8
0x140028d84  mov     [rsp+308h+var_2A0], rdx
0x140028d89  mov     r13, rcx
0x140028d8c  lea     r14, WPP_GLOBAL_Control
0x140028d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140028d9a  cmp     rcx, r14
0x140028d9d  jz      short loc_140028DC0
0x140028d9f  test    byte ptr [rcx+1Ch], 4
0x140028da3  jz      short loc_140028DC0
0x140028da5  cmp     byte ptr [rcx+19h], 5
0x140028da9  jb      short loc_140028DC0
0x140028dab  mov     edx, 1Bh
0x140028db0  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028db7  mov     rcx, [rcx+10h]
0x140028dbb  call    WPP_SF_
0x140028dc0  or      r15, 0FFFFFFFFFFFFFFFFh
0x140028dc4  mov     qword ptr [rsp+308h+dwShareMode], r15
0x140028dc9  mov     [rsp+308h+hObject], r15
0x140028dce  xor     ebx, ebx
0x140028dd0  mov     [rsp+308h+NumberOfBytesWritten], ebx
0x140028dd4  mov     [rsp+308h+var_278], 7
0x140028de0  mov     [rsp+308h+var_280], rbx
0x140028de8  mov     word ptr [rsp+308h+Block], bx
0x140028ded  cmp     cs:?g_fLogStringTableInit@@3HA, ebx; int g_fLogStringTableInit
0x140028df3  jnz     short loc_140028E57
0x140028df5  call    ?InitializeLoggingStringTables@@YAKXZ; InitializeLoggingStringTables(void)
0x140028dfa  mov     r12d, eax
0x140028dfd  test    eax, eax
0x140028dff  jz      short loc_140028E4D
0x140028e01  mov     rcx, cs:WPP_GLOBAL_Control
0x140028e08  cmp     rcx, r14
0x140028e0b  jz      short loc_140028E30
0x140028e0d  test    byte ptr [rcx+1Ch], 4
0x140028e11  jz      short loc_140028E30
0x140028e13  cmp     byte ptr [rcx+19h], 2
0x140028e17  jb      short loc_140028E30
0x140028e19  lea     edx, [rbx+1Ch]
0x140028e1c  mov     r9d, eax
0x140028e1f  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028e26  mov     rcx, [rcx+10h]
0x140028e2a  call    WPP_SF_d
0x140028e2f  nop
0x140028e30  cmp     [rsp+308h+var_278], 8
0x140028e39  jb      short loc_140028E45
0x140028e3b  mov     rcx, [rsp+308h+Block]; Block
0x140028e40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140028e45  mov     eax, r12d
0x140028e48  jmp     loc_140029083
0x140028e4d  mov     cs:?g_fLogStringTableInit@@3HA, 1; int g_fLogStringTableInit
0x140028e57  mov     rcx, r13; unsigned __int16 *
0x140028e5a  call    IsValidFaxFolder
0x140028e5f  mov     r12d, eax
0x140028e62  test    eax, eax
0x140028e64  jz      short loc_140028E9C
0x140028e66  mov     rcx, cs:WPP_GLOBAL_Control
0x140028e6d  cmp     rcx, r14
0x140028e70  jz      short loc_140028E30
0x140028e72  test    byte ptr [rcx+1Ch], 4
0x140028e76  jz      short loc_140028E30
0x140028e78  cmp     byte ptr [rcx+19h], 2
0x140028e7c  jb      short loc_140028E30
0x140028e7e  mov     edx, 1Dh
0x140028e83  mov     dword ptr [rsp+308h+lpOverlapped], eax
0x140028e87  mov     r9, r13
0x140028e8a  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028e91  mov     rcx, [rcx+10h]
0x140028e95  call    WPP_SF_Sd
0x140028e9a  jmp     short loc_140028E30
0x140028e9c  mov     r12d, ebx
0x140028e9f  lea     r8, [rsp+308h+dwShareMode]; dwShareMode
0x140028ea4  mov     rdx, r13; fDesiredAccess
0x140028ea7  xor     ecx, ecx; pszLogFileName
0x140028ea9  call    CreateLogFile
0x140028eae  mov     [rsp+308h+var_2C8], eax
0x140028eb2  test    eax, eax
0x140028eb4  jz      loc_1400290A5
0x140028eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140028ec1  cmp     rcx, r14
0x140028ec4  jz      short loc_140028EEA
0x140028ec6  test    byte ptr [rcx+1Ch], 4
0x140028eca  jz      short loc_140028EEA
0x140028ecc  cmp     byte ptr [rcx+19h], 2
0x140028ed0  jb      short loc_140028EEA
0x140028ed2  mov     edx, 1Eh
0x140028ed7  mov     r9d, eax
0x140028eda  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028ee1  mov     rcx, [rcx+10h]
0x140028ee5  call    WPP_SF_d
0x140028eea  mov     r13, r15
0x140028eed  mov     rcx, [rsp+308h+hObject]; hObject
0x140028ef2  cmp     rcx, r15
0x140028ef5  jz      short loc_140028F4A
0x140028ef7  call    cs:__imp_CloseHandle
0x140028efe  nop     dword ptr [rax+rax+00h]
0x140028f03  test    eax, eax
0x140028f05  jnz     short loc_140028F4A
0x140028f07  mov     rax, cs:WPP_GLOBAL_Control
0x140028f0e  cmp     rax, r14
0x140028f11  jz      short loc_140028F4A
0x140028f13  test    byte ptr [rax+1Ch], 4
0x140028f17  jz      short loc_140028F4A
0x140028f19  cmp     byte ptr [rax+19h], 2
0x140028f1d  jb      short loc_140028F4A
0x140028f1f  call    cs:__imp_GetLastError
0x140028f26  nop     dword ptr [rax+rax+00h]
0x140028f2b  mov     edx, 24h ; '$'
0x140028f30  mov     r9d, eax
0x140028f33  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140028f41  mov     rcx, [rcx+10h]
0x140028f45  call    WPP_SF_d
0x140028f4a  mov     rcx, qword ptr [rsp+308h+dwShareMode]; hObject
0x140028f4f  cmp     rcx, r15
0x140028f52  jz      short loc_140028FA7
0x140028f54  call    cs:__imp_CloseHandle
0x140028f5b  nop     dword ptr [rax+rax+00h]
0x140028f60  test    eax, eax
0x140028f62  jnz     short loc_140028FA7
0x140028f64  mov     rax, cs:WPP_GLOBAL_Control
0x140028f6b  cmp     rax, r14
0x140028f6e  jz      short loc_140028FA7
0x140028f70  test    byte ptr [rax+1Ch], 4
0x140028f74  jz      short loc_140028FA7
0x140028f76  cmp     byte ptr [rax+19h], 2
0x140028f7a  jb      short loc_140028FA7
0x140028f7c  call    cs:__imp_GetLastError
0x140028f83  nop     dword ptr [rax+rax+00h]
0x140028f88  mov     edx, 25h ; '%'
0x140028f8d  mov     r9d, eax
0x140028f90  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028f97  mov     rcx, cs:WPP_GLOBAL_Control
0x140028f9e  mov     rcx, [rcx+10h]
0x140028fa2  call    WPP_SF_d
0x140028fa7  cmp     r13, r15
0x140028faa  jz      short loc_140029002
0x140028fac  mov     rcx, r13; hObject
0x140028faf  call    cs:__imp_CloseHandle
0x140028fb6  nop     dword ptr [rax+rax+00h]
0x140028fbb  test    eax, eax
0x140028fbd  jnz     short loc_140029002
0x140028fbf  mov     rax, cs:WPP_GLOBAL_Control
0x140028fc6  cmp     rax, r14
0x140028fc9  jz      short loc_140029002
0x140028fcb  test    byte ptr [rax+1Ch], 4
0x140028fcf  jz      short loc_140029002
0x140028fd1  cmp     byte ptr [rax+19h], 2
0x140028fd5  jb      short loc_140029002
0x140028fd7  call    cs:__imp_GetLastError
0x140028fde  nop     dword ptr [rax+rax+00h]
0x140028fe3  mov     edx, 26h ; '&'
0x140028fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x140028fef  mov     r9d, eax
0x140028ff2  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028ff9  mov     rcx, [rcx+10h]
0x140028ffd  call    WPP_SF_d
0x140029002  test    r12d, r12d
0x140029005  jz      short loc_14002906A
0x140029007  mov     [rsp+308h+var_270], r12d
0x14002900f  mov     [rsp+308h+var_26C], bx
0x140029017  mov     r9d, r12d
0x14002901a  lea     r8, aLd; "%ld"
0x140029021  mov     edx, 0Ch; unsigned __int64
0x140029026  lea     rcx, [rsp+308h+var_26C]; unsigned __int16 *
0x14002902e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140029033  lea     r8, [rsp+308h+var_26C]
0x14002903b  test    eax, eax
0x14002903d  cmovs   r8, rbx
0x140029041  mov     qword ptr [rsp+308h+var_2E0], r8
0x140029046  lea     rax, [rsp+308h+FileName]
0x14002904e  mov     [rsp+308h+lpOverlapped], rax
0x140029053  mov     edx, 2
0x140029058  lea     ecx, [rdx-1]
0x14002905b  mov     r9d, 80007D4Dh
0x140029061  mov     r8d, edx
0x140029064  call    FaxLog
0x140029069  nop
0x14002906a  cmp     [rsp+308h+var_278], 8
0x140029073  jb      short loc_14002907F
0x140029075  mov     rcx, [rsp+308h+Block]; Block
0x14002907a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002907f  mov     eax, [rsp+308h+var_2C8]
0x140029083  mov     rcx, [rsp+308h+var_38]
0x14002908b  xor     rcx, rsp; StackCookie
0x14002908e  call    __security_check_cookie
0x140029093  add     rsp, 2E0h
0x14002909a  pop     r15
0x14002909c  pop     r14
0x14002909e  pop     r13
0x1400290a0  pop     r12
0x1400290a2  pop     rbx
0x1400290a3  retn
0x1400290a5  lea     r8, [rsp+308h+hObject]; dwShareMode
0x1400290aa  mov     rdx, r13; fDesiredAccess
0x1400290ad  mov     ecx, 1; pszLogFileName
0x1400290b2  call    CreateLogFile
0x1400290b7  mov     [rsp+308h+var_2C8], eax
0x1400290bb  test    eax, eax
0x1400290bd  jz      short loc_1400290ED
0x1400290bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400290c6  cmp     rcx, r14
0x1400290c9  jz      loc_140028EEA
0x1400290cf  test    byte ptr [rcx+1Ch], 4
0x1400290d3  jz      loc_140028EEA
0x1400290d9  cmp     byte ptr [rcx+19h], 2
0x1400290dd  jb      loc_140028EEA
0x1400290e3  mov     edx, 1Fh
0x1400290e8  jmp     loc_140028ED7
0x1400290ed  mov     rax, qword ptr [rsp+308h+dwShareMode]
0x1400290f2  mov     rcx, [rsp+308h+var_2A0]
0x1400290f7  mov     [rcx], rax
0x1400290fa  mov     rax, [rsp+308h+hObject]
0x1400290ff  mov     rcx, [rsp+308h+var_2A8]
0x140029104  mov     [rcx], rax
0x140029107  lea     rax, aSchemaIni; "schema.ini"
0x14002910e  mov     [rsp+308h+lpOverlapped], rax
0x140029113  mov     r9, r13
0x140029116  lea     r8, aSS_0; "%s\\%s"
0x14002911d  mov     edx, 104h; unsigned __int64
0x140029122  lea     rcx, [rsp+308h+FileName]; unsigned __int16 *
0x14002912a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002912f  mov     r13d, eax
0x140029132  test    eax, eax
0x140029134  jns     short loc_140029186
0x140029136  mov     rcx, cs:WPP_GLOBAL_Control
0x14002913d  cmp     rcx, r14
0x140029140  jz      short loc_140029166
0x140029142  test    byte ptr [rcx+1Ch], 4
0x140029146  jz      short loc_140029166
0x140029148  cmp     byte ptr [rcx+19h], 2
0x14002914c  jb      short loc_140029166
0x14002914e  mov     edx, 20h ; ' '
0x140029153  mov     r9d, eax
0x140029156  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002915d  mov     rcx, [rcx+10h]
0x140029161  call    WPP_SF_d
0x140029166  mov     eax, r13d
0x140029169  and     eax, 1FFF0000h
0x14002916e  cmp     eax, 70000h
0x140029173  jnz     short loc_14002917E
0x140029175  movzx   r12d, r13w
0x140029179  jmp     loc_140029002
0x14002917e  mov     r12d, r13d
0x140029181  jmp     loc_140029002
0x140029186  mov     [rsp+308h+var_2E0], 80h; int
0x14002918e  mov     dword ptr [rsp+308h+lpOverlapped], 2; DWORD
0x140029196  xor     r8d, r8d; dwShareMode
0x140029199  mov     edx, 40000000h; dwDesiredAccess
0x14002919e  lea     rcx, [rsp+308h+FileName]; lpFileName
0x1400291a6  call    InternalSafeCreateFile
0x1400291ab  mov     r13, rax
0x1400291ae  mov     [rsp+308h+var_2A8], rax
0x1400291b3  cmp     rax, r15
0x1400291b6  jnz     short loc_1400291F5
0x1400291b8  call    cs:__imp_GetLastError
0x1400291bf  nop     dword ptr [rax+rax+00h]
0x1400291c4  mov     r12d, eax
0x1400291c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400291ce  cmp     rcx, r14
0x1400291d1  jz      loc_140029002
0x1400291d7  test    byte ptr [rcx+1Ch], 4
0x1400291db  jz      loc_140029002
0x1400291e1  cmp     byte ptr [rcx+19h], 2
0x1400291e5  jb      loc_140029002
0x1400291eb  mov     edx, 21h ; '!'
0x1400291f0  jmp     loc_140028FEF
0x1400291f5  lea     rcx, [rsp+308h+Block]; Src
0x1400291fa  call    GetSchemaFileText
0x1400291ff  nop
0x140029200  mov     r8d, dword ptr [rsp+308h+var_280]
0x140029208  lea     rdx, [rsp+308h+Block]
0x14002920d  cmp     [rsp+308h+var_278], 8
0x140029216  cmovnb  rdx, [rsp+308h+Block]; lpBuffer
0x14002921c  add     r8d, r8d; nNumberOfBytesToWrite
0x14002921f  mov     [rsp+308h+lpOverlapped], rbx; lpOverlapped
0x140029224  lea     r9, [rsp+308h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140029229  mov     rcx, r13; hFile
0x14002922c  call    cs:__imp_WriteFile
0x140029233  nop     dword ptr [rax+rax+00h]
0x140029238  test    eax, eax
0x14002923a  jnz     loc_140028FAC
0x140029240  call    cs:__imp_GetLastError
0x140029247  nop     dword ptr [rax+rax+00h]
0x14002924c  mov     r12d, eax
0x14002924f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029256  cmp     rcx, r14
0x140029259  jz      loc_140028FAC
0x14002925f  test    byte ptr [rcx+1Ch], 4
0x140029263  jz      loc_140028FAC
0x140029269  cmp     byte ptr [rcx+19h], 2
0x14002926d  jb      loc_140028FAC
0x140029273  mov     edx, 23h ; '#'
  ... truncated ...
```
