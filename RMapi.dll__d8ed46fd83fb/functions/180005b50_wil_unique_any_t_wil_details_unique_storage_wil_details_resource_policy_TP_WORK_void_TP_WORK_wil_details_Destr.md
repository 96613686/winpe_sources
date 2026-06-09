# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(void)

- ea: `0x180005b50`
- end: `0x180005b7d`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180025365`
- `0x1800253a0`
- `0x1800256b3`

## callees

- `0x180005b50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180005b75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180005b75`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180005b6c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180005b6c`

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
0x180005b50  push    rbx
0x180005b52  sub     rsp, 20h
0x180005b56  mov     rbx, [rcx]
0x180005b59  test    rbx, rbx
0x180005b5c  jnz     short loc_180005B64
0x180005b5e  add     rsp, 20h
0x180005b62  pop     rbx
0x180005b63  retn
0x180005b64  mov     edx, 1; fCancelPendingCallbacks
0x180005b69  mov     rcx, rbx; pwk
0x180005b6c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180005b72  mov     rcx, rbx; pwk
0x180005b75  call    cs:__imp_CloseThreadpoolWork
0x180005b7b  jmp     short loc_180005B5E
```
