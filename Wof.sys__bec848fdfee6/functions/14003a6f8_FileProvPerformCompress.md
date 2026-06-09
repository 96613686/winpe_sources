# FileProvPerformCompress

- ea: `0x14003a6f8`
- end: `0x14003acb5`
- name: `FileProvPerformCompress`
- size: `1469`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003a528`

## callees

- `0x140008fd0`
- `0x14000d158`
- `0x1400116c0`
- `0x14003a6f8`
- `0x14003acc0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14003aaf4`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003aaf4`
- `ntoskrnl!KeSetEvent` at `0x14003ab2a`
- `ntoskrnl!KeSetEvent` at `0x14003ab2a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a871`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a871`
- `ntoskrnl!KeInitializeEvent` at `0x14003ab9b`
- `ntoskrnl!KeInitializeEvent` at `0x14003ab9b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003ab6a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003ab6a`
- `FLTMGR!FltWriteFile` at `0x14003aacd`
- `FLTMGR!FltWriteFile` at `0x14003aacd`
- `FLTMGR!FltSetInformationFile` at `0x14003a9a8`
- `FLTMGR!FltSetInformationFile` at `0x14003a9a8`

## pseudocode

```c
__int64 __fastcall FileProvPerformCompress(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  void (__stdcall *CallbackRoutine)(PFLT_CALLBACK_DATA, PFLT_CONTEXT); // r13
  int v5; // edi
  unsigned int v6; // esi
  __int64 v8; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // r8d
  unsigned int v19; // eax
  int v20; // edx
  __int64 v21; // rax
  __int64 v22; // r10
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned int v28; // r8d
  __int64 v29; // r11
  unsigned __int64 *v30; // rdi
  __int64 v31; // rbp
  __int64 v32; // r14
  __int64 v33; // rcx
  __int64 v34; // r8
  unsigned int v35; // edx
  unsigned __int64 v36; // rcx
  unsigned int v37; // eax
  FLT_IO_OPERATION_FLAGS Flags; // r12d
  unsigned int v39; // edx
  unsigned int v40; // ecx
  void *CallbackContext; // rdx
  NTSTATUS v42; // eax
  __int64 v43; // rdx
  unsigned __int64 v44; // rdi
  int v45; // ebp
  PVOID PoolWithTag; // rax
  int v47; // ecx
  unsigned int v48; // ecx
  __int64 v49; // rax
  unsigned __int64 v50; // rbp
  int v51; // edi
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp-48h] BYREF
  __int64 v54; // [rsp+A8h] [rbp+10h]
  int v55; // [rsp+B0h] [rbp+18h]
  ULONG BytesWritten; // [rsp+B8h] [rbp+20h] BYREF

  v55 = a3;
  v54 = a2;
  CallbackRoutine = 0;
  v5 = a3;
  v6 = 0;
  BytesWritten = 0;
  v8 = a2;
  while ( 1 )
  {
    do
    {
      while ( v5 )
      {
        if ( *(_QWORD *)(a4 + 32) < *(_QWORD *)(a1 + 8) )
        {
          *(_QWORD *)(*(_QWORD *)(a4 + 240) + 64LL) = v8;
          *(_DWORD *)(*(_QWORD *)(a4 + 240) + 88LL) = **(_DWORD **)(a4 + 8);
          *(_QWORD *)(*(_QWORD *)(a4 + 240) + 56LL) = *(_QWORD *)(a4 + 32);
          *(_QWORD *)(a4 + 32) += **(unsigned int **)(a4 + 8);
          v10 = *(_QWORD *)(a1 + 8);
          if ( *(_QWORD *)(a4 + 32) > v10 )
          {
            v11 = *(_QWORD *)(a4 + 240);
            *(_QWORD *)(a4 + 32) = v10;
            *(_DWORD *)(v11 + 88) = *(_DWORD *)(a1 + 8) - *(_DWORD *)(v11 + 56);
          }
          v12 = *(_QWORD *)(a4 + 240);
          v13 = *(unsigned int *)(v12 + 88);
          v5 -= v13;
          v54 = v13 + v8;
          v55 = v5;
          if ( *(_DWORD *)(a4 + 52) <= 1u )
          {
            *(_QWORD *)(v12 + 72) = *(_QWORD *)(a4 + 24);
          }
          else if ( (unsigned __int8)WofTryQueueWorkItem(v12, (unsigned int)(*(_DWORD *)(a4 + 56) + 32)) )
          {
            goto LABEL_11;
          }
          FileProvCompressWorkItem(*(_QWORD *)(a4 + 240));
LABEL_11:
          v14 = *(_DWORD *)(a4 + 252);
          ++*(_DWORD *)(a4 + 256);
          v8 = v54;
          *(_DWORD *)(a4 + 252) = (unsigned int)(v14 + 1) % *(_DWORD *)(a4 + 52);
        }
        if ( !v5 )
          break;
        if ( *(_QWORD *)(a4 + 32) >= *(_QWORD *)(a1 + 8) )
          break;
        v15 = *(unsigned int *)(a4 + 252);
        if ( (_DWORD)v15 == *(_DWORD *)(a4 + 248) )
          break;
        *(_QWORD *)(a4 + 240) = *(_QWORD *)(a4 + 232) + 136 * v15;
      }
      v16 = *(_QWORD *)(a4 + 232);
      if ( !*(_DWORD *)(a4 + 256) )
      {
        *(_QWORD *)(a4 + 240) = v16 + 136LL * *(unsigned int *)(a4 + 252);
        return v6;
      }
      v17 = v16 + 136LL * *(unsigned int *)(a4 + 248);
      *(_QWORD *)(a4 + 240) = v17;
      KeWaitForSingleObject((PVOID)(v17 + 96), Executive, 0, 0, 0);
      v18 = *(_DWORD *)(a4 + 52);
      v19 = *(_DWORD *)(a4 + 248) + 1;
      --*(_DWORD *)(a4 + 256);
      v20 = v19 % v18;
      v21 = *(_QWORD *)(a4 + 240);
      *(_DWORD *)(a4 + 248) = v20;
      if ( *(int *)(v21 + 128) < 0 )
        return *(unsigned int *)(v21 + 128);
      if ( v18 > 1 )
      {
        memmove(*(void **)(a4 + 24), *(const void **)(v21 + 72), *(unsigned int *)(v21 + 92));
        v21 = *(_QWORD *)(a4 + 240);
      }
      v22 = *(_QWORD *)(a4 + 40);
      if ( v22 > 0 )
      {
        v23 = *(unsigned int *)(a4 + 16);
        v24 = *(_QWORD *)(a4 + 96);
        v25 = v23 * (*(_QWORD *)(v21 + 56) / (__int64)**(unsigned int **)(a4 + 8) - 1);
        if ( (_DWORD)v23 == 4 )
          *(_DWORD *)(v25 + v24) = v22;
        else
          *(_QWORD *)(v25 + v24) = v22;
      }
      v26 = *(_QWORD *)(a4 + 240);
      v27 = (unsigned __int64)*(unsigned int *)(a4 + 224) << 6;
      *(_QWORD *)(a4 + 40) += *(unsigned int *)(v26 + 92);
      *(_DWORD *)(a4 + 48) += *(_DWORD *)(v26 + 92);
      v28 = *(_DWORD *)(a4 + 48);
      v29 = *(_QWORD *)(a4 + 40);
      *(_QWORD *)(a4 + 24) = *(_QWORD *)(v27 + a4 + 96) + v28;
      if ( v28 + **(_DWORD **)(a4 + 8) > *(_DWORD *)(v27 + a4 + 104) )
        break;
      v8 = v54;
    }
    while ( (signed __int64)(*(_QWORD *)(v26 + 56) + *(unsigned int *)(v26 + 88)) < *(_QWORD *)(a1 + 8) );
    v30 = (unsigned __int64 *)(a4 + 296);
    v31 = *(_QWORD *)(v26 + 56) + *(unsigned int *)(v26 + 88);
    v32 = *(_QWORD *)(a1 + 8);
    v33 = v29 + (unsigned int)(*(_DWORD *)(a4 + 16) * *(_DWORD *)(a4 + 20));
    *(_QWORD *)(a4 + 296) = v33;
    if ( v31 < v32 )
      *v30 = v33 & 0xFFFFFFFFFFFFF000uLL;
    v6 = FltSetInformationFile(
           *(PFLT_INSTANCE *)(a4 + 64),
           *(PFILE_OBJECT *)(a4 + 72),
           (PVOID)(a4 + 296),
           8u,
           FileEndOfFileInformation);
    if ( (v6 & 0x80000000) != 0 )
      return v6;
    if ( v31 >= v32 && !*(_DWORD *)(a4 + 224) && (__int64)*v30 < *(unsigned int *)(a4 + 104) )
    {
      *(_BYTE *)(a4 + 60) = 1;
      return v6;
    }
    *(_QWORD *)(((unsigned __int64)*(unsigned int *)(a4 + 224) << 6) + a4 + 144) = *(_QWORD *)(a4 + 40)
                                                                                 + *(unsigned int *)(((unsigned __int64)*(unsigned int *)(a4 + 224) << 6) + a4 + 108)
                                                                                 + (unsigned __int64)(unsigned int)(*(_DWORD *)(a4 + 16) * *(_DWORD *)(a4 + 20))
                                                                                 - *(unsigned int *)(a4 + 48);
    v35 = *(_DWORD *)(a4 + 48);
    v36 = (unsigned __int64)*(unsigned int *)(a4 + 224) << 6;
    v37 = *(_DWORD *)(v36 + a4 + 108);
    if ( v37 < v35 )
    {
      Flags = 7;
      if ( VersionInformation.dwBuildNumber < 0x265C )
        Flags = 15;
      v39 = v35 - v37;
      if ( v31 >= v32 )
        v39 += 4095;
      *(_DWORD *)(v36 + a4 + 152) = v39 & 0xFFFFF000;
      if ( (Flags & 8) == 0 )
        CallbackRoutine = FileProvSimpleCompletionRoutine;
      while ( 1 )
      {
        v40 = *(_DWORD *)(a4 + 224);
        CallbackContext = (Flags & 8) != 0 ? 0LL : (void *)(a4 + ((unsigned __int64)v40 << 6) + 96);
        v42 = FltWriteFile(
                *(PFLT_INSTANCE *)(a4 + 64),
                *(PFILE_OBJECT *)(a4 + 72),
                (PLARGE_INTEGER)(((unsigned __int64)v40 << 6) + a4 + 144),
                *(_DWORD *)(((unsigned __int64)v40 << 6) + a4 + 152),
                (PVOID)(*(_QWORD *)(a4 + ((unsigned __int64)v40 << 6) + 96)
                      + *(unsigned int *)(((unsigned __int64)v40 << 6) + a4 + 108)),
                Flags,
                &BytesWritten,
                CallbackRoutine,
                CallbackContext);
        v6 = v42;
        if ( v42 != -1073741740 )
          break;
        Interval.QuadPart = -100000;
        KeDelayExecutionThread(0, 1u, &Interval);
      }
      CallbackRoutine = 0;
      if ( v42 < 0 )
        return v6;
      if ( (Flags & 8) != 0 )
        KeSetEvent((PRKEVENT)(a4 + ((unsigned __int64)*(unsigned int *)(a4 + 224) << 6) + 120), 0, 0);
    }
    v43 = *(unsigned int *)(a4 + 224);
    if ( v31 >= v32 )
      break;
    v44 = (unsigned __int64)(((_BYTE)v43 - 1) & 1) << 6;
    v45 = ((_BYTE)v43 - 1) & 1;
    if ( *(_QWORD *)(v44 + a4 + 96) )
    {
      LOBYTE(v34) = 1;
      FileProvWaitForWriteComplete(a4, ((_BYTE)v43 - 1) & 1, v34);
      if ( *(int *)(v44 + a4 + 112) < 0 )
      {
        v6 = *(_DWORD *)(v44 + a4 + 112);
        *(_DWORD *)(a4 + 224) = v45;
        return v6;
      }
    }
    else
    {
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x200000u, 0x44527066u);
      *(_QWORD *)(v44 + a4 + 96) = PoolWithTag;
      if ( !PoolWithTag )
        return (unsigned int)-1073741670;
      *(_QWORD *)(v44 + a4 + 104) = 0x200000;
      KeInitializeEvent((PRKEVENT)(v44 + a4 + 120), SynchronizationEvent, 0);
    }
    memmove(
      (void *)(*(_QWORD *)(v44 + a4 + 96) + *(unsigned int *)(v44 + a4 + 108)),
      (const void *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(a4 + 224) << 6) + a4 + 96)
                   + (*(_DWORD *)(a4 + 48) & 0xFFFFF000)),
      *(_DWORD *)(a4 + 48) & 0xFFF);
    v8 = v54;
    v47 = *(_DWORD *)(a4 + 48) & 0xFFF;
    *(_DWORD *)(a4 + 224) = v45;
    v48 = *(_DWORD *)(v44 + a4 + 108) + v47;
    *(_DWORD *)(a4 + 48) = v48;
    v49 = *(_QWORD *)(v44 + a4 + 96) + v48;
    v5 = v55;
    *(_QWORD *)(a4 + 24) = v49;
  }
  if ( *(_DWORD *)((v43 << 6) + a4 + 108) < *(_DWORD *)(a4 + 48) )
  {
    v50 = (unsigned __int64)(((_BYTE)v43 - 1) & 1) << 6;
    v51 = ((_BYTE)v43 - 1) & 1;
    if ( *(_QWORD *)(a4 + v50 + 96) )
    {
      LOBYTE(v34) = 1;
      FileProvWaitForWriteComplete(a4, ((_BYTE)v43 - 1) & 1, v34);
      if ( *(int *)(a4 + v50 + 112) < 0 )
        v6 = *(_DWORD *)(a4 + v50 + 112);
    }
    *(_DWORD *)(a4 + 224) = v51;
  }
  return v6;
}

```

## disassembly

```asm
0x14003a6f8  mov     rax, rsp
0x14003a6fb  mov     [rax+8], rbx
0x14003a6ff  mov     [rax+18h], r8d
0x14003a703  mov     [rax+10h], rdx
0x14003a707  push    rbp
0x14003a708  push    rsi
0x14003a709  push    rdi
0x14003a70a  push    r12
0x14003a70c  push    r13
0x14003a70e  push    r14
0x14003a710  push    r15
0x14003a712  sub     rsp, 60h
0x14003a716  xor     r13d, r13d
0x14003a719  mov     edi, r8d
0x14003a71c  mov     esi, r13d
0x14003a71f  mov     [rax+20h], r13d
0x14003a723  mov     rbx, r9
0x14003a726  mov     r8, rdx
0x14003a729  mov     r15, rcx
0x14003a72c  test    edi, edi
0x14003a72e  jz      loc_14003A835
0x14003a734  mov     rax, [r15+8]
0x14003a738  cmp     [rbx+20h], rax
0x14003a73c  jge     loc_14003A7FF
0x14003a742  mov     rax, [rbx+0F0h]
0x14003a749  mov     [rax+40h], r8
0x14003a74d  mov     rax, [rbx+8]
0x14003a751  mov     rcx, [rbx+0F0h]
0x14003a758  mov     eax, [rax]
0x14003a75a  mov     [rcx+58h], eax
0x14003a75d  mov     rax, [rbx+20h]
0x14003a761  mov     rcx, [rbx+0F0h]
0x14003a768  mov     [rcx+38h], rax
0x14003a76c  mov     rax, [rbx+8]
0x14003a770  mov     ecx, [rax]
0x14003a772  add     [rbx+20h], rcx
0x14003a776  mov     rcx, [r15+8]
0x14003a77a  cmp     [rbx+20h], rcx
0x14003a77e  jle     short loc_14003A795
0x14003a780  mov     rdx, [rbx+0F0h]
0x14003a787  mov     [rbx+20h], rcx
0x14003a78b  mov     ecx, [r15+8]
0x14003a78f  sub     ecx, [rdx+38h]
0x14003a792  mov     [rdx+58h], ecx
0x14003a795  mov     rcx, [rbx+0F0h]
0x14003a79c  mov     eax, [rcx+58h]
0x14003a79f  add     r8, rax
0x14003a7a2  sub     edi, eax
0x14003a7a4  cmp     dword ptr [rbx+34h], 1
0x14003a7a8  mov     [rsp+98h+arg_8], r8
0x14003a7b0  mov     [rsp+98h+arg_10], edi
0x14003a7b7  jbe     short loc_14003A7CA
0x14003a7b9  mov     edx, [rbx+38h]
0x14003a7bc  add     edx, 20h ; ' '
0x14003a7bf  call    WofTryQueueWorkItem
0x14003a7c4  test    al, al
0x14003a7c6  jz      short loc_14003A7D2
0x14003a7c8  jmp     short loc_14003A7DE
0x14003a7ca  mov     rax, [rbx+18h]
0x14003a7ce  mov     [rcx+48h], rax
0x14003a7d2  mov     rcx, [rbx+0F0h]
0x14003a7d9  call    FileProvCompressWorkItem
0x14003a7de  mov     eax, [rbx+0FCh]
0x14003a7e4  xor     edx, edx
0x14003a7e6  inc     dword ptr [rbx+100h]
0x14003a7ec  inc     eax
0x14003a7ee  div     dword ptr [rbx+34h]
0x14003a7f1  mov     r8, [rsp+98h+arg_8]
0x14003a7f9  mov     [rbx+0FCh], edx
0x14003a7ff  test    edi, edi
0x14003a801  jz      short loc_14003A835
0x14003a803  mov     rax, [r15+8]
0x14003a807  cmp     [rbx+20h], rax
0x14003a80b  jge     short loc_14003A835
0x14003a80d  mov     eax, [rbx+0FCh]
0x14003a813  cmp     eax, [rbx+0F8h]
0x14003a819  jz      short loc_14003A835
0x14003a81b  imul    rcx, rax, 88h
0x14003a822  add     rcx, [rbx+0E8h]
0x14003a829  mov     [rbx+0F0h], rcx
0x14003a830  jmp     loc_14003A72C
0x14003a835  mov     rdx, [rbx+0E8h]
0x14003a83c  cmp     [rbx+100h], r13d
0x14003a843  jz      loc_14003AC83
0x14003a849  mov     eax, [rbx+0F8h]
0x14003a84f  xor     r9d, r9d; Alertable
0x14003a852  imul    rcx, rax, 88h
0x14003a859  xor     r8d, r8d; WaitMode
0x14003a85c  mov     [rsp+98h+Timeout], r13; Timeout
0x14003a861  add     rcx, rdx
0x14003a864  xor     edx, edx; WaitReason
0x14003a866  mov     [rbx+0F0h], rcx
0x14003a86d  add     rcx, 60h ; '`'; Object
0x14003a871  call    cs:__imp_KeWaitForSingleObject
0x14003a878  nop     dword ptr [rax+rax+00h]
0x14003a87d  mov     eax, [rbx+0F8h]
0x14003a883  xor     edx, edx
0x14003a885  mov     r8d, [rbx+34h]
0x14003a889  inc     eax
0x14003a88b  dec     dword ptr [rbx+100h]
0x14003a891  div     r8d
0x14003a894  mov     rax, [rbx+0F0h]
0x14003a89b  mov     [rbx+0F8h], edx
0x14003a8a1  mov     ecx, [rax+80h]
0x14003a8a7  test    ecx, ecx
0x14003a8a9  js      loc_14003AC7F
0x14003a8af  cmp     r8d, 1
0x14003a8b3  jbe     short loc_14003A8CD
0x14003a8b5  mov     r8d, [rax+5Ch]; Size
0x14003a8b9  mov     rdx, [rax+48h]; Src
0x14003a8bd  mov     rcx, [rbx+18h]; void *
0x14003a8c1  call    memmove
0x14003a8c6  mov     rax, [rbx+0F0h]
0x14003a8cd  mov     r10, [rbx+28h]
0x14003a8d1  test    r10, r10
0x14003a8d4  jle     short loc_14003A907
0x14003a8d6  mov     rax, [rax+38h]
0x14003a8da  mov     rcx, [rbx+8]
0x14003a8de  cqo
0x14003a8e0  mov     r9d, [rbx+10h]
0x14003a8e4  mov     r8d, [rcx]
0x14003a8e7  idiv    r8
0x14003a8ea  mov     rdx, [rbx+60h]
0x14003a8ee  dec     rax
0x14003a8f1  imul    rax, r9
0x14003a8f5  cmp     r9d, 4
0x14003a8f9  jnz     short loc_14003A903
0x14003a8fb  mov     ecx, r10d
0x14003a8fe  mov     [rax+rdx], ecx
0x14003a901  jmp     short loc_14003A907
0x14003a903  mov     [rax+rdx], r10
0x14003a907  mov     rcx, [rbx+0F0h]
0x14003a90e  mov     edx, [rbx+0E0h]
0x14003a914  shl     rdx, 6
0x14003a918  mov     eax, [rcx+5Ch]
0x14003a91b  add     [rbx+28h], rax
0x14003a91f  mov     eax, [rcx+5Ch]
0x14003a922  add     [rbx+30h], eax
0x14003a925  mov     r8d, [rbx+30h]
0x14003a929  mov     r11, [rbx+28h]
0x14003a92d  mov     eax, r8d
0x14003a930  add     rax, [rdx+rbx+60h]
0x14003a935  mov     [rbx+18h], rax
0x14003a939  mov     rax, [rbx+8]
0x14003a93d  mov     eax, [rax]
0x14003a93f  add     eax, r8d
0x14003a942  cmp     eax, [rdx+rbx+68h]
0x14003a946  ja      short loc_14003A961
0x14003a948  mov     eax, [rcx+58h]
0x14003a94b  add     rax, [rcx+38h]
0x14003a94f  mov     r8, [rsp+98h+arg_8]
0x14003a957  cmp     rax, [r15+8]
0x14003a95b  jl      loc_14003A72C
0x14003a961  mov     ebp, [rcx+58h]
0x14003a964  lea     rdi, [rbx+128h]
0x14003a96b  add     rbp, [rcx+38h]
0x14003a96f  mov     ecx, [rbx+14h]
0x14003a972  imul    ecx, [rbx+10h]
0x14003a976  mov     r14, [r15+8]
0x14003a97a  add     rcx, r11
0x14003a97d  mov     [rdi], rcx
0x14003a980  cmp     rbp, r14
0x14003a983  jge     short loc_14003A98F
0x14003a985  and     rcx, 0FFFFFFFFFFFFF000h
0x14003a98c  mov     [rdi], rcx
0x14003a98f  mov     rdx, [rbx+48h]; FileObject
0x14003a993  mov     r9d, 8; Length
0x14003a999  mov     rcx, [rbx+40h]; Instance
0x14003a99d  mov     r8, rdi; FileInformation
0x14003a9a0  mov     dword ptr [rsp+98h+Timeout], 14h; FileInformationClass
0x14003a9a8  call    cs:__imp_FltSetInformationFile
0x14003a9af  nop     dword ptr [rax+rax+00h]
0x14003a9b4  mov     esi, eax
0x14003a9b6  test    eax, eax
0x14003a9b8  js      loc_14003AC9A
0x14003a9be  cmp     rbp, r14
0x14003a9c1  jl      short loc_14003A9D8
0x14003a9c3  cmp     [rbx+0E0h], r13d
0x14003a9ca  jnz     short loc_14003A9D8
0x14003a9cc  mov     ecx, [rbx+68h]
0x14003a9cf  cmp     [rdi], rcx
0x14003a9d2  jl      loc_14003AC24
0x14003a9d8  mov     ecx, [rbx+14h]
0x14003a9db  imul    ecx, [rbx+10h]
0x14003a9df  mov     edx, [rbx+0E0h]
0x14003a9e5  shl     rdx, 6
0x14003a9e9  mov     eax, [rdx+rbx+6Ch]
0x14003a9ed  add     rcx, rax
0x14003a9f0  mov     eax, [rbx+30h]
0x14003a9f3  sub     rcx, rax
0x14003a9f6  add     rcx, [rbx+28h]
0x14003a9fa  mov     [rdx+rbx+90h], rcx
0x14003aa02  mov     ecx, [rbx+0E0h]
0x14003aa08  mov     edx, [rbx+30h]
0x14003aa0b  shl     rcx, 6
0x14003aa0f  mov     eax, [rcx+rbx+6Ch]
0x14003aa13  cmp     eax, edx
0x14003aa15  jnb     loc_14003AB36
0x14003aa1b  cmp     cs:VersionInformation.dwBuildNumber, 265Ch
0x14003aa25  mov     r12d, 7
0x14003aa2b  lea     r8d, [r12+8]
0x14003aa30  cmovb   r12d, r8d
0x14003aa34  sub     edx, eax
0x14003aa36  cmp     rbp, r14
0x14003aa39  mov     edi, r12d
0x14003aa3c  lea     eax, [rdx+0FFFh]
0x14003aa42  cmovge  edx, eax
0x14003aa45  lea     rax, FileProvSimpleCompletionRoutine
0x14003aa4c  and     edx, 0FFFFF000h
0x14003aa52  and     edi, 8
0x14003aa55  mov     [rcx+rbx+98h], edx
0x14003aa5c  cmovz   r13, rax
0x14003aa60  test    edi, edi
0x14003aa62  jz      short loc_14003AA6E
0x14003aa64  mov     ecx, [rbx+0E0h]
0x14003aa6a  xor     edx, edx
0x14003aa6c  jmp     short loc_14003AA81
0x14003aa6e  mov     ecx, [rbx+0E0h]
0x14003aa74  mov     edx, ecx
0x14003aa76  shl     rdx, 6
0x14003aa7a  add     rdx, 60h ; '`'
0x14003aa7e  add     rdx, rbx
0x14003aa81  mov     [rsp+98h+CallbackContext], rdx; CallbackContext
0x14003aa86  lea     r8, [rbx+90h]
0x14003aa8d  mov     rdx, [rbx+48h]; FileObject
0x14003aa91  mov     r9d, ecx
0x14003aa94  lea     rcx, [rsp+98h+arg_18]
0x14003aa9c  shl     r9, 6
0x14003aaa0  mov     [rsp+98h+CallbackRoutine], r13; CallbackRoutine
0x14003aaa5  add     r8, r9; ByteOffset
0x14003aaa8  mov     [rsp+98h+BytesWritten], rcx; BytesWritten
0x14003aaad  mov     rcx, [rbx+40h]; InitiatingInstance
0x14003aab1  mov     eax, [r9+rbx+6Ch]
0x14003aab6  add     rax, [rbx+r9+60h]
0x14003aabb  mov     r9d, [r9+rbx+98h]; Length
0x14003aac3  mov     [rsp+98h+Flags], r12d; Flags
0x14003aac8  mov     [rsp+98h+Timeout], rax; Buffer
0x14003aacd  call    cs:__imp_FltWriteFile
0x14003aad4  nop     dword ptr [rax+rax+00h]
0x14003aad9  mov     esi, eax
0x14003aadb  cmp     eax, 0C0000054h
0x14003aae0  jnz     short loc_14003AB05
0x14003aae2  lea     r8, [rsp+98h+Interval]; Interval
0x14003aae7  mov     qword ptr [rsp+98h+Interval], 0FFFFFFFFFFFE7960h
0x14003aaf0  mov     dl, 1; Alertable
0x14003aaf2  xor     ecx, ecx; WaitMode
0x14003aaf4  call    cs:__imp_KeDelayExecutionThread
0x14003aafb  nop     dword ptr [rax+rax+00h]
0x14003ab00  jmp     loc_14003AA60
0x14003ab05  xor     r13d, r13d
0x14003ab08  test    eax, eax
0x14003ab0a  js      loc_14003AC9A
0x14003ab10  test    edi, edi
0x14003ab12  jz      short loc_14003AB36
0x14003ab14  mov     ecx, [rbx+0E0h]
0x14003ab1a  xor     r8d, r8d; Wait
0x14003ab1d  shl     rcx, 6
0x14003ab21  xor     edx, edx; Increment
0x14003ab23  add     rcx, 78h ; 'x'
0x14003ab27  add     rcx, rbx; Event
0x14003ab2a  call    cs:__imp_KeSetEvent
0x14003ab31  nop     dword ptr [rax+rax+00h]
0x14003ab36  mov     edx, [rbx+0E0h]
0x14003ab3c  cmp     rbp, r14
0x14003ab3f  jge     loc_14003AC3B
0x14003ab45  lea     eax, [rdx-1]
0x14003ab48  and     eax, 1
0x14003ab4b  mov     edi, eax
0x14003ab4d  shl     rdi, 6
0x14003ab51  mov     ebp, eax
0x14003ab53  cmp     [rdi+rbx+60h], r13
0x14003ab58  jnz     short loc_14003ABA9
0x14003ab5a  mov     edx, 200000h; NumberOfBytes
0x14003ab5f  mov     ecx, 1; PoolType
0x14003ab64  mov     r8d, 44527066h; Tag
0x14003ab6a  call    cs:__imp_ExAllocatePoolWithTag
0x14003ab71  nop     dword ptr [rax+rax+00h]
0x14003ab76  mov     [rdi+rbx+60h], rax
0x14003ab7b  test    rax, rax
0x14003ab7e  jz      loc_14003AC2A
0x14003ab84  xor     r8d, r8d; State
0x14003ab87  mov     qword ptr [rdi+rbx+68h], 200000h
0x14003ab90  lea     rcx, [rbx+78h]
0x14003ab94  add     rcx, rdi; Event
0x14003ab97  lea     edx, [r8+1]; Type
0x14003ab9b  call    cs:__imp_KeInitializeEvent
0x14003aba2  nop     dword ptr [rax+rax+00h]
0x14003aba7  jmp     short loc_14003ABBE
0x14003aba9  mov     r8b, 1
0x14003abac  mov     edx, ebp
0x14003abae  mov     rcx, rbx
0x14003abb1  call    FileProvWaitForWriteComplete
0x14003abb6  mov     eax, [rdi+rbx+70h]
0x14003abba  test    eax, eax
0x14003abbc  js      short loc_14003AC31
0x14003abbe  mov     edx, [rbx+30h]
0x14003abc1  mov     eax, [rbx+0E0h]
0x14003abc7  mov     r8d, edx
0x14003abca  mov     ecx, [rdi+rbx+6Ch]
0x14003abce  and     rdx, 0FFFFFFFFFFFFF000h
  ... truncated ...
```
