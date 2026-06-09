# __GSHandlerCheckCommon

- ea: `0x18000bd80`
- end: `0x18000bde3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bd5c`

## callees

- `0x1800072e0`
- `0x18000bd80`

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
0x18000bd80  mov     r10, rcx
0x18000bd83  mov     r11, rdx
0x18000bd86  mov     ecx, [r8]
0x18000bd89  and     ecx, 0FFFFFFF8h
0x18000bd8c  test    byte ptr [r8], 4
0x18000bd90  jz      short loc_18000BDA7
0x18000bd92  mov     eax, [r8+8]
0x18000bd96  movsxd  r9, dword ptr [r8+4]
0x18000bd9a  neg     eax
0x18000bd9c  movsxd  rdx, eax
0x18000bd9f  add     r9, r10
0x18000bda2  and     r9, rdx
0x18000bda5  jmp     short loc_18000BDAA
0x18000bda7  mov     r9, r10
0x18000bdaa  movsxd  rax, ecx
0x18000bdad  mov     rdx, [rax+r9]
0x18000bdb1  mov     rax, [r11+10h]
0x18000bdb5  mov     ecx, [rax+8]
0x18000bdb8  mov     rax, [r11+8]
0x18000bdbc  test    byte ptr [rcx+rax+3], 0Fh
0x18000bdc1  jz      short loc_18000BDD5
0x18000bdc3  movzx   eax, byte ptr [rcx+rax+3]
0x18000bdc8  mov     ecx, 0FFFFFFF0h
0x18000bdcd  and     rax, rcx
0x18000bdd0  add     rax, r10
0x18000bdd3  jmp     short loc_18000BDD8
0x18000bdd5  mov     rax, r10
0x18000bdd8  xor     rdx, rax
0x18000bddb  mov     rcx, rdx; StackCookie
0x18000bdde  jmp     __security_check_cookie
```
