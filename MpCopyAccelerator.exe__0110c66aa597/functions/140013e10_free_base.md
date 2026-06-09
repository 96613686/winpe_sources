# _free_base

- ea: `0x140013e10`
- end: `0x140013e4c`
- name: `_free_base`
- size: `60`
- prototype: `void __cdecl(void *Block)`
- caller_count: `44`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bfd0`
- `0x14000c850`
- `0x14000c8f8`
- `0x140010784`
- `0x1400109d8`
- `0x140011130`
- `0x140011250`
- `0x140011470`
- `0x140011950`
- `0x140011bc0`
- `0x1400124a8`
- `0x140012508`
- `0x140012684`
- `0x1400126f4`
- `0x140012814`
- `0x140012858`
- `0x140013100`
- `0x1400132b0`
- `0x140013540`
- `0x140013580`
- `0x140013650`
- `0x140013800`
- `0x140013930`
- `0x140013950`
- `0x140013a48`
- `0x1400158fc`
- `0x140016224`
- `0x140016620`
- `0x140016664`
- `0x140016a94`
- `0x140016e94`
- `0x140017194`
- `0x140017230`
- `0x140017594`
- `0x1400176c0`
- `0x140017768`
- `0x140017a08`
- `0x140017b14`
- `0x140017b80`
- `0x140017bb4`
- `0x140017da4`
- `0x140017f44`
- `0x140019fac`
- `0x14001b420`

## callees

- `0x140011fc4`
- `0x1400120dc`
- `0x140013e10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140013e30`
- `KERNEL32!GetLastError` at `0x140013e30`
- `KERNEL32!HeapFree` at `0x140013e26`
- `KERNEL32!HeapFree` at `0x140013e26`

## pseudocode

```c
void __cdecl free_base(void *Block)
{
  DWORD LastError; // eax
  int v2; // ebx

  if ( Block )
  {
    if ( !HeapFree(_acrt_heap, 0, Block) )
    {
      LastError = GetLastError();
      v2 = _acrt_errno_from_os_error(LastError);
      *errno() = v2;
    }
  }
}

```

## disassembly

```asm
0x140013e10  test    rcx, rcx
0x140013e13  jz      short locret_140013E4B
0x140013e15  push    rbx
0x140013e16  sub     rsp, 20h
0x140013e1a  mov     r8, rcx; lpMem
0x140013e1d  xor     edx, edx; dwFlags
0x140013e1f  mov     rcx, cs:__acrt_heap; hHeap
0x140013e26  call    cs:__imp_HeapFree
0x140013e2c  test    eax, eax
0x140013e2e  jnz     short loc_140013E46
0x140013e30  call    cs:__imp_GetLastError
0x140013e36  mov     ecx, eax
0x140013e38  call    __acrt_errno_from_os_error
0x140013e3d  mov     ebx, eax
0x140013e3f  call    _errno
0x140013e44  mov     [rax], ebx
0x140013e46  add     rsp, 20h
0x140013e4a  pop     rbx
0x140013e4b  retn
```
