# Broker::DeviceServicesEvent::SignalEvent(uchar *,_GUID const *,ulong,uchar *)

- ea: `0x180017a68`
- end: `0x180017acc`
- name: `?SignalEvent@DeviceServicesEvent@Broker@@QEAAXPEAEPEBU_GUID@@K0@Z`
- size: `100`
- prototype: `void __fastcall(Broker::DeviceServicesEvent *__hidden this, unsigned __int8 *, const struct _GUID *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021af0`

## callees

- `0x180017a68`
- `0x18001d9ac`

## import_xrefs

- `BrokerLib!BrSignalBrokerEvent2` at `0x180017a8b`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180017a8b`

## pseudocode

```c
void __fastcall Broker::DeviceServicesEvent::SignalEvent(
        Broker::DeviceServicesEvent *this,
        unsigned __int8 *a2,
        const struct _GUID *a3)
{
  int v3; // eax
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v5; // [rsp+38h] [rbp-30h]
  int v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+50h] [rbp-18h]

  v3 = BrSignalBrokerEvent2(*((_QWORD *)this + 2), *((_QWORD *)this + 3), 0, 0, 0, 0);
  if ( v3 )
  {
    v6 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v7 = v3;
    v5 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180017a68  sub     rsp, 68h
0x180017a6c  mov     rdx, [rcx+18h]
0x180017a70  xor     r9d, r9d
0x180017a73  mov     rcx, [rcx+10h]
0x180017a77  xor     r8d, r8d
0x180017a7a  mov     [rsp+68h+var_40], 0
0x180017a83  mov     [rsp+68h+var_48], 0
0x180017a8b  call    cs:__imp_BrSignalBrokerEvent2
0x180017a91  test    eax, eax
0x180017a93  jz      short loc_180017AC7
0x180017a95  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180017a9c  mov     [rsp+68h+var_20], 1
0x180017aa4  mov     [rsp+68h+pExceptionObject], rcx
0x180017aa9  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180017ab0  xorps   xmm0, xmm0
0x180017ab3  mov     [rsp+68h+var_18], eax
0x180017ab7  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180017abc  movups  [rsp+68h+var_30], xmm0
0x180017ac1  call    _CxxThrowException_0
0x180017ac7  add     rsp, 68h
0x180017acb  retn
```
