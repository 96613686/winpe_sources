# FXSAPIFree

- ea: `0x180028b00`
- end: `0x180028b3f`
- name: `FXSAPIFree`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800289a8`

## callees

- `0x18002ba10`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180028b0b`
- `KERNEL32!DeleteCriticalSection` at `0x180028b1e`
- `KERNEL32!DeleteCriticalSection` at `0x180028b0b`
- `KERNEL32!DeleteCriticalSection` at `0x180028b1e`

## pseudocode

```c
__int64 FXSAPIFree()
{
  __int64 result; // rax

  DeleteCriticalSection(&g_CsFaxClientRpc);
  DeleteCriticalSection(&g_CsFaxAssyncInfo);
  result = HeapCleanup();
  dword_1800516E0 = 0;
  return result;
}

```

## disassembly

```asm
0x180028b00  sub     rsp, 28h
0x180028b04  lea     rcx, ?g_CsFaxClientRpc@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180028b0b  call    cs:__imp_DeleteCriticalSection
0x180028b12  nop     dword ptr [rax+rax+00h]
0x180028b17  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180028b1e  call    cs:__imp_DeleteCriticalSection
0x180028b25  nop     dword ptr [rax+rax+00h]
0x180028b2a  call    HeapCleanup
0x180028b2f  mov     cs:dword_1800516E0, 0
0x180028b39  add     rsp, 28h
0x180028b3d  retn
```
