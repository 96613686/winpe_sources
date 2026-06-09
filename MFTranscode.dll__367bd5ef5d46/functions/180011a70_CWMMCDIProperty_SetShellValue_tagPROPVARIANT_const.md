# CWMMCDIProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x180011a70`
- end: `0x180011f00`
- name: `?SetShellValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1168`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180011a70`
- `0x18001a330`
- `0x18001c280`
- `0x180022064`
- `0x1800442dc`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011aaa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011acd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011aaa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011acd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011ccb`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180011b73`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180011b73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011ae9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011b92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011c3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011ced`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011e4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011ae9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011b92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011c3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011ced`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011e4c`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetShellValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  unsigned int v4; // r13d
  __int64 v5; // rdx
  HRESULT v6; // esi
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int v19; // eax
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  int v24; // edi
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  char v36; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int64 v37; // [rsp+80h] [rbp+50h] BYREF

  v37 = 0;
  if ( a2->vt == 31 )
  {
    v4 = 0;
    PropVariantClear(this + 5);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v36, "CWMMCDIProperty::SetShellValue", 372);
    v6 = PropVariantClear(this + 4);
    if ( v6 >= 0 )
    {
      v6 = PropVariantCopy(this + 4, a2);
      if ( v6 >= 0 )
      {
        this[5].vt = 65;
        v6 = StringCchLengthW(a2->bstrVal, v11, &v37);
        if ( v6 >= 0 )
        {
          v19 = 2 * v37 + 2;
          this[5].lVal = v19;
          v20 = (unsigned __int16 *)CoTaskMemAlloc(v19);
          this[5].bstrblobVal.pData = (BYTE *)v20;
          if ( v20 )
          {
            v24 = StringCchCopyW(v20, (unsigned __int64)this[5].ulVal >> 1, a2->bstrVal);
            if ( v24 >= 0 )
              goto LABEL_69;
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v24 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetShellValue", 398, v24);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_69;
            v26 = 33;
          }
          else
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
              CallStackTracing::s_wpInstance = v23;
              if ( v23
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
              {
                v22 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v22 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            v24 = -2147024882;
            if ( *((_BYTE *)v22 + 8) )
            {
              v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
              if ( *((_DWORD *)v25 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v25, "CWMMCDIProperty::SetShellValue", 390, -2147024882);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_69;
            v26 = 32;
          }
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v26,
            WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            v24);
          goto LABEL_69;
        }
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
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
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != v6 )
            CallStackContext::TraceFailure(v18, "CWMMCDIProperty::SetShellValue", 386, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 31;
          goto LABEL_13;
        }
      }
      else
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
          if ( *((_DWORD *)v14 + 499) != v6 )
            CallStackContext::TraceFailure(v14, "CWMMCDIProperty::SetShellValue", 374, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 30;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
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
        v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)v9 + 499) != v6 )
          CallStackContext::TraceFailure(v9, "CWMMCDIProperty::SetShellValue", 372, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 29;
LABEL_13:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v6);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v36, "CWMMCDIProperty::SetShellValue", 403);
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    v4 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v34 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v34, "CWMMCDIProperty::SetShellValue", 403, -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -2147418113);
  }
LABEL_69:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v36);
  return v4;
}

```

## disassembly

```asm
0x180011a70  mov     [rsp-38h+arg_0], rbx
0x180011a75  push    rbp
0x180011a76  push    rsi
0x180011a77  push    rdi
0x180011a78  push    r12
0x180011a7a  push    r13
0x180011a7c  push    r14
0x180011a7e  push    r15
0x180011a80  mov     rbp, rsp
0x180011a83  sub     rsp, 30h
0x180011a87  mov     eax, 1Fh
0x180011a8c  mov     [rbp+arg_10], 0
0x180011a94  mov     rdi, rdx
0x180011a97  mov     rbx, rcx
0x180011a9a  cmp     [rdx], ax
0x180011a9d  jnz     loc_180011E1F
0x180011aa3  add     rcx, 78h ; 'x'; pvar
0x180011aa7  xor     r13d, r13d
0x180011aaa  call    cs:__imp_PropVariantClear
0x180011ab0  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x180011ab7  mov     r8d, 174h; int
0x180011abd  mov     rdx, r14; char *
0x180011ac0  lea     rcx, [rbp+arg_8]; this
0x180011ac4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180011ac9  lea     rcx, [rbx+60h]; pvar
0x180011acd  call    cs:__imp_PropVariantClear
0x180011ad3  mov     esi, eax
0x180011ad5  test    eax, eax
0x180011ad7  jns     loc_180011B6C
0x180011add  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011ae4  test    rcx, rcx
0x180011ae7  jnz     short loc_180011B2A
0x180011ae9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011aef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011af6  mov     rcx, rax
0x180011af9  test    rax, rax
0x180011afc  jz      short loc_180011B1C
0x180011afe  mov     rax, [rax]
0x180011b01  mov     edx, 7F0h
0x180011b06  mov     rax, [rax+8]
0x180011b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b0f  test    eax, eax
0x180011b11  jz      short loc_180011B1C
0x180011b13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011b1a  jmp     short loc_180011B2A
0x180011b1c  lea     rcx, qword_180069A90; this
0x180011b23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011b2a  cmp     [rcx+8], r13b
0x180011b2e  jz      short loc_180011B51
0x180011b30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011b35  cmp     [rax+7CCh], esi
0x180011b3b  jz      short loc_180011B51
0x180011b3d  mov     r9d, esi; int
0x180011b40  mov     r8d, 174h; int
0x180011b46  mov     rdx, r14; char *
0x180011b49  mov     rcx, rax; this
0x180011b4c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011b51  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011b56  cmp     al, 1
0x180011b58  jb      loc_180011EDF
0x180011b5e  mov     edx, 1Dh
0x180011b63  mov     [rsp+30h+var_10], esi
0x180011b67  jmp     loc_180011EC5
0x180011b6c  mov     rdx, rdi; pvarSrc
0x180011b6f  lea     rcx, [rbx+60h]; pvarDest
0x180011b73  call    cs:__imp_PropVariantCopy
0x180011b79  xor     r15d, r15d
0x180011b7c  mov     esi, eax
0x180011b7e  test    eax, eax
0x180011b80  jns     loc_180011C11
0x180011b86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011b8d  test    rcx, rcx
0x180011b90  jnz     short loc_180011BD3
0x180011b92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011b98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011b9f  mov     rcx, rax
0x180011ba2  test    rax, rax
0x180011ba5  jz      short loc_180011BC5
0x180011ba7  mov     rax, [rax]
0x180011baa  mov     edx, 7F0h
0x180011baf  mov     rax, [rax+8]
0x180011bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bb8  test    eax, eax
0x180011bba  jz      short loc_180011BC5
0x180011bbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011bc3  jmp     short loc_180011BD3
0x180011bc5  lea     rcx, qword_180069A90; this
0x180011bcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011bd3  cmp     [rcx+8], r15b
0x180011bd7  jz      short loc_180011BFA
0x180011bd9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011bde  cmp     [rax+7CCh], esi
0x180011be4  jz      short loc_180011BFA
0x180011be6  mov     r9d, esi; int
0x180011be9  mov     r8d, 176h; int
0x180011bef  mov     rdx, r14; char *
0x180011bf2  mov     rcx, rax; this
0x180011bf5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011bfa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011bff  cmp     al, 1
0x180011c01  jb      loc_180011EDF
0x180011c07  mov     edx, 1Eh
0x180011c0c  jmp     loc_180011B63
0x180011c11  mov     word ptr [rbx+78h], 41h ; 'A'
0x180011c17  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x180011c1b  mov     rcx, [rdi+8]; unsigned __int16 *
0x180011c1f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180011c24  mov     esi, eax
0x180011c26  test    eax, eax
0x180011c28  jns     loc_180011CB9
0x180011c2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011c35  test    rcx, rcx
0x180011c38  jnz     short loc_180011C7B
0x180011c3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011c40  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011c47  mov     rcx, rax
0x180011c4a  test    rax, rax
0x180011c4d  jz      short loc_180011C6D
0x180011c4f  mov     rax, [rax]
0x180011c52  mov     edx, 7F0h
0x180011c57  mov     rax, [rax+8]
0x180011c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c60  test    eax, eax
0x180011c62  jz      short loc_180011C6D
0x180011c64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011c6b  jmp     short loc_180011C7B
0x180011c6d  lea     rcx, qword_180069A90; this
0x180011c74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011c7b  cmp     [rcx+8], r15b
0x180011c7f  jz      short loc_180011CA2
0x180011c81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011c86  cmp     [rax+7CCh], esi
0x180011c8c  jz      short loc_180011CA2
0x180011c8e  mov     r9d, esi; int
0x180011c91  mov     r8d, 182h; int
0x180011c97  mov     rdx, r14; char *
0x180011c9a  mov     rcx, rax; this
0x180011c9d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011ca2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011ca7  cmp     al, 1
0x180011ca9  jb      loc_180011EDF
0x180011caf  mov     edx, 1Fh
0x180011cb4  jmp     loc_180011B63
0x180011cb9  mov     eax, dword ptr [rbp+arg_10]
0x180011cbc  lea     eax, ds:2[rax*2]
0x180011cc3  mov     ecx, eax; cb
0x180011cc5  mov     [rbx+80h], eax
0x180011ccb  call    cs:__imp_CoTaskMemAlloc
0x180011cd1  mov     [rbx+88h], rax
0x180011cd8  test    rax, rax
0x180011cdb  jnz     loc_180011D75
0x180011ce1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011ce8  test    rcx, rcx
0x180011ceb  jnz     short loc_180011D2E
0x180011ced  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011cf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011cfa  mov     rcx, rax
0x180011cfd  test    rax, rax
0x180011d00  jz      short loc_180011D20
0x180011d02  mov     rax, [rax]
0x180011d05  mov     edx, 7F0h
0x180011d0a  mov     rax, [rax+8]
0x180011d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d13  test    eax, eax
0x180011d15  jz      short loc_180011D20
0x180011d17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011d1e  jmp     short loc_180011D2E
0x180011d20  lea     rcx, qword_180069A90; this
0x180011d27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011d2e  mov     edi, 8007000Eh
0x180011d33  cmp     [rcx+8], r15b
0x180011d37  jz      short loc_180011D5A
0x180011d39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011d3e  cmp     [rax+7CCh], edi
0x180011d44  jz      short loc_180011D5A
0x180011d46  mov     r9d, edi; int
0x180011d49  mov     r8d, 186h; int
0x180011d4f  mov     rdx, r14; char *
0x180011d52  mov     rcx, rax; this
0x180011d55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011d5a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011d5f  cmp     al, 1
0x180011d61  jb      loc_180011EDF
0x180011d67  mov     edx, 20h ; ' '
0x180011d6c  mov     [rsp+30h+var_10], edi
0x180011d70  jmp     loc_180011EC5
0x180011d75  mov     edx, [rbx+80h]
0x180011d7b  mov     rcx, rax; unsigned __int16 *
0x180011d7e  mov     r8, [rdi+8]; unsigned __int16 *
0x180011d82  shr     rdx, 1; unsigned __int64
0x180011d85  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011d8a  mov     edi, eax
0x180011d8c  test    eax, eax
0x180011d8e  jns     loc_180011EDF
0x180011d94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011d9b  test    rcx, rcx
0x180011d9e  jnz     short loc_180011DE1
0x180011da0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011da6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011dad  mov     rcx, rax
0x180011db0  test    rax, rax
0x180011db3  jz      short loc_180011DD3
0x180011db5  mov     rax, [rax]
0x180011db8  mov     edx, 7F0h
0x180011dbd  mov     rax, [rax+8]
0x180011dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc6  test    eax, eax
0x180011dc8  jz      short loc_180011DD3
0x180011dca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011dd1  jmp     short loc_180011DE1
0x180011dd3  lea     rcx, qword_180069A90; this
0x180011dda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011de1  cmp     [rcx+8], r15b
0x180011de5  jz      short loc_180011E08
0x180011de7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011dec  cmp     [rax+7CCh], edi
0x180011df2  jz      short loc_180011E08
0x180011df4  mov     r9d, edi; int
0x180011df7  mov     r8d, 18Eh; int
0x180011dfd  mov     rdx, r14; char *
0x180011e00  mov     rcx, rax; this
0x180011e03  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011e08  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011e0d  cmp     al, 1
0x180011e0f  jb      loc_180011EDF
0x180011e15  mov     edx, 21h ; '!'
0x180011e1a  jmp     loc_180011D6C
0x180011e1f  mov     edi, 193h
0x180011e24  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x180011e2b  mov     r8d, edi; int
0x180011e2e  lea     rcx, [rbp+arg_8]; this
0x180011e32  mov     rdx, r14; char *
0x180011e35  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180011e3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011e41  mov     r13d, 8000FFFFh
0x180011e47  test    rcx, rcx
0x180011e4a  jnz     short loc_180011E8D
0x180011e4c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011e52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011e59  mov     rcx, rax
0x180011e5c  test    rax, rax
0x180011e5f  jz      short loc_180011E7F
0x180011e61  mov     rax, [rax]
0x180011e64  mov     edx, 7F0h
0x180011e69  mov     rax, [rax+8]
0x180011e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e72  test    eax, eax
0x180011e74  jz      short loc_180011E7F
0x180011e76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011e7d  jmp     short loc_180011E8D
0x180011e7f  lea     rcx, qword_180069A90; this
0x180011e86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011e8d  cmp     byte ptr [rcx+8], 0
0x180011e91  jz      short loc_180011EB2
0x180011e93  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011e98  cmp     [rax+7CCh], r13d
0x180011e9f  jz      short loc_180011EB2
0x180011ea1  mov     r9d, r13d; int
0x180011ea4  mov     r8d, edi; int
0x180011ea7  mov     rdx, r14; char *
0x180011eaa  mov     rcx, rax; this
0x180011ead  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011eb2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011eb7  cmp     al, 1
0x180011eb9  jb      short loc_180011EDF
0x180011ebb  mov     edx, 22h ; '"'
0x180011ec0  mov     [rsp+30h+var_10], r13d
0x180011ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ecc  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180011ed3  mov     r9, rbx
0x180011ed6  mov     rcx, [rcx+10h]
0x180011eda  call    WPP_SF_qd
0x180011edf  lea     rcx, [rbp+arg_8]; this
0x180011ee3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180011ee8  mov     rbx, [rsp+30h+arg_0]
0x180011eed  mov     eax, r13d
0x180011ef0  add     rsp, 30h
0x180011ef4  pop     r15
0x180011ef6  pop     r14
0x180011ef8  pop     r13
0x180011efa  pop     r12
0x180011efc  pop     rdi
0x180011efd  pop     rsi
0x180011efe  pop     rbp
0x180011eff  retn
```
