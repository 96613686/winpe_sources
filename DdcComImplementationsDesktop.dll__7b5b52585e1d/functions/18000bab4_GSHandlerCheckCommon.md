# __GSHandlerCheckCommon

- ea: `0x18000bab4`
- end: `0x18000bb17`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ba90`
- `0x18000bb20`

## callees

- `0x1800016b0`
- `0x18000bab4`

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
0x18000bab4  mov     r10, rcx
0x18000bab7  mov     r11, rdx
0x18000baba  mov     ecx, [r8]
0x18000babd  and     ecx, 0FFFFFFF8h
0x18000bac0  test    byte ptr [r8], 4
0x18000bac4  jz      short loc_18000BADB
0x18000bac6  mov     eax, [r8+8]
0x18000baca  movsxd  r9, dword ptr [r8+4]
0x18000bace  neg     eax
0x18000bad0  movsxd  rdx, eax
0x18000bad3  add     r9, r10
0x18000bad6  and     r9, rdx
0x18000bad9  jmp     short loc_18000BADE
0x18000badb  mov     r9, r10
0x18000bade  movsxd  rax, ecx
0x18000bae1  mov     rdx, [rax+r9]
0x18000bae5  mov     rax, [r11+10h]
0x18000bae9  mov     ecx, [rax+8]
0x18000baec  mov     rax, [r11+8]
0x18000baf0  test    byte ptr [rcx+rax+3], 0Fh
0x18000baf5  jz      short loc_18000BB09
0x18000baf7  movzx   eax, byte ptr [rcx+rax+3]
0x18000bafc  mov     ecx, 0FFFFFFF0h
0x18000bb01  and     rax, rcx
0x18000bb04  add     rax, r10
0x18000bb07  jmp     short loc_18000BB0C
0x18000bb09  mov     rax, r10
0x18000bb0c  xor     rdx, rax
0x18000bb0f  mov     rcx, rdx; StackCookie
0x18000bb12  jmp     __security_check_cookie
```
