# CBinaryReader::ReadUnknown(IMFComponentCreator *,IUnknown * *)

- ea: `0x180050768`
- end: `0x180050ca0`
- name: `?ReadUnknown@CBinaryReader@@QEAAJPEAUIMFComponentCreator@@PEAPEAUIUnknown@@@Z`
- size: `1336`
- prototype: `__int64 __fastcall(CBinaryReader *__hidden this, struct IMFComponentCreator *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800332d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180050738`
- `0x180050750`
- `0x180050768`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050a31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050a31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005080f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800508dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050998`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050afc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050bba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005080f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800508dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050998`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050afc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050bba`

## string_xrefs

- `0x18005078b`: `CBinaryReader::ReadUnknown`

## pseudocode

```c
__int64 __fastcall CBinaryReader::ReadUnknown(CBinaryReader *this, struct IMFComponentCreator *a2, LPVOID *a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
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
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 (__fastcall *v28)(__int64, __int64); // rbx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  LPVOID v34; // rcx
  _BYTE v36[8]; // [rsp+30h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-38h] BYREF
  int v38; // [rsp+40h] [rbp-30h] BYREF
  __int64 v39; // [rsp+48h] [rbp-28h] BYREF
  IID rclsid; // [rsp+50h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v36, "CBinaryReader::ReadUnknown", 798);
  v38 = 0;
  ppv = 0;
  v39 = 0;
  rclsid = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    goto LABEL_80;
  }
  if ( (*(__int64 (__fastcall **)(CBinaryReader *))(*(_QWORD *)this + 8LL))(this) )
  {
    v6 = CBinaryReader::ReadInt32(this, &v38);
    if ( v6 < 0 )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CBinaryReader::ReadUnknown", 819, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_76;
      v11 = 35;
      goto LABEL_16;
    }
    if ( !v38 )
    {
      v6 = 0;
      goto LABEL_76;
    }
    v6 = CBinaryReader::ReadGuid(this, &rclsid);
    if ( v6 < 0 )
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
        if ( *((_DWORD *)v15 + 499) != v6 )
          CallStackContext::TraceFailure(v15, "CBinaryReader::ReadUnknown", 827, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_76;
      v11 = 36;
      goto LABEL_16;
    }
    if ( a2 )
    {
      v6 = (*(__int64 (__fastcall **)(struct IMFComponentCreator *, IID *, GUID *, LPVOID *))(*(_QWORD *)a2 + 24LL))(
             a2,
             &rclsid,
             &IID_IUnknown,
             &ppv);
      if ( v6 < 0 )
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
          if ( *((_DWORD *)v19 + 499) != v6 )
            CallStackContext::TraceFailure(v19, "CBinaryReader::ReadUnknown", 836, v6);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_76;
        v11 = 37;
        goto LABEL_16;
      }
    }
    else
    {
      v6 = CoCreateInstance(&rclsid, 0, 1u, &IID_IUnknown, &ppv);
      if ( v6 < 0 )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
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
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v6 )
            CallStackContext::TraceFailure(v23, "CBinaryReader::ReadUnknown", 840, v6);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_76;
        v11 = 38;
LABEL_16:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, this, v6);
        goto LABEL_76;
      }
    }
    v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistStream, &v39);
    if ( v6 >= 0 )
    {
      v28 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 40LL);
      v29 = (*(__int64 (__fastcall **)(CBinaryReader *))(*(_QWORD *)this + 8LL))(this);
      v6 = v28(v39, v29);
      if ( v6 >= 0 )
      {
        v34 = ppv;
        *a3 = ppv;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 8LL))(v34);
        goto LABEL_76;
      }
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v33 + 499) != v6 )
          CallStackContext::TraceFailure(v33, "CBinaryReader::ReadUnknown", 844, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_76;
      v11 = 40;
    }
    else
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != v6 )
          CallStackContext::TraceFailure(v27, "CBinaryReader::ReadUnknown", 842, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_76;
      v11 = 39;
    }
    goto LABEL_16;
  }
  v6 = -2147467261;
LABEL_76:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
LABEL_80:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180050768  push    rbp
0x18005076a  push    rbx
0x18005076b  push    rsi
0x18005076c  push    rdi
0x18005076d  push    r12
0x18005076f  push    r14
0x180050771  push    r15
0x180050773  mov     rbp, rsp
0x180050776  sub     rsp, 70h
0x18005077a  mov     rax, cs:__security_cookie
0x180050781  xor     rax, rsp
0x180050784  mov     [rbp+var_10], rax
0x180050788  mov     r14, r8
0x18005078b  lea     r12, aCbinaryreaderR; "CBinaryReader::ReadUnknown"
0x180050792  mov     rsi, rdx
0x180050795  mov     rdi, rcx
0x180050798  mov     rdx, r12; char *
0x18005079b  lea     rcx, [rbp+var_40]; this
0x18005079f  mov     r8d, 31Eh; int
0x1800507a5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800507aa  xor     r15d, r15d
0x1800507ad  xorps   xmm0, xmm0
0x1800507b0  mov     [rbp+var_30], r15d
0x1800507b4  mov     [rbp+var_38], r15
0x1800507b8  mov     [rbp+var_28], r15
0x1800507bc  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x1800507c0  test    r14, r14
0x1800507c3  jnz     short loc_1800507CF
0x1800507c5  mov     ebx, 80070057h
0x1800507ca  jmp     loc_180050C7A
0x1800507cf  mov     rax, [rdi]
0x1800507d2  mov     rcx, rdi
0x1800507d5  mov     rax, [rax+8]
0x1800507d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507de  test    rax, rax
0x1800507e1  jnz     short loc_1800507ED
0x1800507e3  mov     ebx, 80004003h
0x1800507e8  jmp     loc_180050C48
0x1800507ed  lea     rdx, [rbp+var_30]; int *
0x1800507f1  mov     rcx, rdi; this
0x1800507f4  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1800507f9  mov     ebx, eax
0x1800507fb  test    eax, eax
0x1800507fd  jns     loc_1800508AC
0x180050803  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005080a  test    rcx, rcx
0x18005080d  jnz     short loc_180050850
0x18005080f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050815  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005081c  mov     rcx, rax
0x18005081f  test    rax, rax
0x180050822  jz      short loc_180050842
0x180050824  mov     rax, [rax]
0x180050827  mov     edx, 7F0h
0x18005082c  mov     rax, [rax+8]
0x180050830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050835  test    eax, eax
0x180050837  jz      short loc_180050842
0x180050839  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050840  jmp     short loc_180050850
0x180050842  lea     rcx, qword_180069A90; this
0x180050849  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050850  cmp     [rcx+8], r15b
0x180050854  jz      short loc_180050877
0x180050856  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005085b  cmp     [rax+7CCh], ebx
0x180050861  jz      short loc_180050877
0x180050863  mov     r9d, ebx; int
0x180050866  mov     r8d, 333h; int
0x18005086c  mov     rdx, r12; char *
0x18005086f  mov     rcx, rax; this
0x180050872  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050877  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005087c  cmp     al, 1
0x18005087e  jb      loc_180050C48
0x180050884  mov     edx, 23h ; '#'
0x180050889  mov     rcx, cs:WPP_GLOBAL_Control
0x180050890  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x180050897  mov     r9, rdi
0x18005089a  mov     dword ptr [rsp+70h+ppv], ebx
0x18005089e  mov     rcx, [rcx+10h]
0x1800508a2  call    WPP_SF_qd
0x1800508a7  jmp     loc_180050C48
0x1800508ac  cmp     [rbp+var_30], r15d
0x1800508b0  jnz     short loc_1800508BA
0x1800508b2  mov     ebx, r15d
0x1800508b5  jmp     loc_180050C48
0x1800508ba  lea     rdx, [rbp+rclsid]; struct _GUID *
0x1800508be  mov     rcx, rdi; this
0x1800508c1  call    ?ReadGuid@CBinaryReader@@QEAAJAEAU_GUID@@@Z; CBinaryReader::ReadGuid(_GUID &)
0x1800508c6  mov     ebx, eax
0x1800508c8  test    eax, eax
0x1800508ca  jns     loc_18005095B
0x1800508d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800508d7  test    rcx, rcx
0x1800508da  jnz     short loc_18005091D
0x1800508dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800508e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800508e9  mov     rcx, rax
0x1800508ec  test    rax, rax
0x1800508ef  jz      short loc_18005090F
0x1800508f1  mov     rax, [rax]
0x1800508f4  mov     edx, 7F0h
0x1800508f9  mov     rax, [rax+8]
0x1800508fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050902  test    eax, eax
0x180050904  jz      short loc_18005090F
0x180050906  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005090d  jmp     short loc_18005091D
0x18005090f  lea     rcx, qword_180069A90; this
0x180050916  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005091d  cmp     [rcx+8], r15b
0x180050921  jz      short loc_180050944
0x180050923  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050928  cmp     [rax+7CCh], ebx
0x18005092e  jz      short loc_180050944
0x180050930  mov     r9d, ebx; int
0x180050933  mov     r8d, 33Bh; int
0x180050939  mov     rdx, r12; char *
0x18005093c  mov     rcx, rax; this
0x18005093f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050944  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050949  cmp     al, 1
0x18005094b  jb      loc_180050C48
0x180050951  mov     edx, 24h ; '$'
0x180050956  jmp     loc_180050889
0x18005095b  test    rsi, rsi
0x18005095e  jz      loc_180050A17
0x180050964  mov     rax, [rsi]
0x180050967  lea     r9, [rbp+var_38]
0x18005096b  lea     r8, IID_IUnknown
0x180050972  mov     rcx, rsi
0x180050975  lea     rdx, [rbp+rclsid]
0x180050979  mov     rax, [rax+18h]
0x18005097d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050982  mov     ebx, eax
0x180050984  test    eax, eax
0x180050986  jns     loc_180050ACC
0x18005098c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050993  test    rcx, rcx
0x180050996  jnz     short loc_1800509D9
0x180050998  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005099e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800509a5  mov     rcx, rax
0x1800509a8  test    rax, rax
0x1800509ab  jz      short loc_1800509CB
0x1800509ad  mov     rax, [rax]
0x1800509b0  mov     edx, 7F0h
0x1800509b5  mov     rax, [rax+8]
0x1800509b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509be  test    eax, eax
0x1800509c0  jz      short loc_1800509CB
0x1800509c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800509c9  jmp     short loc_1800509D9
0x1800509cb  lea     rcx, qword_180069A90; this
0x1800509d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800509d9  cmp     [rcx+8], r15b
0x1800509dd  jz      short loc_180050A00
0x1800509df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800509e4  cmp     [rax+7CCh], ebx
0x1800509ea  jz      short loc_180050A00
0x1800509ec  mov     r9d, ebx; int
0x1800509ef  mov     r8d, 344h; int
0x1800509f5  mov     rdx, r12; char *
0x1800509f8  mov     rcx, rax; this
0x1800509fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050a00  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050a05  cmp     al, 1
0x180050a07  jb      loc_180050C48
0x180050a0d  mov     edx, 25h ; '%'
0x180050a12  jmp     loc_180050889
0x180050a17  xor     edx, edx; pUnkOuter
0x180050a19  lea     rax, [rbp+var_38]
0x180050a1d  lea     r9, IID_IUnknown; riid
0x180050a24  mov     [rsp+70h+ppv], rax; ppv
0x180050a29  lea     rcx, [rbp+rclsid]; rclsid
0x180050a2d  lea     r8d, [rdx+1]; dwClsContext
0x180050a31  call    cs:__imp_CoCreateInstance
0x180050a37  mov     ebx, eax
0x180050a39  test    eax, eax
0x180050a3b  jns     loc_180050ACC
0x180050a41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050a48  test    rcx, rcx
0x180050a4b  jnz     short loc_180050A8E
0x180050a4d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050a53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050a5a  mov     rcx, rax
0x180050a5d  test    rax, rax
0x180050a60  jz      short loc_180050A80
0x180050a62  mov     rax, [rax]
0x180050a65  mov     edx, 7F0h
0x180050a6a  mov     rax, [rax+8]
0x180050a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a73  test    eax, eax
0x180050a75  jz      short loc_180050A80
0x180050a77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050a7e  jmp     short loc_180050A8E
0x180050a80  lea     rcx, qword_180069A90; this
0x180050a87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050a8e  cmp     [rcx+8], r15b
0x180050a92  jz      short loc_180050AB5
0x180050a94  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050a99  cmp     [rax+7CCh], ebx
0x180050a9f  jz      short loc_180050AB5
0x180050aa1  mov     r9d, ebx; int
0x180050aa4  mov     r8d, 348h; int
0x180050aaa  mov     rdx, r12; char *
0x180050aad  mov     rcx, rax; this
0x180050ab0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050ab5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050aba  cmp     al, 1
0x180050abc  jb      loc_180050C48
0x180050ac2  mov     edx, 26h ; '&'
0x180050ac7  jmp     loc_180050889
0x180050acc  mov     rcx, [rbp+var_38]
0x180050ad0  lea     r8, [rbp+var_28]
0x180050ad4  lea     rdx, IID_IPersistStream
0x180050adb  mov     rax, [rcx]
0x180050ade  mov     rax, [rax]
0x180050ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ae6  mov     ebx, eax
0x180050ae8  test    eax, eax
0x180050aea  jns     loc_180050B7B
0x180050af0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050af7  test    rcx, rcx
0x180050afa  jnz     short loc_180050B3D
0x180050afc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050b02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050b09  mov     rcx, rax
0x180050b0c  test    rax, rax
0x180050b0f  jz      short loc_180050B2F
0x180050b11  mov     rax, [rax]
0x180050b14  mov     edx, 7F0h
0x180050b19  mov     rax, [rax+8]
0x180050b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b22  test    eax, eax
0x180050b24  jz      short loc_180050B2F
0x180050b26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050b2d  jmp     short loc_180050B3D
0x180050b2f  lea     rcx, qword_180069A90; this
0x180050b36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050b3d  cmp     [rcx+8], r15b
0x180050b41  jz      short loc_180050B64
0x180050b43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050b48  cmp     [rax+7CCh], ebx
0x180050b4e  jz      short loc_180050B64
0x180050b50  mov     r9d, ebx; int
0x180050b53  mov     r8d, 34Ah; int
0x180050b59  mov     rdx, r12; char *
0x180050b5c  mov     rcx, rax; this
0x180050b5f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050b64  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050b69  cmp     al, 1
0x180050b6b  jb      loc_180050C48
0x180050b71  mov     edx, 27h ; '''
0x180050b76  jmp     loc_180050889
0x180050b7b  mov     rax, [rbp+var_28]
0x180050b7f  mov     rcx, [rax]
0x180050b82  mov     rbx, [rcx+28h]
0x180050b86  mov     rcx, [rdi]
0x180050b89  mov     rax, [rcx+8]
0x180050b8d  mov     rcx, rdi
0x180050b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b95  mov     rcx, [rbp+var_28]
0x180050b99  mov     rdx, rax
0x180050b9c  mov     rax, rbx
0x180050b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ba4  mov     ebx, eax
0x180050ba6  test    eax, eax
0x180050ba8  jns     loc_180050C35
0x180050bae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050bb5  test    rcx, rcx
0x180050bb8  jnz     short loc_180050BFB
0x180050bba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050bc0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050bc7  mov     rcx, rax
0x180050bca  test    rax, rax
0x180050bcd  jz      short loc_180050BED
0x180050bcf  mov     rax, [rax]
0x180050bd2  mov     edx, 7F0h
0x180050bd7  mov     rax, [rax+8]
0x180050bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050be0  test    eax, eax
0x180050be2  jz      short loc_180050BED
0x180050be4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050beb  jmp     short loc_180050BFB
0x180050bed  lea     rcx, qword_180069A90; this
0x180050bf4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050bfb  cmp     [rcx+8], r15b
0x180050bff  jz      short loc_180050C22
0x180050c01  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050c06  cmp     [rax+7CCh], ebx
0x180050c0c  jz      short loc_180050C22
0x180050c0e  mov     r9d, ebx; int
0x180050c11  mov     r8d, 34Ch; int
0x180050c17  mov     rdx, r12; char *
0x180050c1a  mov     rcx, rax; this
0x180050c1d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050c22  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050c27  cmp     al, 1
  ... truncated ...
```
