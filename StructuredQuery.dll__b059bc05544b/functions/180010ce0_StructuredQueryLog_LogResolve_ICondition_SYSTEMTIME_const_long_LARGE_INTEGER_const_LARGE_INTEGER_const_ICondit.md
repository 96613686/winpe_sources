# StructuredQueryLog::LogResolve(ICondition *,_SYSTEMTIME const *,long,_LARGE_INTEGER const &,_LARGE_INTEGER const &,ICondition *)

- ea: `0x180010ce0`
- end: `0x180010f6d`
- name: `?LogResolve@StructuredQueryLog@@QEAAJPEAUICondition@@PEBU_SYSTEMTIME@@JAEBT_LARGE_INTEGER@@20@Z`
- size: `653`
- prototype: `__int64 __usercall@<rax>(FILETIME *lpFileTime2@<rcx>, struct ICondition *@<rdx>, const struct _SYSTEMTIME *@<r8>, int@<r9d>, const union _LARGE_INTEGER *, const union _LARGE_INTEGER *, struct ICondition *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010a10`
- `0x1800117c0`
- `0x180011b48`

## callees

- `0x180010ce0`
- `0x180049c30`
- `0x180059708`
- `0x180059848`
- `0x180059c0c`
- `0x18005db64`
- `0x1800710bc`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010d69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010dcf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010d69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010dcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010dac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010e54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010dac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010e54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e4b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010d30`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010d80`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010d30`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010d80`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010d1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010d73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010d1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010d73`

## pseudocode

```c
__int64 __fastcall StructuredQueryLog::LogResolve(
        FILETIME *lpFileTime2,
        struct ICondition *a2,
        const struct _SYSTEMTIME *a3,
        int a4,
        const union _LARGE_INTEGER *a5,
        const union _LARGE_INTEGER *a6,
        struct ICondition *a7)
{
  DWORD dwLowDateTime; // r14d
  RTL_SRWLOCK *v11; // rsi
  __int64 v12; // rdi
  int LogPrintf; // ebx
  DWORD USDWORDW; // eax
  __int64 v16; // rcx
  StructuredQuery1::ParseTracer *v17; // rax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, struct _FILETIME *); // rax
  __int64 (__fastcall ***v19)(_QWORD, GUID *, struct _FILETIME *); // r14
  int v20; // eax
  StructuredQuery1::ParseTracer *v21; // [rsp+50h] [rbp+30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+40h] BYREF

  SystemTimeAsFileTime = (struct _FILETIME)a3;
  dwLowDateTime = lpFileTime2[1].dwLowDateTime;
  v21 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v11 = (RTL_SRWLOCK *)&lpFileTime2[2];
  if ( CompareFileTime(&SystemTimeAsFileTime, lpFileTime2) > 0 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)&lpFileTime2[2]);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&SystemTimeAsFileTime, lpFileTime2) > 0 )
    {
      USDWORDW = SHRegGetUSDWORDW();
      LOBYTE(dwLowDateTime) = USDWORDW;
      v16 = *(_QWORD *)&SystemTimeAsFileTime + 300000000LL;
      lpFileTime2[1].dwLowDateTime = USDWORDW;
      *lpFileTime2 = (FILETIME)v16;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)&lpFileTime2[2]);
  }
  if ( (dwLowDateTime & 3) != 0 )
  {
    LogPrintf = StructuredQueryLogHandle(&v21);
    if ( LogPrintf < 0 )
      return (unsigned int)LogPrintf;
    v12 = (__int64)v21;
  }
  else
  {
    v12 = -1;
    LogPrintf = 1;
  }
  if ( v12 != -1 )
  {
    AcquireSRWLockExclusive(v11);
    LogPrintf = StructuredQueryLogPrintf(v12, L"RESOLVE NODATE");
    if ( LogPrintf < 0 )
      goto LABEL_18;
    if ( (dwLowDateTime & 5) == 0 )
    {
      LogPrintf = StructuredQueryLogPrintf(v12, L".\n");
      goto LABEL_16;
    }
    LogPrintf = StructuredQueryLogPrintf(v12, L" CONDITION:\n");
    if ( LogPrintf < 0 )
      goto LABEL_18;
    SystemTimeAsFileTime = 0;
    LogPrintf = -2147024882;
    v17 = (StructuredQuery1::ParseTracer *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = v17;
    if ( !v17
      || (v18 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct _FILETIME *))StructuredQuery1::ParseTracer::ParseTracer(v17),
          (v19 = v18) == 0) )
    {
LABEL_16:
      if ( LogPrintf >= 0 )
        LogPrintf = StructuredQueryElapsedTime(v12, a5, a6);
      goto LABEL_18;
    }
    LogPrintf = (**v18)(v18, &GUID_558e314c_f216_406f_8ef7_5aa314c3695c, &SystemTimeAsFileTime);
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct _FILETIME *)))(*v19)[2])(v19);
    if ( LogPrintf < 0 )
    {
LABEL_18:
      CloseHandle((HANDLE)v12);
      ReleaseSRWLockExclusive(v11);
      return (unsigned int)LogPrintf;
    }
    LogPrintf = (*(__int64 (__fastcall **)(struct _FILETIME, __int64, struct ICondition *))(**(_QWORD **)&SystemTimeAsFileTime
                                                                                          + 24LL))(
                  SystemTimeAsFileTime,
                  v12,
                  a2);
    if ( LogPrintf >= 0 )
    {
      LogPrintf = StructuredQueryLogPrintf(v12, L"END\n");
      if ( LogPrintf >= 0 )
      {
        if ( a4 < 0 )
        {
          v20 = StructuredQueryLogPrintf(
                  v12,
                  L"FAILURE=0x%08x - Resolution failed with this HRESULT.\n",
                  (unsigned int)a4);
        }
        else if ( a2 == a7 )
        {
          v20 = StructuredQueryLogPrintf(v12, L"SUCCESS IDENTICAL\n");
        }
        else
        {
          LogPrintf = StructuredQueryLogPrintf(v12, L"SUCCESS RESULT:\n");
          if ( LogPrintf < 0 )
            goto LABEL_26;
          LogPrintf = (*(__int64 (__fastcall **)(struct _FILETIME, __int64, struct ICondition *))(**(_QWORD **)&SystemTimeAsFileTime
                                                                                                + 24LL))(
                        SystemTimeAsFileTime,
                        v12,
                        a7);
          if ( LogPrintf < 0 )
            goto LABEL_26;
          v20 = StructuredQueryLogPrintf(v12, L"END\n");
        }
        LogPrintf = v20;
      }
    }
LABEL_26:
    (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&SystemTimeAsFileTime + 16LL))(SystemTimeAsFileTime);
    goto LABEL_16;
  }
  return (unsigned int)LogPrintf;
}

```

## disassembly

```asm
0x180010ce0  mov     [rsp-28h+arg_8], rbx
0x180010ce5  mov     [rsp-28h+arg_18], rsi
0x180010cea  mov     qword ptr [rsp-28h+SystemTimeAsFileTime.dwLowDateTime], r8
0x180010cef  push    rbp
0x180010cf0  push    rdi
0x180010cf1  push    r12
0x180010cf3  push    r14
0x180010cf5  push    r15
0x180010cf7  mov     rbp, rsp
0x180010cfa  sub     rsp, 20h
0x180010cfe  mov     r14d, [rcx+8]
0x180010d02  mov     rbx, rcx
0x180010d05  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010d09  mov     [rbp+arg_0], 0
0x180010d11  mov     r15d, r9d
0x180010d14  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180010d1c  mov     r12, rdx
0x180010d1f  call    cs:__imp_GetSystemTimeAsFileTime
0x180010d25  mov     rdx, rbx; lpFileTime2
0x180010d28  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x180010d2c  lea     rsi, [rbx+10h]
0x180010d30  call    cs:__imp_CompareFileTime
0x180010d36  test    eax, eax
0x180010d38  jg      short loc_180010D66
0x180010d3a  test    r14b, 3
0x180010d3e  jnz     short loc_180010DB4
0x180010d40  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010d44  lea     ebx, [rdi+2]
0x180010d47  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180010d4b  jnz     short loc_180010DCC
0x180010d4d  mov     rsi, [rsp+20h+arg_18]
0x180010d52  mov     eax, ebx
0x180010d54  mov     rbx, [rsp+20h+arg_8]
0x180010d59  add     rsp, 20h
0x180010d5d  pop     r15
0x180010d5f  pop     r14
0x180010d61  pop     r12
0x180010d63  pop     rdi
0x180010d64  pop     rbp
0x180010d65  retn
0x180010d66  mov     rcx, rsi; SRWLock
0x180010d69  call    cs:__imp_AcquireSRWLockExclusive
0x180010d6f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010d73  call    cs:__imp_GetSystemTimeAsFileTime
0x180010d79  mov     rdx, rbx; lpFileTime2
0x180010d7c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x180010d80  call    cs:__imp_CompareFileTime
0x180010d86  test    eax, eax
0x180010d88  jle     short loc_180010DA9
0x180010d8a  call    SHRegGetUSDWORDW
0x180010d8f  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180010d93  mov     r14d, eax
0x180010d96  add     rcx, 11E1A300h
0x180010d9d  mov     [rbx+8], eax
0x180010da0  mov     [rbx], ecx
0x180010da2  shr     rcx, 20h
0x180010da6  mov     [rbx+4], ecx
0x180010da9  mov     rcx, rsi; SRWLock
0x180010dac  call    cs:__imp_ReleaseSRWLockExclusive
0x180010db2  jmp     short loc_180010D3A
0x180010db4  lea     rcx, [rbp+arg_0]
0x180010db8  call    StructuredQueryLogHandle
0x180010dbd  mov     ebx, eax
0x180010dbf  test    eax, eax
0x180010dc1  js      short loc_180010D4D
0x180010dc3  mov     rdi, [rbp+arg_0]
0x180010dc7  jmp     loc_180010D47
0x180010dcc  mov     rcx, rsi; SRWLock
0x180010dcf  call    cs:__imp_AcquireSRWLockExclusive
0x180010dd5  lea     rdx, aResolveNodate; "RESOLVE NODATE"
0x180010ddc  mov     rcx, rdi
0x180010ddf  call    StructuredQueryLogPrintf
0x180010de4  mov     ebx, eax
0x180010de6  test    eax, eax
0x180010de8  js      short loc_180010E48
0x180010dea  mov     rcx, rdi
0x180010ded  test    r14b, 5
0x180010df1  jz      loc_180010F43
0x180010df7  lea     rdx, aCondition_0; " CONDITION:\n"
0x180010dfe  call    StructuredQueryLogPrintf
0x180010e03  mov     ebx, eax
0x180010e05  test    eax, eax
0x180010e07  js      short loc_180010E48
0x180010e09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010e10  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180010e18  mov     ecx, 10h; unsigned __int64
0x180010e1d  mov     ebx, 8007000Eh
0x180010e22  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010e27  mov     [rbp+arg_0], rax
0x180010e2b  test    rax, rax
0x180010e2e  jz      short loc_180010E40
0x180010e30  mov     rcx, rax; this
0x180010e33  call    ??0ParseTracer@StructuredQuery1@@AEAA@XZ; StructuredQuery1::ParseTracer::ParseTracer(void)
0x180010e38  mov     r14, rax
0x180010e3b  test    rax, rax
0x180010e3e  jnz     short loc_180010E5F
0x180010e40  test    ebx, ebx
0x180010e42  jns     loc_180010F56
0x180010e48  mov     rcx, rdi; hObject
0x180010e4b  call    cs:__imp_CloseHandle
0x180010e51  mov     rcx, rsi; SRWLock
0x180010e54  call    cs:__imp_ReleaseSRWLockExclusive
0x180010e5a  jmp     loc_180010D4D
0x180010e5f  mov     rcx, [rax]
0x180010e62  lea     r8, [rbp+SystemTimeAsFileTime]
0x180010e66  lea     rdx, _GUID_558e314c_f216_406f_8ef7_5aa314c3695c
0x180010e6d  mov     rax, [rcx]
0x180010e70  mov     rcx, r14
0x180010e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e78  mov     rcx, [r14]
0x180010e7b  mov     ebx, eax
0x180010e7d  mov     rax, [rcx+10h]
0x180010e81  mov     rcx, r14
0x180010e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e89  test    ebx, ebx
0x180010e8b  js      short loc_180010E48
0x180010e8d  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180010e91  mov     r8, r12
0x180010e94  mov     rdx, rdi
0x180010e97  mov     rax, [rcx]
0x180010e9a  mov     rax, [rax+18h]
0x180010e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ea3  mov     ebx, eax
0x180010ea5  test    eax, eax
0x180010ea7  js      short loc_180010EFB
0x180010ea9  lea     rdx, aEnd; "END\n"
0x180010eb0  mov     rcx, rdi
0x180010eb3  call    StructuredQueryLogPrintf
0x180010eb8  mov     ebx, eax
0x180010eba  test    eax, eax
0x180010ebc  js      short loc_180010EFB
0x180010ebe  mov     rcx, rdi
0x180010ec1  test    r15d, r15d
0x180010ec4  js      short loc_180010F2E
0x180010ec6  cmp     r12, [rbp+arg_30]
0x180010eca  jz      short loc_180010F10
0x180010ecc  lea     rdx, aSuccessResult; "SUCCESS RESULT:\n"
0x180010ed3  call    StructuredQueryLogPrintf
0x180010ed8  mov     ebx, eax
0x180010eda  test    eax, eax
0x180010edc  js      short loc_180010EFB
0x180010ede  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180010ee2  mov     rdx, rdi
0x180010ee5  mov     r8, [rbp+arg_30]
0x180010ee9  mov     rax, [rcx]
0x180010eec  mov     rax, [rax+18h]
0x180010ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef5  mov     ebx, eax
0x180010ef7  test    eax, eax
0x180010ef9  jns     short loc_180010F19
0x180010efb  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180010eff  mov     rax, [rcx]
0x180010f02  mov     rax, [rax+10h]
0x180010f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0b  jmp     loc_180010E40
0x180010f10  lea     rdx, aSuccessIdentic; "SUCCESS IDENTICAL\n"
0x180010f17  jmp     short loc_180010F23
0x180010f19  lea     rdx, aEnd; "END\n"
0x180010f20  mov     rcx, rdi
0x180010f23  call    StructuredQueryLogPrintf
0x180010f28  nop
0x180010f29  jmp     loc_180088210
0x180010f2e  mov     r8d, r15d
0x180010f31  lea     rdx, aFailure0x08xRe; "FAILURE=0x%08x - Resolution failed with"...
0x180010f38  call    StructuredQueryLogPrintf
0x180010f3d  nop
0x180010f3e  jmp     loc_180088210
0x180010f43  lea     rdx, asc_1800A1078; ".\n"
0x180010f4a  call    StructuredQueryLogPrintf
0x180010f4f  mov     ebx, eax
0x180010f51  jmp     loc_180010E40
0x180010f56  mov     r8, [rbp+arg_28]
0x180010f5a  mov     rcx, rdi
0x180010f5d  mov     rdx, [rbp+arg_20]
0x180010f61  call    StructuredQueryElapsedTime
0x180010f66  mov     ebx, eax
0x180010f68  jmp     loc_180010E48
0x180088210  mov     ebx, eax
0x180088212  jmp     loc_180010EFB
```
