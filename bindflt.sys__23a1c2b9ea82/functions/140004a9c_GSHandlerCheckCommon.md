# __GSHandlerCheckCommon

- ea: `0x140004a9c`
- end: `0x140004b0c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004a78`
- `0x140004b14`

## callees

- `0x140004a9c`
- `0x140004b90`

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
0x140004a9c  sub     rsp, 28h
0x140004aa0  mov     eax, [r8]
0x140004aa3  mov     r10, rcx
0x140004aa6  mov     ecx, eax
0x140004aa8  mov     r11, rdx
0x140004aab  and     ecx, 0FFFFFFF8h
0x140004aae  test    al, 4
0x140004ab0  jz      short loc_140004AC7
0x140004ab2  mov     eax, [r8+8]
0x140004ab6  movsxd  r9, dword ptr [r8+4]
0x140004aba  neg     eax
0x140004abc  movsxd  rdx, eax
0x140004abf  add     r9, r10
0x140004ac2  and     r9, rdx
0x140004ac5  jmp     short loc_140004ACA
0x140004ac7  mov     r9, r10
0x140004aca  movsxd  rax, ecx
0x140004acd  mov     rdx, [rax+r9]
0x140004ad1  mov     rax, [r11+10h]
0x140004ad5  mov     ecx, [rax+8]
0x140004ad8  mov     rax, [r11+8]
0x140004adc  movzx   r8d, byte ptr [rcx+rax+3]
0x140004ae2  test    r8b, 0Fh
0x140004ae6  jz      short loc_140004AF8
0x140004ae8  mov     eax, r8d
0x140004aeb  mov     ecx, 0FFFFFFF0h
0x140004af0  and     rax, rcx
0x140004af3  add     rax, r10
0x140004af6  jmp     short loc_140004AFB
0x140004af8  mov     rax, r10
0x140004afb  xor     rdx, rax
0x140004afe  mov     rcx, rdx; StackCookie
0x140004b01  call    __security_check_cookie
0x140004b06  add     rsp, 28h
0x140004b0a  retn
```
