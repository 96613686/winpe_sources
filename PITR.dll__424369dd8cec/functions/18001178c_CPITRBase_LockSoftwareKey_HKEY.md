# CPITRBase::LockSoftwareKey(HKEY__ * *)

- ea: `0x18001178c`
- end: `0x18001196f`
- name: `?LockSoftwareKey@CPITRBase@@QEAAJPEAPEAUHKEY__@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(CPITRBase *__hidden this, HKEY *)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800044f4`
- `0x180004dc8`
- `0x180005614`
- `0x18000a5f0`
- `0x18000b280`
- `0x18000fab0`

## callees

- `0x180009e04`
- `0x18001178c`
- `0x18002125c`
- `0x18003fec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800117b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800117b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011887`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118e1`
- `WDSCORE!CurrentIP` at `0x18001181b`
- `WDSCORE!CurrentIP` at `0x1800118e9`
- `WDSCORE!CurrentIP` at `0x18001181b`
- `WDSCORE!CurrentIP` at `0x1800118e9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180011964`
- `WDSCORE!WdsSetupLogMessageW` at `0x180011964`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800118a8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800118fe`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800118a8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800118fe`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18001189f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800118f5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18001189f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800118f5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800117db`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800117db`

## string_xrefs

- `0x18001185e`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180011941`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180011824`: `GetSoftwareHive: Failed to open SOFTWARE key. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall CPITRBase::LockSoftwareKey(CPITRBase *this, HKEY *a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // r15
  unsigned int v6; // esi
  HKEY *v7; // r14
  HKEY v8; // rax
  int v9; // eax
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  HKEY v13; // rax
  UnBCL::String *v14; // rax
  const unsigned __int16 *CString; // rax
  signed int LastError; // eax
  DWORD v17; // edi
  __int64 v18; // rax
  char *v19; // rcx
  __int64 v20; // rbx
  UnBCL::String *v21; // rax
  const char *v22; // rax
  struct tagLOG_PARTIAL_MSG *v23; // rax

  if ( !a2 )
    return 2147942487LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v7 = (HKEY *)((char *)this + 88);
  v8 = (HKEY)*((_QWORD *)this + 11);
  if ( v8 )
  {
    ++*((_DWORD *)this + 24);
    *a2 = v8;
  }
  else
  {
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 24) )
    {
      v14 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
      CString = UnBCL::String::get_CString(v14);
      v13 = RecMountOfflineHive(CString, L"SOFTWARE", L"$OFFLINE_RW$SOFTWARE");
      *v7 = v13;
      if ( !v13 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v17 = GetLastError();
        v18 = CurrentIP();
        v19 = (char *)this + 24;
        v20 = v18;
        v21 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v19);
        v22 = (const char *)UnBCL::String::get_CString(v21);
        v23 = ConstructPartialMsgW(
                0x2000000,
                "GetSoftwareHive: Failed to load offline SOFTWARE hive from %s. Error: 0x%08X",
                v22,
                v6);
        WdsSetupLogMessageW(
          v23,
          0,
          L"D",
          0,
          3760,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::LockSoftwareKey",
          v20,
          v17,
          0,
          0);
        goto LABEL_13;
      }
    }
    else
    {
      v9 = pOpenRegKeyMaxAccess(HKEY_LOCAL_MACHINE, L"SOFTWARE", (PHKEY)this + 11);
      if ( v9 )
      {
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
        else
          v6 = v9;
        v10 = GetLastError();
        v11 = CurrentIP();
        v12 = ConstructPartialMsgW(0x2000000, "GetSoftwareHive: Failed to open SOFTWARE key. Error: 0x%08X", v6);
        WdsSetupLogMessageW(
          v12,
          0,
          L"D",
          0,
          3745,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::LockSoftwareKey",
          v11,
          v10,
          0,
          0);
        goto LABEL_13;
      }
      v13 = *v7;
    }
    *a2 = v13;
    *((_DWORD *)this + 24) = 1;
  }
LABEL_13:
  LeaveCriticalSection(v5);
  return v6;
}

```

## disassembly

```asm
0x18001178c  push    rbx
0x18001178e  push    rbp
0x18001178f  push    rsi
0x180011790  push    rdi
0x180011791  push    r14
0x180011793  push    r15
0x180011795  sub     rsp, 68h
0x180011799  mov     rdi, rdx
0x18001179c  mov     rbx, rcx
0x18001179f  test    rdx, rdx
0x1800117a2  jnz     short loc_1800117AE
0x1800117a4  mov     eax, 80070057h
0x1800117a9  jmp     loc_18001188F
0x1800117ae  lea     r15, [rcx+28h]
0x1800117b2  xor     esi, esi
0x1800117b4  mov     rcx, r15; lpCriticalSection
0x1800117b7  call    cs:__imp_EnterCriticalSection
0x1800117bd  lea     r14, [rbx+58h]
0x1800117c1  mov     rax, [r14]
0x1800117c4  test    rax, rax
0x1800117c7  jz      short loc_1800117D4
0x1800117c9  inc     dword ptr [rbx+60h]
0x1800117cc  mov     [rdi], rax
0x1800117cf  jmp     loc_180011884
0x1800117d4  lea     rbp, [rbx+18h]
0x1800117d8  mov     rcx, rbp
0x1800117db  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800117e1  test    rax, rax
0x1800117e4  jnz     loc_18001189C
0x1800117ea  mov     r8, r14; phkResult
0x1800117ed  lea     rdx, aSoftware; "SOFTWARE"
0x1800117f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800117fb  call    ?pOpenRegKeyMaxAccess@@YAKPEAUHKEY__@@PEBGPEAPEAU1@@Z; pOpenRegKeyMaxAccess(HKEY__ *,ushort const *,HKEY__ * *)
0x180011800  test    eax, eax
0x180011802  jz      short loc_180011877
0x180011804  jg      short loc_18001180A
0x180011806  mov     esi, eax
0x180011808  jmp     short loc_180011813
0x18001180a  movzx   esi, ax
0x18001180d  or      esi, 80070000h
0x180011813  call    cs:__imp_GetLastError
0x180011819  mov     edi, eax
0x18001181b  call    cs:__imp_CurrentIP
0x180011821  mov     r8d, esi
0x180011824  lea     rdx, aGetsoftwarehiv_0; "GetSoftwareHive: Failed to open SOFTWAR"...
0x18001182b  mov     ecx, 2000000h; unsigned int
0x180011830  mov     rbx, rax
0x180011833  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180011838  mov     [rsp+98h+var_48], 0
0x180011840  lea     rcx, aCpitrbaseLocks; "CPITRBase::LockSoftwareKey"
0x180011847  mov     [rsp+98h+var_50], 0
0x180011850  mov     [rsp+98h+var_58], edi
0x180011854  mov     [rsp+98h+var_60], rbx
0x180011859  mov     [rsp+98h+var_68], rcx
0x18001185e  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180011865  mov     [rsp+98h+var_70], rcx
0x18001186a  mov     [rsp+98h+var_78], 0EA1h
0x180011872  jmp     loc_180011955
0x180011877  mov     rax, [r14]
0x18001187a  mov     [rdi], rax
0x18001187d  mov     dword ptr [rbx+60h], 1
0x180011884  mov     rcx, r15; lpCriticalSection
0x180011887  call    cs:__imp_LeaveCriticalSection
0x18001188d  mov     eax, esi
0x18001188f  add     rsp, 68h
0x180011893  pop     r15
0x180011895  pop     r14
0x180011897  pop     rdi
0x180011898  pop     rsi
0x180011899  pop     rbp
0x18001189a  pop     rbx
0x18001189b  retn
0x18001189c  mov     rcx, rbp
0x18001189f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800118a5  mov     rcx, rax
0x1800118a8  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800118ae  mov     rcx, rax; unsigned __int16 *
0x1800118b1  lea     r8, aOfflineRwSoftw; "$OFFLINE_RW$SOFTWARE"
0x1800118b8  lea     rdx, aSoftware; "SOFTWARE"
0x1800118bf  call    ?RecMountOfflineHive@@YAPEAUHKEY__@@PEBG00@Z; RecMountOfflineHive(ushort const *,ushort const *,ushort const *)
0x1800118c4  mov     [r14], rax
0x1800118c7  test    rax, rax
0x1800118ca  jnz     short loc_18001187A
0x1800118cc  call    cs:__imp_GetLastError
0x1800118d2  mov     esi, eax
0x1800118d4  test    eax, eax
0x1800118d6  jle     short loc_1800118E1
0x1800118d8  movzx   esi, ax
0x1800118db  or      esi, 80070000h
0x1800118e1  call    cs:__imp_GetLastError
0x1800118e7  mov     edi, eax
0x1800118e9  call    cs:__imp_CurrentIP
0x1800118ef  mov     rcx, rbp
0x1800118f2  mov     rbx, rax
0x1800118f5  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800118fb  mov     rcx, rax
0x1800118fe  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180011904  mov     r9d, esi
0x180011907  lea     rdx, aGetsoftwarehiv; "GetSoftwareHive: Failed to load offline"...
0x18001190e  mov     r8, rax
0x180011911  mov     ecx, 2000000h; unsigned int
0x180011916  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001191b  mov     [rsp+98h+var_48], 0
0x180011923  lea     rcx, aCpitrbaseLocks; "CPITRBase::LockSoftwareKey"
0x18001192a  mov     [rsp+98h+var_50], 0
0x180011933  mov     [rsp+98h+var_58], edi
0x180011937  mov     [rsp+98h+var_60], rbx
0x18001193c  mov     [rsp+98h+var_68], rcx
0x180011941  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180011948  mov     [rsp+98h+var_70], rcx
0x18001194d  mov     [rsp+98h+var_78], 0EB0h
0x180011955  xor     r9d, r9d
0x180011958  lea     r8, aD; "D"
0x18001195f  xor     edx, edx
0x180011961  mov     rcx, rax
0x180011964  call    cs:__imp_WdsSetupLogMessageW
0x18001196a  jmp     loc_180011884
```
