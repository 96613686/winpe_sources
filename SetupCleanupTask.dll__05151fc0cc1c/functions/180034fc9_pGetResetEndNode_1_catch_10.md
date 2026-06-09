# _pGetResetEndNode_::_1_::catch$10

- ea: `0x180034fc9`
- end: `0x1800350c8`
- name: `_pGetResetEndNode_::_1_::catch$10`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000638c`
- `0x180034fc9`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fdb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035022`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035032`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035022`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035032`
- `WDSCORE!CurrentIP` at `0x180034fe3`
- `WDSCORE!CurrentIP` at `0x180034fe3`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035098`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035098`

## string_xrefs

- `0x180035075`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskcleanupremediation.cpp`
- `0x18003503e`: `XML parse error while loading %s. Message: %s`

## pseudocode

```c
__int64 __fastcall pGetResetEndNode_::_1_::catch_10(__int64 a1, __int64 a2)
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
  v5 = *(_QWORD *)(a2 + 192);
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
  v9 = ConstructPartialMsgW(0x2000000, "XML parse error while loading %s. Message: %s", v8, (const char *)CString);
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    103,
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
0x180034fc9  mov     [rsp+arg_8], rdx
0x180034fce  push    rbx
0x180034fcf  push    rbp
0x180034fd0  push    rsi
0x180034fd1  push    rdi
0x180034fd2  push    r14
0x180034fd4  sub     rsp, 60h
0x180034fd8  mov     rbp, rdx
0x180034fdb  call    cs:__imp_GetLastError
0x180034fe1  mov     esi, eax
0x180034fe3  call    cs:__imp_CurrentIP
0x180034fe9  mov     r14, rax
0x180034fec  mov     rbx, [rbp+0C0h]
0x180034ff3  mov     rcx, [rbx]
0x180034ff6  mov     rax, [rcx+48h]
0x180034ffa  mov     rcx, rbx
0x180034ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035002  test    rax, rax
0x180035005  jnz     short loc_180035010
0x180035007  lea     rdi, aNull; "(NULL)"
0x18003500e  jmp     short loc_18003502B
0x180035010  mov     rax, [rbx]
0x180035013  mov     rcx, rbx
0x180035016  mov     rax, [rax+48h]
0x18003501a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003501f  mov     rcx, rax
0x180035022  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180035028  mov     rdi, rax
0x18003502b  mov     rcx, [rbp+150h]
0x180035032  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180035038  mov     r8, rax
0x18003503b  mov     r9, rdi
0x18003503e  lea     rdx, aXmlParseErrorW; "XML parse error while loading %s. Messa"...
0x180035045  mov     ecx, 2000000h; unsigned int
0x18003504a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003504f  mov     [rsp+88h+var_38], 0
0x180035057  mov     [rsp+88h+var_40], 0
0x180035060  mov     [rsp+88h+var_48], esi
0x180035064  mov     [rsp+88h+var_50], r14
0x180035069  lea     rcx, aPgetresetendno; "pGetResetEndNode"
0x180035070  mov     [rsp+88h+var_58], rcx
0x180035075  lea     rcx, aBaseNtsetupSet_2; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18003507c  mov     [rsp+88h+var_60], rcx
0x180035081  mov     [rsp+88h+var_68], 67h ; 'g'
0x180035089  xor     r9d, r9d
0x18003508c  lea     r8, aD_0; "D"
0x180035093  xor     edx, edx
0x180035095  mov     rcx, rax
0x180035098  call    cs:__imp_WdsSetupLogMessageW
0x18003509e  mov     rax, [rbx]
0x1800350a1  mov     edx, 1
0x1800350a6  mov     rcx, rbx
0x1800350a9  mov     rax, [rax]
0x1800350ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350b1  nop
0x1800350b2  mov     rax, 0
0x1800350bc  add     rsp, 60h
0x1800350c0  pop     r14
0x1800350c2  pop     rdi
0x1800350c3  pop     rsi
0x1800350c4  pop     rbp
0x1800350c5  pop     rbx
0x1800350c6  retn
```
