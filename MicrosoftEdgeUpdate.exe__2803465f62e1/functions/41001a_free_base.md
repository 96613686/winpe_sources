# __free_base

- ea: `0x41001a`
- end: `0x410054`
- name: `__free_base`
- size: `58`
- prototype: `void __cdecl(void *Block)`
- caller_count: `38`
- callee_count: `3`
- tags: ``

## callers

- `0x40e4a7`
- `0x40e76a`
- `0x40e7c4`
- `0x40e812`
- `0x40e91f`
- `0x40ef25`
- `0x40eff6`
- `0x40f11f`
- `0x40f340`
- `0x40f390`
- `0x40f6b2`
- `0x40f870`
- `0x40f891`
- `0x40f9a9`
- `0x40fa66`
- `0x40fb00`
- `0x410078`
- `0x4102a0`
- `0x4104ea`
- `0x4105c9`
- `0x4108e0`
- `0x4109f4`
- `0x410ef3`
- `0x410f74`
- `0x410fef`
- `0x41141c`
- `0x41151a`
- `0x411583`
- `0x4115bb`
- `0x4117f0`
- `0x41188d`
- `0x4119fe`
- `0x412680`
- `0x412750`
- `0x41361d`
- `0x4141ec`
- `0x414297`
- `0x4146bc`

## callees

- `0x40ff30`
- `0x40ffa9`
- `0x41001a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x410042`
- `KERNEL32!GetLastError` at `0x410042`
- `KERNEL32!HeapFree` at `0x410030`
- `KERNEL32!HeapFree` at `0x410030`

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
0x41001a  mov     edi, edi
0x41001c  push    ebp
0x41001d  mov     ebp, esp
0x41001f  cmp     [ebp+lpMem], 0
0x410023  jz      short loc_410052
0x410025  push    [ebp+lpMem]; lpMem
0x410028  push    0; dwFlags
0x41002a  push    hHeap; hHeap
0x410030  call    ds:HeapFree
0x410036  test    eax, eax
0x410038  jnz     short loc_410052
0x41003a  push    esi
0x41003b  call    __errno
0x410040  mov     esi, eax
0x410042  call    ds:GetLastError
0x410048  push    eax
0x410049  call    ___acrt_errno_from_os_error
0x41004e  pop     ecx
0x41004f  mov     [esi], eax
0x410051  pop     esi
0x410052  pop     ebp
0x410053  retn
```
