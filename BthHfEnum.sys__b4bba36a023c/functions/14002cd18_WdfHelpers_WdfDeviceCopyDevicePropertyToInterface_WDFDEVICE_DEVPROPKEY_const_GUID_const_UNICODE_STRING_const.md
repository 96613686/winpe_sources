# WdfHelpers::WdfDeviceCopyDevicePropertyToInterface(WDFDEVICE__ *,_DEVPROPKEY const &,_GUID const &,_UNICODE_STRING const &)

- ea: `0x14002cd18`
- end: `0x14002ce0a`
- name: `?WdfDeviceCopyDevicePropertyToInterface@WdfHelpers@@YAJPEAUWDFDEVICE__@@AEBU_DEVPROPKEY@@AEBU_GUID@@AEBU_UNICODE_STRING@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(WdfHelpers *__hidden this, struct WDFDEVICE__ *, const struct _DEVPROPKEY *, const struct _GUID *, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140001e70`

## callees

- `0x140001a50`
- `0x14001ae00`
- `0x14002cd18`
- `0x14002ce10`

## pseudocode

```c
__int64 __fastcall WdfHelpers::WdfDeviceCopyDevicePropertyToInterface(
        WdfHelpers *this,
        const struct _UNICODE_STRING *a2,
        struct WDFDEVICE__ *a3,
        const struct _GUID *a4)
{
  int v8; // ebx
  unsigned __int64 v9; // rax
  struct _DEVPROPKEY *v11; // [rsp+20h] [rbp-58h]
  void *v12; // [rsp+38h] [rbp-40h]
  __int64 v13; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v14[2]; // [rsp+48h] [rbp-30h] BYREF
  _QWORD v15[5]; // [rsp+50h] [rbp-28h] BYREF
  struct _DEVPROPKEY *v16; // [rsp+B8h] [rbp+40h] BYREF

  v15[1] = a2;
  v15[0] = 24;
  v15[2] = 0;
  LODWORD(v16) = 0;
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WdfHelpers *, _QWORD *, __int64, _QWORD, __int64 *, struct _DEVPROPKEY **))(WdfFunctions_01015 + 3472))(
         WdfDriverGlobals,
         this,
         v15,
         512,
         0,
         &v13,
         &v16);
  if ( v8 >= 0 )
  {
    *(_QWORD *)v14 = 0;
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, unsigned int *))(WdfFunctions_01015 + 1552))(
           WdfDriverGlobals,
           v13,
           v14);
    LODWORD(v11) = (_DWORD)v16;
    v8 = WdfHelpers::WdfDeviceSetPropertyToDeviceInterface(this, a3, a4, a2, v11, v14[0], v9, v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(&v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002cd18  push    rbp
0x14002cd1a  push    rbx
0x14002cd1b  push    rsi
0x14002cd1c  push    rdi
0x14002cd1d  push    r14
0x14002cd1f  push    r15
0x14002cd21  mov     rbp, rsp
0x14002cd24  sub     rsp, 78h
0x14002cd28  mov     rax, cs:WdfFunctions_01015
0x14002cd2f  mov     rsi, rcx
0x14002cd32  mov     [rbp+var_20], rdx
0x14002cd36  lea     rcx, [rbp+arg_8]
0x14002cd3a  mov     [rsp+78h+var_48], rcx
0x14002cd3f  mov     r14, r9
0x14002cd42  lea     rcx, [rbp+var_38]
0x14002cd46  mov     [rbp+var_28], 18h
0x14002cd4e  mov     qword ptr [rsp+78h+var_50], rcx
0x14002cd53  mov     r15, r8
0x14002cd56  mov     rcx, cs:WdfDriverGlobals
0x14002cd5d  lea     r8, [rbp+var_28]
0x14002cd61  mov     rdi, rdx
0x14002cd64  mov     [rbp+var_18], 0
0x14002cd6c  mov     dword ptr [rbp+arg_8], 0
0x14002cd73  mov     r9d, 200h
0x14002cd79  mov     [rbp+var_38], 0
0x14002cd81  mov     rdx, rsi
0x14002cd84  mov     rax, [rax+0D90h]
0x14002cd8b  mov     [rsp+78h+var_58], 0
0x14002cd94  call    _guard_dispatch_icall
0x14002cd99  mov     ebx, eax
0x14002cd9b  test    eax, eax
0x14002cd9d  js      short loc_14002CDF1
0x14002cd9f  mov     rax, cs:WdfFunctions_01015
0x14002cda6  lea     r8, [rbp+var_30]
0x14002cdaa  mov     rdx, [rbp+var_38]
0x14002cdae  mov     rcx, cs:WdfDriverGlobals
0x14002cdb5  mov     qword ptr [rbp+var_30], 0
0x14002cdbd  mov     rax, [rax+610h]
0x14002cdc4  call    _guard_dispatch_icall
0x14002cdc9  mov     [rsp+78h+var_48], rax; unsigned __int64
0x14002cdce  mov     r9, rdi; struct _UNICODE_STRING *
0x14002cdd1  mov     rax, qword ptr [rbp+var_30]
0x14002cdd5  mov     r8, r14; struct _GUID *
0x14002cdd8  mov     qword ptr [rsp+78h+var_50], rax; unsigned int
0x14002cddd  mov     rdx, r15; struct WDFDEVICE__ *
0x14002cde0  mov     eax, dword ptr [rbp+arg_8]
0x14002cde3  mov     rcx, rsi; this
0x14002cde6  mov     dword ptr [rsp+78h+var_58], eax; struct _DEVPROPKEY *
0x14002cdea  call    ?WdfDeviceSetPropertyToDeviceInterface@WdfHelpers@@YAJPEAUWDFDEVICE__@@AEBU_GUID@@AEBU_UNICODE_STRING@@AEBU_DEVPROPKEY@@K_KPEAX@Z; WdfHelpers::WdfDeviceSetPropertyToDeviceInterface(WDFDEVICE__ *,_GUID const &,_UNICODE_STRING const &,_DEVPROPKEY const &,ulong,unsigned __int64,void *)
0x14002cdef  mov     ebx, eax
0x14002cdf1  lea     rcx, [rbp+var_38]
0x14002cdf5  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x14002cdfa  mov     eax, ebx
0x14002cdfc  add     rsp, 78h
0x14002ce00  pop     r15
0x14002ce02  pop     r14
0x14002ce04  pop     rdi
0x14002ce05  pop     rsi
0x14002ce06  pop     rbx
0x14002ce07  pop     rbp
0x14002ce08  retn
```
