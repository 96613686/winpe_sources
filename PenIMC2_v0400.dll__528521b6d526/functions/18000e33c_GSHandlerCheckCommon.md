# __GSHandlerCheckCommon

- ea: `0x18000e33c`
- end: `0x18000e397`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e31c`
- `0x18000e398`

## callees

- `0x18000cdb0`
- `0x18000e33c`

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
0x18000e33c  push    rbx
0x18000e33e  mov     r11d, [r8]
0x18000e341  mov     rbx, rdx
0x18000e344  and     r11d, 0FFFFFFF8h
0x18000e348  mov     r9, rcx
0x18000e34b  test    byte ptr [r8], 4
0x18000e34f  mov     r10, rcx
0x18000e352  jz      short loc_18000E367
0x18000e354  mov     eax, [r8+8]
0x18000e358  movsxd  r10, dword ptr [r8+4]
0x18000e35c  neg     eax
0x18000e35e  add     r10, rcx
0x18000e361  movsxd  rcx, eax
0x18000e364  and     r10, rcx
0x18000e367  movsxd  rax, r11d
0x18000e36a  mov     rdx, [rax+r10]
0x18000e36e  mov     rax, [rbx+10h]
0x18000e372  mov     ecx, [rax+8]
0x18000e375  mov     rax, [rbx+8]
0x18000e379  test    byte ptr [rcx+rax+3], 0Fh
0x18000e37e  jz      short loc_18000E38B
0x18000e380  movzx   eax, byte ptr [rcx+rax+3]
0x18000e385  and     eax, 0FFFFFFF0h
0x18000e388  add     r9, rax
0x18000e38b  xor     r9, rdx
0x18000e38e  mov     rcx, r9; StackCookie
0x18000e391  pop     rbx
0x18000e392  jmp     __security_check_cookie
```
