# __GSHandlerCheckCommon

- ea: `0x18001b94c`
- end: `0x18001b9bc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b928`
- `0x18001b9c4`

## callees

- `0x18001b94c`
- `0x18001baf0`

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
0x18001b94c  sub     rsp, 28h
0x18001b950  mov     eax, [r8]
0x18001b953  mov     r10, rcx
0x18001b956  mov     ecx, eax
0x18001b958  mov     r11, rdx
0x18001b95b  and     ecx, 0FFFFFFF8h
0x18001b95e  test    al, 4
0x18001b960  jz      short loc_18001B977
0x18001b962  mov     eax, [r8+8]
0x18001b966  movsxd  r9, dword ptr [r8+4]
0x18001b96a  neg     eax
0x18001b96c  movsxd  rdx, eax
0x18001b96f  add     r9, r10
0x18001b972  and     r9, rdx
0x18001b975  jmp     short loc_18001B97A
0x18001b977  mov     r9, r10
0x18001b97a  movsxd  rax, ecx
0x18001b97d  mov     rdx, [rax+r9]
0x18001b981  mov     rax, [r11+10h]
0x18001b985  mov     ecx, [rax+8]
0x18001b988  mov     rax, [r11+8]
0x18001b98c  movzx   r8d, byte ptr [rcx+rax+3]
0x18001b992  test    r8b, 0Fh
0x18001b996  jz      short loc_18001B9A8
0x18001b998  mov     eax, r8d
0x18001b99b  mov     ecx, 0FFFFFFF0h
0x18001b9a0  and     rax, rcx
0x18001b9a3  add     rax, r10
0x18001b9a6  jmp     short loc_18001B9AB
0x18001b9a8  mov     rax, r10
0x18001b9ab  xor     rdx, rax
0x18001b9ae  mov     rcx, rdx; StackCookie
0x18001b9b1  call    __security_check_cookie
0x18001b9b6  add     rsp, 28h
0x18001b9ba  retn
```
