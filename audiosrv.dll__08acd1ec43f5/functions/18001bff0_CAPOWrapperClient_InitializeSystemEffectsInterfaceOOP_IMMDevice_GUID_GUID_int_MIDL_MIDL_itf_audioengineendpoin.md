# CAPOWrapperClient::InitializeSystemEffectsInterfaceOOP(IMMDevice *,_GUID *,_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioSystemEffects2 * *)

- ea: `0x18001bff0`
- end: `0x18001c2b4`
- name: `?InitializeSystemEffectsInterfaceOOP@CAPOWrapperClient@@UEAAJPEAUIMMDevice@@PEAU_GUID@@U3@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUIAudioSystemEffects2@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(CAPOWrapperClient *__hidden this, struct IMMDevice *, struct _GUID *, struct _GUID *, int, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct IAudioSystemEffects2 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001280c`
- `0x18001bff0`
- `0x18001c3ec`
- `0x18001c70c`
- `0x1800cd8d0`
- `0x1800cdd50`
- `0x1800d3dcc`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c050`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c12a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c232`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c12a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c232`

## string_xrefs

- `0x18001c162`: `avcore\audiocore\server\audiosrv\dll\apowrapperclient.cpp`
- `0x18001c19f`: `avcore\audiocore\server\audiosrv\dll\apowrapperclient.cpp`
- `0x18001c1cb`: `avcore\audiocore\server\audiosrv\dll\apowrapperclient.cpp`
- `0x18001c214`: `avcore\audiocore\server\audiosrv\dll\apowrapperclient.cpp`

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
    Context = &qword_1801D5430;
    qword_1801D5430 = (__int64)&AudioSrvTelemetryProvider::`vftable';
    qword_1801D5438 = 0;
    byte_1801D5440 = 0;
    dword_1801D5444 = 0;
    qword_1801D5448 = (__int64)&`AudioSrvTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
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
0x18001bff0  push    rbp
0x18001bff2  push    rbx
0x18001bff3  push    rsi
0x18001bff4  push    rdi
0x18001bff5  push    r12
0x18001bff7  push    r13
0x18001bff9  push    r14
0x18001bffb  push    r15
0x18001bffd  lea     rbp, [rsp-88h]
0x18001c005  sub     rsp, 188h
0x18001c00c  mov     rax, cs:__security_cookie
0x18001c013  xor     rax, rsp
0x18001c016  mov     [rbp+0C0h+var_50], rax
0x18001c01a  mov     rsi, [rbp+0C0h+arg_30]
0x18001c021  lea     r14, ?wrapper@?1??Instance@AudioSrvTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VAudioSrvTelemetryProvider@@@details@wil@@A; wil::details::static_lazy<AudioSrvTelemetryProvider> `AudioSrvTelemetryProvider::Instance(void)'::`2'::wrapper
0x18001c028  mov     r12, r9
0x18001c02b  mov     r15, r8
0x18001c02e  mov     rdi, rdx
0x18001c031  lea     r9, [rsp+1C0h+Context]; lpContext
0x18001c036  mov     rbx, rcx
0x18001c039  lea     r8, [rsp+1C0h+fPending]; fPending
0x18001c03e  xor     r13d, r13d
0x18001c041  mov     rcx, r14; lpInitOnce
0x18001c044  xor     edx, edx; dwFlags
0x18001c046  mov     [rsp+1C0h+Context], r13
0x18001c04b  mov     [rsp+1C0h+fPending], r13d
0x18001c050  call    cs:__imp_InitOnceBeginInitialize
0x18001c056  test    eax, eax
0x18001c058  jz      short loc_18001C065
0x18001c05a  cmp     [rsp+1C0h+fPending], r13d
0x18001c05f  jnz     loc_18001C248
0x18001c065  mov     rdx, [rsp+1C0h+Context]
0x18001c06a  lea     r9, [rbx+84h]; char *
0x18001c071  lea     r8, aSystemeffectIn; "SystemEffect_Initialize"
0x18001c078  lea     rcx, [rbp+0C0h+PerformanceCount]; lpPerformanceCount
0x18001c07c  mov     rdx, [rdx+8]; struct _tlgProvider_t *
0x18001c080  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x18001c085  test    rdi, rdi
0x18001c088  jz      loc_18001C193
0x18001c08e  cmp     [rbx+58h], r13
0x18001c092  jz      loc_18001C2AA
0x18001c098  mov     rax, [rdi]
0x18001c09b  lea     rdx, [rsp+1C0h+pv]
0x18001c0a0  test    rsi, rsi
0x18001c0a3  mov     [rsp+1C0h+pv], r13
0x18001c0a8  mov     r14d, r13d
0x18001c0ab  mov     rcx, rdi
0x18001c0ae  setnz   r14b
0x18001c0b2  mov     rax, [rax+28h]
0x18001c0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0bb  mov     edi, eax
0x18001c0bd  test    eax, eax
0x18001c0bf  js      loc_18001C1C4
0x18001c0c5  mov     r10, [rbx+58h]
0x18001c0c9  lea     rcx, [rbx+68h]
0x18001c0cd  movups  xmm0, xmmword ptr [r12]
0x18001c0d2  mov     rdx, [rsp+1C0h+pv]
0x18001c0d7  lea     r9, [rsp+1C0h+var_150]
0x18001c0dc  mov     [rsp+1C0h+var_188], rcx
0x18001c0e1  mov     r8, r15
0x18001c0e4  mov     ecx, [rbp+0C0h+arg_28]
0x18001c0ea  mov     rax, [r10]
0x18001c0ed  mov     [rsp+1C0h+var_190], r14d
0x18001c0f2  mov     [rsp+1C0h+var_198], ecx
0x18001c0f6  mov     ecx, [rbp+0C0h+arg_20]
0x18001c0fc  mov     rax, [rax+20h]
0x18001c100  mov     [rsp+1C0h+var_1A0], ecx; int
0x18001c104  mov     rcx, r10
0x18001c107  movaps  [rsp+1C0h+var_150], xmm0
0x18001c10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c111  mov     edi, eax
0x18001c113  test    eax, eax
0x18001c115  js      short loc_18001C15B
0x18001c117  test    rsi, rsi
0x18001c11a  jnz     loc_18001C1EB
0x18001c120  mov     rcx, [rsp+1C0h+pv]; pv
0x18001c125  test    rcx, rcx
0x18001c128  jz      short loc_18001C130
0x18001c12a  call    cs:__imp_CoTaskMemFree
0x18001c130  lea     rcx, [rbp+0C0h+PerformanceCount]; this
0x18001c134  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x18001c139  xor     eax, eax
0x18001c13b  mov     rcx, [rbp+0C0h+var_50]
0x18001c13f  xor     rcx, rsp; StackCookie
0x18001c142  call    __security_check_cookie
0x18001c147  add     rsp, 188h
0x18001c14e  pop     r15
0x18001c150  pop     r14
0x18001c152  pop     r13
0x18001c154  pop     r12
0x18001c156  pop     rdi
0x18001c157  pop     rsi
0x18001c158  pop     rbx
0x18001c159  pop     rbp
0x18001c15a  retn
0x18001c15b  mov     rcx, [rbp+0C8h]; this
0x18001c162  lea     r8, aAvcoreAudiocor_56; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001c169  mov     r9d, edi; char *
0x18001c16c  mov     edx, 89h; void *
0x18001c171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c176  mov     rcx, [rsp+1C0h+pv]; pv
0x18001c17b  test    rcx, rcx
0x18001c17e  jz      short loc_18001C186
0x18001c180  call    cs:__imp_CoTaskMemFree
0x18001c186  lea     rcx, [rbp+0C0h+PerformanceCount]; this
0x18001c18a  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x18001c18f  mov     eax, edi
0x18001c191  jmp     short loc_18001C13B
0x18001c193  mov     edx, 81h; void *
0x18001c198  mov     rcx, [rbp+0C8h]; this
0x18001c19f  lea     r8, aAvcoreAudiocor_56; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001c1a6  mov     r9d, 80070057h; char *
0x18001c1ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c1b1  lea     rcx, [rbp+0C0h+PerformanceCount]; this
0x18001c1b5  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x18001c1ba  mov     eax, 80070057h
0x18001c1bf  jmp     loc_18001C13B
0x18001c1c4  mov     rcx, [rbp+0C8h]; this
0x18001c1cb  lea     r8, aAvcoreAudiocor_56; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001c1d2  mov     r9d, edi; char *
0x18001c1d5  mov     edx, 87h; void *
0x18001c1da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c1df  mov     rcx, [rsp+1C0h+pv]
0x18001c1e4  test    rcx, rcx
0x18001c1e7  jz      short loc_18001C186
0x18001c1e9  jmp     short loc_18001C180
0x18001c1eb  mov     rax, [rbx]
0x18001c1ee  lea     rdx, _GUID_bafe99d2_7436_44ce_9e0e_4d89afbfff56
0x18001c1f5  mov     r8, rsi
0x18001c1f8  mov     rcx, rbx
0x18001c1fb  mov     rax, [rax]
0x18001c1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c203  mov     ebx, eax
0x18001c205  test    eax, eax
0x18001c207  jns     loc_18001C120
0x18001c20d  mov     rcx, [rbp+0C8h]; this
0x18001c214  lea     r8, aAvcoreAudiocor_56; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001c21b  mov     r9d, eax; char *
0x18001c21e  mov     edx, 8Dh; void *
0x18001c223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c228  mov     rcx, [rsp+1C0h+pv]; pv
0x18001c22d  test    rcx, rcx
0x18001c230  jz      short loc_18001C238
0x18001c232  call    cs:__imp_CoTaskMemFree
0x18001c238  lea     rcx, [rbp+0C0h+PerformanceCount]; this
0x18001c23c  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x18001c241  mov     eax, ebx
0x18001c243  jmp     loc_18001C13B
0x18001c248  lea     rax, qword_1801D5430
0x18001c24f  mov     qword ptr [rsp+1C0h+var_150], r14
0x18001c254  mov     [rsp+1C0h+Context], rax
0x18001c259  lea     rax, ??_7AudioSrvTelemetryProvider@@6B@; const AudioSrvTelemetryProvider::`vftable'
0x18001c260  mov     cs:qword_1801D5430, rax
0x18001c267  mov     cs:qword_1801D5438, r13
0x18001c26e  mov     cs:byte_1801D5440, r13b
0x18001c275  mov     cs:dword_1801D5444, r13d
0x18001c27c  lea     rax, ?__hInner@?1???0StaticHandle@AudioSrvTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AudioSrvTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001c283  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b4cb8953ddd9016186cd5ae31274160b_@@CA@XZ; void (__cdecl *)()
0x18001c28a  mov     cs:qword_1801D5448, rax
0x18001c291  call    atexit
0x18001c296  lea     rcx, [rsp+1C0h+var_150]
0x18001c29b  mov     dword ptr [rsp+1C0h+var_150+8], r13d
0x18001c2a0  call    ??1Completer@?$static_lazy@VAudioSrvTelemetryProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<AudioSrvTelemetryProvider>::Completer::~Completer(void)
0x18001c2a5  jmp     loc_18001C065
0x18001c2aa  mov     edx, 82h
0x18001c2af  jmp     loc_18001C198
```
