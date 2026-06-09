# SMPInt_Start(DEVICE_EXTENSION *,_SMP_INTERFACE *)

- ea: `0x14014f680`
- end: `0x14014fc19`
- name: `?SMPInt_Start@@YAJPEAUDEVICE_EXTENSION@@PEAU_SMP_INTERFACE@@@Z`
- size: `1433`
- prototype: `__int64 __fastcall(struct DEVICE_EXTENSION *, struct _SMP_INTERFACE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1401bc860`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005690`
- `0x1400d912c`
- `0x14014d2ec`
- `0x14014d364`
- `0x14014f680`
- `0x14014fc80`
- `0x140165540`
- `0x140208838`
- `0x140209168`
- `0x1402095d8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14014f8cd`
- `ntoskrnl!ZwClose` at `0x14014f8cd`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14014f8fd`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14014f995`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14014f8fd`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14014f995`

## string_xrefs

- `0x14014f7d0`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters`

## pseudocode

```c
__int64 __fastcall SMPInt_Start(struct DEVICE_EXTENSION *a1, struct _SMP_INTERFACE *a2)
{
  struct _SMP_INTERFACE *v2; // rsi
  char v4; // bl
  __int16 DeviceType; // ax
  int v6; // edx
  __int16 v7; // ax
  HCI_INTERFACE *Hci; // rax
  int v9; // ecx
  int v10; // r9d
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  NTSTATUS CryptoHandle; // r14d
  int v16; // edx
  int v17; // r8d
  PDEVICE_OBJECT v18; // r10
  int v19; // eax
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // edi
  __int16 v23; // [rsp+30h] [rbp-39h]
  char v24; // [rsp+40h] [rbp-29h]
  int v25; // [rsp+50h] [rbp-19h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-11h] BYREF
  BCRYPT_ALG_HANDLE v27; // [rsp+60h] [rbp-9h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v29[2]; // [rsp+70h] [rbp+7h] BYREF
  int v30; // [rsp+80h] [rbp+17h]

  v2 = a2;
  v4 = 1;
  if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
    || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(a2) = 0;
  }
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      10,
      10,
      (__int64)WPP_d2079bad1218389e735e106ab4414c79_Traceguids);
  v2->DevExt = a1;
  v2->Fdo = a1->BtDevice.FunctionalDeviceObject;
  if ( !a1->IsSmpEnabled || !a1->Hci->LEEnabled )
  {
    if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
    {
      LOBYTE(a2) = 0;
    }
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      1,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      10,
      11,
      (__int64)WPP_d2079bad1218389e735e106ab4414c79_Traceguids);
    return 0;
  }
  wil::acquire_kspin_lock(v29, &v2->ReceivedEventQueueSpinLock);
  v2->IsReceivedEventQueueOpen = 1;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v29);
  if ( v2->BCryptResolveAddressHandle.m_ptr && v2->BCryptRandomGenHandle.m_ptr )
  {
    if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      v4 = 0;
    v7 = WPP_GLOBAL_Control->DeviceType;
    if ( v4 || v7 )
    {
      LOBYTE(v6) = v4;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7 != 0,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        10,
        12,
        (__int64)WPP_d2079bad1218389e735e106ab4414c79_Traceguids);
    }
    return 0;
  }
  Handle = 0;
  if ( (int)BthOpenKey(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BTHPORT\\Parameters", &Handle) >= 0 )
  {
    Hci = a1->Hci;
    v9 = 4;
    v29[0] = 0;
    v30 = 0;
    v29[1] = 4;
    if ( Hci->LEPeripheralRoleEnabled && (Hci->LEPrivacyMode & 4) != 0 )
      v9 = 6;
    v25 = 0;
    v10 = v9 | 8;
    if ( !a1->isSmpSecureConnectionEnabled )
      v10 = v9;
    BthQueryKeyValueUlongBounded(
      (_DWORD)Handle,
      (unsigned int)v29,
      (unsigned int)L"SMPInitiatorKeyDistOverride",
      v10,
      0,
      15,
      (__int64)&v25);
    a1->Hci->DevExt->Smp->InitiatorKeyDist = v25;
    BthQueryKeyValueUlongBounded(
      (_DWORD)Handle,
      (unsigned int)v29,
      (unsigned int)L"SMPResponderKeyDistOverride",
      a1->isSmpSecureConnectionEnabled != 0 ? 15 : 7,
      0,
      15,
      (__int64)&v25);
    a1->Hci->DevExt->Smp->ResponderKeyDist = v25;
    ZwClose(Handle);
  }
  phAlgorithm = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &phAlgorithm,
    0);
  v11 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", L"Microsoft Primitive Provider", 1u);
  CryptoHandle = v11;
  if ( v11 < 0 )
  {
    if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      || (LOBYTE(v12) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v12) = 0;
    }
    LOBYTE(v13) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      v13,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      10,
      13,
      (__int64)WPP_d2079bad1218389e735e106ab4414c79_Traceguids,
      v11);
    goto LABEL_29;
  }
  v27 = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v27,
    0);
  CryptoHandle = BCryptOpenAlgorithmProvider(&v27, L"RNG", L"Microsoft Primitive Provider", 1u);
  if ( CryptoHandle < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v16) = 0;
    }
    v24 = CryptoHandle;
    v23 = 14;
LABEL_35:
    LOBYTE(v17) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      v18->AttachedDevice,
      v16,
      v17,
      v18->DeviceExtension,
      2,
      10,
      v23,
      (__int64)WPP_d2079bad1218389e735e106ab4414c79_Traceguids,
      v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
LABEL_29:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return (unsigned int)CryptoHandle;
  }
  CryptoHandle = BthLELib_SMPUtilCreateCryptoHandleEx(&v2->SmpUtilKeyRef, 1);
  if ( CryptoHandle < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v16) = 0;
    }
    v24 = CryptoHandle;
    v23 = 15;
    goto LABEL_35;
  }
  CryptoHandle = L2CapInt_RegisterFixedChannelServer(
                   a1->L2cap,
                   6u,
                   2u,
                   (void (*)(void *, void *, unsigned int, struct _FIXED_CHANNEL_SERVER_INDICATION_PARAMETER *))SMPInt_FixedChannelCallback,
                   a1,
                   a1->BtDevice.FunctionalDeviceObject,
                   &v2->leFixedCIDServer);
  if ( CryptoHandle < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v16) = 0;
    }
    v24 = CryptoHandle;
    v23 = 16;
    goto LABEL_35;
  }
  if ( !a1->isSmpSecureConnectionEnabled
    || !a1->Hci->isBRSecureConnectionEnabled
    || (v19 = L2CapInt_RegisterFixedChannelServer(
                a1->L2cap,
                7u,
                1u,
                (void (*)(void *, void *, unsigned int, struct _FIXED_CHANNEL_SERVER_INDICATION_PARAMETER *))SMPInt_FixedChannelCallback,
                a1,
                a1->BtDevice.FunctionalDeviceObject,
                &v2->brFixedCIDServer),
        v22 = v19,
        v19 >= 0) )
  {
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v2->BCryptResolveAddressHandle,
      &phAlgorithm);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v2->BCryptRandomGenHandle,
      &v27);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return 0;
  }
  if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
    || (LOBYTE(v20) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
  {
    LOBYTE(v20) = 0;
  }
  LOBYTE(v21) = 1;
  WPP_RECORDER_AND_TRACE_SF_d(
    WPP_GLOBAL_Control->AttachedDevice,
    v20,
    v21,
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    10,
    17,
    (__int64)WPP_d2079bad1218389e735e106ab4414c79_Traceguids,
    v19);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  return v22;
}

```

## disassembly

```asm
0x14014f680  mov     [rsp-8+arg_10], rbx
0x14014f685  push    rbp
0x14014f686  push    rsi
0x14014f687  push    rdi
0x14014f688  push    r12
0x14014f68a  push    r13
0x14014f68c  push    r14
0x14014f68e  push    r15
0x14014f690  lea     rbp, [rsp-27h]
0x14014f695  sub     rsp, 90h
0x14014f69c  mov     rax, cs:__security_cookie
0x14014f6a3  xor     rax, rsp
0x14014f6a6  mov     [rbp+57h+var_38], rax
0x14014f6aa  mov     rsi, rdx
0x14014f6ad  mov     rdi, rcx
0x14014f6b0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014f6b7  xor     r12d, r12d
0x14014f6ba  bt      dword ptr [rcx+2Ch], 9
0x14014f6bf  lea     ebx, [r12+1]
0x14014f6c4  jnb     short loc_14014F6CE
0x14014f6c6  cmp     byte ptr [rcx+29h], 5
0x14014f6ca  mov     dl, bl
0x14014f6cc  jnb     short loc_14014F6D1
0x14014f6ce  mov     dl, r12b
0x14014f6d1  movzx   eax, word ptr [rcx+48h]
0x14014f6d5  lea     r9, WPP_d2079bad1218389e735e106ab4414c79_Traceguids
0x14014f6dc  test    ax, ax
0x14014f6df  mov     r14d, 0Ah
0x14014f6e5  setnz   r8b
0x14014f6e9  test    dl, dl
0x14014f6eb  jnz     short loc_14014F6F2
0x14014f6ed  test    ax, ax
0x14014f6f0  jz      short loc_14014F71B
0x14014f6f2  mov     [rsp+0C0h+var_88], r9
0x14014f6f7  mov     r9, [rcx+40h]
0x14014f6fb  mov     rcx, [rcx+18h]
0x14014f6ff  mov     word ptr [rsp+0C0h+var_90], r14w
0x14014f705  mov     dword ptr [rsp+0C0h+var_98], r14d
0x14014f70a  mov     byte ptr [rsp+0C0h+var_A0], 5
0x14014f70f  call    WPP_RECORDER_AND_TRACE_SF_
0x14014f714  lea     r9, WPP_d2079bad1218389e735e106ab4414c79_Traceguids
0x14014f71b  mov     [rsi], rdi
0x14014f71e  mov     rax, [rdi+8]
0x14014f722  mov     [rsi+8], rax
0x14014f726  cmp     [rdi+190h], r12b
0x14014f72d  jz      loc_14014FBB0
0x14014f733  mov     rax, [rdi+170h]
0x14014f73a  cmp     [rax+0D78h], r12b
0x14014f741  jz      loc_14014FBB0
0x14014f747  lea     rdx, [rsi+58h]
0x14014f74b  lea     rcx, [rbp+57h+var_50]
0x14014f74f  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14014f754  lea     rcx, [rbp+57h+var_50]
0x14014f758  mov     [rsi+70h], bl
0x14014f75b  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14014f760  lea     r15, [rsi+0C8h]
0x14014f767  cmp     [r15], r12
0x14014f76a  jz      short loc_14014F7C8
0x14014f76c  cmp     [rsi+0C0h], r12
0x14014f773  jz      short loc_14014F7C8
0x14014f775  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014f77c  bt      dword ptr [rcx+2Ch], 9
0x14014f781  jnb     short loc_14014F789
0x14014f783  cmp     byte ptr [rcx+29h], 5
0x14014f787  jnb     short loc_14014F78C
0x14014f789  mov     bl, r12b
0x14014f78c  movzx   eax, word ptr [rcx+48h]
0x14014f790  test    ax, ax
0x14014f793  setnz   r8b
0x14014f797  test    bl, bl
0x14014f799  jnz     short loc_14014F7A4
0x14014f79b  test    ax, ax
0x14014f79e  jz      loc_14014FBEF
0x14014f7a4  lea     r9, WPP_d2079bad1218389e735e106ab4414c79_Traceguids
0x14014f7ab  mov     dl, bl
0x14014f7ad  mov     [rsp+0C0h+var_88], r9
0x14014f7b2  mov     word ptr [rsp+0C0h+var_90], 0Ch
0x14014f7b9  mov     dword ptr [rsp+0C0h+var_98], r14d
0x14014f7be  mov     byte ptr [rsp+0C0h+var_A0], 5
0x14014f7c3  jmp     loc_14014FBE2
0x14014f7c8  lea     r8, [rbp+57h+Handle]
0x14014f7cc  mov     [rbp+57h+Handle], r12
0x14014f7d0  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x14014f7d7  xor     ecx, ecx
0x14014f7d9  call    BthOpenKey
0x14014f7de  mov     edx, 6
0x14014f7e3  lea     r14d, [rdx+9]
0x14014f7e7  test    eax, eax
0x14014f7e9  js      loc_14014F8D9
0x14014f7ef  mov     rax, [rdi+170h]
0x14014f7f6  lea     ecx, [rdx-2]
0x14014f7f9  mov     [rbp+57h+var_50], r12
0x14014f7fd  mov     qword ptr [rbp+57h+var_44], r12
0x14014f801  mov     [rbp+57h+var_48], ecx
0x14014f804  cmp     [rax+0D79h], r12b
0x14014f80b  jz      short loc_14014F816
0x14014f80d  test    [rax+0F0Ah], cl
0x14014f813  cmovnz  ecx, edx
0x14014f816  mov     r9d, ecx
0x14014f819  mov     [rbp+57h+var_70], r12d
0x14014f81d  or      r9d, 8
0x14014f821  lea     rax, [rbp+57h+var_70]
0x14014f825  cmp     [rdi+192h], r12b
0x14014f82c  lea     r8, aSmpinitiatorke; "SMPInitiatorKeyDistOverride"
0x14014f833  mov     [rsp+0C0h+var_90], rax
0x14014f838  lea     rdx, [rbp+57h+var_50]
0x14014f83c  cmovz   r9d, ecx
0x14014f840  mov     dword ptr [rsp+0C0h+var_98], r14d
0x14014f845  mov     rcx, [rbp+57h+Handle]
0x14014f849  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x14014f84e  call    BthQueryKeyValueUlongBounded
0x14014f853  mov     rax, [rdi+170h]
0x14014f85a  lea     r8, aSmpresponderke; "SMPResponderKeyDistOverride"
0x14014f861  mov     rcx, [rax+4A8h]
0x14014f868  mov     al, byte ptr [rbp+57h+var_70]
0x14014f86b  mov     rdx, [rcx+198h]
0x14014f872  mov     [rdx+0E8h], al
0x14014f878  lea     rdx, [rbp+57h+var_50]
0x14014f87c  mov     al, [rdi+192h]
0x14014f882  mov     rcx, [rbp+57h+Handle]
0x14014f886  neg     al
0x14014f888  lea     rax, [rbp+57h+var_70]
0x14014f88c  sbb     r9d, r9d
0x14014f88f  mov     [rsp+0C0h+var_90], rax
0x14014f894  and     r9d, 8
0x14014f898  mov     dword ptr [rsp+0C0h+var_98], r14d
0x14014f89d  add     r9d, 7
0x14014f8a1  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x14014f8a6  call    BthQueryKeyValueUlongBounded
0x14014f8ab  mov     rax, [rdi+170h]
0x14014f8b2  mov     rcx, [rax+4A8h]
0x14014f8b9  mov     al, byte ptr [rbp+57h+var_70]
0x14014f8bc  mov     rdx, [rcx+198h]
0x14014f8c3  mov     [rdx+0E9h], al
0x14014f8c9  mov     rcx, [rbp+57h+Handle]; Handle
0x14014f8cd  call    cs:__imp_ZwClose
0x14014f8d4  nop     dword ptr [rax+rax+00h]
0x14014f8d9  xor     edx, edx
0x14014f8db  mov     [rbp+57h+phAlgorithm], r12
0x14014f8df  lea     rcx, [rbp+57h+phAlgorithm]
0x14014f8e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14014f8e8  mov     r9d, ebx; dwFlags
0x14014f8eb  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14014f8f2  lea     rdx, pszAlgId; "AES"
0x14014f8f9  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x14014f8fd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14014f904  nop     dword ptr [rax+rax+00h]
0x14014f909  mov     r14d, eax
0x14014f90c  test    eax, eax
0x14014f90e  jns     short loc_14014F971
0x14014f910  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014f917  bt      dword ptr [r10+2Ch], 9
0x14014f91d  jnb     short loc_14014F928
0x14014f91f  cmp     byte ptr [r10+29h], 2
0x14014f924  mov     dl, bl
0x14014f926  jnb     short loc_14014F92B
0x14014f928  mov     dl, r12b
0x14014f92b  mov     rcx, [r10+18h]
0x14014f92f  lea     r9, WPP_d2079bad1218389e735e106ab4414c79_Traceguids
0x14014f936  mov     dword ptr [rsp+0C0h+var_80], r14d
0x14014f93b  mov     r8b, bl
0x14014f93e  mov     [rsp+0C0h+var_88], r9
0x14014f943  mov     r9, [r10+40h]
0x14014f947  mov     word ptr [rsp+0C0h+var_90], 0Dh
0x14014f94e  mov     dword ptr [rsp+0C0h+var_98], 0Ah
0x14014f956  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14014f95b  call    WPP_RECORDER_AND_TRACE_SF_d
0x14014f960  lea     rcx, [rbp+57h+phAlgorithm]
0x14014f964  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14014f969  mov     eax, r14d
0x14014f96c  jmp     loc_14014FBF1
0x14014f971  xor     edx, edx
0x14014f973  mov     [rbp+57h+var_60], r12
0x14014f977  lea     rcx, [rbp+57h+var_60]
0x14014f97b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14014f980  mov     r9d, ebx; dwFlags
0x14014f983  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14014f98a  lea     rdx, aRng; "RNG"
0x14014f991  lea     rcx, [rbp+57h+var_60]; phAlgorithm
0x14014f995  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14014f99c  nop     dword ptr [rax+rax+00h]
0x14014f9a1  mov     r14d, eax
0x14014f9a4  test    eax, eax
0x14014f9a6  jns     short loc_14014FA06
0x14014f9a8  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014f9af  bt      dword ptr [r10+2Ch], 9
0x14014f9b5  jnb     short loc_14014F9C0
0x14014f9b7  cmp     byte ptr [r10+29h], 2
0x14014f9bc  mov     dl, bl
0x14014f9be  jnb     short loc_14014F9C3
0x14014f9c0  mov     dl, r12b
0x14014f9c3  mov     dword ptr [rsp+0C0h+var_80], r14d
0x14014f9c8  lea     r9, WPP_d2079bad1218389e735e106ab4414c79_Traceguids
0x14014f9cf  mov     [rsp+0C0h+var_88], r9
0x14014f9d4  mov     word ptr [rsp+0C0h+var_90], 0Eh
0x14014f9db  mov     r9, [r10+40h]
0x14014f9df  mov     r8b, bl
0x14014f9e2  mov     rcx, [r10+18h]
0x14014f9e6  mov     dword ptr [rsp+0C0h+var_98], 0Ah
0x14014f9ee  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14014f9f3  call    WPP_RECORDER_AND_TRACE_SF_d
0x14014f9f8  lea     rcx, [rbp+57h+var_60]
0x14014f9fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14014fa01  jmp     loc_14014F960
0x14014fa06  lea     rcx, [rsi+88h]
0x14014fa0d  mov     edx, ebx
0x14014fa0f  call    BthLELib_SMPUtilCreateCryptoHandleEx
0x14014fa14  mov     r14d, eax
0x14014fa17  test    eax, eax
0x14014fa19  jns     short loc_14014FA50
0x14014fa1b  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014fa22  bt      dword ptr [r10+2Ch], 9
0x14014fa28  jnb     short loc_14014FA33
0x14014fa2a  cmp     byte ptr [r10+29h], 2
0x14014fa2f  mov     dl, bl
0x14014fa31  jnb     short loc_14014FA36
0x14014fa33  mov     dl, r12b
0x14014fa36  mov     dword ptr [rsp+0C0h+var_80], r14d
0x14014fa3b  lea     r9, WPP_d2079bad1218389e735e106ab4414c79_Traceguids
0x14014fa42  mov     [rsp+0C0h+var_88], r9
0x14014fa47  mov     word ptr [rsp+0C0h+var_90], 0Fh
0x14014fa4e  jmp     short loc_14014F9DB
0x14014fa50  mov     rcx, [rdi+178h]; struct L2CAP_INTERFACE *
0x14014fa57  lea     rax, [rsi+48h]
0x14014fa5b  mov     [rsp+0C0h+var_90], rax; void **
0x14014fa60  lea     r9, ?SMPInt_FixedChannelCallback@@YAXPEAX0KPEAU_FIXED_CHANNEL_SERVER_INDICATION_PARAMETER@@@Z; void (*)(void *, void *, unsigned int, struct _FIXED_CHANNEL_SERVER_INDICATION_PARAMETER *)
0x14014fa67  mov     rax, [rdi+8]
0x14014fa6b  mov     edx, 6; unsigned __int16
0x14014fa70  mov     [rsp+0C0h+var_98], rax; void *
0x14014fa75  mov     [rsp+0C0h+var_A0], rdi; void *
0x14014fa7a  lea     r8d, [rdx-4]; unsigned int
0x14014fa7e  call    ?L2CapInt_RegisterFixedChannelServer@@YAJPEAUL2CAP_INTERFACE@@GKP6AXPEAX1KPEAU_FIXED_CHANNEL_SERVER_INDICATION_PARAMETER@@@Z11PEAPEAX@Z; L2CapInt_RegisterFixedChannelServer(L2CAP_INTERFACE *,ushort,ulong,void (*)(void *,void *,ulong,_FIXED_CHANNEL_SERVER_INDICATION_PARAMETER *),void *,void *,void * *)
0x14014fa83  mov     r14d, eax
0x14014fa86  test    eax, eax
0x14014fa88  jns     short loc_14014FAC2
0x14014fa8a  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014fa91  bt      dword ptr [r10+2Ch], 9
0x14014fa97  jnb     short loc_14014FAA2
0x14014fa99  cmp     byte ptr [r10+29h], 2
0x14014fa9e  mov     dl, bl
0x14014faa0  jnb     short loc_14014FAA5
0x14014faa2  mov     dl, r12b
0x14014faa5  mov     dword ptr [rsp+0C0h+var_80], r14d
0x14014faaa  lea     r9, WPP_d2079bad1218389e735e106ab4414c79_Traceguids
0x14014fab1  mov     [rsp+0C0h+var_88], r9
0x14014fab6  mov     word ptr [rsp+0C0h+var_90], 10h
0x14014fabd  jmp     loc_14014F9DB
0x14014fac2  cmp     [rdi+192h], r12b
0x14014fac9  jz      loc_14014FB80
0x14014facf  mov     rax, [rdi+170h]
0x14014fad6  cmp     [rax+0D1Bh], r12b
0x14014fadd  jz      loc_14014FB80
0x14014fae3  mov     rcx, [rdi+178h]; struct L2CAP_INTERFACE *
0x14014faea  lea     rax, [rsi+50h]
0x14014faee  mov     [rsp+0C0h+var_90], rax; void **
0x14014faf3  lea     r9, ?SMPInt_FixedChannelCallback@@YAXPEAX0KPEAU_FIXED_CHANNEL_SERVER_INDICATION_PARAMETER@@@Z; void (*)(void *, void *, unsigned int, struct _FIXED_CHANNEL_SERVER_INDICATION_PARAMETER *)
0x14014fafa  mov     rax, [rdi+8]
0x14014fafe  mov     edx, 7; unsigned __int16
0x14014fb03  mov     [rsp+0C0h+var_98], rax; void *
0x14014fb08  mov     r8d, ebx; unsigned int
0x14014fb0b  mov     [rsp+0C0h+var_A0], rdi; void *
0x14014fb10  call    ?L2CapInt_RegisterFixedChannelServer@@YAJPEAUL2CAP_INTERFACE@@GKP6AXPEAX1KPEAU_FIXED_CHANNEL_SERVER_INDICATION_PARAMETER@@@Z11PEAPEAX@Z; L2CapInt_RegisterFixedChannelServer(L2CAP_INTERFACE *,ushort,ulong,void (*)(void *,void *,ulong,_FIXED_CHANNEL_SERVER_INDICATION_PARAMETER *),void *,void *,void * *)
0x14014fb15  mov     edi, eax
0x14014fb17  test    eax, eax
0x14014fb19  jns     short loc_14014FB80
0x14014fb1b  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014fb22  bt      dword ptr [r10+2Ch], 9
0x14014fb28  jnb     short loc_14014FB33
0x14014fb2a  cmp     byte ptr [r10+29h], 2
0x14014fb2f  mov     dl, bl
0x14014fb31  jnb     short loc_14014FB36
0x14014fb33  mov     dl, r12b
0x14014fb36  mov     rcx, [r10+18h]
0x14014fb3a  lea     r9, WPP_d2079bad1218389e735e106ab4414c79_Traceguids
0x14014fb41  mov     dword ptr [rsp+0C0h+var_80], edi
0x14014fb45  mov     r8b, bl
0x14014fb48  mov     [rsp+0C0h+var_88], r9
0x14014fb4d  mov     r9, [r10+40h]
0x14014fb51  mov     word ptr [rsp+0C0h+var_90], 11h
0x14014fb58  mov     dword ptr [rsp+0C0h+var_98], 0Ah
0x14014fb60  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14014fb65  call    WPP_RECORDER_AND_TRACE_SF_d
0x14014fb6a  lea     rcx, [rbp+57h+var_60]
0x14014fb6e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14014fb73  lea     rcx, [rbp+57h+phAlgorithm]
0x14014fb77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14014fb7c  mov     eax, edi
0x14014fb7e  jmp     short loc_14014FBF1
0x14014fb80  lea     rdx, [rbp+57h+phAlgorithm]
0x14014fb84  mov     rcx, r15
0x14014fb87  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x14014fb8c  lea     rcx, [rsi+0C0h]
0x14014fb93  lea     rdx, [rbp+57h+var_60]
0x14014fb97  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x14014fb9c  lea     rcx, [rbp+57h+var_60]
0x14014fba0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14014fba5  lea     rcx, [rbp+57h+phAlgorithm]
0x14014fba9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14014fbae  jmp     short loc_14014FBEF
0x14014fbb0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
  ... truncated ...
```
