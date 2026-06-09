# EvtAdapterPreProcessOidRequest

- ea: `0x140008f40`
- end: `0x140008fdc`
- name: `EvtAdapterPreProcessOidRequest`
- size: `156`
- prototype: `void __fastcall(__int64, struct _NDIS_OID_REQUEST *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140008f40`
- `0x140011e94`
- `0x140047e90`

## import_xrefs

- `NDIS!NdisMOidRequestComplete` at `0x140008fbf`
- `NDIS!NdisMOidRequestComplete` at `0x140008fbf`

## pseudocode

```c
void __fastcall EvtAdapterPreProcessOidRequest(__int64 a1, struct _NDIS_OID_REQUEST *a2, __int64 a3)
{
  __int64 v5; // rdi
  NDIS_STATUS v6; // eax

  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14005DF38);
  v6 = MbbNdisMiniportOidRequest(*(struct NETADAPTER__ **)(v5 + 8), a2);
  if ( v6 == -1073741637 )
  {
    ((void (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD, struct _NDIS_OID_REQUEST *, __int64))qword_14005F608)(
      NetDriverGlobals,
      *(_QWORD *)(v5 + 8),
      a2,
      a3);
  }
  else if ( v6 != 259 )
  {
    NdisMOidRequestComplete(*(NDIS_HANDLE *)(v5 + 40), a2, v6);
  }
}

```

## disassembly

```asm
0x140008f40  mov     [rsp+arg_0], rbx
0x140008f45  mov     [rsp+arg_8], rsi
0x140008f4a  push    rdi
0x140008f4b  sub     rsp, 30h
0x140008f4f  mov     rax, cs:WdfFunctions_01031
0x140008f56  mov     rbx, rdx
0x140008f59  mov     rsi, r8
0x140008f5c  mov     rdx, rcx
0x140008f5f  mov     r8, cs:off_14005DF38
0x140008f66  mov     rcx, cs:WdfDriverGlobals
0x140008f6d  mov     rax, [rax+650h]
0x140008f74  call    _guard_dispatch_icall
0x140008f79  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140008f7c  mov     rdi, rax
0x140008f7f  mov     rcx, [rax+8]; struct NETADAPTER__ *
0x140008f83  call    ?MbbNdisMiniportOidRequest@@YAHPEAUNETADAPTER__@@PEAU_NDIS_OID_REQUEST@@@Z; MbbNdisMiniportOidRequest(NETADAPTER__ *,_NDIS_OID_REQUEST *)
0x140008f88  cmp     eax, 0C00000BBh
0x140008f8d  jnz     short loc_140008FAE
0x140008f8f  mov     rax, cs:qword_14005F608
0x140008f96  mov     r9, rsi
0x140008f99  mov     rdx, [rdi+8]
0x140008f9d  mov     r8, rbx
0x140008fa0  mov     rcx, cs:NetDriverGlobals
0x140008fa7  call    _guard_dispatch_icall
0x140008fac  jmp     short loc_140008FCB
0x140008fae  cmp     eax, 103h
0x140008fb3  jz      short loc_140008FCB
0x140008fb5  mov     rcx, [rdi+28h]; MiniportAdapterHandle
0x140008fb9  mov     r8d, eax; Status
0x140008fbc  mov     rdx, rbx; OidRequest
0x140008fbf  call    cs:__imp_NdisMOidRequestComplete
0x140008fc6  nop     dword ptr [rax+rax+00h]
0x140008fcb  mov     rbx, [rsp+38h+arg_0]
0x140008fd0  mov     rsi, [rsp+38h+arg_8]
0x140008fd5  add     rsp, 30h
0x140008fd9  pop     rdi
0x140008fda  retn
```
