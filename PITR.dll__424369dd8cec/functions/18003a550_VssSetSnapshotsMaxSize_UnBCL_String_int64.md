# VssSetSnapshotsMaxSize(UnBCL::String *,__int64)

- ea: `0x18003a550`
- end: `0x18003a706`
- name: `?VssSetSnapshotsMaxSize@@YAJPEAVString@UnBCL@@_J@Z`
- size: `438`
- prototype: `int(struct UnBCL::String *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800170f0`
- `0x18001ce50`

## callees

- `0x180009e04`
- `0x180036624`
- `0x18003a550`
- `0x180048564`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a665`
- `WDSCORE!CurrentIP` at `0x18003a66d`
- `WDSCORE!CurrentIP` at `0x18003a66d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003a6d3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003a6d3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003a5ed`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003a637`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003a5ed`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003a637`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHG@Z` at `0x18003a5d6`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHG@Z` at `0x18003a5d6`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18003a5fd`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18003a5fd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003a590`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003a60a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003a590`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003a60a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003a624`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003a6df`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003a624`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003a6df`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18003a619`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18003a619`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18003a5c8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18003a5e4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18003a62e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18003a5c8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18003a5e4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18003a62e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003a59b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003a59b`

## string_xrefs

- `0x18003a6b0`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VssSetSnapshotsMaxSize(struct UnBCL::String *a1, struct UnBCL::String **a2, int *a3)
{
  struct UnBCL::String *VolumeNameFromPath; // rax
  signed int v6; // eax
  unsigned int v7; // ebx
  UnBCL::String *v8; // rax
  UnBCL::String *v9; // rax
  const unsigned __int16 *CString; // rax
  struct UnBCL::String *v11; // rax
  UnBCL::String *v12; // rax
  const unsigned __int16 *v13; // rax
  int v14; // esi
  DWORD LastError; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  int v18; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int64 v19[2]; // [rsp+68h] [rbp+1Fh] BYREF
  _BYTE v20[16]; // [rsp+78h] [rbp+2Fh] BYREF

  if ( !a1 )
    return 2147942487LL;
  VolumeNameFromPath = GetVolumeNameFromPath(a1, a2, a3);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v20, VolumeNameFromPath);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v20) )
  {
    v8 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v20);
    if ( !UnBCL::String::EndsWith(v8, 0x5Cu) )
    {
      v9 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v20);
      CString = UnBCL::String::get_CString(v9);
      v11 = UnBCL::String::Concat(CString, L"\\");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v19, v11);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v20, v19);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v19);
    }
    v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v20);
    v13 = UnBCL::String::get_CString(v12);
    v18 = 0;
    v19[0] = 0;
    v14 = ScopeSnapshotHelper::ChangeDiffAreaMaximumSize(&v18, v19, v13, (__int64)a2);
    if ( v14 < 0 )
    {
      LastError = GetLastError();
      v16 = CurrentIP();
      v17 = ConstructPartialMsgW(0x2000000, "VssSetSnapshotsMaxSize: Failed to query snapshot size. Error: 0x%08X", v14);
      WdsSetupLogMessageW(
        v17,
        0,
        L"D",
        0,
        724,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
        L"VssSetSnapshotsMaxSize",
        v16,
        LastError,
        0,
        0);
    }
    v7 = v14;
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v20);
  return v7;
}

```

## disassembly

```asm
0x18003a550  mov     [rsp-8+arg_10], rbx
0x18003a555  push    rbp
0x18003a556  push    rsi
0x18003a557  push    rdi
0x18003a558  lea     rbp, [rsp-47h]
0x18003a55d  sub     rsp, 90h
0x18003a564  mov     rax, cs:__security_cookie
0x18003a56b  xor     rax, rsp
0x18003a56e  mov     [rbp+57h+var_18], rax
0x18003a572  mov     rbx, rdx
0x18003a575  test    rcx, rcx
0x18003a578  jnz     short loc_18003A584
0x18003a57a  mov     eax, 80070057h
0x18003a57f  jmp     loc_18003A6E7
0x18003a584  call    ?GetVolumeNameFromPath@@YAPEAVString@UnBCL@@PEAV12@PEAPEAV12@PEAH@Z; GetVolumeNameFromPath(UnBCL::String *,UnBCL::String * *,int *)
0x18003a589  mov     rdx, rax
0x18003a58c  lea     rcx, [rbp+57h+var_28]
0x18003a590  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003a596  nop
0x18003a597  lea     rcx, [rbp+57h+var_28]
0x18003a59b  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18003a5a1  test    rax, rax
0x18003a5a4  jnz     short loc_18003A5C4
0x18003a5a6  call    cs:__imp_GetLastError
0x18003a5ac  mov     ebx, eax
0x18003a5ae  test    eax, eax
0x18003a5b0  jle     loc_18003A6DB
0x18003a5b6  movzx   ebx, ax
0x18003a5b9  or      ebx, 80070000h
0x18003a5bf  jmp     loc_18003A6DB
0x18003a5c4  lea     rcx, [rbp+57h+var_28]
0x18003a5c8  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18003a5ce  mov     edx, 5Ch ; '\'
0x18003a5d3  mov     rcx, rax
0x18003a5d6  call    cs:__imp_?EndsWith@String@UnBCL@@QEBAHG@Z; UnBCL::String::EndsWith(ushort)
0x18003a5dc  test    eax, eax
0x18003a5de  jnz     short loc_18003A62A
0x18003a5e0  lea     rcx, [rbp+57h+var_28]
0x18003a5e4  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18003a5ea  mov     rcx, rax
0x18003a5ed  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003a5f3  mov     rcx, rax
0x18003a5f6  lea     rdx, pszSrc; "\\"
0x18003a5fd  call    cs:__imp_?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18003a603  mov     rdx, rax
0x18003a606  lea     rcx, [rbp+57h+var_38]
0x18003a60a  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003a610  nop
0x18003a611  lea     rdx, [rbp+57h+var_38]
0x18003a615  lea     rcx, [rbp+57h+var_28]
0x18003a619  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18003a61f  nop
0x18003a620  lea     rcx, [rbp+57h+var_38]
0x18003a624  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18003a62a  lea     rcx, [rbp+57h+var_28]
0x18003a62e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18003a634  mov     rcx, rax
0x18003a637  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003a63d  mov     [rbp+57h+var_40], 0
0x18003a644  mov     [rbp+57h+var_38], 0
0x18003a64c  mov     r9, rbx; __int64
0x18003a64f  mov     r8, rax; unsigned __int16 *
0x18003a652  lea     rdx, [rbp+57h+var_38]; unsigned __int64 *
0x18003a656  lea     rcx, [rbp+57h+var_40]; int *
0x18003a65a  call    ?ChangeDiffAreaMaximumSize@ScopeSnapshotHelper@@SAJPEAJPEA_KPEBG_JE@Z; ScopeSnapshotHelper::ChangeDiffAreaMaximumSize(long *,unsigned __int64 *,ushort const *,__int64,uchar)
0x18003a65f  mov     esi, eax
0x18003a661  test    eax, eax
0x18003a663  jns     short loc_18003A6D9
0x18003a665  call    cs:__imp_GetLastError
0x18003a66b  mov     edi, eax
0x18003a66d  call    cs:__imp_CurrentIP
0x18003a673  mov     rbx, rax
0x18003a676  mov     r8d, esi
0x18003a679  lea     rdx, aVsssetsnapshot_0; "VssSetSnapshotsMaxSize: Failed to query"...
0x18003a680  mov     ecx, 2000000h; unsigned int
0x18003a685  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003a68a  mov     [rsp+0A0h+var_50], 0
0x18003a692  mov     [rsp+0A0h+var_58], 0
0x18003a69b  mov     [rsp+0A0h+var_60], edi
0x18003a69f  mov     [rsp+0A0h+var_68], rbx
0x18003a6a4  lea     rcx, aVsssetsnapshot; "VssSetSnapshotsMaxSize"
0x18003a6ab  mov     [rsp+0A0h+var_70], rcx
0x18003a6b0  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x18003a6b7  mov     [rsp+0A0h+var_78], rcx
0x18003a6bc  mov     [rsp+0A0h+var_80], 2D4h
0x18003a6c4  xor     r9d, r9d
0x18003a6c7  lea     r8, aD; "D"
0x18003a6ce  xor     edx, edx
0x18003a6d0  mov     rcx, rax
0x18003a6d3  call    cs:__imp_WdsSetupLogMessageW
0x18003a6d9  mov     ebx, esi
0x18003a6db  lea     rcx, [rbp+57h+var_28]
0x18003a6df  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18003a6e5  mov     eax, ebx
0x18003a6e7  mov     rcx, [rbp+57h+var_18]
0x18003a6eb  xor     rcx, rsp; StackCookie
0x18003a6ee  call    __security_check_cookie
0x18003a6f3  mov     rbx, [rsp+0A0h+arg_10]
0x18003a6fb  add     rsp, 90h
0x18003a702  pop     rdi
0x18003a703  pop     rsi
0x18003a704  pop     rbp
0x18003a705  retn
```
