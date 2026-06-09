# Fdo::Make(WDFDEVICE_INIT *)

- ea: `0x140019008`
- end: `0x140019463`
- name: `?Make@Fdo@@SAJPEAUWDFDEVICE_INIT@@@Z`
- size: `1115`
- prototype: `__int64 __fastcall(struct WDFDEVICE_INIT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x140017c10`

## callees

- `0x1400017d4`
- `0x140001c74`
- `0x140001ca8`
- `0x140001da0`
- `0x14000bcc8`
- `0x14000ddc0`
- `0x14000de00`
- `0x14000e1c0`
- `0x140017858`
- `0x14001868c`
- `0x140019008`
- `0x14001946c`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogCreate` at `0x14001914e`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14001914e`

## pseudocode

```c
__int64 __fastcall Fdo::Make(struct WDFDEVICE_INIT *a1)
{
  int v1; // eax
  int v2; // edx
  int v3; // edi
  const char *v5; // r8
  __int128 *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  bool v9; // zf
  PDEVICE_OBJECT v10; // rcx
  __int128 *v11; // rax
  int v12; // edx
  int v13; // edx
  Fdo *ContextFromObject; // rax
  struct _BTDEVICE **v15; // rdi
  struct _BTDEVICE **v16; // rsi
  __int64 v17; // rdx
  int v18; // r8d
  int v19; // r14d
  unsigned int RecorderLog; // eax
  __int64 v21; // r10
  int v22; // edx
  int Device; // ebx
  struct RECORDER_LOG__ *v24; // [rsp+50h] [rbp-B0h] BYREF
  struct RECORDER_LOG__ *v25; // [rsp+58h] [rbp-A8h] BYREF
  struct WDFDEVICE__ *v26; // [rsp+60h] [rbp-A0h] BYREF
  struct WDFDEVICE_INIT *v27; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[18]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v29; // [rsp+100h] [rbp+0h] BYREF
  __int128 v30; // [rsp+110h] [rbp+10h]
  __int128 v31; // [rsp+120h] [rbp+20h] BYREF
  __int64 v32; // [rsp+130h] [rbp+30h]

  v27 = a1;
  v1 = ((__int64 (__fastcall *)(__int64, struct WDFDEVICE_INIT *))qword_140013270)(BthDriverGlobals, a1);
  v3 = v1;
  if ( v1 < 0 )
  {
    LOBYTE(v2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      12,
      (__int64)WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids,
      v1);
    return (unsigned int)v3;
  }
  v5 = "Fdo";
  v32 = 0;
  *((_QWORD *)&v30 + 1) = 0x1000000000LL;
  *(_QWORD *)&v30 = 0;
  v6 = &v31;
  v7 = 16;
  v31 = 0;
  LOBYTE(v31) = 0;
  v29 = 0;
  LODWORD(v29) = 56;
  v8 = 2147483646;
  do
  {
    if ( !v8 )
      break;
    if ( !*v5 )
      break;
    *(_BYTE *)v6 = *v5++;
    v6 = (__int128 *)((char *)v6 + 1);
    --v8;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v24 = 0;
  v10 = WPP_GLOBAL_Control;
  v11 = (__int128 *)((char *)v6 - 1);
  if ( !v9 )
    v11 = v6;
  *(_BYTE *)v11 = 0;
  v32 = 0x200000002LL;
  *(_QWORD *)((char *)&v29 + 4) = 0x200042425355LL;
  HIDWORD(v29) = 256;
  v3 = imp_WppRecorderLogCreate(v10, &v29, &v24);
  if ( v3 < 0 )
  {
    LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      13,
      (__int64)WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids,
      v3);
    goto LABEL_20;
  }
  memset(v28, 0, sizeof(v28));
  if ( LOBYTE(WPP_MAIN_CB.DeviceQueue.Lock) )
  {
    if ( (unsigned int)WdfStructureCount <= 0x29 )
      LODWORD(v28[0]) = -1;
    else
      LODWORD(v28[0]) = *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32 + 328LL);
  }
  else
  {
    LODWORD(v28[0]) = 144;
  }
  v28[5] = Fdo::EvtDevicePrepareHardwareThunk;
  v28[6] = Fdo::EvtDeviceReleaseHardwareThunk;
  v28[1] = Fdo::EvtDeviceD0EntryThunk;
  v28[3] = Fdo::EvtDeviceD0ExitThunk;
  ((void (__fastcall *)(_LIST_ENTRY *, struct WDFDEVICE_INIT *, _QWORD *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[27].Blink)(
    WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
    v27,
    v28);
  v26 = 0;
  v29 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  if ( LOBYTE(WPP_MAIN_CB.DeviceQueue.Lock) )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v29) = -1;
    else
      LODWORD(v29) = *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32 + 304LL);
  }
  else
  {
    LODWORD(v29) = 56;
  }
  v32 = (__int64)off_140013060;
  *((_QWORD *)&v30 + 1) = 0x100000001LL;
  *((_QWORD *)&v29 + 1) = WdfCpp::ObjectContext<WDFDEVICE__ *,Fdo,1>::EvtObjectContextCleanupThunk;
  v3 = ((__int64 (__fastcall *)(_LIST_ENTRY *, struct WDFDEVICE_INIT **, __int128 *, struct WDFDEVICE__ **))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[37].Blink)(
         WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
         &v27,
         &v29,
         &v26);
  if ( v3 < 0 )
  {
    LOBYTE(v13) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v13,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      14,
      (__int64)WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids,
      v3);
LABEL_20:
    if ( v24 )
      WppRecorderLogCloseFunction(v24);
    return (unsigned int)v3;
  }
  ContextFromObject = Fdo::GetContextFromObject(v26);
  if ( ContextFromObject )
  {
    v25 = v24;
    v24 = 0;
    v15 = (struct _BTDEVICE **)Fdo::Fdo(ContextFromObject);
  }
  else
  {
    v15 = 0;
  }
  v16 = v15 + 2;
  LODWORD(v25) = 4;
  v19 = ((__int64 (__fastcall *)(__int64, struct WDFDEVICE__ *, struct RECORDER_LOG__ **, struct _BTDEVICE **))BthFunctions)(
          BthDriverGlobals,
          v26,
          &v25,
          v15 + 2);
  if ( v19 >= 0 )
  {
    Device = BthUsb_PnpCreateDevice(*v16, v17, v18);
    if ( Device >= 0 )
    {
      v15[3] = (struct _BTDEVICE *)(*v16)->MiniportContext;
      Fdo::RegisterPLDRCapability((Fdo *)v15);
      if ( v24 )
        WppRecorderLogCloseFunction(v24);
      return 0;
    }
    else
    {
      if ( v24 )
        WppRecorderLogCloseFunction(v24);
      return (unsigned int)Device;
    }
  }
  else
  {
    RecorderLog = (unsigned int)Fdo::GetRecorderLog((Fdo *)v15);
    WPP_RECORDER_AND_TRACE_SF_qd(
      *(_QWORD *)(v21 + 24),
      v22,
      (unsigned int)*v15,
      RecorderLog,
      2,
      1,
      15,
      (__int64)WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids,
      (char)*v15,
      v19);
    if ( v24 )
      WppRecorderLogCloseFunction(v24);
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x140019008  mov     [rsp-8+arg_8], rbx
0x14001900d  mov     [rsp-8+arg_10], rsi
0x140019012  push    rbp
0x140019013  push    rdi
0x140019014  push    r14
0x140019016  lea     rbp, [rsp-40h]
0x14001901b  sub     rsp, 140h
0x140019022  mov     rax, cs:__security_cookie
0x140019029  xor     rax, rsp
0x14001902c  mov     [rbp+50h+var_18], rax
0x140019030  mov     rax, cs:qword_140013270
0x140019037  mov     rdx, rcx
0x14001903a  mov     [rsp+150h+var_E8], rcx
0x14001903f  mov     rcx, cs:BthDriverGlobals
0x140019046  call    _guard_dispatch_icall
0x14001904b  mov     edi, eax
0x14001904d  test    eax, eax
0x14001904f  jns     short loc_1400190A6
0x140019051  mov     r8, cs:WPP_GLOBAL_Control
0x140019058  mov     ebx, 1
0x14001905d  mov     ecx, [r8+2Ch]
0x140019061  test    bl, cl
0x140019063  jz      short loc_140019070
0x140019065  cmp     byte ptr [r8+29h], 2
0x14001906a  jb      short loc_140019070
0x14001906c  mov     dl, bl
0x14001906e  jmp     short loc_140019072
0x140019070  xor     dl, dl
0x140019072  mov     r9, [r8+40h]
0x140019076  lea     rcx, WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids
0x14001907d  mov     dword ptr [rsp+150h+var_110], edi
0x140019081  mov     [rsp+150h+var_118], rcx
0x140019086  mov     rcx, [r8+18h]
0x14001908a  mov     [rsp+150h+var_120], 0Ch
0x140019091  mov     [rsp+150h+var_128], ebx
0x140019095  mov     [rsp+150h+var_130], 2
0x14001909a  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001909f  mov     eax, edi
0x1400190a1  jmp     loc_14001943E
0x1400190a6  xor     eax, eax
0x1400190a8  lea     r8, aFdo; "Fdo"
0x1400190af  xorps   xmm0, xmm0
0x1400190b2  mov     [rbp+50h+var_20], rax
0x1400190b6  movups  [rbp+50h+var_40], xmm0
0x1400190ba  mov     qword ptr [rbp+50h+var_40], rax
0x1400190be  lea     rdx, [rbp+50h+var_30]
0x1400190c2  lea     ecx, [rax+10h]
0x1400190c5  mov     byte ptr [rbp+50h+var_40+8], al
0x1400190c8  lea     r14d, [rax+38h]
0x1400190cc  mov     dword ptr [rbp+50h+var_40+0Ch], ecx
0x1400190cf  movups  [rbp+50h+var_30], xmm0
0x1400190d3  mov     byte ptr [rbp+50h+var_30], al
0x1400190d6  lea     ebx, [rcx-0Fh]
0x1400190d9  movups  [rbp+50h+var_50], xmm0
0x1400190dd  mov     dword ptr [rbp+50h+var_50], r14d
0x1400190e1  mov     eax, 7FFFFFFEh
0x1400190e6  test    rax, rax
0x1400190e9  jz      short loc_140019104
0x1400190eb  mov     r9b, [r8]
0x1400190ee  test    r9b, r9b
0x1400190f1  jz      short loc_140019104
0x1400190f3  mov     [rdx], r9b
0x1400190f6  add     r8, rbx
0x1400190f9  add     rdx, rbx
0x1400190fc  sub     rax, rbx
0x1400190ff  sub     rcx, rbx
0x140019102  jnz     short loc_1400190E6
0x140019104  test    rcx, rcx
0x140019107  mov     [rsp+150h+var_100], 0
0x140019110  mov     rcx, cs:WPP_GLOBAL_Control
0x140019117  lea     rax, [rdx-1]
0x14001911b  cmovnz  rax, rdx
0x14001911f  lea     r8, [rsp+150h+var_100]
0x140019124  lea     rdx, [rbp+50h+var_50]
0x140019128  mov     byte ptr [rax], 0
0x14001912b  mov     dword ptr [rbp+50h+var_20], 2
0x140019132  mov     dword ptr [rbp+50h+var_20+4], 2
0x140019139  mov     dword ptr [rbp+50h+var_50+4], 42425355h
0x140019140  mov     dword ptr [rbp+50h+var_50+8], 2000h
0x140019147  mov     dword ptr [rbp+50h+var_50+0Ch], 100h
0x14001914e  call    cs:__imp_imp_WppRecorderLogCreate
0x140019155  nop     dword ptr [rax+rax+00h]
0x14001915a  mov     edi, eax
0x14001915c  test    eax, eax
0x14001915e  jns     short loc_1400191C1
0x140019160  mov     r8, cs:WPP_GLOBAL_Control
0x140019167  mov     ecx, [r8+2Ch]
0x14001916b  test    bl, cl
0x14001916d  jz      short loc_14001917A
0x14001916f  cmp     byte ptr [r8+29h], 2
0x140019174  jb      short loc_14001917A
0x140019176  mov     dl, bl
0x140019178  jmp     short loc_14001917C
0x14001917a  xor     dl, dl
0x14001917c  mov     dword ptr [rsp+150h+var_110], edi
0x140019180  lea     rcx, WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids
0x140019187  mov     [rsp+150h+var_118], rcx
0x14001918c  mov     [rsp+150h+var_120], 0Dh
0x140019193  mov     r9, [r8+40h]
0x140019197  mov     rcx, [r8+18h]
0x14001919b  mov     [rsp+150h+var_128], ebx
0x14001919f  mov     [rsp+150h+var_130], 2
0x1400191a4  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400191a9  mov     rcx, [rsp+150h+var_100]; struct RECORDER_LOG__ *
0x1400191ae  test    rcx, rcx
0x1400191b1  jz      loc_14001909F
0x1400191b7  call    ?WppRecorderLogCloseFunction@@YAXPEAURECORDER_LOG__@@@Z; WppRecorderLogCloseFunction(RECORDER_LOG__ *)
0x1400191bc  jmp     loc_14001909F
0x1400191c1  mov     esi, 90h
0x1400191c6  lea     rcx, [rsp+150h+var_E0]; void *
0x1400191cb  mov     r8d, esi; Size
0x1400191ce  xor     edx, edx; Val
0x1400191d0  call    memset
0x1400191d5  or      edi, 0FFFFFFFFh
0x1400191d8  cmp     byte ptr cs:WPP_MAIN_CB.DeviceQueue.Lock, 0
0x1400191df  jz      short loc_140019203
0x1400191e1  cmp     cs:WdfStructureCount, 29h ; ')'
0x1400191e8  jbe     short loc_1400191FD
0x1400191ea  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x1400191f1  mov     ecx, [rax+148h]
0x1400191f7  mov     [rsp+150h+var_E0], ecx
0x1400191fb  jmp     short loc_140019207
0x1400191fd  mov     [rsp+150h+var_E0], edi
0x140019201  jmp     short loc_140019207
0x140019203  mov     [rsp+150h+var_E0], esi
0x140019207  mov     rdx, [rsp+150h+var_E8]
0x14001920c  lea     rax, ?EvtDevicePrepareHardwareThunk@Fdo@@CAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@1@Z; Fdo::EvtDevicePrepareHardwareThunk(WDFDEVICE__ *,WDFCMRESLIST__ *,WDFCMRESLIST__ *)
0x140019213  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14001921a  lea     r8, [rsp+150h+var_E0]
0x14001921f  mov     [rbp+50h+var_B8], rax
0x140019223  lea     rax, ?EvtDeviceReleaseHardwareThunk@Fdo@@CAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@@Z; Fdo::EvtDeviceReleaseHardwareThunk(WDFDEVICE__ *,WDFCMRESLIST__ *)
0x14001922a  mov     [rbp+50h+var_B0], rax
0x14001922e  lea     rax, ?EvtDeviceD0EntryThunk@Fdo@@CAJPEAUWDFDEVICE__@@W4_WDF_POWER_DEVICE_STATE@@@Z; Fdo::EvtDeviceD0EntryThunk(WDFDEVICE__ *,_WDF_POWER_DEVICE_STATE)
0x140019235  mov     [rsp+150h+var_D8], rax
0x14001923a  lea     rax, ?EvtDeviceD0ExitThunk@Fdo@@CAJPEAUWDFDEVICE__@@W4_WDF_POWER_DEVICE_STATE@@@Z; Fdo::EvtDeviceD0ExitThunk(WDFDEVICE__ *,_WDF_POWER_DEVICE_STATE)
0x140019241  mov     [rbp+50h+var_C8], rax
0x140019245  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14001924c  mov     rax, [rax+1B8h]
0x140019253  call    _guard_dispatch_icall
0x140019258  xorps   xmm0, xmm0
0x14001925b  mov     [rsp+150h+var_F0], 0
0x140019264  xor     eax, eax
0x140019266  cmp     byte ptr cs:WPP_MAIN_CB.DeviceQueue.Lock, al
0x14001926c  movups  [rbp+50h+var_50], xmm0
0x140019270  mov     [rbp+50h+var_20], rax
0x140019274  movups  [rbp+50h+var_40], xmm0
0x140019278  movups  [rbp+50h+var_30], xmm0
0x14001927c  jz      short loc_14001929E
0x14001927e  cmp     cs:WdfStructureCount, 26h ; '&'
0x140019285  jbe     short loc_140019299
0x140019287  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x14001928e  mov     ecx, [rax+130h]
0x140019294  mov     dword ptr [rbp+50h+var_50], ecx
0x140019297  jmp     short loc_1400192A2
0x140019299  mov     dword ptr [rbp+50h+var_50], edi
0x14001929c  jmp     short loc_1400192A2
0x14001929e  mov     dword ptr [rbp+50h+var_50], r14d
0x1400192a2  mov     rax, cs:off_140013060
0x1400192a9  lea     r9, [rsp+150h+var_F0]
0x1400192ae  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400192b5  lea     r8, [rbp+50h+var_50]
0x1400192b9  mov     [rbp+50h+var_20], rax
0x1400192bd  lea     rdx, [rsp+150h+var_E8]
0x1400192c2  lea     rax, ?EvtObjectContextCleanupThunk@?$ObjectContext@PEAUWDFDEVICE__@@VFdo@@$00@WdfCpp@@KAXPEAX@Z; WdfCpp::ObjectContext<WDFDEVICE__ *,Fdo,1>::EvtObjectContextCleanupThunk(void *)
0x1400192c9  mov     dword ptr [rbp+50h+var_40+8], ebx
0x1400192cc  mov     qword ptr [rbp+50h+var_50+8], rax
0x1400192d0  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x1400192d7  mov     dword ptr [rbp+50h+var_40+0Ch], ebx
0x1400192da  mov     rax, [rax+258h]
0x1400192e1  call    _guard_dispatch_icall
0x1400192e6  mov     edi, eax
0x1400192e8  test    eax, eax
0x1400192ea  jns     short loc_140019324
0x1400192ec  mov     r8, cs:WPP_GLOBAL_Control
0x1400192f3  mov     ecx, [r8+2Ch]
0x1400192f7  test    bl, cl
0x1400192f9  jz      short loc_140019306
0x1400192fb  cmp     byte ptr [r8+29h], 2
0x140019300  jb      short loc_140019306
0x140019302  mov     dl, bl
0x140019304  jmp     short loc_140019308
0x140019306  xor     dl, dl
0x140019308  mov     dword ptr [rsp+150h+var_110], edi
0x14001930c  lea     rcx, WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids
0x140019313  mov     [rsp+150h+var_118], rcx
0x140019318  mov     [rsp+150h+var_120], 0Eh
0x14001931f  jmp     loc_140019193
0x140019324  mov     rcx, [rsp+150h+var_F0]; struct WDFDEVICE__ *
0x140019329  call    ?GetContextFromObject@Fdo@@CAPEAV1@PEAUWDFDEVICE__@@@Z; Fdo::GetContextFromObject(WDFDEVICE__ *)
0x14001932e  test    rax, rax
0x140019331  jz      short loc_140019358
0x140019333  mov     rcx, [rsp+150h+var_100]
0x140019338  lea     rdx, [rsp+150h+var_F8]
0x14001933d  mov     [rsp+150h+var_F8], rcx
0x140019342  mov     rcx, rax; this
0x140019345  mov     [rsp+150h+var_100], 0
0x14001934e  call    ??0Fdo@@AEAA@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAURECORDER_LOG__@@P6AXPEAU1@@Z$1?WppRecorderLogCloseFunction@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Fdo::Fdo(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>>)
0x140019353  mov     rdi, rax
0x140019356  jmp     short loc_14001935A
0x140019358  xor     edi, edi
0x14001935a  mov     rax, cs:BthFunctions
0x140019361  lea     rsi, [rdi+10h]
0x140019365  mov     rdx, [rsp+150h+var_F0]
0x14001936a  lea     r8, [rsp+150h+var_F8]
0x14001936f  mov     rcx, cs:BthDriverGlobals
0x140019376  mov     r9, rsi
0x140019379  mov     dword ptr [rsp+150h+var_F8], 4
0x140019381  call    _guard_dispatch_icall
0x140019386  mov     r14d, eax
0x140019389  test    eax, eax
0x14001938b  jns     short loc_1400193FA
0x14001938d  mov     r10, cs:WPP_GLOBAL_Control
0x140019394  mov     ecx, [r10+2Ch]
0x140019398  test    bl, cl
0x14001939a  jz      short loc_1400193A7
0x14001939c  cmp     byte ptr [r10+29h], 2
0x1400193a1  jb      short loc_1400193A7
0x1400193a3  mov     dl, bl
0x1400193a5  jmp     short loc_1400193A9
0x1400193a7  xor     dl, dl
0x1400193a9  mov     rcx, rdi; this
0x1400193ac  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1400193b1  mov     r8, [rdi]
0x1400193b4  lea     rcx, WPP_f9ea356a715c3570a55843a4975aeeb6_Traceguids
0x1400193bb  mov     [rsp+150h+var_108], r14d
0x1400193c0  mov     r9, rax
0x1400193c3  mov     [rsp+150h+var_110], r8
0x1400193c8  mov     [rsp+150h+var_118], rcx
0x1400193cd  mov     rcx, [r10+18h]
0x1400193d1  mov     [rsp+150h+var_120], 0Fh
0x1400193d8  mov     [rsp+150h+var_128], ebx
0x1400193dc  mov     [rsp+150h+var_130], 2
0x1400193e1  call    WPP_RECORDER_AND_TRACE_SF_qd
0x1400193e6  mov     rcx, [rsp+150h+var_100]; struct RECORDER_LOG__ *
0x1400193eb  test    rcx, rcx
0x1400193ee  jz      short loc_1400193F5
0x1400193f0  call    ?WppRecorderLogCloseFunction@@YAXPEAURECORDER_LOG__@@@Z; WppRecorderLogCloseFunction(RECORDER_LOG__ *)
0x1400193f5  mov     eax, r14d
0x1400193f8  jmp     short loc_14001943E
0x1400193fa  mov     rcx, [rsi]; struct _BTDEVICE *
0x1400193fd  call    ?BthUsb_PnpCreateDevice@@YAJPEAU_BTDEVICE@@@Z; BthUsb_PnpCreateDevice(_BTDEVICE *)
0x140019402  mov     ebx, eax
0x140019404  test    eax, eax
0x140019406  jns     short loc_14001941B
0x140019408  mov     rcx, [rsp+150h+var_100]; struct RECORDER_LOG__ *
0x14001940d  test    rcx, rcx
0x140019410  jz      short loc_140019417
0x140019412  call    ?WppRecorderLogCloseFunction@@YAXPEAURECORDER_LOG__@@@Z; WppRecorderLogCloseFunction(RECORDER_LOG__ *)
0x140019417  mov     eax, ebx
0x140019419  jmp     short loc_14001943E
0x14001941b  mov     rax, [rsi]
0x14001941e  mov     rcx, [rax]
0x140019421  mov     [rdi+18h], rcx
0x140019425  mov     rcx, rdi; this
0x140019428  call    ?RegisterPLDRCapability@Fdo@@AEAAXXZ; Fdo::RegisterPLDRCapability(void)
0x14001942d  mov     rcx, [rsp+150h+var_100]; struct RECORDER_LOG__ *
0x140019432  test    rcx, rcx
0x140019435  jz      short loc_14001943C
0x140019437  call    ?WppRecorderLogCloseFunction@@YAXPEAURECORDER_LOG__@@@Z; WppRecorderLogCloseFunction(RECORDER_LOG__ *)
0x14001943c  xor     eax, eax
0x14001943e  mov     rcx, [rbp+50h+var_18]
0x140019442  xor     rcx, rsp; StackCookie
0x140019445  call    __security_check_cookie
0x14001944a  lea     r11, [rsp+150h+var_10]
0x140019452  mov     rbx, [r11+28h]
0x140019456  mov     rsi, [r11+30h]
0x14001945a  mov     rsp, r11
0x14001945d  pop     r14
0x14001945f  pop     rdi
0x140019460  pop     rbp
0x140019461  retn
```
