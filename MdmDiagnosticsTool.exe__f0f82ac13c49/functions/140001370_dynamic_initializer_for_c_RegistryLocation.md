# _dynamic_initializer_for__c_RegistryLocation__

- ea: `0x140001370`
- end: `0x14000139a`
- name: `_dynamic_initializer_for__c_RegistryLocation__`
- size: `42`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140001374`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140001374`

## pseudocode

```c
__int64 dynamic_initializer_for__c_RegistryLocation__()
{
  __int64 result; // rax
  const WCHAR *v1; // rcx

  result = RtlIsStateSeparationEnabled();
  v1 = L"OSData\\Software\\Microsoft\\MDMDiagnostics";
  if ( !(_BYTE)result )
    v1 = L"Software\\Microsoft\\MDMDiagnostics";
  c_RegistryLocation = v1;
  return result;
}

```

## disassembly

```asm
0x140001370  sub     rsp, 28h
0x140001374  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000137a  test    al, al
0x14000137c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\MDMDiagnostics"
0x140001383  lea     rcx, aOsdataSoftware; "OSData\\Software\\Microsoft\\MDMDiagnos"...
0x14000138a  cmovz   rcx, rdx
0x14000138e  mov     cs:?c_RegistryLocation@@3PEBGEB, rcx; ushort const * const c_RegistryLocation
0x140001395  add     rsp, 28h
0x140001399  retn
```
