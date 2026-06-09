# WorkflowSessionCommon::ResetSpoolFile(void)

- ea: `0x1800242fc`
- end: `0x1800243bd`
- name: `?ResetSpoolFile@WorkflowSessionCommon@@QEAAJXZ`
- size: `193`
- prototype: `__int64 __fastcall(WorkflowSessionCommon *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003d90c`

## callees

- `0x180023664`
- `0x1800242fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180024311`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002432c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180024347`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180024311`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002432c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180024347`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002435a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002435a`

## string_xrefs

- `0x180024377`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180024388`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180024399`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x1800243aa`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`

## pseudocode

```c
__int64 __fastcall WorkflowSessionCommon::ResetSpoolFile(HANDLE *this)
{
  const char *v2; // r9
  const char *v3; // r9
  const char *v4; // r9
  const char *v5; // r9
  const char *v7; // r9
  __int64 *v8; // rdx
  __int64 v9; // [rsp+0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+30h] [rbp+8h]

  if ( !SetFilePointerEx(this[2], 0, 0, 0) )
  {
    try
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
        v2);
    }
    catch ( ... )
    {
      v8 = &v9;
      *((_DWORD *)v8 + 12) = wil::details::in1diag3::Return_CaughtException(
                               (wil::details::in1diag3 *)v8[5],
                               (void *)0x12C,
                               (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
                               v7);
      return v11;
    }
  }
  if ( !SetFilePointerEx(this[3], 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
      v3);
  if ( !SetFilePointerEx(this[4], 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
      v4);
  if ( !SetEndOfFile(this[2]) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
      v5);
  return 0;
}

```

## disassembly

```asm
0x1800242fc  push    rbx
0x1800242fe  sub     rsp, 20h
0x180024302  mov     rbx, rcx
0x180024305  xor     edx, edx; liDistanceToMove
0x180024307  xor     r9d, r9d; dwMoveMethod
0x18002430a  xor     r8d, r8d; lpNewFilePointer
0x18002430d  mov     rcx, [rcx+10h]; hFile
0x180024311  call    cs:__imp_SetFilePointerEx
0x180024317  mov     rcx, [rsp+28h]; this
0x18002431c  test    eax, eax
0x18002431e  jz      short loc_180024377
0x180024320  xor     edx, edx; liDistanceToMove
0x180024322  xor     r9d, r9d; dwMoveMethod
0x180024325  xor     r8d, r8d; lpNewFilePointer
0x180024328  mov     rcx, [rbx+18h]; hFile
0x18002432c  call    cs:__imp_SetFilePointerEx
0x180024332  mov     rcx, [rsp+28h]; this
0x180024337  test    eax, eax
0x180024339  jz      short loc_180024388
0x18002433b  xor     edx, edx; liDistanceToMove
0x18002433d  xor     r9d, r9d; dwMoveMethod
0x180024340  xor     r8d, r8d; lpNewFilePointer
0x180024343  mov     rcx, [rbx+20h]; hFile
0x180024347  call    cs:__imp_SetFilePointerEx
0x18002434d  mov     rcx, [rsp+28h]; this
0x180024352  test    eax, eax
0x180024354  jz      short loc_180024399
0x180024356  mov     rcx, [rbx+10h]; hFile
0x18002435a  call    cs:__imp_SetEndOfFile
0x180024360  mov     rcx, [rsp+28h]; this
0x180024365  test    eax, eax
0x180024367  jz      short loc_1800243AA
0x180024369  xor     eax, eax
0x18002436b  jmp     short loc_180024371
0x18002436d  mov     eax, [rsp+28h+arg_0]
0x180024371  add     rsp, 20h
0x180024375  pop     rbx
0x180024376  retn
0x180024377  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x18002437e  mov     edx, 126h; void *
0x180024383  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180024388  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x18002438f  mov     edx, 127h; void *
0x180024394  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180024399  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x1800243a0  mov     edx, 128h; void *
0x1800243a5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800243aa  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x1800243b1  mov     edx, 129h; void *
0x1800243b6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
