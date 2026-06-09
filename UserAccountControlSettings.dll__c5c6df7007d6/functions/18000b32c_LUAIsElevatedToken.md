# LUAIsElevatedToken

- ea: `0x18000b32c`
- end: `0x18000b3d2`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b3d8`

## callees

- `0x18000b32c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000b379`
- `ntdll!NtQueryInformationToken` at `0x18000b3b3`
- `ntdll!NtQueryInformationToken` at `0x18000b379`
- `ntdll!NtQueryInformationToken` at `0x18000b3b3`

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
0x18000b32c  mov     rax, rsp
0x18000b32f  push    rbx
0x18000b330  push    rsi
0x18000b331  push    rdi
0x18000b332  sub     rsp, 30h
0x18000b336  mov     r9d, 4; TokenInformationLength
0x18000b33c  mov     dword ptr [rax+18h], 0
0x18000b343  mov     dword ptr [rax+20h], 0
0x18000b34a  mov     rdi, r8
0x18000b34d  mov     dword ptr [rax+10h], 1
0x18000b354  lea     rax, [rax+18h]
0x18000b358  mov     rbx, rdx
0x18000b35b  mov     dword ptr [r8], 1
0x18000b362  mov     dword ptr [rdx], 0
0x18000b368  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18000b36d  lea     edx, [r9+0Eh]; TokenInformationClass
0x18000b371  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b376  mov     rsi, rcx
0x18000b379  call    cs:__imp_NtQueryInformationToken
0x18000b37f  test    eax, eax
0x18000b381  js      short loc_18000B3CA
0x18000b383  cmp     [rsp+48h+TokenInformation], 2
0x18000b388  jz      short loc_18000B3C4
0x18000b38a  cmp     [rsp+48h+TokenInformation], 1
0x18000b38f  jnz     short loc_18000B3CA
0x18000b391  mov     r9d, 4; TokenInformationLength
0x18000b397  mov     dword ptr [rdi], 0
0x18000b39d  lea     rax, [rsp+48h+arg_10]
0x18000b3a2  mov     rcx, rsi; TokenHandle
0x18000b3a5  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18000b3aa  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b3af  lea     edx, [r9+10h]; TokenInformationClass
0x18000b3b3  call    cs:__imp_NtQueryInformationToken
0x18000b3b9  test    eax, eax
0x18000b3bb  js      short loc_18000B3CA
0x18000b3bd  cmp     [rsp+48h+arg_18], 0
0x18000b3c2  jz      short loc_18000B3CA
0x18000b3c4  mov     dword ptr [rbx], 1
0x18000b3ca  add     rsp, 30h
0x18000b3ce  pop     rdi
0x18000b3cf  pop     rsi
0x18000b3d0  pop     rbx
0x18000b3d1  retn
```
