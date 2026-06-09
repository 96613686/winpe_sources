# winrt::impl::resume_apartment_sync(winrt::com_ptr<winrt::impl::IContextCallback> const &,std::experimental::coroutine_handle<void>,int *)

- ea: `0x18001ae30`
- end: `0x18001aeb5`
- name: `?resume_apartment_sync@impl@winrt@@YA_NAEBU?$com_ptr@UIContextCallback@impl@winrt@@@2@U?$coroutine_handle@X@experimental@std@@PEAH@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a290`
- `0x18001adc0`

## callees

- `0x18001ae30`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
char __fastcall winrt::impl::resume_apartment_sync(__int64 *a1, __int64 a2, int *a3)
{
  __int64 v3; // rcx
  int v5; // eax
  _QWORD v7[2]; // [rsp+40h] [rbp-28h] BYREF

  v3 = *a1;
  v7[1] = a2;
  v7[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(winrt::impl *__hidden, struct winrt::impl::com_callback_args *), _QWORD *, __int64 *, int, _QWORD))(*(_QWORD *)v3 + 24LL))(
         v3,
         winrt::impl::resume_apartment_callback,
         v7,
         winrt::impl::guid_v<winrt::impl::ICallbackWithNoReentrancyToApplicationSTA>,
         5,
         0);
  if ( v5 >= 0 )
    return 1;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001ae30  push    rbx
0x18001ae32  sub     rsp, 60h
0x18001ae36  mov     rax, cs:__security_cookie
0x18001ae3d  xor     rax, rsp
0x18001ae40  mov     [rsp+68h+var_18], rax
0x18001ae45  mov     rcx, [rcx]
0x18001ae48  lea     r9, ??$guid_v@UICallbackWithNoReentrancyToApplicationSTA@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ICallbackWithNoReentrancyToApplicationSTA>
0x18001ae4f  mov     rbx, r8
0x18001ae52  mov     [rsp+68h+var_20], rdx
0x18001ae57  xor     r8d, r8d
0x18001ae5a  lea     rdx, ?resume_apartment_callback@impl@winrt@@YAHPEAUcom_callback_args@12@@Z; winrt::impl::resume_apartment_callback(winrt::impl::com_callback_args *)
0x18001ae61  mov     [rsp+68h+var_28], r8
0x18001ae66  mov     rax, [rcx]
0x18001ae69  mov     [rsp+68h+var_40], r8
0x18001ae6e  lea     r8, [rsp+68h+var_28]
0x18001ae73  mov     [rsp+68h+var_48], 5
0x18001ae7b  mov     rax, [rax+18h]
0x18001ae7f  call    cs:__guard_dispatch_icall_fptr
0x18001ae85  test    eax, eax
0x18001ae87  jns     short loc_18001AEA0
0x18001ae89  mov     [rbx], eax
0x18001ae8b  xor     al, al
0x18001ae8d  mov     rcx, [rsp+68h+var_18]
0x18001ae92  xor     rcx, rsp; StackCookie
0x18001ae95  call    __security_check_cookie
0x18001ae9a  add     rsp, 60h
0x18001ae9e  pop     rbx
0x18001ae9f  retn
0x18001aea0  mov     al, 1
0x18001aea2  mov     rcx, [rsp+68h+var_18]
0x18001aea7  xor     rcx, rsp; StackCookie
0x18001aeaa  call    __security_check_cookie
0x18001aeaf  add     rsp, 60h
0x18001aeb3  pop     rbx
0x18001aeb4  retn
```
