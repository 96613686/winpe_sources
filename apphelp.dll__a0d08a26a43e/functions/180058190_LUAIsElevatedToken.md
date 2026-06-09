# LUAIsElevatedToken

- ea: `0x180058190`
- end: `0x180058236`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005823c`
- `0x18005834c`

## callees

- `0x180058190`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800581dd`
- `ntdll!NtQueryInformationToken` at `0x180058217`
- `ntdll!NtQueryInformationToken` at `0x1800581dd`
- `ntdll!NtQueryInformationToken` at `0x180058217`

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
0x180058190  mov     rax, rsp
0x180058193  push    rbx
0x180058194  push    rsi
0x180058195  push    rdi
0x180058196  sub     rsp, 30h
0x18005819a  mov     r9d, 4; TokenInformationLength
0x1800581a0  mov     dword ptr [rax+18h], 0
0x1800581a7  mov     dword ptr [rax+20h], 0
0x1800581ae  mov     rdi, r8
0x1800581b1  mov     dword ptr [rax+10h], 1
0x1800581b8  lea     rax, [rax+18h]
0x1800581bc  mov     rbx, rdx
0x1800581bf  mov     dword ptr [r8], 1
0x1800581c6  mov     dword ptr [rdx], 0
0x1800581cc  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1800581d1  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800581d5  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800581da  mov     rsi, rcx
0x1800581dd  call    cs:__imp_NtQueryInformationToken
0x1800581e3  test    eax, eax
0x1800581e5  js      short loc_18005822E
0x1800581e7  cmp     [rsp+48h+TokenInformation], 2
0x1800581ec  jz      short loc_180058228
0x1800581ee  cmp     [rsp+48h+TokenInformation], 1
0x1800581f3  jnz     short loc_18005822E
0x1800581f5  mov     r9d, 4; TokenInformationLength
0x1800581fb  mov     dword ptr [rdi], 0
0x180058201  lea     rax, [rsp+48h+arg_10]
0x180058206  mov     rcx, rsi; TokenHandle
0x180058209  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18005820e  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180058213  lea     edx, [r9+10h]; TokenInformationClass
0x180058217  call    cs:__imp_NtQueryInformationToken
0x18005821d  test    eax, eax
0x18005821f  js      short loc_18005822E
0x180058221  cmp     [rsp+48h+arg_18], 0
0x180058226  jz      short loc_18005822E
0x180058228  mov     dword ptr [rbx], 1
0x18005822e  add     rsp, 30h
0x180058232  pop     rdi
0x180058233  pop     rsi
0x180058234  pop     rbx
0x180058235  retn
```
