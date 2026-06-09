# handle_beginning_of_uncompressed_block

- ea: `0x1400111f0`
- end: `0x140011259`
- name: `handle_beginning_of_uncompressed_block`
- size: `105`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000271c`

## callees

- `0x1400111f0`

## pseudocode

```c
__int64 __fastcall handle_beginning_of_uncompressed_block(__int64 a1)
{
  unsigned __int8 *v2; // rcx
  __int64 i; // r9

  *(_QWORD *)(a1 + 11016) -= 2LL;
  v2 = *(unsigned __int8 **)(a1 + 11016);
  if ( (unsigned __int64)(v2 + 12) >= *(_QWORD *)(a1 + 11024) )
    return 0;
  for ( i = 0; i != 3; ++i )
  {
    *(_DWORD *)(a1 + 4 * i + 16) = *v2 | ((v2[1] | (*((unsigned __int16 *)v2 + 1) << 8)) << 8);
    v2 = (unsigned __int8 *)(*(_QWORD *)(a1 + 11016) + 4LL);
    *(_QWORD *)(a1 + 11016) = v2;
  }
  return 1;
}

```

## disassembly

```asm
0x1400111f0  add     qword ptr [rcx+2B08h], 0FFFFFFFFFFFFFFFEh
0x1400111f8  mov     r8, rcx
0x1400111fb  mov     rcx, [rcx+2B08h]
0x140011202  lea     rax, [rcx+0Ch]
0x140011206  cmp     rax, [r8+2B10h]
0x14001120d  jb      short loc_140011213
0x14001120f  xor     eax, eax
0x140011211  retn
0x140011213  xor     r9d, r9d
0x140011216  movzx   eax, byte ptr [rcx+2]
0x14001121a  movzx   edx, byte ptr [rcx+3]
0x14001121e  shl     edx, 8
0x140011221  or      edx, eax
0x140011223  movzx   eax, byte ptr [rcx+1]
0x140011227  movzx   ecx, byte ptr [rcx]
0x14001122a  shl     edx, 8
0x14001122d  or      edx, eax
0x14001122f  shl     edx, 8
0x140011232  or      edx, ecx
0x140011234  mov     [r8+r9*4+10h], edx
0x140011239  inc     r9
0x14001123c  mov     rcx, [r8+2B08h]
0x140011243  add     rcx, 4
0x140011247  mov     [r8+2B08h], rcx
0x14001124e  cmp     r9, 3
0x140011252  jnz     short loc_140011216
0x140011254  lea     eax, [r9-2]
0x140011258  retn
```
