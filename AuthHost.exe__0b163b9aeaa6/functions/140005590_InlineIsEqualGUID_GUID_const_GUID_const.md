# InlineIsEqualGUID(_GUID const &,_GUID const &)

- ea: `0x140005590`
- end: `0x1400055b7`
- name: `?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z`
- size: `39`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140004a10`
- `0x140005780`
- `0x140007fd0`
- `0x140008030`
- `0x140008090`
- `0x1400080f0`
- `0x14000852c`
- `0x14000b420`

## callees

- `0x140005590`

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
0x140005590  mov     eax, [rdx]
0x140005592  cmp     [rcx], eax
0x140005594  jnz     short loc_1400055B4
0x140005596  mov     eax, [rdx+4]
0x140005599  cmp     [rcx+4], eax
0x14000559c  jnz     short loc_1400055B4
0x14000559e  mov     eax, [rdx+8]
0x1400055a1  cmp     [rcx+8], eax
0x1400055a4  jnz     short loc_1400055B4
0x1400055a6  mov     eax, [rdx+0Ch]
0x1400055a9  cmp     [rcx+0Ch], eax
0x1400055ac  jnz     short loc_1400055B4
0x1400055ae  mov     eax, 1
0x1400055b3  retn
0x1400055b4  xor     eax, eax
0x1400055b6  retn
```
