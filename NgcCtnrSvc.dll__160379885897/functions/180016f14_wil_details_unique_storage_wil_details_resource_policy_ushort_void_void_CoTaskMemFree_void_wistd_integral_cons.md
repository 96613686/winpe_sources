# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180016f14`
- end: `0x180016f6a`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022b70`
- `0x180022f7c`
- `0x1800234ac`
- `0x18003c59c`
- `0x18004ec20`
- `0x180050e90`

## callees

- `0x180016f14`
- `0x180025d04`
- `0x180025d70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016f52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016f52`

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
0x180016f14  mov     [rsp+arg_8], rbx
0x180016f19  mov     [rsp+arg_10], rsi
0x180016f1e  push    rdi
0x180016f1f  sub     rsp, 20h
0x180016f23  mov     rdi, [rcx]
0x180016f26  mov     rsi, rdx
0x180016f29  mov     rbx, rcx
0x180016f2c  test    rdi, rdi
0x180016f2f  jnz     short loc_180016F45
0x180016f31  mov     [rbx], rsi
0x180016f34  mov     rbx, [rsp+28h+arg_8]
0x180016f39  mov     rsi, [rsp+28h+arg_10]
0x180016f3e  add     rsp, 20h
0x180016f42  pop     rdi
0x180016f43  retn
0x180016f45  lea     rcx, [rsp+28h+arg_0]; this
0x180016f4a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180016f4f  mov     rcx, rdi; pv
0x180016f52  call    cs:__imp_CoTaskMemFree
0x180016f59  nop     dword ptr [rax+rax+00h]
0x180016f5e  lea     rcx, [rsp+28h+arg_0]; this
0x180016f63  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180016f68  jmp     short loc_180016F31
```
