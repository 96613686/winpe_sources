# _LogUpdateCV_::_1_::catch$15

- ea: `0x180033306`
- end: `0x1800333f4`
- name: `_LogUpdateCV_::_1_::catch$15`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x180033306`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033316`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003335d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003335d`
- `WDSCORE!CurrentIP` at `0x18003331e`
- `WDSCORE!CurrentIP` at `0x18003331e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800333c0`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800333c0`

## string_xrefs

- `0x18003339d`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x180033391`: `LogUpdateCV`

## pseudocode

```c
__int64 __fastcall LogUpdateCV_::_1_::catch_15(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rsi
  __int64 v5; // rbx
  const wchar_t *CString; // rax
  UnBCL::String *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(_QWORD *)(a2 + 256);
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5) )
  {
    v7 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5);
    CString = UnBCL::String::get_CString(v7);
  }
  else
  {
    CString = L"(NULL)";
  }
  v8 = ConstructPartialMsgW(0x2000000, "An unexpected exception was caught. %s", (const char *)CString);
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    767,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"LogUpdateCV",
    v4,
    LastError,
    0,
    0);
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  *(_DWORD *)(a2 + 96) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x180033306  mov     [rsp+arg_8], rdx
0x18003330b  push    rbx
0x18003330c  push    rbp
0x18003330d  push    rsi
0x18003330e  push    rdi
0x18003330f  sub     rsp, 68h
0x180033313  mov     rbp, rdx
0x180033316  call    cs:__imp_GetLastError
0x18003331c  mov     edi, eax
0x18003331e  call    cs:__imp_CurrentIP
0x180033324  mov     rsi, rax
0x180033327  mov     rbx, [rbp+100h]
0x18003332e  mov     rcx, [rbx]
0x180033331  mov     rax, [rcx+48h]
0x180033335  mov     rcx, rbx
0x180033338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003333d  test    rax, rax
0x180033340  jnz     short loc_18003334B
0x180033342  lea     rax, aNull; "(NULL)"
0x180033349  jmp     short loc_180033363
0x18003334b  mov     rax, [rbx]
0x18003334e  mov     rcx, rbx
0x180033351  mov     rax, [rax+48h]
0x180033355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003335a  mov     rcx, rax
0x18003335d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180033363  mov     r8, rax
0x180033366  lea     rdx, aAnUnexpectedEx; "An unexpected exception was caught. %s"
0x18003336d  mov     ecx, 2000000h; unsigned int
0x180033372  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180033377  mov     [rsp+88h+var_38], 0
0x18003337f  mov     [rsp+88h+var_40], 0
0x180033388  mov     [rsp+88h+var_48], edi
0x18003338c  mov     [rsp+88h+var_50], rsi
0x180033391  lea     rcx, aLogupdatecv; "LogUpdateCV"
0x180033398  mov     [rsp+88h+var_58], rcx
0x18003339d  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800333a4  mov     [rsp+88h+var_60], rcx
0x1800333a9  mov     [rsp+88h+var_68], 2FFh
0x1800333b1  xor     r9d, r9d
0x1800333b4  lea     r8, aD_0; "D"
0x1800333bb  xor     edx, edx
0x1800333bd  mov     rcx, rax
0x1800333c0  call    cs:__imp_WdsSetupLogMessageW
0x1800333c6  mov     rax, [rbx]
0x1800333c9  mov     edx, 1
0x1800333ce  mov     rcx, rbx
0x1800333d1  mov     rax, [rax]
0x1800333d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333d9  mov     dword ptr [rbp+60h], 80004005h
0x1800333e0  mov     rax, 0
0x1800333ea  add     rsp, 68h
0x1800333ee  pop     rdi
0x1800333ef  pop     rsi
0x1800333f0  pop     rbp
0x1800333f1  pop     rbx
0x1800333f2  retn
```
