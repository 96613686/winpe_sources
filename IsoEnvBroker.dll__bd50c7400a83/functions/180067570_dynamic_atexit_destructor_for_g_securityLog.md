# _dynamic_atexit_destructor_for__g_securityLog__

- ea: `0x180067570`
- end: `0x1800675b2`
- name: `_dynamic_atexit_destructor_for__g_securityLog__`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18005f8cc`
- `0x180067570`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067599`
- `AUTHZ!AuthzUnregisterSecurityEventSource` at `0x180067586`
- `AUTHZ!AuthzUnregisterSecurityEventSource` at `0x180067586`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_securityLog__()
{
  DWORD LastError; // [rsp+30h] [rbp+8h] BYREF

  if ( byte_1800B9248 )
  {
    if ( AuthzUnregisterSecurityEventSource(0, &g_securityLog) )
    {
      byte_1800B9248 = 0;
    }
    else
    {
      LastError = GetLastError();
      IsoEnvBrokerTelemetry::SecurityLogShutdownFailure<unsigned long>((int *)&LastError);
    }
  }
}

```

## disassembly

```asm
0x180067570  sub     rsp, 28h
0x180067574  cmp     cs:byte_1800B9248, 0
0x18006757b  jz      short loc_1800675AD
0x18006757d  lea     rdx, ?g_securityLog@@3VSecurityLog@@A; phEventProvider
0x180067584  xor     ecx, ecx; dwFlags
0x180067586  call    cs:__imp_AuthzUnregisterSecurityEventSource
0x18006758c  test    eax, eax
0x18006758e  jz      short loc_180067599
0x180067590  mov     cs:byte_1800B9248, 0
0x180067597  jmp     short loc_1800675AD
0x180067599  call    cs:__imp_GetLastError
0x18006759f  lea     rcx, [rsp+28h+arg_0]
0x1800675a4  mov     [rsp+28h+arg_0], eax
0x1800675a8  call    ??$SecurityLogShutdownFailure@K@IsoEnvBrokerTelemetry@@SAX$$QEAK@Z; IsoEnvBrokerTelemetry::SecurityLogShutdownFailure<ulong>(ulong &&)
0x1800675ad  add     rsp, 28h
0x1800675b1  retn
```
