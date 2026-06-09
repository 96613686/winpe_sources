# CMFASFRecordingTimeProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x18004dba0`
- end: `0x18004dea6`
- name: `?SetNativeValue@CMFASFRecordingTimeProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `774`
- prototype: `int(CMFASFRecordingTimeProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004dba0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004dbd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004dc6f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004dbd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004dc6f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004dd11`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004dd11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dbef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dc8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dd2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ddf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dbef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dc8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dd2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ddf4`

## pseudocode

```c
__int64 __fastcall CMFASFRecordingTimeProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned __int64 QuadPart; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v23; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v23,
    "CMFASFRecordingTimeProperty::SetNativeValue",
    42);
  v5 = PropVariantClear(this + 4);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        QuadPart = this[5].uhVal.QuadPart;
        if ( QuadPart < 0x701CE1722770000LL )
        {
          this[4].hVal.QuadPart = -1;
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
          v5 = -2147024362;
          if ( *((_BYTE *)v19 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CMFASFRecordingTimeProperty::SetNativeValue",
                50,
                -2147024362);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 17;
            goto LABEL_46;
          }
        }
        else
        {
          this[4].hVal.QuadPart = QuadPart - 504911232000000000LL;
          v5 = 0;
          this[4].vt = 64;
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CMFASFRecordingTimeProperty::SetNativeValue", 45, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 16;
          goto LABEL_46;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v5 )
          CallStackContext::TraceFailure(v13, "CMFASFRecordingTimeProperty::SetNativeValue", 43, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 15;
        goto LABEL_46;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CMFASFRecordingTimeProperty::SetNativeValue", 42, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 14;
LABEL_46:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_75ae04f3d2903ae563d10f4836b7a273_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v23);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004dba0  push    rbx
0x18004dba2  push    rbp
0x18004dba3  push    rsi
0x18004dba4  push    rdi
0x18004dba5  push    r12
0x18004dba7  push    r14
0x18004dba9  sub     rsp, 38h
0x18004dbad  mov     r14, rdx
0x18004dbb0  lea     r12, aCmfasfrecordin_0; "CMFASFRecordingTimeProperty::SetNativeV"...
0x18004dbb7  mov     rdi, rcx
0x18004dbba  mov     ebp, 2Ah ; '*'
0x18004dbbf  mov     r8d, ebp; int
0x18004dbc2  lea     rcx, [rsp+68h+arg_0]; this
0x18004dbc7  mov     rdx, r12; char *
0x18004dbca  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004dbcf  lea     rcx, [rdi+60h]; pvar
0x18004dbd3  call    cs:__imp_PropVariantClear
0x18004dbd9  mov     ebx, eax
0x18004dbdb  test    eax, eax
0x18004dbdd  jns     loc_18004DC6B
0x18004dbe3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dbea  test    rcx, rcx
0x18004dbed  jnz     short loc_18004DC30
0x18004dbef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004dbf5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dbfc  mov     rcx, rax
0x18004dbff  test    rax, rax
0x18004dc02  jz      short loc_18004DC22
0x18004dc04  mov     rax, [rax]
0x18004dc07  mov     edx, 7F0h
0x18004dc0c  mov     rax, [rax+8]
0x18004dc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc15  test    eax, eax
0x18004dc17  jz      short loc_18004DC22
0x18004dc19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dc20  jmp     short loc_18004DC30
0x18004dc22  lea     rcx, qword_180069A90; this
0x18004dc29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dc30  cmp     byte ptr [rcx+8], 0
0x18004dc34  jz      short loc_18004DC54
0x18004dc36  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004dc3b  cmp     [rax+7CCh], ebx
0x18004dc41  jz      short loc_18004DC54
0x18004dc43  mov     r9d, ebx; int
0x18004dc46  mov     r8d, ebp; int
0x18004dc49  mov     rdx, r12; char *
0x18004dc4c  mov     rcx, rax; this
0x18004dc4f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004dc54  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004dc59  cmp     al, 1
0x18004dc5b  jb      loc_18004DE8D
0x18004dc61  mov     edx, 0Eh
0x18004dc66  jmp     loc_18004DE6F
0x18004dc6b  lea     rcx, [rdi+78h]; pvar
0x18004dc6f  call    cs:__imp_PropVariantClear
0x18004dc75  mov     ebx, eax
0x18004dc77  test    eax, eax
0x18004dc79  jns     loc_18004DD0A
0x18004dc7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dc86  test    rcx, rcx
0x18004dc89  jnz     short loc_18004DCCC
0x18004dc8b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004dc91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dc98  mov     rcx, rax
0x18004dc9b  test    rax, rax
0x18004dc9e  jz      short loc_18004DCBE
0x18004dca0  mov     rax, [rax]
0x18004dca3  mov     edx, 7F0h
0x18004dca8  mov     rax, [rax+8]
0x18004dcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dcb1  test    eax, eax
0x18004dcb3  jz      short loc_18004DCBE
0x18004dcb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dcbc  jmp     short loc_18004DCCC
0x18004dcbe  lea     rcx, qword_180069A90; this
0x18004dcc5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dccc  cmp     byte ptr [rcx+8], 0
0x18004dcd0  jz      short loc_18004DCF3
0x18004dcd2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004dcd7  cmp     [rax+7CCh], ebx
0x18004dcdd  jz      short loc_18004DCF3
0x18004dcdf  mov     r9d, ebx; int
0x18004dce2  mov     r8d, 2Bh ; '+'; int
0x18004dce8  mov     rdx, r12; char *
0x18004dceb  mov     rcx, rax; this
0x18004dcee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004dcf3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004dcf8  cmp     al, 1
0x18004dcfa  jb      loc_18004DE8D
0x18004dd00  mov     edx, 0Fh
0x18004dd05  jmp     loc_18004DE6F
0x18004dd0a  mov     rdx, r14; pvarSrc
0x18004dd0d  lea     rcx, [rdi+78h]; pvarDest
0x18004dd11  call    cs:__imp_PropVariantCopy
0x18004dd17  mov     ebx, eax
0x18004dd19  test    eax, eax
0x18004dd1b  jns     loc_18004DDAC
0x18004dd21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dd28  test    rcx, rcx
0x18004dd2b  jnz     short loc_18004DD6E
0x18004dd2d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004dd33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dd3a  mov     rcx, rax
0x18004dd3d  test    rax, rax
0x18004dd40  jz      short loc_18004DD60
0x18004dd42  mov     rax, [rax]
0x18004dd45  mov     edx, 7F0h
0x18004dd4a  mov     rax, [rax+8]
0x18004dd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd53  test    eax, eax
0x18004dd55  jz      short loc_18004DD60
0x18004dd57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dd5e  jmp     short loc_18004DD6E
0x18004dd60  lea     rcx, qword_180069A90; this
0x18004dd67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dd6e  cmp     byte ptr [rcx+8], 0
0x18004dd72  jz      short loc_18004DD95
0x18004dd74  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004dd79  cmp     [rax+7CCh], ebx
0x18004dd7f  jz      short loc_18004DD95
0x18004dd81  mov     r9d, ebx; int
0x18004dd84  mov     r8d, 2Dh ; '-'; int
0x18004dd8a  mov     rdx, r12; char *
0x18004dd8d  mov     rcx, rax; this
0x18004dd90  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004dd95  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004dd9a  cmp     al, 1
0x18004dd9c  jb      loc_18004DE8D
0x18004dda2  mov     edx, 10h
0x18004dda7  jmp     loc_18004DE6F
0x18004ddac  mov     rax, [rdi+80h]
0x18004ddb3  mov     rcx, 701CE1722770000h
0x18004ddbd  cmp     rax, rcx
0x18004ddc0  jb      short loc_18004DDE0
0x18004ddc2  mov     rcx, 0F8FE31E8DD890000h
0x18004ddcc  add     rax, rcx
0x18004ddcf  mov     [rdi+68h], rax
0x18004ddd3  xor     ebx, ebx
0x18004ddd5  mov     word ptr [rdi+60h], 40h ; '@'
0x18004dddb  jmp     loc_18004DE8D
0x18004dde0  mov     qword ptr [rdi+68h], 0FFFFFFFFFFFFFFFFh
0x18004dde8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ddef  test    rcx, rcx
0x18004ddf2  jnz     short loc_18004DE35
0x18004ddf4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ddfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de01  mov     rcx, rax
0x18004de04  test    rax, rax
0x18004de07  jz      short loc_18004DE27
0x18004de09  mov     rax, [rax]
0x18004de0c  mov     edx, 7F0h
0x18004de11  mov     rax, [rax+8]
0x18004de15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de1a  test    eax, eax
0x18004de1c  jz      short loc_18004DE27
0x18004de1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de25  jmp     short loc_18004DE35
0x18004de27  lea     rcx, qword_180069A90; this
0x18004de2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de35  cmp     byte ptr [rcx+8], 0
0x18004de39  mov     ebx, 80070216h
0x18004de3e  jz      short loc_18004DE61
0x18004de40  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004de45  cmp     [rax+7CCh], ebx
0x18004de4b  jz      short loc_18004DE61
0x18004de4d  mov     r9d, ebx; int
0x18004de50  mov     r8d, 32h ; '2'; int
0x18004de56  mov     rdx, r12; char *
0x18004de59  mov     rcx, rax; this
0x18004de5c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004de61  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004de66  cmp     al, 1
0x18004de68  jb      short loc_18004DE8D
0x18004de6a  mov     edx, 11h
0x18004de6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004de76  lea     r8, WPP_75ae04f3d2903ae563d10f4836b7a273_Traceguids
0x18004de7d  mov     r9, rdi
0x18004de80  mov     [rsp+68h+var_48], ebx
0x18004de84  mov     rcx, [rcx+10h]
0x18004de88  call    WPP_SF_qd
0x18004de8d  lea     rcx, [rsp+68h+arg_0]; this
0x18004de92  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004de97  mov     eax, ebx
0x18004de99  add     rsp, 38h
0x18004de9d  pop     r14
0x18004de9f  pop     r12
0x18004dea1  pop     rdi
0x18004dea2  pop     rsi
0x18004dea3  pop     rbp
0x18004dea4  pop     rbx
0x18004dea5  retn
```
