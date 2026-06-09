# CFrameWebOC::Navigate(ulong,IBindCtx *,IBindStatusCallback *,IHlink *)

- ea: `0x180b437a0`
- end: `0x180b43cfc`
- name: `?Navigate@CFrameWebOC@@QEAAJKPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlink@@@Z`
- size: `1372`
- prototype: `__int64 __fastcall(CFrameWebOC *__hidden this, unsigned int, struct IBindCtx *, struct IBindStatusCallback *, struct IHlink *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1801c0acc`
- `0x18043c328`
- `0x1804fadf8`
- `0x180717fc4`
- `0x180b437a0`
- `0x1810c2caa`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180b43a6f`
- `msvcrt!memcpy_s` at `0x180b43a6f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNIW` at `0x180b43b1c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpNIW` at `0x180b43b1c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180b43afd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180b43afd`
- `iertutil!CreateUri` at `0x180b4397b`
- `iertutil!CreateUri` at `0x180b4397b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43b54`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43b9c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43c99`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43ca3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43cad`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43b54`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43b9c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43c99`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43ca3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180b43cad`
- `ole32!CreateBindCtx` at `0x180b43933`
- `ole32!CreateBindCtx` at `0x180b43933`
- `urlmon!ReleaseBindInfo` at `0x180b43c50`
- `urlmon!ReleaseBindInfo` at `0x180b43c50`
- `OLEAUT32!__imp_SysAllocString` at `0x180b4390e`
- `OLEAUT32!__imp_SysAllocString` at `0x180b4398f`
- `OLEAUT32!__imp_SysAllocString` at `0x180b439a0`
- `OLEAUT32!__imp_SysAllocString` at `0x180b43b6f`
- `OLEAUT32!__imp_SysAllocString` at `0x180b43bc7`
- `OLEAUT32!__imp_SysAllocString` at `0x180b4390e`
- `OLEAUT32!__imp_SysAllocString` at `0x180b4398f`
- `OLEAUT32!__imp_SysAllocString` at `0x180b439a0`
- `OLEAUT32!__imp_SysAllocString` at `0x180b43b6f`
- `OLEAUT32!__imp_SysAllocString` at `0x180b43bc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43c46`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43cb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43cc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43cd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43c46`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43cb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43cc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180b43cd1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180b43c38`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180b43c38`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180b43a53`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180b43a53`

## pseudocode

```c
__int64 __fastcall CFrameWebOC::Navigate(
        CFrameWebOC *this,
        int a2,
        struct IBindCtx *a3,
        OLECHAR *a4,
        struct IHlink *a5)
{
  unsigned int v5; // ebx
  OLECHAR *v8; // r12
  unsigned __int16 *v9; // r13
  __int64 v10; // rsi
  OLECHAR *v11; // rdi
  struct IUnknown *v12; // rcx
  OLECHAR *v13; // rbx
  int v14; // edx
  int v15; // edi
  SAFEARRAY *v16; // r14
  SAFEARRAY *Vector; // rax
  int v18; // eax
  WCHAR *v19; // rbx
  const WCHAR *v20; // rdi
  PWSTR v21; // rax
  void *v22; // rsi
  const OLECHAR *v23; // rcx
  OLECHAR *v24; // rsi
  unsigned int v26; // [rsp+50h] [rbp-B8h]
  unsigned __int16 *v27; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v28; // [rsp+80h] [rbp-88h]
  OLECHAR *v29; // [rsp+88h] [rbp-80h] BYREF
  PCWSTR pszFirst; // [rsp+90h] [rbp-78h] BYREF
  LPBC ppbc; // [rsp+98h] [rbp-70h] BYREF
  int v32; // [rsp+A0h] [rbp-68h] BYREF
  struct IUnknown *v33; // [rsp+A8h] [rbp-60h] BYREF
  int v34; // [rsp+B0h] [rbp-58h] BYREF
  struct IUnknown *v35; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-48h] BYREF
  struct IUnknown *v37; // [rsp+C8h] [rbp-40h] BYREF
  IUri *ppURI; // [rsp+D0h] [rbp-38h] BYREF
  LPCWSTR pwzURI; // [rsp+D8h] [rbp-30h] BYREF
  OLECHAR *v40; // [rsp+E0h] [rbp-28h] BYREF
  OLECHAR *v41; // [rsp+E8h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+F0h] [rbp-18h]
  CFrameWebOC *v43; // [rsp+F8h] [rbp-10h]
  struct tagVARIANT v44; // [rsp+100h] [rbp-8h] BYREF
  struct tagVARIANT v45; // [rsp+118h] [rbp+10h] BYREF
  BINDINFO pbindinfo; // [rsp+138h] [rbp+30h] BYREF
  OLECHAR psz[264]; // [rsp+1B8h] [rbp+B0h] BYREF

  v5 = -2147467259;
  v43 = this;
  v37 = 0;
  v8 = 0;
  ppbc = 0;
  v9 = 0;
  pwzURI = 0;
  ppURI = 0;
  v27 = 0;
  v40 = 0;
  v41 = 0;
  if ( !a5 || (v10 = -1, a5 == (struct IHlink *)-1LL) )
  {
    v11 = 0;
    v24 = 0;
    goto LABEL_57;
  }
  ((void (__fastcall *)(struct IHlink *, OLECHAR **))a5->lpVtbl->GetTargetFrameName)(a5, &v41);
  v11 = 0;
  v5 = ((__int64 (__fastcall *)(struct IHlink *, __int64, struct IUnknown **, OLECHAR **))a5->lpVtbl->GetMonikerReference)(
         a5,
         1,
         &v37,
         &v40);
  if ( v5 )
    goto LABEL_55;
  if ( !a3 )
  {
    v5 = CreateBindCtx(0, &ppbc);
    if ( !v5 )
      goto LABEL_13;
LABEL_55:
    v24 = 0;
    goto LABEL_57;
  }
  v35 = 0;
  v33 = 0;
  ppbc = a3;
  ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->AddRef)(a3);
  ((void (__fastcall *)(LPBC, const wchar_t *, struct IUnknown **))ppbc->lpVtbl->GetObjectParam)(
    ppbc,
    L"__HTMLLOADOPTIONS",
    &v35);
  if ( !v35 )
  {
LABEL_10:
    v12 = v33;
    goto LABEL_11;
  }
  ((void (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v35->lpVtbl->QueryInterface)(
    v35,
    &IID_IHtmlLoadOptions,
    &v33);
  v12 = v33;
  if ( v33 )
  {
    v32 = 520;
    if ( !((unsigned int (__fastcall *)(struct IUnknown *, __int64, OLECHAR *, int *))v33->lpVtbl[1].QueryInterface)(
            v33,
            1,
            psz,
            &v32)
      && v32 )
    {
      v27 = SysAllocString(psz);
    }
    goto LABEL_10;
  }
LABEL_11:
  ReleaseInterface(v12);
  ReleaseInterface(v35);
LABEL_13:
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, LPBC, _QWORD, LPCWSTR *))v37->lpVtbl[6].Release)(
         v37,
         ppbc,
         0,
         &pwzURI);
  if ( v5 || (v5 = CreateUri(pwzURI, 0x3002B85u, 0, &ppURI)) != 0 )
  {
    v11 = v27;
    v24 = 0;
    goto LABEL_57;
  }
  v13 = SysAllocString(v41);
  bstrString = v13;
  v28 = SysAllocString(v40);
  v34 = 0;
  v14 = (4 * (a2 & 2)) | 0x2001;
  if ( a2 >= 0 )
    v14 = (4 * (a2 & 2)) | 1;
  v15 = v14 | 0x80;
  if ( (a2 & 0x200000) == 0 )
    v15 = v14;
  LODWORD(v29) = v15;
  memset_0(&pbindinfo.cbSize + 1, 0, 0x7Cu);
  pbindinfo.cbSize = 128;
  v16 = 0;
  v36 = 0;
  memset(&v45, 0, sizeof(v45));
  memset(&v44, 0, sizeof(v44));
  if ( !a4 )
    goto LABEL_44;
  if ( (*(int (__fastcall **)(OLECHAR *, int *, BINDINFO *))(*(_QWORD *)a4 + 64LL))(a4, &v34, &pbindinfo) >= 0
    && pbindinfo.stgmedData.tymed == 1 )
  {
    if ( pbindinfo.stgmedData.hBitmap )
    {
      if ( pbindinfo.cbstgmedData )
      {
        Vector = SafeArrayCreateVector(0x11u, 0, pbindinfo.cbstgmedData);
        v16 = Vector;
        if ( Vector )
        {
          memcpy_s(Vector->pvData, pbindinfo.cbstgmedData, pbindinfo.stgmedData.hBitmap, pbindinfo.cbstgmedData);
          v45.llVal = (LONGLONG)v16;
          v45.vt = 8209;
        }
      }
    }
  }
  v18 = (**(__int64 (__fastcall ***)(OLECHAR *, GUID *, __int64 *))a4)(a4, &IID_IHttpNegotiate, &v36);
  a4 = 0;
  if ( v18 < 0 )
    goto LABEL_44;
  pszFirst = 0;
  if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, PCWSTR *))(*(_QWORD *)v36 + 24LL))(
         v36,
         0,
         0,
         0,
         &pszFirst) < 0 )
  {
    v23 = pszFirst;
LABEL_40:
    if ( v23 && *v23 )
    {
      v8 = SysAllocString(v23);
      v44.vt = 8;
      v44.llVal = (LONGLONG)v8;
    }
    goto LABEL_43;
  }
  v19 = (WCHAR *)pszFirst;
  if ( pszFirst )
  {
    do
      ++v10;
    while ( pszFirst[v10] );
    v20 = &pszFirst[v10];
    while ( v19 < v20 )
    {
      v21 = StrStrIW(v19, L"\r\n");
      if ( !v21 )
      {
        *v19 = 0;
        break;
      }
      v22 = v21 + 2;
      if ( !StrCmpNIW(v19, L"Accept-Language:", 16) )
      {
        memmove_0(v19, v22, 2 * (((char *)v20 - (_BYTE *)v22) >> 1) + 2);
        break;
      }
      v19 = (WCHAR *)v22;
    }
    v23 = pszFirst;
    if ( !*pszFirst )
    {
      CoTaskMemFree((LPVOID)pszFirst);
      v23 = 0;
      pszFirst = 0;
    }
    v15 = (int)v29;
    goto LABEL_40;
  }
LABEL_43:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  CoTaskMemFree((LPVOID)pszFirst);
  v13 = bstrString;
LABEL_44:
  if ( ppbc )
  {
    v29 = a4;
    if ( !(unsigned int)GetBindContextParam(ppbc, (struct CStr *)&v29, 0) )
      v9 = SysAllocString(v29);
    CStr::_Free((CStr *)&v29);
  }
  v24 = v28;
  v26 = v15;
  v11 = v27;
  v5 = CWindow::SuperNavigateInternal(
         *((CWindow **)v43 + 7),
         ppURI,
         v28,
         v27,
         v13,
         v9,
         &v45,
         (struct IStream *)a4,
         &v44,
         v26,
         (unsigned int)a4,
         (struct IBindCtx *)a4,
         (int *)a4);
  if ( v16 )
    SafeArrayDestroy(v16);
  if ( v8 )
    SysFreeString(v8);
  ReleaseBindInfo(&pbindinfo);
  v8 = bstrString;
LABEL_57:
  ReleaseInterface(v37);
  ReleaseInterface((struct IUnknown *)ppbc);
  ReleaseInterface((struct IUnknown *)ppURI);
  CoTaskMemFree((LPVOID)pwzURI);
  CoTaskMemFree(v40);
  CoTaskMemFree(v41);
  SysFreeString(v8);
  SysFreeString(v11);
  SysFreeString(v24);
  SysFreeString(v9);
  return v5;
}

```

## disassembly

```asm
0x180b437a0  mov     rax, rsp
0x180b437a3  mov     [rax+20h], r9
0x180b437a7  mov     [rax+18h], r8
0x180b437ab  mov     [rax+10h], edx
0x180b437ae  mov     [rax+8], rcx
0x180b437b2  push    rbp
0x180b437b3  push    rbx
0x180b437b4  push    rsi
0x180b437b5  push    rdi
0x180b437b6  push    r12
0x180b437b8  push    r13
0x180b437ba  push    r14
0x180b437bc  push    r15
0x180b437be  lea     rbp, [rax-318h]
0x180b437c5  sub     rsp, 3D8h
0x180b437cc  mov     rax, cs:__security_cookie
0x180b437d3  xor     rax, rsp
0x180b437d6  mov     [rbp+310h+var_50], rax
0x180b437dd  mov     rax, [rbp+310h+arg_0]
0x180b437e4  mov     ebx, 80004005h
0x180b437e9  mov     rdi, [rbp+310h+arg_20]
0x180b437f0  mov     r14, [rbp+310h+arg_10]
0x180b437f7  mov     r15, [rbp+310h+arg_18]
0x180b437fe  mov     [rbp+310h+var_320], rax
0x180b43802  xor     eax, eax
0x180b43804  mov     [rbp+310h+var_350], rax
0x180b43808  mov     r12d, eax
0x180b4380b  mov     [rbp+310h+ppbc], rax
0x180b4380f  mov     r13d, eax
0x180b43812  mov     [rbp+310h+pwzURI], rax
0x180b43816  mov     [rbp+310h+ppURI], rax
0x180b4381a  mov     [rsp+410h+var_3A0], rax
0x180b4381f  mov     [rbp+310h+var_338], rax
0x180b43823  mov     [rbp+310h+var_330], rax
0x180b43827  test    rdi, rdi
0x180b4382a  jz      loc_180B43C65
0x180b43830  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180b43834  cmp     rdi, rsi
0x180b43837  jz      loc_180B43C65
0x180b4383d  mov     rax, [rdi]
0x180b43840  lea     rdx, [rbp+310h+var_330]
0x180b43844  mov     rcx, rdi
0x180b43847  mov     rax, [rax+60h]
0x180b4384b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b43850  mov     rax, [rdi]
0x180b43853  lea     r9, [rbp+310h+var_338]
0x180b43857  lea     r8, [rbp+310h+var_350]
0x180b4385b  mov     rcx, rdi
0x180b4385e  lea     edx, [rsi+2]
0x180b43861  mov     rax, [rax+30h]
0x180b43865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b4386a  xor     edi, edi
0x180b4386c  mov     ebx, eax
0x180b4386e  test    eax, eax
0x180b43870  jnz     loc_180B43C6D
0x180b43876  test    r14, r14
0x180b43879  jz      loc_180B4392D
0x180b4387f  mov     [rbp+310h+var_360], rdi
0x180b43883  mov     rcx, r14
0x180b43886  mov     [rbp+310h+var_370], rdi
0x180b4388a  mov     [rbp+310h+ppbc], r14
0x180b4388e  mov     rax, [r14]
0x180b43891  mov     rax, [rax+8]
0x180b43895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b4389a  mov     rcx, [rbp+310h+ppbc]
0x180b4389e  lea     r8, [rbp+310h+var_360]
0x180b438a2  lea     rdx, aHtmlloadoption; "__HTMLLOADOPTIONS"
0x180b438a9  mov     rax, [rcx]
0x180b438ac  mov     rax, [rax+50h]
0x180b438b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b438b5  mov     rcx, [rbp+310h+var_360]
0x180b438b9  test    rcx, rcx
0x180b438bc  jz      short loc_180B43919
0x180b438be  mov     rax, [rcx]
0x180b438c1  lea     r8, [rbp+310h+var_370]
0x180b438c5  lea     rdx, IID_IHtmlLoadOptions
0x180b438cc  mov     rax, [rax]
0x180b438cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b438d4  mov     rcx, [rbp+310h+var_370]
0x180b438d8  test    rcx, rcx
0x180b438db  jz      short loc_180B4391D
0x180b438dd  mov     [rbp+310h+var_378], 208h
0x180b438e4  lea     r9, [rbp+310h+var_378]
0x180b438e8  mov     rax, [rcx]
0x180b438eb  lea     r8, [rbp+310h+psz]
0x180b438f2  lea     edx, [rsi+2]
0x180b438f5  mov     rax, [rax+18h]
0x180b438f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b438fe  test    eax, eax
0x180b43900  jnz     short loc_180B43919
0x180b43902  cmp     [rbp+310h+var_378], edi
0x180b43905  jz      short loc_180B43919
0x180b43907  lea     rcx, [rbp+310h+psz]; psz
0x180b4390e  call    cs:__imp_SysAllocString
0x180b43914  mov     [rsp+410h+var_3A0], rax
0x180b43919  mov     rcx, [rbp+310h+var_370]; struct IUnknown *
0x180b4391d  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180b43922  mov     rcx, [rbp+310h+var_360]; struct IUnknown *
0x180b43926  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180b4392b  jmp     short loc_180B43943
0x180b4392d  lea     rdx, [rbp+310h+ppbc]; ppbc
0x180b43931  xor     ecx, ecx; reserved
0x180b43933  call    cs:__imp_CreateBindCtx
0x180b43939  mov     ebx, eax
0x180b4393b  test    eax, eax
0x180b4393d  jnz     loc_180B43C6D
0x180b43943  mov     rcx, [rbp+310h+var_350]
0x180b43947  lea     r9, [rbp+310h+pwzURI]
0x180b4394b  mov     rdx, [rbp+310h+ppbc]
0x180b4394f  xor     r8d, r8d
0x180b43952  mov     rax, [rcx]
0x180b43955  mov     rax, [rax+0A0h]
0x180b4395c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b43961  mov     ebx, eax
0x180b43963  test    eax, eax
0x180b43965  jnz     loc_180B43C72
0x180b4396b  mov     rcx, [rbp+310h+pwzURI]; pwzURI
0x180b4396f  lea     r9, [rbp+310h+ppURI]; ppURI
0x180b43973  xor     r8d, r8d; dwReserved
0x180b43976  mov     edx, 3002B85h; dwFlags
0x180b4397b  call    cs:__imp_CreateUri
0x180b43981  mov     ebx, eax
0x180b43983  test    eax, eax
0x180b43985  jnz     loc_180B43C72
0x180b4398b  mov     rcx, [rbp+310h+var_330]; psz
0x180b4398f  call    cs:__imp_SysAllocString
0x180b43995  mov     rcx, [rbp+310h+var_338]; psz
0x180b43999  mov     rbx, rax
0x180b4399c  mov     [rbp+310h+bstrString], rax
0x180b439a0  call    cs:__imp_SysAllocString
0x180b439a6  mov     r8d, [rbp+310h+arg_8]
0x180b439ad  mov     ecx, r8d
0x180b439b0  and     ecx, 2
0x180b439b3  mov     [rsp+78h], rax
0x180b439b8  shl     ecx, 2
0x180b439bb  or      ecx, 1
0x180b439be  mov     [rbp+310h+var_368], r12d
0x180b439c2  mov     edx, ecx
0x180b439c4  bts     edx, 0Dh
0x180b439c8  test    r8d, r8d
0x180b439cb  cmovns  edx, ecx
0x180b439ce  lea     rcx, [rbp+310h+pbindinfo+4]; void *
0x180b439d2  mov     edi, edx
0x180b439d4  bts     edi, 7
0x180b439d8  bt      r8d, 15h
0x180b439dd  cmovnb  edi, edx
0x180b439e0  xor     edx, edx; Val
0x180b439e2  mov     dword ptr [rbp+310h+var_390], edi
0x180b439e5  lea     r8d, [rdx+7Ch]; Size
0x180b439e9  call    memset_0
0x180b439ee  xor     eax, eax
0x180b439f0  mov     [rbp+310h+pbindinfo.cbSize], 80h
0x180b439f7  xor     r14d, r14d
0x180b439fa  mov     qword ptr [rbp+310h+var_300+10h], rax
0x180b439fe  mov     qword ptr [rbp+310h+var_318+10h], rax
0x180b43a02  xorps   xmm0, xmm0
0x180b43a05  mov     [rbp+310h+var_358], rax
0x180b43a09  xorps   xmm1, xmm1
0x180b43a0c  movups  xmmword ptr [rbp+310h+var_300], xmm0
0x180b43a10  movups  xmmword ptr [rbp+310h+var_318], xmm1
0x180b43a14  test    r15, r15
0x180b43a17  jz      loc_180B43BA6
0x180b43a1d  mov     rax, [r15]
0x180b43a20  lea     r8, [rbp+310h+pbindinfo]
0x180b43a24  lea     rdx, [rbp+310h+var_368]
0x180b43a28  mov     rcx, r15
0x180b43a2b  mov     rax, [rax+40h]
0x180b43a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b43a34  test    eax, eax
0x180b43a36  js      short loc_180B43A82
0x180b43a38  cmp     [rbp+310h+pbindinfo.stgmedData.tymed], 1
0x180b43a3c  jnz     short loc_180B43A82
0x180b43a3e  cmp     qword ptr [rbp+310h+pbindinfo.stgmedData.8], r12
0x180b43a42  jz      short loc_180B43A82
0x180b43a44  mov     r8d, [rbp+310h+pbindinfo.cbstgmedData]; cElements
0x180b43a48  test    r8d, r8d
0x180b43a4b  jz      short loc_180B43A82
0x180b43a4d  lea     ecx, [r14+11h]; vt
0x180b43a51  xor     edx, edx; lLbound
0x180b43a53  call    cs:__imp_SafeArrayCreateVector
0x180b43a59  mov     r14, rax
0x180b43a5c  test    rax, rax
0x180b43a5f  jz      short loc_180B43A82
0x180b43a61  mov     edx, [rbp+310h+pbindinfo.cbstgmedData]; DestinationSize
0x180b43a64  mov     r8, qword ptr [rbp+310h+pbindinfo.stgmedData.8]; Source
0x180b43a68  mov     r9d, edx; SourceSize
0x180b43a6b  mov     rcx, [rax+10h]; Destination
0x180b43a6f  call    cs:__imp_memcpy_s
0x180b43a75  mov     eax, 2011h
0x180b43a7a  mov     qword ptr [rbp+310h+var_300+8], r14
0x180b43a7e  mov     word ptr [rbp+310h+var_300], ax
0x180b43a82  mov     rax, [r15]
0x180b43a85  lea     r8, [rbp+310h+var_358]
0x180b43a89  lea     rdx, IID_IHttpNegotiate
0x180b43a90  mov     rcx, r15
0x180b43a93  mov     rax, [rax]
0x180b43a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b43a9b  xor     r15d, r15d
0x180b43a9e  test    eax, eax
0x180b43aa0  js      loc_180B43BA6
0x180b43aa6  mov     rcx, [rbp+310h+var_358]
0x180b43aaa  lea     rdx, [rbp+310h+pszFirst]
0x180b43aae  mov     [rbp+310h+pszFirst], r15
0x180b43ab2  xor     r9d, r9d
0x180b43ab5  mov     [rsp+410h+var_3F0], rdx
0x180b43aba  xor     r8d, r8d
0x180b43abd  xor     edx, edx
0x180b43abf  mov     rax, [rcx]
0x180b43ac2  mov     rax, [rax+18h]
0x180b43ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b43acb  test    eax, eax
0x180b43acd  js      loc_180B43C5C
0x180b43ad3  mov     rbx, [rbp+310h+pszFirst]
0x180b43ad7  test    rbx, rbx
0x180b43ada  jz      loc_180B43B85
0x180b43ae0  inc     rsi
0x180b43ae3  cmp     [rbx+rsi*2], r15w
0x180b43ae8  jnz     short loc_180B43AE0
0x180b43aea  lea     rdi, [rbx+rsi*2]
0x180b43aee  cmp     rbx, rdi
0x180b43af1  jnb     short loc_180B43B4A
0x180b43af3  lea     rdx, asc_1814088E4; "\r\n"
0x180b43afa  mov     rcx, rbx; pszFirst
0x180b43afd  call    cs:__imp_StrStrIW
0x180b43b03  test    rax, rax
0x180b43b06  jz      short loc_180B43B46
0x180b43b08  mov     r8d, 10h; nChar
0x180b43b0e  lea     rdx, aAcceptLanguage_2; "Accept-Language:"
0x180b43b15  mov     rcx, rbx; psz1
0x180b43b18  lea     rsi, [rax+4]
0x180b43b1c  call    cs:__imp_StrCmpNIW
0x180b43b22  test    eax, eax
0x180b43b24  jz      short loc_180B43B2B
0x180b43b26  mov     rbx, rsi
0x180b43b29  jmp     short loc_180B43AEE
0x180b43b2b  sub     rdi, rsi
0x180b43b2e  mov     rdx, rsi; Src
0x180b43b31  sar     rdi, 1
0x180b43b34  mov     rcx, rbx; void *
0x180b43b37  lea     r8, ds:2[rdi*2]; Size
0x180b43b3f  call    memmove_0
0x180b43b44  jmp     short loc_180B43B4A
0x180b43b46  mov     [rbx], r15w
0x180b43b4a  mov     rcx, [rbp+310h+pszFirst]; pv
0x180b43b4e  cmp     [rcx], r15w
0x180b43b52  jnz     short loc_180B43B61
0x180b43b54  call    cs:__imp_CoTaskMemFree
0x180b43b5a  mov     rcx, r15; psz
0x180b43b5d  mov     [rbp+310h+pszFirst], rcx
0x180b43b61  mov     edi, dword ptr [rbp+310h+var_390]
0x180b43b64  test    rcx, rcx
0x180b43b67  jz      short loc_180B43B85
0x180b43b69  cmp     [rcx], r15w
0x180b43b6d  jz      short loc_180B43B85
0x180b43b6f  call    cs:__imp_SysAllocString
0x180b43b75  mov     r12, rax
0x180b43b78  mov     eax, 8
0x180b43b7d  mov     word ptr [rbp+310h+var_318], ax
0x180b43b81  mov     qword ptr [rbp+310h+var_318+8], r12
0x180b43b85  mov     rdx, [rbp+310h+var_358]
0x180b43b89  mov     rcx, [rdx]
0x180b43b8c  mov     rax, [rcx+10h]
0x180b43b90  mov     rcx, rdx
0x180b43b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b43b98  mov     rcx, [rbp+310h+pszFirst]; pv
0x180b43b9c  call    cs:__imp_CoTaskMemFree
0x180b43ba2  mov     rbx, [rbp+310h+bstrString]
0x180b43ba6  mov     rcx, [rbp+310h+ppbc]; struct IBindCtx *
0x180b43baa  test    rcx, rcx
0x180b43bad  jz      short loc_180B43BD9
0x180b43baf  xor     r8d, r8d; unsigned __int16 *
0x180b43bb2  mov     [rbp+310h+var_390], r15
0x180b43bb6  lea     rdx, [rbp+310h+var_390]; struct CStr *
0x180b43bba  call    ?GetBindContextParam@@YAJPEAUIBindCtx@@PEAVCStr@@PEAG@Z; GetBindContextParam(IBindCtx *,CStr *,ushort *)
0x180b43bbf  test    eax, eax
0x180b43bc1  jnz     short loc_180B43BD0
0x180b43bc3  mov     rcx, [rbp+310h+var_390]; psz
0x180b43bc7  call    cs:__imp_SysAllocString
0x180b43bcd  mov     r13, rax
0x180b43bd0  lea     rcx, [rbp+310h+var_390]; this
0x180b43bd4  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180b43bd9  mov     rcx, [rbp+310h+var_320]
0x180b43bdd  lea     rax, [rbp+310h+var_318]
0x180b43be1  mov     rsi, [rsp+78h]
0x180b43be6  mov     rdx, [rbp+310h+ppURI]; struct IUri *
0x180b43bea  mov     r8, rsi; unsigned __int16 *
0x180b43bed  mov     [rsp+60h], r15; int *
0x180b43bf2  mov     rcx, [rcx+38h]; this
0x180b43bf6  mov     [rsp+410h+var_3B8], r15; struct IBindCtx *
0x180b43bfb  mov     [rsp+410h+var_3C0], r15d; unsigned int
0x180b43c00  mov     [rsp+410h+var_3C8], edi; unsigned int
0x180b43c04  mov     rdi, [rsp+410h+var_3A0]
0x180b43c09  mov     [rsp+410h+var_3D0], rax; struct tagVARIANT *
0x180b43c0e  mov     r9, rdi; unsigned __int16 *
0x180b43c11  mov     [rsp+410h+var_3D8], r15; struct IStream *
0x180b43c16  lea     rax, [rbp+310h+var_300]
0x180b43c1a  mov     [rsp+410h+var_3E0], rax; struct tagVARIANT *
0x180b43c1f  mov     [rsp+410h+var_3E8], r13; unsigned __int16 *
0x180b43c24  mov     [rsp+410h+var_3F0], rbx; unsigned __int16 *
0x180b43c29  call    ?SuperNavigateInternal@CWindow@@QEAAJPEAUIUri@@PEAG111PEAUtagVARIANT@@PEAUIStream@@2KKPEAUIBindCtx@@PEAH@Z; CWindow::SuperNavigateInternal(IUri *,ushort *,ushort *,ushort *,ushort *,tagVARIANT *,IStream *,tagVARIANT *,ulong,ulong,IBindCtx *,int *)
  ... truncated ...
```
