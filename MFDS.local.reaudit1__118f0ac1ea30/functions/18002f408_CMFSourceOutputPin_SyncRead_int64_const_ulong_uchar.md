# CMFSourceOutputPin::_SyncRead(__int64 const &,ulong,uchar *)

- ea: `0x18002f408`
- end: `0x18002f854`
- name: `?_SyncRead@CMFSourceOutputPin@@IEAAJAEB_JKPEAE@Z`
- size: `1100`
- prototype: `__int64 __fastcall(CMFSourceOutputPin *__hidden this, const __int64 *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18002f0b0`
- `0x180067c80`

## callees

- `0x180002820`
- `0x1800140b0`
- `0x18002f408`
- `0x180032a50`
- `0x180051ce4`
- `0x180074160`
- `0x18007c8e8`
- `0x180091618`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f515`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f515`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f686`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f6da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f72e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f686`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f6da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f72e`
- `MFPlat!MFCreateAsyncResult` at `0x18002f4b2`
- `MFPlat!MFCreateAsyncResult` at `0x18002f4b2`

## string_xrefs

- `0x18002f445`: `CMFSourceOutputPin::_SyncRead`

## pseudocode

```c
__int64 __fastcall CMFSourceOutputPin::_SyncRead(
        CMFSourceOutputPin *this,
        const __int64 *a2,
        unsigned int a3,
        unsigned __int8 *a4)
{
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  HRESULT v13; // ebx
  __int64 v14; // rax
  IMFAsyncResult *v15; // r10
  __int64 v16; // rax
  __int64 v17; // rsi
  __int64 v18; // rcx
  struct CallStackContext *v20; // rax
  struct CallStackContext *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  CallStackTracing *v27; // rcx
  CallStackTracing *v28; // rax
  __int64 v29; // rdx
  _BYTE v30[8]; // [rsp+30h] [rbp-58h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+38h] [rbp-50h] BYREF
  __int64 v32; // [rsp+40h] [rbp-48h] BYREF

  v5 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v5 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
    v10 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v10 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v11 = 2 * v10;
      *((_QWORD *)ThreadRelativeContext + v11) = "CMFSourceOutputPin::_SyncRead";
      *((_DWORD *)ThreadRelativeContext + 2 * v11 + 2) = 2326;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  ppAsyncResult = 0;
  v32 = 0;
  if ( !a4 )
  {
    v13 = -2147024809;
LABEL_56:
    *((_DWORD *)this + 395) = 0;
    goto LABEL_20;
  }
  v12 = *((_QWORD *)this + 32);
  if ( *(_DWORD *)(v12 + 208) )
  {
    v13 = -2147467259;
    goto LABEL_56;
  }
  v13 = MFCreateAsyncResult(*(IUnknown **)(v12 + 216), 0, 0, &ppAsyncResult);
  if ( v13 < 0 )
  {
    v23 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext(v23);
      if ( *((_DWORD *)v20 + 499) != v13 )
        CallStackContext::TraceFailure(v20, "CMFSourceOutputPin::_SyncRead", 2355, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_56;
    v29 = 27;
LABEL_55:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids, this, v13);
    goto LABEL_56;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 32)
                                                                                            + 216LL)
                                                                              + 120LL))(
          *(_QWORD *)(*((_QWORD *)this + 32) + 216LL),
          0,
          *a2,
          1,
          &v32);
  if ( v13 < 0 )
  {
    v25 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v25);
      if ( *((_DWORD *)v21 + 499) != v13 )
        CallStackContext::TraceFailure(v21, "CMFSourceOutputPin::_SyncRead", 2357, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_56;
    v29 = 28;
    goto LABEL_55;
  }
  if ( *((_DWORD *)this + 398) )
  {
    *((_DWORD *)this + 398) = 0;
    CMFSourceOutputPin::_EnableBuffering(this, 1);
  }
  ResetEvent(*((HANDLE *)this + 193));
  v14 = *((_QWORD *)this + 32);
  v15 = ppAsyncResult;
  *((_QWORD *)this + 196) = 0;
  *((_DWORD *)this + 395) = 1;
  v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *, IMFAsyncResult *))(**(_QWORD **)(v14 + 216)
                                                                                               + 80LL))(
          *(_QWORD *)(v14 + 216),
          a4,
          a3,
          (char *)this + 272,
          v15);
  if ( v13 < 0 )
  {
    v27 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext(v27);
      if ( *((_DWORD *)v22 + 499) != v13 )
        CallStackContext::TraceFailure(v22, "CMFSourceOutputPin::_SyncRead", 2373, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_56;
    v29 = 29;
    goto LABEL_55;
  }
  v16 = *((_QWORD *)this + 32);
  v17 = *(_QWORD *)(v16 + 216);
  if ( *((_QWORD *)this + 192) != v17 )
  {
    if ( v17 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 8LL))(*(_QWORD *)(v16 + 216));
    v18 = *((_QWORD *)this + 192);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    *((_QWORD *)this + 192) = v17;
  }
LABEL_20:
  if ( ppAsyncResult )
    ((void (__fastcall *)(IMFAsyncResult *))ppAsyncResult->lpVtbl->Release)(ppAsyncResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002f408  push    rbx
0x18002f40a  push    rbp
0x18002f40b  push    rsi
0x18002f40c  push    rdi
0x18002f40d  push    r13
0x18002f40f  push    r14
0x18002f411  push    r15
0x18002f413  sub     rsp, 50h
0x18002f417  mov     rax, cs:__security_cookie
0x18002f41e  xor     rax, rsp
0x18002f421  mov     [rsp+88h+var_40], rax
0x18002f426  mov     rdi, rcx
0x18002f429  xor     r15d, r15d
0x18002f42c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002f433  mov     rsi, r9
0x18002f436  mov     ebp, r8d
0x18002f439  mov     r14, rdx
0x18002f43c  test    rcx, rcx
0x18002f43f  jz      loc_18002F772
0x18002f445  lea     r13, aCmfsourceoutpu_0; "CMFSourceOutputPin::_SyncRead"
0x18002f44c  cmp     [rcx+8], r15b
0x18002f450  jz      short loc_18002F47A
0x18002f452  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f457  mov     ecx, [rax+7C4h]
0x18002f45d  cmp     ecx, [rax+7C8h]
0x18002f463  jnb     short loc_18002F474
0x18002f465  add     rcx, rcx
0x18002f468  mov     [rax+rcx*8], r13
0x18002f46c  mov     dword ptr [rax+rcx*8+8], 916h
0x18002f474  inc     dword ptr [rax+7C4h]
0x18002f47a  mov     [rsp+88h+ppAsyncResult], r15
0x18002f47f  mov     [rsp+88h+var_48], r15
0x18002f484  test    rsi, rsi
0x18002f487  jz      loc_18002F783
0x18002f48d  mov     rcx, [rdi+100h]
0x18002f494  cmp     [rcx+0D0h], r15d
0x18002f49b  jnz     loc_18002F78D
0x18002f4a1  mov     rcx, [rcx+0D8h]; punkObject
0x18002f4a8  lea     r9, [rsp+88h+ppAsyncResult]; ppAsyncResult
0x18002f4ad  xor     r8d, r8d; punkState
0x18002f4b0  xor     edx, edx; pCallback
0x18002f4b2  call    cs:__imp_MFCreateAsyncResult
0x18002f4b9  nop     dword ptr [rax+rax+00h]
0x18002f4be  mov     ebx, eax
0x18002f4c0  test    eax, eax
0x18002f4c2  js      loc_18002F676
0x18002f4c8  mov     rax, [rdi+100h]
0x18002f4cf  lea     rdx, [rsp+88h+var_48]
0x18002f4d4  mov     r8, [r14]
0x18002f4d7  mov     r9d, 1
0x18002f4dd  mov     [rsp+88h+var_68], rdx
0x18002f4e2  xor     edx, edx
0x18002f4e4  mov     rcx, [rax+0D8h]
0x18002f4eb  mov     rax, [rcx]
0x18002f4ee  mov     rax, [rax+78h]
0x18002f4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4f7  mov     ebx, eax
0x18002f4f9  test    eax, eax
0x18002f4fb  js      loc_18002F6CA
0x18002f501  cmp     [rdi+638h], r15d
0x18002f508  jnz     loc_18002F7EB
0x18002f50e  mov     rcx, [rdi+608h]; hEvent
0x18002f515  call    cs:__imp_ResetEvent
0x18002f51c  nop     dword ptr [rax+rax+00h]
0x18002f521  mov     rax, [rdi+100h]
0x18002f528  lea     r9, [rdi+110h]
0x18002f52f  mov     r10, [rsp+88h+ppAsyncResult]
0x18002f534  mov     r8d, ebp
0x18002f537  mov     [rdi+620h], r15
0x18002f53e  mov     rdx, rsi
0x18002f541  mov     dword ptr [rdi+62Ch], 1
0x18002f54b  mov     rcx, [rax+0D8h]
0x18002f552  mov     [rsp+88h+var_68], r10
0x18002f557  mov     rax, [rcx]
0x18002f55a  mov     rax, [rax+50h]
0x18002f55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f563  mov     ebx, eax
0x18002f565  test    eax, eax
0x18002f567  js      loc_18002F71E
0x18002f56d  mov     rax, [rdi+100h]
0x18002f574  mov     rsi, [rax+0D8h]
0x18002f57b  cmp     [rdi+600h], rsi
0x18002f582  jz      short loc_18002F5AB
0x18002f584  test    rsi, rsi
0x18002f587  jz      short loc_18002F598
0x18002f589  mov     rax, [rsi]
0x18002f58c  mov     rcx, rsi
0x18002f58f  mov     rax, [rax+8]
0x18002f593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f598  mov     rcx, [rdi+600h]
0x18002f59f  test    rcx, rcx
0x18002f5a2  jnz     short loc_18002F5EA
0x18002f5a4  mov     [rdi+600h], rsi
0x18002f5ab  mov     rcx, [rsp+88h+ppAsyncResult]
0x18002f5b0  test    rcx, rcx
0x18002f5b3  jz      short loc_18002F5C1
0x18002f5b5  mov     rax, [rcx]
0x18002f5b8  mov     rax, [rax+10h]
0x18002f5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5c1  lea     rcx, [rsp+88h+var_58]; this
0x18002f5c6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002f5cb  mov     eax, ebx
0x18002f5cd  mov     rcx, [rsp+88h+var_40]
0x18002f5d2  xor     rcx, rsp; StackCookie
0x18002f5d5  call    __security_check_cookie
0x18002f5da  add     rsp, 50h
0x18002f5de  pop     r15
0x18002f5e0  pop     r14
0x18002f5e2  pop     r13
0x18002f5e4  pop     rdi
0x18002f5e5  pop     rsi
0x18002f5e6  pop     rbp
0x18002f5e7  pop     rbx
0x18002f5e8  retn
0x18002f5ea  mov     rax, [rcx]
0x18002f5ed  mov     rax, [rax+10h]
0x18002f5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5f6  jmp     short loc_18002F5A4
0x18002f5f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f5fd  cmp     [rax+7CCh], ebx
0x18002f603  jz      loc_18002F7AF
0x18002f609  mov     r9d, ebx; int
0x18002f60c  mov     r8d, 933h; int
0x18002f612  mov     rdx, r13; char *
0x18002f615  mov     rcx, rax; this
0x18002f618  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f61d  jmp     loc_18002F7AF
0x18002f622  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f627  cmp     [rax+7CCh], ebx
0x18002f62d  jz      loc_18002F7DB
0x18002f633  mov     r9d, ebx; int
0x18002f636  mov     r8d, 935h; int
0x18002f63c  mov     rdx, r13; char *
0x18002f63f  mov     rcx, rax; this
0x18002f642  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f647  jmp     loc_18002F7DB
0x18002f64c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f651  cmp     [rax+7CCh], ebx
0x18002f657  jz      loc_18002F81C
0x18002f65d  mov     r9d, ebx; int
0x18002f660  mov     r8d, 945h; int
0x18002f666  mov     rdx, r13; char *
0x18002f669  mov     rcx, rax; this
0x18002f66c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f671  jmp     loc_18002F81C
0x18002f676  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f67d  test    rcx, rcx
0x18002f680  jnz     loc_18002F7A5
0x18002f686  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f68d  nop     dword ptr [rax+rax+00h]
0x18002f692  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f699  mov     rcx, rax
0x18002f69c  test    rax, rax
0x18002f69f  jz      loc_18002F797
0x18002f6a5  mov     rax, [rax]
0x18002f6a8  mov     edx, 7F0h
0x18002f6ad  mov     rax, [rax+8]
0x18002f6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6b6  test    eax, eax
0x18002f6b8  jz      loc_18002F797
0x18002f6be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f6c5  jmp     loc_18002F7A5
0x18002f6ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f6d1  test    rcx, rcx
0x18002f6d4  jnz     loc_18002F7D1
0x18002f6da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f6e1  nop     dword ptr [rax+rax+00h]
0x18002f6e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f6ed  mov     rcx, rax
0x18002f6f0  test    rax, rax
0x18002f6f3  jz      loc_18002F7C3
0x18002f6f9  mov     rax, [rax]
0x18002f6fc  mov     edx, 7F0h
0x18002f701  mov     rax, [rax+8]
0x18002f705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f70a  test    eax, eax
0x18002f70c  jz      loc_18002F7C3
0x18002f712  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f719  jmp     loc_18002F7D1
0x18002f71e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f725  test    rcx, rcx
0x18002f728  jnz     loc_18002F812
0x18002f72e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f735  nop     dword ptr [rax+rax+00h]
0x18002f73a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f741  mov     rcx, rax
0x18002f744  test    rax, rax
0x18002f747  jz      loc_18002F804
0x18002f74d  mov     rax, [rax]
0x18002f750  mov     edx, 7F0h
0x18002f755  mov     rax, [rax+8]
0x18002f759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f75e  test    eax, eax
0x18002f760  jz      loc_18002F804
0x18002f766  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f76d  jmp     loc_18002F812
0x18002f772  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002f777  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f77e  jmp     loc_18002F445
0x18002f783  mov     ebx, 80070057h
0x18002f788  jmp     loc_18002F848
0x18002f78d  mov     ebx, 80004005h
0x18002f792  jmp     loc_18002F848
0x18002f797  lea     rcx, qword_1800EB130; this
0x18002f79e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f7a5  cmp     [rcx+8], r15b
0x18002f7a9  jnz     loc_18002F5F8
0x18002f7af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f7b6  jb      loc_18002F848
0x18002f7bc  mov     edx, 1Bh
0x18002f7c1  jmp     short loc_18002F82A
0x18002f7c3  lea     rcx, qword_1800EB130; this
0x18002f7ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f7d1  cmp     [rcx+8], r15b
0x18002f7d5  jnz     loc_18002F622
0x18002f7db  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f7e2  jb      short loc_18002F848
0x18002f7e4  mov     edx, 1Ch
0x18002f7e9  jmp     short loc_18002F82A
0x18002f7eb  mov     edx, 1; int
0x18002f7f0  mov     [rdi+638h], r15d
0x18002f7f7  mov     rcx, rdi; this
0x18002f7fa  call    ?_EnableBuffering@CMFSourceOutputPin@@IEAAJH@Z; CMFSourceOutputPin::_EnableBuffering(int)
0x18002f7ff  jmp     loc_18002F50E
0x18002f804  lea     rcx, qword_1800EB130; this
0x18002f80b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f812  cmp     [rcx+8], r15b
0x18002f816  jnz     loc_18002F64C
0x18002f81c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f823  jb      short loc_18002F848
0x18002f825  mov     edx, 1Dh
0x18002f82a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f831  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x18002f838  mov     r9, rdi
0x18002f83b  mov     dword ptr [rsp+88h+var_68], ebx
0x18002f83f  mov     rcx, [rcx+10h]
0x18002f843  call    WPP_SF_qD
0x18002f848  mov     [rdi+62Ch], r15d
0x18002f84f  jmp     loc_18002F5AB
```
