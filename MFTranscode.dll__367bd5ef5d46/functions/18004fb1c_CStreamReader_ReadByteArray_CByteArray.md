# CStreamReader::ReadByteArray(CByteArray &)

- ea: `0x18004fb1c`
- end: `0x18004fd81`
- name: `?ReadByteArray@CStreamReader@@QEAAJAEAVCByteArray@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(CStreamReader *__hidden this, struct CByteArray *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001aaf0`
- `0x1800332d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001bd34`
- `0x18001c280`
- `0x18004f410`
- `0x18004fb1c`
- `0x180050738`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fb6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fc13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fcd5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fb6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fc13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fcd5`

## string_xrefs

- `0x18004fb3a`: `CStreamReader::ReadByteArray`
- `0x18004fbc4`: `CStreamReader::ReadByteArray`
- `0x18004fc6a`: `CStreamReader::ReadByteArray`
- `0x18004fd2c`: `CStreamReader::ReadByteArray`

## pseudocode

```c
__int64 __fastcall CStreamReader::ReadByteArray(CStreamReader *this, struct CByteArray *a2)
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
  char v19; // [rsp+50h] [rbp+8h] BYREF
  int v20; // [rsp+60h] [rbp+18h] BYREF
  int v21; // [rsp+68h] [rbp+20h] BYREF

  v21 = 0;
  v20 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v19, "CStreamReader::ReadByteArray", 262);
  if ( *((_QWORD *)this + 1) )
  {
    v6 = CBinaryReader::ReadInt32(this, &v20);
    if ( v6 >= 0 )
    {
      CTEntryArray<unsigned char>::SetSize((__int64)a2, v20);
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 1) + 24LL))(
             *((_QWORD *)this + 1),
             *(_QWORD *)a2,
             (unsigned int)v20,
             &v21);
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
            CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamReader::ReadByteArray", 274, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 38;
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
          CallStackContext::TraceFailure(v13, "CStreamReader::ReadByteArray", 265, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 36;
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
        CallStackContext::TraceFailure(v8, "CStreamReader::ReadByteArray", 262, -1072875850);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 35;
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
0x18004fb1c  push    rbx
0x18004fb1e  push    rsi
0x18004fb1f  push    rdi
0x18004fb20  sub     rsp, 30h
0x18004fb24  mov     rsi, rdx
0x18004fb27  mov     [rsp+48h+arg_18], 0
0x18004fb2f  mov     rdi, rcx
0x18004fb32  mov     [rsp+48h+arg_10], 0
0x18004fb3a  lea     rdx, aCstreamreaderR_1; "CStreamReader::ReadByteArray"
0x18004fb41  mov     r8d, 106h; int
0x18004fb47  lea     rcx, [rsp+48h+arg_0]; this
0x18004fb4c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004fb51  cmp     qword ptr [rdi+8], 0
0x18004fb56  jnz     loc_18004FBF0
0x18004fb5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fb63  mov     ebx, 0C00D36B6h
0x18004fb68  test    rcx, rcx
0x18004fb6b  jnz     short loc_18004FBAE
0x18004fb6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fb73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fb7a  mov     rcx, rax
0x18004fb7d  test    rax, rax
0x18004fb80  jz      short loc_18004FBA0
0x18004fb82  mov     rax, [rax]
0x18004fb85  mov     edx, 7F0h
0x18004fb8a  mov     rax, [rax+8]
0x18004fb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb93  test    eax, eax
0x18004fb95  jz      short loc_18004FBA0
0x18004fb97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fb9e  jmp     short loc_18004FBAE
0x18004fba0  lea     rcx, qword_180069A90; this
0x18004fba7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fbae  cmp     byte ptr [rcx+8], 0
0x18004fbb2  jz      short loc_18004FBD9
0x18004fbb4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fbb9  cmp     [rax+7CCh], ebx
0x18004fbbf  jz      short loc_18004FBD9
0x18004fbc1  mov     r9d, ebx; int
0x18004fbc4  lea     rdx, aCstreamreaderR_1; "CStreamReader::ReadByteArray"
0x18004fbcb  mov     r8d, 106h; int
0x18004fbd1  mov     rcx, rax; this
0x18004fbd4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fbd9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fbde  cmp     al, 1
0x18004fbe0  jb      loc_18004FD6D
0x18004fbe6  mov     edx, 23h ; '#'
0x18004fbeb  jmp     loc_18004FD4F
0x18004fbf0  lea     rdx, [rsp+48h+arg_10]; int *
0x18004fbf5  mov     rcx, rdi; this
0x18004fbf8  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x18004fbfd  mov     ebx, eax
0x18004fbff  test    eax, eax
0x18004fc01  jns     loc_18004FC96
0x18004fc07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fc0e  test    rcx, rcx
0x18004fc11  jnz     short loc_18004FC54
0x18004fc13  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fc19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fc20  mov     rcx, rax
0x18004fc23  test    rax, rax
0x18004fc26  jz      short loc_18004FC46
0x18004fc28  mov     rax, [rax]
0x18004fc2b  mov     edx, 7F0h
0x18004fc30  mov     rax, [rax+8]
0x18004fc34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc39  test    eax, eax
0x18004fc3b  jz      short loc_18004FC46
0x18004fc3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fc44  jmp     short loc_18004FC54
0x18004fc46  lea     rcx, qword_180069A90; this
0x18004fc4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fc54  cmp     byte ptr [rcx+8], 0
0x18004fc58  jz      short loc_18004FC7F
0x18004fc5a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fc5f  cmp     [rax+7CCh], ebx
0x18004fc65  jz      short loc_18004FC7F
0x18004fc67  mov     r9d, ebx; int
0x18004fc6a  lea     rdx, aCstreamreaderR_1; "CStreamReader::ReadByteArray"
0x18004fc71  mov     r8d, 109h; int
0x18004fc77  mov     rcx, rax; this
0x18004fc7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fc7f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fc84  cmp     al, 1
0x18004fc86  jb      loc_18004FD6D
0x18004fc8c  mov     edx, 24h ; '$'
0x18004fc91  jmp     loc_18004FD4F
0x18004fc96  mov     edx, [rsp+48h+arg_10]
0x18004fc9a  mov     rcx, rsi
0x18004fc9d  call    ?SetSize@?$CTEntryArray@E@@QEAAHKK@Z; CTEntryArray<uchar>::SetSize(ulong,ulong)
0x18004fca2  mov     rcx, [rdi+8]
0x18004fca6  lea     r9, [rsp+48h+arg_18]
0x18004fcab  mov     r8d, [rsp+48h+arg_10]
0x18004fcb0  mov     rdx, [rsi]
0x18004fcb3  mov     rax, [rcx]
0x18004fcb6  mov     rax, [rax+18h]
0x18004fcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fcbf  mov     ebx, eax
0x18004fcc1  test    eax, eax
0x18004fcc3  jns     loc_18004FD6D
0x18004fcc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fcd0  test    rcx, rcx
0x18004fcd3  jnz     short loc_18004FD16
0x18004fcd5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fcdb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fce2  mov     rcx, rax
0x18004fce5  test    rax, rax
0x18004fce8  jz      short loc_18004FD08
0x18004fcea  mov     rax, [rax]
0x18004fced  mov     edx, 7F0h
0x18004fcf2  mov     rax, [rax+8]
0x18004fcf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fcfb  test    eax, eax
0x18004fcfd  jz      short loc_18004FD08
0x18004fcff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fd06  jmp     short loc_18004FD16
0x18004fd08  lea     rcx, qword_180069A90; this
0x18004fd0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fd16  cmp     byte ptr [rcx+8], 0
0x18004fd1a  jz      short loc_18004FD41
0x18004fd1c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fd21  cmp     [rax+7CCh], ebx
0x18004fd27  jz      short loc_18004FD41
0x18004fd29  mov     r9d, ebx; int
0x18004fd2c  lea     rdx, aCstreamreaderR_1; "CStreamReader::ReadByteArray"
0x18004fd33  mov     r8d, 112h; int
0x18004fd39  mov     rcx, rax; this
0x18004fd3c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004fd41  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004fd46  cmp     al, 1
0x18004fd48  jb      short loc_18004FD6D
0x18004fd4a  mov     edx, 26h ; '&'
0x18004fd4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fd56  lea     r8, WPP_6dd5de0f919434228b32263d8b482734_Traceguids
0x18004fd5d  mov     r9, rdi
0x18004fd60  mov     [rsp+48h+var_28], ebx
0x18004fd64  mov     rcx, [rcx+10h]
0x18004fd68  call    WPP_SF_qd
0x18004fd6d  lea     rcx, [rsp+48h+arg_0]; this
0x18004fd72  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004fd77  mov     eax, ebx
0x18004fd79  add     rsp, 30h
0x18004fd7d  pop     rdi
0x18004fd7e  pop     rsi
0x18004fd7f  pop     rbx
0x18004fd80  retn
```
