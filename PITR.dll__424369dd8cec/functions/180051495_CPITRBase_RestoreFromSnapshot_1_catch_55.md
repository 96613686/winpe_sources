# _CPITRBase::RestoreFromSnapshot_::_1_::catch$55

- ea: `0x180051495`
- end: `0x1800515b2`
- name: `_CPITRBase::RestoreFromSnapshot_::_1_::catch$55`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x180009e04`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514ce`
- `WDSCORE!CurrentIP` at `0x1800514d6`
- `WDSCORE!CurrentIP` at `0x1800514d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18005156e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18005156e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800514ef`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180051508`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800514ef`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180051508`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800514c7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800514c7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180051595`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180051595`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800514e6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800514ff`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800514e6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800514ff`

## string_xrefs

- `0x18005154b`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`

## pseudocode

```c
__int64 __fastcall CPITRBase::RestoreFromSnapshot_::_1_::catch_55(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  __int64 v4; // rax
  DWORD LastError; // esi
  __int64 v6; // rdi
  UnBCL::String *v7; // rax
  const char *CString; // rbx
  UnBCL::String *v9; // rax
  const char *v10; // rax
  struct tagLOG_PARTIAL_MSG *v11; // rax

  v3 = *(_QWORD *)(a2 + 208);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(a2 + 384, v4);
  LastError = GetLastError();
  v6 = CurrentIP();
  v7 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 384);
  CString = (const char *)UnBCL::String::get_CString(v7);
  v9 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a2 + 504);
  v10 = (const char *)UnBCL::String::get_CString(v9);
  v11 = ConstructPartialMsgW(0x2000000, "Exception creating restore-active marker %s: %s", v10, CString);
  WdsSetupLogMessageW(
    v11,
    0,
    L"D",
    0,
    4948,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
    L"CPITRBase::RestoreFromSnapshot",
    v6,
    LastError,
    0,
    0);
  (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
  *(_DWORD *)(a2 + 96) = -2147467259;
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 384);
  return 0;
}

```

## disassembly

```asm
0x180051495  mov     [rsp+arg_8], rdx
0x18005149a  push    rbx
0x18005149b  push    rbp
0x18005149c  push    rsi
0x18005149d  push    rdi
0x18005149e  push    r14
0x1800514a0  sub     rsp, 60h
0x1800514a4  mov     rbp, rdx
0x1800514a7  mov     r14, [rbp+0D0h]
0x1800514ae  mov     rax, [r14]
0x1800514b1  mov     rcx, r14
0x1800514b4  mov     rax, [rax+20h]
0x1800514b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514bd  mov     rdx, rax
0x1800514c0  lea     rcx, [rbp+180h]
0x1800514c7  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800514cd  nop
0x1800514ce  call    cs:__imp_GetLastError
0x1800514d4  mov     esi, eax
0x1800514d6  call    cs:__imp_CurrentIP
0x1800514dc  mov     rdi, rax
0x1800514df  lea     rcx, [rbp+180h]
0x1800514e6  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800514ec  mov     rcx, rax
0x1800514ef  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800514f5  mov     rbx, rax
0x1800514f8  lea     rcx, [rbp+1F8h]
0x1800514ff  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180051505  mov     rcx, rax
0x180051508  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18005150e  mov     r9, rbx
0x180051511  mov     r8, rax
0x180051514  lea     rdx, aExceptionCreat; "Exception creating restore-active marke"...
0x18005151b  mov     ecx, 2000000h; unsigned int
0x180051520  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180051525  mov     [rsp+88h+var_38], 0
0x18005152d  mov     [rsp+88h+var_40], 0
0x180051536  mov     [rsp+88h+var_48], esi
0x18005153a  mov     [rsp+88h+var_50], rdi
0x18005153f  lea     rcx, aCpitrbaseResto; "CPITRBase::RestoreFromSnapshot"
0x180051546  mov     [rsp+88h+var_58], rcx
0x18005154b  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180051552  mov     [rsp+88h+var_60], rcx
0x180051557  mov     [rsp+88h+var_68], 1354h
0x18005155f  xor     r9d, r9d
0x180051562  lea     r8, aD; "D"
0x180051569  xor     edx, edx
0x18005156b  mov     rcx, rax
0x18005156e  call    cs:__imp_WdsSetupLogMessageW
0x180051574  mov     rax, [r14]
0x180051577  mov     edx, 1
0x18005157c  mov     rcx, r14
0x18005157f  mov     rax, [rax]
0x180051582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051587  mov     dword ptr [rbp+60h], 80004005h
0x18005158e  lea     rcx, [rbp+180h]
0x180051595  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18005159b  nop
0x18005159c  mov     rax, 0
0x1800515a6  add     rsp, 60h
0x1800515aa  pop     r14
0x1800515ac  pop     rdi
0x1800515ad  pop     rsi
0x1800515ae  pop     rbp
0x1800515af  pop     rbx
0x1800515b0  retn
```
