# CTranscodeProfile::SerializeAttributes(CBufferWriter &,IMFAttributes *)

- ea: `0x18001b9ec`
- end: `0x18001bc39`
- name: `?SerializeAttributes@CTranscodeProfile@@IEAAJAEAVCBufferWriter@@PEAUIMFAttributes@@@Z`
- size: `589`
- prototype: `int(CTranscodeProfile *__hidden this, struct CBufferWriter *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001b5c0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001b9ec`
- `0x18001c280`
- `0x18004f410`
- `0x180052c48`
- `0x180052f78`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ba45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bae8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bb8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ba45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bae8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bb8c`

## pseudocode

```c
__int64 __fastcall CTranscodeProfile::SerializeAttributes(
        CTranscodeProfile *this,
        struct CBufferWriter *a2,
        struct IMFAttributes *a3)
{
  CBinaryWriter *v6; // rdi
  __int64 v7; // rdx
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v22; // [rsp+60h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CTranscodeProfile::SerializeAttributes", 525);
  v6 = (struct CBufferWriter *)((char *)a2 + 520);
  if ( a3 )
  {
    v8 = CBinaryWriter::WriteBool(v6, 1);
    if ( v8 >= 0 )
    {
      v8 = CBinaryWriter::WriteAttributes(v6, a3);
      if ( v8 < 0 )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeProfile::SerializeAttributes", 536, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v12 = 64;
          goto LABEL_35;
        }
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
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(v16, "CTranscodeProfile::SerializeAttributes", 535, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 63;
        goto LABEL_35;
      }
    }
  }
  else
  {
    v8 = CBinaryWriter::WriteBool(v6, 0);
    if ( v8 < 0 )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
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
        if ( *((_DWORD *)v11 + 499) != v8 )
          CallStackContext::TraceFailure(v11, "CTranscodeProfile::SerializeAttributes", 531, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 62;
LABEL_35:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, this, v8);
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001b9ec  push    rbx
0x18001b9ee  push    rbp
0x18001b9ef  push    rsi
0x18001b9f0  push    rdi
0x18001b9f1  sub     rsp, 38h
0x18001b9f5  mov     rsi, r8
0x18001b9f8  mov     rdi, rdx
0x18001b9fb  mov     rbp, rcx
0x18001b9fe  lea     rdx, aCtranscodeprof_14; "CTranscodeProfile::SerializeAttributes"
0x18001ba05  mov     r8d, 20Dh; int
0x18001ba0b  lea     rcx, [rsp+58h+arg_0]; this
0x18001ba10  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001ba15  add     rdi, 208h
0x18001ba1c  mov     rcx, rdi; this
0x18001ba1f  test    rsi, rsi
0x18001ba22  jnz     loc_18001BAC8
0x18001ba28  xor     edx, edx; int
0x18001ba2a  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x18001ba2f  mov     ebx, eax
0x18001ba31  test    eax, eax
0x18001ba33  jns     loc_18001BC24
0x18001ba39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ba40  test    rcx, rcx
0x18001ba43  jnz     short loc_18001BA86
0x18001ba45  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001ba4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ba52  mov     rcx, rax
0x18001ba55  test    rax, rax
0x18001ba58  jz      short loc_18001BA78
0x18001ba5a  mov     rax, [rax]
0x18001ba5d  mov     edx, 7F0h
0x18001ba62  mov     rax, [rax+8]
0x18001ba66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba6b  test    eax, eax
0x18001ba6d  jz      short loc_18001BA78
0x18001ba6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ba76  jmp     short loc_18001BA86
0x18001ba78  lea     rcx, qword_180069A90; this
0x18001ba7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ba86  cmp     byte ptr [rcx+8], 0
0x18001ba8a  jz      short loc_18001BAB1
0x18001ba8c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001ba91  cmp     [rax+7CCh], ebx
0x18001ba97  jz      short loc_18001BAB1
0x18001ba99  mov     r9d, ebx; int
0x18001ba9c  lea     rdx, aCtranscodeprof_14; "CTranscodeProfile::SerializeAttributes"
0x18001baa3  mov     r8d, 213h; int
0x18001baa9  mov     rcx, rax; this
0x18001baac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001bab1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001bab6  cmp     al, 1
0x18001bab8  jb      loc_18001BC24
0x18001babe  mov     edx, 3Eh ; '>'
0x18001bac3  jmp     loc_18001BC06
0x18001bac8  mov     edx, 1; int
0x18001bacd  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x18001bad2  mov     ebx, eax
0x18001bad4  test    eax, eax
0x18001bad6  jns     loc_18001BB6B
0x18001badc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bae3  test    rcx, rcx
0x18001bae6  jnz     short loc_18001BB29
0x18001bae8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001baee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001baf5  mov     rcx, rax
0x18001baf8  test    rax, rax
0x18001bafb  jz      short loc_18001BB1B
0x18001bafd  mov     rax, [rax]
0x18001bb00  mov     edx, 7F0h
0x18001bb05  mov     rax, [rax+8]
0x18001bb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb0e  test    eax, eax
0x18001bb10  jz      short loc_18001BB1B
0x18001bb12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bb19  jmp     short loc_18001BB29
0x18001bb1b  lea     rcx, qword_180069A90; this
0x18001bb22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bb29  cmp     byte ptr [rcx+8], 0
0x18001bb2d  jz      short loc_18001BB54
0x18001bb2f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001bb34  cmp     [rax+7CCh], ebx
0x18001bb3a  jz      short loc_18001BB54
0x18001bb3c  mov     r9d, ebx; int
0x18001bb3f  lea     rdx, aCtranscodeprof_14; "CTranscodeProfile::SerializeAttributes"
0x18001bb46  mov     r8d, 217h; int
0x18001bb4c  mov     rcx, rax; this
0x18001bb4f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001bb54  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001bb59  cmp     al, 1
0x18001bb5b  jb      loc_18001BC24
0x18001bb61  mov     edx, 3Fh ; '?'
0x18001bb66  jmp     loc_18001BC06
0x18001bb6b  mov     rdx, rsi; pAttributes
0x18001bb6e  mov     rcx, rdi; this
0x18001bb71  call    ?WriteAttributes@CBinaryWriter@@QEAAJPEAUIMFAttributes@@@Z; CBinaryWriter::WriteAttributes(IMFAttributes *)
0x18001bb76  mov     ebx, eax
0x18001bb78  test    eax, eax
0x18001bb7a  jns     loc_18001BC24
0x18001bb80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bb87  test    rcx, rcx
0x18001bb8a  jnz     short loc_18001BBCD
0x18001bb8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001bb92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bb99  mov     rcx, rax
0x18001bb9c  test    rax, rax
0x18001bb9f  jz      short loc_18001BBBF
0x18001bba1  mov     rax, [rax]
0x18001bba4  mov     edx, 7F0h
0x18001bba9  mov     rax, [rax+8]
0x18001bbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbb2  test    eax, eax
0x18001bbb4  jz      short loc_18001BBBF
0x18001bbb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bbbd  jmp     short loc_18001BBCD
0x18001bbbf  lea     rcx, qword_180069A90; this
0x18001bbc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bbcd  cmp     byte ptr [rcx+8], 0
0x18001bbd1  jz      short loc_18001BBF8
0x18001bbd3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001bbd8  cmp     [rax+7CCh], ebx
0x18001bbde  jz      short loc_18001BBF8
0x18001bbe0  mov     r9d, ebx; int
0x18001bbe3  lea     rdx, aCtranscodeprof_14; "CTranscodeProfile::SerializeAttributes"
0x18001bbea  mov     r8d, 218h; int
0x18001bbf0  mov     rcx, rax; this
0x18001bbf3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001bbf8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001bbfd  cmp     al, 1
0x18001bbff  jb      short loc_18001BC24
0x18001bc01  mov     edx, 40h ; '@'
0x18001bc06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc0d  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x18001bc14  mov     r9, rbp
0x18001bc17  mov     [rsp+58h+var_38], ebx
0x18001bc1b  mov     rcx, [rcx+10h]
0x18001bc1f  call    WPP_SF_qd
0x18001bc24  lea     rcx, [rsp+58h+arg_0]; this
0x18001bc29  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001bc2e  mov     eax, ebx
0x18001bc30  add     rsp, 38h
0x18001bc34  pop     rdi
0x18001bc35  pop     rsi
0x18001bc36  pop     rbp
0x18001bc37  pop     rbx
0x18001bc38  retn
```
