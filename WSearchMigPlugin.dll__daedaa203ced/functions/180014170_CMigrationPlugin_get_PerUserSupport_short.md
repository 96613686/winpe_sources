# CMigrationPlugin::get_PerUserSupport(short *)

- ea: `0x180014170`
- end: `0x18001417d`
- name: `?get_PerUserSupport@CMigrationPlugin@@UEAAJPEAF@Z`
- size: `13`
- prototype: `__int64 __fastcall(CMigrationPlugin *__hidden this, __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014190`
- `0x1800141a0`
- `0x1800141b0`
- `0x1800141c0`

## callees

- `0x180014170`

## pseudocode

```c
__int64 __fastcall CMigrationPlugin::get_PerUserSupport(CMigrationPlugin *this, __int16 *a2)
{
  if ( a2 )
    *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180014170  test    rdx, rdx
0x180014173  jz      short loc_18001417A
0x180014175  xor     eax, eax
0x180014177  mov     [rdx], ax
0x18001417a  xor     eax, eax
0x18001417c  retn
```
