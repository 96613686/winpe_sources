# Broker::DeviceInterfaceArrivalEvent::OnDeviceNotificationArrival(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x180011d60`
- end: `0x180011e06`
- name: `?OnDeviceNotificationArrival@DeviceInterfaceArrivalEvent@Broker@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `166`
- prototype: `static unsigned int __high(struct HCMNOTIFICATION__ *, void *, enum _CM_NOTIFY_ACTION, struct _CM_NOTIFY_EVENT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180011d60`
- `0x180011e10`
- `0x18001d9ac`

## import_xrefs

- `BrokerLib!BrSignalBrokerEvent2` at `0x180011db8`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180011db8`

## pseudocode

```c
__int64 __fastcall Broker::DeviceInterfaceArrivalEvent::OnDeviceNotificationArrival(
        __int64 a1,
        Broker::DeviceInterfaceArrivalEvent *a2,
        int a3,
        __int64 a4)
{
  __int64 v5; // rax
  int v6; // eax
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v9; // [rsp+38h] [rbp-30h]
  int v10; // [rsp+48h] [rbp-20h]
  int v11; // [rsp+50h] [rbp-18h]

  if ( !a3 && !*(_DWORD *)a4 )
  {
    try
    {
      if ( a2 )
      {
        v5 = *(_QWORD *)(a4 + 8) - *((_QWORD *)a2 + 5);
        if ( !v5 )
          v5 = *(_QWORD *)(a4 + 16) - *((_QWORD *)a2 + 6);
        if ( !v5 )
        {
          if ( Broker::DeviceInterfaceArrivalEvent::IsDeviceHwidPresentOnPath(a2, (const unsigned __int16 *)(a4 + 24)) )
          {
            v6 = BrSignalBrokerEvent2(*((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 0, 0, 0, 0);
            if ( v6 )
            {
              v9 = 0;
              v10 = 1;
              pExceptionObject = &Broker::Win32Error::`vftable';
              v11 = v6;
              throw (Broker::Win32Error *)&pExceptionObject;
            }
          }
        }
      }
    }
    catch ( std::bad_alloc )
    {
      return 0;
    }
    catch ( Broker::Win32Error )
    {
      return 0;
    }
    catch ( ... )
    {
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011d60  push    rbx
0x180011d62  sub     rsp, 60h
0x180011d66  mov     rbx, rdx
0x180011d69  test    r8d, r8d
0x180011d6c  jnz     short loc_180011DC2
0x180011d6e  cmp     [r9], r8d
0x180011d71  jnz     short loc_180011DC2
0x180011d73  test    rdx, rdx
0x180011d76  jz      short loc_180011DCC
0x180011d78  mov     rax, [r9+8]
0x180011d7c  sub     rax, [rdx+28h]
0x180011d80  jnz     short loc_180011D8A
0x180011d82  mov     rax, [r9+10h]
0x180011d86  sub     rax, [rdx+30h]
0x180011d8a  test    rax, rax
0x180011d8d  jnz     short loc_180011DCA
0x180011d8f  lea     rdx, [r9+18h]; unsigned __int16 *
0x180011d93  mov     rcx, rbx; this
0x180011d96  call    ?IsDeviceHwidPresentOnPath@DeviceInterfaceArrivalEvent@Broker@@AEAA_NPEBG@Z; Broker::DeviceInterfaceArrivalEvent::IsDeviceHwidPresentOnPath(ushort const *)
0x180011d9b  test    al, al
0x180011d9d  jz      short loc_180011DC2
0x180011d9f  xor     eax, eax
0x180011da1  mov     [rsp+68h+var_40], rax
0x180011da6  mov     [rsp+68h+var_48], eax
0x180011daa  xor     r9d, r9d
0x180011dad  xor     r8d, r8d
0x180011db0  mov     rdx, [rbx+18h]
0x180011db4  mov     rcx, [rbx+10h]
0x180011db8  call    cs:__imp_BrSignalBrokerEvent2
0x180011dbe  test    eax, eax
0x180011dc0  jnz     short loc_180011DCE
0x180011dc2  xor     eax, eax
0x180011dc4  add     rsp, 60h
0x180011dc8  pop     rbx
0x180011dc9  retn
0x180011dca  jmp     short loc_180011DC2
0x180011dcc  jmp     short loc_180011DC2
0x180011dce  xorps   xmm0, xmm0
0x180011dd1  movups  [rsp+68h+var_30], xmm0
0x180011dd6  mov     [rsp+68h+var_20], 1
0x180011dde  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180011de5  mov     [rsp+68h+pExceptionObject], rcx
0x180011dea  mov     [rsp+68h+var_18], eax
0x180011dee  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180011df5  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180011dfa  call    _CxxThrowException_0
0x180011e00  jmp     short loc_180011DC2
0x180011e02  jmp     short loc_180011DC2
0x180011e04  jmp     short loc_180011DC2
```
