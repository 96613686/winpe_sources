# wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)

- ea: `0x18000b92c`
- end: `0x18000b943`
- name: `??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(SC_HANDLE *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000b8fc`
- `0x18000c6e0`
- `0x18001260c`
- `0x180013644`
- `0x180013e50`

## callees

- `0x18000b92c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b938`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b938`

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
0x18000b92c  sub     rsp, 28h
0x18000b930  mov     rcx, [rcx]; hSCObject
0x18000b933  test    rcx, rcx
0x18000b936  jz      short loc_18000B93E
0x18000b938  call    cs:__imp_CloseServiceHandle
0x18000b93e  add     rsp, 28h
0x18000b942  retn
```
