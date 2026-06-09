# __GSHandlerCheckCommon

- ea: `0x14001c7fc`
- end: `0x14001c857`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c7dc`
- `0x14001c8c0`
- `0x140024e2c`
- `0x1400adf94`

## callees

- `0x14001bf00`
- `0x14001c7fc`

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
0x14001c7fc  push    rbx
0x14001c7fe  mov     r11d, [r8]
0x14001c801  mov     rbx, rdx
0x14001c804  and     r11d, 0FFFFFFF8h
0x14001c808  mov     r9, rcx
0x14001c80b  test    byte ptr [r8], 4
0x14001c80f  mov     r10, rcx
0x14001c812  jz      short loc_14001C827
0x14001c814  mov     eax, [r8+8]
0x14001c818  movsxd  r10, dword ptr [r8+4]
0x14001c81c  neg     eax
0x14001c81e  add     r10, rcx
0x14001c821  movsxd  rcx, eax
0x14001c824  and     r10, rcx
0x14001c827  movsxd  rax, r11d
0x14001c82a  mov     rdx, [rax+r10]
0x14001c82e  mov     rax, [rbx+10h]
0x14001c832  mov     ecx, [rax+8]
0x14001c835  mov     rax, [rbx+8]
0x14001c839  test    byte ptr [rcx+rax+3], 0Fh
0x14001c83e  jz      short loc_14001C84B
0x14001c840  movzx   eax, byte ptr [rcx+rax+3]
0x14001c845  and     eax, 0FFFFFFF0h
0x14001c848  add     r9, rax
0x14001c84b  xor     r9, rdx
0x14001c84e  mov     rcx, r9; StackCookie
0x14001c851  pop     rbx
0x14001c852  jmp     __security_check_cookie
```
