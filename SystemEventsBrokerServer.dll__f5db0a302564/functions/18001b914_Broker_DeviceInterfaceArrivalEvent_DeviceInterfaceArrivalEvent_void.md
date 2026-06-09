# Broker::DeviceInterfaceArrivalEvent::~DeviceInterfaceArrivalEvent(void)

- ea: `0x18001b914`
- end: `0x18001b9c2`
- name: `??1DeviceInterfaceArrivalEvent@Broker@@UEAA@XZ`
- size: `174`
- prototype: `void __fastcall(Broker::DeviceInterfaceArrivalEvent *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021a70`

## callees

- `0x180016d74`
- `0x180019130`
- `0x18001b914`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001b930`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001b930`

## pseudocode

```c
void __fastcall Broker::DeviceInterfaceArrivalEvent::~DeviceInterfaceArrivalEvent(
        Broker::DeviceInterfaceArrivalEvent *this)
{
  int v2; // eax
  __int64 v3; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int128 v5; // [rsp+28h] [rbp-30h]
  int v6; // [rsp+38h] [rbp-20h]
  int v7; // [rsp+40h] [rbp-18h]

  *(_QWORD *)this = &Broker::DeviceInterfaceArrivalEvent::`vftable';
  if ( *((_QWORD *)this + 4) )
  {
    v2 = CM_Unregister_Notification();
    if ( v2 )
    {
      v5 = 0;
      v6 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v7 = v2;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    *((_QWORD *)this + 4) = 0;
  }
  v3 = *((_QWORD *)this + 7);
  if ( v3 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v3, *((_QWORD *)this + 8));
    std::_Deallocate<16>(*((void **)this + 7), (*((_QWORD *)this + 9) - *((_QWORD *)this + 7)) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
  }
  *(_QWORD *)this = &Broker::DeviceServicesEvent::`vftable';
}

```

## disassembly

```asm
0x18001b914  push    rbx
0x18001b916  sub     rsp, 50h
0x18001b91a  mov     rbx, rcx
0x18001b91d  lea     rax, ??_7DeviceInterfaceArrivalEvent@Broker@@6B@; const Broker::DeviceInterfaceArrivalEvent::`vftable'
0x18001b924  mov     [rcx], rax
0x18001b927  mov     rcx, [rcx+20h]
0x18001b92b  test    rcx, rcx
0x18001b92e  jz      short loc_18001B974
0x18001b930  call    cs:__imp_CM_Unregister_Notification
0x18001b936  test    eax, eax
0x18001b938  jz      short loc_18001B96C
0x18001b93a  xorps   xmm0, xmm0
0x18001b93d  movups  [rsp+58h+var_30], xmm0
0x18001b942  mov     [rsp+58h+var_20], 1
0x18001b94a  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001b951  mov     [rsp+58h+pExceptionObject], rcx
0x18001b956  mov     [rsp+58h+var_18], eax
0x18001b95a  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001b961  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001b966  call    _CxxThrowException_0
0x18001b96c  mov     qword ptr [rbx+20h], 0
0x18001b974  mov     rcx, [rbx+38h]
0x18001b978  test    rcx, rcx
0x18001b97b  jz      short loc_18001B9B2
0x18001b97d  mov     rdx, [rbx+40h]
0x18001b981  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18001b986  mov     rcx, [rbx+38h]
0x18001b98a  mov     rdx, [rbx+48h]
0x18001b98e  sub     rdx, rcx
0x18001b991  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001b995  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b99a  mov     qword ptr [rbx+38h], 0
0x18001b9a2  mov     qword ptr [rbx+40h], 0
0x18001b9aa  mov     qword ptr [rbx+48h], 0
0x18001b9b2  lea     rax, ??_7DeviceServicesEvent@Broker@@6B@; const Broker::DeviceServicesEvent::`vftable'
0x18001b9b9  mov     [rbx], rax
0x18001b9bc  add     rsp, 50h
0x18001b9c0  pop     rbx
0x18001b9c1  retn
```
