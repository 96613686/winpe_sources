# WdfHelpers::WdfDeviceSetPropertyToDeviceInterface(WDFDEVICE__ *,_GUID const &,_UNICODE_STRING const &,_DEVPROPKEY const &,ulong,unsigned __int64,void *)

- ea: `0x14002ce10`
- end: `0x14002cf14`
- name: `?WdfDeviceSetPropertyToDeviceInterface@WdfHelpers@@YAJPEAUWDFDEVICE__@@AEBU_GUID@@AEBU_UNICODE_STRING@@AEBU_DEVPROPKEY@@K_KPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(WdfHelpers *__hidden this, struct WDFDEVICE__ *, const struct _GUID *, const struct _UNICODE_STRING *, const struct _DEVPROPKEY *, unsigned int, unsigned __int64, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140009d70`
- `0x140029824`
- `0x14002cd18`

## callees

- `0x140001a50`
- `0x14001ae00`
- `0x14002ce10`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14002ceee`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14002ceee`

## pseudocode

```c
__int64 __fastcall WdfHelpers::WdfDeviceSetPropertyToDeviceInterface(
        WdfHelpers *this,
        struct WDFDEVICE__ *a2,
        const struct _GUID *a3,
        const struct _UNICODE_STRING *a4,
        const struct _DEVPROPKEY *a5,
        unsigned int a6,
        unsigned __int64 a7)
{
  int v11; // ebx
  __int64 v13; // [rsp+40h] [rbp-48h] BYREF
  _OWORD v14[4]; // [rsp+48h] [rbp-40h] BYREF

  v13 = 0;
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64 *))(WdfFunctions_01015 + 2464))(
          WdfDriverGlobals,
          0,
          0,
          &v13);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WdfHelpers *, struct WDFDEVICE__ *, const struct _GUID *, __int64))(WdfFunctions_01015 + 632))(
            WdfDriverGlobals,
            this,
            a2,
            a3,
            v13);
    if ( v11 >= 0 )
    {
      v14[0] = 0;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01015 + 2472))(
        WdfDriverGlobals,
        v13,
        v14);
      v11 = IoSetDeviceInterfacePropertyData(v14, a4, 0, 0, (_DWORD)a5, a6, a7);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(&v13);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002ce10  push    rbx
0x14002ce12  push    rbp
0x14002ce13  push    rsi
0x14002ce14  push    rdi
0x14002ce15  push    r14
0x14002ce17  sub     rsp, 60h
0x14002ce1b  mov     rax, cs:WdfFunctions_01015
0x14002ce22  mov     r14, r9
0x14002ce25  mov     rdi, r8
0x14002ce28  mov     [rsp+88h+var_48], 0
0x14002ce31  mov     rsi, rdx
0x14002ce34  lea     r9, [rsp+88h+var_48]
0x14002ce39  mov     rbp, rcx
0x14002ce3c  xor     r8d, r8d
0x14002ce3f  mov     rax, [rax+9A0h]
0x14002ce46  xor     edx, edx
0x14002ce48  mov     rcx, cs:WdfDriverGlobals
0x14002ce4f  call    _guard_dispatch_icall
0x14002ce54  mov     ebx, eax
0x14002ce56  test    eax, eax
0x14002ce58  js      loc_14002CEFC
0x14002ce5e  mov     rcx, [rsp+88h+var_48]
0x14002ce63  mov     r9, rdi
0x14002ce66  mov     rax, cs:WdfFunctions_01015
0x14002ce6d  mov     r8, rsi
0x14002ce70  mov     [rsp+88h+var_68], rcx
0x14002ce75  mov     rdx, rbp
0x14002ce78  mov     rcx, cs:WdfDriverGlobals
0x14002ce7f  mov     rax, [rax+278h]
0x14002ce86  call    _guard_dispatch_icall
0x14002ce8b  mov     ebx, eax
0x14002ce8d  test    eax, eax
0x14002ce8f  js      short loc_14002CEFC
0x14002ce91  mov     rax, cs:WdfFunctions_01015
0x14002ce98  lea     r8, [rsp+88h+var_40]
0x14002ce9d  mov     rdx, [rsp+88h+var_48]
0x14002cea2  xorps   xmm0, xmm0
0x14002cea5  mov     rcx, cs:WdfDriverGlobals
0x14002ceac  movups  [rsp+88h+var_40], xmm0
0x14002ceb1  mov     rax, [rax+9A8h]
0x14002ceb8  call    _guard_dispatch_icall
0x14002cebd  mov     rax, [rsp+88h+arg_30]
0x14002cec5  xor     r9d, r9d
0x14002cec8  mov     ecx, [rsp+88h+arg_28]
0x14002cecf  xor     r8d, r8d
0x14002ced2  mov     [rsp+88h+var_58], rax
0x14002ced7  mov     rdx, r14
0x14002ceda  mov     eax, dword ptr [rsp+88h+arg_20]
0x14002cee1  mov     [rsp+88h+var_60], ecx
0x14002cee5  lea     rcx, [rsp+88h+var_40]
0x14002ceea  mov     dword ptr [rsp+88h+var_68], eax
0x14002ceee  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14002cef5  nop     dword ptr [rax+rax+00h]
0x14002cefa  mov     ebx, eax
0x14002cefc  lea     rcx, [rsp+88h+var_48]
0x14002cf01  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x14002cf06  mov     eax, ebx
0x14002cf08  add     rsp, 60h
0x14002cf0c  pop     r14
0x14002cf0e  pop     rdi
0x14002cf0f  pop     rsi
0x14002cf10  pop     rbp
0x14002cf11  pop     rbx
0x14002cf12  retn
```
