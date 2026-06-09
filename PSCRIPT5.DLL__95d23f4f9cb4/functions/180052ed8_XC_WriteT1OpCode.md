# XC_WriteT1OpCode

- ea: `0x180052ed8`
- end: `0x180052f27`
- name: `XC_WriteT1OpCode`
- size: `79`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x18004e918`
- `0x18004eff8`
- `0x18004f198`
- `0x18004f944`
- `0x18004fa84`
- `0x18004fbc4`
- `0x18004fe44`
- `0x18004ff08`
- `0x18005017c`
- `0x180050620`
- `0x1800506a4`
- `0x180050770`
- `0x180050de0`
- `0x180050e84`
- `0x18005152c`
- `0x180052154`
- `0x180052370`
- `0x180052f30`

## callees

- `0x18005165c`

## pseudocode

```c
__int64 __fastcall XC_WriteT1OpCode(__int64 a1, __int16 a2, unsigned int a3)
{
  char *v4; // rdx
  __int16 v5; // r9
  char v7; // [rsp+38h] [rbp+10h] BYREF
  char v8; // [rsp+39h] [rbp+11h] BYREF

  v7 = 12;
  v8 = a2;
  v4 = &v8;
  v5 = a2 & 0xFF00;
  if ( v5 )
    v4 = &v7;
  return WriteT1Data(a1, v4, (unsigned int)(v5 != 0) + 1, a3);
}

```

## disassembly

```asm
0x180052ed8  sub     rsp, 28h
0x180052edc  movzx   r9d, dx
0x180052ee0  mov     [rsp+28h+arg_8], 0Ch
0x180052ee7  mov     r10d, r8d
0x180052eea  mov     byte ptr [rsp+28h+arg_8+1], r9b
0x180052eef  mov     eax, 0FF00h
0x180052ef4  lea     rdx, [rsp+28h+arg_8+1]
0x180052ef9  and     r9w, ax
0x180052efd  movzx   eax, r9w
0x180052f01  neg     ax
0x180052f04  lea     rax, [rsp+28h+arg_8]
0x180052f09  sbb     r8d, r8d
0x180052f0c  neg     r8d
0x180052f0f  inc     r8d
0x180052f12  test    r9w, r9w
0x180052f16  mov     r9d, r10d
0x180052f19  cmovnz  rdx, rax
0x180052f1d  call    WriteT1Data
0x180052f22  add     rsp, 28h
0x180052f26  retn
```
