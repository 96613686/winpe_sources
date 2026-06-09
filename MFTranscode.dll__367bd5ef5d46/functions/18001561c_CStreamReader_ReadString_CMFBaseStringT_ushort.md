# CStreamReader::ReadString(CMFBaseStringT<ushort> &)

- ea: `0x18001561c`
- end: `0x18001593e`
- name: `?ReadString@CStreamReader@@QEAAJAEAV?$CMFBaseStringT@G@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(CBinaryReader *this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800332d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001561c`
- `0x180015944`
- `0x18001a330`
- `0x18001c280`
- `0x18004a368`
- `0x18004f410`
- `0x180050738`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015674`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015734`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800157e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800158a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015674`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015734`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800157e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800158a0`

## string_xrefs

- `0x18001563f`: `CStreamReader::ReadString`

## pseudocode

```c
__int64 __fastcall CStreamReader::ReadString(CBinaryReader *this, __int64 a2)
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
  __int64 Buffer; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v23; // [rsp+50h] [rbp+8h] BYREF
  int v24; // [rsp+60h] [rbp+18h] BYREF
  int v25; // [rsp+68h] [rbp+20h] BYREF

  v25 = 0;
  v24 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v23, "CStreamReader::ReadString", 224);
  if ( *((_QWORD *)this + 1) )
  {
    v6 = CBinaryReader::ReadInt32(this, &v24);
    if ( v6 >= 0 )
    {
      if ( !v24 )
        goto LABEL_48;
      Buffer = CMFBaseStringT<unsigned short>::GetBuffer(a2);
      if ( Buffer )
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 1) + 24LL))(
               *((_QWORD *)this + 1),
               Buffer,
               (unsigned int)(2 * v24),
               &v25);
        if ( v6 >= 0 )
        {
          CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)v24);
          goto LABEL_48;
        }
        CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, 0);
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
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
        if ( *((_BYTE *)v19 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamReader::ReadString", 245, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 34;
          goto LABEL_12;
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        v6 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
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
          if ( *((_DWORD *)v17 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v17, "CStreamReader::ReadString", 239, -2147024882);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 33;
          goto LABEL_12;
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
          CallStackContext::TraceFailure(v13, "CStreamReader::ReadString", 228, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 32;
        goto LABEL_12;
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
        CallStackContext::TraceFailure(v8, "CStreamReader::ReadString", 224, -1072875850);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 31;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_6dd5de0f919434228b32263d8b482734_Traceguids, this, v6);
    }
  }
LABEL_48:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v23);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001561c  mov     rax, rsp
0x18001561f  mov     [rax+10h], rbx
0x180015623  push    rsi
0x180015624  push    rdi
0x180015625  push    r14
0x180015627  sub     rsp, 30h
0x18001562b  mov     rsi, rdx
0x18001562e  mov     dword ptr [rax+20h], 0
0x180015635  mov     rdi, rcx
0x180015638  mov     dword ptr [rax+18h], 0
0x18001563f  lea     r14, aCstreamreaderR; "CStreamReader::ReadString"
0x180015646  mov     r8d, 0E0h; int
0x18001564c  mov     rdx, r14; char *
0x18001564f  lea     rcx, [rax+8]; this
0x180015653  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015658  cmp     qword ptr [rdi+8], 0
0x18001565d  jnz     loc_180015711
0x180015663  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001566a  mov     ebx, 0C00D36B6h
0x18001566f  test    rcx, rcx
0x180015672  jnz     short loc_1800156B5
0x180015674  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001567a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015681  mov     rcx, rax
0x180015684  test    rax, rax
0x180015687  jz      short loc_1800156A7
0x180015689  mov     rax, [rax]
0x18001568c  mov     edx, 7F0h
0x180015691  mov     rax, [rax+8]
0x180015695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001569a  test    eax, eax
0x18001569c  jz      short loc_1800156A7
0x18001569e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800156a5  jmp     short loc_1800156B5
0x1800156a7  lea     rcx, qword_180069A90; this
0x1800156ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800156b5  cmp     byte ptr [rcx+8], 0
0x1800156b9  jz      short loc_1800156DC
0x1800156bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800156c0  cmp     [rax+7CCh], ebx
0x1800156c6  jz      short loc_1800156DC
0x1800156c8  mov     r9d, ebx; int
0x1800156cb  mov     r8d, 0E0h; int
0x1800156d1  mov     rdx, r14; char *
0x1800156d4  mov     rcx, rax; this
0x1800156d7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800156dc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800156e1  cmp     al, 1
0x1800156e3  jb      loc_180015924
0x1800156e9  mov     edx, 1Fh
0x1800156ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156f5  lea     r8, WPP_6dd5de0f919434228b32263d8b482734_Traceguids
0x1800156fc  mov     r9, rdi
0x1800156ff  mov     [rsp+48h+var_28], ebx
0x180015703  mov     rcx, [rcx+10h]
0x180015707  call    WPP_SF_qd
0x18001570c  jmp     loc_180015924
0x180015711  lea     rdx, [rsp+48h+arg_10]; int *
0x180015716  mov     rcx, rdi; this
0x180015719  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x18001571e  mov     ebx, eax
0x180015720  test    eax, eax
0x180015722  jns     loc_1800157B3
0x180015728  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001572f  test    rcx, rcx
0x180015732  jnz     short loc_180015775
0x180015734  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001573a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015741  mov     rcx, rax
0x180015744  test    rax, rax
0x180015747  jz      short loc_180015767
0x180015749  mov     rax, [rax]
0x18001574c  mov     edx, 7F0h
0x180015751  mov     rax, [rax+8]
0x180015755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001575a  test    eax, eax
0x18001575c  jz      short loc_180015767
0x18001575e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015765  jmp     short loc_180015775
0x180015767  lea     rcx, qword_180069A90; this
0x18001576e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015775  cmp     byte ptr [rcx+8], 0
0x180015779  jz      short loc_18001579C
0x18001577b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015780  cmp     [rax+7CCh], ebx
0x180015786  jz      short loc_18001579C
0x180015788  mov     r9d, ebx; int
0x18001578b  mov     r8d, 0E4h; int
0x180015791  mov     rdx, r14; char *
0x180015794  mov     rcx, rax; this
0x180015797  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001579c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800157a1  cmp     al, 1
0x1800157a3  jb      loc_180015924
0x1800157a9  mov     edx, 20h ; ' '
0x1800157ae  jmp     loc_1800156EE
0x1800157b3  mov     edx, [rsp+48h+arg_10]
0x1800157b7  test    edx, edx
0x1800157b9  jz      loc_180015924
0x1800157bf  mov     rcx, rsi
0x1800157c2  call    ?GetBuffer@?$CMFBaseStringT@G@@QEAAPEAGJ@Z; CMFBaseStringT<ushort>::GetBuffer(long)
0x1800157c7  mov     rdx, rax
0x1800157ca  test    rax, rax
0x1800157cd  jnz     loc_180015863
0x1800157d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800157da  mov     ebx, 8007000Eh
0x1800157df  test    rcx, rcx
0x1800157e2  jnz     short loc_180015825
0x1800157e4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800157ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800157f1  mov     rcx, rax
0x1800157f4  test    rax, rax
0x1800157f7  jz      short loc_180015817
0x1800157f9  mov     rax, [rax]
0x1800157fc  mov     edx, 7F0h
0x180015801  mov     rax, [rax+8]
0x180015805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001580a  test    eax, eax
0x18001580c  jz      short loc_180015817
0x18001580e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015815  jmp     short loc_180015825
0x180015817  lea     rcx, qword_180069A90; this
0x18001581e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015825  cmp     byte ptr [rcx+8], 0
0x180015829  jz      short loc_18001584C
0x18001582b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015830  cmp     [rax+7CCh], ebx
0x180015836  jz      short loc_18001584C
0x180015838  mov     r9d, ebx; int
0x18001583b  mov     r8d, 0EFh; int
0x180015841  mov     rdx, r14; char *
0x180015844  mov     rcx, rax; this
0x180015847  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001584c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180015851  cmp     al, 1
0x180015853  jb      loc_180015924
0x180015859  mov     edx, 21h ; '!'
0x18001585e  jmp     loc_1800156EE
0x180015863  mov     rcx, [rdi+8]
0x180015867  lea     r9, [rsp+48h+arg_18]
0x18001586c  mov     r8d, [rsp+48h+arg_10]
0x180015871  add     r8d, r8d
0x180015874  mov     rax, [rcx]
0x180015877  mov     rax, [rax+18h]
0x18001587b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015880  mov     ebx, eax
0x180015882  mov     rcx, rsi
0x180015885  test    eax, eax
0x180015887  jns     loc_18001591B
0x18001588d  xor     edx, edx
0x18001588f  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x180015894  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001589b  test    rcx, rcx
0x18001589e  jnz     short loc_1800158E1
0x1800158a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800158a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800158ad  mov     rcx, rax
0x1800158b0  test    rax, rax
0x1800158b3  jz      short loc_1800158D3
0x1800158b5  mov     rax, [rax]
0x1800158b8  mov     edx, 7F0h
0x1800158bd  mov     rax, [rax+8]
0x1800158c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158c6  test    eax, eax
0x1800158c8  jz      short loc_1800158D3
0x1800158ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800158d1  jmp     short loc_1800158E1
0x1800158d3  lea     rcx, qword_180069A90; this
0x1800158da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800158e1  cmp     byte ptr [rcx+8], 0
0x1800158e5  jz      short loc_180015908
0x1800158e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800158ec  cmp     [rax+7CCh], ebx
0x1800158f2  jz      short loc_180015908
0x1800158f4  mov     r9d, ebx; int
0x1800158f7  mov     r8d, 0F5h; int
0x1800158fd  mov     rdx, r14; char *
0x180015900  mov     rcx, rax; this
0x180015903  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015908  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001590d  cmp     al, 1
0x18001590f  jb      short loc_180015924
0x180015911  mov     edx, 22h ; '"'
0x180015916  jmp     loc_1800156EE
0x18001591b  mov     edx, [rsp+48h+arg_10]
0x18001591f  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x180015924  lea     rcx, [rsp+48h+arg_0]; this
0x180015929  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001592e  mov     eax, ebx
0x180015930  mov     rbx, [rsp+48h+arg_8]
0x180015935  add     rsp, 30h
0x180015939  pop     r14
0x18001593b  pop     rdi
0x18001593c  pop     rsi
0x18001593d  retn
```
