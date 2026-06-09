# CAudioPump::Start(__int64 *,ISaDeviceCallback *,IUnknown *)

- ea: `0x1400116e0`
- end: `0x1400119b2`
- name: `?Start@CAudioPump@@UEAAJPEA_JPEAUISaDeviceCallback@@PEAUIUnknown@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(CAudioPump *__hidden this, __int64 *, struct ISaDeviceCallback *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000c33c`
- `0x140010610`
- `0x1400116e0`
- `0x1400119b8`
- `0x140011ad4`
- `0x140011afc`
- `0x140011b90`
- `0x140011e00`
- `0x1400121d0`
- `0x140012250`
- `0x1400122f0`
- `0x14004c130`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011831`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001183e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011831`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001183e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400118c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400118c5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001196d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001196d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140011700`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140011700`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400117ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400117ec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400118b0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400118b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioPump::Start(CAudioPump *this, __int64 *a2, struct ISaDeviceCallback *a3, struct IUnknown *a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // rsi
  HANDLE *v8; // rbp
  __int64 v9; // r14
  void *v10; // rdx
  void *v11; // rax
  void *v12; // rcx
  void *v13; // rdx
  __int64 v14; // rcx
  HANDLE Thread; // rax
  const char *v16; // r9
  int LastError; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  void *v21; // rdx
  int v22; // eax
  void *v23; // rax
  int v24; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-48h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  if ( !*((_BYTE *)this + 72) )
  {
    LastError = -2005139437;
    v19 = 1030;
    goto LABEL_21;
  }
  v8 = (HANDLE *)((char *)this + 120);
  if ( (unsigned __int64)(*((_QWORD *)this + 15) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = -2005139434;
    v19 = 1033;
    goto LABEL_21;
  }
  v9 = *((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = a3;
  if ( a3 )
    (*(void (__fastcall **)(struct ISaDeviceCallback *))(*(_QWORD *)a3 + 8LL))(a3);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( a4 )
  {
    wil::com_ptr_t<IAudioStreamingResourceRegistration,wil::err_returncode_policy>::reset((char *)this + 4688);
    LastError = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a4->lpVtbl->QueryInterface)(
                  a4,
                  &GUID_be7a4789_2891_49b3_923e_dc97de058472,
                  (char *)this + 4688);
    if ( LastError < 0 )
    {
      v19 = 1041;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
        (const char *)(unsigned int)LastError,
        dwCreationFlags);
      goto LABEL_14;
    }
  }
  if ( !CAudioPump::IsOffload(this) )
    _InterlockedExchange((volatile __int32 *)this + 84, 2);
  *((_BYTE *)this + 76) = 0;
  wil::details::ResetEvent(*((wil::details **)this + 35), v10);
  *((_BYTE *)this + 4681) = 0;
  v11 = AERTGetDLLRTHeap();
  *((_BYTE *)this + 324) = (int)AERTLockHeap(v11) >= 0;
  *((_BYTE *)this + 325) = (int)AERTLockModuleSection(v12) >= 0;
  wil::details::ResetEvent(*((wil::details **)this + 33), v13);
  v14 = *((_QWORD *)this + 53);
  if ( v14 )
  {
    v23 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    ResetEvent(v23);
  }
  Thread = CreateThread(0, 0, *((LPTHREAD_START_ROUTINE *)this + 27), this, 0, (LPDWORD)this + 24);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 120,
    Thread);
  if ( (((unsigned __int64)*v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x439,
                  (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
                  v16);
LABEL_14:
    if ( v7 )
      LeaveCriticalSection(v7);
    return (unsigned int)LastError;
  }
  SetThreadPriority(*v8, 2);
  WaitForSingleObjectEx(*((HANDLE *)this + 33), 0x2710u, 0);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 84, 0, 0) )
  {
    v20 = *((_QWORD *)this + 13);
    v21 = (void *)*((_QWORD *)this + 37);
    if ( *((_QWORD *)this + 39) )
    {
      v22 = CAudioPump::SetTimer(this, v21, 2 * v20, 0);
      LastError = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x458,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
          (const char *)(unsigned int)v22,
          dwCreationFlagsa);
        CAudioPump::SignalAndWaitForThread(this);
        goto LABEL_14;
      }
    }
    else
    {
      v24 = CAudioPump::SetTimer(this, v21, v20, 1);
      LastError = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45D,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
          (const char *)(unsigned int)v24,
          dwCreationFlagsa);
        CAudioPump::SignalAndWaitForThread(this);
        goto LABEL_14;
      }
    }
  }
  if ( v7 )
    LeaveCriticalSection(v7);
  return 0;
}

```

## disassembly

```asm
0x1400116e0  push    rbx
0x1400116e2  push    rbp
0x1400116e3  push    rsi
0x1400116e4  push    rdi
0x1400116e5  push    r14
0x1400116e7  push    r15
0x1400116e9  sub     rsp, 38h
0x1400116ed  mov     r15, r9
0x1400116f0  mov     rbx, r8
0x1400116f3  mov     rdi, rcx
0x1400116f6  lea     rsi, [rcx+80h]
0x1400116fd  mov     rcx, rsi; lpCriticalSection
0x140011700  call    cs:__imp_EnterCriticalSection
0x140011706  cmp     byte ptr [rdi+48h], 0
0x14001170a  jz      loc_14001188B
0x140011710  lea     rbp, [rdi+78h]
0x140011714  mov     rax, [rbp+0]
0x140011718  dec     rax
0x14001171b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001171f  jbe     loc_14001193B
0x140011725  mov     r14, [rdi+148h]
0x14001172c  mov     [rdi+148h], rbx
0x140011733  test    rbx, rbx
0x140011736  jz      short loc_140011747
0x140011738  mov     rax, [rbx]
0x14001173b  mov     rcx, rbx
0x14001173e  mov     rax, [rax+8]
0x140011742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011747  test    r14, r14
0x14001174a  jnz     loc_14001194A
0x140011750  test    r15, r15
0x140011753  jnz     loc_140011853
0x140011759  mov     rcx, rdi; this
0x14001175c  call    ?IsOffload@CAudioPump@@QEAA_NXZ; CAudioPump::IsOffload(void)
0x140011761  mov     ebx, 2
0x140011766  test    al, al
0x140011768  jnz     short loc_140011772
0x14001176a  mov     eax, ebx
0x14001176c  xchg    eax, [rdi+150h]
0x140011772  mov     byte ptr [rdi+4Ch], 0
0x140011776  mov     rcx, [rdi+118h]; this
0x14001177d  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x140011782  mov     byte ptr [rdi+1249h], 0
0x140011789  call    ?AERTGetDLLRTHeap@@YAPEAXXZ; AERTGetDLLRTHeap(void)
0x14001178e  mov     rcx, rax; void *
0x140011791  call    ?AERTLockHeap@@YAJPEAX@Z; AERTLockHeap(void *)
0x140011796  shr     eax, 1Fh
0x140011799  xor     al, 1
0x14001179b  mov     [rdi+144h], al
0x1400117a1  call    ?AERTLockModuleSection@@YAJPEAX@Z; AERTLockModuleSection(void *)
0x1400117a6  shr     eax, 1Fh
0x1400117a9  xor     al, 1
0x1400117ab  mov     [rdi+145h], al
0x1400117b1  mov     rcx, [rdi+108h]; this
0x1400117b8  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1400117bd  mov     rcx, [rdi+1A8h]
0x1400117c4  test    rcx, rcx
0x1400117c7  jnz     loc_14001195E
0x1400117cd  lea     rax, [rdi+60h]
0x1400117d1  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1400117d6  mov     [rsp+68h+dwCreationFlags], 0; int
0x1400117de  mov     r9, rdi; lpParameter
0x1400117e1  mov     r8, [rdi+0D8h]; lpStartAddress
0x1400117e8  xor     edx, edx; dwStackSize
0x1400117ea  xor     ecx, ecx; lpThreadAttributes
0x1400117ec  call    cs:__imp_CreateThread
0x1400117f2  mov     rdx, rax
0x1400117f5  mov     rcx, rbp
0x1400117f8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400117fd  mov     rcx, [rbp+0]; hThread
0x140011801  lea     rax, [rcx+1]
0x140011805  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001180b  jnz     loc_1400118AE
0x140011811  mov     rcx, [rsp+68h]; this
0x140011816  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14001181d  mov     edx, 439h; void *
0x140011822  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140011827  mov     ebx, eax
0x140011829  test    rsi, rsi
0x14001182c  jz      short loc_140011837
0x14001182e  mov     rcx, rsi; lpCriticalSection
0x140011831  call    cs:__imp_LeaveCriticalSection
0x140011837  mov     eax, ebx
0x140011839  jmp     short loc_140011846
0x14001183b  mov     rcx, rsi; lpCriticalSection
0x14001183e  call    cs:__imp_LeaveCriticalSection
0x140011844  xor     eax, eax
0x140011846  add     rsp, 38h
0x14001184a  pop     r15
0x14001184c  pop     r14
0x14001184e  pop     rdi
0x14001184f  pop     rsi
0x140011850  pop     rbp
0x140011851  pop     rbx
0x140011852  retn
0x140011853  lea     rbx, [rdi+1250h]
0x14001185a  mov     rcx, rbx
0x14001185d  call    ?reset@?$com_ptr_t@UIAudioStreamingResourceRegistration@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAudioStreamingResourceRegistration,wil::err_returncode_policy>::reset(void)
0x140011862  mov     rax, [r15]
0x140011865  mov     r8, rbx
0x140011868  lea     rdx, _GUID_be7a4789_2891_49b3_923e_dc97de058472
0x14001186f  mov     rcx, r15
0x140011872  mov     rax, [rax]
0x140011875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001187a  mov     ebx, eax
0x14001187c  test    eax, eax
0x14001187e  jns     loc_140011759
0x140011884  mov     edx, 411h
0x140011889  jmp     short loc_140011895
0x14001188b  mov     ebx, 887C0013h
0x140011890  mov     edx, 406h; void *
0x140011895  mov     rcx, [rsp+68h]; this
0x14001189a  mov     r9d, ebx; char *
0x14001189d  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400118a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400118a9  jmp     loc_140011829
0x1400118ae  mov     edx, ebx; nPriority
0x1400118b0  call    cs:__imp_SetThreadPriority
0x1400118b6  xor     r8d, r8d; bAlertable
0x1400118b9  mov     edx, 2710h; dwMilliseconds
0x1400118be  mov     rcx, [rdi+108h]; hHandle
0x1400118c5  call    cs:__imp_WaitForSingleObjectEx
0x1400118cb  xor     ecx, ecx
0x1400118cd  xor     eax, eax
0x1400118cf  lock cmpxchg [rdi+150h], ecx
0x1400118d7  jz      short loc_140011905
0x1400118d9  mov     r8, [rdi+68h]; __int64
0x1400118dd  mov     rdx, [rdi+128h]; void *
0x1400118e4  cmp     [rdi+138h], rcx
0x1400118eb  mov     rcx, rdi; this
0x1400118ee  jz      loc_140011978
0x1400118f4  add     r8, r8; __int64
0x1400118f7  xor     r9d, r9d; bool
0x1400118fa  call    ?SetTimer@CAudioPump@@AEAAJPEAX_J_N@Z; CAudioPump::SetTimer(void *,__int64,bool)
0x1400118ff  mov     ebx, eax
0x140011901  test    eax, eax
0x140011903  js      short loc_140011913
0x140011905  test    rsi, rsi
0x140011908  jz      loc_140011844
0x14001190e  jmp     loc_14001183B
0x140011913  mov     rcx, [rsp+68h]; this
0x140011918  mov     r9d, ebx; char *
0x14001191b  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140011922  mov     edx, 458h; void *
0x140011927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001192c  nop
0x14001192d  mov     rcx, rdi; this
0x140011930  call    ?SignalAndWaitForThread@CAudioPump@@AEAAXXZ; CAudioPump::SignalAndWaitForThread(void)
0x140011935  nop
0x140011936  jmp     loc_140011829
0x14001193b  mov     ebx, 887C0016h
0x140011940  mov     edx, 409h
0x140011945  jmp     loc_140011895
0x14001194a  mov     rax, [r14]
0x14001194d  mov     rcx, r14
0x140011950  mov     rax, [rax+10h]
0x140011954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011959  jmp     loc_140011750
0x14001195e  mov     rax, [rcx]
0x140011961  mov     rax, [rax+18h]
0x140011965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001196a  mov     rcx, rax; hEvent
0x14001196d  call    cs:__imp_ResetEvent
0x140011973  jmp     loc_1400117CD
0x140011978  mov     r9b, 1; bool
0x14001197b  call    ?SetTimer@CAudioPump@@AEAAJPEAX_J_N@Z; CAudioPump::SetTimer(void *,__int64,bool)
0x140011980  mov     ebx, eax
0x140011982  test    eax, eax
0x140011984  jns     loc_140011905
0x14001198a  mov     rcx, [rsp+68h]; this
0x14001198f  mov     r9d, eax; char *
0x140011992  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140011999  mov     edx, 45Dh; void *
0x14001199e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400119a3  nop
0x1400119a4  mov     rcx, rdi; this
0x1400119a7  call    ?SignalAndWaitForThread@CAudioPump@@AEAAXXZ; CAudioPump::SignalAndWaitForThread(void)
0x1400119ac  nop
0x1400119ad  jmp     loc_140011829
```
