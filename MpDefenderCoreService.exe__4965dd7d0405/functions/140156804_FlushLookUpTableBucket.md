# FlushLookUpTableBucket

- ea: `0x140156804`
- end: `0x14015693f`
- name: `FlushLookUpTableBucket`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14015698c`
- `0x140156d5c`

## callees

- `0x14003a5c0`
- `0x140156804`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140156918`
- `KERNEL32!HeapFree` at `0x140156918`
- `KERNEL32!GetProcessHeap` at `0x14015690a`
- `KERNEL32!GetProcessHeap` at `0x14015690a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14015683c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14015683c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14015689f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14015689f`
- `ADVAPI32!EventWriteTransfer` at `0x1401568fd`
- `ADVAPI32!EventWriteTransfer` at `0x1401568fd`

## pseudocode

```c
__int64 __fastcall FlushLookUpTableBucket(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  RTL_SRWLOCK *v5; // rbp
  __int64 v6; // rdi
  __int64 *v7; // rax
  unsigned int v8; // esi
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 *v11; // rdx
  __int64 i; // rcx
  REGHANDLE v13; // rbp
  PEVENT_DATA_DESCRIPTOR *v14; // rbx
  int v15; // edx
  __int64 v16; // rcx
  PEVENT_DATA_DESCRIPTOR v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // [rsp+30h] [rbp-28h] BYREF

  v2 = a2;
  if ( !*(_QWORD *)(a1 + 8LL * a2) )
    return 0;
  v5 = (RTL_SRWLOCK *)(a1 + 264);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 264));
  v6 = *(_QWORD *)(a1 + 8 * v2);
  v7 = &v19;
  *(_QWORD *)(a1 + 8 * v2) = 0;
  v8 = 0;
  v19 = v6;
  if ( v6 )
  {
    v9 = v6;
    do
    {
      v10 = *(_QWORD *)(v9 + 32);
      *(_QWORD *)(v9 + 32) = 0;
      v7 = (__int64 *)(*v7 + 24);
      v11 = v7;
      for ( i = *v7; i; i = *(_QWORD *)(i + 32) )
        v11 = (__int64 *)(i + 32);
      *v11 = v10;
      ++v8;
      v9 = *v7;
    }
    while ( *v7 );
  }
  *(_DWORD *)(a1 + 256) -= v8;
  ReleaseSRWLockExclusive(v5);
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 328) + 32LL);
  while ( v6 )
  {
    v14 = (PEVENT_DATA_DESCRIPTOR *)(v6 + 16);
    v15 = 2;
    if ( (unsigned int)*(unsigned __int8 *)(v6 + 45) + 2 > 2 )
    {
      v16 = 2;
      do
      {
        ++v16;
        ++v15;
        (*v14)[v16 - 1].Reserved1 = 0;
      }
      while ( v15 < *(unsigned __int8 *)(v6 + 45) + 2 );
    }
    EventWriteTransfer(v13, (PCEVENT_DESCRIPTOR)v6, 0, 0, *(unsigned __int8 *)(v6 + 44), *v14);
    v6 = *(_QWORD *)(v6 + 24);
    v17 = *v14;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
  }
  return v8;
}

```

## disassembly

```asm
0x140156804  mov     [rsp+arg_10], rbx
0x140156809  push    rbp
0x14015680a  push    rsi
0x14015680b  push    rdi
0x14015680c  sub     rsp, 40h
0x140156810  mov     rax, cs:__security_cookie
0x140156817  xor     rax, rsp
0x14015681a  mov     [rsp+58h+var_20], rax
0x14015681f  mov     esi, edx
0x140156821  mov     rbx, rcx
0x140156824  cmp     qword ptr [rcx+rsi*8], 0
0x140156829  jnz     short loc_140156832
0x14015682b  xor     eax, eax
0x14015682d  jmp     loc_140156925
0x140156832  lea     rbp, [rcx+108h]
0x140156839  mov     rcx, rbp; SRWLock
0x14015683c  call    cs:__imp_AcquireSRWLockExclusive
0x140156842  mov     rdi, [rbx+rsi*8]
0x140156846  lea     rax, [rsp+58h+var_28]
0x14015684b  mov     qword ptr [rbx+rsi*8], 0
0x140156853  xor     esi, esi
0x140156855  mov     [rsp+58h+var_28], rdi
0x14015685a  test    rdi, rdi
0x14015685d  jz      short loc_140156896
0x14015685f  mov     rcx, rdi
0x140156862  mov     r8, [rcx+20h]
0x140156866  mov     qword ptr [rcx+20h], 0
0x14015686e  mov     rax, [rax]
0x140156871  add     rax, 18h
0x140156875  mov     rdx, rax
0x140156878  mov     rcx, [rax]
0x14015687b  jmp     short loc_140156884
0x14015687d  lea     rdx, [rcx+20h]
0x140156881  mov     rcx, [rdx]
0x140156884  test    rcx, rcx
0x140156887  jnz     short loc_14015687D
0x140156889  mov     [rdx], r8
0x14015688c  inc     esi
0x14015688e  mov     rcx, [rax]
0x140156891  test    rcx, rcx
0x140156894  jnz     short loc_140156862
0x140156896  sub     [rbx+100h], esi
0x14015689c  mov     rcx, rbp; SRWLock
0x14015689f  call    cs:__imp_ReleaseSRWLockExclusive
0x1401568a5  mov     rax, [rbx+148h]
0x1401568ac  mov     rbp, [rax+20h]
0x1401568b0  jmp     short loc_14015691E
0x1401568b2  movzx   eax, byte ptr [rdi+2Dh]
0x1401568b6  lea     rbx, [rdi+10h]
0x1401568ba  mov     edx, 2
0x1401568bf  add     eax, edx
0x1401568c1  cmp     eax, edx
0x1401568c3  jbe     short loc_1401568E1
0x1401568c5  lea     ecx, [rdx+1Eh]
0x1401568c8  mov     rax, [rbx]
0x1401568cb  lea     rcx, [rcx+10h]
0x1401568cf  inc     edx
0x1401568d1  mov     byte ptr [rax+rcx-3], 0
0x1401568d6  movzx   eax, byte ptr [rdi+2Dh]
0x1401568da  add     eax, 2
0x1401568dd  cmp     edx, eax
0x1401568df  jl      short loc_1401568C8
0x1401568e1  movzx   ecx, byte ptr [rdi+2Ch]
0x1401568e5  xor     r9d, r9d; RelatedActivityId
0x1401568e8  mov     rax, [rbx]
0x1401568eb  xor     r8d, r8d; ActivityId
0x1401568ee  mov     [rsp+58h+UserData], rax; UserData
0x1401568f3  mov     rdx, rdi; EventDescriptor
0x1401568f6  mov     [rsp+58h+UserDataCount], ecx; UserDataCount
0x1401568fa  mov     rcx, rbp; RegHandle
0x1401568fd  call    cs:__imp_EventWriteTransfer
0x140156903  mov     rdi, [rdi+18h]
0x140156907  mov     rbx, [rbx]
0x14015690a  call    cs:__imp_GetProcessHeap
0x140156910  mov     r8, rbx; lpMem
0x140156913  xor     edx, edx; dwFlags
0x140156915  mov     rcx, rax; hHeap
0x140156918  call    cs:__imp_HeapFree
0x14015691e  test    rdi, rdi
0x140156921  jnz     short loc_1401568B2
0x140156923  mov     eax, esi
0x140156925  mov     rcx, [rsp+58h+var_20]
0x14015692a  xor     rcx, rsp; StackCookie
0x14015692d  call    __security_check_cookie
0x140156932  mov     rbx, [rsp+58h+arg_10]
0x140156937  add     rsp, 40h
0x14015693b  pop     rdi
0x14015693c  pop     rsi
0x14015693d  pop     rbp
0x14015693e  retn
```
