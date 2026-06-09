# MbbUtilDisconnectOnDeleteMPDP(_MINIPORT_ADAPTER_CONTEXT *,_MINIPORT_INTERFACE_CONTEXT *)

- ea: `0x14001ea18`
- end: `0x14001ec9b`
- name: `?MbbUtilDisconnectOnDeleteMPDP@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MINIPORT_INTERFACE_CONTEXT@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, struct _MINIPORT_INTERFACE_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400212ec`

## callees

- `0x140001934`
- `0x140001cf8`
- `0x140003124`
- `0x140011278`
- `0x140019b6c`
- `0x140019f78`
- `0x14001a168`
- `0x14001ea18`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001ec6f`
- `ntoskrnl!KeSetEvent` at `0x14001ec6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ea5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001eabd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ea5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001eabd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ea40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ea7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ea40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ea7e`

## pseudocode

```c
__int64 __fastcall MbbUtilDisconnectOnDeleteMPDP(PKSPIN_LOCK SpinLock, struct _MINIPORT_INTERFACE_CONTEXT *a2)
{
  DWORD v2; // r14d
  unsigned int v3; // edi
  KIRQL v6; // al
  DWORD v7; // esi
  bool v8; // si
  struct _MBB_REQUEST_MANAGER *RequestManager; // rax
  int v10; // edx
  __int64 v11; // r8
  struct _MBB_REQUEST_MANAGER *v12; // rbx
  int v13; // edx
  union _LARGE_INTEGER *v14; // rsi
  char v15; // si
  bool v16; // zf
  void (__fastcall *v17)(_QWORD); // rax
  _DWORD v19[8]; // [rsp+30h] [rbp-20h] BYREF
  int v20; // [rsp+80h] [rbp+30h] BYREF

  v2 = *((_DWORD *)a2 + 17);
  v3 = 0;
  v20 = 0;
  v6 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  v7 = *((_DWORD *)SpinLock + 288);
  *((_BYTE *)SpinLock + 8) = v6;
  KeReleaseSpinLock(SpinLock, v6);
  if ( !v2 || v2 >= v7 )
    return 0;
  v8 = 0;
  *((_BYTE *)SpinLock + 8) = KeAcquireSpinLockRaiseToDpc(SpinLock);
  if ( *(_BYTE *)(SpinLock[143] + 16LL * v2 + 8) )
    v8 = MbbSessionIsConnected(a2) != 0;
  KeReleaseSpinLock(SpinLock, *((_BYTE *)SpinLock + 8));
  if ( v8 )
  {
    v19[0] = -1568027597;
    v19[1] = -1957708613;
    v19[2] = 1041477814;
    v19[3] = -538531134;
    v19[4] = 12;
    RequestManager = MbbAdapterGetRequestManager(SpinLock);
    v12 = RequestManager;
    if ( RequestManager )
    {
      v14 = (union _LARGE_INTEGER *)MbbReqMgrCreateRequest(RequestManager, 0, v11, &v20, 1u);
      if ( v14 )
      {
        v14[10].QuadPart = (LONGLONG)MbbNdisGetOidHandlerByCommand((struct _MBB_COMMAND *)v19);
        v14[91].LowPart = v2;
        v3 = MbbReqMgrDispatchRequest(
               v14,
               1,
               (int (*)(void *, struct _MBB_REQUEST_CONTEXT *))MbbUtilDeactivateContext,
               (void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int))MbbUtilInternalCIDCompletion,
               (void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))MbbUtilInternalCIDResponse);
        if ( v3 != 259 )
          MbbReqMgrDerefRequest((struct _MBB_REQUEST_CONTEXT *)v14);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            3,
            107,
            (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
        }
        v3 = v20;
      }
      v15 = 0;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
        WdfDriverGlobals,
        *((_QWORD *)v12 + 28));
      v16 = (*((_DWORD *)v12 + 58))-- == 1;
      if ( v16 && *((_DWORD *)v12 + 59) )
      {
        v15 = 1;
        *((_DWORD *)v12 + 60) = 1;
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
        WdfDriverGlobals,
        *((_QWORD *)v12 + 28));
      if ( v15 )
      {
        v17 = (void (__fastcall *)(_QWORD))*((_QWORD *)v12 + 31);
        if ( v17 )
          v17(*((_QWORD *)v12 + 32));
        KeSetEvent((PRKEVENT)v12 + 11, 0, 0);
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
          3,
          106,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
      }
      return (unsigned int)-1073676271;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14001ea18  mov     [rsp-28h+arg_8], rbx
0x14001ea1d  mov     [rsp-28h+arg_10], rsi
0x14001ea22  push    rbp
0x14001ea23  push    rdi
0x14001ea24  push    r12
0x14001ea26  push    r14
0x14001ea28  push    r15
0x14001ea2a  mov     rbp, rsp
0x14001ea2d  sub     rsp, 50h
0x14001ea31  mov     r14d, [rdx+44h]
0x14001ea35  xor     edi, edi
0x14001ea37  mov     [rbp+arg_0], edi
0x14001ea3a  mov     r15, rdx
0x14001ea3d  mov     rbx, rcx
0x14001ea40  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ea47  nop     dword ptr [rax+rax+00h]
0x14001ea4c  mov     esi, [rbx+480h]
0x14001ea52  mov     rcx, rbx; SpinLock
0x14001ea55  mov     dl, al; NewIrql
0x14001ea57  mov     [rbx+8], al
0x14001ea5a  call    cs:__imp_KeReleaseSpinLock
0x14001ea61  nop     dword ptr [rax+rax+00h]
0x14001ea66  test    r14d, r14d
0x14001ea69  jz      loc_14001EC7F
0x14001ea6f  cmp     r14d, esi
0x14001ea72  jnb     loc_14001EC7F
0x14001ea78  mov     rcx, rbx; SpinLock
0x14001ea7b  xor     sil, sil
0x14001ea7e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ea85  nop     dword ptr [rax+rax+00h]
0x14001ea8a  mov     [rbx+8], al
0x14001ea8d  mov     ecx, r14d
0x14001ea90  mov     rax, [rbx+478h]
0x14001ea97  lea     r12d, [rdi+1]
0x14001ea9b  add     rcx, rcx
0x14001ea9e  cmp     [rax+rcx*8+8], sil
0x14001eaa3  jz      short loc_14001EAB7
0x14001eaa5  mov     rcx, r15; struct _MINIPORT_INTERFACE_CONTEXT *
0x14001eaa8  call    ?MbbSessionIsConnected@@YAEPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; MbbSessionIsConnected(_MINIPORT_INTERFACE_CONTEXT *)
0x14001eaad  test    al, al
0x14001eaaf  movzx   esi, sil
0x14001eab3  cmovnz  esi, r12d
0x14001eab7  mov     dl, [rbx+8]; NewIrql
0x14001eaba  mov     rcx, rbx; SpinLock
0x14001eabd  call    cs:__imp_KeReleaseSpinLock
0x14001eac4  nop     dword ptr [rax+rax+00h]
0x14001eac9  test    sil, sil
0x14001eacc  jz      loc_14001EC7B
0x14001ead2  mov     rcx, rbx; SpinLock
0x14001ead5  mov     [rbp+var_20], 0A289CC33h
0x14001eadc  mov     [rbp+var_1C], 8B4FBCBBh
0x14001eae3  mov     [rbp+var_18], 3E13B0B6h
0x14001eaea  mov     [rbp+var_14], 0DFE6AAC2h
0x14001eaf1  mov     [rbp+var_10], 0Ch
0x14001eaf8  call    ?MbbAdapterGetRequestManager@@YAPEAU_MBB_REQUEST_MANAGER@@PEAU_MINIPORT_ADAPTER_CONTEXT@@@Z; MbbAdapterGetRequestManager(_MINIPORT_ADAPTER_CONTEXT *)
0x14001eafd  mov     rbx, rax
0x14001eb00  test    rax, rax
0x14001eb03  jnz     short loc_14001EB45
0x14001eb05  lea     rax, WPP_RECORDER_INITIALIZED
0x14001eb0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001eb13  jz      short loc_14001EB3B
0x14001eb15  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb1c  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001eb23  lea     r9d, [rbx+6Ah]
0x14001eb27  mov     [rsp+50h+var_30], rax
0x14001eb2c  lea     r8d, [rbx+3]
0x14001eb30  mov     dl, 2
0x14001eb32  mov     rcx, [rcx+40h]
0x14001eb36  call    WPP_RECORDER_SF_
0x14001eb3b  mov     edi, 0C0010011h
0x14001eb40  jmp     loc_14001EC7B
0x14001eb45  lea     r9, [rbp+arg_0]; int *
0x14001eb49  mov     byte ptr [rsp+50h+var_30], r12b; unsigned __int8
0x14001eb4e  xor     edx, edx; struct _NDIS_OID_REQUEST *
0x14001eb50  mov     rcx, rbx; struct _MBB_REQUEST_MANAGER *
0x14001eb53  call    ?MbbReqMgrCreateRequest@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_NDIS_OID_REQUEST@@KPEAHE@Z; MbbReqMgrCreateRequest(_MBB_REQUEST_MANAGER *,_NDIS_OID_REQUEST *,ulong,int *,uchar)
0x14001eb58  mov     rsi, rax
0x14001eb5b  test    rax, rax
0x14001eb5e  jnz     short loc_14001EB9B
0x14001eb60  lea     rax, WPP_RECORDER_INITIALIZED
0x14001eb67  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001eb6e  jz      short loc_14001EB96
0x14001eb70  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb77  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001eb7e  lea     r9d, [rsi+6Bh]
0x14001eb82  mov     [rsp+50h+var_30], rax
0x14001eb87  lea     r8d, [rsi+3]
0x14001eb8b  mov     dl, 2
0x14001eb8d  mov     rcx, [rcx+40h]
0x14001eb91  call    WPP_RECORDER_SF_
0x14001eb96  mov     edi, [rbp+arg_0]
0x14001eb99  jmp     short loc_14001EBE5
0x14001eb9b  lea     rcx, [rbp+var_20]; struct _MBB_COMMAND *
0x14001eb9f  call    ?MbbNdisGetOidHandlerByCommand@@YAPEAU_MBB_OID_HANDLER_ENTRY@@PEAU_MBB_COMMAND@@@Z; MbbNdisGetOidHandlerByCommand(_MBB_COMMAND *)
0x14001eba4  mov     [rsi+50h], rax
0x14001eba8  lea     r9, ?MbbUtilInternalCIDCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int)
0x14001ebaf  lea     rax, ?MbbUtilInternalCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbUtilInternalCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x14001ebb6  mov     [rsi+2D8h], r14d
0x14001ebbd  lea     r8, ?MbbUtilDeactivateContext@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z; int (*)(void *, struct _MBB_REQUEST_CONTEXT *)
0x14001ebc4  mov     [rsp+50h+var_30], rax; void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int)
0x14001ebc9  mov     dl, r12b; unsigned __int8
0x14001ebcc  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x14001ebcf  call    ?MbbReqMgrDispatchRequest@@YAHPEAU_MBB_REQUEST_CONTEXT@@EP6AHPEAX0@ZP6AX10H@ZP6AX0HW4_MBB_STATUS@@PEAEK@Z@Z; MbbReqMgrDispatchRequest(_MBB_REQUEST_CONTEXT *,uchar,int (*)(void *,_MBB_REQUEST_CONTEXT *),void (*)(void *,_MBB_REQUEST_CONTEXT *,int),void (*)(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong))
0x14001ebd4  mov     edi, eax
0x14001ebd6  cmp     eax, 103h
0x14001ebdb  jz      short loc_14001EBE5
0x14001ebdd  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x14001ebe0  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14001ebe5  mov     rax, cs:WdfFunctions_01031
0x14001ebec  xor     sil, sil
0x14001ebef  mov     rdx, [rbx+0E0h]
0x14001ebf6  mov     rcx, cs:WdfDriverGlobals
0x14001ebfd  mov     rax, [rax+9E0h]
0x14001ec04  call    _guard_dispatch_icall
0x14001ec09  add     dword ptr [rbx+0E8h], 0FFFFFFFFh
0x14001ec10  jnz     short loc_14001EC25
0x14001ec12  cmp     dword ptr [rbx+0ECh], 0
0x14001ec19  jz      short loc_14001EC25
0x14001ec1b  mov     sil, r12b
0x14001ec1e  mov     [rbx+0F0h], r12d
0x14001ec25  mov     rax, cs:WdfFunctions_01031
0x14001ec2c  mov     rdx, [rbx+0E0h]
0x14001ec33  mov     rcx, cs:WdfDriverGlobals
0x14001ec3a  mov     rax, [rax+9E8h]
0x14001ec41  call    _guard_dispatch_icall
0x14001ec46  test    sil, sil
0x14001ec49  jz      short loc_14001EC7B
0x14001ec4b  mov     rax, [rbx+0F8h]
0x14001ec52  test    rax, rax
0x14001ec55  jz      short loc_14001EC63
0x14001ec57  mov     rcx, [rbx+100h]
0x14001ec5e  call    _guard_dispatch_icall
0x14001ec63  lea     rcx, [rbx+108h]; Event
0x14001ec6a  xor     r8d, r8d; Wait
0x14001ec6d  xor     edx, edx; Increment
0x14001ec6f  call    cs:__imp_KeSetEvent
0x14001ec76  nop     dword ptr [rax+rax+00h]
0x14001ec7b  mov     eax, edi
0x14001ec7d  jmp     short loc_14001EC81
0x14001ec7f  xor     eax, eax
0x14001ec81  lea     r11, [rsp+50h+var_s0]
0x14001ec86  mov     rbx, [r11+38h]
0x14001ec8a  mov     rsi, [r11+40h]
0x14001ec8e  mov     rsp, r11
0x14001ec91  pop     r15
0x14001ec93  pop     r14
0x14001ec95  pop     r12
0x14001ec97  pop     rdi
0x14001ec98  pop     rbp
0x14001ec99  retn
```
