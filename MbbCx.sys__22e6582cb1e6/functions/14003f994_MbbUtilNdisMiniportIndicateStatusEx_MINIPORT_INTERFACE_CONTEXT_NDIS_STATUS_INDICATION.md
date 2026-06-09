# MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)

- ea: `0x14003f994`
- end: `0x14003fa2e`
- name: `?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z`
- size: `154`
- prototype: `void __fastcall(NDIS_HANDLE *, struct _NDIS_STATUS_INDICATION *)`
- caller_count: `80`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031d8`
- `0x140004af0`
- `0x14000c37c`
- `0x14000d49c`
- `0x14000fca8`
- `0x14000ff80`
- `0x1400101d0`
- `0x140013590`
- `0x14001f25c`
- `0x140026698`
- `0x140026e44`
- `0x1400275f0`
- `0x140027a54`
- `0x1400298a0`
- `0x140029b20`
- `0x140029d80`
- `0x140029fe0`
- `0x14002a240`
- `0x14002ae5c`
- `0x14002b930`
- `0x14002be90`
- `0x14002c394`
- `0x14002cfa0`
- `0x14002d18c`
- `0x14002daa0`
- `0x14002deb8`
- `0x14002e100`
- `0x14002e470`
- `0x14002e780`
- `0x14002e9c4`
- `0x14002ec90`
- `0x14002f0c8`
- `0x14002f228`
- `0x14002f75c`
- `0x14002f8e0`
- `0x14002fb40`
- `0x140030100`
- `0x140030590`
- `0x140030bc0`
- `0x140030f80`
- `0x140031550`
- `0x140031a40`
- `0x140031e20`
- `0x140032280`
- `0x1400324f0`
- `0x1400327d0`
- `0x140032c30`
- `0x140032ee0`
- `0x140033580`
- `0x140033970`

## callees

- `0x140041664`

## import_xrefs

- `NDIS!NdisMIndicateStatusEx` at `0x14003fa13`
- `NDIS!NdisMIndicateStatusEx` at `0x14003fa13`

## pseudocode

```c
void __fastcall MbbUtilNdisMiniportIndicateStatusEx(NDIS_HANDLE *a1, struct _NDIS_STATUS_INDICATION *a2)
{
  MbbWriteEvent(
    &NDIS_STATUS_INDICATION_EVENT,
    0,
    0,
    5u,
    (char *)*a1 + 32,
    4,
    &a2->StatusCode,
    4,
    &a2->RequestId,
    8,
    &a2->DestinationHandle,
    8,
    &a2->StatusBufferSize,
    4);
  NdisMIndicateStatusEx(a1[2], a2);
}

```

## disassembly

```asm
0x14003f994  mov     [rsp+arg_0], rbx
0x14003f999  push    rdi
0x14003f99a  sub     rsp, 70h
0x14003f99e  mov     r11, [rcx]
0x14003f9a1  lea     rax, [rdx+38h]
0x14003f9a5  lea     r8, [rdx+20h]
0x14003f9a9  mov     rbx, rdx
0x14003f9ac  lea     r9, [rdx+28h]
0x14003f9b0  mov     rdi, rcx
0x14003f9b3  lea     r10, [rdx+14h]
0x14003f9b7  add     r11, 20h ; ' '
0x14003f9bb  mov     edx, 5
0x14003f9c0  lea     ecx, [rdx-1]
0x14003f9c3  mov     [rsp+78h+var_10], rcx
0x14003f9c8  mov     [rsp+78h+var_18], rax
0x14003f9cd  lea     eax, [rdx+3]
0x14003f9d0  mov     [rsp+78h+var_20], rax
0x14003f9d5  mov     [rsp+78h+var_28], r8
0x14003f9da  xor     r8d, r8d; RelatedActivityId
0x14003f9dd  mov     [rsp+78h+var_30], rax
0x14003f9e2  mov     [rsp+78h+var_38], r9
0x14003f9e7  mov     r9d, edx; unsigned __int16
0x14003f9ea  mov     [rsp+78h+var_40], rcx
0x14003f9ef  xor     edx, edx; ActivityId
0x14003f9f1  mov     [rsp+78h+var_48], r10
0x14003f9f6  mov     [rsp+78h+var_50], rcx
0x14003f9fb  lea     rcx, NDIS_STATUS_INDICATION_EVENT; EventDescriptor
0x14003fa02  mov     [rsp+78h+var_58], r11
0x14003fa07  call    ?MbbWriteEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x14003fa0c  mov     rcx, [rdi+10h]; MiniportAdapterHandle
0x14003fa10  mov     rdx, rbx; StatusIndication
0x14003fa13  call    cs:__imp_NdisMIndicateStatusEx
0x14003fa1a  nop     dword ptr [rax+rax+00h]
0x14003fa1f  mov     rbx, [rsp+78h+arg_0]
0x14003fa27  add     rsp, 70h
0x14003fa2b  pop     rdi
0x14003fa2c  retn
```
