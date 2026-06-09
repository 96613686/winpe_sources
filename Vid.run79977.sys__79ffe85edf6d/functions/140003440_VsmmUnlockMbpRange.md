# VsmmUnlockMbpRange

- ea: `0x140003440`
- end: `0x1400036a6`
- name: `VsmmUnlockMbpRange`
- size: `614`
- prototype: `__int64 __fastcall(int, int, int, int, PMDL MemoryDescriptorList)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400276e4`
- `0x1400ef848`
- `0x1400efd40`
- `0x1400fc5e0`

## callees

- `0x140003440`
- `0x1400036ac`
- `0x140003874`
- `0x14001fa24`
- `0x14001fa3c`
- `0x140021e00`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140003640`
- `ntoskrnl!RtlRbRemoveNode` at `0x140003640`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000360f`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000360f`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140003654`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140003654`
- `ntoskrnl!KeSetEvent` at `0x1400035a6`
- `ntoskrnl!KeSetEvent` at `0x1400035a6`
- `ntoskrnl!MmUnlockPages` at `0x1400034ce`
- `ntoskrnl!MmUnlockPages` at `0x140003664`
- `ntoskrnl!MmUnlockPages` at `0x1400034ce`
- `ntoskrnl!MmUnlockPages` at `0x140003664`

## pseudocode

```c
void __fastcall VsmmUnlockMbpRange(__int64 a1, __int64 a2, __int64 a3, int a4, PMDL MemoryDescriptorList)
{
  __int64 v9; // r13
  int v10; // r12d
  struct _MDL *v11; // r14
  unsigned __int64 v12; // rbx
  unsigned int Page; // eax
  __int64 v14; // r15
  __int64 v15; // rax
  unsigned __int64 v16; // rdi
  int v17; // esi
  int v18; // eax
  unsigned __int64 v19; // rax
  KIRQL v20; // al
  unsigned __int64 *v21; // r13
  unsigned __int64 v22; // rsi
  _QWORD v23[22]; // [rsp+20h] [rbp-61h] BYREF
  KIRQL v24; // [rsp+F8h] [rbp+77h]
  volatile LONG *MemoryDescriptorLista; // [rsp+100h] [rbp+7Fh]

  memset(v23, 0, 0x68u);
  v9 = *(_QWORD *)(a1 + 8);
  v10 = 2;
  v11 = MemoryDescriptorList;
  v23[0] = v9;
  LODWORD(v23[1]) = 2;
  v23[3] = MemoryDescriptorList;
  HIDWORD(v23[1]) = a4;
  v23[5] = a3;
  v23[10] = a1;
  v23[11] = a2;
  v23[6] = 0;
  if ( a3 )
  {
    do
    {
      Page = VsmmpUnlockPrepareForNextPage(v23);
      VsmmMbpLockReleaseFast(v23[7], v23[8], Page);
      v12 = v23[9] + 1LL;
      ++v23[6];
      ++v23[9];
    }
    while ( v23[6] < v23[5] );
    a1 = v23[10];
    v11 = (struct _MDL *)v23[3];
    v10 = v23[1];
    v9 = v23[0];
  }
  else
  {
    v12 = v23[9];
  }
  if ( LOBYTE(v23[2]) || !v11 || (v23[4] & 2) == 0 )
    goto LABEL_8;
  if ( LODWORD(v23[4]) != 3 )
  {
    MmUnlockPages(v11);
    goto LABEL_8;
  }
  MemoryDescriptorLista = (volatile LONG *)(v9 + 12528);
  v20 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 12528));
  v21 = (unsigned __int64 *)(v9 + 12536);
  v24 = v20;
  v22 = v21[1];
  v16 = *v21;
  if ( (v22 & 1) == 0 )
  {
LABEL_26:
    v17 = v22 & 1;
    if ( !v16 )
      goto LABEL_37;
    while ( 1 )
    {
      v18 = VsmmpCompareHybridLockContext(v11, v16);
      if ( v18 >= 0 )
      {
        if ( v18 <= 0 )
          goto LABEL_38;
        v19 = *(_QWORD *)(v16 + 8);
        if ( v17 && v19 )
        {
LABEL_30:
          v16 ^= v19;
          goto LABEL_23;
        }
      }
      else
      {
        v19 = *(_QWORD *)v16;
        if ( v17 && v19 )
          goto LABEL_30;
      }
      v16 = v19;
LABEL_23:
      if ( !v16 )
        goto LABEL_37;
    }
  }
  if ( v16 )
  {
    v16 ^= (unsigned __int64)v21;
    goto LABEL_26;
  }
LABEL_37:
  __int2c();
LABEL_38:
  RtlRbRemoveNode(v21, v16);
  ExReleaseSpinLockExclusive(MemoryDescriptorLista, v24);
  MmUnlockPages(*(PMDL *)(v16 + 32));
  VsmmpFreeHybridLockContext((PVOID)v16);
LABEL_8:
  if ( !v12 )
    return;
  if ( v10 )
  {
    if ( v10 != 1 )
    {
      v14 = a1 + 64;
      goto LABEL_15;
    }
  }
  else
  {
    a1 = v23[12];
  }
  v14 = a1 + 448;
LABEL_15:
  if ( *(_QWORD *)(v14 + 8) )
  {
    v15 = *(_QWORD *)v14;
  }
  else
  {
    v15 = _InterlockedExchangeAdd64((volatile signed __int64 *)v14, -(__int64)v12);
    if ( (v15 & 0x7FFFFFFFFFFFFFFFuLL) < v12 )
      __int2c();
  }
  if ( v15 < 0 && (*(_QWORD *)(v14 + 8) || (v15 & 0x7FFFFFFFFFFFFFFFLL) == v12) )
    KeSetEvent((PRKEVENT)(v14 + 16), 0, 0);
}

```

## disassembly

```asm
0x140003440  push    rbp
0x140003442  push    rbx
0x140003443  push    rsi
0x140003444  push    rdi
0x140003445  push    r12
0x140003447  push    r13
0x140003449  push    r14
0x14000344b  push    r15
0x14000344d  lea     rbp, [rsp-17h]
0x140003452  sub     rsp, 98h
0x140003459  mov     rsi, r8
0x14000345c  mov     rdi, rdx
0x14000345f  mov     r15, rcx
0x140003462  xor     edx, edx; Val
0x140003464  mov     r8d, 68h ; 'h'; Size
0x14000346a  lea     rcx, [rbp+4Fh+var_B0]; void *
0x14000346e  mov     ebx, r9d
0x140003471  call    memset
0x140003476  mov     r13, [r15+8]
0x14000347a  mov     r12d, 2
0x140003480  mov     r14, [rbp+4Fh+MemoryDescriptorList]
0x140003484  mov     [rbp+4Fh+var_B0], r13
0x140003488  mov     [rbp+4Fh+var_A8], r12d
0x14000348c  mov     [rbp+4Fh+var_98], r14
0x140003490  mov     [rbp+4Fh+var_A4], ebx
0x140003493  mov     [rbp+4Fh+var_88], rsi
0x140003497  mov     [rbp+4Fh+var_60], r15
0x14000349b  mov     [rbp+4Fh+var_58], rdi
0x14000349f  mov     [rbp+4Fh+var_80], 0
0x1400034a7  test    rsi, rsi
0x1400034aa  jnz     short loc_1400034F4
0x1400034ac  mov     rbx, [rbp+4Fh+var_68]
0x1400034b0  cmp     [rbp+4Fh+var_A0], 0
0x1400034b4  jnz     short loc_1400034DA
0x1400034b6  test    r14, r14
0x1400034b9  jz      short loc_1400034DA
0x1400034bb  mov     eax, [rbp+4Fh+var_90]
0x1400034be  test    al, 2
0x1400034c0  jz      short loc_1400034DA
0x1400034c2  cmp     eax, 3
0x1400034c5  jz      loc_140003601
0x1400034cb  mov     rcx, r14; MemoryDescriptorList
0x1400034ce  call    cs:__imp_MmUnlockPages
0x1400034d5  nop     dword ptr [rax+rax+00h]
0x1400034da  test    rbx, rbx
0x1400034dd  jnz     short loc_14000353E
0x1400034df  add     rsp, 98h
0x1400034e6  pop     r15
0x1400034e8  pop     r14
0x1400034ea  pop     r13
0x1400034ec  pop     r12
0x1400034ee  pop     rdi
0x1400034ef  pop     rsi
0x1400034f0  pop     rbx
0x1400034f1  pop     rbp
0x1400034f2  retn
0x1400034f4  lea     rcx, [rbp+4Fh+var_B0]
0x1400034f8  call    VsmmpUnlockPrepareForNextPage
0x1400034fd  mov     rdx, [rbp+4Fh+var_70]
0x140003501  mov     r8d, eax
0x140003504  mov     rcx, [rbp+4Fh+var_78]
0x140003508  call    VsmmMbpLockReleaseFast
0x14000350d  mov     rax, [rbp+4Fh+var_80]
0x140003511  mov     rbx, [rbp+4Fh+var_68]
0x140003515  inc     rax
0x140003518  inc     rbx
0x14000351b  mov     [rbp+4Fh+var_80], rax
0x14000351f  mov     [rbp+4Fh+var_68], rbx
0x140003523  cmp     rax, [rbp+4Fh+var_88]
0x140003527  jb      short loc_1400034F4
0x140003529  mov     r15, [rbp+4Fh+var_60]
0x14000352d  mov     r14, [rbp+4Fh+var_98]
0x140003531  mov     r12d, [rbp+4Fh+var_A8]
0x140003535  mov     r13, [rbp+4Fh+var_B0]
0x140003539  jmp     loc_1400034B0
0x14000353e  test    r12d, r12d
0x140003541  jnz     loc_140003684
0x140003547  mov     r15, [rbp+4Fh+var_50]
0x14000354b  add     r15, 1C0h
0x140003552  cmp     qword ptr [r15+8], 0
0x140003557  mov     rdx, 7FFFFFFFFFFFFFFFh
0x140003561  jnz     loc_140003697
0x140003567  mov     rax, rbx
0x14000356a  neg     rax
0x14000356d  lock xadd [r15], rax
0x140003572  mov     rcx, rax
0x140003575  and     rcx, rdx
0x140003578  cmp     rcx, rbx
0x14000357b  jb      loc_14000369F
0x140003581  test    rax, rax
0x140003584  jns     loc_1400034DF
0x14000358a  cmp     qword ptr [r15+8], 0
0x14000358f  jnz     short loc_14000359D
0x140003591  and     rax, rdx
0x140003594  cmp     rax, rbx
0x140003597  jnz     loc_1400034DF
0x14000359d  lea     rcx, [r15+10h]; Event
0x1400035a1  xor     r8d, r8d; Wait
0x1400035a4  xor     edx, edx; Increment
0x1400035a6  call    cs:__imp_KeSetEvent
0x1400035ad  nop     dword ptr [rax+rax+00h]
0x1400035b2  jmp     loc_1400034DF
0x1400035b7  mov     rdi, rax
0x1400035ba  test    rdi, rdi
0x1400035bd  jz      short loc_140003638
0x1400035bf  jmp     short loc_1400035CC
0x1400035c1  xor     rdi, r13
0x1400035c4  and     esi, 1
0x1400035c7  test    rdi, rdi
0x1400035ca  jz      short loc_140003638
0x1400035cc  mov     rdx, rdi
0x1400035cf  mov     rcx, r14
0x1400035d2  call    VsmmpCompareHybridLockContext
0x1400035d7  test    eax, eax
0x1400035d9  jns     short loc_1400035EC
0x1400035db  mov     rax, [rdi]
0x1400035de  test    esi, esi
0x1400035e0  jz      short loc_1400035B7
0x1400035e2  test    rax, rax
0x1400035e5  jz      short loc_1400035B7
0x1400035e7  xor     rdi, rax
0x1400035ea  jmp     short loc_1400035BA
0x1400035ec  jle     loc_14000367D
0x1400035f2  mov     rax, [rdi+8]
0x1400035f6  test    esi, esi
0x1400035f8  jz      short loc_1400035B7
0x1400035fa  test    rax, rax
0x1400035fd  jz      short loc_1400035B7
0x1400035ff  jmp     short loc_1400035E7
0x140003601  lea     rax, [r13+30F0h]
0x140003608  mov     rcx, rax; SpinLock
0x14000360b  mov     [rbp+4Fh+MemoryDescriptorList], rax
0x14000360f  call    cs:__imp_ExAcquireSpinLockExclusive
0x140003616  nop     dword ptr [rax+rax+00h]
0x14000361b  add     r13, 30F8h
0x140003622  mov     [rbp+4Fh+arg_18], al
0x140003625  mov     rsi, [r13+8]
0x140003629  mov     rdi, [r13+0]
0x14000362d  test    sil, 1
0x140003631  jz      short loc_1400035C4
0x140003633  test    rdi, rdi
0x140003636  jnz     short loc_1400035C1
0x140003638  int     2Ch; Windows NT - assertion failure
0x14000363a  mov     rdx, rdi
0x14000363d  mov     rcx, r13
0x140003640  call    cs:__imp_RtlRbRemoveNode
0x140003647  nop     dword ptr [rax+rax+00h]
0x14000364c  movzx   edx, [rbp+4Fh+arg_18]; OldIrql
0x140003650  mov     rcx, [rbp+4Fh+MemoryDescriptorList]; SpinLock
0x140003654  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000365b  nop     dword ptr [rax+rax+00h]
0x140003660  mov     rcx, [rdi+20h]; MemoryDescriptorList
0x140003664  call    cs:__imp_MmUnlockPages
0x14000366b  nop     dword ptr [rax+rax+00h]
0x140003670  mov     rcx, rdi; P
0x140003673  call    VsmmpFreeHybridLockContext
0x140003678  jmp     loc_1400034DA
0x14000367d  test    rdi, rdi
0x140003680  jnz     short loc_14000363A
0x140003682  jmp     short loc_140003638
0x140003684  cmp     r12d, 1
0x140003688  jz      loc_14000354B
0x14000368e  add     r15, 40h ; '@'
0x140003692  jmp     loc_140003552
0x140003697  mov     rax, [r15]
0x14000369a  jmp     loc_140003581
0x14000369f  int     2Ch; Windows NT - assertion failure
0x1400036a1  jmp     loc_140003581
```
