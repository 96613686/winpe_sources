# KSMidiDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)

- ea: `0x180048e60`
- end: `0x1800490f8`
- name: `?Initialize@KSMidiDevice@@MEAAJPEBGPEAXIW4_MidiTransport@@AEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z`
- size: `664`
- prototype: `int __high(const unsigned __int16 *, void *, unsigned int, enum _MidiTransport, unsigned int *, enum __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

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
- `0x1800483f4`
- `0x180048e60`
- `0x180049708`
- `0x18004a36c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048ec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048eae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048edd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048f90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048f99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048f90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048f99`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180048fbb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180048fbb`

## pseudocode

```c
__int64 __fastcall KSMidiDevice::Initialize(
        __int64 a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        int a5,
        unsigned int *a6,
        int a7)
{
  int v8; // r15d
  _QWORD *cotaskmem_string_nothrow; // rax
  void **v11; // rsi
  _QWORD *v12; // r14
  void *v13; // r15
  void *v14; // r12
  DWORD LastError; // ebx
  int v16; // ebx
  __int64 v17; // rdx
  __int64 *v19; // rax
  __int64 v20; // rdx
  KsHandleWrapper *v21; // rbx
  void *v22; // rbx
  HANDLE CurrentProcess; // rbx
  HANDLE v24; // rax
  const char *v25; // r9
  __int64 *v26; // rax
  __int64 v27; // rdx
  KsHandleWrapper *v28; // rbx
  KsHandleWrapper *v29; // rbx
  RTL_SRWLOCK *v30; // rcx
  int v31; // r8d
  unsigned int *v32; // rdx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-30h]
  void *Block; // [rsp+40h] [rbp-10h] BYREF
  KsHandleWrapper *v35; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  int v38; // [rsp+A8h] [rbp+58h]

  v38 = a4;
  *(_DWORD *)(a1 + 76) = a5;
  v8 = a4;
  cotaskmem_string_nothrow = (_QWORD *)wil::make_cotaskmem_string_nothrow((wil *)&pv, a2, (unsigned __int64)a3);
  v11 = (void **)(a1 + 64);
  v12 = cotaskmem_string_nothrow;
  if ( (_QWORD *)(a1 + 64) != cotaskmem_string_nothrow )
  {
    v13 = *v11;
    v14 = (void *)*cotaskmem_string_nothrow;
    if ( *v11 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v13);
      SetLastError(LastError);
    }
    v8 = v38;
    *v11 = v14;
    *v12 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !*v11 )
  {
    v16 = -2147024882;
    v17 = 49;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)(unsigned int)v16,
      dwDesiredAccess);
    return (unsigned int)v16;
  }
  if ( a3 )
  {
    pv = 0;
    CurrentProcess = GetCurrentProcess();
    v24 = GetCurrentProcess();
    if ( !DuplicateHandle(v24, a3, CurrentProcess, &pv, 0, 0, 2u) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x3E,
               (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
               v25);
    Block = *v11;
    v26 = (__int64 *)std::make_unique<KsHandleWrapper,unsigned short *,0>(&v35, &Block);
    v27 = *v26;
    *v26 = 0;
    v28 = *(KsHandleWrapper **)(a1 + 48);
    *(_QWORD *)(a1 + 48) = v27;
    if ( v28 )
    {
      KsHandleWrapper::~KsHandleWrapper(v28);
      operator delete(v28);
    }
    v29 = v35;
    if ( v35 )
    {
      KsHandleWrapper::~KsHandleWrapper(v35);
      operator delete(v29);
    }
    v30 = *(RTL_SRWLOCK **)(a1 + 48);
    Block = pv;
    KsHandleWrapper::SetHandle(v30);
    v16 = KsHandleWrapper::RegisterForNotifications(*(KsHandleWrapper **)(a1 + 48));
    if ( v16 < 0 )
    {
      v17 = 66;
      goto LABEL_9;
    }
  }
  else
  {
    pv = *v11;
    v19 = (__int64 *)std::make_unique<KsHandleWrapper,unsigned short *,0>(&Block, &pv);
    v20 = *v19;
    *v19 = 0;
    v21 = *(KsHandleWrapper **)(a1 + 48);
    *(_QWORD *)(a1 + 48) = v20;
    if ( v21 )
    {
      KsHandleWrapper::~KsHandleWrapper(v21);
      operator delete(v21);
    }
    v22 = Block;
    if ( Block )
    {
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)Block);
      operator delete(v22);
    }
    v16 = KsHandleWrapper::Open(*(KsHandleWrapper **)(a1 + 48));
    if ( v16 < 0 )
    {
      v17 = 55;
      goto LABEL_9;
    }
  }
  v31 = a7;
  v32 = a6;
  *(_DWORD *)(a1 + 72) = v8;
  v16 = KSMidiDevice::OpenStream(a1, v32, v31);
  if ( v16 < 0 )
  {
    v17 = 70;
    goto LABEL_9;
  }
  v16 = KSMidiDevice::PinSetState((KSMidiDevice *)a1, KSSTATE_ACQUIRE);
  if ( v16 < 0 )
  {
    v17 = 71;
    goto LABEL_9;
  }
  v16 = KSMidiDevice::PinSetState((KSMidiDevice *)a1, KSSTATE_PAUSE);
  if ( v16 < 0 )
  {
    v17 = 72;
    goto LABEL_9;
  }
  v16 = KSMidiDevice::PinSetState((KSMidiDevice *)a1, KSSTATE_RUN);
  if ( v16 < 0 )
  {
    v17 = 73;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x180048e60  mov     [rsp-38h+arg_8], rbx
0x180048e65  mov     [rsp-38h+arg_18], r9d
0x180048e6a  push    rbp
0x180048e6b  push    rsi
0x180048e6c  push    rdi
0x180048e6d  push    r12
0x180048e6f  push    r13
0x180048e71  push    r14
0x180048e73  push    r15
0x180048e75  mov     rbp, rsp
0x180048e78  sub     rsp, 50h
0x180048e7c  mov     eax, [rbp+arg_20]
0x180048e7f  mov     rdi, rcx
0x180048e82  mov     [rcx+4Ch], eax
0x180048e85  mov     r15d, r9d
0x180048e88  lea     rcx, [rbp+pv]; this
0x180048e8c  mov     r13, r8
0x180048e8f  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180048e94  lea     rsi, [rdi+40h]
0x180048e98  xor     r12d, r12d
0x180048e9b  mov     r14, rax
0x180048e9e  cmp     rsi, rax
0x180048ea1  jz      short loc_180048ED4
0x180048ea3  mov     r15, [rsi]
0x180048ea6  mov     r12, [rax]
0x180048ea9  test    r15, r15
0x180048eac  jz      short loc_180048EC7
0x180048eae  call    cs:__imp_GetLastError
0x180048eb4  mov     rcx, r15; pv
0x180048eb7  mov     ebx, eax
0x180048eb9  call    cs:__imp_CoTaskMemFree
0x180048ebf  mov     ecx, ebx; dwErrCode
0x180048ec1  call    cs:__imp_SetLastError
0x180048ec7  mov     r15d, [rbp+arg_18]
0x180048ecb  mov     [rsi], r12
0x180048ece  xor     r12d, r12d
0x180048ed1  mov     [r14], r12
0x180048ed4  mov     rcx, [rbp+pv]; pv
0x180048ed8  test    rcx, rcx
0x180048edb  jz      short loc_180048EE3
0x180048edd  call    cs:__imp_CoTaskMemFree
0x180048ee3  mov     rax, [rsi]
0x180048ee6  test    rax, rax
0x180048ee9  jnz     short loc_180048F0D
0x180048eeb  mov     ebx, 8007000Eh
0x180048ef0  lea     edx, [rax+31h]; void *
0x180048ef3  mov     rcx, [rbp+38h]; this
0x180048ef7  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180048efe  mov     r9d, ebx; char *
0x180048f01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f06  mov     eax, ebx
0x180048f08  jmp     loc_1800490E0
0x180048f0d  mov     r14d, 2
0x180048f13  test    r13, r13
0x180048f16  jnz     short loc_180048F8C
0x180048f18  lea     rdx, [rbp+pv]
0x180048f1c  mov     [rbp+pv], rax
0x180048f20  lea     rcx, [rbp+Block]
0x180048f24  call    ??$make_unique@VKsHandleWrapper@@PEAG$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAG@Z; std::make_unique<KsHandleWrapper,ushort *,0>(ushort * &&)
0x180048f29  mov     esi, 0D8h
0x180048f2e  mov     rdx, [rax]
0x180048f31  mov     [rax], r12
0x180048f34  mov     rbx, [rdi+30h]
0x180048f38  mov     [rdi+30h], rdx
0x180048f3c  test    rbx, rbx
0x180048f3f  jz      short loc_180048F53
0x180048f41  mov     rcx, rbx; this
0x180048f44  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180048f49  mov     edx, esi
0x180048f4b  mov     rcx, rbx; Block
0x180048f4e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048f53  mov     rbx, [rbp+Block]
0x180048f57  test    rbx, rbx
0x180048f5a  jz      short loc_180048F6F
0x180048f5c  mov     rcx, rbx; this
0x180048f5f  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180048f64  mov     rdx, rsi
0x180048f67  mov     rcx, rbx; Block
0x180048f6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048f6f  mov     rcx, [rdi+30h]; this
0x180048f73  call    ?Open@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::Open(void)
0x180048f78  mov     ebx, eax
0x180048f7a  test    eax, eax
0x180048f7c  jns     loc_180049065
0x180048f82  mov     edx, 37h ; '7'
0x180048f87  jmp     loc_180048EF3
0x180048f8c  mov     [rbp+pv], r12
0x180048f90  call    cs:__imp_GetCurrentProcess
0x180048f96  mov     rbx, rax
0x180048f99  call    cs:__imp_GetCurrentProcess
0x180048f9f  mov     [rsp+50h+dwOptions], r14d; dwOptions
0x180048fa4  lea     r9, [rbp+pv]; lpTargetHandle
0x180048fa8  mov     rcx, rax; hSourceProcessHandle
0x180048fab  mov     [rsp+50h+bInheritHandle], r12d; bInheritHandle
0x180048fb0  mov     r8, rbx; hTargetProcessHandle
0x180048fb3  mov     [rsp+50h+dwDesiredAccess], r12d; dwDesiredAccess
0x180048fb8  mov     rdx, r13; hSourceHandle
0x180048fbb  call    cs:__imp_DuplicateHandle
0x180048fc1  test    eax, eax
0x180048fc3  jnz     short loc_180048FDD
0x180048fc5  mov     rcx, [rbp+38h]; this
0x180048fc9  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180048fd0  lea     edx, [rax+3Eh]; void *
0x180048fd3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180048fd8  jmp     loc_1800490E0
0x180048fdd  mov     rax, [rsi]
0x180048fe0  lea     rdx, [rbp+Block]
0x180048fe4  lea     rcx, [rbp+var_8]
0x180048fe8  mov     [rbp+Block], rax
0x180048fec  call    ??$make_unique@VKsHandleWrapper@@PEAG$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAG@Z; std::make_unique<KsHandleWrapper,ushort *,0>(ushort * &&)
0x180048ff1  mov     esi, 0D8h
0x180048ff6  mov     rdx, [rax]
0x180048ff9  mov     [rax], r12
0x180048ffc  mov     rbx, [rdi+30h]
0x180049000  mov     [rdi+30h], rdx
0x180049004  test    rbx, rbx
0x180049007  jz      short loc_18004901B
0x180049009  mov     rcx, rbx; this
0x18004900c  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180049011  mov     edx, esi
0x180049013  mov     rcx, rbx; Block
0x180049016  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004901b  mov     rbx, [rbp+var_8]
0x18004901f  test    rbx, rbx
0x180049022  jz      short loc_180049037
0x180049024  mov     rcx, rbx; this
0x180049027  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x18004902c  mov     rdx, rsi
0x18004902f  mov     rcx, rbx; Block
0x180049032  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049037  mov     rax, [rbp+pv]
0x18004903b  lea     rdx, [rbp+Block]
0x18004903f  mov     rcx, [rdi+30h]; SRWLock
0x180049043  mov     [rbp+Block], rax
0x180049047  call    ?SetHandle@KsHandleWrapper@@QEAAXV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; KsHandleWrapper::SetHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x18004904c  mov     rcx, [rdi+30h]; this
0x180049050  call    ?RegisterForNotifications@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::RegisterForNotifications(void)
0x180049055  mov     ebx, eax
0x180049057  test    eax, eax
0x180049059  jns     short loc_180049065
0x18004905b  mov     edx, 42h ; 'B'
0x180049060  jmp     loc_180048EF3
0x180049065  mov     r8d, [rbp+arg_30]
0x180049069  mov     rcx, rdi
0x18004906c  mov     rdx, [rbp+arg_28]
0x180049070  mov     [rdi+48h], r15d
0x180049074  call    ?OpenStream@KSMidiDevice@@IEAAJAEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z; KSMidiDevice::OpenStream(ulong &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)
0x180049079  mov     ebx, eax
0x18004907b  test    eax, eax
0x18004907d  jns     short loc_180049089
0x18004907f  mov     edx, 46h ; 'F'
0x180049084  jmp     loc_180048EF3
0x180049089  mov     edx, 1; enum KSSTATE
0x18004908e  mov     rcx, rdi; this
0x180049091  call    ?PinSetState@KSMidiDevice@@IEAAJW4KSSTATE@@@Z; KSMidiDevice::PinSetState(KSSTATE)
0x180049096  mov     ebx, eax
0x180049098  test    eax, eax
0x18004909a  jns     short loc_1800490A6
0x18004909c  mov     edx, 47h ; 'G'
0x1800490a1  jmp     loc_180048EF3
0x1800490a6  mov     edx, r14d; enum KSSTATE
0x1800490a9  mov     rcx, rdi; this
0x1800490ac  call    ?PinSetState@KSMidiDevice@@IEAAJW4KSSTATE@@@Z; KSMidiDevice::PinSetState(KSSTATE)
0x1800490b1  mov     ebx, eax
0x1800490b3  test    eax, eax
0x1800490b5  jns     short loc_1800490C1
0x1800490b7  mov     edx, 48h ; 'H'
0x1800490bc  jmp     loc_180048EF3
0x1800490c1  mov     edx, 3; enum KSSTATE
0x1800490c6  mov     rcx, rdi; this
0x1800490c9  call    ?PinSetState@KSMidiDevice@@IEAAJW4KSSTATE@@@Z; KSMidiDevice::PinSetState(KSSTATE)
0x1800490ce  mov     ebx, eax
0x1800490d0  test    eax, eax
0x1800490d2  jns     short loc_1800490DE
0x1800490d4  mov     edx, 49h ; 'I'
0x1800490d9  jmp     loc_180048EF3
0x1800490de  xor     eax, eax
0x1800490e0  mov     rbx, [rsp+50h+arg_8]
0x1800490e8  add     rsp, 50h
0x1800490ec  pop     r15
0x1800490ee  pop     r14
0x1800490f0  pop     r13
0x1800490f2  pop     r12
0x1800490f4  pop     rdi
0x1800490f5  pop     rsi
0x1800490f6  pop     rbp
0x1800490f7  retn
```
