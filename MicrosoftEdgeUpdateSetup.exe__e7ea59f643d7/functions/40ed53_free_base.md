# __free_base

- ea: `0x40ed53`
- end: `0x40ed8d`
- name: `__free_base`
- size: `58`
- prototype: `void __cdecl(void *Block)`
- caller_count: `44`
- callee_count: `3`
- tags: ``

## callers

- `0x40b2d7`
- `0x40b581`
- `0x40b5db`
- `0x40b62e`
- `0x40b6fe`
- `0x40bdeb`
- `0x40bf14`
- `0x40c130`
- `0x40c180`
- `0x40c28b`
- `0x40c713`
- `0x40c790`
- `0x40caed`
- `0x40cb07`
- `0x40e524`
- `0x40e6e0`
- `0x40e701`
- `0x40e819`
- `0x40e8d6`
- `0x40e970`
- `0x40ef46`
- `0x40f135`
- `0x40f1e6`
- `0x40f47c`
- `0x40f530`
- `0x40f7b2`
- `0x40fac9`
- `0x40fbdd`
- `0x410143`
- `0x4102a9`
- `0x410324`
- `0x41074c`
- `0x41084a`
- `0x4108b3`
- `0x4108eb`
- `0x410e1c`
- `0x410eb9`
- `0x41102a`
- `0x411d90`
- `0x411e60`
- `0x413c7d`
- `0x41484c`
- `0x4148f7`
- `0x41692a`

## callees

- `0x40ec6a`
- `0x40ece3`
- `0x40ed53`

## import_xrefs

- `KERNEL32!HeapFree` at `0x40ed69`
- `KERNEL32!HeapFree` at `0x40ed69`
- `KERNEL32!GetLastError` at `0x40ed7b`
- `KERNEL32!GetLastError` at `0x40ed7b`

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
0x40ed53  mov     edi, edi
0x40ed55  push    ebp
0x40ed56  mov     ebp, esp
0x40ed58  cmp     [ebp+lpMem], 0
0x40ed5c  jz      short loc_40ED8B
0x40ed5e  push    [ebp+lpMem]; lpMem
0x40ed61  push    0; dwFlags
0x40ed63  push    hHeap; hHeap
0x40ed69  call    ds:HeapFree
0x40ed6f  test    eax, eax
0x40ed71  jnz     short loc_40ED8B
0x40ed73  push    esi
0x40ed74  call    __errno
0x40ed79  mov     esi, eax
0x40ed7b  call    ds:GetLastError
0x40ed81  push    eax
0x40ed82  call    ___acrt_errno_from_os_error
0x40ed87  pop     ecx
0x40ed88  mov     [esi], eax
0x40ed8a  pop     esi
0x40ed8b  pop     ebp
0x40ed8c  retn
```
