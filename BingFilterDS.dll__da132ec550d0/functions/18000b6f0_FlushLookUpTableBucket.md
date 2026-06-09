# FlushLookUpTableBucket

- ea: `0x18000b6f0`
- end: `0x18000b80b`
- name: `FlushLookUpTableBucket`
- size: `283`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb9c`
- `0x18000bf80`

## callees

- `0x180002b86`
- `0x18000b6f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b77e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b77e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b716`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b716`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7f5`

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
0x18000b6f0  push    rbx
0x18000b6f2  push    rbp
0x18000b6f3  push    rsi
0x18000b6f4  push    rdi
0x18000b6f5  sub     rsp, 38h
0x18000b6f9  mov     esi, edx
0x18000b6fb  mov     rbx, rcx
0x18000b6fe  cmp     qword ptr [rcx+rsi*8], 0
0x18000b703  jnz     short loc_18000B70C
0x18000b705  xor     eax, eax
0x18000b707  jmp     loc_18000B802
0x18000b70c  lea     rbp, [rcx+108h]
0x18000b713  mov     rcx, rbp; SRWLock
0x18000b716  call    cs:__imp_AcquireSRWLockExclusive
0x18000b71c  mov     rdi, [rbx+rsi*8]
0x18000b720  mov     qword ptr [rbx+rsi*8], 0
0x18000b728  xor     esi, esi
0x18000b72a  mov     [rsp+58h+arg_0], rdi
0x18000b72f  test    rdi, rdi
0x18000b732  jz      short loc_18000B775
0x18000b734  lea     rax, [rsp+58h+arg_0]
0x18000b739  mov     rcx, rdi
0x18000b73c  mov     r8, [rcx+20h]
0x18000b740  mov     qword ptr [rcx+20h], 0
0x18000b748  mov     rax, [rax]
0x18000b74b  add     rax, 18h
0x18000b74f  mov     rcx, [rax]
0x18000b752  test    rcx, rcx
0x18000b755  jz      short loc_18000B765
0x18000b757  lea     rdx, [rcx+20h]
0x18000b75b  mov     rcx, [rdx]
0x18000b75e  test    rcx, rcx
0x18000b761  jnz     short loc_18000B757
0x18000b763  jmp     short loc_18000B768
0x18000b765  mov     rdx, rax
0x18000b768  mov     [rdx], r8
0x18000b76b  inc     esi
0x18000b76d  mov     rcx, [rax]
0x18000b770  test    rcx, rcx
0x18000b773  jnz     short loc_18000B73C
0x18000b775  sub     [rbx+100h], esi
0x18000b77b  mov     rcx, rbp; SRWLock
0x18000b77e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b784  mov     rax, [rbx+148h]
0x18000b78b  mov     rbp, [rax+20h]
0x18000b78f  jmp     short loc_18000B7FB
0x18000b791  movzx   eax, byte ptr [rdi+2Dh]
0x18000b795  lea     rbx, [rdi+10h]
0x18000b799  mov     edx, 2
0x18000b79e  add     eax, edx
0x18000b7a0  cmp     eax, edx
0x18000b7a2  jbe     short loc_18000B7BF
0x18000b7a4  mov     rax, [rbx]
0x18000b7a7  movsxd  rcx, edx
0x18000b7aa  inc     edx
0x18000b7ac  add     rcx, rcx
0x18000b7af  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18000b7b4  movzx   eax, byte ptr [rdi+2Dh]
0x18000b7b8  add     eax, 2
0x18000b7bb  cmp     edx, eax
0x18000b7bd  jl      short loc_18000B7A4
0x18000b7bf  movzx   ecx, byte ptr [rdi+2Ch]
0x18000b7c3  xor     r9d, r9d; RelatedActivityId
0x18000b7c6  mov     rax, [rbx]
0x18000b7c9  xor     r8d, r8d; ActivityId
0x18000b7cc  mov     [rsp+58h+UserData], rax; UserData
0x18000b7d1  mov     rdx, rdi; EventDescriptor
0x18000b7d4  mov     [rsp+58h+UserDataCount], ecx; UserDataCount
0x18000b7d8  mov     rcx, rbp; RegHandle
0x18000b7db  call    EventWriteTransfer_0
0x18000b7e0  mov     rdi, [rdi+18h]
0x18000b7e4  mov     rbx, [rbx]
0x18000b7e7  call    cs:__imp_GetProcessHeap
0x18000b7ed  mov     r8, rbx; lpMem
0x18000b7f0  xor     edx, edx; dwFlags
0x18000b7f2  mov     rcx, rax; hHeap
0x18000b7f5  call    cs:__imp_HeapFree
0x18000b7fb  test    rdi, rdi
0x18000b7fe  jnz     short loc_18000B791
0x18000b800  mov     eax, esi
0x18000b802  add     rsp, 38h
0x18000b806  pop     rdi
0x18000b807  pop     rsi
0x18000b808  pop     rbp
0x18000b809  pop     rbx
0x18000b80a  retn
```
