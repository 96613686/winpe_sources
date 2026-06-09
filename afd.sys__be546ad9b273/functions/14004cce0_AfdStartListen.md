# AfdStartListen

- ea: `0x14004cce0`
- end: `0x14004d29d`
- name: `AfdStartListen`
- size: `1469`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14000d4b0`
- `0x14002c728`
- `0x14002fd7c`
- `0x1400303e8`
- `0x1400338b8`
- `0x140036c24`
- `0x1400445d8`
- `0x1400476c0`
- `0x14004cce0`
- `0x14004da5c`
- `0x140072840`
- `0x140072870`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x14004cf0d`
- `ntoskrnl!InitializeSListHead` at `0x14004cf70`
- `ntoskrnl!InitializeSListHead` at `0x14004cff7`
- `ntoskrnl!InitializeSListHead` at `0x14004cf0d`
- `ntoskrnl!InitializeSListHead` at `0x14004cf70`
- `ntoskrnl!InitializeSListHead` at `0x14004cff7`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004cd7a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004cd7a`
- `ntoskrnl!IofCompleteRequest` at `0x14004d264`
- `ntoskrnl!IofCompleteRequest` at `0x14004d264`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d034`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d1f4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d034`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d1f4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004cfae`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d1b9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004cfae`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d1b9`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004cdc0`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004cdc0`

## pseudocode

```c
__int64 __fastcall AfdStartListen(PIRP Irp, __int64 a2)
{
  __int64 v3; // rbx
  int v4; // edx
  NTSTATUS v5; // edi
  KPROCESSOR_MODE RequestorMode; // cl
  void *v7; // rdx
  HANDLE CurrentProcessId; // rax
  unsigned int v9; // ecx
  int v10; // eax
  int v11; // edx
  char v12; // al
  unsigned __int16 v13; // r13
  unsigned __int16 v14; // r15
  __int64 v15; // rdx
  unsigned int i; // r15d
  int v18; // eax
  unsigned int j; // r15d
  int v20; // eax
  int v21; // eax
  unsigned __int16 v22; // [rsp+30h] [rbp-78h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-60h] BYREF
  __int64 v24; // [rsp+60h] [rbp-48h] BYREF
  char v25; // [rsp+68h] [rbp-40h]

  v24 = 0;
  v25 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  Irp->IoStatus.Information = 0;
  v3 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( *(_DWORD *)(a2 + 16) < 0xCu )
  {
    v4 = 13000;
LABEL_3:
    v5 = -1073741811;
    AFDETW_TRACELISTEN(0, v4, v3, 0, -1073741811);
LABEL_78:
    Irp->IoStatus.Status = v5;
    IofCompleteRequest(Irp, AfdPriorityBoost);
    return (unsigned int)v5;
  }
  v5 = 0;
  RequestorMode = Irp->RequestorMode;
  if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  v7 = *(void **)(a2 + 32);
  if ( RequestorMode )
    RtlCopyFromUser(&v24, v7, 0xCu);
  else
    RtlCopyVolatileMemory(&v24, v7, 0xCu);
  if ( !(_BYTE)v24 && AfdSanServiceHelper )
  {
    if ( (BYTE9(xmmword_1400875E0) & 1) != 0 )
    {
      CurrentProcessId = PsGetCurrentProcessId();
      WPP_SF_q(1288, 10, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids, CurrentProcessId);
    }
    v5 = -1073741574;
    AFDETW_TRACELISTEN(0, 13002, v3, 0, -1073741574);
    goto LABEL_78;
  }
  if ( (*(_DWORD *)(v3 + 8) & 0x100) == 0 || v24 >= 0 )
  {
    v10 = HIDWORD(v24);
    if ( HIDWORD(v24) > 0xC8 )
      v10 = 200;
    if ( !v10 )
      v10 = 1;
LABEL_25:
    HIDWORD(v24) = v10;
    goto LABEL_26;
  }
  v9 = -HIDWORD(v24);
  HIDWORD(v24) = v9;
  if ( v9 < 0xC8 )
  {
    HIDWORD(v24) = 200;
    goto LABEL_26;
  }
  v10 = 0xFFFF;
  if ( v9 > 0xFFFF )
    goto LABEL_25;
LABEL_26:
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 368), *(unsigned __int8 *)(v3 + 2), 0) )
  {
    v4 = 13003;
    goto LABEL_3;
  }
  if ( ((*(_WORD *)v3 + 20528) & 0xFFFD) != 0 )
  {
    v11 = 13004;
LABEL_76:
    v5 = -1073741811;
    AFDETW_TRACELISTEN(0, v11, v3, 0, -1073741811);
LABEL_77:
    _InterlockedExchange((volatile __int32 *)(v3 + 368), 0);
    goto LABEL_78;
  }
  v12 = *(_BYTE *)(v3 + 2);
  if ( v12 != 3 && (v12 != 4 || (*(_BYTE *)(v3 + 6) & 1) == 0)
    || (*(_DWORD *)(v3 + 8) & 1) != 0
    || v25 && (*(_DWORD *)(v3 + 8) & 0x100) == 0 && (*(_DWORD *)(v3 + 16) & 0x80u) == 0 )
  {
    v11 = 13005;
    goto LABEL_76;
  }
  v13 = *(_WORD *)(v3 + 184);
  v14 = *(_WORD *)(v3 + 186);
  v22 = v14;
  *(_QWORD *)(v3 + 104) = v3 + 96;
  *(_QWORD *)(v3 + 96) = v3 + 96;
  *(_QWORD *)(v3 + 120) = v3 + 112;
  *(_QWORD *)(v3 + 112) = v3 + 112;
  *(_QWORD *)(v3 + 136) = v3 + 128;
  *(_QWORD *)(v3 + 128) = v3 + 128;
  InitializeSListHead((PSLIST_HEADER)(v3 + 160));
  *(_DWORD *)(v3 + 184) = 0;
  if ( (*(_DWORD *)(v3 + 8) & 0x100) != 0 )
  {
    *(_BYTE *)(v3 + 189) = 0;
    *(_DWORD *)(v3 + 176) = 0;
    *(_WORD *)(v3 + 190) = WORD2(v24);
  }
  else
  {
    *(_WORD *)(v3 + 190) = WORD2(v24);
    *(_BYTE *)(v3 + 189) = 0;
    *(_DWORD *)(v3 + 176) = 0;
    if ( (*(_DWORD *)(v3 + 8) & 0x400000) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)(v3 + 280) + 48LL) = 0;
      InitializeSListHead((PSLIST_HEADER)(*(_QWORD *)(v3 + 280) + 32LL));
    }
    *(_DWORD *)(v3 + 180) = 0;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
  *(_DWORD *)(v3 + 8) = (v25 != 0 ? 2 : 0) | *(_DWORD *)(v3 + 8) & 0xFFFFFFFD;
  if ( (*(_DWORD *)(v3 + 8) & 2) != 0 )
  {
    *(_QWORD *)(v3 + 152) = v3 + 144;
    *(_QWORD *)(v3 + 144) = v3 + 144;
  }
  else if ( (*(_DWORD *)(v3 + 8) & 0x100) == 0 )
  {
    InitializeSListHead((PSLIST_HEADER)(v3 + 144));
  }
  *(_DWORD *)(v3 + 8) |= 1u;
  *(_WORD *)v3 |= 0xAFD4u;
  AFDETW_TRACELISTEN(0, 13006, v3, SHIDWORD(v24), 0);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (*(_DWORD *)(v3 + 8) & 0x100) == 0 )
  {
    for ( i = 0; i < HIDWORD(v24); ++i )
    {
      v18 = AfdAddFreeConnection(v3, 0);
      v5 = v18;
      if ( v18 < 0 )
      {
        AFDETW_TRACELISTEN(1, 13008, v3, SHIDWORD(v24), v18);
LABEL_70:
        v14 = v22;
        goto LABEL_71;
      }
    }
    if ( (*(_DWORD *)(v3 + 8) & 0x400000) != 0 )
    {
      for ( j = 0; j < HIDWORD(v24); ++j )
      {
        LOBYTE(v15) = 1;
        v20 = AfdAddFreeConnection(v3, v15);
        v5 = v20;
        if ( v20 < 0 )
        {
          AFDETW_TRACELISTEN(1, 13009, v3, SHIDWORD(v24), v20);
          goto LABEL_70;
        }
      }
    }
    if ( (*(_DWORD *)(v3 + 8) & 2) == 0 )
    {
      v21 = AfdSetEventHandler(*(_QWORD *)(v3 + 24), 0, AfdConnectEventHandler, v3);
      v5 = v21;
      if ( v21 < 0 )
      {
        AFDETW_TRACELISTEN(1, 13010, v3, SHIDWORD(v24), v21);
        goto LABEL_70;
      }
      if ( (*(_DWORD *)(v3 + 8) & 0x400000) != 0 )
      {
        v5 = AfdSetEventHandler(*(_QWORD *)(*(_QWORD *)(v3 + 280) + 8LL), 0, AfdConnectEventHandler, v3);
        if ( v5 < 0 )
        {
          AfdSetEventHandler(*(_QWORD *)(v3 + 24), 0, 0, 0);
          AFDETW_TRACELISTEN(1, 13011, v3, SHIDWORD(v24), v5);
          goto LABEL_70;
        }
      }
    }
    AFDETW_TRACELISTEN(1, 13013, v3, 0, v5);
    goto LABEL_77;
  }
  if ( !(unsigned __int8)AfdRefTLBaseEndpoint(v3) )
  {
    v5 = -1073741816;
    AFDETW_TRACELISTEN(1, 13007, v3, SHIDWORD(v24), -1073741816);
LABEL_71:
    if ( (*(_DWORD *)(v3 + 8) & 0x100) == 0 )
      AfdFreeQueuedConnections(v3);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
    *(_DWORD *)(v3 + 8) &= ~1u;
    *(_DWORD *)(v3 + 8) &= ~2u;
    *(_WORD *)v3 &= ~4u;
    *(_WORD *)(v3 + 184) = v13;
    *(_WORD *)(v3 + 186) = v14;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_77;
  }
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  if ( (*(_DWORD *)(v3 + 8) & 2) != 0 )
    AfdTLDelayAcceptListen(Irp, v3, v14, v13);
  else
    AfdTLListen(Irp);
  return 259;
}

```

## disassembly

```asm
0x14004cce0  mov     r11, rsp
0x14004cce3  mov     [r11+18h], rbx
0x14004cce7  mov     [r11+20h], rsi
0x14004cceb  push    rdi
0x14004ccec  push    r12
0x14004ccee  push    r13
0x14004ccf0  push    r14
0x14004ccf2  push    r15
0x14004ccf4  sub     rsp, 80h
0x14004ccfb  mov     rax, cs:__security_cookie
0x14004cd02  xor     rax, rsp
0x14004cd05  mov     [rsp+0A8h+var_38], rax
0x14004cd0a  mov     r14, rcx
0x14004cd0d  mov     [rsp+0A8h+var_68], rcx
0x14004cd12  xor     eax, eax
0x14004cd14  mov     [r11-48h], rax
0x14004cd18  mov     [rsp+0A8h+var_40], al
0x14004cd1c  xorps   xmm0, xmm0
0x14004cd1f  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14004cd24  mov     [r11-50h], rax
0x14004cd28  mov     [rcx+38h], rax
0x14004cd2c  mov     rax, [rdx+30h]
0x14004cd30  mov     rbx, [rax+18h]
0x14004cd34  mov     [rsp+0A8h+var_70], rbx
0x14004cd39  mov     r8d, 0Ch
0x14004cd3f  cmp     [rdx+10h], r8d
0x14004cd43  jnb     short loc_14004CD67
0x14004cd45  mov     edx, 32C8h
0x14004cd4a  mov     eax, 0C000000Dh
0x14004cd4f  mov     [rsp+0A8h+var_88], eax
0x14004cd53  mov     edi, eax
0x14004cd55  xor     r9d, r9d
0x14004cd58  mov     r8, rbx
0x14004cd5b  xor     ecx, ecx
0x14004cd5d  call    AFDETW_TRACELISTEN
0x14004cd62  jmp     loc_14004D257
0x14004cd67  xor     edi, edi
0x14004cd69  mov     [rsp+0A8h+var_74], edi
0x14004cd6d  mov     cl, [rcx+40h]
0x14004cd70  test    cl, cl
0x14004cd72  jz      short loc_14004CD87
0x14004cd74  test    byte ptr [rdx+20h], 3
0x14004cd78  jz      short loc_14004CD87
0x14004cd7a  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14004cd81  nop     dword ptr [rax+rax+00h]
0x14004cd86  int     3; Trap to Debugger
0x14004cd87  mov     rdx, [rdx+20h]; Src
0x14004cd8b  test    cl, cl
0x14004cd8d  lea     rcx, [rsp+0A8h+var_48]; void *
0x14004cd92  jz      short loc_14004CD9B
0x14004cd94  call    RtlCopyFromUser
0x14004cd99  jmp     short loc_14004CDA1
0x14004cd9b  call    RtlCopyVolatileMemory
0x14004cda0  nop
0x14004cda1  cmp     [rsp+0A8h+var_48], 0
0x14004cda6  jnz     short loc_14004CDF6
0x14004cda8  cmp     cs:AfdSanServiceHelper, 0
0x14004cdb0  jz      short loc_14004CDF6
0x14004cdb2  mov     esi, 1
0x14004cdb7  test    byte ptr cs:xmmword_1400875E0+9, sil
0x14004cdbe  jz      short loc_14004CDE3
0x14004cdc0  call    cs:__imp_PsGetCurrentProcessId
0x14004cdc7  nop     dword ptr [rax+rax+00h]
0x14004cdcc  mov     r9, rax
0x14004cdcf  lea     edx, [rsi+9]
0x14004cdd2  mov     ecx, 508h
0x14004cdd7  lea     r8, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids
0x14004cdde  call    WPP_SF_q
0x14004cde3  mov     edi, 0C00000FAh
0x14004cde8  mov     [rsp+0A8h+var_88], edi
0x14004cdec  mov     edx, 32CAh
0x14004cdf1  jmp     loc_14004CD55
0x14004cdf6  mov     eax, [rbx+8]
0x14004cdf9  bt      eax, 8
0x14004cdfd  jnb     short loc_14004CE31
0x14004cdff  mov     eax, [rsp+0A8h+var_44]
0x14004ce03  test    eax, eax
0x14004ce05  jns     short loc_14004CE31
0x14004ce07  mov     ecx, eax
0x14004ce09  neg     ecx
0x14004ce0b  cmovs   ecx, eax
0x14004ce0e  mov     [rsp+0A8h+var_44], ecx
0x14004ce12  mov     edx, 0C8h
0x14004ce17  mov     esi, 1
0x14004ce1c  cmp     ecx, edx
0x14004ce1e  jnb     short loc_14004CE26
0x14004ce20  mov     [rsp+0A8h+var_44], edx
0x14004ce24  jmp     short loc_14004CE4D
0x14004ce26  mov     eax, 0FFFFh
0x14004ce2b  cmp     ecx, eax
0x14004ce2d  ja      short loc_14004CE49
0x14004ce2f  jmp     short loc_14004CE4D
0x14004ce31  mov     eax, [rsp+0A8h+var_44]
0x14004ce35  mov     edx, 0C8h
0x14004ce3a  cmp     eax, edx
0x14004ce3c  cmova   eax, edx
0x14004ce3f  mov     esi, 1
0x14004ce44  cmp     eax, esi
0x14004ce46  cmovb   eax, esi
0x14004ce49  mov     [rsp+0A8h+var_44], eax
0x14004ce4d  movzx   ecx, byte ptr [rbx+2]
0x14004ce51  xor     eax, eax
0x14004ce53  lock cmpxchg [rbx+170h], ecx
0x14004ce5b  jz      short loc_14004CE67
0x14004ce5d  mov     edx, 32CBh
0x14004ce62  jmp     loc_14004CD4A
0x14004ce67  mov     eax, 5030h
0x14004ce6c  add     ax, [rbx]
0x14004ce6f  mov     ecx, 0FFFDh
0x14004ce74  test    cx, ax
0x14004ce77  jz      short loc_14004CE83
0x14004ce79  mov     edx, 32CCh
0x14004ce7e  jmp     loc_14004D214
0x14004ce83  mov     al, [rbx+2]
0x14004ce86  cmp     al, 3
0x14004ce88  jz      short loc_14004CE9C
0x14004ce8a  cmp     al, 4
0x14004ce8c  jnz     loc_14004D20F
0x14004ce92  test    [rbx+6], sil
0x14004ce96  jz      loc_14004D20F
0x14004ce9c  mov     eax, [rbx+8]
0x14004ce9f  test    sil, al
0x14004cea2  jnz     loc_14004D20F
0x14004cea8  cmp     [rsp+0A8h+var_40], 0
0x14004cead  jz      short loc_14004CECC
0x14004ceaf  mov     eax, [rbx+8]
0x14004ceb2  bt      eax, 8
0x14004ceb6  jb      short loc_14004CECC
0x14004ceb8  mov     eax, [rbx+8]
0x14004cebb  bt      eax, 8
0x14004cebf  jb      short loc_14004CECC
0x14004cec1  mov     eax, [rbx+10h]
0x14004cec4  test    al, al
0x14004cec6  jns     loc_14004D20F
0x14004cecc  movzx   r13d, word ptr [rbx+0B8h]
0x14004ced4  movzx   r15d, word ptr [rbx+0BAh]
0x14004cedc  mov     [rsp+0A8h+var_78], r15w
0x14004cee2  lea     rax, [rbx+60h]
0x14004cee6  mov     [rax+8], rax
0x14004ceea  mov     [rax], rax
0x14004ceed  lea     rax, [rbx+70h]
0x14004cef1  mov     [rax+8], rax
0x14004cef5  mov     [rax], rax
0x14004cef8  lea     rax, [rbx+80h]
0x14004ceff  mov     [rax+8], rax
0x14004cf03  mov     [rax], rax
0x14004cf06  lea     rcx, [rbx+0A0h]; SListHead
0x14004cf0d  call    cs:__imp_InitializeSListHead
0x14004cf14  nop     dword ptr [rax+rax+00h]
0x14004cf19  mov     dword ptr [rbx+0B8h], 0
0x14004cf23  mov     eax, [rbx+8]
0x14004cf26  mov     r12d, 400000h
0x14004cf2c  bt      eax, 8
0x14004cf30  jb      short loc_14004CF88
0x14004cf32  movzx   eax, word ptr [rsp+0A8h+var_44]
0x14004cf37  mov     [rbx+0BEh], ax
0x14004cf3e  mov     byte ptr [rbx+0BDh], 0
0x14004cf45  mov     dword ptr [rbx+0B0h], 0
0x14004cf4f  mov     eax, [rbx+8]
0x14004cf52  test    r12d, eax
0x14004cf55  jz      short loc_14004CF7C
0x14004cf57  mov     rax, [rbx+118h]
0x14004cf5e  mov     dword ptr [rax+30h], 0
0x14004cf65  mov     rcx, [rbx+118h]
0x14004cf6c  add     rcx, 20h ; ' '; SListHead
0x14004cf70  call    cs:__imp_InitializeSListHead
0x14004cf77  nop     dword ptr [rax+rax+00h]
0x14004cf7c  mov     dword ptr [rbx+0B4h], 0
0x14004cf86  jmp     short loc_14004CFA5
0x14004cf88  mov     byte ptr [rbx+0BDh], 0
0x14004cf8f  mov     dword ptr [rbx+0B0h], 0
0x14004cf99  movzx   eax, word ptr [rsp+0A8h+var_44]
0x14004cf9e  mov     [rbx+0BEh], ax
0x14004cfa5  lea     rcx, [rbx+38h]; SpinLock
0x14004cfa9  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14004cfae  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004cfb5  nop     dword ptr [rax+rax+00h]
0x14004cfba  mov     edx, [rbx+8]
0x14004cfbd  mov     al, [rsp+0A8h+var_40]
0x14004cfc1  neg     al
0x14004cfc3  sbb     ecx, ecx
0x14004cfc5  and     ecx, 2
0x14004cfc8  and     edx, 0FFFFFFFDh
0x14004cfcb  or      edx, ecx
0x14004cfcd  mov     [rbx+8], edx
0x14004cfd0  mov     eax, [rbx+8]
0x14004cfd3  test    al, 2
0x14004cfd5  jz      short loc_14004CFE7
0x14004cfd7  lea     rax, [rbx+90h]
0x14004cfde  mov     [rax+8], rax
0x14004cfe2  mov     [rax], rax
0x14004cfe5  jmp     short loc_14004D003
0x14004cfe7  mov     eax, [rbx+8]
0x14004cfea  bt      eax, 8
0x14004cfee  jb      short loc_14004D003
0x14004cff0  lea     rcx, [rbx+90h]; SListHead
0x14004cff7  call    cs:__imp_InitializeSListHead
0x14004cffe  nop     dword ptr [rax+rax+00h]
0x14004d003  mov     eax, [rbx+8]
0x14004d006  or      eax, esi
0x14004d008  mov     [rbx+8], eax
0x14004d00b  mov     eax, 0AFD4h
0x14004d010  or      [rbx], ax
0x14004d013  mov     [rsp+0A8h+var_88], 0
0x14004d01b  mov     r9d, [rsp+0A8h+var_44]
0x14004d020  mov     r8, rbx
0x14004d023  mov     edx, 32CEh
0x14004d028  xor     ecx, ecx
0x14004d02a  call    AFDETW_TRACELISTEN
0x14004d02f  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14004d034  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004d03b  nop     dword ptr [rax+rax+00h]
0x14004d040  mov     eax, [rbx+8]
0x14004d043  bt      eax, 8
0x14004d047  jnb     short loc_14004D0AD
0x14004d049  mov     rcx, rbx
0x14004d04c  call    AfdRefTLBaseEndpoint
0x14004d051  test    al, al
0x14004d053  jnz     short loc_14004D077
0x14004d055  mov     edi, 0C0000008h
0x14004d05a  mov     [rsp+0A8h+var_88], edi
0x14004d05e  mov     r9d, [rsp+0A8h+var_44]
0x14004d063  mov     r8, rbx
0x14004d066  mov     edx, 32CFh
0x14004d06b  mov     ecx, esi
0x14004d06d  call    AFDETW_TRACELISTEN
0x14004d072  jmp     loc_14004D19F
0x14004d077  mov     rax, [r14+0B8h]
0x14004d07e  or      [rax+3], sil
0x14004d082  mov     eax, [rbx+8]
0x14004d085  movzx   r9d, r13w
0x14004d089  movzx   r8d, r15w
0x14004d08d  mov     rdx, rbx
0x14004d090  mov     rcx, r14
0x14004d093  test    al, 2
0x14004d095  jz      short loc_14004D09E
0x14004d097  call    AfdTLDelayAcceptListen
0x14004d09c  jmp     short loc_14004D0A3
0x14004d09e  call    AfdTLListen
0x14004d0a3  mov     eax, 103h
0x14004d0a8  jmp     loc_14004D272
0x14004d0ad  xor     r15d, r15d
0x14004d0b0  cmp     r15d, [rsp+0A8h+var_44]
0x14004d0b5  jnb     short loc_14004D0DA
0x14004d0b7  xor     edx, edx
0x14004d0b9  mov     rcx, rbx
0x14004d0bc  call    AfdAddFreeConnection
0x14004d0c1  mov     edi, eax
0x14004d0c3  test    eax, eax
0x14004d0c5  js      short loc_14004D0CC
0x14004d0c7  add     r15d, esi
0x14004d0ca  jmp     short loc_14004D0B0
0x14004d0cc  mov     [rsp+0A8h+var_88], eax
0x14004d0d0  mov     edx, 32D0h
0x14004d0d5  jmp     loc_14004D18A
0x14004d0da  mov     eax, [rbx+8]
0x14004d0dd  test    r12d, eax
0x14004d0e0  jz      short loc_14004D10D
0x14004d0e2  xor     r15d, r15d
0x14004d0e5  cmp     r15d, [rsp+0A8h+var_44]
0x14004d0ea  jnb     short loc_14004D10D
0x14004d0ec  mov     dl, sil
0x14004d0ef  mov     rcx, rbx
0x14004d0f2  call    AfdAddFreeConnection
0x14004d0f7  mov     edi, eax
0x14004d0f9  test    eax, eax
0x14004d0fb  js      short loc_14004D102
0x14004d0fd  add     r15d, esi
0x14004d100  jmp     short loc_14004D0E5
0x14004d102  mov     [rsp+0A8h+var_88], eax
0x14004d106  mov     edx, 32D1h
0x14004d10b  jmp     short loc_14004D18A
0x14004d10d  mov     eax, [rbx+8]
0x14004d110  test    al, 2
0x14004d112  jnz     loc_14004D202
0x14004d118  mov     r9, rbx
0x14004d11b  lea     r8, AfdConnectEventHandler
0x14004d122  xor     edx, edx
0x14004d124  mov     rcx, [rbx+18h]
0x14004d128  call    AfdSetEventHandler
0x14004d12d  mov     edi, eax
0x14004d12f  test    eax, eax
0x14004d131  jns     short loc_14004D13E
0x14004d133  mov     [rsp+0A8h+var_88], eax
0x14004d137  mov     edx, 32D2h
0x14004d13c  jmp     short loc_14004D18A
0x14004d13e  mov     eax, [rbx+8]
0x14004d141  test    r12d, eax
0x14004d144  jz      loc_14004D202
0x14004d14a  mov     rcx, [rbx+118h]
0x14004d151  mov     r9, rbx
0x14004d154  lea     r8, AfdConnectEventHandler
0x14004d15b  xor     edx, edx
0x14004d15d  mov     rcx, [rcx+8]
0x14004d161  call    AfdSetEventHandler
0x14004d166  mov     edi, eax
0x14004d168  test    eax, eax
0x14004d16a  jns     loc_14004D202
0x14004d170  xor     r9d, r9d
0x14004d173  xor     r8d, r8d
  ... truncated ...
```
