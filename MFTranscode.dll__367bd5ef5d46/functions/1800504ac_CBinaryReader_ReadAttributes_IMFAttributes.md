# CBinaryReader::ReadAttributes(IMFAttributes *)

- ea: `0x1800504ac`
- end: `0x18005072f`
- name: `?ReadAttributes@CBinaryReader@@QEAAJPEAUIMFAttributes@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(CBinaryReader *__hidden this, IMFAttributes *pAttributes)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180019da4`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180017068`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x1800504ac`
- `0x180050738`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFInitAttributesFromBlob` at `0x18005065a`
- `MFPlat!MFInitAttributesFromBlob` at `0x18005065a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800505cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050676`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800505cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050676`

## string_xrefs

- `0x1800504be`: `CBinaryReader::ReadAttributes`
- `0x180050559`: `CBinaryReader::ReadAttributes`
- `0x180050623`: `CBinaryReader::ReadAttributes`
- `0x1800506cd`: `CBinaryReader::ReadAttributes`

## pseudocode

```c
__int64 __fastcall CBinaryReader::ReadAttributes(CBinaryReader *this, IMFAttributes *pAttributes)
{
  __int64 v4; // rdx
  HRESULT Int32; // ebx
  __int64 *v6; // rcx
  UINT8 *v7; // rdi
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  UINT8 *v11; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v21; // [rsp+60h] [rbp+18h] BYREF
  UINT cbBufSize; // [rsp+68h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "CBinaryReader::ReadAttributes", 860);
  cbBufSize = 0;
  Int32 = CBinaryReader::ReadInt32(this, (int *)&cbBufSize);
  if ( Int32 >= 0 )
  {
    v11 = (UINT8 *)operator new(cbBufSize);
    v7 = v11;
    if ( v11 )
    {
      Int32 = (**(__int64 (__fastcall ***)(CBinaryReader *, void *, _QWORD))this)(this, v11, cbBufSize);
      if ( Int32 >= 0 )
      {
        Int32 = MFInitAttributesFromBlob(pAttributes, v7, cbBufSize);
        if ( Int32 < 0 )
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != Int32 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CBinaryReader::ReadAttributes", 880, Int32);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v10 = 43;
            goto LABEL_36;
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
          if ( *((_DWORD *)v15 + 499) != Int32 )
            CallStackContext::TraceFailure(v15, "CBinaryReader::ReadAttributes", 878, Int32);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 42;
          goto LABEL_36;
        }
      }
    }
    else
    {
      Int32 = -2147024882;
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = 0;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
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
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v9 + 499) != Int32 )
        CallStackContext::TraceFailure(v9, "CBinaryReader::ReadAttributes", 869, Int32);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 41;
LABEL_36:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, this, Int32);
    }
  }
  operator delete(v7);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)Int32;
}

```

## disassembly

```asm
0x1800504ac  mov     [rsp+arg_0], rbx
0x1800504b1  push    rbp
0x1800504b2  push    rsi
0x1800504b3  push    rdi
0x1800504b4  sub     rsp, 30h
0x1800504b8  mov     rbp, rdx
0x1800504bb  mov     rsi, rcx
0x1800504be  lea     rdx, aCbinaryreaderR_0; "CBinaryReader::ReadAttributes"
0x1800504c5  mov     r8d, 35Ch; int
0x1800504cb  lea     rcx, [rsp+48h+arg_10]; this
0x1800504d0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800504d5  lea     rdx, [rsp+48h+cbBufSize]; int *
0x1800504da  mov     [rsp+48h+cbBufSize], 0
0x1800504e2  mov     rcx, rsi; this
0x1800504e5  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1800504ea  mov     ebx, eax
0x1800504ec  test    eax, eax
0x1800504ee  jns     loc_180050585
0x1800504f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800504fb  xor     edi, edi
0x1800504fd  test    rcx, rcx
0x180050500  jnz     short loc_180050543
0x180050502  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050508  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005050f  mov     rcx, rax
0x180050512  test    rax, rax
0x180050515  jz      short loc_180050535
0x180050517  mov     rax, [rax]
0x18005051a  mov     edx, 7F0h
0x18005051f  mov     rax, [rax+8]
0x180050523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050528  test    eax, eax
0x18005052a  jz      short loc_180050535
0x18005052c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050533  jmp     short loc_180050543
0x180050535  lea     rcx, qword_180069A90; this
0x18005053c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050543  cmp     [rcx+8], dil
0x180050547  jz      short loc_18005056E
0x180050549  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005054e  cmp     [rax+7CCh], ebx
0x180050554  jz      short loc_18005056E
0x180050556  mov     r9d, ebx; int
0x180050559  lea     rdx, aCbinaryreaderR_0; "CBinaryReader::ReadAttributes"
0x180050560  mov     r8d, 365h; int
0x180050566  mov     rcx, rax; this
0x180050569  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005056e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050573  cmp     al, 1
0x180050575  jb      loc_18005070E
0x18005057b  mov     edx, 29h ; ')'
0x180050580  jmp     loc_1800506F0
0x180050585  mov     ecx, [rsp+48h+cbBufSize]; Size
0x180050589  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005058e  mov     rdi, rax
0x180050591  test    rax, rax
0x180050594  jnz     short loc_1800505A0
0x180050596  mov     ebx, 8007000Eh
0x18005059b  jmp     loc_18005070E
0x1800505a0  mov     rax, [rsi]
0x1800505a3  mov     rdx, rdi
0x1800505a6  mov     r8d, [rsp+48h+cbBufSize]
0x1800505ab  mov     rcx, rsi
0x1800505ae  mov     rax, [rax]
0x1800505b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505b6  mov     ebx, eax
0x1800505b8  test    eax, eax
0x1800505ba  jns     loc_18005064F
0x1800505c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800505c7  test    rcx, rcx
0x1800505ca  jnz     short loc_18005060D
0x1800505cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800505d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800505d9  mov     rcx, rax
0x1800505dc  test    rax, rax
0x1800505df  jz      short loc_1800505FF
0x1800505e1  mov     rax, [rax]
0x1800505e4  mov     edx, 7F0h
0x1800505e9  mov     rax, [rax+8]
0x1800505ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505f2  test    eax, eax
0x1800505f4  jz      short loc_1800505FF
0x1800505f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800505fd  jmp     short loc_18005060D
0x1800505ff  lea     rcx, qword_180069A90; this
0x180050606  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005060d  cmp     byte ptr [rcx+8], 0
0x180050611  jz      short loc_180050638
0x180050613  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050618  cmp     [rax+7CCh], ebx
0x18005061e  jz      short loc_180050638
0x180050620  mov     r9d, ebx; int
0x180050623  lea     rdx, aCbinaryreaderR_0; "CBinaryReader::ReadAttributes"
0x18005062a  mov     r8d, 36Eh; int
0x180050630  mov     rcx, rax; this
0x180050633  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050638  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005063d  cmp     al, 1
0x18005063f  jb      loc_18005070E
0x180050645  mov     edx, 2Ah ; '*'
0x18005064a  jmp     loc_1800506F0
0x18005064f  mov     r8d, [rsp+48h+cbBufSize]; cbBufSize
0x180050654  mov     rdx, rdi; pBuf
0x180050657  mov     rcx, rbp; pAttributes
0x18005065a  call    cs:__imp_MFInitAttributesFromBlob
0x180050660  mov     ebx, eax
0x180050662  test    eax, eax
0x180050664  jns     loc_18005070E
0x18005066a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050671  test    rcx, rcx
0x180050674  jnz     short loc_1800506B7
0x180050676  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005067c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050683  mov     rcx, rax
0x180050686  test    rax, rax
0x180050689  jz      short loc_1800506A9
0x18005068b  mov     rax, [rax]
0x18005068e  mov     edx, 7F0h
0x180050693  mov     rax, [rax+8]
0x180050697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005069c  test    eax, eax
0x18005069e  jz      short loc_1800506A9
0x1800506a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800506a7  jmp     short loc_1800506B7
0x1800506a9  lea     rcx, qword_180069A90; this
0x1800506b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800506b7  cmp     byte ptr [rcx+8], 0
0x1800506bb  jz      short loc_1800506E2
0x1800506bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800506c2  cmp     [rax+7CCh], ebx
0x1800506c8  jz      short loc_1800506E2
0x1800506ca  mov     r9d, ebx; int
0x1800506cd  lea     rdx, aCbinaryreaderR_0; "CBinaryReader::ReadAttributes"
0x1800506d4  mov     r8d, 370h; int
0x1800506da  mov     rcx, rax; this
0x1800506dd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800506e2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800506e7  cmp     al, 1
0x1800506e9  jb      short loc_18005070E
0x1800506eb  mov     edx, 2Bh ; '+'
0x1800506f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800506f7  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x1800506fe  mov     r9, rsi
0x180050701  mov     [rsp+48h+var_28], ebx
0x180050705  mov     rcx, [rcx+10h]
0x180050709  call    WPP_SF_qd
0x18005070e  mov     rcx, rdi; Block
0x180050711  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050716  lea     rcx, [rsp+48h+arg_10]; this
0x18005071b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050720  mov     eax, ebx
0x180050722  mov     rbx, [rsp+48h+arg_0]
0x180050727  add     rsp, 30h
0x18005072b  pop     rdi
0x18005072c  pop     rsi
0x18005072d  pop     rbp
0x18005072e  retn
```
