# RegistryKey::~RegistryKey(void)

- ea: `0x1800093a8`
- end: `0x1800093ad`
- name: `??1RegistryKey@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `25`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002ea3a`
- `0x18002ea53`
- `0x18002ea6c`
- `0x18002ea85`
- `0x18002ea97`
- `0x18002eaa9`
- `0x18002eaf1`
- `0x18002eb27`
- `0x18002eb6f`
- `0x18002f926`
- `0x18002f938`
- `0x18002f96e`
- `0x18002f980`
- `0x18002fbfe`
- `0x18002fd32`
- `0x18002fde6`
- `0x18002fe0a`
- `0x18002fe7f`
- `0x18002fefd`
- `0x18003010e`
- `0x1800302be`
- `0x1800302d0`
- `0x1800302f4`
- `0x1800306c9`
- `0x1800306ed`

## callees

- `0x180008e3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
// attributes: thunk
void __fastcall RegistryKey::~RegistryKey(HKEY *this)
{
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(this);
}

```

## disassembly

```asm
0x1800093a8  jmp     ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
```
