# StandardCollectorService::RequestDestroySession(_GUID const &,void * *)

- ea: `0x180034078`
- end: `0x180034340`
- name: `?RequestDestroySession@StandardCollectorService@@AEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `712`
- prototype: `int(StandardCollectorService *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033f50`
- `0x180034070`

## callees

- `0x180010540`
- `0x180031db0`
- `0x18003223c`
- `0x180034078`
- `0x180035508`
- `0x18003d864`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180034201`
- `KERNEL32!GetCurrentProcess` at `0x180034201`
- `KERNEL32!DuplicateHandle` at `0x180034226`
- `KERNEL32!DuplicateHandle` at `0x180034226`
- `KERNEL32!ReleaseSRWLockShared` at `0x180034133`
- `KERNEL32!ReleaseSRWLockShared` at `0x180034199`
- `KERNEL32!ReleaseSRWLockShared` at `0x180034133`
- `KERNEL32!ReleaseSRWLockShared` at `0x180034199`
- `KERNEL32!AcquireSRWLockShared` at `0x180034109`
- `KERNEL32!AcquireSRWLockShared` at `0x180034109`
- `KERNEL32!CloseHandle` at `0x180034263`
- `KERNEL32!CloseHandle` at `0x180034294`
- `KERNEL32!CloseHandle` at `0x180034263`
- `KERNEL32!CloseHandle` at `0x180034294`
- `KERNEL32!GetLastError` at `0x180034230`
- `KERNEL32!GetLastError` at `0x180034230`
- `ole32!StringFromGUID2` at `0x1800340be`
- `ole32!StringFromGUID2` at `0x1800340be`
- `ole32!CoDisconnectObject` at `0x18003424e`
- `ole32!CoDisconnectObject` at `0x18003424e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003426d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003429e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003426d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003429e`

## string_xrefs

- `0x1800340e1`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall StandardCollectorService::RequestDestroySession(RTL_SRWLOCK *this, struct _GUID *a2, void **a3)
{
  DiagHubCommon::LogStream *v5; // rbx
  IUnknown *v6; // rbx
  RTL_SRWLOCK *v7; // r15
  void *v8; // rdi
  int UserTokenOfCaller; // r15d
  volatile signed __int32 *v10; // r14
  IUnknown *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // r13
  void *v14; // rsi
  HANDLE v15; // rdi
  HANDLE *v16; // r15
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v22; // [rsp+50h] [rbp-B0h]
  IUnknown *v23; // [rsp+60h] [rbp-A0h]
  PSID pSid1; // [rsp+68h] [rbp-98h]
  LPHANDLE lpTargetHandle; // [rsp+70h] [rbp-90h]
  OLECHAR sz[136]; // [rsp+80h] [rbp-80h] BYREF

  lpTargetHandle = a3;
  v5 = _logger;
  if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
  {
    if ( !StringFromGUID2(a2, sz, 39) )
    {
      LODWORD(Block) = -2147024882;
      throw (long *)&Block;
    }
    sz[39] = 0;
    sz[78] = 0;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)v5 + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
      L"Destroy session requested for '%s'",
      sz);
  }
  v22 = 0;
  v6 = 0;
  v23 = 0;
  v7 = this + 12;
  AcquireSRWLockShared(this + 12);
  Block = 0;
  std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
    &this[13],
    &Block);
  v8 = Block;
  if ( Block == this[14].Ptr )
  {
    ReleaseSRWLockShared(this + 12);
    UserTokenOfCaller = -2147024809;
    v10 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
LABEL_22:
    if ( v6 )
      ((void (__fastcall *)(IUnknown *))v6->lpVtbl->Release)(v6);
    goto LABEL_30;
  }
  v11 = (IUnknown *)*((_QWORD *)Block + 5);
  if ( v11 )
  {
    ((void (__fastcall *)(_QWORD))v11->lpVtbl->AddRef)(*((_QWORD *)Block + 5));
    v6 = v11;
    v23 = v11;
  }
  pSid1 = (PSID)**((_QWORD **)v8 + 4);
  v12 = *((_QWORD *)v8 + 7);
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  v13 = *((_QWORD *)v8 + 6);
  *(_QWORD *)&v22 = v13;
  v10 = (volatile signed __int32 *)*((_QWORD *)v8 + 7);
  *((_QWORD *)&v22 + 1) = v10;
  ReleaseSRWLockShared(v7);
  Block = 0;
  hObject = 0;
  UserTokenOfCaller = anonymous_namespace_::GetUserTokenOfCaller(&Block, &hObject);
  v14 = Block;
  v15 = hObject;
  if ( UserTokenOfCaller < 0 )
    goto LABEL_19;
  if ( !anonymous_namespace_::IsValidSessionServiceRequest(a2, pSid1, *(PSID *)Block, hObject) )
  {
    UserTokenOfCaller = -2147024891;
    goto LABEL_19;
  }
  v16 = lpTargetHandle;
  if ( lpTargetHandle )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(CurrentProcess, *(HANDLE *)(v13 + 16), CurrentProcess, v16, 0, 0, 2u) )
    {
      LastError = GetLastError();
      UserTokenOfCaller = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        UserTokenOfCaller = LastError;
      goto LABEL_19;
    }
  }
  UserTokenOfCaller = CoDisconnectObject(v6, 0);
  if ( UserTokenOfCaller < 0 )
  {
LABEL_19:
    if ( v15 )
      CloseHandle(v15);
    free(v14);
    goto LABEL_22;
  }
  if ( v15 )
    CloseHandle(v15);
  free(v14);
  if ( v6 )
  {
    _mm_lfence();
    ((void (__fastcall *)(IUnknown *))v6->lpVtbl->Release)(v6);
  }
  UserTokenOfCaller = StandardCollectorService::SessionLifetimeMonitor::TerminateSessionAsync((char *)v13);
LABEL_30:
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  return (unsigned int)UserTokenOfCaller;
}

```

## disassembly

```asm
0x180034078  mov     [rsp-8+arg_18], rbx
0x18003407d  push    rbp
0x18003407e  push    rsi
0x18003407f  push    rdi
0x180034080  push    r12
0x180034082  push    r13
0x180034084  push    r14
0x180034086  push    r15
0x180034088  lea     rbp, [rsp-60h]
0x18003408d  sub     rsp, 160h
0x180034094  mov     [rsp+190h+lpTargetHandle], r8
0x180034099  mov     r12, rdx
0x18003409c  mov     rsi, rcx
0x18003409f  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800340a6  mov     rax, [rbx+40h]
0x1800340aa  xor     r14d, r14d
0x1800340ad  cmp     [rbx+38h], rax
0x1800340b1  jz      short loc_1800340F1
0x1800340b3  lea     r8d, [r14+27h]; cchMax
0x1800340b7  lea     rdx, [rbp+90h+sz]; lpsz
0x1800340bb  mov     rcx, r12; rguid
0x1800340be  call    cs:__imp_StringFromGUID2
0x1800340c4  test    eax, eax
0x1800340c6  jz      loc_180034326
0x1800340cc  mov     [rbp+90h+var_C2], r14w
0x1800340d1  mov     [rbp+90h+var_74], r14w
0x1800340d6  lea     r9, [rbp+90h+sz]
0x1800340da  lea     r8, aDestroySession; "Destroy session requested for '%s'"
0x1800340e1  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800340e8  lea     rcx, [rbx+38h]; this
0x1800340ec  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800340f1  xorps   xmm1, xmm1
0x1800340f4  movdqu  [rsp+190h+var_140], xmm1
0x1800340fa  mov     rbx, r14
0x1800340fd  mov     [rsp+190h+var_130], rbx
0x180034102  lea     r15, [rsi+60h]
0x180034106  mov     rcx, r15; SRWLock
0x180034109  call    cs:__imp_AcquireSRWLockShared
0x18003410f  mov     [rsp+190h+Block], r14
0x180034114  lea     rcx, [rsi+68h]
0x180034118  mov     r8, r12
0x18003411b  lea     rdx, [rsp+190h+Block]
0x180034120  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x180034125  mov     rdi, [rsp+190h+Block]
0x18003412a  cmp     rdi, [rsi+70h]
0x18003412e  jnz     short loc_180034149
0x180034130  mov     rcx, r15; SRWLock
0x180034133  call    cs:__imp_ReleaseSRWLockShared
0x180034139  mov     r15d, 80070057h
0x18003413f  mov     r14, qword ptr [rsp+190h+var_140+8]
0x180034144  jmp     loc_180034274
0x180034149  mov     rsi, [rdi+28h]
0x18003414d  test    rsi, rsi
0x180034150  jz      short loc_18003416B
0x180034152  mov     rax, [rsi]
0x180034155  mov     rcx, rsi
0x180034158  mov     rax, [rax+8]
0x18003415c  call    cs:__guard_dispatch_icall_fptr
0x180034162  nop
0x180034163  mov     rbx, rsi
0x180034166  mov     [rsp+190h+var_130], rbx
0x18003416b  mov     rax, [rdi+20h]
0x18003416f  mov     rax, [rax]
0x180034172  mov     [rsp+190h+pSid1], rax
0x180034177  mov     rax, [rdi+38h]
0x18003417b  test    rax, rax
0x18003417e  jz      short loc_180034184
0x180034180  lock inc dword ptr [rax+8]
0x180034184  mov     r13, [rdi+30h]
0x180034188  mov     qword ptr [rsp+190h+var_140], r13
0x18003418d  mov     r14, [rdi+38h]
0x180034191  mov     qword ptr [rsp+190h+var_140+8], r14
0x180034196  mov     rcx, r15; SRWLock
0x180034199  call    cs:__imp_ReleaseSRWLockShared
0x18003419f  mov     [rsp+190h+Block], 0
0x1800341a8  mov     [rsp+190h+hObject], 0
0x1800341b1  lea     rdx, [rsp+190h+hObject]
0x1800341b6  lea     rcx, [rsp+190h+Block]
0x1800341bb  call    _anonymous_namespace___GetUserTokenOfCaller
0x1800341c0  mov     r15d, eax
0x1800341c3  mov     rsi, [rsp+190h+Block]
0x1800341c8  mov     rdi, [rsp+190h+hObject]
0x1800341cd  test    eax, eax
0x1800341cf  js      loc_18003425B
0x1800341d5  mov     r9, rdi; ClientToken
0x1800341d8  mov     r8, [rsi]; pSid2
0x1800341db  mov     rdx, [rsp+190h+pSid1]; pSid1
0x1800341e0  mov     rcx, r12; rguid
0x1800341e3  call    _anonymous_namespace___IsValidSessionServiceRequest
0x1800341e8  xor     r12d, r12d
0x1800341eb  test    al, al
0x1800341ed  jnz     short loc_1800341F7
0x1800341ef  mov     r15d, 80070005h
0x1800341f5  jmp     short loc_18003425B
0x1800341f7  mov     r15, [rsp+190h+lpTargetHandle]
0x1800341fc  test    r15, r15
0x1800341ff  jz      short loc_180034249
0x180034201  call    cs:__imp_GetCurrentProcess
0x180034207  mov     [rsp+190h+dwOptions], 2; dwOptions
0x18003420f  mov     [rsp+190h+bInheritHandle], r12d; bInheritHandle
0x180034214  mov     [rsp+190h+dwDesiredAccess], r12d; dwDesiredAccess
0x180034219  mov     r9, r15; lpTargetHandle
0x18003421c  mov     r8, rax; hTargetProcessHandle
0x18003421f  mov     rdx, [r13+10h]; hSourceHandle
0x180034223  mov     rcx, rax; hSourceProcessHandle
0x180034226  call    cs:__imp_DuplicateHandle
0x18003422c  test    eax, eax
0x18003422e  jnz     short loc_180034249
0x180034230  call    cs:__imp_GetLastError
0x180034236  movzx   r15d, ax
0x18003423a  or      r15d, 80070000h
0x180034241  test    eax, eax
0x180034243  cmovle  r15d, eax
0x180034247  jmp     short loc_18003425B
0x180034249  xor     edx, edx; dwReserved
0x18003424b  mov     rcx, rbx; pUnk
0x18003424e  call    cs:__imp_CoDisconnectObject
0x180034254  mov     r15d, eax
0x180034257  test    eax, eax
0x180034259  jns     short loc_18003428C
0x18003425b  test    rdi, rdi
0x18003425e  jz      short loc_18003426A
0x180034260  mov     rcx, rdi; hObject
0x180034263  call    cs:__imp_CloseHandle
0x180034269  nop
0x18003426a  mov     rcx, rsi; Block
0x18003426d  call    cs:__imp_free
0x180034273  nop
0x180034274  test    rbx, rbx
0x180034277  jz      short loc_18003428A
0x180034279  mov     rax, [rbx]
0x18003427c  mov     rcx, rbx
0x18003427f  mov     rax, [rax+10h]
0x180034283  call    cs:__guard_dispatch_icall_fptr
0x180034289  nop
0x18003428a  jmp     short loc_1800342C9
0x18003428c  test    rdi, rdi
0x18003428f  jz      short loc_18003429B
0x180034291  mov     rcx, rdi; hObject
0x180034294  call    cs:__imp_CloseHandle
0x18003429a  nop
0x18003429b  mov     rcx, rsi; Block
0x18003429e  call    cs:__imp_free
0x1800342a4  nop
0x1800342a5  test    rbx, rbx
0x1800342a8  jz      short loc_1800342BE
0x1800342aa  lfence
0x1800342ad  mov     rax, [rbx]
0x1800342b0  mov     rcx, rbx
0x1800342b3  mov     rax, [rax+10h]
0x1800342b7  call    cs:__guard_dispatch_icall_fptr
0x1800342bd  nop
0x1800342be  mov     rcx, r13; Context
0x1800342c1  call    ?TerminateSessionAsync@SessionLifetimeMonitor@StandardCollectorService@@QEAAJXZ; StandardCollectorService::SessionLifetimeMonitor::TerminateSessionAsync(void)
0x1800342c6  mov     r15d, eax
0x1800342c9  test    r14, r14
0x1800342cc  jz      short loc_180034308
0x1800342ce  or      ebx, 0FFFFFFFFh
0x1800342d1  mov     ecx, ebx
0x1800342d3  lock xadd [r14+8], ecx
0x1800342d9  add     ecx, ebx
0x1800342db  jnz     short loc_180034308
0x1800342dd  mov     rdx, [r14]
0x1800342e0  mov     rcx, r14
0x1800342e3  mov     rax, [rdx]
0x1800342e6  call    cs:__guard_dispatch_icall_fptr
0x1800342ec  mov     eax, ebx
0x1800342ee  lock xadd [r14+0Ch], eax
0x1800342f4  add     eax, ebx
0x1800342f6  jnz     short loc_180034308
0x1800342f8  mov     rax, [r14]
0x1800342fb  mov     rcx, r14
0x1800342fe  mov     rax, [rax+8]
0x180034302  call    cs:__guard_dispatch_icall_fptr
0x180034308  mov     eax, r15d
0x18003430b  mov     rbx, [rsp+190h+arg_18]
0x180034313  add     rsp, 160h
0x18003431a  pop     r15
0x18003431c  pop     r14
0x18003431e  pop     r13
0x180034320  pop     r12
0x180034322  pop     rdi
0x180034323  pop     rsi
0x180034324  pop     rbp
0x180034325  retn
0x180034326  mov     dword ptr [rsp+190h+Block], 8007000Eh
0x18003432e  lea     rdx, _TI1J; pThrowInfo
0x180034335  lea     rcx, [rsp+190h+Block]; pExceptionObject
0x18003433a  call    _CxxThrowException_0
```
