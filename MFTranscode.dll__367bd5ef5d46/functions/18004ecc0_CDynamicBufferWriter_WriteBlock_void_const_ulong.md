# CDynamicBufferWriter::WriteBlock(void const *,ulong)

- ea: `0x18004ecc0`
- end: `0x18004ef7d`
- name: `?WriteBlock@CDynamicBufferWriter@@UEAAJPEBXK@Z`
- size: `701`
- prototype: `__int64 __fastcall(CDynamicBufferWriter *this, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180017068`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x18004ecc0`
- `0x18004f410`
- `0x1800594bc`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ed4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004edf2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004eec7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ed4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004edf2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004eec7`

## string_xrefs

- `0x18004ecec`: `CDynamicBufferWriter::WriteBlock`
- `0x18004ee49`: `CDynamicBufferWriter::WriteBlock`

## pseudocode

```c
__int64 __fastcall CDynamicBufferWriter::WriteBlock(CDynamicBufferWriter *this, const void *a2, unsigned int a3)
{
  size_t v3; // r12
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // ebp
  unsigned int v10; // ebx
  unsigned int v11; // r14d
  CallStackTracing *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  void *v16; // rax
  __int64 v17; // rdx
  void *v18; // r15
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  void **v22; // rsi
  const void *v23; // rdx
  CallStackTracing *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v27; // [rsp+90h] [rbp+18h] BYREF

  v3 = a3;
  if ( !a3 )
    return 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v27, "CDynamicBufferWriter::WriteBlock", 335);
  v8 = *((_DWORD *)this + 5);
  v9 = v8 + v3;
  if ( v8 + (unsigned int)v3 < v8 )
  {
    v24 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    v10 = -2147024362;
    if ( *((_BYTE *)v24 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v24);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CDynamicBufferWriter::WriteBlock", 335, -2147024362);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_43;
    v15 = 19;
LABEL_42:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      WPP_d7c3bcb185fd354b9c6e619ad1564a2d_Traceguids,
      (char *)this - 520,
      v10);
    goto LABEL_43;
  }
  v10 = 0;
  if ( v9 <= *((_DWORD *)this + 4) )
  {
    v22 = (void **)((char *)this + 8);
  }
  else
  {
    v11 = v9 + 1024;
    if ( v9 + 1024 < v9 )
    {
      v12 = CallStackTracing::s_wpInstance;
      v10 = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = (CallStackTracing *)&qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( *((_DWORD *)v14 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v14, "CDynamicBufferWriter::WriteBlock", 341, -2147024362);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_43;
      v15 = 20;
      goto LABEL_42;
    }
    v16 = operator new(v11);
    v18 = v16;
    if ( !v16 )
    {
      v19 = CallStackTracing::s_wpInstance;
      v10 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = (CallStackTracing *)&qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext(v19);
        if ( *((_DWORD *)v21 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v21, "CDynamicBufferWriter::WriteBlock", 346, -2147024882);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_43;
      v15 = 21;
      goto LABEL_42;
    }
    v22 = (void **)((char *)this + 8);
    v23 = (const void *)*((_QWORD *)this + 1);
    if ( v23 )
      memcpy_0(v16, v23, *((unsigned int *)this + 5));
    operator delete(*v22);
    *v22 = v18;
    *((_DWORD *)this + 4) = v11;
  }
  memcpy_0((char *)*v22 + *((unsigned int *)this + 5), a2, v3);
  *((_DWORD *)this + 5) = v9;
LABEL_43:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v27);
  return v10;
}

```

## disassembly

```asm
0x18004ecc0  push    rbx
0x18004ecc2  push    rbp
0x18004ecc3  push    rsi
0x18004ecc4  push    rdi
0x18004ecc5  push    r12
0x18004ecc7  push    r13
0x18004ecc9  push    r14
0x18004eccb  push    r15
0x18004eccd  sub     rsp, 38h
0x18004ecd1  mov     r12d, r8d
0x18004ecd4  mov     r13, rdx
0x18004ecd7  mov     rdi, rcx
0x18004ecda  test    r8d, r8d
0x18004ecdd  jnz     short loc_18004ECE6
0x18004ecdf  xor     eax, eax
0x18004ece1  jmp     loc_18004EF6C
0x18004ece6  mov     r14d, 14Fh
0x18004ecec  lea     r15, aCdynamicbuffer; "CDynamicBufferWriter::WriteBlock"
0x18004ecf3  mov     r8d, r14d; int
0x18004ecf6  lea     rcx, [rsp+78h+arg_10]; this
0x18004ecfe  mov     rdx, r15; char *
0x18004ed01  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004ed06  lea     rsi, [rdi-208h]
0x18004ed0d  mov     eax, [rsi+21Ch]
0x18004ed13  lea     ebp, [rax+r12]
0x18004ed17  cmp     ebp, eax
0x18004ed19  jb      loc_18004EEBB
0x18004ed1f  xor     ebx, ebx
0x18004ed21  cmp     ebp, [rsi+218h]
0x18004ed27  jbe     loc_18004EE9E
0x18004ed2d  lea     r14d, [rbp+400h]
0x18004ed34  cmp     r14d, ebp
0x18004ed37  jnb     loc_18004EDCD
0x18004ed3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ed44  mov     ebx, 80070216h
0x18004ed49  test    rcx, rcx
0x18004ed4c  jnz     short loc_18004ED8F
0x18004ed4e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ed54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ed5b  mov     rcx, rax
0x18004ed5e  test    rax, rax
0x18004ed61  jz      short loc_18004ED81
0x18004ed63  mov     rax, [rax]
0x18004ed66  mov     edx, 7F0h
0x18004ed6b  mov     rax, [rax+8]
0x18004ed6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed74  test    eax, eax
0x18004ed76  jz      short loc_18004ED81
0x18004ed78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ed7f  jmp     short loc_18004ED8F
0x18004ed81  lea     rcx, qword_180069A90; this
0x18004ed88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ed8f  cmp     byte ptr [rcx+8], 0
0x18004ed93  jz      short loc_18004EDB6
0x18004ed95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ed9a  cmp     [rax+7CCh], ebx
0x18004eda0  jz      short loc_18004EDB6
0x18004eda2  mov     r9d, ebx; int
0x18004eda5  mov     r8d, 155h; int
0x18004edab  mov     rdx, r15; char *
0x18004edae  mov     rcx, rax; this
0x18004edb1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004edb6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004edbb  cmp     al, 1
0x18004edbd  jb      loc_18004EF5D
0x18004edc3  mov     edx, 14h
0x18004edc8  jmp     loc_18004EF3F
0x18004edcd  mov     ecx, r14d; Size
0x18004edd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004edd5  mov     r15, rax
0x18004edd8  test    rax, rax
0x18004eddb  jnz     loc_18004EE75
0x18004ede1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ede8  mov     ebx, 8007000Eh
0x18004eded  test    rcx, rcx
0x18004edf0  jnz     short loc_18004EE33
0x18004edf2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004edf8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004edff  mov     rcx, rax
0x18004ee02  test    rax, rax
0x18004ee05  jz      short loc_18004EE25
0x18004ee07  mov     rax, [rax]
0x18004ee0a  mov     edx, 7F0h
0x18004ee0f  mov     rax, [rax+8]
0x18004ee13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee18  test    eax, eax
0x18004ee1a  jz      short loc_18004EE25
0x18004ee1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ee23  jmp     short loc_18004EE33
0x18004ee25  lea     rcx, qword_180069A90; this
0x18004ee2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ee33  cmp     byte ptr [rcx+8], 0
0x18004ee37  jz      short loc_18004EE5E
0x18004ee39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ee3e  cmp     [rax+7CCh], ebx
0x18004ee44  jz      short loc_18004EE5E
0x18004ee46  mov     r9d, ebx; int
0x18004ee49  lea     rdx, aCdynamicbuffer; "CDynamicBufferWriter::WriteBlock"
0x18004ee50  mov     r8d, 15Ah; int
0x18004ee56  mov     rcx, rax; this
0x18004ee59  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ee5e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ee63  cmp     al, 1
0x18004ee65  jb      loc_18004EF5D
0x18004ee6b  mov     edx, 15h
0x18004ee70  jmp     loc_18004EF3F
0x18004ee75  lea     rsi, [rdi+8]
0x18004ee79  mov     rdx, [rsi]; Src
0x18004ee7c  test    rdx, rdx
0x18004ee7f  jz      short loc_18004EE8D
0x18004ee81  mov     r8d, [rdi+14h]; Size
0x18004ee85  mov     rcx, r15; void *
0x18004ee88  call    memcpy_0
0x18004ee8d  mov     rcx, [rsi]; Block
0x18004ee90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004ee95  mov     [rsi], r15
0x18004ee98  mov     [rdi+10h], r14d
0x18004ee9c  jmp     short loc_18004EEA2
0x18004ee9e  lea     rsi, [rdi+8]
0x18004eea2  mov     ecx, [rdi+14h]
0x18004eea5  mov     r8, r12; Size
0x18004eea8  add     rcx, [rsi]; void *
0x18004eeab  mov     rdx, r13; Src
0x18004eeae  call    memcpy_0
0x18004eeb3  mov     [rdi+14h], ebp
0x18004eeb6  jmp     loc_18004EF5D
0x18004eebb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004eec2  test    rcx, rcx
0x18004eec5  jnz     short loc_18004EF08
0x18004eec7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004eecd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004eed4  mov     rcx, rax
0x18004eed7  test    rax, rax
0x18004eeda  jz      short loc_18004EEFA
0x18004eedc  mov     rax, [rax]
0x18004eedf  mov     edx, 7F0h
0x18004eee4  mov     rax, [rax+8]
0x18004eee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eeed  test    eax, eax
0x18004eeef  jz      short loc_18004EEFA
0x18004eef1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004eef8  jmp     short loc_18004EF08
0x18004eefa  lea     rcx, qword_180069A90; this
0x18004ef01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ef08  cmp     byte ptr [rcx+8], 0
0x18004ef0c  mov     ebx, 80070216h
0x18004ef11  jz      short loc_18004EF31
0x18004ef13  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ef18  cmp     [rax+7CCh], ebx
0x18004ef1e  jz      short loc_18004EF31
0x18004ef20  mov     r9d, ebx; int
0x18004ef23  mov     r8d, r14d; int
0x18004ef26  mov     rdx, r15; char *
0x18004ef29  mov     rcx, rax; this
0x18004ef2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ef31  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ef36  cmp     al, 1
0x18004ef38  jb      short loc_18004EF5D
0x18004ef3a  mov     edx, 13h
0x18004ef3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef46  lea     r8, WPP_d7c3bcb185fd354b9c6e619ad1564a2d_Traceguids
0x18004ef4d  mov     r9, rsi
0x18004ef50  mov     [rsp+78h+var_58], ebx
0x18004ef54  mov     rcx, [rcx+10h]
0x18004ef58  call    WPP_SF_qd
0x18004ef5d  lea     rcx, [rsp+78h+arg_10]; this
0x18004ef65  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004ef6a  mov     eax, ebx
0x18004ef6c  add     rsp, 38h
0x18004ef70  pop     r15
0x18004ef72  pop     r14
0x18004ef74  pop     r13
0x18004ef76  pop     r12
0x18004ef78  pop     rdi
0x18004ef79  pop     rsi
0x18004ef7a  pop     rbp
0x18004ef7b  pop     rbx
0x18004ef7c  retn
```
