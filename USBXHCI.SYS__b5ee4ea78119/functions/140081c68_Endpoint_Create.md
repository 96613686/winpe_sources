# Endpoint_Create

- ea: `0x140081c68`
- end: `0x140082523`
- name: `Endpoint_Create`
- size: `2235`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: ``

## callers

- `0x14007bc40`
- `0x140081850`
- `0x140081a10`

## callees

- `0x140001460`
- `0x140002568`
- `0x140002758`
- `0x1400038c0`
- `0x1400043f8`
- `0x140033a40`
- `0x140033c28`
- `0x140034774`
- `0x140035738`
- `0x1400359e0`
- `0x140035c4c`
- `0x140037208`
- `0x14003b144`
- `0x1400599b0`
- `0x140081c68`
- `0x140082ab4`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x1400820f1`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400820f1`
- `ntoskrnl!KeInitializeEvent` at `0x140081f5d`
- `ntoskrnl!KeInitializeEvent` at `0x140081f5d`

## pseudocode

```c
__int64 __fastcall Endpoint_Create(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6, _QWORD *a7)
{
  __int64 v9; // rsi
  int v10; // ebx
  char IsSecureDevice; // al
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int ClearStallContext; // edi
  int v16; // ebx
  __int64 v17; // rax
  int v18; // edx
  int v19; // r9d
  char v20; // cl
  int v21; // ebx
  __int64 v22; // rax
  int v23; // edx
  __int64 v24; // rbx
  char v25; // al
  int v26; // ebx
  __int64 v27; // rax
  struct _DEVICE_OBJECT *v28; // rax
  PIO_WORKITEM WorkItem; // rax
  int v30; // ebx
  __int64 v31; // rax
  int v32; // edx
  __int64 v33; // rax
  __int64 v34; // rcx
  _QWORD *v35; // rax
  int v36; // ecx
  char v37; // dl
  int v38; // ecx
  int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  int ContextSize; // eax
  __int64 v44; // rdx
  __int64 WdfQueue; // rax
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v49; // [rsp+30h] [rbp-A1h]
  char v50; // [rsp+38h] [rbp-99h]
  __int64 v51; // [rsp+60h] [rbp-71h] BYREF
  __int128 v52; // [rsp+68h] [rbp-69h] BYREF
  __int128 v53; // [rsp+78h] [rbp-59h]
  __int128 v54; // [rsp+88h] [rbp-49h]
  __int64 *v55; // [rsp+98h] [rbp-39h]
  __int128 v56; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v57; // [rsp+B0h] [rbp-21h]
  __int64 v58; // [rsp+C0h] [rbp-11h]
  __int64 v59; // [rsp+C8h] [rbp-9h]
  __int64 v60; // [rsp+130h] [rbp+5Fh] BYREF

  v60 = a3;
  LODWORD(v55) = 0;
  v51 = 0;
  LODWORD(v58) = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v56 = 0;
  v57 = 0;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C310);
  v59 = *(_QWORD *)(v9 + 88);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = *(unsigned __int8 *)(a4 + 2) >> 7;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
      WdfDriverGlobals,
      a2,
      off_14006C1A8);
    WPP_RECORDER_SF_ddqDdd(
      *(_QWORD *)(v9 + 72),
      v10 + 2 * (*(_BYTE *)(a4 + 2) & 0x7F),
      *(_BYTE *)(a4 + 3) & 3,
      *(_WORD *)(a4 + 4) & 0x7FF);
  }
  v52 = 0;
  v55 = 0;
  v53 = 0;
  v54 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v52) = -1;
    else
      LODWORD(v52) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v52) = 56;
  }
  v55 = off_14006C068;
  *((_QWORD *)&v53 + 1) = 0x100000001LL;
  *((_QWORD *)&v52 + 1) = Endpoint_EvtEndpointCleanupCallback;
  *(_QWORD *)&v53 = Endpoint_EvtDestroyCallback;
  IsSecureDevice = Controller_IsSecureDevice(v9);
  v13 = v12;
  v14 = v12 + 1;
  if ( IsSecureDevice )
    v13 = v14;
  DWORD2(v53) = v13;
  ClearStallContext = qword_14006CD10(UcxDriverGlobals, a2, &v60, &v52, &v51);
  if ( ClearStallContext >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = *(unsigned __int8 *)(a4 + 2) >> 7;
      v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
              WdfDriverGlobals,
              a2,
              off_14006C1A8);
      v23 = v21 + 2 * (*(_BYTE *)(a4 + 2) & 0x7F);
      LOBYTE(v23) = 4;
      WPP_RECORDER_SF_ddq(
        *(_QWORD *)(v9 + 72),
        v23,
        13,
        17,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(v22 + 143),
        v21 + 2 * (*(_BYTE *)(a4 + 2) & 0x7F),
        v51);
    }
    v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
            WdfDriverGlobals,
            v51,
            off_14006C068);
    KeInitializeEvent((PRKEVENT)(v24 + 40), NotificationEvent, 0);
    v58 = 0;
    v56 = 0;
    v57 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x37 )
        LODWORD(v56) = -1;
      else
        LODWORD(v56) = *(_DWORD *)(WdfStructures + 440);
    }
    else
    {
      LODWORD(v56) = 40;
    }
    LODWORD(v57) = 0;
    *((_QWORD *)&v56 + 1) = Endpoint_WdfEvtStateMachineTimer;
    BYTE4(v57) = 1;
    DWORD2(v57) = 0;
    v25 = v58;
    if ( (*(_DWORD *)(v9 + 744) & 0x40000) != 0 )
      v25 = 1;
    LOBYTE(v58) = v25;
    v55 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x26 )
        LODWORD(v52) = -1;
      else
        LODWORD(v52) = *(_DWORD *)(WdfStructures + 304);
    }
    else
    {
      LODWORD(v52) = 56;
    }
    *(_QWORD *)&v54 = v51;
    *((_QWORD *)&v53 + 1) = 0x100000001LL;
    ClearStallContext = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033 + 2544))(
                          WdfDriverGlobals,
                          &v56,
                          &v52,
                          v24 + 1320);
    if ( ClearStallContext < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)ClearStallContext;
      v26 = *(unsigned __int8 *)(a4 + 2) >> 7;
      v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
              WdfDriverGlobals,
              a2,
              off_14006C1A8);
      v19 = 18;
      goto LABEL_31;
    }
    v28 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 248))(
                                     WdfDriverGlobals,
                                     *(_QWORD *)v9);
    WorkItem = IoAllocateWorkItem(v28);
    *(_QWORD *)(v24 + 1296) = WorkItem;
    if ( !WorkItem )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v30 = *(unsigned __int8 *)(a4 + 2) >> 7;
        v31 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                WdfDriverGlobals,
                a2,
                off_14006C1A8);
        v32 = v30 + 2 * (*(_BYTE *)(a4 + 2) & 0x7F);
        LOBYTE(v32) = 2;
        WPP_RECORDER_SF_DD(
          *(_QWORD *)(v9 + 72),
          v32,
          13,
          19,
          (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
          *(_BYTE *)(v31 + 143),
          v30 + 2 * (*(_BYTE *)(a4 + 2) & 0x7F));
      }
      return (unsigned int)-1073741670;
    }
    *(_DWORD *)(v24 + 1192) = 0;
    *(_DWORD *)(v24 + 1164) = 2000;
    *(_DWORD *)(v24 + 1288) = 2000;
    *(_QWORD *)(v24 + 1280) = ESMStateTable;
    *(_QWORD *)(v24 + 1272) = v24;
    *(_BYTE *)(v24 + 1330) = Controller_IsSecureDevice(v9);
    if ( *(_BYTE *)(g_WdfDriverUsbXhciContext + 28) && (*(_DWORD *)(v9 + 1324) & 1) != 0 )
      *(_BYTE *)(v24 + 1330) = 1;
    *(_QWORD *)v24 = v9;
    *(_QWORD *)(v24 + 8) = a2;
    v33 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
            WdfDriverGlobals,
            a2,
            off_14006C1A8);
    v34 = a5;
    *(_QWORD *)(v24 + 16) = v33;
    *(_QWORD *)(v24 + 144) = 0;
    *(_QWORD *)(v24 + 288) = 0;
    *(_DWORD *)(v24 + 96) = *(_DWORD *)a4;
    *(_WORD *)(v24 + 100) = *(_WORD *)(a4 + 4);
    *(_BYTE *)(v24 + 102) = *(_BYTE *)(a4 + 6);
    if ( v34 )
    {
      *(_DWORD *)(v24 + 111) = *(_DWORD *)v34;
      *(_WORD *)(v24 + 115) = *(_WORD *)(v34 + 4);
    }
    if ( a6 )
      *(_QWORD *)(v24 + 117) = *a6;
    if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
    {
      v35 = a7;
      if ( a7 )
      {
        *(_BYTE *)(v24 + 39) = 1;
        *(_QWORD *)(v24 + 103) = *v35;
      }
      else
      {
        *(_BYTE *)(v24 + 39) = 0;
      }
    }
    if ( (*(_BYTE *)(v24 + 99) & 3) != 0 )
    {
      switch ( *(_BYTE *)(v24 + 99) & 3 )
      {
        case 1:
          *(_DWORD *)(v24 + 128) = 1;
          v36 = 1;
          goto LABEL_55;
        case 2:
          *(_DWORD *)(v24 + 128) = 2;
          v36 = 2;
          goto LABEL_55;
        case 3:
          *(_DWORD *)(v24 + 128) = 3;
          v36 = 3;
LABEL_55:
          v37 = *(_BYTE *)(v24 + 98);
          if ( v37 < 0 || !v36 )
          {
            v36 += 4;
            *(_DWORD *)(v24 + 128) = v36;
          }
          v38 = v36 - 1;
          if ( v38 && (unsigned int)(v38 - 1) >= 2 )
            v39 = 2 * (v37 & 0xF) + 1;
          else
            v39 = 2 * (v37 & 0xF);
          *(_DWORD *)(v24 + 152) = v39;
          ClearStallContext = XilEndpoint_Create(v24);
          if ( ClearStallContext < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return (unsigned int)ClearStallContext;
            v26 = *(unsigned __int8 *)(a4 + 2) >> 7;
            v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                    WdfDriverGlobals,
                    a2,
                    off_14006C1A8);
            v19 = 20;
LABEL_31:
            v50 = ClearStallContext;
            v18 = v26 + 2 * (*(_BYTE *)(a4 + 2) & 0x7F);
            v20 = *(_BYTE *)(v27 + 143);
            LOBYTE(v49) = v26 + 2 * (*(_BYTE *)(a4 + 2) & 0x7F);
            goto LABEL_13;
          }
          v40 = *(_QWORD *)(v24 + 16);
          *(_QWORD *)(v24 + 280) = 0;
          if ( *(_DWORD *)(v40 + 20) == 3 && (*(_BYTE *)(v24 + 99) & 3) == 2 && (*(_BYTE *)(v24 + 114) & 0x1F) != 0 )
          {
            v41 = *(_QWORD *)v24;
            *(_BYTE *)(v24 + 37) = 1;
            if ( (*(_DWORD *)(v41 + 736) & 0x200000) != 0 )
            {
              ClearStallContext = Endpoint_CreateClearStallContext(v24);
              if ( ClearStallContext < 0 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  return (unsigned int)ClearStallContext;
                v42 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                        WdfDriverGlobals,
                        a2,
                        off_14006C1A8);
                v19 = 21;
                goto LABEL_72;
              }
              ContextSize = XilRegister_GetContextSize(v59);
              v44 = 2112;
              if ( ContextSize != 1 )
                v44 = 1056;
              *(_QWORD *)(v24 + 280) = XilEndpoint_AcquireBuffer(v24, v44, v24, 863268933);
            }
          }
          else
          {
            *(_BYTE *)(v24 + 37) = 0;
          }
          ClearStallContext = TR_Create(v9, v24, v51, *(_BYTE *)(v24 + 37) != 0, v24 + 88);
          if ( ClearStallContext >= 0 )
          {
            WdfQueue = TR_GetWdfQueue(*(_QWORD *)(v24 + 88));
            ((void (__fastcall *)(__int64, __int64, __int64))qword_14006CD38)(UcxDriverGlobals, v51, WdfQueue);
            if ( *(_DWORD *)(v24 + 152) == 1 )
              *(_QWORD *)(*(_QWORD *)(v24 + 16) + 184LL) = v24;
            v46 = *(_QWORD *)(v24 + 16);
            *(_QWORD *)(v24 + 24) = v51;
            UsbDevice_AddEndpointToDeviceEndpointList(v46, v51, v24 + 64);
            Etw_EndpointCreate(v47, v24);
            return (unsigned int)ClearStallContext;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return (unsigned int)ClearStallContext;
          v42 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                  WdfDriverGlobals,
                  a2,
                  off_14006C1A8);
          v19 = 22;
LABEL_72:
          v20 = *(_BYTE *)(v42 + 143);
          v50 = ClearStallContext;
          v49 = *(_DWORD *)(v24 + 152);
          goto LABEL_13;
      }
    }
    *(_DWORD *)(v24 + 128) = 0;
    v36 = 0;
    goto LABEL_55;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v16 = *(unsigned __int8 *)(a4 + 2) >> 7;
    v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
            WdfDriverGlobals,
            a2,
            off_14006C1A8);
    v50 = ClearStallContext;
    v19 = 16;
    v20 = *(_BYTE *)(v17 + 143);
    LOBYTE(v49) = v16 + 2 * (*(_BYTE *)(a4 + 2) & 0x7F);
LABEL_13:
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_ddd(
      *(_QWORD *)(v9 + 72),
      v18,
      13,
      v19,
      (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
      v20,
      v49,
      v50);
  }
  return (unsigned int)ClearStallContext;
}

```

## disassembly

```asm
0x140081c68  mov     [rsp-8+arg_10], r8
0x140081c6d  push    rbp
0x140081c6e  push    rbx
0x140081c6f  push    rsi
0x140081c70  push    rdi
0x140081c71  push    r12
0x140081c73  push    r13
0x140081c75  push    r14
0x140081c77  push    r15
0x140081c79  lea     rbp, [rsp-7]
0x140081c7e  sub     rsp, 0D8h
0x140081c85  mov     r8, cs:off_14006C310
0x140081c8c  xor     eax, eax
0x140081c8e  xorps   xmm0, xmm0
0x140081c91  mov     dword ptr [rbp+3Fh+var_78], eax
0x140081c94  mov     [rbp+3Fh+var_B0], rax
0x140081c98  mov     r15, rdx
0x140081c9b  mov     dword ptr [rbp+3Fh+var_50], eax
0x140081c9e  mov     rdx, rcx
0x140081ca1  mov     rax, cs:WdfFunctions_01033
0x140081ca8  mov     r14, r9
0x140081cab  mov     rcx, cs:WdfDriverGlobals
0x140081cb2  movups  [rbp+3Fh+var_A8], xmm0
0x140081cb6  movups  [rbp+3Fh+var_98], xmm0
0x140081cba  movups  [rbp+3Fh+var_88], xmm0
0x140081cbe  movups  [rbp+3Fh+var_70], xmm0
0x140081cc2  movups  [rbp+3Fh+var_60], xmm0
0x140081cc6  mov     rax, [rax+650h]
0x140081ccd  call    _guard_dispatch_icall
0x140081cd2  mov     rsi, rax
0x140081cd5  mov     rax, [rax+58h]
0x140081cd9  mov     [rbp+3Fh+var_48], rax
0x140081cdd  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140081ce4  mov     r12d, 0FFFFFF7Fh
0x140081cea  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140081cf1  jz      loc_140081D79
0x140081cf7  mov     rax, cs:WdfFunctions_01033
0x140081cfe  mov     rdx, r15
0x140081d01  movzx   ebx, byte ptr [r14+2]
0x140081d06  mov     r8, cs:off_14006C1A8
0x140081d0d  mov     rcx, cs:WdfDriverGlobals
0x140081d14  mov     rax, [rax+650h]
0x140081d1b  shr     ebx, 7
0x140081d1e  call    _guard_dispatch_icall
0x140081d23  movzx   r10d, byte ptr [r14+2]
0x140081d28  movzx   r9d, word ptr [r14+4]
0x140081d2d  mov     ecx, r10d
0x140081d30  movzx   r8d, byte ptr [r14+3]
0x140081d35  and     ecx, r12d
0x140081d38  movzx   eax, byte ptr [rax+8Fh]
0x140081d3f  and     r9d, 7FFh
0x140081d46  mov     [rsp+110h+var_C0], r9d
0x140081d4b  and     r8d, 3
0x140081d4f  mov     [rsp+110h+var_C8], r8d
0x140081d54  mov     [rsp+110h+var_D0], r10d
0x140081d59  lea     edx, [rbx+rcx*2]
0x140081d5c  mov     rcx, [rsi+48h]
0x140081d60  mov     [rsp+110h+var_D8], r14
0x140081d65  mov     [rsp+110h+var_E0], edx
0x140081d69  mov     [rsp+110h+var_E8], eax
0x140081d6d  call    WPP_RECORDER_SF_ddqDdd
0x140081d72  lea     rbx, WPP_RECORDER_INITIALIZED
0x140081d79  xorps   xmm0, xmm0
0x140081d7c  xor     eax, eax
0x140081d7e  cmp     cs:WdfClientVersionHigherThanFramework, al
0x140081d84  movups  [rbp+3Fh+var_A8], xmm0
0x140081d88  mov     [rbp+3Fh+var_78], rax
0x140081d8c  movups  [rbp+3Fh+var_98], xmm0
0x140081d90  movups  [rbp+3Fh+var_88], xmm0
0x140081d94  jz      short loc_140081DBA
0x140081d96  cmp     cs:WdfStructureCount, 26h ; '&'
0x140081d9d  jbe     short loc_140081DB1
0x140081d9f  mov     rax, cs:WdfStructures
0x140081da6  mov     ecx, [rax+130h]
0x140081dac  mov     dword ptr [rbp+3Fh+var_A8], ecx
0x140081daf  jmp     short loc_140081DC1
0x140081db1  mov     dword ptr [rbp+3Fh+var_A8], 0FFFFFFFFh
0x140081db8  jmp     short loc_140081DC1
0x140081dba  mov     dword ptr [rbp+3Fh+var_A8], 38h ; '8'
0x140081dc1  mov     rax, cs:off_14006C068
0x140081dc8  mov     edx, 1
0x140081dcd  mov     [rbp+3Fh+var_78], rax
0x140081dd1  mov     rcx, rsi
0x140081dd4  lea     rax, Endpoint_EvtEndpointCleanupCallback
0x140081ddb  mov     dword ptr [rbp+3Fh+var_98+8], edx
0x140081dde  mov     qword ptr [rbp+3Fh+var_A8+8], rax
0x140081de2  lea     rax, Endpoint_EvtDestroyCallback
0x140081de9  mov     qword ptr [rbp+3Fh+var_98], rax
0x140081ded  mov     dword ptr [rbp+3Fh+var_98+0Ch], edx
0x140081df0  call    Controller_IsSecureDevice
0x140081df5  mov     ecx, edx
0x140081df7  lea     r9, [rbp+3Fh+var_A8]
0x140081dfb  test    al, al
0x140081dfd  lea     r8, [rbp+3Fh+arg_10]
0x140081e01  mov     rax, cs:qword_14006CD10
0x140081e08  lea     edx, [rcx+1]
0x140081e0b  cmovnz  ecx, edx
0x140081e0e  mov     rdx, r15
0x140081e11  mov     dword ptr [rbp+3Fh+var_98+8], ecx
0x140081e14  lea     rcx, [rbp+3Fh+var_B0]
0x140081e18  mov     [rsp+110h+var_F0], rcx
0x140081e1d  mov     rcx, cs:UcxDriverGlobals
0x140081e24  call    _guard_dispatch_icall
0x140081e29  mov     edi, eax
0x140081e2b  test    eax, eax
0x140081e2d  jns     short loc_140081EAE
0x140081e2f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140081e36  jz      loc_14008250C
0x140081e3c  mov     rcx, cs:WdfFunctions_01033
0x140081e43  mov     rdx, r15
0x140081e46  movzx   ebx, byte ptr [r14+2]
0x140081e4b  mov     r8, cs:off_14006C1A8
0x140081e52  shr     ebx, 7
0x140081e55  mov     rax, [rcx+650h]
0x140081e5c  mov     rcx, cs:WdfDriverGlobals
0x140081e63  call    _guard_dispatch_icall
0x140081e68  movzx   ecx, byte ptr [r14+2]
0x140081e6d  lea     r13, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140081e74  and     ecx, r12d
0x140081e77  mov     dword ptr [rsp+110h+var_D8], edi
0x140081e7b  mov     r9d, 10h
0x140081e81  lea     r8d, [rbx+rcx*2]
0x140081e85  movzx   ecx, byte ptr [rax+8Fh]
0x140081e8c  mov     [rsp+110h+var_E0], r8d
0x140081e91  lea     r8d, [r9-3]
0x140081e95  mov     [rsp+110h+var_E8], ecx
0x140081e99  mov     dl, 2
0x140081e9b  mov     rcx, [rsi+48h]
0x140081e9f  mov     [rsp+110h+var_F0], r13
0x140081ea4  call    WPP_RECORDER_SF_ddd
0x140081ea9  jmp     loc_14008250C
0x140081eae  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140081eb5  lea     r13, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140081ebc  mov     r12d, 0Dh
0x140081ec2  jz      short loc_140081F2C
0x140081ec4  mov     rax, cs:WdfFunctions_01033
0x140081ecb  mov     rdx, r15
0x140081ece  movzx   ebx, byte ptr [r14+2]
0x140081ed3  mov     r8, cs:off_14006C1A8
0x140081eda  mov     rcx, cs:WdfDriverGlobals
0x140081ee1  mov     rax, [rax+650h]
0x140081ee8  shr     ebx, 7
0x140081eeb  call    _guard_dispatch_icall
0x140081ef0  movzx   ecx, byte ptr [r14+2]
0x140081ef5  lea     r9d, [r12+4]
0x140081efa  btr     ecx, 7
0x140081efe  mov     r8d, r12d
0x140081f01  lea     edx, [rbx+rcx*2]
0x140081f04  movzx   ecx, byte ptr [rax+8Fh]
0x140081f0b  mov     rax, [rbp+3Fh+var_B0]
0x140081f0f  mov     [rsp+110h+var_D8], rax
0x140081f14  mov     [rsp+110h+var_E0], edx
0x140081f18  mov     dl, 4
0x140081f1a  mov     [rsp+110h+var_E8], ecx
0x140081f1e  mov     rcx, [rsi+48h]
0x140081f22  mov     [rsp+110h+var_F0], r13
0x140081f27  call    WPP_RECORDER_SF_ddq
0x140081f2c  mov     rax, cs:WdfFunctions_01033
0x140081f33  mov     r8, cs:off_14006C068
0x140081f3a  mov     rdx, [rbp+3Fh+var_B0]
0x140081f3e  mov     rcx, cs:WdfDriverGlobals
0x140081f45  mov     rax, [rax+650h]
0x140081f4c  call    _guard_dispatch_icall
0x140081f51  xor     r8d, r8d; State
0x140081f54  xor     edx, edx; Type
0x140081f56  mov     rbx, rax
0x140081f59  lea     rcx, [rax+28h]; Event
0x140081f5d  call    cs:__imp_KeInitializeEvent
0x140081f64  nop     dword ptr [rax+rax+00h]
0x140081f69  mov     dl, cs:WdfClientVersionHigherThanFramework
0x140081f6f  xor     eax, eax
0x140081f71  mov     [rbp+3Fh+var_50], rax
0x140081f75  xorps   xmm0, xmm0
0x140081f78  movups  [rbp+3Fh+var_70], xmm0
0x140081f7c  movups  [rbp+3Fh+var_60], xmm0
0x140081f80  test    dl, dl
0x140081f82  jz      short loc_140081FA8
0x140081f84  cmp     cs:WdfStructureCount, 37h ; '7'
0x140081f8b  jbe     short loc_140081F9F
0x140081f8d  mov     rax, cs:WdfStructures
0x140081f94  mov     ecx, [rax+1B8h]
0x140081f9a  mov     dword ptr [rbp+3Fh+var_70], ecx
0x140081f9d  jmp     short loc_140081FAF
0x140081f9f  mov     dword ptr [rbp+3Fh+var_70], 0FFFFFFFFh
0x140081fa6  jmp     short loc_140081FAF
0x140081fa8  mov     dword ptr [rbp+3Fh+var_70], 28h ; '('
0x140081faf  lea     rax, Endpoint_WdfEvtStateMachineTimer
0x140081fb6  mov     dword ptr [rbp+3Fh+var_60], 0
0x140081fbd  mov     qword ptr [rbp+3Fh+var_70+8], rax
0x140081fc1  mov     r8d, 1
0x140081fc7  mov     byte ptr [rbp+3Fh+var_60+4], r8b
0x140081fcb  mov     dword ptr [rbp+3Fh+var_60+8], 0
0x140081fd2  mov     eax, [rsi+2E8h]
0x140081fd8  bt      rax, 12h
0x140081fdd  movzx   eax, byte ptr [rbp+3Fh+var_50]
0x140081fe1  cmovb   eax, r8d
0x140081fe5  mov     byte ptr [rbp+3Fh+var_50], al
0x140081fe8  xor     eax, eax
0x140081fea  mov     [rbp+3Fh+var_78], rax
0x140081fee  movups  [rbp+3Fh+var_A8], xmm0
0x140081ff2  movups  [rbp+3Fh+var_98], xmm0
0x140081ff6  movups  [rbp+3Fh+var_88], xmm0
0x140081ffa  test    dl, dl
0x140081ffc  jz      short loc_140082022
0x140081ffe  cmp     cs:WdfStructureCount, 26h ; '&'
0x140082005  jbe     short loc_140082019
0x140082007  mov     rax, cs:WdfStructures
0x14008200e  mov     ecx, [rax+130h]
0x140082014  mov     dword ptr [rbp+3Fh+var_A8], ecx
0x140082017  jmp     short loc_140082029
0x140082019  mov     dword ptr [rbp+3Fh+var_A8], 0FFFFFFFFh
0x140082020  jmp     short loc_140082029
0x140082022  mov     dword ptr [rbp+3Fh+var_A8], 38h ; '8'
0x140082029  mov     rax, [rbp+3Fh+var_B0]
0x14008202d  lea     r9, [rbx+528h]
0x140082034  mov     rcx, cs:WdfDriverGlobals
0x14008203b  lea     rdx, [rbp+3Fh+var_70]
0x14008203f  mov     qword ptr [rbp+3Fh+var_88], rax
0x140082043  mov     rax, cs:WdfFunctions_01033
0x14008204a  mov     dword ptr [rbp+3Fh+var_98+8], r8d
0x14008204e  mov     dword ptr [rbp+3Fh+var_98+0Ch], r8d
0x140082052  lea     r8, [rbp+3Fh+var_A8]
0x140082056  mov     rax, [rax+9F0h]
0x14008205d  call    _guard_dispatch_icall
0x140082062  mov     edi, eax
0x140082064  test    eax, eax
0x140082066  jns     short loc_1400820D1
0x140082068  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008206f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082076  jz      loc_14008250C
0x14008207c  mov     rax, cs:WdfFunctions_01033
0x140082083  mov     rdx, r15
0x140082086  movzx   ebx, byte ptr [r14+2]
0x14008208b  mov     r8, cs:off_14006C1A8
0x140082092  mov     rcx, cs:WdfDriverGlobals
0x140082099  mov     rax, [rax+650h]
0x1400820a0  shr     ebx, 7
0x1400820a3  call    _guard_dispatch_icall
0x1400820a8  mov     r9d, 12h
0x1400820ae  movzx   ecx, byte ptr [r14+2]
0x1400820b3  btr     ecx, 7
0x1400820b7  mov     dword ptr [rsp+110h+var_D8], edi
0x1400820bb  lea     edx, [rbx+rcx*2]
0x1400820be  movzx   ecx, byte ptr [rax+8Fh]
0x1400820c5  mov     [rsp+110h+var_E0], edx
0x1400820c9  mov     r8d, r12d
0x1400820cc  jmp     loc_140081E95
0x1400820d1  mov     rax, cs:WdfFunctions_01033
0x1400820d8  mov     rdx, [rsi]
0x1400820db  mov     rcx, cs:WdfDriverGlobals
0x1400820e2  mov     rax, [rax+0F8h]
0x1400820e9  call    _guard_dispatch_icall
0x1400820ee  mov     rcx, rax; DeviceObject
0x1400820f1  call    cs:__imp_IoAllocateWorkItem
0x1400820f8  nop     dword ptr [rax+rax+00h]
0x1400820fd  xor     edi, edi
0x1400820ff  mov     [rbx+510h], rax
0x140082106  test    rax, rax
0x140082109  jnz     short loc_140082183
0x14008210b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140082112  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082119  jz      short loc_140082179
0x14008211b  mov     rax, cs:WdfFunctions_01033
0x140082122  mov     rdx, r15
0x140082125  movzx   ebx, byte ptr [r14+2]
0x14008212a  mov     r8, cs:off_14006C1A8
0x140082131  mov     rcx, cs:WdfDriverGlobals
0x140082138  mov     rax, [rax+650h]
0x14008213f  shr     ebx, 7
0x140082142  call    _guard_dispatch_icall
0x140082147  movzx   ecx, byte ptr [r14+2]
0x14008214c  lea     r9d, [rdi+13h]
0x140082150  btr     ecx, 7
0x140082154  mov     r8d, r12d
0x140082157  movzx   eax, byte ptr [rax+8Fh]
0x14008215e  lea     edx, [rbx+rcx*2]
0x140082161  mov     rcx, [rsi+48h]
0x140082165  mov     [rsp+110h+var_E0], edx
0x140082169  mov     dl, 2
0x14008216b  mov     [rsp+110h+var_E8], eax
0x14008216f  mov     [rsp+110h+var_F0], r13
0x140082174  call    WPP_RECORDER_SF_DD
0x140082179  mov     edi, 0C000009Ah
0x14008217e  jmp     loc_14008250C
0x140082183  mov     ecx, 7D0h
0x140082188  mov     [rbx+4A8h], edi
0x14008218e  mov     [rbx+48Ch], ecx
0x140082194  lea     rax, ESMStateTable
0x14008219b  mov     [rbx+508h], ecx
0x1400821a1  mov     rcx, rsi
0x1400821a4  mov     [rbx+500h], rax
0x1400821ab  mov     [rbx+4F8h], rbx
0x1400821b2  call    Controller_IsSecureDevice
0x1400821b7  mov     [rbx+532h], al
0x1400821bd  mov     rax, cs:g_WdfDriverUsbXhciContext
0x1400821c4  cmp     [rax+1Ch], dil
0x1400821c8  jz      short loc_1400821DB
0x1400821ca  mov     eax, [rsi+52Ch]
0x1400821d0  test    al, 1
0x1400821d2  jz      short loc_1400821DB
  ... truncated ...
```
