# [thunk]:ATL::CComContainedObject<CDfsShell>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800051f0`
- end: `0x1800051f9`
- name: `?QueryInterface@?$CComContainedObject@VCDfsShell@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800051d0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShell>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CDfsShell>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x1800051f0  sub     rcx, 8
0x1800051f4  jmp     ?QueryInterface@?$CComContainedObject@VCDfsShell@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CDfsShell>::QueryInterface(_GUID const &,void * *)
```
