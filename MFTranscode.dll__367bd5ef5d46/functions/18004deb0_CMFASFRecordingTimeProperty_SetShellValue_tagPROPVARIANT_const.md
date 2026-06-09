# CMFASFRecordingTimeProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x18004deb0`
- end: `0x18004e1c0`
- name: `?SetShellValue@CMFASFRecordingTimeProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `784`
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
- `0x18004deb0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004deed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004df89`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004deed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004df89`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004e02b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004e02b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004df09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dfa5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e047`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e104`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004df09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dfa5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e047`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e104`

## pseudocode

```c
__int64 __fastcall CMFASFRecordingTimeProperty::SetShellValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
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
  unsigned __int64 v18; // rcx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v23; // [rsp+60h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v23,
    "CMFASFRecordingTimeProperty::SetShellValue",
    21);
  v5 = PropVariantClear(this + 4);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 4, a2);
      if ( v5 >= 0 )
      {
        v18 = this[4].hVal.QuadPart + 504911232000000000LL;
        if ( v18 < this[4].hVal.QuadPart )
        {
          this[5].hVal.QuadPart = -1;
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
                "CMFASFRecordingTimeProperty::SetShellValue",
                29,
                -2147024362);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 13;
            goto LABEL_46;
          }
        }
        else
        {
          this[5].hVal.QuadPart = v18;
          v5 = 0;
          this[5].vt = 21;
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
            CallStackContext::TraceFailure(v17, "CMFASFRecordingTimeProperty::SetShellValue", 24, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 12;
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
          CallStackContext::TraceFailure(v13, "CMFASFRecordingTimeProperty::SetShellValue", 22, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 11;
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
        CallStackContext::TraceFailure(v8, "CMFASFRecordingTimeProperty::SetShellValue", 21, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 10;
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
0x18004deb0  mov     [rsp+arg_8], rbx
0x18004deb5  mov     [rsp+arg_10], rbp
0x18004deba  push    rsi
0x18004debb  push    rdi
0x18004debc  push    r12
0x18004debe  push    r13
0x18004dec0  push    r14
0x18004dec2  sub     rsp, 30h
0x18004dec6  mov     r14, rdx
0x18004dec9  lea     r12, aCmfasfrecordin; "CMFASFRecordingTimeProperty::SetShellVa"...
0x18004ded0  mov     rsi, rcx
0x18004ded3  mov     r13d, 15h
0x18004ded9  mov     r8d, r13d; int
0x18004dedc  lea     rcx, [rsp+58h+arg_0]; this
0x18004dee1  mov     rdx, r12; char *
0x18004dee4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004dee9  lea     rcx, [rsi+60h]; pvar
0x18004deed  call    cs:__imp_PropVariantClear
0x18004def3  mov     ebx, eax
0x18004def5  test    eax, eax
0x18004def7  jns     loc_18004DF85
0x18004defd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004df04  test    rcx, rcx
0x18004df07  jnz     short loc_18004DF4A
0x18004df09  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004df0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004df16  mov     rcx, rax
0x18004df19  test    rax, rax
0x18004df1c  jz      short loc_18004DF3C
0x18004df1e  mov     rax, [rax]
0x18004df21  mov     edx, 7F0h
0x18004df26  mov     rax, [rax+8]
0x18004df2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df2f  test    eax, eax
0x18004df31  jz      short loc_18004DF3C
0x18004df33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004df3a  jmp     short loc_18004DF4A
0x18004df3c  lea     rcx, qword_180069A90; this
0x18004df43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004df4a  cmp     byte ptr [rcx+8], 0
0x18004df4e  jz      short loc_18004DF6E
0x18004df50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004df55  cmp     [rax+7CCh], ebx
0x18004df5b  jz      short loc_18004DF6E
0x18004df5d  mov     r9d, ebx; int
0x18004df60  mov     r8d, r13d; int
0x18004df63  mov     rdx, r12; char *
0x18004df66  mov     rcx, rax; this
0x18004df69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004df6e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004df73  cmp     al, 1
0x18004df75  jb      loc_18004E19D
0x18004df7b  mov     edx, 0Ah
0x18004df80  jmp     loc_18004E17F
0x18004df85  lea     rcx, [rsi+78h]; pvar
0x18004df89  call    cs:__imp_PropVariantClear
0x18004df8f  mov     ebx, eax
0x18004df91  test    eax, eax
0x18004df93  jns     loc_18004E024
0x18004df99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dfa0  test    rcx, rcx
0x18004dfa3  jnz     short loc_18004DFE6
0x18004dfa5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004dfab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dfb2  mov     rcx, rax
0x18004dfb5  test    rax, rax
0x18004dfb8  jz      short loc_18004DFD8
0x18004dfba  mov     rax, [rax]
0x18004dfbd  mov     edx, 7F0h
0x18004dfc2  mov     rax, [rax+8]
0x18004dfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfcb  test    eax, eax
0x18004dfcd  jz      short loc_18004DFD8
0x18004dfcf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dfd6  jmp     short loc_18004DFE6
0x18004dfd8  lea     rcx, qword_180069A90; this
0x18004dfdf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dfe6  cmp     byte ptr [rcx+8], 0
0x18004dfea  jz      short loc_18004E00D
0x18004dfec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004dff1  cmp     [rax+7CCh], ebx
0x18004dff7  jz      short loc_18004E00D
0x18004dff9  mov     r9d, ebx; int
0x18004dffc  mov     r8d, 16h; int
0x18004e002  mov     rdx, r12; char *
0x18004e005  mov     rcx, rax; this
0x18004e008  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e00d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004e012  cmp     al, 1
0x18004e014  jb      loc_18004E19D
0x18004e01a  mov     edx, 0Bh
0x18004e01f  jmp     loc_18004E17F
0x18004e024  mov     rdx, r14; pvarSrc
0x18004e027  lea     rcx, [rsi+60h]; pvarDest
0x18004e02b  call    cs:__imp_PropVariantCopy
0x18004e031  mov     ebx, eax
0x18004e033  test    eax, eax
0x18004e035  jns     loc_18004E0C6
0x18004e03b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e042  test    rcx, rcx
0x18004e045  jnz     short loc_18004E088
0x18004e047  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e04d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e054  mov     rcx, rax
0x18004e057  test    rax, rax
0x18004e05a  jz      short loc_18004E07A
0x18004e05c  mov     rax, [rax]
0x18004e05f  mov     edx, 7F0h
0x18004e064  mov     rax, [rax+8]
0x18004e068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e06d  test    eax, eax
0x18004e06f  jz      short loc_18004E07A
0x18004e071  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e078  jmp     short loc_18004E088
0x18004e07a  lea     rcx, qword_180069A90; this
0x18004e081  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e088  cmp     byte ptr [rcx+8], 0
0x18004e08c  jz      short loc_18004E0AF
0x18004e08e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e093  cmp     [rax+7CCh], ebx
0x18004e099  jz      short loc_18004E0AF
0x18004e09b  mov     r9d, ebx; int
0x18004e09e  mov     r8d, 18h; int
0x18004e0a4  mov     rdx, r12; char *
0x18004e0a7  mov     rcx, rax; this
0x18004e0aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e0af  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004e0b4  cmp     al, 1
0x18004e0b6  jb      loc_18004E19D
0x18004e0bc  mov     edx, 0Ch
0x18004e0c1  jmp     loc_18004E17F
0x18004e0c6  mov     rcx, 701CE1722770000h
0x18004e0d0  add     rcx, [rsi+68h]
0x18004e0d4  cmp     rcx, [rsi+68h]
0x18004e0d8  jb      short loc_18004E0ED
0x18004e0da  mov     [rsi+80h], rcx
0x18004e0e1  xor     ebx, ebx
0x18004e0e3  mov     [rsi+78h], r13w
0x18004e0e8  jmp     loc_18004E19D
0x18004e0ed  mov     qword ptr [rsi+80h], 0FFFFFFFFFFFFFFFFh
0x18004e0f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e0ff  test    rcx, rcx
0x18004e102  jnz     short loc_18004E145
0x18004e104  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e10a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e111  mov     rcx, rax
0x18004e114  test    rax, rax
0x18004e117  jz      short loc_18004E137
0x18004e119  mov     rax, [rax]
0x18004e11c  mov     edx, 7F0h
0x18004e121  mov     rax, [rax+8]
0x18004e125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e12a  test    eax, eax
0x18004e12c  jz      short loc_18004E137
0x18004e12e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e135  jmp     short loc_18004E145
0x18004e137  lea     rcx, qword_180069A90; this
0x18004e13e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e145  cmp     byte ptr [rcx+8], 0
0x18004e149  mov     ebx, 80070216h
0x18004e14e  jz      short loc_18004E171
0x18004e150  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e155  cmp     [rax+7CCh], ebx
0x18004e15b  jz      short loc_18004E171
0x18004e15d  mov     r9d, ebx; int
0x18004e160  mov     r8d, 1Dh; int
0x18004e166  mov     rdx, r12; char *
0x18004e169  mov     rcx, rax; this
0x18004e16c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e171  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004e176  cmp     al, 1
0x18004e178  jb      short loc_18004E19D
0x18004e17a  mov     edx, 0Dh
0x18004e17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e186  lea     r8, WPP_75ae04f3d2903ae563d10f4836b7a273_Traceguids
0x18004e18d  mov     r9, rsi
0x18004e190  mov     [rsp+58h+var_38], ebx
0x18004e194  mov     rcx, [rcx+10h]
0x18004e198  call    WPP_SF_qd
0x18004e19d  lea     rcx, [rsp+58h+arg_0]; this
0x18004e1a2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004e1a7  mov     rbp, [rsp+58h+arg_10]
0x18004e1ac  mov     eax, ebx
0x18004e1ae  mov     rbx, [rsp+58h+arg_8]
0x18004e1b3  add     rsp, 30h
0x18004e1b7  pop     r14
0x18004e1b9  pop     r13
0x18004e1bb  pop     r12
0x18004e1bd  pop     rdi
0x18004e1be  pop     rsi
0x18004e1bf  retn
```
