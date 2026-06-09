# CPITRSnapshotEnumerator::CPITRSnapshotEnumerator(CPITRBase *)

- ea: `0x180005614`
- end: `0x1800059e7`
- name: `??0CPITRSnapshotEnumerator@@QEAA@PEAVCPITRBase@@@Z`
- size: `979`
- prototype: `CPITRSnapshotEnumerator *__fastcall(CPITRSnapshotEnumerator *this, struct CPITRBase *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d760`
- `0x1800170f0`

## callees

- `0x18000434c`
- `0x180005614`
- `0x180009e04`
- `0x18000b070`
- `0x18001178c`
- `0x1800131c4`
- `0x18001cd2c`
- `0x180020a10`
- `0x18002125c`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000580c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000580c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058b9`
- `WDSCORE!CurrentIP` at `0x180005781`
- `WDSCORE!CurrentIP` at `0x180005814`
- `WDSCORE!CurrentIP` at `0x1800058c1`
- `WDSCORE!CurrentIP` at `0x180005781`
- `WDSCORE!CurrentIP` at `0x180005814`
- `WDSCORE!CurrentIP` at `0x1800058c1`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800057e3`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005921`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800057e3`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005921`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x180005650`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x180005650`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000569a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000569a`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1800056d5`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1800056fc`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1800056d5`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1800056fc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180005731`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180005731`

## string_xrefs

- `0x1800057c0`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180005866`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800058fe`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180005745`: `SeBackupPrivilege`
- `0x180005999`: `SeBackupPrivilege`
- `0x18000575a`: `SeRestorePrivilege`
- `0x1800059b0`: `SeRestorePrivilege`
- `0x180005838`: `Failed to open PITR snapshots key %s. Error: 0x%08X`
- `0x1800058d0`: `Failed to read snapshot for key index %d. Error: 0x%08X`

## pseudocode

```c
CPITRSnapshotEnumerator *__fastcall CPITRSnapshotEnumerator::CPITRSnapshotEnumerator(
        CPITRSnapshotEnumerator *this,
        struct CPITRBase *a2)
{
  CPITRBase *v2; // r14
  HKEY v4; // r12
  void **v5; // rax
  __int64 v6; // rbx
  int v7; // r15d
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  CPITRSnapshotEnumerator *v11; // rcx
  unsigned int v12; // r15d
  DWORD v13; // edi
  __int64 v14; // rbx
  unsigned int v15; // ecx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD i; // r15d
  int NextSnapshot; // eax
  int v19; // r12d
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  __int64 v23; // rcx
  int v25; // [rsp+60h] [rbp-19h] BYREF
  int v26; // [rsp+64h] [rbp-15h] BYREF
  HKEY v27; // [rsp+68h] [rbp-11h] BYREF
  void **v28; // [rsp+70h] [rbp-9h] BYREF
  __int64 v29; // [rsp+78h] [rbp-1h]
  struct CPITRBase *v30; // [rsp+80h] [rbp+7h]
  CPITRSnapshotEnumerator *v31; // [rsp+88h] [rbp+Fh]
  HKEY hKey; // [rsp+90h] [rbp+17h] BYREF

  v2 = a2;
  v30 = a2;
  v31 = this;
  UnBCL::Object::Object((CPITRSnapshotEnumerator *)((char *)this + 8));
  *(_QWORD *)this = &CPITRSnapshotEnumerator::`vftable'{for `PITR::IPITRSnapshotEnumerator'};
  *((_QWORD *)this + 1) = &CPITRSnapshotEnumerator::`vftable'{for `UnBCL::Object'};
  *((_QWORD *)this + 3) = &UnBCL::SmartPtr<UnBCL::ArrayList<CPITRSnapshot *>>::`vftable';
  *((_QWORD *)this + 4) = 0;
  v25 = 0;
  v26 = 0;
  v4 = 0;
  v27 = 0;
  hKey = 0;
  *((_DWORD *)this + 10) = 0;
  v5 = (void **)UnBCL::Object::operator new(0x80u);
  v28 = v5;
  if ( v5 )
    v6 = UnBCL::ArrayList<CPITRSnapshot *>::ArrayList<CPITRSnapshot *>(v5);
  else
    v6 = 0;
  v28 = &UnBCL::SmartPtr<UnBCL::ArrayList<CPITRSnapshot *>>::`vftable';
  v29 = 0;
  if ( v6 )
    UnBCL::Object::AddRef((UnBCL::Object *)(v6 + *(int *)(*(_QWORD *)(v6 + 8) + 4LL) + 8LL));
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign(&v28);
  v29 = v6;
  if ( v6 )
    UnBCL::Object::AddRef((UnBCL::Object *)(v6 + *(int *)(*(_QWORD *)(v6 + 8) + 4LL) + 8LL));
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((char *)this + 24);
  *((_QWORD *)this + 4) = v6;
  v28 = &UnBCL::SmartPtr<UnBCL::ArrayList<CPITRSnapshot *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign(&v28);
  if ( v2 )
  {
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v2 + 24) )
    {
      pEnablePrivilege(L"SeBackupPrivilege", 1, &v25);
      pEnablePrivilege(L"SeRestorePrivilege", 1, &v26);
    }
    v7 = CPITRBase::LockSoftwareKey(v2, &v27);
    if ( v7 < 0 )
    {
      LastError = GetLastError();
      v9 = CurrentIP();
      v10 = ConstructPartialMsgW(0x2000000u, "Failed to lock SOFTWARE key. Error: 0x%08X", v7);
      WdsSetupLogMessageW(
        v10,
        0,
        L"D",
        0,
        1851,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRSnapshotEnumerator::CPITRSnapshotEnumerator",
        v9,
        LastError,
        0,
        0);
      goto LABEL_27;
    }
    v4 = v27;
  }
  v12 = pOpenRegKeyMaxAccess(v4, L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Snapshots", &hKey);
  if ( !v12 )
  {
    for ( i = 0; ; ++i )
    {
      v27 = 0;
      NextSnapshot = CPITRSnapshotEnumerator::ReadNextSnapshot(v11, hKey, i, (struct CPITRSnapshot **)&v27);
      v19 = NextSnapshot;
      if ( NextSnapshot < 0 )
      {
        if ( NextSnapshot == -2147024637 )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 88LL))(*((_QWORD *)this + 4));
          v2 = v30;
          goto LABEL_27;
        }
        v20 = GetLastError();
        v21 = CurrentIP();
        v22 = ConstructPartialMsgW(0x2000000u, "Failed to read snapshot for key index %d. Error: 0x%08X", i, v19);
        WdsSetupLogMessageW(
          v22,
          0,
          L"D",
          0,
          1884,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRSnapshotEnumerator::CPITRSnapshotEnumerator",
          v21,
          v20,
          0,
          0);
      }
      if ( v27 )
      {
        v23 = *((_QWORD *)this + 4) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8LL) + 16LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 40LL))(v23);
      }
    }
  }
  v13 = GetLastError();
  v14 = CurrentIP();
  v15 = 0x2000000;
  if ( v12 == 2 )
    v15 = 50331648;
  v16 = ConstructPartialMsgW(
          v15,
          "Failed to open PITR snapshots key %s. Error: 0x%08X",
          (const char *)L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Snapshots",
          v12);
  WdsSetupLogMessageW(
    v16,
    0,
    L"D",
    0,
    1869,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
    L"CPITRSnapshotEnumerator::CPITRSnapshotEnumerator",
    v14,
    v13,
    0,
    0);
LABEL_27:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v2 )
    CPITRBase::UnlockSoftwareKey(v2);
  if ( v25 )
    pEnablePrivilege(L"SeBackupPrivilege", 0, 0);
  if ( v26 )
    pEnablePrivilege(L"SeRestorePrivilege", 0, 0);
  return this;
}

```

## disassembly

```asm
0x180005614  mov     [rsp-8+arg_10], rbx
0x180005619  push    rbp
0x18000561a  push    rsi
0x18000561b  push    rdi
0x18000561c  push    r12
0x18000561e  push    r13
0x180005620  push    r14
0x180005622  push    r15
0x180005624  lea     rbp, [rsp-27h]
0x180005629  sub     rsp, 0A0h
0x180005630  mov     rax, cs:__security_cookie
0x180005637  xor     rax, rsp
0x18000563a  mov     [rbp+57h+var_38], rax
0x18000563e  mov     r14, rdx
0x180005641  mov     [rbp+57h+var_50], rdx
0x180005645  mov     rsi, rcx
0x180005648  mov     [rbp+57h+var_48], rcx
0x18000564c  add     rcx, 8
0x180005650  call    cs:__imp_??0Object@UnBCL@@QEAA@XZ; UnBCL::Object::Object(void)
0x180005656  nop
0x180005657  lea     rax, ??_7CPITRSnapshotEnumerator@@6BIPITRSnapshotEnumerator@PITR@@@; const CPITRSnapshotEnumerator::`vftable'{for `PITR::IPITRSnapshotEnumerator'}
0x18000565e  mov     [rsi], rax
0x180005661  lea     rax, ??_7CPITRSnapshotEnumerator@@6BObject@UnBCL@@@; const CPITRSnapshotEnumerator::`vftable'{for `UnBCL::Object'}
0x180005668  mov     [rsi+8], rax
0x18000566c  lea     rdi, ??_7?$SmartPtr@V?$ArrayList@PEAVCPITRSnapshot@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CPITRSnapshot *>>::`vftable'
0x180005673  mov     [rsi+18h], rdi
0x180005677  xor     r13d, r13d
0x18000567a  mov     [rsi+20h], r13
0x18000567e  mov     [rbp+57h+var_70], r13d
0x180005682  mov     [rbp+57h+var_6C], r13d
0x180005686  mov     r12d, r13d
0x180005689  mov     [rbp+57h+var_68], r13
0x18000568d  mov     [rbp+57h+hKey], r13
0x180005691  mov     [rsi+28h], r13d
0x180005695  mov     ecx, 80h
0x18000569a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800056a0  mov     [rbp+57h+var_60], rax
0x1800056a4  test    rax, rax
0x1800056a7  jz      short loc_1800056B6
0x1800056a9  mov     rcx, rax
0x1800056ac  call    ??0?$ArrayList@PEAVCPITRSnapshot@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<CPITRSnapshot *>::ArrayList<CPITRSnapshot *>(void)
0x1800056b1  mov     rbx, rax
0x1800056b4  jmp     short loc_1800056B9
0x1800056b6  mov     rbx, r13
0x1800056b9  mov     [rbp+57h+var_60], rdi
0x1800056bd  mov     [rbp+57h+var_58], r13
0x1800056c1  test    rbx, rbx
0x1800056c4  jz      short loc_1800056DB
0x1800056c6  mov     rax, [rbx+8]
0x1800056ca  movsxd  rcx, dword ptr [rax+4]
0x1800056ce  add     rcx, 8
0x1800056d2  add     rcx, rbx
0x1800056d5  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x1800056db  lea     rcx, [rbp+57h+var_60]
0x1800056df  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x1800056e4  mov     [rbp+57h+var_58], rbx
0x1800056e8  test    rbx, rbx
0x1800056eb  jz      short loc_180005702
0x1800056ed  mov     rax, [rbx+8]
0x1800056f1  movsxd  rcx, dword ptr [rax+4]
0x1800056f5  add     rcx, 8
0x1800056f9  add     rcx, rbx
0x1800056fc  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x180005702  lea     rcx, [rsi+18h]
0x180005706  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x18000570b  mov     [rsi+20h], rbx
0x18000570f  lea     rax, ??_7?$SmartPtr@V?$ArrayList@PEAVCPITRSnapshot@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CPITRSnapshot *>>::`vftable'
0x180005716  mov     [rbp+57h+var_60], rax
0x18000571a  lea     rcx, [rbp+57h+var_60]
0x18000571e  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180005723  nop
0x180005724  test    r14, r14
0x180005727  jz      loc_1800057F2
0x18000572d  lea     rcx, [r14+18h]
0x180005731  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180005737  test    rax, rax
0x18000573a  jz      short loc_180005766
0x18000573c  lea     r8, [rbp+57h+var_70]; int *
0x180005740  mov     edx, 1; int
0x180005745  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18000574c  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x180005751  lea     r8, [rbp+57h+var_6C]; int *
0x180005755  mov     edx, 1; int
0x18000575a  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180005761  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x180005766  lea     rdx, [rbp+57h+var_68]; HKEY *
0x18000576a  mov     rcx, r14; this
0x18000576d  call    ?LockSoftwareKey@CPITRBase@@QEAAJPEAPEAUHKEY__@@@Z; CPITRBase::LockSoftwareKey(HKEY__ * *)
0x180005772  mov     r15d, eax
0x180005775  test    eax, eax
0x180005777  jns     short loc_1800057EE
0x180005779  call    cs:__imp_GetLastError
0x18000577f  mov     edi, eax
0x180005781  call    cs:__imp_CurrentIP
0x180005787  mov     rbx, rax
0x18000578a  mov     r8d, r15d
0x18000578d  lea     rdx, aFailedToLockSo; "Failed to lock SOFTWARE key. Error: 0x%"...
0x180005794  mov     ecx, 2000000h; unsigned int
0x180005799  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000579e  xor     r15d, r15d
0x1800057a1  mov     [rsp+0D0h+var_80], r15d
0x1800057a6  mov     [rsp+0D0h+var_88], r15
0x1800057ab  mov     [rsp+0D0h+var_90], edi
0x1800057af  mov     [rsp+0D0h+var_98], rbx
0x1800057b4  lea     rcx, aCpitrsnapshote_1; "CPITRSnapshotEnumerator::CPITRSnapshotE"...
0x1800057bb  mov     [rsp+0D0h+var_A0], rcx
0x1800057c0  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800057c7  mov     [rsp+0D0h+var_A8], rcx
0x1800057cc  mov     [rsp+0D0h+var_B0], 73Bh
0x1800057d4  xor     r9d, r9d
0x1800057d7  lea     r8, aD; "D"
0x1800057de  xor     edx, edx
0x1800057e0  mov     rcx, rax
0x1800057e3  call    cs:__imp_WdsSetupLogMessageW
0x1800057e9  jmp     loc_18000596E
0x1800057ee  mov     r12, [rbp+57h+var_68]
0x1800057f2  lea     r8, [rbp+57h+hKey]; phkResult
0x1800057f6  lea     rdx, aMicrosoftWindo_5; "Microsoft\\Windows\\CurrentVersion\\Set"...
0x1800057fd  mov     rcx, r12; hKey
0x180005800  call    ?pOpenRegKeyMaxAccess@@YAKPEAUHKEY__@@PEBGPEAPEAU1@@Z; pOpenRegKeyMaxAccess(HKEY__ *,ushort const *,HKEY__ * *)
0x180005805  mov     r15d, eax
0x180005808  test    eax, eax
0x18000580a  jz      short loc_18000587F
0x18000580c  call    cs:__imp_GetLastError
0x180005812  mov     edi, eax
0x180005814  call    cs:__imp_CurrentIP
0x18000581a  mov     rbx, rax
0x18000581d  mov     ecx, 2000000h
0x180005822  mov     eax, 3000000h
0x180005827  cmp     r15d, 2
0x18000582b  cmovz   ecx, eax; unsigned int
0x18000582e  mov     r9d, r15d
0x180005831  lea     r8, aMicrosoftWindo_5; "Microsoft\\Windows\\CurrentVersion\\Set"...
0x180005838  lea     rdx, aFailedToOpenPi_0; "Failed to open PITR snapshots key %s. E"...
0x18000583f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005844  xor     r15d, r15d
0x180005847  mov     [rsp+0D0h+var_80], r15d
0x18000584c  mov     [rsp+0D0h+var_88], r15
0x180005851  mov     [rsp+0D0h+var_90], edi
0x180005855  mov     [rsp+0D0h+var_98], rbx
0x18000585a  lea     rcx, aCpitrsnapshote_1; "CPITRSnapshotEnumerator::CPITRSnapshotE"...
0x180005861  mov     [rsp+0D0h+var_A0], rcx
0x180005866  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000586d  mov     [rsp+0D0h+var_A8], rcx
0x180005872  mov     [rsp+0D0h+var_B0], 74Dh
0x18000587a  jmp     loc_1800057D4
0x18000587f  mov     r15d, r13d
0x180005882  mov     r13d, 2000000h
0x180005888  lea     r14, aCpitrsnapshote_1; "CPITRSnapshotEnumerator::CPITRSnapshotE"...
0x18000588f  mov     [rbp+57h+var_68], 0
0x180005897  lea     r9, [rbp+57h+var_68]; struct CPITRSnapshot **
0x18000589b  mov     r8d, r15d; unsigned int
0x18000589e  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800058a2  call    ?ReadNextSnapshot@CPITRSnapshotEnumerator@@IEAAJPEAUHKEY__@@KPEAPEAVCPITRSnapshot@@@Z; CPITRSnapshotEnumerator::ReadNextSnapshot(HKEY__ *,ulong,CPITRSnapshot * *)
0x1800058a7  mov     r12d, eax
0x1800058aa  test    eax, eax
0x1800058ac  jns     short loc_180005927
0x1800058ae  cmp     eax, 80070103h
0x1800058b3  jz      loc_180005957
0x1800058b9  call    cs:__imp_GetLastError
0x1800058bf  mov     edi, eax
0x1800058c1  call    cs:__imp_CurrentIP
0x1800058c7  mov     rbx, rax
0x1800058ca  mov     r9d, r12d
0x1800058cd  mov     r8d, r15d
0x1800058d0  lea     rdx, aFailedToReadSn; "Failed to read snapshot for key index %"...
0x1800058d7  mov     ecx, r13d; unsigned int
0x1800058da  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800058df  mov     [rsp+0D0h+var_80], 0
0x1800058e7  mov     [rsp+0D0h+var_88], 0
0x1800058f0  mov     [rsp+0D0h+var_90], edi
0x1800058f4  mov     [rsp+0D0h+var_98], rbx
0x1800058f9  mov     [rsp+0D0h+var_A0], r14
0x1800058fe  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180005905  mov     [rsp+0D0h+var_A8], rcx
0x18000590a  mov     [rsp+0D0h+var_B0], 75Ch
0x180005912  xor     r9d, r9d
0x180005915  lea     r8, aD; "D"
0x18000591c  xor     edx, edx
0x18000591e  mov     rcx, rax
0x180005921  call    cs:__imp_WdsSetupLogMessageW
0x180005927  mov     rdx, [rbp+57h+var_68]
0x18000592b  test    rdx, rdx
0x18000592e  jz      short loc_18000594F
0x180005930  mov     r8, [rsi+20h]
0x180005934  mov     rax, [r8+8]
0x180005938  movsxd  rcx, dword ptr [rax+10h]
0x18000593c  add     r8, 8
0x180005940  add     rcx, r8
0x180005943  mov     rax, [rcx]
0x180005946  mov     rax, [rax+28h]
0x18000594a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594f  inc     r15d
0x180005952  jmp     loc_18000588F
0x180005957  mov     rcx, [rsi+20h]
0x18000595b  mov     rax, [rcx]
0x18000595e  mov     rax, [rax+58h]
0x180005962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005967  mov     r14, [rbp+57h+var_50]
0x18000596b  xor     r15d, r15d
0x18000596e  mov     rcx, [rbp+57h+hKey]; hKey
0x180005972  test    rcx, rcx
0x180005975  jz      short loc_180005981
0x180005977  call    cs:__imp_RegCloseKey
0x18000597d  mov     [rbp+57h+hKey], r15
0x180005981  test    r14, r14
0x180005984  jz      short loc_18000598E
0x180005986  mov     rcx, r14; this
0x180005989  call    ?UnlockSoftwareKey@CPITRBase@@QEAAJXZ; CPITRBase::UnlockSoftwareKey(void)
0x18000598e  cmp     [rbp+57h+var_70], r15d
0x180005992  jz      short loc_1800059A5
0x180005994  xor     r8d, r8d; int *
0x180005997  xor     edx, edx; int
0x180005999  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x1800059a0  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x1800059a5  cmp     [rbp+57h+var_6C], r15d
0x1800059a9  jz      short loc_1800059BD
0x1800059ab  xor     r8d, r8d; int *
0x1800059ae  xor     edx, edx; int
0x1800059b0  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1800059b7  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x1800059bc  nop
0x1800059bd  mov     rax, rsi
0x1800059c0  mov     rcx, [rbp+57h+var_38]
0x1800059c4  xor     rcx, rsp; StackCookie
0x1800059c7  call    __security_check_cookie
0x1800059cc  mov     rbx, [rsp+0D0h+arg_10]
0x1800059d4  add     rsp, 0A0h
0x1800059db  pop     r15
0x1800059dd  pop     r14
0x1800059df  pop     r13
0x1800059e1  pop     r12
0x1800059e3  pop     rdi
0x1800059e4  pop     rsi
0x1800059e5  pop     rbp
0x1800059e6  retn
```
