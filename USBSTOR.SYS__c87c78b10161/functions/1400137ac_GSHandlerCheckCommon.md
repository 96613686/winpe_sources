# __GSHandlerCheckCommon

- ea: `0x1400137ac`
- end: `0x14001381c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013788`
- `0x140013824`

## callees

- `0x1400137ac`
- `0x140013950`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x1400137ac  sub     rsp, 28h
0x1400137b0  mov     eax, [r8]
0x1400137b3  mov     r10, rcx
0x1400137b6  mov     ecx, eax
0x1400137b8  mov     r11, rdx
0x1400137bb  and     ecx, 0FFFFFFF8h
0x1400137be  test    al, 4
0x1400137c0  jz      short loc_1400137D7
0x1400137c2  mov     eax, [r8+8]
0x1400137c6  movsxd  r9, dword ptr [r8+4]
0x1400137ca  neg     eax
0x1400137cc  movsxd  rdx, eax
0x1400137cf  add     r9, r10
0x1400137d2  and     r9, rdx
0x1400137d5  jmp     short loc_1400137DA
0x1400137d7  mov     r9, r10
0x1400137da  movsxd  rax, ecx
0x1400137dd  mov     rdx, [rax+r9]
0x1400137e1  mov     rax, [r11+10h]
0x1400137e5  mov     ecx, [rax+8]
0x1400137e8  mov     rax, [r11+8]
0x1400137ec  movzx   r8d, byte ptr [rcx+rax+3]
0x1400137f2  test    r8b, 0Fh
0x1400137f6  jz      short loc_140013808
0x1400137f8  mov     eax, r8d
0x1400137fb  mov     ecx, 0FFFFFFF0h
0x140013800  and     rax, rcx
0x140013803  add     rax, r10
0x140013806  jmp     short loc_14001380B
0x140013808  mov     rax, r10
0x14001380b  xor     rdx, rax
0x14001380e  mov     rcx, rdx; StackCookie
0x140013811  call    __security_check_cookie
0x140013816  add     rsp, 28h
0x14001381a  retn
```
