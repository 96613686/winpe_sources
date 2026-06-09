# SrvOdbLaunchBackgroundTaskInternal(void *,void *,uchar const *,ulong,ulong,ulong,ushort const *,ushort const *,_GUID *,uchar *,ulong,_OdbLaunchInfo *,_GUID *,_GUID *)

- ea: `0x18002823c`
- end: `0x18002888c`
- name: `?SrvOdbLaunchBackgroundTaskInternal@@YAJPEAX0PEBEKKKPEBG2PEAU_GUID@@PEAEKPEAU_OdbLaunchInfo@@33@Z`
- size: `1616`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, PSID pSid, PSID Sid, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, unsigned __int8 *, size_t size, struct _OdbLaunchInfo *, struct _GUID *, struct _GUID *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180069bb0`
- `0x18006a1f0`

## callees

- `0x18000da30`
- `0x18002823c`
- `0x180028894`
- `0x180028d04`
- `0x180028d2c`
- `0x180028d8c`
- `0x180028f50`
- `0x180029144`
- `0x180029454`
- `0x180029ed4`
- `0x18004079c`
- `0x18006fec8`
- `0x1800905e4`
- `0x1800906d8`
- `0x180094662`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180028316`
- `ntdll!RtlAllocateHeap` at `0x18002846f`
- `ntdll!RtlAllocateHeap` at `0x1800284bc`
- `ntdll!RtlAllocateHeap` at `0x180028316`
- `ntdll!RtlAllocateHeap` at `0x18002846f`
- `ntdll!RtlAllocateHeap` at `0x1800284bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028529`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028529`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800286cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800286cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002839f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002839f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180028827`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180028827`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180028392`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180028392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028403`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028403`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180028351`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180028351`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180028366`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180028366`

## pseudocode

```c
__int64 __fastcall SrvOdbLaunchBackgroundTaskInternal(
        RPC_BINDING_HANDLE Binding,
        PSID pSid,
        PSID Sid,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        struct _GUID *a9,
        unsigned __int8 *a10,
        size_t size,
        struct _OdbLaunchInfo *a12,
        struct _GUID *a13,
        struct _GUID *a14)
{
  PSID v14; // r10
  RPC_BINDING_HANDLE v15; // rdi
  struct _GUID *v16; // r15
  OnDemandBroker *v17; // r14
  struct _OdbLaunchInfo *v18; // r12
  __int64 v19; // r13
  struct _OdbLaunchInfo *Heap; // rax
  struct _OdbLaunchInfo *v21; // rbx
  HANDLE v22; // r15
  signed int LastError; // eax
  signed int Instance; // edi
  bool v25; // cc
  BackgroundTask *v26; // rax
  BackgroundTask *v27; // rbx
  __int16 v28; // r9
  __int64 v29; // rax
  SIZE_T v30; // rsi
  PVOID v31; // rax
  unsigned int v32; // edx
  PVOID v33; // rax
  volatile signed __int32 *v34; // rax
  unsigned int v35; // edx
  volatile signed __int32 *v36; // rsi
  struct _RTL_CRITICAL_SECTION *v37; // rbx
  char *v38; // rcx
  char *v39; // rax
  char *v40; // r13
  __int64 v41; // rdx
  BackgroundExecutionSession *v42; // r13
  volatile signed __int32 *v43; // r12
  signed int v44; // r14d
  _QWORD *v45; // rax
  __int64 v46; // r8
  __int64 v47; // r9
  _QWORD *v48; // rcx
  _QWORD *v49; // r10
  __int128 v51; // xmm0
  void *v52; // rax
  struct _GUID *v53; // r15
  OnDemandBroker *v54; // [rsp+40h] [rbp-69h]
  unsigned int Pid[2]; // [rsp+48h] [rbp-61h] BYREF
  struct _GUID *v56; // [rsp+50h] [rbp-59h] BYREF
  utl::_RefCountBase *v57; // [rsp+58h] [rbp-51h]
  void *v58; // [rsp+60h] [rbp-49h] BYREF
  volatile signed __int32 *v59; // [rsp+68h] [rbp-41h]
  void *Src; // [rsp+70h] [rbp-39h]
  void *v61; // [rsp+78h] [rbp-31h]
  void *v62; // [rsp+80h] [rbp-29h]
  PSID v63; // [rsp+88h] [rbp-21h]
  struct _GUID v64; // [rsp+90h] [rbp-19h] BYREF

  v14 = pSid;
  v15 = Binding;
  v16 = a13;
  v61 = a8;
  v56 = a14;
  v63 = Sid;
  v62 = pSid;
  *(_QWORD *)Pid = Binding;
  Src = a7;
  v58 = a10;
  *(_QWORD *)&v64.Data1 = a13;
  if ( Sid )
  {
    if ( !IsValidSid(Sid, a4) )
      return (unsigned int)-805306128;
    Sid = v63;
    v14 = v62;
  }
  if ( a10 )
  {
    if ( !(_DWORD)size || !a9 )
      return (unsigned int)-805306320;
  }
  else if ( (_DWORD)size )
  {
    return (unsigned int)-805306320;
  }
  if ( Sid
    && (!IsWellKnownSid(v14, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid)
     || !OdbpDoesPlatformAndPackageSupportMua(a7)) )
  {
    return (unsigned int)-805306320;
  }
  v17 = OnDemandBroker::s_instance;
  if ( !OnDemandBroker::s_instance )
  {
    Instance = OnDemandBroker::CreateInstance();
    if ( Instance < 0 )
      return (unsigned int)Instance;
    v17 = OnDemandBroker::s_instance;
    v15 = *(RPC_BINDING_HANDLE *)Pid;
  }
  v18 = 0;
  Pid[0] = 0;
  v19 = -1;
  if ( !a12 )
    goto LABEL_21;
  Heap = (struct _OdbLaunchInfo *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
  v21 = Heap;
  if ( !Heap )
    return (unsigned int)-2147024882;
  v22 = 0;
  *(_OWORD *)Heap = *(_OWORD *)a12;
  *((_QWORD *)Heap + 2) = *((_QWORD *)a12 + 2);
  *(_QWORD *)Heap = 0;
  if ( *(_QWORD *)a12 )
  {
    LastError = I_RpcBindingInqLocalClientPID(v15, Pid);
    Instance = LastError;
    v25 = LastError <= 0;
    if ( LastError )
    {
LABEL_13:
      if ( !v25 )
        Instance = (unsigned __int16)LastError | 0x80070000;
      if ( Instance < 0 )
        OdbpLaunchInfoDestroy(v21);
      goto LABEL_17;
    }
    v22 = OpenProcess(0x40u, 0, Pid[0]);
    if ( !v22 || !DuplicateHandle(v22, *(HANDLE *)a12, (HANDLE)0xFFFFFFFFFFFFFFFFLL, (LPHANDLE)v21, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v25 = LastError <= 0;
      Instance = LastError;
      goto LABEL_13;
    }
  }
  v18 = v21;
  Instance = 0;
LABEL_17:
  if ( v22 )
    CloseHandle(v22);
  if ( Instance < 0 )
    goto LABEL_23;
  v16 = *(struct _GUID **)&v64.Data1;
LABEL_21:
  v26 = (BackgroundTask *)operator new(0x78u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v26 || (v27 = BackgroundTask::BackgroundTask(v26, a6, v16)) == 0 )
  {
    Instance = -2147024882;
    goto LABEL_23;
  }
  v29 = -1;
  do
    ++v29;
  while ( *((_WORD *)Src + v29) != v28 );
  v30 = 2 * v29 + 2;
  v31 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
  *((_QWORD *)v27 + 4) = v31;
  Instance = -2147024882;
  if ( !v31 )
    goto LABEL_36;
  memcpy_0(v31, Src, v30);
  do
    ++v19;
  while ( *((_WORD *)v61 + v19) );
  v33 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v19 + 2);
  *((_QWORD *)v27 + 6) = v33;
  if ( !v33 )
  {
LABEL_36:
    BackgroundTask::`scalar deleting destructor'(v27, v32);
    Instance = -2147024882;
LABEL_23:
    if ( v18 )
      OdbpLaunchInfoDestroy(v18);
    return (unsigned int)Instance;
  }
  memcpy_0(v33, v61, 2 * v19 + 2);
  if ( a9 )
  {
    v51 = (__int128)*a9;
    *((_DWORD *)v27 + 24) = size;
    *(_OWORD *)((char *)v27 + 68) = v51;
    v52 = MIDL_user_allocate((unsigned int)size);
    *((_QWORD *)v27 + 11) = v52;
    if ( !v52 )
      goto LABEL_36;
    memcpy_0(v52, v58, (unsigned int)size);
  }
  if ( v18 )
    *((_QWORD *)v27 + 13) = v18;
  v53 = (struct _GUID *)v27;
  v54 = v17;
  v34 = (volatile signed __int32 *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v36 = v34;
  if ( v34 )
  {
    *((_DWORD *)v34 + 2) = 1;
    *((_DWORD *)v34 + 3) = 1;
    *(_QWORD *)v34 = &utl::_RefCountVtable<utl::_RefCountNormal<BackgroundTask *,utl::default_delete<BackgroundTask>,utl::allocator<int>>,0>::`vftable';
    *((_QWORD *)v34 + 2) = v27;
    _InterlockedIncrement(v34 + 2);
    v37 = (struct _RTL_CRITICAL_SECTION *)((char *)v17 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v17 + 16));
    v38 = (char *)v17 + 56;
    if ( *((OnDemandBroker **)v17 + 9) == (OnDemandBroker *)((char *)v17 + 56) )
      goto LABEL_44;
    v39 = *(char **)v38;
    v40 = (char *)v17 + 56;
    v54 = v17;
    do
    {
      if ( *((_DWORD *)v39 + 6) < a6 )
      {
        v41 = 16;
      }
      else
      {
        v40 = v39;
        v41 = 8;
      }
      v39 = *(char **)&v39[v41];
    }
    while ( v39 != (char *)&utl::_TreeSentinel );
    if ( v40 == v38 || a6 < *((_DWORD *)v40 + 6) )
    {
LABEL_44:
      v42 = 0;
      v43 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    }
    else
    {
      v43 = (volatile signed __int32 *)*((_QWORD *)v40 + 5);
      v42 = (BackgroundExecutionSession *)*((_QWORD *)v40 + 4);
      if ( v43 )
        _InterlockedIncrement(v43 + 2);
    }
    if ( v42 )
    {
      if ( BackgroundExecutionSession::IsOwner(v42, v62) && *((_DWORD *)v42 + 4) == a5 )
      {
        v58 = v53;
        v59 = v36;
        if ( v36 )
          _InterlockedIncrement(v36 + 2);
        v44 = BackgroundExecutionSession::LaunchBackgroundTask(v42);
        if ( v44 >= 0 )
        {
          v56 = v53;
          v57 = (utl::_RefCountBase *)v36;
          if ( v36 )
            _InterlockedIncrement(v36 + 2);
          v45 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
          if ( v45 )
          {
            utl::shared_ptr<BackgroundTask>::shared_ptr<BackgroundTask>(v45 + 2, &v56);
            v48 = *(_QWORD **)(v47 + 8);
            v49[1] = v48;
            *v49 = v47;
            *v48 = v49;
            *(_QWORD *)(v47 + 8) = v49;
            ++*(_QWORD *)(v47 + 16);
            if ( v36 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v36);
            v56 = v53;
            v57 = (utl::_RefCountBase *)v36;
            if ( v36 )
              _InterlockedIncrement(v36 + 2);
            v64 = *v53;
            utl::_Tree<_GUID,utl::pair<_GUID const,utl::shared_ptr<BackgroundTask>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::shared_ptr<BackgroundTask>>>,0>::_TryEmplace<_GUID,utl::shared_ptr<BackgroundTask> &>(
              (void ***)v54 + 11,
              (__int64)&v58,
              v46,
              &v64,
              (__int64)&v56);
            if ( v58 )
              v44 = (_BYTE)v59 == 0 ? 0x800700B7 : 0;
            else
              v44 = -2147024882;
            if ( v57 )
              utl::_RefCountBase::_DecStrong(v57);
            if ( v44 >= 0 )
              v44 = 0;
          }
          else
          {
            if ( v36 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v36);
            v44 = -2147024882;
          }
        }
      }
      else
      {
        v44 = -2147024891;
      }
    }
    else
    {
      v44 = -2147023728;
    }
    LeaveCriticalSection(v37);
    if ( v43 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v43);
    if ( v36 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v36);
    Instance = v44;
    if ( v44 >= 0 )
      Instance = 0;
    if ( v36 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v36);
  }
  else
  {
    BackgroundTask::`scalar deleting destructor'(v27, v35);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002823c  mov     [rsp-8+arg_18], rbx
0x180028241  push    rbp
0x180028242  push    rsi
0x180028243  push    rdi
0x180028244  push    r12
0x180028246  push    r13
0x180028248  push    r14
0x18002824a  push    r15
0x18002824c  lea     rbp, [rsp-7]
0x180028251  sub     rsp, 0B0h
0x180028258  mov     rax, cs:__security_cookie
0x18002825f  xor     rax, rsp
0x180028262  mov     [rbp+37h+var_40], rax
0x180028266  mov     rax, [rbp+37h+arg_38]
0x18002826a  xor     r13d, r13d
0x18002826d  mov     rbx, [rbp+37h+arg_30]
0x180028271  mov     r10, rdx
0x180028274  mov     r14, [rbp+37h+arg_48]
0x18002827b  mov     rdi, rcx
0x18002827e  mov     r15, [rbp+37h+arg_60]
0x180028285  mov     rsi, [rbp+37h+arg_58]
0x18002828c  mov     [rbp+37h+var_68], rax
0x180028290  mov     rax, [rbp+37h+arg_68]
0x180028297  mov     [rbp+37h+var_90], rax
0x18002829b  mov     [rbp+37h+var_58], r8
0x18002829f  mov     [rbp+37h+var_60], rdx
0x1800282a3  mov     qword ptr [rbp+37h+Pid], rcx
0x1800282a7  mov     [rbp+37h+Src], rbx
0x1800282ab  mov     [rbp+37h+var_80], r14
0x1800282af  mov     qword ptr [rbp+37h+var_50], r15
0x1800282b3  test    r8, r8
0x1800282b6  jnz     loc_1800287F9
0x1800282bc  test    r14, r14
0x1800282bf  jnz     loc_18002840B
0x1800282c5  cmp     dword ptr [rbp+37h+size], r13d
0x1800282cc  jnz     loc_180028421
0x1800282d2  test    r8, r8
0x1800282d5  jnz     loc_18002881F
0x1800282db  mov     r14, cs:?s_instance@OnDemandBroker@@0PEAV1@EA; OnDemandBroker * OnDemandBroker::s_instance
0x1800282e2  mov     [rbp+37h+var_A0], r14
0x1800282e6  test    r14, r14
0x1800282e9  jz      loc_18002884A
0x1800282ef  mov     r12, r13
0x1800282f2  mov     [rbp+37h+Pid], r13d
0x1800282f6  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800282fa  test    rsi, rsi
0x1800282fd  jz      loc_1800283C4
0x180028303  mov     rcx, gs:60h
0x18002830c  lea     r8d, [r13+19h]; Size
0x180028310  xor     edx, edx; Flags
0x180028312  mov     rcx, [rcx+30h]; HeapHandle
0x180028316  call    cs:__imp_RtlAllocateHeap
0x18002831c  xor     r9d, r9d
0x18002831f  mov     rbx, rax
0x180028322  test    rax, rax
0x180028325  jz      loc_18002886D
0x18002832b  movups  xmm0, xmmword ptr [rsi]
0x18002832e  mov     r15d, r9d
0x180028331  movups  xmmword ptr [rax], xmm0
0x180028334  movsd   xmm1, qword ptr [rsi+10h]
0x180028339  movsd   qword ptr [rax+10h], xmm1
0x18002833e  mov     [rax], r9
0x180028341  cmp     [rsi], r9
0x180028344  jz      loc_1800283F8
0x18002834a  lea     rdx, [rbp+37h+Pid]; Pid
0x18002834e  mov     rcx, rdi; Binding
0x180028351  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180028357  mov     edi, eax
0x180028359  test    eax, eax
0x18002835b  jnz     short loc_1800283A9
0x18002835d  mov     r8d, [rbp+37h+Pid]; dwProcessId
0x180028361  lea     ecx, [rax+40h]; dwDesiredAccess
0x180028364  xor     edx, edx; bInheritHandle
0x180028366  call    cs:__imp_OpenProcess
0x18002836c  mov     r15, rax
0x18002836f  xor     eax, eax
0x180028371  test    r15, r15
0x180028374  jz      short loc_18002839F
0x180028376  mov     rdx, [rsi]; hSourceHandle
0x180028379  mov     r9, rbx; lpTargetHandle
0x18002837c  mov     [rsp+0E0h+dwOptions], 2; dwOptions
0x180028384  mov     r8, r13; hTargetProcessHandle
0x180028387  mov     [rsp+0E0h+bInheritHandle], eax; bInheritHandle
0x18002838b  mov     rcx, r15; hSourceProcessHandle
0x18002838e  mov     [rsp+0E0h+dwDesiredAccess], eax; dwDesiredAccess
0x180028392  call    cs:__imp_DuplicateHandle
0x180028398  xor     r9d, r9d
0x18002839b  test    eax, eax
0x18002839d  jnz     short loc_1800283F8
0x18002839f  call    cs:__imp_GetLastError
0x1800283a5  test    eax, eax
0x1800283a7  mov     edi, eax
0x1800283a9  jg      loc_1800287CE
0x1800283af  test    edi, edi
0x1800283b1  js      loc_180028877
0x1800283b7  test    r15, r15
0x1800283ba  jnz     short loc_180028400
0x1800283bc  test    edi, edi
0x1800283be  js      short loc_1800283E2
0x1800283c0  mov     r15, qword ptr [rbp+37h+var_50]
0x1800283c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800283cb  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800283d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800283d5  xor     r9d, r9d
0x1800283d8  test    rax, rax
0x1800283db  jnz     short loc_18002842B
0x1800283dd  mov     edi, 8007000Eh
0x1800283e2  test    r12, r12
0x1800283e5  jz      loc_180028702
0x1800283eb  mov     rcx, r12; struct _OdbLaunchInfo *
0x1800283ee  call    ?OdbpLaunchInfoDestroy@@YAXPEAU_OdbLaunchInfo@@@Z; OdbpLaunchInfoDestroy(_OdbLaunchInfo *)
0x1800283f3  jmp     loc_180028702
0x1800283f8  mov     r12, rbx
0x1800283fb  mov     edi, r9d
0x1800283fe  jmp     short loc_1800283B7
0x180028400  mov     rcx, r15; hObject
0x180028403  call    cs:__imp_CloseHandle
0x180028409  jmp     short loc_1800283BC
0x18002840b  cmp     dword ptr [rbp+37h+size], r13d
0x180028412  jz      short loc_180028421
0x180028414  cmp     [rbp+37h+arg_40], r13
0x18002841b  jnz     loc_1800282D2
0x180028421  mov     edi, 0D0000030h
0x180028426  jmp     loc_180028702
0x18002842b  mov     edx, [rbp+37h+arg_28]; unsigned int
0x18002842e  mov     r8, r15; struct _GUID *
0x180028431  mov     rcx, rax; this
0x180028434  call    ??0BackgroundTask@@QEAA@KPEAU_GUID@@@Z; BackgroundTask::BackgroundTask(ulong,_GUID *)
0x180028439  mov     rbx, rax
0x18002843c  test    rax, rax
0x18002843f  jz      short loc_1800283DD
0x180028441  mov     rcx, [rbp+37h+Src]
0x180028445  mov     r15, r9
0x180028448  mov     rax, r13
0x18002844b  inc     rax
0x18002844e  cmp     [rcx+rax*2], r9w
0x180028453  jnz     short loc_18002844B
0x180028455  mov     rcx, gs:60h
0x18002845e  lea     rsi, ds:2[rax*2]
0x180028466  mov     r8, rsi; Size
0x180028469  xor     edx, edx; Flags
0x18002846b  mov     rcx, [rcx+30h]; HeapHandle
0x18002846f  call    cs:__imp_RtlAllocateHeap
0x180028475  mov     [rbx+20h], rax
0x180028479  mov     edi, 8007000Eh
0x18002847e  test    rax, rax
0x180028481  jz      short loc_1800284D3
0x180028483  mov     rdx, [rbp+37h+Src]; Src
0x180028487  mov     r8, rsi; Size
0x18002848a  mov     rcx, rax; void *
0x18002848d  call    memcpy_0
0x180028492  mov     rax, [rbp+37h+var_68]
0x180028496  xor     ecx, ecx
0x180028498  inc     r13
0x18002849b  cmp     [rax+r13*2], cx
0x1800284a0  jnz     short loc_180028498
0x1800284a2  mov     rcx, gs:60h
0x1800284ab  lea     rsi, ds:2[r13*2]
0x1800284b3  mov     r8, rsi; Size
0x1800284b6  xor     edx, edx; Flags
0x1800284b8  mov     rcx, [rcx+30h]; HeapHandle
0x1800284bc  call    cs:__imp_RtlAllocateHeap
0x1800284c2  mov     [rbx+30h], rax
0x1800284c6  test    rax, rax
0x1800284c9  jnz     loc_18002875D
0x1800284cf  mov     [rbp+37h+var_A0], r14
0x1800284d3  mov     rcx, rbx; this
0x1800284d6  mov     esi, edi
0x1800284d8  call    ??_GBackgroundTask@@QEAAPEAXI@Z; BackgroundTask::`scalar deleting destructor'(uint)
0x1800284dd  test    edi, edi
0x1800284df  js      loc_1800287DC
0x1800284e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800284ec  mov     ecx, 18h; unsigned __int64
0x1800284f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800284f6  mov     rsi, rax
0x1800284f9  test    rax, rax
0x1800284fc  jz      loc_1800287E3
0x180028502  mov     dword ptr [rax+8], 1
0x180028509  mov     dword ptr [rax+0Ch], 1
0x180028510  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountNormal@PEAVBackgroundTask@@U?$default_delete@VBackgroundTask@@@utl@@V?$allocator@H@3@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountNormal<BackgroundTask *,utl::default_delete<BackgroundTask>,utl::allocator<int>>,0>::`vftable'
0x180028517  mov     [rsi], rax
0x18002851a  mov     [rsi+10h], r15
0x18002851e  lock inc dword ptr [rsi+8]
0x180028522  lea     rbx, [r14+10h]
0x180028526  mov     rcx, rbx; lpCriticalSection
0x180028529  call    cs:__imp_EnterCriticalSection
0x18002852f  lea     rcx, [r14+38h]
0x180028533  cmp     [rcx+10h], rcx
0x180028537  jz      short loc_18002856E
0x180028539  mov     rax, [rcx]
0x18002853c  mov     r13, rcx
0x18002853f  mov     r8d, [rbp+37h+arg_28]
0x180028543  mov     [rbp+37h+var_A0], r14
0x180028547  cmp     [rax+18h], r8d
0x18002854b  jb      short loc_180028585
0x18002854d  mov     r13, rax
0x180028550  mov     edx, 8
0x180028555  mov     rax, [rdx+rax]
0x180028559  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180028560  cmp     rax, rdx
0x180028563  jnz     short loc_180028547
0x180028565  cmp     r13, rcx
0x180028568  jnz     loc_18002874E
0x18002856e  xorps   xmm0, xmm0
0x180028571  xorps   xmm1, xmm1
0x180028574  psrldq  xmm0, 8
0x180028579  movq    r13, xmm1
0x18002857e  movq    r12, xmm0
0x180028583  jmp     short loc_18002859F
0x180028585  mov     edx, 10h
0x18002858a  jmp     short loc_180028555
0x18002858c  mov     r12, [r13+28h]
0x180028590  mov     r13, [r13+20h]
0x180028594  test    r12, r12
0x180028597  jz      short loc_18002859F
0x180028599  lock inc dword ptr [r12+8]
0x18002859f  test    r13, r13
0x1800285a2  jz      loc_18002872B
0x1800285a8  mov     rdx, [rbp+37h+var_60]; void *
0x1800285ac  mov     rcx, r13; this
0x1800285af  call    ?IsOwner@BackgroundExecutionSession@@QEAA_NPEAX@Z; BackgroundExecutionSession::IsOwner(void *)
0x1800285b4  test    al, al
0x1800285b6  jz      loc_1800287C3
0x1800285bc  mov     eax, [rbp+37h+arg_20]
0x1800285bf  cmp     [r13+10h], eax
0x1800285c3  jnz     loc_1800287C3
0x1800285c9  mov     [rbp+37h+var_80], r15
0x1800285cd  mov     [rbp+37h+var_78], rsi
0x1800285d1  test    rsi, rsi
0x1800285d4  jz      short loc_1800285DA
0x1800285d6  lock inc dword ptr [rsi+8]
0x1800285da  mov     r9, [rbp+37h+var_90]
0x1800285de  lea     r8, [rbp+37h+var_80]
0x1800285e2  mov     rdx, [rbp+37h+var_58]
0x1800285e6  mov     rcx, r13; this
0x1800285e9  call    ?LaunchBackgroundTask@BackgroundExecutionSession@@QEAAJPEAXV?$shared_ptr@VBackgroundTask@@@utl@@PEAU_GUID@@@Z; BackgroundExecutionSession::LaunchBackgroundTask(void *,utl::shared_ptr<BackgroundTask>,_GUID *)
0x1800285ee  mov     r14d, eax
0x1800285f1  test    eax, eax
0x1800285f3  js      loc_180028731
0x1800285f9  mov     [rbp+37h+var_90], r15
0x1800285fd  mov     [rbp+37h+var_88], rsi
0x180028601  test    rsi, rsi
0x180028604  jz      short loc_18002860A
0x180028606  lock inc dword ptr [rsi+8]
0x18002860a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028611  mov     ecx, 20h ; ' '; unsigned __int64
0x180028616  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002861b  mov     r10, rax
0x18002861e  test    rax, rax
0x180028621  jz      loc_180028736
0x180028627  lea     rcx, [rax+10h]
0x18002862b  lea     rdx, [rbp+37h+var_90]
0x18002862f  lea     r9, [r13+58h]
0x180028633  call    ??0?$shared_ptr@VBackgroundTask@@@utl@@QEAA@AEBV01@@Z; utl::shared_ptr<BackgroundTask>::shared_ptr<BackgroundTask>(utl::shared_ptr<BackgroundTask> const &)
0x180028638  mov     rcx, [r9+8]
0x18002863c  xor     r13d, r13d
0x18002863f  mov     [r10+8], rcx
0x180028643  mov     [r10], r9
0x180028646  mov     [rcx], r10
0x180028649  mov     [r9+8], r10
0x18002864d  inc     qword ptr [r9+10h]
0x180028651  test    rsi, rsi
0x180028654  jz      short loc_18002865E
0x180028656  mov     rcx, rsi; this
0x180028659  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18002865e  mov     [rbp+37h+var_90], r15
0x180028662  mov     [rbp+37h+var_88], rsi
0x180028666  test    rsi, rsi
0x180028669  jz      short loc_18002866F
0x18002866b  lock inc dword ptr [rsi+8]
0x18002866f  movups  xmm0, xmmword ptr [r15]
0x180028673  mov     rcx, [rbp+37h+var_A0]
0x180028677  lea     rax, [rbp+37h+var_90]
0x18002867b  add     rcx, 58h ; 'X'
0x18002867f  mov     qword ptr [rsp+0E0h+dwDesiredAccess], rax
0x180028684  lea     r9, [rbp+37h+var_50]
0x180028688  lea     rdx, [rbp+37h+var_80]
0x18002868c  movdqu  [rbp+37h+var_50], xmm0
0x180028691  call    ??$_TryEmplace@U_GUID@@AEAV?$shared_ptr@VBackgroundTask@@@utl@@@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBackgroundTask@@@utl@@@utl@@UGuidComparator@@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBackgroundTask@@@utl@@@utl@@@3@$0A@@utl@@IEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBackgroundTask@@@utl@@@utl@@@utl@@_N@1@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBackgroundTask@@@utl@@@utl@@@1@$$QEAU_GUID@@AEAV?$shared_ptr@VBackgroundTask@@@1@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::shared_ptr<BackgroundTask>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::shared_ptr<BackgroundTask>>>,0>::_TryEmplace<_GUID,utl::shared_ptr<BackgroundTask> &>(utl::_TreeNode<utl::pair<_GUID const,utl::shared_ptr<BackgroundTask>>> *,_GUID &&,utl::shared_ptr<BackgroundTask> &)
0x180028696  cmp     [rbp+37h+var_80], r13
0x18002869a  jz      loc_180028884
0x1800286a0  mov     al, byte ptr [rbp+37h+var_78]
0x1800286a3  neg     al
0x1800286a5  sbb     r14d, r14d
0x1800286a8  not     r14d
0x1800286ab  and     r14d, 800700B7h
0x1800286b2  mov     rcx, [rbp+37h+var_88]; this
0x1800286b6  test    rcx, rcx
0x1800286b9  jz      short loc_1800286C0
0x1800286bb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800286c0  test    r14d, r14d
0x1800286c3  js      short loc_1800286C8
0x1800286c5  mov     r14d, r13d
0x1800286c8  mov     rcx, rbx; lpCriticalSection
0x1800286cb  call    cs:__imp_LeaveCriticalSection
0x1800286d1  test    r12, r12
0x1800286d4  jz      short loc_1800286DE
0x1800286d6  mov     rcx, r12; this
0x1800286d9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800286de  test    rsi, rsi
  ... truncated ...
```
