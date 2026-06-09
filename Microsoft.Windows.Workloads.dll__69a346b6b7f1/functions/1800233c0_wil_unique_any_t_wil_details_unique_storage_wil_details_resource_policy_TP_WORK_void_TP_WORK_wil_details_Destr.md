# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(void)

- ea: `0x1800233c0`
- end: `0x1800233f1`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(PTP_WORK *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180041778`

## callees

- `0x1800233c0`

## import_xrefs

- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x1800233d6`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x1800233d6`
- `KERNEL32!CloseThreadpoolWork` at `0x1800233e4`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(
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
0x1800233c0  push    rbx
0x1800233c2  sub     rsp, 20h
0x1800233c6  mov     rbx, [rcx]
0x1800233c9  test    rbx, rbx
0x1800233cc  jz      short loc_1800233EB
0x1800233ce  mov     edx, 1; fCancelPendingCallbacks
0x1800233d3  mov     rcx, rbx; pwk
0x1800233d6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800233dc  mov     rcx, rbx
0x1800233df  add     rsp, 20h
0x1800233e3  pop     rbx
0x1800233e4  jmp     cs:__imp_CloseThreadpoolWork
0x1800233eb  add     rsp, 20h
0x1800233ef  pop     rbx
0x1800233f0  retn
```
