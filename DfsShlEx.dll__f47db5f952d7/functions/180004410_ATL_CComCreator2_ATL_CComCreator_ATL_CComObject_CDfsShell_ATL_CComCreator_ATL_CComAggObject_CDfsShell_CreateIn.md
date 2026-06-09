# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDfsShell>>,ATL::CComCreator<ATL::CComAggObject<CDfsShell>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004410`
- end: `0x18000441e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDfsShell@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCDfsShell@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004444`
- `0x18000463c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDfsShell>>,ATL::CComCreator<ATL::CComAggObject<CDfsShell>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CDfsShell>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CDfsShell>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180004410  test    rcx, rcx
0x180004413  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDfsShell@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDfsShell>>::CreateInstance(void *,_GUID const &,void * *)
0x180004419  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCDfsShell@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CDfsShell>>::CreateInstance(void *,_GUID const &,void * *)
```
