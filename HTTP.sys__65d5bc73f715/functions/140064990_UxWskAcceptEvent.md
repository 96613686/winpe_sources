# UxWskAcceptEvent

- ea: `0x140064990`
- end: `0x140064fdb`
- name: `UxWskAcceptEvent`
- size: `1611`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000a350`
- `0x140049d08`
- `0x1400513f0`
- `0x14005d510`
- `0x14005d910`
- `0x140060abc`
- `0x1400647e0`
- `0x140064990`
- `0x140064ff0`
- `0x140065020`
- `0x140065060`
- `0x140065160`
- `0x140065220`
- `0x1401678f0`
- `0x140167940`
- `0x140167c40`
- `0x1401d834c`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!EtwProviderEnabled` at `0x140064c72`
- `ntoskrnl!EtwProviderEnabled` at `0x140064c72`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064a06`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064a06`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140064a3c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140064c2c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140064a3c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140064c2c`
- `ntoskrnl!EtwActivityIdControl` at `0x140064c8e`
- `ntoskrnl!EtwActivityIdControl` at `0x140064c8e`
- `ntoskrnl!IoAllocateIrp` at `0x140064bca`
- `ntoskrnl!IoAllocateIrp` at `0x140064bca`
- `ntoskrnl!KeReadStateEvent` at `0x140064d92`
- `ntoskrnl!KeReadStateEvent` at `0x140064d92`
- `ntoskrnl!KfRaiseIrql` at `0x140064f3d`
- `ntoskrnl!KfRaiseIrql` at `0x140064f3d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140064a28`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140064ead`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140064a28`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140064ead`
- `ntoskrnl!KeLowerIrql` at `0x140064fca`
- `ntoskrnl!KeLowerIrql` at `0x140064fca`
- `ntoskrnl!KeInitializeSpinLock` at `0x140064ad0`
- `ntoskrnl!KeInitializeSpinLock` at `0x140064c53`
- `ntoskrnl!KeInitializeSpinLock` at `0x140064ad0`
- `ntoskrnl!KeInitializeSpinLock` at `0x140064c53`
- `HAL!KeQueryPerformanceCounter` at `0x140064a8b`
- `HAL!KeQueryPerformanceCounter` at `0x140064a8b`

## pseudocode

```c
__int64 __fastcall UxWskAcceptEvent(
        __int64 a1,
        __int64 a2,
        ADDRESS_FAMILY *a3,
        ADDRESS_FAMILY *a4,
        __int64 a5,
        volatile signed __int32 **a6,
        _QWORD *a7)
{
  volatile signed __int32 *v7; // rbx
  unsigned int v10; // ebp
  __int64 v11; // rbx
  USHORT CurrentNodeNumber; // ax
  volatile signed __int32 *v13; // rax
  int v14; // eax
  int v15; // eax
  UCHAR v16; // al
  _WORD *v17; // r12
  UCHAR v18; // al
  const void *v19; // rdx
  _WORD *v20; // r15
  __int16 v21; // dx
  _QWORD *v22; // rcx
  int v23; // eax
  _QWORD *v24; // rcx
  int v25; // eax
  PIRP Irp; // rax
  int LockArray_high; // edi
  unsigned __int64 v28; // rdi
  _DWORD *v29; // rax
  int v30; // edx
  int v31; // ecx
  int v32; // edi
  int v33; // r8d
  int v34; // eax
  int v35; // eax
  __int64 v37; // rdi
  USHORT v38; // ax
  int v39; // eax
  int v40; // [rsp+20h] [rbp-78h]
  KIRQL v41; // [rsp+40h] [rbp-58h]
  __int64 v42; // [rsp+48h] [rbp-50h] BYREF
  __int64 v43; // [rsp+50h] [rbp-48h] BYREF
  char v44; // [rsp+A0h] [rbp+8h]

  v7 = 0;
  v44 = 0;
  v10 = -1073741616;
  v41 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( !a5 )
  {
    v32 = -1073741616;
    goto LABEL_38;
  }
  if ( !*(_QWORD *)(a1 + 24) )
  {
    v32 = -1073741436;
    goto LABEL_38;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 200) + 8354LL) && !KeReadStateEvent(UxHighNonPagedPoolEvent) )
  {
    v32 = -1073741258;
    goto LABEL_38;
  }
  if ( KeGetCurrentIrql() < 2u )
  {
    v41 = KfRaiseIrql(2u);
    v44 = 1;
  }
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 200) + 8680LL);
  CurrentNodeNumber = KeGetCurrentNodeNumber();
  v13 = (volatile signed __int32 *)ExAllocateFromLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v11
                                                                                       + 8LL * CurrentNodeNumber
                                                                                       + 8));
  v7 = v13;
  if ( !v13 )
  {
    v32 = -1073741670;
    goto LABEL_38;
  }
  *((_DWORD *)v13 + 8) = 1129606229;
  v14 = _InterlockedIncrement(v13 + 9);
  if ( UxDebugCheckRefcount && v14 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v7 + 9), 1u, v14);
  memset((void *)(v7 + 10), 0, 0x268u);
  *((LARGE_INTEGER *)v7 + 67) = KeQueryPerformanceCounter(0);
  *((_QWORD *)v7 + 54) = 0;
  *((_QWORD *)v7 + 56) = 0;
  *((_QWORD *)v7 + 58) = 0;
  UlPmAssociateTlConnection(v7);
  *(_OWORD *)(v7 + 10) = 0;
  *((_QWORD *)v7 + 7) = 0;
  *((_DWORD *)v7 + 14) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)v7 + 15);
  *((_QWORD *)v7 + 29) = 0;
  *((_QWORD *)v7 + 17) = v7 + 32;
  *((_QWORD *)v7 + 16) = v7 + 32;
  *((_DWORD *)v7 + 132) = 2;
  *((_QWORD *)v7 + 26) = a1;
  v15 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  if ( UxDebugCheckRefcount && v15 <= -1 )
    UlBugCheckEx(3u, a1 + 8, 0xFu, v15);
  v16 = SOCKADDR_SIZE(*a3);
  if ( v16 > 0x1Cu )
  {
    v32 = -1073741595;
    goto LABEL_38;
  }
  v17 = v7 + 37;
  memmove((void *)(v7 + 37), a3, v16);
  v18 = SOCKADDR_SIZE(*a4);
  if ( v18 > 0x1Cu )
  {
    v32 = -1073741595;
    goto LABEL_38;
  }
  v20 = v7 + 44;
  memmove((void *)(v7 + 44), v19, v18);
  v21 = 23;
  if ( *v17 == 23 && IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(v7 + 39)) )
  {
    v23 = *((_DWORD *)v7 + 42);
    *v17 = 2;
    *((_DWORD *)v7 + 38) = v23;
    *v22 = 0;
  }
  if ( v21 == *v20 && IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(v7 + 46)) )
  {
    v25 = *((_DWORD *)v7 + 49);
    *v20 = 2;
    *((_DWORD *)v7 + 45) = v25;
    *v24 = 0;
  }
  Irp = IoAllocateIrp(1, 0);
  *((_QWORD *)v7 + 12) = Irp;
  if ( !Irp )
    goto LABEL_53;
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  LODWORD(v42) = LockArray_high;
  if ( UxDebugDisableLookaside )
  {
    v29 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0390)(
                      (unsigned int)dword_1401A0378,
                      qword_1401A0380,
                      (unsigned int)dword_1401A0388,
                      0);
  }
  else
  {
    if ( UxCompactMode )
    {
      v37 = qword_1401A0370;
      v38 = KeGetCurrentNodeNumber();
      v29 = (_DWORD *)PplAllocateFromLookasideListProcessor(v37, v38);
    }
    else
    {
      v28 = qword_1401A0370 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
      if ( !*(_BYTE *)(v28 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0370, v28 + 64);
      v29 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v28 + 64));
    }
    LockArray_high = v42;
  }
  if ( !v29 )
  {
    *((_QWORD *)v7 + 13) = 0;
LABEL_53:
    v32 = -1073741670;
    goto LABEL_38;
  }
  *v29 = LockArray_high;
  *((_QWORD *)v7 + 13) = v29;
  *((_QWORD *)v7 + 9) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)v7 + 8);
  if ( EtwProviderEnabled(*(_QWORD *)(*(_QWORD *)(a1 + 200) + 1688LL), 0, 0) )
    EtwActivityIdControl(3u, (LPGUID)(v7 + 102));
  v32 = UlEtInitializeEdgeTraversalCheck(v7);
  if ( v32 >= 0 )
  {
    if ( SBYTE2(xmmword_1401A2CA0) < 0 )
      WPP_SF_qD_SOCKADDR__SOCKADDR_(
        v31,
        v30,
        v33,
        (_DWORD)v7,
        *(_DWORD *)(a1 + 12),
        (__int64)(v7 + 37),
        (__int64)(v7 + 44));
    v34 = _InterlockedIncrement(v7 + 9);
    if ( UxDebugCheckRefcount && v34 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v7 + 9), 0x37u, v34);
    v40 = *(_DWORD *)(a1 + 12);
    v42 = 0;
    v43 = 0;
    v35 = UxSslAttachConnection((_DWORD)v7, (unsigned int)UxTlDispatch, (unsigned int)&v42, (unsigned int)&v43, v40);
    v32 = v35;
    if ( v35 >= 0 )
    {
      *((_QWORD *)v7 + 5) = v42;
      *((_QWORD *)v7 + 6) = v43;
      *((_DWORD *)v7 + 14) = 2;
      *a6 = v7;
      *a7 = &UxWskClientConnDispatch;
      *((_QWORD *)v7 + 10) = a5;
      if ( (int)UxTlIoReadyEvent(v7) >= 0 )
        goto LABEL_41;
      if ( SBYTE2(xmmword_1401A2C90) < 0 )
        WPP_SF_qD(535, 17, WPP_85d1acd0d6aa38520f0f46f425080a58_Traceguids, v7, v32);
      goto LABEL_35;
    }
    if ( SBYTE2(xmmword_1401A2C90) < 0 )
      WPP_SF_qD(535, 16, WPP_85d1acd0d6aa38520f0f46f425080a58_Traceguids, v7, v35);
    v39 = _InterlockedDecrement(v7 + 9);
    if ( UxDebugCheckRefcount && v39 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v7 + 9), 0x37u, v39);
    if ( !v39 )
      UxTlDestroyConnection((char *)v7);
  }
LABEL_38:
  if ( _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 200) + 8424LL)) == 1 )
    UlEnablePeriodicScavenger(*(_QWORD *)(a1 + 200) + 8432LL);
  if ( v7 )
LABEL_35:
    UxTlCleanupConnection((PVOID)v7);
LABEL_41:
  if ( v44 )
    KeLowerIrql(v41);
  if ( v32 >= 0 )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x140064990  mov     [rsp+arg_8], rbx
0x140064995  mov     [rsp+arg_18], r9
0x14006499a  push    rbp
0x14006499b  push    rsi
0x14006499c  push    rdi
0x14006499d  push    r12
0x14006499f  push    r13
0x1400649a1  push    r14
0x1400649a3  push    r15
0x1400649a5  sub     rsp, 60h
0x1400649a9  mov     rax, [rsp+98h+arg_28]
0x1400649b1  xor     r12d, r12d
0x1400649b4  mov     ebx, r12d
0x1400649b7  mov     r15, r8
0x1400649ba  mov     rsi, rcx
0x1400649bd  mov     [rsp+98h+arg_0], bl
0x1400649c4  mov     ebp, 0C00000D0h
0x1400649c9  mov     [rsp+98h+var_58], bl
0x1400649cd  mov     [rax], r12
0x1400649d0  mov     rax, [rsp+98h+arg_30]
0x1400649d8  mov     [rax], r12
0x1400649db  cmp     [rsp+98h+arg_20], r12
0x1400649e3  jz      loc_140064F1E
0x1400649e9  cmp     [rcx+18h], rbx
0x1400649ed  jz      loc_140064F2B
0x1400649f3  mov     rax, [rcx+0C8h]
0x1400649fa  cmp     [rax+20A2h], bl
0x140064a00  jnz     loc_140064D8B
0x140064a06  call    cs:__imp_KeGetCurrentIrql
0x140064a0d  nop     dword ptr [rax+rax+00h]
0x140064a12  cmp     al, 2
0x140064a14  jb      loc_140064F3B
0x140064a1a  mov     rax, [rsi+0C8h]
0x140064a21  mov     rbx, [rax+21E8h]
0x140064a28  call    cs:__imp_KeGetCurrentNodeNumber
0x140064a2f  nop     dword ptr [rax+rax+00h]
0x140064a34  movzx   ecx, ax
0x140064a37  mov     rcx, [rbx+rcx*8+8]; Lookaside
0x140064a3c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140064a43  nop     dword ptr [rax+rax+00h]
0x140064a48  mov     rbx, rax
0x140064a4b  mov     r13d, 1
0x140064a51  test    rax, rax
0x140064a54  jz      loc_140064F5A
0x140064a5a  mov     dword ptr [rax+20h], 43546C55h
0x140064a61  mov     eax, r13d
0x140064a64  lock xadd [rbx+24h], eax
0x140064a69  inc     eax
0x140064a6b  cmp     cs:UxDebugCheckRefcount, r12b
0x140064a72  jnz     loc_140064E11
0x140064a78  xor     edx, edx; Val
0x140064a7a  lea     rcx, [rbx+28h]; void *
0x140064a7e  mov     r8d, 268h; Size
0x140064a84  call    memset
0x140064a89  xor     ecx, ecx; PerformanceFrequency
0x140064a8b  call    cs:__imp_KeQueryPerformanceCounter
0x140064a92  nop     dword ptr [rax+rax+00h]
0x140064a97  mov     [rbx+218h], rax
0x140064a9e  mov     rcx, rbx
0x140064aa1  mov     [rbx+1B0h], r12
0x140064aa8  mov     [rbx+1C0h], r12
0x140064aaf  mov     [rbx+1D0h], r12
0x140064ab6  call    UlPmAssociateTlConnection
0x140064abb  xorps   xmm0, xmm0
0x140064abe  lea     rcx, [rbx+78h]; SpinLock
0x140064ac2  movups  xmmword ptr [rbx+28h], xmm0
0x140064ac6  xor     eax, eax
0x140064ac8  mov     [rbx+38h], rax
0x140064acc  mov     [rbx+38h], r13d
0x140064ad0  call    cs:__imp_KeInitializeSpinLock
0x140064ad7  nop     dword ptr [rax+rax+00h]
0x140064adc  lea     rax, [rbx+80h]
0x140064ae3  mov     [rbx+0E8h], r12
0x140064aea  mov     [rax+8], rax
0x140064aee  lea     rdx, [rsi+8]; BugCheckParameter2
0x140064af2  mov     [rax], rax
0x140064af5  mov     edi, 2
0x140064afa  mov     [rbx+210h], edi
0x140064b00  mov     eax, r13d
0x140064b03  mov     [rbx+0D0h], rsi
0x140064b0a  lock xadd [rdx], eax
0x140064b0e  inc     eax
0x140064b10  cmp     cs:UxDebugCheckRefcount, r12b
0x140064b17  jnz     loc_140064E2F
0x140064b1d  movzx   ecx, word ptr [r15]; af
0x140064b21  call    SOCKADDR_SIZE
0x140064b26  cmp     al, 1Ch
0x140064b28  ja      loc_140064F64
0x140064b2e  lea     r12, [rbx+94h]
0x140064b35  movzx   r8d, al; Size
0x140064b39  mov     rcx, r12; void *
0x140064b3c  mov     rdx, r15; Src
0x140064b3f  call    memmove
0x140064b44  mov     rdx, [rsp+98h+arg_18]
0x140064b4c  movzx   ecx, word ptr [rdx]; af
0x140064b4f  call    SOCKADDR_SIZE
0x140064b54  cmp     al, 1Ch
0x140064b56  ja      loc_140064F6E
0x140064b5c  lea     r15, [rbx+0B0h]
0x140064b63  movzx   r8d, al; Size
0x140064b67  mov     rcx, r15; void *
0x140064b6a  call    memmove
0x140064b6f  mov     edx, 17h
0x140064b74  cmp     dx, [r12]
0x140064b79  jnz     short loc_140064B9E
0x140064b7b  lea     rcx, [r12+8]; a
0x140064b80  call    IN6_IS_ADDR_V4MAPPED
0x140064b85  test    al, al
0x140064b87  jz      short loc_140064B9E
0x140064b89  mov     eax, [rbx+0A8h]
0x140064b8f  mov     [r12], di
0x140064b94  mov     [r12+4], eax
0x140064b99  xor     eax, eax
0x140064b9b  mov     [rcx], rax
0x140064b9e  cmp     dx, [r15]
0x140064ba2  jnz     short loc_140064BC4
0x140064ba4  lea     rcx, [r15+8]; a
0x140064ba8  call    IN6_IS_ADDR_V4MAPPED
0x140064bad  test    al, al
0x140064baf  jz      short loc_140064BC4
0x140064bb1  mov     eax, [rbx+0C4h]
0x140064bb7  mov     [r15], di
0x140064bbb  mov     [r15+4], eax
0x140064bbf  xor     eax, eax
0x140064bc1  mov     [rcx], rax
0x140064bc4  xor     edx, edx; ChargeQuota
0x140064bc6  movzx   ecx, r13b; StackSize
0x140064bca  call    cs:__imp_IoAllocateIrp
0x140064bd1  nop     dword ptr [rax+rax+00h]
0x140064bd6  mov     [rbx+60h], rax
0x140064bda  test    rax, rax
0x140064bdd  jz      loc_140064E71
0x140064be3  mov     edi, gs:1A4h
0x140064beb  cmp     cs:UxDebugDisableLookaside, 0
0x140064bf2  mov     dword ptr [rsp+98h+var_50], edi
0x140064bf6  jnz     loc_140064E7E
0x140064bfc  cmp     cs:UxCompactMode, 0
0x140064c03  jnz     loc_140064EA6
0x140064c09  mov     rcx, cs:qword_1401A0370
0x140064c10  inc     edi
0x140064c12  shl     rdi, 7
0x140064c16  add     rdi, rcx
0x140064c19  movzx   eax, byte ptr [rdi+0B0h]
0x140064c20  test    al, al
0x140064c22  jz      loc_140064EC9
0x140064c28  lea     rcx, [rdi+40h]; Lookaside
0x140064c2c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140064c33  nop     dword ptr [rax+rax+00h]
0x140064c38  mov     edi, dword ptr [rsp+98h+var_50]
0x140064c3c  test    rax, rax
0x140064c3f  jz      loc_140064E6D
0x140064c45  mov     [rax], edi
0x140064c47  lea     rcx, [rbx+40h]; SpinLock
0x140064c4b  mov     [rbx+68h], rax
0x140064c4f  mov     [rbx+48h], r13
0x140064c53  call    cs:__imp_KeInitializeSpinLock
0x140064c5a  nop     dword ptr [rax+rax+00h]
0x140064c5f  mov     rcx, [rsi+0C8h]
0x140064c66  xor     r8d, r8d; Keyword
0x140064c69  xor     edx, edx; Level
0x140064c6b  mov     rcx, [rcx+698h]; RegHandle
0x140064c72  call    cs:__imp_EtwProviderEnabled
0x140064c79  nop     dword ptr [rax+rax+00h]
0x140064c7e  test    al, al
0x140064c80  jz      short loc_140064C9A
0x140064c82  lea     rdx, [rbx+198h]; ActivityId
0x140064c89  mov     ecx, 3; ControlCode
0x140064c8e  call    cs:__imp_EtwActivityIdControl
0x140064c95  nop     dword ptr [rax+rax+00h]
0x140064c9a  mov     rcx, rbx
0x140064c9d  call    UlEtInitializeEdgeTraversalCheck
0x140064ca2  mov     edi, eax
0x140064ca4  test    eax, eax
0x140064ca6  js      loc_140064E76
0x140064cac  cmp     byte ptr cs:xmmword_1401A2CA0+2, 0
0x140064cb3  jl      loc_140064F78
0x140064cb9  mov     eax, r13d
0x140064cbc  lock xadd [rbx+24h], eax
0x140064cc1  inc     eax
0x140064cc3  cmp     cs:UxDebugCheckRefcount, 0
0x140064cca  jnz     loc_140064E4C
0x140064cd0  mov     eax, [rsi+0Ch]
0x140064cd3  lea     r9, [rsp+98h+var_48]
0x140064cd8  xor     r12d, r12d
0x140064cdb  mov     [rsp+98h+var_78], eax
0x140064cdf  lea     r8, [rsp+98h+var_50]
0x140064ce4  mov     [rsp+98h+var_50], r12
0x140064ce9  lea     rdx, UxTlDispatch
0x140064cf0  mov     [rsp+98h+var_48], r12
0x140064cf5  mov     rcx, rbx
0x140064cf8  call    UxSslAttachConnection
0x140064cfd  mov     edi, eax
0x140064cff  test    eax, eax
0x140064d01  js      loc_140064F96
0x140064d07  mov     rax, [rsp+98h+var_50]
0x140064d0c  lea     rcx, UxWskClientConnDispatch
0x140064d13  mov     [rbx+28h], rax
0x140064d17  mov     rax, [rsp+98h+var_48]
0x140064d1c  mov     [rbx+30h], rax
0x140064d20  mov     rax, [rsp+98h+arg_28]
0x140064d28  mov     dword ptr [rbx+38h], 2
0x140064d2f  mov     [rax], rbx
0x140064d32  mov     rax, [rsp+98h+arg_30]
0x140064d3a  mov     [rax], rcx
0x140064d3d  mov     rcx, rbx
0x140064d40  mov     rax, [rsp+98h+arg_20]
0x140064d48  mov     [rbx+50h], rax
0x140064d4c  call    UxTlIoReadyEvent
0x140064d51  test    eax, eax
0x140064d53  jns     loc_140064DE2
0x140064d59  cmp     byte ptr cs:xmmword_1401A2C90+2, r12b
0x140064d60  jge     short loc_140064D7F
0x140064d62  mov     edx, 11h
0x140064d67  mov     [rsp+98h+var_78], edi
0x140064d6b  mov     ecx, 217h
0x140064d70  lea     r8, WPP_85d1acd0d6aa38520f0f46f425080a58_Traceguids
0x140064d77  mov     r9, rbx
0x140064d7a  call    WPP_SF_qD
0x140064d7f  xor     edx, edx
0x140064d81  mov     rcx, rbx; Entry
0x140064d84  call    UxTlCleanupConnection
0x140064d89  jmp     short loc_140064DE2
0x140064d8b  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x140064d92  call    cs:__imp_KeReadStateEvent
0x140064d99  nop     dword ptr [rax+rax+00h]
0x140064d9e  test    eax, eax
0x140064da0  jnz     loc_140064A06
0x140064da6  mov     edi, 0C0000236h
0x140064dab  mov     r13d, 1
0x140064db1  mov     rax, [rsi+0C8h]
0x140064db8  lock xadd [rax+20E8h], r13d
0x140064dc1  inc     r13d
0x140064dc4  cmp     r13d, 1
0x140064dc8  jnz     short loc_140064DDD
0x140064dca  mov     rcx, [rsi+0C8h]
0x140064dd1  add     rcx, 20F0h
0x140064dd8  call    UlEnablePeriodicScavenger
0x140064ddd  test    rbx, rbx
0x140064de0  jnz     short loc_140064D7F
0x140064de2  cmp     [rsp+98h+arg_0], 0
0x140064dea  jnz     loc_140064FC5
0x140064df0  mov     rbx, [rsp+98h+arg_8]
0x140064df8  test    edi, edi
0x140064dfa  cmovns  ebp, r12d
0x140064dfe  mov     eax, ebp
0x140064e00  add     rsp, 60h
0x140064e04  pop     r15
0x140064e06  pop     r14
0x140064e08  pop     r13
0x140064e0a  pop     r12
0x140064e0c  pop     rdi
0x140064e0d  pop     rsi
0x140064e0e  pop     rbp
0x140064e0f  retn
0x140064e11  cmp     eax, 0FFFFFFFFh
0x140064e14  jg      loc_140064A78
0x140064e1a  movsxd  r9, eax; BugCheckParameter4
0x140064e1d  lea     rdx, [rbx+24h]; BugCheckParameter2
0x140064e21  mov     r8, r13; BugCheckParameter3
0x140064e24  mov     ecx, 3; BugCheckParameter1
0x140064e29  call    UlBugCheckEx
0x140064e2f  cmp     eax, 0FFFFFFFFh
0x140064e32  jg      loc_140064B1D
0x140064e38  movsxd  r9, eax; BugCheckParameter4
0x140064e3b  mov     ecx, 3; BugCheckParameter1
0x140064e40  mov     r8d, 0Fh; BugCheckParameter3
0x140064e46  call    UlBugCheckEx
0x140064e4c  cmp     eax, 0FFFFFFFFh
0x140064e4f  jg      loc_140064CD0
0x140064e55  movsxd  r9, eax; BugCheckParameter4
0x140064e58  lea     rdx, [rbx+24h]; BugCheckParameter2
0x140064e5c  mov     r8d, 37h ; '7'; BugCheckParameter3
0x140064e62  mov     ecx, 3; BugCheckParameter1
0x140064e67  call    UlBugCheckEx
0x140064e6d  mov     [rbx+68h], rax
0x140064e71  mov     edi, 0C000009Ah
0x140064e76  xor     r12d, r12d
0x140064e79  jmp     loc_140064DB1
0x140064e7e  mov     rax, cs:off_1401A0390
0x140064e85  xor     r9d, r9d
0x140064e88  mov     r8d, cs:dword_1401A0388
0x140064e8f  mov     rdx, cs:qword_1401A0380
0x140064e96  mov     ecx, cs:dword_1401A0378
0x140064e9c  call    _guard_dispatch_icall
0x140064ea1  jmp     loc_140064C3C
0x140064ea6  mov     rdi, cs:qword_1401A0370
0x140064ead  call    cs:__imp_KeGetCurrentNodeNumber
0x140064eb4  nop     dword ptr [rax+rax+00h]
0x140064eb9  movzx   edx, ax
0x140064ebc  mov     rcx, rdi
0x140064ebf  call    PplAllocateFromLookasideListProcessor
0x140064ec4  jmp     loc_140064C38
0x140064ec9  lea     rdx, [rdi+40h]
0x140064ecd  call    PplpLazyInitializeLookasideList
0x140064ed2  jmp     loc_140064C28
0x140064ed7  mov     eax, 0FFFFFFFFh
0x140064edc  lock xadd [rbx+24h], eax
0x140064ee1  dec     eax
0x140064ee3  cmp     cs:UxDebugCheckRefcount, r12b
0x140064eea  jnz     short loc_140064F01
  ... truncated ...
```
