# std::_Tree_comp<0,std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_FrameworkDependency,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_FrameworkDependency>>,0>>::_Tree_comp<0,std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_FrameworkDependency,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_FrameworkDependency>>,0>>(std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_FrameworkDependency>> const &)

- ea: `0x18000b2b8`
- end: `0x18000b2e2`
- name: `??0?$_Tree_comp@$0A@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@2@$0A@@std@@@std@@QEAA@AEBU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@1@@Z`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b220`
- `0x18000b8b4`

## callees

- `0x180012680`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_comp<0,std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::_Tree_comp<0,std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Buyheadnode();
  return a1;
}

```

## disassembly

```asm
0x18000b2b8  push    rbx
0x18000b2ba  sub     rsp, 20h
0x18000b2be  mov     rbx, rcx
0x18000b2c1  mov     qword ptr [rcx], 0
0x18000b2c8  mov     qword ptr [rcx+8], 0
0x18000b2d0  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Buyheadnode(void)
0x18000b2d5  mov     [rbx], rax
0x18000b2d8  mov     rax, rbx
0x18000b2db  add     rsp, 20h
0x18000b2df  pop     rbx
0x18000b2e0  retn
```
