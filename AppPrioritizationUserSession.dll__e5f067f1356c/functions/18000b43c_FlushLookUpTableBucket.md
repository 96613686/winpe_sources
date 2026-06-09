# FlushLookUpTableBucket

- ea: `0x18000b43c`
- end: `0x18000b557`
- name: `FlushLookUpTableBucket`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5b0`
- `0x18000b994`

## callees

- `0x180003437`
- `0x18000b43c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b462`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b462`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b533`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b533`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b541`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b541`

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
0x18000b43c  push    rbx
0x18000b43e  push    rbp
0x18000b43f  push    rsi
0x18000b440  push    rdi
0x18000b441  sub     rsp, 38h
0x18000b445  mov     esi, edx
0x18000b447  mov     rbx, rcx
0x18000b44a  cmp     qword ptr [rcx+rsi*8], 0
0x18000b44f  jnz     short loc_18000B458
0x18000b451  xor     eax, eax
0x18000b453  jmp     loc_18000B54E
0x18000b458  lea     rbp, [rcx+108h]
0x18000b45f  mov     rcx, rbp; SRWLock
0x18000b462  call    cs:__imp_AcquireSRWLockExclusive
0x18000b468  mov     rdi, [rbx+rsi*8]
0x18000b46c  mov     qword ptr [rbx+rsi*8], 0
0x18000b474  xor     esi, esi
0x18000b476  mov     [rsp+58h+arg_0], rdi
0x18000b47b  test    rdi, rdi
0x18000b47e  jz      short loc_18000B4C1
0x18000b480  lea     rax, [rsp+58h+arg_0]
0x18000b485  mov     rcx, rdi
0x18000b488  mov     r8, [rcx+20h]
0x18000b48c  mov     qword ptr [rcx+20h], 0
0x18000b494  mov     rax, [rax]
0x18000b497  add     rax, 18h
0x18000b49b  mov     rcx, [rax]
0x18000b49e  test    rcx, rcx
0x18000b4a1  jz      short loc_18000B4B1
0x18000b4a3  lea     rdx, [rcx+20h]
0x18000b4a7  mov     rcx, [rdx]
0x18000b4aa  test    rcx, rcx
0x18000b4ad  jnz     short loc_18000B4A3
0x18000b4af  jmp     short loc_18000B4B4
0x18000b4b1  mov     rdx, rax
0x18000b4b4  mov     [rdx], r8
0x18000b4b7  inc     esi
0x18000b4b9  mov     rcx, [rax]
0x18000b4bc  test    rcx, rcx
0x18000b4bf  jnz     short loc_18000B488
0x18000b4c1  sub     [rbx+100h], esi
0x18000b4c7  mov     rcx, rbp; SRWLock
0x18000b4ca  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b4d0  mov     rax, [rbx+148h]
0x18000b4d7  mov     rbp, [rax+20h]
0x18000b4db  jmp     short loc_18000B547
0x18000b4dd  movzx   eax, byte ptr [rdi+2Dh]
0x18000b4e1  lea     rbx, [rdi+10h]
0x18000b4e5  mov     edx, 2
0x18000b4ea  add     eax, edx
0x18000b4ec  cmp     eax, edx
0x18000b4ee  jbe     short loc_18000B50B
0x18000b4f0  mov     rax, [rbx]
0x18000b4f3  movsxd  rcx, edx
0x18000b4f6  inc     edx
0x18000b4f8  add     rcx, rcx
0x18000b4fb  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18000b500  movzx   eax, byte ptr [rdi+2Dh]
0x18000b504  add     eax, 2
0x18000b507  cmp     edx, eax
0x18000b509  jl      short loc_18000B4F0
0x18000b50b  movzx   ecx, byte ptr [rdi+2Ch]
0x18000b50f  xor     r9d, r9d; RelatedActivityId
0x18000b512  mov     rax, [rbx]
0x18000b515  xor     r8d, r8d; ActivityId
0x18000b518  mov     [rsp+58h+UserData], rax; UserData
0x18000b51d  mov     rdx, rdi; EventDescriptor
0x18000b520  mov     [rsp+58h+UserDataCount], ecx; UserDataCount
0x18000b524  mov     rcx, rbp; RegHandle
0x18000b527  call    EventWriteTransfer_0
0x18000b52c  mov     rdi, [rdi+18h]
0x18000b530  mov     rbx, [rbx]
0x18000b533  call    cs:__imp_GetProcessHeap
0x18000b539  mov     r8, rbx; lpMem
0x18000b53c  xor     edx, edx; dwFlags
0x18000b53e  mov     rcx, rax; hHeap
0x18000b541  call    cs:__imp_HeapFree
0x18000b547  test    rdi, rdi
0x18000b54a  jnz     short loc_18000B4DD
0x18000b54c  mov     eax, esi
0x18000b54e  add     rsp, 38h
0x18000b552  pop     rdi
0x18000b553  pop     rsi
0x18000b554  pop     rbp
0x18000b555  pop     rbx
0x18000b556  retn
```
