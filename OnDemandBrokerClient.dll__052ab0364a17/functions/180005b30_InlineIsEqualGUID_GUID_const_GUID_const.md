# InlineIsEqualGUID(_GUID const &,_GUID const &)

- ea: `0x180005b30`
- end: `0x180005b57`
- name: `?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z`
- size: `39`
- prototype: `_BOOL8 __fastcall(const struct _GUID *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004eac`
- `0x180005ea0`

## callees

- `0x180005b30`

## pseudocode

```c
_BOOL8 __fastcall InlineIsEqualGUID(const struct _GUID *a1, const struct _GUID *a2)
{
  return a1->Data1 == a2->Data1
      && *(_DWORD *)&a1->Data2 == *(_DWORD *)&a2->Data2
      && *(_DWORD *)a1->Data4 == *(_DWORD *)a2->Data4
      && *(_DWORD *)&a1->Data4[4] == *(_DWORD *)&a2->Data4[4];
}

```

## disassembly

```asm
0x180005b30  mov     eax, [rdx]
0x180005b32  cmp     [rcx], eax
0x180005b34  jnz     short loc_180005B54
0x180005b36  mov     eax, [rdx+4]
0x180005b39  cmp     [rcx+4], eax
0x180005b3c  jnz     short loc_180005B54
0x180005b3e  mov     eax, [rdx+8]
0x180005b41  cmp     [rcx+8], eax
0x180005b44  jnz     short loc_180005B54
0x180005b46  mov     eax, [rdx+0Ch]
0x180005b49  cmp     [rcx+0Ch], eax
0x180005b4c  jnz     short loc_180005B54
0x180005b4e  mov     eax, 1
0x180005b53  retn
0x180005b54  xor     eax, eax
0x180005b56  retn
```
