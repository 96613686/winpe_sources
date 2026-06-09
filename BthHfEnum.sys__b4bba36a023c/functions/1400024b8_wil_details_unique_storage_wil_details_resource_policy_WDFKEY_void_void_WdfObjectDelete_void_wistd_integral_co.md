# wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::reset(WDFKEY__ *)

- ea: `0x1400024b8`
- end: `0x1400024f9`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUWDFKEY__@@@Z`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140001a2c`
- `0x14002ae68`

## callees

- `0x1400024b8`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::reset(
        _QWORD *a1,
        __int64 a2)
{
  __int64 result; // rax

  if ( *a1 )
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x1400024b8  mov     [rsp+arg_0], rbx
0x1400024bd  push    rdi
0x1400024be  sub     rsp, 20h
0x1400024c2  mov     rdi, rdx
0x1400024c5  mov     rbx, rcx
0x1400024c8  mov     rdx, [rcx]
0x1400024cb  test    rdx, rdx
0x1400024ce  jz      short loc_1400024EA
0x1400024d0  mov     rax, cs:WdfFunctions_01015
0x1400024d7  mov     rcx, cs:WdfDriverGlobals
0x1400024de  mov     rax, [rax+680h]
0x1400024e5  call    _guard_dispatch_icall
0x1400024ea  mov     [rbx], rdi
0x1400024ed  mov     rbx, [rsp+28h+arg_0]
0x1400024f2  add     rsp, 20h
0x1400024f6  pop     rdi
0x1400024f7  retn
```
