# sub_1800AAEC0

- ea: `0x1800aaec0`
- end: `0x1800aaed8`
- name: `sub_1800AAEC0`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ab854`
- `0x1800ac6e0`
- `0x1800ac770`

## callees

- `0x1800aaec0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800aaecd`
- `KERNEL32!DeleteCriticalSection` at `0x1800aaecd`

## pseudocode

```c
void __fastcall sub_1800AAEC0(struct _RTL_CRITICAL_SECTION *a1)
{
  if ( a1->RecursionCount != 252844334 )
    DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x1800aaec0  sub     rsp, 28h
0x1800aaec4  cmp     dword ptr [rcx+0Ch], 0F12192Eh
0x1800aaecb  jz      short loc_1800AAED3
0x1800aaecd  call    cs:__imp_DeleteCriticalSection
0x1800aaed3  add     rsp, 28h
0x1800aaed7  retn
```
