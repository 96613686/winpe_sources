# LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x180003fb0`
- end: `0x180004001`
- name: `?_AddRefRecord@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CAXPEBXH@Z`
- size: `81`
- prototype: `void __fastcall(void *lpMem, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180003fb0`
- `0x1800070f4`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003fec`
- `ole32!CoTaskMemFree` at `0x180003fec`

## pseudocode

```c
void __fastcall LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_AddRefRecord(
        void *lpMem,
        int a2)
{
  if ( a2 <= 0 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 4, 0xFFFFFFFF) == 1 )
    {
      if ( lpMem )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpMem + 1) + 16LL))(*((_QWORD *)lpMem + 1));
        CoTaskMemFree(*(LPVOID *)lpMem);
        operator delete(lpMem);
      }
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)lpMem + 4);
  }
}

```

## disassembly

```asm
0x180003fb0  push    rbx
0x180003fb2  sub     rsp, 20h
0x180003fb6  mov     rbx, rcx
0x180003fb9  test    edx, edx
0x180003fbb  jle     short loc_180003FC7
0x180003fbd  lock inc dword ptr [rcx+10h]
0x180003fc1  add     rsp, 20h
0x180003fc5  pop     rbx
0x180003fc6  retn
0x180003fc7  or      eax, 0FFFFFFFFh
0x180003fca  lock xadd [rcx+10h], eax
0x180003fcf  cmp     eax, 1
0x180003fd2  jnz     short loc_180003FFB
0x180003fd4  test    rbx, rbx
0x180003fd7  jz      short loc_180003FFB
0x180003fd9  mov     rcx, [rcx+8]
0x180003fdd  mov     rax, [rcx]
0x180003fe0  mov     rax, [rax+10h]
0x180003fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fe9  mov     rcx, [rbx]; pv
0x180003fec  call    cs:__imp_CoTaskMemFree
0x180003ff2  nop
0x180003ff3  mov     rcx, rbx; lpMem
0x180003ff6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003ffb  add     rsp, 20h
0x180003fff  pop     rbx
0x180004000  retn
```
