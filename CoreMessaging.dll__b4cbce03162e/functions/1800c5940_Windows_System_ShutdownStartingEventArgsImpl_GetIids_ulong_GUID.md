# Windows::System::ShutdownStartingEventArgsImpl::GetIids(ulong *,_GUID * *)

- ea: `0x1800c5940`
- end: `0x1800c599f`
- name: `?GetIids@ShutdownStartingEventArgsImpl@System@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::System::ShutdownStartingEventArgsImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800c5654`
- `0x1800c5940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c5962`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c5962`

## pseudocode

```c
__int64 __fastcall Windows::System::ShutdownStartingEventArgsImpl::GetIids(
        Windows::System::ShutdownStartingEventArgsImpl *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::DeferrableEventArgs<Windows::System::IDispatcherQueueShutdownStartingEventArgs,Windows::System::ShutdownStartingEventArgsImpl>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800c5940  mov     [rsp+arg_0], rbx
0x1800c5945  push    rdi
0x1800c5946  sub     rsp, 20h
0x1800c594a  mov     qword ptr [r8], 0
0x1800c5951  mov     ecx, 20h ; ' '; cb
0x1800c5956  mov     dword ptr [rdx], 0
0x1800c595c  mov     rbx, r8
0x1800c595f  mov     rdi, rdx
0x1800c5962  call    cs:__imp_CoTaskMemAlloc
0x1800c5968  mov     r8, rax
0x1800c596b  test    rax, rax
0x1800c596e  jnz     short loc_1800C5977
0x1800c5970  mov     eax, 8007000Eh
0x1800c5975  jmp     short loc_1800C5994
0x1800c5977  lea     rdx, [rsp+28h+arg_8]
0x1800c597c  mov     [rsp+28h+arg_8], 0
0x1800c5984  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@V?$DeferrableEventArgs@UIDispatcherQueueShutdownStartingEventArgs@System@Windows@@VShutdownStartingEventArgsImpl@23@@23@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Microsoft::WRL::DeferrableEventArgs<Windows::System::IDispatcherQueueShutdownStartingEventArgs,Windows::System::ShutdownStartingEventArgsImpl>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800c5989  mov     dword ptr [rdi], 2
0x1800c598f  xor     eax, eax
0x1800c5991  mov     [rbx], r8
0x1800c5994  mov     rbx, [rsp+28h+arg_0]
0x1800c5999  add     rsp, 20h
0x1800c599d  pop     rdi
0x1800c599e  retn
```
