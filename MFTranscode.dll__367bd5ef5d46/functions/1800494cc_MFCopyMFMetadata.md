# MFCopyMFMetadata

- ea: `0x1800494cc`
- end: `0x18004979b`
- name: `MFCopyMFMetadata`
- size: `719`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180038188`
- `0x180038368`
- `0x180038604`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x1800494cc`
- `0x180049a9c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800495b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800496d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800495b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800496d5`

## string_xrefs

- `0x180049506`: `MFCopyMFMetadata`
- `0x18004960e`: `MFCopyMFMetadata`
- `0x18004969d`: `MFCopyMFMetadata`
- `0x18004972c`: `MFCopyMFMetadata`

## pseudocode

```c
__int64 __fastcall MFCopyMFMetadata(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v4; // ebx
  __int64 i; // rdi
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // r8d
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v25; // [rsp+30h] [rbp-18h] BYREF
  __int64 v26[2]; // [rsp+38h] [rbp-10h] BYREF
  char v27; // [rsp+A8h] [rbp+60h] BYREF

  v4 = 0;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    v26[0] = 0;
    v25 = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v27, "MFCopyMFMetadata", 225);
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a1 + 24LL))(
           a1,
           0,
           *(unsigned int *)(a3 + 8 * i),
           0,
           v26);
    if ( v4 < 0 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MFCopyMFMetadata", 225, v4);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_38;
      v17 = 16;
LABEL_37:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, 0, v4);
      goto LABEL_38;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           0,
           *(unsigned int *)(a3 + 8 * i + 4),
           0,
           &v25);
    if ( v4 < 0 )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != v4 )
          CallStackContext::TraceFailure(v20, "MFCopyMFMetadata", 226, v4);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_38;
      v17 = 17;
      goto LABEL_37;
    }
    v4 = MFCopyStreamMetadata(v26[0], v25, v12);
    if ( v4 < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != v4 )
          CallStackContext::TraceFailure(v16, "MFCopyMFMetadata", 227, v4);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 18;
        goto LABEL_37;
      }
LABEL_38:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v27);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v25);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v26);
      return (unsigned int)v4;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v27);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v25);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v26);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800494cc  push    rbp
0x1800494ce  push    rbx
0x1800494cf  push    rsi
0x1800494d0  push    rdi
0x1800494d1  push    r12
0x1800494d3  push    r13
0x1800494d5  push    r14
0x1800494d7  push    r15
0x1800494d9  mov     rbp, rsp
0x1800494dc  sub     rsp, 48h
0x1800494e0  xor     ebx, ebx
0x1800494e2  mov     esi, r9d
0x1800494e5  xor     edi, edi
0x1800494e7  mov     r15, r8
0x1800494ea  mov     r14, rdx
0x1800494ed  mov     r13, rcx
0x1800494f0  cmp     edi, esi
0x1800494f2  jnb     loc_180049788
0x1800494f8  mov     r8d, 0E1h; int
0x1800494fe  mov     [rbp+var_10], 0
0x180049506  lea     rdx, aMfcopymfmetada; "MFCopyMFMetadata"
0x18004950d  mov     [rbp+var_18], 0
0x180049515  lea     rcx, [rbp+arg_18]; this
0x180049519  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004951e  mov     rax, [r13+0]
0x180049522  lea     rcx, [rbp+var_10]
0x180049526  mov     r8d, [r15+rdi*8]
0x18004952a  xor     r9d, r9d
0x18004952d  mov     [rsp+48h+var_28], rcx
0x180049532  xor     edx, edx
0x180049534  mov     rcx, r13
0x180049537  mov     rax, [rax+18h]
0x18004953b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049540  mov     ebx, eax
0x180049542  test    eax, eax
0x180049544  js      loc_1800496C9
0x18004954a  mov     rax, [r14]
0x18004954d  lea     rcx, [rbp+var_18]
0x180049551  mov     r8d, [r15+rdi*8+4]
0x180049556  xor     r9d, r9d
0x180049559  mov     [rsp+48h+var_28], rcx
0x18004955e  xor     edx, edx
0x180049560  mov     rcx, r14
0x180049563  mov     rax, [rax+18h]
0x180049567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004956c  mov     ebx, eax
0x18004956e  test    eax, eax
0x180049570  js      loc_18004963A
0x180049576  mov     rdx, [rbp+var_18]
0x18004957a  mov     rcx, [rbp+var_10]
0x18004957e  call    MFCopyStreamMetadata
0x180049583  mov     ebx, eax
0x180049585  test    eax, eax
0x180049587  js      short loc_1800495AB
0x180049589  lea     rcx, [rbp+arg_18]; this
0x18004958d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180049592  lea     rcx, [rbp+var_18]
0x180049596  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18004959b  lea     rcx, [rbp+var_10]
0x18004959f  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800495a4  inc     edi
0x1800495a6  jmp     loc_1800494F0
0x1800495ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800495b2  test    rcx, rcx
0x1800495b5  jnz     short loc_1800495F8
0x1800495b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800495bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800495c4  mov     rcx, rax
0x1800495c7  test    rax, rax
0x1800495ca  jz      short loc_1800495EA
0x1800495cc  mov     rax, [rax]
0x1800495cf  mov     edx, 7F0h
0x1800495d4  mov     rax, [rax+8]
0x1800495d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495dd  test    eax, eax
0x1800495df  jz      short loc_1800495EA
0x1800495e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800495e8  jmp     short loc_1800495F8
0x1800495ea  lea     rcx, qword_180069A90; this
0x1800495f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800495f8  cmp     byte ptr [rcx+8], 0
0x1800495fc  jz      short loc_180049623
0x1800495fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049603  cmp     [rax+7CCh], ebx
0x180049609  jz      short loc_180049623
0x18004960b  mov     r9d, ebx; int
0x18004960e  lea     rdx, aMfcopymfmetada; "MFCopyMFMetadata"
0x180049615  mov     r8d, 0E3h; int
0x18004961b  mov     rcx, rax; this
0x18004961e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049623  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180049628  cmp     al, 1
0x18004962a  jb      loc_18004976D
0x180049630  mov     edx, 12h
0x180049635  jmp     loc_18004974F
0x18004963a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049641  test    rcx, rcx
0x180049644  jnz     short loc_180049687
0x180049646  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004964c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049653  mov     rcx, rax
0x180049656  test    rax, rax
0x180049659  jz      short loc_180049679
0x18004965b  mov     rax, [rax]
0x18004965e  mov     edx, 7F0h
0x180049663  mov     rax, [rax+8]
0x180049667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004966c  test    eax, eax
0x18004966e  jz      short loc_180049679
0x180049670  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049677  jmp     short loc_180049687
0x180049679  lea     rcx, qword_180069A90; this
0x180049680  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049687  cmp     byte ptr [rcx+8], 0
0x18004968b  jz      short loc_1800496B2
0x18004968d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049692  cmp     [rax+7CCh], ebx
0x180049698  jz      short loc_1800496B2
0x18004969a  mov     r9d, ebx; int
0x18004969d  lea     rdx, aMfcopymfmetada; "MFCopyMFMetadata"
0x1800496a4  mov     r8d, 0E2h; int
0x1800496aa  mov     rcx, rax; this
0x1800496ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800496b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800496b7  cmp     al, 1
0x1800496b9  jb      loc_18004976D
0x1800496bf  mov     edx, 11h
0x1800496c4  jmp     loc_18004974F
0x1800496c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800496d0  test    rcx, rcx
0x1800496d3  jnz     short loc_180049716
0x1800496d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800496db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800496e2  mov     rcx, rax
0x1800496e5  test    rax, rax
0x1800496e8  jz      short loc_180049708
0x1800496ea  mov     rax, [rax]
0x1800496ed  mov     edx, 7F0h
0x1800496f2  mov     rax, [rax+8]
0x1800496f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496fb  test    eax, eax
0x1800496fd  jz      short loc_180049708
0x1800496ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049706  jmp     short loc_180049716
0x180049708  lea     rcx, qword_180069A90; this
0x18004970f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049716  cmp     byte ptr [rcx+8], 0
0x18004971a  jz      short loc_180049741
0x18004971c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049721  cmp     [rax+7CCh], ebx
0x180049727  jz      short loc_180049741
0x180049729  mov     r9d, ebx; int
0x18004972c  lea     rdx, aMfcopymfmetada; "MFCopyMFMetadata"
0x180049733  mov     r8d, 0E1h; int
0x180049739  mov     rcx, rax; this
0x18004973c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049741  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180049746  cmp     al, 1
0x180049748  jb      short loc_18004976D
0x18004974a  mov     edx, 10h
0x18004974f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049756  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x18004975d  xor     r9d, r9d
0x180049760  mov     dword ptr [rsp+48h+var_28], ebx
0x180049764  mov     rcx, [rcx+10h]
0x180049768  call    WPP_SF_qd
0x18004976d  lea     rcx, [rbp+arg_18]; this
0x180049771  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180049776  lea     rcx, [rbp+var_18]
0x18004977a  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18004977f  lea     rcx, [rbp+var_10]
0x180049783  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180049788  mov     eax, ebx
0x18004978a  add     rsp, 48h
0x18004978e  pop     r15
0x180049790  pop     r14
0x180049792  pop     r13
0x180049794  pop     r12
0x180049796  pop     rdi
0x180049797  pop     rsi
0x180049798  pop     rbx
0x180049799  pop     rbp
0x18004979a  retn
```
