# LUAIsElevatedToken

- ea: `0x18001959c`
- end: `0x180019643`
- name: `LUAIsElevatedToken`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800230e0`
- `0x180043940`

## callees

- `0x18001959c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800195e0`
- `ntdll!NtQueryInformationToken` at `0x18001961d`
- `ntdll!NtQueryInformationToken` at `0x1800195e0`
- `ntdll!NtQueryInformationToken` at `0x18001961d`

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
  *a2 = 0;
  TokenInformation = 1;
  *a3 = 1;
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
0x18001959c  mov     rax, rsp
0x18001959f  push    rbx
0x1800195a0  push    rsi
0x1800195a1  push    rdi
0x1800195a2  sub     rsp, 30h
0x1800195a6  and     dword ptr [rax+18h], 0
0x1800195aa  mov     r9d, 4; TokenInformationLength
0x1800195b0  and     dword ptr [rax+20h], 0
0x1800195b4  mov     rdi, r8
0x1800195b7  and     dword ptr [rdx], 0
0x1800195ba  mov     rbx, rdx
0x1800195bd  mov     dword ptr [rax+10h], 1
0x1800195c4  lea     rax, [rax+18h]
0x1800195c8  mov     dword ptr [r8], 1
0x1800195cf  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800195d3  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1800195d8  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800195dd  mov     rsi, rcx
0x1800195e0  call    cs:__imp_NtQueryInformationToken
0x1800195e7  nop     dword ptr [rax+rax+00h]
0x1800195ec  test    eax, eax
0x1800195ee  js      short loc_18001963A
0x1800195f0  cmp     [rsp+48h+TokenInformation], 2
0x1800195f5  jz      short loc_180019634
0x1800195f7  cmp     [rsp+48h+TokenInformation], 1
0x1800195fc  jnz     short loc_18001963A
0x1800195fe  and     dword ptr [rdi], 0
0x180019601  lea     rax, [rsp+48h+arg_10]
0x180019606  mov     r9d, 4; TokenInformationLength
0x18001960c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180019611  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x180019616  mov     rcx, rsi; TokenHandle
0x180019619  lea     edx, [r9+10h]; TokenInformationClass
0x18001961d  call    cs:__imp_NtQueryInformationToken
0x180019624  nop     dword ptr [rax+rax+00h]
0x180019629  test    eax, eax
0x18001962b  js      short loc_18001963A
0x18001962d  cmp     [rsp+48h+arg_18], 0
0x180019632  jz      short loc_18001963A
0x180019634  mov     dword ptr [rbx], 1
0x18001963a  add     rsp, 30h
0x18001963e  pop     rdi
0x18001963f  pop     rsi
0x180019640  pop     rbx
0x180019641  retn
```
