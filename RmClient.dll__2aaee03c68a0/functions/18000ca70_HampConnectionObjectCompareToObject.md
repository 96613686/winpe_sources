# HampConnectionObjectCompareToObject

- ea: `0x18000ca70`
- end: `0x18000ca8e`
- name: `HampConnectionObjectCompareToObject`
- size: `30`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ca70`

## pseudocode

```c
__int64 __fastcall HampConnectionObjectCompareToObject(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // rax

  v2 = *(_QWORD *)(a2 + 48);
  v3 = *(_QWORD *)(a1 + 48);
  if ( v3 < v2 )
    return 0xFFFFFFFFLL;
  else
    return v3 > v2;
}

```

## disassembly

```asm
0x18000ca70  mov     r8, [rdx+30h]
0x18000ca74  mov     rax, [rcx+30h]
0x18000ca78  cmp     rax, r8
0x18000ca7b  jb      short loc_18000CA88
0x18000ca7d  xor     ecx, ecx
0x18000ca7f  cmp     rax, r8
0x18000ca82  setnbe  cl
0x18000ca85  mov     eax, ecx
0x18000ca87  retn
0x18000ca88  mov     eax, 0FFFFFFFFh
0x18000ca8d  retn
```
