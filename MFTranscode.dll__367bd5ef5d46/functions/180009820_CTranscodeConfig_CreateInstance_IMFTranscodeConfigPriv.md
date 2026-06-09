# CTranscodeConfig::CreateInstance(IMFTranscodeConfigPriv * *)

- ea: `0x180009820`
- end: `0x180009c43`
- name: `?CreateInstance@CTranscodeConfig@@SAJPEAPEAUIMFTranscodeConfigPriv@@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(struct IMFTranscodeConfigPriv **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800019a0`
- `0x180036820`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180009820`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x180035400`
- `0x18004f3c8`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800098e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800099eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009ad9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009b83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800098e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800099eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009ad9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009b83`

## string_xrefs

- `0x180009999`: `CTranscodeConfig::QueryInterface`
- `0x180009a45`: `CTranscodeConfig::QueryInterface`
- `0x180009b33`: `CTranscodeConfig::QueryInterface`
- `0x180009892`: `CTranscodeConfig::CreateInstance`
- `0x18000993e`: `CTranscodeConfig::CreateInstance`
- `0x180009bda`: `CTranscodeConfig::CreateInstance`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::CreateInstance(struct IMFTranscodeConfigPriv **a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  char *v4; // rdi
  __int64 *v5; // rbx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v7; // esi
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  struct CallStackContext *v10; // rax
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned int v22; // edx
  char v24; // [rsp+58h] [rbp+10h] BYREF

  v4 = (char *)operator new(0x40u);
  if ( v4 )
  {
    *(_QWORD *)v4 = &CTranscodeConfig::`vftable';
    *((_DWORD *)v4 + 8) &= 0xFFFFFFF8;
    *(_QWORD *)(v4 + 36) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_DWORD *)v4 + 11) = 0;
    *((_DWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 7) = 0;
  }
  else
  {
    v4 = 0;
  }
  v5 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
    v3 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v3 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v3 *= 2;
      *((_QWORD *)ThreadRelativeContext + v3) = "CTranscodeConfig::CreateInstance";
      *((_DWORD *)ThreadRelativeContext + 2 * v3 + 2) = 299;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  if ( !v4 )
  {
    v7 = -2147024882;
    if ( !v5 )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v3, v2);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
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
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v9 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v9, "CTranscodeConfig::CreateInstance", 299, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
        0,
        -2147024882);
    goto LABEL_64;
  }
  if ( !v5 )
  {
    CallStackTracing::InitInstance();
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
    v3 = *((unsigned int *)v10 + 497);
    if ( (unsigned int)v3 < *((_DWORD *)v10 + 498) )
    {
      v3 *= 2;
      *((_QWORD *)v10 + v3) = "CTranscodeConfig::QueryInterface";
      *((_DWORD *)v10 + 2 * v3 + 2) = 330;
    }
    ++*((_DWORD *)v10 + 497);
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  if ( !a1 )
  {
    v7 = -2147467261;
    if ( !v5 )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v3, v2);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
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
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v12 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v12, "CTranscodeConfig::QueryInterface", 330, -2147467261);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_52;
    v13 = 51;
    goto LABEL_38;
  }
  *a1 = 0;
  if ( memcmp_0(&IID_IMFTranscodeConfigPriv, &IID_IMFTranscodeConfigPriv, 0x10u)
    && memcmp_0(&IID_IMFTranscodeConfigPriv, &IID_IUnknown, 0x10u) )
  {
    v7 = -2147467262;
    if ( !v5 )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v15, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
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
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v17 + 499) != -2147467262 )
        CallStackContext::TraceFailure(v17, "CTranscodeConfig::QueryInterface", 343, -2147467262);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_52;
    v13 = 52;
LABEL_38:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, v4, v7);
    goto LABEL_52;
  }
  v7 = 0;
  *a1 = (struct IMFTranscodeConfigPriv *)v4;
  _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
LABEL_52:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  if ( v7 < 0 )
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
      if ( *((_DWORD *)v21 + 499) != v7 )
        CallStackContext::TraceFailure(v21, "CTranscodeConfig::CreateInstance", 300, v7);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, 0, v7);
    CTranscodeConfig::`scalar deleting destructor'((CTranscodeConfig *)v4, v22);
  }
LABEL_64:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009820  mov     [rsp+arg_0], rbx
0x180009825  mov     [rsp+arg_10], rsi
0x18000982a  push    rdi
0x18000982b  push    r14
0x18000982d  push    r15
0x18000982f  sub     rsp, 30h
0x180009833  mov     r14, rcx
0x180009836  mov     ecx, 40h ; '@'; Size
0x18000983b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009840  xor     r15d, r15d
0x180009843  mov     rdi, rax
0x180009846  test    rax, rax
0x180009849  jz      short loc_180009877
0x18000984b  lea     rax, ??_7CTranscodeConfig@@6B@; const CTranscodeConfig::`vftable'
0x180009852  mov     [rdi], rax
0x180009855  and     dword ptr [rdi+20h], 0FFFFFFF8h
0x180009859  mov     [rdi+24h], r15
0x18000985d  mov     [rdi+30h], r15
0x180009861  mov     [rdi+2Ch], r15d
0x180009865  mov     [rdi+8], r15d
0x180009869  mov     [rdi+10h], r15
0x18000986d  mov     [rdi+18h], r15
0x180009871  mov     [rdi+38h], r15
0x180009875  jmp     short loc_18000987A
0x180009877  mov     rdi, r15
0x18000987a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009881  test    rbx, rbx
0x180009884  jnz     short loc_180009892
0x180009886  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000988b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009892  lea     rsi, aCtranscodeconf_8; "CTranscodeConfig::CreateInstance"
0x180009899  cmp     [rbx+8], r15b
0x18000989d  jz      short loc_1800098D1
0x18000989f  mov     rcx, rbx; this
0x1800098a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800098a7  mov     ecx, [rax+7C4h]
0x1800098ad  cmp     ecx, [rax+7C8h]
0x1800098b3  jnb     short loc_1800098C4
0x1800098b5  add     rcx, rcx
0x1800098b8  mov     [rax+rcx*8], rsi
0x1800098bc  mov     dword ptr [rax+rcx*8+8], 12Bh
0x1800098c4  inc     dword ptr [rax+7C4h]
0x1800098ca  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098d1  test    rdi, rdi
0x1800098d4  jnz     loc_180009988
0x1800098da  mov     esi, 8007000Eh
0x1800098df  test    rbx, rbx
0x1800098e2  jnz     short loc_180009925
0x1800098e4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800098ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098f1  mov     rcx, rax
0x1800098f4  test    rax, rax
0x1800098f7  jz      short loc_180009917
0x1800098f9  mov     rax, [rax]
0x1800098fc  mov     edx, 7F0h
0x180009901  mov     rax, [rax+8]
0x180009905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000990a  test    eax, eax
0x18000990c  jz      short loc_180009917
0x18000990e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009915  jmp     short loc_180009925
0x180009917  lea     rbx, qword_180069A90
0x18000991e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009925  cmp     [rbx+8], r15b
0x180009929  jz      short loc_180009953
0x18000992b  mov     rcx, rbx; this
0x18000992e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009933  cmp     [rax+7CCh], esi
0x180009939  jz      short loc_180009953
0x18000993b  mov     r9d, esi; int
0x18000993e  lea     rdx, aCtranscodeconf_8; "CTranscodeConfig::CreateInstance"
0x180009945  mov     r8d, 12Bh; int
0x18000994b  mov     rcx, rax; this
0x18000994e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009953  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009958  cmp     al, 1
0x18000995a  jb      loc_180009C23
0x180009960  mov     rcx, cs:WPP_GLOBAL_Control
0x180009967  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x18000996e  mov     edx, 31h ; '1'
0x180009973  mov     [rsp+48h+var_28], esi
0x180009977  xor     r9d, r9d
0x18000997a  mov     rcx, [rcx+10h]
0x18000997e  call    WPP_SF_qd
0x180009983  jmp     loc_180009C23
0x180009988  test    rbx, rbx
0x18000998b  jnz     short loc_180009999
0x18000998d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180009992  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009999  lea     rsi, aCtranscodeconf_5; "CTranscodeConfig::QueryInterface"
0x1800099a0  cmp     [rbx+8], r15b
0x1800099a4  jz      short loc_1800099D8
0x1800099a6  mov     rcx, rbx; this
0x1800099a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800099ae  mov     ecx, [rax+7C4h]
0x1800099b4  cmp     ecx, [rax+7C8h]
0x1800099ba  jnb     short loc_1800099CB
0x1800099bc  add     rcx, rcx
0x1800099bf  mov     [rax+rcx*8], rsi
0x1800099c3  mov     dword ptr [rax+rcx*8+8], 14Ah
0x1800099cb  inc     dword ptr [rax+7C4h]
0x1800099d1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800099d8  test    r14, r14
0x1800099db  jnz     loc_180009A8F
0x1800099e1  mov     esi, 80004003h
0x1800099e6  test    rbx, rbx
0x1800099e9  jnz     short loc_180009A2C
0x1800099eb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800099f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800099f8  mov     rcx, rax
0x1800099fb  test    rax, rax
0x1800099fe  jz      short loc_180009A1E
0x180009a00  mov     rax, [rax]
0x180009a03  mov     edx, 7F0h
0x180009a08  mov     rax, [rax+8]
0x180009a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a11  test    eax, eax
0x180009a13  jz      short loc_180009A1E
0x180009a15  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009a1c  jmp     short loc_180009A2C
0x180009a1e  lea     rbx, qword_180069A90
0x180009a25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009a2c  cmp     [rbx+8], r15b
0x180009a30  jz      short loc_180009A5A
0x180009a32  mov     rcx, rbx; this
0x180009a35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009a3a  cmp     [rax+7CCh], esi
0x180009a40  jz      short loc_180009A5A
0x180009a42  mov     r9d, esi; int
0x180009a45  lea     rdx, aCtranscodeconf_5; "CTranscodeConfig::QueryInterface"
0x180009a4c  mov     r8d, 14Ah; int
0x180009a52  mov     rcx, rax; this
0x180009a55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009a5a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009a5f  cmp     al, 1
0x180009a61  jb      loc_180009B65
0x180009a67  mov     edx, 33h ; '3'
0x180009a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a73  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180009a7a  mov     r9, rdi
0x180009a7d  mov     [rsp+48h+var_28], esi
0x180009a81  mov     rcx, [rcx+10h]
0x180009a85  call    WPP_SF_qd
0x180009a8a  jmp     loc_180009B65
0x180009a8f  lea     rsi, IID_IMFTranscodeConfigPriv
0x180009a96  mov     [r14], r15
0x180009a99  mov     rdx, rsi; Buf2
0x180009a9c  mov     rcx, rsi; Buf1
0x180009a9f  mov     r8d, 10h; Size
0x180009aa5  call    memcmp_0
0x180009aaa  test    eax, eax
0x180009aac  jz      loc_180009B5B
0x180009ab2  mov     r8d, 10h; Size
0x180009ab8  lea     rdx, IID_IUnknown; Buf2
0x180009abf  mov     rcx, rsi; Buf1
0x180009ac2  call    memcmp_0
0x180009ac7  test    eax, eax
0x180009ac9  jz      loc_180009B5B
0x180009acf  mov     esi, 80004002h
0x180009ad4  test    rbx, rbx
0x180009ad7  jnz     short loc_180009B1A
0x180009ad9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009adf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009ae6  mov     rcx, rax
0x180009ae9  test    rax, rax
0x180009aec  jz      short loc_180009B0C
0x180009aee  mov     rax, [rax]
0x180009af1  mov     edx, 7F0h
0x180009af6  mov     rax, [rax+8]
0x180009afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aff  test    eax, eax
0x180009b01  jz      short loc_180009B0C
0x180009b03  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009b0a  jmp     short loc_180009B1A
0x180009b0c  lea     rbx, qword_180069A90
0x180009b13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009b1a  cmp     [rbx+8], r15b
0x180009b1e  jz      short loc_180009B48
0x180009b20  mov     rcx, rbx; this
0x180009b23  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009b28  cmp     [rax+7CCh], esi
0x180009b2e  jz      short loc_180009B48
0x180009b30  mov     r9d, esi; int
0x180009b33  lea     rdx, aCtranscodeconf_5; "CTranscodeConfig::QueryInterface"
0x180009b3a  mov     r8d, 157h; int
0x180009b40  mov     rcx, rax; this
0x180009b43  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009b48  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009b4d  cmp     al, 1
0x180009b4f  jb      short loc_180009B65
0x180009b51  mov     edx, 34h ; '4'
0x180009b56  jmp     loc_180009A6C
0x180009b5b  mov     esi, r15d
0x180009b5e  mov     [r14], rdi
0x180009b61  lock inc dword ptr [rdi+8]
0x180009b65  lea     rcx, [rsp+48h+arg_8]; this
0x180009b6a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180009b6f  test    esi, esi
0x180009b71  jns     loc_180009C23
0x180009b77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009b7e  test    rcx, rcx
0x180009b81  jnz     short loc_180009BC4
0x180009b83  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009b89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009b90  mov     rcx, rax
0x180009b93  test    rax, rax
0x180009b96  jz      short loc_180009BB6
0x180009b98  mov     rax, [rax]
0x180009b9b  mov     edx, 7F0h
0x180009ba0  mov     rax, [rax+8]
0x180009ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba9  test    eax, eax
0x180009bab  jz      short loc_180009BB6
0x180009bad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009bb4  jmp     short loc_180009BC4
0x180009bb6  lea     rcx, qword_180069A90; this
0x180009bbd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009bc4  cmp     [rcx+8], r15b
0x180009bc8  jz      short loc_180009BEF
0x180009bca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009bcf  cmp     [rax+7CCh], esi
0x180009bd5  jz      short loc_180009BEF
0x180009bd7  mov     r9d, esi; int
0x180009bda  lea     rdx, aCtranscodeconf_8; "CTranscodeConfig::CreateInstance"
0x180009be1  mov     r8d, 12Ch; int
0x180009be7  mov     rcx, rax; this
0x180009bea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009bef  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009bf4  cmp     al, 1
0x180009bf6  jb      short loc_180009C1B
0x180009bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bff  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180009c06  mov     edx, 32h ; '2'
0x180009c0b  mov     [rsp+48h+var_28], esi
0x180009c0f  xor     r9d, r9d
0x180009c12  mov     rcx, [rcx+10h]
0x180009c16  call    WPP_SF_qd
0x180009c1b  mov     rcx, rdi; this
0x180009c1e  call    ??_GCTranscodeConfig@@QEAAPEAXI@Z; CTranscodeConfig::`scalar deleting destructor'(uint)
0x180009c23  lea     rcx, [rsp+48h+arg_8]; this
0x180009c28  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180009c2d  mov     rbx, [rsp+48h+arg_0]
0x180009c32  mov     eax, esi
0x180009c34  mov     rsi, [rsp+48h+arg_10]
0x180009c39  add     rsp, 30h
0x180009c3d  pop     r15
0x180009c3f  pop     r14
0x180009c41  pop     rdi
0x180009c42  retn
```
