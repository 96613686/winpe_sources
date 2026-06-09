# CSystemAudioDeviceSharedBase::Initialize(AUDIO_DEVICE_PIPE_DESCRIPTOR *,IUnknown *,IAudioGraphCallback *,ulong)

- ea: `0x140081750`
- end: `0x140081997`
- name: `?Initialize@CSystemAudioDeviceSharedBase@@UEAAJPEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@PEAUIUnknown@@PEAUIAudioGraphCallback@@K@Z`
- size: `583`
- prototype: `__int64 __usercall@<rax>(CSystemAudioDeviceSharedBase *__hidden this@<rcx>, struct AUDIO_DEVICE_PIPE_DESCRIPTOR *@<rdx>, struct IUnknown *@<r8>, struct IAudioGraphCallback *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140055490`

## callees

- `0x140009448`
- `0x14000ad48`
- `0x14000e11c`
- `0x14000e280`
- `0x14000e404`
- `0x140019a00`
- `0x14002ce08`
- `0x140055de0`
- `0x14005d0e0`
- `0x140069128`
- `0x14007e5e4`
- `0x140081750`
- `0x1400b401c`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140081953`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140081953`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400817df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400817df`
- `ntdll!EtwEventActivityIdControl` at `0x1400817ae`
- `ntdll!EtwEventActivityIdControl` at `0x14008196d`
- `ntdll!EtwEventActivityIdControl` at `0x1400817ae`
- `ntdll!EtwEventActivityIdControl` at `0x14008196d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14008180e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14008180e`

## pseudocode

```c
__int64 __fastcall CSystemAudioDeviceSharedBase::Initialize(
        CSystemAudioDeviceSharedBase *this,
        struct AUDIO_DEVICE_PIPE_DESCRIPTOR *a2,
        struct IUnknown *a3,
        struct IUnknown *a4,
        unsigned int a5)
{
  const struct _tlgProvider_t *v9; // rax
  void *v10; // rdx
  unsigned int v11; // ecx
  unsigned __int8 v12; // r8
  HRESULT Instance; // edi
  __int64 v14; // r10
  int v15; // eax
  void *v16; // rdx
  unsigned int v17; // ecx
  unsigned __int8 v18; // r8
  LPVOID *ppv; // [rsp+20h] [rbp-168h]
  LPVOID *ppva; // [rsp+20h] [rbp-168h]
  unsigned __int64 v22; // [rsp+28h] [rbp-160h]
  unsigned __int64 v23; // [rsp+28h] [rbp-160h]
  _QWORD v24[2]; // [rsp+40h] [rbp-148h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-138h] BYREF

  *(_OWORD *)((char *)this + 104) = *(_OWORD *)((char *)a2 + 148);
  v24[0] = *((_QWORD *)this + 13);
  v24[1] = *((_QWORD *)this + 14);
  EtwEventActivityIdControl(4, v24);
  v9 = AudioDgTelemetryProvider::Provider();
  CPerfTracker::CPerfTracker(&PerformanceCount, v9, "SaDevice_Initialize", 0);
  AEWMILOG_PERFORMANCE(v11, v10, v12, 9u, (unsigned __int64)ppv, v22);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( !a4 )
  {
    Instance = -2147024809;
    goto LABEL_12;
  }
  Instance = CoCreateInstance(
               &GUID_add18bf7_ab60_4283_a580_d7544dd255d2,
               0,
               0x17u,
               &GUID_359f1fc4_4a4b_42d0_b75d_a021af7de2ee,
               (LPVOID *)this + 23);
  if ( Instance < 0 )
    goto LABEL_12;
  *((_DWORD *)this + 20) = a5;
  if ( *((struct IUnknown **)this + 22) != a4 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 22, a4);
  v14 = *((_QWORD *)this + 23);
  *((_DWORD *)this + 24) = *((_DWORD *)a2 + 34);
  LODWORD(ppva) = *((_DWORD *)this + 20);
  Instance = (*(__int64 (__fastcall **)(__int64, struct AUDIO_DEVICE_PIPE_DESCRIPTOR *, struct IUnknown *, unsigned __int64))(*(_QWORD *)v14 + 24LL))(
               v14,
               a2,
               a3,
               ((unsigned __int64)this + 8) & -(__int64)(this != 0));
  if ( Instance < 0 )
    goto LABEL_12;
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 18);
  *((_DWORD *)this + 52) = *((_DWORD *)a2 + 25);
  v15 = CSystemAudioDeviceCollection::Add(*((const unsigned __int16 **)a2 + 7), this);
  *((_DWORD *)this + 49) = v15;
  if ( !v15 )
  {
    Instance = -2147024882;
LABEL_12:
    (*(void (__fastcall **)(CSystemAudioDeviceSharedBase *))(*(_QWORD *)this + 184LL))(this);
    goto LABEL_13;
  }
  Instance = CSystemAudioDeviceBase::ApplyFxStateSettings(this, a2, 1);
  if ( Instance < 0 )
    goto LABEL_12;
  if ( *((_DWORD *)this + 52) == 1 )
    CSystemAudioDeviceSharedBase::SetGraphState(this, 3);
LABEL_13:
  AEWMILOG_PERFORMANCE(v17, v16, v18, 0xAu, (unsigned __int64)ppva, v23);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_8627ec98682b3064b061eb6c0d785635_Traceguids,
        (unsigned int)Instance);
    }
    AudDGTraceLoggingErrorHelper("CSystemAudioDeviceSharedBase::Initialize", 0xC1u, Instance);
  }
  PublishDeviceGraphWnfState();
  if ( this != (CSystemAudioDeviceSharedBase *)-40LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
  EtwEventActivityIdControl(4, v24);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140081750  push    rbx
0x140081752  push    rbp
0x140081753  push    rsi
0x140081754  push    rdi
0x140081755  push    r12
0x140081757  push    r14
0x140081759  push    r15
0x14008175b  sub     rsp, 150h
0x140081762  mov     rax, cs:__security_cookie
0x140081769  xor     rax, rsp
0x14008176c  mov     [rsp+188h+var_48], rax
0x140081774  movups  xmm0, xmmword ptr [rdx+94h]
0x14008177b  mov     rsi, rdx
0x14008177e  mov     rbx, rcx
0x140081781  lea     rdx, [rsp+188h+var_148]
0x140081786  mov     rbp, r9
0x140081789  movdqu  xmmword ptr [rcx+68h], xmm0
0x14008178e  mov     rax, [rcx+68h]
0x140081792  mov     r12, r8
0x140081795  mov     [rsp+188h+var_148], rax
0x14008179a  mov     rax, [rcx+70h]
0x14008179e  mov     ecx, 4
0x1400817a3  mov     [rsp+188h+var_140], rax
0x1400817a8  movdqu  [rsp+188h+var_158], xmm0
0x1400817ae  call    cs:__imp_EtwEventActivityIdControl
0x1400817b4  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x1400817b9  mov     rdx, rax; struct _tlgProvider_t *
0x1400817bc  lea     r8, aSadeviceInitia; "SaDevice_Initialize"
0x1400817c3  xor     r9d, r9d; char *
0x1400817c6  lea     rcx, [rsp+188h+PerformanceCount]; lpPerformanceCount
0x1400817cb  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x1400817d0  mov     r9b, 9; unsigned __int8
0x1400817d3  call    ?AEWMILOG_PERFORMANCE@@YAXKPEAXEE_K1@Z; AEWMILOG_PERFORMANCE(ulong,void *,uchar,uchar,unsigned __int64,unsigned __int64)
0x1400817d8  lea     r14, [rbx+28h]
0x1400817dc  mov     rcx, r14; lpCriticalSection
0x1400817df  call    cs:__imp_EnterCriticalSection
0x1400817e5  test    rbp, rbp
0x1400817e8  jz      loc_1400818D5
0x1400817ee  xor     edx, edx; pUnkOuter
0x1400817f0  lea     r15, [rbx+0B8h]
0x1400817f7  lea     r9, _GUID_359f1fc4_4a4b_42d0_b75d_a021af7de2ee; riid
0x1400817fe  mov     [rsp+188h+ppv], r15; ppv
0x140081803  lea     rcx, _GUID_add18bf7_ab60_4283_a580_d7544dd255d2; rclsid
0x14008180a  lea     r8d, [rdx+17h]; dwClsContext
0x14008180e  call    cs:__imp_CoCreateInstance
0x140081814  mov     edi, eax
0x140081816  test    eax, eax
0x140081818  js      loc_1400818DA
0x14008181e  mov     eax, [rsp+188h+arg_20]
0x140081825  lea     rcx, [rbx+0B0h]; struct IUnknown **
0x14008182c  mov     [rbx+50h], eax
0x14008182f  cmp     [rcx], rbp
0x140081832  jz      short loc_14008183C
0x140081834  mov     rdx, rbp; struct IUnknown *
0x140081837  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x14008183c  mov     eax, [rsi+88h]
0x140081842  lea     rcx, [rbx+8]
0x140081846  mov     r10, [r15]
0x140081849  mov     r8, r12
0x14008184c  mov     [rbx+60h], eax
0x14008184f  mov     rax, rbx
0x140081852  neg     rax
0x140081855  mov     rdx, [r10]
0x140081858  sbb     r9, r9
0x14008185b  and     r9, rcx
0x14008185e  mov     ecx, [rbx+50h]
0x140081861  mov     dword ptr [rsp+188h+ppv], ecx
0x140081865  mov     rcx, r10
0x140081868  mov     rax, [rdx+18h]
0x14008186c  mov     rdx, rsi
0x14008186f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081874  mov     edi, eax
0x140081876  test    eax, eax
0x140081878  js      short loc_1400818DA
0x14008187a  mov     eax, [rsi+48h]
0x14008187d  mov     rdx, rbx; struct CSystemAudioDeviceBase *
0x140081880  mov     [rbx+20h], eax
0x140081883  mov     eax, [rsi+64h]
0x140081886  mov     [rbx+0D0h], eax
0x14008188c  mov     rcx, [rsi+38h]; unsigned __int16 *
0x140081890  call    ?Add@CSystemAudioDeviceCollection@@SAHPEBGPEAVCSystemAudioDeviceBase@@@Z; CSystemAudioDeviceCollection::Add(ushort const *,CSystemAudioDeviceBase *)
0x140081895  mov     [rbx+0C4h], eax
0x14008189b  test    eax, eax
0x14008189d  jnz     short loc_1400818A6
0x14008189f  mov     edi, 8007000Eh
0x1400818a4  jmp     short loc_1400818DA
0x1400818a6  mov     r8d, 1; int
0x1400818ac  mov     rdx, rsi; struct AUDIO_DEVICE_PIPE_DESCRIPTOR *
0x1400818af  mov     rcx, rbx; this
0x1400818b2  call    ?ApplyFxStateSettings@CSystemAudioDeviceBase@@IEAAJPEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@H@Z; CSystemAudioDeviceBase::ApplyFxStateSettings(AUDIO_DEVICE_PIPE_DESCRIPTOR *,int)
0x1400818b7  mov     edi, eax
0x1400818b9  test    eax, eax
0x1400818bb  js      short loc_1400818DA
0x1400818bd  cmp     dword ptr [rbx+0D0h], 1
0x1400818c4  jnz     short loc_1400818EC
0x1400818c6  mov     edx, 3
0x1400818cb  mov     rcx, rbx
0x1400818ce  call    ?SetGraphState@CSystemAudioDeviceSharedBase@@IEAAJW4GRAPH_STATE@@@Z; CSystemAudioDeviceSharedBase::SetGraphState(GRAPH_STATE)
0x1400818d3  jmp     short loc_1400818EC
0x1400818d5  mov     edi, 80070057h
0x1400818da  mov     rax, [rbx]
0x1400818dd  mov     rcx, rbx
0x1400818e0  mov     rax, [rax+0B8h]
0x1400818e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400818ec  mov     r9b, 0Ah; unsigned __int8
0x1400818ef  call    ?AEWMILOG_PERFORMANCE@@YAXKPEAXEE_K1@Z; AEWMILOG_PERFORMANCE(ulong,void *,uchar,uchar,unsigned __int64,unsigned __int64)
0x1400818f4  test    edi, edi
0x1400818f6  jns     short loc_140081946
0x1400818f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400818ff  lea     rax, WPP_GLOBAL_Control
0x140081906  cmp     rcx, rax
0x140081909  jz      short loc_140081932
0x14008190b  test    dword ptr [rcx+1Ch], 200h
0x140081912  jz      short loc_140081932
0x140081914  cmp     byte ptr [rcx+19h], 2
0x140081918  jb      short loc_140081932
0x14008191a  mov     rcx, [rcx+10h]
0x14008191e  lea     r8, WPP_8627ec98682b3064b061eb6c0d785635_Traceguids
0x140081925  mov     edx, 10h
0x14008192a  mov     r9d, edi
0x14008192d  call    WPP_SF_d
0x140081932  mov     r8d, edi; int
0x140081935  lea     rcx, aCsystemaudiode_16; "CSystemAudioDeviceSharedBase::Initializ"...
0x14008193c  mov     edx, 0C1h; unsigned int
0x140081941  call    ?AudDGTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudDGTraceLoggingErrorHelper(char const *,uint,long)
0x140081946  call    ?PublishDeviceGraphWnfState@@YAXXZ; PublishDeviceGraphWnfState(void)
0x14008194b  test    r14, r14
0x14008194e  jz      short loc_140081959
0x140081950  mov     rcx, r14; lpCriticalSection
0x140081953  call    cs:__imp_LeaveCriticalSection
0x140081959  lea     rcx, [rsp+188h+PerformanceCount]; this
0x14008195e  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x140081963  lea     rdx, [rsp+188h+var_148]
0x140081968  mov     ecx, 4
0x14008196d  call    cs:__imp_EtwEventActivityIdControl
0x140081973  mov     eax, edi
0x140081975  mov     rcx, [rsp+188h+var_48]
0x14008197d  xor     rcx, rsp; StackCookie
0x140081980  call    __security_check_cookie
0x140081985  add     rsp, 150h
0x14008198c  pop     r15
0x14008198e  pop     r14
0x140081990  pop     r12
0x140081992  pop     rdi
0x140081993  pop     rsi
0x140081994  pop     rbp
0x140081995  pop     rbx
0x140081996  retn
```
