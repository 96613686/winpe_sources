# _AreConditionsMet_::_1_::catch$17

- ea: `0x180032af3`
- end: `0x180032bf1`
- name: `_AreConditionsMet_::_1_::catch$17`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x18000638c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b2a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180032b42`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180032b42`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180032b4b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180032b4b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180032bd6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180032bd6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180032b23`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180032b23`
- `WDSCORE!CurrentIP` at `0x180032b32`
- `WDSCORE!CurrentIP` at `0x180032b32`
- `WDSCORE!WdsSetupLogMessageW` at `0x180032bae`
- `WDSCORE!WdsSetupLogMessageW` at `0x180032bae`

## string_xrefs

- `0x180032b8b`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x180032b54`: `Failed to read uninstall mark time. Will consider uninstall invalid. Exception: %s`

## pseudocode

```c
__int64 __fastcall AreConditionsMet_::_1_::catch_17(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  __int64 v4; // rax
  DWORD LastError; // edi
  __int64 v6; // rbx
  UnBCL::String *v7; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v9; // rax

  v3 = *(_QWORD *)(a2 + 304);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(a2 + 216, v4);
  LastError = GetLastError();
  v6 = CurrentIP();
  v7 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 216);
  CString = (const char *)UnBCL::String::get_CString(v7);
  v9 = ConstructPartialMsgW(
         0x2000000,
         "Failed to read uninstall mark time. Will consider uninstall invalid. Exception: %s",
         CString);
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    396,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"AreConditionsMet",
    v6,
    LastError,
    0,
    0);
  *(_DWORD *)(a2 + 112) = 0;
  (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 216);
  return 0;
}

```

## disassembly

```asm
0x180032af3  mov     [rsp+arg_8], rdx
0x180032af8  push    rbx
0x180032af9  push    rbp
0x180032afa  push    rsi
0x180032afb  push    rdi
0x180032afc  sub     rsp, 68h
0x180032b00  mov     rbp, rdx
0x180032b03  mov     rsi, [rbp+130h]
0x180032b0a  mov     rax, [rsi]
0x180032b0d  mov     rcx, rsi
0x180032b10  mov     rax, [rax+20h]
0x180032b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b19  mov     rdx, rax
0x180032b1c  lea     rcx, [rbp+0D8h]
0x180032b23  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180032b29  nop
0x180032b2a  call    cs:__imp_GetLastError
0x180032b30  mov     edi, eax
0x180032b32  call    cs:__imp_CurrentIP
0x180032b38  mov     rbx, rax
0x180032b3b  lea     rcx, [rbp+0D8h]
0x180032b42  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180032b48  mov     rcx, rax
0x180032b4b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180032b51  mov     r8, rax
0x180032b54  lea     rdx, aFailedToReadUn; "Failed to read uninstall mark time. Wil"...
0x180032b5b  mov     ecx, 2000000h; unsigned int
0x180032b60  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180032b65  mov     [rsp+88h+var_38], 0
0x180032b6d  mov     [rsp+88h+var_40], 0
0x180032b76  mov     [rsp+88h+var_48], edi
0x180032b7a  mov     [rsp+88h+var_50], rbx
0x180032b7f  lea     rcx, aAreconditionsm; "AreConditionsMet"
0x180032b86  mov     [rsp+88h+var_58], rcx
0x180032b8b  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180032b92  mov     [rsp+88h+var_60], rcx
0x180032b97  mov     [rsp+88h+var_68], 18Ch
0x180032b9f  xor     r9d, r9d
0x180032ba2  lea     r8, aD_0; "D"
0x180032ba9  xor     edx, edx
0x180032bab  mov     rcx, rax
0x180032bae  call    cs:__imp_WdsSetupLogMessageW
0x180032bb4  mov     dword ptr [rbp+70h], 0
0x180032bbb  mov     rax, [rsi]
0x180032bbe  mov     edx, 1
0x180032bc3  mov     rcx, rsi
0x180032bc6  mov     rax, [rax]
0x180032bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bce  nop
0x180032bcf  lea     rcx, [rbp+0D8h]
0x180032bd6  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180032bdc  nop
0x180032bdd  mov     rax, 0
0x180032be7  add     rsp, 68h
0x180032beb  pop     rdi
0x180032bec  pop     rsi
0x180032bed  pop     rbp
0x180032bee  pop     rbx
0x180032bef  retn
```
