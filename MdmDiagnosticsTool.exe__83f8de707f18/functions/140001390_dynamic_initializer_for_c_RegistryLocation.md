# _dynamic_initializer_for__c_RegistryLocation__

- ea: `0x140001390`
- end: `0x1400013c1`
- name: `_dynamic_initializer_for__c_RegistryLocation__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140001394`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140001394`

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
0x140001390  sub     rsp, 28h
0x140001394  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000139b  nop     dword ptr [rax+rax+00h]
0x1400013a0  test    al, al
0x1400013a2  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\MDMDiagnostics"
0x1400013a9  lea     rcx, aOsdataSoftware; "OSData\\Software\\Microsoft\\MDMDiagnos"...
0x1400013b0  cmovz   rcx, rdx
0x1400013b4  mov     cs:?c_RegistryLocation@@3PEBGEB, rcx; ushort const * const c_RegistryLocation
0x1400013bb  add     rsp, 28h
0x1400013bf  retn
```
