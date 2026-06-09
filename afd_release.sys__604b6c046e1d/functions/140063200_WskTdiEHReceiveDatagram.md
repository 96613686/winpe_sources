# WskTdiEHReceiveDatagram

- ea: `0x140063200`
- end: `0x14006374e`
- name: `WskTdiEHReceiveDatagram`
- size: `1358`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, void *Src, unsigned int, ULONG SourceBytesToCopy, unsigned int, unsigned int *, PVOID SourceBuffer, PIRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002150`
- `0x140063200`
- `0x140063818`
- `0x140072780`
- `0x140072800`
- `0x140072b00`
- `0x140073020`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400634bf`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400634bf`
- `ntoskrnl!PsReturnPoolQuota` at `0x140063504`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400636f8`
- `ntoskrnl!PsReturnPoolQuota` at `0x140063504`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400636f8`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140063403`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140063403`
- `ntoskrnl!IoAllocateIrp` at `0x14006361a`
- `ntoskrnl!IoAllocateIrp` at `0x14006361a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006334b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006336e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006334b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006336e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400635d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063713`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006372b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400635d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063713`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006372b`
- `ntoskrnl!ObfReferenceObject` at `0x140063463`
- `ntoskrnl!ObfReferenceObject` at `0x140063463`
- `ntoskrnl!IoAllocateMdl` at `0x1400633e6`
- `ntoskrnl!IoAllocateMdl` at `0x1400633e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063296`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063296`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400632ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400632ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400636dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400636dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400633a8`
- `ntoskrnl!ExAllocatePool2` at `0x1400634e1`
- `ntoskrnl!ExAllocatePool2` at `0x1400633a8`
- `ntoskrnl!ExAllocatePool2` at `0x1400634e1`
- `TDI!TdiCopyBufferToMdl` at `0x14006356f`
- `TDI!TdiCopyBufferToMdl` at `0x14006356f`

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
0x140063200  push    rbx
0x140063202  push    rbp
0x140063203  push    rsi
0x140063204  push    rdi
0x140063205  push    r12
0x140063207  push    r13
0x140063209  push    r14
0x14006320b  push    r15
0x14006320d  sub     rsp, 68h
0x140063211  mov     rax, [rsp+0A8h+arg_40]
0x140063219  xorps   xmm0, xmm0
0x14006321c  movsxd  r15, r9d
0x14006321f  mov     rbx, r8
0x140063222  mov     [rsp+0A8h+var_74], 0
0x14006322a  mov     rdi, rcx
0x14006322d  movups  [rsp+0A8h+var_60], xmm0
0x140063232  mov     dword ptr [rax], 0
0x140063238  cmp     edx, 86h
0x14006323e  jg      loc_140063737
0x140063244  cmp     qword ptr [rcx+120h], 0
0x14006324c  jz      loc_140063737
0x140063252  movzx   eax, word ptr [r8+4]
0x140063257  lea     r12, [r8+6]
0x14006325b  mov     r14, [rcx+110h]
0x140063262  add     ax, 2
0x140063266  test    dword ptr [rcx+10h], 10000h
0x14006326d  mov     r13d, [rsp+0A8h+arg_38]
0x140063275  mov     [rsp+0A8h+DestinationMdlChain], r12
0x14006327a  mov     [rsp+0A8h+var_78], ax
0x14006327f  jnz     loc_140063305
0x140063285  cmp     qword ptr [rcx+90h], 0
0x14006328d  jz      short loc_140063305
0x14006328f  add     rcx, 8; SpinLock
0x140063293  xor     sil, sil
0x140063296  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006329d  nop     dword ptr [rax+rax+00h]
0x1400632a2  test    dword ptr [rdi+10h], 10000h
0x1400632a9  mov     [rsp+0A8h+NewIrql], al
0x1400632b0  jnz     short loc_1400632E1
0x1400632b2  mov     rdx, [rdi+90h]
0x1400632b9  test    rdx, rdx
0x1400632bc  jz      short loc_1400632E1
0x1400632be  movzx   ecx, word ptr [rbx+4]
0x1400632c2  cmp     [rdx+3Ch], cx
0x1400632c6  jnz     short loc_1400632DE
0x1400632c8  movzx   r8d, [rsp+0A8h+var_78]; Size
0x1400632ce  add     rdx, 3Eh ; '>'; Buf2
0x1400632d2  mov     rcx, r12; Buf1
0x1400632d5  call    memcmp
0x1400632da  test    eax, eax
0x1400632dc  jz      short loc_1400632E1
0x1400632de  mov     sil, 1
0x1400632e1  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x1400632e8  lea     rcx, [rdi+8]; SpinLock
0x1400632ec  call    cs:__imp_KeReleaseSpinLock
0x1400632f3  nop     dword ptr [rax+rax+00h]
0x1400632f8  cmp     sil, 1
0x1400632fc  jnz     short loc_140063305
0x1400632fe  xor     edi, edi
0x140063300  jmp     loc_1400635E1
0x140063305  test    r15d, r15d
0x140063308  js      loc_140063737
0x14006330e  mov     eax, r13d
0x140063311  not     eax
0x140063313  cmp     eax, r15d
0x140063316  jb      loc_140063737
0x14006331c  test    r15d, r15d
0x14006331f  jnz     short loc_140063326
0x140063321  mov     esi, r13d
0x140063324  jmp     short loc_14006333A
0x140063326  cmp     r13d, 0FFFFFFF7h
0x14006332a  ja      loc_140063737
0x140063330  lea     esi, [r13+7]
0x140063334  and     esi, 0FFFFFFF8h
0x140063337  add     esi, r15d
0x14006333a  mov     eax, 4
0x14006333f  lea     rcx, stru_1400877C0; Lookaside
0x140063346  cmp     esi, eax
0x140063348  cmovb   esi, eax
0x14006334b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140063352  nop     dword ptr [rax+rax+00h]
0x140063357  mov     [rsp+0A8h+Entry], rax
0x14006335c  test    rax, rax
0x14006335f  jz      loc_140063737
0x140063365  lea     rcx, Lookaside; Lookaside
0x14006336c  xor     ebp, ebp
0x14006336e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140063375  nop     dword ptr [rax+rax+00h]
0x14006337a  mov     rbx, rax
0x14006337d  test    rax, rax
0x140063380  jz      short loc_1400633BC
0x140063382  xor     edx, edx; Val
0x140063384  lea     r8d, [rbp+68h]; Size
0x140063388  mov     rcx, rax; void *
0x14006338b  call    memset
0x140063390  mov     r12d, esi
0x140063393  test    r14, r14
0x140063396  jnz     loc_1400634B4
0x14006339c  mov     r8d, 724B5357h
0x1400633a2  lea     ecx, [rbp+40h]
0x1400633a5  mov     edx, r12d
0x1400633a8  call    cs:__imp_ExAllocatePool2
0x1400633af  nop     dword ptr [rax+rax+00h]
0x1400633b4  mov     rbp, rax
0x1400633b7  mov     r12, [rsp+0A8h+DestinationMdlChain]
0x1400633bc  test    rbp, rbp
0x1400633bf  jz      loc_140063704
0x1400633c5  mov     eax, 4
0x1400633ca  mov     [rsp+0A8h+Irp], 0; Irp
0x1400633d3  test    r13d, r13d
0x1400633d6  mov     rdx, r13
0x1400633d9  mov     rcx, rbp; VirtualAddress
0x1400633dc  cmovz   rdx, rax; Length
0x1400633e0  xor     r9d, r9d; ChargeQuota
0x1400633e3  xor     r8d, r8d; SecondaryBuffer
0x1400633e6  call    cs:__imp_IoAllocateMdl
0x1400633ed  nop     dword ptr [rax+rax+00h]
0x1400633f2  mov     [rsp+0A8h+DestinationMdlChain], rax
0x1400633f7  test    rax, rax
0x1400633fa  jz      loc_1400636CF
0x140063400  mov     rcx, rax; MemoryDescriptorList
0x140063403  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14006340a  nop     dword ptr [rax+rax+00h]
0x14006340f  mov     rsi, r13
0x140063412  test    r15d, r15d
0x140063415  jz      short loc_14006343A
0x140063417  mov     rdx, [rsp+0A8h+Src]; Src
0x14006341f  lea     rcx, [r13+7]
0x140063423  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140063427  mov     [rbx+30h], r15d
0x14006342b  add     rcx, rbp; void *
0x14006342e  mov     r8, r15; Size
0x140063431  mov     [rbx+28h], rcx
0x140063435  call    memmove
0x14006343a  mov     rax, [rsp+0A8h+Entry]
0x14006343f  mov     r15, [rsp+0A8h+DestinationMdlChain]
0x140063444  add     rax, 38h ; '8'
0x140063448  mov     [rbx+60h], rax
0x14006344c  mov     [rbx+10h], r15
0x140063450  mov     dword ptr [rbx+18h], 0
0x140063457  mov     [rbx+20h], rsi
0x14006345b  test    r14, r14
0x14006345e  jz      short loc_14006346F
0x140063460  mov     rcx, r14; Object
0x140063463  call    cs:__imp_ObfReferenceObject
0x14006346a  nop     dword ptr [rax+rax+00h]
0x14006346f  mov     rcx, [rbx+60h]; void *
0x140063473  mov     [rbx+50h], r14
0x140063477  xor     r14d, r14d
0x14006347a  mov     [rbx+40h], r14
0x14006347e  mov     [rbx+58h], rbp
0x140063482  mov     byte ptr [rbx], 1
0x140063485  mov     [rbx+38h], rcx
0x140063489  mov     eax, [rdi+10h]
0x14006348c  test    al, 20h
0x14006348e  jz      loc_140063515
0x140063494  lea     eax, [r14+2]
0x140063498  cmp     [r12], ax
0x14006349d  jnz     short loc_140063515
0x14006349f  movzx   r9d, word ptr [r12+2]
0x1400634a5  lea     rdx, [r12+4]
0x1400634aa  mov     r8d, r14d
0x1400634ad  call    IN6ADDR_SETV4MAPPED
0x1400634b2  jmp     short loc_140063523
0x1400634b4  mov     r8, r12; Amount
0x1400634b7  mov     edx, 200h; PoolType
0x1400634bc  mov     rcx, r14; Process
0x1400634bf  call    cs:__imp_PsChargeProcessPoolQuota
0x1400634c6  nop     dword ptr [rax+rax+00h]
0x1400634cb  test    eax, eax
0x1400634cd  js      loc_1400633B7
0x1400634d3  mov     r8d, 724B5357h
0x1400634d9  mov     rdx, r12
0x1400634dc  mov     ecx, 40h ; '@'
0x1400634e1  call    cs:__imp_ExAllocatePool2
0x1400634e8  nop     dword ptr [rax+rax+00h]
0x1400634ed  mov     rbp, rax
0x1400634f0  test    rax, rax
0x1400634f3  jnz     loc_1400633B7
0x1400634f9  mov     r8, r12; Amount
0x1400634fc  mov     edx, 200h; PoolType
0x140063501  mov     rcx, r14; Process
0x140063504  call    cs:__imp_PsReturnPoolQuota
0x14006350b  nop     dword ptr [rax+rax+00h]
0x140063510  jmp     loc_140063709
0x140063515  movzx   r8d, [rsp+0A8h+var_78]; Size
0x14006351b  mov     rdx, r12; Src
0x14006351e  call    memmove
0x140063523  mov     ebp, [rsp+0A8h+arg_28]
0x14006352a  mov     edx, 2
0x14006352f  mov     r8d, [rsp+0A8h+SourceBytesToCopy]; SourceBytesToCopy
0x140063537  mov     ecx, ebp
0x140063539  shr     ecx, 2
0x14006353c  and     ecx, 1
0x14006353f  mov     esi, ecx
0x140063541  or      esi, edx
0x140063543  test    bpl, 8
0x140063547  cmovz   esi, ecx
0x14006354a  cmp     r8d, r13d
0x14006354d  jnz     loc_1400635F3
0x140063553  mov     rcx, [rsp+0A8h+SourceBuffer]; SourceBuffer
0x14006355b  lea     rax, [rsp+0A8h+var_74]
0x140063560  mov     [rsp+0A8h+BytesCopied], rax; BytesCopied
0x140063565  mov     r9, r15; DestinationMdlChain
0x140063568  xor     edx, edx; SourceOffset
0x14006356a  mov     dword ptr [rsp+0A8h+Irp], r14d; DestinationOffset
0x14006356f  call    cs:__imp_TdiCopyBufferToMdl
0x140063576  nop     dword ptr [rax+rax+00h]
0x14006357b  mov     dword ptr [rsp+0A8h+var_60], esi
0x14006357f  lea     rax, [rbx+8]
0x140063583  mov     qword ptr [rsp+0A8h+var_60+8], rax
0x140063588  bt      ebp, 0Bh
0x14006358c  jnb     short loc_140063595
0x14006358e  or      esi, 4
0x140063591  mov     dword ptr [rsp+0A8h+var_60], esi
0x140063595  mov     rax, [rdi+120h]
0x14006359c  lea     rdx, [rsp+0A8h+var_60]
0x1400635a1  mov     rcx, [rdi+118h]
0x1400635a8  mov     rax, [rax+8]
0x1400635ac  call    _guard_dispatch_icall
0x1400635b1  cmp     eax, 0C0000016h
0x1400635b6  mov     edi, r14d
0x1400635b9  cmovnz  edi, eax
0x1400635bc  cmp     qword ptr [rsp+0A8h+var_60+8], r14
0x1400635c1  jz      short loc_1400635E1
0x1400635c3  mov     rcx, rbx
0x1400635c6  call    WskTdiFreeDatagramIndicationResources
0x1400635cb  mov     rdx, rbx; Entry
0x1400635ce  lea     rcx, Lookaside; Lookaside
0x1400635d5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400635dc  nop     dword ptr [rax+rax+00h]
0x1400635e1  mov     rax, [rsp+0A8h+arg_40]
0x1400635e9  mov     [rax], r13d
0x1400635ec  mov     eax, edi
0x1400635ee  jmp     loc_14006373C
0x1400635f3  mov     eax, [rdi+10h]
0x1400635f6  test    al, 20h
0x1400635f8  jz      short loc_14006360B
0x1400635fa  cmp     [r12], dx
0x1400635ff  jnz     short loc_14006360B
0x140063601  mov     rbp, [rdi+60h]
0x140063605  mov     r14, [rdi+58h]
0x140063609  jmp     short loc_140063613
0x14006360b  mov     rbp, [rdi+48h]
0x14006360f  mov     r14, [rdi+40h]
0x140063613  mov     cl, [rbp+4Ch]
0x140063616  xor     edx, edx; ChargeQuota
0x140063618  inc     cl; StackSize
0x14006361a  call    cs:__imp_IoAllocateIrp
0x140063621  nop     dword ptr [rax+rax+00h]
0x140063626  xor     r8d, r8d
0x140063629  mov     rdx, rax
0x14006362c  test    rax, rax
0x14006362f  jnz     short loc_140063648
0x140063631  mov     rcx, rbx
0x140063634  call    WskTdiFreeDatagramIndicationResources
0x140063639  mov     rdx, rbx
0x14006363c  lea     rcx, Lookaside
0x140063643  jmp     loc_14006372B
0x140063648  dec     byte ptr [rax+43h]
0x14006364b  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140063653  mov     rax, [rax+0B8h]
0x14006365a  mov     ecx, esi
0x14006365c  mov     [rax+8], rbx
0x140063660  mov     rax, [rdx+0B8h]
0x140063667  mov     [rax+10h], rcx
0x14006366b  lock inc dword ptr [rdi+18h]
0x14006366f  mov     rax, [rdx+0B8h]
0x140063676  lea     rcx, WskTdiRestartReceiveDatagram
0x14006367d  mov     [rax-10h], rcx
0x140063681  mov     [rax-8], rdi
0x140063685  mov     byte ptr [rax-45h], 0E0h
0x140063689  mov     rax, [rdx+0B8h]
0x140063690  mov     word ptr [rax-48h], 0A0Fh
0x140063696  mov     [rax-20h], rbp
0x14006369a  mov     [rax-18h], r14
0x14006369e  mov     [rax-40h], r13d
0x1400636a2  mov     [rax-38h], r8
0x1400636a6  mov     [rax-30h], r8
0x1400636aa  mov     [rax-28h], r8d
0x1400636ae  mov     rax, [rsp+0A8h+arg_50]
0x1400636b6  dec     byte ptr [rdx+43h]
0x1400636b9  add     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400636c1  mov     [rdx+8], r15
0x1400636c5  mov     [rax], rdx
0x1400636c8  mov     eax, 0C0000016h
0x1400636cd  jmp     short loc_14006373C
0x1400636cf  test    rbp, rbp
0x1400636d2  jz      short loc_140063704
0x1400636d4  mov     edx, 724B5357h; Tag
0x1400636d9  mov     rcx, rbp; P
0x1400636dc  call    cs:__imp_ExFreePoolWithTag
0x1400636e3  nop     dword ptr [rax+rax+00h]
0x1400636e8  test    r14, r14
0x1400636eb  jz      short loc_140063704
0x1400636ed  mov     r8d, esi; Amount
0x1400636f0  mov     edx, 200h; PoolType
0x1400636f5  mov     rcx, r14; Process
0x1400636f8  call    cs:__imp_PsReturnPoolQuota
0x1400636ff  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
