# CPMPSession::HandleGRLReaderUpdate(IUnknown *)

- ea: `0x180195374`
- end: `0x1801956af`
- name: `?HandleGRLReaderUpdate@CPMPSession@@AEAAJPEAUIUnknown@@@Z`
- size: `827`
- prototype: `__int64 __fastcall(CPMPSession *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18029fb00`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x180067eec`
- `0x18006b388`
- `0x1800ec0e0`
- `0x180195374`
- `0x18025a908`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801953fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019541a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801953fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019541a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801953de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801953de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019545f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180195547`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801955e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019545f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180195547`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801955e2`
- `ext-ms-win-mm-pehelper-l1-1-0!MFRR_CreateActivate` at `0x18019543d`
- `ext-ms-win-mm-pehelper-l1-1-0!MFRR_CreateActivate` at `0x18019543d`

## string_xrefs

- `0x180195386`: `CPMPSession::HandleGRLReaderUpdate`
- `0x1801954bd`: `CPMPSession::HandleGRLReaderUpdate`
- `0x1801955a5`: `CPMPSession::HandleGRLReaderUpdate`
- `0x180195640`: `CPMPSession::HandleGRLReaderUpdate`

## pseudocode

```c
__int64 __fastcall CPMPSession::HandleGRLReaderUpdate(CPMPSession *this, struct IUnknown *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v23; // [rsp+50h] [rbp+8h] BYREF
  __int64 v24; // [rsp+60h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v23, "CPMPSession::HandleGRLReaderUpdate", 2534);
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 219, &WPP_e23edcaf414f3d64d6117a45b80c84c1_Traceguids, this);
  v24 = 0;
  v23 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v4 = *((_QWORD *)this + 16);
  if ( !v4 )
  {
    v5 = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    goto LABEL_39;
  }
  ComSmartPtr<CPMPStreamStub>::operator=(&v23, v4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( (unsigned __int8)IsMFRR_CreateActivatePresent() )
  {
    v5 = MFRR_CreateActivate(3, &v24);
    if ( v5 >= 0 )
    {
      (*(void (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)v24 + 168LL))(
        v24,
        &CEACTIVATE_ATTRIBUTE_DEFAULT_HRESULT,
        3222106475LL);
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *, struct IUnknown *))(*(_QWORD *)v23 + 24LL))(
             v23,
             v24,
             0,
             (char *)this + 808,
             a2);
      if ( v5 < 0 )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CPMPSession::HandleGRLReaderUpdate", 2561, v5);
        }
        if ( g_wppLevels )
        {
          v13 = 222;
          goto LABEL_38;
        }
      }
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != v5 )
          CallStackContext::TraceFailure(v12, "CPMPSession::HandleGRLReaderUpdate", 2552, v5);
      }
      if ( g_wppLevels )
      {
        v13 = 220;
LABEL_38:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_e23edcaf414f3d64d6117a45b80c84c1_Traceguids, this, v5);
      }
    }
  }
  else
  {
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147467263;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -2147467263 )
        CallStackContext::TraceFailure(v21, "CPMPSession::HandleGRLReaderUpdate", 2556, -2147467263);
    }
    if ( g_wppLevels )
    {
      v13 = 221;
      goto LABEL_38;
    }
  }
LABEL_39:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v23);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v24);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v23);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180195374  mov     [rsp+arg_8], rbx
0x180195379  push    rbp
0x18019537a  push    rsi
0x18019537b  push    rdi
0x18019537c  sub     rsp, 30h
0x180195380  mov     rbp, rdx
0x180195383  mov     rdi, rcx
0x180195386  lea     rdx, aCpmpsessionHan_0; "CPMPSession::HandleGRLReaderUpdate"
0x18019538d  mov     r8d, 9E6h; int
0x180195393  lea     rcx, [rsp+48h+arg_0]; this
0x180195398  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18019539d  cmp     cs:byte_1803CECE9, 8
0x1801953a4  jb      short loc_1801953C5
0x1801953a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801953ad  lea     r8, WPP_e23edcaf414f3d64d6117a45b80c84c1_Traceguids
0x1801953b4  mov     edx, 0DBh
0x1801953b9  mov     r9, rdi
0x1801953bc  mov     rcx, [rcx+38h]
0x1801953c0  call    WPP_SF_q
0x1801953c5  lea     rsi, [rdi+40h]
0x1801953c9  mov     [rsp+48h+arg_10], 0
0x1801953d2  mov     rcx, rsi; lpCriticalSection
0x1801953d5  mov     [rsp+48h+arg_0], 0
0x1801953de  call    cs:__imp_EnterCriticalSection
0x1801953e5  nop     dword ptr [rax+rax+00h]
0x1801953ea  mov     rdx, [rdi+80h]
0x1801953f1  test    rdx, rdx
0x1801953f4  jnz     short loc_18019540D
0x1801953f6  mov     rcx, rsi; lpCriticalSection
0x1801953f9  lea     ebx, [rdx+1]
0x1801953fc  call    cs:__imp_LeaveCriticalSection
0x180195403  nop     dword ptr [rax+rax+00h]
0x180195408  jmp     loc_180195681
0x18019540d  lea     rcx, [rsp+48h+arg_0]
0x180195412  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180195417  mov     rcx, rsi; lpCriticalSection
0x18019541a  call    cs:__imp_LeaveCriticalSection
0x180195421  nop     dword ptr [rax+rax+00h]
0x180195426  call    IsMFRR_CreateActivatePresent
0x18019542b  test    al, al
0x18019542d  jz      loc_1801955D1
0x180195433  lea     rdx, [rsp+48h+arg_10]
0x180195438  mov     ecx, 3
0x18019543d  call    cs:__imp_MFRR_CreateActivate
0x180195444  nop     dword ptr [rax+rax+00h]
0x180195449  mov     ebx, eax
0x18019544b  test    eax, eax
0x18019544d  jns     loc_1801954E9
0x180195453  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019545a  test    rcx, rcx
0x18019545d  jnz     short loc_1801954A7
0x18019545f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180195466  nop     dword ptr [rax+rax+00h]
0x18019546b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180195472  mov     rcx, rax
0x180195475  test    rax, rax
0x180195478  jz      short loc_180195499
0x18019547a  mov     rax, [rax]
0x18019547d  mov     edx, 7F0h
0x180195482  mov     rax, [rax+8]
0x180195486  call    cs:__guard_dispatch_icall_fptr
0x18019548c  test    eax, eax
0x18019548e  jz      short loc_180195499
0x180195490  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180195497  jmp     short loc_1801954A7
0x180195499  lea     rcx, qword_1803CE250; this
0x1801954a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801954a7  cmp     byte ptr [rcx+8], 0
0x1801954ab  jz      short loc_1801954D2
0x1801954ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801954b2  cmp     [rax+7CCh], ebx
0x1801954b8  jz      short loc_1801954D2
0x1801954ba  mov     r9d, ebx; int
0x1801954bd  lea     rdx, aCpmpsessionHan_0; "CPMPSession::HandleGRLReaderUpdate"
0x1801954c4  mov     r8d, 9F8h; int
0x1801954ca  mov     rcx, rax; this
0x1801954cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801954d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801954d9  jb      loc_180195681
0x1801954df  mov     edx, 0DCh
0x1801954e4  jmp     loc_180195663
0x1801954e9  mov     rcx, [rsp+48h+arg_10]
0x1801954ee  lea     rdx, CEACTIVATE_ATTRIBUTE_DEFAULT_HRESULT
0x1801954f5  mov     r8d, 0C00D716Bh
0x1801954fb  mov     rax, [rcx]
0x1801954fe  mov     rax, [rax+0A8h]
0x180195505  call    cs:__guard_dispatch_icall_fptr
0x18019550b  mov     rcx, [rsp+48h+arg_0]
0x180195510  lea     r9, [rdi+328h]
0x180195517  mov     rdx, [rsp+48h+arg_10]
0x18019551c  xor     r8d, r8d
0x18019551f  mov     [rsp+48h+var_28], rbp
0x180195524  mov     rax, [rcx]
0x180195527  mov     rax, [rax+18h]
0x18019552b  call    cs:__guard_dispatch_icall_fptr
0x180195531  mov     ebx, eax
0x180195533  test    eax, eax
0x180195535  jns     loc_180195681
0x18019553b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180195542  test    rcx, rcx
0x180195545  jnz     short loc_18019558F
0x180195547  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019554e  nop     dword ptr [rax+rax+00h]
0x180195553  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019555a  mov     rcx, rax
0x18019555d  test    rax, rax
0x180195560  jz      short loc_180195581
0x180195562  mov     rax, [rax]
0x180195565  mov     edx, 7F0h
0x18019556a  mov     rax, [rax+8]
0x18019556e  call    cs:__guard_dispatch_icall_fptr
0x180195574  test    eax, eax
0x180195576  jz      short loc_180195581
0x180195578  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019557f  jmp     short loc_18019558F
0x180195581  lea     rcx, qword_1803CE250; this
0x180195588  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019558f  cmp     byte ptr [rcx+8], 0
0x180195593  jz      short loc_1801955BA
0x180195595  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019559a  cmp     [rax+7CCh], ebx
0x1801955a0  jz      short loc_1801955BA
0x1801955a2  mov     r9d, ebx; int
0x1801955a5  lea     rdx, aCpmpsessionHan_0; "CPMPSession::HandleGRLReaderUpdate"
0x1801955ac  mov     r8d, 0A01h; int
0x1801955b2  mov     rcx, rax; this
0x1801955b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801955ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801955c1  jb      loc_180195681
0x1801955c7  mov     edx, 0DEh
0x1801955cc  jmp     loc_180195663
0x1801955d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801955d8  mov     ebx, 80004001h
0x1801955dd  test    rcx, rcx
0x1801955e0  jnz     short loc_18019562A
0x1801955e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801955e9  nop     dword ptr [rax+rax+00h]
0x1801955ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801955f5  mov     rcx, rax
0x1801955f8  test    rax, rax
0x1801955fb  jz      short loc_18019561C
0x1801955fd  mov     rax, [rax]
0x180195600  mov     edx, 7F0h
0x180195605  mov     rax, [rax+8]
0x180195609  call    cs:__guard_dispatch_icall_fptr
0x18019560f  test    eax, eax
0x180195611  jz      short loc_18019561C
0x180195613  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019561a  jmp     short loc_18019562A
0x18019561c  lea     rcx, qword_1803CE250; this
0x180195623  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019562a  cmp     byte ptr [rcx+8], 0
0x18019562e  jz      short loc_180195655
0x180195630  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180195635  cmp     [rax+7CCh], ebx
0x18019563b  jz      short loc_180195655
0x18019563d  mov     r9d, ebx; int
0x180195640  lea     rdx, aCpmpsessionHan_0; "CPMPSession::HandleGRLReaderUpdate"
0x180195647  mov     r8d, 9FCh; int
0x18019564d  mov     rcx, rax; this
0x180195650  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180195655  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019565c  jb      short loc_180195681
0x18019565e  mov     edx, 0DDh
0x180195663  mov     rcx, cs:WPP_GLOBAL_Control
0x18019566a  lea     r8, WPP_e23edcaf414f3d64d6117a45b80c84c1_Traceguids
0x180195671  mov     r9, rdi
0x180195674  mov     dword ptr [rsp+48h+var_28], ebx
0x180195678  mov     rcx, [rcx+10h]
0x18019567c  call    WPP_SF_qD
0x180195681  lea     rcx, [rsp+48h+arg_0]
0x180195686  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18019568b  lea     rcx, [rsp+48h+arg_10]
0x180195690  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180195695  lea     rcx, [rsp+48h+arg_0]; this
0x18019569a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18019569f  mov     eax, ebx
0x1801956a1  mov     rbx, [rsp+48h+arg_8]
0x1801956a6  add     rsp, 30h
0x1801956aa  pop     rdi
0x1801956ab  pop     rsi
0x1801956ac  pop     rbp
0x1801956ad  retn
```
