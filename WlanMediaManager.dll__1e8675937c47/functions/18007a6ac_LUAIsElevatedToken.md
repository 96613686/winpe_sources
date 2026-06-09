# LUAIsElevatedToken

- ea: `0x18007a6ac`
- end: `0x18007a752`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18007a758`
- `0x18007a868`

## callees

- `0x18007a6ac`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18007a6f9`
- `ntdll!NtQueryInformationToken` at `0x18007a733`
- `ntdll!NtQueryInformationToken` at `0x18007a6f9`
- `ntdll!NtQueryInformationToken` at `0x18007a733`

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
0x18007a6ac  mov     rax, rsp
0x18007a6af  push    rbx
0x18007a6b0  push    rsi
0x18007a6b1  push    rdi
0x18007a6b2  sub     rsp, 30h
0x18007a6b6  mov     r9d, 4; TokenInformationLength
0x18007a6bc  mov     dword ptr [rax+18h], 0
0x18007a6c3  mov     dword ptr [rax+20h], 0
0x18007a6ca  mov     rdi, r8
0x18007a6cd  mov     dword ptr [rax+10h], 1
0x18007a6d4  lea     rax, [rax+18h]
0x18007a6d8  mov     rbx, rdx
0x18007a6db  mov     dword ptr [r8], 1
0x18007a6e2  mov     dword ptr [rdx], 0
0x18007a6e8  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18007a6ed  lea     edx, [r9+0Eh]; TokenInformationClass
0x18007a6f1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18007a6f6  mov     rsi, rcx
0x18007a6f9  call    cs:__imp_NtQueryInformationToken
0x18007a6ff  test    eax, eax
0x18007a701  js      short loc_18007A74A
0x18007a703  cmp     [rsp+48h+TokenInformation], 2
0x18007a708  jz      short loc_18007A744
0x18007a70a  cmp     [rsp+48h+TokenInformation], 1
0x18007a70f  jnz     short loc_18007A74A
0x18007a711  mov     r9d, 4; TokenInformationLength
0x18007a717  mov     dword ptr [rdi], 0
0x18007a71d  lea     rax, [rsp+48h+arg_10]
0x18007a722  mov     rcx, rsi; TokenHandle
0x18007a725  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18007a72a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18007a72f  lea     edx, [r9+10h]; TokenInformationClass
0x18007a733  call    cs:__imp_NtQueryInformationToken
0x18007a739  test    eax, eax
0x18007a73b  js      short loc_18007A74A
0x18007a73d  cmp     [rsp+48h+arg_18], 0
0x18007a742  jz      short loc_18007A74A
0x18007a744  mov     dword ptr [rbx], 1
0x18007a74a  add     rsp, 30h
0x18007a74e  pop     rdi
0x18007a74f  pop     rsi
0x18007a750  pop     rbx
0x18007a751  retn
```
