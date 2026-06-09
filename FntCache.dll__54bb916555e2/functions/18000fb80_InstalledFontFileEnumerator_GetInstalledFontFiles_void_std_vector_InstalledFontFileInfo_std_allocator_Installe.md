# InstalledFontFileEnumerator::GetInstalledFontFiles(void *,std::vector<InstalledFontFileInfo,std::allocator<InstalledFontFileInfo>> &,InstalledFontChangeInfo *)

- ea: `0x18000fb80`
- end: `0x18000febe`
- name: `?GetInstalledFontFiles@InstalledFontFileEnumerator@@UEAAXPEAXAEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@PEAUInstalledFontChangeInfo@@@Z`
- size: `830`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004810`
- `0x18000f8a4`
- `0x18000fb80`
- `0x180069df8`
- `0x18009f4ac`
- `0x1800a0058`
- `0x1800a26e8`
- `0x1800a5584`
- `0x1800b4760`
- `0x1800b7b24`
- `0x1800b8be4`
- `0x1800b8d00`
- `0x1800b8d8c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fd1f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fd1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe25`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x18000fc6b`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x18000fc6b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000fbc8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000fbc8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fbfe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fbfe`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InstalledFontFileEnumerator::GetInstalledFontFiles(__int64 a1, __int64 a2, __int64 *a3, _QWORD *a4)
{
  void *v7; // rdx
  __int64 v8; // rsi
  __int64 v9; // rdi
  unsigned __int64 v10; // rcx
  HANDLE v11; // rax
  _QWORD *v12; // rdx
  __int64 v13; // rdx
  void *v14; // r8
  __int64 v15; // r15
  unsigned __int64 v16; // rdx
  DWORD LastError; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rax
  DWORD v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rax
  int v26; // [rsp+28h] [rbp-58h]
  unsigned __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  __int64 v28; // [rsp+48h] [rbp-38h] BYREF
  __int64 v29; // [rsp+50h] [rbp-30h]
  __int64 v30; // [rsp+60h] [rbp-20h] BYREF
  void *v31; // [rsp+68h] [rbp-18h]
  HANDLE v32; // [rsp+C8h] [rbp+48h] BYREF
  __int64 *v33; // [rsp+D0h] [rbp+50h]

  v33 = a3;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v30);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v28);
  v32 = v7;
  if ( v7 && !ImpersonateLoggedOnUser(v7) )
    LogAndThrowLastError(0x6E6F737265706D49LL, 98);
  InstalledFontFileEnumerator::EnumerateRegistry(a1, &v30, &v28, a4);
  if ( a2 )
    RevertToSelf();
  if ( a4 )
  {
    v8 = v29;
    v9 = v28;
    v10 = (v29 - v28) >> 3;
    v32 = (HANDLE)v10;
    if ( v10 > (__int64)(a4[4] - a4[2]) >> 3 )
    {
      if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
        goto LABEL_19;
      std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Reallocate<0>(a4 + 2, &v32);
      v8 = v29;
      v9 = v28;
    }
    while ( v9 != v8 )
    {
      v11 = FindFirstChangeNotificationW((LPCWSTR)(*(_QWORD *)v9 + 8LL), 0, 0x11u);
      if ( v11 != (HANDLE)-1LL )
      {
        v32 = v11;
        v12 = (_QWORD *)a4[3];
        if ( v12 == (_QWORD *)a4[4] )
        {
          std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Emplace_reallocate<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>(
            a4 + 2,
            v12,
            &v32);
        }
        else
        {
          *v12 = v11;
          v32 = 0;
          a4[3] += 8LL;
        }
        ScopedHandle<FileChangeNotificationHandlePolicy,void *>::~ScopedHandle<FileChangeNotificationHandlePolicy,void *>(&v32);
      }
      v9 += 8;
    }
  }
  v13 = 0x6DB6DB6DB6DB6DB7LL * ((v33[1] - *v33) >> 3);
  v14 = v31;
  v32 = v31;
  v15 = v30;
  v16 = 0x6DB6DB6DB6DB6DB7LL * (((__int64)v31 - v30) >> 3) + v13;
  v27 = v16;
  if ( v16 > 0x6DB6DB6DB6DB6DB7LL * ((v33[2] - *v33) >> 3) )
  {
    if ( v16 > 0x492492492492492LL )
LABEL_19:
      std::_Xlength_error("vector too long");
    std::vector<InstalledFontFileInfo>::_Reallocate<0>(v33, &v27);
    v14 = v31;
    v32 = v31;
    v15 = v30;
  }
  if ( (void *)v15 != v14 )
  {
    if ( a2 )
    {
      do
      {
        if ( !(unsigned __int8)InstalledFontFileEnumerator::TryConvertFileInfo(a1, 0, v15)
          && !(unsigned __int8)InstalledFontFileEnumerator::TryConvertFileInfo(a1, a2, v15) )
        {
          LastError = GetLastError();
          if ( *(_BYTE *)(v15 + 48) )
          {
            if ( *(_QWORD *)(v15 + 24) <= 7u )
              v19 = v15;
            else
              v19 = *(_QWORD *)v15;
            EventLogger::LogEvent<long,EventTag,unsigned int,wchar_t const *,unsigned long>(
              a1 + 16,
              1953394502,
              1869771365,
              v18,
              0x6D756E65656C6966LL,
              v26,
              v19,
              LastError);
          }
          else
          {
            if ( *(_QWORD *)(v15 + 24) <= 7u )
              v20 = v15;
            else
              v20 = *(_QWORD *)v15;
            EventSource<ComInterfaceList<InstalledFontFileEnumerator,IInstalledFontFileEnumerator>,IInstalledFontFileEnumerator>::LogEvent<EventTag,int,wchar_t const *>(
              a1,
              0x676E696E726177LL,
              0x6D756E65656C6966LL,
              v18,
              v20);
          }
        }
        v15 += 56;
      }
      while ( (HANDLE)v15 != v32 );
    }
    else
    {
      do
      {
        if ( !(unsigned __int8)InstalledFontFileEnumerator::TryConvertFileInfo(a1, 0, v15) )
        {
          v21 = GetLastError();
          if ( *(_BYTE *)(v15 + 48) )
          {
            if ( *(_QWORD *)(v15 + 24) <= 7u )
              v23 = v15;
            else
              v23 = *(_QWORD *)v15;
            EventLogger::LogEvent<long,EventTag,unsigned int,wchar_t const *,unsigned long>(
              a1 + 16,
              1953394502,
              1869771365,
              v22,
              0x6D756E65656C6966LL,
              v26,
              v23,
              v21);
          }
          else
          {
            if ( *(_QWORD *)(v15 + 24) <= 7u )
              v24 = v15;
            else
              v24 = *(_QWORD *)v15;
            EventSource<ComInterfaceList<InstalledFontFileEnumerator,IInstalledFontFileEnumerator>,IInstalledFontFileEnumerator>::LogEvent<EventTag,int,wchar_t const *>(
              a1,
              0x676E696E726177LL,
              0x6D756E65656C6966LL,
              v22,
              v24);
          }
        }
        v15 += 56;
      }
      while ( (HANDLE)v15 != v32 );
    }
  }
  std::vector<DWrite::RefString>::_Tidy(&v28);
  return std::vector<InstalledFontFileEnumerator::LocalFileInfo>::_Tidy(&v30);
}

```

## disassembly

```asm
0x18000fb80  mov     [rsp-38h+arg_0], rbx
0x18000fb85  mov     [rsp-38h+arg_10], r8
0x18000fb8a  push    rbp
0x18000fb8b  push    rsi
0x18000fb8c  push    rdi
0x18000fb8d  push    r12
0x18000fb8f  push    r13
0x18000fb91  push    r14
0x18000fb93  push    r15
0x18000fb95  mov     rbp, rsp
0x18000fb98  sub     rsp, 80h
0x18000fb9f  mov     rbx, r9
0x18000fba2  mov     r12, rdx
0x18000fba5  mov     r13, rcx
0x18000fba8  lea     rcx, [rbp+var_20]; void *
0x18000fbac  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18000fbb1  nop
0x18000fbb2  lea     rcx, [rbp+var_38]; void *
0x18000fbb6  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18000fbbb  nop
0x18000fbbc  mov     [rbp+arg_8], rdx
0x18000fbc0  test    rdx, rdx
0x18000fbc3  jz      short loc_18000FBE5
0x18000fbc5  mov     rcx, rdx; hToken
0x18000fbc8  call    cs:__imp_ImpersonateLoggedOnUser
0x18000fbce  test    eax, eax
0x18000fbd0  jnz     short loc_18000FBE5
0x18000fbd2  mov     rcx, 6E6F737265706D49h
0x18000fbdc  lea     edx, [rax+62h]
0x18000fbdf  call    ?LogAndThrowLastError@@YAXVEventTag@@I@Z; LogAndThrowLastError(EventTag,uint)
0x18000fbe5  mov     r9, rbx
0x18000fbe8  lea     r8, [rbp+var_38]
0x18000fbec  lea     rdx, [rbp+var_20]
0x18000fbf0  mov     rcx, r13
0x18000fbf3  call    ?EnumerateRegistry@InstalledFontFileEnumerator@@AEAAXAEAV?$vector@ULocalFileInfo@InstalledFontFileEnumerator@@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@AEAV?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@3@PEAUInstalledFontChangeInfo@@@Z; InstalledFontFileEnumerator::EnumerateRegistry(std::vector<InstalledFontFileEnumerator::LocalFileInfo> &,std::vector<DWrite::RefString> &,InstalledFontChangeInfo *)
0x18000fbf8  nop
0x18000fbf9  test    r12, r12
0x18000fbfc  jz      short loc_18000FC04
0x18000fbfe  call    cs:__imp_RevertToSelf
0x18000fc04  test    rbx, rbx
0x18000fc07  jz      loc_18000FCB7
0x18000fc0d  mov     rsi, [rbp+var_30]
0x18000fc11  mov     rcx, rsi
0x18000fc14  mov     rdi, [rbp+var_38]
0x18000fc18  sub     rcx, rdi
0x18000fc1b  sar     rcx, 3
0x18000fc1f  mov     [rbp+arg_8], rcx
0x18000fc23  mov     rax, [rbx+20h]
0x18000fc27  sub     rax, [rbx+10h]
0x18000fc2b  sar     rax, 3
0x18000fc2f  cmp     rcx, rax
0x18000fc32  jbe     short loc_18000FCB2
0x18000fc34  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000fc3e  cmp     rcx, rax
0x18000fc41  ja      loc_18000FD18
0x18000fc47  lea     rdx, [rbp+arg_8]
0x18000fc4b  lea     rcx, [rbx+10h]
0x18000fc4f  call    ??$_Reallocate@$0A@@?$vector@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@V?$allocator@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@@std@@@std@@AEAAXAEA_K@Z; std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Reallocate<0>(unsigned __int64 &)
0x18000fc54  mov     rsi, [rbp+var_30]
0x18000fc58  mov     rdi, [rbp+var_38]
0x18000fc5c  jmp     short loc_18000FCB2
0x18000fc5e  mov     rcx, [rdi]
0x18000fc61  add     rcx, 8; lpPathName
0x18000fc65  xor     edx, edx; bWatchSubtree
0x18000fc67  lea     r8d, [rdx+11h]; dwNotifyFilter
0x18000fc6b  call    cs:__imp_FindFirstChangeNotificationW
0x18000fc71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fc75  jz      short loc_18000FCAE
0x18000fc77  mov     [rbp+arg_8], rax
0x18000fc7b  mov     rdx, [rbx+18h]
0x18000fc7f  cmp     rdx, [rbx+20h]
0x18000fc83  jz      short loc_18000FC97
0x18000fc85  mov     [rdx], rax
0x18000fc88  mov     [rbp+arg_8], 0
0x18000fc90  add     qword ptr [rbx+18h], 8
0x18000fc95  jmp     short loc_18000FCA5
0x18000fc97  lea     r8, [rbp+arg_8]
0x18000fc9b  lea     rcx, [rbx+10h]
0x18000fc9f  call    ??$_Emplace_reallocate@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@@?$vector@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@V?$allocator@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@@std@@@std@@AEAAPEAV?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@QEAV2@$$QEAV2@@Z; std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Emplace_reallocate<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>(ScopedHandle<FileChangeNotificationHandlePolicy,void *> * const,ScopedHandle<FileChangeNotificationHandlePolicy,void *> &&)
0x18000fca4  nop
0x18000fca5  lea     rcx, [rbp+arg_8]
0x18000fca9  call    ??1?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@QEAA@XZ; ScopedHandle<FileChangeNotificationHandlePolicy,void *>::~ScopedHandle<FileChangeNotificationHandlePolicy,void *>(void)
0x18000fcae  add     rdi, 8
0x18000fcb2  cmp     rdi, rsi
0x18000fcb5  jnz     short loc_18000FC5E
0x18000fcb7  mov     r9, [rbp+arg_10]
0x18000fcbb  mov     rdx, [r9+8]
0x18000fcbf  sub     rdx, [r9]
0x18000fcc2  sar     rdx, 3
0x18000fcc6  mov     r10, 6DB6DB6DB6DB6DB7h
0x18000fcd0  imul    rdx, r10
0x18000fcd4  mov     r8, [rbp+var_18]
0x18000fcd8  mov     [rbp+arg_8], r8
0x18000fcdc  mov     rax, r8
0x18000fcdf  mov     r15, [rbp+var_20]
0x18000fce3  sub     rax, r15
0x18000fce6  sar     rax, 3
0x18000fcea  imul    rax, r10
0x18000fcee  add     rdx, rax
0x18000fcf1  mov     [rbp+var_40], rdx
0x18000fcf5  mov     rax, [r9+10h]
0x18000fcf9  sub     rax, [r9]
0x18000fcfc  sar     rax, 3
0x18000fd00  imul    rax, r10
0x18000fd04  cmp     rdx, rax
0x18000fd07  jbe     short loc_18000FD42
0x18000fd09  mov     rax, 492492492492492h
0x18000fd13  cmp     rdx, rax
0x18000fd16  jbe     short loc_18000FD26
0x18000fd18  lea     rcx, aVectorTooLong; "vector too long"
0x18000fd1f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000fd26  lea     rdx, [rbp+var_40]
0x18000fd2a  mov     rcx, r9
0x18000fd2d  call    ??$_Reallocate@$0A@@?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@AEAAXAEA_K@Z; std::vector<InstalledFontFileInfo>::_Reallocate<0>(unsigned __int64 &)
0x18000fd32  mov     r8, [rbp+var_18]
0x18000fd36  mov     [rbp+arg_8], r8
0x18000fd3a  mov     r15, [rbp+var_20]
0x18000fd3e  mov     r9, [rbp+arg_10]
0x18000fd42  cmp     r15, r8
0x18000fd45  jz      loc_18000FE90
0x18000fd4b  mov     rbx, 6D756E65656C6966h
0x18000fd55  mov     rsi, 726F727265h
0x18000fd5f  mov     rdi, 676E696E726177h
0x18000fd69  mov     r14, 6D756E45746E6F46h
0x18000fd73  test    r12, r12
0x18000fd76  jz      loc_18000FE14
0x18000fd7c  mov     r8, r15
0x18000fd7f  xor     edx, edx
0x18000fd81  mov     rcx, r13
0x18000fd84  call    ?TryConvertFileInfo@InstalledFontFileEnumerator@@AEAA_NPEAXAEBULocalFileInfo@1@AEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@@Z; InstalledFontFileEnumerator::TryConvertFileInfo(void *,InstalledFontFileEnumerator::LocalFileInfo const &,std::vector<InstalledFontFileInfo> &)
0x18000fd89  test    al, al
0x18000fd8b  jnz     short loc_18000FE00
0x18000fd8d  mov     r9, [rbp+arg_10]
0x18000fd91  mov     r8, r15
0x18000fd94  mov     rdx, r12
0x18000fd97  mov     rcx, r13
0x18000fd9a  call    ?TryConvertFileInfo@InstalledFontFileEnumerator@@AEAA_NPEAXAEBULocalFileInfo@1@AEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@@Z; InstalledFontFileEnumerator::TryConvertFileInfo(void *,InstalledFontFileEnumerator::LocalFileInfo const &,std::vector<InstalledFontFileInfo> &)
0x18000fd9f  test    al, al
0x18000fda1  jnz     short loc_18000FE00
0x18000fda3  call    cs:__imp_GetLastError
0x18000fda9  cmp     byte ptr [r15+30h], 0
0x18000fdae  jz      short loc_18000FDDE
0x18000fdb0  cmp     qword ptr [r15+18h], 7
0x18000fdb5  jbe     short loc_18000FDBC
0x18000fdb7  mov     rdx, [r15]
0x18000fdba  jmp     short loc_18000FDBF
0x18000fdbc  mov     rdx, r15
0x18000fdbf  lea     rcx, [r13+10h]
0x18000fdc3  mov     [rsp+80h+var_48], eax
0x18000fdc7  mov     [rsp+80h+var_50], rdx
0x18000fdcc  mov     [rsp+80h+var_60], rbx
0x18000fdd1  mov     r8, rsi
0x18000fdd4  mov     rdx, r14
0x18000fdd7  call    ??$LogEvent@JVEventTag@@IPEB_WK@EventLogger@@QEBAXVEventTag@@0J0IPEB_WK@Z; EventLogger::LogEvent<long,EventTag,uint,wchar_t const *,ulong>(EventTag,EventTag,long,EventTag,uint,wchar_t const *,ulong)
0x18000fddc  jmp     short loc_18000FE00
0x18000fdde  cmp     qword ptr [r15+18h], 7
0x18000fde3  jbe     short loc_18000FDEA
0x18000fde5  mov     rax, [r15]
0x18000fde8  jmp     short loc_18000FDED
0x18000fdea  mov     rax, r15
0x18000fded  mov     [rsp+80h+var_60], rax
0x18000fdf2  mov     r8, rbx
0x18000fdf5  mov     rdx, rdi
0x18000fdf8  mov     rcx, r13
0x18000fdfb  call    ??$LogEvent@VEventTag@@HPEB_W@?$EventSource@V?$ComInterfaceList@VInstalledFontFileEnumerator@@UIInstalledFontFileEnumerator@@@@UIInstalledFontFileEnumerator@@@@QEBAXVEventTag@@0HPEB_W@Z; EventSource<ComInterfaceList<InstalledFontFileEnumerator,IInstalledFontFileEnumerator>,IInstalledFontFileEnumerator>::LogEvent<EventTag,int,wchar_t const *>(EventTag,EventTag,int,wchar_t const *)
0x18000fe00  add     r15, 38h ; '8'
0x18000fe04  cmp     r15, [rbp+arg_8]
0x18000fe08  mov     r9, [rbp+arg_10]
0x18000fe0c  jnz     loc_18000FD7C
0x18000fe12  jmp     short loc_18000FE90
0x18000fe14  mov     r8, r15
0x18000fe17  xor     edx, edx
0x18000fe19  mov     rcx, r13
0x18000fe1c  call    ?TryConvertFileInfo@InstalledFontFileEnumerator@@AEAA_NPEAXAEBULocalFileInfo@1@AEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@@Z; InstalledFontFileEnumerator::TryConvertFileInfo(void *,InstalledFontFileEnumerator::LocalFileInfo const &,std::vector<InstalledFontFileInfo> &)
0x18000fe21  test    al, al
0x18000fe23  jnz     short loc_18000FE82
0x18000fe25  call    cs:__imp_GetLastError
0x18000fe2b  cmp     byte ptr [r15+30h], 0
0x18000fe30  jz      short loc_18000FE60
0x18000fe32  cmp     qword ptr [r15+18h], 7
0x18000fe37  jbe     short loc_18000FE3E
0x18000fe39  mov     rdx, [r15]
0x18000fe3c  jmp     short loc_18000FE41
0x18000fe3e  mov     rdx, r15
0x18000fe41  lea     rcx, [r13+10h]
0x18000fe45  mov     [rsp+80h+var_48], eax
0x18000fe49  mov     [rsp+80h+var_50], rdx
0x18000fe4e  mov     [rsp+80h+var_60], rbx
0x18000fe53  mov     r8, rsi
0x18000fe56  mov     rdx, r14
0x18000fe59  call    ??$LogEvent@JVEventTag@@IPEB_WK@EventLogger@@QEBAXVEventTag@@0J0IPEB_WK@Z; EventLogger::LogEvent<long,EventTag,uint,wchar_t const *,ulong>(EventTag,EventTag,long,EventTag,uint,wchar_t const *,ulong)
0x18000fe5e  jmp     short loc_18000FE82
0x18000fe60  cmp     qword ptr [r15+18h], 7
0x18000fe65  jbe     short loc_18000FE6C
0x18000fe67  mov     rax, [r15]
0x18000fe6a  jmp     short loc_18000FE6F
0x18000fe6c  mov     rax, r15
0x18000fe6f  mov     [rsp+80h+var_60], rax
0x18000fe74  mov     r8, rbx
0x18000fe77  mov     rdx, rdi
0x18000fe7a  mov     rcx, r13
0x18000fe7d  call    ??$LogEvent@VEventTag@@HPEB_W@?$EventSource@V?$ComInterfaceList@VInstalledFontFileEnumerator@@UIInstalledFontFileEnumerator@@@@UIInstalledFontFileEnumerator@@@@QEBAXVEventTag@@0HPEB_W@Z; EventSource<ComInterfaceList<InstalledFontFileEnumerator,IInstalledFontFileEnumerator>,IInstalledFontFileEnumerator>::LogEvent<EventTag,int,wchar_t const *>(EventTag,EventTag,int,wchar_t const *)
0x18000fe82  add     r15, 38h ; '8'
0x18000fe86  cmp     r15, [rbp+arg_8]
0x18000fe8a  mov     r9, [rbp+arg_10]
0x18000fe8e  jnz     short loc_18000FE14
0x18000fe90  lea     rcx, [rbp+var_38]
0x18000fe94  call    ?_Tidy@?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@std@@AEAAXXZ; std::vector<DWrite::RefString>::_Tidy(void)
0x18000fe99  nop
0x18000fe9a  lea     rcx, [rbp+var_20]
0x18000fe9e  call    ?_Tidy@?$vector@ULocalFileInfo@InstalledFontFileEnumerator@@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@AEAAXXZ; std::vector<InstalledFontFileEnumerator::LocalFileInfo>::_Tidy(void)
0x18000fea3  mov     rbx, [rsp+80h+arg_0]
0x18000feab  add     rsp, 80h
0x18000feb2  pop     r15
0x18000feb4  pop     r14
0x18000feb6  pop     r13
0x18000feb8  pop     r12
0x18000feba  pop     rdi
0x18000febb  pop     rsi
0x18000febc  pop     rbp
0x18000febd  retn
```
