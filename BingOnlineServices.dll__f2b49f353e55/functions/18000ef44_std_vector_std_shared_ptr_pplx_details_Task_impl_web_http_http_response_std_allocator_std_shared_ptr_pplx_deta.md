# std::vector<std::shared_ptr<pplx::details::_Task_impl<web::http::http_response>>,std::allocator<std::shared_ptr<pplx::details::_Task_impl<web::http::http_response>>>>::_Xlength(void)

- ea: `0x18000ef44`
- end: `0x18000ef56`
- name: `?_Xlength@?$vector@V?$shared_ptr@U?$_Task_impl@Vhttp_response@http@web@@@details@pplx@@@std@@V?$allocator@V?$shared_ptr@U?$_Task_impl@Vhttp_response@http@web@@@details@pplx@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `21`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180006cfc`
- `0x180007404`
- `0x18000756c`
- `0x1800081fc`
- `0x1800082f0`
- `0x1800083d4`
- `0x1800084ec`
- `0x1800089a0`
- `0x1800094e0`
- `0x1800104ac`
- `0x1800106f8`
- `0x18001f380`
- `0x18003e6ec`
- `0x18003f164`
- `0x180042788`
- `0x180043224`
- `0x180051fb0`
- `0x18005209c`
- `0x1800521a0`
- `0x180052318`
- `0x180052428`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ef4f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ef4f`

## pseudocode

```c
void __noreturn std::vector<std::shared_ptr<pplx::details::_Task_impl<web::http::http_response>>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x18000ef44  sub     rsp, 28h
0x18000ef48  lea     rcx, aVectorTooLong; "vector too long"
0x18000ef4f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
