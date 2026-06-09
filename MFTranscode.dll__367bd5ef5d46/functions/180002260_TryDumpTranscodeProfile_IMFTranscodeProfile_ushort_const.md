# TryDumpTranscodeProfile(IMFTranscodeProfile *,ushort const *)

- ea: `0x180002260`
- end: `0x1800026e5`
- name: `?TryDumpTranscodeProfile@@YAJPEAUIMFTranscodeProfile@@PEBG@Z`
- size: `1157`
- prototype: `__int64 __fastcall(struct IMFTranscodeProfile *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800019a0`
- `0x180036820`
- `0x18003b8cc`

## callees

- `0x180002260`
- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x180017068`
- `0x180017074`
- `0x18001a320`
- `0x18001a330`
- `0x18001c280`
- `0x18003717c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000249b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000249b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800022f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000240c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800024b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002567`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002615`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800022f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000240c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800024b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002567`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002615`
- `MFPlat!MFGetConfigurationString` at `0x18000228b`
- `MFPlat!MFGetConfigurationString` at `0x1800023a2`
- `MFPlat!MFGetConfigurationString` at `0x18000228b`
- `MFPlat!MFGetConfigurationString` at `0x1800023a2`

## pseudocode

```c
__int64 __fastcall TryDumpTranscodeProfile(struct IMFTranscodeProfile *a1, const unsigned __int16 *a2)
{
  HRESULT v3; // ebx
  WCHAR *v5; // rdi
  __int64 v6; // rdx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  struct IMFTranscodeProfileVtbl *lpVtbl; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  IStream *ppstm; // [rsp+30h] [rbp-10h] BYREF
  __int64 v32; // [rsp+38h] [rbp-8h] BYREF
  char v33; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v34; // [rsp+78h] [rbp+38h] BYREF

  v3 = 0;
  v34 = 0;
  v5 = 0;
  if ( !(unsigned int)MFGetConfigurationString(0, a2, 0, &v34) && v34 > 1 )
  {
    v5 = (WCHAR *)operator new(saturated_mul(v34, 2u));
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "TryDumpTranscodeProfile", 39);
    if ( !v5 )
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      v3 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "TryDumpTranscodeProfile", 39, -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
          0,
          -2147024882);
      goto LABEL_63;
    }
    if ( (unsigned int)MFGetConfigurationString(0, a2, v5, &v34) )
    {
LABEL_63:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
      goto LABEL_64;
    }
    v5[v34 - 1] = 0;
    if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() >= 8u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), v10, v11, v5);
    lpVtbl = a1->lpVtbl;
    v32 = 0;
    ppstm = 0;
    v3 = ((__int64 (__fastcall *)(struct IMFTranscodeProfile *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a1,
           &IID_IPersistStream,
           &v32);
    if ( v3 >= 0 )
    {
      v3 = SHCreateStreamOnFileW(v5, 0x1001u, &ppstm);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, IStream *, _QWORD))(*(_QWORD *)v32 + 48LL))(v32, ppstm, 0);
        if ( v3 >= 0 )
        {
          v3 = ((__int64 (__fastcall *)(IStream *, __int64))ppstm->lpVtbl->Commit)(ppstm, 1);
          if ( v3 >= 0 )
            goto LABEL_62;
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
            CallStackTracing::s_wpInstance = v28;
            if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
            {
              v27 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v27 + 8) )
          {
            v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)v29 + 499) != v3 )
              CallStackContext::TraceFailure(v29, "TryDumpTranscodeProfile", 52, v3);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_62;
          v17 = 15;
        }
        else
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != v3 )
              CallStackContext::TraceFailure(v25, "TryDumpTranscodeProfile", 51, v3);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_62;
          v17 = 14;
        }
      }
      else
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v21 + 499) != v3 )
            CallStackContext::TraceFailure(v21, "TryDumpTranscodeProfile", 50, v3);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_62;
        v17 = 13;
      }
    }
    else
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
        if ( *((_DWORD *)v16 + 499) != v3 )
          CallStackContext::TraceFailure(v16, "TryDumpTranscodeProfile", 49, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_62;
      v17 = 12;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, 0, v3);
LABEL_62:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v32);
    goto LABEL_63;
  }
LABEL_64:
  operator delete(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002260  mov     [rsp-18h+arg_0], rbx
0x180002265  mov     [rsp-18h+arg_8], rsi
0x18000226a  push    rbp
0x18000226b  push    rdi
0x18000226c  push    r14
0x18000226e  mov     rbp, rsp
0x180002271  sub     rsp, 40h
0x180002275  mov     r14, rcx
0x180002278  lea     r9, [rbp+arg_18]
0x18000227c  xor     ebx, ebx
0x18000227e  xor     ecx, ecx
0x180002280  xor     r8d, r8d
0x180002283  mov     [rbp+arg_18], ebx
0x180002286  mov     rsi, rdx
0x180002289  xor     edi, edi
0x18000228b  call    cs:__imp_MFGetConfigurationString
0x180002291  test    eax, eax
0x180002293  jnz     loc_1800026C8
0x180002299  mov     eax, [rbp+arg_18]
0x18000229c  cmp     eax, 1
0x18000229f  jbe     loc_1800026C8
0x1800022a5  mov     ecx, eax
0x1800022a7  mov     eax, 2
0x1800022ac  mul     rcx
0x1800022af  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800022b6  cmovb   rax, rcx
0x1800022ba  mov     rcx, rax; Size
0x1800022bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800022c2  mov     r8d, 27h ; '''; int
0x1800022c8  lea     rdx, aTrydumptransco; "TryDumpTranscodeProfile"
0x1800022cf  lea     rcx, [rbp+arg_10]; this
0x1800022d3  mov     rdi, rax
0x1800022d6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800022db  test    rdi, rdi
0x1800022de  jnz     loc_180002396
0x1800022e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800022eb  mov     ebx, 8007000Eh
0x1800022f0  test    rcx, rcx
0x1800022f3  jnz     short loc_180002336
0x1800022f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800022fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180002302  mov     rcx, rax
0x180002305  test    rax, rax
0x180002308  jz      short loc_180002328
0x18000230a  mov     rax, [rax]
0x18000230d  mov     edx, 7F0h
0x180002312  mov     rax, [rax+8]
0x180002316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000231b  test    eax, eax
0x18000231d  jz      short loc_180002328
0x18000231f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002326  jmp     short loc_180002336
0x180002328  lea     rcx, qword_180069A90; this
0x18000232f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180002336  cmp     byte ptr [rcx+8], 0
0x18000233a  jz      short loc_180002361
0x18000233c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180002341  cmp     [rax+7CCh], ebx
0x180002347  jz      short loc_180002361
0x180002349  mov     r9d, ebx; int
0x18000234c  lea     rdx, aTrydumptransco; "TryDumpTranscodeProfile"
0x180002353  mov     r8d, 27h ; '''; int
0x180002359  mov     rcx, rax; this
0x18000235c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180002361  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180002366  cmp     al, 1
0x180002368  jb      loc_1800026BF
0x18000236e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002375  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x18000237c  mov     edx, 0Ah
0x180002381  mov     [rsp+40h+var_20], ebx
0x180002385  xor     r9d, r9d
0x180002388  mov     rcx, [rcx+10h]
0x18000238c  call    WPP_SF_qd
0x180002391  jmp     loc_1800026BF
0x180002396  lea     r9, [rbp+arg_18]
0x18000239a  mov     r8, rdi
0x18000239d  mov     rdx, rsi
0x1800023a0  xor     ecx, ecx
0x1800023a2  call    cs:__imp_MFGetConfigurationString
0x1800023a8  test    eax, eax
0x1800023aa  jnz     loc_1800026BF
0x1800023b0  mov     ecx, [rbp+arg_18]
0x1800023b3  dec     ecx
0x1800023b5  mov     [rdi+rcx*2], ax
0x1800023b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x1800023be  cmp     al, 8
0x1800023c0  jb      short loc_1800023D5
0x1800023c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023c9  mov     r9, rdi
0x1800023cc  mov     rcx, [rcx+38h]
0x1800023d0  call    WPP_SF_S
0x1800023d5  mov     rax, [r14]
0x1800023d8  lea     r8, [rbp+var_8]
0x1800023dc  lea     rdx, IID_IPersistStream
0x1800023e3  mov     [rbp+var_8], rbx
0x1800023e7  mov     rcx, r14
0x1800023ea  mov     [rbp+ppstm], rbx
0x1800023ee  mov     rax, [rax]
0x1800023f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f6  mov     ebx, eax
0x1800023f8  test    eax, eax
0x1800023fa  jns     loc_18000248F
0x180002400  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002407  test    rcx, rcx
0x18000240a  jnz     short loc_18000244D
0x18000240c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180002412  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180002419  mov     rcx, rax
0x18000241c  test    rax, rax
0x18000241f  jz      short loc_18000243F
0x180002421  mov     rax, [rax]
0x180002424  mov     edx, 7F0h
0x180002429  mov     rax, [rax+8]
0x18000242d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002432  test    eax, eax
0x180002434  jz      short loc_18000243F
0x180002436  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000243d  jmp     short loc_18000244D
0x18000243f  lea     rcx, qword_180069A90; this
0x180002446  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000244d  cmp     byte ptr [rcx+8], 0
0x180002451  jz      short loc_180002478
0x180002453  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180002458  cmp     [rax+7CCh], ebx
0x18000245e  jz      short loc_180002478
0x180002460  mov     r9d, ebx; int
0x180002463  lea     rdx, aTrydumptransco; "TryDumpTranscodeProfile"
0x18000246a  mov     r8d, 31h ; '1'; int
0x180002470  mov     rcx, rax; this
0x180002473  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180002478  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000247d  cmp     al, 1
0x18000247f  jb      loc_1800026AD
0x180002485  mov     edx, 0Ch
0x18000248a  jmp     loc_18000268F
0x18000248f  lea     r8, [rbp+ppstm]; ppstm
0x180002493  mov     edx, 1001h; grfMode
0x180002498  mov     rcx, rdi; pszFile
0x18000249b  call    cs:__imp_SHCreateStreamOnFileW
0x1800024a1  mov     ebx, eax
0x1800024a3  test    eax, eax
0x1800024a5  jns     loc_18000253A
0x1800024ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800024b2  test    rcx, rcx
0x1800024b5  jnz     short loc_1800024F8
0x1800024b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800024bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800024c4  mov     rcx, rax
0x1800024c7  test    rax, rax
0x1800024ca  jz      short loc_1800024EA
0x1800024cc  mov     rax, [rax]
0x1800024cf  mov     edx, 7F0h
0x1800024d4  mov     rax, [rax+8]
0x1800024d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024dd  test    eax, eax
0x1800024df  jz      short loc_1800024EA
0x1800024e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800024e8  jmp     short loc_1800024F8
0x1800024ea  lea     rcx, qword_180069A90; this
0x1800024f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800024f8  cmp     byte ptr [rcx+8], 0
0x1800024fc  jz      short loc_180002523
0x1800024fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180002503  cmp     [rax+7CCh], ebx
0x180002509  jz      short loc_180002523
0x18000250b  mov     r9d, ebx; int
0x18000250e  lea     rdx, aTrydumptransco; "TryDumpTranscodeProfile"
0x180002515  mov     r8d, 32h ; '2'; int
0x18000251b  mov     rcx, rax; this
0x18000251e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180002523  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180002528  cmp     al, 1
0x18000252a  jb      loc_1800026AD
0x180002530  mov     edx, 0Dh
0x180002535  jmp     loc_18000268F
0x18000253a  mov     rcx, [rbp+var_8]
0x18000253e  xor     r8d, r8d
0x180002541  mov     rdx, [rbp+ppstm]
0x180002545  mov     rax, [rcx]
0x180002548  mov     rax, [rax+30h]
0x18000254c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002551  mov     ebx, eax
0x180002553  test    eax, eax
0x180002555  jns     loc_1800025EA
0x18000255b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002562  test    rcx, rcx
0x180002565  jnz     short loc_1800025A8
0x180002567  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000256d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180002574  mov     rcx, rax
0x180002577  test    rax, rax
0x18000257a  jz      short loc_18000259A
0x18000257c  mov     rax, [rax]
0x18000257f  mov     edx, 7F0h
0x180002584  mov     rax, [rax+8]
0x180002588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000258d  test    eax, eax
0x18000258f  jz      short loc_18000259A
0x180002591  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002598  jmp     short loc_1800025A8
0x18000259a  lea     rcx, qword_180069A90; this
0x1800025a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800025a8  cmp     byte ptr [rcx+8], 0
0x1800025ac  jz      short loc_1800025D3
0x1800025ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800025b3  cmp     [rax+7CCh], ebx
0x1800025b9  jz      short loc_1800025D3
0x1800025bb  mov     r9d, ebx; int
0x1800025be  lea     rdx, aTrydumptransco; "TryDumpTranscodeProfile"
0x1800025c5  mov     r8d, 33h ; '3'; int
0x1800025cb  mov     rcx, rax; this
0x1800025ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800025d3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800025d8  cmp     al, 1
0x1800025da  jb      loc_1800026AD
0x1800025e0  mov     edx, 0Eh
0x1800025e5  jmp     loc_18000268F
0x1800025ea  mov     rcx, [rbp+ppstm]
0x1800025ee  mov     edx, 1
0x1800025f3  mov     rax, [rcx]
0x1800025f6  mov     rax, [rax+40h]
0x1800025fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ff  mov     ebx, eax
0x180002601  test    eax, eax
0x180002603  jns     loc_1800026AD
0x180002609  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002610  test    rcx, rcx
0x180002613  jnz     short loc_180002656
0x180002615  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000261b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180002622  mov     rcx, rax
0x180002625  test    rax, rax
0x180002628  jz      short loc_180002648
0x18000262a  mov     rax, [rax]
0x18000262d  mov     edx, 7F0h
0x180002632  mov     rax, [rax+8]
0x180002636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000263b  test    eax, eax
0x18000263d  jz      short loc_180002648
0x18000263f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002646  jmp     short loc_180002656
0x180002648  lea     rcx, qword_180069A90; this
0x18000264f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180002656  cmp     byte ptr [rcx+8], 0
0x18000265a  jz      short loc_180002681
0x18000265c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180002661  cmp     [rax+7CCh], ebx
0x180002667  jz      short loc_180002681
0x180002669  mov     r9d, ebx; int
0x18000266c  lea     rdx, aTrydumptransco; "TryDumpTranscodeProfile"
0x180002673  mov     r8d, 34h ; '4'; int
0x180002679  mov     rcx, rax; this
0x18000267c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180002681  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180002686  cmp     al, 1
0x180002688  jb      short loc_1800026AD
0x18000268a  mov     edx, 0Fh
0x18000268f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002696  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x18000269d  xor     r9d, r9d
0x1800026a0  mov     [rsp+40h+var_20], ebx
0x1800026a4  mov     rcx, [rcx+10h]
0x1800026a8  call    WPP_SF_qd
0x1800026ad  lea     rcx, [rbp+ppstm]
0x1800026b1  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800026b6  lea     rcx, [rbp+var_8]
0x1800026ba  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800026bf  lea     rcx, [rbp+arg_10]; this
0x1800026c3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800026c8  mov     rcx, rdi; Block
0x1800026cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800026d0  mov     rsi, [rsp+40h+arg_8]
0x1800026d5  mov     eax, ebx
0x1800026d7  mov     rbx, [rsp+40h+arg_0]
0x1800026dc  add     rsp, 40h
0x1800026e0  pop     r14
0x1800026e2  pop     rdi
0x1800026e3  pop     rbp
0x1800026e4  retn
```
