# wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x140001a10`
- end: `0x140001a23`
- name: `??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400285d4`
- `0x14002affc`

## pseudocode

```c
__int64 __fastcall wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  *(_QWORD *)a1 = a2;
  result = a1;
  *(_QWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 16) = 1;
  return result;
}

```

## disassembly

```asm
0x140001a10  mov     [rcx], rdx
0x140001a13  mov     rax, rcx
0x140001a16  mov     qword ptr [rcx+8], 0
0x140001a1e  mov     byte ptr [rcx+10h], 1
0x140001a22  retn
```
