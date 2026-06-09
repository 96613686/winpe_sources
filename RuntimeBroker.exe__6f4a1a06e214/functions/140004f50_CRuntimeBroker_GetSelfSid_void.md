# CRuntimeBroker::GetSelfSid(void)

- ea: `0x140004f50`
- end: `0x140004f85`
- name: `?GetSelfSid@CRuntimeBroker@@SAPEAXXZ`
- size: `53`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000bb9c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140004f68`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140004f68`

## pseudocode

```c
unsigned __int8 near **CRuntimeBroker::GetSelfSid(void)
{
  BOOL inited; // eax
  __int64 v1; // rcx

  inited = InitOnceExecuteOnce(
             &`CRuntimeBroker::GetSelfSid'::`2'::rtbSelfSidInitOnce,
             (PINIT_ONCE_FN)CRuntimeBroker::QueryProcessTokenSid,
             0,
             0);
  v1 = 0;
  if ( inited )
    return &CRuntimeBroker::s_rtbSelfSid;
  return (unsigned __int8 near **)v1;
}

```

## disassembly

```asm
0x140004f50  sub     rsp, 28h
0x140004f54  xor     r9d, r9d; Context
0x140004f57  lea     rdx, ?QueryProcessTokenSid@CRuntimeBroker@@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x140004f5e  xor     r8d, r8d; Parameter
0x140004f61  lea     rcx, ?rtbSelfSidInitOnce@?1??GetSelfSid@CRuntimeBroker@@SAPEAXXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x140004f68  call    cs:__imp_InitOnceExecuteOnce
0x140004f6e  xor     ecx, ecx
0x140004f70  lea     rdx, ?s_rtbSelfSid@CRuntimeBroker@@2PAEA; uchar near * CRuntimeBroker::s_rtbSelfSid
0x140004f77  test    eax, eax
0x140004f79  cmovnz  rcx, rdx
0x140004f7d  mov     rax, rcx
0x140004f80  add     rsp, 28h
0x140004f84  retn
```
