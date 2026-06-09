# BfsInsertNotPresentPolicyEntry

- ea: `0x140007890`
- end: `0x140007b59`
- name: `BfsInsertNotPresentPolicyEntry`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140008e84`

## callees

- `0x140001008`
- `0x140006040`
- `0x140007890`
- `0x140008ca8`
- `0x140012b68`
- `0x140013730`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140007a89`
- `ntoskrnl!KeInitializeEvent` at `0x140007a89`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400078cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400078cf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007909`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007ae2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007909`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007ae2`
- `ntoskrnl!RtlCopySid` at `0x1400079ae`
- `ntoskrnl!RtlCopySid` at `0x1400079e9`
- `ntoskrnl!RtlCopySid` at `0x1400079ae`
- `ntoskrnl!RtlCopySid` at `0x1400079e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007b17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007b2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007b17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007b2d`
- `ntoskrnl!ExAllocatePool2` at `0x14000793f`
- `ntoskrnl!ExAllocatePool2` at `0x140007989`
- `ntoskrnl!ExAllocatePool2` at `0x140007a0d`
- `ntoskrnl!ExAllocatePool2` at `0x140007a44`
- `ntoskrnl!ExAllocatePool2` at `0x14000793f`
- `ntoskrnl!ExAllocatePool2` at `0x140007989`
- `ntoskrnl!ExAllocatePool2` at `0x140007a0d`
- `ntoskrnl!ExAllocatePool2` at `0x140007a44`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400078be`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400078be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007915`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007aee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007915`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007aee`

## pseudocode

```c
__int64 __fastcall BfsInsertNotPresentPolicyEntry(__int64 a1, ULONG_PTR a2, unsigned __int8 *a3, unsigned __int8 *a4)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v8; // rax
  __int64 v9; // rdi
  NTSTATUS inserted; // ebx
  int v11; // r8d
  int v12; // r9d
  void *Pool2; // r14
  void *v14; // rsi
  int v15; // ecx
  bool v16; // cc
  NTSTATUS v17; // eax
  __int64 v18; // rax
  struct _KEVENT *v19; // rax
  int v21; // [rsp+20h] [rbp-58h]
  int v22; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+38h] [rbp-40h] BYREF
  int *v24; // [rsp+58h] [rbp-20h]
  __int64 v25; // [rsp+60h] [rbp-18h]

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1, 0);
  v8 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), a2, a3, a4);
  v9 = (__int64)v8;
  if ( v8 )
  {
    inserted = 0x40000000;
    if ( LODWORD(v8[2].Linkage.Blink) != 0x10000000 )
      inserted = 0;
    ExReleasePushLockExclusiveEx(a1, 0);
    KeLeaveCriticalRegion();
    return (unsigned int)inserted;
  }
  Pool2 = (void *)ExAllocatePool2(256, 4LL * a3[1] + 8, 1400071746);
  if ( !Pool2 )
  {
    v14 = 0;
LABEL_7:
    v15 = dword_140019000;
    v16 = (unsigned int)dword_140019000 <= 3;
LABEL_8:
    inserted = -1073741801;
    if ( v16 )
      goto LABEL_22;
    v22 = -1073741801;
    goto LABEL_21;
  }
  v14 = (void *)ExAllocatePool2(256, 4LL * a4[1] + 8, 1400071746);
  if ( !v14 )
    goto LABEL_7;
  v17 = RtlCopySid(4 * a3[1] + 8, Pool2, a3);
  inserted = v17;
  if ( v17 < 0 )
  {
    v15 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_22;
    v22 = v17;
    goto LABEL_21;
  }
  inserted = RtlCopySid(4 * a4[1] + 8, v14, a4);
  if ( inserted >= 0 )
  {
    v18 = ExAllocatePool2(256, 152, 1165190722);
    v9 = v18;
    if ( !v18
      || (_InterlockedIncrement((volatile signed __int32 *)(v18 + 144)),
          v19 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1987274306),
          (*(_QWORD *)(v9 + 40) = v19) == 0) )
    {
      v16 = (unsigned int)dword_140019000 <= 3;
      goto LABEL_8;
    }
    *(_QWORD *)(v9 + 32) = v14;
    *(_QWORD *)(v9 + 24) = Pool2;
    *(_DWORD *)(v9 + 56) = 2;
    v14 = 0;
    *(_DWORD *)(v9 + 104) = 0;
    *(_OWORD *)(v9 + 112) = 0;
    *(_OWORD *)(v9 + 128) = 0;
    Pool2 = 0;
    KeInitializeEvent(v19, NotificationEvent, 0);
    inserted = BfsInsertEntryHashTable(*(_QWORD *)(a1 + 8), a2, v9);
    if ( inserted >= 0 )
      goto LABEL_22;
  }
  if ( (unsigned int)dword_140019000 <= 3 )
    goto LABEL_22;
  v22 = inserted;
LABEL_21:
  v25 = 4;
  v24 = &v22;
  tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140016D91, v11, v12, v21, &v23);
LABEL_22:
  ExReleasePushLockExclusiveEx(a1, 0);
  KeLeaveCriticalRegion();
  if ( inserted < 0 )
  {
    if ( v9 )
      BfsDereferencePolicyEntryEx((PVOID)v9);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140007890  push    rbp
0x140007892  push    rbx
0x140007893  push    rsi
0x140007894  push    rdi
0x140007895  push    r12
0x140007897  push    r13
0x140007899  push    r14
0x14000789b  push    r15
0x14000789d  mov     rbp, rsp
0x1400078a0  sub     rsp, 78h
0x1400078a4  mov     rax, cs:__security_cookie
0x1400078ab  xor     rax, rsp
0x1400078ae  mov     [rbp+var_10], rax
0x1400078b2  mov     r15, r9
0x1400078b5  mov     rbx, r8
0x1400078b8  mov     r12, rdx
0x1400078bb  mov     r13, rcx
0x1400078be  call    cs:__imp_KeEnterCriticalRegion
0x1400078c5  nop     dword ptr [rax+rax+00h]
0x1400078ca  xor     edx, edx
0x1400078cc  mov     rcx, r13
0x1400078cf  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400078d6  nop     dword ptr [rax+rax+00h]
0x1400078db  mov     rcx, [r13+8]; HashTable
0x1400078df  mov     r9, r15
0x1400078e2  mov     r8, rbx
0x1400078e5  mov     rdx, r12
0x1400078e8  call    BfsLookupPolicyEntryHashTable
0x1400078ed  mov     rdi, rax
0x1400078f0  test    rax, rax
0x1400078f3  jz      short loc_140007926
0x1400078f5  xor     edx, edx
0x1400078f7  mov     ebx, 40000000h
0x1400078fc  cmp     dword ptr [rax+38h], 10000000h
0x140007903  mov     rcx, r13
0x140007906  cmovnz  ebx, edx
0x140007909  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140007910  nop     dword ptr [rax+rax+00h]
0x140007915  call    cs:__imp_KeLeaveCriticalRegion
0x14000791c  nop     dword ptr [rax+rax+00h]
0x140007921  jmp     loc_140007B39
0x140007926  movzx   edx, byte ptr [rbx+1]
0x14000792a  mov     esi, 100h
0x14000792f  mov     r8d, 53736642h
0x140007935  mov     ecx, esi
0x140007937  lea     rdx, ds:8[rdx*4]
0x14000793f  call    cs:__imp_ExAllocatePool2
0x140007946  nop     dword ptr [rax+rax+00h]
0x14000794b  mov     r14, rax
0x14000794e  test    rax, rax
0x140007951  jnz     short loc_140007973
0x140007953  xor     esi, esi
0x140007955  mov     ecx, cs:dword_140019000
0x14000795b  cmp     ecx, 3
0x14000795e  mov     edx, 0C0000017h
0x140007963  mov     ebx, edx
0x140007965  jbe     loc_140007ADD
0x14000796b  mov     [rbp+var_48], edx
0x14000796e  jmp     loc_140007AB8
0x140007973  movzx   edx, byte ptr [r15+1]
0x140007978  mov     r8d, 53736642h
0x14000797e  mov     rcx, rsi
0x140007981  lea     rdx, ds:8[rdx*4]
0x140007989  call    cs:__imp_ExAllocatePool2
0x140007990  nop     dword ptr [rax+rax+00h]
0x140007995  mov     rsi, rax
0x140007998  test    rax, rax
0x14000799b  jz      short loc_140007955
0x14000799d  movzx   ecx, byte ptr [rbx+1]
0x1400079a1  mov     r8, rbx; SourceSid
0x1400079a4  mov     rdx, r14; DestinationSid
0x1400079a7  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x1400079ae  call    cs:__imp_RtlCopySid
0x1400079b5  nop     dword ptr [rax+rax+00h]
0x1400079ba  mov     ebx, eax
0x1400079bc  test    eax, eax
0x1400079be  jns     short loc_1400079D7
0x1400079c0  mov     ecx, cs:dword_140019000
0x1400079c6  cmp     ecx, 3
0x1400079c9  jbe     loc_140007ADD
0x1400079cf  mov     [rbp+var_48], eax
0x1400079d2  jmp     loc_140007AB8
0x1400079d7  movzx   ecx, byte ptr [r15+1]
0x1400079dc  mov     r8, r15; SourceSid
0x1400079df  mov     rdx, rsi; DestinationSid
0x1400079e2  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x1400079e9  call    cs:__imp_RtlCopySid
0x1400079f0  nop     dword ptr [rax+rax+00h]
0x1400079f5  mov     ebx, eax
0x1400079f7  test    eax, eax
0x1400079f9  js      loc_140007AAA
0x1400079ff  mov     edx, 98h
0x140007a04  mov     r8d, 45736642h
0x140007a0a  lea     ecx, [rdx+68h]
0x140007a0d  call    cs:__imp_ExAllocatePool2
0x140007a14  nop     dword ptr [rax+rax+00h]
0x140007a19  mov     rdi, rax
0x140007a1c  test    rax, rax
0x140007a1f  jnz     short loc_140007A2F
0x140007a21  mov     eax, cs:dword_140019000
0x140007a27  cmp     eax, 3
0x140007a2a  jmp     loc_14000795E
0x140007a2f  lock inc dword ptr [rax+90h]
0x140007a36  mov     edx, 18h
0x140007a3b  mov     r8d, 76736642h
0x140007a41  lea     ecx, [rdx+28h]
0x140007a44  call    cs:__imp_ExAllocatePool2
0x140007a4b  nop     dword ptr [rax+rax+00h]
0x140007a50  mov     [rdi+28h], rax
0x140007a54  test    rax, rax
0x140007a57  jz      short loc_140007A21
0x140007a59  mov     [rdi+20h], rsi
0x140007a5d  xorps   xmm0, xmm0
0x140007a60  mov     [rdi+18h], r14
0x140007a64  xorps   xmm1, xmm1
0x140007a67  mov     dword ptr [rdi+38h], 2
0x140007a6e  xor     esi, esi
0x140007a70  mov     [rdi+68h], esi
0x140007a73  xor     r8d, r8d; State
0x140007a76  movups  xmmword ptr [rdi+70h], xmm0
0x140007a7a  xor     edx, edx; Type
0x140007a7c  mov     rcx, rax; Event
0x140007a7f  movups  xmmword ptr [rdi+80h], xmm1
0x140007a86  xor     r14d, r14d
0x140007a89  call    cs:__imp_KeInitializeEvent
0x140007a90  nop     dword ptr [rax+rax+00h]
0x140007a95  mov     rcx, [r13+8]
0x140007a99  mov     r8, rdi
0x140007a9c  mov     rdx, r12
0x140007a9f  call    BfsInsertEntryHashTable
0x140007aa4  mov     ebx, eax
0x140007aa6  test    eax, eax
0x140007aa8  jns     short loc_140007ADD
0x140007aaa  mov     eax, cs:dword_140019000
0x140007ab0  cmp     eax, 3
0x140007ab3  jbe     short loc_140007ADD
0x140007ab5  mov     [rbp+var_48], ebx
0x140007ab8  lea     rax, [rbp+var_48]
0x140007abc  mov     [rbp+var_18], 4
0x140007ac4  mov     [rbp+var_20], rax
0x140007ac8  lea     rdx, byte_140016D91; int
0x140007acf  lea     rax, [rbp+var_40]
0x140007ad3  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x140007ad8  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007add  xor     edx, edx
0x140007adf  mov     rcx, r13
0x140007ae2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140007ae9  nop     dword ptr [rax+rax+00h]
0x140007aee  call    cs:__imp_KeLeaveCriticalRegion
0x140007af5  nop     dword ptr [rax+rax+00h]
0x140007afa  test    ebx, ebx
0x140007afc  jns     short loc_140007B39
0x140007afe  test    rdi, rdi
0x140007b01  jz      short loc_140007B0D
0x140007b03  xor     edx, edx
0x140007b05  mov     rcx, rdi; P
0x140007b08  call    BfsDereferencePolicyEntryEx
0x140007b0d  test    r14, r14
0x140007b10  jz      short loc_140007B23
0x140007b12  xor     edx, edx; Tag
0x140007b14  mov     rcx, r14; P
0x140007b17  call    cs:__imp_ExFreePoolWithTag
0x140007b1e  nop     dword ptr [rax+rax+00h]
0x140007b23  test    rsi, rsi
0x140007b26  jz      short loc_140007B39
0x140007b28  xor     edx, edx; Tag
0x140007b2a  mov     rcx, rsi; P
0x140007b2d  call    cs:__imp_ExFreePoolWithTag
0x140007b34  nop     dword ptr [rax+rax+00h]
0x140007b39  mov     eax, ebx
0x140007b3b  mov     rcx, [rbp+var_10]
0x140007b3f  xor     rcx, rsp; StackCookie
0x140007b42  call    __security_check_cookie
0x140007b47  add     rsp, 78h
0x140007b4b  pop     r15
0x140007b4d  pop     r14
0x140007b4f  pop     r13
0x140007b51  pop     r12
0x140007b53  pop     rdi
0x140007b54  pop     rsi
0x140007b55  pop     rbx
0x140007b56  pop     rbp
0x140007b57  retn
```
