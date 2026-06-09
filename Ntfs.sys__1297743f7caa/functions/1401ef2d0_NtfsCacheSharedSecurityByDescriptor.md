# NtfsCacheSharedSecurityByDescriptor

- ea: `0x1401ef2d0`
- end: `0x1401ef825`
- name: `NtfsCacheSharedSecurityByDescriptor`
- size: `1365`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PSECURITY_DESCRIPTOR SecurityDescriptor@<rdx>, ULONG Length@<r8d>, char)`
- caller_count: `6`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003a498`
- `0x1401edd50`
- `0x1401ee3b0`
- `0x1401f0e58`
- `0x140264ca4`
- `0x140286b8c`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140012e70`
- `0x140025a40`
- `0x140028590`
- `0x140059440`
- `0x140059c60`
- `0x1401403d0`
- `0x140189350`
- `0x1401ef2d0`
- `0x1401efb00`
- `0x1401f0d60`

## import_xrefs

- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ef377`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ef755`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ef377`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ef755`
- `ntoskrnl!RtlNormalizeSecurityDescriptor` at `0x1401ef69d`
- `ntoskrnl!RtlNormalizeSecurityDescriptor` at `0x1401ef69d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ef347`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ef4b7`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ef347`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ef4b7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ef45c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ef7f7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b1a04`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ef45c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ef7f7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b1a04`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ef569`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ef6e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ef569`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ef6e7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401ef5e7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401ef5e7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ef316`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ef4ee`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ef316`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ef4ee`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401ef655`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401ef655`
- `ntoskrnl!ExRaiseStatus` at `0x1401ef5a2`
- `ntoskrnl!ExRaiseStatus` at `0x1401ef5a2`

## pseudocode

```c
__int64 __fastcall NtfsCacheSharedSecurityByDescriptor(
        __int64 a1,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        ULONG Length,
        char a4,
        char a5)
{
  __int64 v9; // rcx
  _DWORD *v10; // rdx
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  char *v14; // rdi
  __int64 CachedSharedSecurityByHashUnsafe; // rsi
  __int64 v16; // rdi
  __int64 v17; // rcx
  ULONG v18; // eax
  __int64 v19; // r9
  volatile signed __int32 **v20; // rdx
  volatile signed __int32 *v21; // r8
  signed __int32 v22; // ebx
  bool v23; // cc
  signed __int32 v24; // ebx
  char *PoolWithTag; // rax
  void *v26; // r14
  __int64 v27; // r8
  size_t Size; // [rsp+30h] [rbp-68h] BYREF
  int v30; // [rsp+38h] [rbp-60h]
  unsigned int v31; // [rsp+3Ch] [rbp-5Ch]
  void *Buf2; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-50h]
  ULONG IsResourceAcquiredSharedLite; // [rsp+4Ch] [rbp-4Ch]
  __int64 v35; // [rsp+50h] [rbp-48h]
  char *v36; // [rsp+58h] [rbp-40h]
  void *v37; // [rsp+60h] [rbp-38h]
  char *v38; // [rsp+68h] [rbp-30h] BYREF

  v35 = 0;
  v9 = *(_QWORD *)(a1 + 104);
  if ( !*(_QWORD *)(v9 + 104) )
    return 0;
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v9 + 664));
  v30 = 1;
  IsResourceAcquiredSharedLite = ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 48LL) + 184LL)
                                                                                       + 104LL)
                                                                           + 64LL));
  LODWORD(Size) = Length;
  Buf2 = SecurityDescriptor;
  v31 = 0;
  v36 = 0;
  if ( !Length || !SeValidSecurityDescriptor(Length, SecurityDescriptor) )
  {
    if ( a4 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225593LL, 2035551);
      NtfsRaiseStatusInternal(a1, -1073741703, 0, 0, 2035551);
      __debugbreak();
    }
    Buf2 = ::SecurityDescriptor;
    LODWORD(Size) = ::Length;
    if ( !SeValidSecurityDescriptor(::Length, ::SecurityDescriptor) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 2035561);
      NtfsRaiseStatusInternal(a1, -1073741811, 0, 0, 2035561);
      __debugbreak();
    }
  }
  v10 = Buf2;
  v37 = Buf2;
  v11 = (unsigned int)Size >> 2;
  v33 = (unsigned int)Size >> 2;
  v12 = 0;
  while ( 1 )
  {
    v13 = v11--;
    v33 = v11;
    if ( !v13 )
      break;
    v12 = *v10++ + __ROR4__(v12, 29);
    v37 = v10;
  }
  v31 = v12;
  v14 = *(char **)(*(_QWORD *)(a1 + 104) + 8LL * (v12 & 0x7F) + 3472);
  if ( v14 )
  {
    if ( *((_DWORD *)v14 + 2) == v12 )
    {
      if ( *((unsigned int *)v14 + 6) - 20LL == (unsigned int)Size )
      {
        if ( memcmp(v14 + 28, Buf2, (unsigned int)Size) )
          v14 = 0;
      }
      else
      {
        v14 = 0;
      }
    }
    else
    {
      v14 = 0;
    }
  }
  else
  {
    v14 = 0;
  }
  v36 = v14;
  if ( v14 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)v14) <= 1 )
      __fastfail(0xEu);
  }
  else
  {
    if ( (unsigned int)Size >= 0xFFFFFFE4 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225859LL, 2035588);
      ExRaiseStatus(-1073741437);
    }
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned int)(Size + 28), 0x5346744Eu);
    v14 = PoolWithTag;
    v36 = PoolWithTag;
    v26 = PoolWithTag + 28;
    if ( a5 )
    {
      memmove(PoolWithTag + 28, Buf2, (unsigned int)Size);
    }
    else
    {
      v38 = PoolWithTag + 28;
      if ( (unsigned __int8)RtlNormalizeSecurityDescriptor(&Buf2, (unsigned int)Size, &v38, &Size, 0) )
      {
        v12 = NtfsHashSecurityDescriptor(v26, (unsigned int)Size);
        v31 = v12;
        CachedSharedSecurityByHashUnsafe = FindCachedSharedSecurityByHashUnsafe(*(_QWORD *)(a1 + 104), v26, v27, v12);
        if ( CachedSharedSecurityByHashUnsafe )
        {
          ExFreePoolWithTag(v14, 0);
          if ( _InterlockedIncrement((volatile signed __int32 *)CachedSharedSecurityByHashUnsafe) <= 1 )
            __fastfail(0xEu);
          goto LABEL_15;
        }
      }
    }
    *(_DWORD *)v14 = 1;
    *((_DWORD *)v14 + 1) = NtfsSecurityDescriptorFlags(v26);
    *((_DWORD *)v14 + 3) = 0;
    *((_DWORD *)v14 + 2) = v12;
    *((_QWORD *)v14 + 2) = -1;
    *((_DWORD *)v14 + 6) = Size + 20;
  }
  CachedSharedSecurityByHashUnsafe = (__int64)v14;
LABEL_15:
  v35 = CachedSharedSecurityByHashUnsafe;
  if ( !*(_DWORD *)(CachedSharedSecurityByHashUnsafe + 12) )
  {
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
    v30 = 0;
    *(_DWORD *)(CachedSharedSecurityByHashUnsafe + 12) = GetSecurityIdFromSecurityDescriptorUnsafe(a1);
    NtfsCheckpointCurrentTransaction(a1);
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 104LL);
    v17 = *(_QWORD *)(v16 + 184);
    if ( *(_QWORD *)(v17 + 80) && ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v17 + 104) + 64LL)) )
      NtfsReleaseFcbEx(a1, *(_QWORD *)(v16 + 184), 0);
    v18 = ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 48LL)
                                                                            + 184LL)
                                                                + 104LL)
                                                    + 64LL));
    if ( v18 != IsResourceAcquiredSharedLite )
      NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 48LL) + 184LL), 0);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
    v30 = 1;
    v19 = *(_QWORD *)(a1 + 104);
    v20 = (volatile signed __int32 **)(v19 + 8 * ((*(_DWORD *)(CachedSharedSecurityByHashUnsafe + 8) & 0x7F) + 434LL));
    v21 = *v20;
    if ( (volatile signed __int32 *)CachedSharedSecurityByHashUnsafe == *v20 )
    {
      *(_QWORD *)(v19 + 8LL * (*(_DWORD *)(CachedSharedSecurityByHashUnsafe + 12) & 0x7F) + 2448) = v20;
    }
    else
    {
      *v20 = (volatile signed __int32 *)CachedSharedSecurityByHashUnsafe;
      if ( _InterlockedIncrement((volatile signed __int32 *)CachedSharedSecurityByHashUnsafe) <= 1 )
        __fastfail(0xEu);
      *(_QWORD *)(v19 + 8LL * (*(_DWORD *)(CachedSharedSecurityByHashUnsafe + 12) & 0x7F) + 2448) = v20;
      if ( v21 )
      {
        v22 = _InterlockedExchangeAdd(v21, 0xFFFFFFFF);
        v23 = v22 <= 1;
        v24 = v22 - 1;
        if ( v23 )
        {
          if ( v24 )
            __fastfail(0xEu);
          ExFreePoolWithTag((PVOID)v21, 0);
        }
      }
    }
  }
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
  return CachedSharedSecurityByHashUnsafe;
}

```

## disassembly

```asm
0x1401ef2d0  mov     [rsp+arg_8], rbx
0x1401ef2d5  mov     [rsp+arg_10], rsi
0x1401ef2da  mov     [rsp+arg_0], rcx
0x1401ef2df  push    rdi
0x1401ef2e0  push    r12
0x1401ef2e2  push    r13
0x1401ef2e4  push    r14
0x1401ef2e6  push    r15
0x1401ef2e8  sub     rsp, 70h
0x1401ef2ec  movzx   esi, r9b
0x1401ef2f0  mov     ebx, r8d
0x1401ef2f3  mov     rdi, rdx
0x1401ef2f6  mov     r15, rcx
0x1401ef2f9  xor     r14d, r14d
0x1401ef2fc  mov     [rsp+98h+var_48], r14
0x1401ef301  mov     rcx, [rcx+68h]
0x1401ef305  cmp     [rcx+68h], r14
0x1401ef309  jz      loc_1401EF821
0x1401ef30f  add     rcx, 298h; Mutex
0x1401ef316  call    cs:__imp_KeAcquireGuardedMutex
0x1401ef31d  nop     dword ptr [rax+rax+00h]
0x1401ef322  mov     r13d, 1
0x1401ef328  mov     r12d, r13d
0x1401ef32b  mov     [rsp+98h+var_60], r13d
0x1401ef330  mov     rax, [r15+68h]
0x1401ef334  mov     rcx, [rax+30h]
0x1401ef338  mov     rax, [rcx+0B8h]
0x1401ef33f  mov     rcx, [rax+68h]
0x1401ef343  add     rcx, 40h ; '@'; Resource
0x1401ef347  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401ef34e  nop     dword ptr [rax+rax+00h]
0x1401ef353  mov     [rsp+98h+var_4C], eax
0x1401ef357  mov     dword ptr [rsp+98h+Size], ebx
0x1401ef35b  mov     [rsp+98h+Buf2], rdi
0x1401ef360  mov     [rsp+98h+var_5C], r14d
0x1401ef365  mov     [rsp+98h+var_40], r14
0x1401ef36a  test    ebx, ebx
0x1401ef36c  jz      loc_1401EF73A
0x1401ef372  mov     rdx, rdi; SecurityDescriptor
0x1401ef375  mov     ecx, ebx; Length
0x1401ef377  call    cs:__imp_SeValidSecurityDescriptor
0x1401ef37e  nop     dword ptr [rax+rax+00h]
0x1401ef383  test    al, al
0x1401ef385  jz      loc_1401EF73A
0x1401ef38b  mov     r9, [rsp+98h+Buf2]
0x1401ef390  mov     rdx, r9
0x1401ef393  mov     [rsp+98h+var_38], rdx
0x1401ef398  mov     esi, dword ptr [rsp+98h+Size]
0x1401ef39c  mov     ecx, esi
0x1401ef39e  shr     ecx, 2
0x1401ef3a1  mov     [rsp+98h+var_50], ecx
0x1401ef3a5  mov     ebx, r14d
0x1401ef3a8  nop     dword ptr [rax+rax+00000000h]
0x1401ef3b0  mov     eax, ecx
0x1401ef3b2  dec     ecx
0x1401ef3b4  mov     [rsp+98h+var_50], ecx
0x1401ef3b8  test    eax, eax
0x1401ef3ba  jz      short loc_1401EF3CC
0x1401ef3bc  ror     ebx, 1Dh
0x1401ef3bf  add     ebx, [rdx]
0x1401ef3c1  add     rdx, 4
0x1401ef3c5  mov     [rsp+98h+var_38], rdx
0x1401ef3ca  jmp     short loc_1401EF3B0
0x1401ef3cc  mov     [rsp+98h+var_5C], ebx
0x1401ef3d0  mov     ecx, ebx
0x1401ef3d2  and     ecx, 7Fh
0x1401ef3d5  mov     rax, [r15+68h]
0x1401ef3d9  mov     rdi, [rax+rcx*8+0D90h]
0x1401ef3e1  test    rdi, rdi
0x1401ef3e4  jz      loc_1401EF7DF
0x1401ef3ea  cmp     [rdi+8], ebx
0x1401ef3ed  jnz     loc_1401EF57A
0x1401ef3f3  mov     r8, rsi; Size
0x1401ef3f6  mov     eax, [rdi+18h]
0x1401ef3f9  sub     rax, 14h
0x1401ef3fd  cmp     rax, rsi
0x1401ef400  jnz     loc_1401EF582
0x1401ef406  lea     rcx, [rdi+1Ch]; Buf1
0x1401ef40a  mov     rdx, r9; Buf2
0x1401ef40d  call    memcmp
0x1401ef412  test    eax, eax
0x1401ef414  cmovnz  rdi, r14
0x1401ef418  mov     [rsp+98h+var_40], rdi
0x1401ef41d  test    rdi, rdi
0x1401ef420  jz      loc_1401EF58A
0x1401ef426  mov     eax, r13d
0x1401ef429  lock xadd [rdi], eax
0x1401ef42d  inc     eax
0x1401ef42f  cmp     eax, 1
0x1401ef432  jle     loc_1401EF70D
0x1401ef438  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1401ef43f  mov     rsi, rdi
0x1401ef442  mov     [rsp+98h+var_48], rsi
0x1401ef447  cmp     dword ptr [rsi+0Ch], 0
0x1401ef44b  jnz     loc_1401EF7E7
0x1401ef451  mov     rcx, [r15+68h]
0x1401ef455  add     rcx, 298h; Mutex
0x1401ef45c  call    cs:__imp_KeReleaseGuardedMutex
0x1401ef463  nop     dword ptr [rax+rax+00h]
0x1401ef468  mov     [rsp+98h+var_60], 0
0x1401ef470  mov     rdx, rsi
0x1401ef473  mov     rcx, r15; int
0x1401ef476  call    GetSecurityIdFromSecurityDescriptorUnsafe
0x1401ef47b  mov     [rsi+0Ch], eax
0x1401ef47e  mov     rcx, r15
0x1401ef481  call    NtfsCheckpointCurrentTransaction
0x1401ef486  mov     rax, [r15+68h]
0x1401ef48a  mov     rdi, [rax+68h]
0x1401ef48e  mov     rcx, [rdi+0B8h]
0x1401ef495  cmp     qword ptr [rcx+50h], 0
0x1401ef49a  jnz     loc_1401EF64D
0x1401ef4a0  mov     rax, [r15+68h]
0x1401ef4a4  mov     rcx, [rax+30h]
0x1401ef4a8  mov     rax, [rcx+0B8h]
0x1401ef4af  mov     rcx, [rax+68h]
0x1401ef4b3  add     rcx, 40h ; '@'; Resource
0x1401ef4b7  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401ef4be  nop     dword ptr [rax+rax+00h]
0x1401ef4c3  cmp     eax, [rsp+98h+var_4C]
0x1401ef4c7  jz      short loc_1401EF4E3
0x1401ef4c9  mov     rax, [r15+68h]
0x1401ef4cd  mov     rdx, [rax+30h]
0x1401ef4d1  xor     r8d, r8d
0x1401ef4d4  mov     rdx, [rdx+0B8h]
0x1401ef4db  mov     rcx, r15
0x1401ef4de  call    NtfsReleaseFcbEx
0x1401ef4e3  mov     rcx, [r15+68h]
0x1401ef4e7  add     rcx, 298h; Mutex
0x1401ef4ee  call    cs:__imp_KeAcquireGuardedMutex
0x1401ef4f5  nop     dword ptr [rax+rax+00h]
0x1401ef4fa  mov     r12d, r13d
0x1401ef4fd  mov     [rsp+98h+var_60], r13d
0x1401ef502  mov     r9, [r15+68h]
0x1401ef506  mov     edx, [rsi+8]
0x1401ef509  and     edx, 7Fh
0x1401ef50c  add     rdx, 1B2h
0x1401ef513  lea     rdx, [r9+rdx*8]
0x1401ef517  mov     r8, [rdx]
0x1401ef51a  cmp     rsi, r8
0x1401ef51d  jz      loc_1401EF5C3
0x1401ef523  mov     [rdx], rsi
0x1401ef526  lock xadd [rsi], r13d
0x1401ef52b  inc     r13d
0x1401ef52e  cmp     r13d, r12d
0x1401ef531  jle     loc_1401EF719
0x1401ef537  mov     eax, [rsi+0Ch]
0x1401ef53a  and     eax, 7Fh
0x1401ef53d  mov     [r9+rax*8+990h], rdx
0x1401ef545  test    r8, r8
0x1401ef548  jz      loc_1401EF7E7
0x1401ef54e  lock xadd [r8], ebx
0x1401ef553  sub     ebx, r12d
0x1401ef556  jg      loc_1401EF7E7
0x1401ef55c  test    ebx, ebx
0x1401ef55e  jnz     loc_1401EF72E
0x1401ef564  xor     edx, edx; Tag
0x1401ef566  mov     rcx, r8; P
0x1401ef569  call    cs:__imp_ExFreePoolWithTag
0x1401ef570  nop     dword ptr [rax+rax+00h]
0x1401ef575  jmp     loc_1401EF7E7
0x1401ef57a  mov     rdi, r14
0x1401ef57d  jmp     loc_1401EF418
0x1401ef582  mov     rdi, r14
0x1401ef585  jmp     loc_1401EF418
0x1401ef58a  lea     eax, [rsi+1Ch]
0x1401ef58d  cmp     eax, 1Ch
0x1401ef590  jnb     short loc_1401EF5D6
0x1401ef592  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ef599  test    al, al
0x1401ef59b  jnz     short loc_1401EF5AF
0x1401ef59d  mov     ecx, 0C0000183h; Status
0x1401ef5a2  call    cs:__imp_ExRaiseStatus
0x1401ef5af  mov     edx, 0C0000183h
0x1401ef5b4  xor     ecx, ecx
0x1401ef5b6  mov     r8d, 1F0F84h
0x1401ef5bc  call    NtfsStatusTraceAndDebugInternal
0x1401ef5c1  jmp     short loc_1401EF59D
0x1401ef5c3  mov     eax, [rsi+0Ch]
0x1401ef5c6  and     eax, 7Fh
0x1401ef5c9  mov     [r9+rax*8+990h], rdx
0x1401ef5d1  jmp     loc_1401EF7E7
0x1401ef5d6  mov     edx, eax; NumberOfBytes
0x1401ef5d8  mov     ecx, cs:PoolType
0x1401ef5de  or      ecx, 10h; PoolType
0x1401ef5e1  mov     r8d, 5346744Eh; Tag
0x1401ef5e7  call    cs:__imp_ExAllocatePoolWithTag
0x1401ef5ee  nop     dword ptr [rax+rax+00h]
0x1401ef5f3  mov     rdi, rax
0x1401ef5f6  mov     [rsp+98h+var_40], rax
0x1401ef5fb  lea     r14, [rax+1Ch]
0x1401ef5ff  cmp     [rsp+98h+arg_20], 0
0x1401ef607  jz      short loc_1401EF680
0x1401ef609  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x1401ef60e  mov     rdx, [rsp+98h+Buf2]; Src
0x1401ef613  mov     rcx, r14; void *
0x1401ef616  call    memmove
0x1401ef61b  mov     [rdi], r13d
0x1401ef61e  mov     rcx, r14; SecurityDescriptor
0x1401ef621  call    NtfsSecurityDescriptorFlags
0x1401ef626  mov     [rdi+4], eax
0x1401ef629  mov     dword ptr [rdi+0Ch], 0
0x1401ef630  mov     [rdi+8], ebx
0x1401ef633  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1401ef63a  mov     [rdi+10h], rbx
0x1401ef63e  mov     eax, dword ptr [rsp+98h+Size]
0x1401ef642  add     eax, 14h
0x1401ef645  mov     [rdi+18h], eax
0x1401ef648  jmp     loc_1401EF43F
0x1401ef64d  mov     rcx, [rcx+68h]
0x1401ef651  add     rcx, 40h ; '@'; Resource
0x1401ef655  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1401ef65c  nop     dword ptr [rax+rax+00h]
0x1401ef661  test    al, al
0x1401ef663  jz      loc_1401EF4A0
0x1401ef669  xor     r8d, r8d
0x1401ef66c  mov     rdx, [rdi+0B8h]
0x1401ef673  mov     rcx, r15
0x1401ef676  call    NtfsReleaseFcbEx
0x1401ef67b  jmp     loc_1401EF4A0
0x1401ef680  mov     [rsp+98h+var_30], r14
0x1401ef685  mov     byte ptr [rsp+98h+var_78], 0
0x1401ef68a  lea     r9, [rsp+98h+Size]
0x1401ef68f  lea     r8, [rsp+98h+var_30]
0x1401ef694  mov     edx, dword ptr [rsp+98h+Size]
0x1401ef698  lea     rcx, [rsp+98h+Buf2]
0x1401ef69d  call    cs:__imp_RtlNormalizeSecurityDescriptor
0x1401ef6a4  nop     dword ptr [rax+rax+00h]
0x1401ef6a9  test    al, al
0x1401ef6ab  jz      loc_1401EF61B
0x1401ef6b1  mov     r8d, dword ptr [rsp+98h+Size]
0x1401ef6b6  mov     edx, r8d
0x1401ef6b9  mov     rcx, r14
0x1401ef6bc  call    NtfsHashSecurityDescriptor
0x1401ef6c1  mov     ebx, eax
0x1401ef6c3  mov     [rsp+98h+var_5C], eax
0x1401ef6c7  mov     r9d, eax
0x1401ef6ca  mov     rdx, r14
0x1401ef6cd  mov     rcx, [r15+68h]
0x1401ef6d1  call    FindCachedSharedSecurityByHashUnsafe
0x1401ef6d6  mov     rsi, rax
0x1401ef6d9  test    rax, rax
0x1401ef6dc  jz      loc_1401EF61B
0x1401ef6e2  xor     edx, edx; Tag
0x1401ef6e4  mov     rcx, rdi; P
0x1401ef6e7  call    cs:__imp_ExFreePoolWithTag
0x1401ef6ee  nop     dword ptr [rax+rax+00h]
0x1401ef6f3  mov     eax, r13d
0x1401ef6f6  lock xadd [rsi], eax
0x1401ef6fa  inc     eax
0x1401ef6fc  cmp     eax, 1
0x1401ef6ff  jle     short loc_1401EF725
0x1401ef701  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1401ef708  jmp     loc_1401EF442
0x1401ef70d  mov     ecx, 0Eh
0x1401ef712  int     29h; Win8: RtlFailFast(ecx)
0x1401ef714  jmp     loc_1401EF438
0x1401ef719  mov     ecx, 0Eh
0x1401ef71e  int     29h; Win8: RtlFailFast(ecx)
0x1401ef720  jmp     loc_1401EF537
0x1401ef725  mov     ecx, 0Eh
0x1401ef72a  int     29h; Win8: RtlFailFast(ecx)
0x1401ef72c  jmp     short loc_1401EF701
0x1401ef72e  mov     ecx, 0Eh
0x1401ef733  int     29h; Win8: RtlFailFast(ecx)
0x1401ef735  jmp     loc_1401EF7E7
0x1401ef73a  test    sil, sil
0x1401ef73d  jnz     short loc_1401EF7A4
0x1401ef73f  mov     rdx, cs:SecurityDescriptor; SecurityDescriptor
0x1401ef746  mov     [rsp+98h+Buf2], rdx
0x1401ef74b  mov     ecx, cs:Length; Length
0x1401ef751  mov     dword ptr [rsp+98h+Size], ecx
0x1401ef755  call    cs:__imp_SeValidSecurityDescriptor
0x1401ef75c  nop     dword ptr [rax+rax+00h]
0x1401ef761  test    al, al
0x1401ef763  jnz     loc_1401EF38B
0x1401ef769  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ef770  test    al, al
0x1401ef772  jz      short loc_1401EF787
0x1401ef774  mov     edx, 0C000000Dh
0x1401ef779  mov     r8d, 1F0F69h
0x1401ef77f  mov     rcx, r15
0x1401ef782  call    NtfsStatusTraceAndDebugInternal
0x1401ef787  mov     [rsp+98h+var_78], 1F0F69h
0x1401ef790  xor     r9d, r9d
0x1401ef793  xor     r8d, r8d
0x1401ef796  mov     edx, 0C000000Dh
0x1401ef79b  mov     rcx, r15
0x1401ef79e  call    NtfsRaiseStatusInternal
0x1401ef7a3  int     3; Trap to Debugger
0x1401ef7a4  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ef7ab  test    al, al
0x1401ef7ad  jz      short loc_1401EF7C2
0x1401ef7af  mov     edx, 0C0000079h
0x1401ef7b4  mov     r8d, 1F0F5Fh
0x1401ef7ba  mov     rcx, r15
0x1401ef7bd  call    NtfsStatusTraceAndDebugInternal
0x1401ef7c2  mov     [rsp+98h+var_78], 1F0F5Fh
0x1401ef7cb  xor     r9d, r9d
0x1401ef7ce  xor     r8d, r8d
0x1401ef7d1  mov     edx, 0C0000079h
  ... truncated ...
```
