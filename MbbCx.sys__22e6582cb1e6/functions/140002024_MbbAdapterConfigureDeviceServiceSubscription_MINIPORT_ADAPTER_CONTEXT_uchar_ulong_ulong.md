# MbbAdapterConfigureDeviceServiceSubscription(_MINIPORT_ADAPTER_CONTEXT *,uchar,ulong,ulong)

- ea: `0x140002024`
- end: `0x14000226f`
- name: `?MbbAdapterConfigureDeviceServiceSubscription@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@EKK@Z`
- size: `587`
- prototype: `__int64 __fastcall(KSPIN_LOCK *, char, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140009720`
- `0x14000a0a8`
- `0x14000bb48`

## callees

- `0x140001cf8`
- `0x140002024`
- `0x140003124`
- `0x140011278`
- `0x140019b6c`
- `0x140019f78`
- `0x14001a168`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002246`
- `ntoskrnl!KeSetEvent` at `0x140002246`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002184`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002184`

## pseudocode

```c
__int64 __fastcall MbbAdapterConfigureDeviceServiceSubscription(KSPIN_LOCK *a1, char a2, int a3, int a4)
{
  struct _MBB_REQUEST_MANAGER *RequestManager; // rax
  int v8; // edx
  __int64 v9; // r8
  struct _MBB_REQUEST_MANAGER *v10; // rsi
  unsigned int v11; // ebx
  int v12; // edx
  struct _MBB_REQUEST_CONTEXT *v13; // rdi
  unsigned int v14; // eax
  char v15; // r14
  bool v16; // zf
  void (__fastcall *v17)(_QWORD); // rax
  int v19; // [rsp+30h] [rbp-38h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+38h] [rbp-30h] BYREF
  _DWORD v21[10]; // [rsp+40h] [rbp-28h] BYREF

  v19 = 0;
  Timeout.QuadPart = 0;
  v21[0] = -1568027597;
  v21[1] = -1957708613;
  v21[2] = 1041477814;
  v21[3] = -538531134;
  v21[4] = 19;
  RequestManager = MbbAdapterGetRequestManager(a1);
  v10 = RequestManager;
  if ( RequestManager )
  {
    v13 = MbbReqMgrCreateRequest(RequestManager, 0, v9, &v19, 0);
    if ( v13 )
    {
      *((_QWORD *)v13 + 10) = MbbNdisGetOidHandlerByCommand((struct _MBB_COMMAND *)v21);
      *((_BYTE *)v13 + 728) = a2;
      *((_DWORD *)v13 + 183) = a3;
      *((_DWORD *)v13 + 184) = a4;
      _InterlockedIncrement((volatile signed __int32 *)v13 + 10);
      v14 = MbbReqMgrDispatchRequest(
              (union _LARGE_INTEGER *)v13,
              1,
              MbbAdapterDispatchConfigureDeviceServiceSubscriptionRequest,
              (void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int))MbbUtilInternalCIDCompletion,
              (void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))MbbUtilInternalCIDResponse);
      v11 = v14;
      if ( v14 == 259 )
      {
        Timeout.QuadPart = -100000000;
        if ( KeWaitForSingleObject((char *)v13 + 56, Executive, 0, 0, &Timeout) )
        {
          v11 = -1073741823;
        }
        else
        {
          v11 = *((_DWORD *)v13 + 160);
          if ( !v11 )
            v11 = *((_DWORD *)v13 + 174);
        }
      }
      else if ( v14 )
      {
        MbbReqMgrDerefRequest(v13);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          1,
          49,
          (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids);
      }
      v11 = v19;
    }
    v15 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
      WdfDriverGlobals,
      *((_QWORD *)v10 + 28));
    v16 = (*((_DWORD *)v10 + 58))-- == 1;
    if ( v16 && *((_DWORD *)v10 + 59) )
    {
      v15 = 1;
      *((_DWORD *)v10 + 60) = 1;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
      WdfDriverGlobals,
      *((_QWORD *)v10 + 28));
    if ( v15 )
    {
      v17 = (void (__fastcall *)(_QWORD))*((_QWORD *)v10 + 31);
      if ( v17 )
        v17(*((_QWORD *)v10 + 32));
      KeSetEvent((PRKEVENT)v10 + 11, 0, 0);
    }
    if ( v13 )
      MbbReqMgrDerefRequest(v13);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        48,
        (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids);
    }
    return (unsigned int)-1073676271;
  }
  return v11;
}

```

## disassembly

```asm
0x140002024  push    rbp
0x140002026  push    rbx
0x140002027  push    rsi
0x140002028  push    rdi
0x140002029  push    r14
0x14000202b  push    r15
0x14000202d  mov     rbp, rsp
0x140002030  sub     rsp, 68h
0x140002034  mov     ebx, r9d
0x140002037  mov     [rbp+var_38], 0
0x14000203e  mov     r14d, r8d
0x140002041  mov     qword ptr [rbp+var_30], 0
0x140002049  mov     r15b, dl
0x14000204c  mov     [rbp+var_28], 0A289CC33h
0x140002053  mov     [rbp+var_24], 8B4FBCBBh
0x14000205a  mov     [rbp+var_20], 3E13B0B6h
0x140002061  mov     [rbp+var_1C], 0DFE6AAC2h
0x140002068  mov     [rbp+var_18], 13h
0x14000206f  call    ?MbbAdapterGetRequestManager@@YAPEAU_MBB_REQUEST_MANAGER@@PEAU_MINIPORT_ADAPTER_CONTEXT@@@Z; MbbAdapterGetRequestManager(_MINIPORT_ADAPTER_CONTEXT *)
0x140002074  mov     rsi, rax
0x140002077  test    rax, rax
0x14000207a  jnz     short loc_1400020BC
0x14000207c  lea     rax, WPP_RECORDER_INITIALIZED
0x140002083  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000208a  jz      short loc_1400020B2
0x14000208c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002093  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x14000209a  lea     r9d, [rsi+30h]
0x14000209e  mov     [rsp+68h+Timeout], rax
0x1400020a3  lea     r8d, [rsi+1]
0x1400020a7  mov     dl, 2
0x1400020a9  mov     rcx, [rcx+40h]
0x1400020ad  call    WPP_RECORDER_SF_
0x1400020b2  mov     ebx, 0C0010011h
0x1400020b7  jmp     loc_14000225F
0x1400020bc  lea     r9, [rbp+var_38]; int *
0x1400020c0  mov     byte ptr [rsp+68h+Timeout], 0; unsigned __int8
0x1400020c5  xor     edx, edx; struct _NDIS_OID_REQUEST *
0x1400020c7  mov     rcx, rsi; struct _MBB_REQUEST_MANAGER *
0x1400020ca  call    ?MbbReqMgrCreateRequest@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_NDIS_OID_REQUEST@@KPEAHE@Z; MbbReqMgrCreateRequest(_MBB_REQUEST_MANAGER *,_NDIS_OID_REQUEST *,ulong,int *,uchar)
0x1400020cf  mov     rdi, rax
0x1400020d2  test    rax, rax
0x1400020d5  jnz     short loc_140002115
0x1400020d7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400020de  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400020e5  jz      short loc_14000210D
0x1400020e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020ee  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x1400020f5  lea     r9d, [rdi+31h]
0x1400020f9  mov     [rsp+68h+Timeout], rax
0x1400020fe  lea     r8d, [rdi+1]
0x140002102  mov     dl, 2
0x140002104  mov     rcx, [rcx+40h]
0x140002108  call    WPP_RECORDER_SF_
0x14000210d  mov     ebx, [rbp+var_38]
0x140002110  jmp     loc_1400021B9
0x140002115  lea     rcx, [rbp+var_28]; struct _MBB_COMMAND *
0x140002119  call    ?MbbNdisGetOidHandlerByCommand@@YAPEAU_MBB_OID_HANDLER_ENTRY@@PEAU_MBB_COMMAND@@@Z; MbbNdisGetOidHandlerByCommand(_MBB_COMMAND *)
0x14000211e  mov     [rdi+50h], rax
0x140002122  mov     [rdi+2D8h], r15b
0x140002129  mov     [rdi+2DCh], r14d
0x140002130  mov     [rdi+2E0h], ebx
0x140002136  lock inc dword ptr [rdi+28h]
0x14000213a  lea     rax, ?MbbUtilInternalCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbUtilInternalCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140002141  mov     dl, 1; unsigned __int8
0x140002143  lea     r9, ?MbbUtilInternalCIDCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int)
0x14000214a  mov     [rsp+68h+Timeout], rax; void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int)
0x14000214f  lea     r8, ?MbbAdapterDispatchConfigureDeviceServiceSubscriptionRequest@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z; int (*)(void *, struct _MBB_REQUEST_CONTEXT *)
0x140002156  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x140002159  call    ?MbbReqMgrDispatchRequest@@YAHPEAU_MBB_REQUEST_CONTEXT@@EP6AHPEAX0@ZP6AX10H@ZP6AX0HW4_MBB_STATUS@@PEAEK@Z@Z; MbbReqMgrDispatchRequest(_MBB_REQUEST_CONTEXT *,uchar,int (*)(void *,_MBB_REQUEST_CONTEXT *),void (*)(void *,_MBB_REQUEST_CONTEXT *,int),void (*)(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong))
0x14000215e  mov     ebx, eax
0x140002160  cmp     eax, 103h
0x140002165  jnz     short loc_1400021AD
0x140002167  lea     rax, [rbp+var_30]
0x14000216b  mov     qword ptr [rbp+var_30], 0FFFFFFFFFA0A1F00h
0x140002173  lea     rcx, [rdi+38h]; Object
0x140002177  mov     [rsp+68h+Timeout], rax; Timeout
0x14000217c  xor     r9d, r9d; Alertable
0x14000217f  xor     r8d, r8d; WaitMode
0x140002182  xor     edx, edx; WaitReason
0x140002184  call    cs:__imp_KeWaitForSingleObject
0x14000218b  nop     dword ptr [rax+rax+00h]
0x140002190  test    eax, eax
0x140002192  jz      short loc_14000219B
0x140002194  mov     ebx, 0C0000001h
0x140002199  jmp     short loc_1400021B9
0x14000219b  mov     ebx, [rdi+280h]
0x1400021a1  test    ebx, ebx
0x1400021a3  jnz     short loc_1400021B9
0x1400021a5  mov     ebx, [rdi+2B8h]
0x1400021ab  jmp     short loc_1400021B9
0x1400021ad  test    eax, eax
0x1400021af  jz      short loc_1400021B9
0x1400021b1  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x1400021b4  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x1400021b9  mov     rax, cs:WdfFunctions_01031
0x1400021c0  xor     r14b, r14b
0x1400021c3  mov     rdx, [rsi+0E0h]
0x1400021ca  mov     rcx, cs:WdfDriverGlobals
0x1400021d1  mov     rax, [rax+9E0h]
0x1400021d8  call    _guard_dispatch_icall
0x1400021dd  add     dword ptr [rsi+0E8h], 0FFFFFFFFh
0x1400021e4  jnz     short loc_1400021FC
0x1400021e6  cmp     dword ptr [rsi+0ECh], 0
0x1400021ed  jz      short loc_1400021FC
0x1400021ef  mov     r14b, 1
0x1400021f2  mov     dword ptr [rsi+0F0h], 1
0x1400021fc  mov     rax, cs:WdfFunctions_01031
0x140002203  mov     rdx, [rsi+0E0h]
0x14000220a  mov     rcx, cs:WdfDriverGlobals
0x140002211  mov     rax, [rax+9E8h]
0x140002218  call    _guard_dispatch_icall
0x14000221d  test    r14b, r14b
0x140002220  jz      short loc_140002252
0x140002222  mov     rax, [rsi+0F8h]
0x140002229  test    rax, rax
0x14000222c  jz      short loc_14000223A
0x14000222e  mov     rcx, [rsi+100h]
0x140002235  call    _guard_dispatch_icall
0x14000223a  lea     rcx, [rsi+108h]; Event
0x140002241  xor     r8d, r8d; Wait
0x140002244  xor     edx, edx; Increment
0x140002246  call    cs:__imp_KeSetEvent
0x14000224d  nop     dword ptr [rax+rax+00h]
0x140002252  test    rdi, rdi
0x140002255  jz      short loc_14000225F
0x140002257  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x14000225a  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14000225f  mov     eax, ebx
0x140002261  add     rsp, 68h
0x140002265  pop     r15
0x140002267  pop     r14
0x140002269  pop     rdi
0x14000226a  pop     rsi
0x14000226b  pop     rbx
0x14000226c  pop     rbp
0x14000226d  retn
```
