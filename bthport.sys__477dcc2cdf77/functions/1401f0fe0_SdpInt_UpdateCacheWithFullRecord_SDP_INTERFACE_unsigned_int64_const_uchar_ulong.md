# SdpInt_UpdateCacheWithFullRecord(_SDP_INTERFACE *,unsigned __int64 const *,uchar *,ulong)

- ea: `0x1401f0fe0`
- end: `0x1401f1643`
- name: `?SdpInt_UpdateCacheWithFullRecord@@YAJPEAU_SDP_INTERFACE@@PEB_KPEAEK@Z`
- size: `1635`
- prototype: `int(struct _SDP_INTERFACE *, const unsigned __int64 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1401ed59c`
- `0x1401f06f0`

## callees

- `0x140005690`
- `0x140005b4c`
- `0x140020414`
- `0x14005fc60`
- `0x140161d7c`
- `0x140165540`
- `0x1401c18d0`
- `0x1401f0fe0`
- `0x140209110`
- `0x14020a978`
- `0x14020b1b0`
- `0x14020bed0`
- `0x14020cf44`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f14d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f1502`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f14d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f1502`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f1243`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f1243`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401f132c`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401f132c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401f14ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401f14f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401f14ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401f14f6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401f1259`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401f1259`
- `ntoskrnl!ZwSetValueKey` at `0x1401f14a7`
- `ntoskrnl!ZwSetValueKey` at `0x1401f14a7`
- `ntoskrnl!ZwClose` at `0x1401f151e`
- `ntoskrnl!ZwClose` at `0x1401f1533`
- `ntoskrnl!ZwClose` at `0x1401f151e`
- `ntoskrnl!ZwClose` at `0x1401f1533`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f1392`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f1392`
- `ntoskrnl!ExAllocatePool2` at `0x1401f12bf`
- `ntoskrnl!ExAllocatePool2` at `0x1401f12bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401f1481`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401f1481`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1401f1289`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1401f12f3`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1401f1289`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1401f12f3`

## string_xrefs

- `0x1401f11ee`: `DynamicCachedServices`

## pseudocode

```c
__int64 __fastcall SdpInt_UpdateCacheWithFullRecord(
        struct _SDP_INTERFACE *a1,
        const unsigned __int64 *a2,
        unsigned __int8 *a3,
        int a4)
{
  struct DEVICE_INFO_BLOCK *v5; // r13
  unsigned __int8 *v6; // r14
  const unsigned __int64 *v7; // rsi
  char v9; // di
  __int16 DeviceType; // ax
  NTSTATUS DeviceKey; // ebx
  unsigned __int8 *v12; // r14
  int v13; // r12d
  __int64 v14; // r13
  struct DEVICE_INFO_BLOCK *DeviceInfoBlockByBaseband; // rax
  int v16; // edx
  int v17; // r8d
  int v18; // edx
  int v19; // r8d
  void *DeviceExtension; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  struct _ERESOURCE *p_SdpCacheRWLock; // r15
  NTSTATUS v23; // eax
  __int64 v24; // rdx
  int v25; // r8d
  unsigned __int16 *Pool2; // rax
  unsigned __int16 *v27; // rsi
  int v28; // edx
  int v29; // r8d
  unsigned __int8 *v30; // r14
  ULONG v31; // r12d
  ULONG v32; // esi
  __int16 v33; // ax
  __int16 v35; // [rsp+30h] [rbp-59h]
  char v36; // [rsp+40h] [rbp-49h]
  ULONG ResultLength; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v38; // [rsp+54h] [rbp-35h] BYREF
  int v39; // [rsp+58h] [rbp-31h] BYREF
  struct DEVICE_INFO_BLOCK *v40; // [rsp+60h] [rbp-29h]
  HANDLE KeyHandle; // [rsp+68h] [rbp-21h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+70h] [rbp-19h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-9h] BYREF
  WCHAR SourceString[12]; // [rsp+88h] [rbp-1h] BYREF

  v39 = 0;
  v5 = 0;
  v38 = 0;
  v6 = a3;
  v40 = 0;
  v7 = a2;
  Handle = 0;
  KeyHandle = 0;
  v9 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
  {
    LOBYTE(a3) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      8,
      44,
      (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
      *v7);
  }
  if ( !a4 || (LOBYTE(a2) = *v6, (*v6 & 0xF8) != 0x30) )
  {
    DeviceKey = -1073741811;
    goto LABEL_57;
  }
  v12 = v6 + 1;
  LOBYTE(a2) = (unsigned __int8)a2 & 7;
  v13 = a4 - 1;
  SdpRetrieveVariableSize(v12, a2, &v39, &v38);
  v14 = v38;
  if ( v38 <= a4 - 1 )
  {
    DeviceInfoBlockByBaseband = HCI_FindDeviceInfoBlockByBaseband(
                                  a1->DevExt->Hci,
                                  v7,
                                  HciPhyTypeBR,
                                  SdpInt_UpdateCacheWithFullRecord,
                                  0);
    v40 = DeviceInfoBlockByBaseband;
    if ( DeviceInfoBlockByBaseband )
    {
      DeviceKey = HCI_GetDeviceKey(&DeviceInfoBlockByBaseband->DeviceInfo.address, &Handle, 1u);
      if ( DeviceKey >= 0 )
      {
        DeviceKey = BthCreateKeySdEnforced(Handle, L"DynamicCachedServices", &KeyHandle);
        if ( DeviceKey >= 0 )
        {
          KeEnterCriticalRegion();
          p_SdpCacheRWLock = &a1->SdpCacheRWLock;
          ExAcquireResourceExclusiveLite(p_SdpCacheRWLock, 1u);
          do
          {
            ResultLength = 0;
            v23 = ZwEnumerateValueKey(KeyHandle, 0, KeyValueFullInformation, 0, 0, &ResultLength);
            DeviceKey = v23;
            if ( v23 >= 0 )
            {
              DeviceKey = -1073741823;
LABEL_72:
              LOBYTE(v24) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              LOBYTE(v25) = 1;
              WPP_RECORDER_AND_TRACE_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                v24,
                v25,
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                8,
                49,
                (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
                DeviceKey);
              goto LABEL_55;
            }
            if ( v23 != -1073741789 && v23 != -2147483643 )
              break;
            Pool2 = (unsigned __int16 *)ExAllocatePool2(256, ResultLength, 1346917442);
            v27 = Pool2;
            if ( !Pool2 )
            {
              DeviceKey = -1073741670;
              goto LABEL_72;
            }
            DeviceKey = ZwEnumerateValueKey(KeyHandle, 0, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
            if ( DeviceKey >= 0 )
            {
              ValueName.Length = v27[8];
              ValueName.MaximumLength = ValueName.Length;
              ValueName.Buffer = v27 + 10;
              *(_DWORD *)(&ValueName.MaximumLength + 1) = 0;
              DeviceKey = ZwDeleteValueKey(KeyHandle, &ValueName);
              if ( DeviceKey < 0 )
              {
                LOBYTE(v28) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                LOBYTE(v29) = 1;
                WPP_RECORDER_AND_TRACE_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v28,
                  v29,
                  WPP_GLOBAL_Control->DeviceExtension,
                  2,
                  8,
                  48,
                  (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
                  DeviceKey);
              }
            }
            ExFreePoolWithTag(v27, 0);
          }
          while ( DeviceKey >= 0 );
          if ( DeviceKey != -2147483622 )
            goto LABEL_72;
          DeviceKey = 0;
          v30 = &v12[v14];
          v31 = v13 - v14;
          if ( v31 )
          {
            while ( (*v30 & 0xF8) == 0x30 )
            {
              LOBYTE(v24) = *v30 & 7;
              SdpRetrieveVariableSize(v30 + 1, v24, &v39, &v38);
              v32 = v38 + v39 + 1;
              if ( v32 > v31 )
                break;
              if ( (int)SdpIsStreamRecord(v30, v32) < 0
                || (LOWORD(ResultLength) = 0, (int)SdpVerifyServiceRecord(v30, v32, 4, &ResultLength) < 0)
                || (*(_QWORD *)&ValueName.Length = 0,
                    (int)SdpFindAttributeInStream((_DWORD)v30, v32, 0, (unsigned int)&ValueName, (__int64)&ResultLength) < 0)
                || (DeviceKey = RtlStringCbPrintfW(
                                  SourceString,
                                  0x12u,
                                  L"%08x",
                                  _byteswap_ulong(*(_DWORD *)(*(_QWORD *)&ValueName.Length + 1LL))),
                    DeviceKey >= 0)
                && (ValueName = 0,
                    RtlInitUnicodeString(&ValueName, SourceString),
                    DeviceKey = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, v30, v32),
                    DeviceKey >= 0) )
              {
                v30 += v32;
                v31 -= v32;
                if ( v31 )
                  continue;
              }
              goto LABEL_55;
            }
            DeviceKey = -1073741811;
          }
LABEL_55:
          ExReleaseResourceLite(p_SdpCacheRWLock);
          KeLeaveCriticalRegion();
          goto LABEL_56;
        }
        LOBYTE(v18) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v36 = DeviceKey;
        v35 = 47;
      }
      else
      {
        LOBYTE(v18) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v36 = DeviceKey;
        v35 = 46;
      }
      LOBYTE(v19) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        (_DWORD)AttachedDevice,
        v18,
        v19,
        (_DWORD)DeviceExtension,
        2,
        8,
        v35,
        (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
        v36);
    }
    else
    {
      DeviceKey = 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v16) = 0;
      LOBYTE(v17) = 1;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v17,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        8,
        45,
        (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
        *v7);
    }
  }
  else
  {
    DeviceKey = -1073741811;
  }
LABEL_56:
  v5 = v40;
LABEL_57:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v5 )
    RefObj_ReleaseEx(
      v5,
      SdpInt_UpdateCacheWithFullRecord,
      2070,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\sdpinterface.cpp");
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v9 = 0;
  v33 = WPP_GLOBAL_Control->DeviceType;
  if ( v9 || v33 )
  {
    LOBYTE(a2) = v9;
    LOBYTE(a3) = v33 != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      8,
      50,
      (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
      DeviceKey);
  }
  return (unsigned int)DeviceKey;
}

```

## disassembly

```asm
0x1401f0fe0  mov     [rsp-8+arg_18], rbx
0x1401f0fe5  push    rbp
0x1401f0fe6  push    rsi
0x1401f0fe7  push    rdi
0x1401f0fe8  push    r12
0x1401f0fea  push    r13
0x1401f0fec  push    r14
0x1401f0fee  push    r15
0x1401f0ff0  lea     rbp, [rsp-27h]
0x1401f0ff5  sub     rsp, 0B0h
0x1401f0ffc  mov     rax, cs:__security_cookie
0x1401f1003  xor     rax, rsp
0x1401f1006  mov     [rbp+57h+var_40], rax
0x1401f100a  xor     r12d, r12d
0x1401f100d  mov     ebx, r9d
0x1401f1010  mov     [rbp+57h+var_88], r12d
0x1401f1014  mov     r13d, r12d
0x1401f1017  mov     [rbp+57h+var_8C], r12d
0x1401f101b  mov     r14, r8
0x1401f101e  mov     [rbp+57h+var_80], r12
0x1401f1022  mov     rsi, rdx
0x1401f1025  mov     [rbp+57h+Handle], r12
0x1401f1029  mov     r15, rcx
0x1401f102c  mov     [rbp+57h+KeyHandle], r12
0x1401f1030  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f1037  lea     edi, [r12+1]
0x1401f103c  mov     eax, [rcx+2Ch]
0x1401f103f  test    al, al
0x1401f1041  jns     short loc_1401F104C
0x1401f1043  cmp     byte ptr [rcx+29h], 5
0x1401f1047  mov     dl, dil
0x1401f104a  jnb     short loc_1401F104F
0x1401f104c  mov     dl, r12b
0x1401f104f  movzx   eax, word ptr [rcx+48h]
0x1401f1053  lea     r10, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f105a  test    ax, ax
0x1401f105d  setnz   r8b
0x1401f1061  test    dl, dl
0x1401f1063  jnz     short loc_1401F106A
0x1401f1065  test    ax, ax
0x1401f1068  jz      short loc_1401F1098
0x1401f106a  mov     rax, [rsi]
0x1401f106d  mov     r9, [rcx+40h]
0x1401f1071  mov     rcx, [rcx+18h]
0x1401f1075  mov     qword ptr [rsp+0E0h+var_A0], rax
0x1401f107a  mov     [rsp+0E0h+var_A8], r10
0x1401f107f  mov     [rsp+0E0h+var_B0], 2Ch ; ','
0x1401f1086  mov     dword ptr [rsp+0E0h+ResultLength], 8
0x1401f108e  mov     byte ptr [rsp+0E0h+Length], 5
0x1401f1093  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401f1098  test    ebx, ebx
0x1401f109a  jnz     short loc_1401F10AD
0x1401f109c  mov     ebx, 0C000000Dh
0x1401f10a1  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f10a8  jmp     loc_1401F1515
0x1401f10ad  mov     dl, [r14]
0x1401f10b0  mov     al, dl
0x1401f10b2  and     al, 0F8h
0x1401f10b4  cmp     al, 30h ; '0'
0x1401f10b6  jnz     short loc_1401F109C
0x1401f10b8  inc     r14
0x1401f10bb  lea     r9, [rbp+57h+var_8C]
0x1401f10bf  mov     rcx, r14
0x1401f10c2  lea     r8, [rbp+57h+var_88]
0x1401f10c6  and     dl, 7
0x1401f10c9  lea     r12d, [rbx-1]
0x1401f10cd  call    SdpRetrieveVariableSize
0x1401f10d2  mov     r13d, [rbp+57h+var_8C]
0x1401f10d6  cmp     r13d, r12d
0x1401f10d9  jbe     short loc_1401F10EC
0x1401f10db  mov     ebx, 0C000000Dh
0x1401f10e0  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f10e7  jmp     loc_1401F150E
0x1401f10ec  mov     rcx, [r15]
0x1401f10ef  lea     r9, ?SdpInt_UpdateCacheWithFullRecord@@YAJPEAU_SDP_INTERFACE@@PEB_KPEAEK@Z; void *
0x1401f10f6  xor     r8d, r8d; enum _HCI_PHY_TYPE
0x1401f10f9  mov     byte ptr [rsp+0E0h+Length], 0; bool
0x1401f10fe  mov     rdx, rsi; unsigned __int64 *
0x1401f1101  mov     rcx, [rcx+170h]; struct HCI_INTERFACE *
0x1401f1108  call    ?HCI_FindDeviceInfoBlockByBaseband@@YAPEAUDEVICE_INFO_BLOCK@@PEAUHCI_INTERFACE@@PEB_KW4_HCI_PHY_TYPE@@PEAX_N@Z; HCI_FindDeviceInfoBlockByBaseband(HCI_INTERFACE *,unsigned __int64 const *,_HCI_PHY_TYPE,void *,bool)
0x1401f110d  mov     [rbp+57h+var_80], rax
0x1401f1111  test    rax, rax
0x1401f1114  jnz     short loc_1401F1175
0x1401f1116  xor     r12d, r12d
0x1401f1119  mov     ebx, r12d
0x1401f111c  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f1123  mov     ecx, [r10+2Ch]
0x1401f1127  test    cl, cl
0x1401f1129  jns     short loc_1401F1135
0x1401f112b  cmp     byte ptr [r10+29h], 2
0x1401f1130  mov     dl, dil
0x1401f1133  jnb     short loc_1401F1138
0x1401f1135  mov     dl, r12b
0x1401f1138  mov     rax, [rsi]
0x1401f113b  mov     r8b, dil
0x1401f113e  mov     r9, [r10+40h]
0x1401f1142  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f1149  mov     rcx, [r10+18h]
0x1401f114d  mov     qword ptr [rsp+0E0h+var_A0], rax
0x1401f1152  mov     [rsp+0E0h+var_A8], rsi
0x1401f1157  mov     [rsp+0E0h+var_B0], 2Dh ; '-'
0x1401f115e  mov     dword ptr [rsp+0E0h+ResultLength], 8
0x1401f1166  mov     byte ptr [rsp+0E0h+Length], 2
0x1401f116b  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401f1170  jmp     loc_1401F1511
0x1401f1175  lea     rcx, [rax+20h]; unsigned __int64 *
0x1401f1179  mov     r8b, dil; unsigned __int8
0x1401f117c  lea     rdx, [rbp+57h+Handle]; void **
0x1401f1180  call    ?HCI_GetDeviceKey@@YAJPEB_KPEAPEAXE@Z; HCI_GetDeviceKey(unsigned __int64 const *,void * *,uchar)
0x1401f1185  mov     ebx, eax
0x1401f1187  test    eax, eax
0x1401f1189  jns     short loc_1401F11E6
0x1401f118b  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f1192  mov     ecx, [rax+2Ch]
0x1401f1195  test    cl, cl
0x1401f1197  jns     short loc_1401F11A7
0x1401f1199  cmp     byte ptr [rax+29h], 2
0x1401f119d  jb      short loc_1401F11A7
0x1401f119f  mov     dl, dil
0x1401f11a2  xor     r12d, r12d
0x1401f11a5  jmp     short loc_1401F11AD
0x1401f11a7  xor     r12d, r12d
0x1401f11aa  mov     dl, r12b
0x1401f11ad  mov     r9, [rax+40h]
0x1401f11b1  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f11b8  mov     rcx, [rax+18h]
0x1401f11bc  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x1401f11c0  mov     [rsp+0E0h+var_A8], rsi
0x1401f11c5  mov     [rsp+0E0h+var_B0], 2Eh ; '.'
0x1401f11cc  mov     dword ptr [rsp+0E0h+ResultLength], 8
0x1401f11d4  mov     r8b, dil
0x1401f11d7  mov     byte ptr [rsp+0E0h+Length], 2
0x1401f11dc  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401f11e1  jmp     loc_1401F1511
0x1401f11e6  mov     rcx, [rbp+57h+Handle]
0x1401f11ea  lea     r8, [rbp+57h+KeyHandle]
0x1401f11ee  lea     rdx, aDynamiccacheds; "DynamicCachedServices"
0x1401f11f5  call    BthCreateKeySdEnforced
0x1401f11fa  mov     ebx, eax
0x1401f11fc  test    eax, eax
0x1401f11fe  jns     short loc_1401F1243
0x1401f1200  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f1207  mov     eax, [rcx+2Ch]
0x1401f120a  test    al, al
0x1401f120c  jns     short loc_1401F121C
0x1401f120e  cmp     byte ptr [rcx+29h], 2
0x1401f1212  jb      short loc_1401F121C
0x1401f1214  mov     dl, dil
0x1401f1217  xor     r12d, r12d
0x1401f121a  jmp     short loc_1401F1222
0x1401f121c  xor     r12d, r12d
0x1401f121f  mov     dl, r12b
0x1401f1222  mov     r9, [rcx+40h]
0x1401f1226  lea     rsi, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f122d  mov     rcx, [rcx+18h]
0x1401f1231  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x1401f1235  mov     [rsp+0E0h+var_A8], rsi
0x1401f123a  mov     [rsp+0E0h+var_B0], 2Fh ; '/'
0x1401f1241  jmp     short loc_1401F11CC
0x1401f1243  call    cs:__imp_KeEnterCriticalRegion
0x1401f124a  nop     dword ptr [rax+rax+00h]
0x1401f124f  add     r15, 40h ; '@'
0x1401f1253  mov     dl, dil; Wait
0x1401f1256  mov     rcx, r15; Resource
0x1401f1259  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401f1260  nop     dword ptr [rax+rax+00h]
0x1401f1265  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401f1269  lea     rax, [rbp+57h+var_90]
0x1401f126d  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1401f1272  xor     r9d, r9d; KeyValueInformation
0x1401f1275  mov     r8d, edi; KeyValueInformationClass
0x1401f1278  mov     [rsp+0E0h+Length], 0; Length
0x1401f1280  xor     edx, edx; Index
0x1401f1282  mov     [rbp+57h+var_90], 0
0x1401f1289  call    cs:__imp_ZwEnumerateValueKey
0x1401f1290  nop     dword ptr [rax+rax+00h]
0x1401f1295  mov     ebx, eax
0x1401f1297  test    eax, eax
0x1401f1299  jns     loc_1401F15EA
0x1401f129f  cmp     eax, 0C0000023h
0x1401f12a4  jz      short loc_1401F12B1
0x1401f12a6  cmp     eax, 80000005h
0x1401f12ab  jnz     loc_1401F13A6
0x1401f12b1  mov     edx, [rbp+57h+var_90]
0x1401f12b4  mov     ecx, 100h
0x1401f12b9  mov     r8d, 50485442h
0x1401f12bf  call    cs:__imp_ExAllocatePool2
0x1401f12c6  nop     dword ptr [rax+rax+00h]
0x1401f12cb  mov     rsi, rax
0x1401f12ce  test    rax, rax
0x1401f12d1  jz      loc_1401F15E3
0x1401f12d7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401f12db  lea     rax, [rbp+57h+var_90]
0x1401f12df  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1401f12e4  mov     r9, rsi; KeyValueInformation
0x1401f12e7  mov     eax, [rbp+57h+var_90]
0x1401f12ea  mov     r8d, edi; KeyValueInformationClass
0x1401f12ed  xor     edx, edx; Index
0x1401f12ef  mov     [rsp+0E0h+Length], eax; Length
0x1401f12f3  call    cs:__imp_ZwEnumerateValueKey
0x1401f12fa  nop     dword ptr [rax+rax+00h]
0x1401f12ff  mov     ebx, eax
0x1401f1301  test    eax, eax
0x1401f1303  js      loc_1401F138D
0x1401f1309  movzx   eax, word ptr [rsi+10h]
0x1401f130d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401f1311  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401f1315  mov     [rbp+57h+ValueName.Length], ax
0x1401f1319  mov     [rbp+57h+ValueName.MaximumLength], ax
0x1401f131d  lea     rax, [rsi+14h]
0x1401f1321  mov     [rbp+57h+ValueName.Buffer], rax
0x1401f1325  mov     dword ptr [rbp+57h+ValueName+4], 0
0x1401f132c  call    cs:__imp_ZwDeleteValueKey
0x1401f1333  nop     dword ptr [rax+rax+00h]
0x1401f1338  mov     ebx, eax
0x1401f133a  test    eax, eax
0x1401f133c  jns     short loc_1401F138D
0x1401f133e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401f1345  mov     eax, [rcx+2Ch]
0x1401f1348  test    al, al
0x1401f134a  jns     short loc_1401F1357
0x1401f134c  cmp     byte ptr [rcx+29h], 2
0x1401f1350  jb      short loc_1401F1357
0x1401f1352  mov     dl, dil
0x1401f1355  jmp     short loc_1401F1359
0x1401f1357  xor     dl, dl
0x1401f1359  mov     r9, [rcx+40h]
0x1401f135d  lea     rax, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x1401f1364  mov     rcx, [rcx+18h]
0x1401f1368  mov     r8b, dil
0x1401f136b  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x1401f136f  mov     [rsp+0E0h+var_A8], rax
0x1401f1374  mov     [rsp+0E0h+var_B0], 30h ; '0'
0x1401f137b  mov     dword ptr [rsp+0E0h+ResultLength], 8
0x1401f1383  mov     byte ptr [rsp+0E0h+Length], 2
0x1401f1388  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401f138d  xor     edx, edx; Tag
0x1401f138f  mov     rcx, rsi; P
0x1401f1392  call    cs:__imp_ExFreePoolWithTag
0x1401f1399  nop     dword ptr [rax+rax+00h]
0x1401f139e  test    ebx, ebx
0x1401f13a0  jns     loc_1401F1265
0x1401f13a6  cmp     ebx, 8000001Ah
0x1401f13ac  jnz     loc_1401F15EF
0x1401f13b2  xor     ebx, ebx
0x1401f13b4  add     r14, r13
0x1401f13b7  sub     r12d, r13d
0x1401f13ba  jz      loc_1401F14C7
0x1401f13c0  mov     dl, [r14]
0x1401f13c3  mov     al, dl
0x1401f13c5  and     al, 0F8h
0x1401f13c7  cmp     al, 30h ; '0'
0x1401f13c9  jnz     loc_1401F14E7
0x1401f13cf  and     dl, 7
0x1401f13d2  lea     rcx, [r14+1]
0x1401f13d6  lea     r9, [rbp+57h+var_8C]
0x1401f13da  lea     r8, [rbp+57h+var_88]
0x1401f13de  call    SdpRetrieveVariableSize
0x1401f13e3  mov     esi, [rbp+57h+var_88]
0x1401f13e6  inc     esi
0x1401f13e8  add     esi, [rbp+57h+var_8C]
0x1401f13eb  cmp     esi, r12d
0x1401f13ee  ja      loc_1401F14E7
0x1401f13f4  mov     edx, esi
0x1401f13f6  mov     rcx, r14
0x1401f13f9  call    SdpIsStreamRecord
0x1401f13fe  test    eax, eax
0x1401f1400  js      loc_1401F14B9
0x1401f1406  xor     eax, eax
0x1401f1408  lea     r9, [rbp+57h+var_90]
0x1401f140c  mov     edx, esi
0x1401f140e  mov     word ptr [rbp+57h+var_90], ax
0x1401f1412  mov     rcx, r14
0x1401f1415  lea     r8d, [rax+4]
0x1401f1419  call    SdpVerifyServiceRecord
0x1401f141e  test    eax, eax
0x1401f1420  js      loc_1401F14B9
0x1401f1426  lea     rax, [rbp+57h+var_90]
0x1401f142a  mov     qword ptr [rbp+57h+ValueName.Length], 0
0x1401f1432  xor     r8d, r8d
0x1401f1435  mov     qword ptr [rsp+0E0h+Length], rax
0x1401f143a  lea     r9, [rbp+57h+ValueName]
0x1401f143e  mov     edx, esi
0x1401f1440  mov     rcx, r14
0x1401f1443  call    SdpFindAttributeInStream
0x1401f1448  test    eax, eax
0x1401f144a  js      short loc_1401F14B9
0x1401f144c  mov     rax, qword ptr [rbp+57h+ValueName.Length]
0x1401f1450  lea     r8, a08x; "%08x"
0x1401f1457  mov     edx, 12h; unsigned __int64
0x1401f145c  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 *
0x1401f1460  mov     r9d, [rax+rdi]
0x1401f1464  bswap   r9d
0x1401f1467  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401f146c  mov     ebx, eax
0x1401f146e  test    eax, eax
0x1401f1470  js      short loc_1401F14EC
0x1401f1472  xorps   xmm0, xmm0
0x1401f1475  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1401f1479  lea     rcx, [rbp+57h+ValueName]; DestinationString
  ... truncated ...
```
