# __free_base

- ea: `0x1001770e`
- end: `0x10017748`
- name: `__free_base`
- size: `58`
- prototype: `void __cdecl(void *Block)`
- caller_count: `43`
- callee_count: `3`
- tags: ``

## callers

- `0x10013b44`
- `0x10013bc3`
- `0x10014076`
- `0x10014090`
- `0x100163d0`
- `0x10016681`
- `0x100166db`
- `0x1001672e`
- `0x10016800`
- `0x1001691b`
- `0x10016ad1`
- `0x10016b21`
- `0x10016bf2`
- `0x10016f1f`
- `0x100170b6`
- `0x100170d7`
- `0x1001721d`
- `0x100172da`
- `0x10017374`
- `0x1001875b`
- `0x10018823`
- `0x10018eb1`
- `0x100190a2`
- `0x10019155`
- `0x100193ef`
- `0x100194a3`
- `0x1001971d`
- `0x10019a39`
- `0x10019b54`
- `0x1001a034`
- `0x1001adca`
- `0x1001ae67`
- `0x1001afda`
- `0x1001b17c`
- `0x1001b27a`
- `0x1001b2e3`
- `0x1001b31b`
- `0x1001d134`
- `0x1001d1d5`
- `0x1001d26b`
- `0x1001d2e8`
- `0x1001dab8`
- `0x1001ecc6`

## callees

- `0x10015d00`
- `0x10015d79`
- `0x1001770e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10017736`
- `KERNEL32!GetLastError` at `0x10017736`
- `KERNEL32!HeapFree` at `0x10017724`
- `KERNEL32!HeapFree` at `0x10017724`

## pseudocode

```c
void __cdecl _free_base(void *Block)
{
  int *v1; // esi
  DWORD LastError; // eax

  if ( Block )
  {
    if ( !HeapFree(hHeap, 0, Block) )
    {
      v1 = _errno();
      LastError = GetLastError();
      *v1 = __acrt_errno_from_os_error(LastError);
    }
  }
}

```

## disassembly

```asm
0x1001770e  mov     edi, edi
0x10017710  push    ebp
0x10017711  mov     ebp, esp
0x10017713  cmp     [ebp+lpMem], 0
0x10017717  jz      short loc_10017746
0x10017719  push    [ebp+lpMem]; lpMem
0x1001771c  push    0; dwFlags
0x1001771e  push    hHeap; hHeap
0x10017724  call    ds:HeapFree
0x1001772a  test    eax, eax
0x1001772c  jnz     short loc_10017746
0x1001772e  push    esi
0x1001772f  call    __errno
0x10017734  mov     esi, eax
0x10017736  call    ds:GetLastError
0x1001773c  push    eax
0x1001773d  call    ___acrt_errno_from_os_error
0x10017742  pop     ecx
0x10017743  mov     [esi], eax
0x10017745  pop     esi
0x10017746  pop     ebp
0x10017747  retn
```
