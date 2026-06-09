# wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)

- ea: `0x1800265dc`
- end: `0x1800265f3`
- name: `??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800158dc`

## callees

- `0x1800265dc`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800265e8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800265e8`

## pseudocode

```c
BOOL __fastcall wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(
        SC_HANDLE *a1)
{
  SC_HANDLE v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return CloseServiceHandle(v1);
  return result;
}

```

## disassembly

```asm
0x1800265dc  sub     rsp, 28h
0x1800265e0  mov     rcx, [rcx]; hSCObject
0x1800265e3  test    rcx, rcx
0x1800265e6  jz      short loc_1800265EE
0x1800265e8  call    cs:__imp_CloseServiceHandle
0x1800265ee  add     rsp, 28h
0x1800265f2  retn
```
