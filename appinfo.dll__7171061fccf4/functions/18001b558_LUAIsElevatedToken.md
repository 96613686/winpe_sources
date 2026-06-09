# LUAIsElevatedToken

- ea: `0x18001b558`
- end: `0x18001b5fe`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _DWORD *, _DWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180026ba0`
- `0x18004610c`
- `0x180046280`
- `0x180046390`

## callees

- `0x18001b558`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18001b5a5`
- `ntdll!NtQueryInformationToken` at `0x18001b5df`
- `ntdll!NtQueryInformationToken` at `0x18001b5a5`
- `ntdll!NtQueryInformationToken` at `0x18001b5df`

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
0x18001b558  mov     rax, rsp
0x18001b55b  push    rbx
0x18001b55c  push    rsi
0x18001b55d  push    rdi
0x18001b55e  sub     rsp, 30h
0x18001b562  mov     r9d, 4; TokenInformationLength
0x18001b568  mov     dword ptr [rax+18h], 0
0x18001b56f  mov     dword ptr [rax+20h], 0
0x18001b576  mov     rdi, r8
0x18001b579  mov     dword ptr [rax+10h], 1
0x18001b580  lea     rax, [rax+18h]
0x18001b584  mov     rbx, rdx
0x18001b587  mov     dword ptr [r8], 1
0x18001b58e  mov     dword ptr [rdx], 0
0x18001b594  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18001b599  lea     edx, [r9+0Eh]; TokenInformationClass
0x18001b59d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001b5a2  mov     rsi, rcx
0x18001b5a5  call    cs:__imp_NtQueryInformationToken
0x18001b5ab  test    eax, eax
0x18001b5ad  js      short loc_18001B5F6
0x18001b5af  cmp     [rsp+48h+TokenInformation], 2
0x18001b5b4  jz      short loc_18001B5F0
0x18001b5b6  cmp     [rsp+48h+TokenInformation], 1
0x18001b5bb  jnz     short loc_18001B5F6
0x18001b5bd  mov     r9d, 4; TokenInformationLength
0x18001b5c3  mov     dword ptr [rdi], 0
0x18001b5c9  lea     rax, [rsp+48h+arg_10]
0x18001b5ce  mov     rcx, rsi; TokenHandle
0x18001b5d1  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18001b5d6  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001b5db  lea     edx, [r9+10h]; TokenInformationClass
0x18001b5df  call    cs:__imp_NtQueryInformationToken
0x18001b5e5  test    eax, eax
0x18001b5e7  js      short loc_18001B5F6
0x18001b5e9  cmp     [rsp+48h+arg_18], 0
0x18001b5ee  jz      short loc_18001B5F6
0x18001b5f0  mov     dword ptr [rbx], 1
0x18001b5f6  add     rsp, 30h
0x18001b5fa  pop     rdi
0x18001b5fb  pop     rsi
0x18001b5fc  pop     rbx
0x18001b5fd  retn
```
