# FileProvReadCompressedOnNewStack

- ea: `0x1400382b0`
- end: `0x14003875a`
- name: `FileProvReadCompressedOnNewStack`
- size: `1194`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009600`

## callees

- `0x140004400`
- `0x140007a30`
- `0x140009aa8`
- `0x14000d3b8`
- `0x14000fb60`
- `0x140010078`
- `0x140011194`
- `0x1400382b0`
- `0x140038760`
- `0x140038b10`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140038433`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140038433`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140038574`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140038574`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038505`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038505`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003855d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003855d`

## pseudocode

```c
__int64 __fastcall FileProvReadCompressedOnNewStack(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rbp
  __int64 v4; // r14
  __int64 *v5; // r13
  __int64 v6; // rcx
  int Compressed; // edi
  __int64 *v8; // r15
  __int64 v9; // r15
  __int64 v10; // r8
  __int64 v11; // r12
  unsigned __int64 v12; // rbp
  int v13; // edi
  int v14; // ecx
  int v15; // edx
  SIZE_T v16; // rbx
  char *v17; // rax
  PVOID v18; // rbp
  char *PoolWithTag; // rdi
  __int64 v20; // rdx
  __int64 v22; // rcx
  SIZE_T NumberOfBytes; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v24; // [rsp+88h] [rbp+10h] BYREF
  __int64 ChunkOffset; // [rsp+90h] [rbp+18h] BYREF
  LARGE_INTEGER v26; // [rsp+98h] [rbp+20h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  v3 = *(_QWORD *)(a1 + 24);
  v4 = *(unsigned int *)(a1 + 48);
  v5 = FileProvCompressionScheme(v1);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  *(_DWORD *)(a1 + 52) = 0;
  v6 = *(_QWORD *)(v1 + 8);
  if ( v3 >= v6 )
    return 0;
  if ( (*(_DWORD *)v1 & 1) != 0 )
  {
    Compressed = 0;
    v8 = (__int64 *)(v1 + 32);
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    v8 = (__int64 *)(v1 + 32);
    Compressed = FileProvBuildChunkTable(a1, v1, (volatile signed __int64 *)(v1 + 32));
    if ( Compressed < 0 )
      goto LABEL_19;
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v1 - 64) + 32LL));
    v22 = *(_QWORD *)(v1 - 64);
    *(_DWORD *)v1 |= 1u;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v22 + 32));
    v6 = *(_QWORD *)(v1 + 8);
  }
  v9 = *v8;
  if ( v4 + v3 > v6 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)v4,
        v6 - v3);
    LODWORD(v4) = *(_DWORD *)(v1 + 8) - v3;
  }
  if ( (_DWORD)v4 )
  {
    v26.QuadPart = 0;
    LODWORD(NumberOfBytes) = 0;
    v24 = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)v4);
    v10 = *(unsigned int *)v5;
    v11 = v3 / v10;
    v12 = (-v10 & (v3 - 1 + v10 + (unsigned __int64)(unsigned int)v4)) / v10;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)v11,
        v12);
    if ( v9 )
    {
      ChunkOffset = FileProvGetChunkOffset(v9, (unsigned int)v11);
      v13 = ChunkOffset;
      v14 = FileProvGetChunkOffset(v9, (unsigned int)v12) - v13;
    }
    else
    {
      v14 = *(_DWORD *)(v1 + 16);
      ChunkOffset = 0;
    }
    v15 = v14 + 4;
    if ( *(_DWORD *)(v1 + 4) != 1 )
      v15 = v14;
    FileProvGetAlignedSizes(
      (unsigned int)&ChunkOffset,
      v15,
      v10,
      (unsigned int)&v26,
      (__int64)&NumberOfBytes,
      (__int64)&v24);
    v16 = (unsigned int)NumberOfBytes;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)NumberOfBytes,
        *((_DWORD *)v5 + 80));
    if ( (unsigned int)v16 > *((_DWORD *)v5 + 80) )
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v16, 0x44527066u);
      if ( PoolWithTag )
      {
        v18 = 0;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_3b099794e4b93327e327da255c047df6_Traceguids,
            (unsigned int)v16);
        goto LABEL_17;
      }
      Compressed = -1073741670;
    }
    else
    {
      v17 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v5 + 3);
      v18 = v17;
      if ( v17 )
      {
        PoolWithTag = v17;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
LABEL_17:
        v20 = v24;
        *(_QWORD *)(a1 + 152) = FileProvReadCompressedOnNewStackExtendedCompletion;
        *(_QWORD *)(a1 + 160) = v9;
        *(_DWORD *)(a1 + 176) = v11;
        *(_QWORD *)(a1 + 184) = v18;
        *(_QWORD *)(a1 + 168) = &PoolWithTag[v20];
        *(_QWORD *)(a1 + 192) = PoolWithTag;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice);
        Compressed = FileProvReadCompressed(v26, PoolWithTag, (unsigned int)v16, a1 - 24);
        goto LABEL_19;
      }
      Compressed = -1073741670;
    }
  }
LABEL_19:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      WPP_3b099794e4b93327e327da255c047df6_Traceguids,
      (unsigned int)Compressed);
  return (unsigned int)Compressed;
}

```

## disassembly

```asm
0x1400382b0  push    rbx
0x1400382b2  push    rbp
0x1400382b3  push    rsi
0x1400382b4  push    r13
0x1400382b6  push    r14
0x1400382b8  sub     rsp, 50h
0x1400382bc  mov     rbx, [rcx+20h]
0x1400382c0  mov     rsi, rcx
0x1400382c3  mov     rbp, [rcx+18h]
0x1400382c7  mov     r14d, [rcx+30h]
0x1400382cb  mov     rcx, rbx
0x1400382ce  call    FileProvCompressionScheme
0x1400382d3  mov     r13, rax
0x1400382d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400382dd  mov     edx, [rcx+2Ch]
0x1400382e0  test    dl, 20h
0x1400382e3  jnz     loc_1400385D7
0x1400382e9  xor     r9d, r9d
0x1400382ec  mov     [rsi+34h], r9d
0x1400382f0  mov     rcx, [rbx+8]
0x1400382f4  cmp     rbp, rcx
0x1400382f7  jge     loc_1400385FB
0x1400382fd  mov     eax, [rbx]
0x1400382ff  mov     [rsp+78h+var_30], rdi
0x140038304  mov     [rsp+78h+var_40], r15
0x140038309  test    al, 1
0x14003830b  jz      loc_140038527
0x140038311  mov     edi, r9d
0x140038314  lea     r15, [rbx+20h]
0x140038318  mov     r15, [r15]
0x14003831b  lea     rax, [r14+rbp]
0x14003831f  cmp     rax, rcx
0x140038322  jg      loc_140038626
0x140038328  test    r14d, r14d
0x14003832b  jz      loc_1400384CC
0x140038331  mov     [rsp+78h+var_38], r12
0x140038336  mov     [rsp+78h+arg_18], r9
0x14003833e  mov     dword ptr [rsp+78h+NumberOfBytes], r9d
0x140038346  mov     [rsp+78h+arg_8], r9d
0x14003834e  mov     rcx, cs:WPP_GLOBAL_Control
0x140038355  mov     eax, [rcx+2Ch]
0x140038358  test    al, 20h
0x14003835a  jnz     loc_140038669
0x140038360  mov     r8d, [r13+0]
0x140038364  mov     rax, rbp
0x140038367  cqo
0x140038369  dec     rbp
0x14003836c  idiv    r8
0x14003836f  mov     ecx, r8d
0x140038372  xor     edx, edx
0x140038374  mov     r12, rax
0x140038377  neg     rcx
0x14003837a  mov     eax, r14d
0x14003837d  add     rax, r8
0x140038380  add     rax, rbp
0x140038383  and     rax, rcx
0x140038386  div     r8
0x140038389  mov     rbp, rax
0x14003838c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038393  mov     edx, [rcx+2Ch]
0x140038396  test    dl, 20h
0x140038399  jnz     loc_140038693
0x14003839f  test    r15, r15
0x1400383a2  jz      loc_1400385C7
0x1400383a8  mov     edx, r12d
0x1400383ab  mov     rcx, r15
0x1400383ae  call    FileProvGetChunkOffset
0x1400383b3  mov     edx, ebp
0x1400383b5  mov     [rsp+78h+arg_10], rax
0x1400383bd  mov     rcx, r15
0x1400383c0  mov     rdi, rax
0x1400383c3  call    FileProvGetChunkOffset
0x1400383c8  mov     rcx, rax
0x1400383cb  sub     ecx, edi
0x1400383cd  cmp     dword ptr [rbx+4], 1
0x1400383d1  lea     edx, [rcx+4]
0x1400383d4  lea     rax, [rsp+78h+arg_8]
0x1400383dc  mov     [rsp+78h+var_50], rax
0x1400383e1  lea     r9, [rsp+78h+arg_18]
0x1400383e9  cmovnz  edx, ecx
0x1400383ec  lea     rax, [rsp+78h+NumberOfBytes]
0x1400383f4  lea     rcx, [rsp+78h+arg_10]
0x1400383fc  mov     [rsp+78h+var_58], rax
0x140038401  call    FileProvGetAlignedSizes
0x140038406  mov     rcx, cs:WPP_GLOBAL_Control
0x14003840d  mov     ebx, dword ptr [rsp+78h+NumberOfBytes]
0x140038414  mov     eax, [rcx+2Ch]
0x140038417  test    al, 20h
0x140038419  jnz     loc_1400386C1
0x14003841f  cmp     ebx, [r13+140h]
0x140038426  ja      loc_1400384F7
0x14003842c  lea     rcx, [r13+180h]; Lookaside
0x140038433  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003843a  nop     dword ptr [rax+rax+00h]
0x14003843f  mov     rbp, rax
0x140038442  test    rax, rax
0x140038445  jz      loc_140038520
0x14003844b  mov     rdi, rax
0x14003844e  mov     rcx, cs:WPP_GLOBAL_Control
0x140038455  mov     eax, [rcx+2Ch]
0x140038458  test    al, 20h
0x14003845a  jnz     loc_1400386F3
0x140038460  mov     edx, [rsp+78h+arg_8]
0x140038467  lea     rax, FileProvReadCompressedOnNewStackExtendedCompletion
0x14003846e  mov     [rsi+98h], rax
0x140038475  mov     [rsi+0A0h], r15
0x14003847c  mov     [rsi+0B0h], r12d
0x140038483  lea     r9, [rdi+rdx]
0x140038487  mov     [rsi+0B8h], rbp
0x14003848e  mov     [rsi+0A8h], r9
0x140038495  mov     [rsi+0C0h], rdi
0x14003849c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400384a3  mov     eax, [rcx+2Ch]
0x1400384a6  test    al, 20h
0x1400384a8  jnz     loc_140038717
0x1400384ae  mov     rcx, [rsp+78h+arg_18]
0x1400384b6  lea     r9, [rsi-18h]
0x1400384ba  mov     r8d, ebx
0x1400384bd  mov     rdx, rdi
0x1400384c0  call    FileProvReadCompressed
0x1400384c5  mov     edi, eax
0x1400384c7  mov     r12, [rsp+78h+var_38]
0x1400384cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400384d3  mov     r15, [rsp+78h+var_40]
0x1400384d8  mov     eax, [rcx+2Ch]
0x1400384db  test    al, 20h
0x1400384dd  jnz     loc_140038733
0x1400384e3  mov     eax, edi
0x1400384e5  mov     rdi, [rsp+78h+var_30]
0x1400384ea  add     rsp, 50h
0x1400384ee  pop     r14
0x1400384f0  pop     r13
0x1400384f2  pop     rsi
0x1400384f3  pop     rbp
0x1400384f4  pop     rbx
0x1400384f5  retn
0x1400384f7  mov     rdx, rbx; NumberOfBytes
0x1400384fa  mov     ecx, 1; PoolType
0x1400384ff  mov     r8d, 44527066h; Tag
0x140038505  call    cs:__imp_ExAllocatePoolWithTag
0x14003850c  nop     dword ptr [rax+rax+00h]
0x140038511  mov     rdi, rax
0x140038514  test    rax, rax
0x140038517  jnz     short loc_14003858C
0x140038519  mov     edi, 0C000009Ah
0x14003851e  jmp     short loc_1400384C7
0x140038520  mov     edi, 0C000009Ah
0x140038525  jmp     short loc_1400384C7
0x140038527  mov     rcx, cs:WPP_GLOBAL_Control
0x14003852e  mov     eax, [rcx+2Ch]
0x140038531  test    al, 20h
0x140038533  jnz     loc_140038602
0x140038539  lea     r15, [rbx+20h]
0x14003853d  mov     rdx, rbx
0x140038540  mov     r8, r15
0x140038543  mov     rcx, rsi
0x140038546  call    FileProvBuildChunkTable
0x14003854b  mov     edi, eax
0x14003854d  test    eax, eax
0x14003854f  js      loc_1400384CC
0x140038555  mov     rcx, [rbx-40h]
0x140038559  add     rcx, 20h ; ' '; FastMutex
0x14003855d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140038564  nop     dword ptr [rax+rax+00h]
0x140038569  mov     rcx, [rbx-40h]
0x14003856d  or      dword ptr [rbx], 1
0x140038570  add     rcx, 20h ; ' '; FastMutex
0x140038574  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003857b  nop     dword ptr [rax+rax+00h]
0x140038580  mov     rcx, [rbx+8]
0x140038584  xor     r9d, r9d
0x140038587  jmp     loc_140038318
0x14003858c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038593  xor     ebp, ebp
0x140038595  mov     eax, [rcx+2Ch]
0x140038598  test    al, 20h
0x14003859a  jz      loc_140038460
0x1400385a0  cmp     byte ptr [rcx+29h], 5
0x1400385a4  jb      loc_140038460
0x1400385aa  mov     rcx, [rcx+18h]
0x1400385ae  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400385b5  mov     edx, 1Ch
0x1400385ba  mov     r9d, ebx
0x1400385bd  call    WPP_SF_d
0x1400385c2  jmp     loc_140038460
0x1400385c7  mov     ecx, [rbx+10h]
0x1400385ca  mov     [rsp+78h+arg_10], r9
0x1400385d2  jmp     loc_1400383CD
0x1400385d7  cmp     byte ptr [rcx+29h], 4
0x1400385db  jb      loc_1400382E9
0x1400385e1  mov     rcx, [rcx+18h]
0x1400385e5  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400385ec  mov     edx, 16h
0x1400385f1  call    WPP_SF_
0x1400385f6  jmp     loc_1400382E9
0x1400385fb  xor     eax, eax
0x1400385fd  jmp     loc_1400384EA
0x140038602  cmp     byte ptr [rcx+29h], 5
0x140038606  jb      loc_140038539
0x14003860c  mov     rcx, [rcx+18h]
0x140038610  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038617  mov     edx, 17h
0x14003861c  call    WPP_SF_
0x140038621  jmp     loc_140038539
0x140038626  mov     r10, cs:WPP_GLOBAL_Control
0x14003862d  mov     eax, [r10+2Ch]
0x140038631  test    al, 20h
0x140038633  jz      short loc_14003865D
0x140038635  cmp     byte ptr [r10+29h], 5
0x14003863a  jb      short loc_14003865D
0x14003863c  sub     ecx, ebp
0x14003863e  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038645  mov     dword ptr [rsp+78h+var_58], ecx
0x140038649  mov     edx, 18h
0x14003864e  mov     rcx, [r10+18h]
0x140038652  mov     r9d, r14d
0x140038655  call    WPP_SF_dd
0x14003865a  xor     r9d, r9d
0x14003865d  mov     r14d, [rbx+8]
0x140038661  sub     r14d, ebp
0x140038664  jmp     loc_140038328
0x140038669  cmp     byte ptr [rcx+29h], 5
0x14003866d  jb      loc_140038360
0x140038673  mov     rcx, [rcx+18h]
0x140038677  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x14003867e  mov     edx, 19h
0x140038683  mov     r9d, r14d
0x140038686  call    WPP_SF_d
0x14003868b  xor     r9d, r9d
0x14003868e  jmp     loc_140038360
0x140038693  cmp     byte ptr [rcx+29h], 5
0x140038697  jb      loc_14003839F
0x14003869d  mov     rcx, [rcx+18h]
0x1400386a1  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400386a8  mov     r9d, r12d
0x1400386ab  mov     dword ptr [rsp+78h+var_58], ebp
0x1400386af  mov     edx, 1Ah
0x1400386b4  call    WPP_SF_dd
0x1400386b9  xor     r9d, r9d
0x1400386bc  jmp     loc_14003839F
0x1400386c1  cmp     byte ptr [rcx+29h], 5
0x1400386c5  jb      loc_14003841F
0x1400386cb  mov     eax, [r13+140h]
0x1400386d2  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400386d9  mov     rcx, [rcx+18h]
0x1400386dd  mov     edx, 1Bh
0x1400386e2  mov     r9d, ebx
0x1400386e5  mov     dword ptr [rsp+78h+var_58], eax
0x1400386e9  call    WPP_SF_dd
0x1400386ee  jmp     loc_14003841F
0x1400386f3  cmp     byte ptr [rcx+29h], 5
0x1400386f7  jb      loc_140038460
0x1400386fd  mov     rcx, [rcx+18h]
0x140038701  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038708  mov     edx, 1Dh
0x14003870d  call    WPP_SF_
0x140038712  jmp     loc_140038460
0x140038717  cmp     byte ptr [rcx+29h], 5
0x14003871b  jb      loc_1400384AE
0x140038721  mov     rcx, [rcx+18h]
0x140038725  mov     dword ptr [rsp+78h+var_58], edx
0x140038729  call    WPP_SF_qD
0x14003872e  jmp     loc_1400384AE
0x140038733  cmp     byte ptr [rcx+29h], 4
0x140038737  jb      loc_1400384E3
0x14003873d  mov     rcx, [rcx+18h]
0x140038741  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038748  mov     edx, 1Fh
0x14003874d  mov     r9d, edi
0x140038750  call    WPP_SF_d
0x140038755  jmp     loc_1400384E3
```
