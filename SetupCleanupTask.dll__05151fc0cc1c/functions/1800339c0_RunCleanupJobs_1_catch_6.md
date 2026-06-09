# _RunCleanupJobs_::_1_::catch$6

- ea: `0x1800339c0`
- end: `0x180033a92`
- name: `_RunCleanupJobs_::_1_::catch$6`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x1800339c0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339d0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033a14`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033a14`
- `WDSCORE!CurrentIP` at `0x1800339d8`
- `WDSCORE!CurrentIP` at `0x1800339d8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033a77`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033a77`

## string_xrefs

- `0x180033a54`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`

## pseudocode

```c
__int64 __fastcall RunCleanupJobs_::_1_::catch_6(__int64 a1, __int64 a2, double a3)
{
  DWORD LastError; // edi
  __int64 v5; // rsi
  __int64 v6; // rbx
  UnBCL::String *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = *(_QWORD *)(a2 + 120);
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
    642,
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
0x1800339c0  mov     [rsp+arg_8], rdx
0x1800339c5  push    rbx
0x1800339c6  push    rbp
0x1800339c7  push    rsi
0x1800339c8  push    rdi
0x1800339c9  sub     rsp, 68h
0x1800339cd  mov     rbp, rdx
0x1800339d0  call    cs:__imp_GetLastError
0x1800339d6  mov     edi, eax
0x1800339d8  call    cs:__imp_CurrentIP
0x1800339de  mov     rsi, rax
0x1800339e1  mov     rbx, [rbp+78h]
0x1800339e5  mov     rcx, [rbx]
0x1800339e8  mov     rax, [rcx+48h]
0x1800339ec  mov     rcx, rbx
0x1800339ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339f4  test    rax, rax
0x1800339f7  jnz     short loc_180033A02
0x1800339f9  lea     rax, aNull; "(NULL)"
0x180033a00  jmp     short loc_180033A1A
0x180033a02  mov     rax, [rbx]
0x180033a05  mov     rcx, rbx
0x180033a08  mov     rax, [rax+48h]
0x180033a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a11  mov     rcx, rax
0x180033a14  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180033a1a  mov     r8, rax
0x180033a1d  lea     rdx, aFailedToSaveCl; "Failed to save cleanup job. %e"
0x180033a24  mov     ecx, 2000000h; unsigned int
0x180033a29  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180033a2e  mov     [rsp+88h+var_38], 0
0x180033a36  mov     [rsp+88h+var_40], 0
0x180033a3f  mov     [rsp+88h+var_48], edi
0x180033a43  mov     [rsp+88h+var_50], rsi
0x180033a48  lea     rcx, aRuncleanupjobs; "RunCleanupJobs"
0x180033a4f  mov     [rsp+88h+var_58], rcx
0x180033a54  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180033a5b  mov     [rsp+88h+var_60], rcx
0x180033a60  mov     [rsp+88h+var_68], 282h
0x180033a68  xor     r9d, r9d
0x180033a6b  lea     r8, aD_0; "D"
0x180033a72  xor     edx, edx
0x180033a74  mov     rcx, rax
0x180033a77  call    cs:__imp_WdsSetupLogMessageW
0x180033a7d  nop
0x180033a7e  mov     rax, 0
0x180033a88  add     rsp, 68h
0x180033a8c  pop     rdi
0x180033a8d  pop     rsi
0x180033a8e  pop     rbp
0x180033a8f  pop     rbx
0x180033a90  retn
```
