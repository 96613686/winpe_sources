# AfdSanFastCementEndpoint

- ea: `0x14005ad90`
- end: `0x14005b106`
- name: `AfdSanFastCementEndpoint`
- size: `886`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, KPROCESSOR_MODE, void *, unsigned int, __int64, __int64, _QWORD *)`
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
- `0x14002fd5c`
- `0x14003f97c`
- `0x1400445b8`
- `0x14005ad90`
- `0x14005d5c0`
- `0x14005d838`
- `0x1400726a0`
- `0x1400726d0`
- `0x140092110`
- `0x140093008`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005ae0c`
- `ntoskrnl!ExRaiseStatus` at `0x14005ae7d`
- `ntoskrnl!ExRaiseStatus` at `0x14005aef9`
- `ntoskrnl!ExRaiseStatus` at `0x14005ae0c`
- `ntoskrnl!ExRaiseStatus` at `0x14005ae7d`
- `ntoskrnl!ExRaiseStatus` at `0x14005aef9`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005ae22`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005ae93`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005ae22`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005ae93`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b0d2`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b0d2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b0a5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b0a5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005afc0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005afc0`
- `ntoskrnl!IoIs32bitProcess` at `0x14005ade4`
- `ntoskrnl!IoIs32bitProcess` at `0x14005ade4`
- `ntoskrnl!ProbeForWrite` at `0x14005af13`
- `ntoskrnl!ProbeForWrite` at `0x14005af13`

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
  unsigned __int64 v19; // r15
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
  result = AfdSanReferenceSwitchSocketByHandle((HANDLE)Address[0], a2 >> 14, a3, v14, 0, &Object);
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
      v21 = AfdIndicatePollEvent(v20, 0x44u, 0, &LockHandle);
      p_LockHandle = &LockHandle;
      if ( v21 )
        p_LockHandle = 0;
      AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v17, p_LockHandle, 0);
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
0x14005ad90  push    rbx
0x14005ad92  push    rsi
0x14005ad93  push    rdi
0x14005ad94  push    r14
0x14005ad96  push    r15
0x14005ad98  sub     rsp, 90h
0x14005ad9f  mov     rax, cs:__security_cookie
0x14005ada6  xor     rax, rsp
0x14005ada9  mov     [rsp+0B8h+var_30], rax
0x14005adb1  mov     rbx, r9
0x14005adb4  mov     dil, r8b
0x14005adb7  mov     esi, edx
0x14005adb9  mov     r14, rcx
0x14005adbc  mov     rax, [rsp+0B8h+arg_38]
0x14005adc4  xorps   xmm0, xmm0
0x14005adc7  xor     ecx, ecx; Irp
0x14005adc9  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x14005adce  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rcx
0x14005add3  mov     [rsp+0B8h+Object], rcx
0x14005add8  movups  xmmword ptr [rsp+0B8h+Address], xmm0
0x14005addd  mov     [rax], rcx
0x14005ade0  mov     [rsp+0B8h+var_88], ecx
0x14005ade4  call    cs:__imp_IoIs32bitProcess
0x14005adeb  nop     dword ptr [rax+rax+00h]
0x14005adf0  test    al, al
0x14005adf2  jz      short loc_14005AE6E
0x14005adf4  mov     [rsp+0B8h+var_80], 0
0x14005adfd  cmp     [rsp+0B8h+arg_20], 8
0x14005ae05  jnb     short loc_14005AE18
0x14005ae07  mov     ecx, 0C000000Dh; Status
0x14005ae0c  call    cs:__imp_ExRaiseStatus
0x14005ae18  test    dil, dil
0x14005ae1b  jz      short loc_14005AE43
0x14005ae1d  test    bl, 3
0x14005ae20  jz      short loc_14005AE2F
0x14005ae22  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005ae29  nop     dword ptr [rax+rax+00h]
0x14005ae2e  int     3; Trap to Debugger
0x14005ae2f  test    dil, dil
0x14005ae32  jz      short loc_14005AE43
0x14005ae34  mov     rcx, rbx
0x14005ae37  call    RtlReadULong64FromUser
0x14005ae3c  mov     [rsp+0B8h+var_80], rax
0x14005ae41  jmp     short loc_14005AE5B
0x14005ae43  mov     r8d, 8; Size
0x14005ae49  mov     rdx, rbx; Src
0x14005ae4c  lea     rcx, [rsp+0B8h+var_80]; void *
0x14005ae51  call    RtlCopyVolatileMemory
0x14005ae56  mov     rax, [rsp+0B8h+var_80]
0x14005ae5b  movsxd  rcx, eax
0x14005ae5e  mov     [rsp+0B8h+Address], rcx
0x14005ae63  mov     ecx, dword ptr [rsp+0B8h+var_80+4]
0x14005ae67  mov     [rsp+0B8h+Address+8], rcx
0x14005ae6c  jmp     short loc_14005AED2
0x14005ae6e  cmp     [rsp+0B8h+arg_20], 10h
0x14005ae76  jnb     short loc_14005AE89
0x14005ae78  mov     ecx, 0C000000Dh; Status
0x14005ae7d  call    cs:__imp_ExRaiseStatus
0x14005ae89  test    dil, dil
0x14005ae8c  jz      short loc_14005AEBA
0x14005ae8e  test    bl, 3
0x14005ae91  jz      short loc_14005AEA0
0x14005ae93  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005ae9a  nop     dword ptr [rax+rax+00h]
0x14005ae9f  int     3; Trap to Debugger
0x14005aea0  test    dil, dil
0x14005aea3  jz      short loc_14005AEBA
0x14005aea5  mov     r8d, 10h; Size
0x14005aeab  mov     rdx, rbx; Src
0x14005aeae  lea     rcx, [rsp+0B8h+Address]; void *
0x14005aeb3  call    RtlCopyFromUser
0x14005aeb8  jmp     short loc_14005AECD
0x14005aeba  mov     r8d, 10h; Size
0x14005aec0  mov     rdx, rbx; Src
0x14005aec3  lea     rcx, [rsp+0B8h+Address]; void *
0x14005aec8  call    RtlCopyVolatileMemory
0x14005aecd  mov     rcx, [rsp+0B8h+Address+8]; Address
0x14005aed2  test    rcx, rcx
0x14005aed5  jnz     short loc_14005AF05
0x14005aed7  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005aede  jz      short loc_14005AEF4
0x14005aee0  lea     edx, [rcx+0Fh]
0x14005aee3  mov     ecx, 413h
0x14005aee8  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005aeef  call    WPP_SF_
0x14005aef4  mov     ecx, 0C000000Dh; Status
0x14005aef9  call    cs:__imp_ExRaiseStatus
0x14005af05  test    dil, dil
0x14005af08  jz      short loc_14005AF20
0x14005af0a  mov     edx, 14h; Length
0x14005af0f  lea     r8d, [rdx-10h]; Alignment
0x14005af13  call    cs:__imp_ProbeForWrite
0x14005af1a  nop     dword ptr [rax+rax+00h]
0x14005af1f  nop
0x14005af20  mov     r14, [r14+18h]
0x14005af24  shr     esi, 0Eh
0x14005af27  and     esi, 3
0x14005af2a  lea     rax, [rsp+0B8h+Object]
0x14005af2f  mov     [rsp+0B8h+var_90], rax; __int64
0x14005af34  mov     [rsp+0B8h+var_98], 0; __int64
0x14005af3d  mov     r9, r14
0x14005af40  mov     r8b, dil; AccessMode
0x14005af43  mov     edx, esi; DesiredAccess
0x14005af45  mov     rcx, [rsp+0B8h+Address]; Handle
0x14005af4a  call    AfdSanReferenceSwitchSocketByHandle
0x14005af4f  test    eax, eax
0x14005af51  js      loc_14005B0E6
0x14005af57  mov     rsi, [rsp+0B8h+Object]
0x14005af5c  mov     rbx, [rsi+18h]
0x14005af60  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005af67  jz      short loc_14005AF87
0x14005af69  mov     edx, 10h
0x14005af6e  mov     ecx, 413h
0x14005af73  mov     [rsp+0B8h+var_98], r14
0x14005af78  mov     r9, rbx
0x14005af7b  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005af82  call    WPP_SF_qq
0x14005af87  mov     edx, [rbx+170h]
0x14005af8d  test    edx, edx
0x14005af8f  jg      loc_14005B0CA
0x14005af95  lea     ecx, [rdx-1]
0x14005af98  mov     eax, edx
0x14005af9a  lock cmpxchg [rbx+170h], ecx
0x14005afa2  jnz     short loc_14005AF87
0x14005afa4  test    edx, edx
0x14005afa6  jg      loc_14005B0CA
0x14005afac  mov     rcx, rbx
0x14005afaf  call    AfdLockEndpointContext
0x14005afb4  mov     r15, rax
0x14005afb7  lea     rcx, [rbx+38h]; SpinLock
0x14005afbb  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x14005afc0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005afc7  nop     dword ptr [rax+rax+00h]
0x14005afcc  test    dword ptr [rbx+8], 800h
0x14005afd3  jnz     loc_14005B0A0
0x14005afd9  mov     eax, 0AFD0h
0x14005afde  cmp     [rbx], ax
0x14005afe1  jnz     loc_14005B0A0
0x14005afe7  cmp     byte ptr [rbx+2], 3
0x14005afeb  jnz     loc_14005B0A0
0x14005aff1  xorps   xmm0, xmm0
0x14005aff4  movups  [rsp+0B8h+var_48], xmm0
0x14005aff9  xor     eax, eax
0x14005affb  mov     [rsp+0B8h+var_38], eax
0x14005b002  mov     r8, [rsp+0B8h+Address+8]
0x14005b007  mov     rdx, rsi
0x14005b00a  mov     rcx, r14
0x14005b00d  call    AfdSanInitEndpoint
0x14005b012  mov     byte ptr [rbx+20h], 1
0x14005b016  mov     byte ptr [rbx+21h], 1
0x14005b01a  mov     eax, [rbx+8]
0x14005b01d  bts     eax, 19h
0x14005b021  mov     [rbx+8], eax
0x14005b024  mov     dword ptr [rbx+98h], 4
0x14005b02e  mov     byte ptr [rbx+2], 4
0x14005b032  lea     rax, [rsp+0B8h+var_48]
0x14005b037  mov     [rbx+78h], rax
0x14005b03b  xor     r8d, r8d
0x14005b03e  lea     r14d, [r8+44h]
0x14005b042  mov     edx, r14d
0x14005b045  mov     rcx, rbx
0x14005b048  call    AfdIndicateEventSelectEvent
0x14005b04d  xor     r8d, r8d
0x14005b050  lea     edx, [r14-40h]
0x14005b054  mov     rcx, rbx
0x14005b057  call    AfdNotifySockEventsChangedUnderLock
0x14005b05c  lea     r9, [rsp+0B8h+LockHandle]
0x14005b061  xor     r8d, r8d
0x14005b064  mov     edx, r14d
0x14005b067  call    AfdIndicatePollEvent
0x14005b06c  lea     rdx, [rsp+0B8h+LockHandle]
0x14005b071  xor     ecx, ecx
0x14005b073  test    al, al
0x14005b075  cmovnz  rdx, rcx
0x14005b079  xor     r8d, r8d
0x14005b07c  mov     rcx, rbx
0x14005b07f  call    AfdNotifySockIndicateEventsUnlock
0x14005b084  mov     r8b, dil
0x14005b087  lea     rdx, [rsp+0B8h+var_48]
0x14005b08c  mov     rcx, rbx
0x14005b08f  call    AfdSanPollMerge
0x14005b094  mov     edi, eax
0x14005b096  mov     qword ptr [rbx+78h], 0
0x14005b09e  jmp     short loc_14005B0B6
0x14005b0a0  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14005b0a5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005b0ac  nop     dword ptr [rax+rax+00h]
0x14005b0b1  mov     edi, 0C0000008h
0x14005b0b6  mov     rdx, r15
0x14005b0b9  mov     rcx, rbx
0x14005b0bc  call    AfdUnlockEndpointContext
0x14005b0c1  lock inc dword ptr [rbx+170h]
0x14005b0c8  jmp     short loc_14005B0CF
0x14005b0ca  mov     edi, 0C0000008h
0x14005b0cf  mov     rcx, rsi; Object
0x14005b0d2  call    cs:__imp_ObfDereferenceObject
0x14005b0d9  nop     dword ptr [rax+rax+00h]
0x14005b0de  mov     eax, edi
0x14005b0e0  jmp     short loc_14005B0E6
0x14005b0e2  mov     eax, [rsp+0B8h+var_88]
0x14005b0e6  mov     rcx, [rsp+0B8h+var_30]
0x14005b0ee  xor     rcx, rsp; StackCookie
0x14005b0f1  call    __security_check_cookie
0x14005b0f6  add     rsp, 90h
0x14005b0fd  pop     r15
0x14005b0ff  pop     r14
0x14005b101  pop     rdi
0x14005b102  pop     rsi
0x14005b103  pop     rbx
0x14005b104  retn
0x1400741af  push    rbp
0x1400741b1  sub     rsp, 30h
0x1400741b5  mov     rbp, rdx
0x1400741b8  mov     r8, rcx
0x1400741bb  lea     r9, [rbp+30h]
0x1400741bf  mov     edx, 15Fh
0x1400741c4  lea     rcx, aMinioSocketsWi_11; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400741cb  call    AfdExceptionFilter
0x1400741d0  nop
0x1400741d1  add     rsp, 30h
0x1400741d5  pop     rbp
0x1400741d6  retn
```
