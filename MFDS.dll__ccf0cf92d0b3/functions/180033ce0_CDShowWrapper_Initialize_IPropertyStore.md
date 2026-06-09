# CDShowWrapper::Initialize(IPropertyStore *)

- ea: `0x180033ce0`
- end: `0x18003426e`
- name: `?Initialize@CDShowWrapper@@UEAAJPEAUIPropertyStore@@@Z`
- size: `1422`
- prototype: `__int64 __fastcall(PVOID pv, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x18002d514`
- `0x180032a50`
- `0x180033ce0`
- `0x180035768`
- `0x180035b84`
- `0x180051ce4`
- `0x180074160`
- `0x18007bd58`
- `0x18007c8e8`
- `0x1800802fc`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180033d99`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180033f3a`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180033d99`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180033f3a`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180034049`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180034083`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180034049`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180034083`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003405f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034099`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003405f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033de2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033fab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034017`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033fab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034017`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180033dca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180033dca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800340d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034183`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800340d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034183`
- `MFPlat!CreatePropertyStore` at `0x180033e6b`
- `MFPlat!CreatePropertyStore` at `0x180033e6b`
- `MFPlat!MFCreateTelemetrySession` at `0x180033ee3`
- `MFPlat!MFCreateTelemetrySession` at `0x180033ee3`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::Initialize(char *pv, struct IPropertyStore *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  signed int DVDGraph; // ebx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  IPropertyStore *v13; // rcx
  int v14; // r14d
  wchar_t Buffer; // ax
  char v16; // dl
  __int16 v17; // r8
  int v18; // r9d
  const wchar_t *v19; // rax
  wchar_t v20; // ax
  char v21; // dl
  __int16 v22; // r8
  int v23; // r9d
  const wchar_t *v24; // rax
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  wchar_t v32; // [rsp+20h] [rbp-49h]
  wchar_t v33; // [rsp+20h] [rbp-49h]
  long double v34; // [rsp+28h] [rbp-41h]
  long double v35; // [rsp+28h] [rbp-41h]
  _BYTE v36[8]; // [rsp+30h] [rbp-39h] BYREF
  IPropertyStore *ppStore; // [rsp+38h] [rbp-31h] BYREF
  __int16 v38; // [rsp+40h] [rbp-29h] BYREF
  void (__fastcall ***v39)(_QWORD, GUID *, char *); // [rsp+48h] [rbp-21h]
  GUID v40; // [rsp+60h] [rbp-9h] BYREF
  PROPVARIANT pvar; // [rsp+70h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v36, "CDShowWrapper::Initialize", 1671);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)pv + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)pv + 60) + 296LL))(*((_QWORD *)pv + 60));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, PROPVARIANT *))(**((_QWORD **)pv + 60) + 280LL))(
                      *((_QWORD *)pv + 60),
                      &pvar);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  memset(&v38, 0, 0x18u);
  ppStore = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IPropertyStore *))a2->lpVtbl->AddRef)(a2);
  ThreadpoolWait = CreateThreadpoolWait(CDShowWrapper::FilterGraphEventCallback, pv, 0);
  *((_QWORD *)pv + 52) = ThreadpoolWait;
  if ( ThreadpoolWait )
    goto LABEL_17;
  LastError = GetLastError();
  DVDGraph = LastError;
  if ( LastError > 0 )
    DVDGraph = (unsigned __int16)LastError | 0x80070000;
  if ( DVDGraph >= 0 )
  {
LABEL_17:
    v13 = ppStore;
    if ( ppStore || (CreatePropertyStore(&ppStore), (v13 = ppStore) != 0) )
    {
      ((void (__fastcall *)(IPropertyStore *, __int64 *, __int16 *))v13->lpVtbl->GetValue)(
        v13,
        MFPKEY_TELEMETRY_SESSION,
        &v38);
      if ( v38 == 13 )
      {
        (**v39)(v39, &GUID_627d2ca6_e1cd_4898_999d_101308f1d431, pv + 480);
      }
      else
      {
        v40 = GUID_00000000_0000_0000_0000_000000000000;
        *(GUID *)&pvar.vt = GUID_00000000_0000_0000_0000_000000000000;
        MFCreateTelemetrySession(&pvar, &v40, pv + 480);
        CMFPropVariant::operator=(&v38, *((_QWORD *)pv + 60));
        ((void (__fastcall *)(IPropertyStore *, __int64 *, __int16 *))ppStore->lpVtbl->SetValue)(
          ppStore,
          MFPKEY_TELEMETRY_SESSION,
          &v38);
      }
    }
    if ( a2 )
    {
      memset(&pvar, 0, sizeof(pvar));
      memset(&pvar, 0, sizeof(pvar));
      if ( ((int (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a2->lpVtbl->GetValue)(
             a2,
             qword_1800D9D28,
             &pvar) >= 0
        && pvar.vt == 11
        && pvar.iVal == -1 )
      {
        if ( (unsigned __int8)byte_1800EACCB >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 123, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, pv);
        *((_DWORD *)pv + 116) = 1;
      }
      PropVariantClear(&pvar);
      if ( ((int (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a2->lpVtbl->GetValue)(
             a2,
             qword_1800D9D10,
             &pvar) >= 0
        && pvar.vt == 11
        && pvar.iVal == -1 )
      {
        if ( (unsigned __int8)byte_1800EACCB >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 124, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, pv);
        *((_DWORD *)pv + 117) = 1;
      }
      PropVariantClear(&pvar);
    }
    if ( *((int *)pv + 5) >= 0
      && (v14 = *((_DWORD *)pv + 6), v14 > 0)
      && (Buffer = CMFBaseStringT<unsigned short>::GetBuffer(pv + 16, (unsigned int)v14),
          v19 = (const wchar_t *)o(Buffer, v16, v17, v18, v32, v34),
          wcsstr(v19, L"msdvd:"))
      && (v20 = CMFBaseStringT<unsigned short>::GetBuffer(pv + 16, (unsigned int)v14),
          v24 = (const wchar_t *)o(v20, v21, v22, v23, v33, v35),
          wcsstr(v24, L"video_ts")) )
    {
      *((_DWORD *)pv + 118) = 1;
      DVDGraph = CDShowWrapper::CreateDVDGraph((CDShowWrapper *)pv);
      if ( DVDGraph < 0 )
      {
        v25 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext(v25);
          if ( *((_DWORD *)v27 + 499) != DVDGraph )
            CallStackContext::TraceFailure(v27, "CDShowWrapper::Initialize", 1753, DVDGraph);
        }
        if ( g_wppLevels )
        {
          v12 = 125;
          goto LABEL_62;
        }
      }
    }
    else
    {
      DVDGraph = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)pv + 160LL))(pv);
      if ( DVDGraph < 0 )
      {
        v28 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext(v28);
          if ( *((_DWORD *)v30 + 499) != DVDGraph )
            CallStackContext::TraceFailure(v30, "CDShowWrapper::Initialize", 1757, DVDGraph);
        }
        if ( g_wppLevels )
        {
          v12 = 126;
          goto LABEL_62;
        }
      }
    }
  }
  else
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v11 + 499) != DVDGraph )
        CallStackContext::TraceFailure(v11, "CDShowWrapper::Initialize", 1688, DVDGraph);
    }
    if ( g_wppLevels )
    {
      v12 = 122;
LABEL_62:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        pv,
        DVDGraph);
    }
  }
  if ( ppStore )
    ((void (__fastcall *)(IPropertyStore *))ppStore->lpVtbl->Release)(ppStore);
  CMFPropVariant::Clear((CMFPropVariant *)&v38);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v36);
  return (unsigned int)DVDGraph;
}

```

## disassembly

```asm
0x180033ce0  mov     [rsp-8+arg_10], rbx
0x180033ce5  push    rbp
0x180033ce6  push    rsi
0x180033ce7  push    rdi
0x180033ce8  push    r13
0x180033cea  push    r14
0x180033cec  lea     rbp, [rsp-37h]
0x180033cf1  sub     rsp, 0A0h
0x180033cf8  mov     rax, cs:__security_cookie
0x180033cff  xor     rax, rsp
0x180033d02  mov     [rbp+57h+var_30], rax
0x180033d06  mov     r14, rdx
0x180033d09  mov     rsi, rcx
0x180033d0c  lea     rdx, aCdshowwrapperI_0; "CDShowWrapper::Initialize"
0x180033d13  mov     r8d, 687h; int
0x180033d19  lea     rcx, [rbp+57h+var_90]; this
0x180033d1d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180033d22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180033d29  cmp     byte ptr [rcx+8], 0
0x180033d2d  jz      short loc_180033D8A
0x180033d2f  cmp     qword ptr [rsi+1E0h], 0
0x180033d37  jz      short loc_180033D8A
0x180033d39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033d3e  mov     rdx, [rsi+1E0h]
0x180033d45  mov     rdi, rax
0x180033d48  mov     rcx, [rdx]
0x180033d4b  mov     rax, [rcx+128h]
0x180033d52  mov     rcx, rdx
0x180033d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d5a  mov     r8, [rsi+1E0h]
0x180033d61  lea     rdx, [rbp+57h+pvar]
0x180033d65  mov     ebx, eax
0x180033d67  mov     rcx, [r8]
0x180033d6a  mov     rax, [rcx+118h]
0x180033d71  mov     rcx, r8
0x180033d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d79  movups  xmm0, xmmword ptr [rax]
0x180033d7c  mov     [rdi+7E0h], ebx
0x180033d82  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180033d8a  mov     r13d, 18h
0x180033d90  lea     rcx, [rbp+57h+var_80]; void *
0x180033d94  mov     r8d, r13d; Size
0x180033d97  xor     edx, edx; Val
0x180033d99  call    cs:__imp_memset
0x180033da0  nop     dword ptr [rax+rax+00h]
0x180033da5  mov     [rbp+57h+ppStore], r14
0x180033da9  test    r14, r14
0x180033dac  jz      short loc_180033DBD
0x180033dae  mov     rax, [r14]
0x180033db1  mov     rcx, r14
0x180033db4  mov     rax, [rax+8]
0x180033db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dbd  xor     r8d, r8d; pcbe
0x180033dc0  lea     rcx, ?FilterGraphEventCallback@CDShowWrapper@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180033dc7  mov     rdx, rsi; pv
0x180033dca  call    cs:__imp_CreateThreadpoolWait
0x180033dd1  nop     dword ptr [rax+rax+00h]
0x180033dd6  mov     [rsi+1A0h], rax
0x180033ddd  test    rax, rax
0x180033de0  jnz     short loc_180033E5E
0x180033de2  call    cs:__imp_GetLastError
0x180033de9  nop     dword ptr [rax+rax+00h]
0x180033dee  mov     ebx, eax
0x180033df0  test    eax, eax
0x180033df2  jle     short loc_180033DFD
0x180033df4  movzx   ebx, ax
0x180033df7  or      ebx, 80070000h
0x180033dfd  test    ebx, ebx
0x180033dff  jns     short loc_180033E5E
0x180033e01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033e08  test    rcx, rcx
0x180033e0b  jnz     short loc_180033E19
0x180033e0d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180033e12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180033e19  cmp     byte ptr [rcx+8], 0
0x180033e1d  jz      short loc_180033E44
0x180033e1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033e24  cmp     [rax+7CCh], ebx
0x180033e2a  jz      short loc_180033E44
0x180033e2c  mov     r9d, ebx; int
0x180033e2f  lea     rdx, aCdshowwrapperI_0; "CDShowWrapper::Initialize"
0x180033e36  mov     r8d, 698h; int
0x180033e3c  mov     rcx, rax; this
0x180033e3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180033e44  mov     edi, 1
0x180033e49  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180033e50  jb      loc_180034221
0x180033e56  lea     edx, [rdi+79h]
0x180033e59  jmp     loc_180034203
0x180033e5e  mov     rcx, [rbp+57h+ppStore]
0x180033e62  test    rcx, rcx
0x180033e65  jnz     short loc_180033E84
0x180033e67  lea     rcx, [rbp+57h+ppStore]; ppStore
0x180033e6b  call    cs:__imp_CreatePropertyStore
0x180033e72  nop     dword ptr [rax+rax+00h]
0x180033e77  mov     rcx, [rbp+57h+ppStore]
0x180033e7b  test    rcx, rcx
0x180033e7e  jz      loc_180033F16
0x180033e84  mov     rax, [rcx]
0x180033e87  lea     r8, [rbp+57h+var_80]
0x180033e8b  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x180033e92  mov     rax, [rax+28h]
0x180033e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e9b  mov     eax, 0Dh
0x180033ea0  cmp     ax, [rbp+57h+var_80]
0x180033ea4  jnz     short loc_180033EC0
0x180033ea6  mov     rcx, [rbp+57h+var_78]
0x180033eaa  lea     r8, [rsi+1E0h]
0x180033eb1  lea     rdx, _GUID_627d2ca6_e1cd_4898_999d_101308f1d431
0x180033eb8  mov     rax, [rcx]
0x180033ebb  mov     rax, [rax]
0x180033ebe  jmp     short loc_180033F11
0x180033ec0  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180033ec7  lea     rbx, [rsi+1E0h]
0x180033ece  mov     r8, rbx
0x180033ed1  lea     rdx, [rbp+57h+var_60]
0x180033ed5  lea     rcx, [rbp+57h+pvar]
0x180033ed9  movdqu  [rbp+57h+var_60], xmm0
0x180033ede  movdqu  xmmword ptr [rbp+57h+pvar], xmm0
0x180033ee3  call    cs:__imp_MFCreateTelemetrySession
0x180033eea  nop     dword ptr [rax+rax+00h]
0x180033eef  mov     rdx, [rbx]
0x180033ef2  lea     rcx, [rbp+57h+var_80]
0x180033ef6  call    ??4CMFPropVariant@@QEAAAEAV0@PEAUIUnknown@@@Z; CMFPropVariant::operator=(IUnknown *)
0x180033efb  mov     rcx, [rbp+57h+ppStore]
0x180033eff  lea     r8, [rbp+57h+var_80]
0x180033f03  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x180033f0a  mov     rax, [rcx]
0x180033f0d  mov     rax, [rax+30h]
0x180033f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f16  mov     edi, 1
0x180033f1b  test    r14, r14
0x180033f1e  jz      loc_180034023
0x180033f24  xorps   xmm0, xmm0
0x180033f27  lea     rcx, [rbp+57h+pvar]; void *
0x180033f2b  xor     eax, eax
0x180033f2d  mov     r8, r13; Size
0x180033f30  xor     edx, edx; Val
0x180033f32  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180033f36  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180033f3a  call    cs:__imp_memset
0x180033f41  nop     dword ptr [rax+rax+00h]
0x180033f46  mov     rax, [r14]
0x180033f49  lea     r8, [rbp+57h+pvar]
0x180033f4d  lea     rdx, qword_1800D9D28
0x180033f54  mov     rcx, r14
0x180033f57  mov     rax, [rax+28h]
0x180033f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f60  or      r13d, 0FFFFFFFFh
0x180033f64  lea     ebx, [rdi+0Ah]
0x180033f67  test    eax, eax
0x180033f69  js      short loc_180033FA7
0x180033f6b  cmp     bx, word ptr [rbp+57h+pvar]
0x180033f6f  jnz     short loc_180033FA7
0x180033f71  cmp     r13w, word ptr [rbp+57h+pvar+8]
0x180033f76  jnz     short loc_180033FA7
0x180033f78  cmp     cs:byte_1800EACCB, 8
0x180033f7f  jb      short loc_180033FA1
0x180033f81  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f88  lea     edx, [rdi+7Ah]
0x180033f8b  mov     r9, rsi
0x180033f8e  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x180033f95  mov     rcx, [rcx+88h]
0x180033f9c  call    WPP_SF_q
0x180033fa1  mov     [rsi+1D0h], edi
0x180033fa7  lea     rcx, [rbp+57h+pvar]; pvar
0x180033fab  call    cs:__imp_PropVariantClear
0x180033fb2  nop     dword ptr [rax+rax+00h]
0x180033fb7  mov     rax, [r14]
0x180033fba  lea     r8, [rbp+57h+pvar]
0x180033fbe  lea     rdx, qword_1800D9D10
0x180033fc5  mov     rcx, r14
0x180033fc8  mov     rax, [rax+28h]
0x180033fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fd1  test    eax, eax
0x180033fd3  js      short loc_180034013
0x180033fd5  cmp     bx, word ptr [rbp+57h+pvar]
0x180033fd9  jnz     short loc_180034013
0x180033fdb  cmp     r13w, word ptr [rbp+57h+pvar+8]
0x180033fe0  jnz     short loc_180034013
0x180033fe2  cmp     cs:byte_1800EACCB, 8
0x180033fe9  jb      short loc_18003400D
0x180033feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180033ff2  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x180033ff9  mov     edx, 7Ch ; '|'
0x180033ffe  mov     r9, rsi
0x180034001  mov     rcx, [rcx+88h]
0x180034008  call    WPP_SF_q
0x18003400d  mov     [rsi+1D4h], edi
0x180034013  lea     rcx, [rbp+57h+pvar]; pvar
0x180034017  call    cs:__imp_PropVariantClear
0x18003401e  nop     dword ptr [rax+rax+00h]
0x180034023  cmp     dword ptr [rsi+14h], 0
0x180034027  jl      loc_18003415B
0x18003402d  mov     r14d, [rsi+18h]
0x180034031  test    r14d, r14d
0x180034034  jle     loc_18003415B
0x18003403a  mov     edx, r14d
0x18003403d  lea     rcx, [rsi+10h]
0x180034041  call    ?GetBuffer@?$CMFBaseStringT@G@@QEAAPEAGJ@Z; CMFBaseStringT<ushort>::GetBuffer(long)
0x180034046  mov     rcx, rax
0x180034049  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180034050  nop     dword ptr [rax+rax+00h]
0x180034055  mov     rcx, rax; Str
0x180034058  lea     rdx, aMsdvd; "msdvd:"
0x18003405f  call    cs:__imp_wcsstr
0x180034066  nop     dword ptr [rax+rax+00h]
0x18003406b  test    rax, rax
0x18003406e  jz      loc_18003415B
0x180034074  mov     edx, r14d
0x180034077  lea     rcx, [rsi+10h]
0x18003407b  call    ?GetBuffer@?$CMFBaseStringT@G@@QEAAPEAGJ@Z; CMFBaseStringT<ushort>::GetBuffer(long)
0x180034080  mov     rcx, rax
0x180034083  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18003408a  nop     dword ptr [rax+rax+00h]
0x18003408f  mov     rcx, rax; Str
0x180034092  lea     rdx, aVideoTs; "video_ts"
0x180034099  call    cs:__imp_wcsstr
0x1800340a0  nop     dword ptr [rax+rax+00h]
0x1800340a5  test    rax, rax
0x1800340a8  jz      loc_18003415B
0x1800340ae  mov     rcx, rsi; this
0x1800340b1  mov     [rsi+1D8h], edi
0x1800340b7  call    ?CreateDVDGraph@CDShowWrapper@@IEAAJXZ; CDShowWrapper::CreateDVDGraph(void)
0x1800340bc  mov     ebx, eax
0x1800340be  test    eax, eax
0x1800340c0  jns     loc_180034221
0x1800340c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800340cd  test    rcx, rcx
0x1800340d0  jnz     short loc_180034119
0x1800340d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800340d9  nop     dword ptr [rax+rax+00h]
0x1800340de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800340e5  mov     rcx, rax
0x1800340e8  test    rax, rax
0x1800340eb  jz      short loc_18003410B
0x1800340ed  mov     rax, [rax]
0x1800340f0  mov     edx, 7F0h
0x1800340f5  mov     rax, [rax+8]
0x1800340f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340fe  test    eax, eax
0x180034100  jz      short loc_18003410B
0x180034102  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034109  jmp     short loc_180034119
0x18003410b  lea     rcx, qword_1800EB130; this
0x180034112  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180034119  cmp     byte ptr [rcx+8], 0
0x18003411d  jz      short loc_180034144
0x18003411f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034124  cmp     [rax+7CCh], ebx
0x18003412a  jz      short loc_180034144
0x18003412c  mov     r9d, ebx; int
0x18003412f  lea     rdx, aCdshowwrapperI_0; "CDShowWrapper::Initialize"
0x180034136  mov     r8d, 6D9h; int
0x18003413c  mov     rcx, rax; this
0x18003413f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034144  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18003414b  jb      loc_180034221
0x180034151  mov     edx, 7Dh ; '}'
0x180034156  jmp     loc_180034203
0x18003415b  mov     rax, [rsi]
0x18003415e  mov     rcx, rsi
0x180034161  mov     rax, [rax+0A0h]
0x180034168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003416d  mov     ebx, eax
0x18003416f  test    eax, eax
0x180034171  jns     loc_180034221
0x180034177  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003417e  test    rcx, rcx
0x180034181  jnz     short loc_1800341CA
0x180034183  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003418a  nop     dword ptr [rax+rax+00h]
0x18003418f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034196  mov     rcx, rax
0x180034199  test    rax, rax
0x18003419c  jz      short loc_1800341BC
0x18003419e  mov     rax, [rax]
0x1800341a1  mov     edx, 7F0h
0x1800341a6  mov     rax, [rax+8]
0x1800341aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341af  test    eax, eax
0x1800341b1  jz      short loc_1800341BC
0x1800341b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800341ba  jmp     short loc_1800341CA
0x1800341bc  lea     rcx, qword_1800EB130; this
0x1800341c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800341ca  cmp     byte ptr [rcx+8], 0
0x1800341ce  jz      short loc_1800341F5
0x1800341d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800341d5  cmp     [rax+7CCh], ebx
0x1800341db  jz      short loc_1800341F5
0x1800341dd  mov     r9d, ebx; int
0x1800341e0  lea     rdx, aCdshowwrapperI_0; "CDShowWrapper::Initialize"
0x1800341e7  mov     r8d, 6DDh; int
0x1800341ed  mov     rcx, rax; this
0x1800341f0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800341f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800341fc  jb      short loc_180034221
0x1800341fe  mov     edx, 7Eh ; '~'
0x180034203  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
