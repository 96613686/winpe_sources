# LoadMofsInDirectory(ushort const *)

- ea: `0x18000ba0c`
- end: `0x18000c01c`
- name: `?LoadMofsInDirectory@@YAXPEBG@Z`
- size: `1552`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180008840`

## callees

- `0x180004120`
- `0x180004c30`
- `0x18000a33c`
- `0x18000ba0c`
- `0x180012e9c`
- `0x18001323c`
- `0x18001329c`
- `0x18001d377`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd4f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000bf8d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000bf8d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bfb4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bfbf`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bfb4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bfbf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000be58`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000be58`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000be4f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000bf19`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000be4f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000bf19`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bbd1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bbd1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bcd1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bcd1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000be3c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bf06`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000be3c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bf06`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bce7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bce7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000befd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000befd`
- `wbemcomn!TestDirExistAndCreateWithSDIfNotThere` at `0x18000bb83`
- `wbemcomn!TestDirExistAndCreateWithSDIfNotThere` at `0x18000bb97`
- `wbemcomn!TestDirExistAndCreateWithSDIfNotThere` at `0x18000bbab`
- `wbemcomn!TestDirExistAndCreateWithSDIfNotThere` at `0x18000bb83`
- `wbemcomn!TestDirExistAndCreateWithSDIfNotThere` at `0x18000bb97`
- `wbemcomn!TestDirExistAndCreateWithSDIfNotThere` at `0x18000bbab`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bf6c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bf76`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bfaa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bfdf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bfe9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bff3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bf6c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bf76`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bfaa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bfdf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bfe9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bff3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ba81`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000bab6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000baf4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000bc2a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000be06`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ba81`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000bab6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000baf4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000bc2a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000be06`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bd7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bd7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LoadMofsInDirectory(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // r12
  __int64 v2; // rax
  unsigned __int64 v3; // r15
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rsi
  __int64 v6; // rcx
  unsigned __int64 v7; // rdi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r14
  __int64 v10; // rax
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r15
  HANDLE FirstFileW; // rax
  void *v15; // r13
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rbx
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rdi
  int v21; // ebx
  HANDLE FileW; // rax
  LPVOID v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // r12
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rbx
  DWORD FileAttributesW; // eax
  int v30; // r8d
  _QWORD *v31; // rcx
  int v32; // r15d
  const char *v33; // rax
  DWORD v34; // eax
  int v35; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v36; // [rsp+58h] [rbp-A8h]
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v38; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v39; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v40; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v41; // [rsp+80h] [rbp-80h]
  HANDLE v42; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v43; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v44; // [rsp+98h] [rbp-68h]
  __int128 v45; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF

  if ( a1 )
  {
    v1 = a1;
    v38 = a1;
    if ( !(unsigned int)CheckGlobalSetupSwitch() )
    {
      v2 = -1;
      do
        ++v2;
      while ( v1[v2] );
      v3 = v2 + 3;
      v4 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v2 + 3, 2u));
      v5 = v4;
      if ( v4 )
      {
        v39 = v4;
        v6 = -1;
        do
          ++v6;
        while ( v1[v6] );
        v7 = v6 + 6;
        v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v6 + 6, 2u));
        v9 = v8;
        if ( v8 )
        {
          v40 = v8;
          v10 = -1;
          do
            ++v10;
          while ( v1[v10] );
          v11 = v10 + 7;
          v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v10 + 7, 2u));
          v36 = v12;
          if ( v12 )
          {
            v41 = v12;
            ppv = 0;
            StringCchCopyW(v5, v3, v1);
            StringCchCatW(v5, v3, L"\\*");
            StringCchCopyW(v9, v7, v1);
            StringCchCatW(v9, v7, L"\\bad\\");
            v13 = v36;
            StringCchCopyW(v36, v11, v1);
            StringCchCatW(v36, v11, L"\\good\\");
            if ( (int)TestDirExistAndCreateWithSDIfNotThere(v1, L"D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)") >= 0
              && (int)TestDirExistAndCreateWithSDIfNotThere(v9, L"D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)") >= 0
              && (int)TestDirExistAndCreateWithSDIfNotThere(v36, L"D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)") >= 0 )
            {
              memset_0(&FindFileData, 0, sizeof(FindFileData));
              FirstFileW = FindFirstFileW(v5, &FindFileData);
              v15 = FirstFileW;
              if ( FirstFileW != (HANDLE)-1LL )
              {
                v42 = FirstFileW;
                while ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
LABEL_71:
                  if ( !FindNextFileW(v15, &FindFileData) )
                  {
                    FindClose(v15);
                    goto LABEL_77;
                  }
                }
                v16 = -1;
                do
                  ++v16;
                while ( FindFileData.cFileName[v16] );
                v17 = -1;
                do
                  ++v17;
                while ( v1[v17] );
                v18 = v16 + v17 + 2;
                v19 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v18, 2u));
                v20 = v19;
                if ( !v19 )
                  goto LABEL_75;
                v43 = v19;
                StringCchCopyW(v19, v18, v1);
                StringCchCatW(v20, v18, L"\\");
                StringCchCatW(v20, v18, FindFileData.cFileName);
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    15,
                    WPP_1ead9032b647397af64ee4622953436c_Traceguids,
                    v20);
                }
                v21 = 10;
                while ( 1 )
                {
                  FileW = CreateFileW(v20, 0x80000000, 0, 0, 3u, 0x80u, 0);
                  if ( FileW != (HANDLE)-1LL )
                    break;
                  if ( !--v21 )
                    break;
                  Sleep(0x3E8u);
                }
                v45 = 0;
                v46 = 0;
                v13 = v36;
                if ( FileW == (HANDLE)-1LL )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      16,
                      WPP_1ead9032b647397af64ee4622953436c_Traceguids,
                      v20);
                  }
                  v35 = 1;
                }
                else
                {
                  CloseHandle(FileW);
                  v23 = ppv;
                  if ( !ppv )
                  {
                    if ( CoCreateInstance(&CLSID_MofCompilerOOP, 0, 0x10004u, &IID_IWinmgmtMofCompilerOOP, &ppv) )
                      goto LABEL_74;
                    v23 = ppv;
                  }
                  v35 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD, __int64, _DWORD, _DWORD, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v23 + 24LL))(
                          v23,
                          v20,
                          0,
                          16,
                          0,
                          0,
                          0,
                          0,
                          &v45);
                  if ( !v35 )
                  {
LABEL_42:
                    v24 = -1;
                    do
                      ++v24;
                    while ( v13[v24] );
                    v25 = -1;
                    do
                      ++v25;
                    while ( FindFileData.cFileName[v25] );
                    v26 = v25 + v24 + 1;
                    v27 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v26, 2u));
                    v28 = v27;
                    if ( !v27 )
                    {
                      v13 = v36;
LABEL_74:
                      CWin32DefaultArena::WbemMemFree(v20);
LABEL_75:
                      FindClose(v15);
                      goto LABEL_79;
                    }
                    v44 = v27;
                    StringCchCopyW(v27, v26, v13);
                    StringCchCatW(v28, v26, FindFileData.cFileName);
                    FileAttributesW = GetFileAttributesW(v28);
                    if ( FileAttributesW != -1 )
                    {
                      SetFileAttributesW(v28, FileAttributesW & 0xFFFFFFFE);
                      if ( DeleteFileW(v28) )
                      {
                        v31 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                          goto LABEL_60;
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
                        {
LABEL_54:
                          if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 )
                          {
                            v32 = v35;
                            if ( *((_BYTE *)v31 + 25) >= 5u )
                            {
                              v33 = "unsuccessful";
                              if ( !v35 )
                                v33 = "successful";
                              WPP_SF_SsS(
                                v31[2],
                                (unsigned int)"successful",
                                v30,
                                (_DWORD)v20,
                                (__int64)v33,
                                (__int64)v28);
                            }
                            goto LABEL_61;
                          }
LABEL_60:
                          v32 = v35;
LABEL_61:
                          MoveFileExW(v20, v28, 2u);
                          v34 = GetFileAttributesW(v28);
                          if ( v34 != -1 )
                            SetFileAttributesW(v28, v34 | 1);
                          if ( !v32 && (v46 & 0x100000000LL) != 0 )
                          {
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                            {
                              WPP_SF_S(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                19,
                                WPP_1ead9032b647397af64ee4622953436c_Traceguids,
                                v28);
                            }
                            AddToAutoRecoverList(v28);
                          }
                          CWin32DefaultArena::WbemMemFree(v28);
                          CWin32DefaultArena::WbemMemFree(v20);
                          v1 = (unsigned __int16 *)v38;
                          v13 = v36;
                          goto LABEL_71;
                        }
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          17,
                          WPP_1ead9032b647397af64ee4622953436c_Traceguids,
                          v28);
                      }
                    }
                    v31 = WPP_GLOBAL_Control;
                    goto LABEL_54;
                  }
                }
                v13 = v9;
                goto LABEL_42;
              }
LABEL_77:
              if ( ppv )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            }
LABEL_79:
            CWin32DefaultArena::WbemMemFree(v13);
          }
          CWin32DefaultArena::WbemMemFree(v9);
        }
        CWin32DefaultArena::WbemMemFree(v5);
      }
    }
  }
}

```

## disassembly

```asm
0x18000ba0c  test    rcx, rcx
0x18000ba0f  jz      locret_18000C01B
0x18000ba15  push    rbp
0x18000ba16  push    rbx
0x18000ba17  push    rsi
0x18000ba18  push    rdi
0x18000ba19  push    r12
0x18000ba1b  push    r13
0x18000ba1d  push    r14
0x18000ba1f  push    r15
0x18000ba21  lea     rbp, [rsp-228h]
0x18000ba29  sub     rsp, 328h
0x18000ba30  mov     rax, cs:__security_cookie
0x18000ba37  xor     rax, rsp
0x18000ba3a  mov     [rbp+260h+var_50], rax
0x18000ba41  mov     r12, rcx
0x18000ba44  mov     [rsp+360h+var_2F8], rcx
0x18000ba49  xor     r13d, r13d
0x18000ba4c  call    ?CheckGlobalSetupSwitch@@YAHXZ; CheckGlobalSetupSwitch(void)
0x18000ba51  test    eax, eax
0x18000ba53  jnz     loc_18000BFF9
0x18000ba59  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ba5d  mov     rax, rbx
0x18000ba60  inc     rax
0x18000ba63  cmp     [r12+rax*2], r13w
0x18000ba68  jnz     short loc_18000BA60
0x18000ba6a  lea     r15, [rax+3]
0x18000ba6e  mov     r14d, 2
0x18000ba74  mov     eax, r14d
0x18000ba77  mul     r15
0x18000ba7a  cmovb   rax, rbx
0x18000ba7e  mov     rcx, rax
0x18000ba81  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ba87  mov     rsi, rax
0x18000ba8a  test    rax, rax
0x18000ba8d  jz      loc_18000BFF9
0x18000ba93  mov     [rsp+360h+var_2F0], rax
0x18000ba98  mov     rcx, rbx
0x18000ba9b  inc     rcx
0x18000ba9e  cmp     [r12+rcx*2], r13w
0x18000baa3  jnz     short loc_18000BA9B
0x18000baa5  lea     rdi, [rcx+6]
0x18000baa9  mov     rax, r14
0x18000baac  mul     rdi
0x18000baaf  cmovb   rax, rbx
0x18000bab3  mov     rcx, rax
0x18000bab6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000babc  mov     r14, rax
0x18000babf  test    rax, rax
0x18000bac2  jz      loc_18000BFF0
0x18000bac8  mov     [rsp+360h+var_2E8], rax
0x18000bacd  mov     rax, rbx
0x18000bad0  inc     rax
0x18000bad3  cmp     [r12+rax*2], r13w
0x18000bad8  jnz     short loc_18000BAD0
0x18000bada  lea     rbx, [rax+7]
0x18000bade  mov     eax, 2
0x18000bae3  mul     rbx
0x18000bae6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000baed  cmovb   rax, rcx
0x18000baf1  mov     rcx, rax
0x18000baf4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000bafa  mov     [rsp+360h+var_308], rax
0x18000baff  test    rax, rax
0x18000bb02  jz      loc_18000BFE6
0x18000bb08  mov     [rbp+260h+var_2E0], rax
0x18000bb0c  mov     [rsp+360h+ppv], r13
0x18000bb11  mov     r8, r12; unsigned __int16 *
0x18000bb14  mov     rdx, r15; unsigned __int64
0x18000bb17  mov     rcx, rsi; unsigned __int16 *
0x18000bb1a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bb1f  lea     r8, asc_180024ED8; "\\*"
0x18000bb26  mov     rdx, r15; unsigned __int64
0x18000bb29  mov     rcx, rsi; unsigned __int16 *
0x18000bb2c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bb31  mov     r8, r12; unsigned __int16 *
0x18000bb34  mov     rdx, rdi; unsigned __int64
0x18000bb37  mov     rcx, r14; unsigned __int16 *
0x18000bb3a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bb3f  lea     r8, aBad; "\\bad\\"
0x18000bb46  mov     rdx, rdi; unsigned __int64
0x18000bb49  mov     rcx, r14; unsigned __int16 *
0x18000bb4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bb51  mov     r8, r12; unsigned __int16 *
0x18000bb54  mov     rdx, rbx; unsigned __int64
0x18000bb57  mov     r15, [rsp+360h+var_308]
0x18000bb5c  mov     rcx, r15; unsigned __int16 *
0x18000bb5f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bb64  lea     r8, aGood; "\\good\\"
0x18000bb6b  mov     rdx, rbx; unsigned __int64
0x18000bb6e  mov     rcx, r15; unsigned __int16 *
0x18000bb71  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bb76  lea     rbx, aDPACioiGaBaACi; "D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)"
0x18000bb7d  mov     rdx, rbx
0x18000bb80  mov     rcx, r12
0x18000bb83  call    cs:__imp_?TestDirExistAndCreateWithSDIfNotThere@@YAJPEAG0@Z; TestDirExistAndCreateWithSDIfNotThere(ushort *,ushort *)
0x18000bb89  test    eax, eax
0x18000bb8b  js      loc_18000BFDC
0x18000bb91  mov     rdx, rbx
0x18000bb94  mov     rcx, r14
0x18000bb97  call    cs:__imp_?TestDirExistAndCreateWithSDIfNotThere@@YAJPEAG0@Z; TestDirExistAndCreateWithSDIfNotThere(ushort *,ushort *)
0x18000bb9d  test    eax, eax
0x18000bb9f  js      loc_18000BFDC
0x18000bba5  mov     rdx, rbx
0x18000bba8  mov     rcx, r15
0x18000bbab  call    cs:__imp_?TestDirExistAndCreateWithSDIfNotThere@@YAJPEAG0@Z; TestDirExistAndCreateWithSDIfNotThere(ushort *,ushort *)
0x18000bbb1  test    eax, eax
0x18000bbb3  js      loc_18000BFDC
0x18000bbb9  xor     edx, edx; Val
0x18000bbbb  mov     r8d, 250h; Size
0x18000bbc1  lea     rcx, [rbp+260h+FindFileData]; void *
0x18000bbc5  call    memset_0
0x18000bbca  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x18000bbce  mov     rcx, rsi; lpFileName
0x18000bbd1  call    cs:__imp_FindFirstFileW
0x18000bbd7  mov     r13, rax
0x18000bbda  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000bbde  cmp     rax, r8
0x18000bbe1  jz      loc_18000BFC5
0x18000bbe7  mov     [rbp+260h+var_2D8], rax
0x18000bbeb  xor     edx, edx
0x18000bbed  test    byte ptr [rbp+260h+FindFileData.dwFileAttributes], 10h
0x18000bbf1  jnz     loc_18000BF86
0x18000bbf7  lea     rax, [rbp+260h+FindFileData.cFileName]
0x18000bbfb  mov     rcx, r8
0x18000bbfe  inc     rcx
0x18000bc01  cmp     [rax+rcx*2], dx
0x18000bc05  jnz     short loc_18000BBFE
0x18000bc07  mov     rax, r8
0x18000bc0a  inc     rax
0x18000bc0d  cmp     [r12+rax*2], dx
0x18000bc12  jnz     short loc_18000BC0A
0x18000bc14  lea     rbx, [rax+2]
0x18000bc18  add     rbx, rcx
0x18000bc1b  mov     eax, 2
0x18000bc20  mul     rbx
0x18000bc23  cmovb   rax, r8
0x18000bc27  mov     rcx, rax
0x18000bc2a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000bc30  mov     rdi, rax
0x18000bc33  test    rax, rax
0x18000bc36  jz      loc_18000BFB1
0x18000bc3c  mov     [rbp+260h+var_2D0], rax
0x18000bc40  mov     r8, r12; unsigned __int16 *
0x18000bc43  mov     rdx, rbx; unsigned __int64
0x18000bc46  mov     rcx, rax; unsigned __int16 *
0x18000bc49  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bc4e  lea     r8, asc_1800231B8; "\\"
0x18000bc55  mov     rdx, rbx; unsigned __int64
0x18000bc58  mov     rcx, rdi; unsigned __int16 *
0x18000bc5b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc60  lea     r8, [rbp+260h+FindFileData.cFileName]; unsigned __int16 *
0x18000bc64  mov     rdx, rbx; unsigned __int64
0x18000bc67  mov     rcx, rdi; unsigned __int16 *
0x18000bc6a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc76  lea     rax, WPP_GLOBAL_Control
0x18000bc7d  cmp     rcx, rax
0x18000bc80  jz      short loc_18000BCA6
0x18000bc82  test    byte ptr [rcx+1Ch], 1
0x18000bc86  jz      short loc_18000BCA6
0x18000bc88  cmp     byte ptr [rcx+19h], 5
0x18000bc8c  jb      short loc_18000BCA6
0x18000bc8e  mov     edx, 0Fh
0x18000bc93  mov     r9, rdi
0x18000bc96  lea     r8, WPP_1ead9032b647397af64ee4622953436c_Traceguids
0x18000bc9d  mov     rcx, [rcx+10h]
0x18000bca1  call    WPP_SF_S
0x18000bca6  mov     ebx, 0Ah
0x18000bcab  xor     r12d, r12d
0x18000bcae  mov     [rsp+360h+hTemplateFile], r12; hTemplateFile
0x18000bcb3  mov     [rsp+360h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000bcbb  mov     [rsp+360h+dwCreationDisposition], 3; dwCreationDisposition
0x18000bcc3  xor     r9d, r9d; lpSecurityAttributes
0x18000bcc6  xor     r8d, r8d; dwShareMode
0x18000bcc9  mov     edx, 80000000h; dwDesiredAccess
0x18000bcce  mov     rcx, rdi; lpFileName
0x18000bcd1  call    cs:__imp_CreateFileW
0x18000bcd7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bcdb  jnz     short loc_18000BCEF
0x18000bcdd  add     ebx, 0FFFFFFFFh
0x18000bce0  jz      short loc_18000BCEF
0x18000bce2  mov     ecx, 3E8h; dwMilliseconds
0x18000bce7  call    cs:__imp_Sleep
0x18000bced  jmp     short loc_18000BCAE
0x18000bcef  xorps   xmm0, xmm0
0x18000bcf2  xor     ecx, ecx
0x18000bcf4  movups  [rbp+260h+var_2C0], xmm0
0x18000bcf8  mov     [rbp+260h+var_2B0], rcx
0x18000bcfc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bd00  cmp     rax, rbx
0x18000bd03  mov     r15, [rsp+360h+var_308]
0x18000bd08  jnz     short loc_18000BD4C
0x18000bd0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd11  lea     rax, WPP_GLOBAL_Control
0x18000bd18  cmp     rcx, rax
0x18000bd1b  jz      short loc_18000BD3F
0x18000bd1d  test    byte ptr [rcx+1Ch], 1
0x18000bd21  jz      short loc_18000BD3F
0x18000bd23  cmp     byte ptr [rcx+19h], 5
0x18000bd27  jb      short loc_18000BD3F
0x18000bd29  lea     edx, [rbx+11h]
0x18000bd2c  mov     r9, rdi
0x18000bd2f  lea     r8, WPP_1ead9032b647397af64ee4622953436c_Traceguids
0x18000bd36  mov     rcx, [rcx+10h]
0x18000bd3a  call    WPP_SF_S
0x18000bd3f  mov     [rsp+360h+var_310], 1
0x18000bd47  jmp     loc_18000BDCF
0x18000bd4c  mov     rcx, rax; hObject
0x18000bd4f  call    cs:__imp_CloseHandle
0x18000bd55  mov     rcx, [rsp+360h+ppv]
0x18000bd5a  test    rcx, rcx
0x18000bd5d  jnz     short loc_18000BD92
0x18000bd5f  lea     rax, [rsp+360h+ppv]
0x18000bd64  mov     qword ptr [rsp+360h+dwCreationDisposition], rax; ppv
0x18000bd69  lea     r9, IID_IWinmgmtMofCompilerOOP; riid
0x18000bd70  xor     edx, edx; pUnkOuter
0x18000bd72  mov     r8d, 10004h; dwClsContext
0x18000bd78  lea     rcx, CLSID_MofCompilerOOP; rclsid
0x18000bd7f  call    cs:__imp_CoCreateInstance
0x18000bd85  test    eax, eax
0x18000bd87  jnz     loc_18000BFA7
0x18000bd8d  mov     rcx, [rsp+360h+ppv]
0x18000bd92  mov     rax, [rcx]
0x18000bd95  lea     rdx, [rbp+260h+var_2C0]
0x18000bd99  mov     [rsp+360h+var_320], rdx
0x18000bd9e  mov     [rsp+360h+var_328], r12
0x18000bda3  mov     [rsp+360h+hTemplateFile], r12
0x18000bda8  mov     [rsp+360h+dwFlagsAndAttributes], r12d
0x18000bdad  mov     [rsp+360h+dwCreationDisposition], r12d
0x18000bdb2  mov     r9d, 10h
0x18000bdb8  xor     r8d, r8d
0x18000bdbb  mov     rdx, rdi
0x18000bdbe  mov     rax, [rax+18h]
0x18000bdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdc7  mov     [rsp+360h+var_310], eax
0x18000bdcb  test    eax, eax
0x18000bdcd  jz      short loc_18000BDD2
0x18000bdcf  mov     r15, r14
0x18000bdd2  mov     rcx, rbx
0x18000bdd5  inc     rcx
0x18000bdd8  cmp     [r15+rcx*2], r12w
0x18000bddd  jnz     short loc_18000BDD5
0x18000bddf  lea     rdx, [rbp+260h+FindFileData.cFileName]
0x18000bde3  mov     rax, rbx
0x18000bde6  inc     rax
0x18000bde9  cmp     [rdx+rax*2], r12w
0x18000bdee  jnz     short loc_18000BDE6
0x18000bdf0  lea     r12, [rcx+1]
0x18000bdf4  add     r12, rax
0x18000bdf7  mov     eax, 2
0x18000bdfc  mul     r12
0x18000bdff  cmovb   rax, rbx
0x18000be03  mov     rcx, rax
0x18000be06  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000be0c  mov     rbx, rax
0x18000be0f  test    rax, rax
0x18000be12  jz      loc_18000BFA2
0x18000be18  mov     [rbp+260h+var_2C8], rax
0x18000be1c  mov     r8, r15; unsigned __int16 *
0x18000be1f  mov     rdx, r12; unsigned __int64
0x18000be22  mov     rcx, rax; unsigned __int16 *
0x18000be25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be2a  lea     r8, [rbp+260h+FindFileData.cFileName]; unsigned __int16 *
0x18000be2e  mov     rdx, r12; unsigned __int64
0x18000be31  mov     rcx, rbx; unsigned __int16 *
0x18000be34  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000be39  mov     rcx, rbx; lpFileName
0x18000be3c  call    cs:__imp_GetFileAttributesW
0x18000be42  cmp     eax, 0FFFFFFFFh
0x18000be45  jz      short loc_18000BE9B
0x18000be47  and     eax, 0FFFFFFFEh
0x18000be4a  mov     edx, eax; dwFileAttributes
0x18000be4c  mov     rcx, rbx; lpFileName
0x18000be4f  call    cs:__imp_SetFileAttributesW
0x18000be55  mov     rcx, rbx; lpFileName
0x18000be58  call    cs:__imp_DeleteFileW
0x18000be5e  test    eax, eax
0x18000be60  jz      short loc_18000BE9B
0x18000be62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be69  lea     r15, WPP_GLOBAL_Control
0x18000be70  cmp     rcx, r15
0x18000be73  jz      short loc_18000BEEC
0x18000be75  test    byte ptr [rcx+1Ch], 1
0x18000be79  jz      short loc_18000BEA9
0x18000be7b  cmp     byte ptr [rcx+19h], 5
0x18000be7f  jb      short loc_18000BEA9
0x18000be81  mov     edx, 11h
0x18000be86  mov     r9, rbx
0x18000be89  lea     r8, WPP_1ead9032b647397af64ee4622953436c_Traceguids
0x18000be90  mov     rcx, [rcx+10h]
0x18000be94  call    WPP_SF_S
0x18000be99  jmp     short loc_18000BEA2
0x18000be9b  lea     r15, WPP_GLOBAL_Control
0x18000bea2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bea9  cmp     rcx, r15
0x18000beac  jz      short loc_18000BEEC
0x18000beae  test    byte ptr [rcx+1Ch], 1
0x18000beb2  jz      short loc_18000BEEC
0x18000beb4  mov     r15d, [rsp+360h+var_310]
  ... truncated ...
```
