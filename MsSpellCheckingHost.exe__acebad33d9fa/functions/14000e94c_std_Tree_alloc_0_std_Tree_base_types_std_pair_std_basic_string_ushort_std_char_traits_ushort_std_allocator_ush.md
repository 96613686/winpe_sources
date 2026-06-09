# std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>::_Buyheadnode(void)

- ea: `0x14000e94c`
- end: `0x14000e985`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@XZ`
- size: `57`
- prototype: `_QWORD *()`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140009b40`
- `0x14000afe0`
- `0x140010d08`
- `0x140011110`

## callees

- `0x1400014fc`
- `0x140001758`
- `0x14000e94c`

## pseudocode

```c
_QWORD *std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode()
{
  _QWORD *result; // rax

  result = operator new(0x60u);
  if ( !result )
    std::_Xbad_alloc();
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  return result;
}

```

## disassembly

```asm
0x14000e94c  mov     [rsp+arg_0], rcx
0x14000e951  sub     rsp, 28h
0x14000e955  mov     ecx, 60h ; '`'; Size
0x14000e95a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e95f  mov     [rsp+28h+arg_0], rax
0x14000e964  test    rax, rax
0x14000e967  jz      short loc_14000E97F
0x14000e969  mov     [rax], rax
0x14000e96c  mov     [rax+8], rax
0x14000e970  mov     [rax+10h], rax
0x14000e974  mov     word ptr [rax+18h], 101h
0x14000e97a  add     rsp, 28h
0x14000e97e  retn
0x14000e97f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
