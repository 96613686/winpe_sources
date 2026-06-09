# WxNdisMOidRequestComplete(void *,_NDIS_OID_REQUEST *,int,CPort const *)

- ea: `0x1400d02ac`
- end: `0x1400d0342`
- name: `?WxNdisMOidRequestComplete@@YAXPEAXPEAU_NDIS_OID_REQUEST@@HPEBVCPort@@@Z`
- size: `150`
- prototype: `void __fastcall(NDIS_HANDLE MiniportAdapterHandle, struct _NDIS_OID_REQUEST *, int, const struct CPort *this)`
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000440c`
- `0x140005a30`
- `0x140005bf0`
- `0x14002a1f0`
- `0x1400656f8`
- `0x140065844`
- `0x1400cfae0`
- `0x1400cfd04`

## callees

- `0x140004d48`
- `0x14001e128`
- `0x14001efb8`
- `0x1400d02ac`

## import_xrefs

- `NDIS!NdisMOidRequestComplete` at `0x1400d032c`
- `NDIS!NdisMOidRequestComplete` at `0x1400d032c`

## pseudocode

```c
void __fastcall WxNdisMOidRequestComplete(
        NDIS_HANDLE MiniportAdapterHandle,
        struct _NDIS_OID_REQUEST *a2,
        int a3,
        const struct CPort *this)
{
  int v8; // edx
  int v9; // r8d

  if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(MiniportAdapterHandle) )
  {
    CPort::CompleteOidRequest(this, a2, a3);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Dddq(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v9,
        12,
        (__int64)WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids,
        a2->DATA.QUERY_INFORMATION.Oid,
        a2->PortNumber,
        a3,
        (char)MiniportAdapterHandle);
    NdisMOidRequestComplete(MiniportAdapterHandle, a2, a3);
  }
}

```

## disassembly

```asm
0x1400d02ac  push    rbx
0x1400d02ae  push    rbp
0x1400d02af  push    rsi
0x1400d02b0  push    rdi
0x1400d02b1  sub     rsp, 58h
0x1400d02b5  mov     rbp, r9
0x1400d02b8  mov     edi, r8d
0x1400d02bb  mov     rbx, rdx
0x1400d02be  mov     rsi, rcx
0x1400d02c1  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1400d02c6  test    eax, eax
0x1400d02c8  jz      short loc_1400D02DA
0x1400d02ca  mov     r8d, edi; int
0x1400d02cd  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x1400d02d0  mov     rcx, rbp; this
0x1400d02d3  call    ?CompleteOidRequest@CPort@@QEBAXPEAU_NDIS_OID_REQUEST@@H@Z; CPort::CompleteOidRequest(_NDIS_OID_REQUEST *,int)
0x1400d02d8  jmp     short loc_1400D0338
0x1400d02da  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d02e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d02e8  jz      short loc_1400D0323
0x1400d02ea  mov     eax, [rbx+8]
0x1400d02ed  mov     r9d, 0Ch
0x1400d02f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d02fa  mov     [rsp+78h+var_38], rsi
0x1400d02ff  mov     [rsp+78h+var_40], edi
0x1400d0303  mov     [rsp+78h+var_48], eax
0x1400d0307  mov     eax, [rbx+20h]
0x1400d030a  mov     rcx, [rcx+40h]
0x1400d030e  mov     [rsp+78h+var_50], eax
0x1400d0312  lea     rax, WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids
0x1400d0319  mov     [rsp+78h+var_58], rax
0x1400d031e  call    WPP_RECORDER_SF_Dddq
0x1400d0323  mov     r8d, edi; Status
0x1400d0326  mov     rdx, rbx; OidRequest
0x1400d0329  mov     rcx, rsi; MiniportAdapterHandle
0x1400d032c  call    cs:__imp_NdisMOidRequestComplete
0x1400d0333  nop     dword ptr [rax+rax+00h]
0x1400d0338  add     rsp, 58h
0x1400d033c  pop     rdi
0x1400d033d  pop     rsi
0x1400d033e  pop     rbp
0x1400d033f  pop     rbx
0x1400d0340  retn
```
