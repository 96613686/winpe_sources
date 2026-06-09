# WppLoadTracingSupport

- ea: `0x18000a490`
- end: `0x18000a5d0`
- name: `WppLoadTracingSupport`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013078`

## callees

- `0x180001fb0`
- `0x18000a490`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a4c2`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a4f0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a51e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a579`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a5ac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a4c2`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a4f0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a51e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a579`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a5ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a4b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a4e0`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a50e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a569`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a59c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a4b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a4e0`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a50e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a569`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a59c`

## pseudocode

```c
PVOID WppLoadTracingSupport()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v2; // [rsp+50h] [rbp+10h] BYREF

  v2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"PsGetVersion");
  pfnWppGetVersion = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"WmiTraceMessage");
  pfnWppTraceMessage = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"WmiQueryTraceInformation");
  pfnWppQueryTraceInformation = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  result = pfnWppGetVersion;
  WPPTraceSuite = 2;
  if ( pfnWppGetVersion )
    result = (PVOID)pfnWppGetVersion(&v2, 0, 0, 0);
  if ( v2 >= 6 )
  {
    RtlInitUnicodeString(&DestinationString, L"EtwRegisterClassicProvider");
    result = MmGetSystemRoutineAddress(&DestinationString);
    pfnEtwRegisterClassicProvider = (__int64)result;
    if ( result )
    {
      RtlInitUnicodeString(&DestinationString, L"EtwUnregister");
      result = MmGetSystemRoutineAddress(&DestinationString);
      pfnEtwUnregister = (__int64)result;
      WPPTraceSuite = 4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a490  push    rbp
0x18000a492  mov     rbp, rsp
0x18000a495  sub     rsp, 40h
0x18000a499  xorps   xmm0, xmm0
0x18000a49c  mov     [rbp+arg_0], 0
0x18000a4a3  lea     rdx, aPsgetversion; "PsGetVersion"
0x18000a4aa  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a4ae  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000a4b2  call    cs:__imp_RtlInitUnicodeString
0x18000a4b9  nop     dword ptr [rax+rax+00h]
0x18000a4be  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x18000a4c2  call    cs:__imp_MmGetSystemRoutineAddress
0x18000a4c9  nop     dword ptr [rax+rax+00h]
0x18000a4ce  lea     rdx, aWmitracemessag; "WmiTraceMessage"
0x18000a4d5  mov     cs:pfnWppGetVersion, rax
0x18000a4dc  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a4e0  call    cs:__imp_RtlInitUnicodeString
0x18000a4e7  nop     dword ptr [rax+rax+00h]
0x18000a4ec  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x18000a4f0  call    cs:__imp_MmGetSystemRoutineAddress
0x18000a4f7  nop     dword ptr [rax+rax+00h]
0x18000a4fc  lea     rdx, aWmiquerytracei; "WmiQueryTraceInformation"
0x18000a503  mov     cs:pfnWppTraceMessage, rax
0x18000a50a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a50e  call    cs:__imp_RtlInitUnicodeString
0x18000a515  nop     dword ptr [rax+rax+00h]
0x18000a51a  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x18000a51e  call    cs:__imp_MmGetSystemRoutineAddress
0x18000a525  nop     dword ptr [rax+rax+00h]
0x18000a52a  mov     cs:pfnWppQueryTraceInformation, rax
0x18000a531  mov     rax, cs:pfnWppGetVersion
0x18000a538  mov     cs:WPPTraceSuite, 2
0x18000a542  test    rax, rax
0x18000a545  jz      short loc_18000A558
0x18000a547  xor     r9d, r9d
0x18000a54a  lea     rcx, [rbp+arg_0]
0x18000a54e  xor     r8d, r8d
0x18000a551  xor     edx, edx
0x18000a553  call    _guard_dispatch_icall
0x18000a558  cmp     [rbp+arg_0], 6
0x18000a55c  jb      short loc_18000A5C9
0x18000a55e  lea     rdx, aEtwregistercla; "EtwRegisterClassicProvider"
0x18000a565  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a569  call    cs:__imp_RtlInitUnicodeString
0x18000a570  nop     dword ptr [rax+rax+00h]
0x18000a575  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x18000a579  call    cs:__imp_MmGetSystemRoutineAddress
0x18000a580  nop     dword ptr [rax+rax+00h]
0x18000a585  mov     cs:pfnEtwRegisterClassicProvider, rax
0x18000a58c  test    rax, rax
0x18000a58f  jz      short loc_18000A5C9
0x18000a591  lea     rdx, aEtwunregister; "EtwUnregister"
0x18000a598  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a59c  call    cs:__imp_RtlInitUnicodeString
0x18000a5a3  nop     dword ptr [rax+rax+00h]
0x18000a5a8  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x18000a5ac  call    cs:__imp_MmGetSystemRoutineAddress
0x18000a5b3  nop     dword ptr [rax+rax+00h]
0x18000a5b8  mov     cs:pfnEtwUnregister, rax
0x18000a5bf  mov     cs:WPPTraceSuite, 4
0x18000a5c9  add     rsp, 40h
0x18000a5cd  pop     rbp
0x18000a5ce  retn
```
