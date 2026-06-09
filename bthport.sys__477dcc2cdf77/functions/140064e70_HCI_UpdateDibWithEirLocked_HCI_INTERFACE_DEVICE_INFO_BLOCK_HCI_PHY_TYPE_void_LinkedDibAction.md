# HCI_UpdateDibWithEirLocked(HCI_INTERFACE *,DEVICE_INFO_BLOCK *,_HCI_PHY_TYPE,void *,LinkedDibAction *)

- ea: `0x140064e70`
- end: `0x1400654e5`
- name: `?HCI_UpdateDibWithEirLocked@@YAKPEAUHCI_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@W4_HCI_PHY_TYPE@@PEAXPEAW4LinkedDibAction@@@Z`
- size: `1653`
- prototype: `unsigned int(struct HCI_INTERFACE *, struct DEVICE_INFO_BLOCK *, enum _HCI_PHY_TYPE, void *, enum LinkedDibAction *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005608`
- `0x140005690`
- `0x1400594d8`
- `0x14005efc4`
- `0x14005f234`
- `0x14005fe30`
- `0x140064e70`
- `0x14015ce38`
- `0x140163120`
- `0x14016319c`
- `0x140165640`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14006522b`
- `ntoskrnl!RtlCompareMemory` at `0x14006522b`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x140064f6e`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x140064f6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400653f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400653f1`
- `ntoskrnl!ExAllocatePool2` at `0x1400650c9`
- `ntoskrnl!ExAllocatePool2` at `0x1400650c9`

## string_xrefs

- `0x140064efb`: `EIR should not be used to update a LE DIB`

## pseudocode

```c
__int64 __fastcall HCI_UpdateDibWithEirLocked(
        struct HCI_INTERFACE *a1,
        struct DEVICE_INFO_BLOCK *a2,
        enum _HCI_PHY_TYPE a3,
        char *a4,
        enum LinkedDibAction *a5)
{
  struct DEVICE_INFO_BLOCK *v6; // rbx
  char *v9; // r15
  int v10; // eax
  unsigned int v11; // esi
  int v12; // edx
  int v13; // r9d
  __int128 v14; // xmm0
  char v15; // r12
  __int128 v16; // xmm0
  int v17; // edx
  int v18; // r9d
  const void *Record; // r14
  size_t v20; // rdi
  char *Pool2; // rax
  int v22; // edx
  unsigned __int8 v23; // di
  int DeviceNameValid; // eax
  int v25; // edx
  int v26; // r8d
  unsigned __int8 v27; // r14
  unsigned int flags; // eax
  unsigned int v29; // eax
  struct DEVICE_INFO_BLOCK *LinkedDib; // rax
  struct DEVICE_INFO_BLOCK *v31; // rdx
  unsigned int v32; // eax
  Microsoft::Bluetooth::Foundation::intrusive_list_hook *p_DisposableListEntry; // rcx
  _LIST_ENTRY *Flink; // rax
  _LIST_ENTRY *Blink; // r8
  __int64 p_DisposableDeviceList; // rax
  _LIST_ENTRY *v37; // r8
  Microsoft::Bluetooth::Foundation::intrusive_list_hook *v38; // rcx
  Microsoft::Bluetooth::Foundation::intrusive_list_hook *v39; // rax
  _LIST_ENTRY *v40; // r8
  __int64 v41; // rax
  _LIST_ENTRY *v42; // rdx
  Microsoft::Bluetooth::Foundation::intrusive_list_hook *v43; // rax
  _LIST_ENTRY *v44; // rcx
  struct _LIST_ENTRY **p_Hci; // rcx
  _LIST_ENTRY *v46; // rdx
  HCI_INTERFACE *Hci; // rdx
  unsigned int NumberOfDisposableDevices; // eax
  struct DEVICE_INFO_BLOCK *v49; // rax
  Microsoft::Bluetooth::Foundation::intrusive_list_hook *v50; // rcx
  _LIST_ENTRY *v51; // rdx
  _LIST_ENTRY *v52; // r8
  HCI_INTERFACE *v53; // rcx
  unsigned int v54; // eax
  unsigned __int8 v55; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int8 v56; // [rsp+A8h] [rbp+58h] BYREF

  v56 = 0;
  v6 = a2;
  v55 = 0;
  if ( a5 )
    *(_DWORD *)a5 = 0;
  if ( a3 != HciPhyTypeLE )
  {
    a2->DeviceInfo.flags |= 0x100u;
    v9 = 0;
    a2->PageScanRepetitionMode = a4[6];
    a2->ClockOffset = *(_WORD *)(a4 + 11) | 0x8000;
    v10 = a4[13];
    a2->DeviceInfo.flags |= 0x1000u;
    a2->DeviceInfo.RSSI = v10;
    HCI_DibUpdateCod(a2, (unsigned __int8 *)a4 + 8);
    v6->DeviceInfo.flags |= 0x4000u;
    v6->LastSeenTimestamp.QuadPart = MEMORY[0xFFFFF78000000014];
    v11 = 20738;
    ExSystemTimeToLocalTime(&v6->LastSeenTimestamp, &v6->LastSeenTimestamp);
    if ( (int)EIR_Validate(a4 + 14) >= 0 && v55 )
    {
      v14 = *(_OWORD *)(a4 + 14);
      v55 = 9;
      *(_OWORD *)v6->EirRecordData = v14;
      v15 = 0;
      *(_OWORD *)&v6->EirRecordData[16] = *(_OWORD *)(a4 + 30);
      *(_OWORD *)&v6->EirRecordData[32] = *(_OWORD *)(a4 + 46);
      *(_OWORD *)&v6->EirRecordData[48] = *(_OWORD *)(a4 + 62);
      *(_OWORD *)&v6->EirRecordData[64] = *(_OWORD *)(a4 + 78);
      *(_OWORD *)&v6->EirRecordData[80] = *(_OWORD *)(a4 + 94);
      *(_OWORD *)&v6->EirRecordData[96] = *(_OWORD *)(a4 + 110);
      *(_OWORD *)&v6->EirRecordData[112] = *(_OWORD *)(a4 + 126);
      *(_OWORD *)&v6->EirRecordData[128] = *(_OWORD *)(a4 + 142);
      *(_OWORD *)&v6->EirRecordData[144] = *(_OWORD *)(a4 + 158);
      *(_OWORD *)&v6->EirRecordData[160] = *(_OWORD *)(a4 + 174);
      *(_OWORD *)&v6->EirRecordData[176] = *(_OWORD *)(a4 + 190);
      *(_OWORD *)&v6->EirRecordData[192] = *(_OWORD *)(a4 + 206);
      *(_OWORD *)&v6->EirRecordData[208] = *(_OWORD *)(a4 + 222);
      v16 = *(_OWORD *)(a4 + 238);
      v6->DeviceInfo.flags |= 0x2100u;
      *(_OWORD *)&v6->EirRecordData[224] = v16;
      Record = (const void *)EIR_GetRecord((int)v6 + 592, v12, (unsigned int)&v55, v13, (__int64)&v56);
      if ( !Record )
      {
        v55 = 8;
        Record = (const void *)EIR_GetRecord((int)v6 + 592, v17, (unsigned int)&v55, v18, (__int64)&v56);
        if ( !Record )
          goto LABEL_45;
        v15 = 1;
      }
      v20 = v56;
      if ( v56 || !v15 )
      {
        v55 = 0;
        Pool2 = (char *)ExAllocatePool2(64, (unsigned int)v56 + 1, 1346917442);
        v9 = Pool2;
        if ( !Pool2 )
        {
          LOBYTE(v22) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v22,
            1,
            v6->IfrLog,
            2,
            2,
            51,
            (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids);
          return v11;
        }
        if ( (_BYTE)v20 )
          memmove(Pool2, Record, v20);
        v9[v20] = 0;
        v23 = v20 + 1;
        DeviceNameValid = HCI_DibMakeDeviceNameValid(v9, v23, &v55);
        if ( DeviceNameValid < 0 )
        {
          LOBYTE(v25) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          LOBYTE(v26) = 1;
          WPP_RECORDER_AND_TRACE_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            v25,
            v26,
            v6->IfrLog,
            2,
            2,
            52,
            (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
            DeviceNameValid);
          goto LABEL_69;
        }
        v27 = v55 + 1;
        if ( (unsigned __int8)(v55 + 1) > v23 )
        {
          LOBYTE(v25) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v25,
            1,
            v6->IfrLog,
            2,
            2,
            53,
            (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids);
          goto LABEL_69;
        }
        if ( (v6->DeviceInfo.flags & 4) != 0
          && v15
          && (unsigned __int8)RtlCompareMemory(v9, v6->DeviceInfo.name, v27) == v27 - 1 )
        {
          v11 = 20742;
          if ( (v6->DeviceInfo.flags & 0x40) == 0 )
            goto LABEL_45;
          goto LABEL_44;
        }
        v6->DeviceInfo.flags &= 0xFFFFFFBB;
        v6->DeviceInfo.name[0] = 0;
        HCI_DibUpdateName(v6, v9, v27);
        flags = v6->DeviceInfo.flags;
        if ( (flags & 4) != 0 )
        {
          v11 = 20742;
          if ( v15 )
          {
            v6->DeviceInfo.flags = flags | 0x40;
LABEL_44:
            v11 = 20806;
          }
        }
      }
    }
LABEL_45:
    if ( !a1->CacheEntryDisposableLimit )
      goto LABEL_68;
    v29 = v6->DeviceInfo.flags;
    if ( ((v29 & 0x4000) == 0 || v6->LinkedDibAddress)
      && (v29 & 0x1030038) == 0
      && (v6->DibFlags._MyVal & 8) == 0
      && v6->ListEntry.Flink != &v6->ListEntry )
    {
      LinkedDib = HCI_FindLinkedDib(&v6->Hci->DeviceList, v6);
      v31 = LinkedDib;
      if ( !LinkedDib
        || ((v32 = LinkedDib->DeviceInfo.flags, (v32 & 0x4000) == 0) || v31->LinkedDibAddress)
        && (v32 & 0x1030038) == 0
        && (v31->DibFlags._MyVal & 8) == 0 )
      {
        p_DisposableListEntry = &v6->DisposableListEntry;
        Flink = v6->DisposableListEntry.Flink;
        if ( Flink == &v6->DisposableListEntry )
        {
          ++v6->Hci->NumberOfDisposableDevices;
        }
        else
        {
          if ( Flink->Blink != p_DisposableListEntry )
            goto LABEL_83;
          Blink = v6->DisposableListEntry.Blink;
          if ( Blink->Flink != p_DisposableListEntry )
            goto LABEL_83;
          Blink->Flink = Flink;
          Flink->Blink = Blink;
          v6->DisposableListEntry.Blink = &v6->DisposableListEntry;
          p_DisposableListEntry->Flink = p_DisposableListEntry;
        }
        p_DisposableDeviceList = (__int64)&v6->Hci->DisposableDeviceList;
        v37 = *(_LIST_ENTRY **)p_DisposableDeviceList;
        if ( *(_QWORD *)(*(_QWORD *)p_DisposableDeviceList + 8LL) != p_DisposableDeviceList )
          goto LABEL_83;
        p_DisposableListEntry->Flink = v37;
        v6->DisposableListEntry.Blink = (_LIST_ENTRY *)p_DisposableDeviceList;
        v37->Blink = p_DisposableListEntry;
        *(_QWORD *)p_DisposableDeviceList = p_DisposableListEntry;
        if ( !v31 )
          goto LABEL_68;
      }
      v38 = &v31->DisposableListEntry;
      v39 = (Microsoft::Bluetooth::Foundation::intrusive_list_hook *)v31->DisposableListEntry.Flink;
      if ( v39 == &v31->DisposableListEntry )
        goto LABEL_68;
      if ( v39->Blink == v38 )
      {
        v40 = v31->DisposableListEntry.Blink;
        if ( v40->Flink == v38 )
        {
          v40->Flink = v39;
          v39->Blink = v40;
          v31->DisposableListEntry.Blink = &v31->DisposableListEntry;
          v38->Flink = v38;
          v41 = (__int64)&v31->Hci->DisposableDeviceList;
          v42 = *(_LIST_ENTRY **)v41;
          if ( *(_QWORD *)(*(_QWORD *)v41 + 8LL) == v41 )
          {
            v38->Flink = v42;
            v38->Blink = (_LIST_ENTRY *)v41;
            v42->Blink = v38;
            *(_QWORD *)v41 = v38;
            goto LABEL_68;
          }
        }
      }
LABEL_83:
      __fastfail(3u);
    }
    v43 = &v6->DisposableListEntry;
    v44 = v6->DisposableListEntry.Flink;
    if ( v44 == &v6->DisposableListEntry )
    {
      p_Hci = (struct _LIST_ENTRY **)&v6->Hci;
    }
    else
    {
      if ( v44->Blink != v43 )
        goto LABEL_83;
      v46 = v6->DisposableListEntry.Blink;
      if ( v46->Flink != v43 )
        goto LABEL_83;
      v46->Flink = v44;
      v44->Blink = v46;
      p_Hci = (struct _LIST_ENTRY **)&v6->Hci;
      v6->DisposableListEntry.Blink = &v6->DisposableListEntry;
      v43->Flink = v43;
      Hci = v6->Hci;
      NumberOfDisposableDevices = Hci->NumberOfDisposableDevices;
      if ( NumberOfDisposableDevices )
        Hci->NumberOfDisposableDevices = NumberOfDisposableDevices - 1;
    }
    v49 = HCI_FindLinkedDib(*p_Hci + 129, v6);
    if ( v49 )
    {
      v50 = &v49->DisposableListEntry;
      v51 = v49->DisposableListEntry.Flink;
      if ( v51 != &v49->DisposableListEntry )
      {
        if ( v51->Blink != v50 )
          goto LABEL_83;
        v52 = v49->DisposableListEntry.Blink;
        if ( v52->Flink != v50 )
          goto LABEL_83;
        v52->Flink = v51;
        v51->Blink = v52;
        v49->DisposableListEntry.Blink = &v49->DisposableListEntry;
        v50->Flink = v50;
        v53 = v49->Hci;
        v54 = v53->NumberOfDisposableDevices;
        if ( v54 )
          v53->NumberOfDisposableDevices = v54 - 1;
      }
    }
LABEL_68:
    if ( !v9 )
      return v11;
LABEL_69:
    ExFreePoolWithTag(v9, 0);
    return v11;
  }
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    1,
    a1->IfrLog,
    2,
    2,
    50,
    (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids);
  MicrosoftTelemetryAssertTriggeredMsgKM("EIR should not be used to update a LE DIB");
  return 0;
}

```

## disassembly

```asm
0x140064e70  mov     [rsp-38h+arg_0], rbx
0x140064e75  push    rbp
0x140064e76  push    rsi
0x140064e77  push    rdi
0x140064e78  push    r12
0x140064e7a  push    r13
0x140064e7c  push    r14
0x140064e7e  push    r15
0x140064e80  mov     rbp, rsp
0x140064e83  sub     rsp, 50h
0x140064e87  mov     rax, [rbp+arg_20]
0x140064e8b  mov     rdi, r9
0x140064e8e  mov     [rbp+arg_18], 0
0x140064e92  mov     rbx, rdx
0x140064e95  mov     [rbp+arg_10], 0
0x140064e99  mov     r13, rcx
0x140064e9c  test    rax, rax
0x140064e9f  jz      short loc_140064EA7
0x140064ea1  mov     dword ptr [rax], 0
0x140064ea7  cmp     r8b, 1
0x140064eab  jnz     short loc_140064F0E
0x140064ead  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140064eb4  mov     eax, [rcx+2Ch]
0x140064eb7  test    al, 2
0x140064eb9  jz      short loc_140064EC6
0x140064ebb  cmp     byte ptr [rcx+29h], 2
0x140064ebf  jb      short loc_140064EC6
0x140064ec1  mov     dl, r8b
0x140064ec4  jmp     short loc_140064EC8
0x140064ec6  xor     dl, dl
0x140064ec8  mov     r9, [r13+10B0h]
0x140064ecf  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140064ed6  mov     rcx, [rcx+18h]
0x140064eda  mov     r8b, 1
0x140064edd  mov     [rsp+50h+var_18], rax
0x140064ee2  mov     [rsp+50h+var_20], 32h ; '2'
0x140064ee9  mov     [rsp+50h+var_28], 2
0x140064ef1  mov     byte ptr [rsp+50h+var_30], 2
0x140064ef6  call    WPP_RECORDER_AND_TRACE_SF_
0x140064efb  lea     rcx, aEirShouldNotBe; __annotation("Debug", "TelemetryAssert", "false", "EIR should not be used to update a LE DIB")
0x140064f02  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140064f07  xor     eax, eax
0x140064f09  jmp     loc_1400653FF
0x140064f0e  bts     dword ptr [rdx+18h], 8
0x140064f13  mov     rcx, rbx; struct DEVICE_INFO_BLOCK *
0x140064f16  mov     al, [r9+6]
0x140064f1a  xor     r15d, r15d
0x140064f1d  mov     [rdx+5B2h], al
0x140064f23  mov     eax, 8000h
0x140064f28  or      ax, [r9+0Bh]
0x140064f2d  mov     [rdx+3CCh], ax
0x140064f34  movsx   eax, byte ptr [r9+0Dh]
0x140064f39  bts     dword ptr [rdx+18h], 0Ch
0x140064f3e  mov     [rdx+124h], eax
0x140064f44  lea     rdx, [r9+8]; unsigned __int8 *
0x140064f48  call    ?HCI_DibUpdateCod@@YAXPEAUDEVICE_INFO_BLOCK@@PEAE@Z; HCI_DibUpdateCod(DEVICE_INFO_BLOCK *,uchar *)
0x140064f4d  bts     dword ptr [rbx+18h], 0Eh
0x140064f52  lea     rcx, [rbx+670h]; SystemTime
0x140064f59  mov     rax, ds:0FFFFF78000000014h
0x140064f63  mov     rdx, rcx; LocalTime
0x140064f66  mov     [rcx], rax
0x140064f69  mov     esi, 5102h
0x140064f6e  call    cs:__imp_ExSystemTimeToLocalTime
0x140064f75  nop     dword ptr [rax+rax+00h]
0x140064f7a  lea     r14, [rdi+0Eh]
0x140064f7e  mov     rcx, r14
0x140064f81  lea     r8, [rbp+arg_10]
0x140064f85  call    EIR_Validate
0x140064f8a  test    eax, eax
0x140064f8c  js      loc_140065284
0x140064f92  cmp     [rbp+arg_10], r15b
0x140064f96  jbe     loc_140065284
0x140064f9c  movups  xmm0, xmmword ptr [r14]
0x140064fa0  lea     rdi, [rbx+250h]
0x140064fa7  mov     [rbp+arg_10], 9
0x140064fab  lea     rax, [rbp+arg_18]
0x140064faf  mov     rcx, rdi
0x140064fb2  movups  xmmword ptr [rdi], xmm0
0x140064fb5  lea     r8, [rbp+arg_10]
0x140064fb9  xor     r12b, r12b
0x140064fbc  movups  xmm1, xmmword ptr [r14+10h]
0x140064fc1  mov     [rsp+50h+var_30], rax
0x140064fc6  movups  xmmword ptr [rdi+10h], xmm1
0x140064fca  movups  xmm0, xmmword ptr [r14+20h]
0x140064fcf  movups  xmmword ptr [rdi+20h], xmm0
0x140064fd3  movups  xmm1, xmmword ptr [r14+30h]
0x140064fd8  movups  xmmword ptr [rdi+30h], xmm1
0x140064fdc  movups  xmm0, xmmword ptr [r14+40h]
0x140064fe1  movups  xmmword ptr [rdi+40h], xmm0
0x140064fe5  movups  xmm1, xmmword ptr [r14+50h]
0x140064fea  movups  xmmword ptr [rdi+50h], xmm1
0x140064fee  movups  xmm0, xmmword ptr [r14+60h]
0x140064ff3  movups  xmmword ptr [rdi+60h], xmm0
0x140064ff7  movups  xmm1, xmmword ptr [r14+70h]
0x140064ffc  movups  xmmword ptr [rdi+70h], xmm1
0x140065000  movups  xmm0, xmmword ptr [r14+80h]
0x140065008  movups  xmmword ptr [rdi+80h], xmm0
0x14006500f  movups  xmm1, xmmword ptr [r14+90h]
0x140065017  movups  xmmword ptr [rdi+90h], xmm1
0x14006501e  movups  xmm0, xmmword ptr [r14+0A0h]
0x140065026  movups  xmmword ptr [rdi+0A0h], xmm0
0x14006502d  movups  xmm1, xmmword ptr [r14+0B0h]
0x140065035  movups  xmmword ptr [rdi+0B0h], xmm1
0x14006503c  movups  xmm0, xmmword ptr [r14+0C0h]
0x140065044  movups  xmmword ptr [rdi+0C0h], xmm0
0x14006504b  movups  xmm1, xmmword ptr [r14+0D0h]
0x140065053  movups  xmmword ptr [rdi+0D0h], xmm1
0x14006505a  movups  xmm0, xmmword ptr [r14+0E0h]
0x140065062  or      dword ptr [rbx+18h], 2100h
0x140065069  movups  xmmword ptr [rdi+0E0h], xmm0
0x140065070  call    EIR_GetRecord
0x140065075  mov     r14, rax
0x140065078  test    rax, rax
0x14006507b  jnz     short loc_1400650A5
0x14006507d  lea     rax, [rbp+arg_18]
0x140065081  mov     [rbp+arg_10], 8
0x140065085  lea     r8, [rbp+arg_10]
0x140065089  mov     [rsp+50h+var_30], rax
0x14006508e  mov     rcx, rdi
0x140065091  call    EIR_GetRecord
0x140065096  mov     r14, rax
0x140065099  test    rax, rax
0x14006509c  jz      loc_140065284
0x1400650a2  mov     r12b, 1
0x1400650a5  movzx   edi, [rbp+arg_18]
0x1400650a9  test    dil, dil
0x1400650ac  jnz     short loc_1400650B7
0x1400650ae  test    r12b, r12b
0x1400650b1  jnz     loc_140065284
0x1400650b7  lea     edx, [rdi+1]
0x1400650ba  mov     [rbp+arg_10], r15b
0x1400650be  mov     ecx, 40h ; '@'
0x1400650c3  mov     r8d, 50485442h
0x1400650c9  call    cs:__imp_ExAllocatePool2
0x1400650d0  nop     dword ptr [rax+rax+00h]
0x1400650d5  mov     r15, rax
0x1400650d8  test    rax, rax
0x1400650db  jnz     short loc_14006512F
0x1400650dd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400650e4  mov     eax, [rcx+2Ch]
0x1400650e7  test    al, 2
0x1400650e9  jz      short loc_1400650F5
0x1400650eb  cmp     byte ptr [rcx+29h], 2
0x1400650ef  jb      short loc_1400650F5
0x1400650f1  mov     dl, 1
0x1400650f3  jmp     short loc_1400650F7
0x1400650f5  xor     dl, dl
0x1400650f7  mov     r9, [rbx+838h]
0x1400650fe  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140065105  mov     rcx, [rcx+18h]
0x140065109  mov     r8b, 1
0x14006510c  mov     [rsp+50h+var_18], rax
0x140065111  mov     [rsp+50h+var_20], 33h ; '3'
0x140065118  mov     [rsp+50h+var_28], 2
0x140065120  mov     byte ptr [rsp+50h+var_30], 2
0x140065125  call    WPP_RECORDER_AND_TRACE_SF_
0x14006512a  jmp     loc_1400653FD
0x14006512f  test    dil, dil
0x140065132  jz      short loc_140065142
0x140065134  mov     r8, rdi; Size
0x140065137  mov     rdx, r14; Src
0x14006513a  mov     rcx, r15; void *
0x14006513d  call    memmove
0x140065142  mov     byte ptr [rdi+r15], 0
0x140065147  lea     r8, [rbp+arg_10]; unsigned __int8 *
0x14006514b  inc     dil
0x14006514e  mov     rcx, r15; char *
0x140065151  mov     dl, dil; unsigned __int8
0x140065154  call    ?HCI_DibMakeDeviceNameValid@@YAJPEADEPEAE@Z; HCI_DibMakeDeviceNameValid(char *,uchar,uchar *)
0x140065159  test    eax, eax
0x14006515b  jns     short loc_1400651B6
0x14006515d  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140065164  mov     ecx, [r10+2Ch]
0x140065168  test    cl, 2
0x14006516b  jz      short loc_140065178
0x14006516d  cmp     byte ptr [r10+29h], 2
0x140065172  jb      short loc_140065178
0x140065174  mov     dl, 1
0x140065176  jmp     short loc_14006517A
0x140065178  xor     dl, dl
0x14006517a  mov     r9, [rbx+838h]
0x140065181  mov     r8b, 1
0x140065184  mov     rcx, [r10+18h]
0x140065188  mov     [rsp+50h+var_10], eax
0x14006518c  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140065193  mov     [rsp+50h+var_18], rax
0x140065198  mov     [rsp+50h+var_20], 34h ; '4'
0x14006519f  mov     [rsp+50h+var_28], 2
0x1400651a7  mov     byte ptr [rsp+50h+var_30], 2
0x1400651ac  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400651b1  jmp     loc_1400653EC
0x1400651b6  mov     r14b, [rbp+arg_10]
0x1400651ba  inc     r14b
0x1400651bd  cmp     r14b, dil
0x1400651c0  jbe     short loc_140065214
0x1400651c2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400651c9  mov     eax, [rcx+2Ch]
0x1400651cc  test    al, 2
0x1400651ce  jz      short loc_1400651DA
0x1400651d0  cmp     byte ptr [rcx+29h], 2
0x1400651d4  jb      short loc_1400651DA
0x1400651d6  mov     dl, 1
0x1400651d8  jmp     short loc_1400651DC
0x1400651da  xor     dl, dl
0x1400651dc  mov     r9, [rbx+838h]
0x1400651e3  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400651ea  mov     rcx, [rcx+18h]
0x1400651ee  mov     r8b, 1
0x1400651f1  mov     [rsp+50h+var_18], rax
0x1400651f6  mov     [rsp+50h+var_20], 35h ; '5'
0x1400651fd  mov     [rsp+50h+var_28], 2
0x140065205  mov     byte ptr [rsp+50h+var_30], 2
0x14006520a  call    WPP_RECORDER_AND_TRACE_SF_
0x14006520f  jmp     loc_1400653EC
0x140065214  mov     eax, [rbx+18h]
0x140065217  test    al, 4
0x140065219  jz      short loc_140065252
0x14006521b  test    r12b, r12b
0x14006521e  jz      short loc_140065252
0x140065220  movzx   r8d, r14b; Length
0x140065224  lea     rdx, [rbx+2Ch]; Source2
0x140065228  mov     rcx, r15; Source1
0x14006522b  call    cs:__imp_RtlCompareMemory
0x140065232  nop     dword ptr [rax+rax+00h]
0x140065237  movzx   ecx, al
0x14006523a  movzx   eax, r14b
0x14006523e  dec     eax
0x140065240  cmp     ecx, eax
0x140065242  jnz     short loc_140065252
0x140065244  mov     eax, [rbx+18h]
0x140065247  mov     esi, 5106h
0x14006524c  test    al, 40h
0x14006524e  jz      short loc_140065284
0x140065250  jmp     short loc_14006527F
0x140065252  and     dword ptr [rbx+18h], 0FFFFFFBBh
0x140065256  mov     r8b, r14b; unsigned __int8
0x140065259  mov     rdx, r15; char *
0x14006525c  mov     byte ptr [rbx+2Ch], 0
0x140065260  mov     rcx, rbx; struct DEVICE_INFO_BLOCK *
0x140065263  call    ?HCI_DibUpdateName@@YAEPEAUDEVICE_INFO_BLOCK@@PEADE@Z; HCI_DibUpdateName(DEVICE_INFO_BLOCK *,char *,uchar)
0x140065268  mov     eax, [rbx+18h]
0x14006526b  test    al, 4
0x14006526d  jz      short loc_140065284
0x14006526f  mov     esi, 5106h
0x140065274  test    r12b, r12b
0x140065277  jz      short loc_140065284
0x140065279  or      eax, 40h
0x14006527c  mov     [rbx+18h], eax
0x14006527f  mov     esi, 5146h
0x140065284  cmp     dword ptr [r13+8ACh], 0
0x14006528c  jbe     loc_1400653E7
0x140065292  mov     eax, [rbx+18h]
0x140065295  bt      eax, 0Eh
0x140065299  jnb     short loc_1400652A9
0x14006529b  cmp     qword ptr [rbx+8E8h], 0
0x1400652a3  jz      loc_140065418
0x1400652a9  mov     edi, 1030038h
0x1400652ae  test    edi, eax
0x1400652b0  jnz     loc_140065418
0x1400652b6  mov     rax, [rbx+368h]
0x1400652bd  nop
0x1400652be  test    al, 8
0x1400652c0  jnz     loc_140065418
0x1400652c6  lea     rax, [rbx+340h]
0x1400652cd  cmp     [rax], rax
0x1400652d0  jz      loc_140065418
0x1400652d6  mov     rcx, [rbx+378h]
0x1400652dd  mov     rdx, rbx; struct DEVICE_INFO_BLOCK *
0x1400652e0  add     rcx, 810h; struct _LIST_ENTRY *
0x1400652e7  call    ?HCI_FindLinkedDib@@YAPEAUDEVICE_INFO_BLOCK@@PEAU_LIST_ENTRY@@PEAU1@@Z; HCI_FindLinkedDib(_LIST_ENTRY *,DEVICE_INFO_BLOCK *)
0x1400652ec  mov     rdx, rax
0x1400652ef  test    rax, rax
0x1400652f2  jz      short loc_14006531B
0x1400652f4  mov     eax, [rax+18h]
0x1400652f7  bt      eax, 0Eh
0x1400652fb  jnb     short loc_14006530B
0x1400652fd  cmp     qword ptr [rdx+8E8h], 0
0x140065305  jz      loc_14006538B
0x14006530b  test    edi, eax
0x14006530d  jnz     short loc_14006538B
0x14006530f  mov     rax, [rdx+368h]
0x140065316  nop
0x140065317  test    al, 8
0x140065319  jnz     short loc_14006538B
0x14006531b  lea     rcx, [rbx+350h]
0x140065322  mov     rax, [rcx]
0x140065325  cmp     rax, rcx
0x140065328  jnz     short loc_140065339
0x14006532a  mov     rax, [rbx+378h]
0x140065331  inc     dword ptr [rax+8C0h]
0x140065337  jmp     short loc_14006535E
0x140065339  cmp     [rax+8], rcx
0x14006533d  jnz     loc_1400654DE
0x140065343  mov     r8, [rcx+8]
0x140065347  cmp     [r8], rcx
0x14006534a  jnz     loc_1400654DE
0x140065350  mov     [r8], rax
0x140065353  mov     [rax+8], r8
0x140065357  mov     [rcx+8], rcx
0x14006535b  mov     [rcx], rcx
  ... truncated ...
```
