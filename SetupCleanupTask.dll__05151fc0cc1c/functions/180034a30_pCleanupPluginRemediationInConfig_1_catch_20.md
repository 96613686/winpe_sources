# _pCleanupPluginRemediationInConfig_::_1_::catch$20

- ea: `0x180034a30`
- end: `0x180034b7b`
- name: `_pCleanupPluginRemediationInConfig_::_1_::catch$20`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x18000638c`
- `0x18001719c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a42`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180034a7d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180034a7d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034a96`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034b31`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034a96`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180034b31`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034a86`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034a9f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034b3a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034a86`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034a9f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034b3a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180034b13`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180034b13`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180034a73`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180034a73`
- `WDSCORE!CurrentIP` at `0x180034a4a`
- `WDSCORE!CurrentIP` at `0x180034a4a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180034b05`
- `WDSCORE!WdsSetupLogMessageW` at `0x180034b05`

## string_xrefs

- `0x180034ae2`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskcleanupremediation.cpp`
- `0x180034ad6`: `pCleanupPluginRemediationInConfig`

## pseudocode

```c
__int64 __fastcall pCleanupPluginRemediationInConfig_::_1_::catch_20(__int64 a1, __int64 a2)
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
  v5 = *(_QWORD *)(a2 + 288);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  v7 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(a2 + 128, v6);
  P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v7);
  CString = (const char *)UnBCL::String::get_CString(P);
  v10 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 248);
  v11 = (const char *)UnBCL::String::get_CString(v10);
  v12 = ConstructPartialMsgW(0x2000000, "Error deleting [%s]. Exception: %s", v11, CString);
  WdsSetupLogMessageW(
    v12,
    0,
    L"D",
    0,
    318,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
    L"pCleanupPluginRemediationInConfig",
    v4,
    LastError,
    0,
    0);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 128);
  LODWORD(CString) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 104LL))(v5);
  v13 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 248);
  v14 = UnBCL::String::get_CString(v13);
  pLogFileDeletionFailure(v14, (int)CString, *(struct TraceLoggingCorrelationVector **)(a2 + 376));
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  return 0;
}

```

## disassembly

```asm
0x180034a30  mov     [rsp+arg_8], rdx
0x180034a35  push    rbx
0x180034a36  push    rbp
0x180034a37  push    rsi
0x180034a38  push    rdi
0x180034a39  push    r14
0x180034a3b  sub     rsp, 60h
0x180034a3f  mov     rbp, rdx
0x180034a42  call    cs:__imp_GetLastError
0x180034a48  mov     esi, eax
0x180034a4a  call    cs:__imp_CurrentIP
0x180034a50  mov     rdi, rax
0x180034a53  mov     r14, [rbp+120h]
0x180034a5a  mov     rax, [r14]
0x180034a5d  mov     rcx, r14
0x180034a60  mov     rax, [rax+20h]
0x180034a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a69  mov     rdx, rax
0x180034a6c  lea     rcx, [rbp+80h]
0x180034a73  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180034a79  nop
0x180034a7a  mov     rcx, rax
0x180034a7d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180034a83  mov     rcx, rax
0x180034a86  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034a8c  mov     rbx, rax
0x180034a8f  lea     rcx, [rbp+0F8h]
0x180034a96  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180034a9c  mov     rcx, rax
0x180034a9f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034aa5  mov     r9, rbx
0x180034aa8  mov     r8, rax
0x180034aab  lea     rdx, aErrorDeletingS; "Error deleting [%s]. Exception: %s"
0x180034ab2  mov     ecx, 2000000h; unsigned int
0x180034ab7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180034abc  mov     [rsp+88h+var_38], 0
0x180034ac4  mov     [rsp+88h+var_40], 0
0x180034acd  mov     [rsp+88h+var_48], esi
0x180034ad1  mov     [rsp+88h+var_50], rdi
0x180034ad6  lea     rcx, aPcleanupplugin; "pCleanupPluginRemediationInConfig"
0x180034add  mov     [rsp+88h+var_58], rcx
0x180034ae2  lea     rcx, aBaseNtsetupSet_2; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180034ae9  mov     [rsp+88h+var_60], rcx
0x180034aee  mov     [rsp+88h+var_68], 13Eh
0x180034af6  xor     r9d, r9d
0x180034af9  lea     r8, aD_0; "D"
0x180034b00  xor     edx, edx
0x180034b02  mov     rcx, rax
0x180034b05  call    cs:__imp_WdsSetupLogMessageW
0x180034b0b  nop
0x180034b0c  lea     rcx, [rbp+80h]
0x180034b13  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180034b19  mov     rax, [r14]
0x180034b1c  mov     rcx, r14
0x180034b1f  mov     rax, [rax+68h]
0x180034b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b28  mov     ebx, eax
0x180034b2a  lea     rcx, [rbp+0F8h]
0x180034b31  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180034b37  mov     rcx, rax
0x180034b3a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034b40  mov     r8, [rbp+178h]; struct TraceLoggingCorrelationVector *
0x180034b47  mov     edx, ebx; int
0x180034b49  mov     rcx, rax; unsigned __int16 *
0x180034b4c  call    ?pLogFileDeletionFailure@@YAXPEBGJPEAVTraceLoggingCorrelationVector@@@Z; pLogFileDeletionFailure(ushort const *,long,TraceLoggingCorrelationVector *)
0x180034b51  mov     rax, [r14]
0x180034b54  mov     edx, 1
0x180034b59  mov     rcx, r14
0x180034b5c  mov     rax, [rax]
0x180034b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b64  nop
0x180034b65  mov     rax, 0
0x180034b6f  add     rsp, 60h
0x180034b73  pop     r14
0x180034b75  pop     rdi
0x180034b76  pop     rsi
0x180034b77  pop     rbp
0x180034b78  pop     rbx
0x180034b79  retn
```
