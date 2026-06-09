# MbbAdapterConfigurePacketFiltersOnSession(_MINIPORT_ADAPTER_CONTEXT *,uchar,ulong)

- ea: `0x140002278`
- end: `0x1400024c4`
- name: `?MbbAdapterConfigurePacketFiltersOnSession@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@EK@Z`
- size: `588`
- prototype: `__int64 __fastcall(KSPIN_LOCK *, char, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140009720`
- `0x14000a0a8`

## callees

- `0x140001cf8`
- `0x140002278`
- `0x140003124`
- `0x140011278`
- `0x140019b6c`
- `0x140019f78`
- `0x14001a168`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002495`
- `ntoskrnl!KeSetEvent` at `0x140002495`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400023d3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400023d3`

## pseudocode

```c
__int64 __fastcall MbbAdapterConfigurePacketFiltersOnSession(KSPIN_LOCK *a1, char a2, int a3)
{
  struct _MBB_REQUEST_MANAGER *RequestManager; // rax
  int v6; // edx
  __int64 v7; // r8
  struct _MBB_REQUEST_MANAGER *v8; // rdi
  unsigned int v9; // ebx
  int v10; // edx
  struct _MBB_REQUEST_CONTEXT *v11; // rsi
  unsigned int v12; // eax
  char v13; // r14
  bool v14; // zf
  void (__fastcall *v15)(_QWORD); // rax
  union _LARGE_INTEGER Timeout; // [rsp+30h] [rbp-20h] BYREF
  _DWORD v18[6]; // [rsp+38h] [rbp-18h] BYREF
  int v19; // [rsp+88h] [rbp+38h] BYREF

  v19 = 0;
  Timeout.QuadPart = 0;
  v18[0] = -1568027597;
  v18[1] = -1957708613;
  v18[2] = 1041477814;
  v18[3] = -538531134;
  v18[4] = 23;
  RequestManager = MbbAdapterGetRequestManager(a1);
  v8 = RequestManager;
  if ( RequestManager )
  {
    v11 = MbbReqMgrCreateRequest(RequestManager, 0, v7, &v19, 0);
    if ( v11 )
    {
      *((_QWORD *)v11 + 10) = MbbNdisGetOidHandlerByCommand((struct _MBB_COMMAND *)v18);
      *((_BYTE *)v11 + 728) = a2;
      *((_DWORD *)v11 + 183) = a3;
      _InterlockedIncrement((volatile signed __int32 *)v11 + 10);
      v12 = MbbReqMgrDispatchRequest(
              (union _LARGE_INTEGER *)v11,
              1,
              (int (*)(void *, struct _MBB_REQUEST_CONTEXT *))MbbAdapterDispatchConfigurePacketFiltersRequest,
              (void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int))MbbUtilInternalCIDCompletion,
              (void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))MbbUtilInternalCIDResponse);
      v9 = v12;
      if ( v12 == 259 )
      {
        Timeout.QuadPart = -100000000;
        if ( KeWaitForSingleObject((char *)v11 + 56, Executive, 0, 0, &Timeout) )
        {
          v9 = -1073741823;
        }
        else
        {
          v9 = *((_DWORD *)v11 + 160);
          if ( !v9 )
            v9 = *((_DWORD *)v11 + 174);
        }
      }
      else if ( v12 )
      {
        MbbReqMgrDerefRequest(v11);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          1,
          45,
          (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids);
      }
      v9 = v19;
    }
    v13 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
      WdfDriverGlobals,
      *((_QWORD *)v8 + 28));
    v14 = (*((_DWORD *)v8 + 58))-- == 1;
    if ( v14 && *((_DWORD *)v8 + 59) )
    {
      v13 = 1;
      *((_DWORD *)v8 + 60) = 1;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
      WdfDriverGlobals,
      *((_QWORD *)v8 + 28));
    if ( v13 )
    {
      v15 = (void (__fastcall *)(_QWORD))*((_QWORD *)v8 + 31);
      if ( v15 )
        v15(*((_QWORD *)v8 + 32));
      KeSetEvent((PRKEVENT)v8 + 11, 0, 0);
    }
    if ( v11 )
      MbbReqMgrDerefRequest(v11);
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
        44,
        (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids);
    }
    return (unsigned int)-1073676271;
  }
  return v9;
}

```

## disassembly

```asm
0x140002278  mov     [rsp-18h+arg_0], rbx
0x14000227d  mov     [rsp-18h+arg_8], rsi
0x140002282  push    rbp
0x140002283  push    rdi
0x140002284  push    r14
0x140002286  mov     rbp, rsp
0x140002289  sub     rsp, 50h
0x14000228d  mov     ebx, r8d
0x140002290  mov     [rbp+arg_18], 0
0x140002297  mov     r14b, dl
0x14000229a  mov     qword ptr [rbp+var_20], 0
0x1400022a2  mov     [rbp+var_18], 0A289CC33h
0x1400022a9  mov     [rbp+var_14], 8B4FBCBBh
0x1400022b0  mov     [rbp+var_10], 3E13B0B6h
0x1400022b7  mov     [rbp+var_C], 0DFE6AAC2h
0x1400022be  mov     [rbp+var_8], 17h
0x1400022c5  call    ?MbbAdapterGetRequestManager@@YAPEAU_MBB_REQUEST_MANAGER@@PEAU_MINIPORT_ADAPTER_CONTEXT@@@Z; MbbAdapterGetRequestManager(_MINIPORT_ADAPTER_CONTEXT *)
0x1400022ca  mov     rdi, rax
0x1400022cd  test    rax, rax
0x1400022d0  jnz     short loc_140002312
0x1400022d2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400022d9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400022e0  jz      short loc_140002308
0x1400022e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022e9  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x1400022f0  lea     r9d, [rdi+2Ch]
0x1400022f4  mov     [rsp+50h+Timeout], rax
0x1400022f9  lea     r8d, [rdi+1]
0x1400022fd  mov     dl, 2
0x1400022ff  mov     rcx, [rcx+40h]
0x140002303  call    WPP_RECORDER_SF_
0x140002308  mov     ebx, 0C0010011h
0x14000230d  jmp     loc_1400024AE
0x140002312  lea     r9, [rbp+arg_18]; int *
0x140002316  mov     byte ptr [rsp+50h+Timeout], 0; unsigned __int8
0x14000231b  xor     edx, edx; struct _NDIS_OID_REQUEST *
0x14000231d  mov     rcx, rdi; struct _MBB_REQUEST_MANAGER *
0x140002320  call    ?MbbReqMgrCreateRequest@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_NDIS_OID_REQUEST@@KPEAHE@Z; MbbReqMgrCreateRequest(_MBB_REQUEST_MANAGER *,_NDIS_OID_REQUEST *,ulong,int *,uchar)
0x140002325  mov     rsi, rax
0x140002328  test    rax, rax
0x14000232b  jnz     short loc_14000236B
0x14000232d  lea     rax, WPP_RECORDER_INITIALIZED
0x140002334  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000233b  jz      short loc_140002363
0x14000233d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002344  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x14000234b  lea     r9d, [rsi+2Dh]
0x14000234f  mov     [rsp+50h+Timeout], rax
0x140002354  lea     r8d, [rsi+1]
0x140002358  mov     dl, 2
0x14000235a  mov     rcx, [rcx+40h]
0x14000235e  call    WPP_RECORDER_SF_
0x140002363  mov     ebx, [rbp+arg_18]
0x140002366  jmp     loc_140002408
0x14000236b  lea     rcx, [rbp+var_18]; struct _MBB_COMMAND *
0x14000236f  call    ?MbbNdisGetOidHandlerByCommand@@YAPEAU_MBB_OID_HANDLER_ENTRY@@PEAU_MBB_COMMAND@@@Z; MbbNdisGetOidHandlerByCommand(_MBB_COMMAND *)
0x140002374  mov     [rsi+50h], rax
0x140002378  mov     [rsi+2D8h], r14b
0x14000237f  mov     [rsi+2DCh], ebx
0x140002385  lock inc dword ptr [rsi+28h]
0x140002389  lea     rax, ?MbbUtilInternalCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbUtilInternalCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140002390  mov     dl, 1; unsigned __int8
0x140002392  lea     r9, ?MbbUtilInternalCIDCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int)
0x140002399  mov     [rsp+50h+Timeout], rax; void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int)
0x14000239e  lea     r8, ?MbbAdapterDispatchConfigurePacketFiltersRequest@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z; int (*)(void *, struct _MBB_REQUEST_CONTEXT *)
0x1400023a5  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x1400023a8  call    ?MbbReqMgrDispatchRequest@@YAHPEAU_MBB_REQUEST_CONTEXT@@EP6AHPEAX0@ZP6AX10H@ZP6AX0HW4_MBB_STATUS@@PEAEK@Z@Z; MbbReqMgrDispatchRequest(_MBB_REQUEST_CONTEXT *,uchar,int (*)(void *,_MBB_REQUEST_CONTEXT *),void (*)(void *,_MBB_REQUEST_CONTEXT *,int),void (*)(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong))
0x1400023ad  mov     ebx, eax
0x1400023af  cmp     eax, 103h
0x1400023b4  jnz     short loc_1400023FC
0x1400023b6  lea     rax, [rbp+var_20]
0x1400023ba  mov     qword ptr [rbp+var_20], 0FFFFFFFFFA0A1F00h
0x1400023c2  lea     rcx, [rsi+38h]; Object
0x1400023c6  mov     [rsp+50h+Timeout], rax; Timeout
0x1400023cb  xor     r9d, r9d; Alertable
0x1400023ce  xor     r8d, r8d; WaitMode
0x1400023d1  xor     edx, edx; WaitReason
0x1400023d3  call    cs:__imp_KeWaitForSingleObject
0x1400023da  nop     dword ptr [rax+rax+00h]
0x1400023df  test    eax, eax
0x1400023e1  jz      short loc_1400023EA
0x1400023e3  mov     ebx, 0C0000001h
0x1400023e8  jmp     short loc_140002408
0x1400023ea  mov     ebx, [rsi+280h]
0x1400023f0  test    ebx, ebx
0x1400023f2  jnz     short loc_140002408
0x1400023f4  mov     ebx, [rsi+2B8h]
0x1400023fa  jmp     short loc_140002408
0x1400023fc  test    eax, eax
0x1400023fe  jz      short loc_140002408
0x140002400  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x140002403  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x140002408  mov     rax, cs:WdfFunctions_01031
0x14000240f  xor     r14b, r14b
0x140002412  mov     rdx, [rdi+0E0h]
0x140002419  mov     rcx, cs:WdfDriverGlobals
0x140002420  mov     rax, [rax+9E0h]
0x140002427  call    _guard_dispatch_icall
0x14000242c  add     dword ptr [rdi+0E8h], 0FFFFFFFFh
0x140002433  jnz     short loc_14000244B
0x140002435  cmp     dword ptr [rdi+0ECh], 0
0x14000243c  jz      short loc_14000244B
0x14000243e  mov     r14b, 1
0x140002441  mov     dword ptr [rdi+0F0h], 1
0x14000244b  mov     rax, cs:WdfFunctions_01031
0x140002452  mov     rdx, [rdi+0E0h]
0x140002459  mov     rcx, cs:WdfDriverGlobals
0x140002460  mov     rax, [rax+9E8h]
0x140002467  call    _guard_dispatch_icall
0x14000246c  test    r14b, r14b
0x14000246f  jz      short loc_1400024A1
0x140002471  mov     rax, [rdi+0F8h]
0x140002478  test    rax, rax
0x14000247b  jz      short loc_140002489
0x14000247d  mov     rcx, [rdi+100h]
0x140002484  call    _guard_dispatch_icall
0x140002489  lea     rcx, [rdi+108h]; Event
0x140002490  xor     r8d, r8d; Wait
0x140002493  xor     edx, edx; Increment
0x140002495  call    cs:__imp_KeSetEvent
0x14000249c  nop     dword ptr [rax+rax+00h]
0x1400024a1  test    rsi, rsi
0x1400024a4  jz      short loc_1400024AE
0x1400024a6  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x1400024a9  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x1400024ae  mov     rsi, [rsp+50h+arg_8]
0x1400024b3  mov     eax, ebx
0x1400024b5  mov     rbx, [rsp+50h+arg_0]
0x1400024ba  add     rsp, 50h
0x1400024be  pop     r14
0x1400024c0  pop     rdi
0x1400024c1  pop     rbp
0x1400024c2  retn
```
