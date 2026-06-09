# LUAIsElevatedToken

- ea: `0x18007abf8`
- end: `0x18007acab`
- name: `LUAIsElevatedToken`
- size: `179`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18007acb4`

## callees

- `0x18007abf8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18007ac45`
- `ntdll!NtQueryInformationToken` at `0x18007ac85`
- `ntdll!NtQueryInformationToken` at `0x18007ac45`
- `ntdll!NtQueryInformationToken` at `0x18007ac85`

## pseudocode

```c
NTSTATUS __fastcall LUAIsElevatedToken(HANDLE TokenHandle, _DWORD *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  int v9; // [rsp+68h] [rbp+20h] BYREF

  ReturnLength = 0;
  v9 = 0;
  TokenInformation = 1;
  *a3 = 1;
  *a2 = 0;
  result = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( result >= 0 )
  {
    if ( TokenInformation == 2
      || TokenInformation == 1
      && (*a3 = 0, result = NtQueryInformationToken(TokenHandle, TokenElevation, &v9, 4u, &ReturnLength), result >= 0)
      && v9 )
    {
      *a2 = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007abf8  mov     rax, rsp
0x18007abfb  push    rbx
0x18007abfc  push    rsi
0x18007abfd  push    rdi
0x18007abfe  sub     rsp, 30h
0x18007ac02  mov     r9d, 4; TokenInformationLength
0x18007ac08  mov     dword ptr [rax+18h], 0
0x18007ac0f  mov     dword ptr [rax+20h], 0
0x18007ac16  mov     rdi, r8
0x18007ac19  mov     dword ptr [rax+10h], 1
0x18007ac20  lea     rax, [rax+18h]
0x18007ac24  mov     rbx, rdx
0x18007ac27  mov     dword ptr [r8], 1
0x18007ac2e  mov     dword ptr [rdx], 0
0x18007ac34  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18007ac39  lea     edx, [r9+0Eh]; TokenInformationClass
0x18007ac3d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18007ac42  mov     rsi, rcx
0x18007ac45  call    cs:__imp_NtQueryInformationToken
0x18007ac4c  nop     dword ptr [rax+rax+00h]
0x18007ac51  test    eax, eax
0x18007ac53  js      short loc_18007ACA2
0x18007ac55  cmp     [rsp+48h+TokenInformation], 2
0x18007ac5a  jz      short loc_18007AC9C
0x18007ac5c  cmp     [rsp+48h+TokenInformation], 1
0x18007ac61  jnz     short loc_18007ACA2
0x18007ac63  mov     r9d, 4; TokenInformationLength
0x18007ac69  mov     dword ptr [rdi], 0
0x18007ac6f  lea     rax, [rsp+48h+arg_10]
0x18007ac74  mov     rcx, rsi; TokenHandle
0x18007ac77  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18007ac7c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18007ac81  lea     edx, [r9+10h]; TokenInformationClass
0x18007ac85  call    cs:__imp_NtQueryInformationToken
0x18007ac8c  nop     dword ptr [rax+rax+00h]
0x18007ac91  test    eax, eax
0x18007ac93  js      short loc_18007ACA2
0x18007ac95  cmp     [rsp+48h+arg_18], 0
0x18007ac9a  jz      short loc_18007ACA2
0x18007ac9c  mov     dword ptr [rbx], 1
0x18007aca2  add     rsp, 30h
0x18007aca6  pop     rdi
0x18007aca7  pop     rsi
0x18007aca8  pop     rbx
0x18007aca9  retn
```
