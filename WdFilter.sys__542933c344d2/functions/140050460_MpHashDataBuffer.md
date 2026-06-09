# MpHashDataBuffer

- ea: `0x140050460`
- end: `0x1400506a4`
- name: `MpHashDataBuffer`
- size: `580`
- prototype: `__int64 __fastcall(PCWSTR SourceString, ULONG cbInput)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140050290`

## callees

- `0x140011890`
- `0x1400118d0`
- `0x140050460`
- `0x1400506a4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140050663`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140050663`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14005057d`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14005057d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140050566`
- `ntoskrnl!RtlInitUnicodeString` at `0x140050566`
- `ntoskrnl!ExQueryDepthSList` at `0x14005061f`
- `ntoskrnl!ExQueryDepthSList` at `0x14005061f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005064e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005064e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400504eb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400504eb`
- `ksecdd!BCryptFinishHash` at `0x1400505d2`
- `ksecdd!BCryptFinishHash` at `0x1400505d2`
- `ksecdd!BCryptDestroyHash` at `0x1400505f9`
- `ksecdd!BCryptDestroyHash` at `0x1400505f9`
- `ksecdd!BCryptHashData` at `0x1400505a0`
- `ksecdd!BCryptHashData` at `0x1400505a0`
- `ksecdd!BCryptCreateHash` at `0x140050549`
- `ksecdd!BCryptCreateHash` at `0x140050549`

## pseudocode

```c
__int64 __fastcall MpHashDataBuffer(PCWSTR SourceString, ULONG cbInput, __int64 a3)
{
  char v6; // r12
  union _SLIST_HEADER *v7; // rbx
  UCHAR *v9; // r14
  __int64 v10; // rdx
  __int64 (__fastcall *Alignment)(__int64, __int64, __int64, union _SLIST_HEADER *); // rax
  __int64 v12; // r8
  __int64 v13; // rcx
  NTSTATUS v14; // esi
  BCRYPT_HASH_HANDLE v15; // rcx
  char *v16; // rdi
  char *v17; // rdi
  USHORT v18; // bx
  USHORT DepthSList; // ax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF

  phHash = 0;
  v6 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  if ( !SourceString || !a3 || !cbInput )
    return 3221225485LL;
  MpHashLibInitIfNeeded();
  v7 = (union _SLIST_HEADER *)MpHashLibData;
  if ( !MpHashLibData )
    return 3221225626LL;
  if ( !*((_BYTE *)MpHashLibData + 24) )
    return 3221225701LL;
  ++*((_DWORD *)MpHashLibData + 13);
  v9 = (UCHAR *)ExpInterlockedPopEntrySList(v7 + 2);
  if ( !v9 )
  {
    v10 = *((unsigned int *)&v7[4].HeaderX64 + 3);
    Alignment = (__int64 (__fastcall *)(__int64, __int64, __int64, union _SLIST_HEADER *))v7[5].Alignment;
    v12 = *((unsigned int *)&v7[4].HeaderX64 + 2);
    v13 = *((unsigned int *)&v7[4].HeaderX64 + 1);
    ++*((_DWORD *)&v7[3].HeaderX64 + 2);
    v9 = (UCHAR *)Alignment(v13, v10, v12, v7 + 2);
    if ( !v9 )
      return 3221225626LL;
  }
  v14 = BCryptCreateHash(
          *((BCRYPT_ALG_HANDLE *)MpHashLibData + 1),
          &phHash,
          v9,
          *((_DWORD *)MpHashLibData + 4),
          0,
          0,
          0);
  if ( v14 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    v14 = RtlUpcaseUnicodeString(&UnicodeString, &DestinationString, 1u);
    if ( v14 >= 0 )
    {
      v6 = 1;
      v14 = BCryptHashData(phHash, (PUCHAR)UnicodeString.Buffer, cbInput, 0);
      if ( v14 >= 0 )
      {
        v15 = phHash;
        *(_OWORD *)(a3 + 4) = 0;
        *(_OWORD *)(a3 + 20) = 0;
        v14 = BCryptFinishHash(v15, (PUCHAR)(a3 + 4), *((_DWORD *)MpHashLibData + 5), 0);
        if ( v14 >= 0 )
          *(_DWORD *)a3 = *((_DWORD *)MpHashLibData + 5);
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  v16 = (char *)MpHashLibData;
  ++*((_DWORD *)MpHashLibData + 15);
  v17 = v16 + 32;
  v18 = *((_WORD *)v17 + 8);
  DepthSList = ExQueryDepthSList((PSLIST_HEADER)v17);
  _mm_lfence();
  if ( DepthSList < v18 )
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)v17, (PSLIST_ENTRY)v9);
  }
  else
  {
    ++*((_DWORD *)v17 + 8);
    (*((void (__fastcall **)(UCHAR *, char *))v17 + 7))(v9, v17);
  }
  if ( v6 )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140050460  mov     [rsp-38h+arg_18], rbx
0x140050465  push    rbp
0x140050466  push    rsi
0x140050467  push    rdi
0x140050468  push    r12
0x14005046a  push    r13
0x14005046c  push    r14
0x14005046e  push    r15
0x140050470  mov     rbp, rsp
0x140050473  sub     rsp, 70h
0x140050477  mov     rax, cs:__security_cookie
0x14005047e  xor     rax, rsp
0x140050481  mov     [rbp+var_8], rax
0x140050485  xor     esi, esi
0x140050487  xorps   xmm0, xmm0
0x14005048a  mov     [rbp+phHash], rsi
0x14005048e  xorps   xmm1, xmm1
0x140050491  mov     rdi, r8
0x140050494  mov     r15d, edx
0x140050497  mov     r13, rcx
0x14005049a  mov     r12b, sil
0x14005049d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400504a1  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x1400504a5  test    rcx, rcx
0x1400504a8  jz      loc_14005067A
0x1400504ae  test    r8, r8
0x1400504b1  jz      loc_14005067A
0x1400504b7  test    edx, edx
0x1400504b9  jz      loc_14005067A
0x1400504bf  call    MpHashLibInitIfNeeded
0x1400504c4  mov     rbx, cs:MpHashLibData
0x1400504cb  test    rbx, rbx
0x1400504ce  jz      loc_140050673
0x1400504d4  cmp     [rbx+18h], sil
0x1400504d8  jnz     short loc_1400504E4
0x1400504da  mov     eax, 0C00000E5h
0x1400504df  jmp     loc_14005067F
0x1400504e4  inc     dword ptr [rbx+34h]
0x1400504e7  lea     rcx, [rbx+20h]; ListHead
0x1400504eb  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400504f2  nop     dword ptr [rax+rax+00h]
0x1400504f7  mov     r14, rax
0x1400504fa  test    rax, rax
0x1400504fd  jnz     short loc_140050526
0x1400504ff  mov     edx, [rbx+4Ch]
0x140050502  lea     r9, [rbx+20h]
0x140050506  mov     rax, [rbx+50h]
0x14005050a  mov     r8d, [rbx+48h]
0x14005050e  mov     ecx, [rbx+44h]
0x140050511  inc     dword ptr [rbx+38h]
0x140050514  call    cs:__guard_dispatch_icall_fptr
0x14005051a  mov     r14, rax
0x14005051d  test    rax, rax
0x140050520  jz      loc_140050673
0x140050526  mov     rcx, cs:MpHashLibData
0x14005052d  lea     rdx, [rbp+phHash]; phHash
0x140050531  mov     [rsp+70h+dwFlags], esi; dwFlags
0x140050535  mov     r8, r14; pbHashObject
0x140050538  mov     [rsp+70h+cbSecret], esi; cbSecret
0x14005053c  mov     [rsp+70h+pbSecret], rsi; pbSecret
0x140050541  mov     r9d, [rcx+10h]; cbHashObject
0x140050545  mov     rcx, [rcx+8]; hAlgorithm
0x140050549  call    cs:__imp_BCryptCreateHash
0x140050550  nop     dword ptr [rax+rax+00h]
0x140050555  mov     esi, eax
0x140050557  test    eax, eax
0x140050559  js      loc_1400505F0
0x14005055f  mov     rdx, r13; SourceString
0x140050562  lea     rcx, [rbp+DestinationString]; DestinationString
0x140050566  call    cs:__imp_RtlInitUnicodeString
0x14005056d  nop     dword ptr [rax+rax+00h]
0x140050572  mov     r8b, 1; AllocateDestinationString
0x140050575  lea     rdx, [rbp+DestinationString]; SourceString
0x140050579  lea     rcx, [rbp+UnicodeString]; DestinationString
0x14005057d  call    cs:__imp_RtlUpcaseUnicodeString
0x140050584  nop     dword ptr [rax+rax+00h]
0x140050589  mov     esi, eax
0x14005058b  test    eax, eax
0x14005058d  js      short loc_1400505F0
0x14005058f  mov     rdx, [rbp+UnicodeString.Buffer]; pbInput
0x140050593  xor     r9d, r9d; dwFlags
0x140050596  mov     rcx, [rbp+phHash]; hHash
0x14005059a  mov     r8d, r15d; cbInput
0x14005059d  mov     r12b, 1
0x1400505a0  call    cs:__imp_BCryptHashData
0x1400505a7  nop     dword ptr [rax+rax+00h]
0x1400505ac  mov     esi, eax
0x1400505ae  test    eax, eax
0x1400505b0  js      short loc_1400505F0
0x1400505b2  mov     rcx, [rbp+phHash]; hHash
0x1400505b6  lea     rdx, [rdi+4]; pbOutput
0x1400505ba  xorps   xmm0, xmm0
0x1400505bd  xor     r9d, r9d; dwFlags
0x1400505c0  movups  xmmword ptr [rdx], xmm0
0x1400505c3  movups  xmmword ptr [rdx+10h], xmm0
0x1400505c7  mov     r8, cs:MpHashLibData
0x1400505ce  mov     r8d, [r8+14h]; cbOutput
0x1400505d2  call    cs:__imp_BCryptFinishHash
0x1400505d9  nop     dword ptr [rax+rax+00h]
0x1400505de  mov     esi, eax
0x1400505e0  test    eax, eax
0x1400505e2  js      short loc_1400505F0
0x1400505e4  mov     rax, cs:MpHashLibData
0x1400505eb  mov     ecx, [rax+14h]
0x1400505ee  mov     [rdi], ecx
0x1400505f0  mov     rcx, [rbp+phHash]; hHash
0x1400505f4  test    rcx, rcx
0x1400505f7  jz      short loc_140050605
0x1400505f9  call    cs:__imp_BCryptDestroyHash
0x140050600  nop     dword ptr [rax+rax+00h]
0x140050605  test    r14, r14
0x140050608  jz      short loc_14005065A
0x14005060a  mov     rdi, cs:MpHashLibData
0x140050611  inc     dword ptr [rdi+3Ch]
0x140050614  add     rdi, 20h ; ' '
0x140050618  mov     rcx, rdi; SListHead
0x14005061b  movzx   ebx, word ptr [rdi+10h]
0x14005061f  call    cs:__imp_ExQueryDepthSList
0x140050626  nop     dword ptr [rax+rax+00h]
0x14005062b  lfence
0x14005062e  cmp     ax, bx
0x140050631  jb      short loc_140050648
0x140050633  inc     dword ptr [rdi+20h]
0x140050636  mov     rdx, rdi
0x140050639  mov     rax, [rdi+38h]
0x14005063d  mov     rcx, r14
0x140050640  call    cs:__guard_dispatch_icall_fptr
0x140050646  jmp     short loc_14005065A
0x140050648  mov     rdx, r14; ListEntry
0x14005064b  mov     rcx, rdi; ListHead
0x14005064e  call    cs:__imp_ExpInterlockedPushEntrySList
0x140050655  nop     dword ptr [rax+rax+00h]
0x14005065a  test    r12b, r12b
0x14005065d  jz      short loc_14005066F
0x14005065f  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140050663  call    cs:__imp_RtlFreeUnicodeString
0x14005066a  nop     dword ptr [rax+rax+00h]
0x14005066f  mov     eax, esi
0x140050671  jmp     short loc_14005067F
0x140050673  mov     eax, 0C000009Ah
0x140050678  jmp     short loc_14005067F
0x14005067a  mov     eax, 0C000000Dh
0x14005067f  mov     rcx, [rbp+var_8]
0x140050683  xor     rcx, rsp; StackCookie
0x140050686  call    __security_check_cookie
0x14005068b  mov     rbx, [rsp+70h+arg_18]
0x140050693  add     rsp, 70h
0x140050697  pop     r15
0x140050699  pop     r14
0x14005069b  pop     r13
0x14005069d  pop     r12
0x14005069f  pop     rdi
0x1400506a0  pop     rsi
0x1400506a1  pop     rbp
0x1400506a2  retn
```
