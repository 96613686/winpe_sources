# __GSHandlerCheckCommon

- ea: `0x140013e84`
- end: `0x140013ee4`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013e64`
- `0x140014bcc`

## callees

- `0x1400137e0`
- `0x140013e84`

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
0x140013e84  push    rbx
0x140013e86  mov     r11d, [r8]
0x140013e89  mov     rbx, rdx
0x140013e8c  and     r11d, 0FFFFFFF8h
0x140013e90  mov     r9, rcx
0x140013e93  test    byte ptr [r8], 4
0x140013e97  mov     r10, rcx
0x140013e9a  jz      short loc_140013EAF
0x140013e9c  mov     eax, [r8+8]
0x140013ea0  movsxd  r10, dword ptr [r8+4]
0x140013ea4  neg     eax
0x140013ea6  add     r10, rcx
0x140013ea9  movsxd  rcx, eax
0x140013eac  and     r10, rcx
0x140013eaf  movsxd  rax, r11d
0x140013eb2  mov     rdx, [rax+r10]
0x140013eb6  mov     rax, [rbx+10h]
0x140013eba  mov     ecx, [rax+8]
0x140013ebd  mov     rax, [rbx+8]
0x140013ec1  test    byte ptr [rcx+rax+3], 0Fh
0x140013ec6  jz      short loc_140013ED8
0x140013ec8  movzx   eax, byte ptr [rcx+rax+3]
0x140013ecd  mov     ecx, 0FFFFFFF0h
0x140013ed2  and     rax, rcx
0x140013ed5  add     r9, rax
0x140013ed8  xor     r9, rdx
0x140013edb  mov     rcx, r9; StackCookie
0x140013ede  pop     rbx
0x140013edf  jmp     __security_check_cookie
```
