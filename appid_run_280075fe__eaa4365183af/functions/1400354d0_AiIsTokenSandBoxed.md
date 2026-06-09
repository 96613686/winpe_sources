# AiIsTokenSandBoxed

- ea: `0x1400354d0`
- end: `0x14003551e`
- name: `AiIsTokenSandBoxed`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f3c0`
- `0x14002cd1c`

## callees

- `0x1400354d0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationToken` at `0x1400354fd`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400354fd`

## pseudocode

```c
NTSTATUS __fastcall AiIsTokenSandBoxed(void *a1, bool *a2)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+50h] [rbp+18h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp+20h] BYREF

  ReturnLength = 0;
  TokenInformation = 0;
  result = ZwQueryInformationToken(a1, TokenSandBoxInert, &TokenInformation, 4u, &ReturnLength);
  if ( result >= 0 )
    *a2 = TokenInformation != 0;
  return result;
}

```

## disassembly

```asm
0x1400354d0  push    rbx
0x1400354d2  sub     rsp, 30h
0x1400354d6  xor     eax, eax
0x1400354d8  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1400354dd  mov     [rsp+38h+arg_18], eax
0x1400354e1  mov     rbx, rdx
0x1400354e4  mov     [rsp+38h+TokenInformation], eax
0x1400354e8  mov     r9d, 4; TokenInformationLength
0x1400354ee  lea     rax, [rsp+38h+arg_18]
0x1400354f3  mov     edx, 0Fh; TokenInformationClass
0x1400354f8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1400354fd  call    cs:__imp_ZwQueryInformationToken
0x140035504  nop     dword ptr [rax+rax+00h]
0x140035509  test    eax, eax
0x14003550b  js      short loc_140035517
0x14003550d  cmp     [rsp+38h+TokenInformation], 0
0x140035512  setnz   cl
0x140035515  mov     [rbx], cl
0x140035517  add     rsp, 30h
0x14003551b  pop     rbx
0x14003551c  retn
```
