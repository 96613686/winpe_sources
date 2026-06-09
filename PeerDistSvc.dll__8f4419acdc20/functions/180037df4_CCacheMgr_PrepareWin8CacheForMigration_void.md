# CCacheMgr::PrepareWin8CacheForMigration(void)

- ea: `0x180037df4`
- end: `0x180038307`
- name: `?PrepareWin8CacheForMigration@CCacheMgr@@QEAAKXZ`
- size: `1299`
- prototype: `unsigned int __fastcall(CCacheMgr *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180038b50`

## callees

- `0x180008290`
- `0x1800094d4`
- `0x180009ec4`
- `0x18000ceac`
- `0x18000cf48`
- `0x1800183a0`
- `0x180037df4`
- `0x1800391e0`
- `0x180114ae0`
- `0x180115578`
- `0x180116428`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003807d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003818f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003807d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003818f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038222`
- `KERNEL32!CloseHandle` at `0x1800381da`
- `KERNEL32!CloseHandle` at `0x18003820d`
- `KERNEL32!CloseHandle` at `0x1800381da`
- `KERNEL32!CloseHandle` at `0x18003820d`
- `KERNEL32!CreateFileW` at `0x18003806d`
- `KERNEL32!CreateFileW` at `0x180038183`
- `KERNEL32!CreateFileW` at `0x18003806d`
- `KERNEL32!CreateFileW` at `0x180038183`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180038218`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180038218`

## pseudocode

```c
__int64 __fastcall CCacheMgr::PrepareWin8CacheForMigration(CCacheMgr *this)
{
  unsigned __int16 *v1; // r14
  unsigned int CacheFolderPath; // eax
  DWORD LastError; // ebx
  CHostedCacheMsgEncoding *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  CHostedCacheMsgEncoding *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  HANDLE FileW; // rax
  int v12; // eax
  HANDLE v13; // rax
  DWORD v15; // eax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v18[264]; // [rsp+250h] [rbp+150h] BYREF

  v1 = (unsigned __int16 *)((char *)this + 130);
  *((_WORD *)this + 65) = 0;
  CacheFolderPath = GetCacheFolderPath(*((__int64 **)this + 5), 85, L"PeerDistRepub", 0, v18, dwFlagsAndAttributes);
  LastError = CacheFolderPath;
  if ( CacheFolderPath )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v6 = 47;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v5 + 12), v6, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids, CacheFolderPath);
      return LastError;
    }
    return LastError;
  }
  v7 = StringCchCopyW(FileName, 0x104u, v18);
  if ( v7 < 0 )
  {
    LastError = TnoWin32ErrFromHR(v7);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return LastError;
    }
    v9 = 48;
    goto LABEL_12;
  }
  CacheFolderPath = AppendFilePath(FileName, L"PeerDistRepubCatalog.pds");
  LastError = CacheFolderPath;
  if ( !CacheFolderPath )
  {
    v10 = StringCchCopyW(v1, 0x104u, v18);
    if ( v10 < 0 )
    {
      LastError = TnoWin32ErrFromHR(v10);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return LastError;
      }
      v9 = 50;
      goto LABEL_12;
    }
    CacheFolderPath = AppendFilePath(v1, L"Migrate");
    LastError = CacheFolderPath;
    if ( CacheFolderPath )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v6 = 51;
        goto LABEL_6;
      }
      return LastError;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        52,
        (unsigned int)WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids,
        (unsigned int)v18,
        (__int64)FileName);
    }
    FileW = CreateFileW(FileName, 0x80010000, 0, 0, 3u, 0x10000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            53,
            (unsigned int)WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids,
            LastError,
            (__int64)FileName);
        }
        v12 = StringCchCopyW(FileName, 0x104u, v1);
        if ( v12 < 0 )
        {
          LastError = TnoWin32ErrFromHR(v12);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            return LastError;
          }
          v9 = 54;
LABEL_12:
          WPP_SF_Dd(*((_QWORD *)v8 + 12), v9, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids);
          return LastError;
        }
        CacheFolderPath = AppendFilePath(FileName, L"PeerDistRepubCatalog.pds");
        LastError = CacheFolderPath;
        if ( CacheFolderPath )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v6 = 55;
            goto LABEL_6;
          }
          return LastError;
        }
        v13 = CreateFileW(FileName, 0x80010000, 0, 0, 3u, 0x10000000u, 0);
        if ( v13 == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          if ( LastError )
          {
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u )
            {
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                56,
                (unsigned int)WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids,
                LastError,
                (__int64)FileName);
            }
            return LastError;
          }
        }
        else
        {
          CloseHandle(v13);
        }
      }
    }
    else
    {
      CloseHandle(FileW);
      if ( !CreateDirectoryW(v1, 0) )
      {
        LastError = GetLastError();
        if ( LastError == 183 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              57,
              (unsigned int)WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids,
              (_DWORD)v1,
              183);
          }
        }
        else if ( LastError )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              58,
              (unsigned int)WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids,
              (_DWORD)v1,
              LastError);
          }
          return LastError;
        }
      }
      v15 = MoveCacheStore(v18, 0, v1, 0, 0);
      LastError = v15;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            59,
            (unsigned int)WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids,
            (_DWORD)v1,
            v15);
        }
        return LastError;
      }
    }
    *((_BYTE *)this + 129) = 1;
    return LastError;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v6 = 49;
    goto LABEL_6;
  }
  return LastError;
}

```

## disassembly

```asm
0x180037df4  push    rbp
0x180037df6  push    rbx
0x180037df7  push    rsi
0x180037df8  push    r13
0x180037dfa  push    r14
0x180037dfc  push    r15
0x180037dfe  lea     rbp, [rsp-378h]
0x180037e06  sub     rsp, 478h
0x180037e0d  mov     rax, cs:__security_cookie
0x180037e14  xor     rax, rsp
0x180037e17  mov     [rbp+3A0h+var_40], rax
0x180037e1e  lea     r14, [rcx+82h]
0x180037e25  xor     eax, eax
0x180037e27  xor     r9d, r9d
0x180037e2a  mov     [r14], ax
0x180037e2e  mov     r15, rcx
0x180037e31  lea     rax, [rbp+3A0h+var_250]
0x180037e38  mov     rcx, [rcx+28h]
0x180037e3c  lea     r8, ?c_wszRepublishDirName@@3QBGB; "PeerDistRepub"
0x180037e43  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x180037e48  lea     edx, [r9+55h]
0x180037e4c  call    ?GetCacheFolderPath@@YAKPEAVITnoCfgMgr@@W4cfg_mgr_reg_ids_tag@@PEBG2PEAG_NPEA_N@Z; GetCacheFolderPath(ITnoCfgMgr *,cfg_mgr_reg_ids_tag,ushort const *,ushort const *,ushort *,bool,bool *)
0x180037e51  mov     ebx, eax
0x180037e53  test    eax, eax
0x180037e55  jz      short loc_180037E9F
0x180037e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e5e  lea     rsi, WPP_GLOBAL_Control
0x180037e65  cmp     rcx, rsi
0x180037e68  jz      loc_1800381E8
0x180037e6e  test    byte ptr [rcx+6Ch], 4
0x180037e72  jz      loc_1800381E8
0x180037e78  cmp     byte ptr [rcx+69h], 1
0x180037e7c  jb      loc_1800381E8
0x180037e82  mov     edx, 2Fh ; '/'
0x180037e87  mov     rcx, [rcx+60h]
0x180037e8b  lea     r8, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids
0x180037e92  mov     r9d, eax
0x180037e95  call    WPP_SF_d
0x180037e9a  jmp     loc_1800381E8
0x180037e9f  mov     r13d, 104h
0x180037ea5  lea     r8, [rbp+3A0h+var_250]; unsigned __int16 *
0x180037eac  mov     edx, r13d; unsigned __int64
0x180037eaf  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x180037eb4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037eb9  mov     r9d, eax
0x180037ebc  test    eax, eax
0x180037ebe  jns     short loc_180037F12
0x180037ec0  mov     ecx, eax; int
0x180037ec2  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180037ec7  mov     ebx, eax
0x180037ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ed0  lea     rsi, WPP_GLOBAL_Control
0x180037ed7  cmp     rcx, rsi
0x180037eda  jz      loc_1800381E8
0x180037ee0  test    byte ptr [rcx+6Ch], 4
0x180037ee4  jz      loc_1800381E8
0x180037eea  cmp     byte ptr [rcx+69h], 1
0x180037eee  jb      loc_1800381E8
0x180037ef4  mov     edx, 30h ; '0'
0x180037ef9  mov     rcx, [rcx+60h]
0x180037efd  lea     r8, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids
0x180037f04  mov     [rsp+4A0h+dwCreationDisposition], eax
0x180037f08  call    WPP_SF_Dd
0x180037f0d  jmp     loc_1800381E8
0x180037f12  lea     rdx, ?c_wszRepubCatalogWin8FileName@@3QBGB; "PeerDistRepubCatalog.pds"
0x180037f19  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x180037f1e  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x180037f23  mov     ebx, eax
0x180037f25  test    eax, eax
0x180037f27  jz      short loc_180037F5E
0x180037f29  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f30  lea     rsi, WPP_GLOBAL_Control
0x180037f37  cmp     rcx, rsi
0x180037f3a  jz      loc_1800381E8
0x180037f40  test    byte ptr [rcx+6Ch], 4
0x180037f44  jz      loc_1800381E8
0x180037f4a  cmp     byte ptr [rcx+69h], 1
0x180037f4e  jb      loc_1800381E8
0x180037f54  mov     edx, 31h ; '1'
0x180037f59  jmp     loc_180037E87
0x180037f5e  lea     r8, [rbp+3A0h+var_250]; unsigned __int16 *
0x180037f65  mov     rdx, r13; unsigned __int64
0x180037f68  mov     rcx, r14; unsigned __int16 *
0x180037f6b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037f70  mov     r9d, eax
0x180037f73  test    eax, eax
0x180037f75  jns     short loc_180037FB5
0x180037f77  mov     ecx, eax; int
0x180037f79  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180037f7e  mov     ebx, eax
0x180037f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f87  lea     rsi, WPP_GLOBAL_Control
0x180037f8e  cmp     rcx, rsi
0x180037f91  jz      loc_1800381E8
0x180037f97  test    byte ptr [rcx+6Ch], 4
0x180037f9b  jz      loc_1800381E8
0x180037fa1  cmp     byte ptr [rcx+69h], 1
0x180037fa5  jb      loc_1800381E8
0x180037fab  mov     edx, 32h ; '2'
0x180037fb0  jmp     loc_180037EF9
0x180037fb5  lea     rdx, ?c_wszRepubCacheMigrationFolderName@@3QBGB; "Migrate"
0x180037fbc  mov     rcx, r14; unsigned __int16 *
0x180037fbf  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x180037fc4  mov     ebx, eax
0x180037fc6  test    eax, eax
0x180037fc8  jz      short loc_180037FFF
0x180037fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fd1  lea     rsi, WPP_GLOBAL_Control
0x180037fd8  cmp     rcx, rsi
0x180037fdb  jz      loc_1800381E8
0x180037fe1  test    byte ptr [rcx+6Ch], 4
0x180037fe5  jz      loc_1800381E8
0x180037feb  cmp     byte ptr [rcx+69h], 1
0x180037fef  jb      loc_1800381E8
0x180037ff5  mov     edx, 33h ; '3'
0x180037ffa  jmp     loc_180037E87
0x180037fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180038006  lea     rsi, WPP_GLOBAL_Control
0x18003800d  cmp     rcx, rsi
0x180038010  jz      short loc_180038044
0x180038012  test    byte ptr [rcx+6Ch], 4
0x180038016  jz      short loc_180038044
0x180038018  cmp     byte ptr [rcx+69h], 3
0x18003801c  jb      short loc_180038044
0x18003801e  mov     rcx, [rcx+60h]
0x180038022  lea     rax, [rsp+4A0h+FileName]
0x180038027  mov     edx, 34h ; '4'
0x18003802c  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x180038031  lea     r9, [rbp+3A0h+var_250]
0x180038038  lea     r8, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids
0x18003803f  call    WPP_SF_SS
0x180038044  mov     [rsp+4A0h+hTemplateFile], 0; hTemplateFile
0x18003804d  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x180038052  mov     [rsp+4A0h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x18003805a  xor     r9d, r9d; lpSecurityAttributes
0x18003805d  xor     r8d, r8d; dwShareMode
0x180038060  mov     [rsp+4A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180038068  mov     edx, 80010000h; dwDesiredAccess
0x18003806d  call    cs:__imp_CreateFileW
0x180038073  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038077  jnz     loc_18003820A
0x18003807d  call    cs:__imp_GetLastError
0x180038083  mov     ebx, eax
0x180038085  test    eax, eax
0x180038087  jz      loc_1800381E0
0x18003808d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038094  cmp     rcx, rsi
0x180038097  jz      short loc_1800380C7
0x180038099  test    byte ptr [rcx+6Ch], 4
0x18003809d  jz      short loc_1800380C7
0x18003809f  cmp     byte ptr [rcx+69h], 2
0x1800380a3  jb      short loc_1800380C7
0x1800380a5  mov     rcx, [rcx+60h]
0x1800380a9  lea     rax, [rsp+4A0h+FileName]
0x1800380ae  mov     edx, 35h ; '5'
0x1800380b3  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x1800380b8  mov     r9d, ebx
0x1800380bb  lea     r8, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids
0x1800380c2  call    WPP_SF_dS
0x1800380c7  mov     r8, r14; unsigned __int16 *
0x1800380ca  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x1800380cf  mov     rdx, r13; unsigned __int64
0x1800380d2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800380d7  mov     r9d, eax
0x1800380da  test    eax, eax
0x1800380dc  jns     short loc_180038115
0x1800380de  mov     ecx, eax; int
0x1800380e0  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x1800380e5  mov     ebx, eax
0x1800380e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380ee  cmp     rcx, rsi
0x1800380f1  jz      loc_1800381E8
0x1800380f7  test    byte ptr [rcx+6Ch], 4
0x1800380fb  jz      loc_1800381E8
0x180038101  cmp     byte ptr [rcx+69h], 1
0x180038105  jb      loc_1800381E8
0x18003810b  mov     edx, 36h ; '6'
0x180038110  jmp     loc_180037EF9
0x180038115  lea     rdx, ?c_wszRepubCatalogWin8FileName@@3QBGB; "PeerDistRepubCatalog.pds"
0x18003811c  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x180038121  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x180038126  mov     ebx, eax
0x180038128  test    eax, eax
0x18003812a  jz      short loc_18003815A
0x18003812c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038133  cmp     rcx, rsi
0x180038136  jz      loc_1800381E8
0x18003813c  test    byte ptr [rcx+6Ch], 4
0x180038140  jz      loc_1800381E8
0x180038146  cmp     byte ptr [rcx+69h], 1
0x18003814a  jb      loc_1800381E8
0x180038150  mov     edx, 37h ; '7'
0x180038155  jmp     loc_180037E87
0x18003815a  mov     [rsp+4A0h+hTemplateFile], 0; hTemplateFile
0x180038163  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x180038168  mov     [rsp+4A0h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180038170  xor     r9d, r9d; lpSecurityAttributes
0x180038173  xor     r8d, r8d; dwShareMode
0x180038176  mov     [rsp+4A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003817e  mov     edx, 80010000h; dwDesiredAccess
0x180038183  call    cs:__imp_CreateFileW
0x180038189  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003818d  jnz     short loc_1800381D7
0x18003818f  call    cs:__imp_GetLastError
0x180038195  mov     ebx, eax
0x180038197  test    eax, eax
0x180038199  jz      short loc_1800381E0
0x18003819b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381a2  cmp     rcx, rsi
0x1800381a5  jz      short loc_1800381E8
0x1800381a7  test    byte ptr [rcx+6Ch], 4
0x1800381ab  jz      short loc_1800381E8
0x1800381ad  cmp     byte ptr [rcx+69h], 2
0x1800381b1  jb      short loc_1800381E8
0x1800381b3  mov     rcx, [rcx+60h]
0x1800381b7  lea     rax, [rsp+4A0h+FileName]
0x1800381bc  mov     edx, 38h ; '8'
0x1800381c1  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x1800381c6  mov     r9d, ebx
0x1800381c9  lea     r8, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids
0x1800381d0  call    WPP_SF_dS
0x1800381d5  jmp     short loc_1800381E8
0x1800381d7  mov     rcx, rax; hObject
0x1800381da  call    cs:__imp_CloseHandle
0x1800381e0  mov     byte ptr [r15+81h], 1
0x1800381e8  mov     eax, ebx
0x1800381ea  mov     rcx, [rbp+3A0h+var_40]
0x1800381f1  xor     rcx, rsp; StackCookie
0x1800381f4  call    __security_check_cookie
0x1800381f9  add     rsp, 478h
0x180038200  pop     r15
0x180038202  pop     r14
0x180038204  pop     r13
0x180038206  pop     rsi
0x180038207  pop     rbx
0x180038208  pop     rbp
0x180038209  retn
0x18003820a  mov     rcx, rax; hObject
0x18003820d  call    cs:__imp_CloseHandle
0x180038213  xor     edx, edx; lpSecurityAttributes
0x180038215  mov     rcx, r14; lpPathName
0x180038218  call    cs:__imp_CreateDirectoryW
0x18003821e  test    eax, eax
0x180038220  jnz     short loc_180038269
0x180038222  call    cs:__imp_GetLastError
0x180038228  mov     ebx, eax
0x18003822a  mov     eax, 0B7h
0x18003822f  cmp     ebx, eax
0x180038231  jnz     loc_1800382BE
0x180038237  mov     rcx, cs:WPP_GLOBAL_Control
0x18003823e  cmp     rcx, rsi
0x180038241  jz      short loc_180038269
0x180038243  test    byte ptr [rcx+6Ch], 4
0x180038247  jz      short loc_180038269
0x180038249  cmp     byte ptr [rcx+69h], 4
0x18003824d  jb      short loc_180038269
0x18003824f  mov     rcx, [rcx+60h]
0x180038253  lea     edx, [rax-7Eh]
0x180038256  mov     r9, r14
0x180038259  mov     [rsp+4A0h+dwCreationDisposition], eax
0x18003825d  lea     r8, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids
0x180038264  call    WPP_SF_Sd
0x180038269  xor     r9d, r9d; void *
0x18003826c  mov     [rsp+4A0h+dwCreationDisposition], 0; unsigned int
0x180038274  mov     r8, r14; unsigned __int16 *
0x180038277  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x18003827e  xor     edx, edx; bool
0x180038280  call    ?MoveCacheStore@@YAKPEBG_N0PEAXK@Z; MoveCacheStore(ushort const *,bool,ushort const *,void *,ulong)
0x180038285  mov     ebx, eax
0x180038287  test    eax, eax
0x180038289  jz      loc_1800381E0
0x18003828f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038296  cmp     rcx, rsi
0x180038299  jz      loc_1800381E8
0x18003829f  test    byte ptr [rcx+6Ch], 4
0x1800382a3  jz      loc_1800381E8
0x1800382a9  cmp     byte ptr [rcx+69h], 1
0x1800382ad  jb      loc_1800381E8
0x1800382b3  mov     edx, 3Bh ; ';'
0x1800382b8  mov     [rsp+4A0h+dwCreationDisposition], eax
0x1800382bc  jmp     short loc_1800382EF
0x1800382be  test    ebx, ebx
0x1800382c0  jz      short loc_180038269
0x1800382c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382c9  cmp     rcx, rsi
0x1800382cc  jz      loc_1800381E8
0x1800382d2  test    byte ptr [rcx+6Ch], 4
0x1800382d6  jz      loc_1800381E8
0x1800382dc  cmp     byte ptr [rcx+69h], 1
0x1800382e0  jb      loc_1800381E8
0x1800382e6  mov     edx, 3Ah ; ':'
0x1800382eb  mov     [rsp+4A0h+dwCreationDisposition], ebx
0x1800382ef  mov     rcx, [rcx+60h]
0x1800382f3  lea     r8, WPP_31ee99573c7e3c63a58af28c6249f9de_Traceguids
0x1800382fa  mov     r9, r14
0x1800382fd  call    WPP_SF_Sd
0x180038302  jmp     loc_1800381E8
```
