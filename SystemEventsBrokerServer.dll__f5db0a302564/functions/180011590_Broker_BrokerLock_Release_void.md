# Broker::BrokerLock::Release(void)

- ea: `0x180011590`
- end: `0x1800115f0`
- name: `?Release@BrokerLock@Broker@@QEAAXXZ`
- size: `96`
- prototype: `void __fastcall(Broker::BrokerLock *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800026d0`
- `0x18000dc40`
- `0x18000e4f0`
- `0x18000e880`
- `0x18000f440`
- `0x180011574`

## callees

- `0x180011590`
- `0x18001d9ac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800115ab`
- `ntdll!RtlNtStatusToDosError` at `0x1800115ab`
- `BrokerLib!BrUnlockBroker` at `0x18001159f`
- `BrokerLib!BrUnlockBroker` at `0x18001159f`

## pseudocode

```c
void __fastcall Broker::BrokerLock::Release(Broker::BrokerLock *this)
{
  NTSTATUS v2; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int128 v4; // [rsp+28h] [rbp-30h]
  int v5; // [rsp+38h] [rbp-20h]
  ULONG v6; // [rsp+40h] [rbp-18h]

  v2 = BrUnlockBroker(*(_QWORD *)this, *((unsigned int *)this + 2));
  if ( v2 < 0 )
  {
    v5 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v6 = RtlNtStatusToDosError(v2);
    v4 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  *((_DWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180011590  push    rbx
0x180011592  sub     rsp, 50h
0x180011596  mov     edx, [rcx+8]
0x180011599  mov     rbx, rcx
0x18001159c  mov     rcx, [rcx]
0x18001159f  call    cs:__imp_BrUnlockBroker
0x1800115a5  test    eax, eax
0x1800115a7  jns     short loc_1800115E3
0x1800115a9  mov     ecx, eax; Status
0x1800115ab  call    cs:__imp_RtlNtStatusToDosError
0x1800115b1  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800115b8  mov     [rsp+58h+var_20], 1
0x1800115c0  mov     [rsp+58h+pExceptionObject], rcx
0x1800115c5  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800115cc  xorps   xmm0, xmm0
0x1800115cf  mov     [rsp+58h+var_18], eax
0x1800115d3  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800115d8  movups  [rsp+58h+var_30], xmm0
0x1800115dd  call    _CxxThrowException_0
0x1800115e3  mov     dword ptr [rbx+0Ch], 0
0x1800115ea  add     rsp, 50h
0x1800115ee  pop     rbx
0x1800115ef  retn
```
