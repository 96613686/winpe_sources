# Broker::BrokerLock::Acquire(void)

- ea: `0x18000e79c`
- end: `0x18000e7fc`
- name: `?Acquire@BrokerLock@Broker@@QEAAXXZ`
- size: `96`
- prototype: `void __fastcall(Broker::BrokerLock *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800026d0`
- `0x18000dc40`
- `0x18000e4f0`
- `0x18000e770`
- `0x18000e880`
- `0x18000f440`

## callees

- `0x18000e79c`
- `0x18001d9ac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000e7c4`
- `ntdll!RtlNtStatusToDosError` at `0x18000e7c4`
- `BrokerLib!BrLockBroker` at `0x18000e7ab`
- `BrokerLib!BrLockBroker` at `0x18000e7ab`

## pseudocode

```c
void __fastcall Broker::BrokerLock::Acquire(Broker::BrokerLock *this)
{
  NTSTATUS v2; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int128 v4; // [rsp+28h] [rbp-30h]
  int v5; // [rsp+38h] [rbp-20h]
  ULONG v6; // [rsp+40h] [rbp-18h]

  v2 = BrLockBroker(*(_QWORD *)this, *((unsigned int *)this + 2));
  if ( v2 < 0 )
  {
    v5 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v6 = RtlNtStatusToDosError(v2);
    v4 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  *((_DWORD *)this + 3) = 1;
}

```

## disassembly

```asm
0x18000e79c  push    rbx
0x18000e79e  sub     rsp, 50h
0x18000e7a2  mov     edx, [rcx+8]
0x18000e7a5  mov     rbx, rcx
0x18000e7a8  mov     rcx, [rcx]
0x18000e7ab  call    cs:__imp_BrLockBroker
0x18000e7b1  test    eax, eax
0x18000e7b3  js      short loc_18000E7C2
0x18000e7b5  mov     dword ptr [rbx+0Ch], 1
0x18000e7bc  add     rsp, 50h
0x18000e7c0  pop     rbx
0x18000e7c1  retn
0x18000e7c2  mov     ecx, eax; Status
0x18000e7c4  call    cs:__imp_RtlNtStatusToDosError
0x18000e7ca  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000e7d1  mov     [rsp+58h+var_20], 1
0x18000e7d9  mov     [rsp+58h+pExceptionObject], rcx
0x18000e7de  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000e7e5  xorps   xmm0, xmm0
0x18000e7e8  mov     [rsp+58h+var_18], eax
0x18000e7ec  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000e7f1  movups  [rsp+58h+var_30], xmm0
0x18000e7f6  call    _CxxThrowException_0
```
