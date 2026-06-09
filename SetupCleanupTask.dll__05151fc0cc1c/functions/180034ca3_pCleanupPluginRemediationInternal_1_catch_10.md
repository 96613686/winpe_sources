# _pCleanupPluginRemediationInternal_::_1_::catch$10

- ea: `0x180034ca3`
- end: `0x180034de5`
- name: `_pCleanupPluginRemediationInternal_::_1_::catch$10`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000638c`
- `0x18001719c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cb5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180034ced`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180034ced`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034d06`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034d9e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034d06`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034d9e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034cf6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034d0f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034da7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034cf6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034d0f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034da7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180034d80`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180034d80`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180034ce3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180034ce3`
- `WDSCORE!CurrentIP` at `0x180034cbd`
- `WDSCORE!CurrentIP` at `0x180034cbd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180034d75`
- `WDSCORE!WdsSetupLogMessageW` at `0x180034d75`

## string_xrefs

- `0x180034d52`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskcleanupremediation.cpp`
- `0x180034d46`: `pCleanupPluginRemediationInternal`

## pseudocode

```c
__int64 __fastcall pCleanupPluginRemediationInternal_::_1_::catch_10(__int64 a1, __int64 a2)
{
  DWORD LastError; // esi
  __int64 v4; // rdi
  __int64 v5; // r14
  __int64 v6; // rax
  __int64 v7; // rax
  UnBCL::String *P; // rax
  const char *CString; // rbx
  UnBCL::String *v10; // rax
  const char *v11; // rax
  struct tagLOG_PARTIAL_MSG *v12; // rax
  UnBCL::String *v13; // rax
  const unsigned __int16 *v14; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(_QWORD *)(a2 + 216);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  v7 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(a2 + 104, v6);
  P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v7);
  CString = (const char *)UnBCL::String::get_CString(P);
  v10 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 136);
  v11 = (const char *)UnBCL::String::get_CString(v10);
  v12 = ConstructPartialMsgW(0x2000000, "Error deleting [%s]. Exception: %s", v11, CString);
  WdsSetupLogMessageW(
    v12,
    0,
    L"D",
    0,
    529,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
    L"pCleanupPluginRemediationInternal",
    v4,
    LastError,
    0,
    0);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 104);
  LODWORD(CString) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 104LL))(v5);
  v13 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 136);
  v14 = UnBCL::String::get_CString(v13);
  pLogFileDeletionFailure(v14, (int)CString, *(struct TraceLoggingCorrelationVector **)(a2 + 120));
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  return 0;
}

```

## disassembly

```asm
0x180034ca3  mov     [rsp+arg_8], rdx
0x180034ca8  push    rbx
0x180034ca9  push    rbp
0x180034caa  push    rsi
0x180034cab  push    rdi
0x180034cac  push    r14
0x180034cae  sub     rsp, 60h
0x180034cb2  mov     rbp, rdx
0x180034cb5  call    cs:__imp_GetLastError
0x180034cbb  mov     esi, eax
0x180034cbd  call    cs:__imp_CurrentIP
0x180034cc3  mov     rdi, rax
0x180034cc6  mov     r14, [rbp+0D8h]
0x180034ccd  mov     rcx, [r14]
0x180034cd0  mov     rax, [rcx+20h]
0x180034cd4  mov     rcx, r14
0x180034cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cdc  mov     rdx, rax
0x180034cdf  lea     rcx, [rbp+68h]
0x180034ce3  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180034ce9  nop
0x180034cea  mov     rcx, rax
0x180034ced  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180034cf3  mov     rcx, rax
0x180034cf6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034cfc  mov     rbx, rax
0x180034cff  lea     rcx, [rbp+88h]
0x180034d06  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180034d0c  mov     rcx, rax
0x180034d0f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034d15  mov     r9, rbx
0x180034d18  mov     r8, rax
0x180034d1b  lea     rdx, aErrorDeletingS; "Error deleting [%s]. Exception: %s"
0x180034d22  mov     ecx, 2000000h; unsigned int
0x180034d27  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180034d2c  mov     [rsp+88h+var_38], 0
0x180034d34  mov     [rsp+88h+var_40], 0
0x180034d3d  mov     [rsp+88h+var_48], esi
0x180034d41  mov     [rsp+88h+var_50], rdi
0x180034d46  lea     rcx, aPcleanupplugin_0; "pCleanupPluginRemediationInternal"
0x180034d4d  mov     [rsp+88h+var_58], rcx
0x180034d52  lea     rcx, aBaseNtsetupSet_2; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180034d59  mov     [rsp+88h+var_60], rcx
0x180034d5e  mov     [rsp+88h+var_68], 211h
0x180034d66  xor     r9d, r9d
0x180034d69  lea     r8, aD_0; "D"
0x180034d70  xor     edx, edx
0x180034d72  mov     rcx, rax
0x180034d75  call    cs:__imp_WdsSetupLogMessageW
0x180034d7b  nop
0x180034d7c  lea     rcx, [rbp+68h]
0x180034d80  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180034d86  mov     rax, [r14]
0x180034d89  mov     rcx, r14
0x180034d8c  mov     rax, [rax+68h]
0x180034d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d95  mov     ebx, eax
0x180034d97  lea     rcx, [rbp+88h]
0x180034d9e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180034da4  mov     rcx, rax
0x180034da7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034dad  mov     r8, [rbp+78h]; struct TraceLoggingCorrelationVector *
0x180034db1  mov     edx, ebx; int
0x180034db3  mov     rcx, rax; unsigned __int16 *
0x180034db6  call    ?pLogFileDeletionFailure@@YAXPEBGJPEAVTraceLoggingCorrelationVector@@@Z; pLogFileDeletionFailure(ushort const *,long,TraceLoggingCorrelationVector *)
0x180034dbb  mov     rax, [r14]
0x180034dbe  mov     edx, 1
0x180034dc3  mov     rcx, r14
0x180034dc6  mov     rax, [rax]
0x180034dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dce  nop
0x180034dcf  mov     rax, 0
0x180034dd9  add     rsp, 60h
0x180034ddd  pop     r14
0x180034ddf  pop     rdi
0x180034de0  pop     rsi
0x180034de1  pop     rbp
0x180034de2  pop     rbx
0x180034de3  retn
```
