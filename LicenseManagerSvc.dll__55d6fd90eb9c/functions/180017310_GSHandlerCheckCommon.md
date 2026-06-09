# __GSHandlerCheckCommon

- ea: `0x180017310`
- end: `0x180017373`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800172ec`
- `0x18001737c`

## callees

- `0x1800033d0`
- `0x180017310`

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
0x180017310  mov     r10, rcx
0x180017313  mov     r11, rdx
0x180017316  mov     ecx, [r8]
0x180017319  and     ecx, 0FFFFFFF8h
0x18001731c  test    byte ptr [r8], 4
0x180017320  jz      short loc_180017337
0x180017322  mov     eax, [r8+8]
0x180017326  movsxd  r9, dword ptr [r8+4]
0x18001732a  neg     eax
0x18001732c  movsxd  rdx, eax
0x18001732f  add     r9, r10
0x180017332  and     r9, rdx
0x180017335  jmp     short loc_18001733A
0x180017337  mov     r9, r10
0x18001733a  movsxd  rax, ecx
0x18001733d  mov     rdx, [rax+r9]
0x180017341  mov     rax, [r11+10h]
0x180017345  mov     ecx, [rax+8]
0x180017348  mov     rax, [r11+8]
0x18001734c  test    byte ptr [rcx+rax+3], 0Fh
0x180017351  jz      short loc_180017365
0x180017353  movzx   eax, byte ptr [rcx+rax+3]
0x180017358  mov     ecx, 0FFFFFFF0h
0x18001735d  and     rax, rcx
0x180017360  add     rax, r10
0x180017363  jmp     short loc_180017368
0x180017365  mov     rax, r10
0x180017368  xor     rdx, rax
0x18001736b  mov     rcx, rdx; StackCookie
0x18001736e  jmp     __security_check_cookie
```
