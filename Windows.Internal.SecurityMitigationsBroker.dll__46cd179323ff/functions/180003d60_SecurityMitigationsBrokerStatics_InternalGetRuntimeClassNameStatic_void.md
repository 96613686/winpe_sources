# SecurityMitigationsBrokerStatics::InternalGetRuntimeClassNameStatic(void)

- ea: `0x180003d60`
- end: `0x180003d68`
- name: `?InternalGetRuntimeClassNameStatic@SecurityMitigationsBrokerStatics@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180003d60`: `Windows.Internal.SecurityMitigationsBroker`

## pseudocode

```c
const unsigned __int16 *SecurityMitigationsBrokerStatics::InternalGetRuntimeClassNameStatic(void)
{
  return L"Windows.Internal.SecurityMitigationsBroker";
}

```

## disassembly

```asm
0x180003d60  lea     rax, aWindowsInterna_0; "Windows.Internal.SecurityMitigationsBro"...
0x180003d67  retn
```
