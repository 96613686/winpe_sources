# DllUnregisterServer

- ea: `0x180017cf0`
- end: `0x180017d19`
- name: `DllUnregisterServer`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x1800178d8`
- `0x180017cf0`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rcx
  int updated; // eax
  int v2; // ebx

  updated = CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::UpdateRegistry(v0, 0);
  v2 = updated;
  if ( updated < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  return v2;
}

```

## disassembly

```asm
0x180017cf0  push    rbx
0x180017cf2  sub     rsp, 20h
0x180017cf6  xor     edx, edx
0x180017cf8  call    ?UpdateRegistry@?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@QEAAJH@Z; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::UpdateRegistry(int)
0x180017cfd  mov     ebx, eax
0x180017cff  test    eax, eax
0x180017d01  jns     short loc_180017D0A
0x180017d03  mov     ecx, eax
0x180017d05  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017d0a  mov     ecx, ebx
0x180017d0c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017d11  mov     eax, ebx
0x180017d13  add     rsp, 20h
0x180017d17  pop     rbx
0x180017d18  retn
```
