# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Alloc_sentinel_and_proxy(void)

- ea: `0x1800120ec`
- end: `0x180012119`
- name: `?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ`
- size: `45`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006aec`

## callees

- `0x18000177c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Alloc_sentinel_and_proxy(
        _QWORD *a1)
{
  _QWORD *result; // rax

  result = operator new(0x30u);
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x1800120ec  push    rbx
0x1800120ee  sub     rsp, 20h
0x1800120f2  mov     rbx, rcx
0x1800120f5  mov     ecx, 30h ; '0'; Size
0x1800120fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800120ff  mov     [rax], rax
0x180012102  mov     [rax+8], rax
0x180012106  mov     [rax+10h], rax
0x18001210a  mov     word ptr [rax+18h], 101h
0x180012110  mov     [rbx], rax
0x180012113  add     rsp, 20h
0x180012117  pop     rbx
0x180012118  retn
```
