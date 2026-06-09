# MbbReqMgrCreateRequest(_MBB_REQUEST_MANAGER *,_NDIS_OID_REQUEST *,ulong,int *,uchar)

- ea: `0x140019b6c`
- end: `0x140019f6f`
- name: `?MbbReqMgrCreateRequest@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_NDIS_OID_REQUEST@@KPEAHE@Z`
- size: `1027`
- prototype: `struct _MBB_REQUEST_CONTEXT *__fastcall(struct _MBB_REQUEST_MANAGER *, struct _NDIS_OID_REQUEST *, __int64, int *, unsigned __int8)`
- caller_count: `18`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140002024`
- `0x140002278`
- `0x1400024cc`
- `0x140003534`
- `0x140003744`
- `0x140003ab0`
- `0x140003d30`
- `0x140004004`
- `0x14000431c`
- `0x14000459c`
- `0x140004844`
- `0x14000f478`
- `0x140011e94`
- `0x140013c08`
- `0x1400174d8`
- `0x14001ea18`
- `0x14002ec90`
- `0x14002f228`

## callees

- `0x140001cf8`
- `0x140019b6c`
- `0x14001a87c`
- `0x14001bcd8`
- `0x14001be98`
- `0x14001dc00`
- `0x14001dc34`
- `0x14001ddf4`
- `0x140047e90`
- `0x140048340`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140019d4e`
- `ntoskrnl!KeInitializeEvent` at `0x140019d4e`
- `ntoskrnl!KeSetEvent` at `0x140019f42`
- `ntoskrnl!KeSetEvent` at `0x140019f42`
- `ntoskrnl!KeResetEvent` at `0x140019d17`
- `ntoskrnl!KeResetEvent` at `0x140019d17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e34`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e34`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e92`

## pseudocode

```c
struct _MBB_REQUEST_CONTEXT *__fastcall MbbReqMgrCreateRequest(
        struct _MBB_REQUEST_MANAGER *a1,
        struct _NDIS_OID_REQUEST *a2,
        __int64 a3,
        int *a4,
        unsigned __int8 a5)
{
  char *v8; // rax
  int v9; // edx
  char *v10; // rbx
  int v11; // edx
  char v12; // bp
  int v13; // edx
  int v14; // ecx
  struct _MBB_REQUEST_MANAGER **v15; // rcx
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  NDIS_REQUEST_TYPE RequestType; // ecx
  __int32 v20; // ecx
  __int32 v21; // ecx
  NDIS_OID Oid; // ecx
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rdi
  char v27; // si
  bool v28; // zf
  void (__fastcall *v29)(_QWORD); // rax

  *a4 = -1073741670;
  v8 = (char *)MbbAllocMgrAllocate(*((PNPAGED_LOOKASIDE_LIST *)a1 + 53));
  v10 = v8;
  if ( !v8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        4,
        27,
        (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids);
    }
    return (struct _MBB_REQUEST_CONTEXT *)v10;
  }
  memset(v8, 0, 0x320u);
  v10[464] = a5;
  *((_QWORD *)v10 + 53) = a2;
  if ( a2 )
  {
    *((_QWORD *)v10 + 54) = a2->RequestId;
    *((_QWORD *)v10 + 55) = a2->RequestHandle;
  }
  *((_QWORD *)v10 + 1) = v10;
  *((_QWORD *)v10 + 63) = v10 + 496;
  *((_QWORD *)v10 + 62) = v10 + 496;
  *((_QWORD *)v10 + 65) = v10 + 512;
  *((_QWORD *)v10 + 64) = v10 + 512;
  *(_QWORD *)v10 = v10;
  MbbReqMgrLockManager(a1);
  if ( *((_BYTE *)a1 + 432) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        4,
        28,
        (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids);
    }
    *a4 = 65539;
  }
  else
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
      WdfDriverGlobals,
      *((_QWORD *)a1 + 28));
    if ( *((_DWORD *)a1 + 59) )
    {
      v12 = 0;
    }
    else
    {
      ++*((_DWORD *)a1 + 58);
      v12 = 1;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
      WdfDriverGlobals,
      *((_QWORD *)a1 + 28));
    if ( v12 )
    {
      v14 = *((_DWORD *)a1 + 54);
      *((_DWORD *)a1 + 54) = v14 + 1;
      *((_DWORD *)v10 + 4) = v14;
      *((_QWORD *)v10 + 6) = a1;
      KeResetEvent((PRKEVENT)a1 + 8);
      v15 = (struct _MBB_REQUEST_MANAGER **)*((_QWORD *)a1 + 2);
      if ( *v15 != (struct _MBB_REQUEST_MANAGER *)((char *)a1 + 8) )
        __fastfail(3u);
      *((_QWORD *)v10 + 1) = v15;
      *(_QWORD *)v10 = (char *)a1 + 8;
      *v15 = (struct _MBB_REQUEST_MANAGER *)v10;
      *((_QWORD *)a1 + 2) = v10;
      KeInitializeEvent((PRKEVENT)(v10 + 56), NotificationEvent, 0);
      if ( a2 )
      {
        if ( a2->RequestType == NdisRequestSetInformation )
          v10[452] = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          RequestType = a2->RequestType;
          if ( RequestType && (v20 = RequestType - 1) != 0 && (v21 = v20 - 1) != 0 && v21 != 10 )
            Oid = 0;
          else
            Oid = a2->DATA.QUERY_INFORMATION.Oid;
          GetOidName(Oid);
          WPP_RECORDER_SF_Dsqqc(WPP_GLOBAL_Control->DeviceExtension, v23, v24, v25);
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_Dq(WPP_GLOBAL_Control->DeviceExtension, v16, v17, v18);
      }
      *((_DWORD *)v10 + 10) = 1;
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 22, *((_BYTE *)a1 + 184));
      *a4 = 0;
      goto LABEL_34;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        4,
        29,
        (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids);
    }
    *a4 = -1073741670;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 22, *((_BYTE *)a1 + 184));
LABEL_34:
  if ( *a4 )
  {
    v26 = *((_QWORD *)v10 + 6);
    if ( v26 )
    {
      v27 = 0;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
        WdfDriverGlobals,
        *(_QWORD *)(v26 + 224));
      v28 = (*(_DWORD *)(v26 + 232))-- == 1;
      if ( v28 && *(_DWORD *)(v26 + 236) )
      {
        v27 = 1;
        *(_DWORD *)(v26 + 240) = 1;
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
        WdfDriverGlobals,
        *(_QWORD *)(v26 + 224));
      if ( v27 )
      {
        v29 = *(void (__fastcall **)(_QWORD))(v26 + 248);
        if ( v29 )
          v29(*(_QWORD *)(v26 + 256));
        KeSetEvent((PRKEVENT)(v26 + 264), 0, 0);
      }
    }
    MbbAllocMgrFree(v10);
    return 0;
  }
  return (struct _MBB_REQUEST_CONTEXT *)v10;
}

```

## disassembly

```asm
0x140019b6c  mov     [rsp+arg_0], rbx
0x140019b71  mov     [rsp+arg_8], rbp
0x140019b76  push    rsi
0x140019b77  push    rdi
0x140019b78  push    r14
0x140019b7a  sub     rsp, 50h
0x140019b7e  mov     rsi, rcx
0x140019b81  mov     dword ptr [r9], 0C000009Ah
0x140019b88  mov     rcx, [rcx+1A8h]; Lookaside
0x140019b8f  mov     r14, r9
0x140019b92  mov     rdi, rdx
0x140019b95  call    ?MbbAllocMgrAllocate@@YAPEAXPEAX@Z; MbbAllocMgrAllocate(void *)
0x140019b9a  mov     rbx, rax
0x140019b9d  test    rax, rax
0x140019ba0  jnz     short loc_140019BE1
0x140019ba2  lea     rax, WPP_RECORDER_INITIALIZED
0x140019ba9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019bb0  jz      loc_140019F58
0x140019bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140019bbd  lea     rax, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x140019bc4  lea     r9d, [rbx+1Bh]
0x140019bc8  mov     [rsp+68h+var_48], rax
0x140019bcd  lea     r8d, [rbx+4]
0x140019bd1  mov     dl, 2
0x140019bd3  mov     rcx, [rcx+40h]
0x140019bd7  call    WPP_RECORDER_SF_
0x140019bdc  jmp     loc_140019F58
0x140019be1  xor     edx, edx; Val
0x140019be3  mov     r8d, 320h; Size
0x140019be9  mov     rcx, rbx; void *
0x140019bec  call    memset
0x140019bf1  mov     al, [rsp+68h+arg_20]
0x140019bf8  mov     [rbx+1D0h], al
0x140019bfe  mov     [rbx+1A8h], rdi
0x140019c05  test    rdi, rdi
0x140019c08  jz      short loc_140019C20
0x140019c0a  mov     rax, [rdi+10h]
0x140019c0e  mov     [rbx+1B0h], rax
0x140019c15  mov     rax, [rdi+18h]
0x140019c19  mov     [rbx+1B8h], rax
0x140019c20  lea     rax, [rbx+1F0h]
0x140019c27  mov     [rbx+8], rbx
0x140019c2b  mov     [rax+8], rax
0x140019c2f  mov     rcx, rsi; struct _MBB_REQUEST_MANAGER *
0x140019c32  mov     [rax], rax
0x140019c35  lea     rax, [rbx+200h]
0x140019c3c  mov     [rax+8], rax
0x140019c40  mov     [rax], rax
0x140019c43  mov     [rbx], rbx
0x140019c46  call    ?MbbReqMgrLockManager@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z; MbbReqMgrLockManager(_MBB_REQUEST_MANAGER *)
0x140019c4b  cmp     byte ptr [rsi+1B0h], 0
0x140019c52  jz      short loc_140019C98
0x140019c54  lea     rax, WPP_RECORDER_INITIALIZED
0x140019c5b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019c62  jz      short loc_140019C8C
0x140019c64  mov     rcx, cs:WPP_GLOBAL_Control
0x140019c6b  lea     rax, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x140019c72  mov     r9d, 1Ch
0x140019c78  mov     [rsp+68h+var_48], rax
0x140019c7d  mov     dl, 2
0x140019c7f  mov     rcx, [rcx+40h]
0x140019c83  lea     r8d, [r9-18h]
0x140019c87  call    WPP_RECORDER_SF_
0x140019c8c  mov     dword ptr [r14], 10003h
0x140019c93  jmp     loc_140019E88
0x140019c98  mov     rax, cs:WdfFunctions_01031
0x140019c9f  mov     rdx, [rsi+0E0h]
0x140019ca6  mov     rcx, cs:WdfDriverGlobals
0x140019cad  mov     rax, [rax+9E0h]
0x140019cb4  call    _guard_dispatch_icall
0x140019cb9  cmp     dword ptr [rsi+0ECh], 0
0x140019cc0  jnz     short loc_140019CCD
0x140019cc2  inc     dword ptr [rsi+0E8h]
0x140019cc8  mov     bpl, 1
0x140019ccb  jmp     short loc_140019CD0
0x140019ccd  xor     bpl, bpl
0x140019cd0  mov     rax, cs:WdfFunctions_01031
0x140019cd7  mov     rdx, [rsi+0E0h]
0x140019cde  mov     rcx, cs:WdfDriverGlobals
0x140019ce5  mov     rax, [rax+9E8h]
0x140019cec  call    _guard_dispatch_icall
0x140019cf1  test    bpl, bpl
0x140019cf4  jz      loc_140019E49
0x140019cfa  mov     ecx, [rsi+0D8h]
0x140019d00  lea     eax, [rcx+1]
0x140019d03  mov     [rsi+0D8h], eax
0x140019d09  mov     [rbx+10h], ecx
0x140019d0c  lea     rcx, [rsi+0C0h]; Event
0x140019d13  mov     [rbx+30h], rsi
0x140019d17  call    cs:__imp_KeResetEvent
0x140019d1e  nop     dword ptr [rax+rax+00h]
0x140019d23  lea     rax, [rsi+8]
0x140019d27  mov     rcx, [rax+8]
0x140019d2b  cmp     [rcx], rax
0x140019d2e  jz      short loc_140019D37
0x140019d30  mov     ecx, 3
0x140019d35  int     29h; Win8: RtlFailFast(ecx)
0x140019d37  mov     [rbx+8], rcx
0x140019d3b  xor     r8d, r8d; State
0x140019d3e  mov     [rbx], rax
0x140019d41  xor     edx, edx; Type
0x140019d43  mov     [rcx], rbx
0x140019d46  lea     rcx, [rbx+38h]; Event
0x140019d4a  mov     [rax+8], rbx
0x140019d4e  call    cs:__imp_KeInitializeEvent
0x140019d55  nop     dword ptr [rax+rax+00h]
0x140019d5a  test    rdi, rdi
0x140019d5d  jz      loc_140019DF7
0x140019d63  cmp     dword ptr [rdi+4], 1
0x140019d67  jnz     short loc_140019D70
0x140019d69  mov     byte ptr [rbx+1C4h], 1
0x140019d70  lea     rax, WPP_RECORDER_INITIALIZED
0x140019d77  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019d7e  jz      loc_140019E23
0x140019d84  cmp     qword ptr [rbx+1A8h], 0
0x140019d8c  jnz     short loc_140019D97
0x140019d8e  cmp     byte ptr [rbx+240h], 0
0x140019d95  jz      short loc_140019DA5
0x140019d97  cmp     byte ptr [rbx+1C4h], 0
0x140019d9e  jz      short loc_140019DA5
0x140019da0  mov     r9b, 1
0x140019da3  jmp     short loc_140019DA8
0x140019da5  xor     r9b, r9b
0x140019da8  mov     ecx, [rdi+4]
0x140019dab  test    ecx, ecx
0x140019dad  jz      short loc_140019DC2
0x140019daf  sub     ecx, 1
0x140019db2  jz      short loc_140019DC2
0x140019db4  sub     ecx, 1
0x140019db7  jz      short loc_140019DC2
0x140019db9  cmp     ecx, 0Ah
0x140019dbc  jz      short loc_140019DC2
0x140019dbe  xor     ecx, ecx
0x140019dc0  jmp     short loc_140019DC5
0x140019dc2  mov     ecx, [rdi+20h]; unsigned int
0x140019dc5  call    ?GetOidName@@YAPEBDK@Z; GetOidName(ulong)
0x140019dca  mov     rcx, cs:WPP_GLOBAL_Control
0x140019dd1  mov     [rsp+68h+var_20], r9b
0x140019dd6  mov     [rsp+68h+var_28], rdi
0x140019ddb  mov     [rsp+68h+var_30], rbx
0x140019de0  mov     rcx, [rcx+40h]
0x140019de4  mov     [rsp+68h+var_38], rax
0x140019de9  mov     eax, [rbx+10h]
0x140019dec  mov     [rsp+68h+var_40], eax
0x140019df0  call    WPP_RECORDER_SF_Dsqqc
0x140019df5  jmp     short loc_140019E23
0x140019df7  lea     rax, WPP_RECORDER_INITIALIZED
0x140019dfe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019e05  jz      short loc_140019E23
0x140019e07  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e0e  mov     eax, [rbx+10h]
0x140019e11  mov     [rsp+68h+var_38], rbx
0x140019e16  mov     [rsp+68h+var_40], eax
0x140019e1a  mov     rcx, [rcx+40h]
0x140019e1e  call    WPP_RECORDER_SF_Dq
0x140019e23  lea     rcx, [rsi+0B0h]; SpinLock
0x140019e2a  mov     dword ptr [rbx+28h], 1
0x140019e31  mov     dl, [rcx+8]; NewIrql
0x140019e34  call    cs:__imp_KeReleaseSpinLock
0x140019e3b  nop     dword ptr [rax+rax+00h]
0x140019e40  mov     dword ptr [r14], 0
0x140019e47  jmp     short loc_140019E9E
0x140019e49  lea     rax, WPP_RECORDER_INITIALIZED
0x140019e50  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019e57  jz      short loc_140019E81
0x140019e59  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e60  lea     rax, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x140019e67  mov     r9d, 1Dh
0x140019e6d  mov     [rsp+68h+var_48], rax
0x140019e72  mov     dl, 2
0x140019e74  mov     rcx, [rcx+40h]
0x140019e78  lea     r8d, [r9-19h]
0x140019e7c  call    WPP_RECORDER_SF_
0x140019e81  mov     dword ptr [r14], 0C000009Ah
0x140019e88  lea     rcx, [rsi+0B0h]; SpinLock
0x140019e8f  mov     dl, [rcx+8]; NewIrql
0x140019e92  call    cs:__imp_KeReleaseSpinLock
0x140019e99  nop     dword ptr [rax+rax+00h]
0x140019e9e  cmp     dword ptr [r14], 0
0x140019ea2  jz      loc_140019F58
0x140019ea8  mov     rdi, [rbx+30h]
0x140019eac  test    rdi, rdi
0x140019eaf  jz      loc_140019F4E
0x140019eb5  mov     rax, cs:WdfFunctions_01031
0x140019ebc  xor     sil, sil
0x140019ebf  mov     rdx, [rdi+0E0h]
0x140019ec6  mov     rcx, cs:WdfDriverGlobals
0x140019ecd  mov     rax, [rax+9E0h]
0x140019ed4  call    _guard_dispatch_icall
0x140019ed9  add     dword ptr [rdi+0E8h], 0FFFFFFFFh
0x140019ee0  jnz     short loc_140019EF8
0x140019ee2  cmp     dword ptr [rdi+0ECh], 0
0x140019ee9  jz      short loc_140019EF8
0x140019eeb  mov     sil, 1
0x140019eee  mov     dword ptr [rdi+0F0h], 1
0x140019ef8  mov     rax, cs:WdfFunctions_01031
0x140019eff  mov     rdx, [rdi+0E0h]
0x140019f06  mov     rcx, cs:WdfDriverGlobals
0x140019f0d  mov     rax, [rax+9E8h]
0x140019f14  call    _guard_dispatch_icall
0x140019f19  test    sil, sil
0x140019f1c  jz      short loc_140019F4E
0x140019f1e  mov     rax, [rdi+0F8h]
0x140019f25  test    rax, rax
0x140019f28  jz      short loc_140019F36
0x140019f2a  mov     rcx, [rdi+100h]
0x140019f31  call    _guard_dispatch_icall
0x140019f36  lea     rcx, [rdi+108h]; Event
0x140019f3d  xor     r8d, r8d; Wait
0x140019f40  xor     edx, edx; Increment
0x140019f42  call    cs:__imp_KeSetEvent
0x140019f49  nop     dword ptr [rax+rax+00h]
0x140019f4e  mov     rcx, rbx; void *
0x140019f51  call    ?MbbAllocMgrFree@@YAXPEAX@Z; MbbAllocMgrFree(void *)
0x140019f56  xor     ebx, ebx
0x140019f58  mov     rbp, [rsp+68h+arg_8]
0x140019f5d  mov     rax, rbx
0x140019f60  mov     rbx, [rsp+68h+arg_0]
0x140019f65  add     rsp, 50h
0x140019f69  pop     r14
0x140019f6b  pop     rdi
0x140019f6c  pop     rsi
0x140019f6d  retn
```
