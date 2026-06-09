# AfdSanFastCementEndpoint

- ea: `0x14005af30`
- end: `0x14005b2a6`
- name: `AfdSanFastCementEndpoint`
- size: `886`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x14000f450`
- `0x1400137a0`
- `0x140019190`
- `0x1400191f0`
- `0x14001b0d0`
- `0x14001b800`
- `0x14002fd7c`
- `0x14003f99c`
- `0x1400445d8`
- `0x14005af30`
- `0x14005d760`
- `0x14005d9d8`
- `0x140072840`
- `0x140072870`
- `0x140092110`
- `0x140093008`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005afac`
- `ntoskrnl!ExRaiseStatus` at `0x14005b01d`
- `ntoskrnl!ExRaiseStatus` at `0x14005b099`
- `ntoskrnl!ExRaiseStatus` at `0x14005afac`
- `ntoskrnl!ExRaiseStatus` at `0x14005b01d`
- `ntoskrnl!ExRaiseStatus` at `0x14005b099`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005afc2`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b033`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005afc2`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005b033`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b272`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b272`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b245`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b245`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b160`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b160`
- `ntoskrnl!IoIs32bitProcess` at `0x14005af84`
- `ntoskrnl!IoIs32bitProcess` at `0x14005af84`
- `ntoskrnl!ProbeForWrite` at `0x14005b0b3`
- `ntoskrnl!ProbeForWrite` at `0x14005b0b3`

## pseudocode

```c
__int64 __fastcall AfdSanFastCementEndpoint(
        __int64 a1,
        unsigned __int16 a2,
        KPROCESSOR_MODE a3,
        void *a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  __int64 ULong64FromUser; // rax
  volatile void *v13; // rcx
  __int64 v14; // r14
  __int64 result; // rax
  PVOID v16; // rsi
  __int64 v17; // rbx
  signed __int32 v18; // edx
  __int64 v19; // r15
  __int64 v20; // rcx
  char v21; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  __int64 v23; // r8
  unsigned int v24; // edi
  __int64 v25; // [rsp+38h] [rbp-80h] BYREF
  volatile void *Address[2]; // [rsp+40h] [rbp-78h] BYREF
  PVOID Object; // [rsp+50h] [rbp-68h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+58h] [rbp-60h] BYREF
  __int128 v29; // [rsp+70h] [rbp-48h] BYREF
  int v30; // [rsp+80h] [rbp-38h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  Object = 0;
  *(_OWORD *)Address = 0;
  *a8 = 0;
  if ( IoIs32bitProcess(0) )
  {
    v25 = 0;
    if ( a5 < 8 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      ULong64FromUser = RtlReadULong64FromUser(a4);
      v25 = ULong64FromUser;
    }
    else
    {
      RtlCopyVolatileMemory(&v25, a4, 8u);
      LODWORD(ULong64FromUser) = v25;
    }
    Address[0] = (volatile void *)(int)ULong64FromUser;
    v13 = (volatile void *)HIDWORD(v25);
    Address[1] = (volatile void *)HIDWORD(v25);
  }
  else
  {
    if ( a5 < 0x10 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(Address, a4, 0x10u);
    }
    else
    {
      RtlCopyVolatileMemory(Address, a4, 0x10u);
    }
    v13 = Address[1];
  }
  if ( !v13 )
  {
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_(1043, 15, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids);
    ExRaiseStatus(-1073741811);
  }
  if ( a3 )
    ProbeForWrite(v13, 0x14u, 4u);
  v14 = *(_QWORD *)(a1 + 24);
  result = AfdSanReferenceSwitchSocketByHandle((HANDLE)Address[0], a2 >> 14, a3, 0, (__int64)&Object);
  if ( (int)result >= 0 )
  {
    v16 = Object;
    v17 = *((_QWORD *)Object + 3);
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_qq(1043, 16, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v17, v14);
    do
    {
      v18 = *(_DWORD *)(v17 + 368);
      if ( v18 > 0 )
      {
        v24 = -1073741816;
        goto LABEL_38;
      }
    }
    while ( v18 != _InterlockedCompareExchange((volatile signed __int32 *)(v17 + 368), v18 - 1, v18) );
    v19 = AfdLockEndpointContext(v17);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v17 + 56), &LockHandle);
    if ( (*(_DWORD *)(v17 + 8) & 0x800) == 0 && *(_WORD *)v17 == 0xAFD0 && *(_BYTE *)(v17 + 2) == 3 )
    {
      v29 = 0;
      v30 = 0;
      AfdSanInitEndpoint(v14, v16, Address[1]);
      *(_BYTE *)(v17 + 32) = 1;
      *(_BYTE *)(v17 + 33) = 1;
      *(_DWORD *)(v17 + 8) |= 0x2000000u;
      *(_DWORD *)(v17 + 152) = 4;
      *(_BYTE *)(v17 + 2) = 4;
      *(_QWORD *)(v17 + 120) = &v29;
      AfdIndicateEventSelectEvent(v17, 68, 0);
      AfdNotifySockEventsChangedUnderLock(v17, 4, 0);
      v21 = AfdIndicatePollEvent(v20, 68, 0, &LockHandle);
      p_LockHandle = &LockHandle;
      if ( v21 )
        p_LockHandle = 0;
      AfdNotifySockIndicateEventsUnlock(v17, p_LockHandle, 0);
      LOBYTE(v23) = a3;
      v24 = AfdSanPollMerge(v17, &v29, v23);
      *(_QWORD *)(v17 + 120) = 0;
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v24 = -1073741816;
    }
    AfdUnlockEndpointContext(v17, v19);
    _InterlockedIncrement((volatile signed __int32 *)(v17 + 368));
LABEL_38:
    ObfDereferenceObject(v16);
    return v24;
  }
  return result;
}

```

## disassembly

```asm
0x14005af30  push    rbx
0x14005af32  push    rsi
0x14005af33  push    rdi
0x14005af34  push    r14
0x14005af36  push    r15
0x14005af38  sub     rsp, 90h
0x14005af3f  mov     rax, cs:__security_cookie
0x14005af46  xor     rax, rsp
0x14005af49  mov     [rsp+0B8h+var_30], rax
0x14005af51  mov     rbx, r9
0x14005af54  mov     dil, r8b
0x14005af57  mov     esi, edx
0x14005af59  mov     r14, rcx
0x14005af5c  mov     rax, [rsp+0B8h+arg_38]
0x14005af64  xorps   xmm0, xmm0
0x14005af67  xor     ecx, ecx; Irp
0x14005af69  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x14005af6e  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rcx
0x14005af73  mov     [rsp+0B8h+Object], rcx
0x14005af78  movups  xmmword ptr [rsp+0B8h+Address], xmm0
0x14005af7d  mov     [rax], rcx
0x14005af80  mov     [rsp+0B8h+var_88], ecx
0x14005af84  call    cs:__imp_IoIs32bitProcess
0x14005af8b  nop     dword ptr [rax+rax+00h]
0x14005af90  test    al, al
0x14005af92  jz      short loc_14005B00E
0x14005af94  mov     [rsp+0B8h+var_80], 0
0x14005af9d  cmp     [rsp+0B8h+arg_20], 8
0x14005afa5  jnb     short loc_14005AFB8
0x14005afa7  mov     ecx, 0C000000Dh; Status
0x14005afac  call    cs:__imp_ExRaiseStatus
0x14005afb8  test    dil, dil
0x14005afbb  jz      short loc_14005AFE3
0x14005afbd  test    bl, 3
0x14005afc0  jz      short loc_14005AFCF
0x14005afc2  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005afc9  nop     dword ptr [rax+rax+00h]
0x14005afce  int     3; Trap to Debugger
0x14005afcf  test    dil, dil
0x14005afd2  jz      short loc_14005AFE3
0x14005afd4  mov     rcx, rbx
0x14005afd7  call    RtlReadULong64FromUser
0x14005afdc  mov     [rsp+0B8h+var_80], rax
0x14005afe1  jmp     short loc_14005AFFB
0x14005afe3  mov     r8d, 8; Size
0x14005afe9  mov     rdx, rbx; Src
0x14005afec  lea     rcx, [rsp+0B8h+var_80]; void *
0x14005aff1  call    RtlCopyVolatileMemory
0x14005aff6  mov     rax, [rsp+0B8h+var_80]
0x14005affb  movsxd  rcx, eax
0x14005affe  mov     [rsp+0B8h+Address], rcx
0x14005b003  mov     ecx, dword ptr [rsp+0B8h+var_80+4]
0x14005b007  mov     [rsp+0B8h+Address+8], rcx
0x14005b00c  jmp     short loc_14005B072
0x14005b00e  cmp     [rsp+0B8h+arg_20], 10h
0x14005b016  jnb     short loc_14005B029
0x14005b018  mov     ecx, 0C000000Dh; Status
0x14005b01d  call    cs:__imp_ExRaiseStatus
0x14005b029  test    dil, dil
0x14005b02c  jz      short loc_14005B05A
0x14005b02e  test    bl, 3
0x14005b031  jz      short loc_14005B040
0x14005b033  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005b03a  nop     dword ptr [rax+rax+00h]
0x14005b03f  int     3; Trap to Debugger
0x14005b040  test    dil, dil
0x14005b043  jz      short loc_14005B05A
0x14005b045  mov     r8d, 10h; Size
0x14005b04b  mov     rdx, rbx; Src
0x14005b04e  lea     rcx, [rsp+0B8h+Address]; void *
0x14005b053  call    RtlCopyFromUser
0x14005b058  jmp     short loc_14005B06D
0x14005b05a  mov     r8d, 10h; Size
0x14005b060  mov     rdx, rbx; Src
0x14005b063  lea     rcx, [rsp+0B8h+Address]; void *
0x14005b068  call    RtlCopyVolatileMemory
0x14005b06d  mov     rcx, [rsp+0B8h+Address+8]; Address
0x14005b072  test    rcx, rcx
0x14005b075  jnz     short loc_14005B0A5
0x14005b077  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005b07e  jz      short loc_14005B094
0x14005b080  lea     edx, [rcx+0Fh]
0x14005b083  mov     ecx, 413h
0x14005b088  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005b08f  call    WPP_SF_
0x14005b094  mov     ecx, 0C000000Dh; Status
0x14005b099  call    cs:__imp_ExRaiseStatus
0x14005b0a5  test    dil, dil
0x14005b0a8  jz      short loc_14005B0C0
0x14005b0aa  mov     edx, 14h; Length
0x14005b0af  lea     r8d, [rdx-10h]; Alignment
0x14005b0b3  call    cs:__imp_ProbeForWrite
0x14005b0ba  nop     dword ptr [rax+rax+00h]
0x14005b0bf  nop
0x14005b0c0  mov     r14, [r14+18h]
0x14005b0c4  shr     esi, 0Eh
0x14005b0c7  and     esi, 3
0x14005b0ca  lea     rax, [rsp+0B8h+Object]
0x14005b0cf  mov     [rsp+0B8h+var_90], rax; __int64
0x14005b0d4  mov     [rsp+0B8h+var_98], 0; __int64
0x14005b0dd  mov     r9, r14
0x14005b0e0  mov     r8b, dil; AccessMode
0x14005b0e3  mov     edx, esi; DesiredAccess
0x14005b0e5  mov     rcx, [rsp+0B8h+Address]; Handle
0x14005b0ea  call    AfdSanReferenceSwitchSocketByHandle
0x14005b0ef  test    eax, eax
0x14005b0f1  js      loc_14005B286
0x14005b0f7  mov     rsi, [rsp+0B8h+Object]
0x14005b0fc  mov     rbx, [rsi+18h]
0x14005b100  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005b107  jz      short loc_14005B127
0x14005b109  mov     edx, 10h
0x14005b10e  mov     ecx, 413h
0x14005b113  mov     [rsp+0B8h+var_98], r14
0x14005b118  mov     r9, rbx
0x14005b11b  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005b122  call    WPP_SF_qq
0x14005b127  mov     edx, [rbx+170h]
0x14005b12d  test    edx, edx
0x14005b12f  jg      loc_14005B26A
0x14005b135  lea     ecx, [rdx-1]
0x14005b138  mov     eax, edx
0x14005b13a  lock cmpxchg [rbx+170h], ecx
0x14005b142  jnz     short loc_14005B127
0x14005b144  test    edx, edx
0x14005b146  jg      loc_14005B26A
0x14005b14c  mov     rcx, rbx
0x14005b14f  call    AfdLockEndpointContext
0x14005b154  mov     r15, rax
0x14005b157  lea     rcx, [rbx+38h]; SpinLock
0x14005b15b  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x14005b160  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005b167  nop     dword ptr [rax+rax+00h]
0x14005b16c  test    dword ptr [rbx+8], 800h
0x14005b173  jnz     loc_14005B240
0x14005b179  mov     eax, 0AFD0h
0x14005b17e  cmp     [rbx], ax
0x14005b181  jnz     loc_14005B240
0x14005b187  cmp     byte ptr [rbx+2], 3
0x14005b18b  jnz     loc_14005B240
0x14005b191  xorps   xmm0, xmm0
0x14005b194  movups  [rsp+0B8h+var_48], xmm0
0x14005b199  xor     eax, eax
0x14005b19b  mov     [rsp+0B8h+var_38], eax
0x14005b1a2  mov     r8, [rsp+0B8h+Address+8]
0x14005b1a7  mov     rdx, rsi
0x14005b1aa  mov     rcx, r14
0x14005b1ad  call    AfdSanInitEndpoint
0x14005b1b2  mov     byte ptr [rbx+20h], 1
0x14005b1b6  mov     byte ptr [rbx+21h], 1
0x14005b1ba  mov     eax, [rbx+8]
0x14005b1bd  bts     eax, 19h
0x14005b1c1  mov     [rbx+8], eax
0x14005b1c4  mov     dword ptr [rbx+98h], 4
0x14005b1ce  mov     byte ptr [rbx+2], 4
0x14005b1d2  lea     rax, [rsp+0B8h+var_48]
0x14005b1d7  mov     [rbx+78h], rax
0x14005b1db  xor     r8d, r8d
0x14005b1de  lea     r14d, [r8+44h]
0x14005b1e2  mov     edx, r14d
0x14005b1e5  mov     rcx, rbx
0x14005b1e8  call    AfdIndicateEventSelectEvent
0x14005b1ed  xor     r8d, r8d
0x14005b1f0  lea     edx, [r14-40h]
0x14005b1f4  mov     rcx, rbx
0x14005b1f7  call    AfdNotifySockEventsChangedUnderLock
0x14005b1fc  lea     r9, [rsp+0B8h+LockHandle]
0x14005b201  xor     r8d, r8d
0x14005b204  mov     edx, r14d
0x14005b207  call    AfdIndicatePollEvent
0x14005b20c  lea     rdx, [rsp+0B8h+LockHandle]
0x14005b211  xor     ecx, ecx
0x14005b213  test    al, al
0x14005b215  cmovnz  rdx, rcx
0x14005b219  xor     r8d, r8d
0x14005b21c  mov     rcx, rbx
0x14005b21f  call    AfdNotifySockIndicateEventsUnlock
0x14005b224  mov     r8b, dil
0x14005b227  lea     rdx, [rsp+0B8h+var_48]
0x14005b22c  mov     rcx, rbx
0x14005b22f  call    AfdSanPollMerge
0x14005b234  mov     edi, eax
0x14005b236  mov     qword ptr [rbx+78h], 0
0x14005b23e  jmp     short loc_14005B256
0x14005b240  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14005b245  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005b24c  nop     dword ptr [rax+rax+00h]
0x14005b251  mov     edi, 0C0000008h
0x14005b256  mov     rdx, r15
0x14005b259  mov     rcx, rbx
0x14005b25c  call    AfdUnlockEndpointContext
0x14005b261  lock inc dword ptr [rbx+170h]
0x14005b268  jmp     short loc_14005B26F
0x14005b26a  mov     edi, 0C0000008h
0x14005b26f  mov     rcx, rsi; Object
0x14005b272  call    cs:__imp_ObfDereferenceObject
0x14005b279  nop     dword ptr [rax+rax+00h]
0x14005b27e  mov     eax, edi
0x14005b280  jmp     short loc_14005B286
0x14005b282  mov     eax, [rsp+0B8h+var_88]
0x14005b286  mov     rcx, [rsp+0B8h+var_30]
0x14005b28e  xor     rcx, rsp; StackCookie
0x14005b291  call    __security_check_cookie
0x14005b296  add     rsp, 90h
0x14005b29d  pop     r15
0x14005b29f  pop     r14
0x14005b2a1  pop     rdi
0x14005b2a2  pop     rsi
0x14005b2a3  pop     rbx
0x14005b2a4  retn
0x14007432f  push    rbp
0x140074331  sub     rsp, 30h
0x140074335  mov     rbp, rdx
0x140074338  mov     r8, rcx
0x14007433b  lea     r9, [rbp+30h]
0x14007433f  mov     edx, 15Fh
0x140074344  lea     rcx, aMinioSocketsWi_11; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007434b  call    AfdExceptionFilter
0x140074350  nop
0x140074351  add     rsp, 30h
0x140074355  pop     rbp
0x140074356  retn
```
