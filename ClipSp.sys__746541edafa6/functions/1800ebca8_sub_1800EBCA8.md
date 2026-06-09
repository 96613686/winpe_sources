# sub_1800EBCA8

- ea: `0x1800ebca8`
- end: `0x1800ebe68`
- name: `sub_1800EBCA8`
- size: `448`
- prototype: `__int64 __fastcall(int, int, int, int, PULONG, HANDLE, __int64, int, int, int, int, int, int, int, int, ULONG)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800ebb50`
- `0x1800ebb90`
- `0x1800f15a0`
- `0x1800f1760`
- `0x1800f2280`

## callees

- `0x180001630`
- `0x1800016bc`
- `0x18005b840`
- `0x1800ebca8`
- `0x1800f87ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800ebe25`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800ebe25`
- `ntoskrnl!ZwClose` at `0x1800ebd7b`
- `ntoskrnl!ZwClose` at `0x1800ebd7b`
- `ntoskrnl!ExAllocatePool2` at `0x1800ebdaa`
- `ntoskrnl!ExAllocatePool2` at `0x1800ebdaa`
- `ntoskrnl!ZwQueryValueKey` at `0x1800ebd55`
- `ntoskrnl!ZwQueryValueKey` at `0x1800ebdeb`
- `ntoskrnl!ZwQueryValueKey` at `0x1800ebd55`
- `ntoskrnl!ZwQueryValueKey` at `0x1800ebdeb`

## pseudocode

```c
__int64 __fastcall sub_1800EBCA8(__int64 a1, __int64 a2, __int64 a3, __int64 a4, PULONG a5, HANDLE a6, _BYTE *a7)
{
  HANDLE KeyHandle[9]; // [rsp+30h] [rbp-48h] BYREF

  KeyHandle[0] = 0;
  *a7 = 1;
  if ( (int)sub_180001630(&dword_1800D7290, &dword_1800DA9B0) >= 0 )
    sub_1800F87EC(asc_180107000, &qword_180107010, 0, KeyHandle);
  return 3221225701LL;
}

```

## disassembly

```asm
0x1800ebca8  mov     rax, rsp
0x1800ebcab  mov     [rax+8], rcx
0x1800ebcaf  push    rbx
0x1800ebcb0  push    rbp
0x1800ebcb1  push    rdi
0x1800ebcb2  push    r13
0x1800ebcb4  push    r14
0x1800ebcb6  push    r15
0x1800ebcb8  sub     rsp, 48h
0x1800ebcbc  mov     qword ptr [rax-48h], 0
0x1800ebcc4  lea     rcx, dword_1800D7290
0x1800ebccb  mov     dword ptr [rax+8], 0
0x1800ebcd2  mov     r15, rdx
0x1800ebcd5  mov     rax, [rsp+78h+arg_30]
0x1800ebcdd  lea     rdx, dword_1800DA9B0
0x1800ebce4  mov     r13b, 1
0x1800ebce7  mov     rbp, r9
0x1800ebcea  mov     r14, r8
0x1800ebced  mov     [rax], r13b
0x1800ebcf0  call    sub_180001630
0x1800ebcf5  test    eax, eax
0x1800ebcf7  js      loc_1800EBE5E
0x1800ebcfd  lea     r9, [rsp+78h+KeyHandle]
0x1800ebd02  xor     r8d, r8d
0x1800ebd05  lea     rdx, qword_180107010
0x1800ebd0c  lea     rcx, asc_180107000; "$&"
0x1800ebd13  call    sub_1800F87EC
0x1800ebd18  lea     rdx, dword_1800DA9B0
0x1800ebd1f  mov     ebx, eax
0x1800ebd21  lea     rcx, dword_1800D7290
0x1800ebd28  call    sub_1800016BC
0x1800ebd2d  test    ebx, ebx
0x1800ebd2f  js      short loc_1800EBD87
0x1800ebd31  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x1800ebd36  lea     rax, [rsp+78h+arg_0]
0x1800ebd3e  xor     r9d, r9d; KeyValueInformation
0x1800ebd41  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1800ebd46  mov     rdx, r15; ValueName
0x1800ebd49  mov     [rsp+78h+Length], 0; Length
0x1800ebd51  lea     r8d, [r9+2]; KeyValueInformationClass
0x1800ebd55  call    cs:ZwQueryValueKey
0x1800ebd5c  nop     dword ptr [rax+rax+00h]
0x1800ebd61  mov     ecx, 80000000h
0x1800ebd66  mov     ebx, eax
0x1800ebd68  add     eax, ecx
0x1800ebd6a  test    ecx, eax
0x1800ebd6c  jnz     short loc_1800EBD98
0x1800ebd6e  cmp     ebx, 0C0000023h
0x1800ebd74  jz      short loc_1800EBD98
0x1800ebd76  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x1800ebd7b  call    cs:ZwClose
0x1800ebd82  nop     dword ptr [rax+rax+00h]
0x1800ebd87  mov     eax, ebx
0x1800ebd89  add     rsp, 48h
0x1800ebd8d  pop     r15
0x1800ebd8f  pop     r14
0x1800ebd91  pop     r13
0x1800ebd93  pop     rdi
0x1800ebd94  pop     rbp
0x1800ebd95  pop     rbx
0x1800ebd96  retn
0x1800ebd98  mov     edx, [rsp+78h+arg_0]
0x1800ebd9f  mov     ecx, 100h
0x1800ebda4  mov     r8d, 20534C53h
0x1800ebdaa  call    cs:ExAllocatePool2
0x1800ebdb1  nop     dword ptr [rax+rax+00h]
0x1800ebdb6  mov     rdi, rax
0x1800ebdb9  test    rax, rax
0x1800ebdbc  jz      loc_1800EBE4C
0x1800ebdc2  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x1800ebdc7  lea     rax, [rsp+78h+arg_0]
0x1800ebdcf  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1800ebdd4  mov     r9, rdi; KeyValueInformation
0x1800ebdd7  mov     eax, [rsp+78h+arg_0]
0x1800ebdde  mov     r8d, 2; KeyValueInformationClass
0x1800ebde4  mov     rdx, r15; ValueName
0x1800ebde7  mov     [rsp+78h+Length], eax; Length
0x1800ebdeb  call    cs:ZwQueryValueKey
0x1800ebdf2  nop     dword ptr [rax+rax+00h]
0x1800ebdf7  mov     ebx, eax
0x1800ebdf9  test    eax, eax
0x1800ebdfb  js      short loc_1800EBE20
0x1800ebdfd  mov     rax, [rsp+78h+arg_28]
0x1800ebe05  mov     ecx, [rdi+8]
0x1800ebe08  mov     [rax], ecx
0x1800ebe0a  test    r14, r14
0x1800ebe0d  jnz     short loc_1800EBE56
0x1800ebe0f  mov     eax, [rdi+8]
0x1800ebe12  cmp     dword ptr [rsp+78h+arg_20], eax
0x1800ebe19  jnb     short loc_1800EBE36
0x1800ebe1b  mov     ebx, 0C0000023h
0x1800ebe20  xor     edx, edx; Tag
0x1800ebe22  mov     rcx, rdi; P
0x1800ebe25  call    cs:ExFreePoolWithTag
0x1800ebe2c  nop     dword ptr [rax+rax+00h]
0x1800ebe31  jmp     loc_1800EBD76
0x1800ebe36  test    rbp, rbp
0x1800ebe39  jz      short loc_1800EBE20
0x1800ebe3b  mov     r8, rax
0x1800ebe3e  lea     rdx, [rdi+0Ch]
0x1800ebe42  mov     rcx, rbp
0x1800ebe45  call    sub_18005B840
0x1800ebe4a  jmp     short loc_1800EBE20
0x1800ebe4c  mov     ebx, 0C0000017h
0x1800ebe51  jmp     loc_1800EBD76
0x1800ebe56  mov     eax, [rdi+4]
0x1800ebe59  mov     [r14], eax
0x1800ebe5c  jmp     short loc_1800EBE0F
0x1800ebe5e  mov     ebx, 0C00000E5h
0x1800ebe63  jmp     loc_1800EBD87
```
