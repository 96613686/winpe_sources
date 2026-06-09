# __GSHandlerCheckCommon

- ea: `0x180002940`
- end: `0x1800029a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000291c`
- `0x18000bcc4`

## callees

- `0x180002200`
- `0x180002940`

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
0x180002940  mov     r10, rcx
0x180002943  mov     r11, rdx
0x180002946  mov     ecx, [r8]
0x180002949  and     ecx, 0FFFFFFF8h
0x18000294c  test    byte ptr [r8], 4
0x180002950  jz      short loc_180002967
0x180002952  mov     eax, [r8+8]
0x180002956  movsxd  r9, dword ptr [r8+4]
0x18000295a  neg     eax
0x18000295c  movsxd  rdx, eax
0x18000295f  add     r9, r10
0x180002962  and     r9, rdx
0x180002965  jmp     short loc_18000296A
0x180002967  mov     r9, r10
0x18000296a  movsxd  rax, ecx
0x18000296d  mov     rdx, [rax+r9]
0x180002971  mov     rax, [r11+10h]
0x180002975  mov     ecx, [rax+8]
0x180002978  mov     rax, [r11+8]
0x18000297c  test    byte ptr [rcx+rax+3], 0Fh
0x180002981  jz      short loc_180002995
0x180002983  movzx   eax, byte ptr [rcx+rax+3]
0x180002988  mov     ecx, 0FFFFFFF0h
0x18000298d  and     rax, rcx
0x180002990  add     rax, r10
0x180002993  jmp     short loc_180002998
0x180002995  mov     rax, r10
0x180002998  xor     rdx, rax
0x18000299b  mov     rcx, rdx; StackCookie
0x18000299e  jmp     __security_check_cookie
```
