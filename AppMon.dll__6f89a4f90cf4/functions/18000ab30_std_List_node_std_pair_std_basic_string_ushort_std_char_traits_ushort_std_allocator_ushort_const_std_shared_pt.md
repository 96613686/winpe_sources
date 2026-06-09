# std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>> &,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *> *)

- ea: `0x18000ab30`
- end: `0x18000ab54`
- name: `??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@1@PEAU01@@Z`
- size: `36`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a59c`
- `0x18000a9a8`
- `0x18000aac0`
- `0x18000b2ac`
- `0x18000d560`

## callees

- `0x180006288`
- `0x18000b34c`

## pseudocode

```c
void __fastcall std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(
        __int64 a1,
        char *a2)
{
  std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>::~pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>(a2 + 16);
  std::_Deallocate<16>(a2, 0x40u);
}

```

## disassembly

```asm
0x18000ab30  push    rbx
0x18000ab32  sub     rsp, 20h
0x18000ab36  lea     rcx, [rdx+10h]
0x18000ab3a  mov     rbx, rdx
0x18000ab3d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>::~pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>(void)
0x18000ab42  mov     edx, 40h ; '@'
0x18000ab47  mov     rcx, rbx
0x18000ab4a  add     rsp, 20h
0x18000ab4e  pop     rbx
0x18000ab4f  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
