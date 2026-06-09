# _DoCleanup_::_1_::catch$34

- ea: `0x180032f49`
- end: `0x1800330b5`
- name: `_DoCleanup_::_1_::catch$34`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x18000638c`
- `0x1800174c4`
- `0x180032f49`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033026`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180032fa0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180032fa0`
- `WDSCORE!CurrentIP` at `0x180032f61`
- `WDSCORE!CurrentIP` at `0x18003302e`
- `WDSCORE!CurrentIP` at `0x180032f61`
- `WDSCORE!CurrentIP` at `0x18003302e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033003`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033094`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033003`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033094`

## string_xrefs

- `0x180032fe0`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x180033071`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18003303a`: `Delete the setup cleanup task. hr = 0x%x`

## pseudocode

```c
__int64 __fastcall DoCleanup_::_1_::catch_34(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rsi
  __int64 v5; // rbx
  const wchar_t *CString; // rax
  UnBCL::String *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax
  int v9; // ebx
  DWORD v10; // esi
  __int64 v11; // rdi
  struct tagLOG_PARTIAL_MSG *v12; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(_QWORD *)(a2 + 472);
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
    1136,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"DoCleanup",
    v4,
    LastError,
    0,
    0);
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  v9 = DeleteSetupCleanupTask();
  *(_DWORD *)(a2 + 112) = v9;
  v10 = GetLastError();
  v11 = CurrentIP();
  v12 = ConstructPartialMsgW(0x4000000, "Delete the setup cleanup task. hr = 0x%x", v9);
  WdsSetupLogMessageW(
    v12,
    0,
    L"D",
    0,
    1140,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"DoCleanup",
    v11,
    v10,
    0,
    0);
  *(_DWORD *)(a2 + 112) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x180032f49  mov     [rsp+arg_8], rdx
0x180032f4e  push    rbx
0x180032f4f  push    rbp
0x180032f50  push    rsi
0x180032f51  push    rdi
0x180032f52  sub     rsp, 68h
0x180032f56  mov     rbp, rdx
0x180032f59  call    cs:__imp_GetLastError
0x180032f5f  mov     edi, eax
0x180032f61  call    cs:__imp_CurrentIP
0x180032f67  mov     rsi, rax
0x180032f6a  mov     rbx, [rbp+1D8h]
0x180032f71  mov     rcx, [rbx]
0x180032f74  mov     rax, [rcx+48h]
0x180032f78  mov     rcx, rbx
0x180032f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f80  test    rax, rax
0x180032f83  jnz     short loc_180032F8E
0x180032f85  lea     rax, aNull; "(NULL)"
0x180032f8c  jmp     short loc_180032FA6
0x180032f8e  mov     rax, [rbx]
0x180032f91  mov     rcx, rbx
0x180032f94  mov     rax, [rax+48h]
0x180032f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f9d  mov     rcx, rax
0x180032fa0  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180032fa6  mov     r8, rax
0x180032fa9  lea     rdx, aAnUnexpectedEx; "An unexpected exception was caught. %s"
0x180032fb0  mov     ecx, 2000000h; unsigned int
0x180032fb5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180032fba  mov     [rsp+88h+var_38], 0
0x180032fc2  mov     [rsp+88h+var_40], 0
0x180032fcb  mov     [rsp+88h+var_48], edi
0x180032fcf  mov     [rsp+88h+var_50], rsi
0x180032fd4  lea     rcx, dwFlags; "DoCleanup"
0x180032fdb  mov     [rsp+88h+var_58], rcx
0x180032fe0  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180032fe7  mov     [rsp+88h+var_60], rcx
0x180032fec  mov     [rsp+88h+var_68], 470h
0x180032ff4  xor     r9d, r9d
0x180032ff7  lea     r8, aD_0; "D"
0x180032ffe  xor     edx, edx
0x180033000  mov     rcx, rax
0x180033003  call    cs:__imp_WdsSetupLogMessageW
0x180033009  mov     rax, [rbx]
0x18003300c  mov     edx, 1
0x180033011  mov     rcx, rbx
0x180033014  mov     rax, [rax]
0x180033017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003301c  call    ?DeleteSetupCleanupTask@@YAJXZ; DeleteSetupCleanupTask(void)
0x180033021  mov     ebx, eax
0x180033023  mov     [rbp+70h], eax
0x180033026  call    cs:__imp_GetLastError
0x18003302c  mov     esi, eax
0x18003302e  call    cs:__imp_CurrentIP
0x180033034  mov     rdi, rax
0x180033037  mov     r8d, ebx
0x18003303a  lea     rdx, aDeleteTheSetup; "Delete the setup cleanup task. hr = 0x%"...
0x180033041  mov     ecx, 4000000h; unsigned int
0x180033046  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003304b  mov     [rsp+88h+var_38], 0
0x180033053  mov     [rsp+88h+var_40], 0
0x18003305c  mov     [rsp+88h+var_48], esi
0x180033060  mov     [rsp+88h+var_50], rdi
0x180033065  lea     rcx, dwFlags; "DoCleanup"
0x18003306c  mov     [rsp+88h+var_58], rcx
0x180033071  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180033078  mov     [rsp+88h+var_60], rcx
0x18003307d  mov     [rsp+88h+var_68], 474h
0x180033085  xor     r9d, r9d
0x180033088  lea     r8, aD_0; "D"
0x18003308f  xor     edx, edx
0x180033091  mov     rcx, rax
0x180033094  call    cs:__imp_WdsSetupLogMessageW
0x18003309a  mov     dword ptr [rbp+70h], 80004005h
0x1800330a1  mov     rax, 0
0x1800330ab  add     rsp, 68h
0x1800330af  pop     rdi
0x1800330b0  pop     rsi
0x1800330b1  pop     rbp
0x1800330b2  pop     rbx
0x1800330b3  retn
```
