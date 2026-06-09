# _free_base

- ea: `0x18000fe3c`
- end: `0x18000fe79`
- name: `_free_base`
- size: `61`
- prototype: `void __cdecl(void *Block)`
- caller_count: `50`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bb08`
- `0x18000c07c`
- `0x18000c250`
- `0x18000c2f8`
- `0x18000dd40`
- `0x18000dda0`
- `0x18000df28`
- `0x18000df94`
- `0x18000e09c`
- `0x18000e1d0`
- `0x18000e380`
- `0x18000e620`
- `0x18000e660`
- `0x18000ffa4`
- `0x1800100e0`
- `0x180010100`
- `0x180010260`
- `0x1800102a4`
- `0x180010378`
- `0x180010420`
- `0x180010590`
- `0x180011ad0`
- `0x180011bf0`
- `0x180012144`
- `0x1800122bc`
- `0x180012448`
- `0x180012654`
- `0x1800127dc`
- `0x180012d28`
- `0x1800131d8`
- `0x180013398`
- `0x180013954`
- `0x180014938`
- `0x180014ad8`
- `0x1800167ec`
- `0x1800168a0`
- `0x180016940`
- `0x180016a4c`
- `0x180016ab8`
- `0x180016b10`
- `0x180016c18`
- `0x180016da8`
- `0x180016e50`
- `0x180017a54`
- `0x180019980`
- `0x18002218c`
- `0x180023724`
- `0x180023918`
- `0x180023984`
- `0x180023d3c`

## callees

- `0x18000bf04`
- `0x18000bfbc`
- `0x18000fe3c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000fe52`
- `KERNEL32!HeapFree` at `0x18000fe52`
- `KERNEL32!GetLastError` at `0x18000fe64`
- `KERNEL32!GetLastError` at `0x18000fe64`

## pseudocode

```c
void __cdecl free_base(void *Block)
{
  int *v1; // rbx
  DWORD LastError; // eax

  if ( Block )
  {
    if ( !HeapFree(_acrt_heap, 0, Block) )
    {
      v1 = errno();
      LastError = GetLastError();
      *v1 = _acrt_errno_from_os_error(LastError);
    }
  }
}

```

## disassembly

```asm
0x18000fe3c  test    rcx, rcx
0x18000fe3f  jz      short locret_18000FE78
0x18000fe41  push    rbx
0x18000fe42  sub     rsp, 20h
0x18000fe46  mov     r8, rcx; lpMem
0x18000fe49  xor     edx, edx; dwFlags
0x18000fe4b  mov     rcx, cs:__acrt_heap; hHeap
0x18000fe52  call    cs:__imp_HeapFree
0x18000fe58  test    eax, eax
0x18000fe5a  jnz     short loc_18000FE73
0x18000fe5c  call    _errno
0x18000fe61  mov     rbx, rax
0x18000fe64  call    cs:__imp_GetLastError
0x18000fe6a  mov     ecx, eax
0x18000fe6c  call    __acrt_errno_from_os_error
0x18000fe71  mov     [rbx], eax
0x18000fe73  add     rsp, 20h
0x18000fe77  pop     rbx
0x18000fe78  retn
```
