# MFCreateMFMetadataOnPropertyStore

- ea: `0x180049f6c`
- end: `0x18004a29f`
- name: `MFCreateMFMetadataOnPropertyStore`
- size: `819`
- prototype: `__int64 __fastcall(struct IPropertyStore *, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180038368`
- `0x180038604`

## callees

- `0x1800035c0`
- `0x180003690`
- `0x180004a40`
- `0x180007000`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x180046900`
- `0x180047f90`
- `0x180049f6c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049fbd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a080`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a12b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a1ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049fbd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a080`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a12b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a1ea`

## string_xrefs

- `0x180049f87`: `MFCreateMFMetadataOnPropertyStore`

## pseudocode

```c
__int64 __fastcall MFCreateMFMetadataOnPropertyStore(struct IPropertyStore *a1, void **a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int Interface; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CWMPropTranslator *v10; // rax
  __int64 v11; // rdx
  CWMPropTranslator *v12; // rax
  CWMPropTranslator *v13; // rdi
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  char v26; // [rsp+50h] [rbp+8h] BYREF
  int v27; // [rsp+60h] [rbp+18h] BYREF

  v27 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v26, "MFCreateMFMetadataOnPropertyStore", 23);
  if ( !a1 )
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    Interface = -2147467261;
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFCreateMFMetadataOnPropertyStore", 23, -2147467261);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_51;
    v9 = 10;
    goto LABEL_50;
  }
  v10 = (CWMPropTranslator *)operator new(0x330u);
  if ( !v10 || (v12 = CWMPropTranslator::CWMPropTranslator(v10, a1, &v27), (v13 = v12) == 0) )
  {
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    Interface = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v24, "MFCreateMFMetadataOnPropertyStore", 26, -2147024882);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_51;
    v9 = 11;
LABEL_50:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, 0, Interface);
    goto LABEL_51;
  }
  Interface = v27;
  if ( v27 >= 0 )
  {
    Interface = CWMPropTranslator::QueryInterface(v12, &IID_IMFMetadataProvider, a2);
    if ( Interface < 0 )
    {
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
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != Interface )
          CallStackContext::TraceFailure(v21, "MFCreateMFMetadataOnPropertyStore", 29, Interface);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 13;
        goto LABEL_37;
      }
    }
  }
  else
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
      if ( Interface < 0 && *((_DWORD *)v16 + 499) != Interface )
        CallStackContext::TraceFailure(v16, "MFCreateMFMetadataOnPropertyStore", 27, Interface);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v17 = 12;
LABEL_37:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, 0, Interface);
    }
  }
  if ( Interface < 0 )
  {
    CWMPropTranslator::`scalar deleting destructor'(v13, 1u);
LABEL_51:
    *a2 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180049f6c  mov     [rsp+arg_8], rbx
0x180049f71  push    rsi
0x180049f72  push    rdi
0x180049f73  push    r14
0x180049f75  sub     rsp, 30h
0x180049f79  mov     rsi, rdx
0x180049f7c  mov     [rsp+48h+arg_10], 0
0x180049f84  mov     rbx, rcx
0x180049f87  lea     r14, aMfcreatemfmeta; "MFCreateMFMetadataOnPropertyStore"
0x180049f8e  mov     edi, 17h
0x180049f93  lea     rcx, [rsp+48h+arg_0]; this
0x180049f98  mov     r8d, edi; int
0x180049f9b  mov     rdx, r14; char *
0x180049f9e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180049fa3  test    rbx, rbx
0x180049fa6  jnz     loc_18004A039
0x180049fac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049fb3  mov     ebx, 80004003h
0x180049fb8  test    rcx, rcx
0x180049fbb  jnz     short loc_180049FFE
0x180049fbd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049fc3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049fca  mov     rcx, rax
0x180049fcd  test    rax, rax
0x180049fd0  jz      short loc_180049FF0
0x180049fd2  mov     rax, [rax]
0x180049fd5  mov     edx, 7F0h
0x180049fda  mov     rax, [rax+8]
0x180049fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fe3  test    eax, eax
0x180049fe5  jz      short loc_180049FF0
0x180049fe7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049fee  jmp     short loc_180049FFE
0x180049ff0  lea     rcx, qword_180069A90; this
0x180049ff7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049ffe  cmp     byte ptr [rcx+8], 0
0x18004a002  jz      short loc_18004A022
0x18004a004  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a009  cmp     [rax+7CCh], ebx
0x18004a00f  jz      short loc_18004A022
0x18004a011  mov     r9d, ebx; int
0x18004a014  mov     r8d, edi; int
0x18004a017  mov     rdx, r14; char *
0x18004a01a  mov     rcx, rax; this
0x18004a01d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a022  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a027  cmp     al, 1
0x18004a029  jb      loc_18004A27E
0x18004a02f  mov     edx, 0Ah
0x18004a034  jmp     loc_18004A260
0x18004a039  mov     ecx, 330h; Size
0x18004a03e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a043  test    rax, rax
0x18004a046  jz      loc_18004A1D9
0x18004a04c  lea     r8, [rsp+48h+arg_10]; int *
0x18004a051  mov     rdx, rbx; struct IPropertyStore *
0x18004a054  mov     rcx, rax; this
0x18004a057  call    ??0CWMPropTranslator@@QEAA@PEAUIPropertyStore@@PEAJ@Z; CWMPropTranslator::CWMPropTranslator(IPropertyStore *,long *)
0x18004a05c  mov     rdi, rax
0x18004a05f  test    rax, rax
0x18004a062  jz      loc_18004A1D9
0x18004a068  mov     ebx, [rsp+48h+arg_10]
0x18004a06c  test    ebx, ebx
0x18004a06e  jns     loc_18004A103
0x18004a074  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a07b  test    rcx, rcx
0x18004a07e  jnz     short loc_18004A0C1
0x18004a080  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a086  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a08d  mov     rcx, rax
0x18004a090  test    rax, rax
0x18004a093  jz      short loc_18004A0B3
0x18004a095  mov     rax, [rax]
0x18004a098  mov     edx, 7F0h
0x18004a09d  mov     rax, [rax+8]
0x18004a0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0a6  test    eax, eax
0x18004a0a8  jz      short loc_18004A0B3
0x18004a0aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a0b1  jmp     short loc_18004A0C1
0x18004a0b3  lea     rcx, qword_180069A90; this
0x18004a0ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a0c1  cmp     byte ptr [rcx+8], 0
0x18004a0c5  jz      short loc_18004A0EC
0x18004a0c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a0cc  test    ebx, ebx
0x18004a0ce  jns     short loc_18004A0EC
0x18004a0d0  cmp     [rax+7CCh], ebx
0x18004a0d6  jz      short loc_18004A0EC
0x18004a0d8  mov     r9d, ebx; int
0x18004a0db  mov     r8d, 1Bh; int
0x18004a0e1  mov     rdx, r14; char *
0x18004a0e4  mov     rcx, rax; this
0x18004a0e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a0ec  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a0f1  cmp     al, 1
0x18004a0f3  jb      loc_18004A1BF
0x18004a0f9  mov     edx, 0Ch
0x18004a0fe  jmp     loc_18004A1A1
0x18004a103  mov     r8, rsi; void **
0x18004a106  lea     rdx, IID_IMFMetadataProvider; struct _GUID *
0x18004a10d  mov     rcx, rdi; this
0x18004a110  call    ?QueryInterface@CWMPropTranslator@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWMPropTranslator::QueryInterface(_GUID const &,void * *)
0x18004a115  mov     ebx, eax
0x18004a117  test    eax, eax
0x18004a119  jns     loc_18004A1BF
0x18004a11f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a126  test    rcx, rcx
0x18004a129  jnz     short loc_18004A16C
0x18004a12b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a131  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a138  mov     rcx, rax
0x18004a13b  test    rax, rax
0x18004a13e  jz      short loc_18004A15E
0x18004a140  mov     rax, [rax]
0x18004a143  mov     edx, 7F0h
0x18004a148  mov     rax, [rax+8]
0x18004a14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a151  test    eax, eax
0x18004a153  jz      short loc_18004A15E
0x18004a155  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a15c  jmp     short loc_18004A16C
0x18004a15e  lea     rcx, qword_180069A90; this
0x18004a165  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a16c  cmp     byte ptr [rcx+8], 0
0x18004a170  jz      short loc_18004A193
0x18004a172  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a177  cmp     [rax+7CCh], ebx
0x18004a17d  jz      short loc_18004A193
0x18004a17f  mov     r9d, ebx; int
0x18004a182  mov     r8d, 1Dh; int
0x18004a188  mov     rdx, r14; char *
0x18004a18b  mov     rcx, rax; this
0x18004a18e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a193  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a198  cmp     al, 1
0x18004a19a  jb      short loc_18004A1BF
0x18004a19c  mov     edx, 0Dh
0x18004a1a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1a8  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x18004a1af  xor     r9d, r9d
0x18004a1b2  mov     [rsp+48h+var_28], ebx
0x18004a1b6  mov     rcx, [rcx+10h]
0x18004a1ba  call    WPP_SF_qd
0x18004a1bf  test    ebx, ebx
0x18004a1c1  jns     loc_18004A285
0x18004a1c7  mov     edx, 1; unsigned int
0x18004a1cc  mov     rcx, rdi; this
0x18004a1cf  call    ??_GCWMPropTranslator@@UEAAPEAXI@Z; CWMPropTranslator::`scalar deleting destructor'(uint)
0x18004a1d4  jmp     loc_18004A27E
0x18004a1d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a1e0  mov     ebx, 8007000Eh
0x18004a1e5  test    rcx, rcx
0x18004a1e8  jnz     short loc_18004A22B
0x18004a1ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a1f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a1f7  mov     rcx, rax
0x18004a1fa  test    rax, rax
0x18004a1fd  jz      short loc_18004A21D
0x18004a1ff  mov     rax, [rax]
0x18004a202  mov     edx, 7F0h
0x18004a207  mov     rax, [rax+8]
0x18004a20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a210  test    eax, eax
0x18004a212  jz      short loc_18004A21D
0x18004a214  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a21b  jmp     short loc_18004A22B
0x18004a21d  lea     rcx, qword_180069A90; this
0x18004a224  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a22b  cmp     byte ptr [rcx+8], 0
0x18004a22f  jz      short loc_18004A252
0x18004a231  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a236  cmp     [rax+7CCh], ebx
0x18004a23c  jz      short loc_18004A252
0x18004a23e  mov     r9d, ebx; int
0x18004a241  mov     r8d, 1Ah; int
0x18004a247  mov     rdx, r14; char *
0x18004a24a  mov     rcx, rax; this
0x18004a24d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a252  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a257  cmp     al, 1
0x18004a259  jb      short loc_18004A27E
0x18004a25b  mov     edx, 0Bh
0x18004a260  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a267  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x18004a26e  xor     r9d, r9d
0x18004a271  mov     [rsp+48h+var_28], ebx
0x18004a275  mov     rcx, [rcx+10h]
0x18004a279  call    WPP_SF_qd
0x18004a27e  mov     qword ptr [rsi], 0
0x18004a285  lea     rcx, [rsp+48h+arg_0]; this
0x18004a28a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004a28f  mov     eax, ebx
0x18004a291  mov     rbx, [rsp+48h+arg_8]
0x18004a296  add     rsp, 30h
0x18004a29a  pop     r14
0x18004a29c  pop     rdi
0x18004a29d  pop     rsi
0x18004a29e  retn
```
