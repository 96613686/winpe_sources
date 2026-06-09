# CAudioDeviceManager::CreateAudioDevice(IMMDevice *,int,ulong)

- ea: `0x180004720`
- end: `0x180004afa`
- name: `?CreateAudioDevice@CAudioDeviceManager@@AEAAJPEAUIMMDevice@@HK@Z`
- size: `986`
- prototype: `__int64 __fastcall(CAudioDeviceManager *__hidden this, struct IMMDevice *, int, unsigned int)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003630`
- `0x180004680`
- `0x180036de4`

## callees

- `0x180004720`
- `0x180004b00`
- `0x180005358`
- `0x180005384`
- `0x18000634c`
- `0x180006b0c`
- `0x180009980`
- `0x180009b94`
- `0x180010da8`
- `0x180021060`
- `0x180027970`
- `0x180029024`
- `0x180059c54`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000474c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000474c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a08`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a13`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a08`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a13`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a55`

## string_xrefs

- `0x18000478a`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000493e`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180004957`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180004a34`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180004aa8`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180004ad3`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CAudioDeviceManager::CreateAudioDevice(
        CAudioDeviceManager *this,
        struct IMMDevice *a2,
        int a3,
        unsigned int a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  int v9; // eax
  void **v10; // r8
  unsigned int v11; // ebx
  BOOL v13; // ebx
  struct IMMDeviceVtbl *lpVtbl; // rax
  CAudioDevice *v15; // rax
  CAudioDevice *v16; // rax
  CAudioDevice *v17; // r14
  _QWORD *v18; // rax
  _QWORD *v19; // rcx
  _QWORD *Endpoint; // rax
  unsigned int v21; // [rsp+20h] [rbp-69h]
  unsigned int v22; // [rsp+20h] [rbp-69h]
  unsigned int v23; // [rsp+20h] [rbp-69h]
  __int64 v24; // [rsp+30h] [rbp-59h] BYREF
  CAudioDevice *AudioDevice; // [rsp+38h] [rbp-51h] BYREF
  CAudioDevice *v26; // [rsp+40h] [rbp-49h]
  PROPVARIANT v27[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v28; // [rsp+58h] [rbp-31h]
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v30; // [rsp+70h] [rbp-19h]
  _BYTE v31[8]; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-9h] BYREF
  char v33; // [rsp+90h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v35; // [rsp+F0h] [rbp+67h] BYREF

  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v32[0] = v8;
  AudioDevice = 0;
  v35 = 0;
  if ( *((_DWORD *)this + 36) )
  {
    v9 = ((__int64 (__fastcall *)(struct IMMDevice *, int *))a2->lpVtbl->GetState)(a2, &v35);
    v11 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7C,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)(unsigned int)v9,
        v21);
      if ( v8 )
        LeaveCriticalSection(v8);
      return v11;
    }
    if ( v35 != 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
      }
      goto LABEL_9;
    }
    v32[1] = &AudioDevice;
    v33 = 1;
    AudioDevice = CAudioDeviceManager::FindAudioDevice(this, a2, v10);
    if ( !AudioDevice )
    {
      v13 = 0;
      lpVtbl = a2->lpVtbl;
      v24 = 0;
      if ( ((int (__fastcall *)(struct IMMDevice *, __int64, __int64 *))lpVtbl->OpenPropertyStore)(a2, 2, &v24) >= 0 )
      {
        *(_OWORD *)v27 = 0;
        v28 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v24 + 40LL))(
               v24,
               PKEY_ApxEndpoint_IsSessionIdLocked,
               v27) >= 0
          && LOWORD(v27[0]) == 11 )
        {
          v13 = LOWORD(v27[1]) == 0xFFFF;
          *(_OWORD *)pvar = 0;
          v30 = 0;
          if ( (*(int (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v24 + 40LL))(
                 v24,
                 &DEVPKEY_Device_SessionId,
                 pvar) < 0
            || LOWORD(pvar[0]) != 19 )
          {
            v11 = -2147024809;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xAA1,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
              (const char *)0x80070057LL,
              v21);
            PropVariantClear(pvar);
            PropVariantClear(v27);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
            if ( AudioDevice )
              CAudioDevice::Delete(AudioDevice);
            goto LABEL_29;
          }
          if ( v13 && LODWORD(pvar[1]) )
            a4 = (unsigned int)pvar[1];
          PropVariantClear(pvar);
        }
        PropVariantClear(v27);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      }
      else if ( v24 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      AudioDevice = 0;
      v15 = (CAudioDevice *)operator new(0x70u);
      v26 = v15;
      if ( v15 && (v16 = CAudioDevice::CAudioDevice(v15), v17 = v16, (v26 = v16) != 0) )
      {
        v11 = CAudioDevice::InitializeInternal(v16, a2, a3, v13, a4);
        if ( (v11 & 0x80000000) == 0 )
        {
          AudioDevice = v17;
          v18 = operator new(0x18u);
          if ( v18 )
          {
            *v18 = 0;
            v18[1] = 0;
            v18[2] = v17;
            v18[1] = *((_QWORD *)this + 12);
            *v18 = 0;
            v19 = (_QWORD *)*((_QWORD *)this + 12);
            if ( v19 )
              *v19 = v18;
            else
              *((_QWORD *)this + 11) = v18;
            *((_QWORD *)this + 12) = v18;
            ++*((_DWORD *)this + 26);
            goto LABEL_9;
          }
          v11 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAAD,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
            (const char *)0x8007000ELL,
            v22);
          if ( AudioDevice )
            CAudioDevice::Delete(AudioDevice);
LABEL_29:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v32);
          return v11;
        }
        Endpoint = (_QWORD *)CAudioDevice::GetEndpoint(v17, v31);
        AEBTelemetry::LogDeviceCreationFailure(0, *Endpoint, 0, v11);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v31);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x631,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
          (const char *)v11,
          v22);
        CAudioDevice::Release(v17);
      }
      else
      {
        v11 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62F,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
          (const char *)0x8007000ELL,
          v21);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAAB,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)v11,
        v23);
      if ( AudioDevice )
        CAudioDevice::Delete(AudioDevice);
      goto LABEL_29;
    }
  }
LABEL_9:
  if ( v8 )
    LeaveCriticalSection(v8);
  return 0;
}

```

## disassembly

```asm
0x180004720  push    rbp
0x180004722  push    rbx
0x180004723  push    rsi
0x180004724  push    rdi
0x180004725  push    r12
0x180004727  push    r13
0x180004729  push    r14
0x18000472b  push    r15
0x18000472d  lea     rbp, [rsp-1Fh]
0x180004732  sub     rsp, 0A8h
0x180004739  mov     r12d, r9d
0x18000473c  mov     r13d, r8d
0x18000473f  mov     r15, rdx
0x180004742  mov     rsi, rcx
0x180004745  lea     rdi, [rcx+8]
0x180004749  mov     rcx, rdi; lpCriticalSection
0x18000474c  call    cs:__imp_EnterCriticalSection
0x180004752  mov     [rbp+57h+var_60], rdi
0x180004756  xor     r14d, r14d
0x180004759  mov     [rbp+57h+var_A8], r14
0x18000475d  mov     [rbp+57h+arg_0], r14d
0x180004761  cmp     [rsi+90h], r14d
0x180004768  jz      short loc_1800047D8
0x18000476a  mov     rax, [r15]
0x18000476d  lea     rdx, [rbp+57h+arg_0]
0x180004771  mov     rcx, r15
0x180004774  mov     rax, [rax+30h]
0x180004778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000477d  mov     ebx, eax
0x18000477f  test    eax, eax
0x180004781  jns     short loc_1800047DF
0x180004783  mov     rcx, [rbp+5Fh]; this
0x180004787  mov     r9d, eax; char *
0x18000478a  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180004791  mov     edx, 0A7Ch; void *
0x180004796  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000479b  nop
0x18000479c  test    rdi, rdi
0x18000479f  jz      short loc_1800047AA
0x1800047a1  mov     rcx, rdi; lpCriticalSection
0x1800047a4  call    cs:__imp_LeaveCriticalSection
0x1800047aa  mov     eax, ebx
0x1800047ac  jmp     short loc_1800047B9
0x1800047ae  mov     rcx, rdi; lpCriticalSection
0x1800047b1  call    cs:__imp_LeaveCriticalSection
0x1800047b7  xor     eax, eax
0x1800047b9  add     rsp, 0A8h
0x1800047c0  pop     r15
0x1800047c2  pop     r14
0x1800047c4  pop     r13
0x1800047c6  pop     r12
0x1800047c8  pop     rdi
0x1800047c9  pop     rsi
0x1800047ca  pop     rbx
0x1800047cb  pop     rbp
0x1800047cc  retn
0x1800047cd  mov     [rsi+58h], rax
0x1800047d1  mov     [rsi+60h], rax
0x1800047d5  inc     dword ptr [rsi+68h]
0x1800047d8  test    rdi, rdi
0x1800047db  jz      short loc_1800047B7
0x1800047dd  jmp     short loc_1800047AE
0x1800047df  mov     r9d, [rbp+57h+arg_0]
0x1800047e3  cmp     r9d, 1
0x1800047e7  jnz     loc_1800048EA
0x1800047ed  lea     rax, [rbp+57h+var_A8]
0x1800047f1  mov     [rbp+57h+var_58], rax
0x1800047f5  mov     [rbp+57h+var_50], r9b
0x1800047f9  mov     rdx, r15; struct IMMDevice *
0x1800047fc  mov     rcx, rsi; this
0x1800047ff  call    ?FindAudioDevice@CAudioDeviceManager@@AEAAPEAVCAudioDevice@@PEAUIMMDevice@@PEAPEAX@Z; CAudioDeviceManager::FindAudioDevice(IMMDevice *,void * *)
0x180004804  mov     [rbp+57h+var_A8], rax
0x180004808  test    rax, rax
0x18000480b  jnz     short loc_1800047D8
0x18000480d  mov     ebx, r14d
0x180004810  mov     rax, [r15]
0x180004813  mov     [rbp+57h+var_B0], r14
0x180004817  lea     r8, [rbp+57h+var_B0]
0x18000481b  mov     edx, 2
0x180004820  mov     rcx, r15
0x180004823  mov     rax, [rax+20h]
0x180004827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000482c  test    eax, eax
0x18000482e  jns     loc_180004986
0x180004834  mov     rcx, [rbp+57h+var_B0]
0x180004838  test    rcx, rcx
0x18000483b  jz      short loc_18000484A
0x18000483d  mov     rax, [rcx]
0x180004840  mov     rax, [rax+10h]
0x180004844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004849  nop
0x18000484a  mov     [rbp+57h+var_A8], r14
0x18000484e  mov     ecx, 70h ; 'p'; unsigned __int64
0x180004853  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004858  mov     [rbp+57h+var_A0], rax
0x18000485c  test    rax, rax
0x18000485f  jz      loc_180004932
0x180004865  mov     rcx, rax; this
0x180004868  call    ??0CAudioDevice@@AEAA@XZ; CAudioDevice::CAudioDevice(void)
0x18000486d  mov     r14, rax
0x180004870  mov     [rbp+57h+var_A0], rax
0x180004874  test    rax, rax
0x180004877  jz      loc_180004932
0x18000487d  mov     [rsp+0E0h+var_C0], r12d; int
0x180004882  mov     r9d, ebx; int
0x180004885  mov     r8d, r13d; int
0x180004888  mov     rdx, r15; struct IMMDevice *
0x18000488b  mov     rcx, rax; this
0x18000488e  call    ?InitializeInternal@CAudioDevice@@AEAAJPEAUIMMDevice@@HHK@Z; CAudioDevice::InitializeInternal(IMMDevice *,int,int,ulong)
0x180004893  mov     ebx, eax
0x180004895  test    eax, eax
0x180004897  js      loc_180004A7A
0x18000489d  mov     [rbp+57h+var_A8], r14
0x1800048a1  mov     ecx, 18h; unsigned __int64
0x1800048a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800048ab  test    rax, rax
0x1800048ae  jz      loc_180004AC7
0x1800048b4  mov     qword ptr [rax], 0
0x1800048bb  mov     qword ptr [rax+8], 0
0x1800048c3  mov     [rax+10h], r14
0x1800048c7  mov     rcx, [rsi+60h]
0x1800048cb  mov     [rax+8], rcx
0x1800048cf  xor     r14d, r14d
0x1800048d2  mov     [rax], r14
0x1800048d5  mov     rcx, [rsi+60h]
0x1800048d9  test    rcx, rcx
0x1800048dc  jz      loc_1800047CD
0x1800048e2  mov     [rcx], rax
0x1800048e5  jmp     loc_1800047D1
0x1800048ea  lea     rax, WPP_GLOBAL_Control
0x1800048f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048f8  cmp     rcx, rax
0x1800048fb  jz      loc_1800047D8
0x180004901  test    dword ptr [rcx+1Ch], 80000h
0x180004908  jz      loc_1800047D8
0x18000490e  cmp     byte ptr [rcx+19h], 4
0x180004912  jb      loc_1800047D8
0x180004918  mov     edx, 2Ch ; ','
0x18000491d  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x180004924  mov     rcx, [rcx+10h]
0x180004928  call    WPP_SF_d
0x18000492d  jmp     loc_1800047D8
0x180004932  mov     rcx, [rbp+5Fh]; this
0x180004936  mov     ebx, 8007000Eh
0x18000493b  mov     r9d, ebx; char *
0x18000493e  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180004945  mov     edx, 62Fh; void *
0x18000494a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000494f  nop
0x180004950  mov     rcx, [rbp+5Fh]; this
0x180004954  mov     r9d, ebx; char *
0x180004957  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000495e  mov     edx, 0AABh; void *
0x180004963  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004968  nop
0x180004969  mov     rcx, [rbp+57h+var_A8]; this
0x18000496d  test    rcx, rcx
0x180004970  jz      short loc_180004978
0x180004972  call    ?Delete@CAudioDevice@@QEAAJXZ; CAudioDevice::Delete(void)
0x180004977  nop
0x180004978  lea     rcx, [rbp+57h+var_60]
0x18000497c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180004981  jmp     loc_1800047AA
0x180004986  xorps   xmm0, xmm0
0x180004989  xor     eax, eax
0x18000498b  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x18000498f  mov     [rbp+57h+var_88], rax
0x180004993  mov     rcx, [rbp+57h+var_B0]
0x180004997  mov     rax, [rcx]
0x18000499a  lea     r8, [rbp+57h+var_98]
0x18000499e  lea     rdx, PKEY_ApxEndpoint_IsSessionIdLocked
0x1800049a5  mov     rax, [rax+28h]
0x1800049a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ae  test    eax, eax
0x1800049b0  js      short loc_180004A0F
0x1800049b2  cmp     word ptr [rbp+57h+var_98], 0Bh
0x1800049b7  jnz     short loc_180004A0F
0x1800049b9  mov     ebx, r14d
0x1800049bc  cmp     word ptr [rbp+57h+var_98+8], 0FFFFh
0x1800049c1  setz    bl
0x1800049c4  xorps   xmm0, xmm0
0x1800049c7  xor     eax, eax
0x1800049c9  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800049cd  mov     [rbp+57h+var_70], rax
0x1800049d1  mov     rcx, [rbp+57h+var_B0]
0x1800049d5  mov     rax, [rcx]
0x1800049d8  lea     r8, [rbp+57h+pvar]
0x1800049dc  lea     rdx, DEVPKEY_Device_SessionId
0x1800049e3  mov     rax, [rax+28h]
0x1800049e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ec  test    eax, eax
0x1800049ee  js      short loc_180004A28
0x1800049f0  cmp     word ptr [rbp+57h+pvar], 13h
0x1800049f5  jnz     short loc_180004A28
0x1800049f7  test    ebx, ebx
0x1800049f9  jz      short loc_180004A04
0x1800049fb  mov     eax, dword ptr [rbp+57h+pvar+8]
0x1800049fe  test    eax, eax
0x180004a00  cmovnz  r12d, eax
0x180004a04  lea     rcx, [rbp+57h+pvar]; pvar
0x180004a08  call    cs:__imp_PropVariantClear
0x180004a0e  nop
0x180004a0f  lea     rcx, [rbp+57h+var_98]; pvar
0x180004a13  call    cs:__imp_PropVariantClear
0x180004a19  nop
0x180004a1a  lea     rcx, [rbp+57h+var_B0]
0x180004a1e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004a23  jmp     loc_18000484A
0x180004a28  mov     rcx, [rbp+5Fh]; this
0x180004a2c  mov     ebx, 80070057h
0x180004a31  mov     r9d, ebx; char *
0x180004a34  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180004a3b  mov     edx, 0AA1h; void *
0x180004a40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a45  nop
0x180004a46  lea     rcx, [rbp+57h+pvar]; pvar
0x180004a4a  call    cs:__imp_PropVariantClear
0x180004a50  nop
0x180004a51  lea     rcx, [rbp+57h+var_98]; pvar
0x180004a55  call    cs:__imp_PropVariantClear
0x180004a5b  nop
0x180004a5c  lea     rcx, [rbp+57h+var_B0]
0x180004a60  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004a65  nop
0x180004a66  mov     rcx, [rbp+57h+var_A8]; this
0x180004a6a  test    rcx, rcx
0x180004a6d  jz      short loc_180004A75
0x180004a6f  call    ?Delete@CAudioDevice@@QEAAJXZ; CAudioDevice::Delete(void)
0x180004a74  nop
0x180004a75  jmp     loc_180004978
0x180004a7a  lea     rdx, [rbp+57h+var_68]
0x180004a7e  mov     rcx, r14
0x180004a81  call    ?GetEndpoint@CAudioDevice@@QEAA?AV?$CComPtr@UIMMDevice@@@ATL@@XZ; CAudioDevice::GetEndpoint(void)
0x180004a86  nop
0x180004a87  mov     r9d, ebx
0x180004a8a  xor     r8d, r8d
0x180004a8d  mov     rdx, [rax]
0x180004a90  xor     ecx, ecx
0x180004a92  call    ?LogDeviceCreationFailure@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@W4DeviceCreationFailureSite@@J@Z; AEBTelemetry::LogDeviceCreationFailure(ushort const *,IMMDevice *,DeviceCreationFailureSite,long)
0x180004a97  nop
0x180004a98  lea     rcx, [rbp+57h+var_68]
0x180004a9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004aa1  mov     rcx, [rbp+5Fh]; this
0x180004aa5  mov     r9d, ebx; char *
0x180004aa8  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180004aaf  mov     edx, 631h; void *
0x180004ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ab9  nop
0x180004aba  mov     rcx, r14; this
0x180004abd  call    ?Release@CAudioDevice@@QEAAKXZ; CAudioDevice::Release(void)
0x180004ac2  jmp     loc_180004950
0x180004ac7  mov     rcx, [rbp+5Fh]; this
0x180004acb  mov     ebx, 8007000Eh
0x180004ad0  mov     r9d, ebx; char *
0x180004ad3  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180004ada  mov     edx, 0AADh; void *
0x180004adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ae4  nop
0x180004ae5  mov     rcx, [rbp+57h+var_A8]; this
0x180004ae9  test    rcx, rcx
0x180004aec  jz      short loc_180004AF4
0x180004aee  call    ?Delete@CAudioDevice@@QEAAJXZ; CAudioDevice::Delete(void)
0x180004af3  nop
0x180004af4  jmp     loc_180004978
```
