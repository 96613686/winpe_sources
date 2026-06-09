# BriUnregisterFromBrokerAvailability

- ea: `0x180008c90`
- end: `0x180008ca2`
- name: `BriUnregisterFromBrokerAvailability`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008c90`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180008c9b`

## pseudocode

```c
__int64 __fastcall BriUnregisterFromBrokerAvailability(__int64 a1)
{
  if ( a1 )
    return RtlUnsubscribeWnfNotificationWaitForCompletion();
  else
    return 3221225485LL;
}

```

## disassembly

```asm
0x180008c90  test    rcx, rcx
0x180008c93  jnz     short loc_180008C9B
0x180008c95  mov     eax, 0C000000Dh
0x180008c9a  retn
0x180008c9b  jmp     cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
```
