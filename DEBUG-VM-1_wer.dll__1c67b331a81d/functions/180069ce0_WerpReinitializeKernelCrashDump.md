# WerpReinitializeKernelCrashDump

- ea: `0x180069ce0`
- end: `0x180069daf`
- name: `WerpReinitializeKernelCrashDump`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007a980`

## callees

- `0x18002ffc4`
- `0x18003db78`
- `0x180069ce0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180069cfd`
- `ntdll!RtlAdjustPrivilege` at `0x180069d71`
- `ntdll!RtlAdjustPrivilege` at `0x180069cfd`
- `ntdll!RtlAdjustPrivilege` at `0x180069d71`
- `ntdll!NtSetSystemInformation` at `0x180069d33`
- `ntdll!NtSetSystemInformation` at `0x180069d33`

## string_xrefs

- `0x180069d18`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`
- `0x180069d4c`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`
- `0x180069d80`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`

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
0x180069ce0  mov     [rsp+arg_8], rbx
0x180069ce5  push    rdi; int
0x180069ce6  sub     rsp, 20h
0x180069cea  xor     r8d, r8d; ForThread
0x180069ced  mov     [rsp+28h+OldValue], 0
0x180069cf2  lea     r9, [rsp+28h+OldValue]; OldValue
0x180069cf7  mov     dl, 1; NewValue
0x180069cf9  lea     ecx, [r8+14h]; Privilege
0x180069cfd  call    cs:__imp_RtlAdjustPrivilege
0x180069d03  mov     ebx, eax
0x180069d05  mov     edi, 10000000h
0x180069d0a  or      ebx, edi
0x180069d0c  jge     short loc_180069D2B
0x180069d0e  mov     edx, 24AFh; void *
0x180069d13  mov     rcx, [rsp+28h]; this
0x180069d18  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x180069d1f  mov     r9d, ebx; char *
0x180069d22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069d27  mov     eax, ebx
0x180069d29  jmp     short loc_180069DA4
0x180069d2b  xor     edx, edx; SystemInformation
0x180069d2d  xor     r8d, r8d; SystemInformationLength
0x180069d30  lea     ecx, [rdx+22h]; SystemInformationClass
0x180069d33  call    cs:__imp_NtSetSystemInformation
0x180069d39  mov     ebx, eax
0x180069d3b  test    eax, eax
0x180069d3d  jns     short loc_180069D5D
0x180069d3f  mov     r9d, eax
0x180069d42  or      r9d, edi; char *
0x180069d45  jge     short loc_180069D5D
0x180069d47  mov     rcx, [rsp+28h]; this
0x180069d4c  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x180069d53  mov     edx, 24B6h; void *
0x180069d58  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180069d5d  cmp     [rsp+28h+OldValue], 0
0x180069d62  jnz     short loc_180069D94
0x180069d64  xor     edx, edx; NewValue
0x180069d66  lea     r9, [rsp+28h+OldValue]; OldValue
0x180069d6b  xor     r8d, r8d; ForThread
0x180069d6e  lea     ecx, [rdx+14h]; Privilege
0x180069d71  call    cs:__imp_RtlAdjustPrivilege
0x180069d77  or      eax, edi
0x180069d79  jge     short loc_180069D94
0x180069d7b  mov     rcx, [rsp+28h]; this
0x180069d80  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x180069d87  mov     r9d, eax; char *
0x180069d8a  mov     edx, 24C2h; void *
0x180069d8f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180069d94  or      ebx, edi
0x180069d96  jge     short loc_180069DA2
0x180069d98  mov     edx, 24C5h
0x180069d9d  jmp     loc_180069D13
0x180069da2  xor     eax, eax
0x180069da4  mov     rbx, [rsp+28h+arg_8]
0x180069da9  add     rsp, 20h
0x180069dad  pop     rdi
0x180069dae  retn
```
