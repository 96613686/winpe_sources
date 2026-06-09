# LUAIsElevatedToken

- ea: `0x180014024`
- end: `0x1800140ca`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013f28`

## callees

- `0x180014024`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180014071`
- `ntdll!NtQueryInformationToken` at `0x1800140ab`
- `ntdll!NtQueryInformationToken` at `0x180014071`
- `ntdll!NtQueryInformationToken` at `0x1800140ab`

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
0x180014024  mov     rax, rsp
0x180014027  push    rbx
0x180014028  push    rsi
0x180014029  push    rdi
0x18001402a  sub     rsp, 30h
0x18001402e  mov     r9d, 4; TokenInformationLength
0x180014034  mov     dword ptr [rax+18h], 0
0x18001403b  mov     dword ptr [rax+20h], 0
0x180014042  mov     rdi, r8
0x180014045  mov     dword ptr [rax+10h], 1
0x18001404c  lea     rax, [rax+18h]
0x180014050  mov     rbx, rdx
0x180014053  mov     dword ptr [r8], 1
0x18001405a  mov     dword ptr [rdx], 0
0x180014060  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180014065  lea     edx, [r9+0Eh]; TokenInformationClass
0x180014069  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001406e  mov     rsi, rcx
0x180014071  call    cs:__imp_NtQueryInformationToken
0x180014077  test    eax, eax
0x180014079  js      short loc_1800140C2
0x18001407b  cmp     [rsp+48h+TokenInformation], 2
0x180014080  jz      short loc_1800140BC
0x180014082  cmp     [rsp+48h+TokenInformation], 1
0x180014087  jnz     short loc_1800140C2
0x180014089  mov     r9d, 4; TokenInformationLength
0x18001408f  mov     dword ptr [rdi], 0
0x180014095  lea     rax, [rsp+48h+arg_10]
0x18001409a  mov     rcx, rsi; TokenHandle
0x18001409d  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x1800140a2  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800140a7  lea     edx, [r9+10h]; TokenInformationClass
0x1800140ab  call    cs:__imp_NtQueryInformationToken
0x1800140b1  test    eax, eax
0x1800140b3  js      short loc_1800140C2
0x1800140b5  cmp     [rsp+48h+arg_18], 0
0x1800140ba  jz      short loc_1800140C2
0x1800140bc  mov     dword ptr [rbx], 1
0x1800140c2  add     rsp, 30h
0x1800140c6  pop     rdi
0x1800140c7  pop     rsi
0x1800140c8  pop     rbx
0x1800140c9  retn
```
