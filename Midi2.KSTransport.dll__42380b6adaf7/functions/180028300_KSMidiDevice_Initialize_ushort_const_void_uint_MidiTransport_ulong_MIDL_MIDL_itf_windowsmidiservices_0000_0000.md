# KSMidiDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)

- ea: `0x180028300`
- end: `0x180028598`
- name: `?Initialize@KSMidiDevice@@MEAAJPEBGPEAXIW4_MidiTransport@@AEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, void *, int, int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

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
- `0x180027890`
- `0x180028300`
- `0x180028bc8`
- `0x18002982c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028361`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002834e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002834e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002837d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002837d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028430`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028430`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028439`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002845b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002845b`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall KSMidiDevice::Initialize(
        __int64 a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        int a5,
        __int64 a6,
        unsigned int a7)
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
  __int64 v31; // r8
  __int64 v32; // rdx
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
0x180028300  mov     [rsp-38h+arg_8], rbx
0x180028305  mov     [rsp-38h+arg_18], r9d
0x18002830a  push    rbp
0x18002830b  push    rsi
0x18002830c  push    rdi
0x18002830d  push    r12
0x18002830f  push    r13
0x180028311  push    r14
0x180028313  push    r15
0x180028315  mov     rbp, rsp
0x180028318  sub     rsp, 50h
0x18002831c  mov     eax, [rbp+arg_20]
0x18002831f  mov     rdi, rcx
0x180028322  mov     [rcx+4Ch], eax
0x180028325  mov     r15d, r9d
0x180028328  lea     rcx, [rbp+pv]; this
0x18002832c  mov     r13, r8
0x18002832f  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180028334  lea     rsi, [rdi+40h]
0x180028338  xor     r12d, r12d
0x18002833b  mov     r14, rax
0x18002833e  cmp     rsi, rax
0x180028341  jz      short loc_180028374
0x180028343  mov     r15, [rsi]
0x180028346  mov     r12, [rax]
0x180028349  test    r15, r15
0x18002834c  jz      short loc_180028367
0x18002834e  call    cs:__imp_GetLastError
0x180028354  mov     rcx, r15; pv
0x180028357  mov     ebx, eax
0x180028359  call    cs:__imp_CoTaskMemFree
0x18002835f  mov     ecx, ebx; dwErrCode
0x180028361  call    cs:__imp_SetLastError
0x180028367  mov     r15d, [rbp+arg_18]
0x18002836b  mov     [rsi], r12
0x18002836e  xor     r12d, r12d
0x180028371  mov     [r14], r12
0x180028374  mov     rcx, [rbp+pv]; pv
0x180028378  test    rcx, rcx
0x18002837b  jz      short loc_180028383
0x18002837d  call    cs:__imp_CoTaskMemFree
0x180028383  mov     rax, [rsi]
0x180028386  test    rax, rax
0x180028389  jnz     short loc_1800283AD
0x18002838b  mov     ebx, 8007000Eh
0x180028390  lea     edx, [rax+31h]; void *
0x180028393  mov     rcx, [rbp+38h]; this
0x180028397  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18002839e  mov     r9d, ebx; char *
0x1800283a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800283a6  mov     eax, ebx
0x1800283a8  jmp     loc_180028580
0x1800283ad  mov     r14d, 2
0x1800283b3  test    r13, r13
0x1800283b6  jnz     short loc_18002842C
0x1800283b8  lea     rdx, [rbp+pv]
0x1800283bc  mov     [rbp+pv], rax
0x1800283c0  lea     rcx, [rbp+Block]
0x1800283c4  call    ??$make_unique@VKsHandleWrapper@@PEAG$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAG@Z; std::make_unique<KsHandleWrapper,ushort *,0>(ushort * &&)
0x1800283c9  mov     esi, 0D8h
0x1800283ce  mov     rdx, [rax]
0x1800283d1  mov     [rax], r12
0x1800283d4  mov     rbx, [rdi+30h]
0x1800283d8  mov     [rdi+30h], rdx
0x1800283dc  test    rbx, rbx
0x1800283df  jz      short loc_1800283F3
0x1800283e1  mov     rcx, rbx; this
0x1800283e4  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x1800283e9  mov     edx, esi
0x1800283eb  mov     rcx, rbx; Block
0x1800283ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800283f3  mov     rbx, [rbp+Block]
0x1800283f7  test    rbx, rbx
0x1800283fa  jz      short loc_18002840F
0x1800283fc  mov     rcx, rbx; this
0x1800283ff  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180028404  mov     rdx, rsi
0x180028407  mov     rcx, rbx; Block
0x18002840a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002840f  mov     rcx, [rdi+30h]; this
0x180028413  call    ?Open@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::Open(void)
0x180028418  mov     ebx, eax
0x18002841a  test    eax, eax
0x18002841c  jns     loc_180028505
0x180028422  mov     edx, 37h ; '7'
0x180028427  jmp     loc_180028393
0x18002842c  mov     [rbp+pv], r12
0x180028430  call    cs:__imp_GetCurrentProcess
0x180028436  mov     rbx, rax
0x180028439  call    cs:__imp_GetCurrentProcess
0x18002843f  mov     [rsp+50h+dwOptions], r14d; dwOptions
0x180028444  lea     r9, [rbp+pv]; lpTargetHandle
0x180028448  mov     rcx, rax; hSourceProcessHandle
0x18002844b  mov     [rsp+50h+bInheritHandle], r12d; bInheritHandle
0x180028450  mov     r8, rbx; hTargetProcessHandle
0x180028453  mov     [rsp+50h+dwDesiredAccess], r12d; dwDesiredAccess
0x180028458  mov     rdx, r13; hSourceHandle
0x18002845b  call    cs:__imp_DuplicateHandle
0x180028461  test    eax, eax
0x180028463  jnz     short loc_18002847D
0x180028465  mov     rcx, [rbp+38h]; this
0x180028469  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180028470  lea     edx, [rax+3Eh]; void *
0x180028473  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028478  jmp     loc_180028580
0x18002847d  mov     rax, [rsi]
0x180028480  lea     rdx, [rbp+Block]
0x180028484  lea     rcx, [rbp+var_8]
0x180028488  mov     [rbp+Block], rax
0x18002848c  call    ??$make_unique@VKsHandleWrapper@@PEAG$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAG@Z; std::make_unique<KsHandleWrapper,ushort *,0>(ushort * &&)
0x180028491  mov     esi, 0D8h
0x180028496  mov     rdx, [rax]
0x180028499  mov     [rax], r12
0x18002849c  mov     rbx, [rdi+30h]
0x1800284a0  mov     [rdi+30h], rdx
0x1800284a4  test    rbx, rbx
0x1800284a7  jz      short loc_1800284BB
0x1800284a9  mov     rcx, rbx; this
0x1800284ac  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x1800284b1  mov     edx, esi
0x1800284b3  mov     rcx, rbx; Block
0x1800284b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800284bb  mov     rbx, [rbp+var_8]
0x1800284bf  test    rbx, rbx
0x1800284c2  jz      short loc_1800284D7
0x1800284c4  mov     rcx, rbx; this
0x1800284c7  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x1800284cc  mov     rdx, rsi
0x1800284cf  mov     rcx, rbx; Block
0x1800284d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800284d7  mov     rax, [rbp+pv]
0x1800284db  lea     rdx, [rbp+Block]
0x1800284df  mov     rcx, [rdi+30h]; SRWLock
0x1800284e3  mov     [rbp+Block], rax
0x1800284e7  call    ?SetHandle@KsHandleWrapper@@QEAAXV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; KsHandleWrapper::SetHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x1800284ec  mov     rcx, [rdi+30h]; this
0x1800284f0  call    ?RegisterForNotifications@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::RegisterForNotifications(void)
0x1800284f5  mov     ebx, eax
0x1800284f7  test    eax, eax
0x1800284f9  jns     short loc_180028505
0x1800284fb  mov     edx, 42h ; 'B'
0x180028500  jmp     loc_180028393
0x180028505  mov     r8d, [rbp+arg_30]
0x180028509  mov     rcx, rdi
0x18002850c  mov     rdx, [rbp+arg_28]
0x180028510  mov     [rdi+48h], r15d
0x180028514  call    ?OpenStream@KSMidiDevice@@IEAAJAEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z; KSMidiDevice::OpenStream(ulong &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)
0x180028519  mov     ebx, eax
0x18002851b  test    eax, eax
0x18002851d  jns     short loc_180028529
0x18002851f  mov     edx, 46h ; 'F'
0x180028524  jmp     loc_180028393
0x180028529  mov     edx, 1; enum KSSTATE
0x18002852e  mov     rcx, rdi; this
0x180028531  call    ?PinSetState@KSMidiDevice@@IEAAJW4KSSTATE@@@Z; KSMidiDevice::PinSetState(KSSTATE)
0x180028536  mov     ebx, eax
0x180028538  test    eax, eax
0x18002853a  jns     short loc_180028546
0x18002853c  mov     edx, 47h ; 'G'
0x180028541  jmp     loc_180028393
0x180028546  mov     edx, r14d; enum KSSTATE
0x180028549  mov     rcx, rdi; this
0x18002854c  call    ?PinSetState@KSMidiDevice@@IEAAJW4KSSTATE@@@Z; KSMidiDevice::PinSetState(KSSTATE)
0x180028551  mov     ebx, eax
0x180028553  test    eax, eax
0x180028555  jns     short loc_180028561
0x180028557  mov     edx, 48h ; 'H'
0x18002855c  jmp     loc_180028393
0x180028561  mov     edx, 3; enum KSSTATE
0x180028566  mov     rcx, rdi; this
0x180028569  call    ?PinSetState@KSMidiDevice@@IEAAJW4KSSTATE@@@Z; KSMidiDevice::PinSetState(KSSTATE)
0x18002856e  mov     ebx, eax
0x180028570  test    eax, eax
0x180028572  jns     short loc_18002857E
0x180028574  mov     edx, 49h ; 'I'
0x180028579  jmp     loc_180028393
0x18002857e  xor     eax, eax
0x180028580  mov     rbx, [rsp+50h+arg_8]
0x180028588  add     rsp, 50h
0x18002858c  pop     r15
0x18002858e  pop     r14
0x180028590  pop     r13
0x180028592  pop     r12
0x180028594  pop     rdi
0x180028595  pop     rsi
0x180028596  pop     rbp
0x180028597  retn
```
