# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180022498`
- end: `0x1800224e5`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022194`
- `0x1800264b4`
- `0x180026554`

## callees

- `0x180011984`
- `0x180011dfc`
- `0x180022498`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224c2`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180022498  mov     [rsp+arg_8], rbx
0x18002249d  mov     [rsp+arg_10], rsi
0x1800224a2  push    rdi
0x1800224a3  sub     rsp, 20h
0x1800224a7  mov     rdi, [rcx]
0x1800224aa  mov     rsi, rdx
0x1800224ad  mov     rbx, rcx
0x1800224b0  test    rdi, rdi
0x1800224b3  jz      short loc_1800224D2
0x1800224b5  lea     rcx, [rsp+28h+arg_0]; this
0x1800224ba  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800224bf  mov     rcx, rdi; pv
0x1800224c2  call    cs:__imp_CoTaskMemFree
0x1800224c8  lea     rcx, [rsp+28h+arg_0]; this
0x1800224cd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800224d2  mov     [rbx], rsi
0x1800224d5  mov     rbx, [rsp+28h+arg_8]
0x1800224da  mov     rsi, [rsp+28h+arg_10]
0x1800224df  add     rsp, 20h
0x1800224e3  pop     rdi
0x1800224e4  retn
```
