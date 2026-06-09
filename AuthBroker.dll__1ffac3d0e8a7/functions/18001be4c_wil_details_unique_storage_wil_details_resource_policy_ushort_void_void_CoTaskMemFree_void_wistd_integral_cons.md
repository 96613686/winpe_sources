# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18001be4c`
- end: `0x18001be99`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `void __fastcall(wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *this, wchar_t *ptr)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800054bc`
- `0x18001ed50`

## callees

- `0x180006650`
- `0x1800066d4`
- `0x18001be4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be76`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *this,
        wchar_t *ptr)
{
  wchar_t *m_ptr; // rdi
  wil::last_error_context v5; // [rsp+30h] [rbp+8h] BYREF

  m_ptr = this->m_ptr;
  if ( this->m_ptr )
  {
    wil::last_error_context::last_error_context(&v5);
    CoTaskMemFree(m_ptr);
    wil::last_error_context::~last_error_context(&v5);
  }
  this->m_ptr = ptr;
}

```

## disassembly

```asm
0x18001be4c  mov     [rsp+arg_8], rbx
0x18001be51  mov     [rsp+arg_10], rsi
0x18001be56  push    rdi
0x18001be57  sub     rsp, 20h
0x18001be5b  mov     rdi, [this]
0x18001be5e  mov     rsi, ptr
0x18001be61  mov     rbx, this
0x18001be64  test    rdi, rdi
0x18001be67  jz      short loc_18001BE86
0x18001be69  lea     this, [rsp+28h+arg_0]; this
0x18001be6e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001be73  mov     this, rdi; pv
0x18001be76  call    cs:__imp_CoTaskMemFree
0x18001be7c  lea     this, [rsp+28h+arg_0]; this
0x18001be81  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001be86  mov     [rbx], rsi
0x18001be89  mov     rbx, [rsp+28h+arg_8]
0x18001be8e  mov     rsi, [rsp+28h+arg_10]
0x18001be93  add     rsp, 20h
0x18001be97  pop     rdi
0x18001be98  retn
```
