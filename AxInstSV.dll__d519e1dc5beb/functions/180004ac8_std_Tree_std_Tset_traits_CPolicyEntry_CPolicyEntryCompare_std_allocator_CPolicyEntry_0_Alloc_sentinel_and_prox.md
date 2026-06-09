# std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Alloc_sentinel_and_proxy(void)

- ea: `0x180004ac8`
- end: `0x180004af5`
- name: `?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEAAXXZ`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800029a8`

## callees

- `0x18000177c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Alloc_sentinel_and_proxy(
        _QWORD *a1)
{
  _QWORD *result; // rax

  result = operator new(0x28u);
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
0x180004ac8  push    rbx
0x180004aca  sub     rsp, 20h
0x180004ace  mov     rbx, rcx
0x180004ad1  mov     ecx, 28h ; '('; Size
0x180004ad6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004adb  mov     [rax], rax
0x180004ade  mov     [rax+8], rax
0x180004ae2  mov     [rax+10h], rax
0x180004ae6  mov     word ptr [rax+18h], 101h
0x180004aec  mov     [rbx], rax
0x180004aef  add     rsp, 20h
0x180004af3  pop     rbx
0x180004af4  retn
```
