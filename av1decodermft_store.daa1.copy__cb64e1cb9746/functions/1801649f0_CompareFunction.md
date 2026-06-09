# CompareFunction

- ea: `0x1801649f0`
- end: `0x180164a11`
- name: `CompareFunction`
- size: `33`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1801649f0`

## pseudocode

```c
__int64 __fastcall CompareFunction(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // rdx

  v2 = a2[287];
  v3 = a1[287];
  if ( v3 <= v2 )
    return v3 < v2;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1801649f0  mov     r8, [rdx+8F8h]
0x1801649f7  mov     rdx, [rcx+8F8h]
0x1801649fe  cmp     rdx, r8
0x180164a01  jbe     short loc_180164A08
0x180164a03  or      eax, 0FFFFFFFFh
0x180164a06  retn
0x180164a08  xor     eax, eax
0x180164a0a  cmp     rdx, r8
0x180164a0d  setb    al
0x180164a10  retn
```
