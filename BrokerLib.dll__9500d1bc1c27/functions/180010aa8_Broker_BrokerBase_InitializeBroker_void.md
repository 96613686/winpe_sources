# Broker::BrokerBase::InitializeBroker(void)

- ea: `0x180010aa8`
- end: `0x180010b7c`
- name: `?InitializeBroker@BrokerBase@Broker@@QEAAXXZ`
- size: `212`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800109f0`
- `0x180016cf0`

## callees

- `0x180005b50`
- `0x180010aa8`
- `0x1800165da`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010b27`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010b27`

## pseudocode

```c
void __fastcall Broker::BrokerBase::InitializeBroker(Broker::BrokerBase *this)
{
  __int64 v2; // [rsp+20h] [rbp-58h]
  void **pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  __int128 v4; // [rsp+48h] [rbp-30h]
  int v5; // [rsp+58h] [rbp-20h]
  int v6; // [rsp+60h] [rbp-18h]
  __int64 v7; // [rsp+80h] [rbp+8h] BYREF

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  v2 = *((_QWORD *)this + 1);
  v7 = 0;
  if ( (int)RtlSubscribeWnfStateChangeNotification(
              &v7,
              WNF_BI_BI_READY,
              0,
              Broker::BrokerBase::BIReadyCallback,
              v2,
              0,
              0,
              0) < 0 )
  {
    v5 = 1;
    v6 = 1359;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v4 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  _InterlockedExchange64((volatile __int64 *)this + 40, v7);
}

```

## disassembly

```asm
0x180010aa8  push    rbx
0x180010aaa  sub     rsp, 70h
0x180010aae  mov     rbx, rcx
0x180010ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ab8  test    dword ptr [rcx+1Ch], 800h
0x180010abf  jz      short loc_180010AE0
0x180010ac1  cmp     byte ptr [rcx+19h], 5
0x180010ac5  jb      short loc_180010AE0
0x180010ac7  mov     r9, [rbx+8]
0x180010acb  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180010ad2  mov     rcx, [rcx+10h]
0x180010ad6  mov     edx, 13h
0x180010adb  call    WPP_SF__guid_
0x180010ae0  mov     rax, [rbx+8]
0x180010ae4  lea     r9, ?BIReadyCallback@BrokerBase@Broker@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Broker::BrokerBase::BIReadyCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180010aeb  mov     rdx, cs:WNF_BI_BI_READY
0x180010af2  lea     rcx, [rsp+78h+arg_0]
0x180010afa  mov     [rsp+78h+var_40], 0
0x180010b02  xor     r8d, r8d
0x180010b05  mov     [rsp+78h+var_48], 0
0x180010b0d  mov     [rsp+78h+var_50], 0
0x180010b16  mov     [rsp+78h+var_58], rax
0x180010b1b  mov     [rsp+78h+arg_0], 0
0x180010b27  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180010b2d  test    eax, eax
0x180010b2f  jns     short loc_180010B67
0x180010b31  xorps   xmm0, xmm0
0x180010b34  mov     [rsp+78h+var_20], 1
0x180010b3c  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180010b43  mov     [rsp+78h+var_18], 54Fh
0x180010b4b  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180010b52  mov     [rsp+78h+pExceptionObject], rax
0x180010b57  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180010b5c  movups  [rsp+78h+var_30], xmm0
0x180010b61  call    _CxxThrowException_0
0x180010b67  mov     rax, [rsp+78h+arg_0]
0x180010b6f  xchg    rax, [rbx+140h]
0x180010b76  add     rsp, 70h
0x180010b7a  pop     rbx
0x180010b7b  retn
```
