# DriverEntry

- ea: `0x140020078`
- end: `0x140020596`
- name: `DriverEntry`
- size: `1310`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140020010`

## callees

- `0x140001008`
- `0x140001328`
- `0x1400013e8`
- `0x140001f44`
- `0x14000466c`
- `0x140006e10`
- `0x140006fa8`
- `0x1400072a8`
- `0x140007998`
- `0x140007d00`
- `0x140007d40`
- `0x140007e40`
- `0x140008140`
- `0x14001bda0`
- `0x14001c0a4`
- `0x14001c16c`
- `0x140020078`
- `0x14002059c`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400202cb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400202cb`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400202eb`
- `ntoskrnl!EtwSetInformation` at `0x1400204f9`
- `ntoskrnl!EtwSetInformation` at `0x1400204f9`
- `ntoskrnl!EtwRegister` at `0x1400204d4`
- `ntoskrnl!EtwRegister` at `0x1400204d4`
- `ntoskrnl!ExAllocatePool2` at `0x140020217`
- `ntoskrnl!ExAllocatePool2` at `0x140020217`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400202ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400202ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002041f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140020432`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002041f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140020432`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x140020479`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x140020479`

## string_xrefs

- `0x14002027e`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // edx
  NTSTATUS v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  void *DeviceExtension; // rdi
  const char *v9; // rax
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  void *Pool2; // rax
  $18E3EACC1E717291AA7C720ECCD5C45C v15; // rdi
  PVOID SystemRoutineAddress; // rax
  int v17; // eax
  int v18; // edx
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // [rsp+20h] [rbp-E0h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  const wchar_t *v28; // [rsp+80h] [rbp-80h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  _QWORD v30[28]; // [rsp+90h] [rbp-70h] BYREF

  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_BthEnumTraceGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  v5 = wil_InitializeFeatureStaging();
  if ( v5 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_6:
      BthUnload((__int64)DriverObject, v4, v6, v7);
      return v5;
    }
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      4,
      21,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
LABEL_4:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
      v9 = NtStatusTxt(v5);
      WPP_RECORDER_SF_qs((_DWORD)DeviceExtension, v10, v11, v12, v23, (char)DriverObject, (__int64)v9);
    }
    goto LABEL_6;
  }
  memset(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0, 0x78u);
  *((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.1 + 5) = 1850045506;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = (_LIST_ENTRY *)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine;
  LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = 0x400000;
  *(_QWORD *)&WPP_MAIN_CB.Dpc.TargetInfoAsUlong = DriverObject;
  LODWORD(WPP_MAIN_CB.Dpc.DpcListEntry.Next) = 0;
  RefObj_GlobalsInit();
  LOWORD(WPP_MAIN_CB.DeviceQueue.Lock) = RegistryPath->Length;
  WORD1(WPP_MAIN_CB.DeviceQueue.Lock) = LOWORD(WPP_MAIN_CB.DeviceQueue.Lock) + 2;
  Pool2 = (void *)ExAllocatePool2(256, (unsigned __int16)(LOWORD(WPP_MAIN_CB.DeviceQueue.Lock) + 2), 1330467906);
  WPP_MAIN_CB.DeviceQueue.1 = ($18E3EACC1E717291AA7C720ECCD5C45C)Pool2;
  if ( !Pool2 )
  {
    v5 = -1073741670;
    goto LABEL_4;
  }
  memmove(Pool2, RegistryPath->Buffer, RegistryPath->Length);
  *(_WORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32 + 2 * ((unsigned __int64)RegistryPath->Length >> 1)) = 0;
  memset(v30, 0, sizeof(v30));
  v15 = WPP_MAIN_CB.DeviceQueue.1;
  v30[2] = L"DUNDevice";
  LODWORD(v30[1]) = 288;
  v30[3] = &WPP_MAIN_CB.DeviceQueue.DeviceListHead;
  LODWORD(v30[4]) = 16777217;
  v30[5] = &dword_14000AC64;
  LODWORD(v30[6]) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SystemRoutineAddress)(0x80000000LL, v15, v30, 0);
  v5 = 0;
  if ( v17 >= 0 )
    v5 = v17;
  DriverObject->DriverExtension->AddDevice = (int (__fastcall *)(_DRIVER_OBJECT *, _DEVICE_OBJECT *))BthEnumAddDevice;
  DriverObject->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))BthUnload;
  memset64(DriverObject->MajorFunction, (unsigned __int64)UnHandledDispatch, 0x1Cu);
  DriverObject->MajorFunction[0] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))BthDispatchCreate;
  DriverObject->MajorFunction[18] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))BthDispatchCleanup;
  DriverObject->MajorFunction[2] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))BthDispatchClose;
  DriverObject->MajorFunction[27] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))BthEnumPnP;
  DriverObject->MajorFunction[22] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))BthEnumPower;
  DriverObject->MajorFunction[23] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))BthEnumWmi;
  DriverObject->MajorFunction[14] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))BthEnumIoctl;
  DriverObject->MajorFunction[15] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))BthEnumInternalIoctl;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      3,
      22,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        4,
        23,
        (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
  }
  memset(&g_Policies, 0, 0x50u);
  g_PolicyStorePath = 0;
  KeInitializeSpinLock(&g_PolicyLock);
  KeInitializeSpinLock(&g_CallbackLock);
  if ( (int)BthGetPolicyRegistryLocation(&g_PolicyStorePath) >= 0 )
  {
    McGenEventRegister_EtwRegister(v20);
    if ( (int)ExSubscribeWnfStateChange(&qword_1400152C8, &WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED, 1) >= 0 )
      BthSyncWithPolicyStore();
  }
  DestinationString = (struct _UNICODE_STRING)*((_OWORD *)EventInformation - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_140015038 = 0;
  if ( !EtwRegister((LPCGUID)&DestinationString, tlgEnableCallback, &dword_140015010, &RegHandle) )
    EtwSetInformation(RegHandle, EventProviderSetTraits, EventInformation, *(unsigned __int16 *)EventInformation);
  if ( (unsigned int)dword_140015010 > 5
    && (qword_140015020 & 0x400000000000LL) != 0
    && (*(_QWORD *)&qword_140015028 & 0x400000000000LL) == *(_QWORD *)&qword_140015028 )
  {
    *(_QWORD *)&DestinationString.Length = 33556480;
    p_DestinationString = &DestinationString;
    v27 = 8;
    v28 = L"BthEnum.sys";
    v29 = 24;
    tlgWriteTransfer_EtwWriteTransfer(
      *(__int64 *)&qword_140015028,
      (unsigned __int8 *)&qword_1400139D0,
      v21,
      v22,
      4u,
      &v25);
  }
  return v5;
}

```

## disassembly

```asm
0x140020078  mov     [rsp-8+arg_10], rbx
0x14002007d  mov     [rsp-8+arg_18], rsi
0x140020082  push    rbp
0x140020083  push    rdi
0x140020084  push    r12
0x140020086  push    r14
0x140020088  push    r15
0x14002008a  lea     rbp, [rsp-80h]
0x14002008f  sub     rsp, 180h
0x140020096  mov     rax, cs:__security_cookie
0x14002009d  xor     rax, rsp
0x1400200a0  mov     [rbp+0A0h+var_30], rax
0x1400200a4  xor     r14d, r14d
0x1400200a7  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400200b2  lea     rax, WPP_ThisDir_CTLGUID_BthEnumTraceGuid
0x1400200b9  mov     qword ptr cs:WPP_MAIN_CB.Type, r14
0x1400200c0  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400200c7  mov     rdi, rdx
0x1400200ca  mov     cs:WPP_MAIN_CB.NextDevice, r14
0x1400200d1  mov     rsi, rcx
0x1400200d4  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x1400200db  mov     cs:WPP_MAIN_CB.DeviceExtension, r14
0x1400200e2  mov     cs:WPP_MAIN_CB.DeviceType, r14d
0x1400200e9  call    WppLoadTracingSupport
0x1400200ee  mov     rdx, rdi
0x1400200f1  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x1400200f8  mov     rcx, rsi
0x1400200fb  call    WppInitKm
0x140020100  call    wil_InitializeFeatureStaging
0x140020105  lea     r15, WPP_RECORDER_INITIALIZED
0x14002010c  mov     ebx, eax
0x14002010e  test    eax, eax
0x140020110  jns     loc_1400201A7
0x140020116  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14002011d  jz      short loc_140020174
0x14002011f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020126  lea     rdi, WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids
0x14002012d  mov     dword ptr [rsp+1A0h+var_178], eax
0x140020131  lea     r9d, [r14+15h]
0x140020135  lea     r8d, [r14+4]
0x140020139  mov     qword ptr [rsp+1A0h+var_180], rdi
0x14002013e  mov     rcx, [rcx+40h]
0x140020142  call    WPP_RECORDER_SF_d
0x140020147  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14002014e  jz      short loc_140020174
0x140020150  mov     rax, cs:WPP_GLOBAL_Control
0x140020157  mov     ecx, ebx
0x140020159  mov     rdi, [rax+40h]
0x14002015d  call    NtStatusTxt
0x140020162  mov     [rsp+1A0h+var_170], rax
0x140020167  mov     rcx, rdi
0x14002016a  mov     [rsp+1A0h+var_178], rsi
0x14002016f  call    WPP_RECORDER_SF_qs
0x140020174  mov     rcx, rsi
0x140020177  call    BthUnload
0x14002017c  mov     eax, ebx
0x14002017e  mov     rcx, [rbp+0A0h+var_30]
0x140020182  xor     rcx, rsp; StackCookie
0x140020185  call    __security_check_cookie
0x14002018a  lea     r11, [rsp+1A0h+var_20]
0x140020192  mov     rbx, [r11+40h]
0x140020196  mov     rsi, [r11+48h]
0x14002019a  mov     rsp, r11
0x14002019d  pop     r15
0x14002019f  pop     r14
0x1400201a1  pop     r12
0x1400201a3  pop     rdi
0x1400201a4  pop     rbp
0x1400201a5  retn
0x1400201a7  xor     edx, edx; Val
0x1400201a9  lea     rcx, WPP_MAIN_CB.Queue+10h; void *
0x1400201b0  lea     r8d, [rdx+78h]; Size
0x1400201b4  call    memset
0x1400201b9  lea     rax, WPP_MAIN_CB.Queue+18h
0x1400201c0  mov     dword ptr cs:WPP_MAIN_CB.Queue+14h, 6E457442h
0x1400201ca  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, rax
0x1400201d1  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, 400000h
0x1400201db  mov     qword ptr cs:WPP_MAIN_CB.Dpc.___u0, rsi
0x1400201e2  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, r14d
0x1400201e9  call    RefObj_GlobalsInit
0x1400201ee  movzx   eax, word ptr [rdi]
0x1400201f1  mov     r12d, 2
0x1400201f7  mov     word ptr cs:WPP_MAIN_CB.DeviceQueue.Lock, ax
0x1400201fe  mov     ecx, 100h
0x140020203  add     ax, r12w
0x140020207  mov     r8d, 4F4D5442h
0x14002020d  movzx   edx, ax
0x140020210  mov     word ptr cs:WPP_MAIN_CB.DeviceQueue.Lock+2, dx
0x140020217  call    cs:__imp_ExAllocatePool2
0x14002021e  nop     dword ptr [rax+rax+00h]
0x140020223  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4, rax
0x14002022a  test    rax, rax
0x14002022d  jnz     short loc_140020239
0x14002022f  mov     ebx, 0C000009Ah
0x140020234  jmp     loc_140020147
0x140020239  movzx   r8d, word ptr [rdi]; Size
0x14002023d  mov     rcx, rax; void *
0x140020240  mov     rdx, [rdi+8]; Src
0x140020244  call    memmove
0x140020249  movzx   edx, word ptr [rdi]
0x14002024c  lea     rcx, [rbp+0A0h+var_110]; void *
0x140020250  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x140020257  mov     r8d, 0E0h; Size
0x14002025d  shr     rdx, 1
0x140020260  mov     [rax+rdx*2], r14w
0x140020265  xor     edx, edx; Val
0x140020267  call    memset
0x14002026c  mov     rdi, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x140020273  lea     rax, aDundevice; "DUNDevice"
0x14002027a  mov     [rbp+0A0h+var_100], rax
0x14002027e  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140020285  lea     rax, WPP_MAIN_CB.DeviceQueue.DeviceListHead
0x14002028c  mov     [rbp+0A0h+var_108], 120h
0x140020293  mov     [rbp+0A0h+var_F8], rax
0x140020297  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x14002029c  lea     rax, dword_14000AC64
0x1400202a3  mov     [rbp+0A0h+var_F0], 1000001h
0x1400202aa  xorps   xmm0, xmm0
0x1400202ad  mov     [rbp+0A0h+var_E8], rax
0x1400202b1  mov     [rbp+0A0h+var_E0], r14d
0x1400202b5  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x1400202ba  call    cs:__imp_RtlInitUnicodeString
0x1400202c1  nop     dword ptr [rax+rax+00h]
0x1400202c6  lea     rcx, [rsp+1A0h+DestinationString]; SystemRoutineName
0x1400202cb  call    cs:__imp_MmGetSystemRoutineAddress
0x1400202d2  nop     dword ptr [rax+rax+00h]
0x1400202d7  lea     r8, [rbp+0A0h+var_110]
0x1400202db  mov     qword ptr [rsp+1A0h+var_180], r14
0x1400202e0  test    rax, rax
0x1400202e3  mov     rdx, rdi
0x1400202e6  mov     ecx, 80000000h
0x1400202eb  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400202f3  xor     r9d, r9d
0x1400202f6  call    _guard_dispatch_icall
0x1400202fb  test    eax, eax
0x1400202fd  lea     rcx, BthEnumAddDevice
0x140020304  mov     ebx, r14d
0x140020307  lea     rdi, [rsi+70h]
0x14002030b  cmovns  ebx, eax
0x14002030e  mov     rax, [rsi+30h]
0x140020312  mov     [rax+8], rcx
0x140020316  lea     rax, BthUnload
0x14002031d  mov     [rsi+68h], rax
0x140020321  mov     ecx, 1Ch
0x140020326  lea     rax, UnHandledDispatch
0x14002032d  rep stosq
0x140020330  lea     rax, BthDispatchCreate
0x140020337  mov     [rsi+70h], rax
0x14002033b  lea     rax, BthDispatchCleanup
0x140020342  mov     [rsi+100h], rax
0x140020349  lea     rax, BthDispatchClose
0x140020350  mov     [rsi+80h], rax
0x140020357  lea     rax, BthEnumPnP
0x14002035e  mov     [rsi+148h], rax
0x140020365  lea     rax, BthEnumPower
0x14002036c  mov     [rsi+120h], rax
0x140020373  lea     rax, BthEnumWmi
0x14002037a  mov     [rsi+128h], rax
0x140020381  lea     rax, BthEnumIoctl
0x140020388  mov     [rsi+0E0h], rax
0x14002038f  lea     rax, BthEnumInternalIoctl
0x140020396  mov     [rsi+0E8h], rax
0x14002039d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400203a4  jz      short loc_1400203F4
0x1400203a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400203ad  lea     rdi, WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids
0x1400203b4  mov     r9d, 16h
0x1400203ba  mov     qword ptr [rsp+1A0h+var_180], rdi
0x1400203bf  mov     rcx, [rcx+40h]
0x1400203c3  lea     r8d, [r9-13h]
0x1400203c7  call    WPP_RECORDER_SF_
0x1400203cc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400203d3  jz      short loc_1400203F4
0x1400203d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400203dc  mov     r9d, 17h
0x1400203e2  mov     qword ptr [rsp+1A0h+var_180], rdi
0x1400203e7  mov     rcx, [rcx+40h]
0x1400203eb  lea     r8d, [r9-13h]
0x1400203ef  call    WPP_RECORDER_SF_
0x1400203f4  test    ebx, ebx
0x1400203f6  js      loc_140020147
0x1400203fc  xor     edx, edx; Val
0x1400203fe  lea     rcx, ?g_Policies@@3UPolicies@@A; void *
0x140020405  lea     r8d, [rdx+50h]; Size
0x140020409  call    memset
0x14002040e  xorps   xmm0, xmm0
0x140020411  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x140020418  movups  xmmword ptr cs:?g_PolicyStorePath@@3U_UNICODE_STRING@@A.Length, xmm0; _UNICODE_STRING g_PolicyStorePath ...
0x14002041f  call    cs:__imp_KeInitializeSpinLock
0x140020426  nop     dword ptr [rax+rax+00h]
0x14002042b  lea     rcx, ?g_CallbackLock@@3_KA; SpinLock
0x140020432  call    cs:__imp_KeInitializeSpinLock
0x140020439  nop     dword ptr [rax+rax+00h]
0x14002043e  lea     rcx, ?g_PolicyStorePath@@3U_UNICODE_STRING@@A; DestinationString
0x140020445  call    BthGetPolicyRegistryLocation
0x14002044a  test    eax, eax
0x14002044c  js      short loc_14002048E
0x14002044e  call    McGenEventRegister_EtwRegister
0x140020453  xor     r9d, r9d
0x140020456  mov     [rsp+1A0h+var_178], r14
0x14002045b  lea     rax, ?CallbackInternal@@YAJPEAU_EX_WNF_SUBSCRIPTION@@PEBU_WNF_STATE_NAME@@KKPEBU_WNF_TYPE_ID@@PEAX@Z; CallbackInternal(_EX_WNF_SUBSCRIPTION *,_WNF_STATE_NAME const *,ulong,ulong,_WNF_TYPE_ID const *,void *)
0x140020462  lea     rdx, WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED
0x140020469  mov     qword ptr [rsp+1A0h+var_180], rax
0x14002046e  lea     rcx, qword_1400152C8
0x140020475  lea     r8d, [r9+1]
0x140020479  call    cs:__imp_ExSubscribeWnfStateChange
0x140020480  nop     dword ptr [rax+rax+00h]
0x140020485  test    eax, eax
0x140020487  js      short loc_14002048E
0x140020489  call    BthSyncWithPolicyStore
0x14002048e  cmp     cs:RegHandle, r14
0x140020495  mov     rax, cs:EventInformation
0x14002049c  movups  xmm0, xmmword ptr [rax-10h]
0x1400204a0  movdqu  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x1400204a6  jz      short loc_1400204AF
0x1400204a8  mov     ecx, 5
0x1400204ad  int     29h; Win8: RtlFailFast(ecx)
0x1400204af  xorps   xmm0, xmm0
0x1400204b2  lea     r9, RegHandle; RegHandle
0x1400204b9  lea     r8, dword_140015010; CallbackContext
0x1400204c0  lea     rdx, _tlgEnableCallback; EnableCallback
0x1400204c7  lea     rcx, [rsp+1A0h+DestinationString]; ProviderId
0x1400204cc  movdqu  cs:xmmword_140015038, xmm0
0x1400204d4  call    cs:__imp_EtwRegister
0x1400204db  nop     dword ptr [rax+rax+00h]
0x1400204e0  test    eax, eax
0x1400204e2  jnz     short loc_140020505
0x1400204e4  mov     r8, cs:EventInformation; EventInformation
0x1400204eb  mov     edx, r12d; InformationClass
0x1400204ee  mov     rcx, cs:RegHandle; RegHandle
0x1400204f5  movzx   r9d, word ptr [r8]; InformationLength
0x1400204f9  call    cs:__imp_EtwSetInformation
0x140020500  nop     dword ptr [rax+rax+00h]
0x140020505  mov     eax, cs:dword_140015010
0x14002050b  cmp     eax, 5
0x14002050e  jbe     loc_14002017C
0x140020514  mov     rcx, cs:qword_140015028; int
0x14002051b  mov     rdx, 400000000000h
0x140020525  mov     rax, cs:qword_140015020
0x14002052c  test    rdx, rax
0x14002052f  jz      loc_14002017C
0x140020535  mov     rax, rcx
0x140020538  and     rax, rdx
0x14002053b  cmp     rax, rcx
0x14002053e  jnz     loc_14002017C
0x140020544  lea     rax, [rsp+1A0h+DestinationString]
0x140020549  mov     qword ptr [rsp+1A0h+DestinationString.Length], 2000800h
0x140020552  mov     [rsp+1A0h+var_130], rax
0x140020557  lea     rdx, qword_1400139D0; int
0x14002055e  lea     rax, aBthenumSys; "BthEnum.sys"
0x140020565  mov     [rsp+1A0h+var_128], 8
0x14002056e  mov     [rbp+0A0h+var_120], rax
0x140020572  lea     rax, [rsp+1A0h+var_150]
0x140020577  mov     [rsp+1A0h+var_178], rax; __int64
0x14002057c  mov     [rsp+1A0h+var_180], 4; ULONG
0x140020584  mov     [rbp+0A0h+var_118], 18h
0x14002058c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140020591  jmp     loc_14002017C
```
