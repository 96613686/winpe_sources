# std::_List_buy<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>::_Buynode<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>(std::_List_node<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,void *> *,std::_List_node<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,void *> *,std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &&)

- ea: `0x18000c558`
- end: `0x18000c583`
- name: `??$_Buynode@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@?$_List_buy@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAX@1@PEAU21@0$$QEAV?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@@Z`
- size: `43`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000db7c`
- `0x18000f75c`

## callees

- `0x18000d9cc`

## pseudocode

```c
__int64 __fastcall std::_List_buy<std::unique_ptr<std::wstring>>::_Buynode<std::unique_ptr<std::wstring>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 result; // rax
  __int64 v6; // rcx

  result = std::_List_alloc<0,std::_List_base_types<std::unique_ptr<CInformationNode>>>::_Buynode0();
  v6 = *a4;
  *a4 = 0;
  *(_QWORD *)(result + 16) = v6;
  return result;
}

```

## disassembly

```asm
0x18000c558  mov     [rsp+arg_0], rcx
0x18000c55d  push    rbx
0x18000c55e  sub     rsp, 20h
0x18000c562  mov     rbx, r9
0x18000c565  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<std::unique_ptr<CInformationNode>>>::_Buynode0(std::_List_node<std::unique_ptr<CInformationNode>,void *> *,std::_List_node<std::unique_ptr<CInformationNode>,void *> *)
0x18000c56a  mov     [rsp+28h+arg_0], rax
0x18000c56f  mov     rcx, [rbx]
0x18000c572  mov     qword ptr [rbx], 0
0x18000c579  mov     [rax+10h], rcx
0x18000c57d  add     rsp, 20h
0x18000c581  pop     rbx
0x18000c582  retn
```
