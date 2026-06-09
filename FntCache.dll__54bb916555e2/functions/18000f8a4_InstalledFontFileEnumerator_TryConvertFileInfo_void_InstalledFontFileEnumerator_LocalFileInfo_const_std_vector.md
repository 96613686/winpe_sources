# InstalledFontFileEnumerator::TryConvertFileInfo(void *,InstalledFontFileEnumerator::LocalFileInfo const &,std::vector<InstalledFontFileInfo,std::allocator<InstalledFontFileInfo>> &)

- ea: `0x18000f8a4`
- end: `0x18000fb1f`
- name: `?TryConvertFileInfo@InstalledFontFileEnumerator@@AEAA_NPEAXAEBULocalFileInfo@1@AEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000fb80`

## callees

- `0x180004810`
- `0x18000e5e8`
- `0x18000e9d8`
- `0x18000f8a4`
- `0x18000fb28`
- `0x18001db38`
- `0x180028c50`
- `0x1800aa650`
- `0x1800b2b5c`
- `0x1800b4760`
- `0x1800b8a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa8d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f9e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000fa41`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f9e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000fa41`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000f8fb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000f8fb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000fa62`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000fa62`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f9f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fa4d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f9f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fa4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall InstalledFontFileEnumerator::TryConvertFileInfo(int a1, void *a2, const WCHAR *a3, __int64 *a4)
{
  const WCHAR *v8; // rcx
  HANDLE FirstFileW; // rdx
  const WCHAR *v10; // rcx
  signed int LastError; // r14d
  struct DWrite::RefString::Data *v13; // rbx
  struct DWrite::RefString::Data *ftLastWriteTime; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[24]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+68h] [rbp-98h]
  struct DWrite::RefString::Data *v18; // [rsp+70h] [rbp-90h]
  bool v19; // [rsp+78h] [rbp-88h]
  void *v20; // [rsp+80h] [rbp-80h]
  HANDLE hFindFile; // [rsp+90h] [rbp-70h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+98h] [rbp-68h] BYREF

  v20 = a2;
  if ( a2 && !ImpersonateLoggedOnUser(a2) )
    LogAndThrowLastError(0x6E6F737265706D49LL, 98);
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v8 = a3;
  else
    v8 = *(const WCHAR **)a3;
  FirstFileW = FindFirstFileW(v8, &FindFileData);
  hFindFile = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL || (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
    if ( (*((_DWORD *)a3 + 8) == 1) == (a2 == 0) )
    {
      LastError = GetLastError();
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(const WCHAR **)a3;
      GetDepersonalizedFilePath(&ftLastWriteTime, a3);
      v13 = ftLastWriteTime;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      EventLogger::LogEvent<long,EventTag,unsigned int,wchar_t const *>(
        a1 + 16,
        1953394502,
        1869771365,
        LastError,
        0x656D697466LL,
        186,
        (__int64)ftLastWriteTime + 8);
      DWrite::RefString::DecrementRef(v13);
      FirstFileW = hFindFile;
    }
    if ( FirstFileW != (HANDLE)-1LL )
      FindClose(FirstFileW);
    if ( a2 )
      RevertToSelf();
    return 0;
  }
  else
  {
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v16);
    v17 = 0;
    v18 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
    v19 = 0;
    v15 = 0;
    ftLastWriteTime = (struct DWrite::RefString::Data *)FindFileData.ftLastWriteTime;
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v10 = a3;
    else
      v10 = *(const WCHAR **)a3;
    LocalFileLoader::SerializeReferenceKeyTo(v10);
    v17 = *((_DWORD *)a3 + 8);
    _InterlockedIncrement(*((volatile signed __int32 **)a3 + 5));
    DWrite::RefString::DecrementRef(v18);
    v18 = (struct DWrite::RefString::Data *)*((_QWORD *)a3 + 5);
    v19 = a2 != 0;
    if ( a4[1] == a4[2] )
    {
      std::vector<InstalledFontFileInfo>::_Emplace_reallocate<InstalledFontFileInfo>(a4, a4[1], (__int64)&v15);
    }
    else
    {
      InstalledFontFileInfo::InstalledFontFileInfo(a4[1], &v15);
      a4[1] += 56;
    }
    DWrite::RefString::DecrementRef(v18);
    std::vector<unsigned char>::_Tidy(v16);
    if ( hFindFile != (HANDLE)-1LL )
      FindClose(hFindFile);
    if ( a2 )
      RevertToSelf();
    return 1;
  }
}

```

## disassembly

```asm
0x18000f8a4  mov     [rsp-8+arg_8], rbx
0x18000f8a9  push    rbp
0x18000f8aa  push    rsi
0x18000f8ab  push    rdi
0x18000f8ac  push    r14
0x18000f8ae  push    r15
0x18000f8b0  lea     rbp, [rsp-200h]
0x18000f8b8  sub     rsp, 300h
0x18000f8bf  mov     rax, cs:__security_cookie
0x18000f8c6  xor     rax, rsp
0x18000f8c9  mov     [rbp+220h+var_30], rax
0x18000f8d0  mov     rdi, r9
0x18000f8d3  mov     rbx, r8
0x18000f8d6  mov     rsi, rdx
0x18000f8d9  mov     r15, rcx
0x18000f8dc  mov     [rbp+220h+var_2A0], rdx
0x18000f8e0  test    rdx, rdx
0x18000f8e3  jnz     loc_18000FA5F
0x18000f8e9  cmp     qword ptr [rbx+18h], 7
0x18000f8ee  jbe     loc_18000FA1F
0x18000f8f4  mov     rcx, [rbx]; lpFileName
0x18000f8f7  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x18000f8fb  call    cs:__imp_FindFirstFileW
0x18000f901  mov     rdx, rax
0x18000f904  mov     [rbp+220h+hFindFile], rax
0x18000f908  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f90c  jz      loc_18000FA27
0x18000f912  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x18000f916  jnz     loc_18000FA27
0x18000f91c  lea     rcx, [rsp+320h+var_2D0]; void *
0x18000f921  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18000f926  mov     [rsp+320h+var_2B8], 0
0x18000f92e  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18000f935  mov     [rsp+320h+var_2B0], rax
0x18000f93a  mov     [rsp+320h+var_2A8], 0
0x18000f93f  mov     [rsp+320h+var_2D8], 0
0x18000f948  mov     eax, [rbp+220h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x18000f94b  mov     dword ptr [rsp+320h+var_2E0+4], eax
0x18000f94f  mov     eax, [rbp+220h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18000f952  mov     dword ptr [rsp+320h+var_2E0], eax
0x18000f956  mov     rax, [rsp+320h+var_2E0]
0x18000f95b  mov     [rsp+320h+var_2E0], rax
0x18000f960  cmp     qword ptr [rbx+18h], 7
0x18000f965  jbe     loc_18000FA57
0x18000f96b  mov     rcx, [rbx]; lpString2
0x18000f96e  lea     r9, [rsp+320h+var_2D0]
0x18000f973  lea     rdx, [rsp+320h+var_2E0]
0x18000f978  call    ?SerializeReferenceKeyTo@LocalFileLoader@@SAXPEB_WPEBVDateTime@@0AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; LocalFileLoader::SerializeReferenceKeyTo(wchar_t const *,DateTime const *,wchar_t const *,std::vector<uchar> &)
0x18000f97d  mov     eax, [rbx+20h]
0x18000f980  mov     [rsp+320h+var_2B8], eax
0x18000f984  mov     rax, [rbx+28h]
0x18000f988  lock inc dword ptr [rax]
0x18000f98b  mov     rcx, [rsp+320h+var_2B0]; struct DWrite::RefString::Data *
0x18000f990  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000f995  mov     rax, [rbx+28h]
0x18000f999  mov     [rsp+320h+var_2B0], rax
0x18000f99e  test    rsi, rsi
0x18000f9a1  setnz   [rsp+320h+var_2A8]
0x18000f9a6  mov     rax, [rdi+8]
0x18000f9aa  cmp     rax, [rdi+10h]
0x18000f9ae  jz      loc_18000FB09
0x18000f9b4  lea     rdx, [rsp+320h+var_2D8]
0x18000f9b9  mov     rcx, rax
0x18000f9bc  call    ??0InstalledFontFileInfo@@QEAA@$$QEAU0@@Z; InstalledFontFileInfo::InstalledFontFileInfo(InstalledFontFileInfo &&)
0x18000f9c1  add     qword ptr [rdi+8], 38h ; '8'
0x18000f9c6  mov     rcx, [rsp+320h+var_2B0]; struct DWrite::RefString::Data *
0x18000f9cb  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000f9d0  lea     rcx, [rsp+320h+var_2D0]
0x18000f9d5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000f9da  nop
0x18000f9db  mov     rcx, [rbp+220h+hFindFile]; hFindFile
0x18000f9df  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f9e3  jz      short loc_18000F9EC
0x18000f9e5  call    cs:__imp_FindClose
0x18000f9eb  nop
0x18000f9ec  test    rsi, rsi
0x18000f9ef  jz      short loc_18000F9F7
0x18000f9f1  call    cs:__imp_RevertToSelf
0x18000f9f7  mov     al, 1
0x18000f9f9  mov     rcx, [rbp+220h+var_30]
0x18000fa00  xor     rcx, rsp; StackCookie
0x18000fa03  call    __security_check_cookie
0x18000fa08  mov     rbx, [rsp+320h+arg_8]
0x18000fa10  add     rsp, 300h
0x18000fa17  pop     r15
0x18000fa19  pop     r14
0x18000fa1b  pop     rdi
0x18000fa1c  pop     rsi
0x18000fa1d  pop     rbp
0x18000fa1e  retn
0x18000fa1f  mov     rcx, rbx
0x18000fa22  jmp     loc_18000F8F7
0x18000fa27  cmp     dword ptr [rbx+20h], 1
0x18000fa2b  setz    cl
0x18000fa2e  test    rsi, rsi
0x18000fa31  setz    al
0x18000fa34  cmp     cl, al
0x18000fa36  jz      short loc_18000FA83
0x18000fa38  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000fa3c  jz      short loc_18000FA48
0x18000fa3e  mov     rcx, rdx; hFindFile
0x18000fa41  call    cs:__imp_FindClose
0x18000fa47  nop
0x18000fa48  test    rsi, rsi
0x18000fa4b  jz      short loc_18000FA53
0x18000fa4d  call    cs:__imp_RevertToSelf
0x18000fa53  xor     al, al
0x18000fa55  jmp     short loc_18000F9F9
0x18000fa57  mov     rcx, rbx
0x18000fa5a  jmp     loc_18000F96E
0x18000fa5f  mov     rcx, rsi; hToken
0x18000fa62  call    cs:__imp_ImpersonateLoggedOnUser
0x18000fa68  test    eax, eax
0x18000fa6a  jnz     loc_18000F8E9
0x18000fa70  mov     rcx, 6E6F737265706D49h
0x18000fa7a  lea     edx, [rax+62h]
0x18000fa7d  call    ?LogAndThrowLastError@@YAXVEventTag@@I@Z; LogAndThrowLastError(EventTag,uint)
0x18000fa83  mov     rdi, 656D697466h
0x18000fa8d  call    cs:__imp_GetLastError
0x18000fa93  mov     r14d, eax
0x18000fa96  cmp     qword ptr [rbx+18h], 7
0x18000fa9b  jbe     short loc_18000FAA0
0x18000fa9d  mov     rbx, [rbx]
0x18000faa0  mov     rdx, rbx
0x18000faa3  lea     rcx, [rsp+320h+var_2E0]
0x18000faa8  call    ?GetDepersonalizedFilePath@@YA?AVRefString@DWrite@@PEB_W@Z; GetDepersonalizedFilePath(wchar_t const *)
0x18000faad  mov     rbx, [rsp+320h+var_2E0]
0x18000fab2  lea     rax, [rbx+8]
0x18000fab6  test    r14d, r14d
0x18000fab9  jle     short loc_18000FAC6
0x18000fabb  movzx   r14d, r14w
0x18000fabf  or      r14d, 80070000h
0x18000fac6  mov     rdx, 6D756E45746E6F46h
0x18000fad0  mov     r8, 726F727265h
0x18000fada  lea     rcx, [r15+10h]
0x18000fade  mov     [rsp+320h+var_2F0], rax
0x18000fae3  mov     [rsp+320h+var_2F8], 0BAh
0x18000faeb  mov     [rsp+320h+var_300], rdi
0x18000faf0  mov     r9d, r14d
0x18000faf3  call    ??$LogEvent@JVEventTag@@IPEB_W@EventLogger@@QEBAXVEventTag@@0J0IPEB_W@Z; EventLogger::LogEvent<long,EventTag,uint,wchar_t const *>(EventTag,EventTag,long,EventTag,uint,wchar_t const *)
0x18000faf8  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18000fafb  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000fb00  mov     rdx, [rbp+220h+hFindFile]
0x18000fb04  jmp     loc_18000FA38
0x18000fb09  lea     r8, [rsp+320h+var_2D8]
0x18000fb0e  mov     rdx, rax
0x18000fb11  mov     rcx, rdi
0x18000fb14  call    ??$_Emplace_reallocate@UInstalledFontFileInfo@@@?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@AEAAPEAUInstalledFontFileInfo@@QEAU2@$$QEAU2@@Z; std::vector<InstalledFontFileInfo>::_Emplace_reallocate<InstalledFontFileInfo>(InstalledFontFileInfo * const,InstalledFontFileInfo &&)
0x18000fb19  jmp     loc_18000F9C6
```
