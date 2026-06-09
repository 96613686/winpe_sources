# IsProcessElevated

- ea: `0x14001187c`
- end: `0x14001192d`
- name: `IsProcessElevated`
- size: `177`
- prototype: `NTSTATUS __fastcall(bool *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140008aa8`
- `0x140008d50`
- `0x14000fd38`

## callees

- `0x14001187c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400118f9`
- `ntoskrnl!ZwClose` at `0x140011909`
- `ntoskrnl!ZwClose` at `0x1400118f9`
- `ntoskrnl!ZwClose` at `0x140011909`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400118b4`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400118b4`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400118e2`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400118e2`

## pseudocode

```c
NTSTATUS __fastcall IsProcessElevated(bool *a1)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // ebx
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  result = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &TokenHandle);
  if ( result >= 0 )
  {
    v3 = ZwQueryInformationToken(TokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength);
    ZwClose(TokenHandle);
    if ( v3 >= 0 )
    {
      *a1 = TokenInformation != 0;
      return 0;
    }
    else
    {
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001187c  mov     rax, rsp
0x14001187f  mov     [rax+8], rbx
0x140011883  push    rdi
0x140011884  sub     rsp, 30h
0x140011888  mov     rdi, rcx
0x14001188b  mov     qword ptr [rax+20h], 0
0x140011893  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140011897  mov     dword ptr [rax+10h], 0
0x14001189e  lea     r9, [rax+20h]; TokenHandle
0x1400118a2  mov     dword ptr [rax+18h], 0
0x1400118a9  mov     edx, 8; DesiredAccess
0x1400118ae  mov     r8d, 200h; HandleAttributes
0x1400118b4  call    cs:__imp_ZwOpenProcessTokenEx
0x1400118bb  nop     dword ptr [rax+rax+00h]
0x1400118c0  test    eax, eax
0x1400118c2  js      short loc_140011921
0x1400118c4  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1400118c9  lea     rax, [rsp+38h+arg_10]
0x1400118ce  mov     r9d, 4; TokenInformationLength
0x1400118d4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1400118d9  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1400118de  lea     edx, [r9+10h]; TokenInformationClass
0x1400118e2  call    cs:__imp_ZwQueryInformationToken
0x1400118e9  nop     dword ptr [rax+rax+00h]
0x1400118ee  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x1400118f3  mov     ebx, eax
0x1400118f5  test    eax, eax
0x1400118f7  jns     short loc_140011909
0x1400118f9  call    cs:__imp_ZwClose
0x140011900  nop     dword ptr [rax+rax+00h]
0x140011905  mov     eax, ebx
0x140011907  jmp     short loc_140011921
0x140011909  call    cs:__imp_ZwClose
0x140011910  nop     dword ptr [rax+rax+00h]
0x140011915  cmp     [rsp+38h+TokenInformation], 0
0x14001191a  setnz   al
0x14001191d  mov     [rdi], al
0x14001191f  xor     eax, eax
0x140011921  mov     rbx, [rsp+38h+arg_0]
0x140011926  add     rsp, 30h
0x14001192a  pop     rdi
0x14001192b  retn
```
