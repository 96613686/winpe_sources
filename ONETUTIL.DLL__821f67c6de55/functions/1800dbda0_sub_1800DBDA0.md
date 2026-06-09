# sub_1800DBDA0

- ea: `0x1800dbda0`
- end: `0x1800dc065`
- name: `sub_1800DBDA0`
- size: `709`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180006270`
- `0x180073710`
- `0x1800838f0`
- `0x180086284`
- `0x1800db0d0`
- `0x1800dbcf8`
- `0x1800dbda0`
- `0x1800dc068`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x1800dbf77`
- `KERNEL32!ReleaseSemaphore` at `0x1800dbf77`
- `KERNEL32!TlsSetValue` at `0x1800dc01f`
- `KERNEL32!TlsSetValue` at `0x1800dc01f`
- `KERNEL32!TlsGetValue` at `0x1800dbfef`
- `KERNEL32!TlsGetValue` at `0x1800dbfef`
- `KERNEL32!GetCurrentThreadId` at `0x1800dbdfd`
- `KERNEL32!GetCurrentThreadId` at `0x1800dbdfd`
- `KERNEL32!LeaveCriticalSection` at `0x1800dbeff`
- `KERNEL32!LeaveCriticalSection` at `0x1800dbfce`
- `KERNEL32!LeaveCriticalSection` at `0x1800dbeff`
- `KERNEL32!LeaveCriticalSection` at `0x1800dbfce`
- `KERNEL32!EnterCriticalSection` at `0x1800dbe9e`
- `KERNEL32!EnterCriticalSection` at `0x1800dbf9a`
- `KERNEL32!EnterCriticalSection` at `0x1800dbfb4`
- `KERNEL32!EnterCriticalSection` at `0x1800dbe9e`
- `KERNEL32!EnterCriticalSection` at `0x1800dbf9a`
- `KERNEL32!EnterCriticalSection` at `0x1800dbfb4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800dc011`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800dc011`
- `ole32!CoUninitialize` at `0x1800dc025`
- `ole32!CoUninitialize` at `0x1800dc025`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sub_1800DBDA0(__int64 a1)
{
  int v2; // r14d
  int v3; // r15d
  DWORD CurrentThreadId; // eax
  COWSThreadWithHeap *v5; // rsi
  DWORD v6; // ecx
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  volatile __int32 *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rdx
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  _QWORD *Value; // rax
  COWSThreadWithHeap *v16[3]; // [rsp+28h] [rbp-E0h] BYREF
  HANDLE Handles[64]; // [rsp+40h] [rbp-C8h] BYREF
  DWORD v18; // [rsp+240h] [rbp+138h]
  _OWORD v19[3]; // [rsp+248h] [rbp+140h] BYREF
  __int64 v20; // [rsp+278h] [rbp+170h]

  v16[1] = (COWSThreadWithHeap *)-2LL;
  v16[2] = (COWSThreadWithHeap *)&COWSWaitableCollection::`vftable';
  v18 = 0;
  v2 = 1;
  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v16[0] = 0;
  CLKRHashTable::FindKey(a1 + 24, CurrentThreadId, v16);
  v5 = v16[0];
  COWSThreadWithHeap::Initialize(v16[0]);
  v6 = v18;
  if ( v18 != 64 )
  {
    Handles[v18] = *(HANDLE *)(a1 + 232);
    v6 = ++v18;
  }
  if ( v6 != 64 )
  {
    Handles[v6] = *(HANDLE *)(a1 + 184);
    v6 = ++v18;
  }
  while ( 1 )
  {
    if ( !v6 )
      goto LABEL_20;
    v7 = VwaitForMultipleObjects(v6, Handles, 0, *(_DWORD *)(a1 + 20));
    if ( v7 >= 2 )
    {
      if ( v7 == 258 )
      {
        v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 136);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 136));
        if ( *(_DWORD *)(a1 + 16) <= *(_DWORD *)(a1 + 8) )
        {
LABEL_22:
          LeaveCriticalSection(v13);
          goto LABEL_23;
        }
      }
      else
      {
LABEL_20:
        v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 136);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 136));
      }
      sub_1800DBCF8(a1, v5);
      v2 = 0;
      v3 = 1;
      goto LABEL_22;
    }
    if ( v7 == 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
      v8 = *(int *)(a1 + 76);
      v9 = *(_QWORD *)(a1 + 64);
      v19[0] = *(_OWORD *)(56 * v8 + v9);
      v19[1] = *(_OWORD *)(56 * v8 + v9 + 16);
      v19[2] = *(_OWORD *)(56 * v8 + v9 + 32);
      v20 = *(_QWORD *)(56 * v8 + v9 + 48);
      if ( (_DWORD)v8 == *(_DWORD *)(a1 + 80) )
      {
        *(_DWORD *)(a1 + 76) = -1;
        *(_DWORD *)(a1 + 80) = -1;
      }
      else
      {
        *(_DWORD *)(a1 + 76) = ((int)v8 + 1) % *(_DWORD *)(a1 + 72);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
      _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v5 + 4) + 8LL), 0);
      sub_1800DC068(v19);
      v10 = (volatile __int32 *)*((_QWORD *)v5 + 4);
      _InterlockedExchange(v10 + 2, 0);
      LOBYTE(v11) = 1;
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v10 + 64LL))(*(_QWORD *)v10, v11);
      v12 = *((_QWORD *)v10 + 3);
      if ( v12 )
      {
        sub_180086284(v10, -v12);
        *((_QWORD *)v10 + 3) = 0;
      }
      if ( (v10[4] & 0x1000) != 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v10 + 80LL))(*(_QWORD *)v10, 0);
      ReleaseSemaphore(*(HANDLE *)(a1 + 208), 1, 0);
      v5 = v16[0];
    }
    else
    {
      v2 = 0;
    }
LABEL_23:
    if ( !v2 )
      break;
    v6 = v18;
  }
  if ( !v3 )
  {
    Value = TlsGetValue(dword_1802AF500);
    if ( Value )
    {
      *Value = 0;
      if ( dword_1802B0018 )
        COWSAllocator::Free(Value);
      else
        free(Value);
    }
    TlsSetValue(dword_1802AF500, 0);
    CoUninitialize();
  }
  return 0;
}

```

## disassembly

```asm
0x1800dbda0  mov     rax, rsp
0x1800dbda3  push    rbp
0x1800dbda4  push    rdi
0x1800dbda5  push    r13
0x1800dbda7  push    r14
0x1800dbda9  push    r15
0x1800dbdab  lea     rbp, [rax-1A8h]
0x1800dbdb2  sub     rsp, 280h
0x1800dbdb9  mov     [rsp+2A0h+var_278], 0FFFFFFFFFFFFFFFEh
0x1800dbdc2  mov     [rax+10h], rbx
0x1800dbdc6  mov     [rax+18h], rsi
0x1800dbdca  mov     rax, cs:__security_cookie
0x1800dbdd1  xor     rax, rsp
0x1800dbdd4  mov     [rbp+1A0h+var_28], rax
0x1800dbddb  mov     rdi, rcx
0x1800dbdde  lea     rax, ??_7COWSWaitableCollection@@6B@; const COWSWaitableCollection::`vftable'
0x1800dbde5  mov     [rsp+2A0h+var_270], rax
0x1800dbdea  and     [rbp+1A0h+var_68], 0
0x1800dbdf1  mov     r13d, 1
0x1800dbdf7  mov     r14d, r13d
0x1800dbdfa  xor     r15d, r15d
0x1800dbdfd  call    cs:GetCurrentThreadId
0x1800dbe03  and     [rsp+2A0h+var_280], r15
0x1800dbe08  mov     edx, eax
0x1800dbe0a  lea     rcx, [rdi+18h]
0x1800dbe0e  lea     r8, [rsp+2A0h+var_280]
0x1800dbe13  call    ?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800dbe18  mov     rsi, [rsp+2A0h+var_280]
0x1800dbe1d  mov     rcx, rsi; this
0x1800dbe20  call    ?Initialize@COWSThreadWithHeap@@QEAAHXZ; COWSThreadWithHeap::Initialize(void)
0x1800dbe25  mov     rdx, [rdi+0E8h]
0x1800dbe2c  movsxd  rcx, [rbp+1A0h+var_68]
0x1800dbe33  cmp     ecx, 40h ; '@'
0x1800dbe36  jz      short loc_1800DBE4C
0x1800dbe38  mov     [rsp+rcx*8+2A0h+Handles], rdx
0x1800dbe3d  mov     ecx, [rbp+1A0h+var_68]
0x1800dbe43  add     ecx, r13d
0x1800dbe46  mov     [rbp+1A0h+var_68], ecx
0x1800dbe4c  mov     rdx, [rdi+0B8h]
0x1800dbe53  cmp     ecx, 40h ; '@'
0x1800dbe56  jz      short loc_1800DBE6F
0x1800dbe58  movsxd  rax, ecx
0x1800dbe5b  mov     [rsp+rax*8+2A0h+Handles], rdx
0x1800dbe60  mov     ecx, [rbp+1A0h+var_68]
0x1800dbe66  add     ecx, r13d; nCount
0x1800dbe69  mov     [rbp+1A0h+var_68], ecx
0x1800dbe6f  test    ecx, ecx
0x1800dbe71  jz      loc_1800DBFAA
0x1800dbe77  mov     r9d, [rdi+14h]; dwMilliseconds
0x1800dbe7b  xor     r8d, r8d; bWaitAll
0x1800dbe7e  lea     rdx, [rsp+2A0h+Handles]; lpHandles
0x1800dbe83  call    ?VwaitForMultipleObjects@@YAKKPEBQEAXHK@Z; VwaitForMultipleObjects(ulong,void * const *,int,ulong)
0x1800dbe88  cmp     eax, 2
0x1800dbe8b  jnb     loc_1800DBF89
0x1800dbe91  cmp     eax, r13d
0x1800dbe94  jnz     loc_1800DBF84
0x1800dbe9a  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800dbe9e  call    cs:EnterCriticalSection
0x1800dbea4  movsxd  rdx, dword ptr [rdi+4Ch]
0x1800dbea8  imul    rcx, rdx, 38h ; '8'
0x1800dbeac  mov     rax, [rdi+40h]
0x1800dbeb0  movups  xmm0, xmmword ptr [rcx+rax]
0x1800dbeb4  movups  [rbp+1A0h+var_60], xmm0
0x1800dbebb  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x1800dbec0  movups  [rbp+1A0h+var_50], xmm1
0x1800dbec7  movups  xmm0, xmmword ptr [rcx+rax+20h]
0x1800dbecc  movups  [rbp+1A0h+var_40], xmm0
0x1800dbed3  movsd   xmm1, qword ptr [rcx+rax+30h]
0x1800dbed9  movsd   [rbp+1A0h+var_30], xmm1
0x1800dbee1  cmp     edx, [rdi+50h]
0x1800dbee4  jnz     short loc_1800DBEF1
0x1800dbee6  or      eax, 0FFFFFFFFh
0x1800dbee9  mov     [rdi+4Ch], eax
0x1800dbeec  mov     [rdi+50h], eax
0x1800dbeef  jmp     short loc_1800DBEFB
0x1800dbef1  lea     eax, [rdx+1]
0x1800dbef4  cdq
0x1800dbef5  idiv    dword ptr [rdi+48h]
0x1800dbef8  mov     [rdi+4Ch], edx
0x1800dbefb  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800dbeff  call    cs:LeaveCriticalSection
0x1800dbf05  mov     rcx, [rsi+20h]
0x1800dbf09  xor     eax, eax
0x1800dbf0b  xchg    eax, [rcx+8]
0x1800dbf0e  lea     rcx, [rbp+1A0h+var_60]
0x1800dbf15  call    sub_1800DC068
0x1800dbf1a  mov     rbx, [rsi+20h]
0x1800dbf1e  xor     eax, eax
0x1800dbf20  xchg    eax, [rbx+8]
0x1800dbf23  mov     rcx, [rbx]
0x1800dbf26  mov     rax, [rcx]
0x1800dbf29  mov     dl, r13b
0x1800dbf2c  mov     rax, [rax+40h]
0x1800dbf30  call    cs:__guard_dispatch_icall_fptr
0x1800dbf36  mov     rdx, [rbx+18h]
0x1800dbf3a  test    rdx, rdx
0x1800dbf3d  jz      short loc_1800DBF4F
0x1800dbf3f  neg     rdx
0x1800dbf42  mov     rcx, rbx
0x1800dbf45  call    sub_180086284
0x1800dbf4a  and     qword ptr [rbx+18h], 0
0x1800dbf4f  test    dword ptr [rbx+10h], 1000h
0x1800dbf56  jz      short loc_1800DBF6A
0x1800dbf58  mov     rcx, [rbx]
0x1800dbf5b  mov     rax, [rcx]
0x1800dbf5e  xor     edx, edx
0x1800dbf60  mov     rax, [rax+50h]
0x1800dbf64  call    cs:__guard_dispatch_icall_fptr
0x1800dbf6a  xor     r8d, r8d; lpPreviousCount
0x1800dbf6d  mov     edx, r13d; lReleaseCount
0x1800dbf70  mov     rcx, [rdi+0D0h]; hSemaphore
0x1800dbf77  call    cs:ReleaseSemaphore
0x1800dbf7d  mov     rsi, [rsp+2A0h+var_280]
0x1800dbf82  jmp     short loc_1800DBFD4
0x1800dbf84  xor     r14d, r14d
0x1800dbf87  jmp     short loc_1800DBFD4
0x1800dbf89  cmp     eax, 102h
0x1800dbf8e  jnz     short loc_1800DBFAA
0x1800dbf90  lea     rbx, [rdi+88h]
0x1800dbf97  mov     rcx, rbx; lpCriticalSection
0x1800dbf9a  call    cs:EnterCriticalSection
0x1800dbfa0  mov     eax, [rdi+8]
0x1800dbfa3  cmp     [rdi+10h], eax
0x1800dbfa6  jle     short loc_1800DBFCB
0x1800dbfa8  jmp     short loc_1800DBFBA
0x1800dbfaa  lea     rbx, [rdi+88h]
0x1800dbfb1  mov     rcx, rbx; lpCriticalSection
0x1800dbfb4  call    cs:EnterCriticalSection
0x1800dbfba  mov     rdx, rsi
0x1800dbfbd  mov     rcx, rdi
0x1800dbfc0  call    sub_1800DBCF8
0x1800dbfc5  xor     r14d, r14d
0x1800dbfc8  mov     r15d, r13d
0x1800dbfcb  mov     rcx, rbx; lpCriticalSection
0x1800dbfce  call    cs:LeaveCriticalSection
0x1800dbfd4  test    r14d, r14d
0x1800dbfd7  jz      short loc_1800DBFE4
0x1800dbfd9  mov     ecx, [rbp+1A0h+var_68]
0x1800dbfdf  jmp     loc_1800DBE6F
0x1800dbfe4  test    r15d, r15d
0x1800dbfe7  jnz     short loc_1800DC02C
0x1800dbfe9  mov     ecx, cs:dword_1802AF500; dwTlsIndex
0x1800dbfef  call    cs:TlsGetValue
0x1800dbff5  test    rax, rax
0x1800dbff8  jz      short loc_1800DC017
0x1800dbffa  and     qword ptr [rax], 0
0x1800dbffe  mov     rcx, rax; void *
0x1800dc001  cmp     cs:dword_1802B0018, r15d
0x1800dc008  jz      short loc_1800DC011
0x1800dc00a  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800dc00f  jmp     short loc_1800DC017
0x1800dc011  call    cs:free
0x1800dc017  xor     edx, edx; lpTlsValue
0x1800dc019  mov     ecx, cs:dword_1802AF500; dwTlsIndex
0x1800dc01f  call    cs:TlsSetValue
0x1800dc025  call    cs:CoUninitialize
0x1800dc02b  nop
0x1800dc02c  lea     rax, ??_7COWSWaitableCollection@@6B@; const COWSWaitableCollection::`vftable'
0x1800dc033  mov     [rsp+2A0h+var_270], rax
0x1800dc038  xor     eax, eax
0x1800dc03a  mov     rcx, [rbp+1A0h+var_28]
0x1800dc041  xor     rcx, rsp
0x1800dc044  call    sub_1801503E0
0x1800dc049  lea     r11, [rsp+2A0h+var_20]
0x1800dc051  mov     rbx, [r11+38h]
0x1800dc055  mov     rsi, [r11+40h]
0x1800dc059  mov     rsp, r11
0x1800dc05c  pop     r15
0x1800dc05e  pop     r14
0x1800dc060  pop     r13
0x1800dc062  pop     rdi
0x1800dc063  pop     rbp
0x1800dc064  retn
```
