# __GSHandlerCheckCommon

- ea: `0x140003068`
- end: `0x1400030c8`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003048`
- `0x1400030cc`

## callees

- `0x140001000`
- `0x140003068`

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
0x140003068  push    rbx
0x14000306a  mov     r11d, [r8]
0x14000306d  mov     rbx, rdx
0x140003070  and     r11d, 0FFFFFFF8h
0x140003074  mov     r9, rcx
0x140003077  test    byte ptr [r8], 4
0x14000307b  mov     r10, rcx
0x14000307e  jz      short loc_140003093
0x140003080  mov     eax, [r8+8]
0x140003084  movsxd  r10, dword ptr [r8+4]
0x140003088  neg     eax
0x14000308a  add     r10, rcx
0x14000308d  movsxd  rcx, eax
0x140003090  and     r10, rcx
0x140003093  movsxd  rax, r11d
0x140003096  mov     rdx, [rax+r10]
0x14000309a  mov     rax, [rbx+10h]
0x14000309e  mov     ecx, [rax+8]
0x1400030a1  mov     rax, [rbx+8]
0x1400030a5  test    byte ptr [rcx+rax+3], 0Fh
0x1400030aa  jz      short loc_1400030BC
0x1400030ac  movzx   eax, byte ptr [rcx+rax+3]
0x1400030b1  mov     ecx, 0FFFFFFF0h
0x1400030b6  and     rax, rcx
0x1400030b9  add     r9, rax
0x1400030bc  xor     r9, rdx
0x1400030bf  mov     rcx, r9; StackCookie
0x1400030c2  pop     rbx
0x1400030c3  jmp     __security_check_cookie
```
