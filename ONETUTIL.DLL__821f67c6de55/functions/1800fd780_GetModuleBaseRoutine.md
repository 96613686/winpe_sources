# GetModuleBaseRoutine

- ea: `0x1800fd780`
- end: `0x1800fdcff`
- name: `GetModuleBaseRoutine`
- size: `1407`
- prototype: `DWORD64 __stdcall(HANDLE hProcess, DWORD64 Address)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800fd608`
- `0x1800fdd00`

## callees

- `0x180083790`
- `0x1800838f0`
- `0x180083b70`
- `0x180083bb0`
- `0x180083bf0`
- `0x1800962c0`
- `0x1800b44b0`
- `0x1800b44f0`
- `0x1800fd484`
- `0x1800fd780`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800fd8a9`
- `KERNEL32!SetEvent` at `0x1800fd8a9`
- `KERNEL32!GetTickCount` at `0x1800fda4b`
- `KERNEL32!GetTickCount` at `0x1800fdcd7`
- `KERNEL32!GetTickCount` at `0x1800fdced`
- `KERNEL32!GetTickCount` at `0x1800fda4b`
- `KERNEL32!GetTickCount` at `0x1800fdcd7`
- `KERNEL32!GetTickCount` at `0x1800fdced`
- `KERNEL32!GetCurrentThreadId` at `0x1800fdb25`
- `KERNEL32!GetCurrentThreadId` at `0x1800fdb36`
- `KERNEL32!GetCurrentThreadId` at `0x1800fdb25`
- `KERNEL32!GetCurrentThreadId` at `0x1800fdb36`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800fdb8d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800fdba5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800fdb8d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800fdba5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fd82c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fd920`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fdaaf`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fd82c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fd920`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fdaaf`
- `api-ms-win-crt-utility-l1-1-0!bsearch` at `0x1800fd9e1`
- `api-ms-win-crt-utility-l1-1-0!bsearch` at `0x1800fdc6b`
- `api-ms-win-crt-utility-l1-1-0!bsearch` at `0x1800fd9e1`
- `api-ms-win-crt-utility-l1-1-0!bsearch` at `0x1800fdc6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetModuleBaseRoutine(HANDLE hProcess, DWORD64 Address)
{
  DWORD64 v2; // r13
  char IsCurrentHeapLocal; // di
  bool v5; // si
  _DWORD *v6; // rax
  __int64 v7; // rcx
  void *v8; // rax
  __int64 v9; // rax
  __int64 v10; // r8
  signed __int32 v11; // edx
  _DWORD *v12; // rax
  __int64 *v13; // rax
  __int64 v14; // r8
  signed __int32 v15; // edx
  signed __int32 v16; // edx
  char v17; // di
  bool v18; // si
  void *v19; // rax
  void *v20; // r14
  __int64 v21; // rdi
  signed __int32 v22; // edx
  DWORD v23; // eax
  void *v24; // rdi
  void *v25; // rcx
  __int64 v26; // r8
  int v27; // edx
  bool v28; // zf
  signed __int32 v29; // edx
  volatile signed __int32 *v30; // rcx
  signed __int32 v31; // r9d
  _DWORD *v32; // rax
  __int64 *v33; // rax
  __int64 v34; // r8
  signed __int32 v35; // edx
  signed __int32 v36; // edx
  DWORD TickCount; // eax
  __int64 v39; // r8
  signed __int32 v40; // edx
  signed __int32 v41; // edx
  __int64 v42; // r8
  signed __int32 v43; // edx
  signed __int32 v44; // edx
  char v45; // [rsp+30h] [rbp-D8h]
  bool v46; // [rsp+31h] [rbp-D7h]
  __int64 v47; // [rsp+38h] [rbp-D0h]
  int v48; // [rsp+40h] [rbp-C8h]
  int v49; // [rsp+44h] [rbp-C4h]
  DWORD64 Key[3]; // [rsp+A0h] [rbp-68h] BYREF
  DWORD64 v51[10]; // [rsp+B8h] [rbp-50h] BYREF
  char v53; // [rsp+120h] [rbp+18h]
  bool v54; // [rsp+121h] [rbp+19h]
  char v55; // [rsp+128h] [rbp+20h]
  bool v56; // [rsp+129h] [rbp+21h]

  v2 = Address;
  if ( !qword_1802B0480 )
  {
    VprocessGlobals::acquireFPGlobalCriticalSection();
    try
    {
      if ( !qword_1802B0480 )
      {
        if ( dword_1802B0018 )
        {
          IsCurrentHeapLocal = COWSAllocator::IsCurrentHeapLocal();
          v5 = IsCurrentHeapLocal == 1;
          if ( IsCurrentHeapLocal == 1 )
            COWSAllocator::UseGlobalHeap();
        }
        else
        {
          v5 = v54;
          IsCurrentHeapLocal = v53;
        }
        if ( dword_1802B0018 )
          v6 = COWSAllocator::AllocCurrentHeap(0x10u);
        else
          v6 = malloc(0x10u);
        v7 = (__int64)v6;
        if ( v6 )
        {
          *(_QWORD *)v6 = &Vlock::`vftable';
          v6[2] = 0;
          v6[3] = 0;
        }
        else
        {
          v7 = 0;
        }
        qword_1802B0480 = v7;
        if ( dword_1802B0018 && v5 )
        {
          if ( IsCurrentHeapLocal )
            COWSAllocator::UseLocalHeap();
          else
            COWSAllocator::UseGlobalHeap();
        }
      }
    }
    catch ( ... )
    {
      qword_1802B0480 = 0;
      if ( !--word_1802B00B8 )
        SetEvent(hEvent);
      return 0;
    }
    if ( !--word_1802B00B8 )
      SetEvent(hEvent);
  }
  if ( !qword_1802B0478 )
  {
    if ( dword_1802B0018 )
    {
      v55 = COWSAllocator::IsCurrentHeapLocal();
      v56 = v55 == 1;
      if ( v55 == 1 )
        COWSAllocator::UseGlobalHeap();
    }
    if ( dword_1802B0018 )
      v8 = COWSAllocator::AllocCurrentHeap(0x10u);
    else
      v8 = malloc(0x10u);
    if ( v8 )
      v9 = sub_1800FD484(v8, hProcess);
    else
      v9 = 0;
    _InterlockedExchange64((volatile __int64 *)&qword_1802B0478, v9);
    if ( dword_1802B0018 && v56 )
    {
      if ( v55 )
        COWSAllocator::UseLocalHeap();
      else
        COWSAllocator::UseGlobalHeap();
    }
  }
  v10 = qword_1802B0480;
  v11 = *(_DWORD *)(qword_1802B0480 + 8);
  if ( (v11 & 0xFFFF8000) != 0
    || v11 != _InterlockedCompareExchange((volatile signed __int32 *)(qword_1802B0480 + 8), v11 + 1, v11) )
  {
    VonetLocks::CReaderWriterLock3::_LockSpin((volatile signed __int32 *)(v10 + 8), 2);
  }
  try
  {
    v12 = qword_1802B0478;
    if ( *(_QWORD *)qword_1802B0478 )
    {
      Key[0] = v2;
      v13 = (__int64 *)bsearch(
                         Key,
                         *(const void **)qword_1802B0478,
                         *((int *)qword_1802B0478 + 2),
                         0x18u,
                         sub_1800FD460);
      if ( v13 )
        v47 = *v13;
      else
        v47 = 0;
      v12 = qword_1802B0478;
    }
    else
    {
      v47 = 0;
    }
    v48 = v12[2];
  }
  catch ( ... )
  {
    v39 = qword_1802B0480;
    v40 = *(_DWORD *)(qword_1802B0480 + 8);
    if ( v40 != _InterlockedCompareExchange((volatile signed __int32 *)(qword_1802B0480 + 8), v40 - 1, v40) )
    {
      _m_prefetchw((const void *)(v39 + 8));
      do
        v41 = *(_DWORD *)(v39 + 8);
      while ( v41 != _InterlockedCompareExchange((volatile signed __int32 *)(v39 + 8), v41 - 1, v41) );
    }
    return 0;
  }
  v14 = qword_1802B0480;
  v15 = *(_DWORD *)(qword_1802B0480 + 8);
  if ( v15 != _InterlockedCompareExchange((volatile signed __int32 *)(qword_1802B0480 + 8), v15 - 1, v15) )
  {
    _m_prefetchw((const void *)(v14 + 8));
    do
      v16 = *(_DWORD *)(v14 + 8);
    while ( v16 != _InterlockedCompareExchange((volatile signed __int32 *)(v14 + 8), v16 - 1, v16) );
  }
  if ( !v47 && GetTickCount() > dword_1802B0474 )
  {
    if ( dword_1802B0018 )
    {
      v17 = COWSAllocator::IsCurrentHeapLocal();
      v18 = v17 == 1;
      if ( v17 == 1 )
        COWSAllocator::UseGlobalHeap();
    }
    else
    {
      v18 = v46;
      v17 = v45;
    }
    if ( dword_1802B0018 )
      v19 = COWSAllocator::AllocCurrentHeap(0x10u);
    else
      v19 = malloc(0x10u);
    if ( v19 )
      v20 = (void *)sub_1800FD484(v19, hProcess);
    else
      v20 = 0;
    if ( dword_1802B0018 && v18 )
    {
      if ( v17 )
        COWSAllocator::UseLocalHeap();
      else
        COWSAllocator::UseGlobalHeap();
    }
    v21 = qword_1802B0480;
    if ( *(_DWORD *)(qword_1802B0480 + 12)
      || (v22 = *(_DWORD *)(qword_1802B0480 + 8), (_WORD)v22)
      || v22 != _InterlockedCompareExchange(
                  (volatile signed __int32 *)(qword_1802B0480 + 8),
                  (v22 + 0x10000) | 0xFFFF,
                  v22) )
    {
      if ( ((GetCurrentThreadId() ^ *(_DWORD *)(v21 + 12)) & 0xFFFFFFFC) != 0 )
      {
        VonetLocks::CReaderWriterLock3::_WriteLockSpin((VonetLocks::CReaderWriterLock3 *)(v21 + 8));
        goto LABEL_125;
      }
      v23 = *(_DWORD *)(v21 + 12) + 1;
    }
    else
    {
      v23 = GetCurrentThreadId() & 0xFFFFFFFC | 1;
    }
    _InterlockedExchange((volatile __int32 *)(v21 + 12), v23);
LABEL_125:
    try
    {
      v24 = qword_1802B0478;
      if ( qword_1802B0478 )
      {
        v25 = *(void **)qword_1802B0478;
        if ( *(_QWORD *)qword_1802B0478 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(v25);
          else
            free(v25);
        }
        if ( dword_1802B0018 )
          COWSAllocator::Free(v24);
        else
          free(v24);
      }
      qword_1802B0478 = v20;
    }
    catch ( ... )
    {
      qword_1802B0478 = v20;
      v2 = Address;
    }
    v26 = qword_1802B0480;
    v27 = *(_DWORD *)(qword_1802B0480 + 12) - 1;
    v28 = (((*(_BYTE *)(qword_1802B0480 + 12) - 1) & 3) != 0 ? v27 : 0) == 0;
    _InterlockedExchange(
      (volatile __int32 *)(qword_1802B0480 + 12),
      ((*(_BYTE *)(qword_1802B0480 + 12) - 1) & 3) != 0 ? v27 : 0);
    if ( v28 )
    {
      _m_prefetchw((const void *)(v26 + 8));
      do
        v29 = *(_DWORD *)(v26 + 8);
      while ( v29 != _InterlockedCompareExchange(
                       (volatile signed __int32 *)(v26 + 8),
                       (v29 - 0x10000) & 0xFFFF0000,
                       v29) );
    }
    v30 = (volatile signed __int32 *)(qword_1802B0480 + 8);
    v31 = *(_DWORD *)(qword_1802B0480 + 8);
    if ( (v31 & 0xFFFF8000) != 0 || v31 != _InterlockedCompareExchange(v30, v31 + 1, v31) )
      VonetLocks::CReaderWriterLock3::_LockSpin(v30, 2);
    try
    {
      v32 = qword_1802B0478;
      if ( *(_QWORD *)qword_1802B0478 )
      {
        v51[0] = v2;
        v33 = (__int64 *)bsearch(
                           v51,
                           *(const void **)qword_1802B0478,
                           *((int *)qword_1802B0478 + 2),
                           0x18u,
                           sub_1800FD460);
        if ( v33 )
          v47 = *v33;
        else
          v47 = 0;
        v32 = qword_1802B0478;
      }
      else
      {
        v47 = 0;
      }
      v49 = v32[2];
    }
    catch ( ... )
    {
      v42 = qword_1802B0480;
      v43 = *(_DWORD *)(qword_1802B0480 + 8);
      if ( v43 != _InterlockedCompareExchange((volatile signed __int32 *)(qword_1802B0480 + 8), v43 - 1, v43) )
      {
        _m_prefetchw((const void *)(v42 + 8));
        do
          v44 = *(_DWORD *)(v42 + 8);
        while ( v44 != _InterlockedCompareExchange((volatile signed __int32 *)(v42 + 8), v44 - 1, v44) );
      }
      return 0;
    }
    v34 = qword_1802B0480;
    v35 = *(_DWORD *)(qword_1802B0480 + 8);
    if ( v35 != _InterlockedCompareExchange((volatile signed __int32 *)(qword_1802B0480 + 8), v35 - 1, v35) )
    {
      _m_prefetchw((const void *)(v34 + 8));
      do
        v36 = *(_DWORD *)(v34 + 8);
      while ( v36 != _InterlockedCompareExchange((volatile signed __int32 *)(v34 + 8), v36 - 1, v36) );
    }
    if ( v49 == v48 )
      TickCount = GetTickCount() + 600000;
    else
      TickCount = GetTickCount();
    dword_1802B0474 = TickCount;
  }
  return v47;
}

```

## disassembly

```asm
0x1800fd780  mov     [rsp+arg_8], rdx
0x1800fd785  push    rbx
0x1800fd786  push    rsi
0x1800fd787  push    rdi
0x1800fd788  push    r12
0x1800fd78a  push    r13
0x1800fd78c  push    r14
0x1800fd78e  push    r15
0x1800fd790  sub     rsp, 0D0h
0x1800fd797  mov     [rsp+108h+var_A8], 0FFFFFFFFFFFFFFFEh
0x1800fd7a0  mov     r13, rdx
0x1800fd7a3  mov     r15, rcx
0x1800fd7a6  xor     ebx, ebx
0x1800fd7a8  cmp     cs:qword_1802B0480, rbx
0x1800fd7af  jnz     loc_1800FD8C6
0x1800fd7b5  call    ?acquireFPGlobalCriticalSection@VprocessGlobals@@SAXXZ; VprocessGlobals::acquireFPGlobalCriticalSection(void)
0x1800fd7ba  nop
0x1800fd7bb  cmp     cs:qword_1802B0480, rbx
0x1800fd7c2  jnz     loc_1800FD892
0x1800fd7c8  cmp     cs:dword_1802B0018, ebx
0x1800fd7ce  jz      short loc_1800FD804
0x1800fd7d0  call    ?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x1800fd7d5  mov     dil, al
0x1800fd7d8  mov     [rsp+108h+arg_10], al
0x1800fd7df  cmp     al, 1
0x1800fd7e1  setz    sil
0x1800fd7e5  mov     [rsp+108h+arg_11], sil
0x1800fd7ed  test    sil, sil
0x1800fd7f0  jz      short loc_1800FD814
0x1800fd7f2  test    al, al
0x1800fd7f4  jz      short loc_1800FD7FD
0x1800fd7f6  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800fd7fb  jmp     short loc_1800FD814
0x1800fd7fd  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800fd802  jmp     short loc_1800FD814
0x1800fd804  mov     sil, [rsp+108h+arg_11]
0x1800fd80c  mov     dil, [rsp+108h+arg_10]
0x1800fd814  mov     r14d, 10h
0x1800fd81a  mov     ecx, r14d; unsigned __int64
0x1800fd81d  cmp     cs:dword_1802B0018, ebx
0x1800fd823  jz      short loc_1800FD82C
0x1800fd825  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800fd82a  jmp     short loc_1800FD832
0x1800fd82c  call    cs:malloc
0x1800fd832  mov     [rsp+108h+var_B8], rax
0x1800fd837  mov     rcx, rax
0x1800fd83a  mov     [rsp+108h+var_A0], rax
0x1800fd83f  test    rax, rax
0x1800fd842  jz      short loc_1800FD863
0x1800fd844  lea     rax, ??_7Vlock@@6B@; const Vlock::`vftable'
0x1800fd84b  mov     [rcx], rax
0x1800fd84e  lea     rax, [rcx+8]
0x1800fd852  mov     [rsp+108h+var_98], rax
0x1800fd857  mov     [rax], ebx
0x1800fd859  mov     [rax+4], ebx
0x1800fd85c  mov     [rsp+108h+var_B0], rcx
0x1800fd861  jmp     short loc_1800FD86B
0x1800fd863  mov     rcx, rbx
0x1800fd866  mov     [rsp+108h+var_B0], rbx
0x1800fd86b  mov     cs:qword_1802B0480, rcx
0x1800fd872  cmp     cs:dword_1802B0018, ebx
0x1800fd878  jz      short loc_1800FD898
0x1800fd87a  test    sil, sil
0x1800fd87d  jz      short loc_1800FD898
0x1800fd87f  test    dil, dil
0x1800fd882  jz      short loc_1800FD88B
0x1800fd884  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800fd889  jmp     short loc_1800FD898
0x1800fd88b  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800fd890  jmp     short loc_1800FD898
0x1800fd892  mov     r14d, 10h
0x1800fd898  sub     cs:word_1802B00B8, 1
0x1800fd8a0  jnz     short loc_1800FD8CC
0x1800fd8a2  mov     rcx, cs:hEvent; hEvent
0x1800fd8a9  call    cs:SetEvent
0x1800fd8af  jmp     short loc_1800FD8CC
0x1800fd8b1  xor     eax, eax
0x1800fd8b3  add     rsp, 0D0h
0x1800fd8ba  pop     r15
0x1800fd8bc  pop     r14
0x1800fd8be  pop     r13
0x1800fd8c0  pop     r12
0x1800fd8c2  pop     rdi
0x1800fd8c3  pop     rsi
0x1800fd8c4  pop     rbx
0x1800fd8c5  retn
0x1800fd8c6  mov     r14d, 10h
0x1800fd8cc  cmp     cs:qword_1802B0478, rbx
0x1800fd8d3  jnz     loc_1800FD96D
0x1800fd8d9  cmp     cs:dword_1802B0018, ebx
0x1800fd8df  jz      short loc_1800FD90E
0x1800fd8e1  call    ?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x1800fd8e6  mov     [rsp+108h+arg_18], al
0x1800fd8ed  cmp     al, 1
0x1800fd8ef  setz    cl
0x1800fd8f2  mov     [rsp+108h+arg_19], cl
0x1800fd8f9  test    cl, cl
0x1800fd8fb  jz      short loc_1800FD90E
0x1800fd8fd  test    al, al
0x1800fd8ff  jz      short loc_1800FD908
0x1800fd901  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800fd906  jmp     short loc_1800FD90E
0x1800fd908  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800fd90d  nop
0x1800fd90e  mov     rcx, r14; unsigned __int64
0x1800fd911  cmp     cs:dword_1802B0018, ebx
0x1800fd917  jz      short loc_1800FD920
0x1800fd919  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800fd91e  jmp     short loc_1800FD926
0x1800fd920  call    cs:malloc
0x1800fd926  mov     [rsp+108h+var_C0], rax
0x1800fd92b  test    rax, rax
0x1800fd92e  jz      short loc_1800FD93D
0x1800fd930  mov     rdx, r15
0x1800fd933  mov     rcx, rax
0x1800fd936  call    sub_1800FD484
0x1800fd93b  jmp     short loc_1800FD940
0x1800fd93d  mov     rax, rbx
0x1800fd940  xchg    rax, cs:qword_1802B0478
0x1800fd947  cmp     cs:dword_1802B0018, ebx
0x1800fd94d  jz      short loc_1800FD96D
0x1800fd94f  cmp     [rsp+108h+arg_19], bl
0x1800fd956  jz      short loc_1800FD96D
0x1800fd958  cmp     [rsp+108h+arg_18], bl
0x1800fd95f  jz      short loc_1800FD968
0x1800fd961  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800fd966  jmp     short loc_1800FD96D
0x1800fd968  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800fd96d  mov     r8, cs:qword_1802B0480
0x1800fd974  mov     edx, [r8+8]
0x1800fd978  test    edx, 0FFFF8000h
0x1800fd97e  jnz     short loc_1800FD98F
0x1800fd980  lea     ecx, [rdx+1]
0x1800fd983  mov     eax, edx
0x1800fd985  lock cmpxchg [r8+8], ecx
0x1800fd98b  cmp     edx, eax
0x1800fd98d  jz      short loc_1800FD99E
0x1800fd98f  mov     edx, 2
0x1800fd994  lea     rcx, [r8+8]
0x1800fd998  call    ?_LockSpin@CReaderWriterLock3@VonetLocks@@AEAAXW4SPIN_TYPE@12@@Z; VonetLocks::CReaderWriterLock3::_LockSpin(VonetLocks::CReaderWriterLock3::SPIN_TYPE)
0x1800fd99d  nop
0x1800fd99e  mov     rax, cs:qword_1802B0478
0x1800fd9a5  cmp     [rax], rbx
0x1800fd9a8  jnz     short loc_1800FD9B8
0x1800fd9aa  mov     [rsp+108h+var_D0], rbx
0x1800fd9af  lea     r12, sub_1800FD460
0x1800fd9b6  jmp     short loc_1800FDA07
0x1800fd9b8  mov     [rsp+108h+Key], r13
0x1800fd9c0  movsxd  r8, dword ptr [rax+8]; NumOfElements
0x1800fd9c4  lea     r12, sub_1800FD460
0x1800fd9cb  mov     [rsp+108h+CompareFunction], r12; CompareFunction
0x1800fd9d0  mov     r9d, 18h; SizeOfElements
0x1800fd9d6  mov     rdx, [rax]; Base
0x1800fd9d9  lea     rcx, [rsp+108h+Key]; Key
0x1800fd9e1  call    cs:bsearch
0x1800fd9e7  mov     [rsp+108h+var_90], rax
0x1800fd9ec  test    rax, rax
0x1800fd9ef  jnz     short loc_1800FD9F8
0x1800fd9f1  mov     [rsp+108h+var_D0], rbx
0x1800fd9f6  jmp     short loc_1800FDA00
0x1800fd9f8  mov     rax, [rax]
0x1800fd9fb  mov     [rsp+108h+var_D0], rax
0x1800fda00  mov     rax, cs:qword_1802B0478
0x1800fda07  mov     eax, [rax+8]
0x1800fda0a  mov     [rsp+108h+var_C8], eax
0x1800fda0e  mov     r8, cs:qword_1802B0480
0x1800fda15  mov     edx, [r8+8]
0x1800fda19  lea     ecx, [rdx-1]
0x1800fda1c  mov     eax, edx
0x1800fda1e  lock cmpxchg [r8+8], ecx
0x1800fda24  cmp     edx, eax
0x1800fda26  jz      short loc_1800FDA40
0x1800fda28  prefetchw byte ptr [r8+8]
0x1800fda2d  mov     edx, [r8+8]
0x1800fda31  lea     ecx, [rdx-1]
0x1800fda34  mov     eax, edx
0x1800fda36  lock cmpxchg [r8+8], ecx
0x1800fda3c  cmp     edx, eax
0x1800fda3e  jnz     short loc_1800FDA2D
0x1800fda40  cmp     [rsp+108h+var_D0], rbx
0x1800fda45  jnz     loc_1800FDCE3
0x1800fda4b  call    cs:GetTickCount
0x1800fda51  cmp     eax, cs:dword_1802B0474
0x1800fda57  jbe     loc_1800FDCE3
0x1800fda5d  cmp     cs:dword_1802B0018, ebx
0x1800fda63  jz      short loc_1800FDA93
0x1800fda65  call    ?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x1800fda6a  mov     dil, al
0x1800fda6d  mov     [rsp+108h+var_D8], al
0x1800fda71  cmp     al, 1
0x1800fda73  setz    sil
0x1800fda77  mov     [rsp+108h+var_D7], sil
0x1800fda7c  test    sil, sil
0x1800fda7f  jz      short loc_1800FDA9D
0x1800fda81  test    al, al
0x1800fda83  jz      short loc_1800FDA8C
0x1800fda85  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800fda8a  jmp     short loc_1800FDA9D
0x1800fda8c  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800fda91  jmp     short loc_1800FDA9D
0x1800fda93  mov     sil, [rsp+108h+var_D7]
0x1800fda98  mov     dil, [rsp+108h+var_D8]
0x1800fda9d  mov     rcx, r14; unsigned __int64
0x1800fdaa0  cmp     cs:dword_1802B0018, ebx
0x1800fdaa6  jz      short loc_1800FDAAF
0x1800fdaa8  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800fdaad  jmp     short loc_1800FDAB5
0x1800fdaaf  call    cs:malloc
0x1800fdab5  mov     [rsp+108h+var_88], rax
0x1800fdabd  test    rax, rax
0x1800fdac0  jz      short loc_1800FDAD2
0x1800fdac2  mov     rdx, r15
0x1800fdac5  mov     rcx, rax
0x1800fdac8  call    sub_1800FD484
0x1800fdacd  mov     r14, rax
0x1800fdad0  jmp     short loc_1800FDAD5
0x1800fdad2  mov     r14, rbx
0x1800fdad5  mov     [rsp+108h+var_C0], r14
0x1800fdada  cmp     cs:dword_1802B0018, ebx
0x1800fdae0  jz      short loc_1800FDAF8
0x1800fdae2  test    sil, sil
0x1800fdae5  jz      short loc_1800FDAF8
0x1800fdae7  test    dil, dil
0x1800fdaea  jz      short loc_1800FDAF3
0x1800fdaec  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800fdaf1  jmp     short loc_1800FDAF8
0x1800fdaf3  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800fdaf8  mov     rdi, cs:qword_1802B0480
0x1800fdaff  mov     eax, [rdi+0Ch]
0x1800fdb02  test    eax, eax
0x1800fdb04  jnz     short loc_1800FDB36
0x1800fdb06  mov     edx, [rdi+8]
0x1800fdb09  test    dx, dx
0x1800fdb0c  jnz     short loc_1800FDB36
0x1800fdb0e  lea     ecx, [rdx+10000h]
0x1800fdb14  or      ecx, 0FFFFh
0x1800fdb1a  mov     eax, edx
0x1800fdb1c  lock cmpxchg [rdi+8], ecx
0x1800fdb21  cmp     edx, eax
0x1800fdb23  jnz     short loc_1800FDB36
0x1800fdb25  call    cs:GetCurrentThreadId
0x1800fdb2b  and     eax, 0FFFFFFFDh
0x1800fdb2e  or      eax, 1
0x1800fdb31  xchg    eax, [rdi+0Ch]
0x1800fdb34  jmp     short loc_1800FDB5A
0x1800fdb36  call    cs:GetCurrentThreadId
0x1800fdb3c  mov     ecx, [rdi+0Ch]
0x1800fdb3f  xor     ecx, eax
0x1800fdb41  test    ecx, 0FFFFFFFCh
0x1800fdb47  jnz     short loc_1800FDB50
0x1800fdb49  mov     eax, [rdi+0Ch]
0x1800fdb4c  inc     eax
0x1800fdb4e  jmp     short loc_1800FDB31
0x1800fdb50  lea     rcx, [rdi+8]; this
0x1800fdb54  call    ?_WriteLockSpin@CReaderWriterLock3@VonetLocks@@AEAAXXZ; VonetLocks::CReaderWriterLock3::_WriteLockSpin(void)
0x1800fdb59  nop
0x1800fdb5a  mov     rdi, cs:qword_1802B0478
0x1800fdb61  mov     [rsp+108h+var_80], rdi
0x1800fdb69  test    rdi, rdi
0x1800fdb6c  jz      short loc_1800FDBAB
0x1800fdb6e  mov     rcx, [rdi]; void *
0x1800fdb71  test    rcx, rcx
0x1800fdb74  jz      short loc_1800FDB93
0x1800fdb76  mov     [rsp+108h+var_78], rcx
0x1800fdb7e  cmp     cs:dword_1802B0018, ebx
0x1800fdb84  jz      short loc_1800FDB8D
0x1800fdb86  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800fdb8b  jmp     short loc_1800FDB93
0x1800fdb8d  call    cs:free
0x1800fdb93  mov     rcx, rdi; void *
0x1800fdb96  cmp     cs:dword_1802B0018, ebx
0x1800fdb9c  jz      short loc_1800FDBA5
0x1800fdb9e  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800fdba3  jmp     short loc_1800FDBAB
0x1800fdba5  call    cs:free
0x1800fdbab  mov     cs:qword_1802B0478, r14
0x1800fdbb2  jmp     short loc_1800FDBC5
0x1800fdbb4  xor     ebx, ebx
0x1800fdbb6  lea     r12, sub_1800FD460
0x1800fdbbd  mov     r13, [rsp+108h+arg_8]
0x1800fdbc5  mov     r8, cs:qword_1802B0480
0x1800fdbcc  mov     edx, [r8+0Ch]
0x1800fdbd0  dec     edx
0x1800fdbd2  mov     al, dl
0x1800fdbd4  and     al, 3
0x1800fdbd6  neg     al
0x1800fdbd8  sbb     ecx, ecx
0x1800fdbda  and     ecx, edx
0x1800fdbdc  xchg    ecx, [r8+0Ch]
0x1800fdbe0  jnz     short loc_1800FDC03
0x1800fdbe2  prefetchw byte ptr [r8+8]
0x1800fdbe7  mov     edx, [r8+8]
0x1800fdbeb  lea     ecx, [rdx-10000h]
0x1800fdbf1  and     ecx, 0FFFF0000h
0x1800fdbf7  mov     eax, edx
0x1800fdbf9  lock cmpxchg [r8+8], ecx
0x1800fdbff  cmp     edx, eax
0x1800fdc01  jnz     short loc_1800FDBE7
0x1800fdc03  mov     rcx, cs:qword_1802B0480
0x1800fdc0a  add     rcx, 8
  ... truncated ...
```
