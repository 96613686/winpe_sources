# wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(void)

- ea: `0x140001a2c`
- end: `0x140001a48`
- name: `??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400285d4`
- `0x14002affc`

## callees

- `0x140001a2c`
- `0x1400024b8`

## pseudocode

```c
__int64 __fastcall wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 16) )
    return wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::reset(
             *(_QWORD *)a1,
             *(_QWORD *)(a1 + 8));
  return result;
}

```

## disassembly

```asm
0x140001a2c  sub     rsp, 28h
0x140001a30  cmp     byte ptr [rcx+10h], 0
0x140001a34  jz      short loc_140001A42
0x140001a36  mov     rdx, [rcx+8]
0x140001a3a  mov     rcx, [rcx]
0x140001a3d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUWDFKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::reset(WDFKEY__ *)
0x140001a42  add     rsp, 28h
0x140001a46  retn
```
