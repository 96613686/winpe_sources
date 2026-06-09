# BfsAddOrModifyEntry

- ea: `0x14001033c`
- end: `0x1400105a4`
- name: `BfsAddOrModifyEntry`
- size: `616`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140001fb0`
- `0x1400055d8`
- `0x140009b9c`
- `0x14000dadc`

## callees

- `0x14001033c`
- `0x14001079c`
- `0x14001126c`
- `0x1400116a0`
- `0x140011894`
- `0x140011a38`
- `0x140011d18`
- `0x140012ab0`
- `0x140012b10`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400104da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400104da`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001051e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010560`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001051e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010560`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400103f2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400103f2`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140010412`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140010412`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400103e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400104c9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400103e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400104c9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001041e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001052a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001056c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001041e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001052a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001056c`

## pseudocode

```c
__int64 __fastcall BfsAddOrModifyEntry(
        __int64 a1,
        ULONG a2,
        NTSTATUS a3,
        ULONG a4,
        const UNICODE_STRING *a5,
        PVOID *a6)
{
  PVOID *v6; // rax
  __int64 result; // rax
  NTSTATUS EntryBlock; // edi
  PVOID *v11; // rbx
  char v12; // r13
  __m128i v13; // xmm6
  ULONG *Entry; // rsi
  unsigned __int16 v15; // r14
  NTSTATUS v16; // r8d
  ULONG v17; // r9d
  ULONG v18; // edx
  int v19; // eax
  volatile signed __int32 *v20; // rcx
  PVOID *v21; // [rsp+30h] [rbp-50h] BYREF
  void *v22; // [rsp+38h] [rbp-48h] BYREF
  UNICODE_STRING v23; // [rsp+40h] [rbp-40h] BYREF
  __m128i v24; // [rsp+50h] [rbp-30h] BYREF
  __int16 v25[8]; // [rsp+60h] [rbp-20h] BYREF

  v6 = a6;
  a6 = 0;
  v23 = 0;
  v24 = *(__m128i *)v6;
  if ( !*(_WORD *)v6 && a3 == 1 && a4 == 2 )
    return 3221225485LL;
  result = BfsCreateDirectory(a1 + 48, a5, 3, &a6);
  EntryBlock = result;
  if ( (int)result >= 0 )
  {
    v11 = a6;
    v12 = 1;
    v21 = a6;
    while ( 1 )
    {
      v13 = *(__m128i *)BfsGetPathComponent(v25, &v24, (__int64)&v23);
      v24 = v13;
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx(v11, 0);
      Entry = (ULONG *)BfsFindEntry(v11, &v23);
      ExReleasePushLockSharedEx(v11, 0);
      KeLeaveCriticalRegion();
      v15 = _mm_cvtsi128_si32(v13);
      if ( !Entry )
      {
        if ( v15 >= 2u )
        {
          v16 = 0;
          v17 = 0;
        }
        else
        {
          v16 = a3;
          v17 = a4;
          v12 = 0;
        }
        v18 = 2;
        if ( v15 < 2u )
          v18 = a2;
        Entry = BfsInsertDirectoryEntry((__int64)v11, v18, v16, v17, (__int64)&v23);
        if ( (unsigned int)Feature_AppSiloBfsInsertEntryValidityCheck__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( !Entry )
            return 3221225495LL;
        }
      }
      if ( v15 < 2u )
      {
        if ( v12 )
        {
          LODWORD(a6) = 0;
          v22 = 0;
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(v11, 0);
          Entry[1] = a3;
          Entry[2] = a4;
          EntryBlock = BfsGetEntryBlock(v11, Entry, &v22, &a6);
          if ( EntryBlock < 0 )
          {
            ExReleasePushLockExclusiveEx(v11, 0);
            KeLeaveCriticalRegion();
            v20 = (volatile signed __int32 *)(v11 - 1);
LABEL_25:
            BfsDereferenceTableEntry(v20);
            return (unsigned int)EntryBlock;
          }
          EntryBlock = BfsWriteBlock(a1, (int)a6, v22);
          ExReleasePushLockExclusiveEx(v11, 0);
          KeLeaveCriticalRegion();
          BfsDereferenceTableEntry((volatile signed __int32 *)v11 - 2);
          if ( EntryBlock < 0 )
            return (unsigned int)EntryBlock;
        }
      }
      else
      {
        v19 = BfsCreateDirectory((__int64)v11, &v23, 1, &v21);
        v20 = (volatile signed __int32 *)(v11 - 1);
        EntryBlock = v19;
        if ( v19 < 0 )
          goto LABEL_25;
        BfsDereferenceTableEntry(v20);
        v11 = v21;
      }
      if ( v15 < 2u )
        return (unsigned int)EntryBlock;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001033c  mov     rax, rsp
0x14001033f  mov     [rax+18h], rbx
0x140010343  mov     [rax+10h], edx
0x140010346  mov     [rax+8], rcx
0x14001034a  push    rbp
0x14001034b  push    rsi
0x14001034c  push    rdi
0x14001034d  push    r12
0x14001034f  push    r13
0x140010351  push    r14
0x140010353  push    r15
0x140010355  mov     rbp, rsp
0x140010358  sub     rsp, 80h
0x14001035f  xor     esi, esi
0x140010361  movaps  xmmword ptr [rax-48h], xmm6
0x140010365  mov     rax, [rbp+arg_28]
0x140010369  xorps   xmm0, xmm0
0x14001036c  mov     r15d, r9d
0x14001036f  mov     [rbp+arg_28], rsi
0x140010373  mov     r12d, r8d
0x140010376  movups  [rbp+var_40], xmm0
0x14001037a  movups  xmm1, xmmword ptr [rax]
0x14001037d  movdqu  [rbp+var_30], xmm1
0x140010382  cmp     [rax], si
0x140010385  jnz     short loc_14001039D
0x140010387  cmp     r8d, 1
0x14001038b  jnz     short loc_14001039D
0x14001038d  cmp     r9d, 2
0x140010391  jnz     short loc_14001039D
0x140010393  mov     eax, 0C000000Dh
0x140010398  jmp     loc_140010583
0x14001039d  mov     rdx, [rbp+arg_20]
0x1400103a1  lea     r9, [rbp+arg_28]
0x1400103a5  add     rcx, 30h ; '0'
0x1400103a9  mov     r8d, 3
0x1400103af  call    BfsCreateDirectory
0x1400103b4  mov     edi, eax
0x1400103b6  test    eax, eax
0x1400103b8  js      loc_140010583
0x1400103be  mov     rbx, [rbp+arg_28]
0x1400103c2  mov     r13b, 1
0x1400103c5  mov     [rbp+var_50], rbx
0x1400103c9  lea     r8, [rbp+var_40]
0x1400103cd  lea     rdx, [rbp+var_30]
0x1400103d1  lea     rcx, [rbp+var_20]
0x1400103d5  call    BfsGetPathComponent
0x1400103da  movups  xmm6, xmmword ptr [rax]
0x1400103dd  movups  [rbp+var_30], xmm6
0x1400103e1  call    cs:__imp_KeEnterCriticalRegion
0x1400103e8  nop     dword ptr [rax+rax+00h]
0x1400103ed  xor     edx, edx
0x1400103ef  mov     rcx, rbx
0x1400103f2  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400103f9  nop     dword ptr [rax+rax+00h]
0x1400103fe  lea     rdx, [rbp+var_40]
0x140010402  mov     rcx, rbx
0x140010405  call    BfsFindEntry
0x14001040a  xor     edx, edx
0x14001040c  mov     rcx, rbx
0x14001040f  mov     rsi, rax
0x140010412  call    cs:__imp_ExReleasePushLockSharedEx
0x140010419  nop     dword ptr [rax+rax+00h]
0x14001041e  call    cs:__imp_KeLeaveCriticalRegion
0x140010425  nop     dword ptr [rax+rax+00h]
0x14001042a  xor     ecx, ecx
0x14001042c  movd    r14d, xmm6
0x140010431  test    rsi, rsi
0x140010434  jnz     short loc_14001047E
0x140010436  lea     eax, [rcx+2]
0x140010439  cmp     r14w, ax
0x14001043d  jnb     short loc_14001044A
0x14001043f  mov     r8d, r12d
0x140010442  mov     r9d, r15d
0x140010445  mov     r13b, cl
0x140010448  jmp     short loc_140010450
0x14001044a  mov     r8d, ecx
0x14001044d  mov     r9d, ecx
0x140010450  mov     edx, eax
0x140010452  mov     rcx, rbx
0x140010455  cmovb   edx, [rbp+arg_8]
0x140010459  lea     rax, [rbp+var_40]
0x14001045d  mov     [rsp+80h+var_60], rax
0x140010462  call    BfsInsertDirectoryEntry
0x140010467  mov     rsi, rax
0x14001046a  call    Feature_AppSiloBfsInsertEntryValidityCheck__private_IsEnabledDeviceUsageNoInline
0x14001046f  xor     ecx, ecx
0x140010471  test    eax, eax
0x140010473  jz      short loc_14001047E
0x140010475  test    rsi, rsi
0x140010478  jz      loc_140010554
0x14001047e  mov     eax, 2
0x140010483  cmp     r14w, ax
0x140010487  jb      short loc_1400104B9
0x140010489  lea     r9, [rbp+var_50]
0x14001048d  mov     rcx, rbx
0x140010490  lea     r8d, [rax-1]
0x140010494  lea     rdx, [rbp+var_40]
0x140010498  call    BfsCreateDirectory
0x14001049d  lea     rcx, [rbx-8]; Buffer
0x1400104a1  mov     edi, eax
0x1400104a3  test    eax, eax
0x1400104a5  js      loc_14001057C
0x1400104ab  call    BfsDereferenceTableEntry
0x1400104b0  mov     rbx, [rbp+var_50]
0x1400104b4  jmp     loc_140010543
0x1400104b9  test    r13b, r13b
0x1400104bc  jz      loc_140010543
0x1400104c2  mov     dword ptr [rbp+arg_28], ecx
0x1400104c5  mov     [rbp+var_48], rcx
0x1400104c9  call    cs:__imp_KeEnterCriticalRegion
0x1400104d0  nop     dword ptr [rax+rax+00h]
0x1400104d5  xor     edx, edx
0x1400104d7  mov     rcx, rbx
0x1400104da  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400104e1  nop     dword ptr [rax+rax+00h]
0x1400104e6  lea     r9, [rbp+arg_28]
0x1400104ea  mov     [rsi+4], r12d
0x1400104ee  lea     r8, [rbp+var_48]
0x1400104f2  mov     [rsi+8], r15d
0x1400104f6  mov     rdx, rsi
0x1400104f9  mov     rcx, rbx
0x1400104fc  call    BfsGetEntryBlock
0x140010501  mov     edi, eax
0x140010503  test    eax, eax
0x140010505  js      short loc_14001055B
0x140010507  mov     r8, [rbp+var_48]
0x14001050b  mov     edx, dword ptr [rbp+arg_28]
0x14001050e  mov     rcx, [rbp+arg_0]
0x140010512  call    BfsWriteBlock
0x140010517  xor     edx, edx
0x140010519  mov     rcx, rbx
0x14001051c  mov     edi, eax
0x14001051e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010525  nop     dword ptr [rax+rax+00h]
0x14001052a  call    cs:__imp_KeLeaveCriticalRegion
0x140010531  nop     dword ptr [rax+rax+00h]
0x140010536  lea     rcx, [rbx-8]; Buffer
0x14001053a  call    BfsDereferenceTableEntry
0x14001053f  test    edi, edi
0x140010541  js      short loc_140010581
0x140010543  mov     ecx, 2
0x140010548  cmp     r14w, cx
0x14001054c  jnb     loc_1400103C9
0x140010552  jmp     short loc_140010581
0x140010554  mov     eax, 0C0000017h
0x140010559  jmp     short loc_140010583
0x14001055b  xor     edx, edx
0x14001055d  mov     rcx, rbx
0x140010560  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010567  nop     dword ptr [rax+rax+00h]
0x14001056c  call    cs:__imp_KeLeaveCriticalRegion
0x140010573  nop     dword ptr [rax+rax+00h]
0x140010578  lea     rcx, [rbx-8]; Buffer
0x14001057c  call    BfsDereferenceTableEntry
0x140010581  mov     eax, edi
0x140010583  mov     rbx, [rsp+80h+arg_10]
0x14001058b  movaps  xmm6, [rsp+80h+var_10]
0x140010590  add     rsp, 80h
0x140010597  pop     r15
0x140010599  pop     r14
0x14001059b  pop     r13
0x14001059d  pop     r12
0x14001059f  pop     rdi
0x1400105a0  pop     rsi
0x1400105a1  pop     rbp
0x1400105a2  retn
```
