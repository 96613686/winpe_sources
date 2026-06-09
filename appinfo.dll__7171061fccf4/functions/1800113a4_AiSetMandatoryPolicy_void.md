# AiSetMandatoryPolicy(void *)

- ea: `0x1800113a4`
- end: `0x18001140b`
- name: `?AiSetMandatoryPolicy@@YAKPEAX@Z`
- size: `103`
- prototype: `ULONG __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d8fc`
- `0x180040d64`

## callees

- `0x1800113a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800113ff`
- `ntdll!RtlNtStatusToDosError` at `0x1800113ff`
- `ntdll!NtQueryInformationToken` at `0x1800113d6`
- `ntdll!NtQueryInformationToken` at `0x1800113d6`
- `ntdll!NtSetInformationToken` at `0x1800113f7`
- `ntdll!NtSetInformationToken` at `0x1800113f7`

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
0x1800113a4  push    rbx
0x1800113a6  sub     rsp, 30h
0x1800113aa  mov     r9d, 4; TokenInformationLength
0x1800113b0  mov     [rsp+38h+TokenInformation], 0
0x1800113b8  lea     rax, [rsp+38h+arg_10]
0x1800113bd  mov     [rsp+38h+arg_10], 0
0x1800113c5  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800113ca  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800113cf  mov     rbx, rcx
0x1800113d2  lea     edx, [r9+17h]; TokenInformationClass
0x1800113d6  call    cs:__imp_NtQueryInformationToken
0x1800113dc  test    eax, eax
0x1800113de  js      short loc_1800113FD
0x1800113e0  and     [rsp+38h+TokenInformation], 0FFFFFFFDh
0x1800113e5  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800113ea  mov     r9d, 4; TokenInformationLength
0x1800113f0  mov     rcx, rbx; TokenHandle
0x1800113f3  lea     edx, [r9+17h]; TokenInformationClass
0x1800113f7  call    cs:__imp_NtSetInformationToken
0x1800113fd  mov     ecx, eax; Status
0x1800113ff  call    cs:__imp_RtlNtStatusToDosError
0x180011405  add     rsp, 30h
0x180011409  pop     rbx
0x18001140a  retn
```
