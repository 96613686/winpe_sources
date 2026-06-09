# _pCleanupPluginRemediationInConfig_::_1_::catch$21

- ea: `0x180034b81`
- end: `0x180034c89`
- name: `_pCleanupPluginRemediationInConfig_::_1_::catch$21`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x18000638c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b91`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180034bcc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180034bcc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034bd5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034bd5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180034c46`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180034c46`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180034bc2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180034bc2`
- `WDSCORE!CurrentIP` at `0x180034b99`
- `WDSCORE!CurrentIP` at `0x180034b99`
- `WDSCORE!WdsSetupLogMessageW` at `0x180034c38`
- `WDSCORE!WdsSetupLogMessageW` at `0x180034c38`

## string_xrefs

- `0x180034c15`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskcleanupremediation.cpp`
- `0x180034c09`: `pCleanupPluginRemediationInConfig`

## pseudocode

```c
__int64 __fastcall pCleanupPluginRemediationInConfig_::_1_::catch_21(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rax
  UnBCL::String *P; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v10; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(_QWORD *)(a2 + 296);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  v7 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(a2 + 128, v6);
  P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v7);
  CString = (const char *)UnBCL::String::get_CString(P);
  v10 = ConstructPartialMsgW(0x2000000, "Error removing child node. Exception: %s", CString);
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    352,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
    L"pCleanupPluginRemediationInConfig",
    v4,
    LastError,
    0,
    0);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 128);
  *(_DWORD *)(a2 + 392) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 104LL))(v5);
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  return 0;
}

```

## disassembly

```asm
0x180034b81  mov     [rsp+arg_8], rdx
0x180034b86  push    rbx
0x180034b87  push    rbp
0x180034b88  push    rsi
0x180034b89  push    rdi
0x180034b8a  sub     rsp, 68h
0x180034b8e  mov     rbp, rdx
0x180034b91  call    cs:__imp_GetLastError
0x180034b97  mov     edi, eax
0x180034b99  call    cs:__imp_CurrentIP
0x180034b9f  mov     rbx, rax
0x180034ba2  mov     rsi, [rbp+128h]
0x180034ba9  mov     rax, [rsi]
0x180034bac  mov     rcx, rsi
0x180034baf  mov     rax, [rax+20h]
0x180034bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bb8  mov     rdx, rax
0x180034bbb  lea     rcx, [rbp+80h]
0x180034bc2  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180034bc8  nop
0x180034bc9  mov     rcx, rax
0x180034bcc  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180034bd2  mov     rcx, rax
0x180034bd5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180034bdb  mov     r8, rax
0x180034bde  lea     rdx, aErrorRemovingC; "Error removing child node. Exception: %"...
0x180034be5  mov     ecx, 2000000h; unsigned int
0x180034bea  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180034bef  mov     [rsp+88h+var_38], 0
0x180034bf7  mov     [rsp+88h+var_40], 0
0x180034c00  mov     [rsp+88h+var_48], edi
0x180034c04  mov     [rsp+88h+var_50], rbx
0x180034c09  lea     rcx, aPcleanupplugin; "pCleanupPluginRemediationInConfig"
0x180034c10  mov     [rsp+88h+var_58], rcx
0x180034c15  lea     rcx, aBaseNtsetupSet_2; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180034c1c  mov     [rsp+88h+var_60], rcx
0x180034c21  mov     [rsp+88h+var_68], 160h
0x180034c29  xor     r9d, r9d
0x180034c2c  lea     r8, aD_0; "D"
0x180034c33  xor     edx, edx
0x180034c35  mov     rcx, rax
0x180034c38  call    cs:__imp_WdsSetupLogMessageW
0x180034c3e  nop
0x180034c3f  lea     rcx, [rbp+80h]
0x180034c46  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180034c4c  mov     rax, [rsi]
0x180034c4f  mov     rcx, rsi
0x180034c52  mov     rax, [rax+68h]
0x180034c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c5b  mov     [rbp+188h], eax
0x180034c61  mov     rax, [rsi]
0x180034c64  mov     edx, 1
0x180034c69  mov     rcx, rsi
0x180034c6c  mov     rax, [rax]
0x180034c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c74  nop
0x180034c75  mov     rax, 0
0x180034c7f  add     rsp, 68h
0x180034c83  pop     rdi
0x180034c84  pop     rsi
0x180034c85  pop     rbp
0x180034c86  pop     rbx
0x180034c87  retn
```
