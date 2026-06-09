# wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)

- ea: `0x1800047f0`
- end: `0x180004815`
- name: `??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(wil::details::event_watcher_state **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000ef03`
- `0x18000ef41`
- `0x18000ef7f`

## callees

- `0x1800047f0`
- `0x180005144`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004809`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004809`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(
        wil::details::event_watcher_state **a1)
{
  wil::details::event_watcher_state *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    wil::details::event_watcher_state::~event_watcher_state(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800047f0  push    rbx
0x1800047f2  sub     rsp, 20h
0x1800047f6  mov     rbx, [rcx]
0x1800047f9  test    rbx, rbx
0x1800047fc  jz      short loc_18000480F
0x1800047fe  mov     rcx, rbx; this
0x180004801  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x180004806  mov     rcx, rbx
0x180004809  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000480f  add     rsp, 20h
0x180004813  pop     rbx
0x180004814  retn
```
