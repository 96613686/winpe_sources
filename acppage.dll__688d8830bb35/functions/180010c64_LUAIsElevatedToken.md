# LUAIsElevatedToken

- ea: `0x180010c64`
- end: `0x180010d0a`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010b5c`

## callees

- `0x180010c64`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180010cb1`
- `ntdll!NtQueryInformationToken` at `0x180010ceb`
- `ntdll!NtQueryInformationToken` at `0x180010cb1`
- `ntdll!NtQueryInformationToken` at `0x180010ceb`

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
0x180010c64  mov     rax, rsp
0x180010c67  push    rbx
0x180010c68  push    rsi
0x180010c69  push    rdi
0x180010c6a  sub     rsp, 30h
0x180010c6e  mov     r9d, 4; TokenInformationLength
0x180010c74  mov     dword ptr [rax+18h], 0
0x180010c7b  mov     dword ptr [rax+20h], 0
0x180010c82  mov     rdi, r8
0x180010c85  mov     dword ptr [rax+10h], 1
0x180010c8c  lea     rax, [rax+18h]
0x180010c90  mov     rbx, rdx
0x180010c93  mov     dword ptr [r8], 1
0x180010c9a  mov     dword ptr [rdx], 0
0x180010ca0  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180010ca5  lea     edx, [r9+0Eh]; TokenInformationClass
0x180010ca9  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180010cae  mov     rsi, rcx
0x180010cb1  call    cs:__imp_NtQueryInformationToken
0x180010cb7  test    eax, eax
0x180010cb9  js      short loc_180010D02
0x180010cbb  cmp     [rsp+48h+TokenInformation], 2
0x180010cc0  jz      short loc_180010CFC
0x180010cc2  cmp     [rsp+48h+TokenInformation], 1
0x180010cc7  jnz     short loc_180010D02
0x180010cc9  mov     r9d, 4; TokenInformationLength
0x180010ccf  mov     dword ptr [rdi], 0
0x180010cd5  lea     rax, [rsp+48h+arg_10]
0x180010cda  mov     rcx, rsi; TokenHandle
0x180010cdd  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x180010ce2  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180010ce7  lea     edx, [r9+10h]; TokenInformationClass
0x180010ceb  call    cs:__imp_NtQueryInformationToken
0x180010cf1  test    eax, eax
0x180010cf3  js      short loc_180010D02
0x180010cf5  cmp     [rsp+48h+arg_18], 0
0x180010cfa  jz      short loc_180010D02
0x180010cfc  mov     dword ptr [rbx], 1
0x180010d02  add     rsp, 30h
0x180010d06  pop     rdi
0x180010d07  pop     rsi
0x180010d08  pop     rbx
0x180010d09  retn
```
