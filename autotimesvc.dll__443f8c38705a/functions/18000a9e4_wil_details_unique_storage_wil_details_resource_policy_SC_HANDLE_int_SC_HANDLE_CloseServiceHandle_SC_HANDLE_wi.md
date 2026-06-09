# wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)

- ea: `0x18000a9e4`
- end: `0x18000aa31`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z`
- size: `77`
- prototype: `void __fastcall(SC_HANDLE *, SC_HANDLE)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180007534`
- `0x1800096b0`
- `0x180009d88`

## callees

- `0x180005318`
- `0x180005a38`
- `0x18000a9e4`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000aa0e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000aa0e`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
        SC_HANDLE *a1,
        SC_HANDLE a2)
{
  SC_HANDLE v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CloseServiceHandle(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000a9e4  mov     [rsp+arg_8], rbx
0x18000a9e9  mov     [rsp+arg_10], rsi
0x18000a9ee  push    rdi
0x18000a9ef  sub     rsp, 20h
0x18000a9f3  mov     rdi, [rcx]
0x18000a9f6  mov     rsi, rdx
0x18000a9f9  mov     rbx, rcx
0x18000a9fc  test    rdi, rdi
0x18000a9ff  jz      short loc_18000AA1E
0x18000aa01  lea     rcx, [rsp+28h+arg_0]; this
0x18000aa06  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000aa0b  mov     rcx, rdi; hSCObject
0x18000aa0e  call    cs:__imp_CloseServiceHandle
0x18000aa14  lea     rcx, [rsp+28h+arg_0]; this
0x18000aa19  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000aa1e  mov     [rbx], rsi
0x18000aa21  mov     rbx, [rsp+28h+arg_8]
0x18000aa26  mov     rsi, [rsp+28h+arg_10]
0x18000aa2b  add     rsp, 20h
0x18000aa2f  pop     rdi
0x18000aa30  retn
```
