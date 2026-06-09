# AfdSanFastRefreshEndpoint

- ea: `0x14005bd40`
- end: `0x14005c128`
- name: `AfdSanFastRefreshEndpoint`
- size: `1000`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, KPROCESSOR_MODE, void *, unsigned int, __int64, __int64, volatile void *Address)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x14000f390`
- `0x140019190`
- `0x1400191f0`
- `0x14002fd5c`
- `0x14003f97c`
- `0x1400445b8`
- `0x14005bd40`
- `0x1400726d0`
- `0x140072780`
- `0x140072b00`
- `0x140092110`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14005bf31`
- `ntoskrnl!KfRaiseIrql` at `0x14005bf31`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005bf94`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005bfe1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005c0d2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005bf94`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005bfe1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005c0d2`
- `ntoskrnl!KeLowerIrql` at `0x14005c0e1`
- `ntoskrnl!KeLowerIrql` at `0x14005c0e1`
- `ntoskrnl!ExRaiseStatus` at `0x14005bdb4`
- `ntoskrnl!ExRaiseStatus` at `0x14005be37`
- `ntoskrnl!ExRaiseStatus` at `0x14005bea7`
- `ntoskrnl!ExRaiseStatus` at `0x14005bdb4`
- `ntoskrnl!ExRaiseStatus` at `0x14005be37`
- `ntoskrnl!ExRaiseStatus` at `0x14005bea7`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005bdca`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005be4d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005bdca`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005be4d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005c00d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005c00d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005bf50`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005bfbc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005bf50`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005bfbc`
- `ntoskrnl!ObfDereferenceObject` at `0x14005c103`
- `ntoskrnl!ObfDereferenceObject` at `0x14005c103`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005bfa8`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005bfa8`
- `ntoskrnl!IoIs32bitProcess` at `0x14005bd89`
- `ntoskrnl!IoIs32bitProcess` at `0x14005bd89`
- `ntoskrnl!ProbeForWrite` at `0x14005bec4`
- `ntoskrnl!ProbeForWrite` at `0x14005bec4`

## pseudocode

```c
__int64 __fastcall AfdSanFastRefreshEndpoint(
        __int64 a1,
        unsigned __int16 a2,
        KPROCESSOR_MODE a3,
        void *a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        volatile void *Address)
{
  volatile void *ULong64FromUser; // rax
  __int64 v13; // rax
  __int64 result; // rax
  unsigned int v15; // ebx
  PVOID v16; // r15
  __int64 v17; // rdi
  unsigned __int64 v18; // r13
  KIRQL v19; // si
  _QWORD *v20; // rbx
  _QWORD *v21; // rsi
  void (__fastcall *v22)(PVOID, _QWORD *); // r14
  char v23; // cl
  int v24; // edx
  KIRQL v25; // [rsp+30h] [rbp-78h]
  PVOID Object; // [rsp+38h] [rbp-70h] BYREF
  HANDLE Handle[2]; // [rsp+40h] [rbp-68h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-58h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  Object = 0;
  *(_OWORD *)Handle = 0;
  *(_QWORD *)Address = 0;
  if ( IoIs32bitProcess(0) )
  {
    Address = 0;
    if ( a5 < 8 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      ULong64FromUser = (volatile void *)RtlReadULong64FromUser(a4);
      Address = ULong64FromUser;
    }
    else
    {
      RtlCopyVolatileMemory(&Address, a4, 8u);
      LODWORD(ULong64FromUser) = (_DWORD)Address;
    }
    Handle[0] = (HANDLE)(int)ULong64FromUser;
    v13 = HIDWORD(Address);
    Handle[1] = (HANDLE)HIDWORD(Address);
  }
  else
  {
    if ( a5 < 0x10 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(Handle, a4, 0x10u);
    }
    else
    {
      RtlCopyVolatileMemory(Handle, a4, 0x10u);
    }
    v13 = (__int64)Handle[1];
  }
  if ( !v13 )
  {
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_(1043, 35, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids);
    ExRaiseStatus(-1073741811);
  }
  if ( a3 )
  {
    ProbeForWrite((volatile void *)v13, 0x14u, 4u);
    v13 = (__int64)Handle[1];
  }
  result = AfdSanReferenceSwitchSocketByHandle(Handle[0], a2 >> 14, a3, *(_QWORD *)(a1 + 24), v13, &Object);
  v15 = result;
  if ( (int)result >= 0 )
  {
    v16 = Object;
    v17 = *((_QWORD *)Object + 3);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v17 + 368), *(unsigned __int8 *)(v17 + 2), 0) )
    {
      v18 = AfdLockEndpointContext(v17);
      v19 = KfRaiseIrql(2u);
      v25 = v19;
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v17 + 56), &LockHandle);
      if ( (*(_DWORD *)(v17 + 8) & 0x800) != 0 || *(_BYTE *)(v17 + 2) != 4 )
      {
        v15 = -1073741816;
      }
      else
      {
        *(_BYTE *)(v17 + 2) = 7;
        v20 = (_QWORD *)(v17 + 128);
        if ( (_QWORD *)*v20 != v20 )
        {
          LOBYTE(Address) = 0;
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
LABEL_30:
          IoAcquireCancelSpinLock((PKIRQL)&Address);
          KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v17 + 56), &LockHandle);
          while ( 1 )
          {
            v21 = (_QWORD *)*v20;
            if ( (_QWORD *)*v20 == v20 )
              break;
            v22 = (void (__fastcall *)(PVOID, _QWORD *))_InterlockedExchange64(v21 - 8, 0);
            if ( v22 )
            {
              KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
              *((_WORD *)v21 - 50) = 513;
              v22(AfdDeviceObject, v21 - 21);
              goto LABEL_30;
            }
          }
          IoReleaseCancelSpinLock(2u);
          v19 = v25;
        }
        AfdDereferenceEndpoint(*(_QWORD *)(v17 + 96));
        memset((void *)(v17 + 96), 0, 0x48u);
        *(_WORD *)v17 = -20528;
        if ( (*(_DWORD *)(v17 + 8) & 0x100) != 0 )
          v23 = (*(_QWORD *)(v17 + 240) != 0) + 2;
        else
          v23 = *(_QWORD *)(v17 + 24) != 0 ? 3 : 1;
        *(_BYTE *)(v17 + 2) = v23;
        v24 = *(_DWORD *)(v17 + 8);
        *(_DWORD *)(v17 + 8) = 0;
        *(_DWORD *)(v17 + 72) = 0;
        *(_DWORD *)(v17 + 8) = v24 & 0xFFFFFF00 ^ (*(_DWORD *)(v17 + 8) ^ v24 & 0xFFFFFF00) & 0xFFFFFEFF;
        *(_DWORD *)(v17 + 8) = v24 ^ (*(_DWORD *)(v17 + 8) ^ v24) & 0x7FFFFFFF;
        *(_DWORD *)(v17 + 8) = v24 & 0xC0000000 ^ (*(_DWORD *)(v17 + 8) ^ v24 & 0xC0000000) & 0xBFFFFFFF;
        *(_DWORD *)(v17 + 8) = v24 & 0xFFFFF000 ^ (*(_DWORD *)(v17 + 8) ^ v24 & 0xFFFFF000) & 0xFFFFEFFF;
        v15 = 0;
      }
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      KeLowerIrql(v19);
      AfdUnlockEndpointContext(v17, v18);
      _InterlockedExchange((volatile __int32 *)(v17 + 368), 0);
    }
    ObfDereferenceObject(v16);
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x14005bd40  push    rbx
0x14005bd42  push    rsi
0x14005bd43  push    rdi
0x14005bd44  push    r12
0x14005bd46  push    r13
0x14005bd48  push    r14
0x14005bd4a  push    r15
0x14005bd4c  sub     rsp, 70h
0x14005bd50  mov     rbx, r9
0x14005bd53  mov     dil, r8b
0x14005bd56  mov     esi, edx
0x14005bd58  mov     r14, rcx
0x14005bd5b  xorps   xmm0, xmm0
0x14005bd5e  xor     eax, eax
0x14005bd60  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14005bd65  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14005bd6a  xor     r15d, r15d
0x14005bd6d  mov     [rsp+0A8h+Object], r15
0x14005bd72  movups  xmmword ptr [rsp+0A8h+Handle], xmm0
0x14005bd77  mov     rax, [rsp+0A8h+Address]
0x14005bd7f  mov     [rax], r15
0x14005bd82  mov     [rsp+0A8h+var_74], r15d
0x14005bd87  xor     ecx, ecx; Irp
0x14005bd89  call    cs:__imp_IoIs32bitProcess
0x14005bd90  nop     dword ptr [rax+rax+00h]
0x14005bd95  test    al, al
0x14005bd97  jz      loc_14005BE22
0x14005bd9d  mov     [rsp+0A8h+Address], r15
0x14005bda5  cmp     [rsp+0A8h+arg_20], 8
0x14005bdad  jnb     short loc_14005BDC0
0x14005bdaf  mov     ecx, 0C000000Dh; Status
0x14005bdb4  call    cs:__imp_ExRaiseStatus
0x14005bdc0  test    dil, dil
0x14005bdc3  jz      short loc_14005BDEE
0x14005bdc5  test    bl, 3
0x14005bdc8  jz      short loc_14005BDD7
0x14005bdca  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005bdd1  nop     dword ptr [rax+rax+00h]
0x14005bdd6  int     3; Trap to Debugger
0x14005bdd7  test    dil, dil
0x14005bdda  jz      short loc_14005BDEE
0x14005bddc  mov     rcx, rbx
0x14005bddf  call    RtlReadULong64FromUser
0x14005bde4  mov     [rsp+0A8h+Address], rax
0x14005bdec  jmp     short loc_14005BE0C
0x14005bdee  mov     r8d, 8; Size
0x14005bdf4  mov     rdx, rbx; Src
0x14005bdf7  lea     rcx, [rsp+0A8h+Address]; void *
0x14005bdff  call    RtlCopyVolatileMemory
0x14005be04  mov     rax, [rsp+0A8h+Address]
0x14005be0c  movsxd  rcx, eax
0x14005be0f  mov     [rsp+0A8h+Handle], rcx
0x14005be14  mov     eax, dword ptr [rsp+0A8h+Address+4]
0x14005be1b  mov     [rsp+0A8h+Handle+8], rax
0x14005be20  jmp     short loc_14005BE80
0x14005be22  mov     r8d, 10h; Size
0x14005be28  cmp     [rsp+0A8h+arg_20], r8d
0x14005be30  jnb     short loc_14005BE43
0x14005be32  mov     ecx, 0C000000Dh; Status
0x14005be37  call    cs:__imp_ExRaiseStatus
0x14005be43  test    dil, dil
0x14005be46  jz      short loc_14005BE6E
0x14005be48  test    bl, 3
0x14005be4b  jz      short loc_14005BE5A
0x14005be4d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005be54  nop     dword ptr [rax+rax+00h]
0x14005be59  int     3; Trap to Debugger
0x14005be5a  test    dil, dil
0x14005be5d  jz      short loc_14005BE6E
0x14005be5f  mov     rdx, rbx; Src
0x14005be62  lea     rcx, [rsp+0A8h+Handle]; void *
0x14005be67  call    RtlCopyFromUser
0x14005be6c  jmp     short loc_14005BE7B
0x14005be6e  mov     rdx, rbx; Src
0x14005be71  lea     rcx, [rsp+0A8h+Handle]; void *
0x14005be76  call    RtlCopyVolatileMemory
0x14005be7b  mov     rax, [rsp+0A8h+Handle+8]
0x14005be80  test    rax, rax
0x14005be83  jnz     short loc_14005BEB3
0x14005be85  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005be8c  jz      short loc_14005BEA2
0x14005be8e  lea     edx, [rax+23h]
0x14005be91  mov     ecx, 413h
0x14005be96  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005be9d  call    WPP_SF_
0x14005bea2  mov     ecx, 0C000000Dh; Status
0x14005bea7  call    cs:__imp_ExRaiseStatus
0x14005beb3  test    dil, dil
0x14005beb6  jz      short loc_14005BED5
0x14005beb8  mov     edx, 14h; Length
0x14005bebd  lea     r8d, [rdx-10h]; Alignment
0x14005bec1  mov     rcx, rax; Address
0x14005bec4  call    cs:__imp_ProbeForWrite
0x14005becb  nop     dword ptr [rax+rax+00h]
0x14005bed0  mov     rax, [rsp+0A8h+Handle+8]
0x14005bed5  shr     esi, 0Eh
0x14005bed8  and     esi, 3
0x14005bedb  lea     rcx, [rsp+0A8h+Object]
0x14005bee0  mov     [rsp+0A8h+var_80], rcx; __int64
0x14005bee5  mov     [rsp+0A8h+var_88], rax; __int64
0x14005beea  mov     r9, [r14+18h]
0x14005beee  mov     r8b, dil; AccessMode
0x14005bef1  mov     edx, esi; DesiredAccess
0x14005bef3  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14005bef8  call    AfdSanReferenceSwitchSocketByHandle
0x14005befd  mov     ebx, eax
0x14005beff  test    eax, eax
0x14005bf01  js      loc_14005C117
0x14005bf07  mov     r15, [rsp+0A8h+Object]
0x14005bf0c  mov     rdi, [r15+18h]
0x14005bf10  movzx   ecx, byte ptr [rdi+2]
0x14005bf14  xor     eax, eax
0x14005bf16  lock cmpxchg [rdi+170h], ecx
0x14005bf1e  jnz     loc_14005C100
0x14005bf24  mov     rcx, rdi
0x14005bf27  call    AfdLockEndpointContext
0x14005bf2c  mov     r13, rax
0x14005bf2f  mov     cl, 2; NewIrql
0x14005bf31  call    cs:__imp_KfRaiseIrql
0x14005bf38  nop     dword ptr [rax+rax+00h]
0x14005bf3d  mov     sil, al
0x14005bf40  mov     [rsp+0A8h+var_78], al
0x14005bf44  lea     r12, [rdi+38h]
0x14005bf48  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14005bf4d  mov     rcx, r12; SpinLock
0x14005bf50  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005bf57  nop     dword ptr [rax+rax+00h]
0x14005bf5c  test    dword ptr [rdi+8], 800h
0x14005bf63  jnz     loc_14005C0C8
0x14005bf69  cmp     byte ptr [rdi+2], 4
0x14005bf6d  jnz     loc_14005C0C8
0x14005bf73  mov     byte ptr [rdi+2], 7
0x14005bf77  lea     rbx, [rdi+80h]
0x14005bf7e  cmp     [rbx], rbx
0x14005bf81  jz      loc_14005C01E
0x14005bf87  mov     byte ptr [rsp+0A8h+Address], 0
0x14005bf8f  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14005bf94  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005bf9b  nop     dword ptr [rax+rax+00h]
0x14005bfa0  lea     rcx, [rsp+0A8h+Address]; Irql
0x14005bfa8  call    cs:__imp_IoAcquireCancelSpinLock
0x14005bfaf  nop     dword ptr [rax+rax+00h]
0x14005bfb4  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14005bfb9  mov     rcx, r12; SpinLock
0x14005bfbc  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005bfc3  nop     dword ptr [rax+rax+00h]
0x14005bfc8  mov     rsi, [rbx]
0x14005bfcb  cmp     rsi, rbx
0x14005bfce  jz      short loc_14005C00B
0x14005bfd0  xor     r14d, r14d
0x14005bfd3  xchg    r14, [rsi-40h]
0x14005bfd7  test    r14, r14
0x14005bfda  jz      short loc_14005BFC8
0x14005bfdc  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14005bfe1  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005bfe8  nop     dword ptr [rax+rax+00h]
0x14005bfed  mov     word ptr [rsi-64h], 201h
0x14005bff3  lea     rdx, [rsi-0A8h]
0x14005bffa  mov     rcx, cs:AfdDeviceObject
0x14005c001  mov     rax, r14
0x14005c004  call    _guard_dispatch_icall
0x14005c009  jmp     short loc_14005BFA0
0x14005c00b  mov     cl, 2; Irql
0x14005c00d  call    cs:__imp_IoReleaseCancelSpinLock
0x14005c014  nop     dword ptr [rax+rax+00h]
0x14005c019  mov     sil, [rsp+0A8h+var_78]
0x14005c01e  mov     rcx, [rdi+60h]
0x14005c022  call    AfdDereferenceEndpoint
0x14005c027  xor     edx, edx; Val
0x14005c029  lea     r8d, [rdx+48h]; Size
0x14005c02d  lea     rcx, [rdi+60h]; void *
0x14005c031  call    memset
0x14005c036  mov     word ptr [rdi], 0AFD0h
0x14005c03b  mov     eax, [rdi+8]
0x14005c03e  bt      eax, 8
0x14005c042  jb      short loc_14005C054
0x14005c044  mov     rax, [rdi+18h]
0x14005c048  neg     rax
0x14005c04b  sbb     cl, cl
0x14005c04d  and     cl, 2
0x14005c050  inc     cl
0x14005c052  jmp     short loc_14005C062
0x14005c054  cmp     qword ptr [rdi+0F0h], 0
0x14005c05c  setnz   cl
0x14005c05f  add     cl, 2
0x14005c062  mov     [rdi+2], cl
0x14005c065  mov     edx, [rdi+8]
0x14005c068  mov     dword ptr [rdi+8], 0
0x14005c06f  mov     dword ptr [rdi+48h], 0
0x14005c076  mov     ecx, edx
0x14005c078  and     ecx, 0FFFFFF00h
0x14005c07e  mov     eax, ecx
0x14005c080  xor     eax, [rdi+8]
0x14005c083  btr     eax, 8
0x14005c087  xor     eax, ecx
0x14005c089  mov     [rdi+8], eax
0x14005c08c  mov     eax, edx
0x14005c08e  xor     eax, [rdi+8]
0x14005c091  btr     eax, 1Fh
0x14005c095  xor     eax, edx
0x14005c097  mov     [rdi+8], eax
0x14005c09a  mov     ecx, edx
0x14005c09c  and     ecx, 0C0000000h
0x14005c0a2  mov     eax, ecx
0x14005c0a4  xor     eax, [rdi+8]
0x14005c0a7  btr     eax, 1Eh
0x14005c0ab  xor     eax, ecx
0x14005c0ad  mov     [rdi+8], eax
0x14005c0b0  and     edx, 0FFFFF000h
0x14005c0b6  mov     eax, edx
0x14005c0b8  xor     eax, [rdi+8]
0x14005c0bb  btr     eax, 0Ch
0x14005c0bf  xor     eax, edx
0x14005c0c1  mov     [rdi+8], eax
0x14005c0c4  xor     ebx, ebx
0x14005c0c6  jmp     short loc_14005C0CD
0x14005c0c8  mov     ebx, 0C0000008h
0x14005c0cd  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14005c0d2  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005c0d9  nop     dword ptr [rax+rax+00h]
0x14005c0de  mov     cl, sil; NewIrql
0x14005c0e1  call    cs:__imp_KeLowerIrql
0x14005c0e8  nop     dword ptr [rax+rax+00h]
0x14005c0ed  mov     rdx, r13
0x14005c0f0  mov     rcx, rdi
0x14005c0f3  call    AfdUnlockEndpointContext
0x14005c0f8  xor     eax, eax
0x14005c0fa  xchg    eax, [rdi+170h]
0x14005c100  mov     rcx, r15; Object
0x14005c103  call    cs:__imp_ObfDereferenceObject
0x14005c10a  nop     dword ptr [rax+rax+00h]
0x14005c10f  mov     eax, ebx
0x14005c111  jmp     short loc_14005C117
0x14005c113  mov     eax, [rsp+0A8h+var_74]
0x14005c117  add     rsp, 70h
0x14005c11b  pop     r15
0x14005c11d  pop     r14
0x14005c11f  pop     r13
0x14005c121  pop     r12
0x14005c123  pop     rdi
0x14005c124  pop     rsi
0x14005c125  pop     rbx
0x14005c126  retn
0x14007430f  push    rbp
0x140074311  sub     rsp, 30h
0x140074315  mov     rbp, rdx
0x140074318  mov     r8, rcx
0x14007431b  lea     r9, [rbp+34h]
0x14007431f  mov     edx, 0A53h
0x140074324  lea     rcx, aMinioSocketsWi_11; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007432b  call    AfdExceptionFilter
0x140074330  nop
0x140074331  add     rsp, 30h
0x140074335  pop     rbp
0x140074336  retn
```
