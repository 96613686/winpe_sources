# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x18000c040`
- end: `0x18000c092`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a97c`
- `0x180018cf0`

## callees

- `0x18000b810`
- `0x18000c020`
- `0x18000c040`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c06c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c06c`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        void **a1,
        void **a2)
{
  void *v4; // rsi
  void *v5; // rbp
  char v7; // [rsp+50h] [rbp+8h] BYREF

  if ( a1 != a2 )
  {
    v4 = *a1;
    v5 = *a2;
    if ( *a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      CoTaskMemFree(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
    }
    *a1 = v5;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000c040  push    rbx
0x18000c042  push    rbp
0x18000c043  push    rsi
0x18000c044  push    rdi
0x18000c045  sub     rsp, 28h
0x18000c049  mov     rdi, rdx
0x18000c04c  mov     rbx, rcx
0x18000c04f  cmp     rcx, rdx
0x18000c052  jz      short loc_18000C086
0x18000c054  mov     rsi, [rcx]
0x18000c057  mov     rbp, [rdx]
0x18000c05a  test    rsi, rsi
0x18000c05d  jz      short loc_18000C07C
0x18000c05f  lea     rcx, [rsp+48h+arg_0]; this
0x18000c064  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000c069  mov     rcx, rsi; pv
0x18000c06c  call    cs:__imp_CoTaskMemFree
0x18000c072  lea     rcx, [rsp+48h+arg_0]; this
0x18000c077  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000c07c  mov     [rbx], rbp
0x18000c07f  mov     qword ptr [rdi], 0
0x18000c086  mov     rax, rbx
0x18000c089  add     rsp, 28h
0x18000c08d  pop     rdi
0x18000c08e  pop     rsi
0x18000c08f  pop     rbp
0x18000c090  pop     rbx
0x18000c091  retn
```
