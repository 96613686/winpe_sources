# CCachingPathIterator::bEnum(_PATHDATA *)

- ea: `0x18003e480`
- end: `0x18003e49a`
- name: `?bEnum@CCachingPathIterator@@UEAAHPEAU_PATHDATA@@@Z`
- size: `26`
- prototype: `__int64 __fastcall(CCachingPathIterator *__hidden this, struct _PATHDATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003e480`
- `0x1800455ac`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18003e493`

## pseudocode

```c
int __fastcall CCachingPathIterator::bEnum(PATHOBJ **this, struct _PATHDATA *a2)
{
  if ( *((_DWORD *)this + 10) )
    return CPathCache::bEnum((CPathCache *)(this + 3), a2);
  else
    return PATHOBJ_bEnum(this[1], a2);
}

```

## disassembly

```asm
0x18003e480  cmp     dword ptr [rcx+28h], 0
0x18003e484  jz      short loc_18003E48F
0x18003e486  add     rcx, 18h; this
0x18003e48a  jmp     ?bEnum@CPathCache@@QEAAHPEAU_PATHDATA@@@Z; CPathCache::bEnum(_PATHDATA *)
0x18003e48f  mov     rcx, [rcx+8]
0x18003e493  jmp     cs:__imp_PATHOBJ_bEnum
```
