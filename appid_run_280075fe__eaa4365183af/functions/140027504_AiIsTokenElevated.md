# AiIsTokenElevated

- ea: `0x140027504`
- end: `0x14002755a`
- name: `AiIsTokenElevated`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140035250`

## callees

- `0x140027504`

## import_xrefs

- `ntoskrnl!ZwQueryInformationToken` at `0x140027539`
- `ntoskrnl!ZwQueryInformationToken` at `0x140027539`

## pseudocode

```c
NTSTATUS __fastcall AiIsTokenElevated(void *a1, _BYTE *a2)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  result = ZwQueryInformationToken(a1, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( result >= 0 && TokenInformation == 2 )
    *a2 = 1;
  return result;
}

```

## disassembly

```asm
0x140027504  push    rbx
0x140027506  sub     rsp, 30h
0x14002750a  mov     r9d, 4; TokenInformationLength
0x140027510  mov     byte ptr [rdx], 0
0x140027513  mov     rbx, rdx
0x140027516  mov     [rsp+38h+arg_10], 0
0x14002751e  lea     rax, [rsp+38h+arg_10]
0x140027523  mov     [rsp+38h+TokenInformation], 0
0x14002752b  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x140027530  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140027535  lea     edx, [r9+0Eh]; TokenInformationClass
0x140027539  call    cs:__imp_ZwQueryInformationToken
0x140027540  nop     dword ptr [rax+rax+00h]
0x140027545  test    eax, eax
0x140027547  js      short loc_140027553
0x140027549  cmp     [rsp+38h+TokenInformation], 2
0x14002754e  jnz     short loc_140027553
0x140027550  mov     byte ptr [rbx], 1
0x140027553  add     rsp, 30h
0x140027557  pop     rbx
0x140027558  retn
```
