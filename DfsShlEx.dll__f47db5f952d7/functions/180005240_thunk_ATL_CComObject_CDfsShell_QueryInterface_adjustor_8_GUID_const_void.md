# [thunk]:ATL::CComObject<CDfsShell>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180005240`
- end: `0x180005249`
- name: `?QueryInterface@?$CComObject@VCDfsShell@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005220`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDfsShell>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CDfsShell>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180005240  sub     rcx, 8
0x180005244  jmp     ?QueryInterface@?$CComObject@VCDfsShell@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CDfsShell>::QueryInterface(_GUID const &,void * *)
```
