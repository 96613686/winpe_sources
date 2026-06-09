# InlineIsEqualGUID(_GUID const &,_GUID const &)

- ea: `0x18000c070`
- end: `0x18000c097`
- name: `?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z`
- size: `39`
- prototype: `_BOOL8 __fastcall(const struct _GUID *, const struct _GUID *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a950`
- `0x18000b220`
- `0x18000cf80`
- `0x180017ae4`
- `0x180018950`
- `0x1800189f0`
- `0x180018a90`
- `0x180018af0`

## callees

- `0x18000c070`

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
0x18000c070  mov     eax, [rdx]
0x18000c072  cmp     [rcx], eax
0x18000c074  jz      short loc_18000C079
0x18000c076  xor     eax, eax
0x18000c078  retn
0x18000c079  mov     eax, [rdx+4]
0x18000c07c  cmp     [rcx+4], eax
0x18000c07f  jnz     short loc_18000C076
0x18000c081  mov     eax, [rdx+8]
0x18000c084  cmp     [rcx+8], eax
0x18000c087  jnz     short loc_18000C076
0x18000c089  mov     eax, [rdx+0Ch]
0x18000c08c  cmp     [rcx+0Ch], eax
0x18000c08f  jnz     short loc_18000C076
0x18000c091  mov     eax, 1
0x18000c096  retn
```
