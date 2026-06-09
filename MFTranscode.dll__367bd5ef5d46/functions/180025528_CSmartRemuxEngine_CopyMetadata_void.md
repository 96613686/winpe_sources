# CSmartRemuxEngine::_CopyMetadata(void)

- ea: `0x180025528`
- end: `0x1800257d6`
- name: `?_CopyMetadata@CSmartRemuxEngine@@IEAAJXZ`
- size: `686`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f5b8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x180025528`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002559f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025663`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025713`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002559f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025663`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025713`
- `MFCORE!CopyPropertyStore` at `0x1800256f7`
- `MFCORE!CopyPropertyStore` at `0x1800256f7`

## string_xrefs

- `0x180025535`: `CSmartRemuxEngine::_CopyMetadata`
- `0x1800255f6`: `CSmartRemuxEngine::_CopyMetadata`
- `0x1800256ba`: `CSmartRemuxEngine::_CopyMetadata`
- `0x18002576a`: `CSmartRemuxEngine::_CopyMetadata`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_CopyMetadata(CSmartRemuxEngine *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  int v4; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v18; // [rsp+40h] [rbp+8h] BYREF
  __int64 v19; // [rsp+48h] [rbp+10h] BYREF
  __int64 v20; // [rsp+50h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v18, "CSmartRemuxEngine::_CopyMetadata", 2318);
  v2 = *((_QWORD *)this + 4);
  v20 = 0;
  v19 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, const IID *, GUID *, __int64 *))(*(_QWORD *)v2 + 88LL))(
         v2,
         0xFFFFFFFFLL,
         &MF_PROPERTY_HANDLER_SERVICE,
         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
         &v20);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, const IID *, GUID *, __int64 *))(**((_QWORD **)this + 5) + 96LL))(
           *((_QWORD *)this + 5),
           0xFFFFFFFFLL,
           &MF_PROPERTY_HANDLER_SERVICE,
           &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
           &v19);
    if ( v4 >= 0 )
    {
      v4 = CopyPropertyStore(&GUID_00000000_0000_0000_0000_000000000000, v19, v20);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_CopyMetadata", 2332, v4);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v8 = 303;
          goto LABEL_34;
        }
      }
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != v4 )
          CallStackContext::TraceFailure(v12, "CSmartRemuxEngine::_CopyMetadata", 2330, v4);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 302;
        goto LABEL_34;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != v4 )
        CallStackContext::TraceFailure(v7, "CSmartRemuxEngine::_CopyMetadata", 2325, v4);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 301;
LABEL_34:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v4);
    }
  }
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v19);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v20);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025528  mov     [rsp+arg_18], rbx
0x18002552d  push    rdi
0x18002552e  sub     rsp, 30h
0x180025532  mov     rdi, rcx
0x180025535  lea     rdx, aCsmartremuxeng_7; "CSmartRemuxEngine::_CopyMetadata"
0x18002553c  lea     rcx, [rsp+38h+arg_0]; this
0x180025541  mov     r8d, 90Eh; int
0x180025547  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002554c  mov     rcx, [rdi+20h]
0x180025550  lea     rdx, [rsp+38h+arg_10]
0x180025555  mov     [rsp+38h+arg_10], 0
0x18002555e  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180025565  mov     [rsp+38h+arg_8], 0
0x18002556e  lea     r8, MF_PROPERTY_HANDLER_SERVICE
0x180025575  mov     [rsp+38h+var_18], rdx
0x18002557a  or      edx, 0FFFFFFFFh
0x18002557d  mov     rax, [rcx]
0x180025580  mov     rax, [rax+58h]
0x180025584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025589  mov     ebx, eax
0x18002558b  test    eax, eax
0x18002558d  jns     loc_180025622
0x180025593  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002559a  test    rcx, rcx
0x18002559d  jnz     short loc_1800255E0
0x18002559f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800255a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800255ac  mov     rcx, rax
0x1800255af  test    rax, rax
0x1800255b2  jz      short loc_1800255D2
0x1800255b4  mov     rax, [rax]
0x1800255b7  mov     edx, 7F0h
0x1800255bc  mov     rax, [rax+8]
0x1800255c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255c5  test    eax, eax
0x1800255c7  jz      short loc_1800255D2
0x1800255c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800255d0  jmp     short loc_1800255E0
0x1800255d2  lea     rcx, qword_180069A90; this
0x1800255d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800255e0  cmp     byte ptr [rcx+8], 0
0x1800255e4  jz      short loc_18002560B
0x1800255e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800255eb  cmp     [rax+7CCh], ebx
0x1800255f1  jz      short loc_18002560B
0x1800255f3  mov     r9d, ebx; int
0x1800255f6  lea     rdx, aCsmartremuxeng_7; "CSmartRemuxEngine::_CopyMetadata"
0x1800255fd  mov     r8d, 915h; int
0x180025603  mov     rcx, rax; this
0x180025606  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002560b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180025610  cmp     al, 1
0x180025612  jb      loc_1800257AB
0x180025618  mov     edx, 12Dh
0x18002561d  jmp     loc_18002578D
0x180025622  mov     rcx, [rdi+28h]
0x180025626  lea     r10, [rsp+38h+arg_8]
0x18002562b  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180025632  mov     [rsp+38h+var_18], r10
0x180025637  lea     r8, MF_PROPERTY_HANDLER_SERVICE
0x18002563e  or      edx, 0FFFFFFFFh
0x180025641  mov     rax, [rcx]
0x180025644  mov     rax, [rax+60h]
0x180025648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002564d  mov     ebx, eax
0x18002564f  test    eax, eax
0x180025651  jns     loc_1800256E6
0x180025657  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002565e  test    rcx, rcx
0x180025661  jnz     short loc_1800256A4
0x180025663  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025669  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025670  mov     rcx, rax
0x180025673  test    rax, rax
0x180025676  jz      short loc_180025696
0x180025678  mov     rax, [rax]
0x18002567b  mov     edx, 7F0h
0x180025680  mov     rax, [rax+8]
0x180025684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025689  test    eax, eax
0x18002568b  jz      short loc_180025696
0x18002568d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025694  jmp     short loc_1800256A4
0x180025696  lea     rcx, qword_180069A90; this
0x18002569d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800256a4  cmp     byte ptr [rcx+8], 0
0x1800256a8  jz      short loc_1800256CF
0x1800256aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800256af  cmp     [rax+7CCh], ebx
0x1800256b5  jz      short loc_1800256CF
0x1800256b7  mov     r9d, ebx; int
0x1800256ba  lea     rdx, aCsmartremuxeng_7; "CSmartRemuxEngine::_CopyMetadata"
0x1800256c1  mov     r8d, 91Ah; int
0x1800256c7  mov     rcx, rax; this
0x1800256ca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800256cf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800256d4  cmp     al, 1
0x1800256d6  jb      loc_1800257AB
0x1800256dc  mov     edx, 12Eh
0x1800256e1  jmp     loc_18002578D
0x1800256e6  mov     r8, [rsp+38h+arg_10]
0x1800256eb  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000
0x1800256f2  mov     rdx, [rsp+38h+arg_8]
0x1800256f7  call    cs:__imp_CopyPropertyStore
0x1800256fd  mov     ebx, eax
0x1800256ff  test    eax, eax
0x180025701  jns     loc_1800257AB
0x180025707  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002570e  test    rcx, rcx
0x180025711  jnz     short loc_180025754
0x180025713  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025719  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025720  mov     rcx, rax
0x180025723  test    rax, rax
0x180025726  jz      short loc_180025746
0x180025728  mov     rax, [rax]
0x18002572b  mov     edx, 7F0h
0x180025730  mov     rax, [rax+8]
0x180025734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025739  test    eax, eax
0x18002573b  jz      short loc_180025746
0x18002573d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025744  jmp     short loc_180025754
0x180025746  lea     rcx, qword_180069A90; this
0x18002574d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025754  cmp     byte ptr [rcx+8], 0
0x180025758  jz      short loc_18002577F
0x18002575a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002575f  cmp     [rax+7CCh], ebx
0x180025765  jz      short loc_18002577F
0x180025767  mov     r9d, ebx; int
0x18002576a  lea     rdx, aCsmartremuxeng_7; "CSmartRemuxEngine::_CopyMetadata"
0x180025771  mov     r8d, 91Ch; int
0x180025777  mov     rcx, rax; this
0x18002577a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002577f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180025784  cmp     al, 1
0x180025786  jb      short loc_1800257AB
0x180025788  mov     edx, 12Fh
0x18002578d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025794  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x18002579b  mov     r9, rdi
0x18002579e  mov     dword ptr [rsp+38h+var_18], ebx
0x1800257a2  mov     rcx, [rcx+10h]
0x1800257a6  call    WPP_SF_qd
0x1800257ab  lea     rcx, [rsp+38h+arg_8]
0x1800257b0  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800257b5  lea     rcx, [rsp+38h+arg_10]
0x1800257ba  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800257bf  lea     rcx, [rsp+38h+arg_0]; this
0x1800257c4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800257c9  mov     eax, ebx
0x1800257cb  mov     rbx, [rsp+38h+arg_18]
0x1800257d0  add     rsp, 30h
0x1800257d4  pop     rdi
0x1800257d5  retn
```
