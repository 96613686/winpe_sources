# wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)

- ea: `0x1800457dc`
- end: `0x180045829`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WSALookupServiceEnd@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18003f834`
- `0x18004ba18`

## callees

- `0x180003ce8`
- `0x180004398`
- `0x1800457dc`

## import_xrefs

- `WS2_32!WSALookupServiceEnd` at `0x180045806`
- `WS2_32!WSALookupServiceEnd` at `0x180045806`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    WSALookupServiceEnd(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800457dc  mov     [rsp+arg_8], rbx
0x1800457e1  mov     [rsp+arg_10], rsi
0x1800457e6  push    rdi
0x1800457e7  sub     rsp, 20h
0x1800457eb  mov     rdi, [rcx]
0x1800457ee  mov     rsi, rdx
0x1800457f1  mov     rbx, rcx
0x1800457f4  test    rdi, rdi
0x1800457f7  jz      short loc_180045816
0x1800457f9  lea     rcx, [rsp+28h+arg_0]; this
0x1800457fe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180045803  mov     rcx, rdi; hLookup
0x180045806  call    cs:__imp_WSALookupServiceEnd
0x18004580c  lea     rcx, [rsp+28h+arg_0]; this
0x180045811  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180045816  mov     [rbx], rsi
0x180045819  mov     rbx, [rsp+28h+arg_8]
0x18004581e  mov     rsi, [rsp+28h+arg_10]
0x180045823  add     rsp, 20h
0x180045827  pop     rdi
0x180045828  retn
```
