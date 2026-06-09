# CRdpSessionAgentProxy::NotifyInitializationComplete(void)

- ea: `0x1400041b0`
- end: `0x1400041d3`
- name: `?NotifyInitializationComplete@CRdpSessionAgentProxy@@UEAAJXZ`
- size: `35`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400041b0`
- `0x140004240`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::NotifyInitializationComplete(CRdpSessionAgentProxy *this)
{
  if ( g_originalProcessAccessMaskForSystem != -1 )
  {
    RevertToOriginalSystemAccess((unsigned int)this);
    g_originalProcessAccessMaskForSystem = -1;
  }
  return 0;
}

```

## disassembly

```asm
0x1400041b0  sub     rsp, 28h
0x1400041b4  cmp     cs:?g_originalProcessAccessMaskForSystem@@3KA, 0FFFFFFFFh; ulong g_originalProcessAccessMaskForSystem
0x1400041bb  jz      short loc_1400041CC
0x1400041bd  call    ?RevertToOriginalSystemAccess@@YAXK@Z; RevertToOriginalSystemAccess(ulong)
0x1400041c2  mov     cs:?g_originalProcessAccessMaskForSystem@@3KA, 0FFFFFFFFh; ulong g_originalProcessAccessMaskForSystem
0x1400041cc  xor     eax, eax
0x1400041ce  add     rsp, 28h
0x1400041d2  retn
```
