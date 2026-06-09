# CompareFunction

- ea: `0x1800565b0`
- end: `0x1800565d1`
- name: `CompareFunction`
- size: `33`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800565b0`

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
0x1800565b0  mov     r8, [rdx+8F8h]
0x1800565b7  mov     rdx, [rcx+8F8h]
0x1800565be  cmp     rdx, r8
0x1800565c1  jbe     short loc_1800565C8
0x1800565c3  or      eax, 0FFFFFFFFh
0x1800565c6  retn
0x1800565c8  xor     eax, eax
0x1800565ca  cmp     rdx, r8
0x1800565cd  setb    al
0x1800565d0  retn
```
