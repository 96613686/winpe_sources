# AiSetMandatoryPolicy(void *)

- ea: `0x180012584`
- end: `0x1800125f8`
- name: `?AiSetMandatoryPolicy@@YAKPEAX@Z`
- size: `116`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180014d40`
- `0x18003c4c4`

## callees

- `0x180012584`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800125e5`
- `ntdll!RtlNtStatusToDosError` at `0x1800125e5`
- `ntdll!NtQueryInformationToken` at `0x1800125b0`
- `ntdll!NtQueryInformationToken` at `0x1800125b0`
- `ntdll!NtSetInformationToken` at `0x1800125d7`
- `ntdll!NtSetInformationToken` at `0x1800125d7`

## pseudocode

```c
ULONG __fastcall AiSetMandatoryPolicy(HANDLE TokenHandle)
{
  int v2; // eax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  v2 = NtQueryInformationToken(TokenHandle, TokenMandatoryPolicy, &TokenInformation, 4u, &ReturnLength);
  if ( v2 >= 0 )
  {
    TokenInformation &= ~2u;
    v2 = NtSetInformationToken(TokenHandle, TokenMandatoryPolicy, &TokenInformation, 4u);
  }
  return RtlNtStatusToDosError(v2);
}

```

## disassembly

```asm
0x180012584  push    rbx
0x180012586  sub     rsp, 30h
0x18001258a  and     [rsp+38h+TokenInformation], 0
0x18001258f  lea     rax, [rsp+38h+arg_10]
0x180012594  and     [rsp+38h+arg_10], 0
0x180012599  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18001259e  mov     r9d, 4; TokenInformationLength
0x1800125a4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800125a9  mov     rbx, rcx
0x1800125ac  lea     edx, [r9+17h]; TokenInformationClass
0x1800125b0  call    cs:__imp_NtQueryInformationToken
0x1800125b7  nop     dword ptr [rax+rax+00h]
0x1800125bc  test    eax, eax
0x1800125be  js      short loc_1800125E3
0x1800125c0  and     [rsp+38h+TokenInformation], 0FFFFFFFDh
0x1800125c5  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800125ca  mov     r9d, 4; TokenInformationLength
0x1800125d0  mov     rcx, rbx; TokenHandle
0x1800125d3  lea     edx, [r9+17h]; TokenInformationClass
0x1800125d7  call    cs:__imp_NtSetInformationToken
0x1800125de  nop     dword ptr [rax+rax+00h]
0x1800125e3  mov     ecx, eax; Status
0x1800125e5  call    cs:__imp_RtlNtStatusToDosError
0x1800125ec  nop     dword ptr [rax+rax+00h]
0x1800125f1  add     rsp, 30h
0x1800125f5  pop     rbx
0x1800125f6  retn
```
