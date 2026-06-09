# FreeFileNode(sFNAME *)

- ea: `0x180011c90`
- end: `0x180011cb1`
- name: `?FreeFileNode@@YAXPEAUsFNAME@@@Z`
- size: `33`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180011dc0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180011c9c`
- `ole32!CoTaskMemFree` at `0x180011c9c`
- `ole32!CoTaskMemFree` at `0x180011caa`

## pseudocode

```c
void __fastcall FreeFileNode(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x180011c90  push    rbx
0x180011c92  sub     rsp, 20h
0x180011c96  mov     rbx, rcx
0x180011c99  mov     rcx, [rcx]; pv
0x180011c9c  call    cs:__imp_CoTaskMemFree
0x180011ca2  mov     rcx, rbx
0x180011ca5  add     rsp, 20h
0x180011ca9  pop     rbx
0x180011caa  jmp     cs:__imp_CoTaskMemFree
```
