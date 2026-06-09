# CompareFunction

- ea: `0x180031a90`
- end: `0x180031ab1`
- name: `CompareFunction`
- size: `33`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180031a90`

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
0x180031a90  mov     r8, [rdx+8F8h]
0x180031a97  mov     rdx, [rcx+8F8h]
0x180031a9e  cmp     rdx, r8
0x180031aa1  jbe     short loc_180031AA8
0x180031aa3  or      eax, 0FFFFFFFFh
0x180031aa6  retn
0x180031aa8  xor     eax, eax
0x180031aaa  cmp     rdx, r8
0x180031aad  setb    al
0x180031ab0  retn
```
