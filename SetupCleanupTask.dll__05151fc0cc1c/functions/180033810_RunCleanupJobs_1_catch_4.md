# _RunCleanupJobs_::_1_::catch$4

- ea: `0x180033810`
- end: `0x1800338e2`
- name: `_RunCleanupJobs_::_1_::catch$4`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x180033810`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033820`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033864`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033864`
- `WDSCORE!CurrentIP` at `0x180033828`
- `WDSCORE!CurrentIP` at `0x180033828`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800338c7`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800338c7`

## string_xrefs

- `0x1800338a4`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`

## pseudocode

```c
__int64 __fastcall RunCleanupJobs_::_1_::catch_4(__int64 a1, __int64 a2, double a3)
{
  DWORD LastError; // edi
  __int64 v5; // rsi
  __int64 v6; // rbx
  UnBCL::String *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = *(_QWORD *)(a2 + 104);
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 72LL))(v6) )
  {
    v7 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 72LL))(v6);
    UnBCL::String::get_CString(v7);
  }
  v8 = ConstructPartialMsgW(0x2000000, "Failed to save cleanup job. %e", a3);
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    678,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"RunCleanupJobs",
    v5,
    LastError,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x180033810  mov     [rsp+arg_8], rdx
0x180033815  push    rbx
0x180033816  push    rbp
0x180033817  push    rsi
0x180033818  push    rdi
0x180033819  sub     rsp, 68h
0x18003381d  mov     rbp, rdx
0x180033820  call    cs:__imp_GetLastError
0x180033826  mov     edi, eax
0x180033828  call    cs:__imp_CurrentIP
0x18003382e  mov     rsi, rax
0x180033831  mov     rbx, [rbp+68h]
0x180033835  mov     rcx, [rbx]
0x180033838  mov     rax, [rcx+48h]
0x18003383c  mov     rcx, rbx
0x18003383f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033844  test    rax, rax
0x180033847  jnz     short loc_180033852
0x180033849  lea     rax, aNull; "(NULL)"
0x180033850  jmp     short loc_18003386A
0x180033852  mov     rax, [rbx]
0x180033855  mov     rcx, rbx
0x180033858  mov     rax, [rax+48h]
0x18003385c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033861  mov     rcx, rax
0x180033864  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003386a  mov     r8, rax
0x18003386d  lea     rdx, aFailedToSaveCl; "Failed to save cleanup job. %e"
0x180033874  mov     ecx, 2000000h; unsigned int
0x180033879  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003387e  mov     [rsp+88h+var_38], 0
0x180033886  mov     [rsp+88h+var_40], 0
0x18003388f  mov     [rsp+88h+var_48], edi
0x180033893  mov     [rsp+88h+var_50], rsi
0x180033898  lea     rcx, aRuncleanupjobs; "RunCleanupJobs"
0x18003389f  mov     [rsp+88h+var_58], rcx
0x1800338a4  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800338ab  mov     [rsp+88h+var_60], rcx
0x1800338b0  mov     [rsp+88h+var_68], 2A6h
0x1800338b8  xor     r9d, r9d
0x1800338bb  lea     r8, aD_0; "D"
0x1800338c2  xor     edx, edx
0x1800338c4  mov     rcx, rax
0x1800338c7  call    cs:__imp_WdsSetupLogMessageW
0x1800338cd  nop
0x1800338ce  mov     rax, 0
0x1800338d8  add     rsp, 68h
0x1800338dc  pop     rdi
0x1800338dd  pop     rsi
0x1800338de  pop     rbp
0x1800338df  pop     rbx
0x1800338e0  retn
```
