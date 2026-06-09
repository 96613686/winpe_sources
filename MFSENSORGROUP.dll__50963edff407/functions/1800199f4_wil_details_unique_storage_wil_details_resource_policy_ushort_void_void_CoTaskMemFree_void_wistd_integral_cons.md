# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x1800199f4`
- end: `0x180019a43`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800185e4`
- `0x180019a4c`
- `0x18001ad90`
- `0x180065c38`

## callees

- `0x1800199f4`
- `0x180031920`
- `0x18003491c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a31`

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
0x1800199f4  mov     [rsp+arg_8], rbx
0x1800199f9  mov     [rsp+arg_10], rsi
0x1800199fe  push    rdi
0x1800199ff  sub     rsp, 20h
0x180019a03  mov     rdi, [rcx]
0x180019a06  mov     rsi, rdx
0x180019a09  mov     rbx, rcx
0x180019a0c  test    rdi, rdi
0x180019a0f  jnz     short loc_180019A24
0x180019a11  mov     [rbx], rsi
0x180019a14  mov     rbx, [rsp+28h+arg_8]
0x180019a19  mov     rsi, [rsp+28h+arg_10]
0x180019a1e  add     rsp, 20h
0x180019a22  pop     rdi
0x180019a23  retn
0x180019a24  lea     rcx, [rsp+28h+arg_0]; this
0x180019a29  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180019a2e  mov     rcx, rdi; pv
0x180019a31  call    cs:__imp_CoTaskMemFree
0x180019a37  lea     rcx, [rsp+28h+arg_0]; this
0x180019a3c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019a41  jmp     short loc_180019A11
```
