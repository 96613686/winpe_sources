# Wow64DetermineEnvironment

- ea: `0x180071d24`
- end: `0x180071ec3`
- name: `Wow64DetermineEnvironment`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180071ca8`

## callees

- `0x180071d24`
- `0x180074010`

## import_xrefs

- `ntdll!RtlInitString` at `0x180071d9c`
- `ntdll!RtlInitString` at `0x180071e4f`
- `ntdll!RtlInitString` at `0x180071d9c`
- `ntdll!RtlInitString` at `0x180071e4f`
- `ntdll!LdrGetProcedureAddress` at `0x180071db7`
- `ntdll!LdrGetProcedureAddress` at `0x180071e6a`
- `ntdll!LdrGetProcedureAddress` at `0x180071db7`
- `ntdll!LdrGetProcedureAddress` at `0x180071e6a`
- `ntdll!LdrGetDllHandle` at `0x180071d85`
- `ntdll!LdrGetDllHandle` at `0x180071d85`
- `ntdll!RtlInitUnicodeString` at `0x180071d6d`
- `ntdll!RtlInitUnicodeString` at `0x180071d6d`

## string_xrefs

- `0x180071d62`: `ntdll.dll`

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
0x180071d24  push    rbp
0x180071d26  push    rdi
0x180071d27  mov     rbp, rsp
0x180071d2a  sub     rsp, 48h
0x180071d2e  cmp     cs:CachedWow64ProcessEnvironment, 0
0x180071d35  xorps   xmm0, xmm0
0x180071d38  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180071d3c  mov     [rbp+arg_0], 0
0x180071d40  movups  xmmword ptr [rbp+Name.Length], xmm0
0x180071d44  mov     [rbp+DllHandle], 0
0x180071d4c  mov     [rbp+ProcedureAddress], 0
0x180071d54  mov     [rbp+arg_10], 0
0x180071d5c  jnz     loc_180071EBB
0x180071d62  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180071d69  lea     rcx, [rbp+DestinationString]; DestinationString
0x180071d6d  call    cs:__imp_RtlInitUnicodeString
0x180071d74  nop     dword ptr [rax+rax+00h]
0x180071d79  lea     r9, [rbp+DllHandle]; DllHandle
0x180071d7d  xor     edx, edx; DllCharacteristics
0x180071d7f  lea     r8, [rbp+DestinationString]; DllName
0x180071d83  xor     ecx, ecx; DllPath
0x180071d85  call    cs:__imp_LdrGetDllHandle
0x180071d8c  nop     dword ptr [rax+rax+00h]
0x180071d91  lea     rdx, aRtlwow64getcur; "RtlWow64GetCurrentMachine"
0x180071d98  lea     rcx, [rbp+Name]; DestinationString
0x180071d9c  call    cs:__imp_RtlInitString
0x180071da3  nop     dword ptr [rax+rax+00h]
0x180071da8  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180071dac  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x180071db0  xor     r8d, r8d; Ordinal
0x180071db3  lea     rdx, [rbp+Name]; Name
0x180071db7  call    cs:__imp_LdrGetProcedureAddress
0x180071dbe  nop     dword ptr [rax+rax+00h]
0x180071dc3  test    eax, eax
0x180071dc5  jns     short loc_180071DD6
0x180071dc7  mov     cs:CachedWow64ProcessEnvironment, 1
0x180071dd1  jmp     loc_180071EBB
0x180071dd6  mov     rax, gs:30h
0x180071ddf  cmp     dword ptr [rax+180Ch], 0
0x180071de6  jnz     short loc_180071DF4
0x180071de8  mov     cs:CachedWow64ProcessEnvironment, 2
0x180071df2  jmp     short loc_180071E44
0x180071df4  mov     rax, gs:30h
0x180071dfd  cmp     dword ptr [rax+180Ch], 0
0x180071e04  jge     short loc_180071E21
0x180071e06  mov     eax, 8664h
0x180071e0b  mov     cs:CachedWow64ProcessEnvironment, 4
0x180071e15  mov     cs:CachedMachine, ax
0x180071e1c  jmp     loc_180071EBB
0x180071e21  mov     rax, [rbp+ProcedureAddress]
0x180071e25  mov     cs:CachedWow64ProcessEnvironment, 3
0x180071e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e34  cmp     cs:CachedWow64ProcessEnvironment, 2
0x180071e3b  mov     cs:CachedMachine, ax
0x180071e42  jnz     short loc_180071EBB
0x180071e44  lea     rdx, aRtlwow64iswowg; "RtlWow64IsWowGuestMachineSupported"
0x180071e4b  lea     rcx, [rbp+Name]; DestinationString
0x180071e4f  call    cs:__imp_RtlInitString
0x180071e56  nop     dword ptr [rax+rax+00h]
0x180071e5b  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180071e5f  lea     r9, [rbp+arg_10]; ProcedureAddress
0x180071e63  xor     r8d, r8d; Ordinal
0x180071e66  lea     rdx, [rbp+Name]; Name
0x180071e6a  call    cs:__imp_LdrGetProcedureAddress
0x180071e71  nop     dword ptr [rax+rax+00h]
0x180071e76  test    eax, eax
0x180071e78  js      short loc_180071EBB
0x180071e7a  mov     rax, [rbp+arg_10]
0x180071e7e  lea     rdx, [rbp+arg_0]
0x180071e82  mov     ecx, 14Ch
0x180071e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e8c  test    eax, eax
0x180071e8e  js      short loc_180071EBB
0x180071e90  cmp     [rbp+arg_0], 0
0x180071e94  jnz     short loc_180071EBB
0x180071e96  mov     rax, [rbp+arg_10]
0x180071e9a  lea     rdx, [rbp+arg_0]
0x180071e9e  mov     edi, 1C4h
0x180071ea3  mov     ecx, edi
0x180071ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071eaa  test    eax, eax
0x180071eac  js      short loc_180071EBB
0x180071eae  cmp     [rbp+arg_0], 0
0x180071eb2  jz      short loc_180071EBB
0x180071eb4  mov     cs:DefaultGuestMachine, di
0x180071ebb  add     rsp, 48h
0x180071ebf  pop     rdi
0x180071ec0  pop     rbp
0x180071ec1  retn
```
