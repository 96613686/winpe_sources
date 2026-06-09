# __GSHandlerCheckCommon

- ea: `0x180035880`
- end: `0x1800358e0`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035860`
- `0x1800358e0`
- `0x180035c60`

## callees

- `0x180034ef0`
- `0x180035880`

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
0x180035880  push    rbx
0x180035882  mov     r11d, [r8]
0x180035885  mov     rbx, rdx
0x180035888  and     r11d, 0FFFFFFF8h
0x18003588c  mov     r9, rcx
0x18003588f  test    byte ptr [r8], 4
0x180035893  mov     r10, rcx
0x180035896  jz      short loc_1800358AB
0x180035898  mov     eax, [r8+8]
0x18003589c  movsxd  r10, dword ptr [r8+4]
0x1800358a0  neg     eax
0x1800358a2  add     r10, rcx
0x1800358a5  movsxd  rcx, eax
0x1800358a8  and     r10, rcx
0x1800358ab  movsxd  rax, r11d
0x1800358ae  mov     rdx, [rax+r10]
0x1800358b2  mov     rax, [rbx+10h]
0x1800358b6  mov     ecx, [rax+8]
0x1800358b9  mov     rax, [rbx+8]
0x1800358bd  test    byte ptr [rcx+rax+3], 0Fh
0x1800358c2  jz      short loc_1800358D4
0x1800358c4  movzx   eax, byte ptr [rcx+rax+3]
0x1800358c9  mov     ecx, 0FFFFFFF0h
0x1800358ce  and     rax, rcx
0x1800358d1  add     r9, rax
0x1800358d4  xor     r9, rdx
0x1800358d7  mov     rcx, r9; StackCookie
0x1800358da  pop     rbx
0x1800358db  jmp     __security_check_cookie
```
