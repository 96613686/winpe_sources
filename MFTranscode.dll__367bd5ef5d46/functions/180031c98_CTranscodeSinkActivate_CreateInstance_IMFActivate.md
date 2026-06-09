# CTranscodeSinkActivate::CreateInstance(IMFActivate * *)

- ea: `0x180031c98`
- end: `0x180031f14`
- name: `?CreateInstance@CTranscodeSinkActivate@@SAJPEAPEAUIMFActivate@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(struct IMFActivate **)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x180012420`
- `0x180035350`
- `0x180040130`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180013280`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x180031320`
- `0x180031c98`
- `0x180033d90`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031cd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031daf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031cd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031daf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031e65`

## string_xrefs

- `0x180031ca5`: `CTranscodeSinkActivate::CreateInstance`
- `0x180031d2d`: `CTranscodeSinkActivate::CreateInstance`
- `0x180031e06`: `CTranscodeSinkActivate::CreateInstance`
- `0x180031ebc`: `CTranscodeSinkActivate::CreateInstance`

## pseudocode

```c
__int64 __fastcall CTranscodeSinkActivate::CreateInstance(struct IMFActivate **a1)
{
  __int64 v2; // rdx
  __int64 *v3; // rcx
  int Interface; // ebx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  CTranscodeSinkActivate *v8; // rax
  __int64 v9; // rdx
  CTranscodeSinkActivate *v10; // rax
  CTranscodeSinkActivate *v11; // rdi
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  char v20; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v20, "CTranscodeSinkActivate::CreateInstance", 33);
  if ( a1 )
  {
    *a1 = 0;
    v8 = (CTranscodeSinkActivate *)operator new(0xA0u);
    if ( v8 && (v10 = CTranscodeSinkActivate::CTranscodeSinkActivate(v8), (v11 = v10) != 0) )
    {
      Interface = CTranscodeSinkActivate::QueryInterface(v10, &IID_IMFActivate, (void **)a1);
      if ( Interface < 0 )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != Interface )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CTranscodeSinkActivate::CreateInstance",
              45,
              Interface);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids,
            0,
            Interface);
        CTranscodeSinkActivate::Release(v11);
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      Interface = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v18, "CTranscodeSinkActivate::CreateInstance", 43, -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 12;
        goto LABEL_36;
      }
    }
  }
  else
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    Interface = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v3 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)v6 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v6, "CTranscodeSinkActivate::CreateInstance", 38, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 11;
LABEL_36:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids, 0, Interface);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180031c98  mov     [rsp+arg_8], rbx
0x180031c9d  push    rdi
0x180031c9e  sub     rsp, 30h
0x180031ca2  mov     rbx, rcx
0x180031ca5  lea     rdx, aCtranscodesink_10; "CTranscodeSinkActivate::CreateInstance"
0x180031cac  lea     rcx, [rsp+38h+arg_0]; this
0x180031cb1  mov     r8d, 21h ; '!'; int
0x180031cb7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180031cbc  test    rbx, rbx
0x180031cbf  jnz     loc_180031D59
0x180031cc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031ccc  mov     ebx, 80004003h
0x180031cd1  test    rcx, rcx
0x180031cd4  jnz     short loc_180031D17
0x180031cd6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031cdc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031ce3  mov     rcx, rax
0x180031ce6  test    rax, rax
0x180031ce9  jz      short loc_180031D09
0x180031ceb  mov     rax, [rax]
0x180031cee  mov     edx, 7F0h
0x180031cf3  mov     rax, [rax+8]
0x180031cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031cfc  test    eax, eax
0x180031cfe  jz      short loc_180031D09
0x180031d00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031d07  jmp     short loc_180031D17
0x180031d09  lea     rcx, qword_180069A90; this
0x180031d10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031d17  cmp     byte ptr [rcx+8], 0
0x180031d1b  jz      short loc_180031D42
0x180031d1d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031d22  cmp     [rax+7CCh], ebx
0x180031d28  jz      short loc_180031D42
0x180031d2a  mov     r9d, ebx; int
0x180031d2d  lea     rdx, aCtranscodesink_10; "CTranscodeSinkActivate::CreateInstance"
0x180031d34  mov     r8d, 26h ; '&'; int
0x180031d3a  mov     rcx, rax; this
0x180031d3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031d42  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180031d47  cmp     al, 1
0x180031d49  jb      loc_180031EFD
0x180031d4f  mov     edx, 0Bh
0x180031d54  jmp     loc_180031EDF
0x180031d59  mov     ecx, 0A0h; Size
0x180031d5e  mov     qword ptr [rbx], 0
0x180031d65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031d6a  test    rax, rax
0x180031d6d  jz      loc_180031E54
0x180031d73  mov     rcx, rax; this
0x180031d76  call    ??0CTranscodeSinkActivate@@IEAA@XZ; CTranscodeSinkActivate::CTranscodeSinkActivate(void)
0x180031d7b  mov     rdi, rax
0x180031d7e  test    rax, rax
0x180031d81  jz      loc_180031E54
0x180031d87  mov     r8, rbx; void **
0x180031d8a  lea     rdx, IID_IMFActivate; struct _GUID *
0x180031d91  mov     rcx, rax; this
0x180031d94  call    ?QueryInterface@CTranscodeSinkActivate@@UEAAJAEBU_GUID@@PEAPEAX@Z; CTranscodeSinkActivate::QueryInterface(_GUID const &,void * *)
0x180031d99  mov     ebx, eax
0x180031d9b  test    eax, eax
0x180031d9d  jns     loc_180031EFD
0x180031da3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031daa  test    rcx, rcx
0x180031dad  jnz     short loc_180031DF0
0x180031daf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031db5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031dbc  mov     rcx, rax
0x180031dbf  test    rax, rax
0x180031dc2  jz      short loc_180031DE2
0x180031dc4  mov     rax, [rax]
0x180031dc7  mov     edx, 7F0h
0x180031dcc  mov     rax, [rax+8]
0x180031dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031dd5  test    eax, eax
0x180031dd7  jz      short loc_180031DE2
0x180031dd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031de0  jmp     short loc_180031DF0
0x180031de2  lea     rcx, qword_180069A90; this
0x180031de9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031df0  cmp     byte ptr [rcx+8], 0
0x180031df4  jz      short loc_180031E1B
0x180031df6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031dfb  cmp     [rax+7CCh], ebx
0x180031e01  jz      short loc_180031E1B
0x180031e03  mov     r9d, ebx; int
0x180031e06  lea     rdx, aCtranscodesink_10; "CTranscodeSinkActivate::CreateInstance"
0x180031e0d  mov     r8d, 2Dh ; '-'; int
0x180031e13  mov     rcx, rax; this
0x180031e16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031e1b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180031e20  cmp     al, 1
0x180031e22  jb      short loc_180031E47
0x180031e24  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e2b  lea     r8, WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids
0x180031e32  mov     edx, 0Dh
0x180031e37  mov     [rsp+38h+var_18], ebx
0x180031e3b  xor     r9d, r9d
0x180031e3e  mov     rcx, [rcx+10h]
0x180031e42  call    WPP_SF_qd
0x180031e47  mov     rcx, rdi; this
0x180031e4a  call    ?Release@CTranscodeSinkActivate@@UEAAKXZ; CTranscodeSinkActivate::Release(void)
0x180031e4f  jmp     loc_180031EFD
0x180031e54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031e5b  mov     ebx, 8007000Eh
0x180031e60  test    rcx, rcx
0x180031e63  jnz     short loc_180031EA6
0x180031e65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031e6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031e72  mov     rcx, rax
0x180031e75  test    rax, rax
0x180031e78  jz      short loc_180031E98
0x180031e7a  mov     rax, [rax]
0x180031e7d  mov     edx, 7F0h
0x180031e82  mov     rax, [rax+8]
0x180031e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e8b  test    eax, eax
0x180031e8d  jz      short loc_180031E98
0x180031e8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031e96  jmp     short loc_180031EA6
0x180031e98  lea     rcx, qword_180069A90; this
0x180031e9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031ea6  cmp     byte ptr [rcx+8], 0
0x180031eaa  jz      short loc_180031ED1
0x180031eac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031eb1  cmp     [rax+7CCh], ebx
0x180031eb7  jz      short loc_180031ED1
0x180031eb9  mov     r9d, ebx; int
0x180031ebc  lea     rdx, aCtranscodesink_10; "CTranscodeSinkActivate::CreateInstance"
0x180031ec3  mov     r8d, 2Bh ; '+'; int
0x180031ec9  mov     rcx, rax; this
0x180031ecc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031ed1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180031ed6  cmp     al, 1
0x180031ed8  jb      short loc_180031EFD
0x180031eda  mov     edx, 0Ch
0x180031edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ee6  lea     r8, WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids
0x180031eed  xor     r9d, r9d
0x180031ef0  mov     [rsp+38h+var_18], ebx
0x180031ef4  mov     rcx, [rcx+10h]
0x180031ef8  call    WPP_SF_qd
0x180031efd  lea     rcx, [rsp+38h+arg_0]; this
0x180031f02  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180031f07  mov     eax, ebx
0x180031f09  mov     rbx, [rsp+38h+arg_8]
0x180031f0e  add     rsp, 30h
0x180031f12  pop     rdi
0x180031f13  retn
```
