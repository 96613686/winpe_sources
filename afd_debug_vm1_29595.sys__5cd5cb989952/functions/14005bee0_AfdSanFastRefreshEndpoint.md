# AfdSanFastRefreshEndpoint

- ea: `0x14005bee0`
- end: `0x14005c2c8`
- name: `AfdSanFastRefreshEndpoint`
- size: `1000`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x14000f390`
- `0x140019190`
- `0x1400191f0`
- `0x14002fd7c`
- `0x14003f99c`
- `0x1400445d8`
- `0x14005bee0`
- `0x140072870`
- `0x140072920`
- `0x140072c80`
- `0x140092110`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14005c0d1`
- `ntoskrnl!KfRaiseIrql` at `0x14005c0d1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005c134`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005c181`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005c272`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005c134`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005c181`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005c272`
- `ntoskrnl!KeLowerIrql` at `0x14005c281`
- `ntoskrnl!KeLowerIrql` at `0x14005c281`
- `ntoskrnl!ExRaiseStatus` at `0x14005bf54`
- `ntoskrnl!ExRaiseStatus` at `0x14005bfd7`
- `ntoskrnl!ExRaiseStatus` at `0x14005c047`
- `ntoskrnl!ExRaiseStatus` at `0x14005bf54`
- `ntoskrnl!ExRaiseStatus` at `0x14005bfd7`
- `ntoskrnl!ExRaiseStatus` at `0x14005c047`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005bf6a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005bfed`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005bf6a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005bfed`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005c1ad`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005c1ad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005c0f0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005c15c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005c0f0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005c15c`
- `ntoskrnl!ObfDereferenceObject` at `0x14005c2a3`
- `ntoskrnl!ObfDereferenceObject` at `0x14005c2a3`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005c148`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005c148`
- `ntoskrnl!IoIs32bitProcess` at `0x14005bf29`
- `ntoskrnl!IoIs32bitProcess` at `0x14005bf29`
- `ntoskrnl!ProbeForWrite` at `0x14005c064`
- `ntoskrnl!ProbeForWrite` at `0x14005c064`

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
  __int64 v12; // rax
  __int64 result; // rax
  unsigned int v14; // ebx
  PVOID v15; // r15
  __int64 v16; // rdi
  __int64 v17; // r13
  KIRQL v18; // si
  _QWORD *v19; // rbx
  _QWORD *v20; // rsi
  void (__fastcall *v21)(PVOID, _QWORD *); // r14
  char v22; // cl
  int v23; // edx
  KIRQL v24; // [rsp+30h] [rbp-78h]
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
    v12 = HIDWORD(Address);
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
    v12 = (__int64)Handle[1];
  }
  if ( !v12 )
  {
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_(1043, 35, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids);
    ExRaiseStatus(-1073741811);
  }
  if ( a3 )
  {
    ProbeForWrite((volatile void *)v12, 0x14u, 4u);
    v12 = (__int64)Handle[1];
  }
  result = AfdSanReferenceSwitchSocketByHandle(Handle[0], a2 >> 14, a3, v12, (__int64)&Object);
  v14 = result;
  if ( (int)result >= 0 )
  {
    v15 = Object;
    v16 = *((_QWORD *)Object + 3);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v16 + 368), *(unsigned __int8 *)(v16 + 2), 0) )
    {
      v17 = AfdLockEndpointContext(v16);
      v18 = KfRaiseIrql(2u);
      v24 = v18;
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v16 + 56), &LockHandle);
      if ( (*(_DWORD *)(v16 + 8) & 0x800) != 0 || *(_BYTE *)(v16 + 2) != 4 )
      {
        v14 = -1073741816;
      }
      else
      {
        *(_BYTE *)(v16 + 2) = 7;
        v19 = (_QWORD *)(v16 + 128);
        if ( (_QWORD *)*v19 != v19 )
        {
          LOBYTE(Address) = 0;
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
LABEL_30:
          IoAcquireCancelSpinLock((PKIRQL)&Address);
          KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v16 + 56), &LockHandle);
          while ( 1 )
          {
            v20 = (_QWORD *)*v19;
            if ( (_QWORD *)*v19 == v19 )
              break;
            v21 = (void (__fastcall *)(PVOID, _QWORD *))_InterlockedExchange64(v20 - 8, 0);
            if ( v21 )
            {
              KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
              *((_WORD *)v20 - 50) = 513;
              v21(AfdDeviceObject, v20 - 21);
              goto LABEL_30;
            }
          }
          IoReleaseCancelSpinLock(2u);
          v18 = v24;
        }
        AfdDereferenceEndpoint(*(_QWORD *)(v16 + 96));
        memset((void *)(v16 + 96), 0, 0x48u);
        *(_WORD *)v16 = -20528;
        if ( (*(_DWORD *)(v16 + 8) & 0x100) != 0 )
          v22 = (*(_QWORD *)(v16 + 240) != 0) + 2;
        else
          v22 = *(_QWORD *)(v16 + 24) != 0 ? 3 : 1;
        *(_BYTE *)(v16 + 2) = v22;
        v23 = *(_DWORD *)(v16 + 8);
        *(_DWORD *)(v16 + 8) = 0;
        *(_DWORD *)(v16 + 72) = 0;
        *(_DWORD *)(v16 + 8) = v23 & 0xFFFFFF00 ^ (*(_DWORD *)(v16 + 8) ^ v23 & 0xFFFFFF00) & 0xFFFFFEFF;
        *(_DWORD *)(v16 + 8) = v23 ^ (*(_DWORD *)(v16 + 8) ^ v23) & 0x7FFFFFFF;
        *(_DWORD *)(v16 + 8) = v23 & 0xC0000000 ^ (*(_DWORD *)(v16 + 8) ^ v23 & 0xC0000000) & 0xBFFFFFFF;
        *(_DWORD *)(v16 + 8) = v23 & 0xFFFFF000 ^ (*(_DWORD *)(v16 + 8) ^ v23 & 0xFFFFF000) & 0xFFFFEFFF;
        v14 = 0;
      }
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      KeLowerIrql(v18);
      AfdUnlockEndpointContext(v16, v17);
      _InterlockedExchange((volatile __int32 *)(v16 + 368), 0);
    }
    ObfDereferenceObject(v15);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x14005bee0  push    rbx
0x14005bee2  push    rsi
0x14005bee3  push    rdi
0x14005bee4  push    r12
0x14005bee6  push    r13
0x14005bee8  push    r14
0x14005beea  push    r15
0x14005beec  sub     rsp, 70h
0x14005bef0  mov     rbx, r9
0x14005bef3  mov     dil, r8b
0x14005bef6  mov     esi, edx
0x14005bef8  mov     r14, rcx
0x14005befb  xorps   xmm0, xmm0
0x14005befe  xor     eax, eax
0x14005bf00  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14005bf05  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14005bf0a  xor     r15d, r15d
0x14005bf0d  mov     [rsp+0A8h+Object], r15
0x14005bf12  movups  xmmword ptr [rsp+0A8h+Handle], xmm0
0x14005bf17  mov     rax, [rsp+0A8h+Address]
0x14005bf1f  mov     [rax], r15
0x14005bf22  mov     [rsp+0A8h+var_74], r15d
0x14005bf27  xor     ecx, ecx; Irp
0x14005bf29  call    cs:__imp_IoIs32bitProcess
0x14005bf30  nop     dword ptr [rax+rax+00h]
0x14005bf35  test    al, al
0x14005bf37  jz      loc_14005BFC2
0x14005bf3d  mov     [rsp+0A8h+Address], r15
0x14005bf45  cmp     [rsp+0A8h+arg_20], 8
0x14005bf4d  jnb     short loc_14005BF60
0x14005bf4f  mov     ecx, 0C000000Dh; Status
0x14005bf54  call    cs:__imp_ExRaiseStatus
0x14005bf60  test    dil, dil
0x14005bf63  jz      short loc_14005BF8E
0x14005bf65  test    bl, 3
0x14005bf68  jz      short loc_14005BF77
0x14005bf6a  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005bf71  nop     dword ptr [rax+rax+00h]
0x14005bf76  int     3; Trap to Debugger
0x14005bf77  test    dil, dil
0x14005bf7a  jz      short loc_14005BF8E
0x14005bf7c  mov     rcx, rbx
0x14005bf7f  call    RtlReadULong64FromUser
0x14005bf84  mov     [rsp+0A8h+Address], rax
0x14005bf8c  jmp     short loc_14005BFAC
0x14005bf8e  mov     r8d, 8; Size
0x14005bf94  mov     rdx, rbx; Src
0x14005bf97  lea     rcx, [rsp+0A8h+Address]; void *
0x14005bf9f  call    RtlCopyVolatileMemory
0x14005bfa4  mov     rax, [rsp+0A8h+Address]
0x14005bfac  movsxd  rcx, eax
0x14005bfaf  mov     [rsp+0A8h+Handle], rcx
0x14005bfb4  mov     eax, dword ptr [rsp+0A8h+Address+4]
0x14005bfbb  mov     [rsp+0A8h+Handle+8], rax
0x14005bfc0  jmp     short loc_14005C020
0x14005bfc2  mov     r8d, 10h; Size
0x14005bfc8  cmp     [rsp+0A8h+arg_20], r8d
0x14005bfd0  jnb     short loc_14005BFE3
0x14005bfd2  mov     ecx, 0C000000Dh; Status
0x14005bfd7  call    cs:__imp_ExRaiseStatus
0x14005bfe3  test    dil, dil
0x14005bfe6  jz      short loc_14005C00E
0x14005bfe8  test    bl, 3
0x14005bfeb  jz      short loc_14005BFFA
0x14005bfed  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005bff4  nop     dword ptr [rax+rax+00h]
0x14005bff9  int     3; Trap to Debugger
0x14005bffa  test    dil, dil
0x14005bffd  jz      short loc_14005C00E
0x14005bfff  mov     rdx, rbx; Src
0x14005c002  lea     rcx, [rsp+0A8h+Handle]; void *
0x14005c007  call    RtlCopyFromUser
0x14005c00c  jmp     short loc_14005C01B
0x14005c00e  mov     rdx, rbx; Src
0x14005c011  lea     rcx, [rsp+0A8h+Handle]; void *
0x14005c016  call    RtlCopyVolatileMemory
0x14005c01b  mov     rax, [rsp+0A8h+Handle+8]
0x14005c020  test    rax, rax
0x14005c023  jnz     short loc_14005C053
0x14005c025  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005c02c  jz      short loc_14005C042
0x14005c02e  lea     edx, [rax+23h]
0x14005c031  mov     ecx, 413h
0x14005c036  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005c03d  call    WPP_SF_
0x14005c042  mov     ecx, 0C000000Dh; Status
0x14005c047  call    cs:__imp_ExRaiseStatus
0x14005c053  test    dil, dil
0x14005c056  jz      short loc_14005C075
0x14005c058  mov     edx, 14h; Length
0x14005c05d  lea     r8d, [rdx-10h]; Alignment
0x14005c061  mov     rcx, rax; Address
0x14005c064  call    cs:__imp_ProbeForWrite
0x14005c06b  nop     dword ptr [rax+rax+00h]
0x14005c070  mov     rax, [rsp+0A8h+Handle+8]
0x14005c075  shr     esi, 0Eh
0x14005c078  and     esi, 3
0x14005c07b  lea     rcx, [rsp+0A8h+Object]
0x14005c080  mov     [rsp+0A8h+var_80], rcx; __int64
0x14005c085  mov     [rsp+0A8h+var_88], rax; __int64
0x14005c08a  mov     r9, [r14+18h]
0x14005c08e  mov     r8b, dil; AccessMode
0x14005c091  mov     edx, esi; DesiredAccess
0x14005c093  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14005c098  call    AfdSanReferenceSwitchSocketByHandle
0x14005c09d  mov     ebx, eax
0x14005c09f  test    eax, eax
0x14005c0a1  js      loc_14005C2B7
0x14005c0a7  mov     r15, [rsp+0A8h+Object]
0x14005c0ac  mov     rdi, [r15+18h]
0x14005c0b0  movzx   ecx, byte ptr [rdi+2]
0x14005c0b4  xor     eax, eax
0x14005c0b6  lock cmpxchg [rdi+170h], ecx
0x14005c0be  jnz     loc_14005C2A0
0x14005c0c4  mov     rcx, rdi
0x14005c0c7  call    AfdLockEndpointContext
0x14005c0cc  mov     r13, rax
0x14005c0cf  mov     cl, 2; NewIrql
0x14005c0d1  call    cs:__imp_KfRaiseIrql
0x14005c0d8  nop     dword ptr [rax+rax+00h]
0x14005c0dd  mov     sil, al
0x14005c0e0  mov     [rsp+0A8h+var_78], al
0x14005c0e4  lea     r12, [rdi+38h]
0x14005c0e8  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14005c0ed  mov     rcx, r12; SpinLock
0x14005c0f0  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005c0f7  nop     dword ptr [rax+rax+00h]
0x14005c0fc  test    dword ptr [rdi+8], 800h
0x14005c103  jnz     loc_14005C268
0x14005c109  cmp     byte ptr [rdi+2], 4
0x14005c10d  jnz     loc_14005C268
0x14005c113  mov     byte ptr [rdi+2], 7
0x14005c117  lea     rbx, [rdi+80h]
0x14005c11e  cmp     [rbx], rbx
0x14005c121  jz      loc_14005C1BE
0x14005c127  mov     byte ptr [rsp+0A8h+Address], 0
0x14005c12f  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14005c134  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005c13b  nop     dword ptr [rax+rax+00h]
0x14005c140  lea     rcx, [rsp+0A8h+Address]; Irql
0x14005c148  call    cs:__imp_IoAcquireCancelSpinLock
0x14005c14f  nop     dword ptr [rax+rax+00h]
0x14005c154  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14005c159  mov     rcx, r12; SpinLock
0x14005c15c  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005c163  nop     dword ptr [rax+rax+00h]
0x14005c168  mov     rsi, [rbx]
0x14005c16b  cmp     rsi, rbx
0x14005c16e  jz      short loc_14005C1AB
0x14005c170  xor     r14d, r14d
0x14005c173  xchg    r14, [rsi-40h]
0x14005c177  test    r14, r14
0x14005c17a  jz      short loc_14005C168
0x14005c17c  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14005c181  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005c188  nop     dword ptr [rax+rax+00h]
0x14005c18d  mov     word ptr [rsi-64h], 201h
0x14005c193  lea     rdx, [rsi-0A8h]
0x14005c19a  mov     rcx, cs:AfdDeviceObject
0x14005c1a1  mov     rax, r14
0x14005c1a4  call    _guard_dispatch_icall
0x14005c1a9  jmp     short loc_14005C140
0x14005c1ab  mov     cl, 2; Irql
0x14005c1ad  call    cs:__imp_IoReleaseCancelSpinLock
0x14005c1b4  nop     dword ptr [rax+rax+00h]
0x14005c1b9  mov     sil, [rsp+0A8h+var_78]
0x14005c1be  mov     rcx, [rdi+60h]
0x14005c1c2  call    AfdDereferenceEndpoint
0x14005c1c7  xor     edx, edx; Val
0x14005c1c9  lea     r8d, [rdx+48h]; Size
0x14005c1cd  lea     rcx, [rdi+60h]; void *
0x14005c1d1  call    memset
0x14005c1d6  mov     word ptr [rdi], 0AFD0h
0x14005c1db  mov     eax, [rdi+8]
0x14005c1de  bt      eax, 8
0x14005c1e2  jb      short loc_14005C1F4
0x14005c1e4  mov     rax, [rdi+18h]
0x14005c1e8  neg     rax
0x14005c1eb  sbb     cl, cl
0x14005c1ed  and     cl, 2
0x14005c1f0  inc     cl
0x14005c1f2  jmp     short loc_14005C202
0x14005c1f4  cmp     qword ptr [rdi+0F0h], 0
0x14005c1fc  setnz   cl
0x14005c1ff  add     cl, 2
0x14005c202  mov     [rdi+2], cl
0x14005c205  mov     edx, [rdi+8]
0x14005c208  mov     dword ptr [rdi+8], 0
0x14005c20f  mov     dword ptr [rdi+48h], 0
0x14005c216  mov     ecx, edx
0x14005c218  and     ecx, 0FFFFFF00h
0x14005c21e  mov     eax, ecx
0x14005c220  xor     eax, [rdi+8]
0x14005c223  btr     eax, 8
0x14005c227  xor     eax, ecx
0x14005c229  mov     [rdi+8], eax
0x14005c22c  mov     eax, edx
0x14005c22e  xor     eax, [rdi+8]
0x14005c231  btr     eax, 1Fh
0x14005c235  xor     eax, edx
0x14005c237  mov     [rdi+8], eax
0x14005c23a  mov     ecx, edx
0x14005c23c  and     ecx, 0C0000000h
0x14005c242  mov     eax, ecx
0x14005c244  xor     eax, [rdi+8]
0x14005c247  btr     eax, 1Eh
0x14005c24b  xor     eax, ecx
0x14005c24d  mov     [rdi+8], eax
0x14005c250  and     edx, 0FFFFF000h
0x14005c256  mov     eax, edx
0x14005c258  xor     eax, [rdi+8]
0x14005c25b  btr     eax, 0Ch
0x14005c25f  xor     eax, edx
0x14005c261  mov     [rdi+8], eax
0x14005c264  xor     ebx, ebx
0x14005c266  jmp     short loc_14005C26D
0x14005c268  mov     ebx, 0C0000008h
0x14005c26d  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14005c272  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005c279  nop     dword ptr [rax+rax+00h]
0x14005c27e  mov     cl, sil; NewIrql
0x14005c281  call    cs:__imp_KeLowerIrql
0x14005c288  nop     dword ptr [rax+rax+00h]
0x14005c28d  mov     rdx, r13
0x14005c290  mov     rcx, rdi
0x14005c293  call    AfdUnlockEndpointContext
0x14005c298  xor     eax, eax
0x14005c29a  xchg    eax, [rdi+170h]
0x14005c2a0  mov     rcx, r15; Object
0x14005c2a3  call    cs:__imp_ObfDereferenceObject
0x14005c2aa  nop     dword ptr [rax+rax+00h]
0x14005c2af  mov     eax, ebx
0x14005c2b1  jmp     short loc_14005C2B7
0x14005c2b3  mov     eax, [rsp+0A8h+var_74]
0x14005c2b7  add     rsp, 70h
0x14005c2bb  pop     r15
0x14005c2bd  pop     r14
0x14005c2bf  pop     r13
0x14005c2c1  pop     r12
0x14005c2c3  pop     rdi
0x14005c2c4  pop     rsi
0x14005c2c5  pop     rbx
0x14005c2c6  retn
0x14007448f  push    rbp
0x140074491  sub     rsp, 30h
0x140074495  mov     rbp, rdx
0x140074498  mov     r8, rcx
0x14007449b  lea     r9, [rbp+34h]
0x14007449f  mov     edx, 0A53h
0x1400744a4  lea     rcx, aMinioSocketsWi_11; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400744ab  call    AfdExceptionFilter
0x1400744b0  nop
0x1400744b1  add     rsp, 30h
0x1400744b5  pop     rbp
0x1400744b6  retn
```
