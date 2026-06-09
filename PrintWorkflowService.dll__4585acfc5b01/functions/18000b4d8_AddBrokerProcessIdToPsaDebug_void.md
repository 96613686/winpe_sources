# AddBrokerProcessIdToPsaDebug(void)

- ea: `0x18000b4d8`
- end: `0x18000b4f8`
- name: `?AddBrokerProcessIdToPsaDebug@@YAXXZ`
- size: `32`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180010c10`

## callees

- `0x18000b4d8`
- `0x18000b500`
- `0x18000e0ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b4e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b4e5`

## pseudocode

```c
void AddBrokerProcessIdToPsaDebug(void)
{
  DWORD CurrentProcessId; // ecx
  const char *v1; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( PrintCore::PrintSupportDebugHelper::IsPsaDebugEnabled() )
  {
    CurrentProcessId = GetCurrentProcessId();
    try
    {
      PrintCore::PrintSupportDebugHelper::AddPsaBrokerProcessId(CurrentProcessId);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\svc\\workflowservice.cpp",
        v1);
    }
  }
}

```

## disassembly

```asm
0x18000b4d8  sub     rsp, 28h
0x18000b4dc  call    ?IsPsaDebugEnabled@PrintSupportDebugHelper@PrintCore@@SA_NXZ; PrintCore::PrintSupportDebugHelper::IsPsaDebugEnabled(void)
0x18000b4e1  test    al, al
0x18000b4e3  jz      short loc_18000B4F3
0x18000b4e5  call    cs:__imp_GetCurrentProcessId
0x18000b4eb  mov     ecx, eax; unsigned int
0x18000b4ed  call    ?AddPsaBrokerProcessId@PrintSupportDebugHelper@PrintCore@@SAXI@Z; PrintCore::PrintSupportDebugHelper::AddPsaBrokerProcessId(uint)
0x18000b4f2  nop
0x18000b4f3  add     rsp, 28h
0x18000b4f7  retn
```
