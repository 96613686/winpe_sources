# BfsInsertPolicyEntry

- ea: `0x140007fec`
- end: `0x140008721`
- name: `BfsInsertPolicyEntry`
- size: `1845`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned __int8 *, unsigned __int8 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400071d4`

## callees

- `0x140001008`
- `0x1400061d0`
- `0x140007fec`
- `0x140008e38`
- `0x140008ecc`
- `0x140010cc8`
- `0x140012ca0`
- `0x140013860`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140008355`
- `ntoskrnl!KeInitializeEvent` at `0x140008355`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008074`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008551`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400085e5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008074`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008551`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400085e5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400080b9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400083eb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008590`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000864f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000868d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400080b9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400083eb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008590`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000864f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000868d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400080eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400080eb`
- `ntoskrnl!RtlCopySid` at `0x14000826b`
- `ntoskrnl!RtlCopySid` at `0x1400082ab`
- `ntoskrnl!RtlCopySid` at `0x14000826b`
- `ntoskrnl!RtlCopySid` at `0x1400082ab`
- `ntoskrnl!ExSetTimer` at `0x1400083a5`
- `ntoskrnl!ExSetTimer` at `0x1400083a5`
- `ntoskrnl!KeResetEvent` at `0x14000817c`
- `ntoskrnl!KeResetEvent` at `0x14000817c`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000840e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008470`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000840e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008470`
- `ntoskrnl!KeSetEvent` at `0x140008576`
- `ntoskrnl!KeSetEvent` at `0x140008670`
- `ntoskrnl!KeSetEvent` at `0x140008576`
- `ntoskrnl!KeSetEvent` at `0x140008670`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008524`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008534`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400086b0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400086c7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008524`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008534`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400086b0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400086c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400086dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400086f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400086dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400086f3`
- `ntoskrnl!ExAllocatePool2` at `0x1400081c7`
- `ntoskrnl!ExAllocatePool2` at `0x140008237`
- `ntoskrnl!ExAllocatePool2` at `0x1400082e3`
- `ntoskrnl!ExAllocatePool2` at `0x140008310`
- `ntoskrnl!ExAllocatePool2` at `0x1400081c7`
- `ntoskrnl!ExAllocatePool2` at `0x140008237`
- `ntoskrnl!ExAllocatePool2` at `0x1400082e3`
- `ntoskrnl!ExAllocatePool2` at `0x140008310`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008063`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008540`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400085d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008063`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008540`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400085d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400080c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400083f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000859c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000865b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008699`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400080c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400083f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000859c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000865b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008699`
- `FLTMGR!FltClose` at `0x140008707`
- `FLTMGR!FltClose` at `0x140008707`

## pseudocode

```c
__int64 __fastcall BfsInsertPolicyEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        __int64 *a7)
{
  void *v7; // r13
  void *v8; // r14
  __int64 v10; // rax
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdi
  int v14; // eax
  void *Pool2; // rsi
  int v16; // r8d
  int v17; // r9d
  int inserted; // ebx
  struct _KEVENT *v20; // rcx
  int v21; // ecx
  bool v22; // cc
  NTSTATUS v23; // eax
  __int64 v24; // rax
  struct _KEVENT *v25; // rax
  _QWORD *v26; // rbx
  _QWORD *v27; // rax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  struct _FLT_INSTANCE *v31; // r14
  struct _FLT_FILTER *v32; // rsi
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  struct _KEVENT *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rdi
  _QWORD *v39; // rdx
  __int64 v40; // r8
  _QWORD *v41; // rax
  int Timeout; // [rsp+20h] [rbp-B1h]
  int Timeouta; // [rsp+20h] [rbp-B1h]
  int Timeoutb; // [rsp+20h] [rbp-B1h]
  char v45; // [rsp+30h] [rbp-A1h]
  char v46; // [rsp+31h] [rbp-A0h]
  unsigned __int64 *v47; // [rsp+38h] [rbp-99h] BYREF
  char v48; // [rsp+40h] [rbp-91h]
  int v49[2]; // [rsp+48h] [rbp-89h] BYREF
  PSID Sid; // [rsp+50h] [rbp-81h]
  PSID SourceSid; // [rsp+58h] [rbp-79h]
  __int64 v52; // [rsp+60h] [rbp-71h]
  struct _UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-69h] BYREF
  struct _UNICODE_STRING v54; // [rsp+78h] [rbp-59h] BYREF
  struct _FLT_INSTANCE *v55; // [rsp+88h] [rbp-49h]
  struct _FLT_FILTER *v56; // [rsp+90h] [rbp-41h]
  struct _EVENT_DATA_DESCRIPTOR v57; // [rsp+98h] [rbp-39h] BYREF
  unsigned __int64 **v58; // [rsp+B8h] [rbp-19h]
  __int64 v59; // [rsp+C0h] [rbp-11h]

  v7 = 0;
  SourceSid = a5;
  v8 = 0;
  Sid = a6;
  v54 = 0;
  v47 = 0;
  UnicodeString = 0;
  *(_QWORD *)v49 = 0;
  v45 = 0;
  v48 = 0;
  v46 = 0;
  v52 = a4;
  v55 = (struct _FLT_INSTANCE *)a2;
  v56 = (struct _FLT_FILTER *)a1;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a3, 0);
  v10 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
  v13 = v10;
  if ( v10 )
  {
    v14 = *(_DWORD *)(v10 + 56);
    Pool2 = 0;
    if ( (v14 & 0x10000000) != 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 144));
      ExReleasePushLockExclusiveEx(a3, 0);
      KeLeaveCriticalRegion();
      if ( *(_DWORD *)(v13 + 56) != 268435457
        || (KeWaitForSingleObject(*(PVOID *)(v13 + 40), Executive, 0, 0, 0), *(_DWORD *)(v13 + 56) == 0x10000000) )
      {
        *a7 = v13;
        return 0;
      }
      inserted = -1073741823;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v47) = -1073741823;
        v58 = &v47;
        v59 = 4;
        tlgWriteTransfer_EtwWriteTransfer(-1073741823, (int)&byte_140016D91, v16, v17, Timeouta, &v57);
      }
      goto LABEL_47;
    }
    if ( v14 == 2 )
    {
      v20 = *(struct _KEVENT **)(v13 + 40);
      *(_DWORD *)(v13 + 56) = 268435457;
      KeResetEvent(v20);
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 144));
      goto LABEL_33;
    }
    v21 = -1073741823;
    inserted = -1073741823;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_44;
    LODWORD(v47) = -1073741823;
LABEL_16:
    v59 = 4;
    v58 = &v47;
    tlgWriteTransfer_EtwWriteTransfer(v21, (int)&byte_140016D91, v11, v12, Timeout, &v57);
    goto LABEL_44;
  }
  Pool2 = (void *)ExAllocatePool2(256, 4LL * a5[1] + 8, 1400071746);
  if ( !Pool2 )
    goto LABEL_13;
  v8 = (void *)ExAllocatePool2(256, 4LL * a6[1] + 8, 1400071746);
  if ( !v8 )
  {
    v21 = dword_140019000;
    v22 = (unsigned int)dword_140019000 <= 3;
    goto LABEL_14;
  }
  v23 = RtlCopySid(4 * *((unsigned __int8 *)SourceSid + 1) + 8, Pool2, SourceSid);
  inserted = v23;
  if ( v23 < 0 )
  {
    v21 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_44;
    LODWORD(v47) = v23;
    goto LABEL_16;
  }
  inserted = RtlCopySid(4 * *((unsigned __int8 *)Sid + 1) + 8, v8, Sid);
  if ( inserted < 0 )
  {
LABEL_23:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_44;
    LODWORD(v47) = inserted;
    goto LABEL_16;
  }
  v24 = ExAllocatePool2(256, 152, 1165190722);
  v13 = v24;
  if ( !v24
    || (_InterlockedIncrement((volatile signed __int32 *)(v24 + 144)),
        v25 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1987274306),
        (*(_QWORD *)(v13 + 40) = v25) == 0) )
  {
LABEL_13:
    v22 = (unsigned int)dword_140019000 <= 3;
LABEL_14:
    inserted = -1073741801;
    if ( v22 )
      goto LABEL_44;
    LODWORD(v47) = -1073741801;
    goto LABEL_16;
  }
  *(_QWORD *)(v13 + 24) = Pool2;
  *(_QWORD *)(v13 + 32) = v8;
  *(_DWORD *)(v13 + 56) = 268435457;
  *(_DWORD *)(v13 + 104) = 0;
  *(_OWORD *)(v13 + 112) = 0;
  *(_OWORD *)(v13 + 128) = 0;
  KeInitializeEvent(v25, NotificationEvent, 0);
  inserted = BfsInsertEntryHashTable(*(_QWORD *)(a3 + 8), v52, v13);
  if ( inserted < 0 )
  {
    Pool2 = 0;
    v8 = 0;
    goto LABEL_23;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v13 + 144));
  v26 = (_QWORD *)(a3 + 16);
  if ( (_QWORD *)*v26 == v26 )
    ExSetTimer(*(_QWORD *)(a3 + 32), -300000000, 300000000, 0);
  v27 = *(_QWORD **)(a3 + 24);
  if ( (_QWORD *)*v27 != v26 )
    goto LABEL_65;
  v48 = 1;
  *(_QWORD *)(v13 + 72) = v27;
  *(_QWORD *)(v13 + 64) = v26;
  *v27 = v13 + 64;
  *(_QWORD *)(a3 + 24) = v13 + 64;
  _InterlockedExchange64((volatile __int64 *)(v13 + 96), MEMORY[0xFFFFF78000000014]);
LABEL_33:
  ExReleasePushLockExclusiveEx(a3, 0);
  KeLeaveCriticalRegion();
  inserted = RtlConvertSidToUnicodeString(&UnicodeString, SourceSid, 1u);
  if ( inserted < 0 )
    goto LABEL_34;
  v45 = 1;
  inserted = RtlConvertSidToUnicodeString(&v54, Sid, 1u);
  if ( inserted < 0 )
    goto LABEL_34;
  v31 = v55;
  v32 = v56;
  v46 = 1;
  inserted = BfsOpenPolicyDirectory((__int64)v56, (__int64)v55, (__int64)&UnicodeString, 0, (void **)v49);
  if ( inserted < 0 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v47) = inserted;
      v58 = &v47;
      v59 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v33, (int)&byte_140016D91, v34, v35, Timeoutb, &v57);
    }
    v7 = *(void **)v49;
    v8 = 0;
    Pool2 = 0;
    goto LABEL_46;
  }
  v7 = *(void **)v49;
  inserted = BfsCreateStorage(v32, v31, *(void **)v49, &v54, &v47);
  if ( inserted < 0 )
  {
LABEL_34:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v47) = inserted;
      v58 = &v47;
      v59 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v28, (int)&byte_140016D91, v29, v30, Timeout, &v57);
    }
    v8 = 0;
    Pool2 = 0;
LABEL_46:
    if ( !v13 )
    {
LABEL_48:
      if ( !v48 )
      {
LABEL_54:
        if ( v45 )
          RtlFreeUnicodeString(&UnicodeString);
        if ( v46 )
          RtlFreeUnicodeString(&v54);
        if ( Pool2 )
          ExFreePoolWithTag(Pool2, 0);
        if ( v8 )
          ExFreePoolWithTag(v8, 0);
        goto LABEL_62;
      }
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a3, 0);
      v37 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
      v38 = v37;
      if ( !v37 )
      {
        ExReleasePushLockExclusiveEx(a3, 0);
        KeLeaveCriticalRegion();
        goto LABEL_54;
      }
      v39 = (_QWORD *)(v37 + 64);
      *(_DWORD *)(v37 + 56) = 1;
      v40 = *(_QWORD *)(v37 + 64);
      if ( *(_QWORD *)(v40 + 8) == v37 + 64 )
      {
        v41 = *(_QWORD **)(v37 + 72);
        if ( (_QWORD *)*v41 == v39 )
        {
          *v41 = v40;
          *(_QWORD *)(v40 + 8) = v41;
          *v39 = 0;
          *(_QWORD *)(v38 + 72) = 0;
          ExReleasePushLockExclusiveEx(a3, 0);
          KeLeaveCriticalRegion();
          KeSetEvent(*(PRKEVENT *)(v38 + 40), 0, 0);
          BfsDereferencePolicyEntryEx((PVOID)v38);
          goto LABEL_54;
        }
      }
LABEL_65:
      __fastfail(3u);
    }
LABEL_47:
    BfsDereferencePolicyEntryEx((PVOID)v13);
    goto LABEL_48;
  }
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v54);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a3, 0);
  v36 = *(struct _KEVENT **)(v13 + 40);
  *(_QWORD *)(v13 + 48) = v47;
  *(_DWORD *)(v13 + 56) = 0x10000000;
  KeSetEvent(v36, 0, 0);
  v8 = 0;
  *a7 = v13;
  Pool2 = 0;
LABEL_44:
  ExReleasePushLockExclusiveEx(a3, 0);
  KeLeaveCriticalRegion();
  if ( inserted < 0 )
  {
    v46 = 0;
    v45 = 0;
    goto LABEL_46;
  }
LABEL_62:
  if ( v7 )
    FltClose(v7);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140007fec  push    rbp
0x140007fee  push    rbx
0x140007fef  push    rsi
0x140007ff0  push    rdi
0x140007ff1  push    r12
0x140007ff3  push    r13
0x140007ff5  push    r14
0x140007ff7  push    r15
0x140007ff9  lea     rbp, [rsp-7]
0x140007ffe  sub     rsp, 0D8h
0x140008005  mov     rax, cs:__security_cookie
0x14000800c  xor     rax, rsp
0x14000800f  mov     [rbp+3Fh+var_48], rax
0x140008013  mov     rsi, [rbp+3Fh+arg_20]
0x140008017  xor     eax, eax
0x140008019  mov     rbx, [rbp+3Fh+arg_28]
0x14000801d  xorps   xmm0, xmm0
0x140008020  mov     r12, [rbp+3Fh+arg_30]
0x140008024  mov     r13d, eax
0x140008027  mov     [rbp+3Fh+SourceSid], rsi
0x14000802b  mov     r14d, eax
0x14000802e  mov     [rsp+110h+Sid], rbx
0x140008033  mov     rdi, r9
0x140008036  movups  xmmword ptr [rbp+3Fh+var_98.Length], xmm0
0x14000803a  mov     [rsp+110h+var_D8], rax
0x14000803f  mov     r15, r8
0x140008042  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm0
0x140008046  mov     qword ptr [rsp+110h+var_C8], rax
0x14000804b  mov     [rsp+110h+var_E0], al
0x14000804f  mov     [rsp+110h+var_D0], al
0x140008053  mov     [rsp+110h+var_DF], al
0x140008057  mov     [rbp+3Fh+var_B0], r9
0x14000805b  mov     [rbp+3Fh+var_88], rdx
0x14000805f  mov     [rbp+3Fh+var_80], rcx
0x140008063  call    cs:__imp_KeEnterCriticalRegion
0x14000806a  nop     dword ptr [rax+rax+00h]
0x14000806f  xor     edx, edx
0x140008071  mov     rcx, r15
0x140008074  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000807b  nop     dword ptr [rax+rax+00h]
0x140008080  mov     rcx, [r15+8]; HashTable
0x140008084  mov     r9, rbx
0x140008087  mov     r8, rsi
0x14000808a  mov     rdx, rdi
0x14000808d  call    BfsLookupPolicyEntryHashTable
0x140008092  mov     rdi, rax
0x140008095  test    rax, rax
0x140008098  jz      loc_1400081B0
0x14000809e  mov     eax, [rax+38h]
0x1400080a1  xor     esi, esi
0x1400080a3  bt      eax, 1Ch
0x1400080a7  jnb     loc_14000816C
0x1400080ad  lock inc dword ptr [rdi+90h]
0x1400080b4  xor     edx, edx
0x1400080b6  mov     rcx, r15
0x1400080b9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400080c0  nop     dword ptr [rax+rax+00h]
0x1400080c5  call    cs:__imp_KeLeaveCriticalRegion
0x1400080cc  nop     dword ptr [rax+rax+00h]
0x1400080d1  cmp     dword ptr [rdi+38h], 10000001h
0x1400080d8  jnz     short loc_140008145
0x1400080da  mov     rcx, [rdi+28h]; Object
0x1400080de  xor     r9d, r9d; Alertable
0x1400080e1  xor     r8d, r8d; WaitMode
0x1400080e4  mov     [rsp+110h+Timeout], rsi; int
0x1400080e9  xor     edx, edx; WaitReason
0x1400080eb  call    cs:__imp_KeWaitForSingleObject
0x1400080f2  nop     dword ptr [rax+rax+00h]
0x1400080f7  cmp     dword ptr [rdi+38h], 10000000h
0x1400080fe  jz      short loc_140008145
0x140008100  mov     eax, cs:dword_140019000
0x140008106  mov     ecx, 0C0000001h; int
0x14000810b  mov     ebx, ecx
0x14000810d  cmp     eax, 3
0x140008110  jbe     loc_1400085BF
0x140008116  lea     rax, [rsp+110h+var_D8]
0x14000811b  mov     dword ptr [rsp+110h+var_D8], ecx
0x14000811f  mov     [rbp+3Fh+var_58], rax
0x140008123  lea     rdx, byte_140016D91; int
0x14000812a  lea     rax, [rbp+3Fh+var_78]
0x14000812e  mov     [rbp+3Fh+var_50], 4
0x140008136  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x14000813b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008140  jmp     loc_1400085BF
0x140008145  mov     [r12], rdi
0x140008149  xor     eax, eax
0x14000814b  mov     rcx, [rbp+3Fh+var_48]
0x14000814f  xor     rcx, rsp; StackCookie
0x140008152  call    __security_check_cookie
0x140008157  add     rsp, 0D8h
0x14000815e  pop     r15
0x140008160  pop     r14
0x140008162  pop     r13
0x140008164  pop     r12
0x140008166  pop     rdi
0x140008167  pop     rsi
0x140008168  pop     rbx
0x140008169  pop     rbp
0x14000816a  retn
0x14000816c  cmp     eax, 2
0x14000816f  jnz     short loc_140008194
0x140008171  mov     rcx, [rdi+28h]; Event
0x140008175  mov     dword ptr [rdi+38h], 10000001h
0x14000817c  call    cs:__imp_KeResetEvent
0x140008183  nop     dword ptr [rax+rax+00h]
0x140008188  lock inc dword ptr [rdi+90h]
0x14000818f  jmp     loc_1400083E6
0x140008194  mov     eax, cs:dword_140019000
0x14000819a  mov     ecx, 0C0000001h
0x14000819f  mov     ebx, ecx
0x1400081a1  cmp     eax, 3
0x1400081a4  jbe     loc_14000858B
0x1400081aa  mov     dword ptr [rsp+110h+var_D8], ecx
0x1400081ae  jmp     short loc_1400081F5
0x1400081b0  movzx   edx, byte ptr [rsi+1]
0x1400081b4  mov     ecx, 100h
0x1400081b9  mov     r8d, 53736642h
0x1400081bf  lea     rdx, ds:8[rdx*4]
0x1400081c7  call    cs:__imp_ExAllocatePool2
0x1400081ce  nop     dword ptr [rax+rax+00h]
0x1400081d3  mov     rsi, rax
0x1400081d6  test    rax, rax
0x1400081d9  jnz     short loc_140008220
0x1400081db  mov     eax, cs:dword_140019000
0x1400081e1  cmp     eax, 3
0x1400081e4  mov     edx, 0C0000017h
0x1400081e9  mov     ebx, edx
0x1400081eb  jbe     loc_14000858B
0x1400081f1  mov     dword ptr [rsp+110h+var_D8], edx
0x1400081f5  lea     rax, [rsp+110h+var_D8]
0x1400081fa  mov     [rbp+3Fh+var_50], 4
0x140008202  mov     [rbp+3Fh+var_58], rax
0x140008206  lea     rdx, byte_140016D91; int
0x14000820d  lea     rax, [rbp+3Fh+var_78]
0x140008211  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x140008216  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000821b  jmp     loc_14000858B
0x140008220  movzx   edx, byte ptr [rbx+1]
0x140008224  mov     ecx, 100h
0x140008229  mov     r8d, 53736642h
0x14000822f  lea     rdx, ds:8[rdx*4]
0x140008237  call    cs:__imp_ExAllocatePool2
0x14000823e  nop     dword ptr [rax+rax+00h]
0x140008243  mov     r14, rax
0x140008246  test    rax, rax
0x140008249  jnz     short loc_140008256
0x14000824b  mov     ecx, cs:dword_140019000
0x140008251  cmp     ecx, 3
0x140008254  jmp     short loc_1400081E4
0x140008256  mov     rax, [rbp+3Fh+SourceSid]
0x14000825a  mov     rdx, rsi; DestinationSid
0x14000825d  mov     r8, rax; SourceSid
0x140008260  movzx   ecx, byte ptr [rax+1]
0x140008264  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000826b  call    cs:__imp_RtlCopySid
0x140008272  nop     dword ptr [rax+rax+00h]
0x140008277  mov     ebx, eax
0x140008279  test    eax, eax
0x14000827b  jns     short loc_140008295
0x14000827d  mov     ecx, cs:dword_140019000
0x140008283  cmp     ecx, 3
0x140008286  jbe     loc_14000858B
0x14000828c  mov     dword ptr [rsp+110h+var_D8], eax
0x140008290  jmp     loc_1400081F5
0x140008295  mov     rax, [rsp+110h+Sid]
0x14000829a  mov     rdx, r14; DestinationSid
0x14000829d  mov     r8, rax; SourceSid
0x1400082a0  movzx   ecx, byte ptr [rax+1]
0x1400082a4  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x1400082ab  call    cs:__imp_RtlCopySid
0x1400082b2  nop     dword ptr [rax+rax+00h]
0x1400082b7  mov     ebx, eax
0x1400082b9  test    eax, eax
0x1400082bb  jns     short loc_1400082D5
0x1400082bd  mov     eax, cs:dword_140019000
0x1400082c3  cmp     eax, 3
0x1400082c6  jbe     loc_14000858B
0x1400082cc  mov     dword ptr [rsp+110h+var_D8], ebx
0x1400082d0  jmp     loc_1400081F5
0x1400082d5  mov     edx, 98h
0x1400082da  mov     r8d, 45736642h
0x1400082e0  lea     ecx, [rdx+68h]
0x1400082e3  call    cs:__imp_ExAllocatePool2
0x1400082ea  nop     dword ptr [rax+rax+00h]
0x1400082ef  mov     rdi, rax
0x1400082f2  test    rax, rax
0x1400082f5  jz      loc_1400081DB
0x1400082fb  lock inc dword ptr [rax+90h]
0x140008302  mov     edx, 18h
0x140008307  mov     r8d, 76736642h
0x14000830d  lea     ecx, [rdx+28h]
0x140008310  call    cs:__imp_ExAllocatePool2
0x140008317  nop     dword ptr [rax+rax+00h]
0x14000831c  mov     [rdi+28h], rax
0x140008320  test    rax, rax
0x140008323  jz      loc_1400081DB
0x140008329  mov     [rdi+18h], rsi
0x14000832d  xorps   xmm0, xmm0
0x140008330  mov     [rdi+20h], r14
0x140008334  xorps   xmm1, xmm1
0x140008337  mov     dword ptr [rdi+38h], 10000001h
0x14000833e  xor     r8d, r8d; State
0x140008341  mov     [rdi+68h], r13d
0x140008345  xor     edx, edx; Type
0x140008347  movups  xmmword ptr [rdi+70h], xmm0
0x14000834b  mov     rcx, rax; Event
0x14000834e  movups  xmmword ptr [rdi+80h], xmm1
0x140008355  call    cs:__imp_KeInitializeEvent
0x14000835c  nop     dword ptr [rax+rax+00h]
0x140008361  mov     rdx, [rbp+3Fh+var_B0]
0x140008365  mov     r8, rdi
0x140008368  mov     rcx, [r15+8]
0x14000836c  call    BfsInsertEntryHashTable
0x140008371  mov     ebx, eax
0x140008373  test    eax, eax
0x140008375  jns     short loc_140008381
0x140008377  xor     esi, esi
0x140008379  xor     r14d, r14d
0x14000837c  jmp     loc_1400082BD
0x140008381  lock inc dword ptr [rdi+90h]
0x140008388  lea     rbx, [r15+10h]
0x14000838c  cmp     [rbx], rbx
0x14000838f  jnz     short loc_1400083B1
0x140008391  mov     rcx, [r15+20h]
0x140008395  xor     r9d, r9d
0x140008398  mov     rdx, 0FFFFFFFFEE1E5D00h
0x14000839f  mov     r8d, 11E1A300h
0x1400083a5  call    cs:__imp_ExSetTimer
0x1400083ac  nop     dword ptr [rax+rax+00h]
0x1400083b1  mov     rax, [rbx+8]
0x1400083b5  cmp     [rax], rbx
0x1400083b8  jnz     loc_14000871A
0x1400083be  lea     rcx, [rdi+40h]
0x1400083c2  mov     [rsp+110h+var_D0], 1
0x1400083c7  mov     [rcx+8], rax
0x1400083cb  mov     [rcx], rbx
0x1400083ce  mov     [rax], rcx
0x1400083d1  mov     rax, 0FFFFF78000000014h
0x1400083db  mov     [rbx+8], rcx
0x1400083df  mov     rax, [rax]
0x1400083e2  xchg    rax, [rcx+20h]
0x1400083e6  xor     edx, edx
0x1400083e8  mov     rcx, r15
0x1400083eb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400083f2  nop     dword ptr [rax+rax+00h]
0x1400083f7  call    cs:__imp_KeLeaveCriticalRegion
0x1400083fe  nop     dword ptr [rax+rax+00h]
0x140008403  mov     rdx, [rbp+3Fh+SourceSid]; Sid
0x140008407  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x14000840b  mov     r8b, 1; AllocateDestinationString
0x14000840e  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008415  nop     dword ptr [rax+rax+00h]
0x14000841a  mov     ebx, eax
0x14000841c  test    eax, eax
0x14000841e  jns     short loc_14000845F
0x140008420  mov     eax, cs:dword_140019000
0x140008426  cmp     eax, 3
0x140008429  jbe     short loc_140008455
0x14000842b  lea     rax, [rsp+110h+var_D8]
0x140008430  mov     dword ptr [rsp+110h+var_D8], ebx
0x140008434  mov     [rbp+3Fh+var_58], rax
0x140008438  lea     rdx, byte_140016D91; int
0x14000843f  lea     rax, [rbp+3Fh+var_78]
0x140008443  mov     [rbp+3Fh+var_50], 4
0x14000844b  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x140008450  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008455  xor     r14d, r14d
0x140008458  xor     esi, esi
0x14000845a  jmp     loc_1400085BA
0x14000845f  mov     rdx, [rsp+110h+Sid]; Sid
0x140008464  lea     rcx, [rbp+3Fh+var_98]; UnicodeString
0x140008468  mov     r8b, 1; AllocateDestinationString
0x14000846b  mov     [rsp+110h+var_E0], 1
0x140008470  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008477  nop     dword ptr [rax+rax+00h]
0x14000847c  mov     ebx, eax
0x14000847e  test    eax, eax
0x140008480  js      short loc_140008420
0x140008482  mov     r14, [rbp+3Fh+var_88]
0x140008486  lea     rax, [rsp+110h+var_C8]
0x14000848b  mov     rsi, [rbp+3Fh+var_80]
0x14000848f  lea     r8, [rbp+3Fh+UnicodeString]
0x140008493  mov     rdx, r14
0x140008496  mov     [rsp+110h+var_DF], 1
0x14000849b  mov     rcx, rsi
0x14000849e  mov     [rsp+110h+Timeout], rax; int
0x1400084a3  xor     r9d, r9d
0x1400084a6  call    BfsOpenPolicyDirectory
0x1400084ab  mov     ebx, eax
0x1400084ad  test    eax, eax
0x1400084af  jns     short loc_1400084F5
0x1400084b1  mov     eax, cs:dword_140019000
0x1400084b7  cmp     eax, 3
0x1400084ba  jbe     short loc_1400084E6
0x1400084bc  lea     rax, [rsp+110h+var_D8]
0x1400084c1  mov     dword ptr [rsp+110h+var_D8], ebx
0x1400084c5  mov     [rbp+3Fh+var_58], rax
0x1400084c9  lea     rdx, byte_140016D91; int
0x1400084d0  lea     rax, [rbp+3Fh+var_78]
0x1400084d4  mov     [rbp+3Fh+var_50], 4
  ... truncated ...
```
