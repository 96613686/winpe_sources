# CAPOWrapperClient::InitializeSystemEffectsInterfaceOOP(IMMDevice *,_GUID *,_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioSystemEffects2 * *)

- ea: `0x18001bea0`
- end: `0x18001c164`
- name: `?InitializeSystemEffectsInterfaceOOP@CAPOWrapperClient@@UEAAJPEAUIMMDevice@@PEAU_GUID@@U3@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUIAudioSystemEffects2@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(CAPOWrapperClient *__hidden this, struct IMMDevice *, struct _GUID *, struct _GUID *, int, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct IAudioSystemEffects2 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800126bc`
- `0x18001bea0`
- `0x18001c29c`
- `0x18001c5bc`
- `0x1800cf8c0`
- `0x1800cfd40`
- `0x1800d5dbc`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001bf00`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001bf00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c0e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c0e2`

## string_xrefs

- `0x18001c012`: `avcore\audiocore\server\audiosrv\dll\apowrapperclient.cpp`
- `0x18001c04f`: `avcore\audiocore\server\audiosrv\dll\apowrapperclient.cpp`
- `0x18001c07b`: `avcore\audiocore\server\audiosrv\dll\apowrapperclient.cpp`
- `0x18001c0c4`: `avcore\audiocore\server\audiosrv\dll\apowrapperclient.cpp`

## pseudocode

```c
__int64 __fastcall CAPOWrapperClient::InitializeSystemEffectsInterfaceOOP(
        CAPOWrapperClient *this,
        struct IMMDevice *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        int a5,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a6,
        struct IAudioSystemEffects2 **a7)
{
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v12; // eax
  unsigned int v13; // edi
  __int64 (__fastcall *v14)(__int64, LPVOID, struct _GUID *, __int128 *); // rax
  __int64 v15; // rcx
  int v16; // eax
  void *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL fPending; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID Context; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v26; // [rsp+70h] [rbp-90h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`AudioSrvTelemetryProvider::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    *(_QWORD *)&v26 = &`AudioSrvTelemetryProvider::Instance'::`2'::wrapper;
    Context = &qword_1801D4440;
    qword_1801D4440 = (__int64)&AudioSrvTelemetryProvider::`vftable';
    qword_1801D4448 = 0;
    byte_1801D4450 = 0;
    dword_1801D4454 = 0;
    qword_1801D4458 = (__int64)&`AudioSrvTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b4cb8953ddd9016186cd5ae31274160b_::_lambda_invoker_cdecl_);
    DWORD2(v26) = 0;
    wil::details::static_lazy<AudioSrvTelemetryProvider>::Completer::~Completer(&v26);
  }
  CPerfTracker::CPerfTracker(
    &PerformanceCount,
    *((const struct _tlgProvider_t **)Context + 1),
    "SystemEffect_Initialize",
    (const char *const)this + 132);
  if ( !a2 )
  {
    v19 = 129;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\apowrapperclient.cpp",
      (const char *)0x80070057LL,
      v22);
    CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
    return 2147942487LL;
  }
  if ( !*((_QWORD *)this + 11) )
  {
    v19 = 130;
    goto LABEL_16;
  }
  lpVtbl = a2->lpVtbl;
  pv = 0;
  v12 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))lpVtbl->GetId)(a2, &pv);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\apowrapperclient.cpp",
      (const char *)(unsigned int)v12,
      v22);
    v18 = pv;
    if ( !pv )
      goto LABEL_14;
    goto LABEL_13;
  }
  v14 = *(__int64 (__fastcall **)(__int64, LPVOID, struct _GUID *, __int128 *))(**((_QWORD **)this + 11) + 32LL);
  v15 = *((_QWORD *)this + 11);
  v26 = (__int128)*a4;
  v16 = v14(v15, pv, a3, &v26);
  v13 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\apowrapperclient.cpp",
      (const char *)(unsigned int)v16,
      a5);
    v18 = pv;
    if ( !pv )
    {
LABEL_14:
      CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
      return v13;
    }
LABEL_13:
    CoTaskMemFree(v18);
    goto LABEL_14;
  }
  if ( a7
    && (v20 = (**(__int64 (__fastcall ***)(CAPOWrapperClient *, GUID *, struct IAudioSystemEffects2 **))this)(
                this,
                &GUID_bafe99d2_7436_44ce_9e0e_4d89afbfff56,
                a7),
        v21 = v20,
        v20 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\apowrapperclient.cpp",
      (const char *)(unsigned int)v20,
      a5);
    if ( pv )
      CoTaskMemFree(pv);
    CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
    return v21;
  }
  else
  {
    if ( pv )
      CoTaskMemFree(pv);
    CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
    return 0;
  }
}

```

## disassembly

```asm
0x18001bea0  push    rbp
0x18001bea2  push    rbx
0x18001bea3  push    rsi
0x18001bea4  push    rdi
0x18001bea5  push    r12
0x18001bea7  push    r13
0x18001bea9  push    r14
0x18001beab  push    r15
0x18001bead  lea     rbp, [rsp-88h]
0x18001beb5  sub     rsp, 188h
0x18001bebc  mov     rax, cs:__security_cookie
0x18001bec3  xor     rax, rsp
0x18001bec6  mov     [rbp+0C0h+var_50], rax
0x18001beca  mov     rsi, [rbp+0C0h+arg_30]
0x18001bed1  lea     r14, ?wrapper@?1??Instance@AudioSrvTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VAudioSrvTelemetryProvider@@@details@wil@@A; wil::details::static_lazy<AudioSrvTelemetryProvider> `AudioSrvTelemetryProvider::Instance(void)'::`2'::wrapper
0x18001bed8  mov     r12, r9
0x18001bedb  mov     r15, r8
0x18001bede  mov     rdi, rdx
0x18001bee1  lea     r9, [rsp+1C0h+Context]; lpContext
0x18001bee6  mov     rbx, rcx
0x18001bee9  lea     r8, [rsp+1C0h+fPending]; fPending
0x18001beee  xor     r13d, r13d
0x18001bef1  mov     rcx, r14; lpInitOnce
0x18001bef4  xor     edx, edx; dwFlags
0x18001bef6  mov     [rsp+1C0h+Context], r13
0x18001befb  mov     [rsp+1C0h+fPending], r13d
0x18001bf00  call    cs:__imp_InitOnceBeginInitialize
0x18001bf06  test    eax, eax
0x18001bf08  jz      short loc_18001BF15
0x18001bf0a  cmp     [rsp+1C0h+fPending], r13d
0x18001bf0f  jnz     loc_18001C0F8
0x18001bf15  mov     rdx, [rsp+1C0h+Context]
0x18001bf1a  lea     r9, [rbx+84h]; char *
0x18001bf21  lea     r8, aSystemeffectIn; "SystemEffect_Initialize"
0x18001bf28  lea     rcx, [rbp+0C0h+PerformanceCount]; lpPerformanceCount
0x18001bf2c  mov     rdx, [rdx+8]; struct _tlgProvider_t *
0x18001bf30  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x18001bf35  test    rdi, rdi
0x18001bf38  jz      loc_18001C043
0x18001bf3e  cmp     [rbx+58h], r13
0x18001bf42  jz      loc_18001C15A
0x18001bf48  mov     rax, [rdi]
0x18001bf4b  lea     rdx, [rsp+1C0h+pv]
0x18001bf50  test    rsi, rsi
0x18001bf53  mov     [rsp+1C0h+pv], r13
0x18001bf58  mov     r14d, r13d
0x18001bf5b  mov     rcx, rdi
0x18001bf5e  setnz   r14b
0x18001bf62  mov     rax, [rax+28h]
0x18001bf66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf6b  mov     edi, eax
0x18001bf6d  test    eax, eax
0x18001bf6f  js      loc_18001C074
0x18001bf75  mov     r10, [rbx+58h]
0x18001bf79  lea     rcx, [rbx+68h]
0x18001bf7d  movups  xmm0, xmmword ptr [r12]
0x18001bf82  mov     rdx, [rsp+1C0h+pv]
0x18001bf87  lea     r9, [rsp+1C0h+var_150]
0x18001bf8c  mov     [rsp+1C0h+var_188], rcx
0x18001bf91  mov     r8, r15
0x18001bf94  mov     ecx, [rbp+0C0h+arg_28]
0x18001bf9a  mov     rax, [r10]
0x18001bf9d  mov     [rsp+1C0h+var_190], r14d
0x18001bfa2  mov     [rsp+1C0h+var_198], ecx
0x18001bfa6  mov     ecx, [rbp+0C0h+arg_20]
0x18001bfac  mov     rax, [rax+20h]
0x18001bfb0  mov     [rsp+1C0h+var_1A0], ecx; int
0x18001bfb4  mov     rcx, r10
0x18001bfb7  movaps  [rsp+1C0h+var_150], xmm0
0x18001bfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfc1  mov     edi, eax
0x18001bfc3  test    eax, eax
0x18001bfc5  js      short loc_18001C00B
0x18001bfc7  test    rsi, rsi
0x18001bfca  jnz     loc_18001C09B
0x18001bfd0  mov     rcx, [rsp+1C0h+pv]; pv
0x18001bfd5  test    rcx, rcx
0x18001bfd8  jz      short loc_18001BFE0
0x18001bfda  call    cs:__imp_CoTaskMemFree
0x18001bfe0  lea     rcx, [rbp+0C0h+PerformanceCount]; this
0x18001bfe4  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x18001bfe9  xor     eax, eax
0x18001bfeb  mov     rcx, [rbp+0C0h+var_50]
0x18001bfef  xor     rcx, rsp; StackCookie
0x18001bff2  call    __security_check_cookie
0x18001bff7  add     rsp, 188h
0x18001bffe  pop     r15
0x18001c000  pop     r14
0x18001c002  pop     r13
0x18001c004  pop     r12
0x18001c006  pop     rdi
0x18001c007  pop     rsi
0x18001c008  pop     rbx
0x18001c009  pop     rbp
0x18001c00a  retn
0x18001c00b  mov     rcx, [rbp+0C8h]; this
0x18001c012  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001c019  mov     r9d, edi; char *
0x18001c01c  mov     edx, 89h; void *
0x18001c021  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c026  mov     rcx, [rsp+1C0h+pv]; pv
0x18001c02b  test    rcx, rcx
0x18001c02e  jz      short loc_18001C036
0x18001c030  call    cs:__imp_CoTaskMemFree
0x18001c036  lea     rcx, [rbp+0C0h+PerformanceCount]; this
0x18001c03a  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x18001c03f  mov     eax, edi
0x18001c041  jmp     short loc_18001BFEB
0x18001c043  mov     edx, 81h; void *
0x18001c048  mov     rcx, [rbp+0C8h]; this
0x18001c04f  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001c056  mov     r9d, 80070057h; char *
0x18001c05c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c061  lea     rcx, [rbp+0C0h+PerformanceCount]; this
0x18001c065  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x18001c06a  mov     eax, 80070057h
0x18001c06f  jmp     loc_18001BFEB
0x18001c074  mov     rcx, [rbp+0C8h]; this
0x18001c07b  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001c082  mov     r9d, edi; char *
0x18001c085  mov     edx, 87h; void *
0x18001c08a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c08f  mov     rcx, [rsp+1C0h+pv]
0x18001c094  test    rcx, rcx
0x18001c097  jz      short loc_18001C036
0x18001c099  jmp     short loc_18001C030
0x18001c09b  mov     rax, [rbx]
0x18001c09e  lea     rdx, _GUID_bafe99d2_7436_44ce_9e0e_4d89afbfff56
0x18001c0a5  mov     r8, rsi
0x18001c0a8  mov     rcx, rbx
0x18001c0ab  mov     rax, [rax]
0x18001c0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0b3  mov     ebx, eax
0x18001c0b5  test    eax, eax
0x18001c0b7  jns     loc_18001BFD0
0x18001c0bd  mov     rcx, [rbp+0C8h]; this
0x18001c0c4  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001c0cb  mov     r9d, eax; char *
0x18001c0ce  mov     edx, 8Dh; void *
0x18001c0d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0d8  mov     rcx, [rsp+1C0h+pv]; pv
0x18001c0dd  test    rcx, rcx
0x18001c0e0  jz      short loc_18001C0E8
0x18001c0e2  call    cs:__imp_CoTaskMemFree
0x18001c0e8  lea     rcx, [rbp+0C0h+PerformanceCount]; this
0x18001c0ec  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x18001c0f1  mov     eax, ebx
0x18001c0f3  jmp     loc_18001BFEB
0x18001c0f8  lea     rax, qword_1801D4440
0x18001c0ff  mov     qword ptr [rsp+1C0h+var_150], r14
0x18001c104  mov     [rsp+1C0h+Context], rax
0x18001c109  lea     rax, ??_7AudioSrvTelemetryProvider@@6B@; const AudioSrvTelemetryProvider::`vftable'
0x18001c110  mov     cs:qword_1801D4440, rax
0x18001c117  mov     cs:qword_1801D4448, r13
0x18001c11e  mov     cs:byte_1801D4450, r13b
0x18001c125  mov     cs:dword_1801D4454, r13d
0x18001c12c  lea     rax, ?__hInner@?1???0StaticHandle@AudioSrvTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AudioSrvTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001c133  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b4cb8953ddd9016186cd5ae31274160b_@@CA@XZ; void (__cdecl *)()
0x18001c13a  mov     cs:qword_1801D4458, rax
0x18001c141  call    atexit
0x18001c146  lea     rcx, [rsp+1C0h+var_150]
0x18001c14b  mov     dword ptr [rsp+1C0h+var_150+8], r13d
0x18001c150  call    ??1Completer@?$static_lazy@VAudioSrvTelemetryProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<AudioSrvTelemetryProvider>::Completer::~Completer(void)
0x18001c155  jmp     loc_18001BF15
0x18001c15a  mov     edx, 82h
0x18001c15f  jmp     loc_18001C048
```
