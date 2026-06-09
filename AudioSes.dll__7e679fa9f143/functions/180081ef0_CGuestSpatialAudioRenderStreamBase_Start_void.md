# CGuestSpatialAudioRenderStreamBase::Start(void)

- ea: `0x180081ef0`
- end: `0x180082118`
- name: `?Start@CGuestSpatialAudioRenderStreamBase@@MEAAJXZ`
- size: `552`
- prototype: `__int64 __fastcall(CGuestSpatialAudioRenderStreamBase *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180102160`

## callees

- `0x180010a90`
- `0x18004cc00`
- `0x18004d8a8`
- `0x18004dab0`
- `0x180081ef0`
- `0x180082120`
- `0x1800821d0`
- `0x1800ae5b8`
- `0x18010c350`
- `0x18010ea9c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180081f16`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180081f16`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180081fe7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180082094`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800820dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180081fe7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180082094`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800820dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081fdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008208a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081fdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008208a`

## pseudocode

```c
__int64 __fastcall CGuestSpatialAudioRenderStreamBase::Start(CSpatialAudioRenderStreamBase **this)
{
  int started; // edi
  int v3; // r8d
  __int64 v4; // rdx
  int v5; // edx
  int v6; // esi
  void *v7; // rcx
  double v8; // xmm0_8
  CSpatialAudioRenderStreamBase *v9; // rcx
  void *v11; // rcx
  void *v12; // rcx
  double v13; // xmm0_8
  CSpatialAudioRenderStreamBase *v14; // rcx
  double TimeSec; // xmm0_8
  CSpatialAudioRenderStreamBase *v16; // rcx
  int v17; // [rsp+20h] [rbp-40h]
  int v18; // [rsp+20h] [rbp-40h]
  __int64 v19; // [rsp+30h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-28h] BYREF
  LARGE_INTEGER Frequency; // [rsp+40h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+50h] [rbp-10h] BYREF
  char v24; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  double v26; // [rsp+80h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+28h] BYREF

  PerformanceCount.QuadPart = 0;
  v19 = 0;
  QueryPerformanceFrequency(&Frequency);
  CQPCStopWatch::Start((CQPCStopWatch *)&v19);
  LOBYTE(v26) = 0;
  started = CGuestSpatialAudioRenderStreamBase::PreStartStream((CGuestSpatialAudioRenderStreamBase *)this, (bool *)&v26);
  if ( started < 0 )
  {
    v4 = 158;
    goto LABEL_16;
  }
  if ( !LOBYTE(v26) )
  {
LABEL_17:
    QueryPerformanceCounter(&PerformanceCount);
    TimeSec = CQPCStopWatch::GetTimeSec((CQPCStopWatch *)&v19);
    v16 = this[61];
    v26 = TimeSec;
    CSpatialAudioRenderStreamBase::LogStart(v16, started, started, &v26);
    return (unsigned int)started;
  }
  started = CSpatialAudioRenderStreamBase::StartStreamPhaseOne(this[61]);
  if ( started < 0 )
  {
    v4 = 161;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)started,
      v17);
    goto LABEL_17;
  }
  v5 = *((_DWORD *)this + 14);
  p_pv = &pv;
  pv = 0;
  LOBYTE(v3) = 0;
  v26 = 0.0;
  v23 = 0;
  v24 = 1;
  v6 = CGuestXvmAudioObject::SendAndValidateResponse<XvmStart>((int)this + 8, v5, v3, (unsigned int)&v23, (__int64)&v26);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v6 >= 0 )
  {
    started = *((_DWORD *)pv + 1);
    if ( started < 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this[61] + 214) + 40LL))(*((_QWORD *)this[61] + 214));
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
        (const char *)(unsigned int)started,
        v18);
      v11 = pv;
      pv = 0;
      if ( v11 )
        CoTaskMemFree(v11);
      goto LABEL_17;
    }
    CSpatialAudioRenderStreamBase::PostStartStream(this[61]);
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    QueryPerformanceCounter(&PerformanceCount);
    v13 = CQPCStopWatch::GetTimeSec((CQPCStopWatch *)&v19);
    v14 = this[61];
    v26 = v13;
    CSpatialAudioRenderStreamBase::LogStart(v14, started, started, &v26);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v6,
      v18);
    v7 = pv;
    pv = 0;
    if ( v7 )
      CoTaskMemFree(v7);
    QueryPerformanceCounter(&PerformanceCount);
    v8 = CQPCStopWatch::GetTimeSec((CQPCStopWatch *)&v19);
    v9 = this[61];
    v26 = v8;
    CSpatialAudioRenderStreamBase::LogStart(v9, started, started, &v26);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180081ef0  mov     [rsp-18h+arg_10], rbx
0x180081ef5  push    rbp
0x180081ef6  push    rsi
0x180081ef7  push    rdi
0x180081ef8  mov     rbp, rsp
0x180081efb  sub     rsp, 60h
0x180081eff  mov     rbx, rcx
0x180081f02  mov     qword ptr [rbp+PerformanceCount], 0
0x180081f0a  lea     rcx, [rbp+Frequency]; lpFrequency
0x180081f0e  mov     [rbp+var_30], 0
0x180081f16  call    cs:__imp_QueryPerformanceFrequency
0x180081f1c  lea     rcx, [rbp+var_30]; this
0x180081f20  call    ?Start@CQPCStopWatch@@QEAAHXZ; CQPCStopWatch::Start(void)
0x180081f25  lea     rdx, [rbp+arg_0]; bool *
0x180081f29  mov     byte ptr [rbp+arg_0], 0
0x180081f2d  mov     rcx, rbx; this
0x180081f30  call    ?PreStartStream@CGuestSpatialAudioRenderStreamBase@@IEAAJAEA_N@Z; CGuestSpatialAudioRenderStreamBase::PreStartStream(bool &)
0x180081f35  mov     edi, eax
0x180081f37  test    eax, eax
0x180081f39  js      loc_1800820C1
0x180081f3f  cmp     byte ptr [rbp+arg_0], 0
0x180081f43  jz      loc_1800820D9
0x180081f49  mov     rcx, [rbx+1E8h]; this
0x180081f50  call    ?StartStreamPhaseOne@CSpatialAudioRenderStreamBase@@QEAAJXZ; CSpatialAudioRenderStreamBase::StartStreamPhaseOne(void)
0x180081f55  mov     edi, eax
0x180081f57  test    eax, eax
0x180081f59  jns     short loc_180081F65
0x180081f5b  mov     edx, 0A1h
0x180081f60  jmp     loc_1800820C6
0x180081f65  mov     edx, [rbx+38h]
0x180081f68  lea     rax, [rbp+pv]
0x180081f6c  mov     [rbp+var_18], rax
0x180081f70  lea     rcx, [rbx+8]
0x180081f74  lea     rax, [rbp+arg_0]
0x180081f78  mov     [rbp+pv], 0
0x180081f80  xor     r8b, r8b
0x180081f83  mov     qword ptr [rsp+60h+var_40], rax; int
0x180081f88  lea     r9, [rbp+var_10]
0x180081f8c  mov     [rbp+arg_0], 0
0x180081f94  mov     [rbp+var_10], 0
0x180081f9c  mov     [rbp+var_8], 1
0x180081fa0  call    ??$SendAndValidateResponse@UXvmStart@@@CGuestXvmAudioObject@@QEAAJIUXvmStart@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmStart>(uint,XvmStart,XvmMessage * *,XvmStart * *)
0x180081fa5  lea     rcx, [rbp+var_18]
0x180081fa9  mov     esi, eax
0x180081fab  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180081fb0  test    esi, esi
0x180081fb2  jns     short loc_180082017
0x180081fb4  mov     rcx, [rbp+18h]; this
0x180081fb8  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180081fbf  mov     r9d, esi; char *
0x180081fc2  mov     edx, 0A6h; void *
0x180081fc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081fcc  mov     rcx, [rbp+pv]; pv
0x180081fd0  mov     [rbp+pv], 0
0x180081fd8  test    rcx, rcx
0x180081fdb  jz      short loc_180081FE3
0x180081fdd  call    cs:__imp_CoTaskMemFree
0x180081fe3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180081fe7  call    cs:__imp_QueryPerformanceCounter
0x180081fed  lea     rcx, [rbp+var_30]; this
0x180081ff1  call    ?GetTimeSec@CQPCStopWatch@@QEAANXZ; CQPCStopWatch::GetTimeSec(void)
0x180081ff6  mov     rcx, [rbx+1E8h]; this
0x180081ffd  lea     r9, [rbp+arg_0]; double *
0x180082001  mov     r8d, edi; int
0x180082004  movsd   [rbp+arg_0], xmm0
0x180082009  mov     edx, edi; int
0x18008200b  call    ?LogStart@CSpatialAudioRenderStreamBase@@QEAAXJJAEBN@Z; CSpatialAudioRenderStreamBase::LogStart(long,long,double const &)
0x180082010  mov     eax, esi
0x180082012  jmp     loc_180082108
0x180082017  mov     rax, [rbp+pv]
0x18008201b  mov     edi, [rax+4]
0x18008201e  test    edi, edi
0x180082020  jns     short loc_18008206D
0x180082022  mov     rax, [rbx+1E8h]
0x180082029  mov     rcx, [rax+6B0h]
0x180082030  mov     rax, [rcx]
0x180082033  mov     rax, [rax+28h]
0x180082037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008203c  mov     rcx, [rbp+18h]; this
0x180082040  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180082047  mov     r9d, edi; char *
0x18008204a  mov     edx, 0ACh; void *
0x18008204f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082054  mov     rcx, [rbp+pv]; pv
0x180082058  mov     [rbp+pv], 0
0x180082060  test    rcx, rcx
0x180082063  jz      short loc_1800820D9
0x180082065  call    cs:__imp_CoTaskMemFree
0x18008206b  jmp     short loc_1800820D9
0x18008206d  mov     rcx, [rbx+1E8h]; this
0x180082074  call    ?PostStartStream@CSpatialAudioRenderStreamBase@@QEAAXXZ; CSpatialAudioRenderStreamBase::PostStartStream(void)
0x180082079  mov     rcx, [rbp+pv]; pv
0x18008207d  mov     [rbp+pv], 0
0x180082085  test    rcx, rcx
0x180082088  jz      short loc_180082090
0x18008208a  call    cs:__imp_CoTaskMemFree
0x180082090  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180082094  call    cs:__imp_QueryPerformanceCounter
0x18008209a  lea     rcx, [rbp+var_30]; this
0x18008209e  call    ?GetTimeSec@CQPCStopWatch@@QEAANXZ; CQPCStopWatch::GetTimeSec(void)
0x1800820a3  mov     rcx, [rbx+1E8h]; this
0x1800820aa  lea     r9, [rbp+arg_0]; double *
0x1800820ae  mov     r8d, edi; int
0x1800820b1  movsd   [rbp+arg_0], xmm0
0x1800820b6  mov     edx, edi; int
0x1800820b8  call    ?LogStart@CSpatialAudioRenderStreamBase@@QEAAXJJAEBN@Z; CSpatialAudioRenderStreamBase::LogStart(long,long,double const &)
0x1800820bd  xor     eax, eax
0x1800820bf  jmp     short loc_180082108
0x1800820c1  mov     edx, 9Eh; void *
0x1800820c6  mov     rcx, [rbp+18h]; this
0x1800820ca  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x1800820d1  mov     r9d, edi; char *
0x1800820d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800820d9  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800820dd  call    cs:__imp_QueryPerformanceCounter
0x1800820e3  lea     rcx, [rbp+var_30]; this
0x1800820e7  call    ?GetTimeSec@CQPCStopWatch@@QEAANXZ; CQPCStopWatch::GetTimeSec(void)
0x1800820ec  mov     rcx, [rbx+1E8h]; this
0x1800820f3  lea     r9, [rbp+arg_0]; double *
0x1800820f7  mov     r8d, edi; int
0x1800820fa  movsd   [rbp+arg_0], xmm0
0x1800820ff  mov     edx, edi; int
0x180082101  call    ?LogStart@CSpatialAudioRenderStreamBase@@QEAAXJJAEBN@Z; CSpatialAudioRenderStreamBase::LogStart(long,long,double const &)
0x180082106  mov     eax, edi
0x180082108  mov     rbx, [rsp+60h+arg_10]
0x180082110  add     rsp, 60h
0x180082114  pop     rdi
0x180082115  pop     rsi
0x180082116  pop     rbp
0x180082117  retn
```
