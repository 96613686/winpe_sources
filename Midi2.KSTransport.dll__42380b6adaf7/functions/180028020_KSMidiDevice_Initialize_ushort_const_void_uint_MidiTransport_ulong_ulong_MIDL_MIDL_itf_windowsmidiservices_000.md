# KSMidiDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong &,ulong *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,IMidiCallback *,__int64)

- ea: `0x180028020`
- end: `0x1800282ef`
- name: `?Initialize@KSMidiDevice@@MEAAJPEBGPEAXIW4_MidiTransport@@AEAKPEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAUIMidiCallback@@_J@Z`
- size: `719`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, void *, int, int, _DWORD *, _DWORD *, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800285a0`
- `0x180028994`

## callees

- `0x180004434`
- `0x18000a7f4`
- `0x18000a814`
- `0x180024cf4`
- `0x180025cfc`
- `0x1800267e4`
- `0x180026b64`
- `0x180026cfc`
- `0x1800270a8`
- `0x180027890`
- `0x180028020`
- `0x180029038`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800282b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800282d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800282b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800282d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002827f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002827f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028097`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002808f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002808f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028160`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028169`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028160`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028169`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002818e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002818e`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall KSMidiDevice::Initialize(
        __int64 a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        int a5,
        _DWORD *a6,
        _DWORD *a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11)
{
  int v11; // r15d
  unsigned __int64 v15; // r8
  _QWORD *cotaskmem_string_nothrow; // rax
  _QWORD *v17; // r14
  LPVOID *v18; // rsi
  void *v19; // r12
  void *v20; // r15
  DWORD LastError; // ebx
  int v22; // ebx
  __int64 v23; // rdx
  __int64 *v25; // rax
  __int64 v26; // rdx
  KsHandleWrapper *v27; // rbx
  void *v28; // rbx
  HANDLE CurrentProcess; // rbx
  HANDLE v30; // rax
  const char *v31; // r9
  __int64 *v32; // rax
  __int64 v33; // rdx
  KsHandleWrapper *v34; // rbx
  KsHandleWrapper *v35; // rbx
  int v36; // eax
  unsigned int v37; // esi
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-48h]
  void *Block; // [rsp+40h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-20h] BYREF
  KsHandleWrapper *v41; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v11 = a4;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl) )
    return 0;
  *(_DWORD *)(a1 + 76) = a5;
  cotaskmem_string_nothrow = (_QWORD *)wil::make_cotaskmem_string_nothrow((wil *)&pv, a2, v15);
  v17 = cotaskmem_string_nothrow;
  v18 = (LPVOID *)(a1 + 64);
  if ( (_QWORD *)(a1 + 64) != cotaskmem_string_nothrow )
  {
    v19 = (void *)*cotaskmem_string_nothrow;
    v20 = *v18;
    if ( *v18 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v20);
      SetLastError(LastError);
    }
    *v18 = v19;
    *v17 = 0;
    v11 = a4;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !*v18 )
  {
    v22 = -2147024882;
    v23 = 98;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)(unsigned int)v22,
      dwDesiredAccess);
    return (unsigned int)v22;
  }
  if ( a3 )
  {
    Block = 0;
    CurrentProcess = GetCurrentProcess();
    v30 = GetCurrentProcess();
    if ( !DuplicateHandle(v30, a3, CurrentProcess, &Block, 0, 0, 2u) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x6F,
               (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
               v31);
    pv = *v18;
    v32 = (__int64 *)std::make_unique<KsHandleWrapper,unsigned short *,0>(&v41, &pv);
    v33 = *v32;
    *v32 = 0;
    v34 = *(KsHandleWrapper **)(a1 + 48);
    *(_QWORD *)(a1 + 48) = v33;
    if ( v34 )
    {
      KsHandleWrapper::~KsHandleWrapper(v34);
      operator delete(v34);
    }
    v35 = v41;
    if ( v41 )
    {
      KsHandleWrapper::~KsHandleWrapper(v41);
      operator delete(v35);
    }
    pv = Block;
    KsHandleWrapper::SetHandle(*(PSRWLOCK *)(a1 + 48));
    v22 = KsHandleWrapper::RegisterForNotifications(*(KsHandleWrapper **)(a1 + 48));
    if ( v22 < 0 )
    {
      v23 = 115;
      goto LABEL_10;
    }
  }
  else
  {
    pv = *v18;
    v25 = (__int64 *)std::make_unique<KsHandleWrapper,unsigned short *,0>(&Block, &pv);
    v26 = *v25;
    *v25 = 0;
    v27 = *(KsHandleWrapper **)(a1 + 48);
    *(_QWORD *)(a1 + 48) = v26;
    if ( v27 )
    {
      KsHandleWrapper::~KsHandleWrapper(v27);
      operator delete(v27);
    }
    v28 = Block;
    if ( Block )
    {
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)Block);
      operator delete(v28);
    }
    v22 = KsHandleWrapper::Open(*(KsHandleWrapper **)(a1 + 48));
    if ( v22 < 0 )
    {
      v23 = 104;
      goto LABEL_10;
    }
  }
  *(_DWORD *)(a1 + 72) = v11;
  *(_QWORD *)(a1 + 24) = a10;
  *(_QWORD *)(a1 + 32) = a11;
  *(_DWORD *)(a1 + 104) = *a7;
  *(_DWORD *)(a1 + 40) = *a6;
  *(_DWORD *)(a1 + 44) = a8;
  *(_DWORD *)(a1 + 16) = a9;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  v41 = (KsHandleWrapper *)(a1 + 8);
  v36 = KSMidiDevice::OpenStream((KSMidiDevice *)a1);
  v37 = v36;
  if ( v36 >= 0 )
  {
    *a7 = *(_DWORD *)(a1 + 104);
    *a6 = *(_DWORD *)(a1 + 40);
    if ( a1 != -8 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x85,
    (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
    (const char *)(unsigned int)v36,
    dwDesiredAccess);
  if ( a1 != -8 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
  return v37;
}

```

## disassembly

```asm
0x180028020  mov     [rsp-40h+arg_18], r9d
0x180028025  push    rbp
0x180028026  push    rbx
0x180028027  push    rsi
0x180028028  push    rdi
0x180028029  push    r12
0x18002802b  push    r13
0x18002802d  push    r14
0x18002802f  push    r15
0x180028031  mov     rbp, rsp
0x180028034  sub     rsp, 68h
0x180028038  mov     r15d, r9d
0x18002803b  mov     r13, r8
0x18002803e  mov     rbx, rdx
0x180028041  mov     rdi, rcx
0x180028044  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x18002804b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x180028050  xor     r12d, r12d
0x180028053  test    al, al
0x180028055  jz      loc_1800282DC
0x18002805b  mov     eax, [rbp+arg_20]
0x18002805e  mov     [rdi+4Ch], eax
0x180028061  mov     rdx, rbx; unsigned __int16 *
0x180028064  lea     rcx, [rbp+pv]; this
0x180028068  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18002806d  mov     r14, rax
0x180028070  lea     rsi, [rdi+40h]
0x180028074  cmp     rsi, rax
0x180028077  jz      short loc_1800280AA
0x180028079  mov     r12, [rax]
0x18002807c  mov     r15, [rsi]
0x18002807f  test    r15, r15
0x180028082  jz      short loc_18002809D
0x180028084  call    cs:__imp_GetLastError
0x18002808a  mov     ebx, eax
0x18002808c  mov     rcx, r15; pv
0x18002808f  call    cs:__imp_CoTaskMemFree
0x180028095  mov     ecx, ebx; dwErrCode
0x180028097  call    cs:__imp_SetLastError
0x18002809d  mov     [rsi], r12
0x1800280a0  xor     r12d, r12d
0x1800280a3  mov     [r14], r12
0x1800280a6  mov     r15d, [rbp+arg_18]
0x1800280aa  mov     rcx, [rbp+pv]; pv
0x1800280ae  test    rcx, rcx
0x1800280b1  jz      short loc_1800280B9
0x1800280b3  call    cs:__imp_CoTaskMemFree
0x1800280b9  mov     rax, [rsi]
0x1800280bc  test    rax, rax
0x1800280bf  jnz     short loc_1800280E3
0x1800280c1  mov     ebx, 8007000Eh
0x1800280c6  lea     edx, [rax+62h]; void *
0x1800280c9  mov     rcx, [rbp+40h]; this
0x1800280cd  mov     r9d, ebx; char *
0x1800280d0  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800280d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800280dc  mov     eax, ebx
0x1800280de  jmp     loc_1800282DE
0x1800280e3  test    r13, r13
0x1800280e6  jnz     short loc_18002815C
0x1800280e8  mov     [rbp+pv], rax
0x1800280ec  lea     rdx, [rbp+pv]
0x1800280f0  lea     rcx, [rbp+Block]
0x1800280f4  call    ??$make_unique@VKsHandleWrapper@@PEAG$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAG@Z; std::make_unique<KsHandleWrapper,ushort *,0>(ushort * &&)
0x1800280f9  mov     rdx, [rax]
0x1800280fc  mov     [rax], r12
0x1800280ff  mov     rbx, [rdi+30h]
0x180028103  mov     [rdi+30h], rdx
0x180028107  mov     esi, 0D8h
0x18002810c  test    rbx, rbx
0x18002810f  jz      short loc_180028123
0x180028111  mov     rcx, rbx; this
0x180028114  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180028119  mov     edx, esi
0x18002811b  mov     rcx, rbx; Block
0x18002811e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028123  mov     rbx, [rbp+Block]
0x180028127  test    rbx, rbx
0x18002812a  jz      short loc_18002813F
0x18002812c  mov     rcx, rbx; this
0x18002812f  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180028134  mov     rdx, rsi
0x180028137  mov     rcx, rbx; Block
0x18002813a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002813f  mov     rcx, [rdi+30h]; this
0x180028143  call    ?Open@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::Open(void)
0x180028148  mov     ebx, eax
0x18002814a  test    eax, eax
0x18002814c  jns     loc_180028238
0x180028152  mov     edx, 68h ; 'h'
0x180028157  jmp     loc_1800280C9
0x18002815c  mov     [rbp+Block], r12
0x180028160  call    cs:__imp_GetCurrentProcess
0x180028166  mov     rbx, rax
0x180028169  call    cs:__imp_GetCurrentProcess
0x18002816f  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180028177  mov     [rsp+68h+bInheritHandle], r12d; bInheritHandle
0x18002817c  mov     [rsp+68h+dwDesiredAccess], r12d; dwDesiredAccess
0x180028181  lea     r9, [rbp+Block]; lpTargetHandle
0x180028185  mov     r8, rbx; hTargetProcessHandle
0x180028188  mov     rdx, r13; hSourceHandle
0x18002818b  mov     rcx, rax; hSourceProcessHandle
0x18002818e  call    cs:__imp_DuplicateHandle
0x180028194  test    eax, eax
0x180028196  jnz     short loc_1800281B0
0x180028198  mov     rcx, [rbp+40h]; this
0x18002819c  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800281a3  lea     edx, [rax+6Fh]; void *
0x1800281a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800281ab  jmp     loc_1800282DE
0x1800281b0  mov     rax, [rsi]
0x1800281b3  mov     [rbp+pv], rax
0x1800281b7  lea     rdx, [rbp+pv]
0x1800281bb  lea     rcx, [rbp+var_18]
0x1800281bf  call    ??$make_unique@VKsHandleWrapper@@PEAG$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAG@Z; std::make_unique<KsHandleWrapper,ushort *,0>(ushort * &&)
0x1800281c4  mov     rdx, [rax]
0x1800281c7  mov     [rax], r12
0x1800281ca  mov     rbx, [rdi+30h]
0x1800281ce  mov     [rdi+30h], rdx
0x1800281d2  mov     esi, 0D8h
0x1800281d7  test    rbx, rbx
0x1800281da  jz      short loc_1800281EE
0x1800281dc  mov     rcx, rbx; this
0x1800281df  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x1800281e4  mov     edx, esi
0x1800281e6  mov     rcx, rbx; Block
0x1800281e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800281ee  mov     rbx, [rbp+var_18]
0x1800281f2  test    rbx, rbx
0x1800281f5  jz      short loc_18002820A
0x1800281f7  mov     rcx, rbx; this
0x1800281fa  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x1800281ff  mov     rdx, rsi
0x180028202  mov     rcx, rbx; Block
0x180028205  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002820a  mov     rax, [rbp+Block]
0x18002820e  mov     [rbp+pv], rax
0x180028212  lea     rdx, [rbp+pv]
0x180028216  mov     rcx, [rdi+30h]; SRWLock
0x18002821a  call    ?SetHandle@KsHandleWrapper@@QEAAXV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; KsHandleWrapper::SetHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x18002821f  mov     rcx, [rdi+30h]; this
0x180028223  call    ?RegisterForNotifications@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::RegisterForNotifications(void)
0x180028228  mov     ebx, eax
0x18002822a  test    eax, eax
0x18002822c  jns     short loc_180028238
0x18002822e  mov     edx, 73h ; 's'
0x180028233  jmp     loc_1800280C9
0x180028238  mov     [rdi+48h], r15d
0x18002823c  mov     rax, [rbp+arg_48]
0x180028243  mov     [rdi+18h], rax
0x180028247  mov     rax, [rbp+arg_50]
0x18002824e  mov     [rdi+20h], rax
0x180028252  mov     r14, [rbp+arg_30]
0x180028256  mov     eax, [r14]
0x180028259  mov     [rdi+68h], eax
0x18002825c  mov     r15, [rbp+arg_28]
0x180028260  mov     eax, [r15]
0x180028263  mov     [rdi+28h], eax
0x180028266  mov     eax, [rbp+arg_38]
0x18002826c  mov     [rdi+2Ch], eax
0x18002826f  mov     eax, [rbp+arg_40]
0x180028275  mov     [rdi+10h], eax
0x180028278  lea     rbx, [rdi+8]
0x18002827c  mov     rcx, rbx; SRWLock
0x18002827f  call    cs:__imp_AcquireSRWLockExclusive
0x180028285  mov     [rbp+var_18], rbx
0x180028289  mov     rcx, rdi; this
0x18002828c  call    ?OpenStream@KSMidiDevice@@IEAAJXZ; KSMidiDevice::OpenStream(void)
0x180028291  mov     esi, eax
0x180028293  test    eax, eax
0x180028295  jns     short loc_1800282C2
0x180028297  mov     rcx, [rbp+40h]; this
0x18002829b  mov     r9d, eax; char *
0x18002829e  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800282a5  mov     edx, 85h; void *
0x1800282aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800282af  nop
0x1800282b0  test    rbx, rbx
0x1800282b3  jz      short loc_1800282BE
0x1800282b5  mov     rcx, rbx; SRWLock
0x1800282b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800282be  mov     eax, esi
0x1800282c0  jmp     short loc_1800282DE
0x1800282c2  mov     eax, [rdi+68h]
0x1800282c5  mov     [r14], eax
0x1800282c8  mov     eax, [rdi+28h]
0x1800282cb  mov     [r15], eax
0x1800282ce  test    rbx, rbx
0x1800282d1  jz      short loc_1800282DC
0x1800282d3  mov     rcx, rbx; SRWLock
0x1800282d6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800282dc  xor     eax, eax
0x1800282de  add     rsp, 68h
0x1800282e2  pop     r15
0x1800282e4  pop     r14
0x1800282e6  pop     r13
0x1800282e8  pop     r12
0x1800282ea  pop     rdi
0x1800282eb  pop     rsi
0x1800282ec  pop     rbx
0x1800282ed  pop     rbp
0x1800282ee  retn
```
