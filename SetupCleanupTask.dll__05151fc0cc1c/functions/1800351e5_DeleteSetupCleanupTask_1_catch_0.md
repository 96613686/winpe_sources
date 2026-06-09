# _DeleteSetupCleanupTask_::_1_::catch$0

- ea: `0x1800351e5`
- end: `0x1800352ca`
- name: `_DeleteSetupCleanupTask_::_1_::catch$0`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x18000638c`
- `0x1800351e5`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351f5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035239`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035239`
- `WDSCORE!CurrentIP` at `0x1800351fd`
- `WDSCORE!CurrentIP` at `0x1800351fd`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003529c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003529c`

## string_xrefs

- `0x180035279`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskmanager.cpp`
- `0x18003526d`: `DeleteSetupCleanupTask`
- `0x180035242`: `Failed to delete the Setup cleanup jobs. %s`

## pseudocode

```c
__int64 __fastcall DeleteSetupCleanupTask_::_1_::catch_0(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rsi
  __int64 v5; // rbx
  const wchar_t *CString; // rax
  UnBCL::String *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(_QWORD *)(a2 + 96);
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5) )
  {
    v7 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5);
    CString = UnBCL::String::get_CString(v7);
  }
  else
  {
    CString = L"(NULL)";
  }
  v8 = ConstructPartialMsgW(0x2000000, "Failed to delete the Setup cleanup jobs. %s", (const char *)CString);
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    682,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
    L"DeleteSetupCleanupTask",
    v4,
    LastError,
    0,
    0);
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  return 0;
}

```

## disassembly

```asm
0x1800351e5  mov     [rsp+arg_8], rdx
0x1800351ea  push    rbx
0x1800351eb  push    rbp
0x1800351ec  push    rsi
0x1800351ed  push    rdi
0x1800351ee  sub     rsp, 68h
0x1800351f2  mov     rbp, rdx
0x1800351f5  call    cs:__imp_GetLastError
0x1800351fb  mov     edi, eax
0x1800351fd  call    cs:__imp_CurrentIP
0x180035203  mov     rsi, rax
0x180035206  mov     rbx, [rbp+60h]
0x18003520a  mov     rcx, [rbx]
0x18003520d  mov     rax, [rcx+48h]
0x180035211  mov     rcx, rbx
0x180035214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035219  test    rax, rax
0x18003521c  jnz     short loc_180035227
0x18003521e  lea     rax, aNull; "(NULL)"
0x180035225  jmp     short loc_18003523F
0x180035227  mov     rax, [rbx]
0x18003522a  mov     rcx, rbx
0x18003522d  mov     rax, [rax+48h]
0x180035231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035236  mov     rcx, rax
0x180035239  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003523f  mov     r8, rax
0x180035242  lea     rdx, aFailedToDelete_4; "Failed to delete the Setup cleanup jobs"...
0x180035249  mov     ecx, 2000000h; unsigned int
0x18003524e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180035253  mov     [rsp+88h+var_38], 0
0x18003525b  mov     [rsp+88h+var_40], 0
0x180035264  mov     [rsp+88h+var_48], edi
0x180035268  mov     [rsp+88h+var_50], rsi
0x18003526d  lea     rcx, aDeletesetupcle; "DeleteSetupCleanupTask"
0x180035274  mov     [rsp+88h+var_58], rcx
0x180035279  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180035280  mov     [rsp+88h+var_60], rcx
0x180035285  mov     [rsp+88h+var_68], 2AAh
0x18003528d  xor     r9d, r9d
0x180035290  lea     r8, aD_0; "D"
0x180035297  xor     edx, edx
0x180035299  mov     rcx, rax
0x18003529c  call    cs:__imp_WdsSetupLogMessageW
0x1800352a2  mov     rax, [rbx]
0x1800352a5  mov     edx, 1
0x1800352aa  mov     rcx, rbx
0x1800352ad  mov     rax, [rax]
0x1800352b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352b5  nop
0x1800352b6  mov     rax, 0
0x1800352c0  add     rsp, 68h
0x1800352c4  pop     rdi
0x1800352c5  pop     rsi
0x1800352c6  pop     rbp
0x1800352c7  pop     rbx
0x1800352c8  retn
```
