# TokenUtility::_SetTokenAsEnterpriseExemptIfNeeded(void *)

- ea: `0x1800327ec`
- end: `0x180032827`
- name: `?_SetTokenAsEnterpriseExemptIfNeeded@TokenUtility@@AEAAXPEAX@Z`
- size: `59`
- prototype: `void(TokenUtility *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180030a60`
- `0x180030cb0`

## callees

- `0x18001d1dc`
- `0x1800327ec`
- `0x180035e2c`

## import_xrefs

- `KERNELBASE!GetIsEdpEnabled` at `0x1800327f5`
- `KERNELBASE!GetIsEdpEnabled` at `0x1800327f5`

## string_xrefs

- `0x180032815`: `TokenUtility::_SetTokenAsEnterpriseExemptIfNeeded`
- `0x18003280e`: `SrpSetTokenEnterpriseExempt failed! Error: %d`

## pseudocode

```c
void __fastcall TokenUtility::_SetTokenAsEnterpriseExemptIfNeeded(TokenUtility *this, void *a2)
{
  int v3; // eax

  if ( (unsigned int)GetIsEdpEnabled(this) )
  {
    v3 = SrpSetTokenEnterpriseExempt(a2);
    if ( v3 < 0 )
      PrintScanBrokerTelemetry::WriteDbgTraceWarning(
        "TokenUtility::_SetTokenAsEnterpriseExemptIfNeeded",
        L"SrpSetTokenEnterpriseExempt failed! Error: %d",
        (unsigned int)v3);
  }
}

```

## disassembly

```asm
0x1800327ec  push    rbx
0x1800327ee  sub     rsp, 20h
0x1800327f2  mov     rbx, rdx
0x1800327f5  call    cs:__imp_GetIsEdpEnabled
0x1800327fb  test    eax, eax
0x1800327fd  jz      short loc_180032821
0x1800327ff  mov     rcx, rbx; TokenHandle
0x180032802  call    SrpSetTokenEnterpriseExempt
0x180032807  test    eax, eax
0x180032809  jns     short loc_180032821
0x18003280b  mov     r8d, eax
0x18003280e  lea     rdx, aSrpsettokenent; "SrpSetTokenEnterpriseExempt failed! Err"...
0x180032815  lea     rcx, aTokenutilitySe; "TokenUtility::_SetTokenAsEnterpriseExem"...
0x18003281c  call    ?WriteDbgTraceWarning@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180032821  add     rsp, 20h
0x180032825  pop     rbx
0x180032826  retn
```
