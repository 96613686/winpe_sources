# wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)

- ea: `0x140001a50`
- end: `0x140001a7c`
- name: `??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140028008`
- `0x1400285d4`
- `0x14002ae68`
- `0x14002affc`
- `0x14002cd18`
- `0x14002ce10`

## callees

- `0x140001a50`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
  return result;
}

```

## disassembly

```asm
0x140001a50  sub     rsp, 28h
0x140001a54  mov     rdx, [rcx]
0x140001a57  test    rdx, rdx
0x140001a5a  jz      short loc_140001A76
0x140001a5c  mov     rax, cs:WdfFunctions_01015
0x140001a63  mov     rcx, cs:WdfDriverGlobals
0x140001a6a  mov     rax, [rax+680h]
0x140001a71  call    _guard_dispatch_icall
0x140001a76  add     rsp, 28h
0x140001a7a  retn
```
