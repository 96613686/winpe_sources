# wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)

- ea: `0x18007edc4`
- end: `0x18007ee1f`
- name: `??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007fca0`

## callees

- `0x18005305c`
- `0x18005437c`
- `0x18007edc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007edf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007edf5`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        void ***a1)
{
  void **v1; // rbx
  void **v2; // rsi
  void *v3; // rdi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_BYTE *)a1 + 16) )
  {
    v1 = *a1;
    v2 = a1[1];
    v3 = **a1;
    if ( v3 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v4);
      CoTaskMemFree(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v4);
    }
    *v1 = v2;
  }
}

```

## disassembly

```asm
0x18007edc4  mov     [rsp+arg_8], rbx
0x18007edc9  mov     [rsp+arg_10], rsi
0x18007edce  push    rdi
0x18007edcf  sub     rsp, 20h
0x18007edd3  cmp     byte ptr [rcx+10h], 0
0x18007edd7  jz      short loc_18007EE0E
0x18007edd9  mov     rbx, [rcx]
0x18007eddc  mov     rsi, [rcx+8]
0x18007ede0  mov     rdi, [rbx]
0x18007ede3  test    rdi, rdi
0x18007ede6  jz      short loc_18007EE0B
0x18007ede8  lea     rcx, [rsp+28h+arg_0]; this
0x18007eded  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007edf2  mov     rcx, rdi; pv
0x18007edf5  call    cs:__imp_CoTaskMemFree
0x18007edfc  nop     dword ptr [rax+rax+00h]
0x18007ee01  lea     rcx, [rsp+28h+arg_0]; this
0x18007ee06  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007ee0b  mov     [rbx], rsi
0x18007ee0e  mov     rbx, [rsp+28h+arg_8]
0x18007ee13  mov     rsi, [rsp+28h+arg_10]
0x18007ee18  add     rsp, 20h
0x18007ee1c  pop     rdi
0x18007ee1d  retn
```
