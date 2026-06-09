# CMapi2Handler::ThreadInit(void)

- ea: `0x1800124e0`
- end: `0x180012503`
- name: `?ThreadInit@CMapi2Handler@@UEAAJXZ`
- size: `35`
- prototype: `__int64 __fastcall(CMapi2Handler *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800113ec`

## string_xrefs

- `0x1800124e4`: `CMapi2Handler::ThreadInit() Enter`
- `0x1800124f0`: `CMapi2Handler::ThreadInit() Exit`

## pseudocode

```c
__int64 __fastcall CMapi2Handler::ThreadInit(CMapi2Handler *this)
{
  CLogger::Info(L"CMapi2Handler::ThreadInit() Enter");
  CLogger::Info(L"CMapi2Handler::ThreadInit() Exit");
  return 0;
}

```

## disassembly

```asm
0x1800124e0  sub     rsp, 28h
0x1800124e4  lea     rcx, aCmapi2handlerT_4; "CMapi2Handler::ThreadInit() Enter"
0x1800124eb  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x1800124f0  lea     rcx, aCmapi2handlerT_0; "CMapi2Handler::ThreadInit() Exit"
0x1800124f7  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x1800124fc  xor     eax, eax
0x1800124fe  add     rsp, 28h
0x180012502  retn
```
