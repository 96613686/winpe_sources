# CStreamWriter::WriteByteArray(CByteArray &)

- ea: `0x18004ffec`
- end: `0x180050234`
- name: `?WriteByteArray@CStreamWriter@@QEAAJAEAVCByteArray@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(CStreamWriter *__hidden this, struct CByteArray *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001b5c0`
- `0x180033df0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18004fd90`
- `0x18004ffec`
- `0x180052f78`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050034`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800500d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050180`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050034`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800500d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050180`

## string_xrefs

- `0x180050001`: `CStreamWriter::WriteByteArray`
- `0x18005008b`: `CStreamWriter::WriteByteArray`
- `0x18005012f`: `CStreamWriter::WriteByteArray`
- `0x1800501d7`: `CStreamWriter::WriteByteArray`

## pseudocode

```c
__int64 __fastcall CStreamWriter::WriteByteArray(CStreamWriter *this, struct CByteArray *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int v6; // ebx
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
  struct CallStackContext *ThreadRelativeContext; // rax
  char v19; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v19, "CStreamWriter::WriteByteArray", 110);
  if ( *((_QWORD *)this + 1) )
  {
    v6 = CBinaryWriter::WriteBool(this, *((_DWORD *)a2 + 2));
    if ( v6 >= 0 )
    {
      v6 = CStreamWriter::WriteBlock(this, *(const void **)a2, *((_DWORD *)a2 + 2));
      if ( v6 < 0 )
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamWriter::WriteByteArray", 116, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 22;
          goto LABEL_34;
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
        if ( *((_DWORD *)v13 + 499) != v6 )
          CallStackContext::TraceFailure(v13, "CStreamWriter::WriteByteArray", 113, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 21;
        goto LABEL_34;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = -1072875850;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
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
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v8 + 499) != -1072875850 )
        CallStackContext::TraceFailure(v8, "CStreamWriter::WriteByteArray", 110, -1072875850);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 20;
LABEL_34:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_6dd5de0f919434228b32263d8b482734_Traceguids, this, v6);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004ffec  mov     [rsp+arg_8], rbx
0x18004fff1  mov     [rsp+arg_10], rsi
0x18004fff6  push    rdi
0x18004fff7  sub     rsp, 30h
0x18004fffb  mov     rsi, rdx
0x18004fffe  mov     rdi, rcx
0x180050001  lea     rdx, aCstreamwriterW_0; "CStreamWriter::WriteByteArray"
0x180050008  mov     r8d, 6Eh ; 'n'; int
0x18005000e  lea     rcx, [rsp+38h+arg_0]; this
0x180050013  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180050018  cmp     qword ptr [rdi+8], 0
0x18005001d  jnz     loc_1800500B7
0x180050023  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005002a  mov     ebx, 0C00D36B6h
0x18005002f  test    rcx, rcx
0x180050032  jnz     short loc_180050075
0x180050034  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005003a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050041  mov     rcx, rax
0x180050044  test    rax, rax
0x180050047  jz      short loc_180050067
0x180050049  mov     rax, [rax]
0x18005004c  mov     edx, 7F0h
0x180050051  mov     rax, [rax+8]
0x180050055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005005a  test    eax, eax
0x18005005c  jz      short loc_180050067
0x18005005e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050065  jmp     short loc_180050075
0x180050067  lea     rcx, qword_180069A90; this
0x18005006e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050075  cmp     byte ptr [rcx+8], 0
0x180050079  jz      short loc_1800500A0
0x18005007b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050080  cmp     [rax+7CCh], ebx
0x180050086  jz      short loc_1800500A0
0x180050088  mov     r9d, ebx; int
0x18005008b  lea     rdx, aCstreamwriterW_0; "CStreamWriter::WriteByteArray"
0x180050092  mov     r8d, 6Eh ; 'n'; int
0x180050098  mov     rcx, rax; this
0x18005009b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800500a0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800500a5  cmp     al, 1
0x1800500a7  jb      loc_180050218
0x1800500ad  mov     edx, 14h
0x1800500b2  jmp     loc_1800501FA
0x1800500b7  mov     edx, [rsi+8]; int
0x1800500ba  mov     rcx, rdi; this
0x1800500bd  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x1800500c2  mov     ebx, eax
0x1800500c4  test    eax, eax
0x1800500c6  jns     loc_18005015B
0x1800500cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500d3  test    rcx, rcx
0x1800500d6  jnz     short loc_180050119
0x1800500d8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800500de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500e5  mov     rcx, rax
0x1800500e8  test    rax, rax
0x1800500eb  jz      short loc_18005010B
0x1800500ed  mov     rax, [rax]
0x1800500f0  mov     edx, 7F0h
0x1800500f5  mov     rax, [rax+8]
0x1800500f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500fe  test    eax, eax
0x180050100  jz      short loc_18005010B
0x180050102  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050109  jmp     short loc_180050119
0x18005010b  lea     rcx, qword_180069A90; this
0x180050112  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050119  cmp     byte ptr [rcx+8], 0
0x18005011d  jz      short loc_180050144
0x18005011f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050124  cmp     [rax+7CCh], ebx
0x18005012a  jz      short loc_180050144
0x18005012c  mov     r9d, ebx; int
0x18005012f  lea     rdx, aCstreamwriterW_0; "CStreamWriter::WriteByteArray"
0x180050136  mov     r8d, 71h ; 'q'; int
0x18005013c  mov     rcx, rax; this
0x18005013f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050144  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050149  cmp     al, 1
0x18005014b  jb      loc_180050218
0x180050151  mov     edx, 15h
0x180050156  jmp     loc_1800501FA
0x18005015b  mov     r8d, [rsi+8]; unsigned int
0x18005015f  mov     rcx, rdi; this
0x180050162  mov     rdx, [rsi]; void *
0x180050165  call    ?WriteBlock@CStreamWriter@@MEAAJPEBXK@Z; CStreamWriter::WriteBlock(void const *,ulong)
0x18005016a  mov     ebx, eax
0x18005016c  test    eax, eax
0x18005016e  jns     loc_180050218
0x180050174  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005017b  test    rcx, rcx
0x18005017e  jnz     short loc_1800501C1
0x180050180  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050186  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005018d  mov     rcx, rax
0x180050190  test    rax, rax
0x180050193  jz      short loc_1800501B3
0x180050195  mov     rax, [rax]
0x180050198  mov     edx, 7F0h
0x18005019d  mov     rax, [rax+8]
0x1800501a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501a6  test    eax, eax
0x1800501a8  jz      short loc_1800501B3
0x1800501aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800501b1  jmp     short loc_1800501C1
0x1800501b3  lea     rcx, qword_180069A90; this
0x1800501ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800501c1  cmp     byte ptr [rcx+8], 0
0x1800501c5  jz      short loc_1800501EC
0x1800501c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800501cc  cmp     [rax+7CCh], ebx
0x1800501d2  jz      short loc_1800501EC
0x1800501d4  mov     r9d, ebx; int
0x1800501d7  lea     rdx, aCstreamwriterW_0; "CStreamWriter::WriteByteArray"
0x1800501de  mov     r8d, 74h ; 't'; int
0x1800501e4  mov     rcx, rax; this
0x1800501e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800501ec  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800501f1  cmp     al, 1
0x1800501f3  jb      short loc_180050218
0x1800501f5  mov     edx, 16h
0x1800501fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180050201  lea     r8, WPP_6dd5de0f919434228b32263d8b482734_Traceguids
0x180050208  mov     r9, rdi
0x18005020b  mov     [rsp+38h+var_18], ebx
0x18005020f  mov     rcx, [rcx+10h]
0x180050213  call    WPP_SF_qd
0x180050218  lea     rcx, [rsp+38h+arg_0]; this
0x18005021d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050222  mov     rsi, [rsp+38h+arg_10]
0x180050227  mov     eax, ebx
0x180050229  mov     rbx, [rsp+38h+arg_8]
0x18005022e  add     rsp, 30h
0x180050232  pop     rdi
0x180050233  retn
```
