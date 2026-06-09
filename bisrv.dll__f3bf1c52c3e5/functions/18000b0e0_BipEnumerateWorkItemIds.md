# BipEnumerateWorkItemIds

- ea: `0x18000b0e0`
- end: `0x18000b507`
- name: `BipEnumerateWorkItemIds`
- size: `1063`
- prototype: `__int64 __usercall@<rax>(PSID Sid2@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009ba0`
- `0x18000ae58`
- `0x18000b510`

## callees

- `0x18000b0e0`
- `0x18000d7c0`
- `0x18000da50`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x18000b2dc`
- `ntdll!RtlReAllocateHeap` at `0x18000b2dc`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000b1bb`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000b1bb`
- `ntdll!RtlInitEnumerationHashTable` at `0x18000b16a`
- `ntdll!RtlInitEnumerationHashTable` at `0x18000b16a`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000b235`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000b235`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b159`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b159`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b32c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b33c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b390`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b32c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b33c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b390`
- `ntdll!RtlFreeHeap` at `0x18000b3e0`
- `ntdll!RtlFreeHeap` at `0x18000b3e0`
- `ntdll!RtlAllocateHeap` at `0x18000b187`
- `ntdll!RtlAllocateHeap` at `0x18000b187`
- `ntdll!RtlEqualSid` at `0x18000b1e5`
- `ntdll!RtlEqualSid` at `0x18000b202`
- `ntdll!RtlEqualSid` at `0x18000b1e5`
- `ntdll!RtlEqualSid` at `0x18000b202`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000b31e`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000b31e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b4e3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b4e3`

## pseudocode

```c
__int64 __fastcall BipEnumerateWorkItemIds(PSID Sid2, __int64 a2, int a3, char a4, unsigned int *a5, _QWORD *a6)
{
  unsigned int v7; // r12d
  char *Heap; // r15
  int v11; // esi
  int v12; // r14d
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 v15; // rbx
  void *v16; // rcx
  void *v17; // rcx
  int v18; // ecx
  int v19; // eax
  int v20; // ecx
  char *v21; // rax
  __int64 v22; // rax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v23; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v25; // edi
  __int64 v26; // rbx
  int UserDataCount; // [rsp+28h] [rbp-B9h]
  __int64 v29; // [rsp+38h] [rbp-A9h] BYREF
  _QWORD *v30; // [rsp+40h] [rbp-A1h] BYREF
  unsigned int *v31; // [rsp+48h] [rbp-99h] BYREF
  __int64 v32; // [rsp+50h] [rbp-91h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34[3]; // [rsp+68h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+98h] [rbp-49h] BYREF
  char *v36; // [rsp+A8h] [rbp-39h]
  int v37; // [rsp+B0h] [rbp-31h]
  int v38; // [rsp+B4h] [rbp-2Dh]
  __int64 *v39; // [rsp+B8h] [rbp-29h]
  __int64 v40; // [rsp+C0h] [rbp-21h]
  _QWORD **v41; // [rsp+C8h] [rbp-19h]
  __int64 v42; // [rsp+D0h] [rbp-11h]
  unsigned int **v43; // [rsp+D8h] [rbp-9h]
  __int64 v44; // [rsp+E0h] [rbp-1h]

  v7 = 0;
  v31 = a5;
  v30 = a6;
  v32 = a2;
  memset(v34, 0, sizeof(v34));
  BipAcquireGlobalLock(Sid2);
  v34[0].Ptr = (ULONGLONG)&qword_1800C4388;
  RtlAcquireSRWLockExclusive(&qword_1800C4390);
  if ( !(unsigned __int8)RtlInitEnumerationHashTable(qword_1800C4388, &v34[0].Size) )
  {
    RtlReleaseSRWLockExclusive(v34[0].Ptr + 8);
    Heap = 0;
    v11 = -1073741823;
    v12 = 10;
    goto LABEL_34;
  }
  Heap = (char *)RtlAllocateHeap(BipHeap, 0, 0x400u);
  if ( !Heap )
  {
    v11 = -1073741801;
    v12 = 20;
    goto LABEL_32;
  }
  v13 = 64;
  while ( 1 )
  {
    v14 = RtlEnumerateEntryHashTable(*(_QWORD *)v34[0].Ptr, &v34[0].Size);
    v15 = v14;
    if ( !v14 )
      break;
    if ( Sid2 )
    {
      v16 = *(void **)(*(_QWORD *)(v14 + 72) + 168LL);
      if ( !v16 )
        continue;
      if ( !RtlEqualSid(v16, Sid2) )
      {
        v17 = *(void **)(*(_QWORD *)(v15 + 72) + 176LL);
        if ( !v17 || !RtlEqualSid(v17, Sid2) )
          continue;
      }
    }
    if ( v32 )
    {
      LOBYTE(UserDataCount) = 1;
      if ( (unsigned int)RtlCompareUnicodeStrings(*(_QWORD *)(v15 + 72) + 448LL, 65, v32 + 256, 65, UserDataCount) )
        continue;
    }
    if ( (a3 & 8) != 0 )
    {
      v18 = *(_DWORD *)(v15 + 400);
      if ( v18 )
      {
        if ( v18 != 2 )
          continue;
      }
    }
    v19 = *(_DWORD *)(v15 + 24);
    if ( (v19 & a3) == 0 )
    {
      if ( (a4 & 2) != 0 )
      {
        if ( v19 >= 0 && (v19 & 0x40000000) == 0 )
        {
LABEL_22:
          if ( (a4 & 1) == 0 || ((v20 = *(_DWORD *)(v15 + 400)) == 0 || v20 == 2) && *(_QWORD *)(v15 + 112) != v15 + 112 )
          {
            if ( v7 >= v13 )
            {
              v13 *= 2;
              v21 = (char *)RtlReAllocateHeap(BipHeap, 0, Heap, 16LL * v13);
              if ( !v21 )
              {
                v11 = -1073741801;
                v12 = 30;
                goto LABEL_32;
              }
              Heap = v21;
            }
            v22 = 2LL * v7++;
            *(_OWORD *)&Heap[8 * v22] = *(_OWORD *)(v15 + 32);
          }
        }
      }
      else if ( v19 >= 0 )
      {
        goto LABEL_22;
      }
    }
  }
  v11 = 0;
  v12 = 0;
LABEL_32:
  RtlEndEnumerationHashTable(*(_QWORD *)v34[0].Ptr, &v34[0].Size);
  RtlReleaseSRWLockExclusive(v34[0].Ptr + 8);
LABEL_34:
  BipLockWatchdogContextDisarmWatchdog(v23);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v25 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v26 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  *(_DWORD *)(v26 + 8) &= v25;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  *(_DWORD *)(v26 + 4) &= v25;
  if ( v11 < 0 )
  {
    if ( Heap )
      RtlFreeHeap(BipHeap, 0, Heap);
    if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
    {
      LODWORD(v29) = v7;
      v39 = &v29;
      v40 = 4;
      v41 = &v30;
      LODWORD(v30) = v11;
      v43 = &v31;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_1800C30A0;
      v42 = 4;
      LODWORD(v31) = v12;
      v44 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 3;
      UserData.Size = *(unsigned __int16 *)off_1800C30A0;
      v36 = byte_1800B131D;
      UserData.Reserved = 2;
      v37 = 69;
      v38 = 1;
      LODWORD(v32) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
  }
  else
  {
    *v31 = v7;
    *v30 = Heap;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000b0e0  mov     r11, rsp
0x18000b0e3  push    rbp
0x18000b0e4  push    rsi
0x18000b0e5  push    r12
0x18000b0e7  push    r14
0x18000b0e9  push    r15
0x18000b0eb  lea     rbp, [r11-4Fh]
0x18000b0ef  sub     rsp, 100h
0x18000b0f6  mov     rax, cs:__security_cookie
0x18000b0fd  xor     rax, rsp
0x18000b100  mov     [rbp+47h+var_40], rax
0x18000b104  mov     rax, [rbp+47h+arg_20]
0x18000b108  xorps   xmm0, xmm0
0x18000b10b  mov     [r11+18h], rbx
0x18000b10f  mov     r14d, r9d
0x18000b112  mov     [r11-30h], rdi
0x18000b116  xor     r12d, r12d
0x18000b119  mov     [rsp+120h+var_E0], rax
0x18000b11e  mov     rdi, rcx
0x18000b121  mov     rax, [rbp+47h+arg_28]
0x18000b125  mov     [r11-38h], r13
0x18000b129  mov     r13d, r8d
0x18000b12c  mov     [rsp+120h+var_E8], rax
0x18000b131  mov     qword ptr [rsp+120h+var_D8], rdx
0x18000b136  movups  [rbp+47h+var_C0], xmm0
0x18000b13a  movups  [rbp+47h+var_B0], xmm0
0x18000b13e  movups  [rbp+47h+var_A0], xmm0
0x18000b142  call    BipAcquireGlobalLock
0x18000b147  lea     rax, qword_1800C4388
0x18000b14e  lea     rcx, qword_1800C4390
0x18000b155  mov     qword ptr [rbp+47h+var_C0], rax
0x18000b159  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b15f  mov     rcx, qword ptr [rbp+47h+var_C0]
0x18000b163  lea     rdx, [rbp+47h+var_C0+8]
0x18000b167  mov     rcx, [rcx]
0x18000b16a  call    cs:__imp_RtlInitEnumerationHashTable
0x18000b170  test    al, al
0x18000b172  jz      loc_18000B334
0x18000b178  mov     rcx, cs:BipHeap; HeapHandle
0x18000b17f  xor     edx, edx; Flags
0x18000b181  mov     r8d, 400h; Size
0x18000b187  call    cs:__imp_RtlAllocateHeap
0x18000b18d  mov     r15, rax
0x18000b190  test    rax, rax
0x18000b193  jnz     short loc_18000B1A5
0x18000b195  mov     esi, 0C0000017h
0x18000b19a  mov     r14d, 14h
0x18000b1a0  jmp     loc_18000B313
0x18000b1a5  mov     esi, 40h ; '@'
0x18000b1aa  nop     word ptr [rax+rax+00h]
0x18000b1b0  mov     rcx, qword ptr [rbp+47h+var_C0]
0x18000b1b4  lea     rdx, [rbp+47h+var_C0+8]
0x18000b1b8  mov     rcx, [rcx]
0x18000b1bb  call    cs:__imp_RtlEnumerateEntryHashTable
0x18000b1c1  mov     rbx, rax
0x18000b1c4  test    rax, rax
0x18000b1c7  jz      loc_18000B30E
0x18000b1cd  test    rdi, rdi
0x18000b1d0  jz      short loc_18000B20C
0x18000b1d2  mov     rcx, [rax+48h]
0x18000b1d6  mov     rcx, [rcx+0A8h]; Sid1
0x18000b1dd  test    rcx, rcx
0x18000b1e0  jz      short loc_18000B1B0
0x18000b1e2  mov     rdx, rdi; Sid2
0x18000b1e5  call    cs:__imp_RtlEqualSid
0x18000b1eb  test    al, al
0x18000b1ed  jnz     short loc_18000B20C
0x18000b1ef  mov     rax, [rbx+48h]
0x18000b1f3  mov     rcx, [rax+0B0h]; Sid1
0x18000b1fa  test    rcx, rcx
0x18000b1fd  jz      short loc_18000B1B0
0x18000b1ff  mov     rdx, rdi; Sid2
0x18000b202  call    cs:__imp_RtlEqualSid
0x18000b208  test    al, al
0x18000b20a  jz      short loc_18000B1B0
0x18000b20c  mov     rax, qword ptr [rsp+120h+var_D8]
0x18000b211  test    rax, rax
0x18000b214  jz      short loc_18000B243
0x18000b216  mov     rcx, [rbx+48h]
0x18000b21a  lea     r8, [rax+100h]
0x18000b221  mov     edx, 41h ; 'A'
0x18000b226  mov     byte ptr [rsp+120h+UserDataCount], 1
0x18000b22b  add     rcx, 1C0h
0x18000b232  mov     r9d, edx
0x18000b235  call    cs:__imp_RtlCompareUnicodeStrings
0x18000b23b  test    eax, eax
0x18000b23d  jnz     loc_18000B1B0
0x18000b243  test    r13b, 8
0x18000b247  jz      short loc_18000B265
0x18000b249  mov     ecx, [rbx+190h]
0x18000b24f  test    ecx, ecx
0x18000b251  jz      short loc_18000B265
0x18000b253  sub     ecx, 1
0x18000b256  jz      loc_18000B1B0
0x18000b25c  cmp     ecx, 1
0x18000b25f  jnz     loc_18000B1B0
0x18000b265  mov     eax, [rbx+18h]
0x18000b268  test    r13d, eax
0x18000b26b  jnz     loc_18000B1B0
0x18000b271  test    r14b, 2
0x18000b275  jz      short loc_18000B28B
0x18000b277  test    eax, eax
0x18000b279  js      loc_18000B1B0
0x18000b27f  bt      eax, 1Eh
0x18000b283  jb      loc_18000B1B0
0x18000b289  jmp     short loc_18000B293
0x18000b28b  test    eax, eax
0x18000b28d  js      loc_18000B1B0
0x18000b293  test    r14b, 1
0x18000b297  jz      short loc_18000B2C2
0x18000b299  mov     ecx, [rbx+190h]
0x18000b29f  test    ecx, ecx
0x18000b2a1  jz      short loc_18000B2B5
0x18000b2a3  sub     ecx, 1
0x18000b2a6  jz      loc_18000B1B0
0x18000b2ac  cmp     ecx, 1
0x18000b2af  jnz     loc_18000B1B0
0x18000b2b5  lea     rax, [rbx+70h]
0x18000b2b9  cmp     [rax], rax
0x18000b2bc  jz      loc_18000B1B0
0x18000b2c2  cmp     r12d, esi
0x18000b2c5  jb      short loc_18000B2EA
0x18000b2c7  mov     rcx, cs:BipHeap; Heap
0x18000b2ce  add     esi, esi
0x18000b2d0  mov     r9d, esi
0x18000b2d3  mov     r8, r15; Ptr
0x18000b2d6  shl     r9, 4; Size
0x18000b2da  xor     edx, edx; Flags
0x18000b2dc  call    cs:__imp_RtlReAllocateHeap
0x18000b2e2  test    rax, rax
0x18000b2e5  jz      short loc_18000B301
0x18000b2e7  mov     r15, rax
0x18000b2ea  movups  xmm0, xmmword ptr [rbx+20h]
0x18000b2ee  mov     eax, r12d
0x18000b2f1  add     rax, rax
0x18000b2f4  inc     r12d
0x18000b2f7  movups  xmmword ptr [r15+rax*8], xmm0
0x18000b2fc  jmp     loc_18000B1B0
0x18000b301  mov     esi, 0C0000017h
0x18000b306  mov     r14d, 1Eh
0x18000b30c  jmp     short loc_18000B313
0x18000b30e  xor     esi, esi
0x18000b310  xor     r14d, r14d
0x18000b313  mov     rcx, qword ptr [rbp+47h+var_C0]
0x18000b317  lea     rdx, [rbp+47h+var_C0+8]
0x18000b31b  mov     rcx, [rcx]
0x18000b31e  call    cs:__imp_RtlEndEnumerationHashTable
0x18000b324  mov     rcx, qword ptr [rbp+47h+var_C0]
0x18000b328  add     rcx, 8
0x18000b32c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b332  jmp     short loc_18000B350
0x18000b334  mov     rcx, qword ptr [rbp+47h+var_C0]
0x18000b338  add     rcx, 8
0x18000b33c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b342  xor     r15d, r15d
0x18000b345  mov     esi, 0C0000001h
0x18000b34a  mov     r14d, 0Ah
0x18000b350  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18000b355  mov     ecx, cs:dword_1800C3CB0
0x18000b35b  mov     edi, 1
0x18000b360  mov     rax, gs:58h
0x18000b369  shl     edi, cl
0x18000b36b  mov     ecx, cs:_tls_index
0x18000b371  not     edi
0x18000b373  mov     cs:dword_1800C3CB4, 0
0x18000b37d  mov     rbx, [rax+rcx*8]
0x18000b381  lea     rcx, BipGlobalLock
0x18000b388  mov     eax, 8
0x18000b38d  and     [rax+rbx], edi
0x18000b390  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b396  mov     r13, [rsp+120h+var_30]
0x18000b39e  mov     eax, 4
0x18000b3a3  and     [rax+rbx], edi
0x18000b3a6  mov     rdi, [rsp+0F8h]
0x18000b3ae  mov     rbx, [rsp+120h+arg_10]
0x18000b3b6  test    esi, esi
0x18000b3b8  js      short loc_18000B3CF
0x18000b3ba  mov     rax, [rsp+120h+var_E0]
0x18000b3bf  mov     [rax], r12d
0x18000b3c2  mov     rax, [rsp+120h+var_E8]
0x18000b3c7  mov     [rax], r15
0x18000b3ca  jmp     loc_18000B4E9
0x18000b3cf  test    r15, r15
0x18000b3d2  jz      short loc_18000B3E6
0x18000b3d4  mov     rcx, cs:BipHeap; HeapHandle
0x18000b3db  mov     r8, r15; P
0x18000b3de  xor     edx, edx; Flags
0x18000b3e0  call    cs:__imp_RtlFreeHeap
0x18000b3e6  mov     eax, cs:dword_1800C3098
0x18000b3ec  cmp     eax, 2
0x18000b3ef  jbe     loc_18000B4E9
0x18000b3f5  mov     rcx, cs:qword_1800C30B0
0x18000b3fc  mov     rax, cs:qword_1800C30A8
0x18000b403  test    al, 3
0x18000b405  jz      loc_18000B4E9
0x18000b40b  mov     rax, rcx
0x18000b40e  and     eax, 3
0x18000b411  cmp     rax, rcx
0x18000b414  jnz     loc_18000B4E9
0x18000b41a  mov     dword ptr [rsp+120h+var_F0], r12d
0x18000b41f  lea     rax, [rsp+120h+var_F0]
0x18000b424  mov     [rbp+47h+var_70], rax
0x18000b428  lea     rcx, _TraceLoggingMetadata
0x18000b42f  mov     [rbp+47h+var_68], 4
0x18000b437  lea     rax, [rsp+120h+var_E8]
0x18000b43c  mov     [rbp+47h+var_60], rax
0x18000b440  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x18000b445  lea     rax, [rsp+120h+var_E0]
0x18000b44a  mov     dword ptr [rsp+120h+var_E8], esi
0x18000b44e  mov     [rbp+47h+var_50], rax
0x18000b452  xor     r9d, r9d; RelatedActivityId
0x18000b455  movzx   eax, cs:word_1800B1313
0x18000b45c  xor     r8d, r8d; ActivityId
0x18000b45f  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x18000b463  mov     rax, cs:off_1800C30A0
0x18000b46a  mov     [rbp+47h+var_90.Ptr], rax
0x18000b46e  mov     [rbp+47h+var_58], 4
0x18000b476  mov     dword ptr [rsp+120h+var_E0], r14d
0x18000b47b  mov     [rbp+47h+var_48], 4
0x18000b483  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x18000b48b  mov     [rsp+120h+EventDescriptor.Keyword], 3
0x18000b494  movzx   eax, word ptr [rax]
0x18000b497  mov     [rbp+47h+var_90.Size], eax
0x18000b49a  lea     rax, byte_1800B131D
0x18000b4a1  mov     [rbp+47h+var_80], rax
0x18000b4a5  lea     rax, _TraceLoggingMetadataEnd
0x18000b4ac  sub     eax, ecx
0x18000b4ae  mov     dword ptr [rbp+47h+var_90.0Ch], 2
0x18000b4b5  mov     [rbp+47h+var_78], 45h ; 'E'
0x18000b4bc  mov     [rbp+47h+var_74], 1
0x18000b4c3  mov     [rsp+120h+var_D8], eax
0x18000b4c7  mov     eax, [rsp+120h+var_D8]
0x18000b4cb  mov     rcx, cs:RegHandle; RegHandle
0x18000b4d2  lea     rax, [rbp+47h+var_90]
0x18000b4d6  mov     [rsp+120h+UserData], rax; UserData
0x18000b4db  mov     [rsp+120h+UserDataCount], 5; UserDataCount
0x18000b4e3  call    cs:__imp_EventWriteTransfer
0x18000b4e9  mov     eax, esi
0x18000b4eb  mov     rcx, [rbp+47h+var_40]
0x18000b4ef  xor     rcx, rsp; StackCookie
0x18000b4f2  call    __security_check_cookie
0x18000b4f7  add     rsp, 100h
0x18000b4fe  pop     r15
0x18000b500  pop     r14
0x18000b502  pop     r12
0x18000b504  pop     rsi
0x18000b505  pop     rbp
0x18000b506  retn
```
