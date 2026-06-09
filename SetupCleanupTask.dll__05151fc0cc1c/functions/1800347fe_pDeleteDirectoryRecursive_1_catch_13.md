# _pDeleteDirectoryRecursive_::_1_::catch$13

- ea: `0x1800347fe`
- end: `0x1800348f0`
- name: `_pDeleteDirectoryRecursive_::_1_::catch$13`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x1800347fe`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034810`
- `unbcl!?get_Win32ErrorCode@Win32Exception@UnBCL@@QEBAKXZ` at `0x18003482b`
- `unbcl!?get_Win32ErrorCode@Win32Exception@UnBCL@@QEBAKXZ` at `0x18003482b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034849`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034849`
- `WDSCORE!CurrentIP` at `0x180034818`
- `WDSCORE!CurrentIP` at `0x180034818`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800348af`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800348af`

## string_xrefs

- `0x180034880`: `pDeleteDirectoryRecursive`
- `0x18003488c`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`

## pseudocode

```c
__int64 __fastcall pDeleteDirectoryRecursive_::_1_::catch_13(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rsi
  UnBCL::Win32Exception *v5; // rbx
  unsigned int Win32ErrorCode; // r14d
  UnBCL::String *v7; // rcx
  const wchar_t *CString; // rax
  struct tagLOG_PARTIAL_MSG *v9; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(UnBCL::Win32Exception **)(a2 + 296);
  Win32ErrorCode = UnBCL::Win32Exception::get_Win32ErrorCode(v5);
  v7 = *(UnBCL::String **)(a2 + 168);
  if ( v7 )
    CString = UnBCL::String::get_CString(v7);
  else
    CString = L"(NULL)";
  v9 = ConstructPartialMsgW(
         0x2000000,
         "Unexpected exception while processing directoy %s. GLE = %d",
         (const char *)CString,
         Win32ErrorCode);
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    214,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
    L"pDeleteDirectoryRecursive",
    v4,
    LastError,
    0,
    0);
  if ( v5 )
    (**(void (__fastcall ***)(UnBCL::Win32Exception *, __int64))v5)(v5, 1);
  **(_DWORD **)(a2 + 176) = 1;
  return 0;
}

```

## disassembly

```asm
0x1800347fe  mov     [rsp+arg_8], rdx
0x180034803  push    rbx
0x180034804  push    rbp
0x180034805  push    rsi
0x180034806  push    rdi
0x180034807  push    r14
0x180034809  sub     rsp, 60h
0x18003480d  mov     rbp, rdx
0x180034810  call    cs:__imp_GetLastError
0x180034816  mov     edi, eax
0x180034818  call    cs:__imp_CurrentIP
0x18003481e  mov     rsi, rax
0x180034821  mov     rbx, [rbp+128h]
0x180034828  mov     rcx, rbx
0x18003482b  call    cs:__imp_?get_Win32ErrorCode@Win32Exception@UnBCL@@QEBAKXZ; UnBCL::Win32Exception::get_Win32ErrorCode(void)
0x180034831  mov     r14d, eax
0x180034834  mov     rcx, [rbp+0A8h]
0x18003483b  test    rcx, rcx
0x18003483e  jnz     short loc_180034849
0x180034840  lea     rax, aNull; "(NULL)"
0x180034847  jmp     short loc_18003484F
0x180034849  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003484f  mov     r9d, r14d
0x180034852  mov     r8, rax
0x180034855  lea     rdx, aUnexpectedExce; "Unexpected exception while processing d"...
0x18003485c  mov     ecx, 2000000h; unsigned int
0x180034861  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180034866  mov     [rsp+88h+var_38], 0
0x18003486e  mov     [rsp+88h+var_40], 0
0x180034877  mov     [rsp+88h+var_48], edi
0x18003487b  mov     [rsp+88h+var_50], rsi
0x180034880  lea     rcx, aPdeletedirecto; "pDeleteDirectoryRecursive"
0x180034887  mov     [rsp+88h+var_58], rcx
0x18003488c  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180034893  mov     [rsp+88h+var_60], rcx
0x180034898  mov     [rsp+88h+var_68], 0D6h
0x1800348a0  xor     r9d, r9d
0x1800348a3  lea     r8, aD_0; "D"
0x1800348aa  xor     edx, edx
0x1800348ac  mov     rcx, rax
0x1800348af  call    cs:__imp_WdsSetupLogMessageW
0x1800348b5  test    rbx, rbx
0x1800348b8  jz      short loc_1800348CD
0x1800348ba  mov     rax, [rbx]
0x1800348bd  mov     edx, 1
0x1800348c2  mov     rcx, rbx
0x1800348c5  mov     rax, [rax]
0x1800348c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348cd  mov     rax, [rbp+0B0h]
0x1800348d4  mov     dword ptr [rax], 1
0x1800348da  mov     rax, 0
0x1800348e4  add     rsp, 60h
0x1800348e8  pop     r14
0x1800348ea  pop     rdi
0x1800348eb  pop     rsi
0x1800348ec  pop     rbp
0x1800348ed  pop     rbx
0x1800348ee  retn
```
