# __free_base

- ea: `0x4136b2`
- end: `0x4136ec`
- name: `__free_base`
- size: `58`
- prototype: `void __cdecl(void *Block)`
- caller_count: `42`
- callee_count: `3`
- tags: ``

## callers

- `0x4101a2`
- `0x41092f`
- `0x410bf2`
- `0x410c4c`
- `0x410c9a`
- `0x410da7`
- `0x410f2d`
- `0x411056`
- `0x411270`
- `0x4112c0`
- `0x411ba6`
- `0x411c23`
- `0x411f70`
- `0x411f8a`
- `0x41373e`
- `0x413900`
- `0x413921`
- `0x413a39`
- `0x413af6`
- `0x413b90`
- `0x413ccd`
- `0x413e98`
- `0x4140c0`
- `0x41430a`
- `0x4143e9`
- `0x414700`
- `0x414814`
- `0x414d77`
- `0x415b10`
- `0x415be0`
- `0x415d2a`
- `0x415da5`
- `0x415fd8`
- `0x4160d6`
- `0x41613f`
- `0x416177`
- `0x416818`
- `0x4168b5`
- `0x416a26`
- `0x419211`
- `0x4192bc`
- `0x41b28a`

## callees

- `0x4103ca`
- `0x410443`
- `0x4136b2`

## import_xrefs

- `KERNEL32!GetLastError` at `0x4136da`
- `KERNEL32!GetLastError` at `0x4136da`
- `KERNEL32!HeapFree` at `0x4136c8`
- `KERNEL32!HeapFree` at `0x4136c8`

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
0x4136b2  mov     edi, edi
0x4136b4  push    ebp
0x4136b5  mov     ebp, esp
0x4136b7  cmp     [ebp+lpMem], 0
0x4136bb  jz      short loc_4136EA
0x4136bd  push    [ebp+lpMem]; lpMem
0x4136c0  push    0; dwFlags
0x4136c2  push    hHeap; hHeap
0x4136c8  call    ds:HeapFree
0x4136ce  test    eax, eax
0x4136d0  jnz     short loc_4136EA
0x4136d2  push    esi
0x4136d3  call    __errno
0x4136d8  mov     esi, eax
0x4136da  call    ds:GetLastError
0x4136e0  push    eax
0x4136e1  call    ___acrt_errno_from_os_error
0x4136e6  pop     ecx
0x4136e7  mov     [esi], eax
0x4136e9  pop     esi
0x4136ea  pop     ebp
0x4136eb  retn
```
