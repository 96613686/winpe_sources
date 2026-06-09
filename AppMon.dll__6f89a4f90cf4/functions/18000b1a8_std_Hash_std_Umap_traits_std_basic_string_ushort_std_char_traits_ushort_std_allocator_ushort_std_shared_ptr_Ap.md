# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::~_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>(void)

- ea: `0x18000b1a8`
- end: `0x18000b1fe`
- name: `??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b3e8`
- `0x18000bafc`
- `0x18000fc50`

## callees

- `0x180006288`
- `0x18000aac0`
- `0x18000b1a8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>(
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
  std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(
    v2,
    a1[1]);
  return std::_Deallocate<16>(a1[1], 64);
}

```

## disassembly

```asm
0x18000b1a8  push    rbx
0x18000b1aa  sub     rsp, 20h
0x18000b1ae  mov     rbx, rcx
0x18000b1b1  mov     rcx, [rcx+18h]
0x18000b1b5  test    rcx, rcx
0x18000b1b8  jz      short loc_18000B1E2
0x18000b1ba  mov     rdx, [rbx+28h]
0x18000b1be  sub     rdx, rcx
0x18000b1c1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000b1c5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b1ca  mov     qword ptr [rbx+18h], 0
0x18000b1d2  mov     qword ptr [rbx+20h], 0
0x18000b1da  mov     qword ptr [rbx+28h], 0
0x18000b1e2  mov     rdx, [rbx+8]
0x18000b1e6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>> &,std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *> *)
0x18000b1eb  mov     rcx, [rbx+8]
0x18000b1ef  mov     edx, 40h ; '@'
0x18000b1f4  add     rsp, 20h
0x18000b1f8  pop     rbx
0x18000b1f9  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
