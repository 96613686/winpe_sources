# ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`scalar deleting destructor'(uint)

- ea: `0x140003f00`
- end: `0x140003f20`
- name: `??_G?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140005a60`
- `0x140009fb0`

## callees

- `0x140003580`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003f11`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003f11`

## pseudocode

```c
_QWORD *__fastcall ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`scalar deleting destructor'(
        _QWORD *a1)
{
  ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::~CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>(a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003f00  push    rbx
0x140003f02  sub     rsp, 20h
0x140003f06  mov     rbx, rcx
0x140003f09  call    ??1?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::~CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>(void)
0x140003f0e  mov     rcx, rbx
0x140003f11  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003f17  mov     rax, rbx
0x140003f1a  add     rsp, 20h
0x140003f1e  pop     rbx
0x140003f1f  retn
```
