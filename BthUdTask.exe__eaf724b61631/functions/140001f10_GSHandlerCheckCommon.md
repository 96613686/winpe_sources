# __GSHandlerCheckCommon

- ea: `0x140001f10`
- end: `0x140001f73`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001eec`
- `0x140001f7c`

## callees

- `0x140001f10`
- `0x140002010`

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
0x140001f10  mov     r10, rcx
0x140001f13  mov     r11, rdx
0x140001f16  mov     ecx, [r8]
0x140001f19  and     ecx, 0FFFFFFF8h
0x140001f1c  test    byte ptr [r8], 4
0x140001f20  jz      short loc_140001F37
0x140001f22  mov     eax, [r8+8]
0x140001f26  movsxd  r9, dword ptr [r8+4]
0x140001f2a  neg     eax
0x140001f2c  movsxd  rdx, eax
0x140001f2f  add     r9, r10
0x140001f32  and     r9, rdx
0x140001f35  jmp     short loc_140001F3A
0x140001f37  mov     r9, r10
0x140001f3a  movsxd  rax, ecx
0x140001f3d  mov     rdx, [rax+r9]
0x140001f41  mov     rax, [r11+10h]
0x140001f45  mov     ecx, [rax+8]
0x140001f48  mov     rax, [r11+8]
0x140001f4c  test    byte ptr [rcx+rax+3], 0Fh
0x140001f51  jz      short loc_140001F65
0x140001f53  movzx   eax, byte ptr [rcx+rax+3]
0x140001f58  mov     ecx, 0FFFFFFF0h
0x140001f5d  and     rax, rcx
0x140001f60  add     rax, r10
0x140001f63  jmp     short loc_140001F68
0x140001f65  mov     rax, r10
0x140001f68  xor     rdx, rax
0x140001f6b  mov     rcx, rdx; StackCookie
0x140001f6e  jmp     __security_check_cookie
```
