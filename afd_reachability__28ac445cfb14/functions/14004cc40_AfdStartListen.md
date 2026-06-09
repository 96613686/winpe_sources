# AfdStartListen

- ea: `0x14004cc40`
- end: `0x14004d1fd`
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
- `0x14002fd5c`
- `0x1400303c8`
- `0x140033898`
- `0x140036c04`
- `0x1400445b8`
- `0x140047640`
- `0x14004cc40`
- `0x14004d9bc`
- `0x1400726a0`
- `0x1400726d0`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x14004ce6d`
- `ntoskrnl!InitializeSListHead` at `0x14004ced0`
- `ntoskrnl!InitializeSListHead` at `0x14004cf57`
- `ntoskrnl!InitializeSListHead` at `0x14004ce6d`
- `ntoskrnl!InitializeSListHead` at `0x14004ced0`
- `ntoskrnl!InitializeSListHead` at `0x14004cf57`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004ccda`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004ccda`
- `ntoskrnl!IofCompleteRequest` at `0x14004d1c4`
- `ntoskrnl!IofCompleteRequest` at `0x14004d1c4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004cf94`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d154`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004cf94`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d154`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004cf0e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d119`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004cf0e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d119`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004cd20`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004cd20`

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
      WPP_SF_q(1288, 10, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, CurrentProcessId);
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
  AFDETW_TRACELISTEN(0, 13006, v3, HIDWORD(v24), 0);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (*(_DWORD *)(v3 + 8) & 0x100) == 0 )
  {
    for ( i = 0; i < HIDWORD(v24); ++i )
    {
      v18 = AfdAddFreeConnection(v3, 0);
      v5 = v18;
      if ( v18 < 0 )
      {
        AFDETW_TRACELISTEN(1, 13008, v3, HIDWORD(v24), v18);
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
          AFDETW_TRACELISTEN(1, 13009, v3, HIDWORD(v24), v20);
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
        AFDETW_TRACELISTEN(1, 13010, v3, HIDWORD(v24), v21);
        goto LABEL_70;
      }
      if ( (*(_DWORD *)(v3 + 8) & 0x400000) != 0 )
      {
        v5 = AfdSetEventHandler(*(_QWORD *)(*(_QWORD *)(v3 + 280) + 8LL), 0, AfdConnectEventHandler, v3);
        if ( v5 < 0 )
        {
          AfdSetEventHandler(*(_QWORD *)(v3 + 24), 0, 0, 0);
          AFDETW_TRACELISTEN(1, 13011, v3, HIDWORD(v24), v5);
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
    AFDETW_TRACELISTEN(1, 13007, v3, HIDWORD(v24), -1073741816);
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
0x14004cc40  mov     r11, rsp
0x14004cc43  mov     [r11+18h], rbx
0x14004cc47  mov     [r11+20h], rsi
0x14004cc4b  push    rdi
0x14004cc4c  push    r12
0x14004cc4e  push    r13
0x14004cc50  push    r14
0x14004cc52  push    r15
0x14004cc54  sub     rsp, 80h
0x14004cc5b  mov     rax, cs:__security_cookie
0x14004cc62  xor     rax, rsp
0x14004cc65  mov     [rsp+0A8h+var_38], rax
0x14004cc6a  mov     r14, rcx
0x14004cc6d  mov     [rsp+0A8h+var_68], rcx
0x14004cc72  xor     eax, eax
0x14004cc74  mov     [r11-48h], rax
0x14004cc78  mov     [rsp+0A8h+var_40], al
0x14004cc7c  xorps   xmm0, xmm0
0x14004cc7f  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14004cc84  mov     [r11-50h], rax
0x14004cc88  mov     [rcx+38h], rax
0x14004cc8c  mov     rax, [rdx+30h]
0x14004cc90  mov     rbx, [rax+18h]
0x14004cc94  mov     [rsp+0A8h+var_70], rbx
0x14004cc99  mov     r8d, 0Ch
0x14004cc9f  cmp     [rdx+10h], r8d
0x14004cca3  jnb     short loc_14004CCC7
0x14004cca5  mov     edx, 32C8h
0x14004ccaa  mov     eax, 0C000000Dh
0x14004ccaf  mov     [rsp+0A8h+var_88], eax
0x14004ccb3  mov     edi, eax
0x14004ccb5  xor     r9d, r9d
0x14004ccb8  mov     r8, rbx
0x14004ccbb  xor     ecx, ecx
0x14004ccbd  call    AFDETW_TRACELISTEN
0x14004ccc2  jmp     loc_14004D1B7
0x14004ccc7  xor     edi, edi
0x14004ccc9  mov     [rsp+0A8h+var_74], edi
0x14004cccd  mov     cl, [rcx+40h]
0x14004ccd0  test    cl, cl
0x14004ccd2  jz      short loc_14004CCE7
0x14004ccd4  test    byte ptr [rdx+20h], 3
0x14004ccd8  jz      short loc_14004CCE7
0x14004ccda  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14004cce1  nop     dword ptr [rax+rax+00h]
0x14004cce6  int     3; Trap to Debugger
0x14004cce7  mov     rdx, [rdx+20h]; Src
0x14004cceb  test    cl, cl
0x14004cced  lea     rcx, [rsp+0A8h+var_48]; void *
0x14004ccf2  jz      short loc_14004CCFB
0x14004ccf4  call    RtlCopyFromUser
0x14004ccf9  jmp     short loc_14004CD01
0x14004ccfb  call    RtlCopyVolatileMemory
0x14004cd00  nop
0x14004cd01  cmp     [rsp+0A8h+var_48], 0
0x14004cd06  jnz     short loc_14004CD56
0x14004cd08  cmp     cs:AfdSanServiceHelper, 0
0x14004cd10  jz      short loc_14004CD56
0x14004cd12  mov     esi, 1
0x14004cd17  test    byte ptr cs:xmmword_1400875E0+9, sil
0x14004cd1e  jz      short loc_14004CD43
0x14004cd20  call    cs:__imp_PsGetCurrentProcessId
0x14004cd27  nop     dword ptr [rax+rax+00h]
0x14004cd2c  mov     r9, rax
0x14004cd2f  lea     edx, [rsi+9]
0x14004cd32  mov     ecx, 508h
0x14004cd37  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004cd3e  call    WPP_SF_q
0x14004cd43  mov     edi, 0C00000FAh
0x14004cd48  mov     [rsp+0A8h+var_88], edi
0x14004cd4c  mov     edx, 32CAh
0x14004cd51  jmp     loc_14004CCB5
0x14004cd56  mov     eax, [rbx+8]
0x14004cd59  bt      eax, 8
0x14004cd5d  jnb     short loc_14004CD91
0x14004cd5f  mov     eax, [rsp+0A8h+var_44]
0x14004cd63  test    eax, eax
0x14004cd65  jns     short loc_14004CD91
0x14004cd67  mov     ecx, eax
0x14004cd69  neg     ecx
0x14004cd6b  cmovs   ecx, eax
0x14004cd6e  mov     [rsp+0A8h+var_44], ecx
0x14004cd72  mov     edx, 0C8h
0x14004cd77  mov     esi, 1
0x14004cd7c  cmp     ecx, edx
0x14004cd7e  jnb     short loc_14004CD86
0x14004cd80  mov     [rsp+0A8h+var_44], edx
0x14004cd84  jmp     short loc_14004CDAD
0x14004cd86  mov     eax, 0FFFFh
0x14004cd8b  cmp     ecx, eax
0x14004cd8d  ja      short loc_14004CDA9
0x14004cd8f  jmp     short loc_14004CDAD
0x14004cd91  mov     eax, [rsp+0A8h+var_44]
0x14004cd95  mov     edx, 0C8h
0x14004cd9a  cmp     eax, edx
0x14004cd9c  cmova   eax, edx
0x14004cd9f  mov     esi, 1
0x14004cda4  cmp     eax, esi
0x14004cda6  cmovb   eax, esi
0x14004cda9  mov     [rsp+0A8h+var_44], eax
0x14004cdad  movzx   ecx, byte ptr [rbx+2]
0x14004cdb1  xor     eax, eax
0x14004cdb3  lock cmpxchg [rbx+170h], ecx
0x14004cdbb  jz      short loc_14004CDC7
0x14004cdbd  mov     edx, 32CBh
0x14004cdc2  jmp     loc_14004CCAA
0x14004cdc7  mov     eax, 5030h
0x14004cdcc  add     ax, [rbx]
0x14004cdcf  mov     ecx, 0FFFDh
0x14004cdd4  test    cx, ax
0x14004cdd7  jz      short loc_14004CDE3
0x14004cdd9  mov     edx, 32CCh
0x14004cdde  jmp     loc_14004D174
0x14004cde3  mov     al, [rbx+2]
0x14004cde6  cmp     al, 3
0x14004cde8  jz      short loc_14004CDFC
0x14004cdea  cmp     al, 4
0x14004cdec  jnz     loc_14004D16F
0x14004cdf2  test    [rbx+6], sil
0x14004cdf6  jz      loc_14004D16F
0x14004cdfc  mov     eax, [rbx+8]
0x14004cdff  test    sil, al
0x14004ce02  jnz     loc_14004D16F
0x14004ce08  cmp     [rsp+0A8h+var_40], 0
0x14004ce0d  jz      short loc_14004CE2C
0x14004ce0f  mov     eax, [rbx+8]
0x14004ce12  bt      eax, 8
0x14004ce16  jb      short loc_14004CE2C
0x14004ce18  mov     eax, [rbx+8]
0x14004ce1b  bt      eax, 8
0x14004ce1f  jb      short loc_14004CE2C
0x14004ce21  mov     eax, [rbx+10h]
0x14004ce24  test    al, al
0x14004ce26  jns     loc_14004D16F
0x14004ce2c  movzx   r13d, word ptr [rbx+0B8h]
0x14004ce34  movzx   r15d, word ptr [rbx+0BAh]
0x14004ce3c  mov     [rsp+0A8h+var_78], r15w
0x14004ce42  lea     rax, [rbx+60h]
0x14004ce46  mov     [rax+8], rax
0x14004ce4a  mov     [rax], rax
0x14004ce4d  lea     rax, [rbx+70h]
0x14004ce51  mov     [rax+8], rax
0x14004ce55  mov     [rax], rax
0x14004ce58  lea     rax, [rbx+80h]
0x14004ce5f  mov     [rax+8], rax
0x14004ce63  mov     [rax], rax
0x14004ce66  lea     rcx, [rbx+0A0h]; SListHead
0x14004ce6d  call    cs:__imp_InitializeSListHead
0x14004ce74  nop     dword ptr [rax+rax+00h]
0x14004ce79  mov     dword ptr [rbx+0B8h], 0
0x14004ce83  mov     eax, [rbx+8]
0x14004ce86  mov     r12d, 400000h
0x14004ce8c  bt      eax, 8
0x14004ce90  jb      short loc_14004CEE8
0x14004ce92  movzx   eax, word ptr [rsp+0A8h+var_44]
0x14004ce97  mov     [rbx+0BEh], ax
0x14004ce9e  mov     byte ptr [rbx+0BDh], 0
0x14004cea5  mov     dword ptr [rbx+0B0h], 0
0x14004ceaf  mov     eax, [rbx+8]
0x14004ceb2  test    r12d, eax
0x14004ceb5  jz      short loc_14004CEDC
0x14004ceb7  mov     rax, [rbx+118h]
0x14004cebe  mov     dword ptr [rax+30h], 0
0x14004cec5  mov     rcx, [rbx+118h]
0x14004cecc  add     rcx, 20h ; ' '; SListHead
0x14004ced0  call    cs:__imp_InitializeSListHead
0x14004ced7  nop     dword ptr [rax+rax+00h]
0x14004cedc  mov     dword ptr [rbx+0B4h], 0
0x14004cee6  jmp     short loc_14004CF05
0x14004cee8  mov     byte ptr [rbx+0BDh], 0
0x14004ceef  mov     dword ptr [rbx+0B0h], 0
0x14004cef9  movzx   eax, word ptr [rsp+0A8h+var_44]
0x14004cefe  mov     [rbx+0BEh], ax
0x14004cf05  lea     rcx, [rbx+38h]; SpinLock
0x14004cf09  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14004cf0e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004cf15  nop     dword ptr [rax+rax+00h]
0x14004cf1a  mov     edx, [rbx+8]
0x14004cf1d  mov     al, [rsp+0A8h+var_40]
0x14004cf21  neg     al
0x14004cf23  sbb     ecx, ecx
0x14004cf25  and     ecx, 2
0x14004cf28  and     edx, 0FFFFFFFDh
0x14004cf2b  or      edx, ecx
0x14004cf2d  mov     [rbx+8], edx
0x14004cf30  mov     eax, [rbx+8]
0x14004cf33  test    al, 2
0x14004cf35  jz      short loc_14004CF47
0x14004cf37  lea     rax, [rbx+90h]
0x14004cf3e  mov     [rax+8], rax
0x14004cf42  mov     [rax], rax
0x14004cf45  jmp     short loc_14004CF63
0x14004cf47  mov     eax, [rbx+8]
0x14004cf4a  bt      eax, 8
0x14004cf4e  jb      short loc_14004CF63
0x14004cf50  lea     rcx, [rbx+90h]; SListHead
0x14004cf57  call    cs:__imp_InitializeSListHead
0x14004cf5e  nop     dword ptr [rax+rax+00h]
0x14004cf63  mov     eax, [rbx+8]
0x14004cf66  or      eax, esi
0x14004cf68  mov     [rbx+8], eax
0x14004cf6b  mov     eax, 0AFD4h
0x14004cf70  or      [rbx], ax
0x14004cf73  mov     [rsp+0A8h+var_88], 0
0x14004cf7b  mov     r9d, [rsp+0A8h+var_44]
0x14004cf80  mov     r8, rbx
0x14004cf83  mov     edx, 32CEh
0x14004cf88  xor     ecx, ecx
0x14004cf8a  call    AFDETW_TRACELISTEN
0x14004cf8f  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14004cf94  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004cf9b  nop     dword ptr [rax+rax+00h]
0x14004cfa0  mov     eax, [rbx+8]
0x14004cfa3  bt      eax, 8
0x14004cfa7  jnb     short loc_14004D00D
0x14004cfa9  mov     rcx, rbx
0x14004cfac  call    AfdRefTLBaseEndpoint
0x14004cfb1  test    al, al
0x14004cfb3  jnz     short loc_14004CFD7
0x14004cfb5  mov     edi, 0C0000008h
0x14004cfba  mov     [rsp+0A8h+var_88], edi
0x14004cfbe  mov     r9d, [rsp+0A8h+var_44]
0x14004cfc3  mov     r8, rbx
0x14004cfc6  mov     edx, 32CFh
0x14004cfcb  mov     ecx, esi
0x14004cfcd  call    AFDETW_TRACELISTEN
0x14004cfd2  jmp     loc_14004D0FF
0x14004cfd7  mov     rax, [r14+0B8h]
0x14004cfde  or      [rax+3], sil
0x14004cfe2  mov     eax, [rbx+8]
0x14004cfe5  movzx   r9d, r13w
0x14004cfe9  movzx   r8d, r15w
0x14004cfed  mov     rdx, rbx
0x14004cff0  mov     rcx, r14
0x14004cff3  test    al, 2
0x14004cff5  jz      short loc_14004CFFE
0x14004cff7  call    AfdTLDelayAcceptListen
0x14004cffc  jmp     short loc_14004D003
0x14004cffe  call    AfdTLListen
0x14004d003  mov     eax, 103h
0x14004d008  jmp     loc_14004D1D2
0x14004d00d  xor     r15d, r15d
0x14004d010  cmp     r15d, [rsp+0A8h+var_44]
0x14004d015  jnb     short loc_14004D03A
0x14004d017  xor     edx, edx
0x14004d019  mov     rcx, rbx
0x14004d01c  call    AfdAddFreeConnection
0x14004d021  mov     edi, eax
0x14004d023  test    eax, eax
0x14004d025  js      short loc_14004D02C
0x14004d027  add     r15d, esi
0x14004d02a  jmp     short loc_14004D010
0x14004d02c  mov     [rsp+0A8h+var_88], eax
0x14004d030  mov     edx, 32D0h
0x14004d035  jmp     loc_14004D0EA
0x14004d03a  mov     eax, [rbx+8]
0x14004d03d  test    r12d, eax
0x14004d040  jz      short loc_14004D06D
0x14004d042  xor     r15d, r15d
0x14004d045  cmp     r15d, [rsp+0A8h+var_44]
0x14004d04a  jnb     short loc_14004D06D
0x14004d04c  mov     dl, sil
0x14004d04f  mov     rcx, rbx
0x14004d052  call    AfdAddFreeConnection
0x14004d057  mov     edi, eax
0x14004d059  test    eax, eax
0x14004d05b  js      short loc_14004D062
0x14004d05d  add     r15d, esi
0x14004d060  jmp     short loc_14004D045
0x14004d062  mov     [rsp+0A8h+var_88], eax
0x14004d066  mov     edx, 32D1h
0x14004d06b  jmp     short loc_14004D0EA
0x14004d06d  mov     eax, [rbx+8]
0x14004d070  test    al, 2
0x14004d072  jnz     loc_14004D162
0x14004d078  mov     r9, rbx
0x14004d07b  lea     r8, AfdConnectEventHandler
0x14004d082  xor     edx, edx
0x14004d084  mov     rcx, [rbx+18h]
0x14004d088  call    AfdSetEventHandler
0x14004d08d  mov     edi, eax
0x14004d08f  test    eax, eax
0x14004d091  jns     short loc_14004D09E
0x14004d093  mov     [rsp+0A8h+var_88], eax
0x14004d097  mov     edx, 32D2h
0x14004d09c  jmp     short loc_14004D0EA
0x14004d09e  mov     eax, [rbx+8]
0x14004d0a1  test    r12d, eax
0x14004d0a4  jz      loc_14004D162
0x14004d0aa  mov     rcx, [rbx+118h]
0x14004d0b1  mov     r9, rbx
0x14004d0b4  lea     r8, AfdConnectEventHandler
0x14004d0bb  xor     edx, edx
0x14004d0bd  mov     rcx, [rcx+8]
0x14004d0c1  call    AfdSetEventHandler
0x14004d0c6  mov     edi, eax
0x14004d0c8  test    eax, eax
0x14004d0ca  jns     loc_14004D162
0x14004d0d0  xor     r9d, r9d
0x14004d0d3  xor     r8d, r8d
  ... truncated ...
```
