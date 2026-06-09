# LUAIsElevatedToken

- ea: `0x180058250`
- end: `0x1800582f6`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800582fc`
- `0x18005840c`

## callees

- `0x180058250`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18005829d`
- `ntdll!NtQueryInformationToken` at `0x1800582d7`
- `ntdll!NtQueryInformationToken` at `0x18005829d`
- `ntdll!NtQueryInformationToken` at `0x1800582d7`

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
0x180058250  mov     rax, rsp
0x180058253  push    rbx
0x180058254  push    rsi
0x180058255  push    rdi
0x180058256  sub     rsp, 30h
0x18005825a  mov     r9d, 4; TokenInformationLength
0x180058260  mov     dword ptr [rax+18h], 0
0x180058267  mov     dword ptr [rax+20h], 0
0x18005826e  mov     rdi, r8
0x180058271  mov     dword ptr [rax+10h], 1
0x180058278  lea     rax, [rax+18h]
0x18005827c  mov     rbx, rdx
0x18005827f  mov     dword ptr [r8], 1
0x180058286  mov     dword ptr [rdx], 0
0x18005828c  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180058291  lea     edx, [r9+0Eh]; TokenInformationClass
0x180058295  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18005829a  mov     rsi, rcx
0x18005829d  call    cs:__imp_NtQueryInformationToken
0x1800582a3  test    eax, eax
0x1800582a5  js      short loc_1800582EE
0x1800582a7  cmp     [rsp+48h+TokenInformation], 2
0x1800582ac  jz      short loc_1800582E8
0x1800582ae  cmp     [rsp+48h+TokenInformation], 1
0x1800582b3  jnz     short loc_1800582EE
0x1800582b5  mov     r9d, 4; TokenInformationLength
0x1800582bb  mov     dword ptr [rdi], 0
0x1800582c1  lea     rax, [rsp+48h+arg_10]
0x1800582c6  mov     rcx, rsi; TokenHandle
0x1800582c9  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x1800582ce  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800582d3  lea     edx, [r9+10h]; TokenInformationClass
0x1800582d7  call    cs:__imp_NtQueryInformationToken
0x1800582dd  test    eax, eax
0x1800582df  js      short loc_1800582EE
0x1800582e1  cmp     [rsp+48h+arg_18], 0
0x1800582e6  jz      short loc_1800582EE
0x1800582e8  mov     dword ptr [rbx], 1
0x1800582ee  add     rsp, 30h
0x1800582f2  pop     rdi
0x1800582f3  pop     rsi
0x1800582f4  pop     rbx
0x1800582f5  retn
```
