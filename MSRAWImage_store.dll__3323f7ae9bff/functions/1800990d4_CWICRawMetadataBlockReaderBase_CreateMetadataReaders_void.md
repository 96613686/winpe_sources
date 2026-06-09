# CWICRawMetadataBlockReaderBase::CreateMetadataReaders(void)

- ea: `0x1800990d4`
- end: `0x1800993cf`
- name: `?CreateMetadataReaders@CWICRawMetadataBlockReaderBase@@IEAAJXZ`
- size: `763`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18009e190`

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x1800989fc`
- `0x1800990d4`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009cd18`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800b4010`

## string_xrefs

- `0x1800990f9`: `CWICRawMetadataBlockReaderBase::CreateMetadataReaders`
- `0x180099380`: `CWICRawMetadataBlockReaderBase::CreateMetadataReaders`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWICRawMetadataBlockReaderBase::CreateMetadataReaders(CWICRawMetadataBlockReaderBase *this)
{
  int v2; // r15d
  __int64 v3; // rdi
  int (__fastcall *v4)(__int64, __int64 *); // rbx
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, GUID *, _QWORD, __int64, __int64, struct IWICMetadataReader **); // rbx
  __int64 v7; // r9
  CallStackTracing *v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v10; // r8d
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, __int64 *, char *); // rbx
  int v13; // r14d
  BOOL v14; // ebx
  __int64 v15; // rsi
  int (__fastcall *v16)(__int64, GUID *, _QWORD, _QWORD, __int64, struct IWICMetadataReader **); // rdi
  CallStackTracing *v17; // rcx
  _QWORD v19[2]; // [rsp+48h] [rbp-20h] BYREF
  int v20; // [rsp+58h] [rbp-10h]
  char v21; // [rsp+B0h] [rbp+48h] BYREF
  char v22; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v23; // [rsp+C0h] [rbp+58h] BYREF
  struct IWICMetadataReader *v24; // [rsp+C8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v22,
    "CWICRawMetadataBlockReaderBase::CreateMetadataReaders",
    253);
  v2 = 0;
  v19[0] = "CWICRawMetadataBlockReaderBase::CreateMetadataReaders";
  v19[1] = 0;
  v20 = 15;
  OutputMsg(0, 0xFu, "=>%s", "CWICRawMetadataBlockReaderBase::CreateMetadataReaders");
  v23 = 0;
  v24 = 0;
  v3 = *((_QWORD *)this + 8);
  v4 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 64LL);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v23);
  if ( v4(v3, &v23) < 0 || !v23 )
    goto LABEL_16;
  v5 = *((_QWORD *)this + 7);
  v6 = *(int (__fastcall **)(__int64, GUID *, _QWORD, __int64, __int64, struct IWICMetadataReader **))(*(_QWORD *)v5 + 224LL);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v24);
  v7 = 4;
  if ( *((_DWORD *)this + 18) != 1 )
    v7 = 0;
  if ( v6(v5, &GUID_MetadataFormatXMP, 0, v7, v23, &v24) >= 0
    && (v2 = CWICRawMetadataBlockReaderBase::AddMetadataReader(this, v24), v2 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids, 0, v2);
    }
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)&off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v2 )
      {
        v10 = 269;
LABEL_31:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWICRawMetadataBlockReaderBase::CreateMetadataReaders",
          v10,
          v2);
      }
    }
  }
  else
  {
LABEL_16:
    v21 = 1;
    v11 = *((_QWORD *)this + 8);
    v12 = *(int (__fastcall **)(__int64, __int64 *, char *))(*(_QWORD *)v11 + 56LL);
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v23);
    if ( v12(v11, &v23, &v21) >= 0 && v23 )
    {
      v13 = 4;
      if ( *((_DWORD *)this + 18) != 1 )
        v13 = 0;
      v14 = v21 != 0;
      v15 = *((_QWORD *)this + 7);
      v16 = *(int (__fastcall **)(__int64, GUID *, _QWORD, _QWORD, __int64, struct IWICMetadataReader **))(*(_QWORD *)v15 + 224LL);
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v24);
      if ( v16(v15, &GUID_MetadataFormatIfd, 0, v14 | (unsigned int)v13, v23, &v24) >= 0 )
      {
        v2 = CWICRawMetadataBlockReaderBase::AddMetadataReader(this, v24);
        if ( v2 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids, 0, v2);
          }
          v17 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v17 = (CallStackTracing *)&off_1800E5190;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v17);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v2 )
            {
              v10 = 285;
              goto LABEL_31;
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v23);
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v19);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800990d4  push    rbp
0x1800990d6  push    rbx
0x1800990d7  push    rsi
0x1800990d8  push    rdi
0x1800990d9  push    r12
0x1800990db  push    r13
0x1800990dd  push    r14
0x1800990df  push    r15
0x1800990e1  mov     rbp, rsp
0x1800990e4  sub     rsp, 68h
0x1800990e8  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x1800990f0  mov     r13, rcx
0x1800990f3  mov     r8d, 0FDh; int
0x1800990f9  lea     r14, aCwicrawmetadat_1; "CWICRawMetadataBlockReaderBase::CreateM"...
0x180099100  mov     rdx, r14; char *
0x180099103  lea     rcx, [rbp+arg_8]; this
0x180099107  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009910c  nop
0x18009910d  xor     r12d, r12d
0x180099110  mov     r15d, r12d
0x180099113  mov     [rbp+var_20], r14
0x180099117  mov     [rbp+var_18], r12
0x18009911b  lea     edx, [r12+0Fh]; unsigned int
0x180099120  mov     [rbp+var_10], edx
0x180099123  mov     r9, r14
0x180099126  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x18009912d  xor     ecx, ecx; unsigned int
0x18009912f  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x180099134  nop
0x180099135  mov     [rbp+arg_10], r12
0x180099139  mov     [rbp+arg_18], r12
0x18009913d  mov     rdi, [r13+40h]
0x180099141  mov     rax, [rdi]
0x180099144  mov     rbx, [rax+40h]
0x180099148  lea     rcx, [rbp+arg_10]
0x18009914c  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x180099151  lea     rdx, [rbp+arg_10]
0x180099155  mov     rcx, rdi
0x180099158  mov     rax, rbx
0x18009915b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099160  lea     esi, [r12+4]
0x180099165  test    eax, eax
0x180099167  js      loc_18009925A
0x18009916d  cmp     [rbp+arg_10], r12
0x180099171  jz      loc_18009925A
0x180099177  mov     rdi, [r13+38h]
0x18009917b  mov     rax, [rdi]
0x18009917e  mov     rbx, [rax+0E0h]
0x180099185  lea     rcx, [rbp+arg_18]
0x180099189  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x18009918e  mov     rdx, [rbp+arg_10]
0x180099192  mov     r9d, esi
0x180099195  cmp     dword ptr [r13+48h], 1
0x18009919a  cmovnz  r9d, r12d
0x18009919e  lea     rax, [rbp+arg_18]
0x1800991a2  mov     [rsp+68h+var_40], rax
0x1800991a7  mov     [rsp+68h+var_48], rdx
0x1800991ac  xor     r8d, r8d
0x1800991af  lea     rdx, GUID_MetadataFormatXMP
0x1800991b6  mov     rcx, rdi
0x1800991b9  mov     rax, rbx
0x1800991bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800991c1  test    eax, eax
0x1800991c3  js      loc_18009925A
0x1800991c9  mov     rdx, [rbp+arg_18]; struct IWICMetadataReader *
0x1800991cd  mov     rcx, r13; this
0x1800991d0  call    ?AddMetadataReader@CWICRawMetadataBlockReaderBase@@IEAAJPEAUIWICMetadataReader@@@Z; CWICRawMetadataBlockReaderBase::AddMetadataReader(IWICMetadataReader *)
0x1800991d5  mov     r15d, eax
0x1800991d8  test    eax, eax
0x1800991da  jns     short loc_18009925A
0x1800991dc  lea     rax, WPP_GLOBAL_Control
0x1800991e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800991ea  cmp     rcx, rax
0x1800991ed  jz      short loc_180099216
0x1800991ef  test    byte ptr [rcx+1Ch], 1
0x1800991f3  jz      short loc_180099216
0x1800991f5  cmp     [rcx+19h], sil
0x1800991f9  jb      short loc_180099216
0x1800991fb  lea     edx, [rsi+14h]
0x1800991fe  mov     dword ptr [rsp+68h+var_48], r15d
0x180099203  xor     r9d, r9d
0x180099206  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x18009920d  mov     rcx, [rcx+10h]
0x180099211  call    WPP_SF_Dd
0x180099216  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009921d  test    rcx, rcx
0x180099220  jnz     short loc_180099230
0x180099222  lea     rcx, off_1800E5190; this
0x180099229  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099230  cmp     [rcx+8], r12b
0x180099234  jz      loc_180099393
0x18009923a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009923f  cmp     [rax+7CCh], r15d
0x180099246  jz      loc_180099393
0x18009924c  mov     r8d, 10Dh
0x180099252  mov     rdx, r14
0x180099255  jmp     loc_180099387
0x18009925a  mov     [rbp+arg_0], 1
0x18009925e  mov     rdi, [r13+40h]
0x180099262  mov     rax, [rdi]
0x180099265  mov     rbx, [rax+38h]
0x180099269  lea     rcx, [rbp+arg_10]
0x18009926d  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x180099272  lea     r8, [rbp+arg_0]
0x180099276  lea     rdx, [rbp+arg_10]
0x18009927a  mov     rcx, rdi
0x18009927d  mov     rax, rbx
0x180099280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099285  test    eax, eax
0x180099287  js      loc_180099393
0x18009928d  cmp     [rbp+arg_10], r12
0x180099291  jz      loc_180099393
0x180099297  mov     r14d, esi
0x18009929a  cmp     dword ptr [r13+48h], 1
0x18009929f  cmovnz  r14d, r12d
0x1800992a3  mov     ebx, r12d
0x1800992a6  cmp     [rbp+arg_0], r12b
0x1800992aa  setnz   bl
0x1800992ad  mov     rsi, [r13+38h]
0x1800992b1  mov     rax, [rsi]
0x1800992b4  mov     rdi, [rax+0E0h]
0x1800992bb  lea     rcx, [rbp+arg_18]
0x1800992bf  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800992c4  mov     rdx, [rbp+arg_10]
0x1800992c8  or      r14d, ebx
0x1800992cb  lea     rax, [rbp+arg_18]
0x1800992cf  mov     [rsp+68h+var_40], rax
0x1800992d4  mov     [rsp+68h+var_48], rdx
0x1800992d9  mov     r9d, r14d
0x1800992dc  xor     r8d, r8d
0x1800992df  lea     rdx, GUID_MetadataFormatIfd
0x1800992e6  mov     rcx, rsi
0x1800992e9  mov     rax, rdi
0x1800992ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800992f1  test    eax, eax
0x1800992f3  js      loc_180099393
0x1800992f9  mov     rdx, [rbp+arg_18]; struct IWICMetadataReader *
0x1800992fd  mov     rcx, r13; this
0x180099300  call    ?AddMetadataReader@CWICRawMetadataBlockReaderBase@@IEAAJPEAUIWICMetadataReader@@@Z; CWICRawMetadataBlockReaderBase::AddMetadataReader(IWICMetadataReader *)
0x180099305  mov     r15d, eax
0x180099308  test    eax, eax
0x18009930a  jns     loc_180099393
0x180099310  lea     rax, WPP_GLOBAL_Control
0x180099317  mov     rcx, cs:WPP_GLOBAL_Control
0x18009931e  cmp     rcx, rax
0x180099321  jz      short loc_18009934C
0x180099323  test    byte ptr [rcx+1Ch], 1
0x180099327  jz      short loc_18009934C
0x180099329  cmp     byte ptr [rcx+19h], 4
0x18009932d  jb      short loc_18009934C
0x18009932f  mov     edx, 19h
0x180099334  mov     dword ptr [rsp+68h+var_48], r15d
0x180099339  xor     r9d, r9d
0x18009933c  lea     r8, WPP_8fe3f2bb9b5e311b0120702be0509c03_Traceguids
0x180099343  mov     rcx, [rcx+10h]
0x180099347  call    WPP_SF_Dd
0x18009934c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099353  test    rcx, rcx
0x180099356  jnz     short loc_180099366
0x180099358  lea     rcx, off_1800E5190; this
0x18009935f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099366  cmp     [rcx+8], r12b
0x18009936a  jz      short loc_180099393
0x18009936c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099371  cmp     [rax+7CCh], r15d
0x180099378  jz      short loc_180099393
0x18009937a  mov     r8d, 11Dh; int
0x180099380  lea     rdx, aCwicrawmetadat_1; "CWICRawMetadataBlockReaderBase::CreateM"...
0x180099387  mov     r9d, r15d; int
0x18009938a  mov     rcx, rax; this
0x18009938d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099392  nop
0x180099393  lea     rcx, [rbp+arg_18]
0x180099397  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x18009939c  nop
0x18009939d  lea     rcx, [rbp+arg_10]
0x1800993a1  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800993a6  nop
0x1800993a7  lea     rcx, [rbp+var_20]; this
0x1800993ab  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x1800993b0  nop
0x1800993b1  lea     rcx, [rbp+arg_8]; this
0x1800993b5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800993ba  mov     eax, r15d
0x1800993bd  add     rsp, 68h
0x1800993c1  pop     r15
0x1800993c3  pop     r14
0x1800993c5  pop     r13
0x1800993c7  pop     r12
0x1800993c9  pop     rdi
0x1800993ca  pop     rsi
0x1800993cb  pop     rbx
0x1800993cc  pop     rbp
0x1800993cd  retn
```
