# CONFIG_HISTORY_ENTITY::SnapshotConfig(void)

- ea: `0x180004b0c`
- end: `0x180004d91`
- name: `?SnapshotConfig@CONFIG_HISTORY_ENTITY@@QEAAJXZ`
- size: `645`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004014`

## callees

- `0x1800043ec`
- `0x180004528`
- `0x180004894`
- `0x180004b0c`
- `0x180004d98`
- `0x180005110`
- `0x180008c1f`
- `0x180008c50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180004beb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180004beb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d56`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d62`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d6e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d56`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d62`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d6e`
- `iisutil!PuDbgPrintError` at `0x180004d2b`
- `iisutil!PuDbgPrintError` at `0x180004d2b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004c33`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004c33`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004b58`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004b7f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004ba5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004b58`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004b7f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004ba5`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180004d38`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180004d38`

## string_xrefs

- `0x180004c77`: `BackupFile() failed to copy applicationHost.config.`
- `0x180004d16`: `CONFIG_HISTORY_ENTITY::SnapshotConfig`
- `0x180004d1d`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history_entity.cxx`
- `0x180004cc9`: `BackupFile() failed to copy administration.config.`
- `0x180004d00`: `SnapshotCustomConfig failed.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CONFIG_HISTORY_ENTITY::SnapshotConfig(const unsigned __int16 **this)
{
  unsigned int v2; // esi
  signed int Path; // ebx
  signed int LastError; // eax
  CONFIG_HISTORY_ENTITY *v5; // rcx
  const unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // r9
  int v8; // eax
  CONFIG_HISTORY_ENTITY *v9; // rcx
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpPathName; // [rsp+50h] [rbp-B0h]
  _BYTE v14[32]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v15; // [rsp+88h] [rbp-78h]
  _BYTE v16[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v17[264]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v18[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v19[264]; // [rsp+500h] [rbp+400h] BYREF

  memset_0(v17, 0, 0x208u);
  STRU::STRU((STRU *)v12, v17, 0x104u);
  memset_0(v18, 0, 0x208u);
  STRU::STRU((STRU *)v14, v18, 0x104u);
  memset_0(v19, 0, 0x208u);
  STRU::STRU((STRU *)v16, v19, 0x104u);
  if ( *((_DWORD *)this + 72) >= *((_DWORD *)this + 71) )
    CONFIG_HISTORY_ENTITY::TrimHistory((CONFIG_HISTORY_ENTITY *)this);
  v2 = *((_DWORD *)this + 74);
  do
  {
    Path = CONFIG_HISTORY_ENTITY::MakePath((CONFIG_HISTORY_ENTITY *)this, (struct STRU *)v12, ++v2);
    if ( Path < 0 )
      goto LABEL_30;
    if ( CreateDirectoryW(lpPathName, 0) )
    {
      if ( (int)STRU::Copy((STRU *)v14, lpPathName) >= 0 )
      {
        v6 = &word_18000C2BC;
        v7 = &word_18000C2BC;
        if ( this[26] )
          v7 = this[26];
        v8 = CONFIG_HISTORY_ENTITY::BackupFile(v5, v15, this[13], v7);
        if ( v8 >= 0 )
        {
          if ( !*((_DWORD *)this + 70) )
            goto LABEL_25;
          if ( this[25] )
            v6 = this[25];
          v10 = CONFIG_HISTORY_ENTITY::BackupFile(v9, v15, this[21], v6);
          if ( v10 < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history_entity.cxx",
                784,
                "CONFIG_HISTORY_ENTITY::SnapshotConfig",
                v10,
                "BackupFile() failed to copy administration.config.");
          }
          else
          {
LABEL_25:
            *((_DWORD *)this + 74) = v2;
            Path = CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles((CONFIG_HISTORY_ENTITY *)this, v2);
            if ( Path >= 0 )
              goto LABEL_30;
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history_entity.cxx",
                803,
                "CONFIG_HISTORY_ENTITY::SnapshotConfig",
                Path,
                "SnapshotCustomConfig failed.\n");
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history_entity.cxx",
            762,
            "CONFIG_HISTORY_ENTITY::SnapshotConfig",
            v8,
            "BackupFile() failed to copy applicationHost.config.");
        }
      }
      goto LABEL_28;
    }
    LastError = GetLastError();
  }
  while ( LastError == 183 );
  if ( LastError != 3 )
  {
    Path = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
    if ( Path < 0 )
    {
LABEL_28:
      Path = STRU::Append((STRU *)v12, 0);
      if ( Path >= 0 )
        CONFIG_HISTORY_ENTITY::DeleteDirectory((CONFIG_HISTORY_ENTITY *)this, lpPathName);
    }
  }
LABEL_30:
  STRU::~STRU((STRU *)v16);
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v12);
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x180004b0c  push    rbp
0x180004b0e  push    rbx
0x180004b0f  push    rsi
0x180004b10  push    rdi
0x180004b11  lea     rbp, [rsp-628h]
0x180004b19  sub     rsp, 728h
0x180004b20  mov     rax, cs:__security_cookie
0x180004b27  xor     rax, rsp
0x180004b2a  mov     [rbp+640h+var_30], rax
0x180004b31  mov     rdi, rcx
0x180004b34  mov     esi, 208h
0x180004b39  mov     r8d, esi; Size
0x180004b3c  xor     edx, edx; Val
0x180004b3e  lea     rcx, [rbp+640h+var_660]; void *
0x180004b42  call    memset_0
0x180004b47  mov     ebx, 104h
0x180004b4c  mov     r8d, ebx
0x180004b4f  lea     rdx, [rbp+640h+var_660]
0x180004b53  lea     rcx, [rsp+740h+var_710]
0x180004b58  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004b5e  nop
0x180004b5f  mov     r8d, esi; Size
0x180004b62  xor     edx, edx; Val
0x180004b64  lea     rcx, [rbp+640h+var_450]; void *
0x180004b6b  call    memset_0
0x180004b70  mov     r8d, ebx
0x180004b73  lea     rdx, [rbp+640h+var_450]
0x180004b7a  lea     rcx, [rsp+740h+var_6D8]
0x180004b7f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004b85  nop
0x180004b86  mov     r8d, esi; Size
0x180004b89  xor     edx, edx; Val
0x180004b8b  lea     rcx, [rbp+640h+var_240]; void *
0x180004b92  call    memset_0
0x180004b97  mov     r8d, ebx
0x180004b9a  lea     rdx, [rbp+640h+var_240]
0x180004ba1  lea     rcx, [rbp+640h+var_6A0]
0x180004ba5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004bab  nop
0x180004bac  mov     eax, [rdi+11Ch]
0x180004bb2  cmp     [rdi+120h], eax
0x180004bb8  jb      short loc_180004BC2
0x180004bba  mov     rcx, rdi; this
0x180004bbd  call    ?TrimHistory@CONFIG_HISTORY_ENTITY@@QEAAJXZ; CONFIG_HISTORY_ENTITY::TrimHistory(void)
0x180004bc2  mov     esi, [rdi+128h]
0x180004bc8  inc     esi
0x180004bca  mov     r8d, esi; unsigned int
0x180004bcd  lea     rdx, [rsp+740h+var_710]; struct STRU *
0x180004bd2  mov     rcx, rdi; this
0x180004bd5  call    ?MakePath@CONFIG_HISTORY_ENTITY@@QEAAJPEAVSTRU@@K@Z; CONFIG_HISTORY_ENTITY::MakePath(STRU *,ulong)
0x180004bda  mov     ebx, eax
0x180004bdc  test    eax, eax
0x180004bde  js      loc_180004D52
0x180004be4  xor     edx, edx; lpSecurityAttributes
0x180004be6  mov     rcx, [rsp+740h+lpPathName]; lpPathName
0x180004beb  call    cs:__imp_CreateDirectoryW
0x180004bf1  test    eax, eax
0x180004bf3  jnz     short loc_180004C29
0x180004bf5  call    cs:__imp_GetLastError
0x180004bfb  cmp     eax, 0B7h
0x180004c00  jz      short loc_180004BC8
0x180004c02  cmp     eax, 3
0x180004c05  jz      loc_180004D52
0x180004c0b  test    eax, eax
0x180004c0d  jg      short loc_180004C13
0x180004c0f  mov     ebx, eax
0x180004c11  jmp     short loc_180004C1C
0x180004c13  movzx   ebx, ax
0x180004c16  or      ebx, 80070000h
0x180004c1c  test    ebx, ebx
0x180004c1e  js      loc_180004D31
0x180004c24  jmp     loc_180004D52
0x180004c29  mov     rdx, [rsp+740h+lpPathName]
0x180004c2e  lea     rcx, [rsp+740h+var_6D8]
0x180004c33  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004c39  test    eax, eax
0x180004c3b  js      loc_180004D31
0x180004c41  mov     rax, [rdi+0D0h]
0x180004c48  lea     rbx, word_18000C2BC
0x180004c4f  mov     r9, rbx
0x180004c52  test    rax, rax
0x180004c55  cmovnz  r9, rax; unsigned __int16 *
0x180004c59  mov     r8, [rdi+68h]; unsigned __int16 *
0x180004c5d  mov     rdx, [rbp+640h+var_6B8]; unsigned __int16 *
0x180004c61  call    ?BackupFile@CONFIG_HISTORY_ENTITY@@QEAAJPEBG00@Z; CONFIG_HISTORY_ENTITY::BackupFile(ushort const *,ushort const *,ushort const *)
0x180004c66  test    eax, eax
0x180004c68  jns     short loc_180004C92
0x180004c6a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004c71  jz      loc_180004D31
0x180004c77  lea     rcx, aBackupfileFail; "BackupFile() failed to copy application"...
0x180004c7e  mov     [rsp+740h+var_718], rcx
0x180004c83  mov     [rsp+740h+var_720], eax
0x180004c87  mov     r8d, 2FAh
0x180004c8d  jmp     loc_180004D16
0x180004c92  cmp     dword ptr [rdi+118h], 0
0x180004c99  jz      short loc_180004CE1
0x180004c9b  mov     rax, [rdi+0C8h]
0x180004ca2  test    rax, rax
0x180004ca5  cmovnz  rbx, rax
0x180004ca9  mov     r9, rbx; unsigned __int16 *
0x180004cac  mov     r8, [rdi+0A8h]; unsigned __int16 *
0x180004cb3  mov     rdx, [rbp+640h+var_6B8]; unsigned __int16 *
0x180004cb7  call    ?BackupFile@CONFIG_HISTORY_ENTITY@@QEAAJPEBG00@Z; CONFIG_HISTORY_ENTITY::BackupFile(ushort const *,ushort const *,ushort const *)
0x180004cbc  test    eax, eax
0x180004cbe  jns     short loc_180004CE1
0x180004cc0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004cc7  jz      short loc_180004D31
0x180004cc9  lea     rcx, aBackupfileFail_0; "BackupFile() failed to copy administrat"...
0x180004cd0  mov     [rsp+740h+var_718], rcx
0x180004cd5  mov     [rsp+740h+var_720], eax
0x180004cd9  mov     r8d, 310h
0x180004cdf  jmp     short loc_180004D16
0x180004ce1  mov     [rdi+128h], esi
0x180004ce7  mov     edx, esi; unsigned int
0x180004ce9  mov     rcx, rdi; this
0x180004cec  call    ?SnapshotSchemaFiles@CONFIG_HISTORY_ENTITY@@QEAAJK@Z; CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles(ulong)
0x180004cf1  mov     ebx, eax
0x180004cf3  test    eax, eax
0x180004cf5  jns     short loc_180004D52
0x180004cf7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004cfe  jz      short loc_180004D31
0x180004d00  lea     rax, aSnapshotcustom; "SnapshotCustomConfig failed.\n"
0x180004d07  mov     [rsp+740h+var_718], rax
0x180004d0c  mov     [rsp+740h+var_720], ebx
0x180004d10  mov     r8d, 323h
0x180004d16  lea     r9, aConfigHistoryE_1; "CONFIG_HISTORY_ENTITY::SnapshotConfig"
0x180004d1d  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180004d24  mov     rcx, cs:g_pDebug
0x180004d2b  call    cs:__imp_PuDbgPrintError
0x180004d31  xor     edx, edx
0x180004d33  lea     rcx, [rsp+740h+var_710]
0x180004d38  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180004d3e  mov     ebx, eax
0x180004d40  test    eax, eax
0x180004d42  js      short loc_180004D52
0x180004d44  mov     rdx, [rsp+740h+lpPathName]; unsigned __int16 *
0x180004d49  mov     rcx, rdi; this
0x180004d4c  call    ?DeleteDirectory@CONFIG_HISTORY_ENTITY@@QEAAJPEBG@Z; CONFIG_HISTORY_ENTITY::DeleteDirectory(ushort const *)
0x180004d51  nop
0x180004d52  lea     rcx, [rbp+640h+var_6A0]
0x180004d56  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004d5c  nop
0x180004d5d  lea     rcx, [rsp+740h+var_6D8]
0x180004d62  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004d68  nop
0x180004d69  lea     rcx, [rsp+740h+var_710]
0x180004d6e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004d74  mov     eax, ebx
0x180004d76  mov     rcx, [rbp+640h+var_30]
0x180004d7d  xor     rcx, rsp; StackCookie
0x180004d80  call    __security_check_cookie
0x180004d85  add     rsp, 728h
0x180004d8c  pop     rdi
0x180004d8d  pop     rsi
0x180004d8e  pop     rbx
0x180004d8f  pop     rbp
0x180004d90  retn
```
