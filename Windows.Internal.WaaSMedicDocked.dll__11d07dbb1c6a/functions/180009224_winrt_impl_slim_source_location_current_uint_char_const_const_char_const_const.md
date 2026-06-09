# winrt::impl::slim_source_location::current(uint,char const * const,char const * const)

- ea: `0x180009224`
- end: `0x180009234`
- name: `?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z`
- size: `16`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800071d0`
- `0x180008230`
- `0x180009144`
- `0x1800097e0`

## pseudocode

```c
__int64 __fastcall winrt::impl::slim_source_location::current(__int64 a1)
{
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  return a1;
}

```

## disassembly

```asm
0x180009224  xor     eax, eax
0x180009226  mov     [rcx], eax
0x180009228  mov     [rcx+8], rax
0x18000922c  mov     [rcx+10h], rax
0x180009230  mov     rax, rcx
0x180009233  retn
```
