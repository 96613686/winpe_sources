# MbbOpen(_MINIPORT_ADAPTER_CONTEXT *)

- ea: `0x1400174d8`
- end: `0x1400178d7`
- name: `?MbbOpen@@YAJPEAU_MINIPORT_ADAPTER_CONTEXT@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c648`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x140003124`
- `0x1400174d8`
- `0x140019b6c`
- `0x140019f78`
- `0x14001a168`
- `0x140047e90`
- `0x140048340`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400175c6`
- `ntoskrnl!KeSetEvent` at `0x14001786e`
- `ntoskrnl!KeSetEvent` at `0x1400175c6`
- `ntoskrnl!KeSetEvent` at `0x14001786e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400176b7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400176b7`

## pseudocode

```c
__int64 __fastcall MbbOpen(PKSPIN_LOCK SpinLock)
{
  struct _MBB_REQUEST_CONTEXT *v1; // rsi
  struct _MBB_REQUEST_MANAGER *v2; // rdi
  unsigned int v4; // r14d
  char v5; // bl
  bool v6; // zf
  void (__fastcall *v7)(_QWORD); // rax
  struct _MBB_REQUEST_MANAGER *RequestManager; // rax
  __int64 v9; // r8
  struct _MBB_REQUEST_CONTEXT *v10; // rax
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  int v13; // edx
  int v14; // r9d
  char v15; // bp
  void (__fastcall *v16)(_QWORD); // rax
  int v18; // [rsp+70h] [rbp+8h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+80h] [rbp+18h] BYREF

  v1 = 0;
  v2 = 0;
  Timeout.QuadPart = 0;
  v18 = 0;
  v4 = 0;
  while ( 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        1,
        175,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
    if ( v2 )
    {
      v5 = 0;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
        WdfDriverGlobals,
        *((_QWORD *)v2 + 28));
      v6 = (*((_DWORD *)v2 + 58))-- == 1;
      if ( v6 && *((_DWORD *)v2 + 59) )
      {
        v5 = 1;
        *((_DWORD *)v2 + 60) = 1;
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
        WdfDriverGlobals,
        *((_QWORD *)v2 + 28));
      if ( v5 )
      {
        v7 = (void (__fastcall *)(_QWORD))*((_QWORD *)v2 + 31);
        if ( v7 )
          v7(*((_QWORD *)v2 + 32));
        KeSetEvent((PRKEVENT)v2 + 11, 0, 0);
      }
    }
    if ( v1 )
    {
      MbbReqMgrDerefRequest(v1);
      v1 = 0;
    }
    RequestManager = MbbAdapterGetRequestManager(SpinLock);
    v2 = RequestManager;
    if ( !RequestManager )
      break;
    v10 = MbbReqMgrCreateRequest(RequestManager, 0, v9, &v18, 0);
    v1 = v10;
    if ( !v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          177,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
      v11 = v18;
      goto LABEL_39;
    }
    ++v4;
    _InterlockedAdd((volatile signed __int32 *)v10 + 10, 1u);
    memset(SpinLock + 146, 0, 0x60u);
    *((_QWORD *)v1 + 10) = SpinLock + 146;
    SpinLock[155] = (KSPIN_LOCK)&MbbOpenDoneHandler;
    *((_DWORD *)v1 + 147) = 1;
    v18 = MbbReqMgrDispatchRequest(
            (union _LARGE_INTEGER *)v1,
            1,
            (int (*)(void *, struct _MBB_REQUEST_CONTEXT *))MbbSendOpenMsg,
            (void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int))MbbUtilInternalCIDCompletion,
            (void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))MbbUtilInternalCIDResponse);
    v11 = v18;
    if ( v18 == 259 )
    {
      Timeout.QuadPart = -120000000LL * v4;
      v12 = KeWaitForSingleObject((char *)v1 + 56, Executive, 0, 0, &Timeout);
      v18 = v12;
      v11 = v12;
      if ( v12 )
      {
        if ( v12 != 258 )
          goto LABEL_39;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_32;
        v14 = 181;
        goto LABEL_22;
      }
      v11 = *((_DWORD *)v1 + 160);
      v18 = v11;
      if ( !v11 )
      {
        v11 = *((_DWORD *)v1 + 174);
        v18 = v11;
        if ( v11 != -1073741643 )
          goto LABEL_39;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_32;
        v14 = 178;
        goto LABEL_22;
      }
      if ( v11 != -1073741643 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            1,
            179,
            (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
            v11);
        }
LABEL_39:
        v15 = 0;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
          WdfDriverGlobals,
          *((_QWORD *)v2 + 28));
        v6 = (*((_DWORD *)v2 + 58))-- == 1;
        if ( v6 && *((_DWORD *)v2 + 59) )
        {
          v15 = 1;
          *((_DWORD *)v2 + 60) = 1;
        }
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
          WdfDriverGlobals,
          *((_QWORD *)v2 + 28));
        if ( v15 )
        {
          v16 = (void (__fastcall *)(_QWORD))*((_QWORD *)v2 + 31);
          if ( v16 )
            v16(*((_QWORD *)v2 + 32));
          KeSetEvent((PRKEVENT)v2 + 11, 0, 0);
        }
        goto LABEL_49;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = 180;
LABEL_22:
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          v14,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
      }
    }
    else
    {
      if ( !v18 )
        goto LABEL_39;
      MbbReqMgrDerefRequest(v1);
      if ( v11 != -1073741643 && v11 != 258 )
        goto LABEL_39;
    }
LABEL_32:
    if ( v4 >= 3 )
      goto LABEL_39;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      176,
      (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
  v11 = -1073676271;
LABEL_49:
  if ( v1 )
    MbbReqMgrDerefRequest(v1);
  if ( v11 == 258 )
    return (unsigned int)-1073741643;
  return v11;
}

```

## disassembly

```asm
0x1400174d8  mov     rax, rsp
0x1400174db  push    rbx
0x1400174dc  push    rbp
0x1400174dd  push    rsi
0x1400174de  push    rdi
0x1400174df  push    r12
0x1400174e1  push    r13
0x1400174e3  push    r14
0x1400174e5  sub     rsp, 30h
0x1400174e9  xor     esi, esi
0x1400174eb  lea     r13, WPP_RECORDER_INITIALIZED
0x1400174f2  xor     edi, edi
0x1400174f4  mov     [rax+18h], rsi
0x1400174f8  mov     rbp, rcx
0x1400174fb  mov     [rax+8], esi
0x1400174fe  xor     r14d, r14d
0x140017501  lea     r12d, [rsi+1]
0x140017505  lea     rbx, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001750c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140017513  jz      short loc_140017535
0x140017515  mov     rcx, cs:WPP_GLOBAL_Control
0x14001751c  mov     r9d, 0AFh
0x140017522  mov     r8d, r12d
0x140017525  mov     [rsp+68h+Timeout], rbx
0x14001752a  mov     dl, 4
0x14001752c  mov     rcx, [rcx+40h]
0x140017530  call    WPP_RECORDER_SF_
0x140017535  test    rdi, rdi
0x140017538  jz      loc_1400175D9
0x14001753e  mov     rax, cs:WdfFunctions_01031
0x140017545  xor     bl, bl
0x140017547  mov     rdx, [rdi+0E0h]
0x14001754e  mov     rcx, cs:WdfDriverGlobals
0x140017555  mov     rax, [rax+9E0h]
0x14001755c  call    _guard_dispatch_icall
0x140017561  add     dword ptr [rdi+0E8h], 0FFFFFFFFh
0x140017568  jnz     short loc_14001757D
0x14001756a  cmp     dword ptr [rdi+0ECh], 0
0x140017571  jz      short loc_14001757D
0x140017573  mov     bl, r12b
0x140017576  mov     [rdi+0F0h], r12d
0x14001757d  mov     rax, cs:WdfFunctions_01031
0x140017584  mov     rdx, [rdi+0E0h]
0x14001758b  mov     rcx, cs:WdfDriverGlobals
0x140017592  mov     rax, [rax+9E8h]
0x140017599  call    _guard_dispatch_icall
0x14001759e  test    bl, bl
0x1400175a0  jz      short loc_1400175D2
0x1400175a2  mov     rax, [rdi+0F8h]
0x1400175a9  test    rax, rax
0x1400175ac  jz      short loc_1400175BA
0x1400175ae  mov     rcx, [rdi+100h]
0x1400175b5  call    _guard_dispatch_icall
0x1400175ba  lea     rcx, [rdi+108h]; Event
0x1400175c1  xor     r8d, r8d; Wait
0x1400175c4  xor     edx, edx; Increment
0x1400175c6  call    cs:__imp_KeSetEvent
0x1400175cd  nop     dword ptr [rax+rax+00h]
0x1400175d2  lea     rbx, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400175d9  test    rsi, rsi
0x1400175dc  jz      short loc_1400175E8
0x1400175de  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x1400175e1  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x1400175e6  xor     esi, esi
0x1400175e8  mov     rcx, rbp; SpinLock
0x1400175eb  call    ?MbbAdapterGetRequestManager@@YAPEAU_MBB_REQUEST_MANAGER@@PEAU_MINIPORT_ADAPTER_CONTEXT@@@Z; MbbAdapterGetRequestManager(_MINIPORT_ADAPTER_CONTEXT *)
0x1400175f0  mov     rdi, rax
0x1400175f3  test    rax, rax
0x1400175f6  jz      loc_14001787C
0x1400175fc  lea     r9, [rsp+68h+arg_0]; int *
0x140017601  mov     byte ptr [rsp+68h+Timeout], 0; unsigned __int8
0x140017606  xor     edx, edx; struct _NDIS_OID_REQUEST *
0x140017608  mov     rcx, rax; struct _MBB_REQUEST_MANAGER *
0x14001760b  call    ?MbbReqMgrCreateRequest@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_NDIS_OID_REQUEST@@KPEAHE@Z; MbbReqMgrCreateRequest(_MBB_REQUEST_MANAGER *,_NDIS_OID_REQUEST *,ulong,int *,uchar)
0x140017610  mov     rsi, rax
0x140017613  test    rax, rax
0x140017616  jz      loc_1400177B7
0x14001761c  add     r14d, r12d
0x14001761f  lock add [rax+28h], r12d
0x140017624  xor     edx, edx; Val
0x140017626  lea     rbx, [rbp+490h]
0x14001762d  mov     rcx, rbx; void *
0x140017630  lea     r8d, [rdx+60h]; Size
0x140017634  call    memset
0x140017639  lea     rax, ?MbbOpenDoneHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbOpenDoneHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140017640  mov     [rsi+50h], rbx
0x140017644  mov     [rbp+4D8h], rax
0x14001764b  lea     r9, ?MbbUtilInternalCIDCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int)
0x140017652  lea     rax, ?MbbUtilInternalCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbUtilInternalCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140017659  mov     [rsi+24Ch], r12d
0x140017660  lea     r8, ?MbbSendOpenMsg@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z; int (*)(void *, struct _MBB_REQUEST_CONTEXT *)
0x140017667  mov     [rsp+68h+Timeout], rax; void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int)
0x14001766c  mov     dl, r12b; unsigned __int8
0x14001766f  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x140017672  call    ?MbbReqMgrDispatchRequest@@YAHPEAU_MBB_REQUEST_CONTEXT@@EP6AHPEAX0@ZP6AX10H@ZP6AX0HW4_MBB_STATUS@@PEAEK@Z@Z; MbbReqMgrDispatchRequest(_MBB_REQUEST_CONTEXT *,uchar,int (*)(void *,_MBB_REQUEST_CONTEXT *),void (*)(void *,_MBB_REQUEST_CONTEXT *,int),void (*)(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong))
0x140017677  mov     [rsp+68h+arg_0], eax
0x14001767b  mov     ebx, eax
0x14001767d  cmp     eax, 103h
0x140017682  jnz     loc_140017756
0x140017688  lea     eax, [r14+r14*2]
0x14001768c  xor     r9d, r9d; Alertable
0x14001768f  shl     eax, 2
0x140017692  xor     r8d, r8d; WaitMode
0x140017695  imul    rcx, rax, 0FFFFFFFFFF676980h
0x14001769c  lea     rax, [rsp+68h+arg_10]
0x1400176a4  xor     edx, edx; WaitReason
0x1400176a6  mov     qword ptr [rsp+68h+arg_10], rcx
0x1400176ae  lea     rcx, [rsi+38h]; Object
0x1400176b2  mov     [rsp+68h+Timeout], rax; Timeout
0x1400176b7  call    cs:__imp_KeWaitForSingleObject
0x1400176be  nop     dword ptr [rax+rax+00h]
0x1400176c3  mov     [rsp+68h+arg_0], eax
0x1400176c7  mov     ebx, eax
0x1400176c9  test    eax, eax
0x1400176cb  jnz     short loc_14001773C
0x1400176cd  mov     ebx, [rsi+280h]
0x1400176d3  mov     [rsp+68h+arg_0], ebx
0x1400176d7  test    ebx, ebx
0x1400176d9  jnz     short loc_140017723
0x1400176db  mov     ebx, [rsi+2B8h]
0x1400176e1  mov     [rsp+68h+arg_0], ebx
0x1400176e5  cmp     ebx, 0C00000B5h
0x1400176eb  jnz     loc_1400177E4
0x1400176f1  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400176f8  jz      short loc_140017776
0x1400176fa  mov     r9d, 0B2h
0x140017700  mov     rcx, cs:WPP_GLOBAL_Control
0x140017707  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001770e  mov     r8d, r12d
0x140017711  mov     [rsp+68h+Timeout], rax
0x140017716  mov     dl, 2
0x140017718  mov     rcx, [rcx+40h]
0x14001771c  call    WPP_RECORDER_SF_
0x140017721  jmp     short loc_140017776
0x140017723  cmp     ebx, 0C00000B5h
0x140017729  jnz     short loc_140017781
0x14001772b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140017732  jz      short loc_140017776
0x140017734  mov     r9d, 0B4h
0x14001773a  jmp     short loc_140017700
0x14001773c  cmp     eax, 102h
0x140017741  jnz     loc_1400177E4
0x140017747  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001774e  jz      short loc_140017776
0x140017750  lea     r9d, [rax-4Dh]
0x140017754  jmp     short loc_140017700
0x140017756  test    ebx, ebx
0x140017758  jz      loc_1400177E4
0x14001775e  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x140017761  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x140017766  cmp     ebx, 0C00000B5h
0x14001776c  jz      short loc_140017776
0x14001776e  cmp     ebx, 102h
0x140017774  jnz     short loc_1400177E4
0x140017776  cmp     r14d, 3
0x14001777a  jnb     short loc_1400177E4
0x14001777c  jmp     loc_140017505
0x140017781  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140017788  jz      short loc_1400177E4
0x14001778a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017791  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140017798  mov     r9d, 0B3h
0x14001779e  mov     [rsp+68h+var_40], ebx
0x1400177a2  mov     r8d, r12d
0x1400177a5  mov     [rsp+68h+Timeout], rax
0x1400177aa  mov     dl, 2
0x1400177ac  mov     rcx, [rcx+40h]
0x1400177b0  call    WPP_RECORDER_SF_d
0x1400177b5  jmp     short loc_1400177E4
0x1400177b7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400177be  jz      short loc_1400177E0
0x1400177c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177c7  mov     r9d, 0B1h
0x1400177cd  mov     r8d, r12d
0x1400177d0  mov     [rsp+68h+Timeout], rbx
0x1400177d5  mov     dl, 2
0x1400177d7  mov     rcx, [rcx+40h]
0x1400177db  call    WPP_RECORDER_SF_
0x1400177e0  mov     ebx, [rsp+68h+arg_0]
0x1400177e4  mov     rax, cs:WdfFunctions_01031
0x1400177eb  xor     bpl, bpl
0x1400177ee  mov     rdx, [rdi+0E0h]
0x1400177f5  mov     rcx, cs:WdfDriverGlobals
0x1400177fc  mov     rax, [rax+9E0h]
0x140017803  call    _guard_dispatch_icall
0x140017808  add     dword ptr [rdi+0E8h], 0FFFFFFFFh
0x14001780f  jnz     short loc_140017824
0x140017811  cmp     dword ptr [rdi+0ECh], 0
0x140017818  jz      short loc_140017824
0x14001781a  mov     bpl, r12b
0x14001781d  mov     [rdi+0F0h], r12d
0x140017824  mov     rax, cs:WdfFunctions_01031
0x14001782b  mov     rdx, [rdi+0E0h]
0x140017832  mov     rcx, cs:WdfDriverGlobals
0x140017839  mov     rax, [rax+9E8h]
0x140017840  call    _guard_dispatch_icall
0x140017845  test    bpl, bpl
0x140017848  jz      short loc_1400178AA
0x14001784a  mov     rax, [rdi+0F8h]
0x140017851  test    rax, rax
0x140017854  jz      short loc_140017862
0x140017856  mov     rcx, [rdi+100h]
0x14001785d  call    _guard_dispatch_icall
0x140017862  lea     rcx, [rdi+108h]; Event
0x140017869  xor     r8d, r8d; Wait
0x14001786c  xor     edx, edx; Increment
0x14001786e  call    cs:__imp_KeSetEvent
0x140017875  nop     dword ptr [rax+rax+00h]
0x14001787a  jmp     short loc_1400178AA
0x14001787c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140017883  jz      short loc_1400178A5
0x140017885  mov     rcx, cs:WPP_GLOBAL_Control
0x14001788c  mov     r9d, 0B0h
0x140017892  mov     r8d, r12d
0x140017895  mov     [rsp+68h+Timeout], rbx
0x14001789a  mov     dl, 2
0x14001789c  mov     rcx, [rcx+40h]
0x1400178a0  call    WPP_RECORDER_SF_
0x1400178a5  mov     ebx, 0C0010011h
0x1400178aa  test    rsi, rsi
0x1400178ad  jz      short loc_1400178B7
0x1400178af  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x1400178b2  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x1400178b7  mov     eax, 0C00000B5h
0x1400178bc  cmp     ebx, 102h
0x1400178c2  cmovz   ebx, eax
0x1400178c5  mov     eax, ebx
0x1400178c7  add     rsp, 30h
0x1400178cb  pop     r14
0x1400178cd  pop     r13
0x1400178cf  pop     r12
0x1400178d1  pop     rdi
0x1400178d2  pop     rsi
0x1400178d3  pop     rbp
0x1400178d4  pop     rbx
0x1400178d5  retn
```
