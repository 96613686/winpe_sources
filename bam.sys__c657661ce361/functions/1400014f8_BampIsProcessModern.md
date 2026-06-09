# BampIsProcessModern

- ea: `0x1400014f8`
- end: `0x140001551`
- name: `BampIsProcessModern`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140012530`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x14000150a`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000150a`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x140001524`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x140001524`
- `ntoskrnl!ObfDereferenceObject` at `0x140001533`
- `ntoskrnl!ObfDereferenceObject` at `0x140001533`

## pseudocode

```c
char __fastcall BampIsProcessModern(struct _KPROCESS *a1, _BYTE *a2)
{
  PACCESS_TOKEN v3; // rbx
  char result; // al
  char v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  v3 = PsReferencePrimaryToken(a1);
  PsQueryProcessAttributesByToken(v3, &v5, 0);
  ObfDereferenceObject(v3);
  result = v5;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x1400014f8  mov     [rsp+arg_0], rbx
0x1400014fd  push    rdi
0x1400014fe  sub     rsp, 20h
0x140001502  mov     rdi, rdx
0x140001505  mov     [rsp+28h+arg_8], 0
0x14000150a  call    cs:__imp_PsReferencePrimaryToken
0x140001511  nop     dword ptr [rax+rax+00h]
0x140001516  xor     r8d, r8d
0x140001519  lea     rdx, [rsp+28h+arg_8]
0x14000151e  mov     rcx, rax
0x140001521  mov     rbx, rax
0x140001524  call    cs:__imp_PsQueryProcessAttributesByToken
0x14000152b  nop     dword ptr [rax+rax+00h]
0x140001530  mov     rcx, rbx; Object
0x140001533  call    cs:__imp_ObfDereferenceObject
0x14000153a  nop     dword ptr [rax+rax+00h]
0x14000153f  mov     al, [rsp+28h+arg_8]
0x140001543  mov     rbx, [rsp+28h+arg_0]
0x140001548  mov     [rdi], al
0x14000154a  add     rsp, 20h
0x14000154e  pop     rdi
0x14000154f  retn
```
