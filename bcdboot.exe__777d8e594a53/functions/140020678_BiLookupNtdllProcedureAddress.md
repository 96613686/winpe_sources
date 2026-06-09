# BiLookupNtdllProcedureAddress

- ea: `0x140020678`
- end: `0x140020718`
- name: `BiLookupNtdllProcedureAddress`
- size: `160`
- prototype: `__int64 __fastcall(PCSZ SourceString, PVOID *)`
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001c14c`
- `0x14001f570`
- `0x14001fe24`
- `0x1400215cc`
- `0x1400218e4`
- `0x140023218`
- `0x140023448`
- `0x1400235bc`
- `0x140023824`
- `0x14002467c`
- `0x140024714`
- `0x14002483c`
- `0x140024a28`
- `0x140024b30`

## callees

- `0x140020678`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x1400206f3`
- `ntdll!LdrGetProcedureAddress` at `0x1400206f3`
- `ntdll!LdrGetDllHandle` at `0x1400206cb`
- `ntdll!LdrGetDllHandle` at `0x1400206cb`
- `ntdll!RtlInitAnsiString` at `0x1400206de`
- `ntdll!RtlInitAnsiString` at `0x1400206de`
- `ntdll!RtlInitUnicodeString` at `0x1400206b9`
- `ntdll!RtlInitUnicodeString` at `0x1400206b9`

## string_xrefs

- `0x1400206a3`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall BiLookupNtdllProcedureAddress(PCSZ SourceString, PVOID *a2)
{
  NTSTATUS v4; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-20h] BYREF
  _STRING Name; // [rsp+30h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+60h] [rbp+20h] BYREF
  PVOID ProcedureAddress; // [rsp+68h] [rbp+28h] BYREF

  ProcedureAddress = 0;
  DllHandle = 0;
  DestinationString = 0;
  Name = 0;
  RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
  v4 = LdrGetDllHandle(0, 0, &DestinationString, &DllHandle);
  if ( v4 >= 0 )
  {
    RtlInitAnsiString(&Name, SourceString);
    v4 = LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress);
    if ( v4 >= 0 )
      *a2 = ProcedureAddress;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140020678  mov     [rsp-8+arg_0], rbx
0x14002067d  mov     [rsp-8+arg_8], rdi
0x140020682  push    rbp
0x140020683  mov     rbp, rsp
0x140020686  sub     rsp, 40h
0x14002068a  mov     rbx, rdx
0x14002068d  mov     [rbp+ProcedureAddress], 0
0x140020695  mov     rdi, rcx
0x140020698  mov     [rbp+DllHandle], 0
0x1400206a0  xorps   xmm0, xmm0
0x1400206a3  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1400206aa  xorps   xmm1, xmm1
0x1400206ad  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400206b1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400206b5  movups  xmmword ptr [rbp+Name.Length], xmm1
0x1400206b9  call    cs:__imp_RtlInitUnicodeString
0x1400206bf  lea     r9, [rbp+DllHandle]; DllHandle
0x1400206c3  xor     edx, edx; DllCharacteristics
0x1400206c5  lea     r8, [rbp+DestinationString]; DllName
0x1400206c9  xor     ecx, ecx; DllPath
0x1400206cb  call    cs:__imp_LdrGetDllHandle
0x1400206d1  mov     ecx, eax
0x1400206d3  test    eax, eax
0x1400206d5  js      short loc_140020706
0x1400206d7  mov     rdx, rdi; SourceString
0x1400206da  lea     rcx, [rbp+Name]; DestinationString
0x1400206de  call    cs:__imp_RtlInitAnsiString
0x1400206e4  mov     rcx, [rbp+DllHandle]; BaseAddress
0x1400206e8  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x1400206ec  xor     r8d, r8d; Ordinal
0x1400206ef  lea     rdx, [rbp+Name]; Name
0x1400206f3  call    cs:__imp_LdrGetProcedureAddress
0x1400206f9  mov     ecx, eax
0x1400206fb  test    eax, eax
0x1400206fd  js      short loc_140020706
0x1400206ff  mov     rax, [rbp+ProcedureAddress]
0x140020703  mov     [rbx], rax
0x140020706  mov     rbx, [rsp+40h+arg_0]
0x14002070b  mov     eax, ecx
0x14002070d  mov     rdi, [rsp+40h+arg_8]
0x140020712  add     rsp, 40h
0x140020716  pop     rbp
0x140020717  retn
```
