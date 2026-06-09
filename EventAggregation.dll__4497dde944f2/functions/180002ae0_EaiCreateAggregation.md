# EaiCreateAggregation

- ea: `0x180002ae0`
- end: `0x180002e1e`
- name: `EaiCreateAggregation`
- size: `830`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, __int64, __int64, char, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001d50`
- `0x180005030`

## callees

- `0x180002ae0`
- `0x180005940`
- `0x1800072e0`
- `0x180007b5e`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c78`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c93`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002cf4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c78`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c93`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002cf4`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x180002bd0`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x180002bd0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002c2d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002cbc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002c2d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002cbc`
- `ntdll!RtlFreeHeap` at `0x180002d0c`
- `ntdll!RtlFreeHeap` at `0x180002d0c`
- `ntdll!RtlAllocateHeap` at `0x180002b5a`
- `ntdll!RtlAllocateHeap` at `0x180002b5a`
- `ntdll!RtlInitializeSRWLock` at `0x180002bca`
- `ntdll!RtlInitializeSRWLock` at `0x180002bca`
- `ntdll!RtlInsertEntryHashTable` at `0x180002c5b`
- `ntdll!RtlInsertEntryHashTable` at `0x180002c5b`
- `ntdll!RtlRemoveEntryHashTable` at `0x180002ce0`
- `ntdll!RtlRemoveEntryHashTable` at `0x180002ce0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002df4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002df4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cc2`

## pseudocode

```c
__int64 __fastcall EaiCreateAggregation(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        _QWORD *a8)
{
  int v12; // esi
  _DWORD *Heap; // rax
  _DWORD *v14; // rbx
  int v15; // edi
  __int64 v16; // rcx
  int v18; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v19[3]; // [rsp+34h] [rbp-A4h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-88h] BYREF
  char *v22; // [rsp+60h] [rbp-78h]
  int v23; // [rsp+68h] [rbp-70h]
  int v24; // [rsp+6Ch] [rbp-6Ch]
  int *v25; // [rsp+70h] [rbp-68h]
  __int64 v26; // [rsp+78h] [rbp-60h]
  _DWORD *v27; // [rsp+80h] [rbp-58h]
  __int64 v28; // [rsp+88h] [rbp-50h]

  if ( !a8 || !a1 )
  {
    v12 = 100;
    goto LABEL_31;
  }
  if ( *a1 || a1[1] )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA0u);
    v14 = Heap;
    if ( !Heap )
    {
      v15 = -1073741801;
      v12 = 300;
      goto LABEL_32;
    }
    memset_0(Heap, 0, 0xA0u);
    v14[35] |= 0x10u;
    *((_QWORD *)v14 + 5) = a5;
    *((_QWORD *)v14 + 9) = a6;
    v14[34] = 1;
    *((_QWORD *)v14 + 7) = a1;
    *((_QWORD *)v14 + 3) = a2;
    *((_QWORD *)v14 + 4) = a3;
    *((_QWORD *)v14 + 6) = a4;
    *((_OWORD *)v14 + 5) = 0;
    RtlInitializeSRWLock();
    v14[36] = RtlAllocateWnfSerializationGroup();
    v16 = **((_QWORD **)v14 + 7);
    if ( !v16 || !*(_DWORD *)(v16 + 8) && !*(_DWORD *)(v16 + 12) )
      *((_BYTE *)v14 + 64) = 1;
    if ( (a7 & 1) != 0 )
      v14[35] |= 1u;
    if ( (a7 & 2) != 0 )
      v14[35] |= 2u;
    if ( (a7 & 4) != 0 )
      v14[35] |= 4u;
    RtlAcquireSRWLockExclusive(AggregateEventListLock);
    dword_1800121B8 = GetCurrentThreadId();
    if ( qword_180012148 )
    {
      if ( (unsigned __int8)RtlInsertEntryHashTable(qword_180012148, v14, v14, 0) )
      {
        dword_1800121B8 = 0;
        RtlReleaseSRWLockExclusive(AggregateEventListLock);
        v15 = 0;
        if ( (a7 & 8) != 0 || (v15 = EaiEnableAggregateEvent(v14), v15 >= 0) )
        {
          *a8 = v14;
          return (unsigned int)v15;
        }
        v12 = 500;
        RtlAcquireSRWLockExclusive(AggregateEventListLock);
        dword_1800121B8 = GetCurrentThreadId();
        if ( qword_180012148 )
          RtlRemoveEntryHashTable(qword_180012148, v14, 0);
        dword_1800121B8 = 0;
        RtlReleaseSRWLockExclusive(AggregateEventListLock);
        goto LABEL_28;
      }
      v15 = -1073741670;
    }
    else
    {
      v15 = -1073741595;
    }
    dword_1800121B8 = 0;
    RtlReleaseSRWLockExclusive(AggregateEventListLock);
    v12 = 400;
LABEL_28:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    goto LABEL_32;
  }
  v12 = 200;
LABEL_31:
  v15 = -1073741811;
LABEL_32:
  if ( (unsigned int)dword_180012000 > 2 )
  {
    v18 = v15;
    v25 = &v18;
    v26 = 4;
    v27 = v19;
    *(_DWORD *)&EventDescriptor.Level = 514;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v19[0] = v12;
    v28 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v22 = &byte_18000EE7F;
    UserData.Reserved = 2;
    v23 = 60;
    v24 = 1;
    v19[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180002ae0  push    rbx
0x180002ae2  push    rbp
0x180002ae3  push    rsi
0x180002ae4  push    rdi
0x180002ae5  push    r12
0x180002ae7  push    r14
0x180002ae9  push    r15
0x180002aeb  sub     rsp, 0A0h
0x180002af2  mov     rax, cs:__security_cookie
0x180002af9  xor     rax, rsp
0x180002afc  mov     [rsp+0D8h+var_48], rax
0x180002b04  mov     r14, [rsp+0D8h+arg_38]
0x180002b0c  xor     r12d, r12d
0x180002b0f  mov     rsi, r9
0x180002b12  mov     rbp, r8
0x180002b15  mov     r15, rdx
0x180002b18  mov     rdi, rcx
0x180002b1b  test    r14, r14
0x180002b1e  jz      loc_180002D1C
0x180002b24  test    rcx, rcx
0x180002b27  jz      loc_180002D1C
0x180002b2d  cmp     [rcx], r12
0x180002b30  jnz     short loc_180002B42
0x180002b32  cmp     [rcx+8], r12
0x180002b36  jnz     short loc_180002B42
0x180002b38  mov     esi, 0C8h
0x180002b3d  jmp     loc_180002D21
0x180002b42  mov     rcx, gs:60h
0x180002b4b  mov     edx, 8; Flags
0x180002b50  mov     r8d, 0A0h; Size
0x180002b56  mov     rcx, [rcx+30h]; HeapHandle
0x180002b5a  call    cs:__imp_RtlAllocateHeap
0x180002b60  mov     rbx, rax
0x180002b63  test    rax, rax
0x180002b66  jnz     short loc_180002B77
0x180002b68  mov     edi, 0C0000017h
0x180002b6d  mov     esi, 12Ch
0x180002b72  jmp     loc_180002D26
0x180002b77  xor     edx, edx; Val
0x180002b79  mov     r8d, 0A0h; Size
0x180002b7f  mov     rcx, rbx; void *
0x180002b82  call    memset_0
0x180002b87  mov     rax, [rsp+0D8h+arg_20]
0x180002b8f  lea     rcx, [rbx+50h]
0x180002b93  or      dword ptr [rbx+8Ch], 10h
0x180002b9a  xorps   xmm0, xmm0
0x180002b9d  mov     [rbx+28h], rax
0x180002ba1  mov     rax, [rsp+0D8h+arg_28]
0x180002ba9  mov     [rbx+48h], rax
0x180002bad  mov     dword ptr [rbx+88h], 1
0x180002bb7  mov     [rbx+38h], rdi
0x180002bbb  mov     [rbx+18h], r15
0x180002bbf  mov     [rbx+20h], rbp
0x180002bc3  mov     [rbx+30h], rsi
0x180002bc7  movups  xmmword ptr [rcx], xmm0
0x180002bca  call    cs:__imp_RtlInitializeSRWLock
0x180002bd0  call    cs:__imp_RtlAllocateWnfSerializationGroup
0x180002bd6  mov     [rbx+90h], eax
0x180002bdc  mov     rax, [rbx+38h]
0x180002be0  mov     rcx, [rax]
0x180002be3  test    rcx, rcx
0x180002be6  jz      short loc_180002BF4
0x180002be8  cmp     [rcx+8], r12d
0x180002bec  jnz     short loc_180002BF8
0x180002bee  cmp     [rcx+0Ch], r12d
0x180002bf2  jnz     short loc_180002BF8
0x180002bf4  mov     byte ptr [rbx+40h], 1
0x180002bf8  mov     esi, dword ptr [rsp+0D8h+arg_30]
0x180002bff  test    sil, 1
0x180002c03  jz      short loc_180002C0C
0x180002c05  or      dword ptr [rbx+8Ch], 1
0x180002c0c  test    sil, 2
0x180002c10  jz      short loc_180002C19
0x180002c12  or      dword ptr [rbx+8Ch], 2
0x180002c19  test    sil, 4
0x180002c1d  jz      short loc_180002C26
0x180002c1f  or      dword ptr [rbx+8Ch], 4
0x180002c26  lea     rcx, AggregateEventListLock
0x180002c2d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002c33  call    cs:__imp_GetCurrentThreadId
0x180002c39  mov     rcx, cs:qword_180012148
0x180002c40  mov     cs:dword_1800121B8, eax
0x180002c46  test    rcx, rcx
0x180002c49  jnz     short loc_180002C52
0x180002c4b  mov     edi, 0C00000E5h
0x180002c50  jmp     short loc_180002C6A
0x180002c52  xor     r9d, r9d
0x180002c55  mov     r8, rbx
0x180002c58  mov     rdx, rbx
0x180002c5b  call    cs:__imp_RtlInsertEntryHashTable
0x180002c61  test    al, al
0x180002c63  jnz     short loc_180002C85
0x180002c65  mov     edi, 0C000009Ah
0x180002c6a  lea     rcx, AggregateEventListLock
0x180002c71  mov     cs:dword_1800121B8, r12d
0x180002c78  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002c7e  mov     esi, 190h
0x180002c83  jmp     short loc_180002CFA
0x180002c85  lea     rcx, AggregateEventListLock
0x180002c8c  mov     cs:dword_1800121B8, r12d
0x180002c93  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002c99  mov     edi, r12d
0x180002c9c  bt      esi, 3
0x180002ca0  jb      short loc_180002D14
0x180002ca2  mov     rcx, rbx
0x180002ca5  call    EaiEnableAggregateEvent
0x180002caa  mov     edi, eax
0x180002cac  test    eax, eax
0x180002cae  jns     short loc_180002D14
0x180002cb0  lea     rcx, AggregateEventListLock
0x180002cb7  mov     esi, 1F4h
0x180002cbc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002cc2  call    cs:__imp_GetCurrentThreadId
0x180002cc8  mov     rcx, cs:qword_180012148
0x180002ccf  mov     cs:dword_1800121B8, eax
0x180002cd5  test    rcx, rcx
0x180002cd8  jz      short loc_180002CE6
0x180002cda  xor     r8d, r8d
0x180002cdd  mov     rdx, rbx
0x180002ce0  call    cs:__imp_RtlRemoveEntryHashTable
0x180002ce6  lea     rcx, AggregateEventListLock
0x180002ced  mov     cs:dword_1800121B8, r12d
0x180002cf4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002cfa  mov     rcx, gs:60h
0x180002d03  mov     r8, rbx; P
0x180002d06  xor     edx, edx; Flags
0x180002d08  mov     rcx, [rcx+30h]; HeapHandle
0x180002d0c  call    cs:__imp_RtlFreeHeap
0x180002d12  jmp     short loc_180002D26
0x180002d14  mov     [r14], rbx
0x180002d17  jmp     loc_180002DFA
0x180002d1c  mov     esi, 64h ; 'd'
0x180002d21  mov     edi, 0C000000Dh
0x180002d26  mov     eax, cs:dword_180012000
0x180002d2c  cmp     eax, 2
0x180002d2f  jbe     loc_180002DFA
0x180002d35  mov     [rsp+0D8h+var_A8], edi
0x180002d39  lea     rax, [rsp+0D8h+var_A8]
0x180002d3e  mov     [rsp+0D8h+var_68], rax
0x180002d43  lea     rcx, _TraceLoggingMetadata
0x180002d4a  lea     rax, [rsp+0D8h+var_A4]
0x180002d4f  mov     [rsp+0D8h+var_60], 4
0x180002d58  mov     [rsp+0D8h+var_58], rax
0x180002d60  lea     rdx, [rsp+0D8h+EventDescriptor]; EventDescriptor
0x180002d65  movzx   eax, cs:word_18000EE75
0x180002d6c  xor     r9d, r9d; RelatedActivityId
0x180002d6f  mov     dword ptr [rsp+0D8h+EventDescriptor.Level], eax
0x180002d73  xor     r8d, r8d; ActivityId
0x180002d76  mov     rax, cs:off_180012008
0x180002d7d  mov     [rsp+0D8h+var_88.Ptr], rax
0x180002d82  mov     [rsp+0D8h+var_A4], esi
0x180002d86  mov     [rsp+0D8h+var_50], 4
0x180002d92  mov     dword ptr [rsp+0D8h+EventDescriptor.Id], 0B000000h
0x180002d9a  mov     [rsp+0D8h+EventDescriptor.Keyword], r12
0x180002d9f  movzx   eax, word ptr [rax]
0x180002da2  mov     [rsp+0D8h+var_88.Size], eax
0x180002da6  lea     rax, byte_18000EE7F
0x180002dad  mov     [rsp+0D8h+var_78], rax
0x180002db2  lea     rax, _TraceLoggingMetadataEnd
0x180002db9  sub     eax, ecx
0x180002dbb  mov     dword ptr [rsp+0D8h+var_88.0Ch], 2
0x180002dc3  mov     [rsp+0D8h+var_70], 3Ch ; '<'
0x180002dcb  mov     [rsp+0D8h+var_6C], 1
0x180002dd3  mov     [rsp+0D8h+var_A0], eax
0x180002dd7  mov     eax, [rsp+0D8h+var_A0]
0x180002ddb  mov     rcx, cs:RegHandle; RegHandle
0x180002de2  lea     rax, [rsp+0D8h+var_88]
0x180002de7  mov     [rsp+0D8h+UserData], rax; UserData
0x180002dec  mov     [rsp+0D8h+UserDataCount], 4; UserDataCount
0x180002df4  call    cs:__imp_EventWriteTransfer
0x180002dfa  mov     eax, edi
0x180002dfc  mov     rcx, [rsp+0D8h+var_48]
0x180002e04  xor     rcx, rsp; StackCookie
0x180002e07  call    __security_check_cookie
0x180002e0c  add     rsp, 0A0h
0x180002e13  pop     r15
0x180002e15  pop     r14
0x180002e17  pop     r12
0x180002e19  pop     rdi
0x180002e1a  pop     rsi
0x180002e1b  pop     rbp
0x180002e1c  pop     rbx
0x180002e1d  retn
```
