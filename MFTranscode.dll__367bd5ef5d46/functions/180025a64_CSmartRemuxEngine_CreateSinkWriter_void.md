# CSmartRemuxEngine::_CreateSinkWriter(void)

- ea: `0x180025a64`
- end: `0x180025e69`
- name: `?_CreateSinkWriter@CSmartRemuxEngine@@IEAAJXZ`
- size: `1029`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001eed8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x180025a64`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025abf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025b76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025c2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025ce2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025daf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025abf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025b76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025c2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025ce2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025daf`
- `MFPlat!MFCreateAttributes` at `0x180025aa3`
- `MFPlat!MFCreateAttributes` at `0x180025aa3`

## string_xrefs

- `0x180025a76`: `CSmartRemuxEngine::_CreateSinkWriter`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_CreateSinkWriter(CSmartRemuxEngine *this)
{
  __int64 v2; // rdx
  HRESULT v3; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v25; // [rsp+50h] [rbp+8h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+58h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v25, "CSmartRemuxEngine::_CreateSinkWriter", 852);
  ppMFAttributes = 0;
  v3 = MFCreateAttributes(&ppMFAttributes, 3u);
  if ( v3 >= 0 )
  {
    v3 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const IID *))ppMFAttributes->lpVtbl->SetGUID)(
           ppMFAttributes,
           &MF_TRANSCODE_CONTAINERTYPE,
           &MFTranscodeContainerType_MPEG4);
    if ( v3 >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
             ppMFAttributes,
             &MF_READWRITE_DISABLE_CONVERTERS,
             1);
      if ( v3 >= 0 )
      {
        v3 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               &MF_SINK_WRITER_DISABLE_THROTTLING,
               1);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD, IMFAttributes *, GUID *, char *))(**((_QWORD **)this + 3)
                                                                                                  + 32LL))(
                 *((_QWORD *)this + 3),
                 &CLSID_MFSinkWriter,
                 *((_QWORD *)this + 40),
                 ppMFAttributes,
                 &GUID_3137f1cd_fe5e_4805_a5d8_fb477448cb3d,
                 (char *)this + 40);
          if ( v3 < 0 )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
              CallStackTracing::s_wpInstance = v22;
              if ( v22
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
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
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_CreateSinkWriter", 865, v3);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v7 = 78;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v17 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)v19 + 499) != v3 )
              CallStackContext::TraceFailure(v19, "CSmartRemuxEngine::_CreateSinkWriter", 863, v3);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v7 = 77;
            goto LABEL_56;
          }
        }
      }
      else
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
          v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)v15 + 499) != v3 )
            CallStackContext::TraceFailure(v15, "CSmartRemuxEngine::_CreateSinkWriter", 860, v3);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v7 = 76;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != v3 )
          CallStackContext::TraceFailure(v11, "CSmartRemuxEngine::_CreateSinkWriter", 857, v3);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 75;
        goto LABEL_56;
      }
    }
  }
  else
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v6 + 499) != v3 )
        CallStackContext::TraceFailure(v6, "CSmartRemuxEngine::_CreateSinkWriter", 855, v3);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 74;
LABEL_56:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v3);
    }
  }
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180025a64  mov     [rsp+arg_10], rbx
0x180025a69  mov     [rsp+arg_18], rbp
0x180025a6e  push    rdi
0x180025a6f  sub     rsp, 40h
0x180025a73  mov     rdi, rcx
0x180025a76  lea     rbp, aCsmartremuxeng; "CSmartRemuxEngine::_CreateSinkWriter"
0x180025a7d  mov     rdx, rbp; char *
0x180025a80  lea     rcx, [rsp+48h+arg_0]; this
0x180025a85  mov     r8d, 354h; int
0x180025a8b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180025a90  mov     edx, 3; cInitialSize
0x180025a95  mov     [rsp+48h+ppMFAttributes], 0
0x180025a9e  lea     rcx, [rsp+48h+ppMFAttributes]; ppMFAttributes
0x180025aa3  call    cs:__imp_MFCreateAttributes
0x180025aa9  mov     ebx, eax
0x180025aab  test    eax, eax
0x180025aad  jns     loc_180025B3E
0x180025ab3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025aba  test    rcx, rcx
0x180025abd  jnz     short loc_180025B00
0x180025abf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025ac5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025acc  mov     rcx, rax
0x180025acf  test    rax, rax
0x180025ad2  jz      short loc_180025AF2
0x180025ad4  mov     rax, [rax]
0x180025ad7  mov     edx, 7F0h
0x180025adc  mov     rax, [rax+8]
0x180025ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ae5  test    eax, eax
0x180025ae7  jz      short loc_180025AF2
0x180025ae9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025af0  jmp     short loc_180025B00
0x180025af2  lea     rcx, qword_180069A90; this
0x180025af9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025b00  cmp     byte ptr [rcx+8], 0
0x180025b04  jz      short loc_180025B27
0x180025b06  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025b0b  cmp     [rax+7CCh], ebx
0x180025b11  jz      short loc_180025B27
0x180025b13  mov     r9d, ebx; int
0x180025b16  mov     r8d, 357h; int
0x180025b1c  mov     rdx, rbp; char *
0x180025b1f  mov     rcx, rax; this
0x180025b22  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025b27  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180025b2c  cmp     al, 1
0x180025b2e  jb      loc_180025E43
0x180025b34  mov     edx, 4Ah ; 'J'
0x180025b39  jmp     loc_180025E25
0x180025b3e  mov     rcx, [rsp+48h+ppMFAttributes]
0x180025b43  lea     r8, MFTranscodeContainerType_MPEG4
0x180025b4a  lea     rdx, MF_TRANSCODE_CONTAINERTYPE
0x180025b51  mov     rax, [rcx]
0x180025b54  mov     rax, [rax+0C0h]
0x180025b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b60  mov     ebx, eax
0x180025b62  test    eax, eax
0x180025b64  jns     loc_180025BF5
0x180025b6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025b71  test    rcx, rcx
0x180025b74  jnz     short loc_180025BB7
0x180025b76  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025b7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025b83  mov     rcx, rax
0x180025b86  test    rax, rax
0x180025b89  jz      short loc_180025BA9
0x180025b8b  mov     rax, [rax]
0x180025b8e  mov     edx, 7F0h
0x180025b93  mov     rax, [rax+8]
0x180025b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b9c  test    eax, eax
0x180025b9e  jz      short loc_180025BA9
0x180025ba0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025ba7  jmp     short loc_180025BB7
0x180025ba9  lea     rcx, qword_180069A90; this
0x180025bb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025bb7  cmp     byte ptr [rcx+8], 0
0x180025bbb  jz      short loc_180025BDE
0x180025bbd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025bc2  cmp     [rax+7CCh], ebx
0x180025bc8  jz      short loc_180025BDE
0x180025bca  mov     r9d, ebx; int
0x180025bcd  mov     r8d, 359h; int
0x180025bd3  mov     rdx, rbp; char *
0x180025bd6  mov     rcx, rax; this
0x180025bd9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025bde  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180025be3  cmp     al, 1
0x180025be5  jb      loc_180025E43
0x180025beb  mov     edx, 4Bh ; 'K'
0x180025bf0  jmp     loc_180025E25
0x180025bf5  mov     rcx, [rsp+48h+ppMFAttributes]
0x180025bfa  lea     rdx, MF_READWRITE_DISABLE_CONVERTERS
0x180025c01  mov     r8d, 1
0x180025c07  mov     rax, [rcx]
0x180025c0a  mov     rax, [rax+0A8h]
0x180025c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c16  mov     ebx, eax
0x180025c18  test    eax, eax
0x180025c1a  jns     loc_180025CAB
0x180025c20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025c27  test    rcx, rcx
0x180025c2a  jnz     short loc_180025C6D
0x180025c2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025c32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025c39  mov     rcx, rax
0x180025c3c  test    rax, rax
0x180025c3f  jz      short loc_180025C5F
0x180025c41  mov     rax, [rax]
0x180025c44  mov     edx, 7F0h
0x180025c49  mov     rax, [rax+8]
0x180025c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c52  test    eax, eax
0x180025c54  jz      short loc_180025C5F
0x180025c56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025c5d  jmp     short loc_180025C6D
0x180025c5f  lea     rcx, qword_180069A90; this
0x180025c66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025c6d  cmp     byte ptr [rcx+8], 0
0x180025c71  jz      short loc_180025C94
0x180025c73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025c78  cmp     [rax+7CCh], ebx
0x180025c7e  jz      short loc_180025C94
0x180025c80  mov     r9d, ebx; int
0x180025c83  mov     r8d, 35Ch; int
0x180025c89  mov     rdx, rbp; char *
0x180025c8c  mov     rcx, rax; this
0x180025c8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025c94  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180025c99  cmp     al, 1
0x180025c9b  jb      loc_180025E43
0x180025ca1  mov     edx, 4Ch ; 'L'
0x180025ca6  jmp     loc_180025E25
0x180025cab  mov     rcx, [rsp+48h+ppMFAttributes]
0x180025cb0  lea     rdx, MF_SINK_WRITER_DISABLE_THROTTLING
0x180025cb7  mov     r8d, 1
0x180025cbd  mov     rax, [rcx]
0x180025cc0  mov     rax, [rax+0A8h]
0x180025cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ccc  mov     ebx, eax
0x180025cce  test    eax, eax
0x180025cd0  jns     loc_180025D61
0x180025cd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025cdd  test    rcx, rcx
0x180025ce0  jnz     short loc_180025D23
0x180025ce2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025ce8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025cef  mov     rcx, rax
0x180025cf2  test    rax, rax
0x180025cf5  jz      short loc_180025D15
0x180025cf7  mov     rax, [rax]
0x180025cfa  mov     edx, 7F0h
0x180025cff  mov     rax, [rax+8]
0x180025d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d08  test    eax, eax
0x180025d0a  jz      short loc_180025D15
0x180025d0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025d13  jmp     short loc_180025D23
0x180025d15  lea     rcx, qword_180069A90; this
0x180025d1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025d23  cmp     byte ptr [rcx+8], 0
0x180025d27  jz      short loc_180025D4A
0x180025d29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025d2e  cmp     [rax+7CCh], ebx
0x180025d34  jz      short loc_180025D4A
0x180025d36  mov     r9d, ebx; int
0x180025d39  mov     r8d, 35Fh; int
0x180025d3f  mov     rdx, rbp; char *
0x180025d42  mov     rcx, rax; this
0x180025d45  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025d4a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180025d4f  cmp     al, 1
0x180025d51  jb      loc_180025E43
0x180025d57  mov     edx, 4Dh ; 'M'
0x180025d5c  jmp     loc_180025E25
0x180025d61  mov     rcx, [rdi+18h]
0x180025d65  lea     rdx, [rdi+28h]
0x180025d69  mov     r9, [rsp+48h+ppMFAttributes]
0x180025d6e  mov     r8, [rdi+140h]
0x180025d75  mov     [rsp+48h+var_20], rdx
0x180025d7a  lea     rdx, _GUID_3137f1cd_fe5e_4805_a5d8_fb477448cb3d
0x180025d81  mov     rax, [rcx]
0x180025d84  mov     [rsp+48h+var_28], rdx
0x180025d89  lea     rdx, CLSID_MFSinkWriter
0x180025d90  mov     rax, [rax+20h]
0x180025d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d99  mov     ebx, eax
0x180025d9b  test    eax, eax
0x180025d9d  jns     loc_180025E43
0x180025da3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025daa  test    rcx, rcx
0x180025dad  jnz     short loc_180025DF0
0x180025daf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025db5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025dbc  mov     rcx, rax
0x180025dbf  test    rax, rax
0x180025dc2  jz      short loc_180025DE2
0x180025dc4  mov     rax, [rax]
0x180025dc7  mov     edx, 7F0h
0x180025dcc  mov     rax, [rax+8]
0x180025dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dd5  test    eax, eax
0x180025dd7  jz      short loc_180025DE2
0x180025dd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025de0  jmp     short loc_180025DF0
0x180025de2  lea     rcx, qword_180069A90; this
0x180025de9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025df0  cmp     byte ptr [rcx+8], 0
0x180025df4  jz      short loc_180025E17
0x180025df6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025dfb  cmp     [rax+7CCh], ebx
0x180025e01  jz      short loc_180025E17
0x180025e03  mov     r9d, ebx; int
0x180025e06  mov     r8d, 361h; int
0x180025e0c  mov     rdx, rbp; char *
0x180025e0f  mov     rcx, rax; this
0x180025e12  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025e17  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180025e1c  cmp     al, 1
0x180025e1e  jb      short loc_180025E43
0x180025e20  mov     edx, 4Eh ; 'N'
0x180025e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e2c  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x180025e33  mov     r9, rdi
0x180025e36  mov     dword ptr [rsp+48h+var_28], ebx
0x180025e3a  mov     rcx, [rcx+10h]
0x180025e3e  call    WPP_SF_qd
0x180025e43  lea     rcx, [rsp+48h+ppMFAttributes]
0x180025e48  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180025e4d  lea     rcx, [rsp+48h+arg_0]; this
0x180025e52  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180025e57  mov     rbp, [rsp+48h+arg_18]
0x180025e5c  mov     eax, ebx
0x180025e5e  mov     rbx, [rsp+48h+arg_10]
0x180025e63  add     rsp, 40h
0x180025e67  pop     rdi
0x180025e68  retn
```
