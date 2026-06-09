# FlushLookUpTableBucket

- ea: `0x18001ab60`
- end: `0x18001ac7b`
- name: `FlushLookUpTableBucket`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b010`
- `0x18001b3f4`

## callees

- `0x1800022fa`
- `0x18001ab60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ac57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ac57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ac65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ac65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001abee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001abee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ab86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ab86`

## pseudocode

```c
__int64 __fastcall FlushLookUpTableBucket(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  RTL_SRWLOCK *v5; // rbp
  __int64 v6; // rdi
  unsigned int v7; // esi
  __int64 *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 *v12; // rdx
  REGHANDLE v13; // rbp
  PEVENT_DATA_DESCRIPTOR *v14; // rbx
  int v15; // edx
  __int64 v16; // rcx
  PEVENT_DATA_DESCRIPTOR v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF

  v2 = a2;
  if ( !*(_QWORD *)(a1 + 8LL * a2) )
    return 0;
  v5 = (RTL_SRWLOCK *)(a1 + 264);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 264));
  v6 = *(_QWORD *)(a1 + 8 * v2);
  *(_QWORD *)(a1 + 8 * v2) = 0;
  v7 = 0;
  v19 = v6;
  if ( v6 )
  {
    v8 = &v19;
    v9 = v6;
    do
    {
      v10 = *(_QWORD *)(v9 + 32);
      *(_QWORD *)(v9 + 32) = 0;
      v8 = (__int64 *)(*v8 + 24);
      v11 = *v8;
      if ( *v8 )
      {
        do
        {
          v12 = (__int64 *)(v11 + 32);
          v11 = *(_QWORD *)(v11 + 32);
        }
        while ( v11 );
      }
      else
      {
        v12 = v8;
      }
      *v12 = v10;
      ++v7;
      v9 = *v8;
    }
    while ( *v8 );
  }
  *(_DWORD *)(a1 + 256) -= v7;
  ReleaseSRWLockExclusive(v5);
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 328) + 32LL);
  while ( v6 )
  {
    v14 = (PEVENT_DATA_DESCRIPTOR *)(v6 + 16);
    v15 = 2;
    if ( (unsigned int)*(unsigned __int8 *)(v6 + 45) + 2 > 2 )
    {
      do
      {
        v16 = v15++;
        (*v14)[v16].Reserved1 = 0;
      }
      while ( v15 < *(unsigned __int8 *)(v6 + 45) + 2 );
    }
    EventWriteTransfer_0(v13, (PCEVENT_DESCRIPTOR)v6, 0, 0, *(unsigned __int8 *)(v6 + 44), *v14);
    v6 = *(_QWORD *)(v6 + 24);
    v17 = *v14;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
  }
  return v7;
}

```

## disassembly

```asm
0x18001ab60  push    rbx
0x18001ab62  push    rbp
0x18001ab63  push    rsi
0x18001ab64  push    rdi
0x18001ab65  sub     rsp, 38h
0x18001ab69  mov     esi, edx
0x18001ab6b  mov     rbx, rcx
0x18001ab6e  cmp     qword ptr [rcx+rsi*8], 0
0x18001ab73  jnz     short loc_18001AB7C
0x18001ab75  xor     eax, eax
0x18001ab77  jmp     loc_18001AC72
0x18001ab7c  lea     rbp, [rcx+108h]
0x18001ab83  mov     rcx, rbp; SRWLock
0x18001ab86  call    cs:__imp_AcquireSRWLockExclusive
0x18001ab8c  mov     rdi, [rbx+rsi*8]
0x18001ab90  mov     qword ptr [rbx+rsi*8], 0
0x18001ab98  xor     esi, esi
0x18001ab9a  mov     [rsp+58h+arg_0], rdi
0x18001ab9f  test    rdi, rdi
0x18001aba2  jz      short loc_18001ABE5
0x18001aba4  lea     rax, [rsp+58h+arg_0]
0x18001aba9  mov     rcx, rdi
0x18001abac  mov     r8, [rcx+20h]
0x18001abb0  mov     qword ptr [rcx+20h], 0
0x18001abb8  mov     rax, [rax]
0x18001abbb  add     rax, 18h
0x18001abbf  mov     rcx, [rax]
0x18001abc2  test    rcx, rcx
0x18001abc5  jz      short loc_18001ABD5
0x18001abc7  lea     rdx, [rcx+20h]
0x18001abcb  mov     rcx, [rdx]
0x18001abce  test    rcx, rcx
0x18001abd1  jnz     short loc_18001ABC7
0x18001abd3  jmp     short loc_18001ABD8
0x18001abd5  mov     rdx, rax
0x18001abd8  mov     [rdx], r8
0x18001abdb  inc     esi
0x18001abdd  mov     rcx, [rax]
0x18001abe0  test    rcx, rcx
0x18001abe3  jnz     short loc_18001ABAC
0x18001abe5  sub     [rbx+100h], esi
0x18001abeb  mov     rcx, rbp; SRWLock
0x18001abee  call    cs:__imp_ReleaseSRWLockExclusive
0x18001abf4  mov     rax, [rbx+148h]
0x18001abfb  mov     rbp, [rax+20h]
0x18001abff  jmp     short loc_18001AC6B
0x18001ac01  movzx   eax, byte ptr [rdi+2Dh]
0x18001ac05  lea     rbx, [rdi+10h]
0x18001ac09  mov     edx, 2
0x18001ac0e  add     eax, edx
0x18001ac10  cmp     eax, edx
0x18001ac12  jbe     short loc_18001AC2F
0x18001ac14  mov     rax, [rbx]
0x18001ac17  movsxd  rcx, edx
0x18001ac1a  inc     edx
0x18001ac1c  add     rcx, rcx
0x18001ac1f  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18001ac24  movzx   eax, byte ptr [rdi+2Dh]
0x18001ac28  add     eax, 2
0x18001ac2b  cmp     edx, eax
0x18001ac2d  jl      short loc_18001AC14
0x18001ac2f  movzx   ecx, byte ptr [rdi+2Ch]
0x18001ac33  xor     r9d, r9d; RelatedActivityId
0x18001ac36  mov     rax, [rbx]
0x18001ac39  xor     r8d, r8d; ActivityId
0x18001ac3c  mov     [rsp+58h+UserData], rax; UserData
0x18001ac41  mov     rdx, rdi; EventDescriptor
0x18001ac44  mov     [rsp+58h+UserDataCount], ecx; UserDataCount
0x18001ac48  mov     rcx, rbp; RegHandle
0x18001ac4b  call    EventWriteTransfer_0
0x18001ac50  mov     rdi, [rdi+18h]
0x18001ac54  mov     rbx, [rbx]
0x18001ac57  call    cs:__imp_GetProcessHeap
0x18001ac5d  mov     r8, rbx; lpMem
0x18001ac60  xor     edx, edx; dwFlags
0x18001ac62  mov     rcx, rax; hHeap
0x18001ac65  call    cs:__imp_HeapFree
0x18001ac6b  test    rdi, rdi
0x18001ac6e  jnz     short loc_18001AC01
0x18001ac70  mov     eax, esi
0x18001ac72  add     rsp, 38h
0x18001ac76  pop     rdi
0x18001ac77  pop     rsi
0x18001ac78  pop     rbp
0x18001ac79  pop     rbx
0x18001ac7a  retn
```
