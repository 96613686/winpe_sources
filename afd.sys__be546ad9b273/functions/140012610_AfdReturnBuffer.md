# AfdReturnBuffer

- ea: `0x140012610`
- end: `0x1400129ca`
- name: `AfdReturnBuffer`
- size: `954`
- prototype: `void __fastcall(unsigned __int16 *Entry, PEPROCESS Process)`
- caller_count: `37`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140007350`
- `0x140008210`
- `0x14000a020`
- `0x14000c0d0`
- `0x140010db0`
- `0x140010eb0`
- `0x140011380`
- `0x140011670`
- `0x140013590`
- `0x140014934`
- `0x14001c708`
- `0x14001ceb0`
- `0x14001d524`
- `0x14001f120`
- `0x140022d50`
- `0x1400277f0`
- `0x14002b8b0`
- `0x14002d394`
- `0x140030a68`
- `0x140031d90`
- `0x14003ae50`
- `0x14003ba00`
- `0x14003e410`
- `0x1400404a0`
- `0x1400406dc`
- `0x140041038`
- `0x140041eac`
- `0x1400537b0`
- `0x1400548c0`
- `0x1400553a4`
- `0x1400557d0`
- `0x140055b60`
- `0x140055f50`
- `0x1400562a0`
- `0x140056860`
- `0x140056a44`
- `0x140056d90`

## callees

- `0x140010948`
- `0x140012610`
- `0x140072920`

## import_xrefs

- `ntoskrnl!PsReturnPoolQuota` at `0x14001284b`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400128d9`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400128f7`
- `ntoskrnl!PsReturnPoolQuota` at `0x140012990`
- `ntoskrnl!PsReturnPoolQuota` at `0x14001284b`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400128d9`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400128f7`
- `ntoskrnl!PsReturnPoolQuota` at `0x140012990`
- `ntoskrnl!MmSizeOfMdl` at `0x1400127da`
- `ntoskrnl!MmSizeOfMdl` at `0x1400127da`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001269c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400127b5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400128aa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001269c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400127b5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400128aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126f5`
- `TDI!TdiReturnChainedReceives` at `0x140012932`
- `TDI!TdiReturnChainedReceives` at `0x140012932`

## pseudocode

```c
void __fastcall AfdReturnBuffer(unsigned __int16 *Entry, PEPROCESS Process)
{
  unsigned int v2; // edi
  char *v4; // rbx
  int v5; // esi
  _BYTE *v6; // rsi
  ULONG_PTR v7; // r8
  unsigned __int64 v8; // rdi
  unsigned __int16 v9; // dx
  int v10; // ecx
  unsigned __int16 v11; // ax
  _QWORD *v12; // rcx
  char *v13; // rdi
  char *v14; // rdi
  __int16 v15; // r14
  unsigned int v16; // edx
  char *v17; // rsi
  _QWORD v18[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v19; // [rsp+30h] [rbp-38h]

  v2 = *((_DWORD *)Entry + 18);
  v4 = (char *)Entry;
  if ( v2 != AfdBufferTagSize )
  {
    v5 = Entry[49];
    if ( v5 == (_DWORD)AfdStandardAddressLength && v2 <= (unsigned int)AfdHugeBufferSize )
    {
      if ( v2 == (_DWORD)AfdSmallBufferSize )
      {
        v6 = AfdPplSmallBufferPool;
        v7 = AfdPplSmallBufferSize;
      }
      else if ( v2 == (_DWORD)AfdMediumBufferSize )
      {
        v6 = AfdPplMediumBufferPool;
        v7 = AfdPplMediumBufferSize;
      }
      else if ( v2 == (_DWORD)AfdLargeBufferSize )
      {
        v6 = AfdPplLargeBufferPool;
        v7 = AfdPplLargeBufferSize;
      }
      else
      {
        v6 = AfdPplHugeBufferPool;
        v7 = AfdPplHugeBufferSize;
      }
      if ( (Entry[48] & 0x100) == 0 )
      {
        if ( Process )
          PsReturnPoolQuota(Process, (POOL_TYPE)512, v7);
        *((_WORD *)v4 + 48) |= 0x100u;
      }
      v8 = (unsigned __int64)(unsigned int)(*((_DWORD *)v4 + 23) + 1) << 7;
      if ( !v6[v8 + 176] )
        PplpLazyInitializeLookasideList(v6, &v6[v8 + 64]);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)&v6[v8 + 64], v4);
      return;
    }
    if ( Process )
    {
      v15 = AfdTdiStackSize;
      v16 = ((v2 + 15) & 0xFFFFFFF0)
          + 128
          + ((MmSizeOfMdl(0, *((unsigned int *)Entry + 18)) + 15) & 0xFFFFFFF0)
          + v5
          + (((unsigned __int16)(72 * v15 + 208) + 15) & 0xFFFFFFF0);
      if ( v16 < 0x1000 )
      {
        v16 += (_BYTE)v15 == AfdTdiStackSize ? AfdAlignmentOverhead : AfdBufferAlignment - 16;
        if ( v16 >= 0x1000 )
          v16 = 4096;
      }
      PsReturnPoolQuota(Process, (POOL_TYPE)512, v16);
    }
    v9 = *((_WORD *)v4 + 48);
    v10 = (v9 >> 5) & 3;
    if ( v10 == 1 )
    {
      v4 = (char *)*((_QWORD *)v4 + 13);
    }
    else if ( v10 )
    {
      if ( v10 == 2 )
        v4 = (char *)*((_QWORD *)v4 + 7);
      else
        v4 = (char *)*((_QWORD *)v4 + 14);
    }
    if ( (v9 & 0x80u) != 0 )
      v4 -= *((_QWORD *)v4 - 1);
LABEL_19:
    ExFreePoolWithTag(v4, 0x42646641u);
    return;
  }
  v11 = Entry[48];
  if ( (v11 & 0x10) != 0 )
  {
    v19 = (_QWORD *)*((_QWORD *)Entry + 6);
    v18[1] = 0;
    v12 = (_QWORD *)*v19;
    *v19 = 0;
    *((_WORD *)v4 + 48) &= 0xFFEDu;
    v18[0] = AfdTLDontCareIOCompletion;
    (*(void (__fastcall **)(_QWORD, _QWORD *))(v12[1] + 48LL))(*v12, v18);
  }
  else if ( (v11 & 8) != 0 )
  {
    Entry[48] = v11 & 0xFFF7;
    TdiReturnChainedReceives((PVOID *)Entry + 6, 1u);
  }
  v13 = (char *)*((_QWORD *)v4 + 5);
  if ( v13 == v4 + 104 )
  {
    if ( Process )
      PsReturnPoolQuota(Process, (POOL_TYPE)512, *((unsigned __int16 *)v4 + 49) + 104LL);
    goto LABEL_19;
  }
  if ( v13 )
  {
    v17 = (char *)PplAddressPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v17[176] )
      PplpLazyInitializeLookasideList(PplAddressPool, v17 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v17 + 64), v13);
    *((_QWORD *)v4 + 5) = 0;
  }
  if ( (*((_WORD *)v4 + 48) & 0x100) == 0 )
  {
    if ( Process )
      PsReturnPoolQuota(Process, (POOL_TYPE)512, *((unsigned __int16 *)v4 + 49) + 104LL);
    *((_WORD *)v4 + 48) |= 0x100u;
  }
  v14 = (char *)AfdPplBufferTagPool + 128 * (unsigned __int64)(unsigned int)(*((_DWORD *)v4 + 23) + 1);
  if ( !v14[176] )
    PplpLazyInitializeLookasideList(AfdPplBufferTagPool, v14 + 64);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 64), v4);
}

```

## disassembly

```asm
0x140012610  push    rbx
0x140012612  push    rbp
0x140012613  push    rsi
0x140012614  push    rdi
0x140012615  push    r14
0x140012617  sub     rsp, 40h
0x14001261b  mov     edi, [rcx+48h]
0x14001261e  mov     rbp, rdx
0x140012621  cmp     edi, cs:AfdBufferTagSize
0x140012627  mov     rbx, rcx
0x14001262a  jz      loc_140012716
0x140012630  movzx   esi, word ptr [rcx+62h]
0x140012634  cmp     esi, cs:AfdStandardAddressLength
0x14001263a  jnz     short loc_1400126B4
0x14001263c  cmp     edi, cs:AfdHugeBufferSize
0x140012642  ja      short loc_1400126B4
0x140012644  cmp     edi, cs:AfdSmallBufferSize
0x14001264a  jz      loc_140012703
0x140012650  cmp     edi, cs:AfdMediumBufferSize
0x140012656  jnz     loc_14001285C
0x14001265c  mov     rsi, cs:AfdPplMediumBufferPool
0x140012663  mov     r8, cs:AfdPplMediumBufferSize; Amount
0x14001266a  mov     edi, 100h
0x14001266f  test    [rcx+60h], di
0x140012673  jz      loc_1400128EA
0x140012679  mov     edi, [rbx+5Ch]
0x14001267c  inc     edi
0x14001267e  shl     rdi, 7
0x140012682  movzx   eax, byte ptr [rdi+rsi+0B0h]
0x14001268a  test    al, al
0x14001268c  jz      loc_140012966
0x140012692  lea     rcx, [rdi+40h]
0x140012696  mov     rdx, rbx; Entry
0x140012699  add     rcx, rsi; Lookaside
0x14001269c  call    cs:__imp_ExFreeToLookasideListEx
0x1400126a3  nop     dword ptr [rax+rax+00h]
0x1400126a8  add     rsp, 40h
0x1400126ac  pop     r14
0x1400126ae  pop     rdi
0x1400126af  pop     rsi
0x1400126b0  pop     rbp
0x1400126b1  pop     rbx
0x1400126b2  retn
0x1400126b4  test    rbp, rbp
0x1400126b7  jnz     loc_1400127CD
0x1400126bd  movzx   edx, word ptr [rbx+60h]
0x1400126c1  mov     ecx, edx
0x1400126c3  shr     ecx, 5
0x1400126c6  and     ecx, 3
0x1400126c9  cmp     ecx, 1
0x1400126cc  jz      short loc_1400126E1
0x1400126ce  test    ecx, ecx
0x1400126d0  jz      short loc_1400126E5
0x1400126d2  cmp     ecx, 2
0x1400126d5  jz      loc_14001290C
0x1400126db  mov     rbx, [rbx+70h]
0x1400126df  jmp     short loc_1400126E5
0x1400126e1  mov     rbx, [rbx+68h]
0x1400126e5  test    dl, dl
0x1400126e7  js      loc_1400129C1
0x1400126ed  mov     edx, 42646641h; Tag
0x1400126f2  mov     rcx, rbx; P
0x1400126f5  call    cs:__imp_ExFreePoolWithTag
0x1400126fc  nop     dword ptr [rax+rax+00h]
0x140012701  jmp     short loc_1400126A8
0x140012703  mov     rsi, cs:AfdPplSmallBufferPool
0x14001270a  mov     r8, cs:AfdPplSmallBufferSize
0x140012711  jmp     loc_14001266A
0x140012716  movzx   eax, word ptr [rcx+60h]
0x14001271a  xor     r14d, r14d
0x14001271d  test    al, 10h
0x14001271f  jz      loc_140012915
0x140012725  mov     rax, [rcx+30h]
0x140012729  mov     edx, 0FFEDh
0x14001272e  mov     [rsp+68h+var_38], rax
0x140012733  mov     [rsp+68h+var_40], r14
0x140012738  mov     rcx, [rax]
0x14001273b  mov     [rax], r14
0x14001273e  lea     rax, AfdTLDontCareIOCompletion
0x140012745  and     [rbx+60h], dx
0x140012749  lea     rdx, [rsp+68h+var_48]
0x14001274e  mov     [rsp+68h+var_48], rax
0x140012753  mov     rax, [rcx+8]
0x140012757  mov     rcx, [rcx]
0x14001275a  mov     rax, [rax+30h]
0x14001275e  call    _guard_dispatch_icall
0x140012763  mov     rdi, [rbx+28h]
0x140012767  lea     rax, [rbx+68h]
0x14001276b  cmp     rdi, rax
0x14001276e  jz      loc_1400128BF
0x140012774  test    rdi, rdi
0x140012777  jnz     loc_14001287B
0x14001277d  mov     edi, 100h
0x140012782  test    [rbx+60h], di
0x140012786  jz      loc_14001297A
0x14001278c  mov     edi, [rbx+5Ch]
0x14001278f  mov     rcx, cs:AfdPplBufferTagPool
0x140012796  inc     edi
0x140012798  shl     rdi, 7
0x14001279c  add     rdi, rcx
0x14001279f  movzx   eax, byte ptr [rdi+0B0h]
0x1400127a6  test    al, al
0x1400127a8  jz      loc_1400129A5
0x1400127ae  mov     rdx, rbx; Entry
0x1400127b1  lea     rcx, [rdi+40h]; Lookaside
0x1400127b5  call    cs:__imp_ExFreeToLookasideListEx
0x1400127bc  nop     dword ptr [rax+rax+00h]
0x1400127c1  add     rsp, 40h
0x1400127c5  pop     r14
0x1400127c7  pop     rdi
0x1400127c8  pop     rsi
0x1400127c9  pop     rbp
0x1400127ca  pop     rbx
0x1400127cb  retn
0x1400127cd  movsx   r14d, cs:AfdTdiStackSize
0x1400127d5  mov     rdx, rdi; Length
0x1400127d8  xor     ecx, ecx; Base
0x1400127da  call    cs:__imp_MmSizeOfMdl
0x1400127e1  nop     dword ptr [rax+rax+00h]
0x1400127e6  movzx   ecx, r14w
0x1400127ea  shl     cx, 3
0x1400127ee  lea     r8d, [rax+0Fh]
0x1400127f2  mov     eax, 0D0h
0x1400127f7  and     r8d, 0FFFFFFF0h
0x1400127fb  lea     edx, [rcx+r14]
0x1400127ff  mov     ecx, 1000h
0x140012804  shl     dx, 3
0x140012808  add     dx, ax
0x14001280b  lea     eax, [rdi+0Fh]
0x14001280e  movzx   edx, dx
0x140012811  and     eax, 0FFFFFFF0h
0x140012814  add     edx, 0Fh
0x140012817  sub     eax, 0FFFFFF80h
0x14001281a  and     edx, 0FFFFFFF0h
0x14001281d  add     edx, esi
0x14001281f  add     edx, r8d
0x140012822  add     edx, eax
0x140012824  cmp     edx, ecx
0x140012826  jnb     short loc_140012840
0x140012828  cmp     r14b, cs:AfdTdiStackSize
0x14001282f  jnz     loc_140012956
0x140012835  add     edx, cs:AfdAlignmentOverhead
0x14001283b  cmp     edx, ecx
0x14001283d  cmovnb  edx, ecx
0x140012840  mov     r8d, edx; Amount
0x140012843  mov     rcx, rbp; Process
0x140012846  mov     edx, 200h; PoolType
0x14001284b  call    cs:__imp_PsReturnPoolQuota
0x140012852  nop     dword ptr [rax+rax+00h]
0x140012857  jmp     loc_1400126BD
0x14001285c  cmp     edi, cs:AfdLargeBufferSize
0x140012862  jnz     loc_140012943
0x140012868  mov     rsi, cs:AfdPplLargeBufferPool
0x14001286f  mov     r8, cs:AfdPplLargeBufferSize
0x140012876  jmp     loc_14001266A
0x14001287b  mov     eax, gs:1A4h
0x140012883  mov     rcx, cs:PplAddressPool
0x14001288a  lea     esi, [rax+1]
0x14001288d  shl     rsi, 7
0x140012891  add     rsi, rcx
0x140012894  movzx   eax, byte ptr [rsi+0B0h]
0x14001289b  test    al, al
0x14001289d  jz      loc_1400129B3
0x1400128a3  mov     rdx, rdi; Entry
0x1400128a6  lea     rcx, [rsi+40h]; Lookaside
0x1400128aa  call    cs:__imp_ExFreeToLookasideListEx
0x1400128b1  nop     dword ptr [rax+rax+00h]
0x1400128b6  mov     [rbx+28h], r14
0x1400128ba  jmp     loc_14001277D
0x1400128bf  test    rbp, rbp
0x1400128c2  jz      loc_1400126ED
0x1400128c8  movzx   r8d, word ptr [rbx+62h]
0x1400128cd  mov     edx, 200h; PoolType
0x1400128d2  add     r8, 68h ; 'h'; Amount
0x1400128d6  mov     rcx, rbp; Process
0x1400128d9  call    cs:__imp_PsReturnPoolQuota
0x1400128e0  nop     dword ptr [rax+rax+00h]
0x1400128e5  jmp     loc_1400126ED
0x1400128ea  test    rbp, rbp
0x1400128ed  jz      short loc_140012903
0x1400128ef  mov     edx, 200h; PoolType
0x1400128f4  mov     rcx, rbp; Process
0x1400128f7  call    cs:__imp_PsReturnPoolQuota
0x1400128fe  nop     dword ptr [rax+rax+00h]
0x140012903  or      [rbx+60h], di
0x140012907  jmp     loc_140012679
0x14001290c  mov     rbx, [rbx+38h]
0x140012910  jmp     loc_1400126E5
0x140012915  test    al, 8
0x140012917  jz      loc_140012763
0x14001291d  mov     ecx, 0FFF7h
0x140012922  mov     edx, 1; NumberOfTsdus
0x140012927  and     ax, cx
0x14001292a  lea     rcx, [rbx+30h]; TsduDescriptors
0x14001292e  mov     [rbx+60h], ax
0x140012932  call    cs:__imp_TdiReturnChainedReceives
0x140012939  nop     dword ptr [rax+rax+00h]
0x14001293e  jmp     loc_140012763
0x140012943  mov     rsi, cs:AfdPplHugeBufferPool
0x14001294a  mov     r8, cs:AfdPplHugeBufferSize
0x140012951  jmp     loc_14001266A
0x140012956  mov     eax, cs:AfdBufferAlignment
0x14001295c  add     eax, 0FFFFFFF0h
0x14001295f  add     edx, eax
0x140012961  jmp     loc_14001283B
0x140012966  lea     rdx, [rdi+40h]
0x14001296a  mov     rcx, rsi
0x14001296d  add     rdx, rsi
0x140012970  call    PplpLazyInitializeLookasideList
0x140012975  jmp     loc_140012692
0x14001297a  test    rbp, rbp
0x14001297d  jz      short loc_14001299C
0x14001297f  movzx   r8d, word ptr [rbx+62h]
0x140012984  mov     edx, 200h; PoolType
0x140012989  add     r8, 68h ; 'h'; Amount
0x14001298d  mov     rcx, rbp; Process
0x140012990  call    cs:__imp_PsReturnPoolQuota
0x140012997  nop     dword ptr [rax+rax+00h]
0x14001299c  or      [rbx+60h], di
0x1400129a0  jmp     loc_14001278C
0x1400129a5  lea     rdx, [rdi+40h]
0x1400129a9  call    PplpLazyInitializeLookasideList
0x1400129ae  jmp     loc_1400127AE
0x1400129b3  lea     rdx, [rsi+40h]
0x1400129b7  call    PplpLazyInitializeLookasideList
0x1400129bc  jmp     loc_1400128A3
0x1400129c1  sub     rbx, [rbx-8]
0x1400129c5  jmp     loc_1400126ED
```
