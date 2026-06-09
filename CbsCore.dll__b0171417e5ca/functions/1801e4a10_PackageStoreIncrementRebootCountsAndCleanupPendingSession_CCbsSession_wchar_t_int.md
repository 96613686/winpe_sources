# PackageStoreIncrementRebootCountsAndCleanupPendingSession(CCbsSession *,wchar_t *,int)

- ea: `0x1801e4a10`
- end: `0x1801e4cc1`
- name: `?PackageStoreIncrementRebootCountsAndCleanupPendingSession@@YAXPEAVCCbsSession@@PEA_WH@Z`
- size: `689`
- prototype: `void __fastcall(struct CCbsSession *this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800b7dbc`

## callees

- `0x180010f54`
- `0x180011094`
- `0x180013018`
- `0x180013250`
- `0x1800132a4`
- `0x1800261e0`
- `0x18002641c`
- `0x1800a8678`
- `0x1800b3f5c`
- `0x1800b693c`
- `0x1800b6e34`
- `0x1800b980c`
- `0x1800eb920`
- `0x1801c1578`
- `0x1801e4a10`
- `0x1801edcc8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e4bc7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e4bfe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e4c29`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e4c54`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e4bc7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e4bfe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e4c29`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801e4c54`

## string_xrefs

- `0x1801e4b92`: `Failed to get online session store directory`
- `0x1801e4b9f`: `%ws%ws.xml`
- `0x1801e4bd7`: `%ws%ws.back.xml`
- `0x1801e4b66`: `Failed to get offline session store directory`
- `0x1801e4c39`: `%s%s_rem.xml`
- `0x1801e4c0e`: `%s%s_exe.xml`

## pseudocode

```c
void __fastcall PackageStoreIncrementRebootCountsAndCleanupPendingSession(
        struct CCbsSession *this,
        wchar_t *a2,
        int a3)
{
  int OnlineStoreObject; // eax
  const char *v6; // r8
  int SessionStoreDirectory; // eax
  const char *v8; // r8
  __int64 v9; // rcx
  wchar_t *v10; // rbx
  unsigned int v11; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *v12; // [rsp+38h] [rbp-21h] BYREF
  LPCWSTR v13; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR v14; // [rsp+48h] [rbp-11h] BYREF
  LPCWSTR v15; // [rsp+50h] [rbp-9h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v17[24]; // [rsp+60h] [rbp+7h] BYREF
  wchar_t *v18; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v19; // [rsp+80h] [rbp+27h] BYREF
  int v20; // [rsp+88h] [rbp+2Fh]
  __int128 v21; // [rsp+90h] [rbp+37h]
  __int64 v22; // [rsp+A0h] [rbp+47h]

  v18 = a2;
  v19 = 0;
  v20 = 0;
  v22 = 0;
  v12 = 0;
  lpFileName = 0;
  v21 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  v11 = 0;
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v17,
    (struct AutoMonitoredCritSec *)&vPackageStoreLock,
    1);
  if ( !this )
  {
    OnlineStoreObject = CCbsStoreParameters::GetOnlineStoreObject(v18, 5, 0, &v19);
    if ( OnlineStoreObject < 0 )
    {
      v6 = "Failed to get pending session object: {} in online mode";
      goto LABEL_4;
    }
LABEL_7:
    if ( !a3 )
    {
      CCbsStoreObject::TryGetValue((CCbsStoreObject *)&v19, L"RebootCounter", &v11);
      if ( v11 + 1 < 3 )
      {
        SessionStoreDirectory = CCbsStoreObject::SetValue((CCbsStoreObject *)&v19, L"RebootCounter", v11 + 1);
        if ( SessionStoreDirectory >= 0 )
          goto LABEL_24;
        v8 = "Failed to set reboot counts";
LABEL_14:
        LogAdapter::TraceAtLevelIfFailed<long,>(2, (unsigned int)SessionStoreDirectory, v8);
        goto LABEL_24;
      }
    }
    CCbsStoreObject::Delete((CCbsStoreObject *)&v19);
    if ( this )
    {
      SessionStoreDirectory = CCbsSession::GetSessionStoreDirectory(this, &v12);
      if ( SessionStoreDirectory < 0 )
      {
        v8 = "Failed to get offline session store directory";
        goto LABEL_14;
      }
    }
    else
    {
      SessionStoreDirectory = GetOnlineStoreDirectory(v9, L"Servicing\\Sessions\\", &v12);
      if ( SessionStoreDirectory < 0 )
      {
        v8 = "Failed to get online session store directory";
        goto LABEL_14;
      }
    }
    v10 = v12;
    SessionStoreDirectory = SczAllocFormatted(&lpFileName, L"%ws%ws.xml", v12, v18);
    if ( SessionStoreDirectory >= 0 )
    {
      DeleteFileW(lpFileName);
      SessionStoreDirectory = SczAllocFormatted(&v15, L"%ws%ws.back.xml", v10, v18);
      if ( SessionStoreDirectory >= 0 )
      {
        DeleteFileW(v15);
        SessionStoreDirectory = SczAllocFormatted(&v14, L"%s%s_exe.xml", v10, v18);
        if ( SessionStoreDirectory >= 0 )
        {
          DeleteFileW(v14);
          SessionStoreDirectory = SczAllocFormatted(&v13, L"%s%s_rem.xml", v10, v18);
          if ( SessionStoreDirectory >= 0 )
          {
            DeleteFileW(v13);
            goto LABEL_24;
          }
        }
      }
      v8 = "Failed to format session backup.";
    }
    else
    {
      v8 = "Failed to format session file.";
    }
    goto LABEL_14;
  }
  OnlineStoreObject = CCbsSession::GetStoreObject(this, v18, 5, 0, &v19);
  if ( OnlineStoreObject >= 0 )
    goto LABEL_7;
  v6 = "Failed to get pending session object: {} in offline mode";
LABEL_4:
  LogAdapter::TraceAtLevelHr<long,wchar_t const *>(2, (unsigned int)OnlineStoreObject, v6, &v18);
LABEL_24:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v17);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v13);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v14);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v15);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v12);
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v19);
}

```

## disassembly

```asm
0x1801e4a10  mov     [rsp-8+arg_10], rbx
0x1801e4a15  mov     [rsp-8+arg_18], rdi
0x1801e4a1a  push    rbp
0x1801e4a1b  lea     rbp, [rsp-57h]
0x1801e4a20  sub     rsp, 0B0h
0x1801e4a27  mov     rax, cs:__security_cookie
0x1801e4a2e  xor     rax, rsp
0x1801e4a31  mov     [rbp+57h+var_8], rax
0x1801e4a35  mov     edi, r8d
0x1801e4a38  mov     [rbp+57h+var_38], rdx
0x1801e4a3c  mov     rbx, rcx
0x1801e4a3f  mov     [rbp+57h+var_30], 0
0x1801e4a47  xorps   xmm0, xmm0
0x1801e4a4a  mov     [rbp+57h+var_28], 0
0x1801e4a51  mov     r8b, 1; bool
0x1801e4a54  mov     [rbp+57h+var_10], 0
0x1801e4a5c  lea     rdx, ?vPackageStoreLock@@3UMonitoredCritSec@@A; struct AutoMonitoredCritSec *
0x1801e4a63  mov     [rbp+57h+var_78], 0
0x1801e4a6b  lea     rcx, [rbp+57h+var_50]; this
0x1801e4a6f  mov     [rbp+57h+lpFileName], 0
0x1801e4a77  movdqu  [rbp+57h+var_20], xmm0
0x1801e4a7c  mov     [rbp+57h+var_60], 0
0x1801e4a84  mov     [rbp+57h+var_68], 0
0x1801e4a8c  mov     [rbp+57h+var_70], 0
0x1801e4a94  mov     [rbp+57h+var_80], 0
0x1801e4a9b  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x1801e4aa0  test    rbx, rbx
0x1801e4aa3  jz      short loc_1801E4AE1
0x1801e4aa5  mov     rdx, [rbp+57h+var_38]
0x1801e4aa9  lea     rax, [rbp+57h+var_30]
0x1801e4aad  xor     r9d, r9d
0x1801e4ab0  mov     [rsp+0B0h+var_90], rax
0x1801e4ab5  mov     rcx, rbx
0x1801e4ab8  lea     r8d, [r9+5]
0x1801e4abc  call    ?GetStoreObject@CCbsSession@@QEAAJPEB_WW4CbsStoreObjectType@@HPEAVCCbsStoreObject@@@Z; CCbsSession::GetStoreObject(wchar_t const *,CbsStoreObjectType,int,CCbsStoreObject *)
0x1801e4ac1  test    eax, eax
0x1801e4ac3  jns     short loc_1801E4B02
0x1801e4ac5  lea     r8, aFailedToGetPen_3; "Failed to get pending session object: {"...
0x1801e4acc  lea     r9, [rbp+57h+var_38]
0x1801e4ad0  mov     edx, eax
0x1801e4ad2  mov     ecx, 2
0x1801e4ad7  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x1801e4adc  jmp     loc_1801E4C60
0x1801e4ae1  mov     rcx, [rbp+57h+var_38]
0x1801e4ae5  lea     r9, [rbp+57h+var_30]
0x1801e4ae9  xor     r8d, r8d
0x1801e4aec  lea     edx, [r8+5]
0x1801e4af0  call    ?GetOnlineStoreObject@CCbsStoreParameters@@SAJPEB_WW4CbsStoreObjectType@@HPEAVCCbsStoreObject@@@Z; CCbsStoreParameters::GetOnlineStoreObject(wchar_t const *,CbsStoreObjectType,int,CCbsStoreObject *)
0x1801e4af5  test    eax, eax
0x1801e4af7  jns     short loc_1801E4B02
0x1801e4af9  lea     r8, aFailedToGetPen_0; "Failed to get pending session object: {"...
0x1801e4b00  jmp     short loc_1801E4ACC
0x1801e4b02  test    edi, edi
0x1801e4b04  jnz     short loc_1801E4B48
0x1801e4b06  lea     r8, [rbp+57h+var_80]; unsigned int *
0x1801e4b0a  lea     rdx, aRebootcounter; "RebootCounter"
0x1801e4b11  lea     rcx, [rbp+57h+var_30]; this
0x1801e4b15  call    ?TryGetValue@CCbsStoreObject@@QEAA_NQEB_WPEAK@Z; CCbsStoreObject::TryGetValue(wchar_t const * const,ulong *)
0x1801e4b1a  mov     r8d, [rbp+57h+var_80]
0x1801e4b1e  inc     r8d; unsigned int
0x1801e4b21  cmp     r8d, 3
0x1801e4b25  jnb     short loc_1801E4B48
0x1801e4b27  lea     rdx, aRebootcounter; "RebootCounter"
0x1801e4b2e  lea     rcx, [rbp+57h+var_30]; this
0x1801e4b32  call    ?SetValue@CCbsStoreObject@@QEAAJPEB_WK@Z; CCbsStoreObject::SetValue(wchar_t const *,ulong)
0x1801e4b37  test    eax, eax
0x1801e4b39  jns     loc_1801E4C60
0x1801e4b3f  lea     r8, aFailedToSetReb; "Failed to set reboot counts"
0x1801e4b46  jmp     short loc_1801E4B6D
0x1801e4b48  lea     rcx, [rbp+57h+var_30]; this
0x1801e4b4c  call    ?Delete@CCbsStoreObject@@QEAAJXZ; CCbsStoreObject::Delete(void)
0x1801e4b51  test    rbx, rbx
0x1801e4b54  jz      short loc_1801E4B7E
0x1801e4b56  lea     rdx, [rbp+57h+var_78]; wchar_t **
0x1801e4b5a  mov     rcx, rbx; this
0x1801e4b5d  call    ?GetSessionStoreDirectory@CCbsSession@@QEAAJPEAPEA_W@Z; CCbsSession::GetSessionStoreDirectory(wchar_t * *)
0x1801e4b62  test    eax, eax
0x1801e4b64  jns     short loc_1801E4B9B
0x1801e4b66  lea     r8, aFailedToGetOff_17; "Failed to get offline session store dir"...
0x1801e4b6d  mov     edx, eax
0x1801e4b6f  mov     ecx, 2
0x1801e4b74  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801e4b79  jmp     loc_1801E4C60
0x1801e4b7e  lea     r8, [rbp+57h+var_78]
0x1801e4b82  lea     rdx, aServicingSessi_1; "Servicing\\Sessions\\"
0x1801e4b89  call    GetOnlineStoreDirectory
0x1801e4b8e  test    eax, eax
0x1801e4b90  jns     short loc_1801E4B9B
0x1801e4b92  lea     r8, aFailedToGetOnl_1; "Failed to get online session store dire"...
0x1801e4b99  jmp     short loc_1801E4B6D
0x1801e4b9b  mov     rbx, [rbp+57h+var_78]
0x1801e4b9f  lea     rdx, aWsWsXml; "%ws%ws.xml"
0x1801e4ba6  mov     r9, [rbp+57h+var_38]
0x1801e4baa  lea     rcx, [rbp+57h+lpFileName]
0x1801e4bae  mov     r8, rbx
0x1801e4bb1  call    SczAllocFormatted
0x1801e4bb6  test    eax, eax
0x1801e4bb8  jns     short loc_1801E4BC3
0x1801e4bba  lea     r8, aFailedToFormat_15; "Failed to format session file."
0x1801e4bc1  jmp     short loc_1801E4B6D
0x1801e4bc3  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1801e4bc7  call    cs:__imp_DeleteFileW
0x1801e4bce  nop     dword ptr [rax+rax+00h]
0x1801e4bd3  mov     r9, [rbp+57h+var_38]
0x1801e4bd7  lea     rdx, aWsWsBackXml; "%ws%ws.back.xml"
0x1801e4bde  mov     r8, rbx
0x1801e4be1  lea     rcx, [rbp+57h+var_60]
0x1801e4be5  call    SczAllocFormatted
0x1801e4bea  test    eax, eax
0x1801e4bec  jns     short loc_1801E4BFA
0x1801e4bee  lea     r8, aFailedToFormat_18; "Failed to format session backup."
0x1801e4bf5  jmp     loc_1801E4B6D
0x1801e4bfa  mov     rcx, [rbp+57h+var_60]; lpFileName
0x1801e4bfe  call    cs:__imp_DeleteFileW
0x1801e4c05  nop     dword ptr [rax+rax+00h]
0x1801e4c0a  mov     r9, [rbp+57h+var_38]
0x1801e4c0e  lea     rdx, aSSExeXml; "%s%s_exe.xml"
0x1801e4c15  mov     r8, rbx
0x1801e4c18  lea     rcx, [rbp+57h+var_68]
0x1801e4c1c  call    SczAllocFormatted
0x1801e4c21  test    eax, eax
0x1801e4c23  js      short loc_1801E4BEE
0x1801e4c25  mov     rcx, [rbp+57h+var_68]; lpFileName
0x1801e4c29  call    cs:__imp_DeleteFileW
0x1801e4c30  nop     dword ptr [rax+rax+00h]
0x1801e4c35  mov     r9, [rbp+57h+var_38]
0x1801e4c39  lea     rdx, aSSRemXml; "%s%s_rem.xml"
0x1801e4c40  mov     r8, rbx
0x1801e4c43  lea     rcx, [rbp+57h+var_70]
0x1801e4c47  call    SczAllocFormatted
0x1801e4c4c  test    eax, eax
0x1801e4c4e  js      short loc_1801E4BEE
0x1801e4c50  mov     rcx, [rbp+57h+var_70]; lpFileName
0x1801e4c54  call    cs:__imp_DeleteFileW
0x1801e4c5b  nop     dword ptr [rax+rax+00h]
0x1801e4c60  lea     rcx, [rbp+57h+var_50]; this
0x1801e4c64  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x1801e4c69  lea     rcx, [rbp+57h+var_70]
0x1801e4c6d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801e4c72  lea     rcx, [rbp+57h+var_68]
0x1801e4c76  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801e4c7b  lea     rcx, [rbp+57h+var_60]
0x1801e4c7f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801e4c84  lea     rcx, [rbp+57h+lpFileName]
0x1801e4c88  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801e4c8d  lea     rcx, [rbp+57h+var_78]
0x1801e4c91  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801e4c96  lea     rcx, [rbp+57h+var_30]; this
0x1801e4c9a  call    ??1CCbsStoreObject@@QEAA@XZ; CCbsStoreObject::~CCbsStoreObject(void)
0x1801e4c9f  mov     rcx, [rbp+57h+var_8]
0x1801e4ca3  xor     rcx, rsp; StackCookie
0x1801e4ca6  call    __security_check_cookie
0x1801e4cab  lea     r11, [rsp+0B0h+var_s0]
0x1801e4cb3  mov     rbx, [r11+20h]
0x1801e4cb7  mov     rdi, [r11+28h]
0x1801e4cbb  mov     rsp, r11
0x1801e4cbe  pop     rbp
0x1801e4cbf  retn
```
