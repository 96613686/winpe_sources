# BthEnumSetPdoInterfaceProperties

- ea: `0x14001b564`
- end: `0x14001bb4c`
- name: `BthEnumSetPdoInterfaceProperties`
- size: `1512`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140019058`
- `0x14001aaac`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x14001b564`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b5e6`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b64d`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b6b5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b72a`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b786`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b89f`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b933`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b992`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b9f3`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001ba69`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bad8`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b5e6`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b64d`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b6b5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b72a`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b786`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b89f`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b933`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b992`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001b9f3`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001ba69`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bad8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b6ee`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b6ee`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x14001b862`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x14001b862`
- `ntoskrnl!ExFreePool` at `0x14001b8e4`
- `ntoskrnl!ExFreePool` at `0x14001b8e4`
- `ntoskrnl!ExAllocatePool2` at `0x14001b7df`
- `ntoskrnl!ExAllocatePool2` at `0x14001b7df`

## pseudocode

```c
char __fastcall BthEnumSetPdoInterfaceProperties(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // eax
  int v6; // edx
  int v7; // eax
  int v8; // edx
  _DWORD *v9; // r14
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edx
  int v14; // eax
  int v15; // edx
  int v16; // eax
  NTSTATUS v17; // ebx
  WCHAR *Pool2; // rsi
  const CHAR *v19; // r9
  __int64 UTF8StringByteCount; // rax
  int v21; // eax
  int v22; // edx
  int v23; // eax
  int v24; // edx
  __int64 v26; // [rsp+28h] [rbp-60h]
  __int64 v27; // [rsp+28h] [rbp-60h]
  __int64 v28; // [rsp+28h] [rbp-60h]
  __int64 v29; // [rsp+28h] [rbp-60h]
  __int64 v30; // [rsp+28h] [rbp-60h]
  __int64 v31; // [rsp+28h] [rbp-60h]
  __int64 v32; // [rsp+28h] [rbp-60h]
  __int64 v33; // [rsp+28h] [rbp-60h]
  __int64 v34; // [rsp+28h] [rbp-60h]
  __int64 v35; // [rsp+28h] [rbp-60h]
  ULONG UnicodeStringActualByteCount; // [rsp+90h] [rbp+8h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      30,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids);
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL);
  v5 = IoSetDeviceInterfacePropertyData(a2, &DEVPKEY_Bluetooth_DeviceAddress, 0, 0, 18, 26, a1 + 24);
  if ( v5 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v26) = v5;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3u,
      0x1Fu,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      v26);
  }
  v7 = IoSetDeviceInterfacePropertyData(a2, DEVPKEY_Bluetooth_RadioAddress, 0, 0, 9, 8, v4 + 320);
  if ( v7 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v27) = v7;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v8,
      3u,
      0x20u,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      v27);
  }
  v9 = (_DWORD *)(a1 + 184);
  v10 = IoSetDeviceInterfacePropertyData(a2, &DEVPKEY_Bluetooth_DeviceFlags, 0, 0, 7, 4, a1 + 184);
  if ( v10 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v28) = v10;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v11,
      3u,
      0x21u,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      v28);
  }
  LOBYTE(v12) = KeGetCurrentIrql();
  if ( (_BYTE)v12 )
    goto LABEL_51;
  v14 = IoSetDeviceInterfacePropertyData(a2, &DEVPKEY_Bluetooth_ClassOfDevice, 0, 0, 7, 4, a1 + 200);
  if ( v14 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v29) = v14;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v15,
      3u,
      0x22u,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      v29);
  }
  v16 = IoSetDeviceInterfacePropertyData(a2, &DEVPKEY_Bluetooth_ClassOfDevice_Deprecated, 0, 0, 7, 4, a1 + 200);
  v17 = v16;
  if ( v16 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v30) = v16;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v13,
      3u,
      0x23u,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      v30);
  }
  if ( (*v9 & 4) != 0 )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, 498, 1330467906);
    if ( Pool2 )
    {
      if ( v17 >= 0 )
      {
        UnicodeStringActualByteCount = 0;
        v19 = (const CHAR *)(a1 + 204);
        UTF8StringByteCount = -1;
        do
          ++UTF8StringByteCount;
        while ( v19[UTF8StringByteCount] );
        v17 = RtlUTF8ToUnicodeN(Pool2, 0x1F2u, &UnicodeStringActualByteCount, v19, UTF8StringByteCount);
        if ( v17 >= 0 )
        {
          v17 = IoSetDeviceInterfacePropertyData(
                  a2,
                  &DEVPKEY_DeviceInterface_FriendlyName,
                  0,
                  0,
                  18,
                  UnicodeStringActualByteCount + 2,
                  Pool2);
          if ( v17 >= 0 )
          {
LABEL_31:
            ExFreePool(Pool2);
            goto LABEL_32;
          }
        }
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_32;
      v17 = -1073741670;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        3,
        36,
        (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v30) = v17;
      WPP_RECORDER_SF_d(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v13,
        3u,
        0x25u,
        (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
        v30);
    }
    if ( Pool2 )
      goto LABEL_31;
  }
LABEL_32:
  LOBYTE(v12) = 0;
  if ( *(_WORD *)(a1 + 1596) && *(_WORD *)(a1 + 1588) )
  {
    v21 = IoSetDeviceInterfacePropertyData(a2, &DEVPKEY_Bluetooth_DeviceVIDSource, 0, 0, 3, 1, a1 + 1596);
    if ( v21 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v31) = v21;
      WPP_RECORDER_SF_d(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v22,
        3u,
        0x26u,
        (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
        v31);
    }
    v23 = IoSetDeviceInterfacePropertyData(a2, &DEVPKEY_Bluetooth_DeviceVID, 0, 0, 5, 2, a1 + 1588);
    if ( v23 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v32) = v23;
      WPP_RECORDER_SF_d(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v24,
        3u,
        0x27u,
        (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
        v32);
    }
    v12 = IoSetDeviceInterfacePropertyData(a2, &DEVPKEY_Bluetooth_DevicePID, 0, 0, 5, 2, a1 + 1590);
    if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v33) = v12;
      LOBYTE(v12) = WPP_RECORDER_SF_d(
                      (__int64)WPP_GLOBAL_Control->DeviceExtension,
                      v13,
                      3u,
                      0x28u,
                      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
                      v33);
    }
  }
  if ( (*v9 & 0x8000000) != 0 )
  {
    LOBYTE(UnicodeStringActualByteCount) = -1;
    v12 = IoSetDeviceInterfacePropertyData(
            a2,
            &DEVPKEY_Bluetooth_SecureConnectionPaired,
            0,
            0,
            17,
            1,
            &UnicodeStringActualByteCount);
    if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v34) = v12;
      LOBYTE(v12) = WPP_RECORDER_SF_d(
                      (__int64)WPP_GLOBAL_Control->DeviceExtension,
                      v13,
                      3u,
                      0x29u,
                      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
                      v34);
    }
  }
  if ( (*v9 & 0x4000000) != 0 )
  {
    LOBYTE(UnicodeStringActualByteCount) = -1;
    v12 = IoSetDeviceInterfacePropertyData(
            a2,
            DEVPKEY_Bluetooth_SdpCachePopulated,
            0,
            0,
            17,
            1,
            &UnicodeStringActualByteCount);
    if ( v12 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v12;
      LODWORD(v35) = v12;
      LOBYTE(v12) = WPP_RECORDER_SF_d(
                      (__int64)WPP_GLOBAL_Control->DeviceExtension,
                      v13,
                      3u,
                      0x2Au,
                      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
                      v35);
    }
  }
LABEL_51:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    LOBYTE(v12) = WPP_RECORDER_SF_(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v13,
                    3,
                    43,
                    (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids);
  return v12;
}

```

## disassembly

```asm
0x14001b564  push    rbx
0x14001b566  push    rbp
0x14001b567  push    rsi
0x14001b568  push    rdi
0x14001b569  push    r12
0x14001b56b  push    r13
0x14001b56d  push    r14
0x14001b56f  push    r15
0x14001b571  sub     rsp, 48h
0x14001b575  mov     rdi, rdx
0x14001b578  mov     rbp, rcx
0x14001b57b  lea     r15, WPP_RECORDER_INITIALIZED
0x14001b582  mov     r12d, 3
0x14001b588  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b58f  lea     r13, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14001b596  jz      short loc_14001B5B5
0x14001b598  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b59f  lea     r9d, [r12+1Bh]
0x14001b5a4  mov     r8d, r12d
0x14001b5a7  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b5ac  mov     rcx, [rcx+40h]
0x14001b5b0  call    WPP_RECORDER_SF_
0x14001b5b5  mov     rax, [rbp+8]
0x14001b5b9  lea     rdx, DEVPKEY_Bluetooth_DeviceAddress
0x14001b5c0  xor     r9d, r9d
0x14001b5c3  xor     r8d, r8d
0x14001b5c6  mov     rcx, rdi
0x14001b5c9  mov     rbx, [rax+40h]
0x14001b5cd  lea     rax, [rbp+18h]
0x14001b5d1  mov     [rsp+88h+var_58], rax
0x14001b5d6  mov     dword ptr [rsp+88h+var_60], 1Ah
0x14001b5de  mov     [rsp+88h+UTF8StringByteCount], 12h
0x14001b5e6  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b5ed  nop     dword ptr [rax+rax+00h]
0x14001b5f2  test    eax, eax
0x14001b5f4  jns     short loc_14001B621
0x14001b5f6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b5fd  jz      short loc_14001B621
0x14001b5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b606  mov     r9d, 1Fh
0x14001b60c  mov     dword ptr [rsp+88h+var_60], eax
0x14001b610  mov     r8d, r12d
0x14001b613  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b618  mov     rcx, [rcx+40h]
0x14001b61c  call    WPP_RECORDER_SF_d
0x14001b621  lea     rax, [rbx+140h]
0x14001b628  xor     r9d, r9d
0x14001b62b  mov     [rsp+88h+var_58], rax
0x14001b630  lea     rdx, DEVPKEY_Bluetooth_RadioAddress
0x14001b637  mov     dword ptr [rsp+88h+var_60], 8
0x14001b63f  xor     r8d, r8d
0x14001b642  mov     rcx, rdi
0x14001b645  mov     [rsp+88h+UTF8StringByteCount], 9
0x14001b64d  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b654  nop     dword ptr [rax+rax+00h]
0x14001b659  test    eax, eax
0x14001b65b  jns     short loc_14001B688
0x14001b65d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b664  jz      short loc_14001B688
0x14001b666  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b66d  mov     r9d, 20h ; ' '
0x14001b673  mov     dword ptr [rsp+88h+var_60], eax
0x14001b677  mov     r8d, r12d
0x14001b67a  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b67f  mov     rcx, [rcx+40h]
0x14001b683  call    WPP_RECORDER_SF_d
0x14001b688  lea     r14, [rbp+0B8h]
0x14001b68f  mov     esi, 4
0x14001b694  mov     [rsp+88h+var_58], r14
0x14001b699  lea     rdx, DEVPKEY_Bluetooth_DeviceFlags
0x14001b6a0  mov     dword ptr [rsp+88h+var_60], esi
0x14001b6a4  xor     r9d, r9d
0x14001b6a7  xor     r8d, r8d
0x14001b6aa  mov     [rsp+88h+UTF8StringByteCount], 7
0x14001b6b2  mov     rcx, rdi
0x14001b6b5  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b6bc  nop     dword ptr [rax+rax+00h]
0x14001b6c1  test    eax, eax
0x14001b6c3  jns     short loc_14001B6EE
0x14001b6c5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b6cc  jz      short loc_14001B6EE
0x14001b6ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6d5  lea     r9d, [rsi+1Dh]
0x14001b6d9  mov     dword ptr [rsp+88h+var_60], eax
0x14001b6dd  mov     r8d, r12d
0x14001b6e0  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b6e5  mov     rcx, [rcx+40h]
0x14001b6e9  call    WPP_RECORDER_SF_d
0x14001b6ee  call    cs:__imp_KeGetCurrentIrql
0x14001b6f5  nop     dword ptr [rax+rax+00h]
0x14001b6fa  test    al, al
0x14001b6fc  jnz     loc_14001BB13
0x14001b702  lea     rbx, [rbp+0C8h]
0x14001b709  xor     r9d, r9d
0x14001b70c  mov     [rsp+88h+var_58], rbx
0x14001b711  lea     rdx, DEVPKEY_Bluetooth_ClassOfDevice
0x14001b718  mov     dword ptr [rsp+88h+var_60], esi
0x14001b71c  xor     r8d, r8d
0x14001b71f  mov     rcx, rdi
0x14001b722  mov     [rsp+88h+UTF8StringByteCount], 7
0x14001b72a  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b731  nop     dword ptr [rax+rax+00h]
0x14001b736  test    eax, eax
0x14001b738  jns     short loc_14001B765
0x14001b73a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b741  jz      short loc_14001B765
0x14001b743  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b74a  mov     r9d, 22h ; '"'
0x14001b750  mov     dword ptr [rsp+88h+var_60], eax
0x14001b754  mov     r8d, r12d
0x14001b757  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b75c  mov     rcx, [rcx+40h]
0x14001b760  call    WPP_RECORDER_SF_d
0x14001b765  mov     [rsp+88h+var_58], rbx
0x14001b76a  lea     rdx, DEVPKEY_Bluetooth_ClassOfDevice_Deprecated
0x14001b771  mov     dword ptr [rsp+88h+var_60], esi
0x14001b775  xor     r9d, r9d
0x14001b778  xor     r8d, r8d
0x14001b77b  mov     [rsp+88h+UTF8StringByteCount], 7
0x14001b783  mov     rcx, rdi
0x14001b786  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b78d  nop     dword ptr [rax+rax+00h]
0x14001b792  mov     ebx, eax
0x14001b794  test    eax, eax
0x14001b796  jns     short loc_14001B7C3
0x14001b798  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b79f  jz      short loc_14001B7C3
0x14001b7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b7a8  mov     r9d, 23h ; '#'
0x14001b7ae  mov     dword ptr [rsp+88h+var_60], eax
0x14001b7b2  mov     r8d, r12d
0x14001b7b5  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b7ba  mov     rcx, [rcx+40h]
0x14001b7be  call    WPP_RECORDER_SF_d
0x14001b7c3  mov     eax, [r14]
0x14001b7c6  test    sil, al
0x14001b7c9  jz      loc_14001B8F0
0x14001b7cf  mov     edx, 1F2h
0x14001b7d4  mov     ecx, 100h
0x14001b7d9  mov     r8d, 4F4D5442h
0x14001b7df  call    cs:__imp_ExAllocatePool2
0x14001b7e6  nop     dword ptr [rax+rax+00h]
0x14001b7eb  mov     rsi, rax
0x14001b7ee  test    rax, rax
0x14001b7f1  jnz     short loc_14001B826
0x14001b7f3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b7fa  jz      loc_14001B8F0
0x14001b800  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b807  lea     r9d, [rax+24h]
0x14001b80b  mov     r8d, r12d
0x14001b80e  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b813  mov     ebx, 0C000009Ah
0x14001b818  mov     rcx, [rcx+40h]
0x14001b81c  call    WPP_RECORDER_SF_
0x14001b821  jmp     loc_14001B8B1
0x14001b826  test    ebx, ebx
0x14001b828  js      loc_14001B8B1
0x14001b82e  mov     [rsp+88h+UnicodeStringActualByteCount], 0
0x14001b839  lea     r9, [rbp+0CCh]; UTF8StringSource
0x14001b840  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b844  inc     rax
0x14001b847  cmp     byte ptr [r9+rax], 0
0x14001b84c  jnz     short loc_14001B844
0x14001b84e  lea     r8, [rsp+88h+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x14001b856  mov     [rsp+88h+UTF8StringByteCount], eax; UTF8StringByteCount
0x14001b85a  mov     edx, 1F2h; UnicodeStringMaxByteCount
0x14001b85f  mov     rcx, rsi; UnicodeStringDestination
0x14001b862  call    cs:__imp_RtlUTF8ToUnicodeN
0x14001b869  nop     dword ptr [rax+rax+00h]
0x14001b86e  mov     ebx, eax
0x14001b870  test    eax, eax
0x14001b872  js      short loc_14001B8B1
0x14001b874  mov     eax, [rsp+88h+UnicodeStringActualByteCount]
0x14001b87b  lea     rdx, DEVPKEY_DeviceInterface_FriendlyName
0x14001b882  add     eax, 2
0x14001b885  mov     [rsp+88h+var_58], rsi
0x14001b88a  mov     dword ptr [rsp+88h+var_60], eax
0x14001b88e  xor     r9d, r9d
0x14001b891  xor     r8d, r8d
0x14001b894  mov     [rsp+88h+UTF8StringByteCount], 12h
0x14001b89c  mov     rcx, rdi
0x14001b89f  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b8a6  nop     dword ptr [rax+rax+00h]
0x14001b8ab  mov     ebx, eax
0x14001b8ad  test    eax, eax
0x14001b8af  jns     short loc_14001B8E1
0x14001b8b1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b8b8  jz      short loc_14001B8DC
0x14001b8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8c1  mov     r9d, 25h ; '%'
0x14001b8c7  mov     dword ptr [rsp+88h+var_60], ebx
0x14001b8cb  mov     r8d, r12d
0x14001b8ce  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b8d3  mov     rcx, [rcx+40h]
0x14001b8d7  call    WPP_RECORDER_SF_d
0x14001b8dc  test    rsi, rsi
0x14001b8df  jz      short loc_14001B8F0
0x14001b8e1  mov     rcx, rsi; P
0x14001b8e4  call    cs:__imp_ExFreePool
0x14001b8eb  nop     dword ptr [rax+rax+00h]
0x14001b8f0  xor     eax, eax
0x14001b8f2  lea     rcx, [rbp+63Ch]
0x14001b8f9  lea     esi, [rax+1]
0x14001b8fc  cmp     ax, [rcx]
0x14001b8ff  jz      loc_14001BA2E
0x14001b905  lea     rbx, [rbp+634h]
0x14001b90c  cmp     ax, [rbx]
0x14001b90f  jz      loc_14001BA2E
0x14001b915  mov     [rsp+88h+var_58], rcx
0x14001b91a  lea     rdx, DEVPKEY_Bluetooth_DeviceVIDSource
0x14001b921  mov     dword ptr [rsp+88h+var_60], esi
0x14001b925  mov     rcx, rdi
0x14001b928  xor     r9d, r9d
0x14001b92b  mov     [rsp+88h+UTF8StringByteCount], r12d
0x14001b930  xor     r8d, r8d
0x14001b933  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b93a  nop     dword ptr [rax+rax+00h]
0x14001b93f  test    eax, eax
0x14001b941  jns     short loc_14001B96C
0x14001b943  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b94a  jz      short loc_14001B96C
0x14001b94c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b953  lea     r9d, [rsi+25h]
0x14001b957  mov     dword ptr [rsp+88h+var_60], eax
0x14001b95b  mov     r8d, r12d
0x14001b95e  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b963  mov     rcx, [rcx+40h]
0x14001b967  call    WPP_RECORDER_SF_d
0x14001b96c  mov     [rsp+88h+var_58], rbx
0x14001b971  lea     rdx, DEVPKEY_Bluetooth_DeviceVID
0x14001b978  mov     ebx, 2
0x14001b97d  xor     r9d, r9d
0x14001b980  mov     dword ptr [rsp+88h+var_60], ebx
0x14001b984  xor     r8d, r8d
0x14001b987  mov     rcx, rdi
0x14001b98a  mov     [rsp+88h+UTF8StringByteCount], 5
0x14001b992  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b999  nop     dword ptr [rax+rax+00h]
0x14001b99e  test    eax, eax
0x14001b9a0  jns     short loc_14001B9CB
0x14001b9a2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001b9a9  jz      short loc_14001B9CB
0x14001b9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b9b2  lea     r9d, [rbx+25h]
0x14001b9b6  mov     dword ptr [rsp+88h+var_60], eax
0x14001b9ba  mov     r8d, r12d
0x14001b9bd  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001b9c2  mov     rcx, [rcx+40h]
0x14001b9c6  call    WPP_RECORDER_SF_d
0x14001b9cb  lea     rax, [rbp+636h]
0x14001b9d2  xor     r9d, r9d
0x14001b9d5  mov     [rsp+88h+var_58], rax
0x14001b9da  lea     rdx, DEVPKEY_Bluetooth_DevicePID
0x14001b9e1  mov     dword ptr [rsp+88h+var_60], ebx
0x14001b9e5  xor     r8d, r8d
0x14001b9e8  mov     rcx, rdi
0x14001b9eb  mov     [rsp+88h+UTF8StringByteCount], 5
0x14001b9f3  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001b9fa  nop     dword ptr [rax+rax+00h]
0x14001b9ff  test    eax, eax
0x14001ba01  jns     short loc_14001BA2E
0x14001ba03  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001ba0a  jz      short loc_14001BA2E
0x14001ba0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba13  mov     r9d, 28h ; '('
0x14001ba19  mov     dword ptr [rsp+88h+var_60], eax
0x14001ba1d  mov     r8d, r12d
0x14001ba20  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001ba25  mov     rcx, [rcx+40h]
0x14001ba29  call    WPP_RECORDER_SF_d
0x14001ba2e  test    dword ptr [r14], 8000000h
0x14001ba35  mov     ebx, 11h
0x14001ba3a  jz      short loc_14001BAA2
0x14001ba3c  lea     rax, [rsp+88h+UnicodeStringActualByteCount]
0x14001ba44  mov     byte ptr [rsp+88h+UnicodeStringActualByteCount], 0FFh
0x14001ba4c  mov     [rsp+88h+var_58], rax
0x14001ba51  lea     rdx, DEVPKEY_Bluetooth_SecureConnectionPaired
0x14001ba58  mov     dword ptr [rsp+88h+var_60], esi
0x14001ba5c  xor     r9d, r9d
0x14001ba5f  xor     r8d, r8d
0x14001ba62  mov     [rsp+88h+UTF8StringByteCount], ebx
0x14001ba66  mov     rcx, rdi
0x14001ba69  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001ba70  nop     dword ptr [rax+rax+00h]
0x14001ba75  test    eax, eax
0x14001ba77  jns     short loc_14001BAA2
0x14001ba79  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001ba80  jz      short loc_14001BAA2
0x14001ba82  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba89  lea     r9d, [rbx+18h]
0x14001ba8d  mov     dword ptr [rsp+88h+var_60], eax
0x14001ba91  mov     r8d, r12d
0x14001ba94  mov     qword ptr [rsp+88h+UTF8StringByteCount], r13
0x14001ba99  mov     rcx, [rcx+40h]
0x14001ba9d  call    WPP_RECORDER_SF_d
0x14001baa2  test    dword ptr [r14], 4000000h
0x14001baa9  jz      short loc_14001BB13
0x14001baab  lea     rax, [rsp+88h+UnicodeStringActualByteCount]
0x14001bab3  mov     byte ptr [rsp+88h+UnicodeStringActualByteCount], 0FFh
0x14001babb  mov     [rsp+88h+var_58], rax
  ... truncated ...
```
