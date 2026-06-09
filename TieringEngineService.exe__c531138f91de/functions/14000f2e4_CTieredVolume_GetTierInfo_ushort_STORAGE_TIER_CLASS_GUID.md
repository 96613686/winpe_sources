# CTieredVolume::GetTierInfo(ushort *,_STORAGE_TIER_CLASS *,_GUID *)

- ea: `0x14000f2e4`
- end: `0x14000f5f3`
- name: `?GetTierInfo@CTieredVolume@@QEAAJPEAGPEAW4_STORAGE_TIER_CLASS@@PEAU_GUID@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned __int16 *, enum _STORAGE_TIER_CLASS *, struct _GUID *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140039fd0`
- `0x14003aa90`
- `0x14003b070`

## callees

- `0x140004aa8`
- `0x14000b7f8`
- `0x14000ccc0`
- `0x14000f2e4`
- `0x1400127dc`
- `0x140017d98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000f4aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000f57e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000f4aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000f57e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000f3de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000f3de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000f474`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000f474`

## pseudocode

```c
__int64 __fastcall CTieredVolume::GetTierInfo(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        enum _STORAGE_TIER_CLASS *a3,
        struct _GUID *a4)
{
  char v7; // di
  __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned int v10; // ebx
  unsigned __int64 v11; // r13
  int v12; // eax
  unsigned __int64 cchCount2; // r13
  _QWORD *Ptr; // rdx
  __int64 v15; // r12
  __int64 v16; // rcx
  _WORD *v17; // rax
  unsigned int v18; // edi
  _QWORD *v21; // [rsp+98h] [rbp+20h]

  v7 = 0;
  if ( a3 )
    *a3 = StorageTierClassUnspecified;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
    goto LABEL_47;
  }
  v8 = 256;
  v9 = a2;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
  {
LABEL_47:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        248,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (_DWORD)this + 672,
        v10);
    }
    return v10;
  }
  v11 = (2 * (256 - v8)) & -(__int64)(v8 != 0);
  v12 = CTieredVolume::ReferenceVolume((CTieredVolume *)this, 0);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        249,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        LODWORD(this[16].Ptr),
        v12);
    }
    return v10;
  }
  cchCount2 = v11 >> 1;
  AcquireSRWLockShared(this + 3);
  Ptr = this[4].Ptr;
  if ( Ptr )
  {
    while ( 1 )
    {
      v15 = Ptr[2];
      if ( v15 == -4 )
        break;
      v16 = 256;
      v17 = (_WORD *)(v15 + 4);
      do
      {
        if ( !*v17 )
          break;
        ++v17;
        --v16;
      }
      while ( v16 );
      v18 = v16 == 0 ? 0x80070057 : 0;
      if ( !v16 )
        goto LABEL_38;
      v21 = (_QWORD *)*Ptr;
      if ( CompareStringW(
             0x400u,
             1u,
             (PCNZWCH)(v15 + 4),
             ((2 * (256 - v16)) & (unsigned __int64)-(__int64)(v16 != 0)) >> 1,
             a2,
             cchCount2) == 2 )
      {
        if ( a3 )
          *a3 = *(enum _STORAGE_TIER_CLASS *)v15;
        if ( a4 )
          *a4 = *(struct _GUID *)(v15 + 516);
        v7 = 1;
        goto LABEL_24;
      }
      Ptr = v21;
      if ( !v21 )
      {
        v7 = 0;
        goto LABEL_24;
      }
    }
    v18 = -2147024809;
LABEL_38:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        250,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (_DWORD)this + 672,
        87);
    }
    if ( this != (RTL_SRWLOCK *)-24LL )
      ReleaseSRWLockShared(this + 3);
  }
  else
  {
LABEL_24:
    if ( this != (RTL_SRWLOCK *)-24LL )
      ReleaseSRWLockShared(this + 3);
    if ( v7 )
    {
      v18 = 0;
    }
    else
    {
      v18 = -2138898429;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SZd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&this[84]);
      }
    }
  }
  CTieredVolume::DereferenceVolume((CTieredVolume *)this);
  return v18;
}

```

## disassembly

```asm
0x14000f2e4  mov     [rsp+arg_0], rbx
0x14000f2e9  mov     [rsp+arg_8], rdx
0x14000f2ee  push    rbp
0x14000f2ef  push    rsi
0x14000f2f0  push    rdi
0x14000f2f1  push    r12
0x14000f2f3  push    r13
0x14000f2f5  push    r14
0x14000f2f7  push    r15
0x14000f2f9  sub     rsp, 40h
0x14000f2fd  mov     r14, r9
0x14000f300  mov     r15, r8
0x14000f303  mov     r12, rdx
0x14000f306  mov     rbp, rcx
0x14000f309  xor     edi, edi
0x14000f30b  test    r8, r8
0x14000f30e  jz      short loc_14000F313
0x14000f310  mov     [r8], edi
0x14000f313  test    r14, r14
0x14000f316  jz      short loc_14000F31F
0x14000f318  xorps   xmm0, xmm0
0x14000f31b  movups  xmmword ptr [r9], xmm0
0x14000f31f  test    r12, r12
0x14000f322  jz      loc_14000F595
0x14000f328  mov     edx, 100h
0x14000f32d  mov     ecx, edx
0x14000f32f  mov     rax, r12
0x14000f332  cmp     [rax], di
0x14000f335  jz      short loc_14000F341
0x14000f337  add     rax, 2
0x14000f33b  sub     rcx, 1
0x14000f33f  jnz     short loc_14000F332
0x14000f341  mov     rax, rcx
0x14000f344  neg     rax
0x14000f347  sbb     ebx, ebx
0x14000f349  not     ebx
0x14000f34b  mov     esi, 80070057h
0x14000f350  and     ebx, esi
0x14000f352  test    rcx, rcx
0x14000f355  jz      loc_14000F59A
0x14000f35b  mov     rax, rdx
0x14000f35e  sub     rax, rcx
0x14000f361  add     rax, rax
0x14000f364  neg     rcx
0x14000f367  sbb     r13, r13
0x14000f36a  and     r13, rax
0x14000f36d  xor     edx, edx; bool
0x14000f36f  mov     rcx, rbp; this
0x14000f372  call    ?ReferenceVolume@CTieredVolume@@QEAAJ_N@Z; CTieredVolume::ReferenceVolume(bool)
0x14000f377  mov     ebx, eax
0x14000f379  test    eax, eax
0x14000f37b  jns     short loc_14000F3CF
0x14000f37d  lea     rcx, WPP_GLOBAL_Control
0x14000f384  mov     r10, cs:WPP_GLOBAL_Control
0x14000f38b  cmp     r10, rcx
0x14000f38e  jz      loc_14000F5D9
0x14000f394  test    byte ptr [r10+1Ch], 1
0x14000f399  jz      loc_14000F5D9
0x14000f39f  cmp     byte ptr [r10+19h], 2
0x14000f3a4  jb      loc_14000F5D9
0x14000f3aa  mov     edx, 0F9h
0x14000f3af  mov     dword ptr [rsp+78h+lpString2], eax
0x14000f3b3  mov     r9d, [rbp+80h]
0x14000f3ba  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000f3c1  mov     rcx, [r10+10h]
0x14000f3c5  call    WPP_SF_Dd
0x14000f3ca  jmp     loc_14000F5D9
0x14000f3cf  shr     r13, 1
0x14000f3d2  lea     rbx, [rbp+18h]
0x14000f3d6  mov     [rsp+78h+var_48], rbx
0x14000f3db  mov     rcx, rbx; SRWLock
0x14000f3de  call    cs:__imp_AcquireSRWLockShared
0x14000f3e4  nop
0x14000f3e5  mov     rdx, [rbp+20h]
0x14000f3e9  xor     r9d, r9d
0x14000f3ec  test    rdx, rdx
0x14000f3ef  jz      loc_14000F4A2
0x14000f3f5  mov     r12, [rdx+10h]
0x14000f3f9  lea     r8, [r12+4]; lpString1
0x14000f3fe  test    r8, r8
0x14000f401  jz      loc_14000F534
0x14000f407  mov     r10d, 100h
0x14000f40d  mov     ecx, r10d
0x14000f410  mov     rax, r8
0x14000f413  cmp     [rax], r9w
0x14000f417  jz      short loc_14000F423
0x14000f419  add     rax, 2
0x14000f41d  sub     rcx, 1
0x14000f421  jnz     short loc_14000F413
0x14000f423  mov     rax, rcx
0x14000f426  neg     rax
0x14000f429  sbb     edi, edi
0x14000f42b  not     edi
0x14000f42d  and     edi, esi
0x14000f42f  test    rcx, rcx
0x14000f432  jz      loc_14000F530
0x14000f438  mov     rdx, [rdx]
0x14000f43b  mov     [rsp+78h+arg_18], rdx
0x14000f443  mov     rax, r10
0x14000f446  sub     rax, rcx
0x14000f449  add     rax, rax
0x14000f44c  neg     rcx
0x14000f44f  sbb     r9, r9
0x14000f452  and     r9, rax
0x14000f455  shr     r9, 1; cchCount1
0x14000f458  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x14000f45d  mov     rax, [rsp+78h+arg_8]
0x14000f465  mov     [rsp+78h+lpString2], rax; lpString2
0x14000f46a  mov     edx, 1; dwCmpFlags
0x14000f46f  mov     ecx, 400h; Locale
0x14000f474  call    cs:__imp_CompareStringW
0x14000f47a  xor     r9d, r9d
0x14000f47d  cmp     eax, 2
0x14000f480  jz      loc_14000F509
0x14000f486  mov     rdx, [rsp+78h+arg_18]
0x14000f48e  test    rdx, rdx
0x14000f491  jnz     loc_14000F3F5
0x14000f497  mov     dil, r9b
0x14000f49a  mov     r12, [rsp+78h+arg_8]
0x14000f4a2  test    rbx, rbx
0x14000f4a5  jz      short loc_14000F4B3
0x14000f4a7  mov     rcx, rbx; SRWLock
0x14000f4aa  call    cs:__imp_ReleaseSRWLockShared
0x14000f4b0  xor     r9d, r9d
0x14000f4b3  test    dil, dil
0x14000f4b6  jnz     loc_14000F586
0x14000f4bc  mov     edi, 80830003h
0x14000f4c1  lea     rcx, WPP_GLOBAL_Control
0x14000f4c8  mov     rdx, cs:WPP_GLOBAL_Control
0x14000f4cf  cmp     rdx, rcx
0x14000f4d2  jz      loc_14000F589
0x14000f4d8  test    byte ptr [rdx+1Ch], 1
0x14000f4dc  jz      loc_14000F589
0x14000f4e2  cmp     byte ptr [rdx+19h], 2
0x14000f4e6  jb      loc_14000F589
0x14000f4ec  lea     rax, [rbp+2A0h]
0x14000f4f3  mov     [rsp+78h+lpString2], rax; __int64
0x14000f4f8  mov     r9, r12
0x14000f4fb  mov     rcx, [rdx+10h]; LoggerHandle
0x14000f4ff  call    WPP_SF_SZd
0x14000f504  jmp     loc_14000F589
0x14000f509  test    r15, r15
0x14000f50c  jz      short loc_14000F515
0x14000f50e  mov     eax, [r12]
0x14000f512  mov     [r15], eax
0x14000f515  test    r14, r14
0x14000f518  jz      short loc_14000F528
0x14000f51a  movups  xmm0, xmmword ptr [r12+204h]
0x14000f523  movdqu  xmmword ptr [r14], xmm0
0x14000f528  mov     dil, 1
0x14000f52b  jmp     loc_14000F49A
0x14000f530  mov     esi, edi
0x14000f532  jmp     short loc_14000F536
0x14000f534  mov     edi, esi
0x14000f536  lea     rcx, WPP_GLOBAL_Control
0x14000f53d  mov     rax, cs:WPP_GLOBAL_Control
0x14000f544  cmp     rax, rcx
0x14000f547  jz      short loc_14000F576
0x14000f549  test    byte ptr [rax+1Ch], 1
0x14000f54d  jz      short loc_14000F576
0x14000f54f  cmp     byte ptr [rax+19h], 2
0x14000f553  jb      short loc_14000F576
0x14000f555  lea     r9, [rbp+2A0h]
0x14000f55c  mov     edx, 0FAh
0x14000f561  mov     dword ptr [rsp+78h+lpString2], esi
0x14000f565  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000f56c  mov     rcx, [rax+10h]
0x14000f570  call    WPP_SF_Zd
0x14000f575  nop
0x14000f576  test    rbx, rbx
0x14000f579  jz      short loc_14000F589
0x14000f57b  mov     rcx, rbx; SRWLock
0x14000f57e  call    cs:__imp_ReleaseSRWLockShared
0x14000f584  jmp     short loc_14000F589
0x14000f586  mov     edi, r9d
0x14000f589  mov     rcx, rbp; this
0x14000f58c  call    ?DereferenceVolume@CTieredVolume@@QEAAXXZ; CTieredVolume::DereferenceVolume(void)
0x14000f591  mov     eax, edi
0x14000f593  jmp     short loc_14000F5DB
0x14000f595  mov     ebx, 80070057h
0x14000f59a  lea     rcx, WPP_GLOBAL_Control
0x14000f5a1  mov     rax, cs:WPP_GLOBAL_Control
0x14000f5a8  cmp     rax, rcx
0x14000f5ab  jz      short loc_14000F5D9
0x14000f5ad  test    byte ptr [rax+1Ch], 1
0x14000f5b1  jz      short loc_14000F5D9
0x14000f5b3  cmp     byte ptr [rax+19h], 2
0x14000f5b7  jb      short loc_14000F5D9
0x14000f5b9  lea     r9, [rbp+2A0h]
0x14000f5c0  mov     edx, 0F8h
0x14000f5c5  mov     dword ptr [rsp+78h+lpString2], ebx
0x14000f5c9  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000f5d0  mov     rcx, [rax+10h]
0x14000f5d4  call    WPP_SF_Zd
0x14000f5d9  mov     eax, ebx
0x14000f5db  mov     rbx, [rsp+78h+arg_0]
0x14000f5e3  add     rsp, 40h
0x14000f5e7  pop     r15
0x14000f5e9  pop     r14
0x14000f5eb  pop     r13
0x14000f5ed  pop     r12
0x14000f5ef  pop     rdi
0x14000f5f0  pop     rsi
0x14000f5f1  pop     rbp
0x14000f5f2  retn
```
