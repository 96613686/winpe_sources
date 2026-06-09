# BfsInsertPolicyEntry

- ea: `0x140007e5c`
- end: `0x140008591`
- name: `BfsInsertPolicyEntry`
- size: `1845`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007044`

## callees

- `0x140001008`
- `0x140006040`
- `0x140007e5c`
- `0x140008ca8`
- `0x140008d3c`
- `0x140010b30`
- `0x140012b68`
- `0x140013730`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400081c5`
- `ntoskrnl!KeInitializeEvent` at `0x1400081c5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140007ee4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400083c1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008455`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140007ee4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400083c1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008455`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007f29`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000825b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008400`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400084bf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400084fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007f29`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000825b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008400`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400084bf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400084fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007f5b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007f5b`
- `ntoskrnl!RtlCopySid` at `0x1400080db`
- `ntoskrnl!RtlCopySid` at `0x14000811b`
- `ntoskrnl!RtlCopySid` at `0x1400080db`
- `ntoskrnl!RtlCopySid` at `0x14000811b`
- `ntoskrnl!ExSetTimer` at `0x140008215`
- `ntoskrnl!ExSetTimer` at `0x140008215`
- `ntoskrnl!KeResetEvent` at `0x140007fec`
- `ntoskrnl!KeResetEvent` at `0x140007fec`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000827e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400082e0`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000827e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400082e0`
- `ntoskrnl!KeSetEvent` at `0x1400083e6`
- `ntoskrnl!KeSetEvent` at `0x1400084e0`
- `ntoskrnl!KeSetEvent` at `0x1400083e6`
- `ntoskrnl!KeSetEvent` at `0x1400084e0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008394`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400083a4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008520`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008537`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008394`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400083a4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008520`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008537`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000854d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008563`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000854d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008563`
- `ntoskrnl!ExAllocatePool2` at `0x140008037`
- `ntoskrnl!ExAllocatePool2` at `0x1400080a7`
- `ntoskrnl!ExAllocatePool2` at `0x140008153`
- `ntoskrnl!ExAllocatePool2` at `0x140008180`
- `ntoskrnl!ExAllocatePool2` at `0x140008037`
- `ntoskrnl!ExAllocatePool2` at `0x1400080a7`
- `ntoskrnl!ExAllocatePool2` at `0x140008153`
- `ntoskrnl!ExAllocatePool2` at `0x140008180`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007ed3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400083b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008444`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007ed3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400083b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008444`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007f35`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008267`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000840c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400084cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008509`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007f35`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008267`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000840c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400084cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008509`
- `FLTMGR!FltClose` at `0x140008577`
- `FLTMGR!FltClose` at `0x140008577`

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
  NTSTATUS inserted; // ebx
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
  int v31; // r14d
  int v32; // esi
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
  __int64 v47; // [rsp+38h] [rbp-99h] BYREF
  char v48; // [rsp+40h] [rbp-91h]
  int v49[2]; // [rsp+48h] [rbp-89h] BYREF
  PSID Sid; // [rsp+50h] [rbp-81h]
  PSID SourceSid; // [rsp+58h] [rbp-79h]
  __int64 v52; // [rsp+60h] [rbp-71h]
  struct _UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-69h] BYREF
  struct _UNICODE_STRING v54; // [rsp+78h] [rbp-59h] BYREF
  __int64 v55; // [rsp+88h] [rbp-49h]
  __int64 v56; // [rsp+90h] [rbp-41h]
  struct _EVENT_DATA_DESCRIPTOR v57; // [rsp+98h] [rbp-39h] BYREF
  __int64 *v58; // [rsp+B8h] [rbp-19h]
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
  v55 = a2;
  v56 = a1;
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
  inserted = BfsOpenPolicyDirectory(v56, v55, (unsigned int)&UnicodeString, 0, (__int64)v49);
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
  inserted = BfsCreateStorage(v32, v31, v49[0], (unsigned int)&v54, (__int64)&v47);
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
0x140007e5c  push    rbp
0x140007e5e  push    rbx
0x140007e5f  push    rsi
0x140007e60  push    rdi
0x140007e61  push    r12
0x140007e63  push    r13
0x140007e65  push    r14
0x140007e67  push    r15
0x140007e69  lea     rbp, [rsp-7]
0x140007e6e  sub     rsp, 0D8h
0x140007e75  mov     rax, cs:__security_cookie
0x140007e7c  xor     rax, rsp
0x140007e7f  mov     [rbp+3Fh+var_48], rax
0x140007e83  mov     rsi, [rbp+3Fh+arg_20]
0x140007e87  xor     eax, eax
0x140007e89  mov     rbx, [rbp+3Fh+arg_28]
0x140007e8d  xorps   xmm0, xmm0
0x140007e90  mov     r12, [rbp+3Fh+arg_30]
0x140007e94  mov     r13d, eax
0x140007e97  mov     [rbp+3Fh+SourceSid], rsi
0x140007e9b  mov     r14d, eax
0x140007e9e  mov     [rsp+110h+Sid], rbx
0x140007ea3  mov     rdi, r9
0x140007ea6  movups  xmmword ptr [rbp+3Fh+var_98.Length], xmm0
0x140007eaa  mov     [rsp+110h+var_D8], rax
0x140007eaf  mov     r15, r8
0x140007eb2  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm0
0x140007eb6  mov     qword ptr [rsp+110h+var_C8], rax
0x140007ebb  mov     [rsp+110h+var_E0], al
0x140007ebf  mov     [rsp+110h+var_D0], al
0x140007ec3  mov     [rsp+110h+var_DF], al
0x140007ec7  mov     [rbp+3Fh+var_B0], r9
0x140007ecb  mov     [rbp+3Fh+var_88], rdx
0x140007ecf  mov     [rbp+3Fh+var_80], rcx
0x140007ed3  call    cs:__imp_KeEnterCriticalRegion
0x140007eda  nop     dword ptr [rax+rax+00h]
0x140007edf  xor     edx, edx
0x140007ee1  mov     rcx, r15
0x140007ee4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140007eeb  nop     dword ptr [rax+rax+00h]
0x140007ef0  mov     rcx, [r15+8]; HashTable
0x140007ef4  mov     r9, rbx
0x140007ef7  mov     r8, rsi
0x140007efa  mov     rdx, rdi
0x140007efd  call    BfsLookupPolicyEntryHashTable
0x140007f02  mov     rdi, rax
0x140007f05  test    rax, rax
0x140007f08  jz      loc_140008020
0x140007f0e  mov     eax, [rax+38h]
0x140007f11  xor     esi, esi
0x140007f13  bt      eax, 1Ch
0x140007f17  jnb     loc_140007FDC
0x140007f1d  lock inc dword ptr [rdi+90h]
0x140007f24  xor     edx, edx
0x140007f26  mov     rcx, r15
0x140007f29  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140007f30  nop     dword ptr [rax+rax+00h]
0x140007f35  call    cs:__imp_KeLeaveCriticalRegion
0x140007f3c  nop     dword ptr [rax+rax+00h]
0x140007f41  cmp     dword ptr [rdi+38h], 10000001h
0x140007f48  jnz     short loc_140007FB5
0x140007f4a  mov     rcx, [rdi+28h]; Object
0x140007f4e  xor     r9d, r9d; Alertable
0x140007f51  xor     r8d, r8d; WaitMode
0x140007f54  mov     [rsp+110h+Timeout], rsi; int
0x140007f59  xor     edx, edx; WaitReason
0x140007f5b  call    cs:__imp_KeWaitForSingleObject
0x140007f62  nop     dword ptr [rax+rax+00h]
0x140007f67  cmp     dword ptr [rdi+38h], 10000000h
0x140007f6e  jz      short loc_140007FB5
0x140007f70  mov     eax, cs:dword_140019000
0x140007f76  mov     ecx, 0C0000001h; int
0x140007f7b  mov     ebx, ecx
0x140007f7d  cmp     eax, 3
0x140007f80  jbe     loc_14000842F
0x140007f86  lea     rax, [rsp+110h+var_D8]
0x140007f8b  mov     dword ptr [rsp+110h+var_D8], ecx
0x140007f8f  mov     [rbp+3Fh+var_58], rax
0x140007f93  lea     rdx, byte_140016D91; int
0x140007f9a  lea     rax, [rbp+3Fh+var_78]
0x140007f9e  mov     [rbp+3Fh+var_50], 4
0x140007fa6  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x140007fab  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007fb0  jmp     loc_14000842F
0x140007fb5  mov     [r12], rdi
0x140007fb9  xor     eax, eax
0x140007fbb  mov     rcx, [rbp+3Fh+var_48]
0x140007fbf  xor     rcx, rsp; StackCookie
0x140007fc2  call    __security_check_cookie
0x140007fc7  add     rsp, 0D8h
0x140007fce  pop     r15
0x140007fd0  pop     r14
0x140007fd2  pop     r13
0x140007fd4  pop     r12
0x140007fd6  pop     rdi
0x140007fd7  pop     rsi
0x140007fd8  pop     rbx
0x140007fd9  pop     rbp
0x140007fda  retn
0x140007fdc  cmp     eax, 2
0x140007fdf  jnz     short loc_140008004
0x140007fe1  mov     rcx, [rdi+28h]; Event
0x140007fe5  mov     dword ptr [rdi+38h], 10000001h
0x140007fec  call    cs:__imp_KeResetEvent
0x140007ff3  nop     dword ptr [rax+rax+00h]
0x140007ff8  lock inc dword ptr [rdi+90h]
0x140007fff  jmp     loc_140008256
0x140008004  mov     eax, cs:dword_140019000
0x14000800a  mov     ecx, 0C0000001h
0x14000800f  mov     ebx, ecx
0x140008011  cmp     eax, 3
0x140008014  jbe     loc_1400083FB
0x14000801a  mov     dword ptr [rsp+110h+var_D8], ecx
0x14000801e  jmp     short loc_140008065
0x140008020  movzx   edx, byte ptr [rsi+1]
0x140008024  mov     ecx, 100h
0x140008029  mov     r8d, 53736642h
0x14000802f  lea     rdx, ds:8[rdx*4]
0x140008037  call    cs:__imp_ExAllocatePool2
0x14000803e  nop     dword ptr [rax+rax+00h]
0x140008043  mov     rsi, rax
0x140008046  test    rax, rax
0x140008049  jnz     short loc_140008090
0x14000804b  mov     eax, cs:dword_140019000
0x140008051  cmp     eax, 3
0x140008054  mov     edx, 0C0000017h
0x140008059  mov     ebx, edx
0x14000805b  jbe     loc_1400083FB
0x140008061  mov     dword ptr [rsp+110h+var_D8], edx
0x140008065  lea     rax, [rsp+110h+var_D8]
0x14000806a  mov     [rbp+3Fh+var_50], 4
0x140008072  mov     [rbp+3Fh+var_58], rax
0x140008076  lea     rdx, byte_140016D91; int
0x14000807d  lea     rax, [rbp+3Fh+var_78]
0x140008081  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x140008086  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000808b  jmp     loc_1400083FB
0x140008090  movzx   edx, byte ptr [rbx+1]
0x140008094  mov     ecx, 100h
0x140008099  mov     r8d, 53736642h
0x14000809f  lea     rdx, ds:8[rdx*4]
0x1400080a7  call    cs:__imp_ExAllocatePool2
0x1400080ae  nop     dword ptr [rax+rax+00h]
0x1400080b3  mov     r14, rax
0x1400080b6  test    rax, rax
0x1400080b9  jnz     short loc_1400080C6
0x1400080bb  mov     ecx, cs:dword_140019000
0x1400080c1  cmp     ecx, 3
0x1400080c4  jmp     short loc_140008054
0x1400080c6  mov     rax, [rbp+3Fh+SourceSid]
0x1400080ca  mov     rdx, rsi; DestinationSid
0x1400080cd  mov     r8, rax; SourceSid
0x1400080d0  movzx   ecx, byte ptr [rax+1]
0x1400080d4  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x1400080db  call    cs:__imp_RtlCopySid
0x1400080e2  nop     dword ptr [rax+rax+00h]
0x1400080e7  mov     ebx, eax
0x1400080e9  test    eax, eax
0x1400080eb  jns     short loc_140008105
0x1400080ed  mov     ecx, cs:dword_140019000
0x1400080f3  cmp     ecx, 3
0x1400080f6  jbe     loc_1400083FB
0x1400080fc  mov     dword ptr [rsp+110h+var_D8], eax
0x140008100  jmp     loc_140008065
0x140008105  mov     rax, [rsp+110h+Sid]
0x14000810a  mov     rdx, r14; DestinationSid
0x14000810d  mov     r8, rax; SourceSid
0x140008110  movzx   ecx, byte ptr [rax+1]
0x140008114  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000811b  call    cs:__imp_RtlCopySid
0x140008122  nop     dword ptr [rax+rax+00h]
0x140008127  mov     ebx, eax
0x140008129  test    eax, eax
0x14000812b  jns     short loc_140008145
0x14000812d  mov     eax, cs:dword_140019000
0x140008133  cmp     eax, 3
0x140008136  jbe     loc_1400083FB
0x14000813c  mov     dword ptr [rsp+110h+var_D8], ebx
0x140008140  jmp     loc_140008065
0x140008145  mov     edx, 98h
0x14000814a  mov     r8d, 45736642h
0x140008150  lea     ecx, [rdx+68h]
0x140008153  call    cs:__imp_ExAllocatePool2
0x14000815a  nop     dword ptr [rax+rax+00h]
0x14000815f  mov     rdi, rax
0x140008162  test    rax, rax
0x140008165  jz      loc_14000804B
0x14000816b  lock inc dword ptr [rax+90h]
0x140008172  mov     edx, 18h
0x140008177  mov     r8d, 76736642h
0x14000817d  lea     ecx, [rdx+28h]
0x140008180  call    cs:__imp_ExAllocatePool2
0x140008187  nop     dword ptr [rax+rax+00h]
0x14000818c  mov     [rdi+28h], rax
0x140008190  test    rax, rax
0x140008193  jz      loc_14000804B
0x140008199  mov     [rdi+18h], rsi
0x14000819d  xorps   xmm0, xmm0
0x1400081a0  mov     [rdi+20h], r14
0x1400081a4  xorps   xmm1, xmm1
0x1400081a7  mov     dword ptr [rdi+38h], 10000001h
0x1400081ae  xor     r8d, r8d; State
0x1400081b1  mov     [rdi+68h], r13d
0x1400081b5  xor     edx, edx; Type
0x1400081b7  movups  xmmword ptr [rdi+70h], xmm0
0x1400081bb  mov     rcx, rax; Event
0x1400081be  movups  xmmword ptr [rdi+80h], xmm1
0x1400081c5  call    cs:__imp_KeInitializeEvent
0x1400081cc  nop     dword ptr [rax+rax+00h]
0x1400081d1  mov     rdx, [rbp+3Fh+var_B0]
0x1400081d5  mov     r8, rdi
0x1400081d8  mov     rcx, [r15+8]
0x1400081dc  call    BfsInsertEntryHashTable
0x1400081e1  mov     ebx, eax
0x1400081e3  test    eax, eax
0x1400081e5  jns     short loc_1400081F1
0x1400081e7  xor     esi, esi
0x1400081e9  xor     r14d, r14d
0x1400081ec  jmp     loc_14000812D
0x1400081f1  lock inc dword ptr [rdi+90h]
0x1400081f8  lea     rbx, [r15+10h]
0x1400081fc  cmp     [rbx], rbx
0x1400081ff  jnz     short loc_140008221
0x140008201  mov     rcx, [r15+20h]
0x140008205  xor     r9d, r9d
0x140008208  mov     rdx, 0FFFFFFFFEE1E5D00h
0x14000820f  mov     r8d, 11E1A300h
0x140008215  call    cs:__imp_ExSetTimer
0x14000821c  nop     dword ptr [rax+rax+00h]
0x140008221  mov     rax, [rbx+8]
0x140008225  cmp     [rax], rbx
0x140008228  jnz     loc_14000858A
0x14000822e  lea     rcx, [rdi+40h]
0x140008232  mov     [rsp+110h+var_D0], 1
0x140008237  mov     [rcx+8], rax
0x14000823b  mov     [rcx], rbx
0x14000823e  mov     [rax], rcx
0x140008241  mov     rax, 0FFFFF78000000014h
0x14000824b  mov     [rbx+8], rcx
0x14000824f  mov     rax, [rax]
0x140008252  xchg    rax, [rcx+20h]
0x140008256  xor     edx, edx
0x140008258  mov     rcx, r15
0x14000825b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140008262  nop     dword ptr [rax+rax+00h]
0x140008267  call    cs:__imp_KeLeaveCriticalRegion
0x14000826e  nop     dword ptr [rax+rax+00h]
0x140008273  mov     rdx, [rbp+3Fh+SourceSid]; Sid
0x140008277  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x14000827b  mov     r8b, 1; AllocateDestinationString
0x14000827e  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008285  nop     dword ptr [rax+rax+00h]
0x14000828a  mov     ebx, eax
0x14000828c  test    eax, eax
0x14000828e  jns     short loc_1400082CF
0x140008290  mov     eax, cs:dword_140019000
0x140008296  cmp     eax, 3
0x140008299  jbe     short loc_1400082C5
0x14000829b  lea     rax, [rsp+110h+var_D8]
0x1400082a0  mov     dword ptr [rsp+110h+var_D8], ebx
0x1400082a4  mov     [rbp+3Fh+var_58], rax
0x1400082a8  lea     rdx, byte_140016D91; int
0x1400082af  lea     rax, [rbp+3Fh+var_78]
0x1400082b3  mov     [rbp+3Fh+var_50], 4
0x1400082bb  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x1400082c0  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400082c5  xor     r14d, r14d
0x1400082c8  xor     esi, esi
0x1400082ca  jmp     loc_14000842A
0x1400082cf  mov     rdx, [rsp+110h+Sid]; Sid
0x1400082d4  lea     rcx, [rbp+3Fh+var_98]; UnicodeString
0x1400082d8  mov     r8b, 1; AllocateDestinationString
0x1400082db  mov     [rsp+110h+var_E0], 1
0x1400082e0  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400082e7  nop     dword ptr [rax+rax+00h]
0x1400082ec  mov     ebx, eax
0x1400082ee  test    eax, eax
0x1400082f0  js      short loc_140008290
0x1400082f2  mov     r14, [rbp+3Fh+var_88]
0x1400082f6  lea     rax, [rsp+110h+var_C8]
0x1400082fb  mov     rsi, [rbp+3Fh+var_80]
0x1400082ff  lea     r8, [rbp+3Fh+UnicodeString]
0x140008303  mov     rdx, r14
0x140008306  mov     [rsp+110h+var_DF], 1
0x14000830b  mov     rcx, rsi
0x14000830e  mov     [rsp+110h+Timeout], rax; int
0x140008313  xor     r9d, r9d
0x140008316  call    BfsOpenPolicyDirectory
0x14000831b  mov     ebx, eax
0x14000831d  test    eax, eax
0x14000831f  jns     short loc_140008365
0x140008321  mov     eax, cs:dword_140019000
0x140008327  cmp     eax, 3
0x14000832a  jbe     short loc_140008356
0x14000832c  lea     rax, [rsp+110h+var_D8]
0x140008331  mov     dword ptr [rsp+110h+var_D8], ebx
0x140008335  mov     [rbp+3Fh+var_58], rax
0x140008339  lea     rdx, byte_140016D91; int
0x140008340  lea     rax, [rbp+3Fh+var_78]
0x140008344  mov     [rbp+3Fh+var_50], 4
  ... truncated ...
```
