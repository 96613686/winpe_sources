# BipAcquireGlobalLock

- ea: `0x18000d7c0`
- end: `0x18000da24`
- name: `BipAcquireGlobalLock`
- size: `612`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `107`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800044f8`
- `0x180005188`
- `0x180005280`
- `0x180005b90`
- `0x180006014`
- `0x180007014`
- `0x180007ebc`
- `0x1800080f0`
- `0x18000820c`
- `0x180008598`
- `0x180009728`
- `0x18000a560`
- `0x18000ac6c`
- `0x18000b0e0`
- `0x18000b7a8`
- `0x18000bb10`
- `0x18000cd10`
- `0x18000db40`
- `0x18000f334`
- `0x180010370`
- `0x180011d90`
- `0x180011e98`
- `0x180013214`
- `0x180016d24`
- `0x18002731c`
- `0x18002d0b0`
- `0x18002da30`
- `0x180037928`
- `0x180039d14`
- `0x18003ad50`
- `0x18003d104`
- `0x18003d5b4`
- `0x18003dc6c`
- `0x1800437fc`
- `0x180044b34`
- `0x18004e12c`
- `0x18004e7f0`
- `0x18004fc90`
- `0x180054c20`
- `0x180055490`
- `0x180055b80`
- `0x180055c70`
- `0x180055df0`
- `0x180055f80`
- `0x1800563a0`
- `0x1800568b8`
- `0x180056ff0`
- `0x180057614`
- `0x180057830`
- `0x180057dec`

## callees

- `0x18000d7c0`
- `0x1800170b0`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x18000d98f`
- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x18000d98f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d839`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d964`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d839`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d964`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d9d3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000da08`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d9d3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000da08`
- `ntdll!RtlWakeAddressAll` at `0x18000d9e4`
- `ntdll!RtlWakeAddressAll` at `0x18000d9e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d83f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d96a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d83f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d96a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d81c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d947`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d81c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d947`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000d867`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000d867`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d7e8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d85d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d7e8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d85d`

## pseudocode

```c
__int64 BipAcquireGlobalLock()
{
  int v0; // edi
  __int64 v1; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v3; // r8
  LARGE_INTEGER v4; // rax
  int v5; // edi
  DWORD v6; // eax
  __int64 v7; // rax
  unsigned __int64 v8; // rdx
  int v9; // ebx
  __int64 result; // rax
  int v11; // ebx
  LARGE_INTEGER v12; // [rsp+50h] [rbp-30h] BYREF
  LARGE_INTEGER v13; // [rsp+58h] [rbp-28h] BYREF
  LARGE_INTEGER v14; // [rsp+60h] [rbp-20h] BYREF
  _BOOL8 v15; // [rsp+68h] [rbp-18h] BYREF
  __int64 v16; // [rsp+70h] [rbp-10h] BYREF
  LARGE_INTEGER v17; // [rsp+C0h] [rbp+40h] BYREF
  LARGE_INTEGER Frequency; // [rsp+C8h] [rbp+48h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+D0h] [rbp+50h] BYREF
  unsigned __int64 v20; // [rsp+D8h] [rbp+58h] BYREF

  v17.QuadPart = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v0 = 1 << dword_1800C3CB0;
  v1 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_DWORD *)(v1 + 4) >= (unsigned int)(1 << dword_1800C3CB0) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)&BipGlobalLock);
  RtlAcquireSRWLockExclusive(&BipGlobalLock);
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(v1 + 4) |= v0;
  dword_1800C3CB4 = CurrentThreadId;
  *(_DWORD *)(v1 + 8) |= v0;
  QueryPerformanceCounter(&v17);
  QueryPerformanceFrequency(&Frequency);
  v4.QuadPart = 1000000000 * (v17.QuadPart - PerformanceCount.QuadPart);
  v17.QuadPart -= PerformanceCount.QuadPart;
  if ( v4.QuadPart > v17.QuadPart )
  {
    v17.QuadPart = v4.QuadPart / Frequency.QuadPart;
    if ( (unsigned int)dword_1800C3098 > 4
      && (qword_1800C30A8 & 0x400000000003LL) != 0
      && (qword_1800C30B0 & 0x400000000003LL) == qword_1800C30B0 )
    {
      v12 = Frequency;
      v13 = v17;
      v14 = v17;
      v20 = 0x1000000;
      v15 = v17.QuadPart > 500000000;
      v16 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v15,
        (unsigned __int64)byte_1800B3603,
        v3,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v20);
    }
  }
  v5 = 1 << dword_1800C3CF8;
  if ( *(_DWORD *)(v1 + 4) >= (unsigned int)(1 << dword_1800C3CF8) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipGlobals);
  RtlAcquireSRWLockExclusive(BipGlobals);
  v6 = GetCurrentThreadId();
  *(_DWORD *)(v1 + 8) |= v5;
  *(_DWORD *)(v1 + 4) |= v5;
  dword_1800C3CFC = v6;
  if ( *((_QWORD *)&xmmword_1800C3D00 + 1) )
  {
    v20 = 0;
    RtlQueryUnbiasedInterruptTime(&v20);
    v7 = (unsigned int)qword_1800C3D10;
    v8 = v20 / 0x2710;
    v9 = ~(1 << dword_1800C3CF8);
    *(_DWORD *)(v1 + 8) &= v9;
    *(_QWORD *)&xmmword_1800C3D00 = v7 + v8;
    dword_1800C3CFC = 0;
    RtlReleaseSRWLockExclusive(BipGlobals);
    *(_DWORD *)(v1 + 4) &= v9;
    return RtlWakeAddressAll(&xmmword_1800C3D00);
  }
  else
  {
    v11 = ~(1 << dword_1800C3CF8);
    dword_1800C3CFC = 0;
    *(_DWORD *)(v1 + 8) &= v11;
    result = RtlReleaseSRWLockExclusive(BipGlobals);
    *(_DWORD *)(v1 + 4) &= v11;
  }
  return result;
}

```

## disassembly

```asm
0x18000d7c0  push    rbp
0x18000d7c2  push    rbx
0x18000d7c3  push    rsi
0x18000d7c4  push    rdi
0x18000d7c5  push    r12
0x18000d7c7  push    r14
0x18000d7c9  push    r15
0x18000d7cb  mov     rbp, rsp
0x18000d7ce  sub     rsp, 80h
0x18000d7d5  xor     r12d, r12d
0x18000d7d8  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000d7dc  mov     qword ptr [rbp+arg_0], r12
0x18000d7e0  mov     qword ptr [rbp+Frequency], r12
0x18000d7e4  mov     qword ptr [rbp+PerformanceCount], r12
0x18000d7e8  call    cs:__imp_QueryPerformanceCounter
0x18000d7ee  mov     ecx, cs:dword_1800C3CB0
0x18000d7f4  mov     ebx, 1
0x18000d7f9  mov     rax, gs:58h
0x18000d802  mov     edi, ebx
0x18000d804  shl     edi, cl
0x18000d806  mov     ecx, cs:_tls_index
0x18000d80c  mov     r14d, 4
0x18000d812  mov     rsi, [rax+rcx*8]
0x18000d816  cmp     [r14+rsi], edi
0x18000d81a  jb      short loc_18000D832
0x18000d81c  call    cs:__imp_IsDebuggerPresent
0x18000d822  test    eax, eax
0x18000d824  jz      short loc_18000D832
0x18000d826  lea     rcx, BipGlobalLock; struct _BI_LOCK *
0x18000d82d  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18000d832  lea     rcx, BipGlobalLock
0x18000d839  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000d83f  call    cs:__imp_GetCurrentThreadId
0x18000d845  or      [r14+rsi], edi
0x18000d849  lea     rcx, [rbp+arg_0]; lpPerformanceCount
0x18000d84d  mov     r15d, 8
0x18000d853  mov     cs:dword_1800C3CB4, eax
0x18000d859  or      [r15+rsi], edi
0x18000d85d  call    cs:__imp_QueryPerformanceCounter
0x18000d863  lea     rcx, [rbp+Frequency]; lpFrequency
0x18000d867  call    cs:__imp_QueryPerformanceFrequency
0x18000d86d  mov     rcx, qword ptr [rbp+arg_0]
0x18000d871  sub     rcx, qword ptr [rbp+PerformanceCount]
0x18000d875  imul    rax, rcx, 3B9ACA00h
0x18000d87c  mov     qword ptr [rbp+arg_0], rcx
0x18000d880  cmp     rax, rcx
0x18000d883  jle     loc_18000D937
0x18000d889  cqo
0x18000d88b  idiv    qword ptr [rbp+Frequency]
0x18000d88f  mov     qword ptr [rbp+arg_0], rax
0x18000d893  mov     eax, cs:dword_1800C3098
0x18000d899  cmp     eax, 4
0x18000d89c  jbe     loc_18000D937
0x18000d8a2  mov     rcx, cs:qword_1800C30B0
0x18000d8a9  mov     rdx, 400000000003h
0x18000d8b3  mov     rax, cs:qword_1800C30A8
0x18000d8ba  test    rdx, rax
0x18000d8bd  jz      short loc_18000D937
0x18000d8bf  mov     rax, rcx
0x18000d8c2  and     rax, rdx
0x18000d8c5  cmp     rax, rcx
0x18000d8c8  jnz     short loc_18000D937
0x18000d8ca  mov     rax, qword ptr [rbp+Frequency]
0x18000d8ce  lea     r9, [rbp+var_10]
0x18000d8d2  mov     [rbp+var_30], rax
0x18000d8d6  lea     rdx, byte_1800B3603
0x18000d8dd  mov     rax, qword ptr [rbp+arg_0]
0x18000d8e1  mov     rcx, r12
0x18000d8e4  cmp     rax, 1DCD6500h
0x18000d8ea  mov     [rbp+var_28], rax
0x18000d8ee  mov     [rbp+var_20], rax
0x18000d8f2  lea     rax, [rbp+arg_18]
0x18000d8f6  mov     [rsp+80h+var_40], rax
0x18000d8fb  setnle  cl
0x18000d8fe  lea     rax, [rbp+var_30]
0x18000d902  mov     [rbp+arg_18], 1000000h
0x18000d90a  mov     [rsp+80h+var_48], rax
0x18000d90f  lea     rax, [rbp+var_28]
0x18000d913  mov     [rsp+80h+var_50], rax
0x18000d918  lea     rax, [rbp+var_20]
0x18000d91c  mov     [rsp+80h+var_58], rax
0x18000d921  lea     rax, [rbp+var_18]
0x18000d925  mov     [rsp+80h+var_60], rax
0x18000d92a  mov     [rbp+var_18], rcx
0x18000d92e  mov     [rbp+var_10], rbx
0x18000d932  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@22222@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000d937  mov     ecx, cs:dword_1800C3CF8
0x18000d93d  mov     edi, ebx
0x18000d93f  shl     edi, cl
0x18000d941  cmp     [r14+rsi], edi
0x18000d945  jb      short loc_18000D95D
0x18000d947  call    cs:__imp_IsDebuggerPresent
0x18000d94d  test    eax, eax
0x18000d94f  jz      short loc_18000D95D
0x18000d951  lea     rcx, BipGlobals; struct _BI_LOCK *
0x18000d958  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18000d95d  lea     rcx, BipGlobals
0x18000d964  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000d96a  call    cs:__imp_GetCurrentThreadId
0x18000d970  or      [r15+rsi], edi
0x18000d974  or      [r14+rsi], edi
0x18000d978  cmp     qword ptr cs:xmmword_1800C3D00+8, r12
0x18000d97f  mov     cs:dword_1800C3CFC, eax
0x18000d985  jz      short loc_18000D9EC
0x18000d987  lea     rcx, [rbp+arg_18]
0x18000d98b  mov     [rbp+arg_18], r12
0x18000d98f  call    cs:__imp_RtlQueryUnbiasedInterruptTime
0x18000d995  mov     ecx, cs:dword_1800C3CF8
0x18000d99b  mov     rax, 346DC5D63886594Bh
0x18000d9a5  mul     [rbp+arg_18]
0x18000d9a9  mov     eax, dword ptr cs:qword_1800C3D10
0x18000d9af  shl     ebx, cl
0x18000d9b1  lea     rcx, BipGlobals
0x18000d9b8  shr     rdx, 0Bh
0x18000d9bc  not     ebx
0x18000d9be  and     [r15+rsi], ebx
0x18000d9c2  add     rdx, rax
0x18000d9c5  mov     qword ptr cs:xmmword_1800C3D00, rdx
0x18000d9cc  mov     cs:dword_1800C3CFC, r12d
0x18000d9d3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000d9d9  and     [r14+rsi], ebx
0x18000d9dd  lea     rcx, xmmword_1800C3D00
0x18000d9e4  call    cs:__imp_RtlWakeAddressAll
0x18000d9ea  jmp     short loc_18000DA12
0x18000d9ec  mov     ecx, cs:dword_1800C3CF8
0x18000d9f2  shl     ebx, cl
0x18000d9f4  lea     rcx, BipGlobals
0x18000d9fb  not     ebx
0x18000d9fd  mov     cs:dword_1800C3CFC, r12d
0x18000da04  and     [r15+rsi], ebx
0x18000da08  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000da0e  and     [r14+rsi], ebx
0x18000da12  add     rsp, 80h
0x18000da19  pop     r15
0x18000da1b  pop     r14
0x18000da1d  pop     r12
0x18000da1f  pop     rdi
0x18000da20  pop     rsi
0x18000da21  pop     rbx
0x18000da22  pop     rbp
0x18000da23  retn
```
