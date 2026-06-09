# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>(void)

- ea: `0x18005cedc`
- end: `0x18005cf07`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(PTP_WAIT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180068dd9`
- `0x180068e30`

## callees

- `0x18005cedc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005cefb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005cefb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005cef2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005cef2`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>(
        PTP_WAIT *a1)
{
  struct _TP_WAIT *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    WaitForThreadpoolWaitCallbacks(*a1, 1);
    CloseThreadpoolWait(v1);
  }
}

```

## disassembly

```asm
0x18005cedc  push    rbx
0x18005cede  sub     rsp, 20h
0x18005cee2  mov     rbx, [rcx]
0x18005cee5  test    rbx, rbx
0x18005cee8  jz      short loc_18005CF01
0x18005ceea  mov     edx, 1; fCancelPendingCallbacks
0x18005ceef  mov     rcx, rbx; pwa
0x18005cef2  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005cef8  mov     rcx, rbx; pwa
0x18005cefb  call    cs:__imp_CloseThreadpoolWait
0x18005cf01  add     rsp, 20h
0x18005cf05  pop     rbx
0x18005cf06  retn
```
