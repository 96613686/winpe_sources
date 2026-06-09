# CStreamWriter::WriteString(CMFBaseStringT<ushort> &)

- ea: `0x18005023c`
- end: `0x1800504a4`
- name: `?WriteString@CStreamWriter@@QEAAJAEAV?$CMFBaseStringT@G@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(CStreamWriter *this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180033df0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000f05c`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18004fd90`
- `0x18005023c`
- `0x180052f78`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050284`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800503f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050284`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800503f0`

## string_xrefs

- `0x180050251`: `CStreamWriter::WriteString`
- `0x1800502db`: `CStreamWriter::WriteString`
- `0x180050389`: `CStreamWriter::WriteString`
- `0x180050447`: `CStreamWriter::WriteString`

## pseudocode

```c
__int64 __fastcall CStreamWriter::WriteString(CStreamWriter *this, __int64 a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  int v10; // edx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  const void *v15; // rax
  int v16; // r8d
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v22; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CStreamWriter::WriteString", 91);
  if ( *((_QWORD *)this + 1) )
  {
    if ( *(int *)(a2 + 4) >= 0 )
      v10 = *(_DWORD *)(a2 + 8);
    else
      v10 = 0;
    v6 = CBinaryWriter::WriteBool(this, v10);
    if ( v6 >= 0 )
    {
      v15 = (const void *)CMFBaseStringT<unsigned short>::PContents(a2, v11);
      v6 = CStreamWriter::WriteBlock(this, v15, 2 * v16);
      if ( v6 < 0 )
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
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamWriter::WriteString", 98, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 19;
          goto LABEL_37;
        }
      }
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != v6 )
          CallStackContext::TraceFailure(v14, "CStreamWriter::WriteString", 95, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 18;
        goto LABEL_37;
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
        CallStackContext::TraceFailure(v8, "CStreamWriter::WriteString", 91, -1072875850);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 17;
LABEL_37:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_6dd5de0f919434228b32263d8b482734_Traceguids, this, v6);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005023c  mov     [rsp+arg_8], rbx
0x180050241  mov     [rsp+arg_10], rsi
0x180050246  push    rdi
0x180050247  sub     rsp, 30h
0x18005024b  mov     rdi, rdx
0x18005024e  mov     rsi, rcx
0x180050251  lea     rdx, aCstreamwriterW_1; "CStreamWriter::WriteString"
0x180050258  mov     r8d, 5Bh ; '['; int
0x18005025e  lea     rcx, [rsp+38h+arg_0]; this
0x180050263  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180050268  cmp     qword ptr [rsi+8], 0
0x18005026d  jnz     loc_180050307
0x180050273  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005027a  mov     ebx, 0C00D36B6h
0x18005027f  test    rcx, rcx
0x180050282  jnz     short loc_1800502C5
0x180050284  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005028a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050291  mov     rcx, rax
0x180050294  test    rax, rax
0x180050297  jz      short loc_1800502B7
0x180050299  mov     rax, [rax]
0x18005029c  mov     edx, 7F0h
0x1800502a1  mov     rax, [rax+8]
0x1800502a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502aa  test    eax, eax
0x1800502ac  jz      short loc_1800502B7
0x1800502ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800502b5  jmp     short loc_1800502C5
0x1800502b7  lea     rcx, qword_180069A90; this
0x1800502be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800502c5  cmp     byte ptr [rcx+8], 0
0x1800502c9  jz      short loc_1800502F0
0x1800502cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800502d0  cmp     [rax+7CCh], ebx
0x1800502d6  jz      short loc_1800502F0
0x1800502d8  mov     r9d, ebx; int
0x1800502db  lea     rdx, aCstreamwriterW_1; "CStreamWriter::WriteString"
0x1800502e2  mov     r8d, 5Bh ; '['; int
0x1800502e8  mov     rcx, rax; this
0x1800502eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800502f0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800502f5  cmp     al, 1
0x1800502f7  jb      loc_180050488
0x1800502fd  mov     edx, 11h
0x180050302  jmp     loc_18005046A
0x180050307  cmp     dword ptr [rdi+4], 0
0x18005030b  jge     short loc_180050311
0x18005030d  xor     edx, edx
0x18005030f  jmp     short loc_180050314
0x180050311  mov     edx, [rdi+8]; int
0x180050314  mov     rcx, rsi; this
0x180050317  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x18005031c  mov     ebx, eax
0x18005031e  test    eax, eax
0x180050320  jns     loc_1800503B5
0x180050326  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005032d  test    rcx, rcx
0x180050330  jnz     short loc_180050373
0x180050332  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050338  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005033f  mov     rcx, rax
0x180050342  test    rax, rax
0x180050345  jz      short loc_180050365
0x180050347  mov     rax, [rax]
0x18005034a  mov     edx, 7F0h
0x18005034f  mov     rax, [rax+8]
0x180050353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050358  test    eax, eax
0x18005035a  jz      short loc_180050365
0x18005035c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050363  jmp     short loc_180050373
0x180050365  lea     rcx, qword_180069A90; this
0x18005036c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050373  cmp     byte ptr [rcx+8], 0
0x180050377  jz      short loc_18005039E
0x180050379  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005037e  cmp     [rax+7CCh], ebx
0x180050384  jz      short loc_18005039E
0x180050386  mov     r9d, ebx; int
0x180050389  lea     rdx, aCstreamwriterW_1; "CStreamWriter::WriteString"
0x180050390  mov     r8d, 5Fh ; '_'; int
0x180050396  mov     rcx, rax; this
0x180050399  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005039e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800503a3  cmp     al, 1
0x1800503a5  jb      loc_180050488
0x1800503ab  mov     edx, 12h
0x1800503b0  jmp     loc_18005046A
0x1800503b5  cmp     dword ptr [rdi+4], 0
0x1800503b9  jge     short loc_1800503C0
0x1800503bb  xor     r8d, r8d
0x1800503be  jmp     short loc_1800503C4
0x1800503c0  mov     r8d, [rdi+8]
0x1800503c4  mov     rcx, rdi
0x1800503c7  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x1800503cc  mov     rdx, rax; void *
0x1800503cf  add     r8d, r8d; unsigned int
0x1800503d2  mov     rcx, rsi; this
0x1800503d5  call    ?WriteBlock@CStreamWriter@@MEAAJPEBXK@Z; CStreamWriter::WriteBlock(void const *,ulong)
0x1800503da  mov     ebx, eax
0x1800503dc  test    eax, eax
0x1800503de  jns     loc_180050488
0x1800503e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800503eb  test    rcx, rcx
0x1800503ee  jnz     short loc_180050431
0x1800503f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800503f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800503fd  mov     rcx, rax
0x180050400  test    rax, rax
0x180050403  jz      short loc_180050423
0x180050405  mov     rax, [rax]
0x180050408  mov     edx, 7F0h
0x18005040d  mov     rax, [rax+8]
0x180050411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050416  test    eax, eax
0x180050418  jz      short loc_180050423
0x18005041a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050421  jmp     short loc_180050431
0x180050423  lea     rcx, qword_180069A90; this
0x18005042a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050431  cmp     byte ptr [rcx+8], 0
0x180050435  jz      short loc_18005045C
0x180050437  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005043c  cmp     [rax+7CCh], ebx
0x180050442  jz      short loc_18005045C
0x180050444  mov     r9d, ebx; int
0x180050447  lea     rdx, aCstreamwriterW_1; "CStreamWriter::WriteString"
0x18005044e  mov     r8d, 62h ; 'b'; int
0x180050454  mov     rcx, rax; this
0x180050457  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005045c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050461  cmp     al, 1
0x180050463  jb      short loc_180050488
0x180050465  mov     edx, 13h
0x18005046a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050471  lea     r8, WPP_6dd5de0f919434228b32263d8b482734_Traceguids
0x180050478  mov     r9, rsi
0x18005047b  mov     [rsp+38h+var_18], ebx
0x18005047f  mov     rcx, [rcx+10h]
0x180050483  call    WPP_SF_qd
0x180050488  lea     rcx, [rsp+38h+arg_0]; this
0x18005048d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050492  mov     rsi, [rsp+38h+arg_10]
0x180050497  mov     eax, ebx
0x180050499  mov     rbx, [rsp+38h+arg_8]
0x18005049e  add     rsp, 30h
0x1800504a2  pop     rdi
0x1800504a3  retn
```
