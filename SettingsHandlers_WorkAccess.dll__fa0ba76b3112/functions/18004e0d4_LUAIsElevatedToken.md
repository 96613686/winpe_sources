# LUAIsElevatedToken

- ea: `0x18004e0d4`
- end: `0x18004e187`
- name: `LUAIsElevatedToken`
- size: `179`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004e190`
- `0x18004e2d4`

## callees

- `0x18004e0d4`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18004e121`
- `ntdll!NtQueryInformationToken` at `0x18004e161`
- `ntdll!NtQueryInformationToken` at `0x18004e121`
- `ntdll!NtQueryInformationToken` at `0x18004e161`

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
0x18004e0d4  mov     rax, rsp
0x18004e0d7  push    rbx
0x18004e0d8  push    rsi
0x18004e0d9  push    rdi
0x18004e0da  sub     rsp, 30h
0x18004e0de  mov     r9d, 4; TokenInformationLength
0x18004e0e4  mov     dword ptr [rax+18h], 0
0x18004e0eb  mov     dword ptr [rax+20h], 0
0x18004e0f2  mov     rdi, r8
0x18004e0f5  mov     dword ptr [rax+10h], 1
0x18004e0fc  lea     rax, [rax+18h]
0x18004e100  mov     rbx, rdx
0x18004e103  mov     dword ptr [r8], 1
0x18004e10a  mov     dword ptr [rdx], 0
0x18004e110  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18004e115  lea     edx, [r9+0Eh]; TokenInformationClass
0x18004e119  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18004e11e  mov     rsi, rcx
0x18004e121  call    cs:__imp_NtQueryInformationToken
0x18004e128  nop     dword ptr [rax+rax+00h]
0x18004e12d  test    eax, eax
0x18004e12f  js      short loc_18004E17E
0x18004e131  cmp     [rsp+48h+TokenInformation], 2
0x18004e136  jz      short loc_18004E178
0x18004e138  cmp     [rsp+48h+TokenInformation], 1
0x18004e13d  jnz     short loc_18004E17E
0x18004e13f  mov     r9d, 4; TokenInformationLength
0x18004e145  mov     dword ptr [rdi], 0
0x18004e14b  lea     rax, [rsp+48h+arg_10]
0x18004e150  mov     rcx, rsi; TokenHandle
0x18004e153  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18004e158  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18004e15d  lea     edx, [r9+10h]; TokenInformationClass
0x18004e161  call    cs:__imp_NtQueryInformationToken
0x18004e168  nop     dword ptr [rax+rax+00h]
0x18004e16d  test    eax, eax
0x18004e16f  js      short loc_18004E17E
0x18004e171  cmp     [rsp+48h+arg_18], 0
0x18004e176  jz      short loc_18004E17E
0x18004e178  mov     dword ptr [rbx], 1
0x18004e17e  add     rsp, 30h
0x18004e182  pop     rdi
0x18004e183  pop     rsi
0x18004e184  pop     rbx
0x18004e185  retn
```
