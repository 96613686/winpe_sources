# _pCleanupPluginRemediationInternal_::_1_::catch$11

- ea: `0x180034deb`
- end: `0x180034f2d`
- name: `_pCleanupPluginRemediationInternal_::_1_::catch$11`
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

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034dfd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180034e35`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180034e35`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034e4e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034ee6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034e4e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034ee6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034e3e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034e57`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034eef`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034e3e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034e57`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034eef`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180034ec8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180034ec8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180034e2b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180034e2b`
- `WDSCORE!CurrentIP` at `0x180034e05`
- `WDSCORE!CurrentIP` at `0x180034e05`
- `WDSCORE!WdsSetupLogMessageW` at `0x180034ebd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180034ebd`

## string_xrefs

- `0x180034e9a`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskcleanupremediation.cpp`
- `0x180034e8e`: `pCleanupPluginRemediationInternal`

## pseudocode

```c
__int64 __fastcall pCleanupPluginRemediationInternal_::_1_::catch_11(__int64 a1, __int64 a2)
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
  v5 = *(_QWORD *)(a2 + 224);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  v7 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(a2 + 104, v6);
  P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v7);
  CString = (const char *)UnBCL::String::get_CString(P);
  v10 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 152);
  v11 = (const char *)UnBCL::String::get_CString(v10);
  v12 = ConstructPartialMsgW(0x2000000, "Error deleting [%s]. Exception: %s", v11, CString);
  WdsSetupLogMessageW(
    v12,
    0,
    L"D",
    0,
    551,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
    L"pCleanupPluginRemediationInternal",
    v4,
    LastError,
    0,
    0);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 104);
  LODWORD(CString) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 104LL))(v5);
  v13 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 152);
  v14 = UnBCL::String::get_CString(v13);
  pLogFileDeletionFailure(v14, (int)CString, *(struct TraceLoggingCorrelationVector **)(a2 + 120));
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  return 0;
}

```

## disassembly

```asm
0x180034deb  mov     [rsp+arg_8], rdx
0x180034df0  push    rbx
0x180034df1  push    rbp
0x180034df2  push    rsi
0x180034df3  push    rdi
0x180034df4  push    r14
0x180034df6  sub     rsp, 60h
0x180034dfa  mov     rbp, rdx
0x180034dfd  call    cs:__imp_GetLastError
0x180034e03  mov     esi, eax
0x180034e05  call    cs:__imp_CurrentIP
0x180034e0b  mov     rdi, rax
0x180034e0e  mov     r14, [rbp+0E0h]
0x180034e15  mov     rcx, [r14]
0x180034e18  mov     rax, [rcx+20h]
0x180034e1c  mov     rcx, r14
0x180034e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e24  mov     rdx, rax
0x180034e27  lea     rcx, [rbp+68h]
0x180034e2b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180034e31  nop
0x180034e32  mov     rcx, rax
0x180034e35  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180034e3b  mov     rcx, rax
0x180034e3e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034e44  mov     rbx, rax
0x180034e47  lea     rcx, [rbp+98h]
0x180034e4e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180034e54  mov     rcx, rax
0x180034e57  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034e5d  mov     r9, rbx
0x180034e60  mov     r8, rax
0x180034e63  lea     rdx, aErrorDeletingS; "Error deleting [%s]. Exception: %s"
0x180034e6a  mov     ecx, 2000000h; unsigned int
0x180034e6f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180034e74  mov     [rsp+88h+var_38], 0
0x180034e7c  mov     [rsp+88h+var_40], 0
0x180034e85  mov     [rsp+88h+var_48], esi
0x180034e89  mov     [rsp+88h+var_50], rdi
0x180034e8e  lea     rcx, aPcleanupplugin_0; "pCleanupPluginRemediationInternal"
0x180034e95  mov     [rsp+88h+var_58], rcx
0x180034e9a  lea     rcx, aBaseNtsetupSet_2; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180034ea1  mov     [rsp+88h+var_60], rcx
0x180034ea6  mov     [rsp+88h+var_68], 227h
0x180034eae  xor     r9d, r9d
0x180034eb1  lea     r8, aD_0; "D"
0x180034eb8  xor     edx, edx
0x180034eba  mov     rcx, rax
0x180034ebd  call    cs:__imp_WdsSetupLogMessageW
0x180034ec3  nop
0x180034ec4  lea     rcx, [rbp+68h]
0x180034ec8  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180034ece  mov     rax, [r14]
0x180034ed1  mov     rcx, r14
0x180034ed4  mov     rax, [rax+68h]
0x180034ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034edd  mov     ebx, eax
0x180034edf  lea     rcx, [rbp+98h]
0x180034ee6  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180034eec  mov     rcx, rax
0x180034eef  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034ef5  mov     r8, [rbp+78h]; struct TraceLoggingCorrelationVector *
0x180034ef9  mov     edx, ebx; int
0x180034efb  mov     rcx, rax; unsigned __int16 *
0x180034efe  call    ?pLogFileDeletionFailure@@YAXPEBGJPEAVTraceLoggingCorrelationVector@@@Z; pLogFileDeletionFailure(ushort const *,long,TraceLoggingCorrelationVector *)
0x180034f03  mov     rax, [r14]
0x180034f06  mov     edx, 1
0x180034f0b  mov     rcx, r14
0x180034f0e  mov     rax, [rax]
0x180034f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f16  nop
0x180034f17  mov     rax, 0
0x180034f21  add     rsp, 60h
0x180034f25  pop     r14
0x180034f27  pop     rdi
0x180034f28  pop     rsi
0x180034f29  pop     rbp
0x180034f2a  pop     rbx
0x180034f2b  retn
```
