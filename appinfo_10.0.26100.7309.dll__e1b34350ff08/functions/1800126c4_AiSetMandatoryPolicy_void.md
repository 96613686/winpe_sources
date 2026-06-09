# AiSetMandatoryPolicy(void *)

- ea: `0x1800126c4`
- end: `0x180012738`
- name: `?AiSetMandatoryPolicy@@YAKPEAX@Z`
- size: `116`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180014da0`
- `0x18003e094`

## callees

- `0x1800126c4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180012725`
- `ntdll!RtlNtStatusToDosError` at `0x180012725`
- `ntdll!NtQueryInformationToken` at `0x1800126f0`
- `ntdll!NtQueryInformationToken` at `0x1800126f0`
- `ntdll!NtSetInformationToken` at `0x180012717`
- `ntdll!NtSetInformationToken` at `0x180012717`

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
0x1800126c4  push    rbx
0x1800126c6  sub     rsp, 30h
0x1800126ca  and     [rsp+38h+TokenInformation], 0
0x1800126cf  lea     rax, [rsp+38h+arg_10]
0x1800126d4  and     [rsp+38h+arg_10], 0
0x1800126d9  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800126de  mov     r9d, 4; TokenInformationLength
0x1800126e4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800126e9  mov     rbx, rcx
0x1800126ec  lea     edx, [r9+17h]; TokenInformationClass
0x1800126f0  call    cs:__imp_NtQueryInformationToken
0x1800126f7  nop     dword ptr [rax+rax+00h]
0x1800126fc  test    eax, eax
0x1800126fe  js      short loc_180012723
0x180012700  and     [rsp+38h+TokenInformation], 0FFFFFFFDh
0x180012705  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18001270a  mov     r9d, 4; TokenInformationLength
0x180012710  mov     rcx, rbx; TokenHandle
0x180012713  lea     edx, [r9+17h]; TokenInformationClass
0x180012717  call    cs:__imp_NtSetInformationToken
0x18001271e  nop     dword ptr [rax+rax+00h]
0x180012723  mov     ecx, eax; Status
0x180012725  call    cs:__imp_RtlNtStatusToDosError
0x18001272c  nop     dword ptr [rax+rax+00h]
0x180012731  add     rsp, 30h
0x180012735  pop     rbx
0x180012736  retn
```
