# WskTdiEHReceiveDatagram

- ea: `0x1400633a0`
- end: `0x1400638ee`
- name: `WskTdiEHReceiveDatagram`
- size: `1358`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, int, ULONG SourceBytesToCopy, int, __int64, PVOID SourceBuffer, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002150`
- `0x1400633a0`
- `0x1400639b8`
- `0x140072920`
- `0x140072980`
- `0x140072c80`
- `0x1400731a0`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14006365f`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14006365f`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400636a4`
- `ntoskrnl!PsReturnPoolQuota` at `0x140063898`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400636a4`
- `ntoskrnl!PsReturnPoolQuota` at `0x140063898`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400635a3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400635a3`
- `ntoskrnl!IoAllocateIrp` at `0x1400637ba`
- `ntoskrnl!IoAllocateIrp` at `0x1400637ba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400634eb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006350e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400634eb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006350e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063775`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400638b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400638cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063775`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400638b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400638cb`
- `ntoskrnl!ObfReferenceObject` at `0x140063603`
- `ntoskrnl!ObfReferenceObject` at `0x140063603`
- `ntoskrnl!IoAllocateMdl` at `0x140063586`
- `ntoskrnl!IoAllocateMdl` at `0x140063586`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063436`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063436`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006348c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006348c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006387c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006387c`
- `ntoskrnl!ExAllocatePool2` at `0x140063548`
- `ntoskrnl!ExAllocatePool2` at `0x140063681`
- `ntoskrnl!ExAllocatePool2` at `0x140063548`
- `ntoskrnl!ExAllocatePool2` at `0x140063681`
- `TDI!TdiCopyBufferToMdl` at `0x14006370f`
- `TDI!TdiCopyBufferToMdl` at `0x14006370f`

## pseudocode

```c
__int64 __fastcall WskTdiEHReceiveDatagram(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        void *Src,
        unsigned int a6,
        ULONG SourceBytesToCopy,
        unsigned int a8,
        unsigned int *a9,
        PVOID SourceBuffer,
        PIRP *a11)
{
  size_t v11; // r15
  unsigned __int16 *v14; // r12
  struct _KPROCESS *v15; // r14
  unsigned __int16 v16; // ax
  bool v17; // zf
  char v18; // si
  __int64 v19; // rdx
  unsigned int v20; // edi
  unsigned int v21; // esi
  char *Pool2; // rbp
  _DWORD *v23; // rax
  _DWORD *v24; // rbx
  ULONG v25; // edx
  struct _MDL *Mdl; // rax
  char *v27; // rcx
  struct _MDL *v28; // r15
  void *v29; // rcx
  unsigned int v30; // esi
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  struct _DEVICE_OBJECT *v35; // rbp
  struct _FILE_OBJECT *v36; // r14
  PIRP Irp; // rax
  PIRP v38; // rdx
  PVOID v39; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v40; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v42; // rax
  unsigned __int16 v43; // [rsp+30h] [rbp-78h]
  ULONG BytesCopied; // [rsp+34h] [rbp-74h] BYREF
  PMDL DestinationMdlChain; // [rsp+38h] [rbp-70h]
  PVOID Entry; // [rsp+40h] [rbp-68h]
  __int128 v47; // [rsp+48h] [rbp-60h] BYREF
  KIRQL NewIrql; // [rsp+B8h] [rbp+10h]

  v11 = a4;
  BytesCopied = 0;
  v47 = 0;
  *a9 = 0;
  if ( a2 > 134 || !*(_QWORD *)(a1 + 288) )
    return 3221226011LL;
  v14 = (unsigned __int16 *)(a3 + 6);
  v15 = *(struct _KPROCESS **)(a1 + 272);
  v16 = *(_WORD *)(a3 + 4) + 2;
  v17 = (*(_DWORD *)(a1 + 16) & 0x10000) == 0;
  DestinationMdlChain = (PMDL)(a3 + 6);
  v43 = v16;
  if ( v17 && *(_QWORD *)(a1 + 144) )
  {
    v18 = 0;
    NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    if ( (*(_DWORD *)(a1 + 16) & 0x10000) == 0 )
    {
      v19 = *(_QWORD *)(a1 + 144);
      if ( v19 )
      {
        if ( *(_WORD *)(v19 + 60) != *(_WORD *)(a3 + 4) || memcmp(v14, (const void *)(v19 + 62), v43) )
          v18 = 1;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), NewIrql);
    if ( v18 == 1 )
    {
      v20 = 0;
LABEL_49:
      *a9 = a8;
      return v20;
    }
  }
  if ( (v11 & 0x80000000) != 0LL || ~a8 < (unsigned int)v11 )
    return 3221226011LL;
  if ( !(_DWORD)v11 )
  {
    v21 = a8;
    goto LABEL_18;
  }
  if ( a8 <= 0xFFFFFFF7 )
  {
    v21 = v11 + ((a8 + 7) & 0xFFFFFFF8);
LABEL_18:
    if ( v21 < 4 )
      v21 = 4;
    Entry = ExAllocateFromNPagedLookasideList(&stru_1400877C0);
    if ( !Entry )
      return 3221226011LL;
    Pool2 = 0;
    v23 = ExAllocateFromNPagedLookasideList(&Lookaside);
    v24 = v23;
    if ( v23 )
    {
      memset(v23, 0, 0x68u);
      if ( v15 )
      {
        if ( PsChargeProcessPoolQuota(v15, (POOL_TYPE)512, v21) >= 0 )
        {
          Pool2 = (char *)ExAllocatePool2(64, v21, 1917539159);
          if ( !Pool2 )
          {
            PsReturnPoolQuota(v15, (POOL_TYPE)512, v21);
            goto LABEL_60;
          }
        }
      }
      else
      {
        Pool2 = (char *)ExAllocatePool2(64, v21, 1917539159);
      }
      v14 = (unsigned __int16 *)DestinationMdlChain;
    }
    if ( Pool2 )
    {
      v25 = a8;
      if ( !a8 )
        v25 = 4;
      Mdl = IoAllocateMdl(Pool2, v25, 0, 0, 0);
      DestinationMdlChain = Mdl;
      if ( Mdl )
      {
        MmBuildMdlForNonPagedPool(Mdl);
        if ( (_DWORD)v11 )
        {
          v24[12] = v11;
          v27 = &Pool2[(a8 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
          *((_QWORD *)v24 + 5) = v27;
          memmove(v27, Src, v11);
        }
        v28 = DestinationMdlChain;
        *((_QWORD *)v24 + 12) = (char *)Entry + 56;
        *((_QWORD *)v24 + 2) = v28;
        v24[6] = 0;
        *((_QWORD *)v24 + 4) = a8;
        if ( v15 )
          ObfReferenceObject(v15);
        v29 = (void *)*((_QWORD *)v24 + 12);
        *((_QWORD *)v24 + 10) = v15;
        *((_QWORD *)v24 + 8) = 0;
        *((_QWORD *)v24 + 11) = Pool2;
        *(_BYTE *)v24 = 1;
        *((_QWORD *)v24 + 7) = v29;
        if ( (*(_DWORD *)(a1 + 16) & 0x20) != 0 && *v14 == 2 )
          IN6ADDR_SETV4MAPPED(v29, v14 + 2, 0, v14[1]);
        else
          memmove(v29, v14, v43);
        v30 = (a6 >> 2) & 1 | 2;
        if ( (a6 & 8) == 0 )
          v30 = (a6 >> 2) & 1;
        if ( SourceBytesToCopy == a8 )
        {
          TdiCopyBufferToMdl(SourceBuffer, 0, SourceBytesToCopy, v28, 0, &BytesCopied);
          LODWORD(v47) = v30;
          *((_QWORD *)&v47 + 1) = v24 + 2;
          if ( (a6 & 0x800) != 0 )
            LODWORD(v47) = v30 | 4;
          v31 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(a1 + 288) + 8LL))(
                  *(_QWORD *)(a1 + 280),
                  &v47);
          v20 = 0;
          if ( v31 != -1073741802 )
            v20 = v31;
          if ( *((_QWORD *)&v47 + 1) )
          {
            WskTdiFreeDatagramIndicationResources(v24, v32, v33);
            ExFreeToNPagedLookasideList(&Lookaside, v24);
          }
          goto LABEL_49;
        }
        if ( (*(_DWORD *)(a1 + 16) & 0x20) != 0 && *v14 == 2 )
        {
          v35 = *(struct _DEVICE_OBJECT **)(a1 + 96);
          v36 = *(struct _FILE_OBJECT **)(a1 + 88);
        }
        else
        {
          v35 = *(struct _DEVICE_OBJECT **)(a1 + 72);
          v36 = *(struct _FILE_OBJECT **)(a1 + 64);
        }
        Irp = IoAllocateIrp(v35->StackSize + 1, 0);
        v38 = Irp;
        if ( Irp )
        {
          --Irp->CurrentLocation;
          --Irp->Tail.Overlay.CurrentStackLocation;
          Irp->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId = (ULONG_PTR)v24;
          Irp->Tail.Overlay.CurrentStackLocation->Parameters.QueryDirectory.FileName = (PUNICODE_STRING)v30;
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 24));
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskTdiRestartReceiveDatagram;
          CurrentStackLocation[-1].Context = (PVOID)a1;
          CurrentStackLocation[-1].Control = -32;
          v42 = v38->Tail.Overlay.CurrentStackLocation;
          *(_WORD *)&v42[-1].MajorFunction = 2575;
          v42[-1].DeviceObject = v35;
          v42[-1].FileObject = v36;
          v42[-1].Parameters.Read.Length = a8;
          v42[-1].Parameters.QueryDirectory.FileName = 0;
          v42[-1].Parameters.Read.ByteOffset.QuadPart = 0;
          v42[-1].Parameters.Create.EaLength = 0;
          --v38->CurrentLocation;
          --v38->Tail.Overlay.CurrentStackLocation;
          v38->MdlAddress = v28;
          *a11 = v38;
          return 3221225494LL;
        }
        WskTdiFreeDatagramIndicationResources(v24, 0, 0);
        v39 = v24;
        v40 = &Lookaside;
        goto LABEL_62;
      }
      ExFreePoolWithTag(Pool2, 0x724B5357u);
      if ( v15 )
        PsReturnPoolQuota(v15, (POOL_TYPE)512, v21);
    }
    if ( !v24 )
    {
LABEL_61:
      v39 = Entry;
      v40 = &stru_1400877C0;
LABEL_62:
      ExFreeToNPagedLookasideList(v40, v39);
      return 3221226011LL;
    }
LABEL_60:
    ExFreeToNPagedLookasideList(&Lookaside, v24);
    goto LABEL_61;
  }
  return 3221226011LL;
}

```

## disassembly

```asm
0x1400633a0  push    rbx
0x1400633a2  push    rbp
0x1400633a3  push    rsi
0x1400633a4  push    rdi
0x1400633a5  push    r12
0x1400633a7  push    r13
0x1400633a9  push    r14
0x1400633ab  push    r15
0x1400633ad  sub     rsp, 68h
0x1400633b1  mov     rax, [rsp+0A8h+arg_40]
0x1400633b9  xorps   xmm0, xmm0
0x1400633bc  movsxd  r15, r9d
0x1400633bf  mov     rbx, r8
0x1400633c2  mov     [rsp+0A8h+var_74], 0
0x1400633ca  mov     rdi, rcx
0x1400633cd  movups  [rsp+0A8h+var_60], xmm0
0x1400633d2  mov     dword ptr [rax], 0
0x1400633d8  cmp     edx, 86h
0x1400633de  jg      loc_1400638D7
0x1400633e4  cmp     qword ptr [rcx+120h], 0
0x1400633ec  jz      loc_1400638D7
0x1400633f2  movzx   eax, word ptr [r8+4]
0x1400633f7  lea     r12, [r8+6]
0x1400633fb  mov     r14, [rcx+110h]
0x140063402  add     ax, 2
0x140063406  test    dword ptr [rcx+10h], 10000h
0x14006340d  mov     r13d, [rsp+0A8h+arg_38]
0x140063415  mov     [rsp+0A8h+DestinationMdlChain], r12
0x14006341a  mov     [rsp+0A8h+var_78], ax
0x14006341f  jnz     loc_1400634A5
0x140063425  cmp     qword ptr [rcx+90h], 0
0x14006342d  jz      short loc_1400634A5
0x14006342f  add     rcx, 8; SpinLock
0x140063433  xor     sil, sil
0x140063436  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006343d  nop     dword ptr [rax+rax+00h]
0x140063442  test    dword ptr [rdi+10h], 10000h
0x140063449  mov     [rsp+0A8h+NewIrql], al
0x140063450  jnz     short loc_140063481
0x140063452  mov     rdx, [rdi+90h]
0x140063459  test    rdx, rdx
0x14006345c  jz      short loc_140063481
0x14006345e  movzx   ecx, word ptr [rbx+4]
0x140063462  cmp     [rdx+3Ch], cx
0x140063466  jnz     short loc_14006347E
0x140063468  movzx   r8d, [rsp+0A8h+var_78]; Size
0x14006346e  add     rdx, 3Eh ; '>'; Buf2
0x140063472  mov     rcx, r12; Buf1
0x140063475  call    memcmp
0x14006347a  test    eax, eax
0x14006347c  jz      short loc_140063481
0x14006347e  mov     sil, 1
0x140063481  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x140063488  lea     rcx, [rdi+8]; SpinLock
0x14006348c  call    cs:__imp_KeReleaseSpinLock
0x140063493  nop     dword ptr [rax+rax+00h]
0x140063498  cmp     sil, 1
0x14006349c  jnz     short loc_1400634A5
0x14006349e  xor     edi, edi
0x1400634a0  jmp     loc_140063781
0x1400634a5  test    r15d, r15d
0x1400634a8  js      loc_1400638D7
0x1400634ae  mov     eax, r13d
0x1400634b1  not     eax
0x1400634b3  cmp     eax, r15d
0x1400634b6  jb      loc_1400638D7
0x1400634bc  test    r15d, r15d
0x1400634bf  jnz     short loc_1400634C6
0x1400634c1  mov     esi, r13d
0x1400634c4  jmp     short loc_1400634DA
0x1400634c6  cmp     r13d, 0FFFFFFF7h
0x1400634ca  ja      loc_1400638D7
0x1400634d0  lea     esi, [r13+7]
0x1400634d4  and     esi, 0FFFFFFF8h
0x1400634d7  add     esi, r15d
0x1400634da  mov     eax, 4
0x1400634df  lea     rcx, stru_1400877C0; Lookaside
0x1400634e6  cmp     esi, eax
0x1400634e8  cmovb   esi, eax
0x1400634eb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400634f2  nop     dword ptr [rax+rax+00h]
0x1400634f7  mov     [rsp+0A8h+Entry], rax
0x1400634fc  test    rax, rax
0x1400634ff  jz      loc_1400638D7
0x140063505  lea     rcx, Lookaside; Lookaside
0x14006350c  xor     ebp, ebp
0x14006350e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140063515  nop     dword ptr [rax+rax+00h]
0x14006351a  mov     rbx, rax
0x14006351d  test    rax, rax
0x140063520  jz      short loc_14006355C
0x140063522  xor     edx, edx; Val
0x140063524  lea     r8d, [rbp+68h]; Size
0x140063528  mov     rcx, rax; void *
0x14006352b  call    memset
0x140063530  mov     r12d, esi
0x140063533  test    r14, r14
0x140063536  jnz     loc_140063654
0x14006353c  mov     r8d, 724B5357h
0x140063542  lea     ecx, [rbp+40h]
0x140063545  mov     edx, r12d
0x140063548  call    cs:__imp_ExAllocatePool2
0x14006354f  nop     dword ptr [rax+rax+00h]
0x140063554  mov     rbp, rax
0x140063557  mov     r12, [rsp+0A8h+DestinationMdlChain]
0x14006355c  test    rbp, rbp
0x14006355f  jz      loc_1400638A4
0x140063565  mov     eax, 4
0x14006356a  mov     [rsp+0A8h+Irp], 0; Irp
0x140063573  test    r13d, r13d
0x140063576  mov     rdx, r13
0x140063579  mov     rcx, rbp; VirtualAddress
0x14006357c  cmovz   rdx, rax; Length
0x140063580  xor     r9d, r9d; ChargeQuota
0x140063583  xor     r8d, r8d; SecondaryBuffer
0x140063586  call    cs:__imp_IoAllocateMdl
0x14006358d  nop     dword ptr [rax+rax+00h]
0x140063592  mov     [rsp+0A8h+DestinationMdlChain], rax
0x140063597  test    rax, rax
0x14006359a  jz      loc_14006386F
0x1400635a0  mov     rcx, rax; MemoryDescriptorList
0x1400635a3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400635aa  nop     dword ptr [rax+rax+00h]
0x1400635af  mov     rsi, r13
0x1400635b2  test    r15d, r15d
0x1400635b5  jz      short loc_1400635DA
0x1400635b7  mov     rdx, [rsp+0A8h+Src]; Src
0x1400635bf  lea     rcx, [r13+7]
0x1400635c3  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1400635c7  mov     [rbx+30h], r15d
0x1400635cb  add     rcx, rbp; void *
0x1400635ce  mov     r8, r15; Size
0x1400635d1  mov     [rbx+28h], rcx
0x1400635d5  call    memmove
0x1400635da  mov     rax, [rsp+0A8h+Entry]
0x1400635df  mov     r15, [rsp+0A8h+DestinationMdlChain]
0x1400635e4  add     rax, 38h ; '8'
0x1400635e8  mov     [rbx+60h], rax
0x1400635ec  mov     [rbx+10h], r15
0x1400635f0  mov     dword ptr [rbx+18h], 0
0x1400635f7  mov     [rbx+20h], rsi
0x1400635fb  test    r14, r14
0x1400635fe  jz      short loc_14006360F
0x140063600  mov     rcx, r14; Object
0x140063603  call    cs:__imp_ObfReferenceObject
0x14006360a  nop     dword ptr [rax+rax+00h]
0x14006360f  mov     rcx, [rbx+60h]; void *
0x140063613  mov     [rbx+50h], r14
0x140063617  xor     r14d, r14d
0x14006361a  mov     [rbx+40h], r14
0x14006361e  mov     [rbx+58h], rbp
0x140063622  mov     byte ptr [rbx], 1
0x140063625  mov     [rbx+38h], rcx
0x140063629  mov     eax, [rdi+10h]
0x14006362c  test    al, 20h
0x14006362e  jz      loc_1400636B5
0x140063634  lea     eax, [r14+2]
0x140063638  cmp     [r12], ax
0x14006363d  jnz     short loc_1400636B5
0x14006363f  movzx   r9d, word ptr [r12+2]
0x140063645  lea     rdx, [r12+4]
0x14006364a  mov     r8d, r14d
0x14006364d  call    IN6ADDR_SETV4MAPPED
0x140063652  jmp     short loc_1400636C3
0x140063654  mov     r8, r12; Amount
0x140063657  mov     edx, 200h; PoolType
0x14006365c  mov     rcx, r14; Process
0x14006365f  call    cs:__imp_PsChargeProcessPoolQuota
0x140063666  nop     dword ptr [rax+rax+00h]
0x14006366b  test    eax, eax
0x14006366d  js      loc_140063557
0x140063673  mov     r8d, 724B5357h
0x140063679  mov     rdx, r12
0x14006367c  mov     ecx, 40h ; '@'
0x140063681  call    cs:__imp_ExAllocatePool2
0x140063688  nop     dword ptr [rax+rax+00h]
0x14006368d  mov     rbp, rax
0x140063690  test    rax, rax
0x140063693  jnz     loc_140063557
0x140063699  mov     r8, r12; Amount
0x14006369c  mov     edx, 200h; PoolType
0x1400636a1  mov     rcx, r14; Process
0x1400636a4  call    cs:__imp_PsReturnPoolQuota
0x1400636ab  nop     dword ptr [rax+rax+00h]
0x1400636b0  jmp     loc_1400638A9
0x1400636b5  movzx   r8d, [rsp+0A8h+var_78]; Size
0x1400636bb  mov     rdx, r12; Src
0x1400636be  call    memmove
0x1400636c3  mov     ebp, [rsp+0A8h+arg_28]
0x1400636ca  mov     edx, 2
0x1400636cf  mov     r8d, [rsp+0A8h+SourceBytesToCopy]; SourceBytesToCopy
0x1400636d7  mov     ecx, ebp
0x1400636d9  shr     ecx, 2
0x1400636dc  and     ecx, 1
0x1400636df  mov     esi, ecx
0x1400636e1  or      esi, edx
0x1400636e3  test    bpl, 8
0x1400636e7  cmovz   esi, ecx
0x1400636ea  cmp     r8d, r13d
0x1400636ed  jnz     loc_140063793
0x1400636f3  mov     rcx, [rsp+0A8h+SourceBuffer]; SourceBuffer
0x1400636fb  lea     rax, [rsp+0A8h+var_74]
0x140063700  mov     [rsp+0A8h+BytesCopied], rax; BytesCopied
0x140063705  mov     r9, r15; DestinationMdlChain
0x140063708  xor     edx, edx; SourceOffset
0x14006370a  mov     dword ptr [rsp+0A8h+Irp], r14d; DestinationOffset
0x14006370f  call    cs:__imp_TdiCopyBufferToMdl
0x140063716  nop     dword ptr [rax+rax+00h]
0x14006371b  mov     dword ptr [rsp+0A8h+var_60], esi
0x14006371f  lea     rax, [rbx+8]
0x140063723  mov     qword ptr [rsp+0A8h+var_60+8], rax
0x140063728  bt      ebp, 0Bh
0x14006372c  jnb     short loc_140063735
0x14006372e  or      esi, 4
0x140063731  mov     dword ptr [rsp+0A8h+var_60], esi
0x140063735  mov     rax, [rdi+120h]
0x14006373c  lea     rdx, [rsp+0A8h+var_60]
0x140063741  mov     rcx, [rdi+118h]
0x140063748  mov     rax, [rax+8]
0x14006374c  call    _guard_dispatch_icall
0x140063751  cmp     eax, 0C0000016h
0x140063756  mov     edi, r14d
0x140063759  cmovnz  edi, eax
0x14006375c  cmp     qword ptr [rsp+0A8h+var_60+8], r14
0x140063761  jz      short loc_140063781
0x140063763  mov     rcx, rbx
0x140063766  call    WskTdiFreeDatagramIndicationResources
0x14006376b  mov     rdx, rbx; Entry
0x14006376e  lea     rcx, Lookaside; Lookaside
0x140063775  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006377c  nop     dword ptr [rax+rax+00h]
0x140063781  mov     rax, [rsp+0A8h+arg_40]
0x140063789  mov     [rax], r13d
0x14006378c  mov     eax, edi
0x14006378e  jmp     loc_1400638DC
0x140063793  mov     eax, [rdi+10h]
0x140063796  test    al, 20h
0x140063798  jz      short loc_1400637AB
0x14006379a  cmp     [r12], dx
0x14006379f  jnz     short loc_1400637AB
0x1400637a1  mov     rbp, [rdi+60h]
0x1400637a5  mov     r14, [rdi+58h]
0x1400637a9  jmp     short loc_1400637B3
0x1400637ab  mov     rbp, [rdi+48h]
0x1400637af  mov     r14, [rdi+40h]
0x1400637b3  mov     cl, [rbp+4Ch]
0x1400637b6  xor     edx, edx; ChargeQuota
0x1400637b8  inc     cl; StackSize
0x1400637ba  call    cs:__imp_IoAllocateIrp
0x1400637c1  nop     dword ptr [rax+rax+00h]
0x1400637c6  xor     r8d, r8d
0x1400637c9  mov     rdx, rax
0x1400637cc  test    rax, rax
0x1400637cf  jnz     short loc_1400637E8
0x1400637d1  mov     rcx, rbx
0x1400637d4  call    WskTdiFreeDatagramIndicationResources
0x1400637d9  mov     rdx, rbx
0x1400637dc  lea     rcx, Lookaside
0x1400637e3  jmp     loc_1400638CB
0x1400637e8  dec     byte ptr [rax+43h]
0x1400637eb  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400637f3  mov     rax, [rax+0B8h]
0x1400637fa  mov     ecx, esi
0x1400637fc  mov     [rax+8], rbx
0x140063800  mov     rax, [rdx+0B8h]
0x140063807  mov     [rax+10h], rcx
0x14006380b  lock inc dword ptr [rdi+18h]
0x14006380f  mov     rax, [rdx+0B8h]
0x140063816  lea     rcx, WskTdiRestartReceiveDatagram
0x14006381d  mov     [rax-10h], rcx
0x140063821  mov     [rax-8], rdi
0x140063825  mov     byte ptr [rax-45h], 0E0h
0x140063829  mov     rax, [rdx+0B8h]
0x140063830  mov     word ptr [rax-48h], 0A0Fh
0x140063836  mov     [rax-20h], rbp
0x14006383a  mov     [rax-18h], r14
0x14006383e  mov     [rax-40h], r13d
0x140063842  mov     [rax-38h], r8
0x140063846  mov     [rax-30h], r8
0x14006384a  mov     [rax-28h], r8d
0x14006384e  mov     rax, [rsp+0A8h+arg_50]
0x140063856  dec     byte ptr [rdx+43h]
0x140063859  add     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140063861  mov     [rdx+8], r15
0x140063865  mov     [rax], rdx
0x140063868  mov     eax, 0C0000016h
0x14006386d  jmp     short loc_1400638DC
0x14006386f  test    rbp, rbp
0x140063872  jz      short loc_1400638A4
0x140063874  mov     edx, 724B5357h; Tag
0x140063879  mov     rcx, rbp; P
0x14006387c  call    cs:__imp_ExFreePoolWithTag
0x140063883  nop     dword ptr [rax+rax+00h]
0x140063888  test    r14, r14
0x14006388b  jz      short loc_1400638A4
0x14006388d  mov     r8d, esi; Amount
0x140063890  mov     edx, 200h; PoolType
0x140063895  mov     rcx, r14; Process
0x140063898  call    cs:__imp_PsReturnPoolQuota
0x14006389f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
