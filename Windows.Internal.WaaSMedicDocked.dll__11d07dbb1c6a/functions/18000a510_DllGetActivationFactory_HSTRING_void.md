# DllGetActivationFactory(HSTRING__ *,void * *)

- ea: `0x18000a510`
- end: `0x18000a515`
- name: `?DllGetActivationFactory@@YAJPEAUHSTRING__@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(HSTRING, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b2fc`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall DllGetActivationFactory(HSTRING a1, void **a2)
{
  return WINRT_GetActivationFactory(a1, (struct Microsoft::WRL::Details::CreatorMap *)a2);
}

```

## disassembly

```asm
0x18000a510  jmp     WINRT_GetActivationFactory
```
