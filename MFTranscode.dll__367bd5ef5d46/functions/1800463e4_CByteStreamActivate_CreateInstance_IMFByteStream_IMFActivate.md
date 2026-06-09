# CByteStreamActivate::CreateInstance(IMFByteStream *,IMFActivate * *)

- ea: `0x1800463e4`
- end: `0x180046687`
- name: `?CreateInstance@CByteStreamActivate@@SAJPEAUIMFByteStream@@PEAPEAUIMFActivate@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(struct IMFByteStream *, struct IMFActivate **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180043aa0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x1800312dc`
- `0x1800463e4`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004642c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800464d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800465d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004642c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800464d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800465d3`

## string_xrefs

- `0x1800463f9`: `CByteStreamActivate::CreateInstance`
- `0x180046483`: `CByteStreamActivate::CreateInstance`
- `0x18004652d`: `CByteStreamActivate::CreateInstance`
- `0x18004662a`: `CByteStreamActivate::CreateInstance`

## pseudocode

```c
__int64 __fastcall CByteStreamActivate::CreateInstance(struct IMFActivateVtbl *a1, struct IMFActivate **a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // edi
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  struct IMFActivate *v13; // rax
  __int64 v14; // rdx
  struct IMFActivate *v15; // rbx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v20; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v20, "CByteStreamActivate::CreateInstance", 23);
  if ( a2 )
  {
    *a2 = 0;
    if ( a1 )
    {
      v13 = (struct IMFActivate *)operator new(0x58u);
      v15 = v13;
      if ( v13 )
      {
        CMFAttributesImpl<IMFActivate,CMFCSLock>::CMFAttributesImpl<IMFActivate,CMFCSLock>(v13);
        LODWORD(v15[9].lpVtbl) = 1;
        v15->lpVtbl = (struct IMFActivateVtbl *)&CByteStreamActivate::`vftable';
        v15[10].lpVtbl = a1;
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v20,
          "CByteStreamActivate::CByteStreamActivate",
          50);
        (*((void (__fastcall **)(struct IMFActivateVtbl *))a1->QueryInterface + 1))(a1);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
        v6 = 0;
        *a2 = v15;
      }
      else
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        v6 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CByteStreamActivate::CreateInstance",
              35,
              -2147024882);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_0560b53295bd3d99a578533dd9ca2e7b_Traceguids,
            0,
            -2147024882);
      }
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      v6 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v12, "CByteStreamActivate::CreateInstance", 31, -2147467261);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 12;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = -2147467261;
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
      if ( *((_DWORD *)v8 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v8, "CByteStreamActivate::CreateInstance", 28, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 11;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        WPP_0560b53295bd3d99a578533dd9ca2e7b_Traceguids,
        0,
        -2147467261);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
  return v6;
}

```

## disassembly

```asm
0x1800463e4  mov     [rsp+arg_0], rbx
0x1800463e9  mov     [rsp+arg_10], rsi
0x1800463ee  push    rdi
0x1800463ef  sub     rsp, 30h
0x1800463f3  mov     rsi, rdx
0x1800463f6  mov     rdi, rcx
0x1800463f9  lea     rdx, aCbytestreamact_2; "CByteStreamActivate::CreateInstance"
0x180046400  mov     r8d, 17h; int
0x180046406  lea     rcx, [rsp+38h+arg_8]; this
0x18004640b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180046410  test    rsi, rsi
0x180046413  jnz     loc_1800464B3
0x180046419  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046420  mov     ebx, 80004003h
0x180046425  mov     edi, ebx
0x180046427  test    rcx, rcx
0x18004642a  jnz     short loc_18004646D
0x18004642c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046432  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046439  mov     rcx, rax
0x18004643c  test    rax, rax
0x18004643f  jz      short loc_18004645F
0x180046441  mov     rax, [rax]
0x180046444  mov     edx, 7F0h
0x180046449  mov     rax, [rax+8]
0x18004644d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046452  test    eax, eax
0x180046454  jz      short loc_18004645F
0x180046456  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004645d  jmp     short loc_18004646D
0x18004645f  lea     rcx, qword_180069A90; this
0x180046466  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004646d  cmp     byte ptr [rcx+8], 0
0x180046471  jz      short loc_180046498
0x180046473  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046478  cmp     [rax+7CCh], ebx
0x18004647e  jz      short loc_180046498
0x180046480  mov     r9d, ebx; int
0x180046483  lea     rdx, aCbytestreamact_2; "CByteStreamActivate::CreateInstance"
0x18004648a  mov     r8d, 1Ch; int
0x180046490  mov     rcx, rax; this
0x180046493  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046498  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004649d  cmp     al, 1
0x18004649f  jb      loc_18004666B
0x1800464a5  mov     edx, 0Bh
0x1800464aa  mov     [rsp+38h+var_18], ebx
0x1800464ae  jmp     loc_180046651
0x1800464b3  mov     qword ptr [rsi], 0
0x1800464ba  test    rdi, rdi
0x1800464bd  jnz     loc_180046559
0x1800464c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800464ca  mov     ebx, 80004003h
0x1800464cf  mov     edi, ebx
0x1800464d1  test    rcx, rcx
0x1800464d4  jnz     short loc_180046517
0x1800464d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800464dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800464e3  mov     rcx, rax
0x1800464e6  test    rax, rax
0x1800464e9  jz      short loc_180046509
0x1800464eb  mov     rax, [rax]
0x1800464ee  mov     edx, 7F0h
0x1800464f3  mov     rax, [rax+8]
0x1800464f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464fc  test    eax, eax
0x1800464fe  jz      short loc_180046509
0x180046500  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046507  jmp     short loc_180046517
0x180046509  lea     rcx, qword_180069A90; this
0x180046510  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046517  cmp     byte ptr [rcx+8], 0
0x18004651b  jz      short loc_180046542
0x18004651d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046522  cmp     [rax+7CCh], ebx
0x180046528  jz      short loc_180046542
0x18004652a  mov     r9d, ebx; int
0x18004652d  lea     rdx, aCbytestreamact_2; "CByteStreamActivate::CreateInstance"
0x180046534  mov     r8d, 1Fh; int
0x18004653a  mov     rcx, rax; this
0x18004653d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046542  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180046547  cmp     al, 1
0x180046549  jb      loc_18004666B
0x18004654f  mov     edx, 0Ch
0x180046554  jmp     loc_1800464AA
0x180046559  mov     ecx, 58h ; 'X'; Size
0x18004655e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046563  mov     rbx, rax
0x180046566  test    rax, rax
0x180046569  jz      short loc_1800465C2
0x18004656b  mov     rcx, rax
0x18004656e  call    ??0?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@QEAA@I@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::CMFAttributesImpl<IMFActivate,CMFCSLock>(uint)
0x180046573  lea     rax, ??_7CByteStreamActivate@@6B@; const CByteStreamActivate::`vftable'
0x18004657a  mov     dword ptr [rbx+48h], 1
0x180046581  mov     r8d, 32h ; '2'; int
0x180046587  mov     [rbx], rax
0x18004658a  lea     rdx, aCbytestreamact_3; "CByteStreamActivate::CByteStreamActivat"...
0x180046591  mov     [rbx+50h], rdi
0x180046595  lea     rcx, [rsp+38h+arg_8]; this
0x18004659a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004659f  mov     rax, [rdi]
0x1800465a2  mov     rcx, rdi
0x1800465a5  mov     rax, [rax+8]
0x1800465a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465ae  lea     rcx, [rsp+38h+arg_8]; this
0x1800465b3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800465b8  xor     edi, edi
0x1800465ba  mov     [rsi], rbx
0x1800465bd  jmp     loc_18004666B
0x1800465c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800465c9  mov     edi, 8007000Eh
0x1800465ce  test    rcx, rcx
0x1800465d1  jnz     short loc_180046614
0x1800465d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800465d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800465e0  mov     rcx, rax
0x1800465e3  test    rax, rax
0x1800465e6  jz      short loc_180046606
0x1800465e8  mov     rax, [rax]
0x1800465eb  mov     edx, 7F0h
0x1800465f0  mov     rax, [rax+8]
0x1800465f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465f9  test    eax, eax
0x1800465fb  jz      short loc_180046606
0x1800465fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046604  jmp     short loc_180046614
0x180046606  lea     rcx, qword_180069A90; this
0x18004660d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046614  cmp     byte ptr [rcx+8], 0
0x180046618  jz      short loc_18004663F
0x18004661a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004661f  cmp     [rax+7CCh], edi
0x180046625  jz      short loc_18004663F
0x180046627  mov     r9d, edi; int
0x18004662a  lea     rdx, aCbytestreamact_2; "CByteStreamActivate::CreateInstance"
0x180046631  mov     r8d, 23h ; '#'; int
0x180046637  mov     rcx, rax; this
0x18004663a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004663f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180046644  cmp     al, 1
0x180046646  jb      short loc_18004666B
0x180046648  mov     edx, 0Dh
0x18004664d  mov     [rsp+38h+var_18], edi
0x180046651  mov     rcx, cs:WPP_GLOBAL_Control
0x180046658  lea     r8, WPP_0560b53295bd3d99a578533dd9ca2e7b_Traceguids
0x18004665f  xor     r9d, r9d
0x180046662  mov     rcx, [rcx+10h]
0x180046666  call    WPP_SF_qd
0x18004666b  lea     rcx, [rsp+38h+arg_8]; this
0x180046670  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180046675  mov     rbx, [rsp+38h+arg_0]
0x18004667a  mov     eax, edi
0x18004667c  mov     rsi, [rsp+38h+arg_10]
0x180046681  add     rsp, 30h
0x180046685  pop     rdi
0x180046686  retn
```
