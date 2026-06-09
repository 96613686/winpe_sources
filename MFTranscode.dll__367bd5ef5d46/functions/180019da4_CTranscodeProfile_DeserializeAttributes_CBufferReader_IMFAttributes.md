# CTranscodeProfile::DeserializeAttributes(CBufferReader &,IMFAttributes * *)

- ea: `0x180019da4`
- end: `0x18001a0e2`
- name: `?DeserializeAttributes@CTranscodeProfile@@IEAAJAEAVCBufferReader@@PEAPEAUIMFAttributes@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(CTranscodeProfile *__hidden this, struct CBufferReader *, struct IMFAttributes **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001aaf0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180019da4`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x1800504ac`
- `0x180050738`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019e02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019ecc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019f7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a01f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019e02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019ecc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019f7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a01f`
- `MFPlat!MFCreateAttributes` at `0x180019f5e`
- `MFPlat!MFCreateAttributes` at `0x180019f5e`

## string_xrefs

- `0x180019dba`: `CTranscodeProfile::DeserializeAttributes`

## pseudocode

```c
__int64 __fastcall CTranscodeProfile::DeserializeAttributes(
        CTranscodeProfile *this,
        struct CBufferReader *a2,
        struct IMFAttributes **a3)
{
  __int64 v6; // rdx
  __int64 *v7; // rcx
  HRESULT Attributes; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
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
  char v25; // [rsp+60h] [rbp+30h] BYREF
  int v26; // [rsp+70h] [rbp+40h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+78h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v25, "CTranscodeProfile::DeserializeAttributes", 545);
  v26 = 0;
  ppMFAttributes = 0;
  if ( a3 )
  {
    *a3 = 0;
    Attributes = CBinaryReader::ReadInt32((struct CBufferReader *)((char *)a2 + 520), &v26);
    if ( Attributes >= 0 )
    {
      if ( v26 )
      {
        Attributes = MFCreateAttributes(&ppMFAttributes, 5u);
        if ( Attributes >= 0 )
        {
          Attributes = CBinaryReader::ReadAttributes((struct CBufferReader *)((char *)a2 + 520), ppMFAttributes);
          if ( Attributes >= 0 )
          {
            *a3 = ppMFAttributes;
            ppMFAttributes = 0;
          }
          else
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
              if ( *((_DWORD *)ThreadRelativeContext + 499) != Attributes )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CTranscodeProfile::DeserializeAttributes",
                  561,
                  Attributes);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v11 = 69;
              goto LABEL_12;
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
            if ( *((_DWORD *)v19 + 499) != Attributes )
              CallStackContext::TraceFailure(v19, "CTranscodeProfile::DeserializeAttributes", 560, Attributes);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 68;
            goto LABEL_12;
          }
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
        if ( *((_DWORD *)v15 + 499) != Attributes )
          CallStackContext::TraceFailure(v15, "CTranscodeProfile::DeserializeAttributes", 554, Attributes);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 67;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    Attributes = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CTranscodeProfile::DeserializeAttributes", 551, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 66;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        WPP_60c454de96f7327ebad2115a8fee1984_Traceguids,
        this,
        Attributes);
    }
  }
  if ( ppMFAttributes )
  {
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
    ppMFAttributes = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
  return (unsigned int)Attributes;
}

```

## disassembly

```asm
0x180019da4  mov     [rsp-28h+arg_8], rbx
0x180019da9  push    rbp
0x180019daa  push    rsi
0x180019dab  push    rdi
0x180019dac  push    r12
0x180019dae  push    r14
0x180019db0  mov     rbp, rsp
0x180019db3  sub     rsp, 30h
0x180019db7  mov     rdi, r8
0x180019dba  lea     r12, aCtranscodeprof_10; "CTranscodeProfile::DeserializeAttribute"...
0x180019dc1  mov     rsi, rdx
0x180019dc4  mov     r14, rcx
0x180019dc7  mov     rdx, r12; char *
0x180019dca  lea     rcx, [rbp+arg_0]; this
0x180019dce  mov     r8d, 221h; int
0x180019dd4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180019dd9  mov     [rbp+arg_10], 0
0x180019de0  mov     [rbp+ppMFAttributes], 0
0x180019de8  test    rdi, rdi
0x180019deb  jnz     loc_180019E9F
0x180019df1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019df8  mov     ebx, 80004003h
0x180019dfd  test    rcx, rcx
0x180019e00  jnz     short loc_180019E43
0x180019e02  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019e08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019e0f  mov     rcx, rax
0x180019e12  test    rax, rax
0x180019e15  jz      short loc_180019E35
0x180019e17  mov     rax, [rax]
0x180019e1a  mov     edx, 7F0h
0x180019e1f  mov     rax, [rax+8]
0x180019e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e28  test    eax, eax
0x180019e2a  jz      short loc_180019E35
0x180019e2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019e33  jmp     short loc_180019E43
0x180019e35  lea     rcx, qword_180069A90; this
0x180019e3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019e43  cmp     byte ptr [rcx+8], 0
0x180019e47  jz      short loc_180019E6A
0x180019e49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019e4e  cmp     [rax+7CCh], ebx
0x180019e54  jz      short loc_180019E6A
0x180019e56  mov     r9d, ebx; int
0x180019e59  mov     r8d, 227h; int
0x180019e5f  mov     rdx, r12; char *
0x180019e62  mov     rcx, rax; this
0x180019e65  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019e6a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019e6f  cmp     al, 1
0x180019e71  jb      loc_18001A0A9
0x180019e77  mov     edx, 42h ; 'B'
0x180019e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e83  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180019e8a  mov     r9, r14
0x180019e8d  mov     [rsp+30h+var_10], ebx
0x180019e91  mov     rcx, [rcx+10h]
0x180019e95  call    WPP_SF_qd
0x180019e9a  jmp     loc_18001A0A9
0x180019e9f  lea     rdx, [rbp+arg_10]; int *
0x180019ea3  mov     qword ptr [rdi], 0
0x180019eaa  lea     rcx, [rsi+208h]; this
0x180019eb1  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x180019eb6  mov     ebx, eax
0x180019eb8  test    eax, eax
0x180019eba  jns     loc_180019F4B
0x180019ec0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019ec7  test    rcx, rcx
0x180019eca  jnz     short loc_180019F0D
0x180019ecc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019ed2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019ed9  mov     rcx, rax
0x180019edc  test    rax, rax
0x180019edf  jz      short loc_180019EFF
0x180019ee1  mov     rax, [rax]
0x180019ee4  mov     edx, 7F0h
0x180019ee9  mov     rax, [rax+8]
0x180019eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ef2  test    eax, eax
0x180019ef4  jz      short loc_180019EFF
0x180019ef6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019efd  jmp     short loc_180019F0D
0x180019eff  lea     rcx, qword_180069A90; this
0x180019f06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019f0d  cmp     byte ptr [rcx+8], 0
0x180019f11  jz      short loc_180019F34
0x180019f13  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019f18  cmp     [rax+7CCh], ebx
0x180019f1e  jz      short loc_180019F34
0x180019f20  mov     r9d, ebx; int
0x180019f23  mov     r8d, 22Ah; int
0x180019f29  mov     rdx, r12; char *
0x180019f2c  mov     rcx, rax; this
0x180019f2f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019f34  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019f39  cmp     al, 1
0x180019f3b  jb      loc_18001A0A9
0x180019f41  mov     edx, 43h ; 'C'
0x180019f46  jmp     loc_180019E7C
0x180019f4b  cmp     [rbp+arg_10], 0
0x180019f4f  jz      loc_18001A0A9
0x180019f55  mov     edx, 5; cInitialSize
0x180019f5a  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180019f5e  call    cs:__imp_MFCreateAttributes
0x180019f64  mov     ebx, eax
0x180019f66  test    eax, eax
0x180019f68  jns     loc_180019FF9
0x180019f6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019f75  test    rcx, rcx
0x180019f78  jnz     short loc_180019FBB
0x180019f7a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019f80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019f87  mov     rcx, rax
0x180019f8a  test    rax, rax
0x180019f8d  jz      short loc_180019FAD
0x180019f8f  mov     rax, [rax]
0x180019f92  mov     edx, 7F0h
0x180019f97  mov     rax, [rax+8]
0x180019f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fa0  test    eax, eax
0x180019fa2  jz      short loc_180019FAD
0x180019fa4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019fab  jmp     short loc_180019FBB
0x180019fad  lea     rcx, qword_180069A90; this
0x180019fb4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019fbb  cmp     byte ptr [rcx+8], 0
0x180019fbf  jz      short loc_180019FE2
0x180019fc1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019fc6  cmp     [rax+7CCh], ebx
0x180019fcc  jz      short loc_180019FE2
0x180019fce  mov     r9d, ebx; int
0x180019fd1  mov     r8d, 230h; int
0x180019fd7  mov     rdx, r12; char *
0x180019fda  mov     rcx, rax; this
0x180019fdd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019fe2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019fe7  cmp     al, 1
0x180019fe9  jb      loc_18001A0A9
0x180019fef  mov     edx, 44h ; 'D'
0x180019ff4  jmp     loc_180019E7C
0x180019ff9  mov     rdx, [rbp+ppMFAttributes]; pAttributes
0x180019ffd  lea     rcx, [rsi+208h]; this
0x18001a004  call    ?ReadAttributes@CBinaryReader@@QEAAJPEAUIMFAttributes@@@Z; CBinaryReader::ReadAttributes(IMFAttributes *)
0x18001a009  mov     ebx, eax
0x18001a00b  test    eax, eax
0x18001a00d  jns     loc_18001A09A
0x18001a013  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a01a  test    rcx, rcx
0x18001a01d  jnz     short loc_18001A060
0x18001a01f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a025  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a02c  mov     rcx, rax
0x18001a02f  test    rax, rax
0x18001a032  jz      short loc_18001A052
0x18001a034  mov     rax, [rax]
0x18001a037  mov     edx, 7F0h
0x18001a03c  mov     rax, [rax+8]
0x18001a040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a045  test    eax, eax
0x18001a047  jz      short loc_18001A052
0x18001a049  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a050  jmp     short loc_18001A060
0x18001a052  lea     rcx, qword_180069A90; this
0x18001a059  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a060  cmp     byte ptr [rcx+8], 0
0x18001a064  jz      short loc_18001A087
0x18001a066  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a06b  cmp     [rax+7CCh], ebx
0x18001a071  jz      short loc_18001A087
0x18001a073  mov     r9d, ebx; int
0x18001a076  mov     r8d, 231h; int
0x18001a07c  mov     rdx, r12; char *
0x18001a07f  mov     rcx, rax; this
0x18001a082  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a087  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a08c  cmp     al, 1
0x18001a08e  jb      short loc_18001A0A9
0x18001a090  mov     edx, 45h ; 'E'
0x18001a095  jmp     loc_180019E7C
0x18001a09a  mov     rax, [rbp+ppMFAttributes]
0x18001a09e  mov     [rdi], rax
0x18001a0a1  mov     [rbp+ppMFAttributes], 0
0x18001a0a9  mov     rcx, [rbp+ppMFAttributes]
0x18001a0ad  test    rcx, rcx
0x18001a0b0  jz      short loc_18001A0C6
0x18001a0b2  mov     rax, [rcx]
0x18001a0b5  mov     rax, [rax+10h]
0x18001a0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0be  mov     [rbp+ppMFAttributes], 0
0x18001a0c6  lea     rcx, [rbp+arg_0]; this
0x18001a0ca  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001a0cf  mov     eax, ebx
0x18001a0d1  mov     rbx, [rsp+30h+arg_8]
0x18001a0d6  add     rsp, 30h
0x18001a0da  pop     r14
0x18001a0dc  pop     r12
0x18001a0de  pop     rdi
0x18001a0df  pop     rsi
0x18001a0e0  pop     rbp
0x18001a0e1  retn
```
