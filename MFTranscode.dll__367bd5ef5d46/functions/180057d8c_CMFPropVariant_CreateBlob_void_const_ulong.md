# CMFPropVariant::CreateBlob(void const *,ulong)

- ea: `0x180057d8c`
- end: `0x180057eb7`
- name: `?CreateBlob@CMFPropVariant@@QEAAJPEBXK@Z`
- size: `299`
- prototype: `int(CMFPropVariant *__hidden this, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180055d04`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180057d8c`
- `0x1800594bc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057daf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057daf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057dee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057dee`

## string_xrefs

- `0x180057dbb`: `CMFPropVariant::CreateBlob`
- `0x180057e45`: `CMFPropVariant::CreateBlob`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateBlob(CMFPropVariant *this, const void *a2, unsigned int a3)
{
  size_t v5; // rsi
  __int64 v6; // rdx
  void *v7; // rcx
  __int64 *v8; // rcx
  unsigned int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v13; // [rsp+60h] [rbp+18h] BYREF

  *(_WORD *)this = 65;
  v5 = a3;
  *((_QWORD *)this + 2) = CoTaskMemAlloc(a3);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v13, "CMFPropVariant::CreateBlob", 1805);
  v7 = (void *)*((_QWORD *)this + 2);
  if ( v7 )
  {
    v9 = 0;
    memcpy_0(v7, a2, v5);
    *((_DWORD *)this + 2) = v5;
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147024882;
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateBlob", 1805, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        121,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return v9;
}

```

## disassembly

```asm
0x180057d8c  mov     [rsp+arg_0], rbx
0x180057d91  mov     [rsp+arg_8], rbp
0x180057d96  push    rsi
0x180057d97  push    rdi
0x180057d98  push    r14
0x180057d9a  sub     rsp, 30h
0x180057d9e  mov     rdi, rcx
0x180057da1  mov     word ptr [rcx], 41h ; 'A'
0x180057da6  mov     ecx, r8d; cb
0x180057da9  mov     r14, rdx
0x180057dac  mov     esi, r8d
0x180057daf  call    cs:__imp_CoTaskMemAlloc
0x180057db5  mov     r8d, 70Dh; int
0x180057dbb  lea     rdx, aCmfpropvariant_0; "CMFPropVariant::CreateBlob"
0x180057dc2  lea     rcx, [rsp+48h+arg_10]; this
0x180057dc7  mov     [rdi+10h], rax
0x180057dcb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180057dd0  mov     rcx, [rdi+10h]; void *
0x180057dd4  test    rcx, rcx
0x180057dd7  jnz     loc_180057E88
0x180057ddd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057de4  mov     ebx, 8007000Eh
0x180057de9  test    rcx, rcx
0x180057dec  jnz     short loc_180057E2F
0x180057dee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057df4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057dfb  mov     rcx, rax
0x180057dfe  test    rax, rax
0x180057e01  jz      short loc_180057E21
0x180057e03  mov     rax, [rax]
0x180057e06  mov     edx, 7F0h
0x180057e0b  mov     rax, [rax+8]
0x180057e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e14  test    eax, eax
0x180057e16  jz      short loc_180057E21
0x180057e18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057e1f  jmp     short loc_180057E2F
0x180057e21  lea     rcx, qword_180069A90; this
0x180057e28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057e2f  cmp     byte ptr [rcx+8], 0
0x180057e33  jz      short loc_180057E5A
0x180057e35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057e3a  cmp     [rax+7CCh], ebx
0x180057e40  jz      short loc_180057E5A
0x180057e42  mov     r9d, ebx; int
0x180057e45  lea     rdx, aCmfpropvariant_0; "CMFPropVariant::CreateBlob"
0x180057e4c  mov     r8d, 70Dh; int
0x180057e52  mov     rcx, rax; this
0x180057e55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057e5a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180057e5f  cmp     al, 1
0x180057e61  jb      short loc_180057E98
0x180057e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e6a  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180057e71  mov     edx, 79h ; 'y'
0x180057e76  mov     [rsp+48h+var_28], ebx
0x180057e7a  mov     r9, rdi
0x180057e7d  mov     rcx, [rcx+10h]
0x180057e81  call    WPP_SF_qd
0x180057e86  jmp     short loc_180057E98
0x180057e88  xor     ebx, ebx
0x180057e8a  mov     r8, rsi; Size
0x180057e8d  mov     rdx, r14; Src
0x180057e90  call    memcpy_0
0x180057e95  mov     [rdi+8], esi
0x180057e98  lea     rcx, [rsp+48h+arg_10]; this
0x180057e9d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180057ea2  mov     rbp, [rsp+48h+arg_8]
0x180057ea7  mov     eax, ebx
0x180057ea9  mov     rbx, [rsp+48h+arg_0]
0x180057eae  add     rsp, 30h
0x180057eb2  pop     r14
0x180057eb4  pop     rdi
0x180057eb5  pop     rsi
0x180057eb6  retn
```
