# MbbAdapterQueryDeviceServices(_MINIPORT_ADAPTER_CONTEXT *)

- ea: `0x140003ab0`
- end: `0x140003d2a`
- name: `?MbbAdapterQueryDeviceServices@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(KSPIN_LOCK *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000bb48`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x140003124`
- `0x140003ab0`
- `0x140011278`
- `0x140019b6c`
- `0x140019f78`
- `0x14001a168`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140003cf9`
- `ntoskrnl!KeSetEvent` at `0x140003cf9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003c37`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003c37`

## pseudocode

```c
__int64 __fastcall MbbAdapterQueryDeviceServices(KSPIN_LOCK *a1)
{
  struct _MBB_REQUEST_MANAGER *RequestManager; // rax
  int v2; // edx
  __int64 v3; // r8
  struct _MBB_REQUEST_MANAGER *v4; // rsi
  unsigned int LowPart; // edi
  int v6; // edx
  union _LARGE_INTEGER *v7; // rbx
  int v8; // edx
  unsigned int v9; // eax
  char v10; // r15
  bool v11; // zf
  void (__fastcall *v12)(_QWORD); // rax
  _DWORD v14[8]; // [rsp+30h] [rbp-20h] BYREF
  int v15; // [rsp+78h] [rbp+28h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+80h] [rbp+30h] BYREF

  v15 = 0;
  Timeout.QuadPart = 0;
  v14[0] = -1568027597;
  v14[1] = -1957708613;
  v14[2] = 1041477814;
  v14[3] = -538531134;
  v14[4] = 16;
  RequestManager = MbbAdapterGetRequestManager(a1);
  v4 = RequestManager;
  if ( RequestManager )
  {
    v7 = (union _LARGE_INTEGER *)MbbReqMgrCreateRequest(RequestManager, 0, v3, &v15, 0);
    if ( v7 )
    {
      v7[10].QuadPart = (LONGLONG)MbbNdisGetOidHandlerByCommand((struct _MBB_COMMAND *)v14);
      _InterlockedIncrement((volatile signed __int32 *)&v7[5]);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 4;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          1,
          20,
          (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids,
          v7[2].LowPart);
      }
      v9 = MbbReqMgrDispatchRequest(
             v7,
             1,
             (int (*)(void *, struct _MBB_REQUEST_CONTEXT *))MbbAdapterDispatchQueryDeviceServicesRequest,
             (void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int))MbbUtilInternalCIDCompletion,
             (void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))MbbUtilInternalCIDResponse);
      LowPart = v9;
      if ( v9 == 259 )
      {
        Timeout.QuadPart = -100000000;
        if ( KeWaitForSingleObject(&v7[7], Executive, 0, 0, &Timeout) )
        {
          LowPart = -1073741823;
        }
        else
        {
          LowPart = v7[80].LowPart;
          if ( !LowPart )
            LowPart = v7[87].LowPart;
        }
      }
      else if ( v9 )
      {
        MbbReqMgrDerefRequest((struct _MBB_REQUEST_CONTEXT *)v7);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          19,
          (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids);
      }
      LowPart = v15;
    }
    v10 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
      WdfDriverGlobals,
      *((_QWORD *)v4 + 28));
    v11 = (*((_DWORD *)v4 + 58))-- == 1;
    if ( v11 && *((_DWORD *)v4 + 59) )
    {
      v10 = 1;
      *((_DWORD *)v4 + 60) = 1;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
      WdfDriverGlobals,
      *((_QWORD *)v4 + 28));
    if ( v10 )
    {
      v12 = (void (__fastcall *)(_QWORD))*((_QWORD *)v4 + 31);
      if ( v12 )
        v12(*((_QWORD *)v4 + 32));
      KeSetEvent((PRKEVENT)v4 + 11, 0, 0);
    }
    if ( v7 )
      MbbReqMgrDerefRequest((struct _MBB_REQUEST_CONTEXT *)v7);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v2,
        1,
        18,
        (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids);
    }
    return (unsigned int)-1073676271;
  }
  return LowPart;
}

```

## disassembly

```asm
0x140003ab0  mov     [rsp-18h+arg_0], rbx
0x140003ab5  mov     [rsp-18h+arg_18], rsi
0x140003aba  push    rbp
0x140003abb  push    rdi
0x140003abc  push    r15
0x140003abe  mov     rbp, rsp
0x140003ac1  sub     rsp, 50h
0x140003ac5  mov     [rbp+arg_8], 0
0x140003acc  mov     qword ptr [rbp+arg_10], 0
0x140003ad4  mov     [rbp+var_20], 0A289CC33h
0x140003adb  mov     [rbp+var_1C], 8B4FBCBBh
0x140003ae2  mov     [rbp+var_18], 3E13B0B6h
0x140003ae9  mov     [rbp+var_14], 0DFE6AAC2h
0x140003af0  mov     [rbp+var_10], 10h
0x140003af7  call    ?MbbAdapterGetRequestManager@@YAPEAU_MBB_REQUEST_MANAGER@@PEAU_MINIPORT_ADAPTER_CONTEXT@@@Z; MbbAdapterGetRequestManager(_MINIPORT_ADAPTER_CONTEXT *)
0x140003afc  mov     rsi, rax
0x140003aff  test    rax, rax
0x140003b02  jnz     short loc_140003B44
0x140003b04  lea     rax, WPP_RECORDER_INITIALIZED
0x140003b0b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003b12  jz      short loc_140003B3A
0x140003b14  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b1b  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x140003b22  lea     r9d, [rsi+12h]
0x140003b26  mov     [rsp+50h+Timeout], rax
0x140003b2b  lea     r8d, [rsi+1]
0x140003b2f  mov     dl, 2
0x140003b31  mov     rcx, [rcx+40h]
0x140003b35  call    WPP_RECORDER_SF_
0x140003b3a  mov     edi, 0C0010011h
0x140003b3f  jmp     loc_140003D12
0x140003b44  lea     r9, [rbp+arg_8]; int *
0x140003b48  mov     byte ptr [rsp+50h+Timeout], 0; unsigned __int8
0x140003b4d  xor     edx, edx; struct _NDIS_OID_REQUEST *
0x140003b4f  mov     rcx, rsi; struct _MBB_REQUEST_MANAGER *
0x140003b52  call    ?MbbReqMgrCreateRequest@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_NDIS_OID_REQUEST@@KPEAHE@Z; MbbReqMgrCreateRequest(_MBB_REQUEST_MANAGER *,_NDIS_OID_REQUEST *,ulong,int *,uchar)
0x140003b57  mov     rbx, rax
0x140003b5a  test    rax, rax
0x140003b5d  jnz     short loc_140003B9D
0x140003b5f  lea     rax, WPP_RECORDER_INITIALIZED
0x140003b66  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003b6d  jz      short loc_140003B95
0x140003b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b76  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x140003b7d  lea     r9d, [rbx+13h]
0x140003b81  mov     [rsp+50h+Timeout], rax
0x140003b86  lea     r8d, [rbx+1]
0x140003b8a  mov     dl, 2
0x140003b8c  mov     rcx, [rcx+40h]
0x140003b90  call    WPP_RECORDER_SF_
0x140003b95  mov     edi, [rbp+arg_8]
0x140003b98  jmp     loc_140003C6C
0x140003b9d  lea     rcx, [rbp+var_20]; struct _MBB_COMMAND *
0x140003ba1  call    ?MbbNdisGetOidHandlerByCommand@@YAPEAU_MBB_OID_HANDLER_ENTRY@@PEAU_MBB_COMMAND@@@Z; MbbNdisGetOidHandlerByCommand(_MBB_COMMAND *)
0x140003ba6  mov     [rbx+50h], rax
0x140003baa  lock inc dword ptr [rbx+28h]
0x140003bae  lea     rax, WPP_RECORDER_INITIALIZED
0x140003bb5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003bbc  jz      short loc_140003BED
0x140003bbe  mov     eax, [rbx+10h]
0x140003bc1  mov     r9d, 14h
0x140003bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bce  mov     dl, 4
0x140003bd0  mov     [rsp+50h+var_28], eax
0x140003bd4  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x140003bdb  mov     [rsp+50h+Timeout], rax
0x140003be0  lea     r8d, [r9-13h]
0x140003be4  mov     rcx, [rcx+40h]
0x140003be8  call    WPP_RECORDER_SF_d
0x140003bed  lea     rax, ?MbbUtilInternalCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbUtilInternalCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140003bf4  mov     dl, 1; unsigned __int8
0x140003bf6  lea     r9, ?MbbUtilInternalCIDCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int)
0x140003bfd  mov     [rsp+50h+Timeout], rax; void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int)
0x140003c02  lea     r8, ?MbbAdapterDispatchQueryDeviceServicesRequest@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z; int (*)(void *, struct _MBB_REQUEST_CONTEXT *)
0x140003c09  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140003c0c  call    ?MbbReqMgrDispatchRequest@@YAHPEAU_MBB_REQUEST_CONTEXT@@EP6AHPEAX0@ZP6AX10H@ZP6AX0HW4_MBB_STATUS@@PEAEK@Z@Z; MbbReqMgrDispatchRequest(_MBB_REQUEST_CONTEXT *,uchar,int (*)(void *,_MBB_REQUEST_CONTEXT *),void (*)(void *,_MBB_REQUEST_CONTEXT *,int),void (*)(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong))
0x140003c11  mov     edi, eax
0x140003c13  cmp     eax, 103h
0x140003c18  jnz     short loc_140003C60
0x140003c1a  lea     rax, [rbp+arg_10]
0x140003c1e  mov     qword ptr [rbp+arg_10], 0FFFFFFFFFA0A1F00h
0x140003c26  lea     rcx, [rbx+38h]; Object
0x140003c2a  mov     [rsp+50h+Timeout], rax; Timeout
0x140003c2f  xor     r9d, r9d; Alertable
0x140003c32  xor     r8d, r8d; WaitMode
0x140003c35  xor     edx, edx; WaitReason
0x140003c37  call    cs:__imp_KeWaitForSingleObject
0x140003c3e  nop     dword ptr [rax+rax+00h]
0x140003c43  test    eax, eax
0x140003c45  jz      short loc_140003C4E
0x140003c47  mov     edi, 0C0000001h
0x140003c4c  jmp     short loc_140003C6C
0x140003c4e  mov     edi, [rbx+280h]
0x140003c54  test    edi, edi
0x140003c56  jnz     short loc_140003C6C
0x140003c58  mov     edi, [rbx+2B8h]
0x140003c5e  jmp     short loc_140003C6C
0x140003c60  test    eax, eax
0x140003c62  jz      short loc_140003C6C
0x140003c64  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140003c67  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x140003c6c  mov     rax, cs:WdfFunctions_01031
0x140003c73  xor     r15b, r15b
0x140003c76  mov     rdx, [rsi+0E0h]
0x140003c7d  mov     rcx, cs:WdfDriverGlobals
0x140003c84  mov     rax, [rax+9E0h]
0x140003c8b  call    _guard_dispatch_icall
0x140003c90  add     dword ptr [rsi+0E8h], 0FFFFFFFFh
0x140003c97  jnz     short loc_140003CAF
0x140003c99  cmp     dword ptr [rsi+0ECh], 0
0x140003ca0  jz      short loc_140003CAF
0x140003ca2  mov     r15b, 1
0x140003ca5  mov     dword ptr [rsi+0F0h], 1
0x140003caf  mov     rax, cs:WdfFunctions_01031
0x140003cb6  mov     rdx, [rsi+0E0h]
0x140003cbd  mov     rcx, cs:WdfDriverGlobals
0x140003cc4  mov     rax, [rax+9E8h]
0x140003ccb  call    _guard_dispatch_icall
0x140003cd0  test    r15b, r15b
0x140003cd3  jz      short loc_140003D05
0x140003cd5  mov     rax, [rsi+0F8h]
0x140003cdc  test    rax, rax
0x140003cdf  jz      short loc_140003CED
0x140003ce1  mov     rcx, [rsi+100h]
0x140003ce8  call    _guard_dispatch_icall
0x140003ced  lea     rcx, [rsi+108h]; Event
0x140003cf4  xor     r8d, r8d; Wait
0x140003cf7  xor     edx, edx; Increment
0x140003cf9  call    cs:__imp_KeSetEvent
0x140003d00  nop     dword ptr [rax+rax+00h]
0x140003d05  test    rbx, rbx
0x140003d08  jz      short loc_140003D12
0x140003d0a  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140003d0d  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x140003d12  lea     r11, [rsp+50h+var_s0]
0x140003d17  mov     eax, edi
0x140003d19  mov     rbx, [r11+20h]
0x140003d1d  mov     rsi, [r11+38h]
0x140003d21  mov     rsp, r11
0x140003d24  pop     r15
0x140003d26  pop     rdi
0x140003d27  pop     rbp
0x140003d28  retn
```
