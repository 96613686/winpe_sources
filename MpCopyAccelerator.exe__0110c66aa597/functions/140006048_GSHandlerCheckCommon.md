# __GSHandlerCheckCommon

- ea: `0x140006048`
- end: `0x1400060a8`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006028`
- `0x140006194`
- `0x14001cf2c`
- `0x14001d020`

## callees

- `0x140005c20`
- `0x140006048`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x140006048  push    rbx
0x14000604a  mov     r11d, [r8]
0x14000604d  mov     rbx, rdx
0x140006050  and     r11d, 0FFFFFFF8h
0x140006054  mov     r9, rcx
0x140006057  test    byte ptr [r8], 4
0x14000605b  mov     r10, rcx
0x14000605e  jz      short loc_140006073
0x140006060  mov     eax, [r8+8]
0x140006064  movsxd  r10, dword ptr [r8+4]
0x140006068  neg     eax
0x14000606a  add     r10, rcx
0x14000606d  movsxd  rcx, eax
0x140006070  and     r10, rcx
0x140006073  movsxd  rax, r11d
0x140006076  mov     rdx, [rax+r10]
0x14000607a  mov     rax, [rbx+10h]
0x14000607e  mov     ecx, [rax+8]
0x140006081  mov     rax, [rbx+8]
0x140006085  test    byte ptr [rcx+rax+3], 0Fh
0x14000608a  jz      short loc_14000609C
0x14000608c  movzx   eax, byte ptr [rcx+rax+3]
0x140006091  mov     ecx, 0FFFFFFF0h
0x140006096  and     rax, rcx
0x140006099  add     r9, rax
0x14000609c  xor     r9, rdx
0x14000609f  mov     rcx, r9; StackCookie
0x1400060a2  pop     rbx
0x1400060a3  jmp     __security_check_cookie
```
