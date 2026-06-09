# __GSHandlerCheckCommon

- ea: `0x180009e68`
- end: `0x180009ecb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e44`
- `0x180009ed4`

## callees

- `0x180001610`
- `0x180009e68`

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
0x180009e68  mov     r10, rcx
0x180009e6b  mov     r11, rdx
0x180009e6e  mov     ecx, [r8]
0x180009e71  and     ecx, 0FFFFFFF8h
0x180009e74  test    byte ptr [r8], 4
0x180009e78  jz      short loc_180009E8F
0x180009e7a  mov     eax, [r8+8]
0x180009e7e  movsxd  r9, dword ptr [r8+4]
0x180009e82  neg     eax
0x180009e84  movsxd  rdx, eax
0x180009e87  add     r9, r10
0x180009e8a  and     r9, rdx
0x180009e8d  jmp     short loc_180009E92
0x180009e8f  mov     r9, r10
0x180009e92  movsxd  rax, ecx
0x180009e95  mov     rdx, [rax+r9]
0x180009e99  mov     rax, [r11+10h]
0x180009e9d  mov     ecx, [rax+8]
0x180009ea0  mov     rax, [r11+8]
0x180009ea4  test    byte ptr [rcx+rax+3], 0Fh
0x180009ea9  jz      short loc_180009EBD
0x180009eab  movzx   eax, byte ptr [rcx+rax+3]
0x180009eb0  mov     ecx, 0FFFFFFF0h
0x180009eb5  and     rax, rcx
0x180009eb8  add     rax, r10
0x180009ebb  jmp     short loc_180009EC0
0x180009ebd  mov     rax, r10
0x180009ec0  xor     rdx, rax
0x180009ec3  mov     rcx, rdx; StackCookie
0x180009ec6  jmp     __security_check_cookie
```
