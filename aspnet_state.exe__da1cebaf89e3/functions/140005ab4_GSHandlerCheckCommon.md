# __GSHandlerCheckCommon

- ea: `0x140005ab4`
- end: `0x140005b0f`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005a94`

## callees

- `0x140005ab4`
- `0x140005b20`

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
0x140005ab4  push    rbx
0x140005ab6  mov     r11d, [r8]
0x140005ab9  mov     rbx, rdx
0x140005abc  and     r11d, 0FFFFFFF8h
0x140005ac0  mov     r9, rcx
0x140005ac3  test    byte ptr [r8], 4
0x140005ac7  mov     r10, rcx
0x140005aca  jz      short loc_140005ADF
0x140005acc  mov     eax, [r8+8]
0x140005ad0  movsxd  r10, dword ptr [r8+4]
0x140005ad4  neg     eax
0x140005ad6  add     r10, rcx
0x140005ad9  movsxd  rcx, eax
0x140005adc  and     r10, rcx
0x140005adf  movsxd  rax, r11d
0x140005ae2  mov     rdx, [rax+r10]
0x140005ae6  mov     rax, [rbx+10h]
0x140005aea  mov     ecx, [rax+8]
0x140005aed  mov     rax, [rbx+8]
0x140005af1  test    byte ptr [rcx+rax+3], 0Fh
0x140005af6  jz      short loc_140005B03
0x140005af8  movzx   eax, byte ptr [rcx+rax+3]
0x140005afd  and     eax, 0FFFFFFF0h
0x140005b00  add     r9, rax
0x140005b03  xor     r9, rdx
0x140005b06  mov     rcx, r9; StackCookie
0x140005b09  pop     rbx
0x140005b0a  jmp     __security_check_cookie
```
