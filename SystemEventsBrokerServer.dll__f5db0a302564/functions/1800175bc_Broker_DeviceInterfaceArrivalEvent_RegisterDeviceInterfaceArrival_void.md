# Broker::DeviceInterfaceArrivalEvent::RegisterDeviceInterfaceArrival(void)

- ea: `0x1800175bc`
- end: `0x18001766f`
- name: `?RegisterDeviceInterfaceArrival@DeviceInterfaceArrivalEvent@Broker@@AEAAXXZ`
- size: `179`
- prototype: `void __fastcall(Broker::DeviceInterfaceArrivalEvent *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021af0`

## callees

- `0x1800175bc`
- `0x18001cf50`
- `0x18001d9a0`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18001761a`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18001761a`

## pseudocode

```c
void __fastcall Broker::DeviceInterfaceArrivalEvent::RegisterDeviceInterfaceArrival(
        Broker::DeviceInterfaceArrivalEvent *this)
{
  __int128 v2; // xmm0
  int v3; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-1E8h] BYREF
  __int128 v5; // [rsp+28h] [rbp-1E0h]
  int v6; // [rsp+38h] [rbp-1D0h]
  int v7; // [rsp+40h] [rbp-1C8h]
  __int64 v8; // [rsp+50h] [rbp-1B8h] BYREF
  int v9; // [rsp+58h] [rbp-1B0h]
  _BYTE v10[4]; // [rsp+5Ch] [rbp-1ACh] BYREF
  __int128 v11; // [rsp+60h] [rbp-1A8h]

  memset_0(v10, 0, 0x194u);
  v2 = *(_OWORD *)((char *)this + 40);
  v8 = 416;
  v9 = 0;
  v11 = v2;
  v3 = CM_Register_Notification(
         &v8,
         this,
         Broker::DeviceInterfaceArrivalEvent::OnDeviceNotificationArrival,
         (char *)this + 32);
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
0x1800175bc  push    rbx
0x1800175be  sub     rsp, 200h
0x1800175c5  mov     rax, cs:__security_cookie
0x1800175cc  xor     rax, rsp
0x1800175cf  mov     [rsp+208h+var_18], rax
0x1800175d7  mov     rbx, rcx
0x1800175da  xor     edx, edx; Val
0x1800175dc  lea     rcx, [rsp+208h+var_1AC]; void *
0x1800175e1  mov     r8d, 194h; Size
0x1800175e7  call    memset_0
0x1800175ec  movups  xmm0, xmmword ptr [rbx+28h]
0x1800175f0  lea     r9, [rbx+20h]
0x1800175f4  mov     [rsp+208h+var_1B8], 1A0h
0x1800175fd  lea     r8, ?OnDeviceNotificationArrival@DeviceInterfaceArrivalEvent@Broker@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; Broker::DeviceInterfaceArrivalEvent::OnDeviceNotificationArrival(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180017604  mov     [rsp+208h+var_1B0], 0
0x18001760c  mov     rdx, rbx
0x18001760f  lea     rcx, [rsp+208h+var_1B8]
0x180017614  movdqu  [rsp+208h+var_1A8], xmm0
0x18001761a  call    cs:__imp_CM_Register_Notification
0x180017620  test    eax, eax
0x180017622  jz      short loc_180017656
0x180017624  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001762b  mov     [rsp+208h+var_1D0], 1
0x180017633  mov     [rsp+208h+pExceptionObject], rcx
0x180017638  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001763f  xorps   xmm0, xmm0
0x180017642  mov     [rsp+208h+var_1C8], eax
0x180017646  lea     rcx, [rsp+208h+pExceptionObject]; pExceptionObject
0x18001764b  movups  [rsp+208h+var_1E0], xmm0
0x180017650  call    _CxxThrowException_0
0x180017656  mov     rcx, [rsp+208h+var_18]
0x18001765e  xor     rcx, rsp; StackCookie
0x180017661  call    __security_check_cookie
0x180017666  add     rsp, 200h
0x18001766d  pop     rbx
0x18001766e  retn
```
