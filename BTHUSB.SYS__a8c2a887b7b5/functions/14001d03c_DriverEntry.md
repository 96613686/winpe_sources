# DriverEntry

- ea: `0x14001d03c`
- end: `0x14001d5ad`
- name: `DriverEntry`
- size: `1393`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x14000be64`

## callees

- `0x140001008`
- `0x1400014f0`
- `0x14000175c`
- `0x1400017d4`
- `0x14000c908`
- `0x14000d810`
- `0x14000de00`
- `0x140017008`
- `0x140017c68`
- `0x140017d1c`
- `0x140017de4`
- `0x14001d03c`
- `0x14001d5b4`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x14001d1b8`
- `ntoskrnl!EtwRegister` at `0x14001d1b8`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d181`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d181`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d345`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d345`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d38d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d38d`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14001d358`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14001d358`
- `ntoskrnl!RtlFreeAnsiString` at `0x14001d3f3`
- `ntoskrnl!RtlFreeAnsiString` at `0x14001d3f3`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14001d379`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14001d379`
- `ntoskrnl!RtlInitAnsiString` at `0x14001d3cf`
- `ntoskrnl!RtlInitAnsiString` at `0x14001d3cf`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v4; // di
  int v5; // edx
  int v6; // r8d
  int v7; // eax
  int v8; // edx
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  NTSTATUS v18; // ebx
  __int64 v19; // rcx
  bool v20; // zf
  int v21; // eax
  int v22; // edx
  NTSTATUS v23; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-69h] BYREF
  struct _STRING AnsiString; // [rsp+60h] [rbp-59h] BYREF
  __int128 v27; // [rsp+70h] [rbp-49h] BYREF
  __int128 v28; // [rsp+80h] [rbp-39h]
  struct _STRING v29; // [rsp+90h] [rbp-29h] BYREF
  int *v30; // [rsp+A0h] [rbp-19h] BYREF
  char v31; // [rsp+A8h] [rbp-11h]
  _QWORD v32[6]; // [rsp+B0h] [rbp-9h] BYREF
  struct _STRING v33; // [rsp+E0h] [rbp+27h] BYREF
  int v34; // [rsp+130h] [rbp+77h] BYREF
  const wchar_t *v35; // [rsp+138h] [rbp+7Fh] BYREF

  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_bthusb;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  v4 = 1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(v5) = 0;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    v6,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    10,
    (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids);
  v7 = wil_InitializeFeatureStaging();
  v34 = v7;
  v30 = &v34;
  v31 = 1;
  if ( v7 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v8) = 0;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      2,
      11,
      (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
      v7);
    v34 = 0;
  }
  qword_1400132E0 = (__int64)&g_PdoLockedList;
  g_PdoLockedList = (struct _LIST_ENTRY *)&g_PdoLockedList;
  KeInitializeSpinLock(&qword_1400132E8);
  SpinLock = &qword_1400132E8;
  dword_1400132F8 = 0;
  RefObj_GlobalsInit();
  v9 = EtwRegister(&BTHUSB_ETW_PROVIDER, BthUsb_EtwEnableCallback, 0, &g_EtwRegHandle);
  v34 = v9;
  if ( v9 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v10) = 0;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      2,
      12,
      (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
      v9);
    v34 = 0;
  }
  AnsiString = 0;
  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
  {
    v34 = 0;
    goto LABEL_16;
  }
  RtlInitUnicodeString(&DestinationString, 0);
  v15 = IoQueryFullDriverPath(DriverObject, &DestinationString);
  LOBYTE(v18) = v15;
  if ( v15 < 0 )
  {
    v34 = v15;
LABEL_40:
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v16) = 0;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v16,
      v17,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      2,
      13,
      (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
      v18);
    v34 = 0;
    goto LABEL_16;
  }
  v18 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
  ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( v18 < 0 )
  {
    v34 = v18;
    goto LABEL_40;
  }
  v19 = (unsigned int)AnsiString.Length - 1;
  if ( AnsiString.Length != 1 )
  {
    while ( AnsiString.Buffer[v19] != 92 )
    {
      v20 = (_DWORD)v19 == 1;
      v19 = (unsigned int)(v19 - 1);
      if ( v20 )
        goto LABEL_36;
    }
    if ( (_DWORD)v19 != AnsiString.Length )
    {
      v29 = 0;
      RtlInitAnsiString(&v29, &AnsiString.Buffer[(unsigned int)(v19 + 1)]);
      v33 = v29;
      v18 = InitializeTelemetryAssertsKMWorkerInternal(&v33);
    }
  }
LABEL_36:
  RtlFreeAnsiString(&AnsiString);
  v34 = v18;
  if ( v18 < 0 )
    goto LABEL_40;
LABEL_16:
  v11 = TraceLoggingRegister_EtwRegister_EtwSetInformation(&dword_140013000);
  v34 = v11;
  if ( v11 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v12) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v12) = 0;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      2,
      14,
      (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
      v11);
    v34 = 0;
  }
  if ( (unsigned int)dword_140013000 > 5
    && (qword_140013010 & 0x400000000000LL) != 0
    && (qword_140013018 & 0x400000000000LL) == qword_140013018 )
  {
    *(_QWORD *)&DestinationString.Length = 33556480;
    v35 = L"BthUsb.sys";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      qword_140013018,
      (unsigned int)&byte_140010D4F,
      v13,
      v14,
      (__int64)&DestinationString,
      (__int64)&v35);
  }
  v27 = 0;
  v28 = 0;
  if ( LOBYTE(WPP_MAIN_CB.DeviceQueue.Lock) )
  {
    if ( (unsigned int)WdfStructureCount <= 0x18 )
      LODWORD(v27) = -1;
    else
      LODWORD(v27) = *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32 + 192LL);
  }
  else
  {
    LODWORD(v27) = 32;
  }
  HIDWORD(v28) = 1111642965;
  *((_QWORD *)&v27 + 1) = BthUsb_WdfDeviceAdd;
  *(_QWORD *)&v28 = BthUsb_WdfDriverUnload;
  v21 = ((__int64 (__fastcall *)(_LIST_ENTRY *, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD, __int128 *, _QWORD))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[58].Flink)(
          WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
          DriverObject,
          RegistryPath,
          0,
          &v27,
          0);
  v34 = v21;
  if ( v21 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      v4 = 0;
    LOBYTE(v22) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v22,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      2,
      15,
      (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids,
      v21);
    if ( v34 < 0 )
      goto LABEL_52;
  }
  v32[0] = BthUsb_GetCapabilities;
  v32[1] = BthUsb_ScoValidateChannel;
  v32[2] = BthUsb_ScoAddChannel;
  v32[3] = BthUsb_ScoRemoveChannel;
  v32[4] = BthUsb_ScoControlChannel;
  v34 = ((__int64 (__fastcall *)(__int64, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD *, int))qword_140013280)(
          BthDriverGlobals,
          DriverObject,
          RegistryPath,
          v32,
          40);
  v23 = v34;
  if ( v34 < 0 )
  {
LABEL_52:
    BthUsb_DriverUnload(DriverObject);
    v23 = v34;
  }
  wil::details::lambda_call__lambda_ab0b21a5b1f80815114ac5907429201e___::_lambda_call__lambda_ab0b21a5b1f80815114ac5907429201e___(&v30);
  return v23;
}

```

## disassembly

```asm
0x14001d03c  mov     [rsp-8+arg_0], rbx
0x14001d041  mov     [rsp-8+arg_8], rsi
0x14001d046  push    rbp
0x14001d047  push    rdi
0x14001d048  push    r12
0x14001d04a  push    r14
0x14001d04c  push    r15
0x14001d04e  lea     rbp, [rsp-37h]
0x14001d053  sub     rsp, 0F0h
0x14001d05a  xor     r15d, r15d
0x14001d05d  mov     cs:WPP_MAIN_CB.Timer, 1
0x14001d068  lea     rax, WPP_ThisDir_CTLGUID_bthusb
0x14001d06f  mov     qword ptr cs:WPP_MAIN_CB.Type, r15
0x14001d076  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14001d07d  mov     r14, rdx
0x14001d080  mov     cs:WPP_MAIN_CB.NextDevice, r15
0x14001d087  mov     rsi, rcx
0x14001d08a  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x14001d091  mov     dil, 1
0x14001d094  mov     cs:WPP_MAIN_CB.DeviceExtension, r15
0x14001d09b  mov     cs:WPP_MAIN_CB.DeviceType, r15d
0x14001d0a2  call    WppLoadTracingSupport
0x14001d0a7  mov     rdx, r14
0x14001d0aa  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x14001d0b1  mov     rcx, rsi
0x14001d0b4  call    WppInitKm
0x14001d0b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0c0  lea     r12d, [r15+2]
0x14001d0c4  mov     eax, [rcx+2Ch]
0x14001d0c7  test    r12b, al
0x14001d0ca  jz      short loc_14001D0D5
0x14001d0cc  cmp     byte ptr [rcx+29h], 4
0x14001d0d0  mov     dl, dil
0x14001d0d3  jnb     short loc_14001D0D8
0x14001d0d5  mov     dl, r15b
0x14001d0d8  mov     r9, [rcx+40h]
0x14001d0dc  lea     rbx, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x14001d0e3  mov     rcx, [rcx+18h]
0x14001d0e7  mov     [rsp+110h+var_D8], rbx
0x14001d0ec  mov     [rsp+110h+var_E0], 0Ah
0x14001d0f3  mov     dword ptr [rsp+110h+var_E8], r12d
0x14001d0f8  mov     byte ptr [rsp+110h+var_F0], 4
0x14001d0fd  call    WPP_RECORDER_AND_TRACE_SF_
0x14001d102  call    wil_InitializeFeatureStaging
0x14001d107  mov     [rbp+57h+arg_10], eax
0x14001d10a  lea     rcx, [rbp+57h+arg_10]
0x14001d10e  mov     [rbp+57h+var_70], rcx
0x14001d112  mov     [rbp+57h+var_68], dil
0x14001d116  test    eax, eax
0x14001d118  jns     short loc_14001D162
0x14001d11a  mov     r8, cs:WPP_GLOBAL_Control
0x14001d121  mov     ecx, [r8+2Ch]
0x14001d125  test    r12b, cl
0x14001d128  jz      short loc_14001D134
0x14001d12a  cmp     byte ptr [r8+29h], 3
0x14001d12f  mov     dl, dil
0x14001d132  jnb     short loc_14001D137
0x14001d134  mov     dl, r15b
0x14001d137  mov     r9, [r8+40h]
0x14001d13b  mov     rcx, [r8+18h]
0x14001d13f  mov     [rsp+110h+var_D0], eax
0x14001d143  mov     [rsp+110h+var_D8], rbx
0x14001d148  mov     [rsp+110h+var_E0], 0Bh
0x14001d14f  mov     dword ptr [rsp+110h+var_E8], r12d
0x14001d154  mov     byte ptr [rsp+110h+var_F0], 3
0x14001d159  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001d15e  mov     [rbp+57h+arg_10], r15d
0x14001d162  lea     rax, ?g_PdoLockedList@@3U_LOCKED_LIST@@A; _LOCKED_LIST g_PdoLockedList
0x14001d169  lea     rbx, qword_1400132E8
0x14001d170  mov     cs:qword_1400132E0, rax
0x14001d177  mov     rcx, rbx; SpinLock
0x14001d17a  mov     cs:?g_PdoLockedList@@3U_LOCKED_LIST@@A, rax; _LOCKED_LIST g_PdoLockedList
0x14001d181  call    cs:__imp_KeInitializeSpinLock
0x14001d188  nop     dword ptr [rax+rax+00h]
0x14001d18d  mov     cs:SpinLock, rbx
0x14001d194  mov     cs:dword_1400132F8, r15d
0x14001d19b  call    RefObj_GlobalsInit
0x14001d1a0  lea     r9, ?g_EtwRegHandle@@3_KA; RegHandle
0x14001d1a7  xor     r8d, r8d; CallbackContext
0x14001d1aa  lea     rdx, ?BthUsb_EtwEnableCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; EnableCallback
0x14001d1b1  lea     rcx, BTHUSB_ETW_PROVIDER; ProviderId
0x14001d1b8  call    cs:__imp_EtwRegister
0x14001d1bf  nop     dword ptr [rax+rax+00h]
0x14001d1c4  mov     [rbp+57h+arg_10], eax
0x14001d1c7  test    eax, eax
0x14001d1c9  jns     short loc_14001D21A
0x14001d1cb  mov     r8, cs:WPP_GLOBAL_Control
0x14001d1d2  mov     ecx, [r8+2Ch]
0x14001d1d6  test    r12b, cl
0x14001d1d9  jz      short loc_14001D1E5
0x14001d1db  cmp     byte ptr [r8+29h], 3
0x14001d1e0  mov     dl, dil
0x14001d1e3  jnb     short loc_14001D1E8
0x14001d1e5  mov     dl, r15b
0x14001d1e8  mov     r9, [r8+40h]
0x14001d1ec  mov     rcx, [r8+18h]
0x14001d1f0  mov     [rsp+110h+var_D0], eax
0x14001d1f4  lea     rax, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x14001d1fb  mov     [rsp+110h+var_D8], rax
0x14001d200  mov     [rsp+110h+var_E0], 0Ch
0x14001d207  mov     dword ptr [rsp+110h+var_E8], r12d
0x14001d20c  mov     byte ptr [rsp+110h+var_F0], 3
0x14001d211  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001d216  mov     [rbp+57h+arg_10], r15d
0x14001d21a  xorps   xmm0, xmm0
0x14001d21d  xorps   xmm1, xmm1
0x14001d220  movups  xmmword ptr [rbp+57h+AnsiString.Length], xmm0
0x14001d224  mov     eax, r15d
0x14001d227  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14001d22b  lock xadd cs:g_AssertsOperational, eax
0x14001d233  test    eax, eax
0x14001d235  jz      loc_14001D33F
0x14001d23b  mov     [rbp+57h+arg_10], r15d
0x14001d23f  lea     rbx, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x14001d246  lea     rcx, dword_140013000; CallbackContext
0x14001d24d  call    TraceLoggingRegister_EtwRegister_EtwSetInformation
0x14001d252  mov     [rbp+57h+arg_10], eax
0x14001d255  test    eax, eax
0x14001d257  jns     short loc_14001D2A1
0x14001d259  mov     r8, cs:WPP_GLOBAL_Control
0x14001d260  mov     ecx, [r8+2Ch]
0x14001d264  test    r12b, cl
0x14001d267  jz      short loc_14001D273
0x14001d269  cmp     byte ptr [r8+29h], 3
0x14001d26e  mov     dl, dil
0x14001d271  jnb     short loc_14001D276
0x14001d273  mov     dl, r15b
0x14001d276  mov     r9, [r8+40h]
0x14001d27a  mov     rcx, [r8+18h]
0x14001d27e  mov     [rsp+110h+var_D0], eax
0x14001d282  mov     [rsp+110h+var_D8], rbx
0x14001d287  mov     [rsp+110h+var_E0], 0Eh
0x14001d28e  mov     dword ptr [rsp+110h+var_E8], r12d
0x14001d293  mov     byte ptr [rsp+110h+var_F0], 3
0x14001d298  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001d29d  mov     [rbp+57h+arg_10], r15d
0x14001d2a1  mov     eax, cs:dword_140013000
0x14001d2a7  cmp     eax, 5
0x14001d2aa  jbe     short loc_14001D305
0x14001d2ac  mov     rcx, cs:qword_140013018
0x14001d2b3  mov     rdx, 400000000000h
0x14001d2bd  mov     rax, cs:qword_140013010
0x14001d2c4  test    rdx, rax
0x14001d2c7  jz      short loc_14001D305
0x14001d2c9  mov     rax, rcx
0x14001d2cc  and     rax, rdx
0x14001d2cf  cmp     rax, rcx
0x14001d2d2  jnz     short loc_14001D305
0x14001d2d4  lea     rax, aBthusbSys; "BthUsb.sys"
0x14001d2db  mov     qword ptr [rbp+57h+DestinationString.Length], 2000800h
0x14001d2e3  mov     [rbp+57h+arg_18], rax
0x14001d2e7  lea     rdx, byte_140010D4F
0x14001d2ee  lea     rax, [rbp+57h+arg_18]
0x14001d2f2  mov     [rsp+110h+var_E8], rax
0x14001d2f7  lea     rax, [rbp+57h+DestinationString]
0x14001d2fb  mov     [rsp+110h+var_F0], rax
0x14001d300  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14001d305  cmp     byte ptr cs:WPP_MAIN_CB.DeviceQueue.Lock, r15b
0x14001d30c  xorps   xmm0, xmm0
0x14001d30f  movups  [rbp+57h+var_A0], xmm0
0x14001d313  movups  [rbp+57h+var_90], xmm0
0x14001d317  jz      loc_14001D46F
0x14001d31d  cmp     cs:WdfStructureCount, 18h
0x14001d324  jbe     loc_14001D466
0x14001d32a  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x14001d331  mov     ecx, [rax+0C0h]
0x14001d337  mov     dword ptr [rbp+57h+var_A0], ecx
0x14001d33a  jmp     loc_14001D476
0x14001d33f  xor     edx, edx; SourceString
0x14001d341  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001d345  call    cs:__imp_RtlInitUnicodeString
0x14001d34c  nop     dword ptr [rax+rax+00h]
0x14001d351  lea     rdx, [rbp+57h+DestinationString]
0x14001d355  mov     rcx, rsi
0x14001d358  call    cs:__imp_IoQueryFullDriverPath
0x14001d35f  nop     dword ptr [rax+rax+00h]
0x14001d364  mov     ebx, eax
0x14001d366  test    eax, eax
0x14001d368  js      loc_14001D411
0x14001d36e  mov     r8b, dil; AllocateDestinationString
0x14001d371  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14001d375  lea     rcx, [rbp+57h+AnsiString]; DestinationString
0x14001d379  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14001d380  nop     dword ptr [rax+rax+00h]
0x14001d385  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x14001d389  xor     edx, edx; Tag
0x14001d38b  mov     ebx, eax
0x14001d38d  call    cs:__imp_ExFreePoolWithTag
0x14001d394  nop     dword ptr [rax+rax+00h]
0x14001d399  test    ebx, ebx
0x14001d39b  js      short loc_14001D40C
0x14001d39d  movzx   edx, [rbp+57h+AnsiString.Length]
0x14001d3a1  lea     ecx, [rdx-1]
0x14001d3a4  test    ecx, ecx
0x14001d3a6  jz      short loc_14001D3EF
0x14001d3a8  mov     r8, [rbp+57h+AnsiString.Buffer]
0x14001d3ac  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14001d3b1  jz      short loc_14001D3BA
0x14001d3b3  add     ecx, 0FFFFFFFFh
0x14001d3b6  jnz     short loc_14001D3AC
0x14001d3b8  jmp     short loc_14001D3EF
0x14001d3ba  cmp     ecx, edx
0x14001d3bc  jz      short loc_14001D3EF
0x14001d3be  lea     edx, [rcx+1]
0x14001d3c1  xorps   xmm0, xmm0
0x14001d3c4  add     rdx, r8; SourceString
0x14001d3c7  lea     rcx, [rbp+57h+var_80]; DestinationString
0x14001d3cb  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x14001d3cf  call    cs:__imp_RtlInitAnsiString
0x14001d3d6  nop     dword ptr [rax+rax+00h]
0x14001d3db  movaps  xmm0, xmmword ptr [rbp+57h+var_80.Length]
0x14001d3df  lea     rcx, [rbp+57h+var_30]
0x14001d3e3  movdqa  [rbp+57h+var_30], xmm0
0x14001d3e8  call    InitializeTelemetryAssertsKMWorkerInternal
0x14001d3ed  mov     ebx, eax
0x14001d3ef  lea     rcx, [rbp+57h+AnsiString]; AnsiString
0x14001d3f3  call    cs:__imp_RtlFreeAnsiString
0x14001d3fa  nop     dword ptr [rax+rax+00h]
0x14001d3ff  mov     [rbp+57h+arg_10], ebx
0x14001d402  test    ebx, ebx
0x14001d404  jns     loc_14001D23F
0x14001d40a  jmp     short loc_14001D414
0x14001d40c  mov     [rbp+57h+arg_10], ebx
0x14001d40f  jmp     short loc_14001D414
0x14001d411  mov     [rbp+57h+arg_10], eax
0x14001d414  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d41b  mov     eax, [rcx+2Ch]
0x14001d41e  test    r12b, al
0x14001d421  jz      short loc_14001D42C
0x14001d423  cmp     byte ptr [rcx+29h], 3
0x14001d427  mov     dl, dil
0x14001d42a  jnb     short loc_14001D42F
0x14001d42c  mov     dl, r15b
0x14001d42f  mov     r9, [rcx+40h]
0x14001d433  mov     rcx, [rcx+18h]
0x14001d437  mov     [rsp+110h+var_D0], ebx
0x14001d43b  lea     rbx, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x14001d442  mov     [rsp+110h+var_D8], rbx
0x14001d447  mov     [rsp+110h+var_E0], 0Dh
0x14001d44e  mov     dword ptr [rsp+110h+var_E8], r12d
0x14001d453  mov     byte ptr [rsp+110h+var_F0], 3
0x14001d458  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001d45d  mov     [rbp+57h+arg_10], r15d
0x14001d461  jmp     loc_14001D246
0x14001d466  mov     dword ptr [rbp+57h+var_A0], 0FFFFFFFFh
0x14001d46d  jmp     short loc_14001D476
0x14001d46f  mov     dword ptr [rbp+57h+var_A0], 20h ; ' '
0x14001d476  lea     rax, ?BthUsb_WdfDeviceAdd@@YAJPEAUWDFDRIVER__@@PEAUWDFDEVICE_INIT@@@Z; BthUsb_WdfDeviceAdd(WDFDRIVER__ *,WDFDEVICE_INIT *)
0x14001d47d  mov     dword ptr [rbp+57h+var_90+0Ch], 42425355h
0x14001d484  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14001d488  lea     rcx, [rbp+57h+var_A0]
0x14001d48c  lea     rax, ?BthUsb_WdfDriverUnload@@YAXPEAUWDFDRIVER__@@@Z; BthUsb_WdfDriverUnload(WDFDRIVER__ *)
0x14001d493  mov     [rsp+110h+var_E8], r15
0x14001d498  mov     qword ptr [rbp+57h+var_90], rax
0x14001d49c  xor     r9d, r9d
0x14001d49f  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14001d4a6  mov     r8, r14
0x14001d4a9  mov     [rsp+110h+var_F0], rcx
0x14001d4ae  mov     rdx, rsi
0x14001d4b1  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14001d4b8  mov     rax, [rax+3A0h]
0x14001d4bf  call    _guard_dispatch_icall
0x14001d4c4  mov     [rbp+57h+arg_10], eax
0x14001d4c7  test    eax, eax
0x14001d4c9  jns     short loc_14001D515
0x14001d4cb  mov     r8, cs:WPP_GLOBAL_Control
0x14001d4d2  mov     ecx, [r8+2Ch]
0x14001d4d6  test    r12b, cl
0x14001d4d9  jz      short loc_14001D4E1
0x14001d4db  cmp     [r8+29h], r12b
0x14001d4df  jnb     short loc_14001D4E4
0x14001d4e1  mov     dil, r15b
0x14001d4e4  mov     r9, [r8+40h]
0x14001d4e8  mov     dl, dil
0x14001d4eb  mov     rcx, [r8+18h]
0x14001d4ef  mov     [rsp+110h+var_D0], eax
0x14001d4f3  mov     [rsp+110h+var_D8], rbx
0x14001d4f8  mov     [rsp+110h+var_E0], 0Fh
0x14001d4ff  mov     dword ptr [rsp+110h+var_E8], r12d
0x14001d504  mov     byte ptr [rsp+110h+var_F0], r12b
0x14001d509  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001d50e  mov     eax, [rbp+57h+arg_10]
0x14001d511  test    eax, eax
0x14001d513  js      short loc_14001D57A
0x14001d515  mov     rcx, cs:BthDriverGlobals
0x14001d51c  lea     rax, ?BthUsb_GetCapabilities@@YAJPEAU_BTDEVICE@@PEAU_BTH_GET_CAPABILITIES_ARG@@@Z; BthUsb_GetCapabilities(_BTDEVICE *,_BTH_GET_CAPABILITIES_ARG *)
0x14001d523  mov     [rbp+57h+var_60], rax
0x14001d527  lea     r9, [rbp+57h+var_60]
0x14001d52b  lea     rax, ?BthUsb_ScoValidateChannel@@YAJPEAU_BTDEVICE@@PEAU_BTH_SCO_VALIDATE_CHANNEL_ARG@@@Z; BthUsb_ScoValidateChannel(_BTDEVICE *,_BTH_SCO_VALIDATE_CHANNEL_ARG *)
0x14001d532  mov     dword ptr [rsp+110h+var_F0], 28h ; '('
0x14001d53a  mov     [rbp+57h+var_58], rax
0x14001d53e  mov     r8, r14
0x14001d541  lea     rax, ?BthUsb_ScoAddChannel@@YAJPEAU_BTDEVICE@@PEAU_BTH_SCO_ADD_CHANNEL_ARG@@@Z; BthUsb_ScoAddChannel(_BTDEVICE *,_BTH_SCO_ADD_CHANNEL_ARG *)
0x14001d548  mov     rdx, rsi
0x14001d54b  mov     [rbp+57h+var_50], rax
0x14001d54f  lea     rax, ?BthUsb_ScoRemoveChannel@@YAJPEAU_BTDEVICE@@PEAU_BTH_SCO_REMOVE_CHANNEL_ARG@@@Z; BthUsb_ScoRemoveChannel(_BTDEVICE *,_BTH_SCO_REMOVE_CHANNEL_ARG *)
0x14001d556  mov     [rbp+57h+var_48], rax
0x14001d55a  lea     rax, ?BthUsb_ScoControlChannel@@YAJPEAU_BTDEVICE@@PEAU_BTH_SCO_CONTROL_CHANNEL_ARG@@@Z; BthUsb_ScoControlChannel(_BTDEVICE *,_BTH_SCO_CONTROL_CHANNEL_ARG *)
0x14001d561  mov     [rbp+57h+var_40], rax
0x14001d565  mov     rax, cs:qword_140013280
  ... truncated ...
```
