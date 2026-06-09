# CCacheMigration::MigrateCache(void)

- ea: `0x18005eab4`
- end: `0x18005efac`
- name: `?MigrateCache@CCacheMigration@@QEAAJXZ`
- size: `1272`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18005f390`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800083bc`
- `0x18000cef8`
- `0x18002e2fc`
- `0x18002f2bc`
- `0x18005d290`
- `0x18005d4d8`
- `0x18005eab4`
- `0x18005f21c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005eb0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005eb85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005eb0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005eb85`
- `KERNEL32!CloseHandle` at `0x18005ee10`
- `KERNEL32!CloseHandle` at `0x18005ee84`
- `KERNEL32!CloseHandle` at `0x18005eef8`
- `KERNEL32!CloseHandle` at `0x18005ee10`
- `KERNEL32!CloseHandle` at `0x18005ee84`
- `KERNEL32!CloseHandle` at `0x18005eef8`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005ed03`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005ed5b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005edb3`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005ed03`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005ed5b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005edb3`

## pseudocode

```c
__int64 __fastcall CCacheMigration::MigrateCache(HANDLE *this)
{
  unsigned int v2; // ebx
  ULONGLONG TickCount64; // r14
  int Begin; // esi
  __int64 v5; // rax
  int v6; // eax
  CHostedCacheMsgEncoding *v7; // rcx
  DWORD LastError; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  HANDLE v11; // rbx
  DWORD v12; // eax
  HANDLE v13; // rbx
  DWORD v14; // eax
  HANDLE v15; // rbx
  DWORD v16; // eax
  const char *v17; // r9
  __int64 FileInformation; // [rsp+80h] [rbp+40h] BYREF
  __int64 v20; // [rsp+88h] [rbp+48h]
  __int64 v21; // [rsp+90h] [rbp+50h]
  char v22; // [rsp+98h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 54, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids);
  }
  v2 = 0;
  v21 = 0;
  v20 = 0;
  TickCount64 = GetTickCount64();
  Begin = CCacheMigration::CacheLoad_Begin((CCacheMigration *)this);
  if ( Begin < 0 )
    goto LABEL_36;
  while ( !*((_BYTE *)this + 64) )
  {
    FileInformation = 0;
    Begin = CCacheMigration::CacheLoad_Segment((CCacheMigration *)this);
    if ( Begin < 0 )
      goto LABEL_20;
    v5 = SmartPointer<ICacheSegment>::SmartPointer<ICacheSegment>(&v22, &FileInformation);
    v6 = CCacheMigration::MigrateSegment(this, v5, v21, v20);
    Begin = v6;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          55,
          WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids,
          (unsigned int)v6);
      }
      goto LABEL_20;
    }
    ++v2;
    if ( GetTickCount64() - TickCount64 > 0x1EE62800 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 56, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids);
      }
      Begin = -2147023436;
LABEL_20:
      SmartPointer<ISegmentRecord>::Release(&FileInformation);
      break;
    }
    SmartPointer<ISegmentRecord>::Release(&FileInformation);
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 57, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids, v2);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (int)(Begin + 0x80000000) < 0 || Begin == -2147024637 )
  {
    if ( v7 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v7 + 108) & 4) != 0
      && *((_BYTE *)v7 + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)v7 + 12), 59, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    Begin = 0;
  }
  else if ( v7 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
         && (*((_BYTE *)v7 + 108) & 4) != 0
         && *((_BYTE *)v7 + 105) )
  {
    WPP_SF_d(*((_QWORD *)v7 + 12), 58, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids, (unsigned int)Begin);
LABEL_36:
    v7 = WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 64) )
    goto LABEL_54;
  LOBYTE(FileInformation) = 1;
  if ( !SetFileInformationByHandle(this[25], FileDispositionInfo, &FileInformation, 1u)
    && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 60, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids, LastError);
  }
  if ( !SetFileInformationByHandle(this[23], FileDispositionInfo, &FileInformation, 1u)
    && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v9 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 61, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids, v9);
  }
  if ( SetFileInformationByHandle(this[24], FileDispositionInfo, &FileInformation, 1u) )
    goto LABEL_53;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v10 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 62, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids, v10);
LABEL_53:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_54:
  if ( this[25] )
  {
    if ( !CloseHandle(this[25])
      && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v11 = this[25];
      v12 = GetLastError();
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 12), 63, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids, v12, v11);
    }
    this[25] = 0;
    v7 = WPP_GLOBAL_Control;
  }
  if ( this[23] )
  {
    if ( !CloseHandle(this[23])
      && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v13 = this[23];
      v14 = GetLastError();
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 12), 64, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids, v14, v13);
    }
    this[23] = 0;
    v7 = WPP_GLOBAL_Control;
  }
  if ( this[24] )
  {
    if ( !CloseHandle(this[24])
      && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v15 = this[24];
      v16 = GetLastError();
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 12), 65, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids, v16, v15);
    }
    this[24] = 0;
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v7 + 108) & 4) != 0
    && *((_BYTE *)v7 + 105) >= 4u )
  {
    v17 = "success";
    if ( Begin < 0 )
      v17 = "failure";
    WPP_SF_sd(
      *((_QWORD *)v7 + 12),
      66,
      (unsigned int)WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids,
      (_DWORD)v17,
      Begin);
  }
  return (unsigned int)Begin;
}

```

## disassembly

```asm
0x18005eab4  push    rbp
0x18005eab6  push    rbx
0x18005eab7  push    rsi
0x18005eab8  push    rdi
0x18005eab9  push    r12
0x18005eabb  push    r13
0x18005eabd  push    r14
0x18005eabf  mov     rbp, rsp
0x18005eac2  sub     rsp, 40h
0x18005eac6  mov     rdi, rcx
0x18005eac9  lea     rax, WPP_GLOBAL_Control
0x18005ead0  mov     r12d, 4
0x18005ead6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eadd  cmp     rcx, rax
0x18005eae0  jz      short loc_18005EB03
0x18005eae2  test    [rcx+6Ch], r12b
0x18005eae6  jz      short loc_18005EB03
0x18005eae8  cmp     [rcx+69h], r12b
0x18005eaec  jb      short loc_18005EB03
0x18005eaee  lea     edx, [r12+32h]
0x18005eaf3  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005eafa  mov     rcx, [rcx+60h]
0x18005eafe  call    WPP_SF_
0x18005eb03  xor     ebx, ebx
0x18005eb05  mov     [rbp+arg_10], rbx
0x18005eb09  mov     [rbp+arg_8], rbx
0x18005eb0d  call    cs:__imp_GetTickCount64
0x18005eb13  mov     r14, rax
0x18005eb16  mov     rcx, rdi; this
0x18005eb19  call    ?CacheLoad_Begin@CCacheMigration@@AEAAJXZ; CCacheMigration::CacheLoad_Begin(void)
0x18005eb1e  mov     esi, eax
0x18005eb20  lea     r13d, [rbx+1]
0x18005eb24  test    eax, eax
0x18005eb26  js      loc_18005ECD6
0x18005eb2c  cmp     byte ptr [rdi+40h], 0
0x18005eb30  jnz     loc_18005EC28
0x18005eb36  mov     [rbp+FileInformation], 0
0x18005eb3e  lea     r9, [rbp+arg_8]
0x18005eb42  lea     r8, [rbp+arg_10]
0x18005eb46  lea     rdx, [rbp+FileInformation]
0x18005eb4a  mov     rcx, rdi; this
0x18005eb4d  call    ?CacheLoad_Segment@CCacheMigration@@AEAAJPEAV?$SmartPointer@VICacheSegment@@@@PEA_K1@Z; CCacheMigration::CacheLoad_Segment(SmartPointer<ICacheSegment> *,unsigned __int64 *,unsigned __int64 *)
0x18005eb52  mov     esi, eax
0x18005eb54  test    eax, eax
0x18005eb56  js      loc_18005EC1F
0x18005eb5c  lea     rdx, [rbp+FileInformation]
0x18005eb60  lea     rcx, [rbp+arg_18]
0x18005eb64  call    ??0?$SmartPointer@VICacheSegment@@@@QEAA@AEBV0@@Z; SmartPointer<ICacheSegment>::SmartPointer<ICacheSegment>(SmartPointer<ICacheSegment> const &)
0x18005eb69  mov     r9, [rbp+arg_8]
0x18005eb6d  mov     r8, [rbp+arg_10]
0x18005eb71  mov     rdx, rax
0x18005eb74  mov     rcx, rdi
0x18005eb77  call    ?MigrateSegment@CCacheMigration@@AEAAJV?$SmartPointer@VICacheSegment@@@@_K1@Z; CCacheMigration::MigrateSegment(SmartPointer<ICacheSegment>,unsigned __int64,unsigned __int64)
0x18005eb7c  mov     esi, eax
0x18005eb7e  test    eax, eax
0x18005eb80  js      short loc_18005EBDC
0x18005eb82  add     ebx, r13d
0x18005eb85  call    cs:__imp_GetTickCount64
0x18005eb8b  sub     rax, r14
0x18005eb8e  cmp     rax, 1EE62800h
0x18005eb94  ja      short loc_18005EBA1
0x18005eb96  lea     rcx, [rbp+FileInformation]
0x18005eb9a  call    ?Release@?$SmartPointer@VISegmentRecord@@@@IEAAXXZ; SmartPointer<ISegmentRecord>::Release(void)
0x18005eb9f  jmp     short loc_18005EB2C
0x18005eba1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eba8  lea     r14, WPP_GLOBAL_Control
0x18005ebaf  cmp     rcx, r14
0x18005ebb2  jz      short loc_18005EBD5
0x18005ebb4  test    [rcx+6Ch], r12b
0x18005ebb8  jz      short loc_18005EBD5
0x18005ebba  cmp     [rcx+69h], r13b
0x18005ebbe  jb      short loc_18005EBD5
0x18005ebc0  mov     edx, 38h ; '8'
0x18005ebc5  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ebcc  mov     rcx, [rcx+60h]
0x18005ebd0  call    WPP_SF_
0x18005ebd5  mov     esi, 800705B4h
0x18005ebda  jmp     short loc_18005EC14
0x18005ebdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebe3  lea     r14, WPP_GLOBAL_Control
0x18005ebea  cmp     rcx, r14
0x18005ebed  jz      short loc_18005EC14
0x18005ebef  test    [rcx+6Ch], r12b
0x18005ebf3  jz      short loc_18005EC14
0x18005ebf5  cmp     [rcx+69h], r13b
0x18005ebf9  jb      short loc_18005EC14
0x18005ebfb  mov     edx, 37h ; '7'
0x18005ec00  mov     r9d, eax
0x18005ec03  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ec0a  mov     rcx, [rcx+60h]
0x18005ec0e  call    WPP_SF_d
0x18005ec13  nop
0x18005ec14  lea     rcx, [rbp+FileInformation]
0x18005ec18  call    ?Release@?$SmartPointer@VISegmentRecord@@@@IEAAXXZ; SmartPointer<ISegmentRecord>::Release(void)
0x18005ec1d  jmp     short loc_18005EC2F
0x18005ec1f  lea     rcx, [rbp+FileInformation]
0x18005ec23  call    ?Release@?$SmartPointer@VISegmentRecord@@@@IEAAXXZ; SmartPointer<ISegmentRecord>::Release(void)
0x18005ec28  lea     r14, WPP_GLOBAL_Control
0x18005ec2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec36  cmp     rcx, r14
0x18005ec39  jz      short loc_18005EC66
0x18005ec3b  test    [rcx+6Ch], r12b
0x18005ec3f  jz      short loc_18005EC66
0x18005ec41  cmp     byte ptr [rcx+69h], 3
0x18005ec45  jb      short loc_18005EC66
0x18005ec47  mov     edx, 39h ; '9'
0x18005ec4c  mov     r9d, ebx
0x18005ec4f  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ec56  mov     rcx, [rcx+60h]
0x18005ec5a  call    WPP_SF_d
0x18005ec5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec66  mov     edx, 80000000h
0x18005ec6b  lea     eax, [rsi+rdx]
0x18005ec6e  test    edx, eax
0x18005ec70  jnz     short loc_18005ECA5
0x18005ec72  cmp     esi, 80070103h
0x18005ec78  jz      short loc_18005ECA5
0x18005ec7a  cmp     rcx, r14
0x18005ec7d  jz      short loc_18005ECE4
0x18005ec7f  test    [rcx+6Ch], r12b
0x18005ec83  jz      short loc_18005ECE4
0x18005ec85  cmp     [rcx+69h], r13b
0x18005ec89  jb      short loc_18005ECE4
0x18005ec8b  mov     edx, 3Ah ; ':'
0x18005ec90  mov     r9d, esi
0x18005ec93  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ec9a  mov     rcx, [rcx+60h]
0x18005ec9e  call    WPP_SF_d
0x18005eca3  jmp     short loc_18005ECDD
0x18005eca5  cmp     rcx, r14
0x18005eca8  jz      short loc_18005ECD2
0x18005ecaa  test    [rcx+6Ch], r12b
0x18005ecae  jz      short loc_18005ECD2
0x18005ecb0  cmp     byte ptr [rcx+69h], 3
0x18005ecb4  jb      short loc_18005ECD2
0x18005ecb6  mov     edx, 3Bh ; ';'
0x18005ecbb  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ecc2  mov     rcx, [rcx+60h]
0x18005ecc6  call    WPP_SF_
0x18005eccb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ecd2  xor     esi, esi
0x18005ecd4  jmp     short loc_18005ECE4
0x18005ecd6  lea     r14, WPP_GLOBAL_Control
0x18005ecdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ece4  cmp     byte ptr [rdi+40h], 0
0x18005ece8  jnz     loc_18005EE01
0x18005ecee  mov     byte ptr [rbp+FileInformation], r13b
0x18005ecf2  mov     r9d, r13d; dwBufferSize
0x18005ecf5  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18005ecf9  mov     edx, r12d; FileInformationClass
0x18005ecfc  mov     rcx, [rdi+0C8h]; hFile
0x18005ed03  call    cs:__imp_SetFileInformationByHandle
0x18005ed09  test    eax, eax
0x18005ed0b  jnz     short loc_18005ED4A
0x18005ed0d  mov     rax, cs:WPP_GLOBAL_Control
0x18005ed14  cmp     rax, r14
0x18005ed17  jz      short loc_18005ED4A
0x18005ed19  test    [rax+6Ch], r12b
0x18005ed1d  jz      short loc_18005ED4A
0x18005ed1f  cmp     [rax+69h], r13b
0x18005ed23  jb      short loc_18005ED4A
0x18005ed25  call    cs:__imp_GetLastError
0x18005ed2b  mov     edx, 3Ch ; '<'
0x18005ed30  mov     r9d, eax
0x18005ed33  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ed3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ed41  mov     rcx, [rcx+60h]
0x18005ed45  call    WPP_SF_d
0x18005ed4a  mov     r9d, r13d; dwBufferSize
0x18005ed4d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18005ed51  mov     edx, r12d; FileInformationClass
0x18005ed54  mov     rcx, [rdi+0B8h]; hFile
0x18005ed5b  call    cs:__imp_SetFileInformationByHandle
0x18005ed61  test    eax, eax
0x18005ed63  jnz     short loc_18005EDA2
0x18005ed65  mov     rax, cs:WPP_GLOBAL_Control
0x18005ed6c  cmp     rax, r14
0x18005ed6f  jz      short loc_18005EDA2
0x18005ed71  test    [rax+6Ch], r12b
0x18005ed75  jz      short loc_18005EDA2
0x18005ed77  cmp     [rax+69h], r13b
0x18005ed7b  jb      short loc_18005EDA2
0x18005ed7d  call    cs:__imp_GetLastError
0x18005ed83  mov     edx, 3Dh ; '='
0x18005ed88  mov     r9d, eax
0x18005ed8b  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ed92  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ed99  mov     rcx, [rcx+60h]
0x18005ed9d  call    WPP_SF_d
0x18005eda2  mov     r9d, r13d; dwBufferSize
0x18005eda5  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18005eda9  mov     edx, r12d; FileInformationClass
0x18005edac  mov     rcx, [rdi+0C0h]; hFile
0x18005edb3  call    cs:__imp_SetFileInformationByHandle
0x18005edb9  test    eax, eax
0x18005edbb  jnz     short loc_18005EDFA
0x18005edbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005edc4  cmp     rcx, r14
0x18005edc7  jz      short loc_18005EE01
0x18005edc9  test    [rcx+6Ch], r12b
0x18005edcd  jz      short loc_18005EE01
0x18005edcf  cmp     [rcx+69h], r13b
0x18005edd3  jb      short loc_18005EE01
0x18005edd5  call    cs:__imp_GetLastError
0x18005eddb  mov     edx, 3Eh ; '>'
0x18005ede0  mov     r9d, eax
0x18005ede3  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005edea  mov     rcx, cs:WPP_GLOBAL_Control
0x18005edf1  mov     rcx, [rcx+60h]
0x18005edf5  call    WPP_SF_d
0x18005edfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee01  mov     rax, [rdi+0C8h]
0x18005ee08  test    rax, rax
0x18005ee0b  jz      short loc_18005EE75
0x18005ee0d  mov     rcx, rax; hObject
0x18005ee10  call    cs:__imp_CloseHandle
0x18005ee16  test    eax, eax
0x18005ee18  jnz     short loc_18005EE63
0x18005ee1a  mov     rax, cs:WPP_GLOBAL_Control
0x18005ee21  cmp     rax, r14
0x18005ee24  jz      short loc_18005EE63
0x18005ee26  test    [rax+6Ch], r12b
0x18005ee2a  jz      short loc_18005EE63
0x18005ee2c  cmp     [rax+69h], r13b
0x18005ee30  jb      short loc_18005EE63
0x18005ee32  mov     rbx, [rdi+0C8h]
0x18005ee39  call    cs:__imp_GetLastError
0x18005ee3f  mov     edx, 3Fh ; '?'
0x18005ee44  mov     [rsp+40h+var_20], rbx
0x18005ee49  mov     r9d, eax
0x18005ee4c  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ee53  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee5a  mov     rcx, [rcx+60h]
0x18005ee5e  call    WPP_SF_dq
0x18005ee63  mov     qword ptr [rdi+0C8h], 0
0x18005ee6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee75  mov     rax, [rdi+0B8h]
0x18005ee7c  test    rax, rax
0x18005ee7f  jz      short loc_18005EEE9
0x18005ee81  mov     rcx, rax; hObject
0x18005ee84  call    cs:__imp_CloseHandle
0x18005ee8a  test    eax, eax
0x18005ee8c  jnz     short loc_18005EED7
0x18005ee8e  mov     rax, cs:WPP_GLOBAL_Control
0x18005ee95  cmp     rax, r14
0x18005ee98  jz      short loc_18005EED7
0x18005ee9a  test    [rax+6Ch], r12b
0x18005ee9e  jz      short loc_18005EED7
0x18005eea0  cmp     [rax+69h], r13b
0x18005eea4  jb      short loc_18005EED7
0x18005eea6  mov     rbx, [rdi+0B8h]
0x18005eead  call    cs:__imp_GetLastError
0x18005eeb3  mov     edx, 40h ; '@'
0x18005eeb8  mov     [rsp+40h+var_20], rbx
0x18005eebd  mov     r9d, eax
0x18005eec0  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005eec7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eece  mov     rcx, [rcx+60h]
0x18005eed2  call    WPP_SF_dq
0x18005eed7  mov     qword ptr [rdi+0B8h], 0
0x18005eee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eee9  mov     rax, [rdi+0C0h]
0x18005eef0  test    rax, rax
0x18005eef3  jz      short loc_18005EF5D
0x18005eef5  mov     rcx, rax; hObject
0x18005eef8  call    cs:__imp_CloseHandle
0x18005eefe  test    eax, eax
0x18005ef00  jnz     short loc_18005EF4B
0x18005ef02  mov     rax, cs:WPP_GLOBAL_Control
0x18005ef09  cmp     rax, r14
0x18005ef0c  jz      short loc_18005EF4B
0x18005ef0e  test    [rax+6Ch], r12b
0x18005ef12  jz      short loc_18005EF4B
0x18005ef14  cmp     [rax+69h], r13b
0x18005ef18  jb      short loc_18005EF4B
0x18005ef1a  mov     rbx, [rdi+0C0h]
0x18005ef21  call    cs:__imp_GetLastError
0x18005ef27  mov     edx, 41h ; 'A'
0x18005ef2c  mov     [rsp+40h+var_20], rbx
0x18005ef31  mov     r9d, eax
0x18005ef34  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ef3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef42  mov     rcx, [rcx+60h]
0x18005ef46  call    WPP_SF_dq
0x18005ef4b  mov     qword ptr [rdi+0C0h], 0
0x18005ef56  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef5d  cmp     rcx, r14
0x18005ef60  jz      short loc_18005EF9B
0x18005ef62  test    [rcx+6Ch], r12b
0x18005ef66  jz      short loc_18005EF9B
0x18005ef68  cmp     [rcx+69h], r12b
0x18005ef6c  jb      short loc_18005EF9B
0x18005ef6e  lea     rax, aFailure; "failure"
0x18005ef75  lea     r9, aSuccess; "success"
0x18005ef7c  test    esi, esi
0x18005ef7e  cmovs   r9, rax
0x18005ef82  mov     edx, 42h ; 'B'
0x18005ef87  mov     dword ptr [rsp+40h+var_20], esi
0x18005ef8b  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005ef92  mov     rcx, [rcx+60h]
  ... truncated ...
```
