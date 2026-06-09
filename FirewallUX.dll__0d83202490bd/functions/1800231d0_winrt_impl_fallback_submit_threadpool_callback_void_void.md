# winrt::impl::fallback_submit_threadpool_callback(void *,void *)

- ea: `0x1800231d0`
- end: `0x18002325b`
- name: `?fallback_submit_threadpool_callback@impl@winrt@@YAXPEAX0@Z`
- size: `139`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, __int64 *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800025f8`
- `0x18000b5d0`
- `0x1800231d0`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::fallback_submit_threadpool_callback(PTP_CALLBACK_INSTANCE Instance, __int64 *Context)
{
  __int64 v2; // rcx
  int *v3; // rdi
  int v5; // eax
  _QWORD v6[3]; // [rsp+40h] [rbp-18h] BYREF

  v2 = *Context;
  v3 = (int *)Context[2];
  v6[1] = Context[1];
  v6[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(winrt::impl *__hidden, struct winrt::impl::com_callback_args *), _QWORD *, void *, int, _QWORD))(*(_QWORD *)v2 + 24LL))(
         v2,
         winrt::impl::resume_apartment_callback,
         v6,
         &winrt::impl::guid_v<winrt::impl::ICallbackWithNoReentrancyToApplicationSTA>,
         5,
         0);
  if ( v5 < 0 )
  {
    *v3 = v5;
    (*(void (**)(void))Context[1])();
  }
  if ( *Context )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(Context);
  operator delete(Context);
}

```

## disassembly

```asm
0x1800231d0  mov     r11, rsp
0x1800231d3  mov     [r11+8], rbx
0x1800231d7  push    rdi
0x1800231d8  sub     rsp, 50h
0x1800231dc  mov     rax, [rdx+8]
0x1800231e0  lea     r9, ??$guid_v@UICallbackWithNoReentrancyToApplicationSTA@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ICallbackWithNoReentrancyToApplicationSTA>
0x1800231e7  mov     rcx, [rdx]
0x1800231ea  lea     r8, [r11-18h]
0x1800231ee  mov     rdi, [rdx+10h]
0x1800231f2  mov     rbx, rdx
0x1800231f5  mov     [r11-10h], rax
0x1800231f9  lea     rdx, ?resume_apartment_callback@impl@winrt@@YAHPEAUcom_callback_args@12@@Z; winrt::impl::resume_apartment_callback(winrt::impl::com_callback_args *)
0x180023200  mov     qword ptr [r11-18h], 0
0x180023208  mov     rax, [rcx]
0x18002320b  mov     qword ptr [r11-30h], 0
0x180023213  mov     [rsp+58h+var_38], 5
0x18002321b  mov     rax, [rax+18h]
0x18002321f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023224  test    eax, eax
0x180023226  jns     short loc_180023236
0x180023228  mov     [rdi], eax
0x18002322a  mov     rcx, [rbx+8]
0x18002322e  mov     rax, [rcx]
0x180023231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023236  cmp     qword ptr [rbx], 0
0x18002323a  jz      short loc_180023244
0x18002323c  mov     rcx, rbx
0x18002323f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180023244  mov     edx, 18h; unsigned __int64
0x180023249  mov     rcx, rbx; void *
0x18002324c  mov     rbx, [rsp+58h+arg_0]
0x180023251  add     rsp, 50h
0x180023255  pop     rdi
0x180023256  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
