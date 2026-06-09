# CVsShellExtHandler::Create(_GUID const &,_GUID const *,ulong,ulong,IPropertyStorage * *)

- ea: `0x180002480`
- end: `0x18000248f`
- name: `?Create@CVsShellExtHandler@@UEAAJAEBU_GUID@@PEBU2@KKPEAPEAUIPropertyStorage@@@Z`
- size: `15`
- prototype: `__int64 __fastcall(CVsShellExtHandler *this, const struct _GUID *, const struct _GUID *, __int64, unsigned int, struct IPropertyStorage **)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall CVsShellExtHandler::Create(
        CVsShellExtHandler *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned int a5,
        struct IPropertyStorage **a6)
{
  *a6 = 0;
  return 2147500033LL;
}

```

## disassembly

```asm
0x180002480  mov     rax, [rsp+arg_28]
0x180002485  and     qword ptr [rax], 0
0x180002489  mov     eax, 80004001h
0x18000248e  retn
```
