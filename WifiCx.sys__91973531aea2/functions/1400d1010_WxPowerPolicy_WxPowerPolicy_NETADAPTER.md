# WxPowerPolicy::WxPowerPolicy(NETADAPTER__ *)

- ea: `0x1400d1010`
- end: `0x1400d1376`
- name: `??0WxPowerPolicy@@QEAA@PEAUNETADAPTER__@@@Z`
- size: `870`
- prototype: `WxPowerPolicy *__fastcall(WxPowerPolicy *__hidden this, struct NETADAPTER__ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14011f51c`

## callees

- `0x14000c778`
- `0x14001a630`
- `0x140032580`
- `0x1400cfab8`
- `0x1400d1010`
- `0x1400dc4c8`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400e0100`

## string_xrefs

- `0x1400d12b2`: `System\CurrentControlSet\Services\WlanSvc`

## pseudocode

```c
WxPowerPolicy *__fastcall WxPowerPolicy::WxPowerPolicy(WxPowerPolicy *this, struct NETADAPTER__ *a2)
{
  WxAdapter *v3; // rax
  struct WDFDEVICE__ *Device; // rax
  __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rax
  CPropertyCache *v8; // rax
  int v9; // edx
  int v10; // eax
  __int64 v11; // rdx
  int v12; // edx
  CAdapter *v13; // rcx
  unsigned int v14; // ebx
  __int64 v16; // [rsp+28h] [rbp-250h]
  int v17; // [rsp+28h] [rbp-250h]
  unsigned int v18; // [rsp+30h] [rbp-248h] BYREF
  unsigned __int8 *v19; // [rsp+38h] [rbp-240h] BYREF
  WCHAR SourceString[264]; // [rsp+40h] [rbp-238h] BYREF

  *(_BYTE *)this = 0;
  *(_QWORD *)((char *)this + 4) = 0;
  *(_QWORD *)((char *)this + 12) = 0;
  *((_DWORD *)this + 5) = 0;
  *((_QWORD *)this + 3) = a2;
  *((_QWORD *)this + 4) = 0;
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 6) = a2;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = &WxWakeOnClientDriverDiagnostic::`vftable';
  *((_DWORD *)this + 20) = 1;
  *((_QWORD *)this + 12) = a2;
  *((_BYTE *)this + 104) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 11) = &WxWakeOnClientDriverDiagnostic::`vftable';
  *((_DWORD *)this + 32) = 2;
  *((_QWORD *)this + 18) = a2;
  *((_BYTE *)this + 152) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 17) = &WxWakeOnClientDriverDiagnostic::`vftable';
  *((_DWORD *)this + 44) = 3;
  *((_QWORD *)this + 24) = a2;
  *((_BYTE *)this + 200) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 23) = &WxWakeOnClientDriverDiagnostic::`vftable';
  *((_DWORD *)this + 56) = 4;
  *((_QWORD *)this + 30) = a2;
  *((_BYTE *)this + 248) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 29) = &WxWakeOnClientDriverDiagnostic::`vftable';
  *((_DWORD *)this + 68) = 5;
  *((_QWORD *)this + 36) = a2;
  *((_BYTE *)this + 296) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 35) = &WxWakeOnClientDriverDiagnostic::`vftable';
  *((_DWORD *)this + 80) = 6;
  *(_OWORD *)((char *)this + 328) = 0;
  *((_QWORD *)this + 43) = 0;
  v3 = (WxAdapter *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
                      WdfDriverGlobals,
                      *((_QWORD *)this + 3),
                      off_14010EB80);
  Device = WxAdapter::GetDevice(v3);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         Device,
         off_14010E308);
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         *((_QWORD *)this + 3),
         off_14010EB80);
  v18 = 0;
  v7 = *(_QWORD *)(v5 + 64);
  v19 = 0;
  v8 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(v7 + 8))(v5 + 64);
  if ( (unsigned int)CPropertyCache::GetPropertyBuffer(v8, 0x19u, &v18, &v19) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      v17 = *(_DWORD *)(v6 + 536);
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        10,
        (__int64)WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids,
        v17);
    }
    v10 = 0;
  }
  else
  {
    v10 = *((_DWORD *)v19 + 141);
  }
  *((_DWORD *)this + 87) = v10;
  v18 = 0;
  memset(SourceString, 0, 0x208u);
  if ( !(unsigned int)KmWlanStateSeparation_GetMutableRegistryKey(
                        SourceString,
                        v11,
                        L"System\\CurrentControlSet\\Services\\WlanSvc",
                        0)
    && !(unsigned int)CAdapter::ReadRegDword(v13, SourceString, L"OverrideQoSActionFrameWakeRequirement", &v18) )
  {
    v14 = v18;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v16) = v18;
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        1,
        11,
        (__int64)WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids,
        v16);
    }
    *(_BYTE *)this = v14 != 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v16) = *(unsigned __int8 *)this;
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      12,
      (__int64)WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids,
      v16);
  }
  return this;
}

```

## disassembly

```asm
0x1400d1010  mov     [rsp+arg_8], rbx
0x1400d1015  mov     [rsp+arg_10], rsi
0x1400d101a  push    rdi
0x1400d101b  push    r12
0x1400d101d  push    r14
0x1400d101f  sub     rsp, 260h
0x1400d1026  mov     rax, cs:__security_cookie
0x1400d102d  xor     rax, rsp
0x1400d1030  mov     [rsp+278h+var_28], rax
0x1400d1038  mov     byte ptr [rcx], 0
0x1400d103b  xor     eax, eax
0x1400d103d  mov     [rcx+4], rax
0x1400d1041  xorps   xmm0, xmm0
0x1400d1044  mov     [rcx+0Ch], rax
0x1400d1048  mov     rdi, rcx
0x1400d104b  mov     [rcx+14h], eax
0x1400d104e  mov     [rcx+18h], rdx
0x1400d1052  mov     [rcx+20h], rax
0x1400d1056  mov     [rcx+38h], al
0x1400d1059  mov     [rcx+30h], rdx
0x1400d105d  mov     [rcx+40h], rax
0x1400d1061  mov     [rcx+48h], rax
0x1400d1065  lea     rax, ??_7WxWakeOnClientDriverDiagnostic@@6B@; const WxWakeOnClientDriverDiagnostic::`vftable'
0x1400d106c  mov     [rcx+28h], rax
0x1400d1070  xor     eax, eax
0x1400d1072  mov     dword ptr [rcx+50h], 1
0x1400d1079  mov     [rcx+60h], rdx
0x1400d107d  mov     byte ptr [rcx+68h], 0
0x1400d1081  mov     [rcx+70h], rax
0x1400d1085  mov     [rcx+78h], rax
0x1400d1089  lea     rax, ??_7WxWakeOnClientDriverDiagnostic@@6B@; const WxWakeOnClientDriverDiagnostic::`vftable'
0x1400d1090  mov     [rcx+58h], rax
0x1400d1094  xor     eax, eax
0x1400d1096  mov     dword ptr [rcx+80h], 2
0x1400d10a0  mov     [rcx+90h], rdx
0x1400d10a7  mov     byte ptr [rcx+98h], 0
0x1400d10ae  mov     [rcx+0A0h], rax
0x1400d10b5  mov     [rcx+0A8h], rax
0x1400d10bc  lea     rax, ??_7WxWakeOnClientDriverDiagnostic@@6B@; const WxWakeOnClientDriverDiagnostic::`vftable'
0x1400d10c3  mov     [rcx+88h], rax
0x1400d10ca  xor     eax, eax
0x1400d10cc  mov     dword ptr [rcx+0B0h], 3
0x1400d10d6  mov     [rcx+0C0h], rdx
0x1400d10dd  mov     byte ptr [rcx+0C8h], 0
0x1400d10e4  mov     [rcx+0D0h], rax
0x1400d10eb  mov     [rcx+0D8h], rax
0x1400d10f2  lea     rax, ??_7WxWakeOnClientDriverDiagnostic@@6B@; const WxWakeOnClientDriverDiagnostic::`vftable'
0x1400d10f9  mov     [rcx+0B8h], rax
0x1400d1100  xor     eax, eax
0x1400d1102  mov     dword ptr [rcx+0E0h], 4
0x1400d110c  mov     [rcx+0F0h], rdx
0x1400d1113  mov     byte ptr [rcx+0F8h], 0
0x1400d111a  mov     [rcx+100h], rax
0x1400d1121  mov     [rcx+108h], rax
0x1400d1128  lea     rax, ??_7WxWakeOnClientDriverDiagnostic@@6B@; const WxWakeOnClientDriverDiagnostic::`vftable'
0x1400d112f  mov     [rcx+0E8h], rax
0x1400d1136  xor     eax, eax
0x1400d1138  mov     dword ptr [rcx+110h], 5
0x1400d1142  mov     [rcx+120h], rdx
0x1400d1149  mov     byte ptr [rcx+128h], 0
0x1400d1150  mov     [rcx+130h], rax
0x1400d1157  mov     [rcx+138h], rax
0x1400d115e  lea     rax, ??_7WxWakeOnClientDriverDiagnostic@@6B@; const WxWakeOnClientDriverDiagnostic::`vftable'
0x1400d1165  mov     [rcx+118h], rax
0x1400d116c  xor     eax, eax
0x1400d116e  mov     dword ptr [rcx+140h], 6
0x1400d1178  movups  xmmword ptr [rcx+148h], xmm0
0x1400d117f  mov     [rcx+158h], rax
0x1400d1186  mov     rax, cs:WdfFunctions_01031
0x1400d118d  mov     rdx, [rcx+18h]
0x1400d1191  mov     r8, cs:off_14010EB80
0x1400d1198  mov     rcx, cs:WdfDriverGlobals
0x1400d119f  mov     rax, [rax+650h]
0x1400d11a6  call    _guard_dispatch_icall
0x1400d11ab  mov     rcx, rax; this
0x1400d11ae  call    ?GetDevice@WxAdapter@@QEAAPEAUWDFDEVICE__@@XZ; WxAdapter::GetDevice(void)
0x1400d11b3  mov     r8, cs:off_14010E308
0x1400d11ba  mov     rdx, rax
0x1400d11bd  mov     rax, cs:WdfFunctions_01031
0x1400d11c4  mov     rcx, cs:WdfDriverGlobals
0x1400d11cb  mov     rax, [rax+650h]
0x1400d11d2  call    _guard_dispatch_icall
0x1400d11d7  mov     r8, cs:off_14010EB80
0x1400d11de  mov     rbx, rax
0x1400d11e1  mov     rax, cs:WdfFunctions_01031
0x1400d11e8  mov     rdx, [rdi+18h]
0x1400d11ec  mov     rcx, cs:WdfDriverGlobals
0x1400d11f3  mov     rax, [rax+650h]
0x1400d11fa  call    _guard_dispatch_icall
0x1400d11ff  mov     rsi, rax
0x1400d1202  lea     rcx, [rbx+40h]
0x1400d1206  mov     [rsp+278h+var_248], 0
0x1400d120e  mov     rax, [rcx]
0x1400d1211  mov     [rsp+278h+var_240], 0
0x1400d121a  mov     rax, [rax+8]
0x1400d121e  call    _guard_dispatch_icall
0x1400d1223  lea     r9, [rsp+278h+var_240]; unsigned __int8 **
0x1400d1228  mov     edx, 19h; unsigned int
0x1400d122d  lea     r8, [rsp+278h+var_248]; unsigned int *
0x1400d1232  mov     rcx, rax; this
0x1400d1235  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400d123a  lea     r14, WPP_RECORDER_INITIALIZED
0x1400d1241  lea     r12, WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids
0x1400d1248  test    eax, eax
0x1400d124a  jz      short loc_1400D1284
0x1400d124c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400d1253  jz      short loc_1400D1280
0x1400d1255  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d125c  mov     r9d, 0Ah
0x1400d1262  mov     eax, [rsi+218h]
0x1400d1268  mov     dl, 2
0x1400d126a  mov     dword ptr [rsp+278h+var_250], eax
0x1400d126e  mov     [rsp+278h+var_258], r12
0x1400d1273  mov     rcx, [rcx+40h]
0x1400d1277  lea     r8d, [r9-9]
0x1400d127b  call    WPP_RECORDER_SF_d
0x1400d1280  xor     eax, eax
0x1400d1282  jmp     short loc_1400D128F
0x1400d1284  mov     rax, [rsp+278h+var_240]
0x1400d1289  mov     eax, [rax+234h]
0x1400d128f  mov     [rdi+15Ch], eax
0x1400d1295  lea     rcx, [rsp+278h+SourceString]; void *
0x1400d129a  xor     edx, edx; Val
0x1400d129c  mov     [rsp+278h+var_248], 0
0x1400d12a4  mov     r8d, 208h; Size
0x1400d12aa  call    memset
0x1400d12af  xor     r9d, r9d
0x1400d12b2  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Wl"...
0x1400d12b9  lea     rcx, [rsp+278h+SourceString]; SourceString
0x1400d12be  call    KmWlanStateSeparation_GetMutableRegistryKey
0x1400d12c3  test    eax, eax
0x1400d12c5  jnz     short loc_1400D1318
0x1400d12c7  lea     r9, [rsp+278h+var_248]; unsigned int *
0x1400d12cc  lea     r8, aOverrideqosact; "OverrideQoSActionFrameWakeRequirement"
0x1400d12d3  lea     rdx, [rsp+278h+SourceString]; unsigned __int16 *
0x1400d12d8  call    ?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z; CAdapter::ReadRegDword(ushort *,ushort *,ulong *)
0x1400d12dd  test    eax, eax
0x1400d12df  jnz     short loc_1400D1318
0x1400d12e1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400d12e8  mov     ebx, [rsp+278h+var_248]
0x1400d12ec  jz      short loc_1400D1311
0x1400d12ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d12f5  lea     r9d, [rax+0Bh]
0x1400d12f9  mov     dword ptr [rsp+278h+var_250], ebx
0x1400d12fd  lea     r8d, [rax+1]
0x1400d1301  mov     dl, 4
0x1400d1303  mov     [rsp+278h+var_258], r12
0x1400d1308  mov     rcx, [rcx+40h]
0x1400d130c  call    WPP_RECORDER_SF_d
0x1400d1311  test    ebx, ebx
0x1400d1313  setnz   al
0x1400d1316  mov     [rdi], al
0x1400d1318  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400d131f  jz      short loc_1400D1349
0x1400d1321  movzx   ecx, byte ptr [rdi]
0x1400d1324  mov     r9d, 0Ch
0x1400d132a  mov     dword ptr [rsp+278h+var_250], ecx
0x1400d132e  mov     dl, 4
0x1400d1330  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1337  mov     [rsp+278h+var_258], r12
0x1400d133c  lea     r8d, [r9-0Bh]
0x1400d1340  mov     rcx, [rcx+40h]
0x1400d1344  call    WPP_RECORDER_SF_d
0x1400d1349  mov     rax, rdi
0x1400d134c  mov     rcx, [rsp+278h+var_28]
0x1400d1354  xor     rcx, rsp; StackCookie
0x1400d1357  call    __security_check_cookie
0x1400d135c  lea     r11, [rsp+278h+var_18]
0x1400d1364  mov     rbx, [r11+28h]
0x1400d1368  mov     rsi, [r11+30h]
0x1400d136c  mov     rsp, r11
0x1400d136f  pop     r14
0x1400d1371  pop     r12
0x1400d1373  pop     rdi
0x1400d1374  retn
```
