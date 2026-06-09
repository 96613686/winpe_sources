# CStreamReader::ReadBlock(uchar *,ulong)

- ea: `0x18004f8c0`
- end: `0x18004fb16`
- name: `?ReadBlock@CStreamReader@@MEAAJPEAEK@Z`
- size: `598`
- prototype: `__int64 __fastcall(CStreamReader *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18004f8c0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f914`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f9c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fa62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f914`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f9c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fa62`

## string_xrefs

- `0x18004f8e6`: `CStreamReader::ReadBlock`
- `0x18004f96b`: `CStreamReader::ReadBlock`
- `0x18004fa1b`: `CStreamReader::ReadBlock`
- `0x18004fab9`: `CStreamReader::ReadBlock`

## pseudocode

```c
__int64 __fastcall CStreamReader::ReadBlock(CStreamReader *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 *v8; // rcx
  int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v21; // [rsp+40h] [rbp+8h] BYREF
  int v22; // [rsp+58h] [rbp+20h] BYREF

  v22 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "CStreamReader::ReadBlock", 164);
  v7 = *((_QWORD *)this + 1);
  if ( v7 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, int *))(*(_QWORD *)v7 + 24LL))(v7, a2, a3, &v22);
    if ( v9 >= 0 )
    {
      if ( v22 != a3 )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        v9 = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamReader::ReadBlock", 170, -2147024809);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v12 = 26;
          goto LABEL_34;
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
        if ( *((_DWORD *)v16 + 499) != v9 )
          CallStackContext::TraceFailure(v16, "CStreamReader::ReadBlock", 166, v9);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 25;
        goto LABEL_34;
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -1072875850;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v11 + 499) != -1072875850 )
        CallStackContext::TraceFailure(v11, "CStreamReader::ReadBlock", 164, -1072875850);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 24;
LABEL_34:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_6dd5de0f919434228b32263d8b482734_Traceguids, this, v9);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004f8c0  mov     rax, rsp
0x18004f8c3  mov     [rax+10h], rbx
0x18004f8c7  mov     [rax+18h], rsi
0x18004f8cb  push    rdi
0x18004f8cc  sub     rsp, 30h
0x18004f8d0  mov     edi, r8d
0x18004f8d3  mov     dword ptr [rax+20h], 0
0x18004f8da  mov     rbx, rdx
0x18004f8dd  mov     rsi, rcx
0x18004f8e0  mov     r8d, 0A4h; int
0x18004f8e6  lea     rdx, aCstreamreaderR_0; "CStreamReader::ReadBlock"
0x18004f8ed  lea     rcx, [rax+8]; this
0x18004f8f1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004f8f6  mov     rcx, [rsi+8]
0x18004f8fa  test    rcx, rcx
0x18004f8fd  jnz     loc_18004F997
0x18004f903  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f90a  mov     ebx, 0C00D36B6h
0x18004f90f  test    rcx, rcx
0x18004f912  jnz     short loc_18004F955
0x18004f914  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f91a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f921  mov     rcx, rax
0x18004f924  test    rax, rax
0x18004f927  jz      short loc_18004F947
0x18004f929  mov     rax, [rax]
0x18004f92c  mov     edx, 7F0h
0x18004f931  mov     rax, [rax+8]
0x18004f935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f93a  test    eax, eax
0x18004f93c  jz      short loc_18004F947
0x18004f93e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f945  jmp     short loc_18004F955
0x18004f947  lea     rcx, qword_180069A90; this
0x18004f94e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f955  cmp     byte ptr [rcx+8], 0
0x18004f959  jz      short loc_18004F980
0x18004f95b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f960  cmp     [rax+7CCh], ebx
0x18004f966  jz      short loc_18004F980
0x18004f968  mov     r9d, ebx; int
0x18004f96b  lea     rdx, aCstreamreaderR_0; "CStreamReader::ReadBlock"
0x18004f972  mov     r8d, 0A4h; int
0x18004f978  mov     rcx, rax; this
0x18004f97b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004f980  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004f985  cmp     al, 1
0x18004f987  jb      loc_18004FAFA
0x18004f98d  mov     edx, 18h
0x18004f992  jmp     loc_18004FADC
0x18004f997  mov     rax, [rcx]
0x18004f99a  lea     r9, [rsp+38h+arg_18]
0x18004f99f  mov     r8d, edi
0x18004f9a2  mov     rdx, rbx
0x18004f9a5  mov     rax, [rax+18h]
0x18004f9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9ae  mov     ebx, eax
0x18004f9b0  test    eax, eax
0x18004f9b2  jns     loc_18004FA47
0x18004f9b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f9bf  test    rcx, rcx
0x18004f9c2  jnz     short loc_18004FA05
0x18004f9c4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f9ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f9d1  mov     rcx, rax
0x18004f9d4  test    rax, rax
0x18004f9d7  jz      short loc_18004F9F7
0x18004f9d9  mov     rax, [rax]
0x18004f9dc  mov     edx, 7F0h
0x18004f9e1  mov     rax, [rax+8]
0x18004f9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9ea  test    eax, eax
0x18004f9ec  jz      short loc_18004F9F7
0x18004f9ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f9f5  jmp     short loc_18004FA05
0x18004f9f7  lea     rcx, qword_180069A90; this
0x18004f9fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fa05  cmp     byte ptr [rcx+8], 0
0x18004fa09  jz      short loc_18004FA30
0x18004fa0b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fa10  cmp     [rax+7CCh], ebx
0x18004fa16  jz      short loc_18004FA30
0x18004fa18  mov     r9d, ebx; int
0x18004fa1b  lea     rdx, aCstreamreaderR_0; "CStreamReader::ReadBlock"
0x18004fa22  mov     r8d, 0A6h; int
0x18004fa28  mov     rcx, rax; this
0x18004fa2b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fa30  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fa35  cmp     al, 1
0x18004fa37  jb      loc_18004FAFA
0x18004fa3d  mov     edx, 19h
0x18004fa42  jmp     loc_18004FADC
0x18004fa47  cmp     [rsp+38h+arg_18], edi
0x18004fa4b  jz      loc_18004FAFA
0x18004fa51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fa58  mov     ebx, 80070057h
0x18004fa5d  test    rcx, rcx
0x18004fa60  jnz     short loc_18004FAA3
0x18004fa62  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fa68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fa6f  mov     rcx, rax
0x18004fa72  test    rax, rax
0x18004fa75  jz      short loc_18004FA95
0x18004fa77  mov     rax, [rax]
0x18004fa7a  mov     edx, 7F0h
0x18004fa7f  mov     rax, [rax+8]
0x18004fa83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa88  test    eax, eax
0x18004fa8a  jz      short loc_18004FA95
0x18004fa8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fa93  jmp     short loc_18004FAA3
0x18004fa95  lea     rcx, qword_180069A90; this
0x18004fa9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004faa3  cmp     byte ptr [rcx+8], 0
0x18004faa7  jz      short loc_18004FACE
0x18004faa9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004faae  cmp     [rax+7CCh], ebx
0x18004fab4  jz      short loc_18004FACE
0x18004fab6  mov     r9d, ebx; int
0x18004fab9  lea     rdx, aCstreamreaderR_0; "CStreamReader::ReadBlock"
0x18004fac0  mov     r8d, 0AAh; int
0x18004fac6  mov     rcx, rax; this
0x18004fac9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004face  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fad3  cmp     al, 1
0x18004fad5  jb      short loc_18004FAFA
0x18004fad7  mov     edx, 1Ah
0x18004fadc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fae3  lea     r8, WPP_6dd5de0f919434228b32263d8b482734_Traceguids
0x18004faea  mov     r9, rsi
0x18004faed  mov     [rsp+38h+var_18], ebx
0x18004faf1  mov     rcx, [rcx+10h]
0x18004faf5  call    WPP_SF_qd
0x18004fafa  lea     rcx, [rsp+38h+arg_0]; this
0x18004faff  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004fb04  mov     rsi, [rsp+38h+arg_10]
0x18004fb09  mov     eax, ebx
0x18004fb0b  mov     rbx, [rsp+38h+arg_8]
0x18004fb10  add     rsp, 30h
0x18004fb14  pop     rdi
0x18004fb15  retn
```
