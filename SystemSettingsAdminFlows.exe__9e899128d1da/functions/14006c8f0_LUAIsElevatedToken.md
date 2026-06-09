# LUAIsElevatedToken

- ea: `0x14006c8f0`
- end: `0x14006c996`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14006c9e0`
- `0x14006caf0`

## callees

- `0x14006c8f0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x14006c93d`
- `ntdll!NtQueryInformationToken` at `0x14006c977`
- `ntdll!NtQueryInformationToken` at `0x14006c93d`
- `ntdll!NtQueryInformationToken` at `0x14006c977`

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
0x14006c8f0  mov     rax, rsp
0x14006c8f3  push    rbx
0x14006c8f4  push    rsi
0x14006c8f5  push    rdi
0x14006c8f6  sub     rsp, 30h
0x14006c8fa  mov     r9d, 4; TokenInformationLength
0x14006c900  mov     dword ptr [rax+18h], 0
0x14006c907  mov     dword ptr [rax+20h], 0
0x14006c90e  mov     rdi, r8
0x14006c911  mov     dword ptr [rax+10h], 1
0x14006c918  lea     rax, [rax+18h]
0x14006c91c  mov     rbx, rdx
0x14006c91f  mov     dword ptr [r8], 1
0x14006c926  mov     dword ptr [rdx], 0
0x14006c92c  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14006c931  lea     edx, [r9+0Eh]; TokenInformationClass
0x14006c935  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14006c93a  mov     rsi, rcx
0x14006c93d  call    cs:__imp_NtQueryInformationToken
0x14006c943  test    eax, eax
0x14006c945  js      short loc_14006C98E
0x14006c947  cmp     [rsp+48h+TokenInformation], 2
0x14006c94c  jz      short loc_14006C988
0x14006c94e  cmp     [rsp+48h+TokenInformation], 1
0x14006c953  jnz     short loc_14006C98E
0x14006c955  mov     r9d, 4; TokenInformationLength
0x14006c95b  mov     dword ptr [rdi], 0
0x14006c961  lea     rax, [rsp+48h+arg_10]
0x14006c966  mov     rcx, rsi; TokenHandle
0x14006c969  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x14006c96e  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14006c973  lea     edx, [r9+10h]; TokenInformationClass
0x14006c977  call    cs:__imp_NtQueryInformationToken
0x14006c97d  test    eax, eax
0x14006c97f  js      short loc_14006C98E
0x14006c981  cmp     [rsp+48h+arg_18], 0
0x14006c986  jz      short loc_14006C98E
0x14006c988  mov     dword ptr [rbx], 1
0x14006c98e  add     rsp, 30h
0x14006c992  pop     rdi
0x14006c993  pop     rsi
0x14006c994  pop     rbx
0x14006c995  retn
```
