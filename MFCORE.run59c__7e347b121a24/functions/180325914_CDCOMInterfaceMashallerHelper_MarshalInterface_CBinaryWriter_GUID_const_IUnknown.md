# CDCOMInterfaceMashallerHelper::MarshalInterface(CBinaryWriter &,_GUID const &,IUnknown *)

- ea: `0x180325914`
- end: `0x180325eea`
- name: `?MarshalInterface@CDCOMInterfaceMashallerHelper@@SAJAEAVCBinaryWriter@@AEBU_GUID@@PEAUIUnknown@@@Z`
- size: `1494`
- prototype: `__int64 __fastcall(struct CBinaryWriter *this, IID *riid, LPUNKNOWN pUnk)`
- caller_count: `8`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180191ee0`
- `0x18019f084`
- `0x1801ef094`
- `0x1802354ec`
- `0x1802a0e40`
- `0x1802cb2dc`
- `0x1802cb64c`
- `0x180328570`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x1801128dc`
- `0x180258480`
- `0x1802592a0`
- `0x180325914`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180325ea6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180325ea6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180325c7a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180325c7a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180325e96`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180325e96`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180325b17`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180325b17`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180325983`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180325983`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180325a67`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180325a67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1803259a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325a89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325b39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325bf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325ca3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325d54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325e06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1803259a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325a89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325b39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325bf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325ca3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325d54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180325e06`

## string_xrefs

- `0x180325962`: `CDCOMInterfaceMashallerHelper::MarshalInterface`

## pseudocode

```c
__int64 __fastcall CDCOMInterfaceMashallerHelper::MarshalInterface(
        struct CBinaryWriter *this,
        IID *riid,
        LPUNKNOWN pUnk)
{
  __int64 v6; // rdx
  HRESULT HGlobalFromStream; // ebx
  __int64 v8; // r8
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  LPVOID v29; // rdi
  __int64 v30; // r8
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v45[8]; // [rsp+30h] [rbp-49h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-41h] BYREF
  HGLOBAL phglobal; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v48[16]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v49; // [rsp+60h] [rbp-19h]

  ppstm = 0;
  phglobal = 0;
  memset_0(v48, 0, 0x50u);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v45,
    "CDCOMInterfaceMashallerHelper::MarshalInterface",
    1240);
  HGlobalFromStream = CreateStreamOnHGlobal(0, 0, &ppstm);
  if ( HGlobalFromStream >= 0 )
  {
    HGlobalFromStream = CoMarshalInterface(ppstm, riid, pUnk, 0, 0, 0);
    if ( HGlobalFromStream >= 0 )
    {
      HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
      if ( HGlobalFromStream >= 0 )
      {
        HGlobalFromStream = (*(__int64 (__fastcall **)(LPSTREAM, _BYTE *, __int64))(*(_QWORD *)ppstm + 96LL))(
                              ppstm,
                              v48,
                              1);
        if ( HGlobalFromStream >= 0 )
        {
          v29 = GlobalLock(phglobal);
          if ( v29 )
          {
            if ( v49 )
            {
              HGlobalFromStream = CBinaryWriter::WriteInt64(this, v49);
              if ( HGlobalFromStream >= 0 )
              {
                HGlobalFromStream = (**(__int64 (__fastcall ***)(struct CBinaryWriter *, LPVOID, _QWORD))this)(
                                      this,
                                      v29,
                                      (unsigned int)v49);
                if ( HGlobalFromStream < 0 )
                {
                  v41 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40);
                    CallStackTracing::s_wpInstance = v42;
                    if ( v42
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                    {
                      v41 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v41 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v41 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != HGlobalFromStream )
                      CallStackContext::TraceFailure(
                        ThreadRelativeContext,
                        "CDCOMInterfaceMashallerHelper::MarshalInterface",
                        1260,
                        HGlobalFromStream);
                  }
                  if ( g_wppLevels )
                  {
                    v12 = 98;
                    goto LABEL_12;
                  }
                }
              }
              else
              {
                v36 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35);
                  CallStackTracing::s_wpInstance = v37;
                  if ( v37
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                  {
                    v36 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v36 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v36 + 8) )
                {
                  v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                  if ( *((_DWORD *)v38 + 499) != HGlobalFromStream )
                    CallStackContext::TraceFailure(
                      v38,
                      "CDCOMInterfaceMashallerHelper::MarshalInterface",
                      1259,
                      HGlobalFromStream);
                }
                if ( g_wppLevels )
                {
                  v12 = 97;
                  goto LABEL_12;
                }
              }
            }
            else
            {
              HGlobalFromStream = -2147418113;
            }
          }
          else
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
            HGlobalFromStream = -2147418113;
            if ( !CallStackTracing::s_wpInstance )
            {
              v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v30);
              CallStackTracing::s_wpInstance = v32;
              if ( v32
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
              {
                v31 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v31 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v31 + 8) )
            {
              v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
              if ( *((_DWORD *)v33 + 499) != -2147418113 )
                CallStackContext::TraceFailure(
                  v33,
                  "CDCOMInterfaceMashallerHelper::MarshalInterface",
                  1255,
                  -2147418113);
            }
            if ( g_wppLevels )
            {
              v12 = 96;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
            if ( *((_DWORD *)v27 + 499) != HGlobalFromStream )
              CallStackContext::TraceFailure(
                v27,
                "CDCOMInterfaceMashallerHelper::MarshalInterface",
                1252,
                HGlobalFromStream);
          }
          if ( g_wppLevels )
          {
            v12 = 95;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != HGlobalFromStream )
            CallStackContext::TraceFailure(
              v22,
              "CDCOMInterfaceMashallerHelper::MarshalInterface",
              1250,
              HGlobalFromStream);
        }
        if ( g_wppLevels )
        {
          v12 = 94;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != HGlobalFromStream )
          CallStackContext::TraceFailure(
            v17,
            "CDCOMInterfaceMashallerHelper::MarshalInterface",
            1245,
            HGlobalFromStream);
      }
      if ( g_wppLevels )
      {
        v12 = 93;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != HGlobalFromStream )
        CallStackContext::TraceFailure(v11, "CDCOMInterfaceMashallerHelper::MarshalInterface", 1240, HGlobalFromStream);
    }
    if ( g_wppLevels )
    {
      v12 = 92;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids,
        0,
        HGlobalFromStream);
    }
  }
  if ( phglobal )
  {
    GlobalUnlock(phglobal);
    GlobalFree(phglobal);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v45);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x180325914  mov     [rsp-8+arg_18], rbx
0x180325919  push    rbp
0x18032591a  push    rsi
0x18032591b  push    rdi
0x18032591c  push    r12
0x18032591e  push    r14
0x180325920  lea     rbp, [rsp-37h]
0x180325925  sub     rsp, 0B0h
0x18032592c  mov     rax, cs:__security_cookie
0x180325933  xor     rax, rsp
0x180325936  mov     [rbp+57h+var_30], rax
0x18032593a  mov     rdi, rdx
0x18032593d  mov     [rbp+57h+ppstm], 0
0x180325945  xor     edx, edx; Val
0x180325947  mov     [rbp+57h+phglobal], 0
0x18032594f  mov     r14, r8
0x180325952  mov     rsi, rcx
0x180325955  lea     rcx, [rbp+57h+var_80]; void *
0x180325959  lea     r8d, [rdx+50h]; Size
0x18032595d  call    memset_0
0x180325962  lea     r12, aCdcominterface_0; "CDCOMInterfaceMashallerHelper::MarshalI"...
0x180325969  mov     r8d, 4D8h; int
0x18032596f  mov     rdx, r12; char *
0x180325972  lea     rcx, [rbp+57h+var_A0]; this
0x180325976  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18032597b  lea     r8, [rbp+57h+ppstm]; ppstm
0x18032597f  xor     edx, edx; fDeleteOnRelease
0x180325981  xor     ecx, ecx; hGlobal
0x180325983  call    cs:__imp_CreateStreamOnHGlobal
0x18032598a  nop     dword ptr [rax+rax+00h]
0x18032598f  mov     ebx, eax
0x180325991  test    eax, eax
0x180325993  jns     loc_180325A49
0x180325999  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1803259a0  test    rcx, rcx
0x1803259a3  jnz     short loc_1803259ED
0x1803259a5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1803259ac  nop     dword ptr [rax+rax+00h]
0x1803259b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1803259b8  mov     rcx, rax
0x1803259bb  test    rax, rax
0x1803259be  jz      short loc_1803259DF
0x1803259c0  mov     rax, [rax]
0x1803259c3  mov     edx, 7F0h
0x1803259c8  mov     rax, [rax+8]
0x1803259cc  call    cs:__guard_dispatch_icall_fptr
0x1803259d2  test    eax, eax
0x1803259d4  jz      short loc_1803259DF
0x1803259d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1803259dd  jmp     short loc_1803259ED
0x1803259df  lea     rcx, qword_1803CE250; this
0x1803259e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1803259ed  cmp     byte ptr [rcx+8], 0
0x1803259f1  jz      short loc_180325A14
0x1803259f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1803259f8  cmp     [rax+7CCh], ebx
0x1803259fe  jz      short loc_180325A14
0x180325a00  mov     r9d, ebx; int
0x180325a03  mov     r8d, 4D8h; int
0x180325a09  mov     rdx, r12; char *
0x180325a0c  mov     rcx, rax; this
0x180325a0f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180325a14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180325a1b  jb      loc_180325E8D
0x180325a21  mov     edx, 5Ch ; '\'
0x180325a26  mov     rcx, cs:WPP_GLOBAL_Control
0x180325a2d  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x180325a34  xor     r9d, r9d
0x180325a37  mov     dword ptr [rsp+0D0h+pvDestContext], ebx
0x180325a3b  mov     rcx, [rcx+10h]
0x180325a3f  call    WPP_SF_qD
0x180325a44  jmp     loc_180325E8D
0x180325a49  mov     rcx, [rbp+57h+ppstm]; pStm
0x180325a4d  xor     r9d, r9d; dwDestContext
0x180325a50  mov     [rsp+0D0h+mshlflags], 0; mshlflags
0x180325a58  mov     r8, r14; pUnk
0x180325a5b  mov     rdx, rdi; riid
0x180325a5e  mov     [rsp+0D0h+pvDestContext], 0; pvDestContext
0x180325a67  call    cs:__imp_CoMarshalInterface
0x180325a6e  nop     dword ptr [rax+rax+00h]
0x180325a73  mov     ebx, eax
0x180325a75  test    eax, eax
0x180325a77  jns     loc_180325B0F
0x180325a7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325a84  test    rcx, rcx
0x180325a87  jnz     short loc_180325AD1
0x180325a89  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180325a90  nop     dword ptr [rax+rax+00h]
0x180325a95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180325a9c  mov     rcx, rax
0x180325a9f  test    rax, rax
0x180325aa2  jz      short loc_180325AC3
0x180325aa4  mov     rax, [rax]
0x180325aa7  mov     edx, 7F0h
0x180325aac  mov     rax, [rax+8]
0x180325ab0  call    cs:__guard_dispatch_icall_fptr
0x180325ab6  test    eax, eax
0x180325ab8  jz      short loc_180325AC3
0x180325aba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325ac1  jmp     short loc_180325AD1
0x180325ac3  lea     rcx, qword_1803CE250; this
0x180325aca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180325ad1  cmp     byte ptr [rcx+8], 0
0x180325ad5  jz      short loc_180325AF8
0x180325ad7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180325adc  cmp     [rax+7CCh], ebx
0x180325ae2  jz      short loc_180325AF8
0x180325ae4  mov     r9d, ebx; int
0x180325ae7  mov     r8d, 4DDh; int
0x180325aed  mov     rdx, r12; char *
0x180325af0  mov     rcx, rax; this
0x180325af3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180325af8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180325aff  jb      loc_180325E8D
0x180325b05  mov     edx, 5Dh ; ']'
0x180325b0a  jmp     loc_180325A26
0x180325b0f  mov     rcx, [rbp+57h+ppstm]; pstm
0x180325b13  lea     rdx, [rbp+57h+phglobal]; phglobal
0x180325b17  call    cs:__imp_GetHGlobalFromStream
0x180325b1e  nop     dword ptr [rax+rax+00h]
0x180325b23  mov     ebx, eax
0x180325b25  test    eax, eax
0x180325b27  jns     loc_180325BBF
0x180325b2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325b34  test    rcx, rcx
0x180325b37  jnz     short loc_180325B81
0x180325b39  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180325b40  nop     dword ptr [rax+rax+00h]
0x180325b45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180325b4c  mov     rcx, rax
0x180325b4f  test    rax, rax
0x180325b52  jz      short loc_180325B73
0x180325b54  mov     rax, [rax]
0x180325b57  mov     edx, 7F0h
0x180325b5c  mov     rax, [rax+8]
0x180325b60  call    cs:__guard_dispatch_icall_fptr
0x180325b66  test    eax, eax
0x180325b68  jz      short loc_180325B73
0x180325b6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325b71  jmp     short loc_180325B81
0x180325b73  lea     rcx, qword_1803CE250; this
0x180325b7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180325b81  cmp     byte ptr [rcx+8], 0
0x180325b85  jz      short loc_180325BA8
0x180325b87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180325b8c  cmp     [rax+7CCh], ebx
0x180325b92  jz      short loc_180325BA8
0x180325b94  mov     r9d, ebx; int
0x180325b97  mov     r8d, 4E2h; int
0x180325b9d  mov     rdx, r12; char *
0x180325ba0  mov     rcx, rax; this
0x180325ba3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180325ba8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180325baf  jb      loc_180325E8D
0x180325bb5  mov     edx, 5Eh ; '^'
0x180325bba  jmp     loc_180325A26
0x180325bbf  mov     rcx, [rbp+57h+ppstm]
0x180325bc3  lea     rdx, [rbp+57h+var_80]
0x180325bc7  mov     r8d, 1
0x180325bcd  mov     rax, [rcx]
0x180325bd0  mov     rax, [rax+60h]
0x180325bd4  call    cs:__guard_dispatch_icall_fptr
0x180325bda  mov     ebx, eax
0x180325bdc  test    eax, eax
0x180325bde  jns     loc_180325C76
0x180325be4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325beb  test    rcx, rcx
0x180325bee  jnz     short loc_180325C38
0x180325bf0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180325bf7  nop     dword ptr [rax+rax+00h]
0x180325bfc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180325c03  mov     rcx, rax
0x180325c06  test    rax, rax
0x180325c09  jz      short loc_180325C2A
0x180325c0b  mov     rax, [rax]
0x180325c0e  mov     edx, 7F0h
0x180325c13  mov     rax, [rax+8]
0x180325c17  call    cs:__guard_dispatch_icall_fptr
0x180325c1d  test    eax, eax
0x180325c1f  jz      short loc_180325C2A
0x180325c21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325c28  jmp     short loc_180325C38
0x180325c2a  lea     rcx, qword_1803CE250; this
0x180325c31  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180325c38  cmp     byte ptr [rcx+8], 0
0x180325c3c  jz      short loc_180325C5F
0x180325c3e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180325c43  cmp     [rax+7CCh], ebx
0x180325c49  jz      short loc_180325C5F
0x180325c4b  mov     r9d, ebx; int
0x180325c4e  mov     r8d, 4E4h; int
0x180325c54  mov     rdx, r12; char *
0x180325c57  mov     rcx, rax; this
0x180325c5a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180325c5f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180325c66  jb      loc_180325E8D
0x180325c6c  mov     edx, 5Fh ; '_'
0x180325c71  jmp     loc_180325A26
0x180325c76  mov     rcx, [rbp+57h+phglobal]; hMem
0x180325c7a  call    cs:__imp_GlobalLock
0x180325c81  nop     dword ptr [rax+rax+00h]
0x180325c86  mov     rdi, rax
0x180325c89  test    rax, rax
0x180325c8c  jnz     loc_180325D29
0x180325c92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325c99  mov     ebx, 8000FFFFh
0x180325c9e  test    rcx, rcx
0x180325ca1  jnz     short loc_180325CEB
0x180325ca3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180325caa  nop     dword ptr [rax+rax+00h]
0x180325caf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180325cb6  mov     rcx, rax
0x180325cb9  test    rax, rax
0x180325cbc  jz      short loc_180325CDD
0x180325cbe  mov     rax, [rax]
0x180325cc1  mov     edx, 7F0h
0x180325cc6  mov     rax, [rax+8]
0x180325cca  call    cs:__guard_dispatch_icall_fptr
0x180325cd0  test    eax, eax
0x180325cd2  jz      short loc_180325CDD
0x180325cd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325cdb  jmp     short loc_180325CEB
0x180325cdd  lea     rcx, qword_1803CE250; this
0x180325ce4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180325ceb  cmp     byte ptr [rcx+8], 0
0x180325cef  jz      short loc_180325D12
0x180325cf1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180325cf6  cmp     [rax+7CCh], ebx
0x180325cfc  jz      short loc_180325D12
0x180325cfe  mov     r9d, ebx; int
0x180325d01  mov     r8d, 4E7h; int
0x180325d07  mov     rdx, r12; char *
0x180325d0a  mov     rcx, rax; this
0x180325d0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180325d12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180325d19  jb      loc_180325E8D
0x180325d1f  mov     edx, 60h ; '`'
0x180325d24  jmp     loc_180325A26
0x180325d29  mov     rdx, [rbp+57h+var_70]; __int64
0x180325d2d  test    rdx, rdx
0x180325d30  jz      loc_180325E88
0x180325d36  mov     rcx, rsi; this
0x180325d39  call    ?WriteInt64@CBinaryWriter@@QEAAJ_J@Z; CBinaryWriter::WriteInt64(__int64)
0x180325d3e  mov     ebx, eax
0x180325d40  test    eax, eax
0x180325d42  jns     loc_180325DDA
0x180325d48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325d4f  test    rcx, rcx
0x180325d52  jnz     short loc_180325D9C
0x180325d54  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180325d5b  nop     dword ptr [rax+rax+00h]
0x180325d60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180325d67  mov     rcx, rax
0x180325d6a  test    rax, rax
0x180325d6d  jz      short loc_180325D8E
0x180325d6f  mov     rax, [rax]
0x180325d72  mov     edx, 7F0h
0x180325d77  mov     rax, [rax+8]
0x180325d7b  call    cs:__guard_dispatch_icall_fptr
0x180325d81  test    eax, eax
0x180325d83  jz      short loc_180325D8E
0x180325d85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325d8c  jmp     short loc_180325D9C
0x180325d8e  lea     rcx, qword_1803CE250; this
0x180325d95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180325d9c  cmp     byte ptr [rcx+8], 0
0x180325da0  jz      short loc_180325DC3
0x180325da2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180325da7  cmp     [rax+7CCh], ebx
0x180325dad  jz      short loc_180325DC3
0x180325daf  mov     r9d, ebx; int
0x180325db2  mov     r8d, 4EBh; int
0x180325db8  mov     rdx, r12; char *
0x180325dbb  mov     rcx, rax; this
0x180325dbe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180325dc3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180325dca  jb      loc_180325E8D
0x180325dd0  mov     edx, 61h ; 'a'
0x180325dd5  jmp     loc_180325A26
0x180325dda  mov     rax, [rsi]
0x180325ddd  mov     rdx, rdi
0x180325de0  mov     r8d, dword ptr [rbp+57h+var_70]
0x180325de4  mov     rcx, rsi
0x180325de7  mov     rax, [rax]
0x180325dea  call    cs:__guard_dispatch_icall_fptr
0x180325df0  mov     ebx, eax
0x180325df2  test    eax, eax
0x180325df4  jns     loc_180325E8D
0x180325dfa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180325e01  test    rcx, rcx
0x180325e04  jnz     short loc_180325E4E
0x180325e06  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180325e0d  nop     dword ptr [rax+rax+00h]
0x180325e12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180325e19  mov     rcx, rax
0x180325e1c  test    rax, rax
0x180325e1f  jz      short loc_180325E40
0x180325e21  mov     rax, [rax]
0x180325e24  mov     edx, 7F0h
0x180325e29  mov     rax, [rax+8]
  ... truncated ...
```
