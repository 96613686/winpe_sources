# CStreamWriter::WriteBlock(void const *,ulong)

- ea: `0x18004fd90`
- end: `0x18004ffe6`
- name: `?WriteBlock@CStreamWriter@@MEAAJPEBXK@Z`
- size: `598`
- prototype: `__int64 __fastcall(CStreamWriter *__hidden this, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18004ffec`
- `0x18005023c`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18004fd90`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fde4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fe94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ff32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fde4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fe94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ff32`

## string_xrefs

- `0x18004fdb6`: `CStreamWriter::WriteBlock`
- `0x18004fe3b`: `CStreamWriter::WriteBlock`
- `0x18004feeb`: `CStreamWriter::WriteBlock`
- `0x18004ff89`: `CStreamWriter::WriteBlock`

## pseudocode

```c
__int64 __fastcall CStreamWriter::WriteBlock(CStreamWriter *this, const void *a2, unsigned int a3)
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
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "CStreamWriter::WriteBlock", 54);
  v7 = *((_QWORD *)this + 1);
  if ( v7 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const void *, _QWORD, int *))(*(_QWORD *)v7 + 32LL))(v7, a2, a3, &v22);
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
            CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamWriter::WriteBlock", 61, -2147024809);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v12 = 13;
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
          CallStackContext::TraceFailure(v16, "CStreamWriter::WriteBlock", 57, v9);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 12;
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
        CallStackContext::TraceFailure(v11, "CStreamWriter::WriteBlock", 54, -1072875850);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 11;
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
0x18004fd90  mov     rax, rsp
0x18004fd93  mov     [rax+10h], rbx
0x18004fd97  mov     [rax+18h], rsi
0x18004fd9b  push    rdi
0x18004fd9c  sub     rsp, 30h
0x18004fda0  mov     edi, r8d
0x18004fda3  mov     dword ptr [rax+20h], 0
0x18004fdaa  mov     rbx, rdx
0x18004fdad  mov     rsi, rcx
0x18004fdb0  mov     r8d, 36h ; '6'; int
0x18004fdb6  lea     rdx, aCstreamwriterW; "CStreamWriter::WriteBlock"
0x18004fdbd  lea     rcx, [rax+8]; this
0x18004fdc1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004fdc6  mov     rcx, [rsi+8]
0x18004fdca  test    rcx, rcx
0x18004fdcd  jnz     loc_18004FE67
0x18004fdd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fdda  mov     ebx, 0C00D36B6h
0x18004fddf  test    rcx, rcx
0x18004fde2  jnz     short loc_18004FE25
0x18004fde4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fdea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fdf1  mov     rcx, rax
0x18004fdf4  test    rax, rax
0x18004fdf7  jz      short loc_18004FE17
0x18004fdf9  mov     rax, [rax]
0x18004fdfc  mov     edx, 7F0h
0x18004fe01  mov     rax, [rax+8]
0x18004fe05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe0a  test    eax, eax
0x18004fe0c  jz      short loc_18004FE17
0x18004fe0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fe15  jmp     short loc_18004FE25
0x18004fe17  lea     rcx, qword_180069A90; this
0x18004fe1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fe25  cmp     byte ptr [rcx+8], 0
0x18004fe29  jz      short loc_18004FE50
0x18004fe2b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fe30  cmp     [rax+7CCh], ebx
0x18004fe36  jz      short loc_18004FE50
0x18004fe38  mov     r9d, ebx; int
0x18004fe3b  lea     rdx, aCstreamwriterW; "CStreamWriter::WriteBlock"
0x18004fe42  mov     r8d, 36h ; '6'; int
0x18004fe48  mov     rcx, rax; this
0x18004fe4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fe50  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fe55  cmp     al, 1
0x18004fe57  jb      loc_18004FFCA
0x18004fe5d  mov     edx, 0Bh
0x18004fe62  jmp     loc_18004FFAC
0x18004fe67  mov     rax, [rcx]
0x18004fe6a  lea     r9, [rsp+38h+arg_18]
0x18004fe6f  mov     r8d, edi
0x18004fe72  mov     rdx, rbx
0x18004fe75  mov     rax, [rax+20h]
0x18004fe79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe7e  mov     ebx, eax
0x18004fe80  test    eax, eax
0x18004fe82  jns     loc_18004FF17
0x18004fe88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fe8f  test    rcx, rcx
0x18004fe92  jnz     short loc_18004FED5
0x18004fe94  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fe9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fea1  mov     rcx, rax
0x18004fea4  test    rax, rax
0x18004fea7  jz      short loc_18004FEC7
0x18004fea9  mov     rax, [rax]
0x18004feac  mov     edx, 7F0h
0x18004feb1  mov     rax, [rax+8]
0x18004feb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004feba  test    eax, eax
0x18004febc  jz      short loc_18004FEC7
0x18004febe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fec5  jmp     short loc_18004FED5
0x18004fec7  lea     rcx, qword_180069A90; this
0x18004fece  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fed5  cmp     byte ptr [rcx+8], 0
0x18004fed9  jz      short loc_18004FF00
0x18004fedb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fee0  cmp     [rax+7CCh], ebx
0x18004fee6  jz      short loc_18004FF00
0x18004fee8  mov     r9d, ebx; int
0x18004feeb  lea     rdx, aCstreamwriterW; "CStreamWriter::WriteBlock"
0x18004fef2  mov     r8d, 39h ; '9'; int
0x18004fef8  mov     rcx, rax; this
0x18004fefb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ff00  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ff05  cmp     al, 1
0x18004ff07  jb      loc_18004FFCA
0x18004ff0d  mov     edx, 0Ch
0x18004ff12  jmp     loc_18004FFAC
0x18004ff17  cmp     [rsp+38h+arg_18], edi
0x18004ff1b  jz      loc_18004FFCA
0x18004ff21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff28  mov     ebx, 80070057h
0x18004ff2d  test    rcx, rcx
0x18004ff30  jnz     short loc_18004FF73
0x18004ff32  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ff38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff3f  mov     rcx, rax
0x18004ff42  test    rax, rax
0x18004ff45  jz      short loc_18004FF65
0x18004ff47  mov     rax, [rax]
0x18004ff4a  mov     edx, 7F0h
0x18004ff4f  mov     rax, [rax+8]
0x18004ff53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff58  test    eax, eax
0x18004ff5a  jz      short loc_18004FF65
0x18004ff5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff63  jmp     short loc_18004FF73
0x18004ff65  lea     rcx, qword_180069A90; this
0x18004ff6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff73  cmp     byte ptr [rcx+8], 0
0x18004ff77  jz      short loc_18004FF9E
0x18004ff79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ff7e  cmp     [rax+7CCh], ebx
0x18004ff84  jz      short loc_18004FF9E
0x18004ff86  mov     r9d, ebx; int
0x18004ff89  lea     rdx, aCstreamwriterW; "CStreamWriter::WriteBlock"
0x18004ff90  mov     r8d, 3Dh ; '='; int
0x18004ff96  mov     rcx, rax; this
0x18004ff99  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ff9e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ffa3  cmp     al, 1
0x18004ffa5  jb      short loc_18004FFCA
0x18004ffa7  mov     edx, 0Dh
0x18004ffac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ffb3  lea     r8, WPP_6dd5de0f919434228b32263d8b482734_Traceguids
0x18004ffba  mov     r9, rsi
0x18004ffbd  mov     [rsp+38h+var_18], ebx
0x18004ffc1  mov     rcx, [rcx+10h]
0x18004ffc5  call    WPP_SF_qd
0x18004ffca  lea     rcx, [rsp+38h+arg_0]; this
0x18004ffcf  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004ffd4  mov     rsi, [rsp+38h+arg_10]
0x18004ffd9  mov     eax, ebx
0x18004ffdb  mov     rbx, [rsp+38h+arg_8]
0x18004ffe0  add     rsp, 30h
0x18004ffe4  pop     rdi
0x18004ffe5  retn
```
