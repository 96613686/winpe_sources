# WcmCommon::Registry::Key::~Key(void)

- ea: `0x18000c150`
- end: `0x18000c155`
- name: `??1Key@Registry@WcmCommon@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(WcmCommon::Registry::Key *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025402`
- `0x180025784`
- `0x180025b54`
- `0x180026032`
- `0x18002686a`
- `0x180026aa2`
- `0x180026eb9`

## callees

- `0x18000c15c`

## pseudocode

```c
// attributes: thunk
void __fastcall WcmCommon::Registry::Key::~Key(WcmCommon::Registry::Key *this)
{
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(this);
}

```

## disassembly

```asm
0x18000c150  jmp     ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
```
