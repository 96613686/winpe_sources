# HCI_DibUnpairClassic(DEVICE_INFO_BLOCK *,_IRP *,bool)

- ea: `0x14005d3a0`
- end: `0x14005d8aa`
- name: `?HCI_DibUnpairClassic@@YAJPEAUDEVICE_INFO_BLOCK@@PEAU_IRP@@_N@Z`
- size: `1290`
- prototype: `__int64 __fastcall(struct DEVICE_INFO_BLOCK *, struct _IRP *, bool)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005cfe0`
- `0x14005e140`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005690`
- `0x140005c04`
- `0x14000f27c`
- `0x14000fab4`
- `0x14001c5dc`
- `0x140020414`
- `0x140020574`
- `0x140052de4`
- `0x140052f74`
- `0x14005335c`
- `0x14005b478`
- `0x14005d3a0`
- `0x14005d8b0`
- `0x14005fe30`
- `0x14006405c`
- `0x1400640fc`
- `0x1400a6210`
- `0x1400a6300`
- `0x140130dac`
- `0x140162008`
- `0x140165540`
- `0x1401be5f8`
- `0x1401bebe8`
- `0x1401c053c`
- `0x1401c1a48`
- `0x1401e629c`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x14005d6ff`
- `ntoskrnl!ZwDeleteValueKey` at `0x14005d72a`
- `ntoskrnl!ZwDeleteValueKey` at `0x14005d6ff`
- `ntoskrnl!ZwDeleteValueKey` at `0x14005d72a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d6eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d716`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d6eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d716`

## string_xrefs

- `0x14005d70b`: `Store Link Key`

## pseudocode

```c
__int64 __fastcall HCI_DibUnpairClassic(struct DEVICE_INFO_BLOCK *a1, struct _IRP *a2, char a3)
{
  struct _GUID *v6; // rax
  unsigned __int64 *p_HciLock; // rdx
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // ebx
  unsigned int v11; // r14d
  bool v12; // bl
  unsigned __int64 *p_address; // r15
  unsigned __int8 v15; // r12
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  HCI_INTERFACE *Hci; // rax
  void **v20; // rax
  int v21; // edx
  int PersonalDevicesKey; // r8d
  unsigned int v23; // r9d
  enum ExtendedDeviceInfoFlags v24; // dl
  void **v25; // rax
  HCI_INTERFACE *v26; // rcx
  struct HCI_INTERFACE *v27; // rcx
  struct DEVICE_INFO_BLOCK *LinkedDib; // rax
  unsigned int NumProtocols; // ebx
  struct HCI_INTERFACE *v30; // rcx
  __int64 v31; // [rsp+20h] [rbp-89h]
  char v32; // [rsp+40h] [rbp-69h]
  unsigned __int8 v33[8]; // [rsp+50h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-51h] BYREF
  HANDLE KeyHandle; // [rsp+68h] [rbp-41h] BYREF
  GUID ActivityId; // [rsp+70h] [rbp-39h] BYREF
  struct _GUID v37; // [rsp+80h] [rbp-29h] BYREF
  struct _ENUMERATOR_INFO *v38[3]; // [rsp+90h] [rbp-19h] BYREF
  WCHAR SourceString[16]; // [rsp+A8h] [rbp-1h] BYREF

  v6 = (struct _GUID *)BthGetActivityID(&ActivityId);
  p_HciLock = &a1->Hci->HciLock;
  v33[0] = 0;
  v37 = *v6;
  wil::acquire_kspin_lock(&ActivityId, p_HciLock);
  if ( (a1->DeviceInfo.flags & 0x18) == 0 )
  {
    LOBYTE(v8) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v9) = 1;
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      a1->IfrLog,
      4,
      2,
      157,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
      (char)a1,
      a1->DeviceInfo.flags);
    v10 = -1073741811;
    goto LABEL_12;
  }
  v11 = a1->DeviceInfo.flags & 8;
  _InterlockedOr64((volatile signed __int64 *)&a1->DibFlags, 0x10u);
  if ( a3 )
    _InterlockedOr64((volatile signed __int64 *)&a1->DibFlags, 0x1000000000uLL);
  v12 = 1;
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  a1->UnpairIrp = a2;
  if ( v11 && (a1->DibFlags._MyVal & 0x2000000) != 0 )
  {
    v10 = 259;
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&ActivityId);
    return v10;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&ActivityId);
  p_address = &a1->DeviceInfo.address;
  HCI_CallPairServers(a1->Hci, a1->DeviceInfo.address, v11 != 0 ? 2 : 4);
  wil::acquire_fast_mutex_with_critical_region(&ActivityId, &a1->ProtocolsLock);
  v15 = HCI_IsDeleteStoredLinkKeyRequired(a1->Hci, a1, v33);
  if ( v11 )
  {
    v16 = HCI_DibDeleteLinkKey(a1);
    if ( v16 < 0 )
    {
      LOBYTE(v17) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      LOBYTE(v18) = 1;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v17,
        v18,
        a1->IfrLog,
        3,
        2,
        158,
        (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
        *p_address,
        v16);
    }
    Hci = a1->Hci;
    a1->IoCapability = IoCaps_Undefined;
    a1->LocalAuthenticationRequirements = Hci->DefaultAuthenticationRequirements;
    a1->RemoteAuthenticationRequirements = MITMProtectionNotDefined;
    a1->LocalEvaldIoCap = IoCaps_Undefined;
    a1->StrictMITM = 0;
  }
  else
  {
    *(_QWORD *)&DestinationString.Length = 0;
    v20 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&DestinationString);
    PersonalDevicesKey = HCI_GetPersonalDevicesKey(a1->Hci, v20, 0);
    if ( PersonalDevicesKey < 0 )
    {
      LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      v32 = PersonalDevicesKey;
      LOBYTE(PersonalDevicesKey) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v21,
        PersonalDevicesKey,
        a1->IfrLog,
        2,
        2,
        159,
        (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
        v32);
    }
    else
    {
      HCI_DibSetPersonal(a1, *(HANDLE *)&DestinationString.Length, 0, v23);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&DestinationString);
  }
  HCI_DibSetFlags(a1, 0x2C000618u, 0);
  HCI_DibClearExtendedFlags(a1, v24);
  KeyHandle = 0;
  v25 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&KeyHandle);
  if ( (int)HCI_DibGetDeviceKey(a1, v25, 0) >= 0 )
  {
    v26 = a1->Hci;
    DestinationString = 0;
    LODWORD(v31) = v26->LocalInfo.localInfo.address;
    if ( (int)RtlStringCbPrintfW(
                SourceString,
                0x1Au,
                L"%04x%08x",
                (unsigned __int16)WORD2(v26->LocalInfo.localInfo.address),
                v31) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      ZwDeleteValueKey(KeyHandle, &DestinationString);
    }
    RtlInitUnicodeString(&DestinationString, L"Store Link Key");
    ZwDeleteValueKey(KeyHandle, &DestinationString);
  }
  HCI_CleanupHidStateHack(a1->Hci, &a1->DeviceInfo.address);
  v27 = a1->Hci;
  memset(v38, 0, sizeof(v38));
  HCI_ReferenceEnumerators(v27, HCI_DibUnpairClassic, (struct _ENUMERATOR_INFO *(*)[3])v38, 0);
  wil::acquire_kspin_lock(&DestinationString, &a1->Hci->HciLock);
  if ( a1->LinkedDibAddress == *p_address )
  {
    LinkedDib = HCI_FindLinkedDib(&a1->Hci->DeviceList, a1);
    if ( LinkedDib )
      v12 = (LinkedDib->DeviceInfo.flags & 0x30000) == 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&DestinationString);
  HCI_DibEnumerateAll(a1, v38, ENUMERATOR_ACTION_DESTROY, 0, v12);
  NumProtocols = a1->NumProtocols;
  HCI_DibFreeProtocolTree(a1);
  HCI_ReleaseEnumerators(v38, HCI_DibUnpairClassic);
  wil::acquire_kspin_lock(&DestinationString, &a1->Hci->HciLock);
  a1->Hci->TotalRemotePDOs -= NumProtocols;
  _InterlockedAnd64((volatile signed __int64 *)&a1->DibFlags, 0xFFFFFFFFFFFFFF7FuLL);
  if ( v15 )
    _InterlockedAnd64((volatile signed __int64 *)&a1->DibFlags, 0xFFFFFFFFFBFFFFFFuLL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&DestinationString);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&ActivityId);
  v30 = a1->Hci;
  if ( v15 )
    HCI_SendDeleteLinkKeyCommand(v30, a1, v33[0], &v37);
  else
    HCI_DibUnpairComplete(v30, a1, v11 != 0);
  return 259;
}

```

## disassembly

```asm
0x14005d3a0  mov     [rsp-8+arg_10], rbx
0x14005d3a5  push    rbp
0x14005d3a6  push    rsi
0x14005d3a7  push    rdi
0x14005d3a8  push    r12
0x14005d3aa  push    r13
0x14005d3ac  push    r14
0x14005d3ae  push    r15
0x14005d3b0  lea     rbp, [rsp-27h]
0x14005d3b5  sub     rsp, 0D0h
0x14005d3bc  mov     rax, cs:__security_cookie
0x14005d3c3  xor     rax, rsp
0x14005d3c6  mov     [rbp+57h+var_38], rax
0x14005d3ca  mov     rdi, rcx
0x14005d3cd  mov     bl, r8b
0x14005d3d0  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x14005d3d4  mov     rsi, rdx
0x14005d3d7  call    BthGetActivityID
0x14005d3dc  mov     rdx, [rdi+378h]
0x14005d3e3  lea     rcx, [rbp+57h+ActivityId]
0x14005d3e7  add     rdx, 7B0h
0x14005d3ee  mov     [rbp+57h+var_B0], 0
0x14005d3f2  movups  xmm0, xmmword ptr [rax]
0x14005d3f5  movdqu  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x14005d3fa  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005d3ff  mov     r14d, [rdi+18h]
0x14005d403  test    r14b, 18h
0x14005d407  jnz     short loc_14005D46B
0x14005d409  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005d410  mov     esi, 2
0x14005d415  mov     bl, 1
0x14005d417  mov     eax, [rcx+2Ch]
0x14005d41a  test    sil, al
0x14005d41d  jz      short loc_14005D429
0x14005d41f  cmp     byte ptr [rcx+29h], 4
0x14005d423  jb      short loc_14005D429
0x14005d425  mov     dl, bl
0x14005d427  jmp     short loc_14005D42B
0x14005d429  xor     dl, dl
0x14005d42b  mov     r9, [rdi+838h]
0x14005d432  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x14005d439  mov     rcx, [rcx+18h]
0x14005d43d  mov     r8b, bl
0x14005d440  mov     [rsp+100h+var_B8], r14d
0x14005d445  mov     [rsp+100h+var_C0], rdi
0x14005d44a  mov     [rsp+100h+var_C8], rax
0x14005d44f  mov     [rsp+100h+var_D0], 9Dh
0x14005d456  mov     [rsp+100h+var_D8], esi
0x14005d45a  mov     [rsp+100h+var_E0], 4
0x14005d45f  call    WPP_RECORDER_AND_TRACE_SF_qL
0x14005d464  mov     ebx, 0C000000Dh
0x14005d469  jmp     short loc_14005D4C2
0x14005d46b  and     r14d, 8
0x14005d46f  nop
0x14005d470  setnz   r13b
0x14005d474  lock or qword ptr [rdi+368h], 10h
0x14005d47d  nop
0x14005d47e  test    bl, bl
0x14005d480  jz      short loc_14005D496
0x14005d482  nop
0x14005d483  mov     rax, 1000000000h
0x14005d48d  lock or [rdi+368h], rax
0x14005d495  nop
0x14005d496  mov     rax, [rsi+0B8h]
0x14005d49d  mov     bl, 1
0x14005d49f  or      [rax+3], bl
0x14005d4a2  mov     [rdi+5C0h], rsi
0x14005d4a9  test    r14d, r14d
0x14005d4ac  jz      short loc_14005D4D2
0x14005d4ae  mov     rax, [rdi+368h]
0x14005d4b5  nop
0x14005d4b6  bt      rax, 19h
0x14005d4bb  jnb     short loc_14005D4D2
0x14005d4bd  mov     ebx, 103h
0x14005d4c2  lea     rcx, [rbp+57h+ActivityId]
0x14005d4c6  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005d4cb  mov     eax, ebx
0x14005d4cd  jmp     loc_14005D882
0x14005d4d2  lea     rcx, [rbp+57h+ActivityId]
0x14005d4d6  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005d4db  mov     rcx, [rdi+378h]; struct HCI_INTERFACE *
0x14005d4e2  lea     r15, [rdi+20h]
0x14005d4e6  mov     rdx, [r15]; unsigned __int64
0x14005d4e9  mov     eax, r14d
0x14005d4ec  neg     eax
0x14005d4ee  sbb     r8d, r8d
0x14005d4f1  and     r8d, 0FFFFFFFEh
0x14005d4f5  add     r8d, 4; unsigned int
0x14005d4f9  call    ?HCI_CallPairServers@@YAXPEAUHCI_INTERFACE@@_KK@Z; HCI_CallPairServers(HCI_INTERFACE *,unsigned __int64,ulong)
0x14005d4fe  lea     rdx, [rdi+380h]
0x14005d505  lea     rcx, [rbp+57h+ActivityId]
0x14005d509  call    ?acquire_fast_mutex_with_critical_region@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_FAST_MUTEX@@@Z
0x14005d50e  mov     rcx, [rdi+378h]; struct HCI_INTERFACE *
0x14005d515  lea     r8, [rbp+57h+var_B0]; unsigned __int8 *
0x14005d519  mov     rdx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d51c  call    ?HCI_IsDeleteStoredLinkKeyRequired@@YAEPEAUHCI_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@PEAE@Z; HCI_IsDeleteStoredLinkKeyRequired(HCI_INTERFACE *,DEVICE_INFO_BLOCK *,uchar *)
0x14005d521  mov     r12b, al
0x14005d524  test    r14d, r14d
0x14005d527  jz      loc_14005D5CC
0x14005d52d  mov     rcx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d530  call    ?HCI_DibDeleteLinkKey@@YAJPEAUDEVICE_INFO_BLOCK@@@Z; HCI_DibDeleteLinkKey(DEVICE_INFO_BLOCK *)
0x14005d535  mov     esi, 2
0x14005d53a  test    eax, eax
0x14005d53c  jns     short loc_14005D596
0x14005d53e  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005d545  mov     ecx, [r10+2Ch]
0x14005d549  test    sil, cl
0x14005d54c  jz      short loc_14005D559
0x14005d54e  cmp     byte ptr [r10+29h], 3
0x14005d553  jb      short loc_14005D559
0x14005d555  mov     dl, bl
0x14005d557  jmp     short loc_14005D55B
0x14005d559  xor     dl, dl
0x14005d55b  mov     r9, [rdi+838h]
0x14005d562  mov     r8b, bl
0x14005d565  mov     rcx, [r10+18h]
0x14005d569  mov     [rsp+100h+var_B8], eax
0x14005d56d  mov     rax, [r15]
0x14005d570  mov     [rsp+100h+var_C0], rax
0x14005d575  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x14005d57c  mov     [rsp+100h+var_C8], rax
0x14005d581  mov     [rsp+100h+var_D0], 9Eh
0x14005d588  mov     [rsp+100h+var_D8], esi
0x14005d58c  mov     [rsp+100h+var_E0], 3
0x14005d591  call    WPP_RECORDER_AND_TRACE_SF_qL
0x14005d596  mov     rax, [rdi+378h]
0x14005d59d  mov     edx, 0FFh
0x14005d5a2  mov     [rdi+5C8h], edx
0x14005d5a8  mov     ecx, [rax+0D34h]
0x14005d5ae  mov     [rdi+5CCh], ecx
0x14005d5b4  mov     [rdi+5D0h], edx
0x14005d5ba  mov     [rdi+840h], edx
0x14005d5c0  mov     byte ptr [rdi+844h], 0
0x14005d5c7  jmp     loc_14005D664
0x14005d5cc  lea     rcx, [rbp+57h+DestinationString]
0x14005d5d0  mov     qword ptr [rbp+57h+DestinationString.Length], 0
0x14005d5d8  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x14005d5dd  mov     rcx, [rdi+378h]; struct HCI_INTERFACE *
0x14005d5e4  xor     r8d, r8d; unsigned __int8
0x14005d5e7  mov     rdx, rax; void **
0x14005d5ea  call    ?HCI_GetPersonalDevicesKey@@YAJPEAUHCI_INTERFACE@@PEAPEAXE@Z; HCI_GetPersonalDevicesKey(HCI_INTERFACE *,void * *,uchar)
0x14005d5ef  mov     r8d, eax
0x14005d5f2  mov     esi, 2
0x14005d5f7  test    eax, eax
0x14005d5f9  js      short loc_14005D60C
0x14005d5fb  mov     rdx, qword ptr [rbp+57h+DestinationString.Length]; KeyHandle
0x14005d5ff  xor     r8d, r8d; struct _BTH_DEVICE_INFO *
0x14005d602  mov     rcx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d605  call    ?HCI_DibSetPersonal@@YAXPEAUDEVICE_INFO_BLOCK@@PEAXPEAU_BTH_DEVICE_INFO@@K@Z; HCI_DibSetPersonal(DEVICE_INFO_BLOCK *,void *,_BTH_DEVICE_INFO *,ulong)
0x14005d60a  jmp     short loc_14005D65B
0x14005d60c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005d613  mov     eax, [rcx+2Ch]
0x14005d616  test    sil, al
0x14005d619  jz      short loc_14005D625
0x14005d61b  cmp     [rcx+29h], sil
0x14005d61f  jb      short loc_14005D625
0x14005d621  mov     dl, bl
0x14005d623  jmp     short loc_14005D627
0x14005d625  xor     dl, dl
0x14005d627  mov     r9, [rdi+838h]
0x14005d62e  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x14005d635  mov     rcx, [rcx+18h]
0x14005d639  mov     dword ptr [rsp+100h+var_C0], r8d
0x14005d63e  mov     r8b, bl
0x14005d641  mov     [rsp+100h+var_C8], rax
0x14005d646  mov     [rsp+100h+var_D0], 9Fh
0x14005d64d  mov     [rsp+100h+var_D8], esi
0x14005d651  mov     [rsp+100h+var_E0], sil
0x14005d656  call    WPP_RECORDER_AND_TRACE_SF_d
0x14005d65b  lea     rcx, [rbp+57h+DestinationString]
0x14005d65f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005d664  xor     r8d, r8d; unsigned __int8
0x14005d667  mov     edx, 2C000618h; unsigned int
0x14005d66c  mov     rcx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d66f  call    ?HCI_DibSetFlags@@YAEPEAUDEVICE_INFO_BLOCK@@KE@Z; HCI_DibSetFlags(DEVICE_INFO_BLOCK *,ulong,uchar)
0x14005d674  mov     rcx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d677  call    ?HCI_DibClearExtendedFlags@@YA?AW4ExtendedDeviceInfoFlags@@AEAUDEVICE_INFO_BLOCK@@W41@@Z; HCI_DibClearExtendedFlags(DEVICE_INFO_BLOCK &,ExtendedDeviceInfoFlags)
0x14005d67c  lea     rcx, [rbp+57h+KeyHandle]
0x14005d680  mov     [rbp+57h+KeyHandle], 0
0x14005d688  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x14005d68d  xor     r8d, r8d; unsigned __int8
0x14005d690  mov     rdx, rax; void **
0x14005d693  mov     rcx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d696  call    ?HCI_DibGetDeviceKey@@YAJPEBUDEVICE_INFO_BLOCK@@PEAPEAXE@Z; HCI_DibGetDeviceKey(DEVICE_INFO_BLOCK const *,void * *,uchar)
0x14005d69b  test    eax, eax
0x14005d69d  js      loc_14005D736
0x14005d6a3  mov     rcx, [rdi+378h]
0x14005d6aa  lea     r8, a04x08x; "%04x%08x"
0x14005d6b1  xorps   xmm0, xmm0
0x14005d6b4  mov     edx, 1Ah; unsigned __int64
0x14005d6b9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005d6bd  mov     rax, [rcx+124h]
0x14005d6c4  shr     rax, 20h
0x14005d6c8  movzx   r9d, ax
0x14005d6cc  mov     eax, [rcx+124h]
0x14005d6d2  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 *
0x14005d6d6  mov     dword ptr [rsp+100h+var_E0], eax
0x14005d6da  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005d6df  test    eax, eax
0x14005d6e1  js      short loc_14005D70B
0x14005d6e3  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14005d6e7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005d6eb  call    cs:__imp_RtlInitUnicodeString
0x14005d6f2  nop     dword ptr [rax+rax+00h]
0x14005d6f7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005d6fb  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14005d6ff  call    cs:__imp_ZwDeleteValueKey
0x14005d706  nop     dword ptr [rax+rax+00h]
0x14005d70b  lea     rdx, aStoreLinkKey; "Store Link Key"
0x14005d712  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005d716  call    cs:__imp_RtlInitUnicodeString
0x14005d71d  nop     dword ptr [rax+rax+00h]
0x14005d722  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005d726  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14005d72a  call    cs:__imp_ZwDeleteValueKey
0x14005d731  nop     dword ptr [rax+rax+00h]
0x14005d736  mov     rcx, [rdi+378h]; struct HCI_INTERFACE *
0x14005d73d  mov     rdx, r15; unsigned __int64 *
0x14005d740  call    ?HCI_CleanupHidStateHack@@YAXPEAUHCI_INTERFACE@@PEA_K@Z; HCI_CleanupHidStateHack(HCI_INTERFACE *,unsigned __int64 *)
0x14005d745  mov     rcx, [rdi+378h]; struct HCI_INTERFACE *
0x14005d74c  lea     r8, [rbp+57h+var_70]; struct _ENUMERATOR_INFO *(*)[3]
0x14005d750  xorps   xmm0, xmm0
0x14005d753  lea     rdx, ?HCI_DibUnpairClassic@@YAJPEAUDEVICE_INFO_BLOCK@@PEAU_IRP@@_N@Z; void *
0x14005d75a  xor     eax, eax
0x14005d75c  xor     r9d, r9d; bool
0x14005d75f  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x14005d763  mov     [rbp+57h+var_70+10h], rax
0x14005d767  call    ?HCI_ReferenceEnumerators@@YAXPEAUHCI_INTERFACE@@PEAXAEAY02PEAU_ENUMERATOR_INFO@@_N@Z; HCI_ReferenceEnumerators(HCI_INTERFACE *,void *,_ENUMERATOR_INFO * (&)[3],bool)
0x14005d76c  mov     rdx, [rdi+378h]
0x14005d773  lea     rcx, [rbp+57h+DestinationString]
0x14005d777  mov     r14d, 7B0h
0x14005d77d  add     rdx, r14
0x14005d780  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005d785  mov     rax, [r15]
0x14005d788  cmp     [rdi+8E8h], rax
0x14005d78f  jnz     short loc_14005D7BE
0x14005d791  mov     rcx, [rdi+378h]
0x14005d798  mov     rdx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d79b  add     rcx, 810h; struct _LIST_ENTRY *
0x14005d7a2  call    ?HCI_FindLinkedDib@@YAPEAUDEVICE_INFO_BLOCK@@PEAU_LIST_ENTRY@@PEAU1@@Z; HCI_FindLinkedDib(_LIST_ENTRY *,DEVICE_INFO_BLOCK *)
0x14005d7a7  test    rax, rax
0x14005d7aa  jz      short loc_14005D7BE
0x14005d7ac  test    dword ptr [rax+18h], 30000h
0x14005d7b3  mov     eax, 0
0x14005d7b8  movzx   ebx, bl
0x14005d7bb  cmovnz  ebx, eax
0x14005d7be  lea     rcx, [rbp+57h+DestinationString]
0x14005d7c2  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005d7c7  xor     r9d, r9d; enum _ENUMERATOR_TYPE *
0x14005d7ca  mov     [rsp+100h+var_E0], bl; bool
0x14005d7ce  mov     r8d, esi; enum _ENUMERATOR_ACTION
0x14005d7d1  lea     rdx, [rbp+57h+var_70]; struct _ENUMERATOR_INFO **
0x14005d7d5  mov     rcx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d7d8  call    ?HCI_DibEnumerateAll@@YAXPEAUDEVICE_INFO_BLOCK@@PEAPEAU_ENUMERATOR_INFO@@W4_ENUMERATOR_ACTION@@PEAW4_ENUMERATOR_TYPE@@_N@Z; HCI_DibEnumerateAll(DEVICE_INFO_BLOCK *,_ENUMERATOR_INFO * *,_ENUMERATOR_ACTION,_ENUMERATOR_TYPE *,bool)
0x14005d7dd  mov     ebx, [rdi+3C0h]
0x14005d7e3  mov     rcx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d7e6  call    ?HCI_DibFreeProtocolTree@@YAXPEAUDEVICE_INFO_BLOCK@@@Z; HCI_DibFreeProtocolTree(DEVICE_INFO_BLOCK *)
0x14005d7eb  lea     rdx, ?HCI_DibUnpairClassic@@YAJPEAUDEVICE_INFO_BLOCK@@PEAU_IRP@@_N@Z; void *
0x14005d7f2  lea     rcx, [rbp+57h+var_70]; struct _ENUMERATOR_INFO **
0x14005d7f6  call    ?HCI_ReleaseEnumerators@@YAXPEAPEAU_ENUMERATOR_INFO@@PEAX@Z; HCI_ReleaseEnumerators(_ENUMERATOR_INFO * *,void *)
0x14005d7fb  mov     rdx, [rdi+378h]
0x14005d802  lea     rcx, [rbp+57h+DestinationString]
0x14005d806  add     rdx, r14
0x14005d809  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005d80e  mov     rax, [rdi+378h]
0x14005d815  sub     [rax+0D40h], ebx
0x14005d81b  nop
0x14005d81c  lock and qword ptr [rdi+368h], 0FFFFFFFFFFFFFF7Fh
0x14005d828  nop
0x14005d829  test    r12b, r12b
0x14005d82c  jz      short loc_14005D83C
0x14005d82e  nop
0x14005d82f  lock and qword ptr [rdi+368h], 0FFFFFFFFFBFFFFFFh
0x14005d83b  nop
0x14005d83c  lea     rcx, [rbp+57h+DestinationString]
0x14005d840  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005d845  lea     rcx, [rbp+57h+KeyHandle]
0x14005d849  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005d84e  lea     rcx, [rbp+57h+ActivityId]
0x14005d852  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14005d857  mov     rcx, [rdi+378h]; struct HCI_INTERFACE *
0x14005d85e  mov     rdx, rdi; struct DEVICE_INFO_BLOCK *
0x14005d861  test    r12b, r12b
0x14005d864  jz      short loc_14005D875
0x14005d866  mov     r8b, [rbp+57h+var_B0]; unsigned __int8
0x14005d86a  lea     r9, [rbp+57h+var_80]; struct _GUID *
0x14005d86e  call    ?HCI_SendDeleteLinkKeyCommand@@YAJPEAUHCI_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@EPEAU_GUID@@@Z; HCI_SendDeleteLinkKeyCommand(HCI_INTERFACE *,DEVICE_INFO_BLOCK *,uchar,_GUID *)
0x14005d873  jmp     short loc_14005D87D
0x14005d875  mov     r8b, r13b; unsigned __int8
0x14005d878  call    ?HCI_DibUnpairComplete@@YAXPEAUHCI_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@E@Z; HCI_DibUnpairComplete(HCI_INTERFACE *,DEVICE_INFO_BLOCK *,uchar)
0x14005d87d  mov     eax, 103h
0x14005d882  mov     rcx, [rbp+57h+var_38]
0x14005d886  xor     rcx, rsp; StackCookie
0x14005d889  call    __security_check_cookie
0x14005d88e  mov     rbx, [rsp+100h+arg_10]
0x14005d896  add     rsp, 0D0h
0x14005d89d  pop     r15
0x14005d89f  pop     r14
0x14005d8a1  pop     r13
0x14005d8a3  pop     r12
  ... truncated ...
```
