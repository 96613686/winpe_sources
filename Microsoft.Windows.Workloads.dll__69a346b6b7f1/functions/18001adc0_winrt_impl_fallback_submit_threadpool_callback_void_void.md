# winrt::impl::fallback_submit_threadpool_callback(void *,void *)

- ea: `0x18001adc0`
- end: `0x18001ae0a`
- name: `?fallback_submit_threadpool_callback@impl@winrt@@YAXPEAX0@Z`
- size: `74`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, void (***Context)(void))`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800040a0`
- `0x18001adc0`
- `0x18001ae30`
- `0x18003509c`
- `0x18003bed0`

## pseudocode

```c
void __fastcall winrt::impl::fallback_submit_threadpool_callback(
        PTP_CALLBACK_INSTANCE Instance,
        void (***Context)(void))
{
  if ( !(unsigned __int8)winrt::impl::resume_apartment_sync(Context, Context[1], Context[2]) )
    (*Context[1])();
  if ( *Context )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(Context);
  operator delete(Context);
}

```

## disassembly

```asm
0x18001adc0  push    rbx
0x18001adc2  sub     rsp, 20h
0x18001adc6  mov     r8, [rdx+10h]
0x18001adca  mov     rbx, rdx
0x18001adcd  mov     rdx, [rdx+8]
0x18001add1  mov     rcx, rbx
0x18001add4  call    ?resume_apartment_sync@impl@winrt@@YA_NAEBU?$com_ptr@UIContextCallback@impl@winrt@@@2@U?$coroutine_handle@X@experimental@std@@PEAH@Z; winrt::impl::resume_apartment_sync(winrt::com_ptr<winrt::impl::IContextCallback> const &,std::experimental::coroutine_handle<void>,int *)
0x18001add9  test    al, al
0x18001addb  jnz     short loc_18001ADEA
0x18001addd  mov     rcx, [rbx+8]
0x18001ade1  mov     rax, [rcx]
0x18001ade4  call    cs:__guard_dispatch_icall_fptr
0x18001adea  cmp     qword ptr [rbx], 0
0x18001adee  jz      short loc_18001ADF8
0x18001adf0  mov     rcx, rbx
0x18001adf3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001adf8  mov     edx, 18h; unsigned __int64
0x18001adfd  mov     rcx, rbx; void *
0x18001ae00  add     rsp, 20h
0x18001ae04  pop     rbx
0x18001ae05  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
