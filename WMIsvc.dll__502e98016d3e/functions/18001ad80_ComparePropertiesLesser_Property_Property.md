# ComparePropertiesLesser(_Property *,_Property *)

- ea: `0x18001ad80`
- end: `0x18001ada1`
- name: `?ComparePropertiesLesser@@YA_NPEAU_Property@@0@Z`
- size: `33`
- prototype: `bool __fastcall(struct _Property *, struct _Property *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a508`
- `0x18001a5c4`
- `0x18001a640`
- `0x18001a834`

## callees

- `0x18001ad80`

## pseudocode

```c
bool __fastcall ComparePropertiesLesser(struct _Property *a1, struct _Property *a2)
{
  if ( !a1 )
  {
    if ( !a2 )
      return 0;
    return a1 < a2;
  }
  if ( !a2 )
    return a1 < a2;
  return *((_DWORD *)a1 + 8) < *((_DWORD *)a2 + 8);
}

```

## disassembly

```asm
0x18001ad80  test    rcx, rcx
0x18001ad83  jnz     short loc_18001AD8D
0x18001ad85  test    rdx, rdx
0x18001ad88  jnz     short loc_18001AD9A
0x18001ad8a  xor     al, al
0x18001ad8c  retn
0x18001ad8d  test    rdx, rdx
0x18001ad90  jz      short loc_18001AD9A
0x18001ad92  mov     eax, [rdx+20h]
0x18001ad95  cmp     [rcx+20h], eax
0x18001ad98  jmp     short loc_18001AD9D
0x18001ad9a  cmp     rcx, rdx
0x18001ad9d  setb    al
0x18001ada0  retn
```
