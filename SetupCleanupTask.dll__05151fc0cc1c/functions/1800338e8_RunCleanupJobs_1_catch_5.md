# _RunCleanupJobs_::_1_::catch$5

- ea: `0x1800338e8`
- end: `0x1800339ba`
- name: `_RunCleanupJobs_::_1_::catch$5`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x1800338e8`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338f8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003393c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003393c`
- `WDSCORE!CurrentIP` at `0x180033900`
- `WDSCORE!CurrentIP` at `0x180033900`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003399f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003399f`

## string_xrefs

- `0x18003397c`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`

## pseudocode

```c
__int64 __fastcall RunCleanupJobs_::_1_::catch_5(__int64 a1, __int64 a2, double a3)
{
  DWORD LastError; // edi
  __int64 v5; // rsi
  __int64 v6; // rbx
  UnBCL::String *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = *(_QWORD *)(a2 + 112);
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
    660,
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
0x1800338e8  mov     [rsp+arg_8], rdx
0x1800338ed  push    rbx
0x1800338ee  push    rbp
0x1800338ef  push    rsi
0x1800338f0  push    rdi
0x1800338f1  sub     rsp, 68h
0x1800338f5  mov     rbp, rdx
0x1800338f8  call    cs:__imp_GetLastError
0x1800338fe  mov     edi, eax
0x180033900  call    cs:__imp_CurrentIP
0x180033906  mov     rsi, rax
0x180033909  mov     rbx, [rbp+70h]
0x18003390d  mov     rcx, [rbx]
0x180033910  mov     rax, [rcx+48h]
0x180033914  mov     rcx, rbx
0x180033917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003391c  test    rax, rax
0x18003391f  jnz     short loc_18003392A
0x180033921  lea     rax, aNull; "(NULL)"
0x180033928  jmp     short loc_180033942
0x18003392a  mov     rax, [rbx]
0x18003392d  mov     rcx, rbx
0x180033930  mov     rax, [rax+48h]
0x180033934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033939  mov     rcx, rax
0x18003393c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180033942  mov     r8, rax
0x180033945  lea     rdx, aFailedToSaveCl; "Failed to save cleanup job. %e"
0x18003394c  mov     ecx, 2000000h; unsigned int
0x180033951  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180033956  mov     [rsp+88h+var_38], 0
0x18003395e  mov     [rsp+88h+var_40], 0
0x180033967  mov     [rsp+88h+var_48], edi
0x18003396b  mov     [rsp+88h+var_50], rsi
0x180033970  lea     rcx, aRuncleanupjobs; "RunCleanupJobs"
0x180033977  mov     [rsp+88h+var_58], rcx
0x18003397c  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180033983  mov     [rsp+88h+var_60], rcx
0x180033988  mov     [rsp+88h+var_68], 294h
0x180033990  xor     r9d, r9d
0x180033993  lea     r8, aD_0; "D"
0x18003399a  xor     edx, edx
0x18003399c  mov     rcx, rax
0x18003399f  call    cs:__imp_WdsSetupLogMessageW
0x1800339a5  nop
0x1800339a6  mov     rax, 0
0x1800339b0  add     rsp, 68h
0x1800339b4  pop     rdi
0x1800339b5  pop     rsi
0x1800339b6  pop     rbp
0x1800339b7  pop     rbx
0x1800339b8  retn
```
