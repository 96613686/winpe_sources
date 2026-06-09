# CLanguageResourcePool::_GetSuitableWordBreaker(ulong,WORDBREAKERFLAGS,ulong,_GUID const &,void * *,ulong *)

- ea: `0x180038624`
- end: `0x180038bea`
- name: `?_GetSuitableWordBreaker@CLanguageResourcePool@@AEAAJKW4WORDBREAKERFLAGS@@KAEBU_GUID@@PEAPEAXPEAK@Z`
- size: `1478`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, int, int, int, __int64, LPVOID *ppv, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038530`

## callees

- `0x18002683c`
- `0x180038624`
- `0x180038bf0`
- `0x180038d14`
- `0x1800390d0`
- `0x1800395d8`
- `0x1800396e0`
- `0x18005bec0`
- `0x18005daf0`
- `0x18005db64`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003868a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800386b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003868a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800386b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038697`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038720`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038697`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038720`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038917`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038b42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038917`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038b42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800389d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038b5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800389d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038b5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038923`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038afc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038afc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038770`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038b89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038770`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038b89`

## pseudocode

```c
__int64 __fastcall CLanguageResourcePool::_GetSuitableWordBreaker(
        RTL_SRWLOCK *a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        LPVOID *ppv,
        unsigned int *a7)
{
  char v7; // r15
  unsigned int *v10; // r12
  RTL_SRWLOCK *v11; // r14
  PVOID Ptr; // rbx
  int v13; // ebx
  __int64 v14; // rdx
  _DWORD *v15; // r9
  int v16; // ecx
  int v17; // eax
  const void *v18; // rdx
  unsigned __int64 v19; // r8
  unsigned int v20; // r9d
  HRESULT SearchWordBreakerWrapper; // ebx
  __int64 v22; // r8
  unsigned int v23; // r14d
  const struct _GUID *v24; // r9
  struct IWordBreaker *v25; // rcx
  LARGE_INTEGER v26; // rcx
  struct IBorrowedWordBreaker *v27; // rbx
  struct IBorrowedWordBreaker *v28; // rcx
  _QWORD *v30; // rbx
  __int64 v31; // rax
  int v32; // r15d
  DWORD CurrentThreadId; // r11d
  __int64 v34; // rdi
  __int64 v35; // r8
  __int64 v36; // r12
  __int64 v37; // rdx
  _DWORD *v38; // rcx
  __int64 (__fastcall *v39)(__int64, GUID *, struct IBorrowedWordBreaker **); // rbx
  __int64 v40; // r8
  CDelayedInitReplayingWordBreaker *v41; // rax
  CDelayedInitReplayingWordBreaker *inited; // rdi
  __int64 v43; // rax
  unsigned int v44; // [rsp+30h] [rbp-81h]
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-79h] BYREF
  struct IBorrowedWordBreaker *v46; // [rsp+40h] [rbp-71h] BYREF
  int v47; // [rsp+48h] [rbp-69h]
  unsigned int *v48; // [rsp+50h] [rbp-61h]
  IID rclsid; // [rsp+58h] [rbp-59h] BYREF
  struct IWordBreaker *v50[7]; // [rsp+68h] [rbp-49h] BYREF

  LODWORD(v50[0]) = a4;
  v7 = a3;
  v47 = a3;
  v10 = a7;
  v48 = a7;
  *ppv = 0;
  *a7 = 0;
  rclsid = GUID_NULL;
  v11 = a1 + 3;
  AcquireSRWLockShared(a1 + 3);
  Ptr = a1[5].Ptr;
  ReleaseSRWLockShared(v11);
  if ( Ptr
    || ((AcquireSRWLockExclusive(v11), a1[5].Ptr)
      ? (SearchWordBreakerWrapper = 0)
      : (SearchWordBreakerWrapper = CLanguageResourcePool::_InitializeTables((CLanguageResourcePool *)a1)),
        ReleaseSRWLockExclusive(v11),
        SearchWordBreakerWrapper >= 0) )
  {
    v44 = 0;
    v13 = 0;
    AcquireSRWLockShared(v11);
    v14 = 0;
    do
    {
      if ( (unsigned int)v14 >= HIDWORD(a1[4].Ptr) )
        break;
      v15 = a1[5].Ptr;
      v16 = v15[5 * v14];
      if ( a2 == v16 )
      {
        v17 = 5;
      }
      else if ( (_WORD)a2 == (_WORD)v16 )
      {
        v17 = 4;
      }
      else if ( (((unsigned __int16)v16 ^ (unsigned __int16)a2) & 0x3FF) != 0 )
      {
        v17 = v16 == 0;
      }
      else
      {
        v17 = 3;
      }
      if ( v17 > v13 )
      {
        v13 = v17;
        rclsid = *(IID *)&v15[5 * v14 + 1];
        v44 = v15[5 * v14];
      }
      v14 = (unsigned int)(v14 + 1);
    }
    while ( v13 != 5 );
    ReleaseSRWLockShared(v11);
    if ( !v13 )
      return (unsigned int)-2147418113;
    v30 = (char *)a1[6].Ptr
        + 104 * (314159269 * HashFn::HashBlob((HashFn *)&rclsid, v18, v19, v20) % 0x3B9ACA07 % LODWORD(a1[4].Ptr));
    if ( !v30 )
      return (unsigned int)-2147023728;
    do
    {
      v31 = *v30 - *(_QWORD *)&rclsid.Data1;
      if ( *v30 == *(_QWORD *)&rclsid.Data1 )
        v31 = v30[1] - *(_QWORD *)rclsid.Data4;
      if ( !v31 )
        break;
      v30 = (_QWORD *)v30[12];
    }
    while ( v30 );
    if ( !v30 )
      return (unsigned int)-2147023728;
    if ( (v7 & 1) != 0 )
    {
      SearchWordBreakerWrapper = CoCreateInstance(&rclsid, 0, 1u, &GUID_4ad66795_d0a1_4083_aa28_087e5636bbf3, ppv);
      v23 = v44;
LABEL_32:
      if ( SearchWordBreakerWrapper >= 0 )
        *v10 = v23;
      return (unsigned int)SearchWordBreakerWrapper;
    }
    v46 = 0;
    AcquireSRWLockExclusive(v11);
    v32 = -2147467259;
    CurrentThreadId = GetCurrentThreadId();
    v34 = 0;
    v35 = 0xFFFFFFFFLL;
    v36 = 0;
    v37 = 0;
    while ( (unsigned int)v37 < 0xA )
    {
      v38 = (_DWORD *)v30[v37 + 2];
      if ( v38 )
      {
        if ( v38[12] )
        {
          if ( v38[13] == CurrentThreadId && v38[14] == (v47 & 4) && v38[15] == LODWORD(v50[0]) )
          {
            v34 = v30[v37 + 2];
            v30[v37 + 2] = 0;
            v32 = 0;
          }
          else
          {
            *((_DWORD *)&v50[2] + v36) = v37;
            v36 = (unsigned int)(v36 + 1);
          }
        }
        else
        {
          v35 = (unsigned int)v37;
        }
      }
      v37 = (unsigned int)(v37 + 1);
      if ( v34 )
        goto LABEL_50;
    }
    if ( (unsigned int)v35 < 0xA )
    {
      _mm_lfence();
      v43 = (unsigned int)v35;
LABEL_75:
      v34 = v30[v43 + 2];
      v30[v43 + 2] = 0;
      goto LABEL_51;
    }
    if ( (unsigned int)v36 > 5 )
    {
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v35 = (314159269 * PerformanceCount.HighPart + 1665315097 * PerformanceCount.LowPart) % 0x3B9ACA07;
      v37 = (unsigned int)v35 % (unsigned int)v36;
      v43 = *((unsigned int *)&v50[2] + v37);
      goto LABEL_75;
    }
LABEL_50:
    SearchWordBreakerWrapper = 0;
    if ( v32 < 0 )
      goto LABEL_52;
LABEL_51:
    *(_DWORD *)(v34 + 64) = 0;
    *(_QWORD *)(v34 + 80) = a1;
    (*((void (__fastcall **)(RTL_SRWLOCK *, __int64, __int64))a1->Ptr + 1))(a1, v37, v35);
    v39 = **(__int64 (__fastcall ***)(__int64, GUID *, struct IBorrowedWordBreaker **))v34;
    Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&v46);
    SearchWordBreakerWrapper = v39(v34, &GUID_4ad66795_d0a1_4083_aa28_087e5636bbf3, &v46);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
LABEL_52:
    ReleaseSRWLockExclusive(v11);
    if ( SearchWordBreakerWrapper < 0 )
    {
      v23 = v44;
    }
    else
    {
      v27 = v46;
      if ( v46 )
      {
        v23 = v44;
      }
      else
      {
        if ( (byte_1800B11C3 & 0x40) != 0 )
          McGenEventWrite_EventWriteTransfer(
            Microsoft_Windows_Shell_Core_Provider_Context,
            ShellTraceId_StructuredQuery_CreateWordBreaker_Start,
            v40,
            1,
            v50);
        PerformanceCount.QuadPart = 0;
        Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&PerformanceCount);
        SearchWordBreakerWrapper = CoCreateInstance(
                                     &rclsid,
                                     0,
                                     1u,
                                     &GUID_d53552c8_77e3_101a_b552_08002b33b0e6,
                                     (LPVOID *)&PerformanceCount);
        if ( SearchWordBreakerWrapper < 0 )
        {
          v23 = v44;
        }
        else
        {
          v50[0] = 0;
          Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(v50);
          v23 = v44;
          SearchWordBreakerWrapper = CreateSearchWordBreakerWrapper(
                                       v44,
                                       (struct IWordBreaker *)PerformanceCount.QuadPart,
                                       v50);
          if ( SearchWordBreakerWrapper >= 0 )
          {
            Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&v46);
            SearchWordBreakerWrapper = CBorrowedWordBreaker::CreateInstance(
                                         v50[0],
                                         &rclsid,
                                         (struct CLanguageResourcePool *)a1,
                                         v24,
                                         (void **)&v46);
          }
          v25 = v50[0];
          if ( v50[0] )
          {
            v50[0] = 0;
            ((void (__fastcall *)(struct IWordBreaker *))v25->lpVtbl->Release)(v25);
          }
        }
        if ( (byte_1800B11C3 & 0x40) != 0 )
          McGenEventWrite_EventWriteTransfer(
            Microsoft_Windows_Shell_Core_Provider_Context,
            ShellTraceId_StructuredQuery_CreateWordBreaker_Stop,
            v22,
            1,
            v50);
        v26 = PerformanceCount;
        if ( PerformanceCount.QuadPart )
        {
          PerformanceCount.QuadPart = 0;
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v26.QuadPart + 16LL))(v26);
        }
        if ( SearchWordBreakerWrapper < 0 )
          goto LABEL_29;
        v27 = v46;
      }
      if ( (v47 & 8) != 0 )
      {
        v41 = (CDelayedInitReplayingWordBreaker *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v41 )
          inited = CDelayedInitReplayingWordBreaker::CDelayedInitReplayingWordBreaker(v41, &rclsid, v27);
        else
          inited = 0;
        if ( inited )
          SearchWordBreakerWrapper = (**(__int64 (__fastcall ***)(CDelayedInitReplayingWordBreaker *, GUID *, LPVOID *))inited)(
                                       inited,
                                       &GUID_4ad66795_d0a1_4083_aa28_087e5636bbf3,
                                       ppv);
        else
          SearchWordBreakerWrapper = -2147024882;
        if ( inited )
          (*(void (__fastcall **)(CDelayedInitReplayingWordBreaker *))(*(_QWORD *)inited + 16LL))(inited);
      }
      else
      {
        SearchWordBreakerWrapper = (**(__int64 (__fastcall ***)(struct IBorrowedWordBreaker *, GUID *, LPVOID *))v27)(
                                     v27,
                                     &GUID_4ad66795_d0a1_4083_aa28_087e5636bbf3,
                                     ppv);
      }
    }
LABEL_29:
    v28 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(struct IBorrowedWordBreaker *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v10 = v48;
    goto LABEL_32;
  }
  return (unsigned int)SearchWordBreakerWrapper;
}

```

## disassembly

```asm
0x180038624  push    rbp
0x180038626  push    rbx
0x180038627  push    rsi
0x180038628  push    rdi
0x180038629  push    r12
0x18003862b  push    r13
0x18003862d  push    r14
0x18003862f  push    r15
0x180038631  lea     rbp, [rsp-7]
0x180038636  sub     rsp, 0B8h
0x18003863d  mov     rax, cs:__security_cookie
0x180038644  xor     rax, rsp
0x180038647  mov     [rbp+3Fh+var_50], rax
0x18003864b  mov     dword ptr [rbp+3Fh+var_88], r9d
0x18003864f  mov     r15d, r8d
0x180038652  mov     [rbp+3Fh+var_A8], r8d
0x180038656  mov     edi, edx
0x180038658  mov     rsi, rcx
0x18003865b  mov     r13, [rbp+3Fh+arg_28]
0x18003865f  mov     r12, [rbp+3Fh+arg_30]
0x180038663  mov     [rbp+3Fh+var_A0], r12
0x180038667  mov     qword ptr [r13+0], 0
0x18003866f  mov     dword ptr [r12], 0
0x180038677  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003867e  movdqu  xmmword ptr [rbp+3Fh+rclsid.Data1], xmm0
0x180038683  lea     r14, [rcx+18h]
0x180038687  mov     rcx, r14; SRWLock
0x18003868a  call    cs:__imp_AcquireSRWLockShared
0x180038690  mov     rbx, [rsi+28h]
0x180038694  mov     rcx, r14; SRWLock
0x180038697  call    cs:__imp_ReleaseSRWLockShared
0x18003869d  test    rbx, rbx
0x1800386a0  jz      loc_180038B3F
0x1800386a6  mov     [rsp+0F0h+var_C0], 0
0x1800386ae  xor     ebx, ebx
0x1800386b0  mov     rcx, r14; SRWLock
0x1800386b3  call    cs:__imp_AcquireSRWLockShared
0x1800386b9  xor     edx, edx
0x1800386bb  cmp     edx, [rsi+24h]
0x1800386be  jnb     short loc_18003871D
0x1800386c0  lea     r8, [rdx+rdx*4]
0x1800386c4  mov     r9, [rsi+28h]
0x1800386c8  mov     ecx, [r9+r8*4]
0x1800386cc  cmp     edi, ecx
0x1800386ce  jz      short loc_1800386F8
0x1800386d0  cmp     di, cx
0x1800386d3  jz      loc_180038AAF
0x1800386d9  movzx   eax, di
0x1800386dc  xor     ax, cx
0x1800386df  mov     r10d, 3FFh
0x1800386e5  test    r10w, ax
0x1800386e9  jz      loc_1800388D9
0x1800386ef  xor     eax, eax
0x1800386f1  test    ecx, ecx
0x1800386f3  setz    al
0x1800386f6  jmp     short loc_1800386FD
0x1800386f8  mov     eax, 5
0x1800386fd  cmp     eax, ebx
0x1800386ff  jle     short loc_180038716
0x180038701  mov     ebx, eax
0x180038703  movups  xmm0, xmmword ptr [r9+r8*4+4]
0x180038709  movdqu  xmmword ptr [rbp+3Fh+rclsid.Data1], xmm0
0x18003870e  mov     eax, [r9+r8*4]
0x180038712  mov     [rsp+0F0h+var_C0], eax
0x180038716  inc     edx
0x180038718  cmp     ebx, 5
0x18003871b  jnz     short loc_1800386BB
0x18003871d  mov     rcx, r14; SRWLock
0x180038720  call    cs:__imp_ReleaseSRWLockShared
0x180038726  test    ebx, ebx
0x180038728  jnz     loc_180038891
0x18003872e  mov     ebx, 8000FFFFh
0x180038733  jmp     loc_18003886F
0x180038738  test    cs:byte_1800B11C3, 40h
0x18003873f  jnz     loc_180038B9B
0x180038745  mov     qword ptr [rbp+3Fh+PerformanceCount], 0
0x18003874d  lea     rcx, [rbp+3Fh+PerformanceCount]
0x180038751  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x180038756  lea     rax, [rbp+3Fh+PerformanceCount]
0x18003875a  mov     [rsp+0F0h+ppv], rax; ppv
0x18003875f  lea     r9, _GUID_d53552c8_77e3_101a_b552_08002b33b0e6; riid
0x180038766  xor     edx, edx; pUnkOuter
0x180038768  lea     r8d, [rdx+1]; dwClsContext
0x18003876c  lea     rcx, [rbp+3Fh+rclsid]; rclsid
0x180038770  call    cs:__imp_CoCreateInstance
0x180038776  mov     ebx, eax
0x180038778  test    eax, eax
0x18003877a  js      loc_180038AB9
0x180038780  mov     [rbp+3Fh+var_88], 0
0x180038788  lea     rcx, [rbp+3Fh+var_88]
0x18003878c  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x180038791  lea     r8, [rbp+3Fh+var_88]; struct IWordBreaker **
0x180038795  mov     rdx, qword ptr [rbp+3Fh+PerformanceCount]; struct IWordBreaker *
0x180038799  mov     r14d, [rsp+0F0h+var_C0]
0x18003879e  mov     ecx, r14d; unsigned int
0x1800387a1  call    ?CreateSearchWordBreakerWrapper@@YAJKPEAUIWordBreaker@@PEAPEAU1@@Z; CreateSearchWordBreakerWrapper(ulong,IWordBreaker *,IWordBreaker * *)
0x1800387a6  mov     ebx, eax
0x1800387a8  test    eax, eax
0x1800387aa  js      short loc_1800387D0
0x1800387ac  lea     rcx, [rbp+3Fh+var_B0]
0x1800387b0  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x1800387b5  lea     rax, [rbp+3Fh+var_B0]
0x1800387b9  mov     [rsp+0F0h+ppv], rax; void **
0x1800387be  mov     r8, rsi; struct CLanguageResourcePool *
0x1800387c1  lea     rdx, [rbp+3Fh+rclsid]; struct _GUID *
0x1800387c5  mov     rcx, [rbp+3Fh+var_88]; struct IWordBreaker *
0x1800387c9  call    ?CreateInstance@CBorrowedWordBreaker@@SAJPEAUIWordBreaker@@AEBU_GUID@@PEAVCLanguageResourcePool@@1PEAPEAX@Z; CBorrowedWordBreaker::CreateInstance(IWordBreaker *,_GUID const &,CLanguageResourcePool *,_GUID const &,void * *)
0x1800387ce  mov     ebx, eax
0x1800387d0  mov     rcx, [rbp+3Fh+var_88]
0x1800387d4  test    rcx, rcx
0x1800387d7  jz      short loc_1800387EE
0x1800387d9  mov     [rbp+3Fh+var_88], 0
0x1800387e1  mov     rax, [rcx]
0x1800387e4  mov     rax, [rax+10h]
0x1800387e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387ed  nop
0x1800387ee  test    cs:byte_1800B11C3, 40h
0x1800387f5  jnz     loc_180038BC2
0x1800387fb  mov     rcx, qword ptr [rbp+3Fh+PerformanceCount]
0x1800387ff  test    rcx, rcx
0x180038802  jz      short loc_180038819
0x180038804  mov     qword ptr [rbp+3Fh+PerformanceCount], 0
0x18003880c  mov     rax, [rcx]
0x18003880f  mov     rax, [rax+10h]
0x180038813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038818  nop
0x180038819  test    ebx, ebx
0x18003881b  js      short loc_180038845
0x18003881d  mov     rbx, [rbp+3Fh+var_B0]
0x180038821  test    byte ptr [rbp+3Fh+var_A8], 8
0x180038825  jnz     loc_180038A47
0x18003882b  mov     rax, [rbx]
0x18003882e  mov     r8, r13
0x180038831  lea     rdx, _GUID_4ad66795_d0a1_4083_aa28_087e5636bbf3
0x180038838  mov     rcx, rbx
0x18003883b  mov     rax, [rax]
0x18003883e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038843  mov     ebx, eax
0x180038845  mov     rcx, [rbp+3Fh+var_B0]
0x180038849  test    rcx, rcx
0x18003884c  jz      short loc_180038863
0x18003884e  mov     [rbp+3Fh+var_B0], 0
0x180038856  mov     rax, [rcx]
0x180038859  mov     rax, [rax+10h]
0x18003885d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038862  nop
0x180038863  mov     r12, [rbp+3Fh+var_A0]
0x180038867  test    ebx, ebx
0x180038869  js      short loc_18003886F
0x18003886b  mov     [r12], r14d
0x18003886f  mov     eax, ebx
0x180038871  mov     rcx, [rbp+3Fh+var_50]
0x180038875  xor     rcx, rsp; StackCookie
0x180038878  call    __security_check_cookie
0x18003887d  add     rsp, 0B8h
0x180038884  pop     r15
0x180038886  pop     r14
0x180038888  pop     r13
0x18003888a  pop     r12
0x18003888c  pop     rdi
0x18003888d  pop     rsi
0x18003888e  pop     rbx
0x18003888f  pop     rbp
0x180038890  retn
0x180038891  lea     rcx, [rbp+3Fh+rclsid]; this
0x180038895  call    ?HashBlob@HashFn@@YAKPEBX_KK@Z; HashFn::HashBlob(void const *,unsigned __int64,ulong)
0x18003889a  imul    r8d, eax, 12B9B0A5h
0x1800388a1  mov     eax, 12E0BE63h
0x1800388a6  mul     r8d
0x1800388a9  mov     ecx, r8d
0x1800388ac  sub     ecx, edx
0x1800388ae  shr     ecx, 1
0x1800388b0  add     ecx, edx
0x1800388b2  shr     ecx, 1Dh
0x1800388b5  imul    ecx, 3B9ACA07h
0x1800388bb  sub     r8d, ecx
0x1800388be  xor     edx, edx
0x1800388c0  mov     eax, r8d
0x1800388c3  div     dword ptr [rsi+20h]
0x1800388c6  mov     ecx, edx
0x1800388c8  imul    rbx, rcx, 68h ; 'h'
0x1800388cc  add     rbx, [rsi+30h]
0x1800388d0  jnz     short loc_1800388E3
0x1800388d2  mov     ebx, 80070490h
0x1800388d7  jmp     short loc_18003886F
0x1800388d9  mov     eax, 3
0x1800388de  jmp     loc_1800386FD
0x1800388e3  mov     rax, [rbx]
0x1800388e6  sub     rax, qword ptr [rbp+3Fh+rclsid.Data1]
0x1800388ea  jnz     short loc_1800388F4
0x1800388ec  mov     rax, [rbx+8]
0x1800388f0  sub     rax, qword ptr [rbp+3Fh+rclsid.Data4]
0x1800388f4  test    rax, rax
0x1800388f7  jnz     loc_180038A35
0x1800388fd  test    rbx, rbx
0x180038900  jz      short loc_1800388D2
0x180038902  test    r15b, 1
0x180038906  jnz     loc_180038B73
0x18003890c  mov     [rbp+3Fh+var_B0], 0
0x180038914  mov     rcx, r14; SRWLock
0x180038917  call    cs:__imp_AcquireSRWLockExclusive
0x18003891d  mov     r15d, 80004005h
0x180038923  call    cs:__imp_GetCurrentThreadId
0x180038929  mov     r11d, eax
0x18003892c  xor     edi, edi
0x18003892e  or      r8d, 0FFFFFFFFh
0x180038932  xor     r12d, r12d
0x180038935  xor     edx, edx
0x180038937  cmp     edx, 0Ah
0x18003893a  jnb     loc_180038AC7
0x180038940  mov     rcx, [rbx+rdx*8+10h]
0x180038945  test    rcx, rcx
0x180038948  jz      short loc_180038972
0x18003894a  mov     r9d, [rcx+30h]
0x18003894e  test    r9d, r9d
0x180038951  jz      loc_180038A23
0x180038957  cmp     [rcx+34h], r11d
0x18003895b  jz      loc_1800389F4
0x180038961  test    r9d, r9d
0x180038964  jz      loc_180038A23
0x18003896a  mov     [rbp+r12*4+3Fh+var_78], edx
0x18003896f  inc     r12d
0x180038972  inc     edx
0x180038974  test    rdi, rdi
0x180038977  jz      short loc_180038937
0x180038979  xor     ebx, ebx
0x18003897b  test    r15d, r15d
0x18003897e  js      short loc_1800389D0
0x180038980  mov     dword ptr [rdi+40h], 0
0x180038987  mov     [rdi+50h], rsi
0x18003898b  mov     rax, [rsi]
0x18003898e  mov     rcx, rsi
0x180038991  mov     rax, [rax+8]
0x180038995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003899a  mov     rax, [rdi]
0x18003899d  mov     rbx, [rax]
0x1800389a0  lea     rcx, [rbp+3Fh+var_B0]
0x1800389a4  call    ?InternalRelease@?$ComPtr@UIWordBreaker@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(void)
0x1800389a9  lea     r8, [rbp+3Fh+var_B0]
0x1800389ad  lea     rdx, _GUID_4ad66795_d0a1_4083_aa28_087e5636bbf3
0x1800389b4  mov     rcx, rdi
0x1800389b7  mov     rax, rbx
0x1800389ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389bf  mov     ebx, eax
0x1800389c1  mov     rax, [rdi]
0x1800389c4  mov     rcx, rdi
0x1800389c7  mov     rax, [rax+10h]
0x1800389cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389d0  mov     rcx, r14; SRWLock
0x1800389d3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800389d9  test    ebx, ebx
0x1800389db  js      short loc_180038A2B
0x1800389dd  mov     rbx, [rbp+3Fh+var_B0]
0x1800389e1  test    rbx, rbx
0x1800389e4  jz      loc_180038738
0x1800389ea  mov     r14d, [rsp+0F0h+var_C0]
0x1800389ef  jmp     loc_180038821
0x1800389f4  mov     eax, [rbp+3Fh+var_A8]
0x1800389f7  and     eax, 4
0x1800389fa  cmp     [rcx+38h], eax
0x1800389fd  jnz     loc_180038961
0x180038a03  mov     eax, dword ptr [rbp+3Fh+var_88]
0x180038a06  cmp     [rcx+3Ch], eax
0x180038a09  jnz     loc_180038961
0x180038a0f  mov     rdi, rcx
0x180038a12  mov     qword ptr [rbx+rdx*8+10h], 0
0x180038a1b  xor     r15d, r15d
0x180038a1e  jmp     loc_180038972
0x180038a23  mov     r8d, edx
0x180038a26  jmp     loc_180038972
0x180038a2b  mov     r14d, [rsp+0F0h+var_C0]
0x180038a30  jmp     loc_180038845
0x180038a35  mov     rbx, [rbx+60h]
0x180038a39  test    rbx, rbx
0x180038a3c  jz      loc_1800388FD
0x180038a42  jmp     loc_1800388E3
0x180038a47  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038a4e  mov     ecx, 38h ; '8'; unsigned __int64
0x180038a53  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038a58  test    rax, rax
0x180038a5b  jz      short loc_180038AC3
0x180038a5d  mov     r8, rbx; struct IBorrowedWordBreaker *
0x180038a60  lea     rdx, [rbp+3Fh+rclsid]; struct _GUID *
0x180038a64  mov     rcx, rax; this
0x180038a67  call    ??0CDelayedInitReplayingWordBreaker@@QEAA@AEBU_GUID@@PEAUIBorrowedWordBreaker@@@Z; CDelayedInitReplayingWordBreaker::CDelayedInitReplayingWordBreaker(_GUID const &,IBorrowedWordBreaker *)
0x180038a6c  mov     rdi, rax
0x180038a6f  test    rdi, rdi
0x180038a72  jnz     short loc_180038A93
0x180038a74  mov     ebx, 8007000Eh
0x180038a79  test    rdi, rdi
0x180038a7c  jz      short loc_180038A8E
0x180038a7e  mov     rax, [rdi]
0x180038a81  mov     rcx, rdi
0x180038a84  mov     rax, [rax+10h]
0x180038a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a8d  nop
0x180038a8e  jmp     loc_180038845
0x180038a93  mov     rax, [rdi]
0x180038a96  mov     r8, r13
0x180038a99  lea     rdx, _GUID_4ad66795_d0a1_4083_aa28_087e5636bbf3
  ... truncated ...
```
