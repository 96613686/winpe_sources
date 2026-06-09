# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min(std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)

- ea: `0x1800105f4`
- end: `0x180010610`
- name: `?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@PEAU32@@Z`
- size: `28`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e87c`
- `0x180016580`
- `0x180018fb0`
- `0x1800199e0`

## callees

- `0x1800105f4`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min(
        _QWORD *a1)
{
  __int64 *v1; // rdx

  v1 = (__int64 *)*a1;
  if ( !*(_BYTE *)(*a1 + 25LL) )
  {
    do
    {
      a1 = v1;
      v1 = (__int64 *)*v1;
    }
    while ( !*((_BYTE *)v1 + 25) );
  }
  return a1;
}

```

## disassembly

```asm
0x1800105f4  mov     rdx, [rcx]
0x1800105f7  cmp     byte ptr [rdx+19h], 0
0x1800105fb  jnz     short loc_18001060C
0x1800105fd  mov     rax, [rdx]
0x180010600  mov     rcx, rdx
0x180010603  mov     rdx, rax
0x180010606  cmp     byte ptr [rax+19h], 0
0x18001060a  jz      short loc_1800105FD
0x18001060c  mov     rax, rcx
0x18001060f  retn
```
