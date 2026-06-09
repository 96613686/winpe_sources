# RegKey::~RegKey(void)

- ea: `0x18000dfa8`
- end: `0x18000dfcc`
- name: `??1RegKey@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(RegKey *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f6e0`
- `0x18001020c`
- `0x1800102c4`
- `0x180010514`
- `0x1800115a7`
- `0x18001162e`
- `0x18001168e`

## callees

- `0x18000df38`
- `0x18000e020`

## pseudocode

```c
void __fastcall RegKey::~RegKey(RegKey *this)
{
  RegKey::Close(this);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((char *)this + 8);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(this);
}

```

## disassembly

```asm
0x18000dfa8  push    rbx
0x18000dfaa  sub     rsp, 20h
0x18000dfae  mov     rbx, rcx
0x18000dfb1  call    ?Close@RegKey@@QEAAXXZ; RegKey::Close(void)
0x18000dfb6  lea     rcx, [rbx+8]
0x18000dfba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000dfbf  mov     rcx, rbx
0x18000dfc2  add     rsp, 20h
0x18000dfc6  pop     rbx
0x18000dfc7  jmp     ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
```
