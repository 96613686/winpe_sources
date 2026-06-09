# UxSslConnectionHandshakeCompletion

- ea: `0x140009a90`
- end: `0x14000a343`
- name: `UxSslConnectionHandshakeCompletion`
- size: `2227`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140079aa4`

## callees

- `0x140009a90`
- `0x14000a350`
- `0x14000a37c`
- `0x140022610`
- `0x14004ebe0`
- `0x140065a10`
- `0x140093150`
- `0x1400a9b00`
- `0x1400abee0`
- `0x1400b42a0`
- `0x1400ee29c`
- `0x14013a238`
- `0x1401678f0`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d5060`
- `0x1401d9f54`
- `0x1401da4fc`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140009d1b`
- `ntoskrnl!IofCompleteRequest` at `0x140009e85`
- `ntoskrnl!IofCompleteRequest` at `0x140009d1b`
- `ntoskrnl!IofCompleteRequest` at `0x140009e85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009bea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009bea`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009b65`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009baf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009b65`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009baf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009bde`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009bde`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140009afa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140009afa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009ae5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009ae5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b92`

## pseudocode

```c
__int64 __fastcall UxSslConnectionHandshakeCompletion(__int64 a1)
{
  char v2; // r13
  char v3; // r12
  KIRQL v4; // r14
  int v5; // edi
  unsigned int v6; // ecx
  KIRQL v7; // al
  _BYTE *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  IRP *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 Status; // r9
  NTSTATUS v16; // edi
  __int64 v17; // r9
  int v18; // eax
  ULONG_PTR v19; // rdx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  IRP *v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  NTSTATUS v27; // edi
  __int64 v28; // r9
  int v29; // eax
  ULONG_PTR v30; // rdx
  unsigned int v31; // ebx
  __int64 v32; // rcx
  int v33; // edx
  unsigned int v34; // r8d
  int v35; // ecx
  int v36; // eax
  int v37; // eax
  __int64 v38; // r9
  __int64 v39; // rax
  __int64 v40; // rcx
  int v42; // edx
  int v43; // ecx
  int v44; // esi
  ULONG_PTR v45; // rdx
  char v46; // di
  _BYTE *v47; // rbx
  _BYTE *v48; // r14
  unsigned int v49; // ecx
  unsigned int v50; // edx
  unsigned int v51; // ecx
  _QWORD v52[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v53[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v54; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v55; // [rsp+A8h] [rbp+38h] BYREF

  v52[0] = v52;
  v2 = 0;
  v52[1] = v52;
  v53[0] = v53;
  v53[1] = v53;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 93, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, a1);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 208, 0);
  if ( !*(_BYTE *)(a1 + 232) )
  {
    v3 = 1;
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 248));
    if ( *(_BYTE *)(a1 + 356) && (*(_DWORD *)(a1 + 352) & 1) != 0 )
    {
      if ( (BYTE2(xmmword_1401A2CA0) & 8) != 0 )
        WPP_SF_qLd(1043, 16, WPP_94ca9e589e4f3da486b24c2e49372186_Traceguids, a1 + 256, *(_DWORD *)(a1 + 256), 12);
      *(_DWORD *)(a1 + 300) = 0;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 248), v4);
    v5 = 33792;
    v6 = *(_DWORD *)(*(_QWORD *)(a1 + 432) + 804LL);
    if ( v6 )
    {
      if ( v6 <= 0x8400 )
        v6 = 33792;
      v5 = v6;
    }
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1328));
    *(_DWORD *)(a1 + 1340) = v5;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1328), v7);
    v8 = (_BYTE *)(a1 + 233);
    *(_BYTE *)(a1 + 232) = 0;
    *(_BYTE *)(a1 + 234) = 0;
    goto LABEL_76;
  }
  v46 = 0;
  v8 = (_BYTE *)(a1 + 233);
  v47 = (_BYTE *)(a1 + 234);
  if ( *(_BYTE *)(a1 + 233) )
  {
    if ( !*v47 )
      goto LABEL_75;
    v48 = (_BYTE *)(a1 + 233);
  }
  else
  {
    v48 = (_BYTE *)(a1 + 233);
  }
  if ( (*(_DWORD *)(a1 + 1184) & 4) != 0 )
  {
    v46 = 1;
    UxSslStopRenegotiationTimer(a1);
    v8 = v48;
  }
LABEL_75:
  v3 = 0;
  *(_BYTE *)(a1 + 232) = 0;
  *v47 = 0;
  if ( v46 )
  {
LABEL_76:
    v42 = *(_DWORD *)(a1 + 1184);
    *v8 = 0;
    if ( (v42 & 4) != 0 )
    {
      v49 = v42 & 0xFFFFFFF1 | 8;
      v50 = v42 & 0xFFFFFFE1 | 0x18;
      v51 = v49 & 0xFFFFFFEF;
      if ( !*(_QWORD *)(a1 + 1264) )
        v50 = v51;
      *(_DWORD *)(a1 + 1184) = v50;
      UlSiqDequeueIrps((PKSPIN_LOCK)(a1 + 1192));
      UlSiqDequeueIrps((PKSPIN_LOCK)(a1 + 1224));
    }
  }
  v43 = *(_DWORD *)(a1 + 1296);
  if ( (v43 & 2) != 0 )
  {
    v43 &= ~2u;
    *(_DWORD *)(a1 + 1296) = v43;
  }
  if ( (*(_DWORD *)(a1 + 1184) & 2) == 0 && *(_QWORD *)(a1 + 1304) != a1 + 1304 )
  {
    v2 = 1;
    *(_DWORD *)(a1 + 1296) = v43 | 1;
  }
  ExReleasePushLockExclusiveEx(a1 + 208, 0);
  KeLeaveCriticalRegion();
  while ( 1 )
  {
    v9 = (_QWORD *)v52[0];
    if ( (_QWORD *)v52[0] == v52 )
      break;
    if ( *(_QWORD **)(v52[0] + 8LL) != v52 || (v10 = *(_QWORD *)v52[0], *(_QWORD *)(*(_QWORD *)v52[0] + 8LL) != v52[0]) )
LABEL_33:
      __fastfail(3u);
    v52[0] = *(_QWORD *)v52[0];
    *(_QWORD *)(v10 + 8) = v52;
    *v9 = 0;
    v11 = (IRP *)(v9 - 21);
    v9[1] = 0;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qqD(1041, 102, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, v9 - 21, a1, 0);
    UxSslCopyClientCertToIrp(v11);
    Status = (unsigned int)v11->IoStatus.Status;
    if ( (int)Status < 0 )
    {
      v13 = *(_QWORD *)(a1 + 1696);
      if ( (*(_BYTE *)(v13 + 1762) & 2) != 0 )
      {
        if ( !*(_QWORD *)(v13 + 1776) )
          goto LABEL_115;
        if ( (unsigned __int8)UlEtwEvaluateFilter(
                                v13,
                                a1 + 88,
                                a1 + 116,
                                0,
                                *(_QWORD *)(a1 + 1656),
                                *(unsigned __int16 *)(a1 + 1648),
                                0,
                                0) )
        {
          Status = (unsigned int)v11->IoStatus.Status;
LABEL_115:
          McTemplateK0qp_EtwWriteTransfer(
            *(_QWORD *)(a1 + 1696) + 1688LL,
            HTTP_EVENT_SSL_RECEIVE_CLIENT_CERT_COMPLETE,
            a1 + 72,
            Status,
            a1);
        }
      }
      if ( (BYTE10(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_qD(785, 103, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, a1, v11->IoStatus.Status);
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 104, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
    v16 = v11->IoStatus.Status;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qdq(v13, v12, v14, v11, v16, a1);
    UxpSslSetIrpConnection(v11, 0);
    v18 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 20));
    if ( UxDebugCheckRefcount && v18 <= -1 )
      UlBugCheckEx(3u, a1 + 20, 0x3Bu, v18);
    if ( !v18 )
    {
      v19 = a1 + 160;
      if ( *(_QWORD *)(a1 + 160) || *(_QWORD *)(a1 + 176) || *(_QWORD *)(a1 + 192) )
        UlBugCheckEx(1u, v19, (ULONG_PTR)"minio\\http\\sys\\sslconn.h", 0x500u);
      LOBYTE(v17) = 1;
      UlThreadPoolEnqueueWorkItem(1, v19, UxSslFreeConnection, v17, *(_QWORD *)(a1 + 1688), -1);
    }
    v11->IoStatus.Status = v16;
    IofCompleteRequest(v11, 0);
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 100, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
  }
  while ( 2 )
  {
    v20 = (_QWORD *)v53[0];
    if ( (_QWORD *)v53[0] != v53 )
    {
      if ( *(_QWORD **)(v53[0] + 8LL) != v53 )
        goto LABEL_33;
      v21 = *(_QWORD *)v53[0];
      if ( *(_QWORD *)(*(_QWORD *)v53[0] + 8LL) != v53[0] )
        goto LABEL_33;
      v53[0] = *(_QWORD *)v53[0];
      *(_QWORD *)(v21 + 8) = v53;
      *v20 = 0;
      v22 = (IRP *)(v20 - 21);
      v20[1] = 0;
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qqD(1041, 102, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, v20 - 21, a1, 1);
      UxSslCopyClientCertToIrp(v22);
      v26 = (unsigned int)v22->IoStatus.Status;
      if ( (int)v26 >= 0 )
        goto LABEL_40;
      v24 = *(_QWORD *)(a1 + 1696);
      if ( (*(_BYTE *)(v24 + 1762) & 2) != 0 )
      {
        if ( !*(_QWORD *)(v24 + 1776) )
          goto LABEL_122;
        if ( (unsigned __int8)UlEtwEvaluateFilter(
                                v24,
                                a1 + 88,
                                a1 + 116,
                                0,
                                *(_QWORD *)(a1 + 1656),
                                *(unsigned __int16 *)(a1 + 1648),
                                0,
                                0) )
        {
          v26 = (unsigned int)v22->IoStatus.Status;
LABEL_122:
          McTemplateK0qp_EtwWriteTransfer(
            *(_QWORD *)(a1 + 1696) + 1688LL,
            HTTP_EVENT_SSL_RECEIVE_CLIENT_CERT_COMPLETE,
            a1 + 72,
            v26,
            a1);
        }
      }
      if ( (BYTE10(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_qD(785, 103, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, a1, v22->IoStatus.Status);
LABEL_40:
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 104, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
      v27 = v22->IoStatus.Status;
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qdq(v24, v23, v25, v22, v27, a1);
      UxpSslSetIrpConnection(v22, 0);
      v29 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 20));
      if ( UxDebugCheckRefcount && v29 <= -1 )
        UlBugCheckEx(3u, a1 + 20, 0x3Bu, v29);
      if ( !v29 )
      {
        v30 = a1 + 160;
        if ( *(_QWORD *)(a1 + 160) || *(_QWORD *)(a1 + 176) || *(_QWORD *)(a1 + 192) )
          UlBugCheckEx(1u, v30, (ULONG_PTR)"minio\\http\\sys\\sslconn.h", 0x500u);
        LOBYTE(v28) = 1;
        UlThreadPoolEnqueueWorkItem(1, v30, UxSslFreeConnection, v28, *(_QWORD *)(a1 + 1688), -1);
      }
      v22->IoStatus.Status = v27;
      IofCompleteRequest(v22, 0);
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 100, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
      continue;
    }
    break;
  }
  v31 = 0;
  if ( v2 )
    UxSslPostsendCheck(a1);
  v32 = *(_QWORD *)(a1 + 1696);
  if ( (*(_BYTE *)(v32 + 1762) & 1) != 0
    && (!*(_QWORD *)(v32 + 1776)
     || (unsigned __int8)UlEtwEvaluateFilter(
                           v32,
                           a1 + 88,
                           a1 + 116,
                           0,
                           *(_QWORD *)(a1 + 1656),
                           *(unsigned __int16 *)(a1 + 1648),
                           0,
                           0)) )
  {
    McTemplateK0qp_EtwWriteTransfer(*(_QWORD *)(a1 + 1696) + 1688LL, HTTP_EVENT_SSL_HANDSHAKE_COMPLETE, a1 + 72, 0, a1);
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qD(1041, 94, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, a1, 0);
  if ( v3 )
  {
    v33 = *(_DWORD *)(a1 + 1180);
    if ( v33 == 1 )
    {
      v34 = 1;
    }
    else if ( v33 )
    {
      v34 = 3;
      if ( v33 != 2 )
        v34 = 0;
    }
    else
    {
      v34 = 2;
    }
    UlTelemetrySslHandshakeCompletion(
      v34,
      1000LL * *(_QWORD *)(a1 + 1704) / (unsigned __int64)UxPerformanceCounterPeriod);
    v35 = 32;
    if ( *(_DWORD *)(a1 + 1180) )
      v35 = 0;
    v36 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
    if ( UxDebugCheckRefcount && v36 <= -1 )
      UlBugCheckEx(3u, a1 + 20, 0x37u, v36);
    v54 = 0;
    v55 = 0;
    v37 = UxDuoAttachConnection(a1, (unsigned int)&UxSslDispatch, (unsigned int)&v54, (unsigned int)&v55, v35);
    v31 = v37;
    if ( v37 < 0 )
    {
      if ( (BYTE2(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_qD(529, 95, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, a1, v37);
      v44 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 20));
      if ( UxDebugCheckRefcount && v44 <= -1 )
        UlBugCheckEx(3u, a1 + 20, 0x37u, v44);
      if ( !v44 )
      {
        v45 = a1 + 160;
        if ( *(_QWORD *)(a1 + 160) || *(_QWORD *)(a1 + 176) || *(_QWORD *)(a1 + 192) )
          UlBugCheckEx(1u, v45, (ULONG_PTR)"minio\\http\\sys\\sslconn.h", 0x500u);
        LOBYTE(v38) = 1;
        UlThreadPoolEnqueueWorkItem(1, v45, UxSslFreeConnection, v38, *(_QWORD *)(a1 + 1688), -1);
      }
    }
    else
    {
      *(_QWORD *)(a1 + 24) = v54;
      v39 = v55;
      *(_DWORD *)(a1 + 40) = 2;
      *(_QWORD *)(a1 + 32) = v39;
      v40 = *(_QWORD *)(a1 + 24);
      *(_DWORD *)(a1 + 40) = 3;
      (*(void (__fastcall **)(__int64))(v39 + 24))(v40);
    }
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 96, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, v31);
  return v31;
}

```

## disassembly

```asm
0x140009a90  push    rbp
0x140009a92  push    rsi
0x140009a93  push    r13
0x140009a95  push    r14
0x140009a97  push    r15
0x140009a99  mov     rbp, rsp
0x140009a9c  sub     rsp, 70h
0x140009aa0  lea     rax, [rbp+var_30]
0x140009aa4  mov     r15, rcx
0x140009aa7  mov     [rbp+var_30], rax
0x140009aab  xor     r13b, r13b
0x140009aae  lea     rax, [rbp+var_30]
0x140009ab2  mov     [rbp+var_28], rax
0x140009ab6  lea     rax, [rbp+var_20]
0x140009aba  mov     [rbp+var_20], rax
0x140009abe  lea     rax, [rbp+var_20]
0x140009ac2  mov     [rbp+var_18], rax
0x140009ac6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009acd  jnz     loc_14000A135
0x140009ad3  mov     [rsp+70h+arg_10], rbx
0x140009adb  mov     [rsp+70h+var_8], rdi
0x140009ae0  mov     [rsp+70h+var_10], r12
0x140009ae5  call    cs:__imp_KeEnterCriticalRegion
0x140009aec  nop     dword ptr [rax+rax+00h]
0x140009af1  xor     edx, edx
0x140009af3  lea     rcx, [r15+0D0h]
0x140009afa  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140009b01  nop     dword ptr [rax+rax+00h]
0x140009b06  cmp     [r15+0E8h], r13b
0x140009b0d  jnz     loc_14000A153
0x140009b13  lea     rcx, [r15+0F8h]; SpinLock
0x140009b1a  mov     r12b, 1
0x140009b1d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009b24  nop     dword ptr [rax+rax+00h]
0x140009b29  movzx   r14d, al
0x140009b2d  cmp     [r15+164h], r13b
0x140009b34  jz      short loc_140009B5A
0x140009b36  mov     ecx, [r15+160h]
0x140009b3d  test    r12b, cl
0x140009b40  jz      short loc_140009B5A
0x140009b42  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x140009b49  jnz     loc_14000A182
0x140009b4f  mov     dword ptr [r15+12Ch], 0
0x140009b5a  movzx   edx, r14b; NewIrql
0x140009b5e  lea     rcx, [r15+0F8h]; SpinLock
0x140009b65  call    cs:__imp_KeReleaseSpinLock
0x140009b6c  nop     dword ptr [rax+rax+00h]
0x140009b71  mov     rax, [r15+1B0h]
0x140009b78  mov     edi, 8400h
0x140009b7d  mov     ecx, [rax+324h]
0x140009b83  test    ecx, ecx
0x140009b85  jnz     loc_14000A1B7
0x140009b8b  lea     rcx, [r15+530h]; SpinLock
0x140009b92  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009b99  nop     dword ptr [rax+rax+00h]
0x140009b9e  lea     rcx, [r15+530h]; SpinLock
0x140009ba5  mov     [r15+53Ch], edi
0x140009bac  movzx   edx, al; NewIrql
0x140009baf  call    cs:__imp_KeReleaseSpinLock
0x140009bb6  nop     dword ptr [rax+rax+00h]
0x140009bbb  lea     rcx, [r15+0E9h]
0x140009bc2  mov     [r15+0E8h], r13b
0x140009bc9  mov     [r15+0EAh], r13b
0x140009bd0  jmp     loc_14000A04E
0x140009bd5  xor     edx, edx
0x140009bd7  lea     rcx, [r15+0D0h]
0x140009bde  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140009be5  nop     dword ptr [rax+rax+00h]
0x140009bea  call    cs:__imp_KeLeaveCriticalRegion
0x140009bf1  nop     dword ptr [rax+rax+00h]
0x140009bf6  mov     esi, 0FFFFFFFFh
0x140009bfb  nop     dword ptr [rax+rax+00h]
0x140009c00  mov     rax, [rbp+var_30]
0x140009c04  lea     rcx, [rbp+var_30]
0x140009c08  cmp     rax, rcx
0x140009c0b  jz      loc_140009D72
0x140009c11  lea     rcx, [rbp+var_30]
0x140009c15  cmp     [rax+8], rcx
0x140009c19  jnz     loc_140009D6B
0x140009c1f  mov     rcx, [rax]
0x140009c22  cmp     [rcx+8], rax
0x140009c26  jnz     loc_140009D6B
0x140009c2c  mov     [rbp+var_30], rcx
0x140009c30  lea     rdx, [rbp+var_30]
0x140009c34  xor     edi, edi
0x140009c36  mov     [rcx+8], rdx
0x140009c3a  mov     [rax], rdi
0x140009c3d  lea     rbx, [rax-0A8h]
0x140009c44  mov     [rax+8], rdi
0x140009c48  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009c4f  jnz     loc_14000A1D2
0x140009c55  xor     r8d, r8d
0x140009c58  lea     rdx, [r15+4A0h]
0x140009c5f  mov     rcx, rbx; Irp
0x140009c62  call    UxSslCopyClientCertToIrp
0x140009c67  mov     r9d, [rbx+30h]
0x140009c6b  test    r9d, r9d
0x140009c6e  js      loc_1401708B7
0x140009c74  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009c7b  jnz     loc_14000A1F9
0x140009c81  mov     edi, [rbx+30h]
0x140009c84  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009c8b  jnz     loc_14000A214
0x140009c91  xor     edx, edx
0x140009c93  mov     rcx, rbx
0x140009c96  call    UxpSslSetIrpConnection
0x140009c9b  lea     rdx, [r15+14h]; BugCheckParameter2
0x140009c9f  mov     eax, esi
0x140009ca1  lock xadd [rdx], eax
0x140009ca5  dec     eax
0x140009ca7  cmp     cs:UxDebugCheckRefcount, 0
0x140009cae  jnz     loc_140009D4F
0x140009cb4  test    eax, eax
0x140009cb6  jnz     short loc_140009D13
0x140009cb8  lea     rdx, [r15+0A0h]; BugCheckParameter2
0x140009cbf  cmp     qword ptr [rdx], 0
0x140009cc3  jnz     short loc_140009CD3
0x140009cc5  cmp     qword ptr [rdx+10h], 0
0x140009cca  jnz     short loc_140009CD3
0x140009ccc  cmp     qword ptr [rdx+20h], 0
0x140009cd1  jz      short loc_140009CEB
0x140009cd3  mov     r9d, 500h; BugCheckParameter4
0x140009cd9  lea     r8, aMinioHttpSysSs_0; "minio\\http\\sys\\sslconn.h"
0x140009ce0  mov     ecx, 1; BugCheckParameter1
0x140009ce5  call    UlBugCheckEx
0x140009ceb  mov     rax, [r15+698h]
0x140009cf2  lea     r8, UxSslFreeConnection
0x140009cf9  mov     dword ptr [rsp+70h+var_48], 0FFFFFFFFh
0x140009d01  mov     r9b, 1
0x140009d04  mov     ecx, 1
0x140009d09  mov     [rsp+70h+var_50], rax
0x140009d0e  call    UlThreadPoolEnqueueWorkItem
0x140009d13  xor     edx, edx; PriorityBoost
0x140009d15  mov     [rbx+30h], edi
0x140009d18  mov     rcx, rbx; Irp
0x140009d1b  call    cs:__imp_IofCompleteRequest
0x140009d22  nop     dword ptr [rax+rax+00h]
0x140009d27  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009d2e  jz      loc_140009C00
0x140009d34  mov     edx, 64h ; 'd'
0x140009d39  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x140009d40  mov     ecx, 411h
0x140009d45  call    WPP_SF_
0x140009d4a  jmp     loc_140009C00
0x140009d4f  cmp     eax, esi
0x140009d51  jg      loc_140009CB4
0x140009d57  movsxd  r9, eax; BugCheckParameter4
0x140009d5a  mov     ecx, 3; BugCheckParameter1
0x140009d5f  mov     r8d, 3Bh ; ';'; BugCheckParameter3
0x140009d65  call    UlBugCheckEx
0x140009d6b  mov     ecx, 3
0x140009d70  int     29h; Win8: RtlFailFast(ecx)
0x140009d72  mov     rax, [rbp+var_20]
0x140009d76  lea     rcx, [rbp+var_20]
0x140009d7a  cmp     rax, rcx
0x140009d7d  jz      loc_140009ED5
0x140009d83  lea     rcx, [rbp+var_20]
0x140009d87  cmp     [rax+8], rcx
0x140009d8b  jnz     short loc_140009D6B
0x140009d8d  mov     rcx, [rax]
0x140009d90  cmp     [rcx+8], rax
0x140009d94  jnz     short loc_140009D6B
0x140009d96  mov     [rbp+var_20], rcx
0x140009d9a  lea     rdx, [rbp+var_20]
0x140009d9e  xor     edi, edi
0x140009da0  mov     [rcx+8], rdx
0x140009da4  mov     [rax], rdi
0x140009da7  lea     rbx, [rax-0A8h]
0x140009dae  mov     [rax+8], rdi
0x140009db2  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009db9  jnz     loc_14000A22A
0x140009dbf  mov     r8b, 1
0x140009dc2  lea     rdx, [r15+4A0h]
0x140009dc9  mov     rcx, rbx; Irp
0x140009dcc  call    UxSslCopyClientCertToIrp
0x140009dd1  mov     r9d, [rbx+30h]
0x140009dd5  test    r9d, r9d
0x140009dd8  js      loc_14017095F
0x140009dde  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009de5  jnz     loc_14000A255
0x140009deb  mov     edi, [rbx+30h]
0x140009dee  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009df5  jnz     loc_14000A270
0x140009dfb  xor     edx, edx
0x140009dfd  mov     rcx, rbx
0x140009e00  call    UxpSslSetIrpConnection
0x140009e05  lea     rdx, [r15+14h]; BugCheckParameter2
0x140009e09  mov     eax, esi
0x140009e0b  lock xadd [rdx], eax
0x140009e0f  dec     eax
0x140009e11  cmp     cs:UxDebugCheckRefcount, 0
0x140009e18  jnz     loc_140009EB9
0x140009e1e  test    eax, eax
0x140009e20  jnz     short loc_140009E7D
0x140009e22  lea     rdx, [r15+0A0h]; BugCheckParameter2
0x140009e29  cmp     qword ptr [rdx], 0
0x140009e2d  jnz     short loc_140009E3D
0x140009e2f  cmp     qword ptr [rdx+10h], 0
0x140009e34  jnz     short loc_140009E3D
0x140009e36  cmp     qword ptr [rdx+20h], 0
0x140009e3b  jz      short loc_140009E55
0x140009e3d  mov     r9d, 500h; BugCheckParameter4
0x140009e43  lea     r8, aMinioHttpSysSs_0; "minio\\http\\sys\\sslconn.h"
0x140009e4a  mov     ecx, 1; BugCheckParameter1
0x140009e4f  call    UlBugCheckEx
0x140009e55  mov     rax, [r15+698h]
0x140009e5c  lea     r8, UxSslFreeConnection
0x140009e63  mov     dword ptr [rsp+70h+var_48], 0FFFFFFFFh
0x140009e6b  mov     r9b, 1
0x140009e6e  mov     ecx, 1
0x140009e73  mov     [rsp+70h+var_50], rax
0x140009e78  call    UlThreadPoolEnqueueWorkItem
0x140009e7d  xor     edx, edx; PriorityBoost
0x140009e7f  mov     [rbx+30h], edi
0x140009e82  mov     rcx, rbx; Irp
0x140009e85  call    cs:__imp_IofCompleteRequest
0x140009e8c  nop     dword ptr [rax+rax+00h]
0x140009e91  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009e98  jz      loc_140009D72
0x140009e9e  mov     edx, 64h ; 'd'
0x140009ea3  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x140009eaa  mov     ecx, 411h
0x140009eaf  call    WPP_SF_
0x140009eb4  jmp     loc_140009D72
0x140009eb9  cmp     eax, esi
0x140009ebb  jg      loc_140009E1E
0x140009ec1  movsxd  r9, eax; BugCheckParameter4
0x140009ec4  mov     ecx, 3; BugCheckParameter1
0x140009ec9  mov     r8d, 3Bh ; ';'; BugCheckParameter3
0x140009ecf  call    UlBugCheckEx
0x140009ed5  xor     r14d, r14d
0x140009ed8  mov     ebx, r14d
0x140009edb  test    r13b, r13b
0x140009ede  jnz     loc_14000A286
0x140009ee4  mov     rcx, [r15+6A0h]
0x140009eeb  test    byte ptr [rcx+6E2h], 1
0x140009ef2  jnz     loc_14000A293
0x140009ef8  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009eff  jnz     loc_14000A2DF
0x140009f05  test    r12b, r12b
0x140009f08  jz      loc_140009FC3
0x140009f0e  imul    rax, [r15+6A8h], 3E8h
0x140009f19  xor     edx, edx
0x140009f1b  div     cs:UxPerformanceCounterPeriod
0x140009f22  mov     edx, [r15+49Ch]
0x140009f29  cmp     edx, 1
0x140009f2c  jnz     loc_140009FEE
0x140009f32  mov     r8d, edx
0x140009f35  mov     rdx, rax
0x140009f38  mov     ecx, r8d
0x140009f3b  call    UlTelemetrySslHandshakeCompletion
0x140009f40  cmp     [r15+49Ch], ebx
0x140009f47  mov     ecx, 20h ; ' '
0x140009f4c  mov     eax, 1
0x140009f51  cmovnz  ecx, r14d
0x140009f55  lock xadd [r15+14h], eax
0x140009f5b  inc     eax
0x140009f5d  cmp     cs:UxDebugCheckRefcount, bl
0x140009f63  jnz     loc_14000A001
0x140009f69  mov     dword ptr [rsp+70h+var_50], ecx
0x140009f6d  lea     r9, [rbp+arg_8]
0x140009f71  mov     rcx, r15
0x140009f74  mov     [rbp+arg_0], r14
0x140009f78  lea     r8, [rbp+arg_0]
0x140009f7c  mov     [rbp+arg_8], r14
0x140009f80  lea     rdx, UxSslDispatch
0x140009f87  call    UxDuoAttachConnection
0x140009f8c  mov     ebx, eax
0x140009f8e  test    eax, eax
0x140009f90  js      loc_14000A314
0x140009f96  mov     rax, [rbp+arg_0]
0x140009f9a  mov     [r15+18h], rax
0x140009f9e  mov     rax, [rbp+arg_8]
0x140009fa2  mov     dword ptr [r15+28h], 2
0x140009faa  mov     [r15+20h], rax
0x140009fae  mov     rcx, [r15+18h]
0x140009fb2  mov     dword ptr [r15+28h], 3
0x140009fba  mov     rax, [rax+18h]
0x140009fbe  call    _guard_dispatch_icall
0x140009fc3  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140009fca  jnz     short loc_14000A021
0x140009fcc  mov     r12, [rsp+70h+var_10]
0x140009fd1  mov     eax, ebx
0x140009fd3  mov     rbx, [rsp+70h+arg_10]
0x140009fdb  mov     rdi, [rsp+70h+var_8]
0x140009fe0  add     rsp, 70h
0x140009fe4  pop     r15
0x140009fe6  pop     r14
0x140009fe8  pop     r13
0x140009fea  pop     rsi
0x140009feb  pop     rbp
0x140009fec  retn
0x140009fee  test    edx, edx
0x140009ff0  jnz     loc_14000A302
0x140009ff6  mov     r8d, 2
0x140009ffc  jmp     loc_140009F35
0x14000a001  cmp     eax, esi
0x14000a003  jg      loc_140009F69
0x14000a009  movsxd  r9, eax; BugCheckParameter4
0x14000a00c  lea     rdx, [r15+14h]; BugCheckParameter2
  ... truncated ...
```
