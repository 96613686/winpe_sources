# CoInternetCombineUrlInternal

- ea: `0x180015700`
- end: `0x180015f07`
- name: `CoInternetCombineUrlInternal`
- size: `2055`
- prototype: `__int64 __fastcall(int, int, int, int, int, IUri *, DWORD_PTR dwReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800f5838`

## callees

- `0x18001063c`
- `0x1800150e0`
- `0x18001511c`
- `0x180015700`
- `0x18001e160`
- `0x18009f200`
- `0x18011ba26`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x18001597e`
- `iertutil!CreateUri` at `0x180015aec`
- `iertutil!CreateUri` at `0x18001597e`
- `iertutil!CreateUri` at `0x180015aec`
- `iertutil!PrivateCoInternetCombineIUri` at `0x180015bc5`
- `iertutil!PrivateCoInternetCombineIUri` at `0x180015bc5`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180015e0c`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180015e37`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180015e0c`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180015e37`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180015868`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x1800159d1`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180015868`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x1800159d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015dba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015dba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b17`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800158ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800158d0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015909`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015a15`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015a38`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015a71`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800158ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800158d0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015909`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015a15`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015a38`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015a71`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e83`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ef8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e83`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ef8`
- `OLEAUT32!__imp_SysStringLen` at `0x180015eba`
- `OLEAUT32!__imp_SysStringLen` at `0x180015eba`

## pseudocode

```c
__int64 __fastcall CoInternetCombineUrlInternal(
        const WCHAR *a1,
        const WCHAR *a2,
        unsigned int a3,
        _WORD *a4,
        unsigned int a5,
        IUri *a6,
        DWORD_PTR dwReserved)
{
  IUri *v7; // r12
  int v10; // edi
  int v11; // esi
  HRESULT v12; // esi
  _WORD *v13; // rcx
  BOOL v14; // ebx
  bool ShouldUseEdge; // r14
  DWORD v17; // edx
  bool v18; // si
  DWORD v19; // edx
  IUri *v20; // rsi
  void *v21; // rdi
  COInetSession *v22; // rax
  int v23; // r15d
  volatile signed __int32 *v24; // r14
  int v25; // eax
  __int64 v26; // rcx
  struct IUri *v27; // r14
  BOOL v28; // edi
  BOOL v29; // r15d
  __int64 v30; // rcx
  __int64 v31; // r8
  BSTR v32; // rdx
  __int64 v33; // rax
  struct IUriVtbl *lpVtbl; // rax
  COInetSession *v35; // rax
  int IsFeatureEnabledInternal; // eax
  int v37; // eax
  struct IUri *v38; // [rsp+40h] [rbp-49h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-41h] BYREF
  void *v40; // [rsp+50h] [rbp-39h] BYREF
  IUri *v41; // [rsp+58h] [rbp-31h]
  void **v42; // [rsp+60h] [rbp-29h] BYREF
  struct IUri *v43; // [rsp+68h] [rbp-21h]
  unsigned int v44; // [rsp+70h] [rbp-19h]
  BSTR bstrString[2]; // [rsp+78h] [rbp-11h] BYREF
  UINT v46[14]; // [rsp+88h] [rbp-1h] BYREF

  v7 = a6;
  v42 = &CUString::`vftable';
  v43 = 0;
  v44 = 11;
  v46[0] = 0;
  ppURI = 0;
  v38 = 0;
  *(_OWORD *)bstrString = 0;
  if ( a6 )
    LODWORD(a6->lpVtbl) = 0;
  v10 = (a3 >> 11) & 0x20 | 0x3002B85;
  v11 = v10;
  if ( (a3 & 0x8000000) != 0 )
    v11 = (a3 >> 11) & 0x20 | 0x3002A95;
  if ( (v11 & 0x110) == 0x110 )
  {
    v12 = -2147024809;
    goto LABEL_14;
  }
  ShouldUseEdge = InternalForkingSupport_ShouldUseEdge();
  if ( !ShouldUseEdge )
  {
LABEL_26:
    v11 &= ~0x1000000u;
    if ( !ShouldUseEdge )
      goto LABEL_30;
    goto LABEL_27;
  }
  if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
  {
    IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
    if ( IsFeatureEnabledInternal < 0 )
      goto LABEL_27;
    dword_180159BE8 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180159BE8 )
    goto LABEL_26;
LABEL_27:
  InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18015E75C & 1) != 0 )
  {
    InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18015E75C & 2) != 0 || (unsigned int)IsABrowserApp() )
    {
LABEL_31:
      InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
      if ( (dword_18015E75C & 4) != 0 )
        goto LABEL_32;
      goto LABEL_51;
    }
  }
LABEL_30:
  v11 &= ~0x2000000u;
  if ( ShouldUseEdge )
    goto LABEL_31;
LABEL_51:
  v11 &= ~0x8000000u;
LABEL_32:
  if ( (v11 & 0x110) == 0 )
    v11 |= 0x100u;
  v17 = v11 | 0x80;
  if ( (v11 & 0xC0) != 0 )
    v17 = v11;
  if ( (v17 & 0x600) == 0 )
    v17 |= 0x200u;
  if ( (v17 & 0x1800) == 0 )
    v17 |= 0x800u;
  if ( (v17 & 0x6000) == 0 )
    v17 |= 0x2000u;
  if ( (v17 & 0x2000000) == 0 )
    v17 |= 0x2000000u;
  if ( (v17 & 0x1000000) == 0 )
    v17 |= 0x1000000u;
  v12 = CreateUri(a1, v17, 0, &ppURI);
  if ( v12 < 0 )
    goto LABEL_10;
  v41 = ppURI;
  a6 = 0;
  v38 = 0;
  if ( (a3 & 0x8000000) != 0 )
    v10 = (a3 >> 11) & 0x20 | 0x3002A95;
  if ( (v10 & 0x110) == 0x110 )
  {
LABEL_50:
    v12 = -2147024809;
    goto LABEL_10;
  }
  v18 = InternalForkingSupport_ShouldUseEdge();
  if ( v18 )
  {
    if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
    {
      v37 = CoInternetIsFeatureEnabledInternal();
      if ( v37 < 0 )
        goto LABEL_56;
      dword_180159BE8 = v37 == 0;
      FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
    }
    if ( !dword_180159BE8 )
      goto LABEL_56;
  }
  v10 &= ~0x1000000u;
  if ( v18 )
  {
LABEL_56:
    InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18015E75C & 1) != 0 )
    {
      InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
      if ( (dword_18015E75C & 2) != 0 || (unsigned int)IsABrowserApp() )
        goto LABEL_60;
    }
  }
  v10 &= ~0x2000000u;
  if ( !v18 )
  {
LABEL_127:
    v10 &= ~0x8000000u;
    goto LABEL_61;
  }
LABEL_60:
  InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18015E75C & 4) == 0 )
    goto LABEL_127;
LABEL_61:
  if ( !a2 )
    goto LABEL_77;
  if ( (v10 & 0x110) == 0 )
    v10 |= 0x100u;
  v19 = v10 | 0x80;
  if ( (v10 & 0xC0) != 0 )
    v19 = v10;
  if ( (v19 & 0x600) == 0 )
    v19 |= 0x200u;
  if ( (v19 & 0x1800) == 0 )
    v19 |= 0x800u;
  if ( (v19 & 0x6000) == 0 )
    v19 |= 0x2000u;
  if ( (v19 & 0x2000000) == 0 )
    v19 |= 0x2000000u;
  if ( (v19 & 0x1000000) == 0 )
    v19 |= 0x1000000u;
  v12 = CreateUri(a2, v19, (unsigned int)dwReserved, &a6);
  if ( v12 >= 0 )
  {
LABEL_77:
    v20 = a6;
    if ( !a6 )
    {
      v12 = -2147418113;
      goto LABEL_10;
    }
    v40 = 0;
    v21 = 0;
    EnterCriticalSection(&g_mxsOInet);
    v22 = g_pCOInetSession;
    v23 = 0;
    if ( g_pCOInetSession
      || ((v35 = (COInetSession *)operator new(0x180u)) == 0 || (v22 = COInetSession::COInetSession(v35)) == 0
        ? (COInetSession *)(v22 = g_pCOInetSession, v23 = -2147024882)
        : (g_pCOInetSession = v22),
          v22) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v22 + 4);
      v24 = (volatile signed __int32 *)g_pCOInetSession;
      LeaveCriticalSection(&g_mxsOInet);
      if ( !v23 )
      {
        if ( v24 )
        {
          if ( !memcmp_0(&GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &IID_IInternetProtocolInfo, 0x10u) )
          {
            v21 = (void *)(v24 + 2);
            v26 = (__int64)(v24 + 4);
            _InterlockedIncrement(v24 + 4);
          }
          else
          {
            v25 = COInetSession::QueryInterface((COInetSession *)v24, &GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &v40);
            v26 = (__int64)(v24 + 4);
            if ( !v25 )
              v21 = v40;
          }
        }
        else
        {
          v26 = 16;
        }
        _InterlockedDecrement((volatile signed __int32 *)v26);
      }
    }
    else
    {
      LeaveCriticalSection(&g_mxsOInet);
    }
    v12 = PrivateCoInternetCombineIUri(v41, v20, a3, &v38, (unsigned int)dwReserved, v21, 0, 0);
    if ( v21 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  if ( a6 )
    ((void (__fastcall *)(IUri *))a6->lpVtbl->Release)(a6);
  if ( v12 < 0 )
    goto LABEL_10;
  v27 = v38;
  v12 = 0;
  v28 = v38 != v43;
  v29 = v44 != 0;
  if ( v38 != v43 || v44 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v46[0] = 0;
    if ( v28 && v43 )
    {
      ((void (__fastcall *)(struct IUri *))v43->lpVtbl->Release)(v43);
      v43 = 0;
    }
  }
  v44 = 0;
  if ( v27 && (v29 || v28) )
  {
    lpVtbl = v27->lpVtbl;
    a6 = 0;
    if ( ((int (__fastcall *)(struct IUri *, GUID *, IUri **))lpVtbl->QueryInterface)(
           v27,
           &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
           &a6) < 0 )
    {
      v12 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))v27->lpVtbl->GetPropertyBSTR)(
              v27,
              v44,
              bstrString,
              0);
      if ( v12 >= 0 )
      {
        bstrString[1] = bstrString[0];
        v46[0] = SysStringLen(bstrString[0]);
      }
    }
    else
    {
      v12 = ((__int64 (__fastcall *)(IUri *, _QWORD, BSTR *, UINT *))a6->lpVtbl[1].QueryInterface)(
              a6,
              v44,
              &bstrString[1],
              v46);
      ((void (__fastcall *)(IUri *))a6->lpVtbl->Release)(a6);
    }
    if ( v28 && v12 >= 0 )
    {
      v43 = v27;
      ((void (__fastcall *)(struct IUri *))v27->lpVtbl->AddRef)(v27);
    }
    if ( v12 == 1 )
    {
      v12 = CUString::Set((CUString *)&v42, v38, Uri_PROPERTY_RAW_URI);
      if ( v12 == 1 )
      {
        v12 = -2146697214;
        goto LABEL_10;
      }
    }
  }
  if ( v12 >= 0 )
  {
    v30 = v46[0];
    if ( a5 <= v46[0] )
    {
      if ( v7 )
        LODWORD(v7->lpVtbl) = v46[0] + 1;
      v12 = -2147467261;
      goto LABEL_10;
    }
    if ( v7 )
      LODWORD(v7->lpVtbl) = v46[0];
    v31 = a5;
    if ( a5 - 1 > 0x7FFFFFFE )
    {
      v12 = -2147024809;
      if ( a5 )
        *a4 = 0;
      goto LABEL_10;
    }
    if ( (unsigned int)v30 <= 0x7FFFFFFE )
    {
      v32 = bstrString[1];
      v33 = v30;
      do
      {
        if ( !v33 )
          break;
        if ( !*v32 )
          break;
        *a4++ = *v32++;
        --v33;
        --v31;
      }
      while ( v31 );
      v13 = a4 - 1;
      v12 = -2147024774;
      if ( v31 )
      {
        v13 = a4;
        v12 = 0;
      }
      *v13 = 0;
      goto LABEL_10;
    }
    *a4 = 0;
    goto LABEL_50;
  }
LABEL_10:
  if ( ppURI )
  {
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    ppURI = 0;
  }
  if ( v38 )
  {
    ((void (__fastcall *)(struct IUri *))v38->lpVtbl->Release)(v38);
    v38 = 0;
  }
LABEL_14:
  v42 = &CUString::`vftable';
  v14 = v43 != 0;
  if ( v43 || v44 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v46[0] = 0;
    if ( v14 && v43 )
      ((void (__fastcall *)(struct IUri *))v43->lpVtbl->Release)(v43);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180015700  mov     [rsp-8+arg_10], rbx
0x180015705  mov     [rsp-8+arg_8], rdx
0x18001570a  mov     [rsp-8+pwzURI], rcx
0x18001570f  push    rbp
0x180015710  push    rsi
0x180015711  push    rdi
0x180015712  push    r12
0x180015714  push    r13
0x180015716  push    r14
0x180015718  push    r15
0x18001571a  lea     rbp, [rsp-7]
0x18001571f  sub     rsp, 90h
0x180015726  mov     r12, [rbp+37h+arg_28]
0x18001572a  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180015731  xor     r14d, r14d
0x180015734  mov     [rbp+37h+var_60], rax
0x180015738  mov     [rbp+37h+var_58], r14
0x18001573c  xorps   xmm0, xmm0
0x18001573f  mov     [rbp+37h+var_50], 0Bh
0x180015746  mov     rbx, r9
0x180015749  mov     [rbp+37h+var_38], r14d
0x18001574d  mov     r13d, r8d
0x180015750  mov     [rbp+37h+ppURI], r14
0x180015754  mov     [rbp+37h+var_80], r14
0x180015758  movdqu  xmmword ptr [rbp+37h+bstrString], xmm0
0x18001575d  test    r12, r12
0x180015760  jz      short loc_180015766
0x180015762  mov     [r12], r14d
0x180015766  mov     edi, r13d
0x180015769  mov     r15d, r13d
0x18001576c  shr     edi, 0Bh
0x18001576f  and     edi, 20h
0x180015772  or      edi, 3002B85h
0x180015778  mov     esi, edi
0x18001577a  and     r15d, 8000000h
0x180015781  jz      short loc_18001578A
0x180015783  btr     esi, 8
0x180015787  or      esi, 10h
0x18001578a  mov     eax, esi
0x18001578c  and     eax, 110h
0x180015791  cmp     eax, 110h
0x180015796  jnz     loc_180015868
0x18001579c  mov     esi, 80070057h
0x1800157a1  jmp     short loc_1800157F3
0x1800157a3  test    r8, r8
0x1800157a6  lea     rcx, [rbx-2]
0x1800157aa  mov     esi, 8007007Ah
0x1800157af  cmovnz  rcx, rbx
0x1800157b3  xor     r14d, r14d
0x1800157b6  test    r8, r8
0x1800157b9  cmovnz  esi, r14d
0x1800157bd  mov     [rcx], r14w
0x1800157c1  mov     rcx, [rbp+37h+ppURI]
0x1800157c5  test    rcx, rcx
0x1800157c8  jz      short loc_1800157DA
0x1800157ca  mov     rax, [rcx]
0x1800157cd  mov     rax, [rax+10h]
0x1800157d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d6  mov     [rbp+37h+ppURI], r14
0x1800157da  mov     rcx, [rbp+37h+var_80]
0x1800157de  test    rcx, rcx
0x1800157e1  jz      short loc_1800157F3
0x1800157e3  mov     rax, [rcx]
0x1800157e6  mov     rax, [rax+10h]
0x1800157ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157ef  mov     [rbp+37h+var_80], r14
0x1800157f3  cmp     [rbp+37h+var_58], 0
0x1800157f8  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x1800157ff  mov     ebx, r14d
0x180015802  mov     [rbp+37h+var_60], rax
0x180015806  setnz   bl
0x180015809  mov     eax, r14d
0x18001580c  cmp     [rbp+37h+var_50], 0Bh
0x180015810  setnz   al
0x180015813  test    ebx, ebx
0x180015815  jz      short loc_180015862
0x180015817  mov     rcx, [rbp+37h+bstrString]; bstrString
0x18001581b  test    rcx, rcx
0x18001581e  jnz     loc_180015EF8
0x180015824  mov     [rbp+37h+bstrString+8], r14
0x180015828  mov     [rbp+37h+var_38], r14d
0x18001582c  test    ebx, ebx
0x18001582e  jz      short loc_180015845
0x180015830  mov     rcx, [rbp+37h+var_58]
0x180015834  test    rcx, rcx
0x180015837  jz      short loc_180015845
0x180015839  mov     rax, [rcx]
0x18001583c  mov     rax, [rax+10h]
0x180015840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015845  mov     rbx, [rsp+0C0h+arg_10]
0x18001584d  mov     eax, esi
0x18001584f  add     rsp, 90h
0x180015856  pop     r15
0x180015858  pop     r14
0x18001585a  pop     r13
0x18001585c  pop     r12
0x18001585e  pop     rdi
0x18001585f  pop     rsi
0x180015860  pop     rbp
0x180015861  retn
0x180015862  test    eax, eax
0x180015864  jz      short loc_180015845
0x180015866  jmp     short loc_180015817
0x180015868  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18001586e  movzx   r14d, al
0x180015872  test    al, al
0x180015874  jz      short loc_180015890
0x180015876  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001587d  test    rcx, rcx
0x180015880  jnz     loc_180015E0C
0x180015886  mov     eax, cs:dword_180159BE8
0x18001588c  test    eax, eax
0x18001588e  jz      short loc_180015899
0x180015890  btr     esi, 18h
0x180015894  test    r14b, r14b
0x180015897  jz      short loc_1800158E8
0x180015899  xor     r9d, r9d; Context
0x18001589c  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800158a3  xor     r8d, r8d; Parameter
0x1800158a6  lea     rcx, stru_18015DE28; InitOnce
0x1800158ad  call    cs:__imp_InitOnceExecuteOnce
0x1800158b3  test    byte ptr cs:dword_18015E75C, 1
0x1800158ba  jz      short loc_1800158E8
0x1800158bc  xor     r9d, r9d; Context
0x1800158bf  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800158c6  xor     r8d, r8d; Parameter
0x1800158c9  lea     rcx, stru_18015DE28; InitOnce
0x1800158d0  call    cs:__imp_InitOnceExecuteOnce
0x1800158d6  test    byte ptr cs:dword_18015E75C, 2
0x1800158dd  jnz     short loc_1800158F5
0x1800158df  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x1800158e4  test    eax, eax
0x1800158e6  jnz     short loc_1800158F5
0x1800158e8  btr     esi, 19h
0x1800158ec  test    r14b, r14b
0x1800158ef  jz      loc_1800159C8
0x1800158f5  xor     r9d, r9d; Context
0x1800158f8  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800158ff  xor     r8d, r8d; Parameter
0x180015902  lea     rcx, stru_18015DE28; InitOnce
0x180015909  call    cs:__imp_InitOnceExecuteOnce
0x18001590f  test    byte ptr cs:dword_18015E75C, 4
0x180015916  jz      loc_1800159C8
0x18001591c  mov     eax, esi
0x18001591e  bts     eax, 8
0x180015922  test    esi, 110h
0x180015928  cmovz   esi, eax
0x18001592b  mov     edx, esi
0x18001592d  bts     edx, 7
0x180015931  test    sil, 0C0h
0x180015935  cmovnz  edx, esi
0x180015938  mov     eax, edx
0x18001593a  bts     eax, 9
0x18001593e  test    edx, 600h
0x180015944  cmovz   edx, eax
0x180015947  test    edx, 1800h
0x18001594d  jnz     short loc_180015953
0x18001594f  bts     edx, 0Bh
0x180015953  test    edx, 6000h
0x180015959  jnz     short loc_18001595F
0x18001595b  bts     edx, 0Dh
0x18001595f  bt      edx, 19h
0x180015963  jb      short loc_180015969
0x180015965  bts     edx, 19h
0x180015969  bt      edx, 18h
0x18001596d  jb      short loc_180015973
0x18001596f  bts     edx, 18h; dwFlags
0x180015973  mov     rcx, [rbp+37h+pwzURI]; pwzURI
0x180015977  lea     r9, [rbp+37h+ppURI]; ppURI
0x18001597b  xor     r8d, r8d; dwReserved
0x18001597e  call    cs:__imp_CreateUri
0x180015984  xor     r14d, r14d
0x180015987  mov     esi, eax
0x180015989  test    eax, eax
0x18001598b  js      loc_1800157C1
0x180015991  mov     rax, [rbp+37h+ppURI]
0x180015995  mov     [rbp+37h+var_68], rax
0x180015999  mov     eax, edi
0x18001599b  btr     eax, 8
0x18001599f  mov     [rbp+37h+arg_28], r14
0x1800159a3  or      eax, 10h
0x1800159a6  mov     [rbp+37h+var_80], r14
0x1800159aa  test    r15d, r15d
0x1800159ad  cmovnz  edi, eax
0x1800159b0  mov     eax, edi
0x1800159b2  and     eax, 110h
0x1800159b7  cmp     eax, 110h
0x1800159bc  jnz     short loc_1800159D1
0x1800159be  mov     esi, 80070057h
0x1800159c3  jmp     loc_1800157C1
0x1800159c8  btr     esi, 1Bh
0x1800159cc  jmp     loc_18001591C
0x1800159d1  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x1800159d7  movzx   esi, al
0x1800159da  test    al, al
0x1800159dc  jz      short loc_1800159F8
0x1800159de  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x1800159e5  test    rcx, rcx
0x1800159e8  jnz     loc_180015E37
0x1800159ee  mov     eax, cs:dword_180159BE8
0x1800159f4  test    eax, eax
0x1800159f6  jz      short loc_180015A01
0x1800159f8  btr     edi, 18h
0x1800159fc  test    sil, sil
0x1800159ff  jz      short loc_180015A50
0x180015a01  xor     r9d, r9d; Context
0x180015a04  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180015a0b  xor     r8d, r8d; Parameter
0x180015a0e  lea     rcx, stru_18015DE28; InitOnce
0x180015a15  call    cs:__imp_InitOnceExecuteOnce
0x180015a1b  test    byte ptr cs:dword_18015E75C, 1
0x180015a22  jz      short loc_180015A50
0x180015a24  xor     r9d, r9d; Context
0x180015a27  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180015a2e  xor     r8d, r8d; Parameter
0x180015a31  lea     rcx, stru_18015DE28; InitOnce
0x180015a38  call    cs:__imp_InitOnceExecuteOnce
0x180015a3e  test    byte ptr cs:dword_18015E75C, 2
0x180015a45  jnz     short loc_180015A5D
0x180015a47  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x180015a4c  test    eax, eax
0x180015a4e  jnz     short loc_180015A5D
0x180015a50  btr     edi, 19h
0x180015a54  test    sil, sil
0x180015a57  jz      loc_180015DEB
0x180015a5d  xor     r9d, r9d; Context
0x180015a60  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180015a67  xor     r8d, r8d; Parameter
0x180015a6a  lea     rcx, stru_18015DE28; InitOnce
0x180015a71  call    cs:__imp_InitOnceExecuteOnce
0x180015a77  test    byte ptr cs:dword_18015E75C, 4
0x180015a7e  jz      loc_180015DEB
0x180015a84  mov     rcx, [rbp+37h+arg_8]; pwzURI
0x180015a88  test    rcx, rcx
0x180015a8b  jz      short loc_180015AFC
0x180015a8d  mov     eax, edi
0x180015a8f  bts     eax, 8
0x180015a93  test    edi, 110h
0x180015a99  cmovz   edi, eax
0x180015a9c  mov     edx, edi
0x180015a9e  bts     edx, 7
0x180015aa2  test    dil, 0C0h
0x180015aa6  cmovnz  edx, edi
0x180015aa9  mov     eax, edx
0x180015aab  bts     eax, 9
0x180015aaf  test    edx, 600h
0x180015ab5  cmovz   edx, eax
0x180015ab8  test    edx, 1800h
0x180015abe  jnz     short loc_180015AC4
0x180015ac0  bts     edx, 0Bh
0x180015ac4  test    edx, 6000h
0x180015aca  jnz     short loc_180015AD0
0x180015acc  bts     edx, 0Dh
0x180015ad0  bt      edx, 19h
0x180015ad4  jb      short loc_180015ADA
0x180015ad6  bts     edx, 19h
0x180015ada  bt      edx, 18h
0x180015ade  jb      short loc_180015AE4
0x180015ae0  bts     edx, 18h; dwFlags
0x180015ae4  mov     r8d, dword ptr [rbp+37h+dwReserved]; dwReserved
0x180015ae8  lea     r9, [rbp+37h+arg_28]; ppURI
0x180015aec  call    cs:__imp_CreateUri
0x180015af2  mov     esi, eax
0x180015af4  test    eax, eax
0x180015af6  js      loc_180015BE1
0x180015afc  mov     rsi, [rbp+37h+arg_28]
0x180015b00  test    rsi, rsi
0x180015b03  jz      loc_180015EEE
0x180015b09  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180015b10  mov     [rbp+37h+var_70], r14
0x180015b14  mov     rdi, r14
0x180015b17  call    cs:__imp_EnterCriticalSection
0x180015b1d  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180015b24  mov     r15d, r14d
0x180015b27  test    rax, rax
0x180015b2a  jz      loc_180015D87
0x180015b30  lock inc dword ptr [rax+10h]
0x180015b34  mov     r14, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180015b3b  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180015b42  call    cs:__imp_LeaveCriticalSection
0x180015b48  test    r15d, r15d
0x180015b4b  jnz     loc_180015DC5
0x180015b51  test    r14, r14
0x180015b54  jz      loc_180015E03
0x180015b5a  mov     r8d, 10h; Size
0x180015b60  lea     rdx, IID_IInternetProtocolInfo; Buf2
0x180015b67  lea     rcx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; Buf1
0x180015b6e  call    memcmp_0
0x180015b73  test    eax, eax
0x180015b75  jz      loc_180015DDB
0x180015b7b  lea     r8, [rbp+37h+var_70]; void **
0x180015b7f  mov     rcx, r14; this
0x180015b82  lea     rdx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; struct _GUID *
0x180015b89  call    ?QueryInterface@COInetSession@@UEAAJAEBU_GUID@@PEAPEAX@Z; COInetSession::QueryInterface(_GUID const &,void * *)
0x180015b8e  lea     rcx, [r14+10h]
0x180015b92  test    eax, eax
0x180015b94  jnz     short loc_180015B9A
0x180015b96  mov     rdi, [rbp+37h+var_70]
0x180015b9a  xor     r14d, r14d
0x180015b9d  lock dec dword ptr [rcx]
  ... truncated ...
```
