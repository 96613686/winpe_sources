# XC_WriteT1OpCode

- ea: `0x180054864`
- end: `0x1800548b4`
- name: `XC_WriteT1OpCode`
- size: `80`
- prototype: `void __fastcall(__int64, __int16, int)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180050274`
- `0x180050960`
- `0x180050b04`
- `0x1800512b8`
- `0x1800513f8`
- `0x180051538`
- `0x1800517bc`
- `0x180051880`
- `0x180051af4`
- `0x180051f98`
- `0x18005201c`
- `0x1800520e8`
- `0x180052758`
- `0x1800527fc`
- `0x180052ea8`
- `0x180053ad4`
- `0x180053cf0`
- `0x1800548bc`

## callees

- `0x180052fd8`

## pseudocode

```c
void __fastcall XC_WriteT1OpCode(__int64 a1, __int16 a2, int a3)
{
  char *v4; // rdx
  __int16 v5; // r9
  char v6; // [rsp+38h] [rbp+10h] BYREF
  char v7; // [rsp+39h] [rbp+11h] BYREF

  v6 = 12;
  v7 = a2;
  v4 = &v7;
  v5 = a2 & 0xFF00;
  if ( v5 )
    v4 = &v6;
  WriteT1Data(a1, v4, (v5 != 0) + 1, a3);
}

```

## disassembly

```asm
0x180054864  sub     rsp, 28h
0x180054868  movzx   r9d, dx
0x18005486c  mov     [rsp+28h+arg_8], 0Ch
0x180054873  mov     r10d, r8d
0x180054876  mov     byte ptr [rsp+28h+arg_8+1], r9b
0x18005487b  mov     eax, 0FF00h
0x180054880  lea     rdx, [rsp+28h+arg_8+1]
0x180054885  and     r9w, ax
0x180054889  movzx   eax, r9w
0x18005488d  neg     ax
0x180054890  lea     rax, [rsp+28h+arg_8]
0x180054895  sbb     r8d, r8d
0x180054898  neg     r8d
0x18005489b  inc     r8d
0x18005489e  test    r9w, r9w
0x1800548a2  mov     r9d, r10d
0x1800548a5  cmovnz  rdx, rax
0x1800548a9  call    WriteT1Data
0x1800548ae  add     rsp, 28h
0x1800548b2  retn
```
