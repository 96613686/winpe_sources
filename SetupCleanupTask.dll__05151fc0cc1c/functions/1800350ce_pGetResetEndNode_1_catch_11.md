# _pGetResetEndNode_::_1_::catch$11

- ea: `0x1800350ce`
- end: `0x1800351cd`
- name: `_pGetResetEndNode_::_1_::catch$11`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x1800350ce`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350e0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035127`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035137`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035127`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035137`
- `WDSCORE!CurrentIP` at `0x1800350e8`
- `WDSCORE!CurrentIP` at `0x1800350e8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003519d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003519d`

## string_xrefs

- `0x18003517a`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskcleanupremediation.cpp`

## pseudocode

```c
__int64 __fastcall pGetResetEndNode_::_1_::catch_11(__int64 a1, __int64 a2)
{
  DWORD LastError; // esi
  __int64 v4; // r14
  __int64 v5; // rbx
  const wchar_t *CString; // rdi
  UnBCL::String *v7; // rax
  const char *v8; // rax
  struct tagLOG_PARTIAL_MSG *v9; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(_QWORD *)(a2 + 200);
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5) )
  {
    v7 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5);
    CString = UnBCL::String::get_CString(v7);
  }
  else
  {
    CString = L"(NULL)";
  }
  v8 = (const char *)UnBCL::String::get_CString(*(UnBCL::String **)(a2 + 336));
  v9 = ConstructPartialMsgW(0x2000000, "IO error while loading %s. Message: %s", v8, (const char *)CString);
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    115,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskcleanupremediation.cpp",
    L"pGetResetEndNode",
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
0x1800350ce  mov     [rsp+arg_8], rdx
0x1800350d3  push    rbx
0x1800350d4  push    rbp
0x1800350d5  push    rsi
0x1800350d6  push    rdi
0x1800350d7  push    r14
0x1800350d9  sub     rsp, 60h
0x1800350dd  mov     rbp, rdx
0x1800350e0  call    cs:__imp_GetLastError
0x1800350e6  mov     esi, eax
0x1800350e8  call    cs:__imp_CurrentIP
0x1800350ee  mov     r14, rax
0x1800350f1  mov     rbx, [rbp+0C8h]
0x1800350f8  mov     rcx, [rbx]
0x1800350fb  mov     rax, [rcx+48h]
0x1800350ff  mov     rcx, rbx
0x180035102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035107  test    rax, rax
0x18003510a  jnz     short loc_180035115
0x18003510c  lea     rdi, aNull; "(NULL)"
0x180035113  jmp     short loc_180035130
0x180035115  mov     rax, [rbx]
0x180035118  mov     rcx, rbx
0x18003511b  mov     rax, [rax+48h]
0x18003511f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035124  mov     rcx, rax
0x180035127  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003512d  mov     rdi, rax
0x180035130  mov     rcx, [rbp+150h]
0x180035137  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003513d  mov     r8, rax
0x180035140  mov     r9, rdi
0x180035143  lea     rdx, aIoErrorWhileLo; "IO error while loading %s. Message: %s"
0x18003514a  mov     ecx, 2000000h; unsigned int
0x18003514f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180035154  mov     [rsp+88h+var_38], 0
0x18003515c  mov     [rsp+88h+var_40], 0
0x180035165  mov     [rsp+88h+var_48], esi
0x180035169  mov     [rsp+88h+var_50], r14
0x18003516e  lea     rcx, aPgetresetendno; "pGetResetEndNode"
0x180035175  mov     [rsp+88h+var_58], rcx
0x18003517a  lea     rcx, aBaseNtsetupSet_2; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180035181  mov     [rsp+88h+var_60], rcx
0x180035186  mov     [rsp+88h+var_68], 73h ; 's'
0x18003518e  xor     r9d, r9d
0x180035191  lea     r8, aD_0; "D"
0x180035198  xor     edx, edx
0x18003519a  mov     rcx, rax
0x18003519d  call    cs:__imp_WdsSetupLogMessageW
0x1800351a3  mov     rax, [rbx]
0x1800351a6  mov     edx, 1
0x1800351ab  mov     rcx, rbx
0x1800351ae  mov     rax, [rax]
0x1800351b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351b6  nop
0x1800351b7  mov     rax, 0
0x1800351c1  add     rsp, 60h
0x1800351c5  pop     r14
0x1800351c7  pop     rdi
0x1800351c8  pop     rsi
0x1800351c9  pop     rbp
0x1800351ca  pop     rbx
0x1800351cb  retn
```
