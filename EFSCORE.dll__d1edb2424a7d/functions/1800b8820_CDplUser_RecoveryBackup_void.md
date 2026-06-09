# CDplUser::RecoveryBackup(void)

- ea: `0x1800b8820`
- end: `0x1800b916e`
- name: `?RecoveryBackup@CDplUser@@AEAAXXZ`
- size: `2382`
- prototype: `void __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bd8c0`

## callees

- `0x180005045`
- `0x18000505d`
- `0x18000b884`
- `0x18000b8c8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x18008914c`
- `0x1800b62c0`
- `0x1800b8820`
- `0x1800b9174`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b89b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b89b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8d96`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800b8d88`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800b8d88`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800b89a2`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800b89a2`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800b8db9`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800b90ef`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800b8db9`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800b90ef`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800b8a51`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800b8a51`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800b8a08`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800b8a08`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800b8a8e`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800b8a8e`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x1800b8b22`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x1800b8b22`
- `ntdll!RtlNtStatusToDosError` at `0x1800b8a9e`
- `ntdll!RtlNtStatusToDosError` at `0x1800b8b32`
- `ntdll!RtlNtStatusToDosError` at `0x1800b8a9e`
- `ntdll!RtlNtStatusToDosError` at `0x1800b8b32`
- `RPCRT4!UuidToStringW` at `0x1800b8ed9`
- `RPCRT4!UuidToStringW` at `0x1800b8ed9`
- `RPCRT4!RpcStringFreeW` at `0x1800b8ea2`
- `RPCRT4!RpcStringFreeW` at `0x1800b9102`
- `RPCRT4!RpcStringFreeW` at `0x1800b8ea2`
- `RPCRT4!RpcStringFreeW` at `0x1800b9102`

## pseudocode

```c
void __fastcall CDplUser::RecoveryBackup(const unsigned __int16 **this)
{
  int v2; // r12d
  __int64 FirstVolumeW; // r15
  struct _LIST_ENTRY *v4; // rdi
  int v5; // ecx
  int v6; // ecx
  __int64 v7; // r8
  int RecoveryFolderPath; // ebx
  signed int LastError; // eax
  signed int v10; // eax
  int v11; // ecx
  NTSTATUS v12; // ebx
  int v13; // eax
  int v14; // ecx
  int v15; // ebx
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int DirectoryInternal; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  struct _LIST_ENTRY *Blink; // rax
  signed int v26; // eax
  const unsigned __int16 *v27; // rcx
  int v28; // ecx
  int v29; // eax
  RPC_STATUS v30; // eax
  int v31; // ecx
  int v32; // ecx
  CDplUser *v33; // rcx
  __int64 v34; // rax
  struct _LIST_ENTRY *v35; // rcx
  struct _LIST_ENTRY *v36; // rax
  char v37; // [rsp+20h] [rbp-E0h]
  char v38; // [rsp+30h] [rbp-D0h]
  RPC_WSTR String; // [rsp+40h] [rbp-C0h] BYREF
  struct _LIST_ENTRY v40; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReturnLength; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING VolumeRootPath; // [rsp+68h] [rbp-98h] BYREF
  UUID Buf1; // [rsp+78h] [rbp-88h] BYREF
  WCHAR szVolumePathNames[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v46[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v48[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 v49[264]; // [rsp+8D0h] [rbp+7D0h] BYREF
  unsigned __int16 v50[264]; // [rsp+AE0h] [rbp+9E0h] BYREF

  v2 = 0;
  String = 0;
  Buf1 = 0;
  memset_0(v48, 0, 0x208u);
  memset_0(v49, 0, 0x208u);
  FirstVolumeW = -1;
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(szVolumePathNames, 0, 0x20Au);
  cchReturnLength = 0;
  v4 = 0;
  memset_0(v50, 0, 0x208u);
  VolumeRootPath = 0;
  memset_0(v46, 0, 0x208u);
  if ( g_DplDbgBreakEnabled )
    __int2c();
  v40.Blink = &v40;
  v40.Flink = &v40;
  fnEfsLogTrace1Strings(v5, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 13);
  fnEfsLogTrace1Strings(v6, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 19);
  RecoveryFolderPath = CDplUser::MakeRecoveryFolderPath(this[13], v49, v7, 0);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              RecoveryFolderPath,
              40,
              19) < 0 )
    goto LABEL_62;
  FirstVolumeW = (__int64)FindFirstVolumeW(szVolumeName, 0x104u);
  if ( FirstVolumeW == -1 )
  {
    LastError = GetLastError();
    RecoveryFolderPath = LastError;
    if ( LastError > 0 )
      RecoveryFolderPath = (unsigned __int16)LastError | 0x80070000;
    v37 = 29;
    goto LABEL_8;
  }
  do
  {
    if ( !GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x105u, &cchReturnLength) )
    {
      v10 = GetLastError();
      RecoveryFolderPath = v10;
      if ( v10 > 0 )
        RecoveryFolderPath = (unsigned __int16)v10 | 0x80070000;
      if ( RecoveryFolderPath != -2147024662 )
      {
        v37 = 37;
        goto LABEL_8;
      }
    }
    szVolumePathNames[260] = 0;
    if ( v4 )
      DplibMemFree(v4);
    v4 = 0;
    v42 = 0;
    if ( GetDriveTypeW(szVolumePathNames) == 3 )
    {
      fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 52);
      v12 = RtlDosPathNameToNtPathName_U_WithStatus(szVolumePathNames, &VolumeRootPath, 0, 0);
      v13 = 0;
      if ( v12 < 0 )
      {
        v13 = RtlNtStatusToDosError(v12);
        if ( !v13 || v13 == 317 )
        {
          v13 = v12 | 0x10000000;
        }
        else if ( v13 > 0 )
        {
          v13 = (unsigned __int16)v13 | 0x80070000;
        }
      }
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v13,
                  40,
                  52) >= 0 )
      {
        fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 54);
        v15 = RtlCreateSystemVolumeInformationFolder(&VolumeRootPath);
        v16 = 0;
        if ( v15 < 0 )
        {
          v16 = RtlNtStatusToDosError(v15);
          if ( !v16 || v16 == 317 )
          {
            v16 = v15 | 0x10000000;
          }
          else if ( v16 > 0 )
          {
            v16 = (unsigned __int16)v16 | 0x80070000;
          }
        }
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v16,
                    40,
                    54) >= 0 )
        {
          fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 60);
          v18 = StringCchPrintfW(v46, 0x104u, L"%s%s\\EDP\\Recovery", szVolumePathNames, L"System Volume Information");
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      v18,
                      40,
                      60) >= 0 )
          {
            fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 62);
            DirectoryInternal = CDplService::CreateDirectoryInternal(v46);
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        DirectoryInternal,
                        40,
                        62) >= 0 )
            {
              fnEfsLogTrace1Strings(v21, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 64);
              v22 = DplibpMemAllocEx(536, 0, 0, &v42);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          v22,
                          40,
                          64) < 0 )
              {
                v4 = (struct _LIST_ENTRY *)v42;
              }
              else
              {
                fnEfsLogTrace1Strings(v23, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 66);
                v4 = (struct _LIST_ENTRY *)v42;
                v24 = StringCchCopyW((unsigned __int16 *)(v42 + 16), 0x104u, v46);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            v24,
                            40,
                            66) >= 0 )
                {
                  Blink = v40.Blink;
                  if ( v40.Blink->Flink != &v40 )
LABEL_69:
                    __fastfail(3u);
                  v4->Blink = v40.Blink;
                  v4->Flink = &v40;
                  Blink->Flink = v4;
                  v40.Blink = v4;
                  v4 = 0;
                }
              }
            }
          }
        }
      }
    }
  }
  while ( FindNextVolumeW((HANDLE)FirstVolumeW, szVolumeName, 0x104u) );
  v26 = GetLastError();
  RecoveryFolderPath = v26;
  if ( v26 > 0 )
    RecoveryFolderPath = (unsigned __int16)v26 | 0x80070000;
  if ( RecoveryFolderPath != -2147024878 )
  {
    v37 = 80;
LABEL_8:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, RecoveryFolderPath, 40, v37);
    goto LABEL_62;
  }
  RecoveryFolderPath = 0;
  FindVolumeClose((HANDLE)FirstVolumeW);
  FirstVolumeW = -1;
  if ( v40.Flink != &v40 )
  {
    v2 = CDplUser::UserSvcLock((CDplUser *)this);
    do
    {
      v27 = this[42];
      if ( !v27 )
        v27 = this[43];
      if ( !v27 )
        break;
      Buf1 = (UUID)*((_OWORD *)this + 21);
      v2 = CDplUser::UserSvcUnlock((CDplUser *)this, v2);
      if ( !memcmp_0(&Buf1, &xmmword_1800F7208, 0x10u) )
      {
        fnEfsLogTrace1Strings(v28, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 116);
        v29 = StringCchCopyW(v48, 0x104u, L"EdpAccount_????????-????-????-????-????????????_?");
        v38 = 116;
      }
      else
      {
        if ( String )
        {
          RpcStringFreeW(&String);
          String = 0;
        }
        fnEfsLogTrace1Strings(v28, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 129);
        v30 = UuidToStringW(&Buf1, &String);
        RecoveryFolderPath = 0;
        if ( v30 )
          RecoveryFolderPath = v30 | 0x80010000;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    RecoveryFolderPath,
                    40,
                    129) < 0 )
          goto LABEL_62;
        fnEfsLogTrace1Strings(v31, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 134);
        v29 = StringCchPrintfW(v48, 0x104u, L"EdpAccount_%s_?", String);
        v38 = -122;
      }
      RecoveryFolderPath = v29;
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v29,
                  40,
                  v38) < 0 )
        goto LABEL_62;
      fnEfsLogTrace1Strings(v32, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 137);
      RecoveryFolderPath = StringCchPrintfW(v50, 0x104u, L"%s\\%s", v49, v48);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  RecoveryFolderPath,
                  40,
                  137) < 0 )
        goto LABEL_62;
      CDplUser::RecoveryBackupWorker(v33, v49, v50, &v40);
      v2 = CDplUser::UserSvcLock((CDplUser *)this);
      v34 = *(_QWORD *)&Buf1.Data1 - (_QWORD)this[42];
      if ( *(const unsigned __int16 **)&Buf1.Data1 == this[42] )
        v34 = *(_QWORD *)Buf1.Data4 - (_QWORD)this[43];
    }
    while ( v34 );
    this[40] = (const unsigned __int16 *)-1LL;
    *((_OWORD *)this + 21) = xmmword_1800F71F8;
  }
LABEL_62:
  CDplUser::UserSvcUnlock((CDplUser *)this, v2);
  if ( !v4 )
    goto LABEL_65;
  v35 = v4;
  while ( 1 )
  {
    DplibMemFree(v35);
LABEL_65:
    if ( v40.Flink == &v40 )
      break;
    v35 = v40.Blink;
    if ( v40.Blink->Flink != &v40 )
      goto LABEL_69;
    v36 = v40.Blink->Blink;
    if ( v36->Flink != v40.Blink )
      goto LABEL_69;
    v40.Blink = v40.Blink->Blink;
    v36->Flink = &v40;
  }
  if ( FirstVolumeW != -1 )
    FindVolumeClose((HANDLE)FirstVolumeW);
  if ( String )
  {
    RpcStringFreeW(&String);
    String = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    RecoveryFolderPath,
    40,
    193);
}

```

## disassembly

```asm
0x1800b8820  mov     [rsp-8+arg_8], rbx
0x1800b8825  mov     [rsp-8+arg_10], rsi
0x1800b882a  push    rbp
0x1800b882b  push    rdi
0x1800b882c  push    r12
0x1800b882e  push    r14
0x1800b8830  push    r15
0x1800b8832  lea     rbp, [rsp-0C00h]
0x1800b883a  sub     rsp, 0D00h
0x1800b8841  mov     rax, cs:__security_cookie
0x1800b8848  xor     rax, rsp
0x1800b884b  mov     [rbp+0C20h+var_30], rax
0x1800b8852  mov     rsi, rcx
0x1800b8855  xorps   xmm0, xmm0
0x1800b8858  mov     ebx, 208h
0x1800b885d  lea     rcx, [rbp+0C20h+var_660]; void *
0x1800b8864  xor     r12d, r12d
0x1800b8867  mov     r8d, ebx; Size
0x1800b886a  xor     edx, edx; Val
0x1800b886c  mov     [rsp+0D20h+String], r12
0x1800b8871  movups  [rsp+0D20h+Buf1], xmm0
0x1800b8876  call    memset_0
0x1800b887b  mov     r8d, ebx; Size
0x1800b887e  lea     rcx, [rbp+0C20h+var_450]; void *
0x1800b8885  xor     edx, edx; Val
0x1800b8887  call    memset_0
0x1800b888c  mov     r8d, ebx; Size
0x1800b888f  lea     rcx, [rbp+0C20h+szVolumeName]; void *
0x1800b8896  xor     edx, edx; Val
0x1800b8898  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800b889c  call    memset_0
0x1800b88a1  xor     edx, edx; Val
0x1800b88a3  lea     r8d, [rbx+2]; Size
0x1800b88a7  lea     rcx, [rbp+0C20h+szVolumePathNames]; void *
0x1800b88ab  call    memset_0
0x1800b88b0  mov     r8d, ebx; Size
0x1800b88b3  mov     [rsp+0D20h+cchReturnLength], r12d
0x1800b88b8  xor     edx, edx; Val
0x1800b88ba  lea     rcx, [rbp+0C20h+var_240]; void *
0x1800b88c1  xor     edi, edi
0x1800b88c3  call    memset_0
0x1800b88c8  xorps   xmm0, xmm0
0x1800b88cb  lea     rcx, [rbp+0C20h+var_A80]; void *
0x1800b88d2  mov     r8d, ebx; Size
0x1800b88d5  xor     edx, edx; Val
0x1800b88d7  movups  xmmword ptr [rsp+0D20h+VolumeRootPath.Length], xmm0
0x1800b88dc  call    memset_0
0x1800b88e1  cmp     cs:?g_DplDbgBreakEnabled@@3IA, edi; uint g_DplDbgBreakEnabled
0x1800b88e7  jz      short loc_1800B88EB
0x1800b88e9  int     2Ch; Windows NT - assertion failure
0x1800b88eb  lea     rax, [rsp+0D20h+var_CD8]
0x1800b88f0  mov     dword ptr [rsp+0D20h+var_D00], 250Dh
0x1800b88f8  mov     [rsp+0D20h+var_CD8.Blink], rax
0x1800b88fd  lea     r8, sourceString
0x1800b8904  lea     rax, [rsp+0D20h+var_CD8]
0x1800b8909  mov     r9d, 28h ; '('
0x1800b890f  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800b8916  mov     [rsp+0D20h+var_CD8.Flink], rax
0x1800b891b  call    fnEfsLogTrace1Strings
0x1800b8920  mov     r14d, 2513h
0x1800b8926  lea     r8, sourceString
0x1800b892d  mov     r9d, 28h ; '('
0x1800b8933  mov     dword ptr [rsp+0D20h+var_D00], r14d
0x1800b8938  lea     rdx, EFS_TRACE_START_EVENT
0x1800b893f  call    fnEfsLogTrace1Strings
0x1800b8944  mov     rcx, [rsi+68h]; unsigned __int16 *
0x1800b8948  lea     rdx, [rbp+0C20h+var_450]; unsigned __int16 *
0x1800b894f  xor     r9d, r9d; int
0x1800b8952  call    ?MakeRecoveryFolderPath@CDplUser@@CAJPEBGPEAGKH@Z; CDplUser::MakeRecoveryFolderPath(ushort const *,ushort *,ulong,int)
0x1800b8957  mov     rcx, cs:g_hPublisher
0x1800b895e  lea     r9, sourceString
0x1800b8965  mov     dword ptr [rsp+0D20h+var_CF0], r14d
0x1800b896a  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b8971  mov     r14d, 28h ; '('
0x1800b8977  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b897e  mov     [rsp+0D20h+var_CF8], r14d
0x1800b8983  mov     ebx, eax
0x1800b8985  mov     dword ptr [rsp+0D20h+var_D00], eax
0x1800b8989  call    fnEfsLogTrace1String1Dword
0x1800b898e  test    eax, eax
0x1800b8990  js      loc_1800B9094
0x1800b8996  mov     edx, 104h; cchBufferLength
0x1800b899b  lea     rcx, [rbp+0C20h+szVolumeName]; lpszVolumeName
0x1800b89a2  call    cs:__imp_FindFirstVolumeW
0x1800b89a8  mov     r15, rax
0x1800b89ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b89af  jnz     short loc_1800B89EC
0x1800b89b1  call    cs:__imp_GetLastError
0x1800b89b7  mov     ebx, eax
0x1800b89b9  test    eax, eax
0x1800b89bb  jle     short loc_1800B89C6
0x1800b89bd  movzx   ebx, ax
0x1800b89c0  or      ebx, 80070000h
0x1800b89c6  mov     dword ptr [rsp+0D20h+var_D00], 251Dh
0x1800b89ce  mov     rcx, cs:g_hPublisher
0x1800b89d5  lea     rdx, EFS_TRACE_ERROR
0x1800b89dc  mov     r9d, r14d
0x1800b89df  mov     r8d, ebx
0x1800b89e2  call    fnEfsLogTrace1
0x1800b89e7  jmp     loc_1800B9094
0x1800b89ec  mov     r14d, 80070000h
0x1800b89f2  lea     r9, [rsp+0D20h+cchReturnLength]; lpcchReturnLength
0x1800b89f7  mov     r8d, 105h; cchBufferLength
0x1800b89fd  lea     rdx, [rbp+0C20h+szVolumePathNames]; lpszVolumePathNames
0x1800b8a01  lea     rcx, [rbp+0C20h+szVolumeName]; lpszVolumeName
0x1800b8a08  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800b8a0e  test    eax, eax
0x1800b8a10  jnz     short loc_1800B8A30
0x1800b8a12  call    cs:__imp_GetLastError
0x1800b8a18  mov     ebx, eax
0x1800b8a1a  test    eax, eax
0x1800b8a1c  jle     short loc_1800B8A24
0x1800b8a1e  movzx   ebx, ax
0x1800b8a21  or      ebx, r14d
0x1800b8a24  cmp     ebx, 800700EAh
0x1800b8a2a  jnz     loc_1800B8E82
0x1800b8a30  xor     eax, eax
0x1800b8a32  mov     [rbp+0C20h+var_A88], ax
0x1800b8a39  test    rdi, rdi
0x1800b8a3c  jz      short loc_1800B8A46
0x1800b8a3e  mov     rcx, rdi; void *
0x1800b8a41  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800b8a46  xor     edi, edi
0x1800b8a48  lea     rcx, [rbp+0C20h+szVolumePathNames]; lpRootPathName
0x1800b8a4c  mov     [rsp+0D20h+var_CC0], rdi
0x1800b8a51  call    cs:__imp_GetDriveTypeW
0x1800b8a57  cmp     eax, 3
0x1800b8a5a  jnz     loc_1800B8D78
0x1800b8a60  lea     r9d, [rdi+28h]
0x1800b8a64  mov     dword ptr [rsp+0D20h+var_D00], 2534h
0x1800b8a6c  lea     r8, sourceString
0x1800b8a73  lea     rdx, EFS_TRACE_START_EVENT
0x1800b8a7a  call    fnEfsLogTrace1Strings
0x1800b8a7f  xor     r9d, r9d
0x1800b8a82  lea     rdx, [rsp+0D20h+VolumeRootPath]
0x1800b8a87  xor     r8d, r8d
0x1800b8a8a  lea     rcx, [rbp+0C20h+szVolumePathNames]
0x1800b8a8e  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800b8a94  mov     ebx, eax
0x1800b8a96  xor     eax, eax
0x1800b8a98  test    ebx, ebx
0x1800b8a9a  jns     short loc_1800B8AC1
0x1800b8a9c  mov     ecx, ebx; Status
0x1800b8a9e  call    cs:__imp_RtlNtStatusToDosError
0x1800b8aa4  test    eax, eax
0x1800b8aa6  jz      short loc_1800B8ABB
0x1800b8aa8  cmp     eax, 13Dh
0x1800b8aad  jz      short loc_1800B8ABB
0x1800b8aaf  test    eax, eax
0x1800b8ab1  jle     short loc_1800B8AC1
0x1800b8ab3  movzx   eax, ax
0x1800b8ab6  or      eax, r14d
0x1800b8ab9  jmp     short loc_1800B8AC1
0x1800b8abb  mov     eax, ebx
0x1800b8abd  bts     eax, 1Ch
0x1800b8ac1  mov     rcx, cs:g_hPublisher
0x1800b8ac8  lea     r9, sourceString
0x1800b8acf  mov     dword ptr [rsp+0D20h+var_CF0], 2534h
0x1800b8ad7  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b8ade  mov     ebx, 28h ; '('
0x1800b8ae3  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b8aea  mov     [rsp+0D20h+var_CF8], ebx
0x1800b8aee  mov     dword ptr [rsp+0D20h+var_D00], eax
0x1800b8af2  call    fnEfsLogTrace1String1Dword
0x1800b8af7  test    eax, eax
0x1800b8af9  js      loc_1800B8D78
0x1800b8aff  mov     r9d, ebx
0x1800b8b02  mov     dword ptr [rsp+0D20h+var_D00], 2536h
0x1800b8b0a  lea     r8, sourceString
0x1800b8b11  lea     rdx, EFS_TRACE_START_EVENT
0x1800b8b18  call    fnEfsLogTrace1Strings
0x1800b8b1d  lea     rcx, [rsp+0D20h+VolumeRootPath]; VolumeRootPath
0x1800b8b22  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x1800b8b28  mov     ebx, eax
0x1800b8b2a  xor     eax, eax
0x1800b8b2c  test    ebx, ebx
0x1800b8b2e  jns     short loc_1800B8B55
0x1800b8b30  mov     ecx, ebx; Status
0x1800b8b32  call    cs:__imp_RtlNtStatusToDosError
0x1800b8b38  test    eax, eax
0x1800b8b3a  jz      short loc_1800B8B4F
0x1800b8b3c  cmp     eax, 13Dh
0x1800b8b41  jz      short loc_1800B8B4F
0x1800b8b43  test    eax, eax
0x1800b8b45  jle     short loc_1800B8B55
0x1800b8b47  movzx   eax, ax
0x1800b8b4a  or      eax, r14d
0x1800b8b4d  jmp     short loc_1800B8B55
0x1800b8b4f  mov     eax, ebx
0x1800b8b51  bts     eax, 1Ch
0x1800b8b55  mov     rcx, cs:g_hPublisher
0x1800b8b5c  lea     r9, sourceString
0x1800b8b63  mov     dword ptr [rsp+0D20h+var_CF0], 2536h
0x1800b8b6b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b8b72  mov     ebx, 28h ; '('
0x1800b8b77  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b8b7e  mov     [rsp+0D20h+var_CF8], ebx
0x1800b8b82  mov     dword ptr [rsp+0D20h+var_D00], eax
0x1800b8b86  call    fnEfsLogTrace1String1Dword
0x1800b8b8b  test    eax, eax
0x1800b8b8d  js      loc_1800B8D78
0x1800b8b93  mov     r9d, ebx
0x1800b8b96  mov     dword ptr [rsp+0D20h+var_D00], 253Ch
0x1800b8b9e  lea     r8, sourceString
0x1800b8ba5  lea     rdx, EFS_TRACE_START_EVENT
0x1800b8bac  call    fnEfsLogTrace1Strings
0x1800b8bb1  lea     rax, aSystemVolumeIn; "System Volume Information"
0x1800b8bb8  mov     edx, 104h; unsigned __int64
0x1800b8bbd  lea     r9, [rbp+0C20h+szVolumePathNames]
0x1800b8bc1  mov     [rsp+0D20h+var_D00], rax
0x1800b8bc6  lea     r8, aSSEdpRecovery; "%s%s\\EDP\\Recovery"
0x1800b8bcd  lea     rcx, [rbp+0C20h+var_A80]; unsigned __int16 *
0x1800b8bd4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b8bd9  mov     rcx, cs:g_hPublisher
0x1800b8be0  lea     r9, sourceString
0x1800b8be7  mov     dword ptr [rsp+0D20h+var_CF0], 253Ch
0x1800b8bef  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b8bf6  mov     [rsp+0D20h+var_CF8], ebx
0x1800b8bfa  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b8c01  mov     dword ptr [rsp+0D20h+var_D00], eax
0x1800b8c05  call    fnEfsLogTrace1String1Dword
0x1800b8c0a  test    eax, eax
0x1800b8c0c  js      loc_1800B8D78
0x1800b8c12  mov     r9d, ebx
0x1800b8c15  mov     dword ptr [rsp+0D20h+var_D00], 253Eh
0x1800b8c1d  lea     r8, sourceString
0x1800b8c24  lea     rdx, EFS_TRACE_START_EVENT
0x1800b8c2b  call    fnEfsLogTrace1Strings
0x1800b8c30  lea     rcx, [rbp+0C20h+var_A80]; unsigned __int16 *
0x1800b8c37  call    ?CreateDirectoryInternal@CDplService@@SAJPEBG@Z; CDplService::CreateDirectoryInternal(ushort const *)
0x1800b8c3c  mov     rcx, cs:g_hPublisher
0x1800b8c43  lea     r9, sourceString
0x1800b8c4a  mov     dword ptr [rsp+0D20h+var_CF0], 253Eh
0x1800b8c52  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b8c59  mov     [rsp+0D20h+var_CF8], ebx
0x1800b8c5d  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b8c64  mov     dword ptr [rsp+0D20h+var_D00], eax
0x1800b8c68  call    fnEfsLogTrace1String1Dword
0x1800b8c6d  test    eax, eax
0x1800b8c6f  js      loc_1800B8D78
0x1800b8c75  lea     rdi, sourceString
0x1800b8c7c  mov     dword ptr [rsp+0D20h+var_D00], 2540h
0x1800b8c84  mov     r8, rdi
0x1800b8c87  lea     rdx, EFS_TRACE_START_EVENT
0x1800b8c8e  mov     r9d, ebx
0x1800b8c91  call    fnEfsLogTrace1Strings
0x1800b8c96  lea     r9, [rsp+0D20h+var_CC0]
0x1800b8c9b  xor     r8d, r8d
0x1800b8c9e  xor     edx, edx
0x1800b8ca0  mov     ecx, 218h
0x1800b8ca5  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800b8caa  mov     rcx, cs:g_hPublisher
0x1800b8cb1  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b8cb8  mov     dword ptr [rsp+0D20h+var_CF0], 2540h
0x1800b8cc0  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b8cc7  mov     [rsp+0D20h+var_CF8], ebx
0x1800b8ccb  mov     r9, rdi
0x1800b8cce  mov     dword ptr [rsp+0D20h+var_D00], eax
0x1800b8cd2  call    fnEfsLogTrace1String1Dword
0x1800b8cd7  test    eax, eax
0x1800b8cd9  js      loc_1800B8D73
0x1800b8cdf  mov     r9d, ebx
0x1800b8ce2  mov     dword ptr [rsp+0D20h+var_D00], 2542h
0x1800b8cea  mov     r8, rdi
0x1800b8ced  lea     rdx, EFS_TRACE_START_EVENT
0x1800b8cf4  call    fnEfsLogTrace1Strings
0x1800b8cf9  mov     rdi, [rsp+0D20h+var_CC0]
0x1800b8cfe  lea     r8, [rbp+0C20h+var_A80]; unsigned __int16 *
0x1800b8d05  mov     edx, 104h; unsigned __int64
0x1800b8d0a  lea     rcx, [rdi+10h]; unsigned __int16 *
0x1800b8d0e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b8d13  mov     rcx, cs:g_hPublisher
0x1800b8d1a  lea     r9, sourceString
0x1800b8d21  mov     dword ptr [rsp+0D20h+var_CF0], 2542h
0x1800b8d29  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b8d30  mov     [rsp+0D20h+var_CF8], ebx
0x1800b8d34  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b8d3b  mov     dword ptr [rsp+0D20h+var_D00], eax
0x1800b8d3f  call    fnEfsLogTrace1String1Dword
0x1800b8d44  test    eax, eax
0x1800b8d46  js      short loc_1800B8D78
0x1800b8d48  mov     rax, [rsp+0D20h+var_CD8.Blink]
0x1800b8d4d  lea     rcx, [rsp+0D20h+var_CD8]
0x1800b8d52  cmp     [rax], rcx
0x1800b8d55  jnz     loc_1800B90DF
0x1800b8d5b  mov     [rdi+8], rax
0x1800b8d5f  lea     rcx, [rsp+0D20h+var_CD8]
0x1800b8d64  mov     [rdi], rcx
0x1800b8d67  mov     [rax], rdi
0x1800b8d6a  mov     [rsp+0D20h+var_CD8.Blink], rdi
0x1800b8d6f  xor     edi, edi
0x1800b8d71  jmp     short loc_1800B8D78
0x1800b8d73  mov     rdi, [rsp+0D20h+var_CC0]
0x1800b8d78  mov     r8d, 104h; cchBufferLength
0x1800b8d7e  lea     rdx, [rbp+0C20h+szVolumeName]; lpszVolumeName
0x1800b8d85  mov     rcx, r15; hFindVolume
0x1800b8d88  call    cs:__imp_FindNextVolumeW
0x1800b8d8e  test    eax, eax
0x1800b8d90  jnz     loc_1800B89F2
0x1800b8d96  call    cs:__imp_GetLastError
  ... truncated ...
```
