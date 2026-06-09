# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)

- ea: `0x1800229e8`
- end: `0x1800229fd`
- name: `?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ`
- size: `21`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x18001de6c`
- `0x18001dff0`
- `0x180022bec`
- `0x1800231f4`
- `0x1800314b8`
- `0x180031574`
- `0x1800323f0`
- `0x180032840`
- `0x1800328f4`
- `0x180032d08`
- `0x180035264`
- `0x180036e4c`
- `0x180037aa8`
- `0x18003ebd8`
- `0x18003edd0`
- `0x18003f580`
- `0x18003feb0`
- `0x180040014`
- `0x180041a30`
- `0x180041d30`
- `0x180043174`
- `0x1800432dc`
- `0x1800446d8`
- `0x180044b78`
- `0x180044f78`
- `0x18004686c`

## callees

- `0x180011fb8`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rdx

  std::vector<tagRGBQUAD>::begin(a1 + 8, a2, a3);
  return v3;
}

```

## disassembly

```asm
0x1800229e8  sub     rsp, 28h
0x1800229ec  add     rcx, 8
0x1800229f0  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x1800229f5  mov     rax, rdx
0x1800229f8  add     rsp, 28h
0x1800229fc  retn
```
