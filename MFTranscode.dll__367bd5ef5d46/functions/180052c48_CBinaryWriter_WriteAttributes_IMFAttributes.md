# CBinaryWriter::WriteAttributes(IMFAttributes *)

- ea: `0x180052c48`
- end: `0x180052f70`
- name: `?WriteAttributes@CBinaryWriter@@QEAAJPEAUIMFAttributes@@@Z`
- size: `808`
- prototype: `__int64 __fastcall(CBinaryWriter *__hidden this, IMFAttributes *pAttributes)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18001b9ec`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180017068`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180052c48`
- `0x180052f78`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetAttributesAsBlob` at `0x180052d4d`
- `MFPlat!MFGetAttributesAsBlob` at `0x180052d4d`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180052c8a`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180052c8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052ca8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052d69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052e0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052eb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052ca8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052d69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052e0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052eb5`

## string_xrefs

- `0x180052c5d`: `CBinaryWriter::WriteAttributes`

## pseudocode

```c
__int64 __fastcall CBinaryWriter::WriteAttributes(CBinaryWriter *this, IMFAttributes *pAttributes)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 *v6; // rcx
  UINT8 *v7; // rsi
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
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v25; // [rsp+60h] [rbp+18h] BYREF
  UINT32 pcbBufSize; // [rsp+68h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v25, "CBinaryWriter::WriteAttributes", 145);
  pcbBufSize = 0;
  v5 = MFGetAttributesAsBlobSize(pAttributes, &pcbBufSize);
  if ( v5 >= 0 )
  {
    v11 = (UINT8 *)operator new(pcbBufSize);
    v7 = v11;
    if ( v11 )
    {
      v5 = MFGetAttributesAsBlob(pAttributes, v11, pcbBufSize);
      if ( v5 >= 0 )
      {
        v5 = CBinaryWriter::WriteBool(this, pcbBufSize);
        if ( v5 >= 0 )
        {
          v5 = (**(__int64 (__fastcall ***)(CBinaryWriter *, void *, _QWORD))this)(this, v7, pcbBufSize);
          if ( v5 < 0 )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
              CallStackTracing::s_wpInstance = v22;
              if ( v22
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
              {
                v21 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v21 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CBinaryWriter::WriteAttributes", 167, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v10 = 22;
              goto LABEL_47;
            }
          }
        }
        else
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
            v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)v19 + 499) != v5 )
              CallStackContext::TraceFailure(v19, "CBinaryWriter::WriteAttributes", 165, v5);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v10 = 21;
            goto LABEL_47;
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
          if ( *((_DWORD *)v15 + 499) != v5 )
            CallStackContext::TraceFailure(v15, "CBinaryWriter::WriteAttributes", 163, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 20;
          goto LABEL_47;
        }
      }
    }
    else
    {
      v5 = -2147024882;
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
      if ( *((_DWORD *)v9 + 499) != v5 )
        CallStackContext::TraceFailure(v9, "CBinaryWriter::WriteAttributes", 154, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 19;
LABEL_47:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, this, v5);
    }
  }
  operator delete(v7);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180052c48  mov     [rsp+arg_0], rbx
0x180052c4d  mov     [rsp+arg_8], rbp
0x180052c52  push    rsi
0x180052c53  push    rdi
0x180052c54  push    r15
0x180052c56  sub     rsp, 30h
0x180052c5a  mov     rbp, rdx
0x180052c5d  lea     r15, aCbinarywriterW_0; "CBinaryWriter::WriteAttributes"
0x180052c64  mov     rdi, rcx
0x180052c67  mov     rdx, r15; char *
0x180052c6a  mov     r8d, 91h; int
0x180052c70  lea     rcx, [rsp+48h+arg_10]; this
0x180052c75  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052c7a  lea     rdx, [rsp+48h+pcbBufSize]; pcbBufSize
0x180052c7f  mov     [rsp+48h+pcbBufSize], 0
0x180052c87  mov     rcx, rbp; pAttributes
0x180052c8a  call    cs:__imp_MFGetAttributesAsBlobSize
0x180052c90  mov     ebx, eax
0x180052c92  test    eax, eax
0x180052c94  jns     loc_180052D27
0x180052c9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ca1  xor     esi, esi
0x180052ca3  test    rcx, rcx
0x180052ca6  jnz     short loc_180052CE9
0x180052ca8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052cae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052cb5  mov     rcx, rax
0x180052cb8  test    rax, rax
0x180052cbb  jz      short loc_180052CDB
0x180052cbd  mov     rax, [rax]
0x180052cc0  mov     edx, 7F0h
0x180052cc5  mov     rax, [rax+8]
0x180052cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cce  test    eax, eax
0x180052cd0  jz      short loc_180052CDB
0x180052cd2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052cd9  jmp     short loc_180052CE9
0x180052cdb  lea     rcx, qword_180069A90; this
0x180052ce2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ce9  cmp     [rcx+8], sil
0x180052ced  jz      short loc_180052D10
0x180052cef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052cf4  cmp     [rax+7CCh], ebx
0x180052cfa  jz      short loc_180052D10
0x180052cfc  mov     r9d, ebx; int
0x180052cff  mov     r8d, 9Ah; int
0x180052d05  mov     rdx, r15; char *
0x180052d08  mov     rcx, rax; this
0x180052d0b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052d10  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180052d15  cmp     al, 1
0x180052d17  jb      loc_180052F49
0x180052d1d  mov     edx, 13h
0x180052d22  jmp     loc_180052F2B
0x180052d27  mov     ecx, [rsp+48h+pcbBufSize]; Size
0x180052d2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052d30  mov     rsi, rax
0x180052d33  test    rax, rax
0x180052d36  jnz     short loc_180052D42
0x180052d38  mov     ebx, 8007000Eh
0x180052d3d  jmp     loc_180052F49
0x180052d42  mov     r8d, [rsp+48h+pcbBufSize]; cbBufSize
0x180052d47  mov     rdx, rsi; pBuf
0x180052d4a  mov     rcx, rbp; pAttributes
0x180052d4d  call    cs:__imp_MFGetAttributesAsBlob
0x180052d53  mov     ebx, eax
0x180052d55  test    eax, eax
0x180052d57  jns     loc_180052DE8
0x180052d5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d64  test    rcx, rcx
0x180052d67  jnz     short loc_180052DAA
0x180052d69  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052d6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d76  mov     rcx, rax
0x180052d79  test    rax, rax
0x180052d7c  jz      short loc_180052D9C
0x180052d7e  mov     rax, [rax]
0x180052d81  mov     edx, 7F0h
0x180052d86  mov     rax, [rax+8]
0x180052d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d8f  test    eax, eax
0x180052d91  jz      short loc_180052D9C
0x180052d93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d9a  jmp     short loc_180052DAA
0x180052d9c  lea     rcx, qword_180069A90; this
0x180052da3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052daa  cmp     byte ptr [rcx+8], 0
0x180052dae  jz      short loc_180052DD1
0x180052db0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052db5  cmp     [rax+7CCh], ebx
0x180052dbb  jz      short loc_180052DD1
0x180052dbd  mov     r9d, ebx; int
0x180052dc0  mov     r8d, 0A3h; int
0x180052dc6  mov     rdx, r15; char *
0x180052dc9  mov     rcx, rax; this
0x180052dcc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052dd1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180052dd6  cmp     al, 1
0x180052dd8  jb      loc_180052F49
0x180052dde  mov     edx, 14h
0x180052de3  jmp     loc_180052F2B
0x180052de8  mov     edx, [rsp+48h+pcbBufSize]; int
0x180052dec  mov     rcx, rdi; this
0x180052def  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180052df4  mov     ebx, eax
0x180052df6  test    eax, eax
0x180052df8  jns     loc_180052E89
0x180052dfe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e05  test    rcx, rcx
0x180052e08  jnz     short loc_180052E4B
0x180052e0a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052e10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e17  mov     rcx, rax
0x180052e1a  test    rax, rax
0x180052e1d  jz      short loc_180052E3D
0x180052e1f  mov     rax, [rax]
0x180052e22  mov     edx, 7F0h
0x180052e27  mov     rax, [rax+8]
0x180052e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e30  test    eax, eax
0x180052e32  jz      short loc_180052E3D
0x180052e34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e3b  jmp     short loc_180052E4B
0x180052e3d  lea     rcx, qword_180069A90; this
0x180052e44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e4b  cmp     byte ptr [rcx+8], 0
0x180052e4f  jz      short loc_180052E72
0x180052e51  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052e56  cmp     [rax+7CCh], ebx
0x180052e5c  jz      short loc_180052E72
0x180052e5e  mov     r9d, ebx; int
0x180052e61  mov     r8d, 0A5h; int
0x180052e67  mov     rdx, r15; char *
0x180052e6a  mov     rcx, rax; this
0x180052e6d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052e72  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180052e77  cmp     al, 1
0x180052e79  jb      loc_180052F49
0x180052e7f  mov     edx, 15h
0x180052e84  jmp     loc_180052F2B
0x180052e89  mov     rax, [rdi]
0x180052e8c  mov     rdx, rsi
0x180052e8f  mov     r8d, [rsp+48h+pcbBufSize]
0x180052e94  mov     rcx, rdi
0x180052e97  mov     rax, [rax]
0x180052e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e9f  mov     ebx, eax
0x180052ea1  test    eax, eax
0x180052ea3  jns     loc_180052F49
0x180052ea9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052eb0  test    rcx, rcx
0x180052eb3  jnz     short loc_180052EF6
0x180052eb5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052ebb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ec2  mov     rcx, rax
0x180052ec5  test    rax, rax
0x180052ec8  jz      short loc_180052EE8
0x180052eca  mov     rax, [rax]
0x180052ecd  mov     edx, 7F0h
0x180052ed2  mov     rax, [rax+8]
0x180052ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052edb  test    eax, eax
0x180052edd  jz      short loc_180052EE8
0x180052edf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ee6  jmp     short loc_180052EF6
0x180052ee8  lea     rcx, qword_180069A90; this
0x180052eef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ef6  cmp     byte ptr [rcx+8], 0
0x180052efa  jz      short loc_180052F1D
0x180052efc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052f01  cmp     [rax+7CCh], ebx
0x180052f07  jz      short loc_180052F1D
0x180052f09  mov     r9d, ebx; int
0x180052f0c  mov     r8d, 0A7h; int
0x180052f12  mov     rdx, r15; char *
0x180052f15  mov     rcx, rax; this
0x180052f18  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052f1d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180052f22  cmp     al, 1
0x180052f24  jb      short loc_180052F49
0x180052f26  mov     edx, 16h
0x180052f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052f32  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x180052f39  mov     r9, rdi
0x180052f3c  mov     [rsp+48h+var_28], ebx
0x180052f40  mov     rcx, [rcx+10h]
0x180052f44  call    WPP_SF_qd
0x180052f49  mov     rcx, rsi; Block
0x180052f4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052f51  lea     rcx, [rsp+48h+arg_10]; this
0x180052f56  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180052f5b  mov     rbp, [rsp+48h+arg_8]
0x180052f60  mov     eax, ebx
0x180052f62  mov     rbx, [rsp+48h+arg_0]
0x180052f67  add     rsp, 30h
0x180052f6b  pop     r15
0x180052f6d  pop     rdi
0x180052f6e  pop     rsi
0x180052f6f  retn
```
