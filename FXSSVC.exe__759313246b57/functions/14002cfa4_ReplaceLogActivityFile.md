# ReplaceLogActivityFile

- ea: `0x14002cfa4`
- end: `0x14002d42e`
- name: `ReplaceLogActivityFile`
- size: `1162`
- prototype: `__int64 __fastcall(LPCWSTR pszLogFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002c820`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140028c3c`
- `0x1400292bc`
- `0x14002cfa4`
- `0x14002d434`
- `0x14006998c`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002d071`
- `KERNEL32!GetLastError` at `0x14002d0da`
- `KERNEL32!GetLastError` at `0x14002d12d`
- `KERNEL32!GetLastError` at `0x14002d2c3`
- `KERNEL32!GetLastError` at `0x14002d31c`
- `KERNEL32!GetLastError` at `0x14002d071`
- `KERNEL32!GetLastError` at `0x14002d0da`
- `KERNEL32!GetLastError` at `0x14002d12d`
- `KERNEL32!GetLastError` at `0x14002d2c3`
- `KERNEL32!GetLastError` at `0x14002d31c`
- `KERNEL32!FileTimeToSystemTime` at `0x14002d0ca`
- `KERNEL32!FileTimeToSystemTime` at `0x14002d11d`
- `KERNEL32!FileTimeToSystemTime` at `0x14002d0ca`
- `KERNEL32!FileTimeToSystemTime` at `0x14002d11d`
- `KERNEL32!CloseHandle` at `0x14002d2b3`
- `KERNEL32!CloseHandle` at `0x14002d2b3`
- `KERNEL32!GetFileTime` at `0x14002d061`
- `KERNEL32!GetFileTime` at `0x14002d061`
- `KERNEL32!MoveFileW` at `0x14002d30c`
- `KERNEL32!MoveFileW` at `0x14002d30c`

## pseudocode

```c
__int64 __fastcall ReplaceLogActivityFile(LPCWSTR pszLogFileName)
{
  WCHAR *v1; // r15
  unsigned int v2; // esi
  WCHAR *v3; // r14
  HANDLE v4; // rcx
  HANDLE *v5; // rdi
  DWORD LastError; // eax
  unsigned int v7; // ebx
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  const wchar_t *v10; // rdx
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r8
  int v14; // eax
  struct _SECURITY_ATTRIBUTES *v15; // r9
  DWORD v16; // eax
  ULONG fCreateDisposition; // [rsp+20h] [rbp-E0h]
  ULONG fFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME v22; // [rsp+60h] [rbp-A0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[264]; // [rsp+80h] [rbp-80h] BYREF

  CreationTime = 0;
  LastWriteTime = 0;
  v1 = 0;
  v2 = (unsigned int)pszLogFileName;
  SystemTime = 0;
  v3 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  v4 = g_hOutboxActivityLogFile;
  v5 = &g_hInboxActivityLogFile;
  if ( v2 )
    v5 = &g_hOutboxActivityLogFile;
  else
    v4 = g_hInboxActivityLogFile;
  if ( !GetFileTime(v4, &CreationTime, 0, &LastWriteTime) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 107;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  if ( FileTimeToSystemTime(&CreationTime, &SystemTime) )
  {
    if ( !FileTimeToSystemTime(&LastWriteTime, &v22) )
    {
      LastError = GetLastError();
      v7 = LastError;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 109;
        goto LABEL_13;
      }
      goto LABEL_71;
    }
    v10 = L"InboxLOG.txt";
    if ( v2 )
      v10 = L"OutboxLOG.txt";
    v1 = (WCHAR *)BuildFullFileName(*(_QWORD *)&fDesiredAccess, v10);
    if ( !v1 )
    {
      v7 = 8;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v12 = 110;
      goto LABEL_70;
    }
    v13 = L"InboxLOG %04d-%02d-%02d - %04d-%02d-%02d.txt";
    if ( v2 )
      v13 = L"OutboxLOG %04d-%02d-%02d - %04d-%02d-%02d.txt";
    fFlagsAndAttributes = SystemTime.wDay;
    v14 = StringCchPrintfW(v24, 0x104u, v13, SystemTime.wYear, SystemTime.wMonth);
    v7 = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
          (unsigned int)v14);
      }
      if ( (v7 & 0x1FFF0000) == 0x70000 )
        v7 = (unsigned __int16)v7;
      goto LABEL_71;
    }
    v3 = (WCHAR *)BuildFullFileName(*(_QWORD *)&fDesiredAccess, v24);
    if ( !v3 )
    {
      v7 = 8;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v12 = 112;
      goto LABEL_70;
    }
    if ( !CloseHandle(*v5) )
    {
      LastError = GetLastError();
      v7 = LastError;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 113;
        goto LABEL_13;
      }
      goto LABEL_71;
    }
    *v5 = (HANDLE)-1LL;
    if ( !MoveFileW(v1, v3) )
    {
      v16 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v16);
      }
    }
    LastError = (unsigned int)CreateLogFile(
                                (LPCWSTR)v2,
                                fDesiredAccess,
                                (DWORD)v5,
                                v15,
                                fCreateDisposition,
                                fFlagsAndAttributes);
    v7 = LastError;
    if ( LastError )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 115;
        goto LABEL_13;
      }
      goto LABEL_71;
    }
    if ( !(unsigned int)SetFileToCurrentTime(*v5) )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
        goto LABEL_71;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_66;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, 0);
    }
    v11 = WPP_GLOBAL_Control;
LABEL_66:
    if ( v11 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 4) == 0 || *((_BYTE *)v11 + 25) < 5u )
      goto LABEL_71;
    v12 = 117;
LABEL_70:
    WPP_SF_(*((_QWORD *)v11 + 2), v12, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
    goto LABEL_71;
  }
  LastError = GetLastError();
  v7 = LastError;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 108;
    goto LABEL_13;
  }
LABEL_71:
  pMemFree(v1);
  pMemFree(v3);
  return v7;
}

```

## disassembly

```asm
0x14002cfa4  push    rbp
0x14002cfa6  push    rbx
0x14002cfa7  push    rsi
0x14002cfa8  push    rdi
0x14002cfa9  push    r12
0x14002cfab  push    r13
0x14002cfad  push    r14
0x14002cfaf  push    r15
0x14002cfb1  lea     rbp, [rsp-1A8h]
0x14002cfb9  sub     rsp, 2A8h
0x14002cfc0  mov     rax, cs:__security_cookie
0x14002cfc7  xor     rax, rsp
0x14002cfca  mov     [rbp+1E0h+var_50], rax
0x14002cfd1  xorps   xmm0, xmm0
0x14002cfd4  mov     qword ptr [rsp+2E0h+CreationTime.dwLowDateTime], 0
0x14002cfdd  xorps   xmm1, xmm1
0x14002cfe0  mov     qword ptr [rsp+2E0h+LastWriteTime.dwLowDateTime], 0
0x14002cfe9  xor     r15d, r15d
0x14002cfec  mov     esi, ecx
0x14002cfee  movups  xmmword ptr [rsp+2E0h+SystemTime.wYear], xmm0
0x14002cff3  xor     r14d, r14d
0x14002cff6  movups  xmmword ptr [rsp+2E0h+var_280.wYear], xmm1
0x14002cffb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d002  lea     r13, WPP_GLOBAL_Control
0x14002d009  mov     r12b, 4
0x14002d00c  cmp     rcx, r13
0x14002d00f  jz      short loc_14002D031
0x14002d011  test    [rcx+1Ch], r12b
0x14002d015  jz      short loc_14002D031
0x14002d017  cmp     byte ptr [rcx+19h], 5
0x14002d01b  jb      short loc_14002D031
0x14002d01d  mov     rcx, [rcx+10h]
0x14002d021  lea     edx, [r15+6Ah]
0x14002d025  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002d02c  call    WPP_SF_
0x14002d031  mov     rcx, cs:?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x14002d038  lea     rax, ?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x14002d03f  test    esi, esi
0x14002d041  lea     rdi, ?g_hInboxActivityLogFile@@3PEAXEA; void * g_hInboxActivityLogFile
0x14002d048  lea     r9, [rsp+2E0h+LastWriteTime]; lpLastWriteTime
0x14002d04d  cmovz   rcx, cs:?g_hInboxActivityLogFile@@3PEAXEA; hFile
0x14002d055  lea     rdx, [rsp+2E0h+CreationTime]; lpCreationTime
0x14002d05a  cmovnz  rdi, rax
0x14002d05e  xor     r8d, r8d; lpLastAccessTime
0x14002d061  call    cs:__imp_GetFileTime
0x14002d068  nop     dword ptr [rax+rax+00h]
0x14002d06d  test    eax, eax
0x14002d06f  jnz     short loc_14002D0C0
0x14002d071  call    cs:__imp_GetLastError
0x14002d078  nop     dword ptr [rax+rax+00h]
0x14002d07d  mov     ebx, eax
0x14002d07f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d086  cmp     rcx, r13
0x14002d089  jz      loc_14002D3F8
0x14002d08f  test    [rcx+1Ch], r12b
0x14002d093  jz      loc_14002D3F8
0x14002d099  cmp     byte ptr [rcx+19h], 2
0x14002d09d  jb      loc_14002D3F8
0x14002d0a3  mov     edx, 6Bh ; 'k'
0x14002d0a8  mov     rcx, [rcx+10h]
0x14002d0ac  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002d0b3  mov     r9d, eax
0x14002d0b6  call    WPP_SF_d
0x14002d0bb  jmp     loc_14002D3F8
0x14002d0c0  lea     rdx, [rsp+2E0h+SystemTime]; lpSystemTime
0x14002d0c5  lea     rcx, [rsp+2E0h+CreationTime]; lpFileTime
0x14002d0ca  call    cs:__imp_FileTimeToSystemTime
0x14002d0d1  nop     dword ptr [rax+rax+00h]
0x14002d0d6  test    eax, eax
0x14002d0d8  jnz     short loc_14002D113
0x14002d0da  call    cs:__imp_GetLastError
0x14002d0e1  nop     dword ptr [rax+rax+00h]
0x14002d0e6  mov     ebx, eax
0x14002d0e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d0ef  cmp     rcx, r13
0x14002d0f2  jz      loc_14002D3F8
0x14002d0f8  test    [rcx+1Ch], r12b
0x14002d0fc  jz      loc_14002D3F8
0x14002d102  cmp     byte ptr [rcx+19h], 2
0x14002d106  jb      loc_14002D3F8
0x14002d10c  mov     edx, 6Ch ; 'l'
0x14002d111  jmp     short loc_14002D0A8
0x14002d113  lea     rdx, [rsp+2E0h+var_280]; lpSystemTime
0x14002d118  lea     rcx, [rsp+2E0h+LastWriteTime]; lpFileTime
0x14002d11d  call    cs:__imp_FileTimeToSystemTime
0x14002d124  nop     dword ptr [rax+rax+00h]
0x14002d129  test    eax, eax
0x14002d12b  jnz     short loc_14002D169
0x14002d12d  call    cs:__imp_GetLastError
0x14002d134  nop     dword ptr [rax+rax+00h]
0x14002d139  mov     ebx, eax
0x14002d13b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d142  cmp     rcx, r13
0x14002d145  jz      loc_14002D3F8
0x14002d14b  test    [rcx+1Ch], r12b
0x14002d14f  jz      loc_14002D3F8
0x14002d155  cmp     byte ptr [rcx+19h], 2
0x14002d159  jb      loc_14002D3F8
0x14002d15f  mov     edx, 6Dh ; 'm'
0x14002d164  jmp     loc_14002D0A8
0x14002d169  mov     rcx, qword ptr cs:fDesiredAccess
0x14002d170  lea     rax, aOutboxlogTxt; "OutboxLOG.txt"
0x14002d177  test    esi, esi
0x14002d179  lea     rdx, aInboxlogTxt; "InboxLOG.txt"
0x14002d180  cmovnz  rdx, rax
0x14002d184  call    BuildFullFileName
0x14002d189  mov     r15, rax
0x14002d18c  test    rax, rax
0x14002d18f  jnz     short loc_14002D1C0
0x14002d191  lea     ebx, [rax+8]
0x14002d194  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d19b  cmp     rcx, r13
0x14002d19e  jz      loc_14002D3F8
0x14002d1a4  test    [rcx+1Ch], r12b
0x14002d1a8  jz      loc_14002D3F8
0x14002d1ae  cmp     byte ptr [rcx+19h], 2
0x14002d1b2  jb      loc_14002D3F8
0x14002d1b8  lea     edx, [rax+6Eh]
0x14002d1bb  jmp     loc_14002D3E8
0x14002d1c0  movzx   ecx, [rsp+2E0h+var_280.wMonth]
0x14002d1c5  lea     rbx, aOutboxlog04d02; "OutboxLOG %04d-%02d-%02d - %04d-%02d-%0"...
0x14002d1cc  movzx   edx, [rsp+2E0h+var_280.wYear]
0x14002d1d1  lea     r8, aInboxlog04d02d; "InboxLOG %04d-%02d-%02d - %04d-%02d-%02"...
0x14002d1d8  movzx   eax, [rsp+2E0h+var_280.wDay]
0x14002d1dd  test    esi, esi
0x14002d1df  movzx   r10d, [rsp+2E0h+SystemTime.wDay]
0x14002d1e5  movzx   r11d, [rsp+2E0h+SystemTime.wMonth]
0x14002d1eb  cmovnz  r8, rbx; unsigned __int16 *
0x14002d1ef  movzx   r9d, [rsp+2E0h+SystemTime.wYear]
0x14002d1f5  mov     [rsp+2E0h+var_2A0], eax
0x14002d1f9  mov     [rsp+2E0h+var_2A8], ecx
0x14002d1fd  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x14002d201  mov     [rsp+2E0h+var_2B0], edx
0x14002d205  mov     edx, 104h; unsigned __int64
0x14002d20a  mov     [rsp+2E0h+fFlagsAndAttributes], r10d; fFlagsAndAttributes
0x14002d20f  mov     [rsp+2E0h+fCreateDisposition], r11d; fCreateDisposition
0x14002d214  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002d219  mov     ebx, eax
0x14002d21b  test    eax, eax
0x14002d21d  jns     short loc_14002D269
0x14002d21f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d226  cmp     rcx, r13
0x14002d229  jz      short loc_14002D24F
0x14002d22b  test    [rcx+1Ch], r12b
0x14002d22f  jz      short loc_14002D24F
0x14002d231  cmp     byte ptr [rcx+19h], 2
0x14002d235  jb      short loc_14002D24F
0x14002d237  mov     rcx, [rcx+10h]
0x14002d23b  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002d242  mov     edx, 6Fh ; 'o'
0x14002d247  mov     r9d, eax
0x14002d24a  call    WPP_SF_d
0x14002d24f  mov     eax, ebx
0x14002d251  and     eax, 1FFF0000h
0x14002d256  cmp     eax, 70000h
0x14002d25b  jnz     loc_14002D3F8
0x14002d261  movzx   ebx, bx
0x14002d264  jmp     loc_14002D3F8
0x14002d269  mov     rcx, qword ptr cs:fDesiredAccess
0x14002d270  lea     rdx, [rbp+1E0h+var_260]
0x14002d274  call    BuildFullFileName
0x14002d279  mov     r14, rax
0x14002d27c  test    rax, rax
0x14002d27f  jnz     short loc_14002D2B0
0x14002d281  lea     ebx, [rax+8]
0x14002d284  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d28b  cmp     rcx, r13
0x14002d28e  jz      loc_14002D3F8
0x14002d294  test    [rcx+1Ch], r12b
0x14002d298  jz      loc_14002D3F8
0x14002d29e  cmp     byte ptr [rcx+19h], 2
0x14002d2a2  jb      loc_14002D3F8
0x14002d2a8  lea     edx, [rax+70h]
0x14002d2ab  jmp     loc_14002D3E8
0x14002d2b0  mov     rcx, [rdi]; hObject
0x14002d2b3  call    cs:__imp_CloseHandle
0x14002d2ba  nop     dword ptr [rax+rax+00h]
0x14002d2bf  test    eax, eax
0x14002d2c1  jnz     short loc_14002D2FF
0x14002d2c3  call    cs:__imp_GetLastError
0x14002d2ca  nop     dword ptr [rax+rax+00h]
0x14002d2cf  mov     ebx, eax
0x14002d2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d2d8  cmp     rcx, r13
0x14002d2db  jz      loc_14002D3F8
0x14002d2e1  test    [rcx+1Ch], r12b
0x14002d2e5  jz      loc_14002D3F8
0x14002d2eb  cmp     byte ptr [rcx+19h], 2
0x14002d2ef  jb      loc_14002D3F8
0x14002d2f5  mov     edx, 71h ; 'q'
0x14002d2fa  jmp     loc_14002D0A8
0x14002d2ff  mov     rdx, r14; lpNewFileName
0x14002d302  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14002d309  mov     rcx, r15; lpExistingFileName
0x14002d30c  call    cs:__imp_MoveFileW
0x14002d313  nop     dword ptr [rax+rax+00h]
0x14002d318  test    eax, eax
0x14002d31a  jnz     short loc_14002D358
0x14002d31c  call    cs:__imp_GetLastError
0x14002d323  nop     dword ptr [rax+rax+00h]
0x14002d328  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d32f  cmp     rcx, r13
0x14002d332  jz      short loc_14002D358
0x14002d334  test    [rcx+1Ch], r12b
0x14002d338  jz      short loc_14002D358
0x14002d33a  cmp     byte ptr [rcx+19h], 2
0x14002d33e  jb      short loc_14002D358
0x14002d340  mov     rcx, [rcx+10h]
0x14002d344  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002d34b  mov     edx, 72h ; 'r'
0x14002d350  mov     r9d, eax
0x14002d353  call    WPP_SF_d
0x14002d358  mov     rdx, qword ptr cs:fDesiredAccess; fDesiredAccess
0x14002d35f  mov     r8, rdi; dwShareMode
0x14002d362  mov     ecx, esi; pszLogFileName
0x14002d364  call    CreateLogFile
0x14002d369  mov     ebx, eax
0x14002d36b  test    eax, eax
0x14002d36d  jz      short loc_14002D391
0x14002d36f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d376  cmp     rcx, r13
0x14002d379  jz      short loc_14002D3F8
0x14002d37b  test    [rcx+1Ch], r12b
0x14002d37f  jz      short loc_14002D3F8
0x14002d381  cmp     byte ptr [rcx+19h], 2
0x14002d385  jb      short loc_14002D3F8
0x14002d387  mov     edx, 73h ; 's'
0x14002d38c  jmp     loc_14002D0A8
0x14002d391  mov     rcx, [rdi]; hFile
0x14002d394  call    SetFileToCurrentTime
0x14002d399  test    eax, eax
0x14002d39b  jnz     short loc_14002D3CB
0x14002d39d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d3a4  cmp     rcx, r13
0x14002d3a7  jz      short loc_14002D3F8
0x14002d3a9  test    [rcx+1Ch], r12b
0x14002d3ad  jz      short loc_14002D3D2
0x14002d3af  cmp     byte ptr [rcx+19h], 2
0x14002d3b3  jb      short loc_14002D3D2
0x14002d3b5  mov     rcx, [rcx+10h]
0x14002d3b9  lea     edx, [rax+74h]
0x14002d3bc  xor     r9d, r9d
0x14002d3bf  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002d3c6  call    WPP_SF_d
0x14002d3cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d3d2  cmp     rcx, r13
0x14002d3d5  jz      short loc_14002D3F8
0x14002d3d7  test    [rcx+1Ch], r12b
0x14002d3db  jz      short loc_14002D3F8
0x14002d3dd  cmp     byte ptr [rcx+19h], 5
0x14002d3e1  jb      short loc_14002D3F8
0x14002d3e3  mov     edx, 75h ; 'u'
0x14002d3e8  mov     rcx, [rcx+10h]
0x14002d3ec  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002d3f3  call    WPP_SF_
0x14002d3f8  mov     rcx, r15; lpMem
0x14002d3fb  call    pMemFree
0x14002d400  mov     rcx, r14; lpMem
0x14002d403  call    pMemFree
0x14002d408  mov     eax, ebx
0x14002d40a  mov     rcx, [rbp+1E0h+var_50]
0x14002d411  xor     rcx, rsp; StackCookie
0x14002d414  call    __security_check_cookie
0x14002d419  add     rsp, 2A8h
0x14002d420  pop     r15
0x14002d422  pop     r14
0x14002d424  pop     r13
0x14002d426  pop     r12
0x14002d428  pop     rdi
0x14002d429  pop     rsi
0x14002d42a  pop     rbx
0x14002d42b  pop     rbp
0x14002d42c  retn
```
