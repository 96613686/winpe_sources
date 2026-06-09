# _NumberOfDaysSinceOOBEFinished_::_1_::catch$9

- ea: `0x1800334ac`
- end: `0x180033605`
- name: `_NumberOfDaysSinceOOBEFinished_::_1_::catch$9`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x1800334ac`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003357f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003357f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033503`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033503`
- `WDSCORE!CurrentIP` at `0x1800334c4`
- `WDSCORE!CurrentIP` at `0x180033587`
- `WDSCORE!CurrentIP` at `0x1800334c4`
- `WDSCORE!CurrentIP` at `0x180033587`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033566`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800335ea`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033566`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800335ea`

## string_xrefs

- `0x180033543`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x1800335c7`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`

## pseudocode

```c
__int64 __fastcall NumberOfDaysSinceOOBEFinished_::_1_::catch_9(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rsi
  __int64 v5; // rbx
  const wchar_t *CString; // rax
  UnBCL::String *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(_QWORD *)(a2 + 168);
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5) )
  {
    v7 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5);
    CString = UnBCL::String::get_CString(v7);
  }
  else
  {
    CString = L"(NULL)";
  }
  v8 = ConstructPartialMsgW(50331648, "Couldn't find OOBE end time: %s", (const char *)CString);
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    482,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"NumberOfDaysSinceOOBEFinished",
    v4,
    LastError,
    0,
    0);
  (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  v9 = GetLastError();
  v10 = CurrentIP();
  v11 = ConstructPartialMsgW(0x4000000, "Assuming OOBE finished more than 5 days ago");
  WdsSetupLogMessageW(
    v11,
    0,
    L"D",
    0,
    485,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"NumberOfDaysSinceOOBEFinished",
    v10,
    v9,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x1800334ac  mov     [rsp+arg_8], rdx
0x1800334b1  push    rbx
0x1800334b2  push    rbp
0x1800334b3  push    rsi
0x1800334b4  push    rdi
0x1800334b5  sub     rsp, 68h
0x1800334b9  mov     rbp, rdx
0x1800334bc  call    cs:__imp_GetLastError
0x1800334c2  mov     edi, eax
0x1800334c4  call    cs:__imp_CurrentIP
0x1800334ca  mov     rsi, rax
0x1800334cd  mov     rbx, [rbp+0A8h]
0x1800334d4  mov     rcx, [rbx]
0x1800334d7  mov     rax, [rcx+48h]
0x1800334db  mov     rcx, rbx
0x1800334de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334e3  test    rax, rax
0x1800334e6  jnz     short loc_1800334F1
0x1800334e8  lea     rax, aNull; "(NULL)"
0x1800334ef  jmp     short loc_180033509
0x1800334f1  mov     rax, [rbx]
0x1800334f4  mov     rcx, rbx
0x1800334f7  mov     rax, [rax+48h]
0x1800334fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033500  mov     rcx, rax
0x180033503  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180033509  mov     r8, rax
0x18003350c  lea     rdx, aCouldnTFindOob; "Couldn't find OOBE end time: %s"
0x180033513  mov     ecx, 3000000h; unsigned int
0x180033518  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003351d  mov     [rsp+88h+var_38], 0
0x180033525  mov     [rsp+88h+var_40], 0
0x18003352e  mov     [rsp+88h+var_48], edi
0x180033532  mov     [rsp+88h+var_50], rsi
0x180033537  lea     rcx, aNumberofdayssi; "NumberOfDaysSinceOOBEFinished"
0x18003353e  mov     [rsp+88h+var_58], rcx
0x180033543  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18003354a  mov     [rsp+88h+var_60], rcx
0x18003354f  mov     [rsp+88h+var_68], 1E2h
0x180033557  xor     r9d, r9d
0x18003355a  lea     r8, aD_0; "D"
0x180033561  xor     edx, edx
0x180033563  mov     rcx, rax
0x180033566  call    cs:__imp_WdsSetupLogMessageW
0x18003356c  mov     rax, [rbx]
0x18003356f  mov     edx, 1
0x180033574  mov     rcx, rbx
0x180033577  mov     rax, [rax]
0x18003357a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003357f  call    cs:__imp_GetLastError
0x180033585  mov     edi, eax
0x180033587  call    cs:__imp_CurrentIP
0x18003358d  mov     rbx, rax
0x180033590  lea     rdx, aAssumingOobeFi; "Assuming OOBE finished more than 5 days"...
0x180033597  mov     ecx, 4000000h; unsigned int
0x18003359c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800335a1  mov     [rsp+88h+var_38], 0
0x1800335a9  mov     [rsp+88h+var_40], 0
0x1800335b2  mov     [rsp+88h+var_48], edi
0x1800335b6  mov     [rsp+88h+var_50], rbx
0x1800335bb  lea     rcx, aNumberofdayssi; "NumberOfDaysSinceOOBEFinished"
0x1800335c2  mov     [rsp+88h+var_58], rcx
0x1800335c7  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800335ce  mov     [rsp+88h+var_60], rcx
0x1800335d3  mov     [rsp+88h+var_68], 1E5h
0x1800335db  xor     r9d, r9d
0x1800335de  lea     r8, aD_0; "D"
0x1800335e5  xor     edx, edx
0x1800335e7  mov     rcx, rax
0x1800335ea  call    cs:__imp_WdsSetupLogMessageW
0x1800335f0  nop
0x1800335f1  mov     rax, 0
0x1800335fb  add     rsp, 68h
0x1800335ff  pop     rdi
0x180033600  pop     rsi
0x180033601  pop     rbp
0x180033602  pop     rbx
0x180033603  retn
```
