# LUAIsElevatedToken

- ea: `0x1800287ec`
- end: `0x180028892`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180028898`
- `0x1800289a8`

## callees

- `0x1800287ec`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180028839`
- `ntdll!NtQueryInformationToken` at `0x180028873`
- `ntdll!NtQueryInformationToken` at `0x180028839`
- `ntdll!NtQueryInformationToken` at `0x180028873`

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
0x1800287ec  mov     rax, rsp
0x1800287ef  push    rbx
0x1800287f0  push    rsi
0x1800287f1  push    rdi
0x1800287f2  sub     rsp, 30h
0x1800287f6  mov     r9d, 4; TokenInformationLength
0x1800287fc  mov     dword ptr [rax+18h], 0
0x180028803  mov     dword ptr [rax+20h], 0
0x18002880a  mov     rdi, r8
0x18002880d  mov     dword ptr [rax+10h], 1
0x180028814  lea     rax, [rax+18h]
0x180028818  mov     rbx, rdx
0x18002881b  mov     dword ptr [r8], 1
0x180028822  mov     dword ptr [rdx], 0
0x180028828  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18002882d  lea     edx, [r9+0Eh]; TokenInformationClass
0x180028831  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180028836  mov     rsi, rcx
0x180028839  call    cs:__imp_NtQueryInformationToken
0x18002883f  test    eax, eax
0x180028841  js      short loc_18002888A
0x180028843  cmp     [rsp+48h+TokenInformation], 2
0x180028848  jz      short loc_180028884
0x18002884a  cmp     [rsp+48h+TokenInformation], 1
0x18002884f  jnz     short loc_18002888A
0x180028851  mov     r9d, 4; TokenInformationLength
0x180028857  mov     dword ptr [rdi], 0
0x18002885d  lea     rax, [rsp+48h+arg_10]
0x180028862  mov     rcx, rsi; TokenHandle
0x180028865  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18002886a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002886f  lea     edx, [r9+10h]; TokenInformationClass
0x180028873  call    cs:__imp_NtQueryInformationToken
0x180028879  test    eax, eax
0x18002887b  js      short loc_18002888A
0x18002887d  cmp     [rsp+48h+arg_18], 0
0x180028882  jz      short loc_18002888A
0x180028884  mov     dword ptr [rbx], 1
0x18002888a  add     rsp, 30h
0x18002888e  pop     rdi
0x18002888f  pop     rsi
0x180028890  pop     rbx
0x180028891  retn
```
