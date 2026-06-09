# BfsInsertPolicyEntryLocked

- ea: `0x140008598`
- end: `0x140008c9f`
- name: `BfsInsertPolicyEntryLocked`
- size: `1799`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007250`

## callees

- `0x140001008`
- `0x140006040`
- `0x140008598`
- `0x140008ca8`
- `0x140008d3c`
- `0x140010b30`
- `0x140012b68`
- `0x140013730`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140008983`
- `ntoskrnl!KeInitializeEvent` at `0x140008983`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000865f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000865f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008691`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008691`
- `ntoskrnl!RtlCopySid` at `0x140008844`
- `ntoskrnl!RtlCopySid` at `0x140008880`
- `ntoskrnl!RtlCopySid` at `0x140008844`
- `ntoskrnl!RtlCopySid` at `0x140008880`
- `ntoskrnl!ExSetTimer` at `0x1400089ea`
- `ntoskrnl!ExSetTimer` at `0x1400089ea`
- `ntoskrnl!KeResetEvent` at `0x140008728`
- `ntoskrnl!KeResetEvent` at `0x140008728`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008a36`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008a5c`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008a36`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008a5c`
- `ntoskrnl!KeSetEvent` at `0x140008bc3`
- `ntoskrnl!KeSetEvent` at `0x140008c6e`
- `ntoskrnl!KeSetEvent` at `0x140008bc3`
- `ntoskrnl!KeSetEvent` at `0x140008c6e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008be4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008bfb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008c39`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008c49`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008be4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008bfb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008c39`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008c49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c27`
- `ntoskrnl!ExAllocatePool2` at `0x14000879f`
- `ntoskrnl!ExAllocatePool2` at `0x14000880d`
- `ntoskrnl!ExAllocatePool2` at `0x1400088b5`
- `ntoskrnl!ExAllocatePool2` at `0x140008923`
- `ntoskrnl!ExAllocatePool2` at `0x14000879f`
- `ntoskrnl!ExAllocatePool2` at `0x14000880d`
- `ntoskrnl!ExAllocatePool2` at `0x1400088b5`
- `ntoskrnl!ExAllocatePool2` at `0x140008923`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000866b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000866b`
- `FLTMGR!FltClose` at `0x140008c85`
- `FLTMGR!FltClose` at `0x140008c85`

## pseudocode

```c
__int64 __fastcall BfsInsertPolicyEntryLocked(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        _DWORD *a7,
        __int64 *a8)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v10; // rcx
  void *v11; // r12
  __int64 v12; // rax
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rdi
  int v16; // eax
  void *Pool2; // r14
  void *v18; // rsi
  int v19; // r8d
  int v20; // r9d
  NTSTATUS inserted; // ebx
  struct _KEVENT *v23; // rcx
  int v24; // ecx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // r8d
  int v29; // r9d
  int v30; // ecx
  bool v31; // cc
  NTSTATUS v32; // eax
  __int64 v33; // rax
  struct _KEVENT *v34; // rax
  __int64 v35; // rsi
  _QWORD *v36; // rbx
  _QWORD *v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  __int64 v44; // rax
  _QWORD *v45; // rdi
  _QWORD *v46; // rax
  __int64 v47; // rcx
  _QWORD *v48; // r8
  struct _KEVENT *v49; // rcx
  struct _KEVENT *v50; // rcx
  int Timeout; // [rsp+20h] [rbp-A9h]
  int Timeouta; // [rsp+20h] [rbp-A9h]
  int Timeoutb; // [rsp+20h] [rbp-A9h]
  int v54[2]; // [rsp+30h] [rbp-99h] BYREF
  char v55; // [rsp+38h] [rbp-91h]
  char v56; // [rsp+39h] [rbp-90h]
  char v57; // [rsp+3Ah] [rbp-8Fh]
  _DWORD *v58; // [rsp+40h] [rbp-89h]
  int v59[2]; // [rsp+48h] [rbp-81h] BYREF
  PSID Sid; // [rsp+50h] [rbp-79h]
  PSID SourceSid; // [rsp+58h] [rbp-71h]
  __int64 v62; // [rsp+60h] [rbp-69h]
  __int64 v63; // [rsp+68h] [rbp-61h]
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-59h] BYREF
  struct _UNICODE_STRING v65; // [rsp+80h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v66; // [rsp+90h] [rbp-39h] BYREF
  int *v67; // [rsp+B0h] [rbp-19h]
  __int64 v68; // [rsp+B8h] [rbp-11h]

  v10 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a3 + 8);
  v58 = a7;
  v62 = a4;
  v63 = a3;
  SourceSid = a5;
  v11 = 0;
  Sid = a6;
  v65 = 0;
  *(_QWORD *)v54 = 0;
  UnicodeString = 0;
  *(_QWORD *)v59 = 0;
  v56 = 0;
  v55 = 0;
  v57 = 0;
  v12 = BfsLookupPolicyEntryHashTable(v10);
  v15 = v12;
  if ( !v12 )
  {
    Pool2 = (void *)ExAllocatePool2(256, 4LL * a5[1] + 8, 1400071746);
    if ( !Pool2 )
    {
      inserted = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v54[0] = -1073741801;
        v67 = v54;
        v68 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v25, (int)&byte_140016D91, v26, v27, Timeout, &v66);
      }
      goto LABEL_64;
    }
    v18 = (void *)ExAllocatePool2(256, 4LL * a6[1] + 8, 1400071746);
    if ( !v18 )
    {
      v30 = dword_140019000;
      v31 = (unsigned int)dword_140019000 <= 3;
      goto LABEL_26;
    }
    v32 = RtlCopySid(4 * *((unsigned __int8 *)SourceSid + 1) + 8, Pool2, SourceSid);
    inserted = v32;
    if ( v32 >= 0 )
    {
      inserted = RtlCopySid(4 * *((unsigned __int8 *)Sid + 1) + 8, v18, Sid);
      if ( inserted >= 0 )
      {
        v33 = ExAllocatePool2(256, 152, 1165190722);
        v15 = v33;
        if ( v33 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v33 + 144));
          v34 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1987274306);
          *(_QWORD *)(v15 + 40) = v34;
          if ( !v34 )
          {
            inserted = -1073741801;
            if ( (unsigned int)dword_140019000 <= 3 )
              goto LABEL_49;
            v54[0] = -1073741801;
            goto LABEL_12;
          }
          *(_QWORD *)(v15 + 24) = Pool2;
          *(_QWORD *)(v15 + 32) = v18;
          *(_DWORD *)(v15 + 56) = 268435457;
          *(_DWORD *)(v15 + 104) = 0;
          *(_OWORD *)(v15 + 112) = 0;
          *(_OWORD *)(v15 + 128) = 0;
          KeInitializeEvent(v34, NotificationEvent, 0);
          v35 = v63;
          inserted = BfsInsertEntryHashTable(*(_QWORD *)(v63 + 8), v62, v15);
          if ( inserted >= 0 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v15 + 144));
            v36 = (_QWORD *)(v63 + 16);
            if ( (_QWORD *)*v36 == v36 )
              ExSetTimer(*(_QWORD *)(v63 + 32), -300000000, 300000000, 0);
            v37 = *(_QWORD **)(v63 + 24);
            if ( (_QWORD *)*v37 != v36 )
              goto LABEL_67;
            v55 = 1;
            *(_QWORD *)(v15 + 72) = v37;
            *(_QWORD *)(v15 + 64) = v36;
            *v37 = v15 + 64;
            *(_QWORD *)(v35 + 24) = v15 + 64;
            _InterlockedExchange64((volatile __int64 *)(v15 + 96), MEMORY[0xFFFFF78000000014]);
            goto LABEL_39;
          }
          Pool2 = 0;
          v18 = 0;
          if ( (unsigned int)dword_140019000 > 3 )
          {
            v54[0] = inserted;
            goto LABEL_12;
          }
LABEL_49:
          BfsDereferencePolicyEntryEx((PVOID)v15);
LABEL_50:
          if ( !v55
            || (v44 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v63 + 8)), (v45 = (_QWORD *)v44) == 0) )
          {
LABEL_55:
            if ( v56 )
              RtlFreeUnicodeString(&UnicodeString);
            if ( v57 )
              RtlFreeUnicodeString(&v65);
            if ( !Pool2 )
              goto LABEL_61;
            goto LABEL_60;
          }
          *(_DWORD *)(v44 + 56) = 1;
          v46 = (_QWORD *)(v44 + 64);
          v47 = *v46;
          if ( *(_QWORD **)(*v46 + 8LL) == v46 )
          {
            v48 = (_QWORD *)v46[1];
            if ( (_QWORD *)*v48 == v46 )
            {
              *v48 = v47;
              *(_QWORD *)(v47 + 8) = v48;
              v49 = (struct _KEVENT *)v45[5];
              *v46 = 0;
              v45[9] = 0;
              KeSetEvent(v49, 0, 0);
              BfsDereferencePolicyEntryEx(v45);
              goto LABEL_55;
            }
          }
LABEL_67:
          __fastfail(3u);
        }
        v31 = (unsigned int)dword_140019000 <= 3;
LABEL_26:
        inserted = -1073741801;
        if ( !v31 )
        {
          v54[0] = -1073741801;
          goto LABEL_28;
        }
LABEL_60:
        ExFreePoolWithTag(Pool2, 0);
LABEL_61:
        if ( v18 )
          ExFreePoolWithTag(v18, 0);
        goto LABEL_64;
      }
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_60;
      v54[0] = inserted;
    }
    else
    {
      v30 = dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_60;
      v54[0] = v32;
    }
LABEL_28:
    v68 = 4;
    v67 = v54;
    tlgWriteTransfer_EtwWriteTransfer(v30, (int)&byte_140016D91, v28, v29, Timeout, &v66);
    goto LABEL_60;
  }
  v16 = *(_DWORD *)(v12 + 56);
  Pool2 = 0;
  v18 = 0;
  if ( (v16 & 0x10000000) != 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 144));
    if ( *(_DWORD *)(v15 + 56) != 268435457
      || (ExReleasePushLockExclusiveEx(a3, 0),
          KeLeaveCriticalRegion(),
          *v58 = 0,
          KeWaitForSingleObject(*(PVOID *)(v15 + 40), Executive, 0, 0, 0),
          *(_DWORD *)(v15 + 56) == 0x10000000) )
    {
      *a8 = v15;
      return 0;
    }
    inserted = -1073741823;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v54[0] = -1073741823;
      v67 = v54;
      v68 = 4;
      tlgWriteTransfer_EtwWriteTransfer(-1073741823, (int)&byte_140016D91, v19, v20, Timeouta, &v66);
    }
    goto LABEL_49;
  }
  if ( v16 != 2 )
  {
    v24 = -1073741823;
    inserted = -1073741823;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v54[0] = -1073741823;
LABEL_12:
      v68 = 4;
      v67 = v54;
      tlgWriteTransfer_EtwWriteTransfer(v24, (int)&byte_140016D91, v13, v14, Timeout, &v66);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v23 = *(struct _KEVENT **)(v15 + 40);
  *(_DWORD *)(v15 + 56) = 268435457;
  KeResetEvent(v23);
  _InterlockedIncrement((volatile signed __int32 *)(v15 + 144));
LABEL_39:
  inserted = RtlConvertSidToUnicodeString(&UnicodeString, SourceSid, 1u);
  if ( inserted < 0 )
    goto LABEL_46;
  v56 = 1;
  inserted = RtlConvertSidToUnicodeString(&v65, Sid, 1u);
  if ( inserted < 0 )
    goto LABEL_46;
  v57 = 1;
  inserted = BfsOpenPolicyDirectory(a1, 0, (unsigned int)&UnicodeString, 0, (__int64)v59);
  if ( inserted < 0 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v54[0] = inserted;
      v67 = v54;
      v68 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v41, (int)&byte_140016D91, v42, v43, Timeoutb, &v66);
    }
    v11 = *(void **)v59;
    goto LABEL_48;
  }
  v11 = *(void **)v59;
  inserted = BfsCreateStorage(a1, 0, v59[0], (unsigned int)&v65, (__int64)v54);
  if ( inserted < 0 )
  {
LABEL_46:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v67 = v54;
      v54[0] = inserted;
      v68 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v38, (int)&byte_140016D91, v39, v40, Timeout, &v66);
    }
LABEL_48:
    v18 = 0;
    Pool2 = 0;
    if ( !v15 )
      goto LABEL_50;
    goto LABEL_49;
  }
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v65);
  v50 = *(struct _KEVENT **)(v15 + 40);
  *(_QWORD *)(v15 + 48) = *(_QWORD *)v54;
  *(_DWORD *)(v15 + 56) = 0x10000000;
  KeSetEvent(v50, 0, 0);
  *a8 = v15;
LABEL_64:
  if ( v11 )
    FltClose(v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140008598  mov     [rsp-8+arg_8], rbx
0x14000859d  push    rbp
0x14000859e  push    rsi
0x14000859f  push    rdi
0x1400085a0  push    r12
0x1400085a2  push    r13
0x1400085a4  push    r14
0x1400085a6  push    r15
0x1400085a8  lea     rbp, [rsp-7]
0x1400085ad  sub     rsp, 0D0h
0x1400085b4  mov     rax, cs:__security_cookie
0x1400085bb  xor     rax, rsp
0x1400085be  mov     [rbp+37h+var_40], rax
0x1400085c2  mov     rax, [rbp+37h+arg_30]
0x1400085c6  mov     rbx, r8
0x1400085c9  mov     r14, [rbp+37h+arg_20]
0x1400085cd  mov     r10, r9
0x1400085d0  mov     rsi, [rbp+37h+arg_28]
0x1400085d4  xorps   xmm0, xmm0
0x1400085d7  mov     r15, [rbp+37h+arg_38]
0x1400085db  mov     r13, rcx
0x1400085de  mov     rcx, [rbx+8]; HashTable
0x1400085e2  mov     r8, r14
0x1400085e5  mov     [rsp+100h+var_C0], rax
0x1400085ea  mov     rdx, r10
0x1400085ed  xor     eax, eax
0x1400085ef  mov     [rbp+37h+var_A0], r9
0x1400085f3  mov     r9, rsi
0x1400085f6  mov     [rbp+37h+var_98], rbx
0x1400085fa  mov     [rbp+37h+SourceSid], r14
0x1400085fe  mov     r12d, eax
0x140008601  mov     [rbp+37h+Sid], rsi
0x140008605  movups  xmmword ptr [rbp+37h+var_80.Length], xmm0
0x140008609  mov     qword ptr [rsp+100h+var_D0], rax
0x14000860e  movups  xmmword ptr [rbp+37h+UnicodeString.Length], xmm0
0x140008612  mov     qword ptr [rsp+100h+var_B8], rax
0x140008617  mov     [rsp+100h+var_C7], al
0x14000861b  mov     [rsp+100h+var_C8], al
0x14000861f  mov     [rsp+100h+var_C6], al
0x140008623  call    BfsLookupPolicyEntryHashTable
0x140008628  mov     rdi, rax
0x14000862b  test    rax, rax
0x14000862e  jz      loc_140008785
0x140008634  mov     eax, [rax+38h]
0x140008637  xor     r14d, r14d
0x14000863a  xor     esi, esi
0x14000863c  bt      eax, 1Ch
0x140008640  jnb     loc_140008718
0x140008646  lock inc dword ptr [rdi+90h]
0x14000864d  cmp     dword ptr [rdi+38h], 10000001h
0x140008654  jnz     loc_1400086EB
0x14000865a  xor     edx, edx
0x14000865c  mov     rcx, rbx
0x14000865f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140008666  nop     dword ptr [rax+rax+00h]
0x14000866b  call    cs:__imp_KeLeaveCriticalRegion
0x140008672  nop     dword ptr [rax+rax+00h]
0x140008677  mov     r13, [rsp+100h+var_C0]
0x14000867c  xor     r9d, r9d; Alertable
0x14000867f  xor     r8d, r8d; WaitMode
0x140008682  mov     [rsp+100h+Timeout], rsi; int
0x140008687  xor     edx, edx; WaitReason
0x140008689  mov     [r13+0], esi
0x14000868d  mov     rcx, [rdi+28h]; Object
0x140008691  call    cs:__imp_KeWaitForSingleObject
0x140008698  nop     dword ptr [rax+rax+00h]
0x14000869d  cmp     dword ptr [rdi+38h], 10000000h
0x1400086a4  jz      short loc_1400086EB
0x1400086a6  mov     eax, cs:dword_140019000
0x1400086ac  mov     ecx, 0C0000001h; int
0x1400086b1  mov     ebx, ecx
0x1400086b3  cmp     eax, 3
0x1400086b6  jbe     loc_140008B42
0x1400086bc  lea     rax, [rsp+100h+var_D0]
0x1400086c1  mov     [rsp+100h+var_D0], ecx
0x1400086c5  mov     [rbp+37h+var_50], rax
0x1400086c9  lea     rdx, byte_140016D91; int
0x1400086d0  lea     rax, [rbp+37h+var_70]
0x1400086d4  mov     [rbp+37h+var_48], 4
0x1400086dc  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x1400086e1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400086e6  jmp     loc_140008B42
0x1400086eb  mov     [r15], rdi
0x1400086ee  xor     eax, eax
0x1400086f0  mov     rcx, [rbp+37h+var_40]
0x1400086f4  xor     rcx, rsp; StackCookie
0x1400086f7  call    __security_check_cookie
0x1400086fc  mov     rbx, [rsp+100h+arg_8]
0x140008704  add     rsp, 0D0h
0x14000870b  pop     r15
0x14000870d  pop     r14
0x14000870f  pop     r13
0x140008711  pop     r12
0x140008713  pop     rdi
0x140008714  pop     rsi
0x140008715  pop     rbp
0x140008716  retn
0x140008718  cmp     eax, 2
0x14000871b  jnz     short loc_140008740
0x14000871d  mov     rcx, [rdi+28h]; Event
0x140008721  mov     dword ptr [rdi+38h], 10000001h
0x140008728  call    cs:__imp_KeResetEvent
0x14000872f  nop     dword ptr [rax+rax+00h]
0x140008734  lock inc dword ptr [rdi+90h]
0x14000873b  jmp     loc_140008A2B
0x140008740  mov     eax, cs:dword_140019000
0x140008746  mov     ecx, 0C0000001h; int
0x14000874b  mov     ebx, ecx
0x14000874d  cmp     eax, 3
0x140008750  jbe     loc_140008B3D
0x140008756  mov     [rsp+100h+var_D0], ecx
0x14000875a  lea     rax, [rsp+100h+var_D0]
0x14000875f  mov     [rbp+37h+var_48], 4
0x140008767  mov     [rbp+37h+var_50], rax
0x14000876b  lea     rdx, byte_140016D91; int
0x140008772  lea     rax, [rbp+37h+var_70]
0x140008776  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14000877b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008780  jmp     loc_140008B3D
0x140008785  movzx   edx, byte ptr [r14+1]
0x14000878a  mov     ebx, 100h
0x14000878f  mov     r8d, 53736642h
0x140008795  mov     ecx, ebx
0x140008797  lea     rdx, ds:8[rdx*4]
0x14000879f  call    cs:__imp_ExAllocatePool2
0x1400087a6  nop     dword ptr [rax+rax+00h]
0x1400087ab  mov     r14, rax
0x1400087ae  test    rax, rax
0x1400087b1  jnz     short loc_1400087F8
0x1400087b3  mov     eax, cs:dword_140019000
0x1400087b9  mov     edx, 0C0000017h
0x1400087be  mov     ebx, edx
0x1400087c0  cmp     eax, 3
0x1400087c3  jbe     loc_140008C7D
0x1400087c9  lea     rax, [rsp+100h+var_D0]
0x1400087ce  mov     [rsp+100h+var_D0], edx
0x1400087d2  mov     [rbp+37h+var_50], rax
0x1400087d6  lea     rdx, byte_140016D91; int
0x1400087dd  lea     rax, [rbp+37h+var_70]
0x1400087e1  mov     [rbp+37h+var_48], 4
0x1400087e9  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x1400087ee  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400087f3  jmp     loc_140008C7D
0x1400087f8  movzx   edx, byte ptr [rsi+1]
0x1400087fc  mov     r8d, 53736642h
0x140008802  mov     rcx, rbx
0x140008805  lea     rdx, ds:8[rdx*4]
0x14000880d  call    cs:__imp_ExAllocatePool2
0x140008814  nop     dword ptr [rax+rax+00h]
0x140008819  mov     rsi, rax
0x14000881c  test    rax, rax
0x14000881f  jnz     short loc_14000882F
0x140008821  mov     ecx, cs:dword_140019000
0x140008827  cmp     ecx, 3
0x14000882a  jmp     loc_1400088D2
0x14000882f  mov     rax, [rbp+37h+SourceSid]
0x140008833  mov     rdx, r14; DestinationSid
0x140008836  mov     r8, rax; SourceSid
0x140008839  movzx   ecx, byte ptr [rax+1]
0x14000883d  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140008844  call    cs:__imp_RtlCopySid
0x14000884b  nop     dword ptr [rax+rax+00h]
0x140008850  mov     ebx, eax
0x140008852  test    eax, eax
0x140008854  jns     short loc_14000886B
0x140008856  mov     ecx, cs:dword_140019000
0x14000885c  cmp     ecx, 3
0x14000885f  jbe     loc_140008C0C
0x140008865  mov     [rsp+100h+var_D0], eax
0x140008869  jmp     short loc_1400088E3
0x14000886b  mov     rax, [rbp+37h+Sid]
0x14000886f  mov     rdx, rsi; DestinationSid
0x140008872  mov     r8, rax; SourceSid
0x140008875  movzx   ecx, byte ptr [rax+1]
0x140008879  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140008880  call    cs:__imp_RtlCopySid
0x140008887  nop     dword ptr [rax+rax+00h]
0x14000888c  mov     ebx, eax
0x14000888e  test    eax, eax
0x140008890  jns     short loc_1400088A7
0x140008892  mov     eax, cs:dword_140019000
0x140008898  cmp     eax, 3
0x14000889b  jbe     loc_140008C0C
0x1400088a1  mov     [rsp+100h+var_D0], ebx
0x1400088a5  jmp     short loc_1400088E3
0x1400088a7  mov     edx, 98h
0x1400088ac  mov     r8d, 45736642h
0x1400088b2  lea     ecx, [rdx+68h]
0x1400088b5  call    cs:__imp_ExAllocatePool2
0x1400088bc  nop     dword ptr [rax+rax+00h]
0x1400088c1  mov     rdi, rax
0x1400088c4  test    rax, rax
0x1400088c7  jnz     short loc_14000890E
0x1400088c9  mov     eax, cs:dword_140019000
0x1400088cf  cmp     eax, 3
0x1400088d2  mov     edx, 0C0000017h
0x1400088d7  mov     ebx, edx
0x1400088d9  jbe     loc_140008C0C
0x1400088df  mov     [rsp+100h+var_D0], edx
0x1400088e3  lea     rax, [rsp+100h+var_D0]
0x1400088e8  mov     [rbp+37h+var_48], 4
0x1400088f0  mov     [rbp+37h+var_50], rax
0x1400088f4  lea     rdx, byte_140016D91; int
0x1400088fb  lea     rax, [rbp+37h+var_70]
0x1400088ff  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140008904  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008909  jmp     loc_140008C0C
0x14000890e  lock inc dword ptr [rax+90h]
0x140008915  mov     edx, 18h
0x14000891a  mov     r8d, 76736642h
0x140008920  lea     ecx, [rdx+28h]
0x140008923  call    cs:__imp_ExAllocatePool2
0x14000892a  nop     dword ptr [rax+rax+00h]
0x14000892f  mov     [rdi+28h], rax
0x140008933  test    rax, rax
0x140008936  jnz     short loc_140008957
0x140008938  mov     eax, cs:dword_140019000
0x14000893e  mov     edx, 0C0000017h
0x140008943  mov     ebx, edx
0x140008945  cmp     eax, 3
0x140008948  jbe     loc_140008B3D
0x14000894e  mov     [rsp+100h+var_D0], edx
0x140008952  jmp     loc_14000875A
0x140008957  mov     [rdi+18h], r14
0x14000895b  xorps   xmm0, xmm0
0x14000895e  mov     [rdi+20h], rsi
0x140008962  xorps   xmm1, xmm1
0x140008965  mov     dword ptr [rdi+38h], 10000001h
0x14000896c  xor     r8d, r8d; State
0x14000896f  mov     [rdi+68h], r12d
0x140008973  xor     edx, edx; Type
0x140008975  movups  xmmword ptr [rdi+70h], xmm0
0x140008979  mov     rcx, rax; Event
0x14000897c  movups  xmmword ptr [rdi+80h], xmm1
0x140008983  call    cs:__imp_KeInitializeEvent
0x14000898a  nop     dword ptr [rax+rax+00h]
0x14000898f  mov     rsi, [rbp+37h+var_98]
0x140008993  mov     r8, rdi
0x140008996  mov     rdx, [rbp+37h+var_A0]
0x14000899a  mov     rcx, [rsi+8]
0x14000899e  call    BfsInsertEntryHashTable
0x1400089a3  mov     ebx, eax
0x1400089a5  test    eax, eax
0x1400089a7  jns     short loc_1400089C6
0x1400089a9  mov     eax, cs:dword_140019000
0x1400089af  xor     r14d, r14d
0x1400089b2  xor     esi, esi
0x1400089b4  cmp     eax, 3
0x1400089b7  jbe     loc_140008B3D
0x1400089bd  mov     [rsp+100h+var_D0], ebx
0x1400089c1  jmp     loc_14000875A
0x1400089c6  lock inc dword ptr [rdi+90h]
0x1400089cd  lea     rbx, [rsi+10h]
0x1400089d1  cmp     [rbx], rbx
0x1400089d4  jnz     short loc_1400089F6
0x1400089d6  mov     rcx, [rsi+20h]
0x1400089da  xor     r9d, r9d
0x1400089dd  mov     rdx, 0FFFFFFFFEE1E5D00h
0x1400089e4  mov     r8d, 11E1A300h
0x1400089ea  call    cs:__imp_ExSetTimer
0x1400089f1  nop     dword ptr [rax+rax+00h]
0x1400089f6  mov     rax, [rbx+8]
0x1400089fa  cmp     [rax], rbx
0x1400089fd  jnz     loc_140008C98
0x140008a03  lea     rcx, [rdi+40h]
0x140008a07  mov     [rsp+100h+var_C8], 1
0x140008a0c  mov     [rcx+8], rax
0x140008a10  mov     [rcx], rbx
0x140008a13  mov     [rax], rcx
0x140008a16  mov     rax, 0FFFFF78000000014h
0x140008a20  mov     [rbx+8], rcx
0x140008a24  mov     rax, [rax]
0x140008a27  xchg    rax, [rcx+20h]
0x140008a2b  mov     rdx, [rbp+37h+SourceSid]; Sid
0x140008a2f  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x140008a33  mov     r8b, 1; AllocateDestinationString
0x140008a36  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008a3d  nop     dword ptr [rax+rax+00h]
0x140008a42  mov     ebx, eax
0x140008a44  test    eax, eax
0x140008a46  js      loc_140008AFE
0x140008a4c  mov     rdx, [rbp+37h+Sid]; Sid
0x140008a50  lea     rcx, [rbp+37h+var_80]; UnicodeString
0x140008a54  mov     r8b, 1; AllocateDestinationString
0x140008a57  mov     [rsp+100h+var_C7], 1
0x140008a5c  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008a63  nop     dword ptr [rax+rax+00h]
0x140008a68  mov     ebx, eax
0x140008a6a  test    eax, eax
0x140008a6c  js      loc_140008AFE
0x140008a72  lea     rax, [rsp+100h+var_B8]
0x140008a77  mov     [rsp+100h+var_C6], 1
0x140008a7c  xor     r9d, r9d
0x140008a7f  mov     [rsp+100h+Timeout], rax; int
0x140008a84  lea     r8, [rbp+37h+UnicodeString]
0x140008a88  xor     edx, edx
0x140008a8a  mov     rcx, r13
0x140008a8d  call    BfsOpenPolicyDirectory
0x140008a92  mov     ebx, eax
0x140008a94  test    eax, eax
  ... truncated ...
```
