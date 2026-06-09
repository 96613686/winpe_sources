# InlineIsEqualGUID(_GUID const &,_GUID const &)

- ea: `0x18000532c`
- end: `0x180005353`
- name: `?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z`
- size: `39`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180004460`
- `0x1800044a8`
- `0x180004528`
- `0x1800045a8`
- `0x1800045dc`
- `0x180005840`
- `0x1800058f0`
- `0x1800059a0`
- `0x180005a20`
- `0x180005ae0`
- `0x1800071d0`
- `0x180007720`
- `0x18000a400`

## callees

- `0x18000532c`

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
0x18000532c  mov     eax, [rdx]
0x18000532e  cmp     [rcx], eax
0x180005330  jnz     short loc_180005350
0x180005332  mov     eax, [rdx+4]
0x180005335  cmp     [rcx+4], eax
0x180005338  jnz     short loc_180005350
0x18000533a  mov     eax, [rdx+8]
0x18000533d  cmp     [rcx+8], eax
0x180005340  jnz     short loc_180005350
0x180005342  mov     eax, [rdx+0Ch]
0x180005345  cmp     [rcx+0Ch], eax
0x180005348  jnz     short loc_180005350
0x18000534a  mov     eax, 1
0x18000534f  retn
0x180005350  xor     eax, eax
0x180005352  retn
```
