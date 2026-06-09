# CWICRawMetadataBlockReaderBase::GetReaderByIndex(uint,IWICMetadataReader * *)

- ea: `0x18009b4b0`
- end: `0x18009b6e4`
- name: `?GetReaderByIndex@CWICRawMetadataBlockReaderBase@@UEAAJIPEAPEAUIWICMetadataReader@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *__hidden this, unsigned int, struct IWICMetadataReader **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18009b490`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x18009b4b0`
- `0x18009b9e4`
- `0x18009c41c`
- `0x18009cd18`
- `0x18009e190`
- `0x18009e8b8`
- `0x1800a34f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b6a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b6a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b518`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b518`

## string_xrefs

- `0x18009b4d0`: `CWICRawMetadataBlockReaderBase::GetReaderByIndex`

## pseudocode

```c
__int64 __fastcall CWICRawMetadataBlockReaderBase::GetReaderByIndex(
        CWICRawMetadataBlockReaderBase *this,
        unsigned int a2,
        struct IWICMetadataReader **a3)
{
  __int64 v4; // rbp
  void ***v6; // rcx
  unsigned int v7; // edi
  struct CallStackContext *ThreadRelativeContext; // rax
  int v9; // r8d
  int MetadataReaders; // eax
  void ***v11; // rcx
  char *v12; // rdi
  struct IWICMetadataReader *v13; // rax
  void ***v14; // rcx
  _QWORD v16[2]; // [rsp+30h] [rbp-38h] BYREF
  int v17; // [rsp+40h] [rbp-28h]
  char v18; // [rsp+70h] [rbp+8h] BYREF

  v4 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v18,
    "CWICRawMetadataBlockReaderBase::GetReaderByIndex",
    194);
  v16[0] = "CWICRawMetadataBlockReaderBase::GetReaderByIndex";
  v17 = 15;
  v16[1] = 0;
  OutputMsg(0, 0xFu, "=>%s", "CWICRawMetadataBlockReaderBase::GetReaderByIndex");
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a3 )
  {
    *a3 = 0;
    MetadataReaders = CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders(this);
    v7 = MetadataReaders;
    if ( MetadataReaders >= 0 )
    {
      if ( (unsigned int)v4 >= *((_DWORD *)this + 24) || (unsigned int)v4 >= 2 )
      {
        v7 = -2147024809;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids,
            0,
            -2147024809);
        }
        v14 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
          {
            v9 = 204;
            goto LABEL_29;
          }
        }
      }
      else
      {
        v12 = (char *)this + 8 * v4;
        Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(v12 + 80);
        v13 = (struct IWICMetadataReader *)*((_QWORD *)v12 + 10);
        v7 = 0;
        *a3 = v13;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids,
          0,
          MetadataReaders);
      }
      v11 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
        {
          v9 = 200;
          goto LABEL_29;
        }
      }
    }
  }
  else
  {
    v6 = (void ***)CallStackTracing::s_wpInstance;
    v7 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
      {
        v9 = 197;
LABEL_29:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWICRawMetadataBlockReaderBase::GetReaderByIndex",
          v9,
          v7);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v16);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
  return v7;
}

```

## disassembly

```asm
0x18009b4b0  mov     rax, rsp
0x18009b4b3  mov     [rax+10h], rbx
0x18009b4b7  mov     [rax+18h], rbp
0x18009b4bb  mov     [rax+20h], rsi
0x18009b4bf  push    rdi
0x18009b4c0  push    r12
0x18009b4c2  push    r14
0x18009b4c4  sub     rsp, 50h
0x18009b4c8  mov     r14, r8
0x18009b4cb  mov     ebp, edx
0x18009b4cd  mov     rsi, rcx
0x18009b4d0  lea     r12, aCwicrawmetadat_5; "CWICRawMetadataBlockReaderBase::GetRead"...
0x18009b4d7  mov     rdx, r12; char *
0x18009b4da  lea     rcx, [rax+8]; this
0x18009b4de  mov     r8d, 0C2h; int
0x18009b4e4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009b4e9  mov     edx, 0Fh; unsigned int
0x18009b4ee  mov     [rsp+68h+var_38], r12
0x18009b4f3  mov     r9, r12
0x18009b4f6  mov     [rsp+68h+var_28], edx
0x18009b4fa  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x18009b501  mov     [rsp+68h+var_30], 0
0x18009b50a  xor     ecx, ecx; unsigned int
0x18009b50c  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x18009b511  lea     rbx, [rsi+10h]
0x18009b515  mov     rcx, rbx; lpCriticalSection
0x18009b518  call    cs:__imp_EnterCriticalSection
0x18009b51f  nop     dword ptr [rax+rax+00h]
0x18009b524  test    r14, r14
0x18009b527  jnz     short loc_18009B56E
0x18009b529  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b530  mov     edi, 80004003h
0x18009b535  test    rcx, rcx
0x18009b538  jnz     short loc_18009B548
0x18009b53a  lea     rcx, off_1800E5190; this
0x18009b541  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b548  cmp     byte ptr [rcx+8], 0
0x18009b54c  jz      loc_18009B6A4
0x18009b552  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009b557  cmp     [rax+7CCh], edi
0x18009b55d  jz      loc_18009B6A4
0x18009b563  mov     r8d, 0C5h
0x18009b569  jmp     loc_18009B696
0x18009b56e  mov     rcx, rsi; this
0x18009b571  mov     qword ptr [r14], 0
0x18009b578  call    ?TryCreateMetadataReaders@CWICRawMetadataBlockReaderBase@@AEAAJXZ; CWICRawMetadataBlockReaderBase::TryCreateMetadataReaders(void)
0x18009b57d  mov     edi, eax
0x18009b57f  test    eax, eax
0x18009b581  jns     short loc_18009B5FE
0x18009b583  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b58a  lea     rdx, WPP_GLOBAL_Control
0x18009b591  cmp     rcx, rdx
0x18009b594  jz      short loc_18009B5BE
0x18009b596  test    byte ptr [rcx+1Ch], 1
0x18009b59a  jz      short loc_18009B5BE
0x18009b59c  cmp     byte ptr [rcx+19h], 4
0x18009b5a0  jb      short loc_18009B5BE
0x18009b5a2  mov     rcx, [rcx+10h]
0x18009b5a6  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009b5ad  mov     edx, 11h
0x18009b5b2  mov     [rsp+68h+var_48], eax
0x18009b5b6  xor     r9d, r9d
0x18009b5b9  call    WPP_SF_Dd
0x18009b5be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b5c5  test    rcx, rcx
0x18009b5c8  jnz     short loc_18009B5D8
0x18009b5ca  lea     rcx, off_1800E5190; this
0x18009b5d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b5d8  cmp     byte ptr [rcx+8], 0
0x18009b5dc  jz      loc_18009B6A4
0x18009b5e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009b5e7  cmp     [rax+7CCh], edi
0x18009b5ed  jz      loc_18009B6A4
0x18009b5f3  mov     r8d, 0C8h
0x18009b5f9  jmp     loc_18009B696
0x18009b5fe  cmp     ebp, [rsi+60h]
0x18009b601  jnb     short loc_18009B623
0x18009b603  cmp     ebp, 2
0x18009b606  jnb     short loc_18009B623
0x18009b608  lea     rdi, [rsi+rbp*8]
0x18009b60c  lea     rcx, [rdi+50h]
0x18009b610  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x18009b615  mov     rax, [rdi+50h]
0x18009b619  xor     edi, edi
0x18009b61b  mov     [r14], rax
0x18009b61e  jmp     loc_18009B6A4
0x18009b623  mov     edi, 80070057h
0x18009b628  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b62f  lea     rdx, WPP_GLOBAL_Control
0x18009b636  cmp     rcx, rdx
0x18009b639  jz      short loc_18009B663
0x18009b63b  test    byte ptr [rcx+1Ch], 1
0x18009b63f  jz      short loc_18009B663
0x18009b641  cmp     byte ptr [rcx+19h], 4
0x18009b645  jb      short loc_18009B663
0x18009b647  mov     rcx, [rcx+10h]
0x18009b64b  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009b652  mov     edx, 12h
0x18009b657  mov     [rsp+68h+var_48], edi
0x18009b65b  xor     r9d, r9d
0x18009b65e  call    WPP_SF_Dd
0x18009b663  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b66a  test    rcx, rcx
0x18009b66d  jnz     short loc_18009B67D
0x18009b66f  lea     rcx, off_1800E5190; this
0x18009b676  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b67d  cmp     byte ptr [rcx+8], 0
0x18009b681  jz      short loc_18009B6A4
0x18009b683  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009b688  cmp     [rax+7CCh], edi
0x18009b68e  jz      short loc_18009B6A4
0x18009b690  mov     r8d, 0CCh; int
0x18009b696  mov     r9d, edi; int
0x18009b699  mov     rdx, r12; char *
0x18009b69c  mov     rcx, rax; this
0x18009b69f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009b6a4  mov     rcx, rbx; lpCriticalSection
0x18009b6a7  call    cs:__imp_LeaveCriticalSection
0x18009b6ae  nop     dword ptr [rax+rax+00h]
0x18009b6b3  lea     rcx, [rsp+68h+var_38]; this
0x18009b6b8  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x18009b6bd  lea     rcx, [rsp+68h+arg_0]; this
0x18009b6c2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009b6c7  lea     r11, [rsp+68h+var_18]
0x18009b6cc  mov     eax, edi
0x18009b6ce  mov     rbx, [r11+28h]
0x18009b6d2  mov     rbp, [r11+30h]
0x18009b6d6  mov     rsi, [r11+38h]
0x18009b6da  mov     rsp, r11
0x18009b6dd  pop     r14
0x18009b6df  pop     r12
0x18009b6e1  pop     rdi
0x18009b6e2  retn
```
