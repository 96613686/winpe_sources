# ReplaceLogActivityFile

- ea: `0x14002bb00`
- end: `0x14002bf4d`
- name: `ReplaceLogActivityFile`
- size: `1101`
- prototype: `__int64 __fastcall(LPCWSTR pszLogFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002b3d0`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x14002793c`
- `0x140027f80`
- `0x14002bb00`
- `0x14002bf54`
- `0x140065dbc`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002bbc7`
- `KERNEL32!GetLastError` at `0x14002bc24`
- `KERNEL32!GetLastError` at `0x14002bc6b`
- `KERNEL32!GetLastError` at `0x14002bdf5`
- `KERNEL32!GetLastError` at `0x14002be42`
- `KERNEL32!GetLastError` at `0x14002bbc7`
- `KERNEL32!GetLastError` at `0x14002bc24`
- `KERNEL32!GetLastError` at `0x14002bc6b`
- `KERNEL32!GetLastError` at `0x14002bdf5`
- `KERNEL32!GetLastError` at `0x14002be42`
- `KERNEL32!FileTimeToSystemTime` at `0x14002bc1a`
- `KERNEL32!FileTimeToSystemTime` at `0x14002bc61`
- `KERNEL32!FileTimeToSystemTime` at `0x14002bc1a`
- `KERNEL32!FileTimeToSystemTime` at `0x14002bc61`
- `KERNEL32!CloseHandle` at `0x14002bdeb`
- `KERNEL32!CloseHandle` at `0x14002bdeb`
- `KERNEL32!GetFileTime` at `0x14002bbbd`
- `KERNEL32!GetFileTime` at `0x14002bbbd`
- `KERNEL32!MoveFileW` at `0x14002be38`
- `KERNEL32!MoveFileW` at `0x14002be38`

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
0x14002bb00  push    rbp
0x14002bb02  push    rbx
0x14002bb03  push    rsi
0x14002bb04  push    rdi
0x14002bb05  push    r12
0x14002bb07  push    r13
0x14002bb09  push    r14
0x14002bb0b  push    r15
0x14002bb0d  lea     rbp, [rsp-1A8h]
0x14002bb15  sub     rsp, 2A8h
0x14002bb1c  mov     rax, cs:__security_cookie
0x14002bb23  xor     rax, rsp
0x14002bb26  mov     [rbp+1E0h+var_50], rax
0x14002bb2d  xorps   xmm0, xmm0
0x14002bb30  mov     qword ptr [rsp+2E0h+CreationTime.dwLowDateTime], 0
0x14002bb39  xorps   xmm1, xmm1
0x14002bb3c  mov     qword ptr [rsp+2E0h+LastWriteTime.dwLowDateTime], 0
0x14002bb45  xor     r15d, r15d
0x14002bb48  mov     esi, ecx
0x14002bb4a  movups  xmmword ptr [rsp+2E0h+SystemTime.wYear], xmm0
0x14002bb4f  xor     r14d, r14d
0x14002bb52  movups  xmmword ptr [rsp+2E0h+var_280.wYear], xmm1
0x14002bb57  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bb5e  lea     r13, WPP_GLOBAL_Control
0x14002bb65  mov     r12b, 4
0x14002bb68  cmp     rcx, r13
0x14002bb6b  jz      short loc_14002BB8D
0x14002bb6d  test    [rcx+1Ch], r12b
0x14002bb71  jz      short loc_14002BB8D
0x14002bb73  cmp     byte ptr [rcx+19h], 5
0x14002bb77  jb      short loc_14002BB8D
0x14002bb79  mov     rcx, [rcx+10h]
0x14002bb7d  lea     edx, [r15+6Ah]
0x14002bb81  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002bb88  call    WPP_SF_
0x14002bb8d  mov     rcx, cs:?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x14002bb94  lea     rax, ?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x14002bb9b  test    esi, esi
0x14002bb9d  lea     rdi, ?g_hInboxActivityLogFile@@3PEAXEA; void * g_hInboxActivityLogFile
0x14002bba4  lea     r9, [rsp+2E0h+LastWriteTime]; lpLastWriteTime
0x14002bba9  cmovz   rcx, cs:?g_hInboxActivityLogFile@@3PEAXEA; hFile
0x14002bbb1  lea     rdx, [rsp+2E0h+CreationTime]; lpCreationTime
0x14002bbb6  cmovnz  rdi, rax
0x14002bbba  xor     r8d, r8d; lpLastAccessTime
0x14002bbbd  call    cs:__imp_GetFileTime
0x14002bbc3  test    eax, eax
0x14002bbc5  jnz     short loc_14002BC10
0x14002bbc7  call    cs:__imp_GetLastError
0x14002bbcd  mov     ebx, eax
0x14002bbcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bbd6  cmp     rcx, r13
0x14002bbd9  jz      loc_14002BF18
0x14002bbdf  test    [rcx+1Ch], r12b
0x14002bbe3  jz      loc_14002BF18
0x14002bbe9  cmp     byte ptr [rcx+19h], 2
0x14002bbed  jb      loc_14002BF18
0x14002bbf3  mov     edx, 6Bh ; 'k'
0x14002bbf8  mov     rcx, [rcx+10h]
0x14002bbfc  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002bc03  mov     r9d, eax
0x14002bc06  call    WPP_SF_d
0x14002bc0b  jmp     loc_14002BF18
0x14002bc10  lea     rdx, [rsp+2E0h+SystemTime]; lpSystemTime
0x14002bc15  lea     rcx, [rsp+2E0h+CreationTime]; lpFileTime
0x14002bc1a  call    cs:__imp_FileTimeToSystemTime
0x14002bc20  test    eax, eax
0x14002bc22  jnz     short loc_14002BC57
0x14002bc24  call    cs:__imp_GetLastError
0x14002bc2a  mov     ebx, eax
0x14002bc2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc33  cmp     rcx, r13
0x14002bc36  jz      loc_14002BF18
0x14002bc3c  test    [rcx+1Ch], r12b
0x14002bc40  jz      loc_14002BF18
0x14002bc46  cmp     byte ptr [rcx+19h], 2
0x14002bc4a  jb      loc_14002BF18
0x14002bc50  mov     edx, 6Ch ; 'l'
0x14002bc55  jmp     short loc_14002BBF8
0x14002bc57  lea     rdx, [rsp+2E0h+var_280]; lpSystemTime
0x14002bc5c  lea     rcx, [rsp+2E0h+LastWriteTime]; lpFileTime
0x14002bc61  call    cs:__imp_FileTimeToSystemTime
0x14002bc67  test    eax, eax
0x14002bc69  jnz     short loc_14002BCA1
0x14002bc6b  call    cs:__imp_GetLastError
0x14002bc71  mov     ebx, eax
0x14002bc73  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc7a  cmp     rcx, r13
0x14002bc7d  jz      loc_14002BF18
0x14002bc83  test    [rcx+1Ch], r12b
0x14002bc87  jz      loc_14002BF18
0x14002bc8d  cmp     byte ptr [rcx+19h], 2
0x14002bc91  jb      loc_14002BF18
0x14002bc97  mov     edx, 6Dh ; 'm'
0x14002bc9c  jmp     loc_14002BBF8
0x14002bca1  mov     rcx, qword ptr cs:fDesiredAccess
0x14002bca8  lea     rax, aOutboxlogTxt; "OutboxLOG.txt"
0x14002bcaf  test    esi, esi
0x14002bcb1  lea     rdx, aInboxlogTxt; "InboxLOG.txt"
0x14002bcb8  cmovnz  rdx, rax
0x14002bcbc  call    BuildFullFileName
0x14002bcc1  mov     r15, rax
0x14002bcc4  test    rax, rax
0x14002bcc7  jnz     short loc_14002BCF8
0x14002bcc9  lea     ebx, [rax+8]
0x14002bccc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bcd3  cmp     rcx, r13
0x14002bcd6  jz      loc_14002BF18
0x14002bcdc  test    [rcx+1Ch], r12b
0x14002bce0  jz      loc_14002BF18
0x14002bce6  cmp     byte ptr [rcx+19h], 2
0x14002bcea  jb      loc_14002BF18
0x14002bcf0  lea     edx, [rax+6Eh]
0x14002bcf3  jmp     loc_14002BF08
0x14002bcf8  movzx   ecx, [rsp+2E0h+var_280.wMonth]
0x14002bcfd  lea     rbx, aOutboxlog04d02; "OutboxLOG %04d-%02d-%02d - %04d-%02d-%0"...
0x14002bd04  movzx   edx, [rsp+2E0h+var_280.wYear]
0x14002bd09  lea     r8, aInboxlog04d02d; "InboxLOG %04d-%02d-%02d - %04d-%02d-%02"...
0x14002bd10  movzx   eax, [rsp+2E0h+var_280.wDay]
0x14002bd15  test    esi, esi
0x14002bd17  movzx   r10d, [rsp+2E0h+SystemTime.wDay]
0x14002bd1d  movzx   r11d, [rsp+2E0h+SystemTime.wMonth]
0x14002bd23  cmovnz  r8, rbx; unsigned __int16 *
0x14002bd27  movzx   r9d, [rsp+2E0h+SystemTime.wYear]
0x14002bd2d  mov     [rsp+2E0h+var_2A0], eax
0x14002bd31  mov     [rsp+2E0h+var_2A8], ecx
0x14002bd35  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x14002bd39  mov     [rsp+2E0h+var_2B0], edx
0x14002bd3d  mov     edx, 104h; unsigned __int64
0x14002bd42  mov     [rsp+2E0h+fFlagsAndAttributes], r10d; fFlagsAndAttributes
0x14002bd47  mov     [rsp+2E0h+fCreateDisposition], r11d; fCreateDisposition
0x14002bd4c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002bd51  mov     ebx, eax
0x14002bd53  test    eax, eax
0x14002bd55  jns     short loc_14002BDA1
0x14002bd57  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd5e  cmp     rcx, r13
0x14002bd61  jz      short loc_14002BD87
0x14002bd63  test    [rcx+1Ch], r12b
0x14002bd67  jz      short loc_14002BD87
0x14002bd69  cmp     byte ptr [rcx+19h], 2
0x14002bd6d  jb      short loc_14002BD87
0x14002bd6f  mov     rcx, [rcx+10h]
0x14002bd73  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002bd7a  mov     edx, 6Fh ; 'o'
0x14002bd7f  mov     r9d, eax
0x14002bd82  call    WPP_SF_d
0x14002bd87  mov     eax, ebx
0x14002bd89  and     eax, 1FFF0000h
0x14002bd8e  cmp     eax, 70000h
0x14002bd93  jnz     loc_14002BF18
0x14002bd99  movzx   ebx, bx
0x14002bd9c  jmp     loc_14002BF18
0x14002bda1  mov     rcx, qword ptr cs:fDesiredAccess
0x14002bda8  lea     rdx, [rbp+1E0h+var_260]
0x14002bdac  call    BuildFullFileName
0x14002bdb1  mov     r14, rax
0x14002bdb4  test    rax, rax
0x14002bdb7  jnz     short loc_14002BDE8
0x14002bdb9  lea     ebx, [rax+8]
0x14002bdbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bdc3  cmp     rcx, r13
0x14002bdc6  jz      loc_14002BF18
0x14002bdcc  test    [rcx+1Ch], r12b
0x14002bdd0  jz      loc_14002BF18
0x14002bdd6  cmp     byte ptr [rcx+19h], 2
0x14002bdda  jb      loc_14002BF18
0x14002bde0  lea     edx, [rax+70h]
0x14002bde3  jmp     loc_14002BF08
0x14002bde8  mov     rcx, [rdi]; hObject
0x14002bdeb  call    cs:__imp_CloseHandle
0x14002bdf1  test    eax, eax
0x14002bdf3  jnz     short loc_14002BE2B
0x14002bdf5  call    cs:__imp_GetLastError
0x14002bdfb  mov     ebx, eax
0x14002bdfd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002be04  cmp     rcx, r13
0x14002be07  jz      loc_14002BF18
0x14002be0d  test    [rcx+1Ch], r12b
0x14002be11  jz      loc_14002BF18
0x14002be17  cmp     byte ptr [rcx+19h], 2
0x14002be1b  jb      loc_14002BF18
0x14002be21  mov     edx, 71h ; 'q'
0x14002be26  jmp     loc_14002BBF8
0x14002be2b  mov     rdx, r14; lpNewFileName
0x14002be2e  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14002be35  mov     rcx, r15; lpExistingFileName
0x14002be38  call    cs:__imp_MoveFileW
0x14002be3e  test    eax, eax
0x14002be40  jnz     short loc_14002BE78
0x14002be42  call    cs:__imp_GetLastError
0x14002be48  mov     rcx, cs:WPP_GLOBAL_Control
0x14002be4f  cmp     rcx, r13
0x14002be52  jz      short loc_14002BE78
0x14002be54  test    [rcx+1Ch], r12b
0x14002be58  jz      short loc_14002BE78
0x14002be5a  cmp     byte ptr [rcx+19h], 2
0x14002be5e  jb      short loc_14002BE78
0x14002be60  mov     rcx, [rcx+10h]
0x14002be64  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002be6b  mov     edx, 72h ; 'r'
0x14002be70  mov     r9d, eax
0x14002be73  call    WPP_SF_d
0x14002be78  mov     rdx, qword ptr cs:fDesiredAccess; fDesiredAccess
0x14002be7f  mov     r8, rdi; dwShareMode
0x14002be82  mov     ecx, esi; pszLogFileName
0x14002be84  call    CreateLogFile
0x14002be89  mov     ebx, eax
0x14002be8b  test    eax, eax
0x14002be8d  jz      short loc_14002BEB1
0x14002be8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002be96  cmp     rcx, r13
0x14002be99  jz      short loc_14002BF18
0x14002be9b  test    [rcx+1Ch], r12b
0x14002be9f  jz      short loc_14002BF18
0x14002bea1  cmp     byte ptr [rcx+19h], 2
0x14002bea5  jb      short loc_14002BF18
0x14002bea7  mov     edx, 73h ; 's'
0x14002beac  jmp     loc_14002BBF8
0x14002beb1  mov     rcx, [rdi]; hFile
0x14002beb4  call    SetFileToCurrentTime
0x14002beb9  test    eax, eax
0x14002bebb  jnz     short loc_14002BEEB
0x14002bebd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bec4  cmp     rcx, r13
0x14002bec7  jz      short loc_14002BF18
0x14002bec9  test    [rcx+1Ch], r12b
0x14002becd  jz      short loc_14002BEF2
0x14002becf  cmp     byte ptr [rcx+19h], 2
0x14002bed3  jb      short loc_14002BEF2
0x14002bed5  mov     rcx, [rcx+10h]
0x14002bed9  lea     edx, [rax+74h]
0x14002bedc  xor     r9d, r9d
0x14002bedf  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002bee6  call    WPP_SF_d
0x14002beeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bef2  cmp     rcx, r13
0x14002bef5  jz      short loc_14002BF18
0x14002bef7  test    [rcx+1Ch], r12b
0x14002befb  jz      short loc_14002BF18
0x14002befd  cmp     byte ptr [rcx+19h], 5
0x14002bf01  jb      short loc_14002BF18
0x14002bf03  mov     edx, 75h ; 'u'
0x14002bf08  mov     rcx, [rcx+10h]
0x14002bf0c  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002bf13  call    WPP_SF_
0x14002bf18  mov     rcx, r15; lpMem
0x14002bf1b  call    pMemFree
0x14002bf20  mov     rcx, r14; lpMem
0x14002bf23  call    pMemFree
0x14002bf28  mov     eax, ebx
0x14002bf2a  mov     rcx, [rbp+1E0h+var_50]
0x14002bf31  xor     rcx, rsp; StackCookie
0x14002bf34  call    __security_check_cookie
0x14002bf39  add     rsp, 2A8h
0x14002bf40  pop     r15
0x14002bf42  pop     r14
0x14002bf44  pop     r13
0x14002bf46  pop     r12
0x14002bf48  pop     rdi
0x14002bf49  pop     rsi
0x14002bf4a  pop     rbx
0x14002bf4b  pop     rbp
0x14002bf4c  retn
```
