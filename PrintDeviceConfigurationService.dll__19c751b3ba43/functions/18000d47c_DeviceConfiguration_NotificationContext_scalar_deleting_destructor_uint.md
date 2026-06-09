# DeviceConfiguration::NotificationContext::`scalar deleting destructor'(uint)

- ea: `0x18000d47c`
- end: `0x18000d4a4`
- name: `??_GNotificationContext@DeviceConfiguration@@QEAAPEAXI@Z`
- size: `40`
- prototype: `HMODULE *__fastcall(HMODULE *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000d3e0`
- `0x18000da84`
- `0x18000db34`
- `0x18000dbe4`

## callees

- `0x180002490`
- `0x18000d284`

## pseudocode

```c
HMODULE *__fastcall DeviceConfiguration::NotificationContext::`scalar deleting destructor'(HMODULE *this)
{
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(this + 3);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000d47c  push    rbx
0x18000d47e  sub     rsp, 20h
0x18000d482  mov     rbx, rcx
0x18000d485  add     rcx, 18h
0x18000d489  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000d48e  mov     edx, 20h ; ' '; unsigned __int64
0x18000d493  mov     rcx, rbx; void *
0x18000d496  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d49b  mov     rax, rbx
0x18000d49e  add     rsp, 20h
0x18000d4a2  pop     rbx
0x18000d4a3  retn
```
