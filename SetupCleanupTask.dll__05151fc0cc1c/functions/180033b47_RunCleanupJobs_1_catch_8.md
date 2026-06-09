# _RunCleanupJobs_::_1_::catch$8

- ea: `0x180033b47`
- end: `0x180033c3b`
- name: `_RunCleanupJobs_::_1_::catch$8`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x180033b47`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b57`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033b9e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033b9e`
- `WDSCORE!CurrentIP` at `0x180033b5f`
- `WDSCORE!CurrentIP` at `0x180033b5f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033c01`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033c01`

## string_xrefs

- `0x180033bde`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`

## pseudocode

```c
__int64 __fastcall RunCleanupJobs_::_1_::catch_8(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rsi
  __int64 v5; // rbx
  const wchar_t *CString; // rax
  UnBCL::String *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(_QWORD *)(a2 + 128);
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5) )
  {
    v7 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5);
    CString = UnBCL::String::get_CString(v7);
  }
  else
  {
    CString = L"(NULL)";
  }
  v8 = ConstructPartialMsgW(0x2000000, "Cleanup job failed. %s", (const char *)CString);
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    690,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"RunCleanupJobs",
    v4,
    LastError,
    0,
    0);
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  **(_DWORD **)(a2 + 280) = 1;
  return 0;
}

```

## disassembly

```asm
0x180033b47  mov     [rsp+arg_8], rdx
0x180033b4c  push    rbx
0x180033b4d  push    rbp
0x180033b4e  push    rsi
0x180033b4f  push    rdi
0x180033b50  sub     rsp, 68h
0x180033b54  mov     rbp, rdx
0x180033b57  call    cs:__imp_GetLastError
0x180033b5d  mov     edi, eax
0x180033b5f  call    cs:__imp_CurrentIP
0x180033b65  mov     rsi, rax
0x180033b68  mov     rbx, [rbp+80h]
0x180033b6f  mov     rcx, [rbx]
0x180033b72  mov     rax, [rcx+48h]
0x180033b76  mov     rcx, rbx
0x180033b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b7e  test    rax, rax
0x180033b81  jnz     short loc_180033B8C
0x180033b83  lea     rax, aNull; "(NULL)"
0x180033b8a  jmp     short loc_180033BA4
0x180033b8c  mov     rax, [rbx]
0x180033b8f  mov     rcx, rbx
0x180033b92  mov     rax, [rax+48h]
0x180033b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b9b  mov     rcx, rax
0x180033b9e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180033ba4  mov     r8, rax
0x180033ba7  lea     rdx, aCleanupJobFail; "Cleanup job failed. %s"
0x180033bae  mov     ecx, 2000000h; unsigned int
0x180033bb3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180033bb8  mov     [rsp+88h+var_38], 0
0x180033bc0  mov     [rsp+88h+var_40], 0
0x180033bc9  mov     [rsp+88h+var_48], edi
0x180033bcd  mov     [rsp+88h+var_50], rsi
0x180033bd2  lea     rcx, aRuncleanupjobs; "RunCleanupJobs"
0x180033bd9  mov     [rsp+88h+var_58], rcx
0x180033bde  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180033be5  mov     [rsp+88h+var_60], rcx
0x180033bea  mov     [rsp+88h+var_68], 2B2h
0x180033bf2  xor     r9d, r9d
0x180033bf5  lea     r8, aD_0; "D"
0x180033bfc  xor     edx, edx
0x180033bfe  mov     rcx, rax
0x180033c01  call    cs:__imp_WdsSetupLogMessageW
0x180033c07  mov     rax, [rbx]
0x180033c0a  mov     edx, 1
0x180033c0f  mov     rcx, rbx
0x180033c12  mov     rax, [rax]
0x180033c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c1a  mov     rax, [rbp+118h]
0x180033c21  mov     dword ptr [rax], 1
0x180033c27  mov     rax, 0
0x180033c31  add     rsp, 68h
0x180033c35  pop     rdi
0x180033c36  pop     rsi
0x180033c37  pop     rbp
0x180033c38  pop     rbx
0x180033c39  retn
```
