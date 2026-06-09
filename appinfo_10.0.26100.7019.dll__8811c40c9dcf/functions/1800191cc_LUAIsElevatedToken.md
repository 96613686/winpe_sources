# LUAIsElevatedToken

- ea: `0x1800191cc`
- end: `0x180019273`
- name: `LUAIsElevatedToken`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800249f0`
- `0x180041d78`

## callees

- `0x1800191cc`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180019210`
- `ntdll!NtQueryInformationToken` at `0x18001924d`
- `ntdll!NtQueryInformationToken` at `0x180019210`
- `ntdll!NtQueryInformationToken` at `0x18001924d`

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
0x1800191cc  mov     rax, rsp
0x1800191cf  push    rbx
0x1800191d0  push    rsi
0x1800191d1  push    rdi
0x1800191d2  sub     rsp, 30h
0x1800191d6  and     dword ptr [rax+18h], 0
0x1800191da  mov     r9d, 4; TokenInformationLength
0x1800191e0  and     dword ptr [rax+20h], 0
0x1800191e4  mov     rdi, r8
0x1800191e7  and     dword ptr [rdx], 0
0x1800191ea  mov     rbx, rdx
0x1800191ed  mov     dword ptr [rax+10h], 1
0x1800191f4  lea     rax, [rax+18h]
0x1800191f8  mov     dword ptr [r8], 1
0x1800191ff  lea     edx, [r9+0Eh]; TokenInformationClass
0x180019203  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180019208  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001920d  mov     rsi, rcx
0x180019210  call    cs:__imp_NtQueryInformationToken
0x180019217  nop     dword ptr [rax+rax+00h]
0x18001921c  test    eax, eax
0x18001921e  js      short loc_18001926A
0x180019220  cmp     [rsp+48h+TokenInformation], 2
0x180019225  jz      short loc_180019264
0x180019227  cmp     [rsp+48h+TokenInformation], 1
0x18001922c  jnz     short loc_18001926A
0x18001922e  and     dword ptr [rdi], 0
0x180019231  lea     rax, [rsp+48h+arg_10]
0x180019236  mov     r9d, 4; TokenInformationLength
0x18001923c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180019241  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x180019246  mov     rcx, rsi; TokenHandle
0x180019249  lea     edx, [r9+10h]; TokenInformationClass
0x18001924d  call    cs:__imp_NtQueryInformationToken
0x180019254  nop     dword ptr [rax+rax+00h]
0x180019259  test    eax, eax
0x18001925b  js      short loc_18001926A
0x18001925d  cmp     [rsp+48h+arg_18], 0
0x180019262  jz      short loc_18001926A
0x180019264  mov     dword ptr [rbx], 1
0x18001926a  add     rsp, 30h
0x18001926e  pop     rdi
0x18001926f  pop     rsi
0x180019270  pop     rbx
0x180019271  retn
```
