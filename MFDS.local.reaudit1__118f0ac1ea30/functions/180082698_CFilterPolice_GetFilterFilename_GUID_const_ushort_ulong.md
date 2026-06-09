# CFilterPolice::GetFilterFilename(_GUID const &,ushort *,ulong)

- ea: `0x180082698`
- end: `0x180082cd8`
- name: `?GetFilterFilename@CFilterPolice@@IEAAJAEBU_GUID@@PEAGK@Z`
- size: `1600`
- prototype: `int(CFilterPolice *__hidden this, const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180062868`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180023f20`
- `0x180032a50`
- `0x18004840c`
- `0x18004f520`
- `0x180051ce4`
- `0x180074160`
- `0x1800765a0`
- `0x18007bd58`
- `0x180082698`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800827fe`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800828de`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800827fe`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800828de`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180082c59`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180082c59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082c8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082c8f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180082724`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180082724`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082c68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082c68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180082c19`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180082c19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180082c3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180082c3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800829e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800829e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180082aae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180082aae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180082c7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180082c7e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180082c00`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180082c00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082746`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008284e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082932`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082a07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082ad5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082b78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082746`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008284e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082932`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082a07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082ad5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082b78`

## string_xrefs

- `0x1800826ca`: `\CLSID\`

## pseudocode

```c
__int64 __fastcall CFilterPolice::GetFilterFilename(CFilterPolice *this, const struct _GUID *a2, unsigned __int16 *a3)
{
  HRESULT v6; // ebx
  CallStackTracing *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  LPOLESTR v11; // rbx
  size_t v12; // rax
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  size_t v16; // rax
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  const WCHAR *Buffer; // rax
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  HMODULE Library; // rax
  HMODULE v32; // rdi
  _BYTE v34[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v41; // [rsp+5Ch] [rbp-A4h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF

  CMFBaseStringT<unsigned short>::CMFBaseStringT<unsigned short>(v40, L"\\CLSID\\");
  lpsz = 0;
  hKey = 0;
  Type = 0;
  cbData = 520;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v34, "CFilterPolice::GetFilterFilename", 4885);
  v6 = StringFromCLSID(a2, &lpsz);
  if ( v6 < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CFilterPolice::GetFilterFilename", 4885, v6);
    }
    if ( g_wppLevels )
    {
      v10 = 433;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, this, v6);
      goto LABEL_80;
    }
    goto LABEL_80;
  }
  v11 = lpsz;
  v35 = -1;
  if ( lpsz )
  {
    v12 = wcslen(lpsz);
    if ( (int)UIntPtrToLong(v12, &v35) < 0 )
    {
      v6 = -2147024785;
      v41 = -2147024785;
      goto LABEL_18;
    }
    v6 = CMFBaseStringT<unsigned short>::_Append(v40, v11, (unsigned int)v35);
    if ( v6 < 0 )
    {
LABEL_18:
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( *((_DWORD *)v15 + 499) != v6 )
          CallStackContext::TraceFailure(v15, "CFilterPolice::GetFilterFilename", 4887, v6);
      }
      if ( g_wppLevels )
      {
        v10 = 434;
        goto LABEL_12;
      }
      goto LABEL_80;
    }
  }
  v35 = -1;
  v16 = wcslen(L"\\InprocServer32");
  if ( (int)UIntPtrToLong(v16, &v35) >= 0 )
  {
    v6 = CMFBaseStringT<unsigned short>::_Append(v40, L"\\InprocServer32", (unsigned int)v35);
    if ( v6 >= 0 )
    {
      Buffer = (const WCHAR *)CMFBaseStringT<unsigned short>::GetBuffer(v40, 0);
      if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, Buffer, 0, 0x20019u, &hKey) )
      {
        v21 = CallStackTracing::s_wpInstance;
        v6 = -2147467259;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext(v21);
          if ( *((_DWORD *)v23 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v23, "CFilterPolice::GetFilterFilename", 4892, -2147467259);
        }
        if ( !g_wppLevels )
          goto LABEL_80;
        v24 = 436;
      }
      else if ( RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)a3, &cbData) )
      {
        v25 = CallStackTracing::s_wpInstance;
        v6 = -2147467259;
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
          if ( *((_DWORD *)v27 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v27, "CFilterPolice::GetFilterFilename", 4897, -2147467259);
        }
        if ( !g_wppLevels )
          goto LABEL_80;
        v24 = 437;
      }
      else
      {
        if ( Type == 1 )
        {
          if ( PathIsRelativeW(a3) )
          {
            Library = LoadLibraryExW(a3, 0, 1u);
            v32 = Library;
            if ( Library )
            {
              if ( GetModuleFileNameW(Library, Filename, 0x104u) )
                _o_wcscpy_s(a3, 260, Filename);
              FreeLibrary(v32);
            }
          }
          goto LABEL_80;
        }
        v28 = CallStackTracing::s_wpInstance;
        v6 = -2147467259;
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
          if ( *((_DWORD *)v30 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v30, "CFilterPolice::GetFilterFilename", 4902, -2147467259);
        }
        if ( !g_wppLevels )
          goto LABEL_80;
        v24 = 438;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        this,
        -2147467259);
      goto LABEL_80;
    }
  }
  else
  {
    v6 = -2147024785;
    v41 = -2147024785;
  }
  v17 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext(v17);
    if ( *((_DWORD *)v19 + 499) != v6 )
      CallStackContext::TraceFailure(v19, "CFilterPolice::GetFilterFilename", 4888, v6);
  }
  if ( g_wppLevels )
  {
    v10 = 435;
    goto LABEL_12;
  }
LABEL_80:
  if ( hKey )
    RegCloseKey(hKey);
  CoTaskMemFree(lpsz);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v34);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(v40);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180082698  mov     [rsp-8+arg_18], rbx
0x18008269d  push    rbp
0x18008269e  push    rsi
0x18008269f  push    rdi
0x1800826a0  push    r12
0x1800826a2  push    r14
0x1800826a4  lea     rbp, [rsp-190h]
0x1800826ac  sub     rsp, 290h
0x1800826b3  mov     rax, cs:__security_cookie
0x1800826ba  xor     rax, rsp
0x1800826bd  mov     [rbp+1B0h+var_30], rax
0x1800826c4  mov     rbx, rdx
0x1800826c7  mov     r14, rcx
0x1800826ca  lea     rdx, aClsid_0; "\\CLSID\\"
0x1800826d1  mov     rsi, r8
0x1800826d4  lea     rcx, [rsp+2B0h+var_258]
0x1800826d9  call    ??0?$CMFBaseStringT@G@@QEAA@PEBGJ@Z; CMFBaseStringT<ushort>::CMFBaseStringT<ushort>(ushort const *,long)
0x1800826de  mov     edi, 1315h
0x1800826e3  mov     [rsp+2B0h+lpsz], 0
0x1800826ec  lea     r12, aCfilterpoliceG_0; "CFilterPolice::GetFilterFilename"
0x1800826f3  mov     [rsp+2B0h+hKey], 0
0x1800826fc  mov     r8d, edi; int
0x1800826ff  mov     [rsp+2B0h+Type], 0
0x180082707  mov     rdx, r12; char *
0x18008270a  mov     [rsp+2B0h+cbData], 208h
0x180082712  lea     rcx, [rsp+2B0h+var_280]; this
0x180082717  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008271c  lea     rdx, [rsp+2B0h+lpsz]; lplpsz
0x180082721  mov     rcx, rbx; rclsid
0x180082724  call    cs:__imp_StringFromCLSID
0x18008272b  nop     dword ptr [rax+rax+00h]
0x180082730  mov     ebx, eax
0x180082732  test    eax, eax
0x180082734  jns     loc_1800827E6
0x18008273a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082741  test    rcx, rcx
0x180082744  jnz     short loc_18008278D
0x180082746  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008274d  nop     dword ptr [rax+rax+00h]
0x180082752  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082759  mov     rcx, rax
0x18008275c  test    rax, rax
0x18008275f  jz      short loc_18008277F
0x180082761  mov     rax, [rax]
0x180082764  mov     edx, 7F0h
0x180082769  mov     rax, [rax+8]
0x18008276d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082772  test    eax, eax
0x180082774  jz      short loc_18008277F
0x180082776  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008277d  jmp     short loc_18008278D
0x18008277f  lea     rcx, qword_1800EB130; this
0x180082786  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008278d  cmp     byte ptr [rcx+8], 0
0x180082791  jz      short loc_1800827B1
0x180082793  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082798  cmp     [rax+7CCh], ebx
0x18008279e  jz      short loc_1800827B1
0x1800827a0  mov     r9d, ebx; int
0x1800827a3  mov     r8d, edi; int
0x1800827a6  mov     rdx, r12; char *
0x1800827a9  mov     rcx, rax; this
0x1800827ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800827b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800827b8  jb      loc_180082C74
0x1800827be  mov     edx, 1B1h
0x1800827c3  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x1800827c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800827ce  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x1800827d5  mov     r9, r14
0x1800827d8  mov     rcx, [rcx+10h]
0x1800827dc  call    WPP_SF_qD
0x1800827e1  jmp     loc_180082C74
0x1800827e6  mov     rbx, [rsp+2B0h+lpsz]
0x1800827eb  or      edi, 0FFFFFFFFh
0x1800827ee  mov     [rsp+2B0h+var_278], edi
0x1800827f2  test    rbx, rbx
0x1800827f5  jz      loc_1800828D3
0x1800827fb  mov     rcx, rbx; String
0x1800827fe  call    cs:__imp_wcslen
0x180082805  nop     dword ptr [rax+rax+00h]
0x18008280a  mov     rcx, rax; unsigned __int64
0x18008280d  lea     rdx, [rsp+2B0h+var_278]; int *
0x180082812  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180082817  test    eax, eax
0x180082819  jns     short loc_180082826
0x18008281b  mov     ebx, 8007006Fh
0x180082820  mov     [rsp+2B0h+var_254], ebx
0x180082824  jmp     short loc_180082842
0x180082826  mov     r8d, [rsp+2B0h+var_278]
0x18008282b  lea     rcx, [rsp+2B0h+var_258]
0x180082830  mov     rdx, rbx
0x180082833  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x180082838  mov     ebx, eax
0x18008283a  test    eax, eax
0x18008283c  jns     loc_1800828D3
0x180082842  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082849  test    rcx, rcx
0x18008284c  jnz     short loc_180082895
0x18008284e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082855  nop     dword ptr [rax+rax+00h]
0x18008285a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082861  mov     rcx, rax
0x180082864  test    rax, rax
0x180082867  jz      short loc_180082887
0x180082869  mov     rax, [rax]
0x18008286c  mov     edx, 7F0h
0x180082871  mov     rax, [rax+8]
0x180082875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008287a  test    eax, eax
0x18008287c  jz      short loc_180082887
0x18008287e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082885  jmp     short loc_180082895
0x180082887  lea     rcx, qword_1800EB130; this
0x18008288e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082895  cmp     byte ptr [rcx+8], 0
0x180082899  jz      short loc_1800828BC
0x18008289b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800828a0  cmp     [rax+7CCh], ebx
0x1800828a6  jz      short loc_1800828BC
0x1800828a8  mov     r9d, ebx; int
0x1800828ab  mov     r8d, 1317h; int
0x1800828b1  mov     rdx, r12; char *
0x1800828b4  mov     rcx, rax; this
0x1800828b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800828bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800828c3  jb      loc_180082C74
0x1800828c9  mov     edx, 1B2h
0x1800828ce  jmp     loc_1800827C3
0x1800828d3  lea     rcx, aInprocserver32_0; "\\InprocServer32"
0x1800828da  mov     [rsp+2B0h+var_278], edi
0x1800828de  call    cs:__imp_wcslen
0x1800828e5  nop     dword ptr [rax+rax+00h]
0x1800828ea  mov     rcx, rax; unsigned __int64
0x1800828ed  lea     rdx, [rsp+2B0h+var_278]; int *
0x1800828f2  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x1800828f7  test    eax, eax
0x1800828f9  jns     short loc_180082906
0x1800828fb  mov     ebx, 8007006Fh
0x180082900  mov     [rsp+2B0h+var_254], ebx
0x180082904  jmp     short loc_180082926
0x180082906  mov     r8d, [rsp+2B0h+var_278]
0x18008290b  lea     rdx, aInprocserver32_0; "\\InprocServer32"
0x180082912  lea     rcx, [rsp+2B0h+var_258]
0x180082917  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x18008291c  mov     ebx, eax
0x18008291e  test    eax, eax
0x180082920  jns     loc_1800829B7
0x180082926  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008292d  test    rcx, rcx
0x180082930  jnz     short loc_180082979
0x180082932  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082939  nop     dword ptr [rax+rax+00h]
0x18008293e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082945  mov     rcx, rax
0x180082948  test    rax, rax
0x18008294b  jz      short loc_18008296B
0x18008294d  mov     rax, [rax]
0x180082950  mov     edx, 7F0h
0x180082955  mov     rax, [rax+8]
0x180082959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008295e  test    eax, eax
0x180082960  jz      short loc_18008296B
0x180082962  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082969  jmp     short loc_180082979
0x18008296b  lea     rcx, qword_1800EB130; this
0x180082972  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082979  cmp     byte ptr [rcx+8], 0
0x18008297d  jz      short loc_1800829A0
0x18008297f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082984  cmp     [rax+7CCh], ebx
0x18008298a  jz      short loc_1800829A0
0x18008298c  mov     r9d, ebx; int
0x18008298f  mov     r8d, 1318h; int
0x180082995  mov     rdx, r12; char *
0x180082998  mov     rcx, rax; this
0x18008299b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800829a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800829a7  jb      loc_180082C74
0x1800829ad  mov     edx, 1B3h
0x1800829b2  jmp     loc_1800827C3
0x1800829b7  xor     edx, edx
0x1800829b9  lea     rcx, [rsp+2B0h+var_258]
0x1800829be  call    ?GetBuffer@?$CMFBaseStringT@G@@QEAAPEAGJ@Z; CMFBaseStringT<ushort>::GetBuffer(long)
0x1800829c3  mov     rdx, rax; lpSubKey
0x1800829c6  mov     r9d, 20019h; samDesired
0x1800829cc  lea     rax, [rsp+2B0h+hKey]
0x1800829d1  xor     r8d, r8d; ulOptions
0x1800829d4  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800829db  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800829e0  call    cs:__imp_RegOpenKeyExW
0x1800829e7  nop     dword ptr [rax+rax+00h]
0x1800829ec  test    eax, eax
0x1800829ee  jz      loc_180082A90
0x1800829f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800829fb  mov     edi, 80004005h
0x180082a00  mov     ebx, edi
0x180082a02  test    rcx, rcx
0x180082a05  jnz     short loc_180082A4E
0x180082a07  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082a0e  nop     dword ptr [rax+rax+00h]
0x180082a13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082a1a  mov     rcx, rax
0x180082a1d  test    rax, rax
0x180082a20  jz      short loc_180082A40
0x180082a22  mov     rax, [rax]
0x180082a25  mov     edx, 7F0h
0x180082a2a  mov     rax, [rax+8]
0x180082a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a33  test    eax, eax
0x180082a35  jz      short loc_180082A40
0x180082a37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082a3e  jmp     short loc_180082A4E
0x180082a40  lea     rcx, qword_1800EB130; this
0x180082a47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082a4e  cmp     byte ptr [rcx+8], 0
0x180082a52  jz      short loc_180082A75
0x180082a54  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082a59  cmp     [rax+7CCh], edi
0x180082a5f  jz      short loc_180082A75
0x180082a61  mov     r9d, edi; int
0x180082a64  mov     r8d, 131Ch; int
0x180082a6a  mov     rdx, r12; char *
0x180082a6d  mov     rcx, rax; this
0x180082a70  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082a75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082a7c  jb      loc_180082C74
0x180082a82  mov     edx, 1B4h
0x180082a87  mov     dword ptr [rsp+2B0h+phkResult], edi
0x180082a8b  jmp     loc_1800827C7
0x180082a90  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180082a95  lea     rax, [rsp+2B0h+cbData]
0x180082a9a  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x180082a9f  lea     r9, [rsp+2B0h+Type]; lpType
0x180082aa4  xor     r8d, r8d; lpReserved
0x180082aa7  mov     [rsp+2B0h+phkResult], rsi; lpData
0x180082aac  xor     edx, edx; lpValueName
0x180082aae  call    cs:__imp_RegQueryValueExW
0x180082ab5  nop     dword ptr [rax+rax+00h]
0x180082aba  test    eax, eax
0x180082abc  jz      loc_180082B5A
0x180082ac2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082ac9  mov     edi, 80004005h
0x180082ace  mov     ebx, edi
0x180082ad0  test    rcx, rcx
0x180082ad3  jnz     short loc_180082B1C
0x180082ad5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082adc  nop     dword ptr [rax+rax+00h]
0x180082ae1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082ae8  mov     rcx, rax
0x180082aeb  test    rax, rax
0x180082aee  jz      short loc_180082B0E
0x180082af0  mov     rax, [rax]
0x180082af3  mov     edx, 7F0h
0x180082af8  mov     rax, [rax+8]
0x180082afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b01  test    eax, eax
0x180082b03  jz      short loc_180082B0E
0x180082b05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082b0c  jmp     short loc_180082B1C
0x180082b0e  lea     rcx, qword_1800EB130; this
0x180082b15  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082b1c  cmp     byte ptr [rcx+8], 0
0x180082b20  jz      short loc_180082B43
0x180082b22  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082b27  cmp     [rax+7CCh], edi
0x180082b2d  jz      short loc_180082B43
0x180082b2f  mov     r9d, edi; int
0x180082b32  mov     r8d, 1321h; int
0x180082b38  mov     rdx, r12; char *
0x180082b3b  mov     rcx, rax; this
0x180082b3e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082b43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082b4a  jb      loc_180082C74
0x180082b50  mov     edx, 1B5h
0x180082b55  jmp     loc_180082A87
0x180082b5a  cmp     [rsp+2B0h+Type], 1
0x180082b5f  jz      loc_180082BFD
0x180082b65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082b6c  mov     edi, 80004005h
0x180082b71  mov     ebx, edi
0x180082b73  test    rcx, rcx
0x180082b76  jnz     short loc_180082BBF
0x180082b78  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082b7f  nop     dword ptr [rax+rax+00h]
0x180082b84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082b8b  mov     rcx, rax
0x180082b8e  test    rax, rax
0x180082b91  jz      short loc_180082BB1
0x180082b93  mov     rax, [rax]
0x180082b96  mov     edx, 7F0h
0x180082b9b  mov     rax, [rax+8]
0x180082b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ba4  test    eax, eax
0x180082ba6  jz      short loc_180082BB1
0x180082ba8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082baf  jmp     short loc_180082BBF
0x180082bb1  lea     rcx, qword_1800EB130; this
0x180082bb8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082bbf  cmp     byte ptr [rcx+8], 0
  ... truncated ...
```
