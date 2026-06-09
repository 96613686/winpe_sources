# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Buynode(void)

- ea: `0x18000e4d0`
- end: `0x18000e50a`
- name: `?_Buynode@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@IEAAPEAU_Node@?$_List_nod@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@2@XZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800098d0`

## callees

- `0x18000e4d0`
- `0x18002687c`

## pseudocode

```c
_QWORD *std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode()
{
  _QWORD *result; // rax
  _QWORD *v1; // rcx

  result = operator new(0xB8u);
  try
  {
    if ( result )
      *result = result;
    v1 = result + 1;
    if ( result != (_QWORD *)-8LL )
      *v1 = result;
  }
  catch ( ... )
  {
    std::allocator<unsigned int>::deallocate(v1, result);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000e4d0  mov     [rsp+arg_0], rcx
0x18000e4d5  sub     rsp, 38h
0x18000e4d9  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000e4e2  mov     ecx, 0B8h; Size
0x18000e4e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e4ec  mov     [rsp+38h+arg_0], rax
0x18000e4f1  test    rax, rax
0x18000e4f4  jz      short loc_18000E4F9
0x18000e4f6  mov     [rax], rax
0x18000e4f9  lea     rcx, [rax+8]
0x18000e4fd  test    rcx, rcx
0x18000e500  jz      short loc_18000E505
0x18000e502  mov     [rcx], rax
0x18000e505  add     rsp, 38h
0x18000e509  retn
```
