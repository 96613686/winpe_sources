# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>(void)

- ea: `0x180004880`
- end: `0x1800048b9`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(PTP_WAIT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f8d6`

## callees

- `0x180004880`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180004896`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180004896`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800048a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800048a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800048ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800048ad`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>(
        PTP_WAIT *a1)
{
  struct _TP_WAIT *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    SetThreadpoolWait(*a1, 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
}

```

## disassembly

```asm
0x180004880  push    rbx
0x180004882  sub     rsp, 20h
0x180004886  mov     rbx, [rcx]
0x180004889  test    rbx, rbx
0x18000488c  jz      short loc_1800048B3
0x18000488e  xor     r8d, r8d; pftTimeout
0x180004891  xor     edx, edx; h
0x180004893  mov     rcx, rbx; pwa
0x180004896  call    cs:__imp_SetThreadpoolWait
0x18000489c  mov     edx, 1; fCancelPendingCallbacks
0x1800048a1  mov     rcx, rbx; pwa
0x1800048a4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800048aa  mov     rcx, rbx; pwa
0x1800048ad  call    cs:__imp_CloseThreadpoolWait
0x1800048b3  add     rsp, 20h
0x1800048b7  pop     rbx
0x1800048b8  retn
```
