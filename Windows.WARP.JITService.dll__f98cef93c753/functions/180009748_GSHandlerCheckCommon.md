# __GSHandlerCheckCommon

- ea: `0x180009748`
- end: `0x1800097ab`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009724`
- `0x1800097b4`

## callees

- `0x180008a80`
- `0x180009748`

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
0x180009748  mov     r10, rcx
0x18000974b  mov     r11, rdx
0x18000974e  mov     ecx, [r8]
0x180009751  and     ecx, 0FFFFFFF8h
0x180009754  test    byte ptr [r8], 4
0x180009758  jz      short loc_18000976F
0x18000975a  mov     eax, [r8+8]
0x18000975e  movsxd  r9, dword ptr [r8+4]
0x180009762  neg     eax
0x180009764  movsxd  rdx, eax
0x180009767  add     r9, r10
0x18000976a  and     r9, rdx
0x18000976d  jmp     short loc_180009772
0x18000976f  mov     r9, r10
0x180009772  movsxd  rax, ecx
0x180009775  mov     rdx, [rax+r9]
0x180009779  mov     rax, [r11+10h]
0x18000977d  mov     ecx, [rax+8]
0x180009780  mov     rax, [r11+8]
0x180009784  test    byte ptr [rcx+rax+3], 0Fh
0x180009789  jz      short loc_18000979D
0x18000978b  movzx   eax, byte ptr [rcx+rax+3]
0x180009790  mov     ecx, 0FFFFFFF0h
0x180009795  and     rax, rcx
0x180009798  add     rax, r10
0x18000979b  jmp     short loc_1800097A0
0x18000979d  mov     rax, r10
0x1800097a0  xor     rdx, rax
0x1800097a3  mov     rcx, rdx; StackCookie
0x1800097a6  jmp     __security_check_cookie
```
