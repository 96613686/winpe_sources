# MapControl::PersistentMapsCache::loadIndexInternal(MapControl::LoadIndexFailurePolicy)

- ea: `0x1800546f4`
- end: `0x180054a49`
- name: `?loadIndexInternal@PersistentMapsCache@MapControl@@AEAA?AVStatusCode@Core@@W4LoadIndexFailurePolicy@2@@Z`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config`

## callers

- `0x1800546b0`

## callees

- `0x18000d090`
- `0x18000dc8c`
- `0x180016cbc`
- `0x180017a58`
- `0x18001b9e0`
- `0x18002de08`
- `0x18002e310`
- `0x18002f724`
- `0x18002f774`
- `0x18002f7b4`
- `0x18002f99c`
- `0x18002f9c4`
- `0x1800403ac`
- `0x18004756c`
- `0x180050058`
- `0x1800528f8`
- `0x1800546f4`
- `0x180055838`
- `0x180077b8c`
- `0x180077cac`
- `0x18008d054`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005478b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005478b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054968`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054968`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800549c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800549c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int *__fastcall MapControl::PersistentMapsCache::loadIndexInternal(__int64 a1, int *a2, int a3)
{
  RTL_SRWLOCK *Instance; // rbx
  __int64 *v7; // rax
  __int64 v8; // rbx
  std::_Ref_count_base *v9; // rdi
  _DWORD *StatusCode; // rax
  int v11; // ecx
  __int64 Results; // rax
  const char *v13; // r13
  unsigned __int64 v14; // rbx
  const char *v15; // r15
  __int128 *v16; // r13
  unsigned __int64 v17; // r15
  char v19; // [rsp+20h] [rbp-89h]
  HANDLE *v20; // [rsp+28h] [rbp-81h] BYREF
  const char *v21; // [rsp+30h] [rbp-79h] BYREF
  std::_Ref_count_base *v22; // [rsp+38h] [rbp-71h]
  std::_Ref_count_base *v23[2]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-59h] BYREF
  __int128 v25; // [rsp+60h] [rbp-49h]
  _BYTE v26[8]; // [rsp+70h] [rbp-39h] BYREF
  std::_Ref_count_base *v27; // [rsp+78h] [rbp-31h]
  __int128 v28; // [rsp+80h] [rbp-29h] BYREF
  __int128 v29; // [rsp+90h] [rbp-19h]
  __int64 v30; // [rsp+A0h] [rbp-9h]
  __int128 *v31; // [rsp+B8h] [rbp+Fh]

  Instance = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<MapControl::DataLoaderPerformanceTracer>::getInstance();
  Pal::PerformanceTracer::traceEvent<>(Instance, (struct Pal::PerformanceEventId *)&dword_1800F10A8);
  Pal::ScopedPerformanceSpan::ScopedPerformanceSpan(
    (Pal::ScopedPerformanceSpan *)v24,
    (struct Pal::PerformanceTracer *)Instance,
    (const struct Pal::PerformanceEventId *)&dword_1800F10B4);
  Pal::ManualResetEvent::ManualResetEvent((Pal::ManualResetEvent *)&v20);
  *(_OWORD *)v23 = 0;
  v25 = 0;
  if ( !(unsigned __int8)Pal::IO::fileExists(a1 + 304, *(unsigned int *)(a1 + 384)) )
  {
    SetEvent(*v20);
    *a2 = 1;
    goto LABEL_36;
  }
  v7 = (__int64 *)Pal::IO::beginReadFile(&v21, a1 + 304, *(unsigned int *)(a1 + 384));
  v8 = *v7;
  v9 = (std::_Ref_count_base *)v7[1];
  *v7 = 0;
  v7[1] = 0;
  *(_QWORD *)&v25 = v8;
  *((_QWORD *)&v25 + 1) = v9;
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  *(_QWORD *)&v28 = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::PersistentMapsCache::*)(Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char>>> const &,Pal::ManualResetEvent &),MapControl::PersistentMapsCache *,std::_Ph<1> const &,std::reference_wrapper<Pal::ManualResetEvent>>,void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char>>> &>::`vftable';
  *((_QWORD *)&v28 + 1) = MapControl::PersistentMapsCache::indexWriteDone;
  *(_QWORD *)&v29 = &v20;
  BYTE8(v29) = v19;
  v30 = a1;
  v31 = &v28;
  Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char>>>::setCallback(v8, &v28);
  std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>> &>::_Tidy(&v28);
  Pal::ManualResetEvent::wait((Pal::ManualResetEvent *)&v20);
  if ( !*(_BYTE *)(v8 + 150) )
  {
    if ( a3 == 1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1);
    StatusCode = (_DWORD *)Pal::UntypedAsyncOperation::getStatusCode(v8, &v21);
    v11 = 41943040;
    if ( *StatusCode != 25165824 )
      v11 = 8388610;
    *a2 = v11;
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    goto LABEL_36;
  }
  Results = Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>>::getResults(v8);
  std::shared_ptr<MapControl::OdvsChunkIndex>::operator=(v23, Results);
  v13 = *(const char **)v23[0];
  if ( !*(_QWORD *)v23[0] )
    goto LABEL_29;
  v14 = *((_QWORD *)v23[0] + 1) - (_QWORD)v13;
  if ( v14 < 8 )
    goto LABEL_29;
  v21 = 0;
  if ( !strncmp_0(v13, "MCI 1.00", 8u) )
  {
    if ( v14 < 0x1C )
      goto LABEL_29;
    v21 = "MCI 1.00";
  }
  v15 = "MCI 1.01";
  if ( strncmp_0(v13, "MCI 1.01", 8u) )
    v15 = v21;
  if ( !strncmp_0(v13, "MCI 1.02", 8u) )
  {
    v15 = "MCI 1.02";
    goto LABEL_23;
  }
  if ( !v15 )
  {
LABEL_29:
    if ( a3 == 1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1);
    *a2 = 41943040;
    goto LABEL_32;
  }
LABEL_23:
  if ( memcmp_0(v15, "MCI 1.02", 8u) )
    goto LABEL_29;
  v16 = (__int128 *)(v13 + 8);
  v17 = v14 - 8;
  v21 = (const char *)(a1 + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
  while ( v17 >= 0x20 )
  {
    v28 = *v16;
    v29 = v16[1];
    v16 += 2;
    v17 -= 32LL;
    std::make_shared<MapControl::PersistentMapsCache::IndexEntry,MapControl::PersistentMapsCache::IndexEntry &>(
      v26,
      &v28);
    MapControl::PersistentMapsCache::addPairToIndexMap((MapControl::PersistentMapsCache *)a1);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
  *a2 = 1;
LABEL_32:
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  if ( v23[1] )
    std::_Ref_count_base::_Decref(v23[1]);
LABEL_36:
  std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(&v20);
  Pal::ScopedPerformanceSpan::~ScopedPerformanceSpan((Pal::ScopedPerformanceSpan *)v24);
  return a2;
}

```

## disassembly

```asm
0x1800546f4  mov     [rsp-8+arg_10], rbx
0x1800546f9  push    rbp
0x1800546fa  push    rsi
0x1800546fb  push    rdi
0x1800546fc  push    r12
0x1800546fe  push    r13
0x180054700  push    r14
0x180054702  push    r15
0x180054704  lea     rbp, [rsp-27h]
0x180054709  sub     rsp, 0D0h
0x180054710  mov     rax, cs:__security_cookie
0x180054717  xor     rax, rsp
0x18005471a  mov     [rbp+57h+var_40], rax
0x18005471e  mov     r12d, r8d
0x180054721  mov     r14, rdx
0x180054724  mov     rsi, rcx
0x180054727  call    ?getInstance@?$PerformanceTracerSingleton@VDataLoaderPerformanceTracer@MapControl@@@Pal@@KAAEAVDataLoaderPerformanceTracer@MapControl@@XZ; Pal::PerformanceTracerSingleton<MapControl::DataLoaderPerformanceTracer>::getInstance(void)
0x18005472c  mov     rbx, rax
0x18005472f  lea     rdx, dword_1800F10A8; struct Pal::PerformanceEventId *
0x180054736  mov     rcx, rax; SRWLock
0x180054739  call    ??$traceEvent@$$V@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@@Z; Pal::PerformanceTracer::traceEvent<>(Pal::PerformanceEventId const &)
0x18005473e  lea     r8, dword_1800F10B4; struct Pal::PerformanceEventId *
0x180054745  mov     rdx, rbx; struct Pal::PerformanceTracer *
0x180054748  lea     rcx, [rbp+57h+var_B0]; this
0x18005474c  call    ??0ScopedPerformanceSpan@Pal@@QEAA@PEAVPerformanceTracer@1@AEBVPerformanceEventId@1@@Z; Pal::ScopedPerformanceSpan::ScopedPerformanceSpan(Pal::PerformanceTracer *,Pal::PerformanceEventId const &)
0x180054751  nop
0x180054752  lea     rcx, [rsp+100h+var_D8]; this
0x180054757  call    ??0ManualResetEvent@Pal@@QEAA@XZ; Pal::ManualResetEvent::ManualResetEvent(void)
0x18005475c  nop
0x18005475d  xorps   xmm0, xmm0
0x180054760  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180054765  movdqu  [rbp+57h+var_A0], xmm0
0x18005476a  lea     rbx, [rsi+130h]
0x180054771  mov     edx, [rsi+180h]
0x180054777  mov     rcx, rbx
0x18005477a  call    ?fileExists@IO@Pal@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FileLocation@2@@Z; Pal::IO::fileExists(std::wstring const &,Pal::FileLocation)
0x18005477f  test    al, al
0x180054781  jnz     short loc_18005479D
0x180054783  mov     rcx, [rsp+100h+var_D8]
0x180054788  mov     rcx, [rcx]; hEvent
0x18005478b  call    cs:__imp_SetEvent
0x180054791  mov     dword ptr [r14], 1
0x180054798  jmp     loc_180054A0B
0x18005479d  mov     r8d, [rsi+180h]
0x1800547a4  mov     rdx, rbx
0x1800547a7  lea     rcx, [rbp+57h+var_D0]
0x1800547ab  call    ?beginReadFile@IO@Pal@@SA?AV?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@W4FileLocation@2@@Z; Pal::IO::beginReadFile(std::wstring const &,Pal::FileLocation)
0x1800547b0  mov     rbx, [rax]
0x1800547b3  mov     rdi, [rax+8]
0x1800547b7  mov     qword ptr [rax], 0
0x1800547be  mov     qword ptr [rax+8], 0
0x1800547c6  mov     qword ptr [rbp+57h+var_A0], rbx
0x1800547ca  mov     qword ptr [rbp+57h+var_A0+8], rdi
0x1800547ce  mov     rcx, [rbp+57h+var_C8]; this
0x1800547d2  test    rcx, rcx
0x1800547d5  jz      short loc_1800547DC
0x1800547d7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800547dc  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8PersistentMapsCache@MapControl@@EAAXAEBV?$AsyncOperation@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@AEAVManualResetEvent@6@@ZPEAV34@AEBU?$_Ph@$00@2@V?$reference_wrapper@VManualResetEvent@Pal@@@2@@std@@XAEAV?$AsyncOperation@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::PersistentMapsCache::*)(Pal::AsyncOperation<std::shared_ptr<std::vector<uchar>>> const &,Pal::ManualResetEvent &),MapControl::PersistentMapsCache *,std::_Ph<1> const &,std::reference_wrapper<Pal::ManualResetEvent>>,void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar>>> &>::`vftable'
0x1800547e3  mov     qword ptr [rbp+57h+var_80], rax
0x1800547e7  lea     rax, ?indexWriteDone@PersistentMapsCache@MapControl@@AEAAXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@4@@Z; MapControl::PersistentMapsCache::indexWriteDone(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *)
0x1800547ee  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800547f2  lea     rax, [rsp+100h+var_D8]
0x1800547f7  mov     qword ptr [rbp+57h+var_70], rax
0x1800547fb  mov     al, [rsp+100h+var_E0]
0x1800547ff  mov     byte ptr [rbp+57h+var_70+8], al
0x180054802  mov     [rbp+57h+var_60], rsi
0x180054806  lea     rax, [rbp+57h+var_80]
0x18005480a  mov     [rbp+57h+var_48], rax
0x18005480e  lea     rdx, [rbp+57h+var_80]
0x180054812  mov     rcx, rbx
0x180054815  call    ?setCallback@?$AsyncOperation@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@QEAAXAEBV?$function@$$A6AXAEAV?$AsyncOperation@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@Z@std@@@Z; Pal::AsyncOperation<std::shared_ptr<std::vector<uchar>>>::setCallback(std::function<void (Pal::AsyncOperation<std::shared_ptr<std::vector<uchar>>> &)> const &)
0x18005481a  nop
0x18005481b  lea     rcx, [rbp+57h+var_80]
0x18005481f  call    ?_Tidy@?$_Func_class@XAEAV?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@IEAAXXZ; std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>> &>::_Tidy(void)
0x180054824  lea     rcx, [rsp+100h+var_D8]; this
0x180054829  call    ?wait@ManualResetEvent@Pal@@QEAAXXZ; Pal::ManualResetEvent::wait(void)
0x18005482e  cmp     byte ptr [rbx+96h], 0
0x180054835  jnz     short loc_180054884
0x180054837  cmp     r12d, 1
0x18005483b  jnz     short loc_18005484C
0x18005483d  mov     rax, [rsi]
0x180054840  mov     rcx, rsi
0x180054843  mov     rax, [rax+40h]
0x180054847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005484c  lea     rdx, [rbp+57h+var_D0]
0x180054850  mov     rcx, rbx
0x180054853  call    ?getStatusCode@UntypedAsyncOperation@Pal@@QEBA?AVStatusCode@Core@@XZ; Pal::UntypedAsyncOperation::getStatusCode(void)
0x180054858  mov     ecx, 2800000h
0x18005485d  mov     edx, 800002h
0x180054862  cmp     dword ptr [rax], 1800000h
0x180054868  cmovnz  ecx, edx
0x18005486b  mov     [r14], ecx
0x18005486e  test    rdi, rdi
0x180054871  jz      loc_180054798
0x180054877  mov     rcx, rdi; this
0x18005487a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005487f  jmp     loc_180054798
0x180054884  mov     rcx, rbx
0x180054887  call    ?getResults@?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@QEBAAEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@XZ; Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>>::getResults(void)
0x18005488c  mov     rdx, rax
0x18005488f  lea     rcx, [rbp+57h+var_C0]
0x180054893  call    ??4?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<MapControl::OdvsChunkIndex>::operator=(std::shared_ptr<MapControl::OdvsChunkIndex> const &)
0x180054898  mov     rax, [rbp+57h+var_C0]
0x18005489c  mov     r13, [rax]
0x18005489f  test    r13, r13
0x1800548a2  jz      loc_1800549D2
0x1800548a8  mov     rbx, [rax+8]
0x1800548ac  sub     rbx, r13
0x1800548af  cmp     rbx, 8
0x1800548b3  jb      loc_1800549D2
0x1800548b9  mov     [rbp+57h+var_D0], 0
0x1800548c1  mov     r8d, 8; MaxCount
0x1800548c7  lea     r15, Str2; "MCI 1.00"
0x1800548ce  mov     rdx, r15; Str2
0x1800548d1  mov     rcx, r13; Str1
0x1800548d4  call    strncmp_0
0x1800548d9  test    eax, eax
0x1800548db  jnz     short loc_1800548EB
0x1800548dd  cmp     rbx, 1Ch
0x1800548e1  jb      loc_1800549D2
0x1800548e7  mov     [rbp+57h+var_D0], r15
0x1800548eb  mov     r8d, 8; MaxCount
0x1800548f1  lea     r15, aMci101; "MCI 1.01"
0x1800548f8  mov     rdx, r15; Str2
0x1800548fb  mov     rcx, r13; Str1
0x1800548fe  call    strncmp_0
0x180054903  test    eax, eax
0x180054905  cmovnz  r15, [rbp+57h+var_D0]
0x18005490a  mov     r8d, 8; MaxCount
0x180054910  lea     rdx, Buf2; "MCI 1.02"
0x180054917  mov     rcx, r13; Str1
0x18005491a  call    strncmp_0
0x18005491f  test    eax, eax
0x180054921  jnz     short loc_18005492C
0x180054923  lea     r15, Buf2; "MCI 1.02"
0x18005492a  jmp     short loc_180054935
0x18005492c  test    r15, r15
0x18005492f  jz      loc_1800549D2
0x180054935  mov     r8d, 8; Size
0x18005493b  lea     rdx, Buf2; "MCI 1.02"
0x180054942  mov     rcx, r15; Buf1
0x180054945  call    memcmp_0
0x18005494a  test    eax, eax
0x18005494c  jnz     loc_1800549D2
0x180054952  add     r13, 8
0x180054956  lea     r15, [rbx-8]
0x18005495a  lea     rbx, [rsi+0B0h]
0x180054961  mov     [rbp+57h+var_D0], rbx
0x180054965  mov     rcx, rbx; lpCriticalSection
0x180054968  call    cs:__imp_EnterCriticalSection
0x18005496e  nop
0x18005496f  jmp     short loc_1800549BA
0x180054971  movups  xmm0, xmmword ptr [r13+0]
0x180054976  movups  [rbp+57h+var_80], xmm0
0x18005497a  movups  xmm1, xmmword ptr [r13+10h]
0x18005497f  movups  [rbp+57h+var_70], xmm1
0x180054983  lea     r13, [r13+20h]
0x180054987  sub     r15, 20h ; ' '
0x18005498b  lea     rdx, [rbp+57h+var_80]
0x18005498f  lea     rcx, [rbp+57h+var_90]
0x180054993  call    ??$make_shared@TIndexEntry@PersistentMapsCache@MapControl@@AEAT123@@std@@YA?AV?$shared_ptr@TIndexEntry@PersistentMapsCache@MapControl@@@0@AEATIndexEntry@PersistentMapsCache@MapControl@@@Z; std::make_shared<MapControl::PersistentMapsCache::IndexEntry,MapControl::PersistentMapsCache::IndexEntry &>(MapControl::PersistentMapsCache::IndexEntry &)
0x180054998  nop
0x180054999  xor     r9d, r9d
0x18005499c  mov     r8, rax
0x18005499f  lea     rdx, [rbp+57h+var_80]
0x1800549a3  mov     rcx, rsi; this
0x1800549a6  call    ?addPairToIndexMap@PersistentMapsCache@MapControl@@AEAAXAEBUPersistentDataKey@2@AEBV?$shared_ptr@TIndexEntry@PersistentMapsCache@MapControl@@@std@@W4LruStamp@12@@Z; MapControl::PersistentMapsCache::addPairToIndexMap(MapControl::PersistentDataKey const &,std::shared_ptr<MapControl::PersistentMapsCache::IndexEntry> const &,MapControl::PersistentMapsCache::LruStamp)
0x1800549ab  nop
0x1800549ac  mov     rcx, [rbp+57h+var_88]; this
0x1800549b0  test    rcx, rcx
0x1800549b3  jz      short loc_1800549BA
0x1800549b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800549ba  cmp     r15, 20h ; ' '
0x1800549be  jnb     short loc_180054971
0x1800549c0  mov     rcx, rbx; lpCriticalSection
0x1800549c3  call    cs:__imp_LeaveCriticalSection
0x1800549c9  mov     dword ptr [r14], 1
0x1800549d0  jmp     short loc_1800549EE
0x1800549d2  cmp     r12d, 1
0x1800549d6  jnz     short loc_1800549E7
0x1800549d8  mov     rax, [rsi]
0x1800549db  mov     rcx, rsi
0x1800549de  mov     rax, [rax+40h]
0x1800549e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549e7  mov     dword ptr [r14], 2800000h
0x1800549ee  test    rdi, rdi
0x1800549f1  jz      short loc_1800549FC
0x1800549f3  mov     rcx, rdi; this
0x1800549f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800549fb  nop
0x1800549fc  mov     rcx, [rbp+57h+var_C0+8]; this
0x180054a00  test    rcx, rcx
0x180054a03  jz      short loc_180054A0B
0x180054a05  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054a0a  nop
0x180054a0b  lea     rcx, [rsp+100h+var_D8]
0x180054a10  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x180054a15  nop
0x180054a16  lea     rcx, [rbp+57h+var_B0]; this
0x180054a1a  call    ??1ScopedPerformanceSpan@Pal@@QEAA@XZ; Pal::ScopedPerformanceSpan::~ScopedPerformanceSpan(void)
0x180054a1f  mov     rax, r14
0x180054a22  mov     rcx, [rbp+57h+var_40]
0x180054a26  xor     rcx, rsp; StackCookie
0x180054a29  call    __security_check_cookie
0x180054a2e  mov     rbx, [rsp+100h+arg_10]
0x180054a36  add     rsp, 0D0h
0x180054a3d  pop     r15
0x180054a3f  pop     r14
0x180054a41  pop     r13
0x180054a43  pop     r12
0x180054a45  pop     rdi
0x180054a46  pop     rsi
0x180054a47  pop     rbp
0x180054a48  retn
```
