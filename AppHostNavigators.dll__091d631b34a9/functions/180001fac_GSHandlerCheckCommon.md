# __GSHandlerCheckCommon

- ea: `0x180001fac`
- end: `0x18000200f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f88`
- `0x180012f80`
- `0x180012fe8`

## callees

- `0x180001fac`
- `0x1800130a0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x180001fac  mov     r10, rcx
0x180001faf  mov     r11, rdx
0x180001fb2  mov     ecx, [r8]
0x180001fb5  and     ecx, 0FFFFFFF8h
0x180001fb8  test    byte ptr [r8], 4
0x180001fbc  jz      short loc_180001FD3
0x180001fbe  mov     eax, [r8+8]
0x180001fc2  movsxd  r9, dword ptr [r8+4]
0x180001fc6  neg     eax
0x180001fc8  movsxd  rdx, eax
0x180001fcb  add     r9, r10
0x180001fce  and     r9, rdx
0x180001fd1  jmp     short loc_180001FD6
0x180001fd3  mov     r9, r10
0x180001fd6  movsxd  rax, ecx
0x180001fd9  mov     rdx, [rax+r9]
0x180001fdd  mov     rax, [r11+10h]
0x180001fe1  mov     ecx, [rax+8]
0x180001fe4  mov     rax, [r11+8]
0x180001fe8  test    byte ptr [rcx+rax+3], 0Fh
0x180001fed  jz      short loc_180002001
0x180001fef  movzx   eax, byte ptr [rcx+rax+3]
0x180001ff4  mov     ecx, 0FFFFFFF0h
0x180001ff9  and     rax, rcx
0x180001ffc  add     rax, r10
0x180001fff  jmp     short loc_180002004
0x180002001  mov     rax, r10
0x180002004  xor     rdx, rax
0x180002007  mov     rcx, rdx; StackCookie
0x18000200a  jmp     __security_check_cookie
```
