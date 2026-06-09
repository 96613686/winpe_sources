# CFilterIgnoreSet::LPCWStrCompare::operator()(ushort const *,ushort const *)

- ea: `0x1800174a4`
- end: `0x1800174bc`
- name: `??RLPCWStrCompare@CFilterIgnoreSet@@QEBA_NPEBG0@Z`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d380`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800174ae`
- `msvcrt!_wcsicmp` at `0x1800174ae`

## pseudocode

```c
__int64 __fastcall CFilterIgnoreSet::LPCWStrCompare::operator()(__int64 a1, const wchar_t *a2, const wchar_t *a3)
{
  return (unsigned int)_wcsicmp(a2, a3) >> 31;
}

```

## disassembly

```asm
0x1800174a4  sub     rsp, 28h
0x1800174a8  mov     rcx, rdx; String1
0x1800174ab  mov     rdx, r8; String2
0x1800174ae  call    cs:__imp__wcsicmp
0x1800174b4  shr     eax, 1Fh
0x1800174b7  add     rsp, 28h
0x1800174bb  retn
```
