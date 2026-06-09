# wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)

- ea: `0x14000c570`
- end: `0x14000c59c`
- name: `??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000cb04`
- `0x14000d140`
- `0x14000d76c`
- `0x14000e510`
- `0x14000fa40`
- `0x14001117c`
- `0x1400139e8`
- `0x140013df8`
- `0x140015e9c`

## callees

- `0x14000c570`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2536))(WdfDriverGlobals);
  return result;
}

```

## disassembly

```asm
0x14000c570  sub     rsp, 28h
0x14000c574  mov     rdx, [rcx]
0x14000c577  test    rdx, rdx
0x14000c57a  jz      short loc_14000C596
0x14000c57c  mov     rax, cs:WdfFunctions_01015
0x14000c583  mov     rcx, cs:WdfDriverGlobals
0x14000c58a  mov     rax, [rax+9E8h]
0x14000c591  call    _guard_dispatch_icall
0x14000c596  add     rsp, 28h
0x14000c59a  retn
```
