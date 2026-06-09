# GetScoState(_SCOCONTEXT *)

- ea: `0x14000cb04`
- end: `0x14000cb37`
- name: `?GetScoState@@YA?AW4SCOSTATE@@PEAU_SCOCONTEXT@@@Z`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140001790`
- `0x14000e510`
- `0x14000e87c`
- `0x14000ecc4`
- `0x140012100`
- `0x140013148`
- `0x140013df8`

## callees

- `0x14000c570`
- `0x140011484`

## pseudocode

```c
__int64 __fastcall GetScoState(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1;
  wil::acquire_wdf_spin_lock(&v3, *(_QWORD *)(a1 + 368));
  LODWORD(v1) = *(_DWORD *)(v1 + 376);
  wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14000cb04  push    rbx
0x14000cb06  sub     rsp, 20h
0x14000cb0a  mov     rdx, [rcx+170h]
0x14000cb11  mov     rbx, rcx
0x14000cb14  lea     rcx, [rsp+28h+arg_0]
0x14000cb19  call    ?acquire_wdf_spin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAUWDFSPINLOCK__@@@Z; wil::acquire_wdf_spin_lock(WDFSPINLOCK__ *)
0x14000cb1e  mov     ebx, [rbx+178h]
0x14000cb24  lea     rcx, [rsp+28h+arg_0]
0x14000cb29  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x14000cb2e  mov     eax, ebx
0x14000cb30  add     rsp, 20h
0x14000cb34  pop     rbx
0x14000cb35  retn
```
