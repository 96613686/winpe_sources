# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&DestroyThreadpoolWork(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&DestroyThreadpoolWork(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(void)

- ea: `0x18005d3f8`
- end: `0x18005d423`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?DestroyThreadpoolWork@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(PTP_WORK *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180068e92`
- `0x180068ea8`

## callees

- `0x18005d3f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d40e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d40e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d417`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d417`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&void DestroyThreadpoolWork(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&void DestroyThreadpoolWork(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(
        PTP_WORK *a1)
{
  struct _TP_WORK *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    WaitForThreadpoolWorkCallbacks(*a1, 1);
    CloseThreadpoolWork(v1);
  }
}

```

## disassembly

```asm
0x18005d3f8  push    rbx
0x18005d3fa  sub     rsp, 20h
0x18005d3fe  mov     rbx, [rcx]
0x18005d401  test    rbx, rbx
0x18005d404  jz      short loc_18005D41D
0x18005d406  mov     edx, 1; fCancelPendingCallbacks
0x18005d40b  mov     rcx, rbx; pwk
0x18005d40e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005d414  mov     rcx, rbx; pwk
0x18005d417  call    cs:__imp_CloseThreadpoolWork
0x18005d41d  add     rsp, 20h
0x18005d421  pop     rbx
0x18005d422  retn
```
