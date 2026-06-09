# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::wait_callback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180020080`
- end: `0x1800200eb`
- name: `?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `107`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800082d4`
- `0x18001f6f8`
- `0x180020080`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800200cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800200cf`

## pseudocode

```c
void __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::wait_callback(
        PTP_CALLBACK_INSTANCE Instance,
        wil::details **Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  wil::details *v6; // rcx

  if ( ((_BYTE)Context[17] & 1) == 0 )
    wil::details::ResetEvent(Context[15], Context);
  v6 = Context[14];
  if ( !v6 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  (*(void (__fastcall **)(wil::details *, wil::details **, PTP_WAIT, __int64))(*(_QWORD *)v6 + 32LL))(
    v6,
    Context,
    Wait,
    WaitResult);
  if ( ((_BYTE)Context[17] & 2) == 0 )
    SetThreadpoolWait(Wait, Context[15], 0);
}

```

## disassembly

```asm
0x180020080  mov     [rsp+arg_0], rbx
0x180020085  mov     [rsp+arg_8], rsi
0x18002008a  push    rdi
0x18002008b  sub     rsp, 20h
0x18002008f  test    byte ptr [rdx+88h], 1
0x180020096  mov     rsi, r8
0x180020099  mov     rdi, rdx
0x18002009c  jnz     short loc_1800200A7
0x18002009e  mov     rcx, [rdx+78h]; this
0x1800200a2  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1800200a7  mov     rcx, [rdi+70h]; this
0x1800200ab  test    rcx, rcx
0x1800200ae  jz      short loc_1800200E5
0x1800200b0  mov     rax, [rcx]
0x1800200b3  mov     rax, [rax+20h]
0x1800200b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200bc  test    byte ptr [rdi+88h], 2
0x1800200c3  jnz     short loc_1800200D5
0x1800200c5  mov     rdx, [rdi+78h]; h
0x1800200c9  xor     r8d, r8d; pftTimeout
0x1800200cc  mov     rcx, rsi; pwa
0x1800200cf  call    cs:__imp_SetThreadpoolWait
0x1800200d5  mov     rbx, [rsp+28h+arg_0]
0x1800200da  mov     rsi, [rsp+28h+arg_8]
0x1800200df  add     rsp, 20h
0x1800200e3  pop     rdi
0x1800200e4  retn
0x1800200e5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
