# CCachingPathIterator::bEnum(_PATHDATA *)

- ea: `0x18003f580`
- end: `0x18003f59a`
- name: `?bEnum@CCachingPathIterator@@UEAAHPEAU_PATHDATA@@@Z`
- size: `26`
- prototype: `int __fastcall(PATHOBJ **this, struct _PATHDATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003f580`
- `0x1800468ec`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18003f593`

## pseudocode

```c
BOOL __fastcall CCachingPathIterator::bEnum(PATHOBJ **this, struct _PATHDATA *a2)
{
  if ( *((_DWORD *)this + 10) )
    return CPathCache::bEnum((CPathCache *)(this + 3), a2);
  else
    return PATHOBJ_bEnum(this[1], a2);
}

```

## disassembly

```asm
0x18003f580  cmp     dword ptr [rcx+28h], 0
0x18003f584  jz      short loc_18003F58F
0x18003f586  add     rcx, 18h; this
0x18003f58a  jmp     ?bEnum@CPathCache@@QEAAHPEAU_PATHDATA@@@Z; CPathCache::bEnum(_PATHDATA *)
0x18003f58f  mov     rcx, [rcx+8]
0x18003f593  jmp     cs:__imp_PATHOBJ_bEnum
```
