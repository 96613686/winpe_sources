# DllRegisterServer

- ea: `0x180017cb0`
- end: `0x180017cdc`
- name: `DllRegisterServer`
- size: `44`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x1800178d8`
- `0x180017cb0`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rcx
  int updated; // eax
  int v2; // ebx

  updated = CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::UpdateRegistry(v0, 1);
  v2 = updated;
  if ( updated < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  return v2;
}

```

## disassembly

```asm
0x180017cb0  push    rbx
0x180017cb2  sub     rsp, 20h
0x180017cb6  mov     edx, 1
0x180017cbb  call    ?UpdateRegistry@?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@QEAAJH@Z; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::UpdateRegistry(int)
0x180017cc0  mov     ebx, eax
0x180017cc2  test    eax, eax
0x180017cc4  jns     short loc_180017CCD
0x180017cc6  mov     ecx, eax
0x180017cc8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017ccd  mov     ecx, ebx
0x180017ccf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017cd4  mov     eax, ebx
0x180017cd6  add     rsp, 20h
0x180017cda  pop     rbx
0x180017cdb  retn
```
