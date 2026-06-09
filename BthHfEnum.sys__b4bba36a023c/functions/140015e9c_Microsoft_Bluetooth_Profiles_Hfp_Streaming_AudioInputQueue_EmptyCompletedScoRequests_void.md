# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::EmptyCompletedScoRequests(void)

- ea: `0x140015e9c`
- end: `0x140015f53`
- name: `?EmptyCompletedScoRequests@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXXZ`
- size: `183`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002d044`
- `0x14002e860`

## callees

- `0x14000c570`
- `0x140011484`
- `0x140015e9c`
- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::EmptyCompletedScoRequests(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *this)
{
  __int64 v2; // rax
  char v3; // [rsp+30h] [rbp+8h] BYREF

  wil::acquire_wdf_spin_lock(&v3, *((_QWORD *)this + 29));
  while ( (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 112))(
            WdfDriverGlobals,
            *((_QWORD *)this + 30)) )
  {
    v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 152))(
           WdfDriverGlobals,
           *((_QWORD *)this + 30));
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, v2);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 136))(
      WdfDriverGlobals,
      *((_QWORD *)this + 30),
      0);
  }
  wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v3);
}

```

## disassembly

```asm
0x140015e9c  push    rbx
0x140015e9e  sub     rsp, 20h
0x140015ea2  mov     rdx, [rcx+0E8h]
0x140015ea9  mov     rbx, rcx
0x140015eac  lea     rcx, [rsp+28h+arg_0]
0x140015eb1  call    ?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z; wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)
0x140015eb6  mov     rax, cs:WdfFunctions_01015
0x140015ebd  mov     rdx, [rbx+0F0h]
0x140015ec4  mov     rcx, cs:WdfDriverGlobals
0x140015ecb  mov     rax, [rax+70h]
0x140015ecf  call    _guard_dispatch_icall
0x140015ed4  test    eax, eax
0x140015ed6  jz      short loc_140015F42
0x140015ed8  mov     rax, cs:WdfFunctions_01015
0x140015edf  mov     rdx, [rbx+0F0h]
0x140015ee6  mov     rcx, cs:WdfDriverGlobals
0x140015eed  mov     rax, [rax+98h]
0x140015ef4  call    _guard_dispatch_icall
0x140015ef9  mov     rcx, cs:WdfFunctions_01015
0x140015f00  mov     rdx, rax
0x140015f03  mov     r8, [rcx+680h]
0x140015f0a  mov     rcx, cs:WdfDriverGlobals
0x140015f11  mov     rax, r8
0x140015f14  call    _guard_dispatch_icall
0x140015f19  mov     rax, cs:WdfFunctions_01015
0x140015f20  xor     r8d, r8d
0x140015f23  mov     rdx, [rbx+0F0h]
0x140015f2a  mov     rcx, cs:WdfDriverGlobals
0x140015f31  mov     rax, [rax+88h]
0x140015f38  call    _guard_dispatch_icall
0x140015f3d  jmp     loc_140015EB6
0x140015f42  lea     rcx, [rsp+28h+arg_0]
0x140015f47  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x140015f4c  add     rsp, 20h
0x140015f50  pop     rbx
0x140015f51  retn
```
