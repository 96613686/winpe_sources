# CMediaSession::CreateQualityManager(IMFAttributes *)

- ea: `0x180165228`
- end: `0x18016569b`
- name: `?CreateQualityManager@CMediaSession@@AEAAJPEAUIMFAttributes@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(CMediaSession *__hidden this, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180169580`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18006b388`
- `0x1800ec0e0`
- `0x180165228`
- `0x1801cc2e8`
- `0x180258480`
- `0x18025885c`
- `0x18025bb00`
- `0x18025bb68`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180165289`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180165289`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801653c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801653d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801653c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801653d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180165336`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180165336`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180165503`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180165503`
- `MFPlat!MFGetConfigurationDWORD` at `0x180165366`
- `MFPlat!MFGetConfigurationDWORD` at `0x180165366`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016543d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180165525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801655d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016543d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180165525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801655d1`

## string_xrefs

- `0x1801652b3`: `CMediaSession::CreateQualityManager`
- `0x18016549b`: `CMediaSession::CreateQualityManager`
- `0x180165583`: `CMediaSession::CreateQualityManager`
- `0x18016562f`: `CMediaSession::CreateQualityManager`

## pseudocode

```c
__int64 __fastcall CMediaSession::CreateQualityManager(CMediaSession *this, struct IMFAttributes *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  HRESULT Instance; // ebx
  struct IMFAttributesVtbl *lpVtbl; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  _BYTE v26[4]; // [rsp+30h] [rbp-38h] BYREF
  int v27; // [rsp+34h] [rbp-34h] BYREF
  IID Buf1; // [rsp+38h] [rbp-30h] BYREF

  if ( dword_1803CF258 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1803CF258);
    if ( dword_1803CF258 == -1 )
    {
      InitializeCriticalSection(&stru_1803CF260);
      atexit(CMediaSession::CreateQualityManager_::_2_::_dynamic_atexit_destructor_for__s_createQMLock__);
      Init_thread_footer(&dword_1803CF258);
    }
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v26, "CMediaSession::CreateQualityManager", 9921);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 202) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 202) + 296LL))(*((_QWORD *)this + 202));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, IID *))(**((_QWORD **)this + 202) + 280LL))(
                      *((_QWORD *)this + 202),
                      &Buf1);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  EnterCriticalSection(&stru_1803CF260);
  if ( !dword_1803CEFD8 )
  {
    v27 = 0;
    if ( (int)MFGetConfigurationDWORD(0, L"QM\\DisableQM", &v27) >= 0 )
      dword_1803CEFD4 = v27;
    dword_1803CEFD8 = 1;
  }
  if ( dword_1803CEFD4 )
  {
    Instance = 0;
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 796, &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids, this);
    LeaveCriticalSection(&stru_1803CF260);
    goto LABEL_52;
  }
  LeaveCriticalSection(&stru_1803CF260);
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    Buf1 = 0;
    Instance = ((__int64 (__fastcall *)(struct IMFAttributes *, const IID *, IID *))lpVtbl->GetGUID)(
                 a2,
                 &MF_SESSION_QUALITY_MANAGER,
                 &Buf1);
    if ( Instance >= 0 )
    {
      if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      {
        Instance = CoCreateInstance(&Buf1, 0, 1u, &IID_IMFQualityManager, (LPVOID *)this + 199);
        if ( Instance < 0 )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v17 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)v19 + 499) != Instance )
              CallStackContext::TraceFailure(v19, "CMediaSession::CreateQualityManager", 9970, Instance);
          }
          if ( g_wppLevels )
          {
            v14 = 798;
            goto LABEL_51;
          }
        }
      }
    }
    else
    {
      Instance = CMFQualityManager::CreateInstance((struct IMFQualityManager **)this + 199);
      if ( Instance < 0 )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10);
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v13 + 499) != Instance )
            CallStackContext::TraceFailure(v13, "CMediaSession::CreateQualityManager", 9962, Instance);
        }
        if ( g_wppLevels )
        {
          v14 = 797;
LABEL_51:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids,
            this,
            Instance);
        }
      }
    }
  }
  else
  {
    Instance = CMFQualityManager::CreateInstance((struct IMFQualityManager **)this + 199);
    if ( Instance < 0 )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != Instance )
          CallStackContext::TraceFailure(v24, "CMediaSession::CreateQualityManager", 9976, Instance);
      }
      if ( g_wppLevels )
      {
        v14 = 799;
        goto LABEL_51;
      }
    }
  }
LABEL_52:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v26);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180165228  mov     [rsp+arg_10], rbx
0x18016522d  push    rsi
0x18016522e  push    rdi
0x18016522f  push    r14
0x180165231  sub     rsp, 50h
0x180165235  mov     rax, cs:__security_cookie
0x18016523c  xor     rax, rsp
0x18016523f  mov     [rsp+68h+var_20], rax
0x180165244  mov     rax, gs:58h
0x18016524d  mov     rsi, rcx
0x180165250  mov     ecx, cs:_tls_index
0x180165256  mov     r14, rdx
0x180165259  mov     edx, 4
0x18016525e  mov     rax, [rax+rcx*8]
0x180165262  mov     eax, [rdx+rax]
0x180165265  cmp     cs:dword_1803CF258, eax
0x18016526b  jle     short loc_1801652AD
0x18016526d  lea     rcx, dword_1803CF258
0x180165274  call    _Init_thread_header
0x180165279  cmp     cs:dword_1803CF258, 0FFFFFFFFh
0x180165280  jnz     short loc_1801652AD
0x180165282  lea     rcx, stru_1803CF260; lpCriticalSection
0x180165289  call    cs:__imp_InitializeCriticalSection
0x180165290  nop     dword ptr [rax+rax+00h]
0x180165295  lea     rcx, _CMediaSession__CreateQualityManager____2____dynamic_atexit_destructor_for__s_createQMLock__; void (__cdecl *)()
0x18016529c  call    atexit
0x1801652a1  lea     rcx, dword_1803CF258
0x1801652a8  call    _Init_thread_footer
0x1801652ad  mov     r8d, 26C1h; int
0x1801652b3  lea     rdx, aCmediasessionC_7; "CMediaSession::CreateQualityManager"
0x1801652ba  lea     rcx, [rsp+68h+var_38]; this
0x1801652bf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801652c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801652cb  cmp     byte ptr [rcx+8], 0
0x1801652cf  jz      short loc_18016532F
0x1801652d1  cmp     qword ptr [rsi+650h], 0
0x1801652d9  jz      short loc_18016532F
0x1801652db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801652e0  mov     rdx, [rsi+650h]
0x1801652e7  mov     rdi, rax
0x1801652ea  mov     rcx, [rdx]
0x1801652ed  mov     rax, [rcx+128h]
0x1801652f4  mov     rcx, rdx
0x1801652f7  call    cs:__guard_dispatch_icall_fptr
0x1801652fd  mov     r8, [rsi+650h]
0x180165304  lea     rdx, [rsp+68h+Buf1]
0x180165309  mov     ebx, eax
0x18016530b  mov     rcx, [r8]
0x18016530e  mov     rax, [rcx+118h]
0x180165315  mov     rcx, r8
0x180165318  call    cs:__guard_dispatch_icall_fptr
0x18016531e  movups  xmm0, xmmword ptr [rax]
0x180165321  mov     [rdi+7E0h], ebx
0x180165327  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18016532f  lea     rcx, stru_1803CF260; lpCriticalSection
0x180165336  call    cs:__imp_EnterCriticalSection
0x18016533d  nop     dword ptr [rax+rax+00h]
0x180165342  cmp     cs:dword_1803CEFD8, 0
0x180165349  mov     edi, 1
0x18016534e  jnz     short loc_180165386
0x180165350  lea     r8, [rsp+68h+var_34]
0x180165355  mov     [rsp+68h+var_34], 0
0x18016535d  lea     rdx, aQmDisableqm; "QM\\DisableQM"
0x180165364  xor     ecx, ecx
0x180165366  call    cs:__imp_MFGetConfigurationDWORD
0x18016536d  nop     dword ptr [rax+rax+00h]
0x180165372  test    eax, eax
0x180165374  js      short loc_180165380
0x180165376  mov     eax, [rsp+68h+var_34]
0x18016537a  mov     cs:dword_1803CEFD4, eax
0x180165380  mov     cs:dword_1803CEFD8, edi
0x180165386  cmp     cs:dword_1803CEFD4, 0
0x18016538d  jz      short loc_1801653D1
0x18016538f  xor     ebx, ebx
0x180165391  cmp     cs:byte_1803CECE9, 8
0x180165398  jb      short loc_1801653B9
0x18016539a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801653a1  lea     r8, WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids
0x1801653a8  mov     edx, 31Ch
0x1801653ad  mov     r9, rsi
0x1801653b0  mov     rcx, [rcx+38h]
0x1801653b4  call    WPP_SF_q
0x1801653b9  lea     rcx, stru_1803CF260; lpCriticalSection
0x1801653c0  call    cs:__imp_LeaveCriticalSection
0x1801653c7  nop     dword ptr [rax+rax+00h]
0x1801653cc  jmp     loc_180165670
0x1801653d1  lea     rcx, stru_1803CF260; lpCriticalSection
0x1801653d8  call    cs:__imp_LeaveCriticalSection
0x1801653df  nop     dword ptr [rax+rax+00h]
0x1801653e4  test    r14, r14
0x1801653e7  jz      loc_1801655AF
0x1801653ed  mov     rax, [r14]
0x1801653f0  lea     r8, [rsp+68h+Buf1]
0x1801653f5  xorps   xmm0, xmm0
0x1801653f8  lea     rdx, MF_SESSION_QUALITY_MANAGER
0x1801653ff  mov     rcx, r14
0x180165402  movups  [rsp+68h+Buf1], xmm0
0x180165407  mov     rax, [rax+50h]
0x18016540b  call    cs:__guard_dispatch_icall_fptr
0x180165411  mov     ebx, eax
0x180165413  test    eax, eax
0x180165415  jns     loc_1801654C7
0x18016541b  lea     rcx, [rsi+638h]; struct IMFQualityManager **
0x180165422  call    ?CreateInstance@CMFQualityManager@@SAJPEAPEAUIMFQualityManager@@@Z; CMFQualityManager::CreateInstance(IMFQualityManager * *)
0x180165427  mov     ebx, eax
0x180165429  test    eax, eax
0x18016542b  jns     loc_180165670
0x180165431  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180165438  test    rcx, rcx
0x18016543b  jnz     short loc_180165485
0x18016543d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180165444  nop     dword ptr [rax+rax+00h]
0x180165449  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180165450  mov     rcx, rax
0x180165453  test    rax, rax
0x180165456  jz      short loc_180165477
0x180165458  mov     rax, [rax]
0x18016545b  mov     edx, 7F0h
0x180165460  mov     rax, [rax+8]
0x180165464  call    cs:__guard_dispatch_icall_fptr
0x18016546a  test    eax, eax
0x18016546c  jz      short loc_180165477
0x18016546e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180165475  jmp     short loc_180165485
0x180165477  lea     rcx, qword_1803CE250; this
0x18016547e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180165485  cmp     byte ptr [rcx+8], 0
0x180165489  jz      short loc_1801654B0
0x18016548b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180165490  cmp     [rax+7CCh], ebx
0x180165496  jz      short loc_1801654B0
0x180165498  mov     r9d, ebx; int
0x18016549b  lea     rdx, aCmediasessionC_7; "CMediaSession::CreateQualityManager"
0x1801654a2  mov     r8d, 26EAh; int
0x1801654a8  mov     rcx, rax; this
0x1801654ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801654b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801654b7  jb      loc_180165670
0x1801654bd  mov     edx, 31Dh
0x1801654c2  jmp     loc_180165652
0x1801654c7  mov     r8d, 10h; Size
0x1801654cd  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1801654d4  lea     rcx, [rsp+68h+Buf1]; Buf1
0x1801654d9  call    memcmp_0
0x1801654de  test    eax, eax
0x1801654e0  jz      loc_180165670
0x1801654e6  lea     rax, [rsi+638h]
0x1801654ed  mov     r8d, edi; dwClsContext
0x1801654f0  lea     r9, IID_IMFQualityManager; riid
0x1801654f7  mov     [rsp+68h+ppv], rax; ppv
0x1801654fc  xor     edx, edx; pUnkOuter
0x1801654fe  lea     rcx, [rsp+68h+Buf1]; rclsid
0x180165503  call    cs:__imp_CoCreateInstance
0x18016550a  nop     dword ptr [rax+rax+00h]
0x18016550f  mov     ebx, eax
0x180165511  test    eax, eax
0x180165513  jns     loc_180165670
0x180165519  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180165520  test    rcx, rcx
0x180165523  jnz     short loc_18016556D
0x180165525  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016552c  nop     dword ptr [rax+rax+00h]
0x180165531  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180165538  mov     rcx, rax
0x18016553b  test    rax, rax
0x18016553e  jz      short loc_18016555F
0x180165540  mov     rax, [rax]
0x180165543  mov     edx, 7F0h
0x180165548  mov     rax, [rax+8]
0x18016554c  call    cs:__guard_dispatch_icall_fptr
0x180165552  test    eax, eax
0x180165554  jz      short loc_18016555F
0x180165556  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016555d  jmp     short loc_18016556D
0x18016555f  lea     rcx, qword_1803CE250; this
0x180165566  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016556d  cmp     byte ptr [rcx+8], 0
0x180165571  jz      short loc_180165598
0x180165573  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180165578  cmp     [rax+7CCh], ebx
0x18016557e  jz      short loc_180165598
0x180165580  mov     r9d, ebx; int
0x180165583  lea     rdx, aCmediasessionC_7; "CMediaSession::CreateQualityManager"
0x18016558a  mov     r8d, 26F2h; int
0x180165590  mov     rcx, rax; this
0x180165593  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180165598  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18016559f  jb      loc_180165670
0x1801655a5  mov     edx, 31Eh
0x1801655aa  jmp     loc_180165652
0x1801655af  lea     rcx, [rsi+638h]; struct IMFQualityManager **
0x1801655b6  call    ?CreateInstance@CMFQualityManager@@SAJPEAPEAUIMFQualityManager@@@Z; CMFQualityManager::CreateInstance(IMFQualityManager * *)
0x1801655bb  mov     ebx, eax
0x1801655bd  test    eax, eax
0x1801655bf  jns     loc_180165670
0x1801655c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801655cc  test    rcx, rcx
0x1801655cf  jnz     short loc_180165619
0x1801655d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801655d8  nop     dword ptr [rax+rax+00h]
0x1801655dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801655e4  mov     rcx, rax
0x1801655e7  test    rax, rax
0x1801655ea  jz      short loc_18016560B
0x1801655ec  mov     rax, [rax]
0x1801655ef  mov     edx, 7F0h
0x1801655f4  mov     rax, [rax+8]
0x1801655f8  call    cs:__guard_dispatch_icall_fptr
0x1801655fe  test    eax, eax
0x180165600  jz      short loc_18016560B
0x180165602  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180165609  jmp     short loc_180165619
0x18016560b  lea     rcx, qword_1803CE250; this
0x180165612  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180165619  cmp     byte ptr [rcx+8], 0
0x18016561d  jz      short loc_180165644
0x18016561f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180165624  cmp     [rax+7CCh], ebx
0x18016562a  jz      short loc_180165644
0x18016562c  mov     r9d, ebx; int
0x18016562f  lea     rdx, aCmediasessionC_7; "CMediaSession::CreateQualityManager"
0x180165636  mov     r8d, 26F8h; int
0x18016563c  mov     rcx, rax; this
0x18016563f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180165644  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18016564b  jb      short loc_180165670
0x18016564d  mov     edx, 31Fh
0x180165652  mov     rcx, cs:WPP_GLOBAL_Control
0x180165659  lea     r8, WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids
0x180165660  mov     r9, rsi
0x180165663  mov     dword ptr [rsp+68h+ppv], ebx
0x180165667  mov     rcx, [rcx+10h]
0x18016566b  call    WPP_SF_qD
0x180165670  lea     rcx, [rsp+68h+var_38]; this
0x180165675  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18016567a  mov     eax, ebx
0x18016567c  mov     rcx, [rsp+68h+var_20]
0x180165681  xor     rcx, rsp; StackCookie
0x180165684  call    __security_check_cookie
0x180165689  mov     rbx, [rsp+68h+arg_10]
0x180165691  add     rsp, 50h
0x180165695  pop     r14
0x180165697  pop     rdi
0x180165698  pop     rsi
0x180165699  retn
```
