# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::~_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>(void)

- ea: `0x18000e7c4`
- end: `0x18000e81a`
- name: `??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ea80`
- `0x18000ead0`

## callees

- `0x180006288`
- `0x180007f80`
- `0x18000e7c4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(
        _QWORD *a1)
{
  __int64 v2; // rcx

  v2 = a1[3];
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (a1[5] - v2) & 0xFFFFFFFFFFFFFFF8uLL);
    a1[3] = 0;
    a1[4] = 0;
    a1[5] = 0;
  }
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(v2, a1[1]);
  return std::_Deallocate<16>(a1[1], 48);
}

```

## disassembly

```asm
0x18000e7c4  push    rbx
0x18000e7c6  sub     rsp, 20h
0x18000e7ca  mov     rbx, rcx
0x18000e7cd  mov     rcx, [rcx+18h]
0x18000e7d1  test    rcx, rcx
0x18000e7d4  jz      short loc_18000E7FE
0x18000e7d6  mov     rdx, [rbx+28h]
0x18000e7da  sub     rdx, rcx
0x18000e7dd  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000e7e1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e7e6  mov     qword ptr [rbx+18h], 0
0x18000e7ee  mov     qword ptr [rbx+20h], 0
0x18000e7f6  mov     qword ptr [rbx+28h], 0
0x18000e7fe  mov     rdx, [rbx+8]
0x18000e802  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18000e807  mov     rcx, [rbx+8]
0x18000e80b  mov     edx, 30h ; '0'
0x18000e810  add     rsp, 20h
0x18000e814  pop     rbx
0x18000e815  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
