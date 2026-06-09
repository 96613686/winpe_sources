# HCI_DibRefDestroy(_REF_OBJ *)

- ea: `0x14005aa60`
- end: `0x14005ad21`
- name: `?HCI_DibRefDestroy@@YAXPEAU_REF_OBJ@@@Z`
- size: `705`
- prototype: `void __fastcall(struct _REF_OBJ *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005b4c`
- `0x14001be50`
- `0x140055a50`
- `0x14005aa60`
- `0x14005ad28`
- `0x140161a44`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14005ac9a`
- `ntoskrnl!IoQueueWorkItem` at `0x14005ac9a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14005ac6f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14005ac6f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005ab86`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005ab86`

## pseudocode

```c
void __fastcall HCI_DibRefDestroy(struct DEVICE_INFO_BLOCK *a1)
{
  char v2; // di
  char v3; // dl
  __int16 DeviceType; // ax
  char v5; // dl
  __int16 v6; // ax
  __int64 v7; // r9
  Microsoft::Bluetooth::Foundation::intrusive_list_hook **v8; // rdx
  __int64 v9; // rcx
  __int16 v10; // ax
  _BYTE v11[56]; // [rsp+60h] [rbp-38h] BYREF

  if ( a1->ListEntry.Flink != &a1->ListEntry )
    NT_ASSERT("DIB still in device list at the time of destruction.");
  if ( a1->WhiteListEntry.Flink != &a1->WhiteListEntry )
    NT_ASSERT("DIB still in filter list at the time of destruction.");
  v2 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v3 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v3 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_qiq(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      DeviceType != 0,
      a1->Hci->IfrLog,
      5,
      2,
      11,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
      (char)a1,
      (char)a1,
      a1->DeviceInfo.address);
  if ( _InterlockedExchange(&a1->DeviceChangeStatus, 0) == 2 )
    HCI_DibReportDeviceChange(a1, 0, 0, 0);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v5 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v5 = 0;
  v6 = WPP_GLOBAL_Control->DeviceType;
  if ( v5 || v6 )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      v6 != 0,
      a1->Hci->IfrLog,
      5,
      2,
      12,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
      a1);
  if ( KeGetCurrentIrql() > 1u || a1->DeferredPairing._MyDat._MyRealVal )
  {
    wil::acquire_kspin_lock(v11, &a1->Hci->HciLock);
    v7 = (__int64)&a1->Hci->DibDestructionList & -(__int64)(a1->Hci != (HCI_INTERFACE *)-2264LL);
    v8 = *(Microsoft::Bluetooth::Foundation::intrusive_list_hook ***)(v7 + 8);
    if ( *v8 != (Microsoft::Bluetooth::Foundation::intrusive_list_hook *)v7 )
      __fastfail(3u);
    v9 = *(_QWORD *)v7;
    a1->DestructionWorkerEntry.Flink = (_LIST_ENTRY *)v7;
    a1->DestructionWorkerEntry.Blink = (_LIST_ENTRY *)v8;
    *v8 = &a1->DestructionWorkerEntry;
    *(_QWORD *)(v7 + 8) = &a1->DestructionWorkerEntry;
    if ( v9 == v7 )
    {
      RefObj_AddRefEx(
        &a1->Hci->RefObj,
        HCI_DibRefDestroy,
        223,
        "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcidib.cpp");
      if ( IoAcquireRemoveLockEx(
             &a1->Hci->DevExt->RemoveLock,
             HCI_DibRefDestroy,
             "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcidib.cpp",
             0xE1u,
             0x20u) < 0 )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          v2 = 0;
        v10 = WPP_GLOBAL_Control->DeviceType;
        if ( v2 || v10 )
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            v2,
            v10 != 0,
            a1->Hci->IfrLog,
            5,
            2,
            13,
            (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
            a1);
      }
      else
      {
        IoQueueWorkItem(
          a1->Hci->DibDestructionWorkItem.m_ptr,
          HCI_DibDestructionWorkerCallback,
          DelayedWorkQueue,
          a1->Hci);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v11);
  }
  else
  {
    HCI_DibFinalDestroy(a1);
  }
}

```

## disassembly

```asm
0x14005aa60  push    rbx
0x14005aa62  push    rsi
0x14005aa63  push    rdi
0x14005aa64  push    r15
0x14005aa66  sub     rsp, 78h
0x14005aa6a  lea     rax, [rcx+340h]
0x14005aa71  mov     rbx, rcx
0x14005aa74  cmp     [rax], rax
0x14005aa77  jz      short loc_14005AA7B
0x14005aa79  int     2Ch; NT_ASSERT("DIB still in device list at the time of destruction.")
0x14005aa7b  lea     rax, [rcx+7E0h]
0x14005aa82  cmp     [rax], rax
0x14005aa85  jz      short loc_14005AA89
0x14005aa87  int     2Ch; NT_ASSERT("DIB still in filter list at the time of destruction.")
0x14005aa89  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005aa90  xor     esi, esi
0x14005aa92  mov     eax, [rcx+2Ch]
0x14005aa95  lea     edi, [rsi+1]
0x14005aa98  test    al, 2
0x14005aa9a  jz      short loc_14005AAA5
0x14005aa9c  cmp     byte ptr [rcx+29h], 5
0x14005aaa0  mov     dl, dil
0x14005aaa3  jnb     short loc_14005AAA8
0x14005aaa5  mov     dl, sil
0x14005aaa8  movzx   eax, word ptr [rcx+48h]
0x14005aaac  lea     r15, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x14005aab3  test    ax, ax
0x14005aab6  setnz   r8b
0x14005aaba  test    dl, dl
0x14005aabc  jnz     short loc_14005AAC3
0x14005aabe  test    ax, ax
0x14005aac1  jz      short loc_14005AB06
0x14005aac3  mov     rax, [rbx+20h]
0x14005aac7  mov     r9, [rbx+378h]
0x14005aace  mov     rcx, [rcx+18h]
0x14005aad2  mov     [rsp+98h+var_48], rax
0x14005aad7  mov     [rsp+98h+var_50], rbx
0x14005aadc  mov     r9, [r9+10B0h]
0x14005aae3  mov     [rsp+98h+var_58], rbx
0x14005aae8  mov     [rsp+98h+var_60], r15
0x14005aaed  mov     [rsp+98h+var_68], 0Bh
0x14005aaf4  mov     [rsp+98h+var_70], 2
0x14005aafc  mov     byte ptr [rsp+98h+RemlockSize], 5
0x14005ab01  call    WPP_RECORDER_AND_TRACE_SF_qiq
0x14005ab06  mov     eax, esi
0x14005ab08  xchg    eax, [rbx+370h]
0x14005ab0e  cmp     eax, 2
0x14005ab11  jnz     short loc_14005AB23
0x14005ab13  xor     r9d, r9d; bool
0x14005ab16  xor     r8d, r8d; bool
0x14005ab19  xor     edx, edx; unsigned int
0x14005ab1b  mov     rcx, rbx; struct DEVICE_INFO_BLOCK *
0x14005ab1e  call    ?HCI_DibReportDeviceChange@@YAXPEAUDEVICE_INFO_BLOCK@@K_N1@Z; HCI_DibReportDeviceChange(DEVICE_INFO_BLOCK *,ulong,bool,bool)
0x14005ab23  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005ab2a  mov     eax, [rcx+2Ch]
0x14005ab2d  test    al, 2
0x14005ab2f  jz      short loc_14005AB3A
0x14005ab31  cmp     byte ptr [rcx+29h], 5
0x14005ab35  mov     dl, dil
0x14005ab38  jnb     short loc_14005AB3D
0x14005ab3a  mov     dl, sil
0x14005ab3d  movzx   eax, word ptr [rcx+48h]
0x14005ab41  test    ax, ax
0x14005ab44  setnz   r8b
0x14005ab48  test    dl, dl
0x14005ab4a  jnz     short loc_14005AB51
0x14005ab4c  test    ax, ax
0x14005ab4f  jz      short loc_14005AB86
0x14005ab51  mov     r9, [rbx+378h]
0x14005ab58  mov     rcx, [rcx+18h]
0x14005ab5c  mov     [rsp+98h+var_58], rbx
0x14005ab61  mov     [rsp+98h+var_60], r15
0x14005ab66  mov     r9, [r9+10B0h]
0x14005ab6d  mov     [rsp+98h+var_68], 0Ch
0x14005ab74  mov     [rsp+98h+var_70], 2
0x14005ab7c  mov     byte ptr [rsp+98h+RemlockSize], 5
0x14005ab81  call    WPP_RECORDER_AND_TRACE_SF_q
0x14005ab86  call    cs:__imp_KeGetCurrentIrql
0x14005ab8d  nop     dword ptr [rax+rax+00h]
0x14005ab92  cmp     al, dil
0x14005ab95  ja      short loc_14005ABAD
0x14005ab97  cmp     [rbx+918h], rsi
0x14005ab9e  jnz     short loc_14005ABAD
0x14005aba0  mov     rcx, rbx; struct DEVICE_INFO_BLOCK *
0x14005aba3  call    ?HCI_DibFinalDestroy@@YAXPEAUDEVICE_INFO_BLOCK@@@Z; HCI_DibFinalDestroy(DEVICE_INFO_BLOCK *)
0x14005aba8  jmp     loc_14005AD16
0x14005abad  mov     rdx, [rbx+378h]
0x14005abb4  lea     rcx, [rsp+98h+var_38]
0x14005abb9  add     rdx, 7B0h
0x14005abc0  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005abc5  mov     rdx, [rbx+378h]
0x14005abcc  add     rdx, 8C8h
0x14005abd3  lea     rcx, [rdx+10h]
0x14005abd7  mov     rax, rcx
0x14005abda  neg     rax
0x14005abdd  sbb     r9, r9
0x14005abe0  and     r9, rdx
0x14005abe3  neg     rcx
0x14005abe6  sbb     r8, r8
0x14005abe9  and     r8, rdx
0x14005abec  mov     rdx, [r8+8]
0x14005abf0  cmp     [rdx], r8
0x14005abf3  jz      short loc_14005ABFC
0x14005abf5  mov     ecx, 3
0x14005abfa  int     29h; Win8: RtlFailFast(ecx)
0x14005abfc  mov     rcx, [r9]
0x14005abff  lea     rax, [rbx+820h]
0x14005ac06  mov     [rax], r8
0x14005ac09  mov     [rax+8], rdx
0x14005ac0d  mov     [rdx], rax
0x14005ac10  mov     [r8+8], rax
0x14005ac14  cmp     rcx, r9
0x14005ac17  jnz     loc_14005AD0C
0x14005ac1d  mov     rcx, [rbx+378h]
0x14005ac24  lea     r9, aOnecoreDrivers_11; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14005ac2b  add     rcx, 8
0x14005ac2f  lea     rdx, ?HCI_DibRefDestroy@@YAXPEAU_REF_OBJ@@@Z; HCI_DibRefDestroy(_REF_OBJ *)
0x14005ac36  mov     r8d, 0DFh
0x14005ac3c  call    RefObj_AddRefEx
0x14005ac41  mov     rax, [rbx+378h]
0x14005ac48  lea     r8, aOnecoreDrivers_11; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14005ac4f  mov     r9d, 0E1h; Line
0x14005ac55  mov     [rsp+98h+RemlockSize], 20h ; ' '; RemlockSize
0x14005ac5d  lea     rdx, ?HCI_DibRefDestroy@@YAXPEAU_REF_OBJ@@@Z; Tag
0x14005ac64  mov     rcx, [rax+4A8h]
0x14005ac6b  add     rcx, 38h ; '8'; RemoveLock
0x14005ac6f  call    cs:__imp_IoAcquireRemoveLockEx
0x14005ac76  nop     dword ptr [rax+rax+00h]
0x14005ac7b  test    eax, eax
0x14005ac7d  js      short loc_14005ACA8
0x14005ac7f  mov     rcx, [rbx+378h]
0x14005ac86  lea     rdx, ?HCI_DibDestructionWorkerCallback@@YAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x14005ac8d  mov     r9, rcx; Context
0x14005ac90  mov     r8d, edi; QueueType
0x14005ac93  mov     rcx, [rcx+8D8h]; IoWorkItem
0x14005ac9a  call    cs:__imp_IoQueueWorkItem
0x14005aca1  nop     dword ptr [rax+rax+00h]
0x14005aca6  jmp     short loc_14005AD0C
0x14005aca8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005acaf  mov     eax, [rcx+2Ch]
0x14005acb2  test    al, 2
0x14005acb4  jz      short loc_14005ACBC
0x14005acb6  cmp     byte ptr [rcx+29h], 5
0x14005acba  jnb     short loc_14005ACBF
0x14005acbc  mov     dil, sil
0x14005acbf  movzx   eax, word ptr [rcx+48h]
0x14005acc3  test    ax, ax
0x14005acc6  setnz   r8b
0x14005acca  test    dil, dil
0x14005accd  jnz     short loc_14005ACD4
0x14005accf  test    ax, ax
0x14005acd2  jz      short loc_14005AD0C
0x14005acd4  mov     r9, [rbx+378h]
0x14005acdb  mov     dl, dil
0x14005acde  mov     rcx, [rcx+18h]
0x14005ace2  mov     [rsp+98h+var_58], rbx
0x14005ace7  mov     [rsp+98h+var_60], r15
0x14005acec  mov     r9, [r9+10B0h]
0x14005acf3  mov     [rsp+98h+var_68], 0Dh
0x14005acfa  mov     [rsp+98h+var_70], 2
0x14005ad02  mov     byte ptr [rsp+98h+RemlockSize], 5
0x14005ad07  call    WPP_RECORDER_AND_TRACE_SF_q
0x14005ad0c  lea     rcx, [rsp+98h+var_38]
0x14005ad11  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005ad16  add     rsp, 78h
0x14005ad1a  pop     r15
0x14005ad1c  pop     rdi
0x14005ad1d  pop     rsi
0x14005ad1e  pop     rbx
0x14005ad1f  retn
```
