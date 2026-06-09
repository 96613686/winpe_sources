# SIDKeyProvFree(void *)

- ea: `0x180010950`
- end: `0x180010977`
- name: `?SIDKeyProvFree@@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `74`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180002888`
- `0x180002a14`
- `0x180002a5c`
- `0x180002b28`
- `0x180002bf0`
- `0x180003160`
- `0x1800035a0`
- `0x180003670`
- `0x1800038c0`
- `0x18000398c`
- `0x180003fd8`
- `0x180004360`
- `0x180004624`
- `0x180004a00`
- `0x180004d5c`
- `0x180004e20`
- `0x180004ee0`
- `0x180004f40`
- `0x180005934`
- `0x180005a24`
- `0x180006564`
- `0x180006908`
- `0x180006d90`
- `0x180007354`
- `0x180007a10`
- `0x180008528`
- `0x180008570`
- `0x180008850`
- `0x18000898c`
- `0x180008eb4`
- `0x180009408`
- `0x18000a878`
- `0x18000a9f0`
- `0x18000aef0`
- `0x18000b758`
- `0x18000b960`
- `0x18000be6c`
- `0x18000bfd8`
- `0x18000c1fc`
- `0x18000ce40`
- `0x18000d63c`
- `0x18000d6a0`
- `0x18000dc90`
- `0x18000de80`
- `0x18000dfc0`
- `0x18000e644`
- `0x18000e8a0`
- `0x18000eab8`
- `0x18000ec54`
- `0x18000f1a8`

## callees

- `0x180010950`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001096b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001096b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001095d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001095d`

## pseudocode

```c
void __fastcall SIDKeyProvFree(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180010950  test    rcx, rcx
0x180010953  jz      short locret_180010976
0x180010955  push    rbx
0x180010956  sub     rsp, 20h
0x18001095a  mov     rbx, rcx
0x18001095d  call    cs:__imp_GetProcessHeap
0x180010963  mov     r8, rbx; lpMem
0x180010966  xor     edx, edx; dwFlags
0x180010968  mov     rcx, rax; hHeap
0x18001096b  call    cs:__imp_HeapFree
0x180010971  add     rsp, 20h
0x180010975  pop     rbx
0x180010976  retn
```
