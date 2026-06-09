# Wow64DetermineEnvironment

- ea: `0x180064d4c`
- end: `0x180064ec6`
- name: `Wow64DetermineEnvironment`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180064cd4`

## callees

- `0x180064d4c`
- `0x180066010`

## import_xrefs

- `ntdll!RtlInitString` at `0x180064db8`
- `ntdll!RtlInitString` at `0x180064e5f`
- `ntdll!RtlInitString` at `0x180064db8`
- `ntdll!RtlInitString` at `0x180064e5f`
- `ntdll!LdrGetProcedureAddress` at `0x180064dcd`
- `ntdll!LdrGetProcedureAddress` at `0x180064e74`
- `ntdll!LdrGetProcedureAddress` at `0x180064dcd`
- `ntdll!LdrGetProcedureAddress` at `0x180064e74`
- `ntdll!LdrGetDllHandle` at `0x180064da7`
- `ntdll!LdrGetDllHandle` at `0x180064da7`
- `ntdll!RtlInitUnicodeString` at `0x180064d95`
- `ntdll!RtlInitUnicodeString` at `0x180064d95`

## string_xrefs

- `0x180064d8a`: `ntdll.dll`

## pseudocode

```c
void Wow64DetermineEnvironment()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  struct _STRING Name; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  char v6; // [rsp+60h] [rbp+18h] BYREF
  PVOID DllHandle; // [rsp+68h] [rbp+20h] BYREF
  PVOID v8; // [rsp+70h] [rbp+28h] BYREF
  PVOID ProcedureAddress; // [rsp+78h] [rbp+30h] BYREF

  DestinationString = 0;
  v6 = 0;
  Name = 0;
  DllHandle = 0;
  ProcedureAddress = 0;
  v8 = 0;
  if ( CachedWow64ProcessEnvironment )
    return;
  RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
  LdrGetDllHandle(0, 0, &DestinationString, &DllHandle);
  RtlInitString(&Name, "RtlWow64GetCurrentMachine");
  if ( LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress) < 0 )
  {
    CachedWow64ProcessEnvironment = 1;
    return;
  }
  if ( !NtCurrentTeb()->SpareUlong0 )
  {
    CachedWow64ProcessEnvironment = 2;
LABEL_9:
    RtlInitString(&Name, "RtlWow64IsWowGuestMachineSupported");
    if ( LdrGetProcedureAddress(DllHandle, &Name, 0, &v8) >= 0
      && ((int (__fastcall *)(__int64, char *))v8)(332, &v6) >= 0
      && !v6
      && ((int (__fastcall *)(__int64, char *))v8)(452, &v6) >= 0 )
    {
      if ( v6 )
        DefaultGuestMachine = 452;
    }
    return;
  }
  if ( (NtCurrentTeb()->SpareUlong0 & 0x80000000) != 0 )
  {
    CachedWow64ProcessEnvironment = 4;
    CachedMachine = -31132;
    return;
  }
  CachedWow64ProcessEnvironment = 3;
  CachedMachine = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))ProcedureAddress)(v1, v0, v2, v3);
  if ( CachedWow64ProcessEnvironment == 2 )
    goto LABEL_9;
}

```

## disassembly

```asm
0x180064d4c  push    rbp
0x180064d4e  push    rdi
0x180064d4f  mov     rbp, rsp
0x180064d52  sub     rsp, 48h
0x180064d56  cmp     cs:CachedWow64ProcessEnvironment, 0
0x180064d5d  xorps   xmm0, xmm0
0x180064d60  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180064d64  mov     [rbp+arg_0], 0
0x180064d68  movups  xmmword ptr [rbp+Name.Length], xmm0
0x180064d6c  mov     [rbp+DllHandle], 0
0x180064d74  mov     [rbp+ProcedureAddress], 0
0x180064d7c  mov     [rbp+arg_10], 0
0x180064d84  jnz     loc_180064EBF
0x180064d8a  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180064d91  lea     rcx, [rbp+DestinationString]; DestinationString
0x180064d95  call    cs:__imp_RtlInitUnicodeString
0x180064d9b  lea     r9, [rbp+DllHandle]; DllHandle
0x180064d9f  xor     edx, edx; DllCharacteristics
0x180064da1  lea     r8, [rbp+DestinationString]; DllName
0x180064da5  xor     ecx, ecx; DllPath
0x180064da7  call    cs:__imp_LdrGetDllHandle
0x180064dad  lea     rdx, aRtlwow64getcur; "RtlWow64GetCurrentMachine"
0x180064db4  lea     rcx, [rbp+Name]; DestinationString
0x180064db8  call    cs:__imp_RtlInitString
0x180064dbe  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180064dc2  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x180064dc6  xor     r8d, r8d; Ordinal
0x180064dc9  lea     rdx, [rbp+Name]; Name
0x180064dcd  call    cs:__imp_LdrGetProcedureAddress
0x180064dd3  test    eax, eax
0x180064dd5  jns     short loc_180064DE6
0x180064dd7  mov     cs:CachedWow64ProcessEnvironment, 1
0x180064de1  jmp     loc_180064EBF
0x180064de6  mov     rax, gs:30h
0x180064def  cmp     dword ptr [rax+180Ch], 0
0x180064df6  jnz     short loc_180064E04
0x180064df8  mov     cs:CachedWow64ProcessEnvironment, 2
0x180064e02  jmp     short loc_180064E54
0x180064e04  mov     rax, gs:30h
0x180064e0d  cmp     dword ptr [rax+180Ch], 0
0x180064e14  jge     short loc_180064E31
0x180064e16  mov     eax, 8664h
0x180064e1b  mov     cs:CachedWow64ProcessEnvironment, 4
0x180064e25  mov     cs:CachedMachine, ax
0x180064e2c  jmp     loc_180064EBF
0x180064e31  mov     rax, [rbp+ProcedureAddress]
0x180064e35  mov     cs:CachedWow64ProcessEnvironment, 3
0x180064e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e44  cmp     cs:CachedWow64ProcessEnvironment, 2
0x180064e4b  mov     cs:CachedMachine, ax
0x180064e52  jnz     short loc_180064EBF
0x180064e54  lea     rdx, aRtlwow64iswowg; "RtlWow64IsWowGuestMachineSupported"
0x180064e5b  lea     rcx, [rbp+Name]; DestinationString
0x180064e5f  call    cs:__imp_RtlInitString
0x180064e65  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180064e69  lea     r9, [rbp+arg_10]; ProcedureAddress
0x180064e6d  xor     r8d, r8d; Ordinal
0x180064e70  lea     rdx, [rbp+Name]; Name
0x180064e74  call    cs:__imp_LdrGetProcedureAddress
0x180064e7a  test    eax, eax
0x180064e7c  js      short loc_180064EBF
0x180064e7e  mov     rax, [rbp+arg_10]
0x180064e82  lea     rdx, [rbp+arg_0]
0x180064e86  mov     ecx, 14Ch
0x180064e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e90  test    eax, eax
0x180064e92  js      short loc_180064EBF
0x180064e94  cmp     [rbp+arg_0], 0
0x180064e98  jnz     short loc_180064EBF
0x180064e9a  mov     rax, [rbp+arg_10]
0x180064e9e  lea     rdx, [rbp+arg_0]
0x180064ea2  mov     edi, 1C4h
0x180064ea7  mov     ecx, edi
0x180064ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064eae  test    eax, eax
0x180064eb0  js      short loc_180064EBF
0x180064eb2  cmp     [rbp+arg_0], 0
0x180064eb6  jz      short loc_180064EBF
0x180064eb8  mov     cs:DefaultGuestMachine, di
0x180064ebf  add     rsp, 48h
0x180064ec3  pop     rdi
0x180064ec4  pop     rbp
0x180064ec5  retn
```
