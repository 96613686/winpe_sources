# _lambda_2c7fe16221c4d1b98351ecccb9afd2c9_::operator()

- ea: `0x18003d634`
- end: `0x18003dc16`
- name: `_lambda_2c7fe16221c4d1b98351ecccb9afd2c9_::operator()`
- size: `1506`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180043080`

## callees

- `0x180004a54`
- `0x18000c668`
- `0x1800344f8`
- `0x180037780`
- `0x18003d634`
- `0x1800433fc`
- `0x180043938`
- `0x180044dd8`
- `0x180045754`
- `0x1800467e8`
- `0x180047010`
- `0x180089010`

## import_xrefs

- `SHCORE!CreateStreamOverRandomAccessStream` at `0x18003db5b`
- `SHCORE!CreateStreamOverRandomAccessStream` at `0x18003db5b`
- `SHCORE!__imp_CreateRandomAccessStreamOnPlaceholderFile` at `0x18003dadd`
- `SHCORE!__imp_CreateRandomAccessStreamOnPlaceholderFile` at `0x18003dadd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d6a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d8bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d6a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d8bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003d826`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003d826`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003d87a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003d87a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003d89a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003d89a`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall lambda_2c7fe16221c4d1b98351ecccb9afd2c9_::operator()(int *a1)
{
  __int64 v2; // rcx
  int LocalFileStream; // ebx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rax
  int v6; // r14d
  _OWORD *v7; // rax
  DWORD *p_nFileSizeLow; // rcx
  __int64 v9; // r15
  __int64 v10; // rdx
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  __int64 (__fastcall *v12)(HANDLE *, Windows::Internal::FilePlaceholderHelper **); // rbx
  struct IFilePlaceholderStreamResolver **v13; // r9
  int FilePlaceholderStreamResolver; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  HANDLE FirstFileW; // rdi
  enum PLACEHOLDER_STATES *v18; // r9
  struct _RTL_CRITICAL_SECTION *v19; // rbx
  char v20; // bl
  struct _RTL_CRITICAL_SECTION *v21; // rax
  __int64 v22; // xmm6_8
  _OWORD *v23; // rax
  DWORD *v24; // rcx
  __int64 v25; // rcx
  struct _RTL_CRITICAL_SECTION *v26; // rdi
  __int64 (__fastcall *v27)(struct _RTL_CRITICAL_SECTION *, GUID *, __int64 *); // rbx
  __int64 v28; // rcx
  struct IFilePlaceholderCallback *v30; // [rsp+28h] [rbp-E0h]
  __int64 v31; // [rsp+28h] [rbp-E0h]
  __int64 v32; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+68h] [rbp-A0h] BYREF
  Windows::Internal::FilePlaceholderHelper *v35; // [rsp+70h] [rbp-98h] BYREF
  Windows::Internal::FilePlaceholderHelper *v36; // [rsp+78h] [rbp-90h] BYREF
  __int64 v37; // [rsp+80h] [rbp-88h] BYREF
  struct _RTL_CRITICAL_SECTION *v38; // [rsp+88h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION *v39; // [rsp+90h] [rbp-78h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp-70h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-60h] BYREF
  Windows::Internal::FilePlaceholderHelper *v43; // [rsp+B0h] [rbp-58h] BYREF
  struct _WIN32_FIND_DATAW v44; // [rsp+B8h] [rbp-50h] BYREF

  v33 = 0;
  v2 = *((_QWORD *)a1 + 4);
  if ( v2 )
    LocalFileStream = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  else
    LocalFileStream = 0;
  if ( LocalFileStream >= 0 )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)a1 + 80LL);
    EnterCriticalSection(v4);
    v39 = v4;
    v5 = *(struct _RTL_CRITICAL_SECTION **)a1;
    v6 = *(_DWORD *)(*(_QWORD *)a1 + 148LL);
    LODWORD(v32) = v6;
    *(_OWORD *)&v44.dwFileAttributes = *(_OWORD *)&v5[3].SpinCount;
    *(_OWORD *)&v44.ftLastAccessTime.dwHighDateTime = *(_OWORD *)&v5[4].LockCount;
    v7 = (_OWORD *)((char *)&v5[4].SpinCount + 4);
    p_nFileSizeLow = &v44.nFileSizeLow;
    v9 = 4;
    v10 = 4;
    do
    {
      *(_OWORD *)p_nFileSizeLow = *v7;
      *((_OWORD *)p_nFileSizeLow + 1) = v7[1];
      *((_OWORD *)p_nFileSizeLow + 2) = v7[2];
      *((_OWORD *)p_nFileSizeLow + 3) = v7[3];
      *((_OWORD *)p_nFileSizeLow + 4) = v7[4];
      *((_OWORD *)p_nFileSizeLow + 5) = v7[5];
      *((_OWORD *)p_nFileSizeLow + 6) = v7[6];
      *((_OWORD *)p_nFileSizeLow + 7) = v7[7];
      p_nFileSizeLow += 32;
      v7 += 8;
      --v10;
    }
    while ( v10 );
    *(_OWORD *)p_nFileSizeLow = *v7;
    *((_OWORD *)p_nFileSizeLow + 1) = v7[1];
    *((_OWORD *)p_nFileSizeLow + 2) = v7[2];
    *((_OWORD *)p_nFileSizeLow + 3) = v7[3];
    *((_OWORD *)p_nFileSizeLow + 4) = v7[4];
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v39);
    v36 = 0;
    v11 = *(struct _RTL_CRITICAL_SECTION **)a1;
    v12 = *(__int64 (__fastcall **)(HANDLE *, Windows::Internal::FilePlaceholderHelper **))(*(_QWORD *)(*(_QWORD *)a1 + 16LL)
                                                                                          + 64LL);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v36);
    LocalFileStream = v12(&v11->OwningThread, &v36);
    if ( LocalFileStream < 0 )
      goto LABEL_39;
    v35 = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v35);
    FilePlaceholderStreamResolver = Windows::Internal::FilePlaceholderHelper::CreateFilePlaceholderStreamResolver(
                                      v36,
                                      *(struct IPropertyStore **)(*(_QWORD *)a1 + 120LL),
                                      (const unsigned __int16 *)&v35,
                                      v13);
    LocalFileStream = FilePlaceholderStreamResolver;
    if ( FilePlaceholderStreamResolver >= 0 )
      goto LABEL_11;
    if ( FilePlaceholderStreamResolver != -2147023728 )
    {
LABEL_38:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v35);
LABEL_39:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v36);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v39);
      goto LABEL_40;
    }
    if ( (v6 & 4) == 0 )
    {
LABEL_11:
      if ( (v6 & 3) != 3 )
      {
        if ( FilePlaceholderStreamResolver >= 0 )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          LocalFileStream = Windows::Internal::FilePlaceholderHelper::VerifyFileVersionSyncWithWritableExtrinsicPropertyStore(
                              v35,
                              v36,
                              *(struct IPropertyStore **)(*(_QWORD *)a1 + 120LL),
                              *((const unsigned __int16 **)a1 + 4),
                              v30);
          if ( LocalFileStream >= 0 )
          {
            v16 = *((_QWORD *)a1 + 4);
            if ( !v16
              || (LocalFileStream = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16),
                  LocalFileStream >= 0) )
            {
              FirstFileW = FindFirstFileW(*(LPCWSTR *)(*(_QWORD *)a1 + 120LL), (LPWIN32_FIND_DATAW)&v44.nFileSizeLow);
              if ( FirstFileW || (LocalFileStream = ResultFromKnownLastError(), LocalFileStream >= 0) )
              {
                FindClose(FirstFileW);
                Windows::Internal::FilePlaceholderHelper::GetFilePlaceholderInformationAndStatesFromFindData(
                  (Windows::Internal::FilePlaceholderHelper *)&v44.nFileSizeLow,
                  &v44,
                  (struct FILE_PLACEHOLDER_INFORMATION *)&v32,
                  v18);
                v19 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)a1 + 80LL);
                EnterCriticalSection(v19);
                v38 = v19;
                v20 = v32;
                *(_DWORD *)(*(_QWORD *)a1 + 148LL) = v32;
                v21 = *(struct _RTL_CRITICAL_SECTION **)a1;
                *(_OWORD *)&v21[3].SpinCount = *(_OWORD *)&v44.dwFileAttributes;
                v22 = *(_QWORD *)&v44.ftLastAccessTime.dwHighDateTime;
                *(_OWORD *)&v21[4].LockCount = *(_OWORD *)&v44.ftLastAccessTime.dwHighDateTime;
                v23 = (_OWORD *)(*(_QWORD *)a1 + 196LL);
                v24 = &v44.nFileSizeLow;
                do
                {
                  *v23 = *(_OWORD *)v24;
                  v23[1] = *((_OWORD *)v24 + 1);
                  v23[2] = *((_OWORD *)v24 + 2);
                  v23[3] = *((_OWORD *)v24 + 3);
                  v23[4] = *((_OWORD *)v24 + 4);
                  v23[5] = *((_OWORD *)v24 + 5);
                  v23[6] = *((_OWORD *)v24 + 6);
                  v23[7] = *((_OWORD *)v24 + 7);
                  v23 += 8;
                  v24 += 32;
                  --v9;
                }
                while ( v9 );
                *v23 = *(_OWORD *)v24;
                v23[1] = *((_OWORD *)v24 + 1);
                v23[2] = *((_OWORD *)v24 + 2);
                v23[3] = *((_OWORD *)v24 + 3);
                v23[4] = *((_OWORD *)v24 + 4);
                Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v38);
                if ( (v20 & 2) != 0 )
                {
                  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
                  LocalFileStream = CFilePlaceholder::_CreateLocalFileStream(
                                      v25,
                                      a1[5],
                                      *(_QWORD *)(*(_QWORD *)a1 + 120LL),
                                      a1[6],
                                      v31,
                                      (__int64)&v33);
                }
                else
                {
                  v37 = 0;
                  v26 = *(struct _RTL_CRITICAL_SECTION **)a1;
                  v27 = ***(__int64 (__fastcall ****)(struct _RTL_CRITICAL_SECTION *, GUID *, __int64 *))a1;
                  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v37);
                  LocalFileStream = v27(v26, &GUID_c8b34e60_6ee3_4881_9138_6b4fb6bfb461, &v37);
                  if ( LocalFileStream >= 0 )
                  {
                    v34 = 0;
                    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v34);
                    v42 = *((_QWORD *)a1 + 4);
                    v43 = v35;
                    v41 = v22;
                    v34 = 0;
                    v32 = 0;
                    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32);
                    LocalFileStream = Microsoft::WRL::Details::MakeAndInitialize<CFilePlaceholderRemoteStream,CFilePlaceholderRemoteStream,IFilePlaceholderStreamResolver * &,IFilePlaceholderCallback * &,unsigned __int64 &>(
                                        &v32,
                                        &v43,
                                        &v42,
                                        &v41);
                    if ( LocalFileStream >= 0 )
                      LocalFileStream = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v32)(
                                          v32,
                                          &GUID_0000000c_0000_0000_c000_000000000046,
                                          &v34);
                    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32);
                    if ( LocalFileStream >= 0 )
                    {
                      v32 = 0;
                      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32);
                      LocalFileStream = CreateRandomAccessStreamOnPlaceholderFile(
                                          *(_QWORD *)(*(_QWORD *)a1 + 120LL),
                                          (a1[6] & 0x1003) != 0,
                                          HIWORD(a1[6]) & 1,
                                          v34,
                                          v37,
                                          *((_QWORD *)a1 + 4),
                                          a1[4],
                                          &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                          &v32);
                      if ( LocalFileStream >= 0 )
                      {
                        if ( (a1[6] & 0x11000) != 0x11000
                          || (LocalFileStream = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 56LL))(
                                                  v32,
                                                  0),
                              LocalFileStream >= 0) )
                        {
                          if ( a1[5] == 1 )
                          {
                            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
                            LocalFileStream = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v32)(
                                                v32,
                                                &GUID_00000000_0000_0000_c000_000000000046,
                                                &v33);
                          }
                          else
                          {
                            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
                            LocalFileStream = CreateStreamOverRandomAccessStream(
                                                v32,
                                                &GUID_00000000_0000_0000_c000_000000000046,
                                                &v33);
                            if ( LocalFileStream >= 0 )
                              LocalFileStream = SetStreamEmulationMode(v33);
                          }
                        }
                      }
                      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32);
                    }
                    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v34);
                  }
                  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v37);
                }
                Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v38);
              }
            }
          }
        }
        goto LABEL_38;
      }
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
    LocalFileStream = CFilePlaceholder::_CreateLocalFileStream(
                        v15,
                        a1[5],
                        *(_QWORD *)(*(_QWORD *)a1 + 120LL),
                        a1[6],
                        (__int64)v30,
                        (__int64)&v33);
    goto LABEL_38;
  }
LABEL_40:
  v28 = *((_QWORD *)a1 + 4);
  if ( v28 )
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v28 + 48LL))(v28, (unsigned int)LocalFileStream, v33);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
  return 0;
}

```

## disassembly

```asm
0x18003d634  mov     rax, rsp
0x18003d637  mov     [rax+10h], rbx
0x18003d63b  mov     [rax+18h], rsi
0x18003d63f  push    rbp
0x18003d640  push    rdi
0x18003d641  push    r13
0x18003d643  push    r14
0x18003d645  push    r15
0x18003d647  lea     rbp, [rax-268h]
0x18003d64e  sub     rsp, 340h
0x18003d655  movaps  xmmword ptr [rax-38h], xmm6
0x18003d659  mov     rax, cs:__security_cookie
0x18003d660  xor     rax, rsp
0x18003d663  mov     [rbp+260h+var_40], rax
0x18003d66a  mov     rsi, rcx
0x18003d66d  mov     [rsp+360h+var_308], 0
0x18003d676  mov     rcx, [rcx+20h]
0x18003d67a  test    rcx, rcx
0x18003d67d  jnz     short loc_18003D683
0x18003d67f  xor     ebx, ebx
0x18003d681  jmp     short loc_18003D691
0x18003d683  mov     rax, [rcx]
0x18003d686  mov     rax, [rax+18h]
0x18003d68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d68f  mov     ebx, eax
0x18003d691  test    ebx, ebx
0x18003d693  js      loc_18003DBBD
0x18003d699  mov     rbx, [rsi]
0x18003d69c  add     rbx, 50h ; 'P'
0x18003d6a0  mov     rcx, rbx; lpCriticalSection
0x18003d6a3  call    cs:__imp_EnterCriticalSection
0x18003d6a9  mov     [rbp+260h+var_2D8], rbx
0x18003d6ad  mov     rax, [rsi]
0x18003d6b0  mov     r14d, [rax+94h]
0x18003d6b7  mov     dword ptr [rsp+360h+var_310], r14d
0x18003d6bc  movups  xmm0, xmmword ptr [rax+98h]
0x18003d6c3  movups  xmmword ptr [rbp+260h+var_2B0.dwFileAttributes], xmm0
0x18003d6c7  movups  xmm1, xmmword ptr [rax+0A8h]
0x18003d6ce  movups  xmmword ptr [rbp+260h+var_2B0.ftLastAccessTime.dwHighDateTime], xmm1
0x18003d6d2  add     rax, 0C4h
0x18003d6d8  lea     rcx, [rbp+260h+var_2B0.nFileSizeLow]
0x18003d6dc  mov     r15d, 4
0x18003d6e2  mov     edx, r15d
0x18003d6e5  lea     r13d, [r15+7Ch]
0x18003d6e9  movups  xmm0, xmmword ptr [rax]
0x18003d6ec  movups  xmmword ptr [rcx], xmm0
0x18003d6ef  movups  xmm1, xmmword ptr [rax+10h]
0x18003d6f3  movups  xmmword ptr [rcx+10h], xmm1
0x18003d6f7  movups  xmm0, xmmword ptr [rax+20h]
0x18003d6fb  movups  xmmword ptr [rcx+20h], xmm0
0x18003d6ff  movups  xmm1, xmmword ptr [rax+30h]
0x18003d703  movups  xmmword ptr [rcx+30h], xmm1
0x18003d707  movups  xmm0, xmmword ptr [rax+40h]
0x18003d70b  movups  xmmword ptr [rcx+40h], xmm0
0x18003d70f  movups  xmm1, xmmword ptr [rax+50h]
0x18003d713  movups  xmmword ptr [rcx+50h], xmm1
0x18003d717  movups  xmm0, xmmword ptr [rax+60h]
0x18003d71b  movups  xmmword ptr [rcx+60h], xmm0
0x18003d71f  movups  xmm1, xmmword ptr [rax+70h]
0x18003d723  movups  xmmword ptr [rcx+70h], xmm1
0x18003d727  add     rcx, r13
0x18003d72a  add     rax, r13
0x18003d72d  sub     rdx, 1
0x18003d731  jnz     short loc_18003D6E9
0x18003d733  movups  xmm0, xmmword ptr [rax]
0x18003d736  movups  xmmword ptr [rcx], xmm0
0x18003d739  movups  xmm1, xmmword ptr [rax+10h]
0x18003d73d  movups  xmmword ptr [rcx+10h], xmm1
0x18003d741  movups  xmm0, xmmword ptr [rax+20h]
0x18003d745  movups  xmmword ptr [rcx+20h], xmm0
0x18003d749  movups  xmm1, xmmword ptr [rax+30h]
0x18003d74d  movups  xmmword ptr [rcx+30h], xmm1
0x18003d751  movups  xmm0, xmmword ptr [rax+40h]
0x18003d755  movups  xmmword ptr [rcx+40h], xmm0
0x18003d759  lea     rcx, [rbp+260h+var_2D8]; this
0x18003d75d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003d762  mov     [rsp+360h+var_2F0], 0
0x18003d76b  mov     rdi, [rsi]
0x18003d76e  mov     rax, [rdi+10h]
0x18003d772  mov     rbx, [rax+40h]
0x18003d776  lea     rcx, [rsp+360h+var_2F0]
0x18003d77b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003d780  lea     rdx, [rsp+360h+var_2F0]
0x18003d785  lea     rcx, [rdi+10h]
0x18003d789  mov     rax, rbx
0x18003d78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d791  mov     ebx, eax
0x18003d793  test    eax, eax
0x18003d795  js      loc_18003DBA9
0x18003d79b  mov     [rsp+360h+var_2F8], 0
0x18003d7a4  lea     rcx, [rsp+360h+var_2F8]
0x18003d7a9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003d7ae  mov     rdx, [rsi]
0x18003d7b1  lea     r8, [rsp+360h+var_2F8]; unsigned __int16 *
0x18003d7b6  mov     rdx, [rdx+78h]; struct IPropertyStore *
0x18003d7ba  mov     rcx, [rsp+360h+var_2F0]; this
0x18003d7bf  call    ?CreateFilePlaceholderStreamResolver@FilePlaceholderHelper@Internal@Windows@@YAJPEAUIPropertyStore@@PEBGPEAPEAUIFilePlaceholderStreamResolver@@@Z; Windows::Internal::FilePlaceholderHelper::CreateFilePlaceholderStreamResolver(IPropertyStore *,ushort const *,IFilePlaceholderStreamResolver * *)
0x18003d7c4  mov     ebx, eax
0x18003d7c6  test    eax, eax
0x18003d7c8  jns     short loc_18003D7DA
0x18003d7ca  cmp     eax, 80070490h
0x18003d7cf  jnz     loc_18003DB9E
0x18003d7d5  test    r15b, r14b
0x18003d7d8  jnz     short loc_18003D7E4
0x18003d7da  and     r14d, 3
0x18003d7de  cmp     r14b, 3
0x18003d7e2  jnz     short loc_18003D812
0x18003d7e4  lea     rcx, [rsp+360h+var_308]
0x18003d7e9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003d7ee  mov     r8, [rsi]
0x18003d7f1  lea     rax, [rsp+360h+var_308]
0x18003d7f6  mov     qword ptr [rsp+360h+var_338], rax
0x18003d7fb  mov     r9d, [rsi+18h]
0x18003d7ff  mov     r8, [r8+78h]
0x18003d803  mov     edx, [rsi+14h]
0x18003d806  call    ?_CreateLocalFileStream@CFilePlaceholder@@AEAAJW4FILE_PLACEHOLDER_STREAM_HANDLER@@PEBGKAEBU_GUID@@PEAPEAX@Z; CFilePlaceholder::_CreateLocalFileStream(FILE_PLACEHOLDER_STREAM_HANDLER,ushort const *,ulong,_GUID const &,void * *)
0x18003d80b  mov     ebx, eax
0x18003d80d  jmp     loc_18003DB9E
0x18003d812  test    eax, eax
0x18003d814  js      loc_18003DB9E
0x18003d81a  mov     qword ptr [rbp+260h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003d822  lea     rcx, [rbp+260h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003d826  call    cs:__imp_GetSystemTimeAsFileTime
0x18003d82c  mov     r8, [rsi]
0x18003d82f  mov     r9, [rsi+20h]; unsigned __int16 *
0x18003d833  mov     r8, [r8+78h]; struct IPropertyStore *
0x18003d837  mov     rdx, [rsp+360h+var_2F0]; struct IFilePlaceholderStreamResolver *
0x18003d83c  mov     rcx, [rsp+360h+var_2F8]; this
0x18003d841  call    ?VerifyFileVersionSyncWithWritableExtrinsicPropertyStore@FilePlaceholderHelper@Internal@Windows@@YAJPEAUIFilePlaceholderStreamResolver@@PEAUIPropertyStore@@PEBGPEAUIFilePlaceholderCallback@@@Z; Windows::Internal::FilePlaceholderHelper::VerifyFileVersionSyncWithWritableExtrinsicPropertyStore(IFilePlaceholderStreamResolver *,IPropertyStore *,ushort const *,IFilePlaceholderCallback *)
0x18003d846  mov     ebx, eax
0x18003d848  test    eax, eax
0x18003d84a  js      loc_18003DB9E
0x18003d850  mov     rcx, [rsi+20h]
0x18003d854  test    rcx, rcx
0x18003d857  jz      short loc_18003D86F
0x18003d859  mov     rax, [rcx]
0x18003d85c  mov     rax, [rax+18h]
0x18003d860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d865  mov     ebx, eax
0x18003d867  test    eax, eax
0x18003d869  js      loc_18003DB9E
0x18003d86f  mov     rcx, [rsi]
0x18003d872  lea     rdx, [rbp+260h+var_2B0.nFileSizeLow]; lpFindFileData
0x18003d876  mov     rcx, [rcx+78h]; lpFileName
0x18003d87a  call    cs:__imp_FindFirstFileW
0x18003d880  mov     rdi, rax
0x18003d883  test    rax, rax
0x18003d886  jnz     short loc_18003D897
0x18003d888  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003d88d  mov     ebx, eax
0x18003d88f  test    eax, eax
0x18003d891  js      loc_18003DB9E
0x18003d897  mov     rcx, rdi; hFindFile
0x18003d89a  call    cs:__imp_FindClose
0x18003d8a0  lea     r8, [rsp+360h+var_310]; struct FILE_PLACEHOLDER_INFORMATION *
0x18003d8a5  lea     rdx, [rbp+260h+var_2B0]; struct _WIN32_FIND_DATAW *
0x18003d8a9  lea     rcx, [rbp+260h+var_2B0.nFileSizeLow]; this
0x18003d8ad  call    ?GetFilePlaceholderInformationAndStatesFromFindData@FilePlaceholderHelper@Internal@Windows@@YAXAEBU_WIN32_FIND_DATAW@@PEAUFILE_PLACEHOLDER_INFORMATION@@PEAW4PLACEHOLDER_STATES@@@Z; Windows::Internal::FilePlaceholderHelper::GetFilePlaceholderInformationAndStatesFromFindData(_WIN32_FIND_DATAW const &,FILE_PLACEHOLDER_INFORMATION *,PLACEHOLDER_STATES *)
0x18003d8b2  mov     rbx, [rsi]
0x18003d8b5  add     rbx, 50h ; 'P'
0x18003d8b9  mov     rcx, rbx; lpCriticalSection
0x18003d8bc  call    cs:__imp_EnterCriticalSection
0x18003d8c2  mov     [rbp+260h+var_2E0], rbx
0x18003d8c6  mov     rax, [rsi]
0x18003d8c9  mov     ebx, dword ptr [rsp+360h+var_310]
0x18003d8cd  mov     [rax+94h], ebx
0x18003d8d3  mov     rax, [rsi]
0x18003d8d6  movups  xmm0, xmmword ptr [rbp+260h+var_2B0.dwFileAttributes]
0x18003d8da  movups  xmmword ptr [rax+98h], xmm0
0x18003d8e1  movups  xmm6, xmmword ptr [rbp+260h+var_2B0.ftLastAccessTime.dwHighDateTime]
0x18003d8e5  movups  xmmword ptr [rax+0A8h], xmm6
0x18003d8ec  mov     rax, [rsi]
0x18003d8ef  add     rax, 0C4h
0x18003d8f5  lea     rcx, [rbp+260h+var_2B0.nFileSizeLow]
0x18003d8f9  movups  xmm0, xmmword ptr [rcx]
0x18003d8fc  movups  xmmword ptr [rax], xmm0
0x18003d8ff  movups  xmm1, xmmword ptr [rcx+10h]
0x18003d903  movups  xmmword ptr [rax+10h], xmm1
0x18003d907  movups  xmm0, xmmword ptr [rcx+20h]
0x18003d90b  movups  xmmword ptr [rax+20h], xmm0
0x18003d90f  movups  xmm1, xmmword ptr [rcx+30h]
0x18003d913  movups  xmmword ptr [rax+30h], xmm1
0x18003d917  movups  xmm0, xmmword ptr [rcx+40h]
0x18003d91b  movups  xmmword ptr [rax+40h], xmm0
0x18003d91f  movups  xmm1, xmmword ptr [rcx+50h]
0x18003d923  movups  xmmword ptr [rax+50h], xmm1
0x18003d927  movups  xmm0, xmmword ptr [rcx+60h]
0x18003d92b  movups  xmmword ptr [rax+60h], xmm0
0x18003d92f  movups  xmm1, xmmword ptr [rcx+70h]
0x18003d933  movups  xmmword ptr [rax+70h], xmm1
0x18003d937  add     rax, r13
0x18003d93a  add     rcx, r13
0x18003d93d  sub     r15, 1
0x18003d941  jnz     short loc_18003D8F9
0x18003d943  movups  xmm0, xmmword ptr [rcx]
0x18003d946  movups  xmmword ptr [rax], xmm0
0x18003d949  movups  xmm1, xmmword ptr [rcx+10h]
0x18003d94d  movups  xmmword ptr [rax+10h], xmm1
0x18003d951  movups  xmm0, xmmword ptr [rcx+20h]
0x18003d955  movups  xmmword ptr [rax+20h], xmm0
0x18003d959  movups  xmm1, xmmword ptr [rcx+30h]
0x18003d95d  movups  xmmword ptr [rax+30h], xmm1
0x18003d961  movups  xmm0, xmmword ptr [rcx+40h]
0x18003d965  movups  xmmword ptr [rax+40h], xmm0
0x18003d969  lea     rcx, [rbp+260h+var_2E0]; this
0x18003d96d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003d972  test    bl, 2
0x18003d975  jz      short loc_18003D9A5
0x18003d977  lea     rcx, [rsp+360h+var_308]
0x18003d97c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003d981  mov     r8, [rsi]
0x18003d984  lea     rax, [rsp+360h+var_308]
0x18003d989  mov     qword ptr [rsp+360h+var_338], rax
0x18003d98e  mov     r9d, [rsi+18h]
0x18003d992  mov     r8, [r8+78h]
0x18003d996  mov     edx, [rsi+14h]
0x18003d999  call    ?_CreateLocalFileStream@CFilePlaceholder@@AEAAJW4FILE_PLACEHOLDER_STREAM_HANDLER@@PEBGKAEBU_GUID@@PEAPEAX@Z; CFilePlaceholder::_CreateLocalFileStream(FILE_PLACEHOLDER_STREAM_HANDLER,ushort const *,ulong,_GUID const &,void * *)
0x18003d99e  mov     ebx, eax
0x18003d9a0  jmp     loc_18003DB94
0x18003d9a5  mov     [rsp+360h+var_2E8], 0
0x18003d9ae  mov     rdi, [rsi]
0x18003d9b1  mov     rax, [rdi]
0x18003d9b4  mov     rbx, [rax]
0x18003d9b7  lea     rcx, [rsp+360h+var_2E8]
0x18003d9bc  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003d9c1  lea     r8, [rsp+360h+var_2E8]
0x18003d9c6  lea     rdx, _GUID_c8b34e60_6ee3_4881_9138_6b4fb6bfb461
0x18003d9cd  mov     rcx, rdi
0x18003d9d0  mov     rax, rbx
0x18003d9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9d8  mov     ebx, eax
0x18003d9da  test    eax, eax
0x18003d9dc  js      loc_18003DB89
0x18003d9e2  mov     [rsp+360h+var_300], 0
0x18003d9eb  lea     rcx, [rsp+360h+var_300]
0x18003d9f0  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003d9f5  mov     rax, [rsi+20h]
0x18003d9f9  mov     [rbp+260h+var_2C0], rax
0x18003d9fd  mov     rax, [rsp+360h+var_2F8]
0x18003da02  mov     [rbp+260h+var_2B8], rax
0x18003da06  movsd   [rbp+260h+var_2C8], xmm6
0x18003da0b  mov     [rsp+360h+var_300], 0
0x18003da14  mov     [rsp+360h+var_310], 0
0x18003da1d  lea     rcx, [rsp+360h+var_310]
0x18003da22  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003da27  lea     r9, [rbp+260h+var_2C8]
0x18003da2b  lea     r8, [rbp+260h+var_2C0]
0x18003da2f  lea     rdx, [rbp+260h+var_2B8]
0x18003da33  lea     rcx, [rsp+360h+var_310]
0x18003da38  call    ??$MakeAndInitialize@VCFilePlaceholderRemoteStream@@V1@AEAPEAUIFilePlaceholderStreamResolver@@AEAPEAUIFilePlaceholderCallback@@AEA_K@Details@WRL@Microsoft@@YAJPEAPEAVCFilePlaceholderRemoteStream@@AEAPEAUIFilePlaceholderStreamResolver@@AEAPEAUIFilePlaceholderCallback@@AEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<CFilePlaceholderRemoteStream,CFilePlaceholderRemoteStream,IFilePlaceholderStreamResolver * &,IFilePlaceholderCallback * &,unsigned __int64 &>(CFilePlaceholderRemoteStream * *,IFilePlaceholderStreamResolver * &,IFilePlaceholderCallback * &,unsigned __int64 &)
0x18003da3d  mov     ebx, eax
0x18003da3f  test    eax, eax
0x18003da41  js      short loc_18003DA61
0x18003da43  mov     rcx, [rsp+360h+var_310]
0x18003da48  mov     rax, [rcx]
0x18003da4b  lea     r8, [rsp+360h+var_300]
0x18003da50  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18003da57  mov     rax, [rax]
0x18003da5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da5f  mov     ebx, eax
0x18003da61  lea     rcx, [rsp+360h+var_310]
0x18003da66  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003da6b  test    ebx, ebx
0x18003da6d  js      loc_18003DB7E
0x18003da73  mov     [rsp+360h+var_310], 0
0x18003da7c  lea     rcx, [rsp+360h+var_310]
0x18003da81  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003da86  mov     r10, [rsp+360h+var_2E8]
0x18003da8b  mov     r8d, [rsi+18h]
0x18003da8f  shr     r8d, 10h
0x18003da93  and     r8d, 1
0x18003da97  test    dword ptr [rsi+18h], 1003h
0x18003da9e  mov     edx, 0
0x18003daa3  setnz   dl
0x18003daa6  mov     rcx, [rsi]
0x18003daa9  lea     rax, [rsp+360h+var_310]
0x18003daae  mov     [rsp+360h+var_320], rax
0x18003dab3  lea     rax, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18003daba  mov     [rsp+360h+var_328], rax
0x18003dabf  mov     eax, [rsi+10h]
0x18003dac2  mov     dword ptr [rsp+360h+var_330], eax
0x18003dac6  mov     rax, [rsi+20h]
0x18003daca  mov     qword ptr [rsp+360h+var_338], rax
0x18003dacf  mov     [rsp+360h+var_340], r10
0x18003dad4  mov     r9, [rsp+360h+var_300]
0x18003dad9  mov     rcx, [rcx+78h]
0x18003dadd  call    cs:__imp_CreateRandomAccessStreamOnPlaceholderFile
0x18003dae3  mov     ebx, eax
0x18003dae5  test    eax, eax
0x18003dae7  js      loc_18003DB73
0x18003daed  mov     eax, [rsi+18h]
0x18003daf0  mov     ecx, 11000h
0x18003daf5  and     eax, ecx
0x18003daf7  cmp     eax, ecx
0x18003daf9  jnz     short loc_18003DB14
0x18003dafb  mov     rcx, [rsp+360h+var_310]
0x18003db00  mov     rax, [rcx]
0x18003db03  xor     edx, edx
0x18003db05  mov     rax, [rax+38h]
0x18003db09  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
