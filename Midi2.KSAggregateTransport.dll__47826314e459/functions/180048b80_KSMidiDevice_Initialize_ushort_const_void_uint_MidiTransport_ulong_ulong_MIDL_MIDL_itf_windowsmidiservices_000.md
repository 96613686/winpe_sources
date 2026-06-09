# KSMidiDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong &,ulong *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,IMidiCallback *,__int64)

- ea: `0x180048b80`
- end: `0x180048e4f`
- name: `?Initialize@KSMidiDevice@@MEAAJPEBGPEAXIW4_MidiTransport@@AEAKPEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAUIMidiCallback@@_J@Z`
- size: `719`
- prototype: `int __high(const unsigned __int16 *, void *, unsigned int, enum _MidiTransport, unsigned int *, unsigned int *, enum __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004, enum __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002, struct IMidiCallback *, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180049100`
- `0x1800494d4`

## callees

- `0x180005044`
- `0x18000b374`
- `0x18000b394`
- `0x18001f6f8`
- `0x1800467b0`
- `0x180047294`
- `0x180047614`
- `0x1800477ac`
- `0x180047b58`
- `0x1800483f4`
- `0x180048b80`
- `0x180049b78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048e18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048e18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048e36`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048ddf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048ddf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048bf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048be4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048cc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048cc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048cc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048cc9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180048cee`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180048cee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180048b80  mov     [rsp-40h+arg_18], r9d
0x180048b85  push    rbp
0x180048b86  push    rbx
0x180048b87  push    rsi
0x180048b88  push    rdi
0x180048b89  push    r12
0x180048b8b  push    r13
0x180048b8d  push    r14
0x180048b8f  push    r15
0x180048b91  mov     rbp, rsp
0x180048b94  sub     rsp, 68h
0x180048b98  mov     r15d, r9d
0x180048b9b  mov     r13, r8
0x180048b9e  mov     rbx, rdx
0x180048ba1  mov     rdi, rcx
0x180048ba4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x180048bab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x180048bb0  xor     r12d, r12d
0x180048bb3  test    al, al
0x180048bb5  jz      loc_180048E3C
0x180048bbb  mov     eax, [rbp+arg_20]
0x180048bbe  mov     [rdi+4Ch], eax
0x180048bc1  mov     rdx, rbx; unsigned __int16 *
0x180048bc4  lea     rcx, [rbp+pv]; this
0x180048bc8  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180048bcd  mov     r14, rax
0x180048bd0  lea     rsi, [rdi+40h]
0x180048bd4  cmp     rsi, rax
0x180048bd7  jz      short loc_180048C0A
0x180048bd9  mov     r12, [rax]
0x180048bdc  mov     r15, [rsi]
0x180048bdf  test    r15, r15
0x180048be2  jz      short loc_180048BFD
0x180048be4  call    cs:__imp_GetLastError
0x180048bea  mov     ebx, eax
0x180048bec  mov     rcx, r15; pv
0x180048bef  call    cs:__imp_CoTaskMemFree
0x180048bf5  mov     ecx, ebx; dwErrCode
0x180048bf7  call    cs:__imp_SetLastError
0x180048bfd  mov     [rsi], r12
0x180048c00  xor     r12d, r12d
0x180048c03  mov     [r14], r12
0x180048c06  mov     r15d, [rbp+arg_18]
0x180048c0a  mov     rcx, [rbp+pv]; pv
0x180048c0e  test    rcx, rcx
0x180048c11  jz      short loc_180048C19
0x180048c13  call    cs:__imp_CoTaskMemFree
0x180048c19  mov     rax, [rsi]
0x180048c1c  test    rax, rax
0x180048c1f  jnz     short loc_180048C43
0x180048c21  mov     ebx, 8007000Eh
0x180048c26  lea     edx, [rax+62h]; void *
0x180048c29  mov     rcx, [rbp+40h]; this
0x180048c2d  mov     r9d, ebx; char *
0x180048c30  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180048c37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048c3c  mov     eax, ebx
0x180048c3e  jmp     loc_180048E3E
0x180048c43  test    r13, r13
0x180048c46  jnz     short loc_180048CBC
0x180048c48  mov     [rbp+pv], rax
0x180048c4c  lea     rdx, [rbp+pv]
0x180048c50  lea     rcx, [rbp+Block]
0x180048c54  call    ??$make_unique@VKsHandleWrapper@@PEAG$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAG@Z; std::make_unique<KsHandleWrapper,ushort *,0>(ushort * &&)
0x180048c59  mov     rdx, [rax]
0x180048c5c  mov     [rax], r12
0x180048c5f  mov     rbx, [rdi+30h]
0x180048c63  mov     [rdi+30h], rdx
0x180048c67  mov     esi, 0D8h
0x180048c6c  test    rbx, rbx
0x180048c6f  jz      short loc_180048C83
0x180048c71  mov     rcx, rbx; this
0x180048c74  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180048c79  mov     edx, esi
0x180048c7b  mov     rcx, rbx; Block
0x180048c7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048c83  mov     rbx, [rbp+Block]
0x180048c87  test    rbx, rbx
0x180048c8a  jz      short loc_180048C9F
0x180048c8c  mov     rcx, rbx; this
0x180048c8f  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180048c94  mov     rdx, rsi
0x180048c97  mov     rcx, rbx; Block
0x180048c9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048c9f  mov     rcx, [rdi+30h]; this
0x180048ca3  call    ?Open@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::Open(void)
0x180048ca8  mov     ebx, eax
0x180048caa  test    eax, eax
0x180048cac  jns     loc_180048D98
0x180048cb2  mov     edx, 68h ; 'h'
0x180048cb7  jmp     loc_180048C29
0x180048cbc  mov     [rbp+Block], r12
0x180048cc0  call    cs:__imp_GetCurrentProcess
0x180048cc6  mov     rbx, rax
0x180048cc9  call    cs:__imp_GetCurrentProcess
0x180048ccf  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180048cd7  mov     [rsp+68h+bInheritHandle], r12d; bInheritHandle
0x180048cdc  mov     [rsp+68h+dwDesiredAccess], r12d; dwDesiredAccess
0x180048ce1  lea     r9, [rbp+Block]; lpTargetHandle
0x180048ce5  mov     r8, rbx; hTargetProcessHandle
0x180048ce8  mov     rdx, r13; hSourceHandle
0x180048ceb  mov     rcx, rax; hSourceProcessHandle
0x180048cee  call    cs:__imp_DuplicateHandle
0x180048cf4  test    eax, eax
0x180048cf6  jnz     short loc_180048D10
0x180048cf8  mov     rcx, [rbp+40h]; this
0x180048cfc  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180048d03  lea     edx, [rax+6Fh]; void *
0x180048d06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180048d0b  jmp     loc_180048E3E
0x180048d10  mov     rax, [rsi]
0x180048d13  mov     [rbp+pv], rax
0x180048d17  lea     rdx, [rbp+pv]
0x180048d1b  lea     rcx, [rbp+var_18]
0x180048d1f  call    ??$make_unique@VKsHandleWrapper@@PEAG$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAG@Z; std::make_unique<KsHandleWrapper,ushort *,0>(ushort * &&)
0x180048d24  mov     rdx, [rax]
0x180048d27  mov     [rax], r12
0x180048d2a  mov     rbx, [rdi+30h]
0x180048d2e  mov     [rdi+30h], rdx
0x180048d32  mov     esi, 0D8h
0x180048d37  test    rbx, rbx
0x180048d3a  jz      short loc_180048D4E
0x180048d3c  mov     rcx, rbx; this
0x180048d3f  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180048d44  mov     edx, esi
0x180048d46  mov     rcx, rbx; Block
0x180048d49  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048d4e  mov     rbx, [rbp+var_18]
0x180048d52  test    rbx, rbx
0x180048d55  jz      short loc_180048D6A
0x180048d57  mov     rcx, rbx; this
0x180048d5a  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180048d5f  mov     rdx, rsi
0x180048d62  mov     rcx, rbx; Block
0x180048d65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048d6a  mov     rax, [rbp+Block]
0x180048d6e  mov     [rbp+pv], rax
0x180048d72  lea     rdx, [rbp+pv]
0x180048d76  mov     rcx, [rdi+30h]; SRWLock
0x180048d7a  call    ?SetHandle@KsHandleWrapper@@QEAAXV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; KsHandleWrapper::SetHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x180048d7f  mov     rcx, [rdi+30h]; this
0x180048d83  call    ?RegisterForNotifications@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::RegisterForNotifications(void)
0x180048d88  mov     ebx, eax
0x180048d8a  test    eax, eax
0x180048d8c  jns     short loc_180048D98
0x180048d8e  mov     edx, 73h ; 's'
0x180048d93  jmp     loc_180048C29
0x180048d98  mov     [rdi+48h], r15d
0x180048d9c  mov     rax, [rbp+arg_48]
0x180048da3  mov     [rdi+18h], rax
0x180048da7  mov     rax, [rbp+arg_50]
0x180048dae  mov     [rdi+20h], rax
0x180048db2  mov     r14, [rbp+arg_30]
0x180048db6  mov     eax, [r14]
0x180048db9  mov     [rdi+68h], eax
0x180048dbc  mov     r15, [rbp+arg_28]
0x180048dc0  mov     eax, [r15]
0x180048dc3  mov     [rdi+28h], eax
0x180048dc6  mov     eax, [rbp+arg_38]
0x180048dcc  mov     [rdi+2Ch], eax
0x180048dcf  mov     eax, [rbp+arg_40]
0x180048dd5  mov     [rdi+10h], eax
0x180048dd8  lea     rbx, [rdi+8]
0x180048ddc  mov     rcx, rbx; SRWLock
0x180048ddf  call    cs:__imp_AcquireSRWLockExclusive
0x180048de5  mov     [rbp+var_18], rbx
0x180048de9  mov     rcx, rdi; this
0x180048dec  call    ?OpenStream@KSMidiDevice@@IEAAJXZ; KSMidiDevice::OpenStream(void)
0x180048df1  mov     esi, eax
0x180048df3  test    eax, eax
0x180048df5  jns     short loc_180048E22
0x180048df7  mov     rcx, [rbp+40h]; this
0x180048dfb  mov     r9d, eax; char *
0x180048dfe  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180048e05  mov     edx, 85h; void *
0x180048e0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048e0f  nop
0x180048e10  test    rbx, rbx
0x180048e13  jz      short loc_180048E1E
0x180048e15  mov     rcx, rbx; SRWLock
0x180048e18  call    cs:__imp_ReleaseSRWLockExclusive
0x180048e1e  mov     eax, esi
0x180048e20  jmp     short loc_180048E3E
0x180048e22  mov     eax, [rdi+68h]
0x180048e25  mov     [r14], eax
0x180048e28  mov     eax, [rdi+28h]
0x180048e2b  mov     [r15], eax
0x180048e2e  test    rbx, rbx
0x180048e31  jz      short loc_180048E3C
0x180048e33  mov     rcx, rbx; SRWLock
0x180048e36  call    cs:__imp_ReleaseSRWLockExclusive
0x180048e3c  xor     eax, eax
0x180048e3e  add     rsp, 68h
0x180048e42  pop     r15
0x180048e44  pop     r14
0x180048e46  pop     r13
0x180048e48  pop     r12
0x180048e4a  pop     rdi
0x180048e4b  pop     rsi
0x180048e4c  pop     rbx
0x180048e4d  pop     rbp
0x180048e4e  retn
```
