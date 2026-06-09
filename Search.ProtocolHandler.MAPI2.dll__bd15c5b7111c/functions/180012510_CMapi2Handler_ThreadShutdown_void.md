# CMapi2Handler::ThreadShutdown(void)

- ea: `0x180012510`
- end: `0x180012533`
- name: `?ThreadShutdown@CMapi2Handler@@UEAAJXZ`
- size: `35`
- prototype: `__int64 __fastcall(CMapi2Handler *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800113ec`

## string_xrefs

- `0x180012514`: `CMapi2Handler::ThreadShutdown() Enter`
- `0x180012520`: `CMapi2Handler::ThreadShutdown() Exit`

## pseudocode

```c
__int64 __fastcall CMapi2Handler::ThreadShutdown(CMapi2Handler *this)
{
  CLogger::Info(L"CMapi2Handler::ThreadShutdown() Enter");
  CLogger::Info(L"CMapi2Handler::ThreadShutdown() Exit");
  return 0;
}

```

## disassembly

```asm
0x180012510  sub     rsp, 28h
0x180012514  lea     rcx, aCmapi2handlerT_3; "CMapi2Handler::ThreadShutdown() Enter"
0x18001251b  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180012520  lea     rcx, aCmapi2handlerT; "CMapi2Handler::ThreadShutdown() Exit"
0x180012527  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18001252c  xor     eax, eax
0x18001252e  add     rsp, 28h
0x180012532  retn
```
