# DisconnectCallback

- ea: `0x1400067a0`
- end: `0x140006805`
- name: `DisconnectCallback`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400067a0`
- `0x14000e328`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400067ac`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400067ac`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x1400067d8`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x1400067d8`

## string_xrefs

- `0x1400067e4`: `Unable to disconnect context from COM.`

## pseudocode

```c
__int64 DisconnectCallback()
{
  HRESULT v0; // eax
  unsigned int v1; // ebx

  CoRevokeClassObject(dwRegisteredWorkerFactoryID);
  if ( vpWorkerFactory )
  {
    ((void (__fastcall *)(LPUNKNOWN))vpWorkerFactory->lpVtbl->Release)(vpWorkerFactory);
    vpWorkerFactory = 0;
  }
  v0 = CoDisconnectContext(0xFFFFFFFF);
  v1 = v0;
  if ( v0 < 0 )
    CBSWdsLog(0x4000000u, v0, (size_t *)1, "Unable to disconnect context from COM.");
  return v1;
}

```

## disassembly

```asm
0x1400067a0  push    rbx
0x1400067a2  sub     rsp, 20h
0x1400067a6  mov     ecx, cs:?dwRegisteredWorkerFactoryID@@3KA; dwRegister
0x1400067ac  call    cs:__imp_CoRevokeClassObject
0x1400067b2  mov     rcx, cs:?vpWorkerFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpWorkerFactory
0x1400067b9  test    rcx, rcx
0x1400067bc  jz      short loc_1400067D5
0x1400067be  mov     rax, [rcx]
0x1400067c1  mov     rax, [rax+10h]
0x1400067c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067ca  mov     cs:?vpWorkerFactory@@3PEAUIClassFactory@@EA, 0; IClassFactory * vpWorkerFactory
0x1400067d5  or      ecx, 0FFFFFFFFh; dwTimeout
0x1400067d8  call    cs:__imp_CoDisconnectContext
0x1400067de  mov     ebx, eax
0x1400067e0  test    eax, eax
0x1400067e2  jns     short loc_1400067FD
0x1400067e4  lea     r9, aUnableToDiscon_0; "Unable to disconnect context from COM."
0x1400067eb  mov     r8d, 1
0x1400067f1  mov     edx, eax
0x1400067f3  mov     ecx, 4000000h
0x1400067f8  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400067fd  mov     eax, ebx
0x1400067ff  add     rsp, 20h
0x140006803  pop     rbx
0x140006804  retn
```
