# WerpReinitializeKernelCrashDump

- ea: `0x180069c90`
- end: `0x180069d5f`
- name: `WerpReinitializeKernelCrashDump`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007a930`

## callees

- `0x18002ffc4`
- `0x18003db78`
- `0x180069c90`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180069cad`
- `ntdll!RtlAdjustPrivilege` at `0x180069d21`
- `ntdll!RtlAdjustPrivilege` at `0x180069cad`
- `ntdll!RtlAdjustPrivilege` at `0x180069d21`
- `ntdll!NtSetSystemInformation` at `0x180069ce3`
- `ntdll!NtSetSystemInformation` at `0x180069ce3`

## string_xrefs

- `0x180069cc8`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`
- `0x180069cfc`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`
- `0x180069d30`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`

## pseudocode

```c
__int64 WerpReinitializeKernelCrashDump()
{
  NTSTATUS v0; // eax
  int v1; // ebx
  __int64 v2; // rdx
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF

  OldValue = 0;
  v0 = RtlAdjustPrivilege(0x14u, 1u, 0, &OldValue);
  v1 = v0 | 0x10000000;
  if ( v0 < 0 )
  {
    v2 = 9391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\werpapi.cpp",
      (const char *)(unsigned int)v1,
      v7);
    return (unsigned int)v1;
  }
  v4 = NtSetSystemInformation(SystemCrashDumpStateInformation, 0, 0);
  v5 = v4;
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24B6,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\werpapi.cpp",
      (const char *)(v4 | 0x10000000u),
      v7);
  if ( !OldValue )
  {
    v6 = RtlAdjustPrivilege(0x14u, 0, 0, &OldValue) | 0x10000000;
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x24C2,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\werpapi.cpp",
        (const char *)(unsigned int)v6,
        v7);
  }
  v1 = v5 | 0x10000000;
  if ( v1 < 0 )
  {
    v2 = 9413;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180069c90  mov     [rsp+arg_8], rbx
0x180069c95  push    rdi; int
0x180069c96  sub     rsp, 20h
0x180069c9a  xor     r8d, r8d; ForThread
0x180069c9d  mov     [rsp+28h+OldValue], 0
0x180069ca2  lea     r9, [rsp+28h+OldValue]; OldValue
0x180069ca7  mov     dl, 1; NewValue
0x180069ca9  lea     ecx, [r8+14h]; Privilege
0x180069cad  call    cs:__imp_RtlAdjustPrivilege
0x180069cb3  mov     ebx, eax
0x180069cb5  mov     edi, 10000000h
0x180069cba  or      ebx, edi
0x180069cbc  jge     short loc_180069CDB
0x180069cbe  mov     edx, 24AFh; void *
0x180069cc3  mov     rcx, [rsp+28h]; this
0x180069cc8  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x180069ccf  mov     r9d, ebx; char *
0x180069cd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069cd7  mov     eax, ebx
0x180069cd9  jmp     short loc_180069D54
0x180069cdb  xor     edx, edx; SystemInformation
0x180069cdd  xor     r8d, r8d; SystemInformationLength
0x180069ce0  lea     ecx, [rdx+22h]; SystemInformationClass
0x180069ce3  call    cs:__imp_NtSetSystemInformation
0x180069ce9  mov     ebx, eax
0x180069ceb  test    eax, eax
0x180069ced  jns     short loc_180069D0D
0x180069cef  mov     r9d, eax
0x180069cf2  or      r9d, edi; char *
0x180069cf5  jge     short loc_180069D0D
0x180069cf7  mov     rcx, [rsp+28h]; this
0x180069cfc  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x180069d03  mov     edx, 24B6h; void *
0x180069d08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180069d0d  cmp     [rsp+28h+OldValue], 0
0x180069d12  jnz     short loc_180069D44
0x180069d14  xor     edx, edx; NewValue
0x180069d16  lea     r9, [rsp+28h+OldValue]; OldValue
0x180069d1b  xor     r8d, r8d; ForThread
0x180069d1e  lea     ecx, [rdx+14h]; Privilege
0x180069d21  call    cs:__imp_RtlAdjustPrivilege
0x180069d27  or      eax, edi
0x180069d29  jge     short loc_180069D44
0x180069d2b  mov     rcx, [rsp+28h]; this
0x180069d30  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x180069d37  mov     r9d, eax; char *
0x180069d3a  mov     edx, 24C2h; void *
0x180069d3f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180069d44  or      ebx, edi
0x180069d46  jge     short loc_180069D52
0x180069d48  mov     edx, 24C5h
0x180069d4d  jmp     loc_180069CC3
0x180069d52  xor     eax, eax
0x180069d54  mov     rbx, [rsp+28h+arg_8]
0x180069d59  add     rsp, 20h
0x180069d5d  pop     rdi
0x180069d5e  retn
```
