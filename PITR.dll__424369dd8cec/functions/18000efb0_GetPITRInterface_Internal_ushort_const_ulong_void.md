# GetPITRInterface_Internal(ushort const *,ulong,void * *)

- ea: `0x18000efb0`
- end: `0x18000f084`
- name: `?GetPITRInterface_Internal@@YAJPEBGKPEAPEAX@Z`
- size: `212`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, CPITRBase **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800044f4`
- `0x180009e04`
- `0x18000efb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efcc`
- `WDSCORE!CurrentIP` at `0x18000efd4`
- `WDSCORE!CurrentIP` at `0x18000efd4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f03a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f03a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f04c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000f04c`

## string_xrefs

- `0x18000f017`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`

## pseudocode

```c
__int64 __fastcall GetPITRInterface_Internal(const unsigned __int16 *a1, int a2, CPITRBase **a3)
{
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  unsigned int v9; // esi
  CPITRBase *v10; // rax
  CPITRBase *v11; // rax

  if ( a2 == 1 )
  {
    v9 = 0;
    v10 = (CPITRBase *)UnBCL::Object::operator new(0x70u);
    if ( v10 )
      v11 = CPITRBase::CPITRBase(v10, a1);
    else
      v11 = 0;
    *a3 = v11;
  }
  else
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           0x2000000u,
           "GetPITRInterface: Found version mismatch: %d (internal) vs %d (caller).",
           1,
           a2);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      1395,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"GetPITRInterface_Internal",
      v7,
      LastError,
      0,
      0);
    return (unsigned int)-2147023590;
  }
  return v9;
}

```

## disassembly

```asm
0x18000efb0  mov     [rsp+arg_0], rbx
0x18000efb5  mov     [rsp+arg_8], rsi
0x18000efba  push    rdi
0x18000efbb  sub     rsp, 60h
0x18000efbf  mov     rbx, r8
0x18000efc2  mov     esi, edx
0x18000efc4  mov     rdi, rcx
0x18000efc7  cmp     edx, 1
0x18000efca  jz      short loc_18000F047
0x18000efcc  call    cs:__imp_GetLastError
0x18000efd2  mov     edi, eax
0x18000efd4  call    cs:__imp_CurrentIP
0x18000efda  mov     rbx, rax
0x18000efdd  mov     r9d, esi
0x18000efe0  mov     r8d, 1
0x18000efe6  lea     rdx, aGetpitrinterfa_0; "GetPITRInterface: Found version mismatc"...
0x18000efed  mov     ecx, 2000000h; unsigned int
0x18000eff2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000eff7  xor     esi, esi
0x18000eff9  mov     [rsp+68h+var_18], esi
0x18000effd  mov     [rsp+68h+var_20], rsi
0x18000f002  mov     [rsp+68h+var_28], edi
0x18000f006  mov     [rsp+68h+var_30], rbx
0x18000f00b  lea     rcx, aGetpitrinterfa_1; "GetPITRInterface_Internal"
0x18000f012  mov     [rsp+68h+var_38], rcx
0x18000f017  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000f01e  mov     [rsp+68h+var_40], rcx
0x18000f023  mov     [rsp+68h+var_48], 573h
0x18000f02b  xor     r9d, r9d
0x18000f02e  lea     r8, aD; "D"
0x18000f035  xor     edx, edx
0x18000f037  mov     rcx, rax
0x18000f03a  call    cs:__imp_WdsSetupLogMessageW
0x18000f040  mov     esi, 8007051Ah
0x18000f045  jmp     short loc_18000F072
0x18000f047  xor     esi, esi
0x18000f049  lea     ecx, [rsi+70h]
0x18000f04c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000f052  mov     [rsp+68h+arg_18], rax
0x18000f05a  test    rax, rax
0x18000f05d  jz      short loc_18000F06C
0x18000f05f  mov     rdx, rdi; unsigned __int16 *
0x18000f062  mov     rcx, rax; this
0x18000f065  call    ??0CPITRBase@@QEAA@PEBG@Z; CPITRBase::CPITRBase(ushort const *)
0x18000f06a  jmp     short loc_18000F06F
0x18000f06c  mov     rax, rsi
0x18000f06f  mov     [rbx], rax
0x18000f072  mov     eax, esi
0x18000f074  mov     rbx, [rsp+68h+arg_0]
0x18000f079  mov     rsi, [rsp+68h+arg_8]
0x18000f07e  add     rsp, 60h
0x18000f082  pop     rdi
0x18000f083  retn
```
