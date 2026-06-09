# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>(void)

- ea: `0x180002080`
- end: `0x18000208b`
- name: `??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@@Details@WRL@Microsoft@@IEAA@XZ`
- size: `11`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800016b0`
- `0x180001f10`
- `0x1800042d4`
- `0x18000645c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 12) = 1;
  return a1;
}

```

## disassembly

```asm
0x180002080  mov     dword ptr [rcx+0Ch], 1
0x180002087  mov     rax, rcx
0x18000208a  retn
```
