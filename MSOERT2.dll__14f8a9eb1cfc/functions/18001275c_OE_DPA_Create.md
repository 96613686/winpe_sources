# OE_DPA_Create

- ea: `0x18001275c`
- end: `0x180012789`
- name: `OE_DPA_Create`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a420`

## callees

- `0x18001275c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180012772`
- `KERNEL32!HeapAlloc` at `0x180012772`
- `KERNEL32!GetProcessHeap` at `0x180012760`
- `KERNEL32!GetProcessHeap` at `0x180012760`

## pseudocode

```c
_DWORD *OE_DPA_Create()
{
  HANDLE ProcessHeap; // rax
  _DWORD *result; // rax

  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 8u, 0x18u);
  if ( result )
    result[5] = 8;
  return result;
}

```

## disassembly

```asm
0x18001275c  sub     rsp, 28h
0x180012760  call    cs:__imp_GetProcessHeap
0x180012766  mov     edx, 8; dwFlags
0x18001276b  mov     rcx, rax; hHeap
0x18001276e  lea     r8d, [rdx+10h]; dwBytes
0x180012772  call    cs:__imp_HeapAlloc
0x180012778  test    rax, rax
0x18001277b  jz      short loc_180012784
0x18001277d  mov     dword ptr [rax+14h], 8
0x180012784  add     rsp, 28h
0x180012788  retn
```
