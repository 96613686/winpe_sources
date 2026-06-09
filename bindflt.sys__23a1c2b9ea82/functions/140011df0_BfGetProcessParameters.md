# BfGetProcessParameters

- ea: `0x140011df0`
- end: `0x140011e2a`
- name: `BfGetProcessParameters`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011fb4`

## callees

- `0x14000f6a4`
- `0x140011df0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140011e13`
- `ntoskrnl!ProbeForRead` at `0x140011e13`

## pseudocode

```c
__int64 __fastcall BfGetProcessParameters(__int64 a1, _QWORD *a2)
{
  volatile void *ULong64FromUser; // rax

  ULong64FromUser = (volatile void *)RtlReadULong64FromUser(a1 + 32);
  *a2 = ULong64FromUser;
  ProbeForRead(ULong64FromUser, 0x450u, 4u);
  return 0;
}

```

## disassembly

```asm
0x140011df0  push    rbx
0x140011df2  sub     rsp, 20h
0x140011df6  mov     rbx, rdx
0x140011df9  add     rcx, 20h ; ' '
0x140011dfd  call    RtlReadULong64FromUser
0x140011e02  mov     [rbx], rax
0x140011e05  mov     edx, 450h; Length
0x140011e0a  mov     r8d, 4; Alignment
0x140011e10  mov     rcx, rax; Address
0x140011e13  call    cs:__imp_ProbeForRead
0x140011e1a  nop     dword ptr [rax+rax+00h]
0x140011e1f  xor     eax, eax
0x140011e21  jmp     short $+2
0x140011e23  add     rsp, 20h
0x140011e27  pop     rbx
0x140011e28  retn
```
