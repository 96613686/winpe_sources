# __GSHandlerCheckCommon

- ea: `0x18000608c`
- end: `0x1800060ef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006068`
- `0x1800060f8`

## callees

- `0x180001590`
- `0x18000608c`

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
0x18000608c  mov     r10, rcx
0x18000608f  mov     r11, rdx
0x180006092  mov     ecx, [r8]
0x180006095  and     ecx, 0FFFFFFF8h
0x180006098  test    byte ptr [r8], 4
0x18000609c  jz      short loc_1800060B3
0x18000609e  mov     eax, [r8+8]
0x1800060a2  movsxd  r9, dword ptr [r8+4]
0x1800060a6  neg     eax
0x1800060a8  movsxd  rdx, eax
0x1800060ab  add     r9, r10
0x1800060ae  and     r9, rdx
0x1800060b1  jmp     short loc_1800060B6
0x1800060b3  mov     r9, r10
0x1800060b6  movsxd  rax, ecx
0x1800060b9  mov     rdx, [rax+r9]
0x1800060bd  mov     rax, [r11+10h]
0x1800060c1  mov     ecx, [rax+8]
0x1800060c4  mov     rax, [r11+8]
0x1800060c8  test    byte ptr [rcx+rax+3], 0Fh
0x1800060cd  jz      short loc_1800060E1
0x1800060cf  movzx   eax, byte ptr [rcx+rax+3]
0x1800060d4  mov     ecx, 0FFFFFFF0h
0x1800060d9  and     rax, rcx
0x1800060dc  add     rax, r10
0x1800060df  jmp     short loc_1800060E4
0x1800060e1  mov     rax, r10
0x1800060e4  xor     rdx, rax
0x1800060e7  mov     rcx, rdx; StackCookie
0x1800060ea  jmp     __security_check_cookie
```
