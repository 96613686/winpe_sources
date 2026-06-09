# HCI_DibReportDeviceChange(DEVICE_INFO_BLOCK *,ulong,bool,bool)

- ea: `0x14005ad28`
- end: `0x14005b2cd`
- name: `?HCI_DibReportDeviceChange@@YAXPEAUDEVICE_INFO_BLOCK@@K_N1@Z`
- size: `1445`
- prototype: `void __fastcall(struct DEVICE_INFO_BLOCK *, unsigned int, bool, bool)`
- caller_count: `8`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14003db44`
- `0x14003e0f4`
- `0x14003e510`
- `0x14005aa60`
- `0x14005b478`
- `0x14005baa0`
- `0x140065b9c`
- `0x1400a9a50`

## callees

- `0x140004368`
- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005690`
- `0x14001b794`
- `0x140050870`
- `0x140059630`
- `0x14005ad28`
- `0x140067bc0`
- `0x140165640`
- `0x140165940`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14005afe8`
- `ntoskrnl!RtlCompareMemory` at `0x14005afe8`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x14005ae58`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x14005ae58`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14005b246`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14005b246`
- `ntoskrnl!ExAllocatePool2` at `0x14005ad6a`
- `ntoskrnl!ExAllocatePool2` at `0x14005ad6a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005b210`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005b210`

## pseudocode

```c
void __fastcall HCI_DibReportDeviceChange(struct DEVICE_INFO_BLOCK *a1, int a2, char a3, char a4)
{
  unsigned int v7; // edi
  char *Pool2; // rax
  int v10; // edx
  int v11; // r8d
  char *v12; // r14
  unsigned __int64 *v13; // rdi
  unsigned int flags; // r8d
  unsigned int v15; // r9d
  int v16; // r8d
  int NameLen; // eax
  unsigned int v18; // ecx
  int *p_RSSI; // rdx
  int SavedRadioInRangeRssi; // ecx
  int SimilarEventRssiDelta; // r8d
  char v22; // r15
  _BTH_RADIO_IN_RANGE *p_SavedEventRadioInRange; // rcx
  _OWORD *v24; // rax
  __int64 v25; // rdx
  __int128 v26; // xmm1
  unsigned __int8 LEOriginalAddressType; // cl
  __int128 v28; // xmm0
  HCI_INTERFACE *Hci; // rcx
  int v30; // eax
  int v31; // edx
  int v32; // r8d
  union _LARGE_INTEGER SystemTime[2]; // [rsp+50h] [rbp-19h] BYREF
  char *v34; // [rsp+60h] [rbp-9h] BYREF
  _OWORD v35[5]; // [rsp+70h] [rbp+7h] BYREF

  v7 = a3 != 0 ? 0x108 : 0;
  Pool2 = (char *)ExAllocatePool2(64, v7 + 56LL, 1346917442);
  v12 = Pool2;
  if ( !Pool2 )
  {
    v34 = 0;
    LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v11) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      v11,
      a1->IfrLog,
      2,
      2,
      117,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids);
    goto LABEL_53;
  }
  memset(Pool2, 0, v7 + 56LL);
  v34 = v12;
  *(_WORD *)v12 = 1;
  v13 = (unsigned __int64 *)(v12 + 36);
  *((_DWORD *)v12 + 8) = -1;
  *((_QWORD *)v12 + 3) = 0;
  if ( !a3 )
  {
    *((_WORD *)v12 + 1) = 55;
    *(GUID *)(v12 + 4) = GUID_BLUETOOTH_RADIO_OUT_OF_RANGE;
    *v13 = a1->DeviceInfo.address;
    if ( (a1->DeviceInfo.flags & 0x8000) != 0 )
    {
      LEOriginalAddressType = 0;
      if ( a1->LEOriginalAddressType != 0xFF )
        LEOriginalAddressType = a1->LEOriginalAddressType;
    }
    else
    {
      LEOriginalAddressType = -1;
    }
    v12[44] = LEOriginalAddressType;
    wil::acquire_kspin_lock(v35, &a1->Hci->HciLock);
    a1->SavedEventIsOutOfRange = 1;
    v22 = 1;
    goto LABEL_34;
  }
  *((_WORD *)v12 + 1) = 319;
  *(GUID *)(v12 + 4) = GUID_BLUETOOTH_RADIO_IN_RANGE;
  *((_DWORD *)v12 + 77) = a2;
  wil::acquire_kspin_lock(v35, &a1->Hci->HciLock);
  *(_QWORD *)(v12 + 44) = a1->DeviceInfo.address;
  *((_DWORD *)v12 + 13) = a1->DeviceInfo.classOfDevice;
  flags = a1->DeviceInfo.flags;
  *(_DWORD *)v13 = flags;
  v15 = a1->DeviceInfo.flags;
  if ( (v15 & 0x4000) != 0 && a1->Hci->CountInquiryScan - a1->LastInquiryScan <= a1->Hci->NumInquiryCycleCleanup )
  {
    flags |= 0x80u;
  }
  else
  {
    if ( (v15 & 0x8000) == 0 )
      goto LABEL_11;
    SystemTime[0].QuadPart = MEMORY[0xFFFFF78000000014];
    ExSystemTimeToLocalTime(SystemTime, SystemTime);
    v16 = *(_DWORD *)v13;
    if ( SystemTime[0].QuadPart - a1->LastSeenTimestamp.QuadPart > a1->Hci->LastEventThreshold.QuadPart )
      flags = v16 & 0xFD7FFFFF;
    else
      flags = v16 | 0x800000;
  }
  *(_DWORD *)v13 = flags;
LABEL_11:
  if ( a1->FriendlyName[0] )
  {
    *(_OWORD *)(v12 + 56) = *(_OWORD *)a1->FriendlyName;
    *(_OWORD *)(v12 + 72) = *(_OWORD *)&a1->FriendlyName[16];
    *(_OWORD *)(v12 + 88) = *(_OWORD *)&a1->FriendlyName[32];
    *(_OWORD *)(v12 + 104) = *(_OWORD *)&a1->FriendlyName[48];
    *(_OWORD *)(v12 + 120) = *(_OWORD *)&a1->FriendlyName[64];
    *(_OWORD *)(v12 + 136) = *(_OWORD *)&a1->FriendlyName[80];
    *(_OWORD *)(v12 + 152) = *(_OWORD *)&a1->FriendlyName[96];
    *(_OWORD *)(v12 + 168) = *(_OWORD *)&a1->FriendlyName[112];
    *(_OWORD *)(v12 + 184) = *(_OWORD *)&a1->FriendlyName[128];
    *(_OWORD *)(v12 + 200) = *(_OWORD *)&a1->FriendlyName[144];
    *(_OWORD *)(v12 + 216) = *(_OWORD *)&a1->FriendlyName[160];
    *(_OWORD *)(v12 + 232) = *(_OWORD *)&a1->FriendlyName[176];
    *(_OWORD *)(v12 + 248) = *(_OWORD *)&a1->FriendlyName[192];
    *(_OWORD *)(v12 + 264) = *(_OWORD *)&a1->FriendlyName[208];
    *(_OWORD *)(v12 + 280) = *(_OWORD *)&a1->FriendlyName[224];
    *((_QWORD *)v12 + 37) = *(_QWORD *)&a1->FriendlyName[240];
    *(_DWORD *)v13 = flags | 4;
    goto LABEL_19;
  }
  if ( (a1->DeviceInfo.flags & 4) != 0 && a1->NameLen )
  {
    memmove(v12 + 56, a1->DeviceInfo.name, a1->NameLen);
    NameLen = a1->NameLen;
    v18 = 248 - NameLen;
    if ( NameLen == 248 )
      goto LABEL_19;
  }
  else
  {
    v18 = 240;
    *((_QWORD *)v12 + 7) = *(_QWORD *)a1->DeviceInfo.name;
  }
  memset((char *)v13 - v18 + 268, 0, v18);
LABEL_19:
  if ( a1->SavedEventIsOutOfRange
    || RtlCompareMemory(&a1->SavedEventRadioInRange, v12 + 36, 0x118u) != 280
    || (p_RSSI = &a1->DeviceInfo.RSSI,
        SavedRadioInRangeRssi = a1->SavedRadioInRangeRssi,
        SimilarEventRssiDelta = a1->Hci->SimilarEventRssiDelta,
        a1->DeviceInfo.RSSI - SavedRadioInRangeRssi >= SimilarEventRssiDelta)
    || SavedRadioInRangeRssi - a1->DeviceInfo.RSSI >= SimilarEventRssiDelta )
  {
    v22 = 1;
    a1->SavedEventIsOutOfRange = 0;
    p_SavedEventRadioInRange = &a1->SavedEventRadioInRange;
    v24 = v12 + 36;
    v25 = 2;
    do
    {
      *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.flags = *v24;
      *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.classOfDevice = v24[1];
      *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.name[12] = v24[2];
      *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.name[28] = v24[3];
      *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.name[44] = v24[4];
      *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.name[60] = v24[5];
      *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.name[76] = v24[6];
      v26 = v24[7];
      v24 += 8;
      *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.name[92] = v26;
      p_SavedEventRadioInRange = (_BTH_RADIO_IN_RANGE *)((char *)p_SavedEventRadioInRange + 128);
      --v25;
    }
    while ( v25 );
    p_RSSI = &a1->DeviceInfo.RSSI;
    *(_OWORD *)&p_SavedEventRadioInRange->deviceInfo.flags = *v24;
    *(_QWORD *)&p_SavedEventRadioInRange->deviceInfo.classOfDevice = *((_QWORD *)v24 + 2);
  }
  else
  {
    v22 = 0;
  }
  *((_DWORD *)v12 + 76) = *p_RSSI;
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v35);
  if ( v22 || MEMORY[0xFFFFF78000000014] - a1->SavedEventTimestamp.QuadPart >= a1->Hci->SimilarEventTimeDelta.QuadPart )
  {
    a1->SavedEventTimestamp.QuadPart = MEMORY[0xFFFFF78000000014];
    if ( (a1->DeviceInfo.flags & 0x18) != 0 && (a1->DeviceInfo.flags & 0x4000) != 0 )
    {
      if ( a4 )
      {
        _MakeWithAddRef___RefObjReference_UDEVICE_INFO_BLOCK___0A__M__T0A__M__T0A___SA_AV1_PEAUDEVICE_INFO_BLOCK__PEBX_Z(
          SystemTime,
          a1,
          HCI_DibNotifyDeviceEnumerator);
        v28 = *(_OWORD *)&SystemTime[0].LowPart;
        Hci = a1->Hci;
        SystemTime[1].QuadPart = 0;
        SystemTime[0].QuadPart = 0;
        v35[0] = v28;
        v30 = ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_((__int64)Hci->DevExt, v35);
        if ( v30 < 0 )
        {
          LOBYTE(v31) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          LOBYTE(v32) = 1;
          WPP_RECORDER_AND_TRACE_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            v31,
            v32,
            a1->IfrLog,
            2,
            2,
            118,
            (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
            v30);
        }
        _Reset___RefObjReference_UREAD_CONNECTED_RSSI_CONTEXT___0A__M__T0A__M__T0A___QEAAXPEAUREAD_CONNECTED_RSSI_CONTEXT__PEBX_Z(SystemTime);
      }
      else if ( KeGetCurrentIrql() <= 1u )
      {
        HCI_DibNotifyDeviceEnumerator(ENUMERATOR_ACTION_CREATE, a1);
      }
    }
    IoReportTargetDeviceChangeAsynchronous(a1->Hci->BtDevice->PhysicalDeviceObject, v12, 0, 0);
  }
LABEL_53:
  utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(&v34);
}

```

## disassembly

```asm
0x14005ad28  push    rbp
0x14005ad2a  push    rbx
0x14005ad2b  push    rsi
0x14005ad2c  push    rdi
0x14005ad2d  push    r12
0x14005ad2f  push    r13
0x14005ad31  push    r14
0x14005ad33  push    r15
0x14005ad35  lea     rbp, [rsp-1Fh]
0x14005ad3a  sub     rsp, 88h
0x14005ad41  mov     al, r8b
0x14005ad44  mov     r15b, r8b
0x14005ad47  neg     al
0x14005ad49  mov     r12d, edx
0x14005ad4c  mov     rbx, rcx
0x14005ad4f  mov     r8d, 50485442h
0x14005ad55  sbb     rdi, rdi
0x14005ad58  mov     ecx, 40h ; '@'
0x14005ad5d  and     edi, 108h
0x14005ad63  mov     r13b, r9b
0x14005ad66  lea     rdx, [rdi+38h]
0x14005ad6a  call    cs:__imp_ExAllocatePool2
0x14005ad71  nop     dword ptr [rax+rax+00h]
0x14005ad76  mov     r14, rax
0x14005ad79  test    rax, rax
0x14005ad7c  jz      loc_14005B254
0x14005ad82  lea     r8, [rdi+38h]; Size
0x14005ad86  xor     edx, edx; Val
0x14005ad88  mov     rcx, rax; void *
0x14005ad8b  call    memset
0x14005ad90  mov     [rbp+57h+var_60], r14
0x14005ad94  mov     esi, 1
0x14005ad99  mov     [r14], si
0x14005ad9d  lea     rdi, [r14+24h]
0x14005ada1  mov     dword ptr [r14+20h], 0FFFFFFFFh
0x14005ada9  mov     qword ptr [r14+18h], 0
0x14005adb1  test    r15b, r15b
0x14005adb4  jz      loc_14005B0AF
0x14005adba  movups  xmm0, xmmword ptr cs:GUID_BLUETOOTH_RADIO_IN_RANGE.Data1
0x14005adc1  mov     word ptr [r14+2], 13Fh
0x14005adc8  lea     rcx, [rbp+57h+var_50]
0x14005adcc  movdqu  xmmword ptr [r14+4], xmm0
0x14005add2  mov     [rdi+110h], r12d
0x14005add9  mov     rdx, [rbx+378h]
0x14005ade0  add     rdx, 7B0h
0x14005ade7  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005adec  mov     rax, [rbx+20h]
0x14005adf0  lea     r12d, [rsi+7Fh]
0x14005adf4  mov     [rdi+8], rax
0x14005adf8  mov     eax, [rbx+28h]
0x14005adfb  mov     [rdi+10h], eax
0x14005adfe  mov     r8d, [rbx+18h]
0x14005ae02  mov     [rdi], r8d
0x14005ae05  mov     r9d, [rbx+18h]
0x14005ae09  bt      r9d, 0Eh
0x14005ae0e  jnb     short loc_14005AE30
0x14005ae10  mov     rdx, [rbx+378h]
0x14005ae17  mov     ecx, [rdx+968h]
0x14005ae1d  sub     ecx, [rbx+360h]
0x14005ae23  cmp     ecx, [rdx+0BC8h]
0x14005ae29  ja      short loc_14005AE30
0x14005ae2b  or      r8d, r12d
0x14005ae2e  jmp     short loc_14005AE90
0x14005ae30  bt      r9d, 0Fh
0x14005ae35  jnb     short loc_14005AE93
0x14005ae37  mov     qword ptr [rbp+57h+SystemTime], 0
0x14005ae3f  lea     rdx, [rbp+57h+SystemTime]; LocalTime
0x14005ae43  mov     rax, 0FFFFF78000000014h
0x14005ae4d  lea     rcx, [rbp+57h+SystemTime]; SystemTime
0x14005ae51  mov     rax, [rax]
0x14005ae54  mov     qword ptr [rbp+57h+SystemTime], rax
0x14005ae58  call    cs:__imp_ExSystemTimeToLocalTime
0x14005ae5f  nop     dword ptr [rax+rax+00h]
0x14005ae64  mov     rax, [rbx+378h]
0x14005ae6b  mov     rcx, qword ptr [rbp+57h+SystemTime]
0x14005ae6f  sub     rcx, [rbx+670h]
0x14005ae76  mov     r8d, [rdi]
0x14005ae79  cmp     rcx, [rax+0F40h]
0x14005ae80  jg      short loc_14005AE89
0x14005ae82  bts     r8d, 17h
0x14005ae87  jmp     short loc_14005AE90
0x14005ae89  and     r8d, 0FD7FFFFFh
0x14005ae90  mov     [rdi], r8d
0x14005ae93  cmp     byte ptr [rbx+158h], 0
0x14005ae9a  jz      loc_14005AF74
0x14005aea0  movups  xmm0, xmmword ptr [rbx+158h]
0x14005aea7  or      r8d, 4
0x14005aeab  movups  xmmword ptr [rdi+14h], xmm0
0x14005aeaf  movups  xmm1, xmmword ptr [rbx+168h]
0x14005aeb6  movups  xmmword ptr [rdi+24h], xmm1
0x14005aeba  movups  xmm0, xmmword ptr [rbx+178h]
0x14005aec1  movups  xmmword ptr [rdi+34h], xmm0
0x14005aec5  movups  xmm1, xmmword ptr [rbx+188h]
0x14005aecc  movups  xmmword ptr [rdi+44h], xmm1
0x14005aed0  movups  xmm0, xmmword ptr [rbx+198h]
0x14005aed7  movups  xmmword ptr [rdi+54h], xmm0
0x14005aedb  movups  xmm1, xmmword ptr [rbx+1A8h]
0x14005aee2  movups  xmmword ptr [rdi+64h], xmm1
0x14005aee6  movups  xmm0, xmmword ptr [rbx+1B8h]
0x14005aeed  movups  xmmword ptr [rdi+74h], xmm0
0x14005aef1  movups  xmm1, xmmword ptr [rbx+1C8h]
0x14005aef8  movups  xmmword ptr [rdi+84h], xmm1
0x14005aeff  movups  xmm0, xmmword ptr [rbx+1D8h]
0x14005af06  movups  xmmword ptr [rdi+94h], xmm0
0x14005af0d  movups  xmm1, xmmword ptr [rbx+1E8h]
0x14005af14  movups  xmmword ptr [rdi+0A4h], xmm1
0x14005af1b  movups  xmm0, xmmword ptr [rbx+1F8h]
0x14005af22  movups  xmmword ptr [rdi+0B4h], xmm0
0x14005af29  movups  xmm1, xmmword ptr [rbx+208h]
0x14005af30  movups  xmmword ptr [rdi+0C4h], xmm1
0x14005af37  movups  xmm0, xmmword ptr [rbx+218h]
0x14005af3e  movups  xmmword ptr [rdi+0D4h], xmm0
0x14005af45  movups  xmm1, xmmword ptr [rbx+228h]
0x14005af4c  movups  xmmword ptr [rdi+0E4h], xmm1
0x14005af53  movups  xmm0, xmmword ptr [rbx+238h]
0x14005af5a  movups  xmmword ptr [rdi+0F4h], xmm0
0x14005af61  mov     rax, [rbx+248h]
0x14005af68  mov     [rdi+104h], rax
0x14005af6f  mov     [rdi], r8d
0x14005af72  jmp     short loc_14005AFCC
0x14005af74  mov     eax, [rbx+18h]
0x14005af77  test    al, 4
0x14005af79  jz      short loc_14005AFA8
0x14005af7b  movzx   eax, byte ptr [rbx+5B5h]
0x14005af82  test    al, al
0x14005af84  jz      short loc_14005AFA8
0x14005af86  mov     r8d, eax; Size
0x14005af89  lea     rdx, [rbx+2Ch]; Src
0x14005af8d  lea     rcx, [rdi+14h]; void *
0x14005af91  call    memmove
0x14005af96  movzx   eax, byte ptr [rbx+5B5h]
0x14005af9d  mov     ecx, 0F8h
0x14005afa2  sub     ecx, eax
0x14005afa4  jz      short loc_14005AFCC
0x14005afa6  jmp     short loc_14005AFB5
0x14005afa8  mov     rax, [rbx+2Ch]
0x14005afac  mov     ecx, 0F0h
0x14005afb1  mov     [rdi+14h], rax
0x14005afb5  mov     r8d, ecx; Size
0x14005afb8  xor     edx, edx; Val
0x14005afba  mov     rcx, rdi
0x14005afbd  sub     rcx, r8
0x14005afc0  add     rcx, 10Ch; void *
0x14005afc7  call    memset
0x14005afcc  cmp     byte ptr [rbx+3FDh], 0
0x14005afd3  jnz     short loc_14005B02E
0x14005afd5  mov     r15d, 118h
0x14005afdb  lea     rcx, [rbx+400h]; Source1
0x14005afe2  mov     r8d, r15d; Length
0x14005afe5  mov     rdx, rdi; Source2
0x14005afe8  call    cs:__imp_RtlCompareMemory
0x14005afef  nop     dword ptr [rax+rax+00h]
0x14005aff4  cmp     rax, r15
0x14005aff7  jnz     short loc_14005B02E
0x14005aff9  mov     rax, [rbx+378h]
0x14005b000  lea     rdx, [rbx+124h]
0x14005b007  mov     r9d, [rdx]
0x14005b00a  mov     ecx, [rbx+518h]
0x14005b010  mov     r8d, [rax+0F38h]
0x14005b017  mov     eax, r9d
0x14005b01a  sub     eax, ecx
0x14005b01c  cmp     eax, r8d
0x14005b01f  jge     short loc_14005B02E
0x14005b021  sub     ecx, r9d
0x14005b024  cmp     ecx, r8d
0x14005b027  jge     short loc_14005B02E
0x14005b029  xor     r15b, r15b
0x14005b02c  jmp     short loc_14005B0A5
0x14005b02e  mov     r15b, sil
0x14005b031  mov     byte ptr [rbx+3FDh], 0
0x14005b038  lea     rcx, [rbx+400h]
0x14005b03f  mov     rax, rdi
0x14005b042  mov     edx, 2
0x14005b047  movups  xmm0, xmmword ptr [rax]
0x14005b04a  movups  xmmword ptr [rcx], xmm0
0x14005b04d  movups  xmm1, xmmword ptr [rax+10h]
0x14005b051  movups  xmmword ptr [rcx+10h], xmm1
0x14005b055  movups  xmm0, xmmword ptr [rax+20h]
0x14005b059  movups  xmmword ptr [rcx+20h], xmm0
0x14005b05d  movups  xmm1, xmmword ptr [rax+30h]
0x14005b061  movups  xmmword ptr [rcx+30h], xmm1
0x14005b065  movups  xmm0, xmmword ptr [rax+40h]
0x14005b069  movups  xmmword ptr [rcx+40h], xmm0
0x14005b06d  movups  xmm1, xmmword ptr [rax+50h]
0x14005b071  movups  xmmword ptr [rcx+50h], xmm1
0x14005b075  movups  xmm0, xmmword ptr [rax+60h]
0x14005b079  movups  xmmword ptr [rcx+60h], xmm0
0x14005b07d  movups  xmm1, xmmword ptr [rax+70h]
0x14005b081  add     rax, r12
0x14005b084  movups  xmmword ptr [rcx+70h], xmm1
0x14005b088  add     rcx, r12
0x14005b08b  sub     rdx, rsi
0x14005b08e  jnz     short loc_14005B047
0x14005b090  movups  xmm0, xmmword ptr [rax]
0x14005b093  lea     rdx, [rbx+124h]
0x14005b09a  movups  xmmword ptr [rcx], xmm0
0x14005b09d  mov     rax, [rax+10h]
0x14005b0a1  mov     [rcx+10h], rax
0x14005b0a5  mov     eax, [rdx]
0x14005b0a7  mov     [rdi+10Ch], eax
0x14005b0ad  jmp     short loc_14005B109
0x14005b0af  movups  xmm0, xmmword ptr cs:GUID_BLUETOOTH_RADIO_OUT_OF_RANGE.Data1
0x14005b0b6  mov     word ptr [r14+2], 37h ; '7'
0x14005b0bd  movdqu  xmmword ptr [r14+4], xmm0
0x14005b0c3  mov     rax, [rbx+20h]
0x14005b0c7  mov     [rdi], rax
0x14005b0ca  test    dword ptr [rbx+18h], 8000h
0x14005b0d1  jz      short loc_14005B0E3
0x14005b0d3  movzx   eax, byte ptr [rbx+5B0h]
0x14005b0da  xor     ecx, ecx
0x14005b0dc  cmp     al, 0FFh
0x14005b0de  cmovnz  ecx, eax
0x14005b0e1  jmp     short loc_14005B0E5
0x14005b0e3  mov     cl, 0FFh
0x14005b0e5  mov     [rdi+8], cl
0x14005b0e8  lea     rcx, [rbp+57h+var_50]
0x14005b0ec  mov     rdx, [rbx+378h]
0x14005b0f3  add     rdx, 7B0h
0x14005b0fa  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005b0ff  mov     [rbx+3FDh], sil
0x14005b106  mov     r15b, sil
0x14005b109  lea     rcx, [rbp+57h+var_50]
0x14005b10d  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005b112  mov     rax, 0FFFFF78000000014h
0x14005b11c  mov     rax, [rax]
0x14005b11f  test    r15b, r15b
0x14005b122  jnz     short loc_14005B142
0x14005b124  mov     rcx, [rbx+378h]
0x14005b12b  mov     rdx, rax
0x14005b12e  sub     rdx, [rbx+520h]
0x14005b135  cmp     rdx, [rcx+0F30h]
0x14005b13c  jl      loc_14005B2AF
0x14005b142  mov     [rbx+520h], rax
0x14005b149  mov     eax, [rbx+18h]
0x14005b14c  test    al, 18h
0x14005b14e  setnz   cl
0x14005b151  bt      eax, 0Eh
0x14005b155  setb    al
0x14005b158  test    al, cl
0x14005b15a  jz      loc_14005B22B
0x14005b160  test    r13b, r13b
0x14005b163  jz      loc_14005B210
0x14005b169  lea     r8, ?HCI_DibNotifyDeviceEnumerator@@YAXW4_ENUMERATOR_ACTION@@PEAUDEVICE_INFO_BLOCK@@@Z; HCI_DibNotifyDeviceEnumerator(_ENUMERATOR_ACTION,DEVICE_INFO_BLOCK *)
0x14005b170  mov     rdx, rbx
0x14005b173  lea     rcx, [rbp+57h+SystemTime]
0x14005b177  call    ?MakeWithAddRef@?$RefObjReference@UDEVICE_INFO_BLOCK@@$0A@$M$$T0A@$M$$T0A@@@SA?AV1@PEAUDEVICE_INFO_BLOCK@@PEBX@Z
0x14005b17c  movaps  xmm0, xmmword ptr [rbp+57h+SystemTime]
0x14005b180  lea     rdx, [rbp+57h+var_50]
0x14005b184  mov     rcx, [rbx+378h]
0x14005b18b  mov     qword ptr [rbp+57h+SystemTime+8], 0
0x14005b193  mov     qword ptr [rbp+57h+SystemTime], 0
0x14005b19b  movdqa  [rbp+57h+var_50], xmm0
0x14005b1a0  mov     rcx, [rcx+4A8h]
0x14005b1a7  call    ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9___; ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_
0x14005b1ac  test    eax, eax
0x14005b1ae  jns     short loc_14005B205
0x14005b1b0  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b1b7  mov     ecx, [r10+2Ch]
0x14005b1bb  test    cl, 2
0x14005b1be  jz      short loc_14005B1CC
0x14005b1c0  cmp     byte ptr [r10+29h], 2
0x14005b1c5  jb      short loc_14005B1CC
0x14005b1c7  mov     dl, sil
0x14005b1ca  jmp     short loc_14005B1CE
0x14005b1cc  xor     dl, dl
0x14005b1ce  mov     r9, [rbx+838h]
0x14005b1d5  mov     r8b, sil
0x14005b1d8  mov     rcx, [r10+18h]
0x14005b1dc  mov     [rsp+0C0h+var_80], eax
0x14005b1e0  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x14005b1e7  mov     [rsp+0C0h+var_88], rax
0x14005b1ec  mov     [rsp+0C0h+var_90], 76h ; 'v'
0x14005b1f3  mov     [rsp+0C0h+var_98], 2
0x14005b1fb  mov     [rsp+0C0h+var_A0], 2
0x14005b200  call    WPP_RECORDER_AND_TRACE_SF_d
0x14005b205  lea     rcx, [rbp+57h+SystemTime]
0x14005b209  call    ?Reset@?$RefObjReference@UREAD_CONNECTED_RSSI_CONTEXT@@$0A@$M$$T0A@$M$$T0A@@@QEAAXPEAUREAD_CONNECTED_RSSI_CONTEXT@@PEBX@Z
0x14005b20e  jmp     short loc_14005B22B
0x14005b210  call    cs:__imp_KeGetCurrentIrql
0x14005b217  nop     dword ptr [rax+rax+00h]
0x14005b21c  cmp     al, sil
0x14005b21f  ja      short loc_14005B22B
0x14005b221  mov     rdx, rbx; struct DEVICE_INFO_BLOCK *
0x14005b224  xor     ecx, ecx; enum _ENUMERATOR_ACTION
0x14005b226  call    ?HCI_DibNotifyDeviceEnumerator@@YAXW4_ENUMERATOR_ACTION@@PEAUDEVICE_INFO_BLOCK@@@Z; HCI_DibNotifyDeviceEnumerator(_ENUMERATOR_ACTION,DEVICE_INFO_BLOCK *)
0x14005b22b  mov     rax, [rbx+378h]
0x14005b232  xor     r9d, r9d; Context
0x14005b235  xor     r8d, r8d; Callback
0x14005b238  mov     rdx, r14; NotificationStructure
0x14005b23b  mov     rcx, [rax+4B0h]
0x14005b242  mov     rcx, [rcx+10h]; PhysicalDeviceObject
0x14005b246  call    cs:__imp_IoReportTargetDeviceChangeAsynchronous
0x14005b24d  nop     dword ptr [rax+rax+00h]
0x14005b252  jmp     short loc_14005B2AF
0x14005b254  mov     [rbp+57h+var_60], 0
0x14005b25c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b263  mov     esi, 1
0x14005b268  mov     eax, [rcx+2Ch]
0x14005b26b  test    al, 2
0x14005b26d  jz      short loc_14005B27A
  ... truncated ...
```
