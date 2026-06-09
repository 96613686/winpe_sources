# LUAIsElevatedToken

- ea: `0x180027388`
- end: `0x18002742e`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180027434`
- `0x180027544`

## callees

- `0x180027388`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800273d5`
- `ntdll!NtQueryInformationToken` at `0x18002740f`
- `ntdll!NtQueryInformationToken` at `0x1800273d5`
- `ntdll!NtQueryInformationToken` at `0x18002740f`

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
0x180027388  mov     rax, rsp
0x18002738b  push    rbx
0x18002738c  push    rsi
0x18002738d  push    rdi
0x18002738e  sub     rsp, 30h
0x180027392  mov     r9d, 4; TokenInformationLength
0x180027398  mov     dword ptr [rax+18h], 0
0x18002739f  mov     dword ptr [rax+20h], 0
0x1800273a6  mov     rdi, r8
0x1800273a9  mov     dword ptr [rax+10h], 1
0x1800273b0  lea     rax, [rax+18h]
0x1800273b4  mov     rbx, rdx
0x1800273b7  mov     dword ptr [r8], 1
0x1800273be  mov     dword ptr [rdx], 0
0x1800273c4  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1800273c9  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800273cd  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800273d2  mov     rsi, rcx
0x1800273d5  call    cs:__imp_NtQueryInformationToken
0x1800273db  test    eax, eax
0x1800273dd  js      short loc_180027426
0x1800273df  cmp     [rsp+48h+TokenInformation], 2
0x1800273e4  jz      short loc_180027420
0x1800273e6  cmp     [rsp+48h+TokenInformation], 1
0x1800273eb  jnz     short loc_180027426
0x1800273ed  mov     r9d, 4; TokenInformationLength
0x1800273f3  mov     dword ptr [rdi], 0
0x1800273f9  lea     rax, [rsp+48h+arg_10]
0x1800273fe  mov     rcx, rsi; TokenHandle
0x180027401  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x180027406  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002740b  lea     edx, [r9+10h]; TokenInformationClass
0x18002740f  call    cs:__imp_NtQueryInformationToken
0x180027415  test    eax, eax
0x180027417  js      short loc_180027426
0x180027419  cmp     [rsp+48h+arg_18], 0
0x18002741e  jz      short loc_180027426
0x180027420  mov     dword ptr [rbx], 1
0x180027426  add     rsp, 30h
0x18002742a  pop     rdi
0x18002742b  pop     rsi
0x18002742c  pop     rbx
0x18002742d  retn
```
