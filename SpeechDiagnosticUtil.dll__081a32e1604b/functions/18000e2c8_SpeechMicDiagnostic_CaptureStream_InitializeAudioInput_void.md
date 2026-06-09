# SpeechMicDiagnostic::CaptureStream::InitializeAudioInput(void)

- ea: `0x18000e2c8`
- end: `0x18000eb34`
- name: `?InitializeAudioInput@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ`
- size: `2156`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CaptureStream *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007c88`

## callees

- `0x180005b28`
- `0x18000d630`
- `0x18000d6b4`
- `0x18000e2c8`
- `0x18000ef9c`
- `0x18000f270`
- `0x180010564`
- `0x180011010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e4d1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e4d1`
- `ole32!CoCreateInstance` at `0x18000e30d`
- `ole32!CoCreateInstance` at `0x18000e3b8`
- `ole32!CoCreateInstance` at `0x18000e5e2`
- `ole32!CoCreateInstance` at `0x18000e30d`
- `ole32!CoCreateInstance` at `0x18000e3b8`
- `ole32!CoCreateInstance` at `0x18000e5e2`
- `ole32!CoTaskMemFree` at `0x18000e413`
- `ole32!CoTaskMemFree` at `0x18000e562`
- `ole32!CoTaskMemFree` at `0x18000e5b1`
- `ole32!CoTaskMemFree` at `0x18000e413`
- `ole32!CoTaskMemFree` at `0x18000e562`
- `ole32!CoTaskMemFree` at `0x18000e5b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall SpeechMicDiagnostic::CaptureStream::InitializeAudioInput(wchar_t **this)
{
  wchar_t *v2; // rbx
  HRESULT Instance; // edi
  wchar_t *v4; // rcx
  LPVOID v5; // r14
  wchar_t *v6; // rax
  wchar_t *v7; // rcx
  unsigned int v9; // ebx
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  wchar_t *v13; // rax
  _WORD *v14; // r14
  void **v15; // rbx
  __int64 v16; // rdi
  HRESULT v17; // eax
  LPVOID v18; // rcx
  struct IMMDevice *v19; // rcx
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, void *, struct IMMDevice **); // r14
  struct IMMDevice *v22; // rcx
  int v23; // eax
  LPVOID v24; // rcx
  struct IMMDevice *v25; // rcx
  int v26; // eax
  LPVOID v27; // rcx
  struct IMMDevice *v28; // rcx
  int DeviceProperties; // eax
  LPVOID v30; // rcx
  struct IMMDevice *v31; // rcx
  __int64 (__fastcall *v32)(wchar_t *, _QWORD, __int64, GUID *); // rdi
  wchar_t *v33; // rcx
  int v34; // eax
  LPVOID v35; // rcx
  struct IMMDevice *v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  LPVOID v39; // rcx
  struct IMMDevice *v40; // rcx
  int v41; // eax
  __int64 v42; // rcx
  LPVOID v43; // rcx
  struct IMMDevice *v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  LPVOID v47; // rcx
  struct IMMDevice *v48; // rcx
  __int64 v49; // rcx
  LPVOID v50; // rcx
  struct IMMDevice *v51; // rcx
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  int ppvb; // [rsp+20h] [rbp-30h]
  __int64 v55; // [rsp+30h] [rbp-20h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-10h] BYREF
  wchar_t *v58; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  wchar_t *v60; // [rsp+88h] [rbp+38h]
  struct IMMDevice *v61; // [rsp+90h] [rbp+40h] BYREF
  LPVOID v62; // [rsp+98h] [rbp+48h] BYREF

  v60 = 0;
  v2 = 0;
  v58 = 0;
  Str = 0;
  Instance = CoCreateInstance(
               &CLSID_SpObjectTokenCategory,
               0,
               0x17u,
               &GUID_2d3d3845_39af_4850_bbf9_40b49780011d,
               (LPVOID *)&Str);
  if ( Instance < 0
    || (Instance = (*(__int64 (__fastcall **)(wchar_t *, const wchar_t *, __int64))(*(_QWORD *)Str + 120LL))(
                     Str,
                     L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput",
                     1),
        Instance < 0) )
  {
    v4 = Str;
  }
  else
  {
    v2 = Str;
    v4 = 0;
    Str = 0;
    v58 = v2;
  }
  if ( v4 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( Instance >= 0 )
  {
    pv = 0;
    Instance = (*(__int64 (__fastcall **)(wchar_t *, LPVOID *))(*(_QWORD *)v2 + 160LL))(v2, &pv);
    if ( Instance >= 0 )
    {
      v5 = pv;
      Str = 0;
      Instance = CoCreateInstance(
                   &CLSID_SpObjectToken,
                   0,
                   0x17u,
                   &GUID_14056589_e16c_11d2_bb90_00c04f8ee6c0,
                   (LPVOID *)&Str);
      if ( Instance < 0
        || (Instance = (*(__int64 (__fastcall **)(wchar_t *, _QWORD, LPVOID, _QWORD))(*(_QWORD *)Str + 120LL))(
                         Str,
                         0,
                         v5,
                         0),
            Instance < 0) )
      {
        v7 = Str;
      }
      else
      {
        v6 = Str;
        v7 = 0;
        Str = 0;
        v60 = v6;
      }
      if ( v7 )
        (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v7 + 16LL))(v7);
      CoTaskMemFree(pv);
    }
  }
  if ( v2 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v2 + 16LL))(v2);
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return (unsigned int)Instance;
  }
  if ( !v60 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)0x80070057LL,
      ppv);
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)v9,
      ppva);
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return v9;
  }
  Str = 0;
  v10 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)v60 + 128LL))(v60, &Str);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v12 = 413;
    goto LABEL_37;
  }
  v13 = wcsrchr(Str, 0x5Cu);
  if ( !v13 )
  {
    v9 = -2147418113;
    v12 = 417;
LABEL_36:
    v11 = v9;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)v11,
      ppv);
    if ( Str )
      CoTaskMemFree(Str);
    goto LABEL_39;
  }
  v14 = v13 + 1;
  v15 = (void **)(this + 17);
  if ( v13 + 1 != this[17] )
  {
    CSpDynamicString::_free((CSpDynamicString *)(this + 17));
    if ( v14 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v14[v16] );
      if ( (int)CSpDynamicString::_allocate((CSpDynamicString *)(this + 17), v16) >= 0 )
        memcpy_0(*v15, v14, 2 * v16);
    }
  }
  if ( !*v15 )
  {
    v9 = -2147024882;
    v12 = 420;
    goto LABEL_36;
  }
  if ( Str )
    CoTaskMemFree(Str);
  v61 = 0;
  v62 = 0;
  v17 = CoCreateInstance(
          &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
          0,
          0x17u,
          &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
          &v62);
  Instance = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v17,
      ppvb);
    v18 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IMMDevice *))v19->lpVtbl->Release)(v19);
    }
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return (unsigned int)Instance;
  }
  v20 = v62;
  v21 = *(__int64 (__fastcall **)(LPVOID, void *, struct IMMDevice **))(*(_QWORD *)v62 + 40LL);
  v22 = v61;
  if ( v61 )
  {
    v61 = 0;
    ((void (__fastcall *)(struct IMMDevice *))v22->lpVtbl->Release)(v22);
  }
  v23 = v21(v20, *v15, &v61);
  v9 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v23,
      ppvb);
    v24 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IMMDevice *))v25->lpVtbl->Release)(v25);
    }
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return v9;
  }
  v26 = SpeechMicDiagnostic::CaptureStream::InstantiateHelpers((SpeechMicDiagnostic::CaptureStream *)this, v61);
  v9 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v26,
      ppvb);
    v27 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IMMDevice *))v28->lpVtbl->Release)(v28);
    }
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return v9;
  }
  DeviceProperties = SpeechMicDiagnostic::CaptureStream::QueryDeviceProperties(
                       (SpeechMicDiagnostic::CaptureStream *)this,
                       v61);
  v9 = DeviceProperties;
  if ( DeviceProperties < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)DeviceProperties,
      ppvb);
    v30 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IMMDevice *))v31->lpVtbl->Release)(v31);
    }
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return v9;
  }
  v32 = *(__int64 (__fastcall **)(wchar_t *, _QWORD, __int64, GUID *))(*(_QWORD *)v60 + 144LL);
  v33 = *this;
  if ( *this )
  {
    *this = 0;
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v32(v60, 0, 23, &GUID_f4c6587c_c49e_4254_923b_fb0b09fe13c7);
  v9 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v34,
      (int)this);
    v35 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IMMDevice *))v36->lpVtbl->Release)(v36);
    }
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return v9;
  }
  v55 = 0;
  v37 = (**(__int64 (__fastcall ***)(wchar_t *, GUID *, __int64 *))*this)(
          *this,
          &GUID_251ab6f7_5ffa_42d8_a2e9_5b05f617a03b,
          &v55);
  v9 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v37,
      (int)this);
    v38 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IMMDevice *))v40->lpVtbl->Release)(v40);
    }
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return v9;
  }
  v41 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 40LL))(v55, 1);
  v9 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v41,
      (int)this);
    v42 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IMMDevice *))v44->lpVtbl->Release)(v44);
    }
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return v9;
  }
  v45 = (*(__int64 (__fastcall **)(wchar_t *, char *))(*(_QWORD *)*this + 176LL))(*this, (char *)this + 156);
  v9 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v45,
      (int)this);
    v46 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IMMDevice *))v48->lpVtbl->Release)(v48);
    }
    if ( v60 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
    return v9;
  }
  v49 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v61;
  if ( v61 )
  {
    v61 = 0;
    ((void (__fastcall *)(struct IMMDevice *))v51->lpVtbl->Release)(v51);
  }
  if ( v60 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v60 + 16LL))(v60);
  return 0;
}

```

## disassembly

```asm
0x18000e2c8  mov     [rsp-28h+arg_0], rbx
0x18000e2cd  push    rbp
0x18000e2ce  push    rsi
0x18000e2cf  push    rdi
0x18000e2d0  push    r14
0x18000e2d2  push    r15
0x18000e2d4  mov     rbp, rsp
0x18000e2d7  sub     rsp, 50h
0x18000e2db  mov     rsi, rcx
0x18000e2de  xor     r15d, r15d
0x18000e2e1  mov     [rbp+arg_8], r15
0x18000e2e5  mov     ebx, r15d
0x18000e2e8  mov     [rbp+var_8], rbx
0x18000e2ec  mov     [rbp+Str], r15
0x18000e2f0  lea     rax, [rbp+Str]
0x18000e2f4  mov     qword ptr [rsp+50h+ppv], rax; ppv
0x18000e2f9  lea     r9, _GUID_2d3d3845_39af_4850_bbf9_40b49780011d; riid
0x18000e300  xor     edx, edx; pUnkOuter
0x18000e302  lea     r8d, [r15+17h]; dwClsContext
0x18000e306  lea     rcx, CLSID_SpObjectTokenCategory; rclsid
0x18000e30d  call    cs:__imp_CoCreateInstance
0x18000e314  nop     dword ptr [rax+rax+00h]
0x18000e319  mov     edi, eax
0x18000e31b  test    eax, eax
0x18000e31d  js      short loc_18000E351
0x18000e31f  mov     rcx, [rbp+Str]
0x18000e323  mov     rax, [rcx]
0x18000e326  lea     r8d, [r15+1]
0x18000e32a  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18000e331  mov     rax, [rax+78h]
0x18000e335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33a  mov     edi, eax
0x18000e33c  test    eax, eax
0x18000e33e  js      short loc_18000E351
0x18000e340  mov     rbx, [rbp+Str]
0x18000e344  mov     ecx, r15d
0x18000e347  mov     [rbp+Str], rcx
0x18000e34b  mov     [rbp+var_8], rbx
0x18000e34f  jmp     short loc_18000E355
0x18000e351  mov     rcx, [rbp+Str]
0x18000e355  test    rcx, rcx
0x18000e358  jz      short loc_18000E367
0x18000e35a  mov     rax, [rcx]
0x18000e35d  mov     rax, [rax+10h]
0x18000e361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e366  nop
0x18000e367  test    edi, edi
0x18000e369  js      loc_18000E420
0x18000e36f  mov     [rbp+pv], r15
0x18000e373  mov     rax, [rbx]
0x18000e376  lea     rdx, [rbp+pv]
0x18000e37a  mov     rcx, rbx
0x18000e37d  mov     rax, [rax+0A0h]
0x18000e384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e389  mov     edi, eax
0x18000e38b  test    eax, eax
0x18000e38d  js      loc_18000E420
0x18000e393  mov     r14, [rbp+pv]
0x18000e397  mov     [rbp+Str], r15
0x18000e39b  lea     rax, [rbp+Str]
0x18000e39f  mov     qword ptr [rsp+50h+ppv], rax; int
0x18000e3a4  lea     r9, _GUID_14056589_e16c_11d2_bb90_00c04f8ee6c0; riid
0x18000e3ab  xor     edx, edx; pUnkOuter
0x18000e3ad  lea     r8d, [rdx+17h]; dwClsContext
0x18000e3b1  lea     rcx, CLSID_SpObjectToken; rclsid
0x18000e3b8  call    cs:__imp_CoCreateInstance
0x18000e3bf  nop     dword ptr [rax+rax+00h]
0x18000e3c4  mov     edi, eax
0x18000e3c6  test    eax, eax
0x18000e3c8  js      short loc_18000E3F9
0x18000e3ca  mov     rcx, [rbp+Str]
0x18000e3ce  mov     rax, [rcx]
0x18000e3d1  xor     r9d, r9d
0x18000e3d4  mov     r8, r14
0x18000e3d7  xor     edx, edx
0x18000e3d9  mov     rax, [rax+78h]
0x18000e3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3e2  mov     edi, eax
0x18000e3e4  test    eax, eax
0x18000e3e6  js      short loc_18000E3F9
0x18000e3e8  mov     rax, [rbp+Str]
0x18000e3ec  mov     rcx, r15
0x18000e3ef  mov     [rbp+Str], rcx
0x18000e3f3  mov     [rbp+arg_8], rax
0x18000e3f7  jmp     short loc_18000E3FD
0x18000e3f9  mov     rcx, [rbp+Str]
0x18000e3fd  test    rcx, rcx
0x18000e400  jz      short loc_18000E40F
0x18000e402  mov     rax, [rcx]
0x18000e405  mov     rax, [rax+10h]
0x18000e409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e40e  nop
0x18000e40f  mov     rcx, [rbp+pv]; pv
0x18000e413  call    cs:__imp_CoTaskMemFree
0x18000e41a  nop     dword ptr [rax+rax+00h]
0x18000e41f  nop
0x18000e420  test    rbx, rbx
0x18000e423  jz      short loc_18000E435
0x18000e425  mov     rax, [rbx]
0x18000e428  mov     rcx, rbx
0x18000e42b  mov     rax, [rax+10h]
0x18000e42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e434  nop
0x18000e435  test    edi, edi
0x18000e437  jns     short loc_18000E473
0x18000e439  mov     rcx, [rbp+28h]; this
0x18000e43d  mov     r9d, edi; char *
0x18000e440  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e447  mov     edx, 85h; void *
0x18000e44c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e451  nop
0x18000e452  mov     rcx, [rbp+arg_8]
0x18000e456  test    rcx, rcx
0x18000e459  jz      short loc_18000E46C
0x18000e45b  mov     [rbp+arg_8], r15
0x18000e45f  mov     rax, [rcx]
0x18000e462  mov     rax, [rax+10h]
0x18000e466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e46b  nop
0x18000e46c  mov     eax, edi
0x18000e46e  jmp     loc_18000EB1F
0x18000e473  mov     rcx, [rbp+arg_8]
0x18000e477  test    rcx, rcx
0x18000e47a  jnz     short loc_18000E49E
0x18000e47c  mov     rcx, [rbp+28h]; this
0x18000e480  mov     ebx, 80070057h
0x18000e485  mov     r9d, ebx; char *
0x18000e488  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e48f  mov     edx, 19Ah; void *
0x18000e494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e499  jmp     loc_18000E56E
0x18000e49e  mov     [rbp+Str], r15
0x18000e4a2  mov     rax, [rcx]
0x18000e4a5  lea     rdx, [rbp+Str]
0x18000e4a9  mov     rax, [rax+80h]
0x18000e4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4b5  mov     ebx, eax
0x18000e4b7  test    eax, eax
0x18000e4b9  jns     short loc_18000E4C8
0x18000e4bb  mov     r9d, eax
0x18000e4be  mov     edx, 19Dh
0x18000e4c3  jmp     loc_18000E548
0x18000e4c8  mov     edx, 5Ch ; '\'; Ch
0x18000e4cd  mov     rcx, [rbp+Str]; Str
0x18000e4d1  call    cs:__imp_wcsrchr
0x18000e4d8  nop     dword ptr [rax+rax+00h]
0x18000e4dd  test    rax, rax
0x18000e4e0  jnz     short loc_18000E4EE
0x18000e4e2  mov     ebx, 8000FFFFh
0x18000e4e7  mov     edx, 1A1h
0x18000e4ec  jmp     short loc_18000E545
0x18000e4ee  lea     r14, [rax+2]
0x18000e4f2  lea     rbx, [rsi+88h]
0x18000e4f9  cmp     r14, [rbx]
0x18000e4fc  jz      short loc_18000E536
0x18000e4fe  mov     rcx, rbx; this
0x18000e501  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000e506  test    r14, r14
0x18000e509  jz      short loc_18000E536
0x18000e50b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e50f  inc     rdi
0x18000e512  cmp     [r14+rdi*2], r15w
0x18000e517  jnz     short loc_18000E50F
0x18000e519  mov     edx, edi; unsigned int
0x18000e51b  mov     rcx, rbx; this
0x18000e51e  call    ?_allocate@CSpDynamicString@@AEAAJK@Z; CSpDynamicString::_allocate(ulong)
0x18000e523  test    eax, eax
0x18000e525  js      short loc_18000E536
0x18000e527  lea     r8, [rdi+rdi]; Size
0x18000e52b  mov     rdx, r14; Src
0x18000e52e  mov     rcx, [rbx]; void *
0x18000e531  call    memcpy_0
0x18000e536  cmp     [rbx], r15
0x18000e539  jnz     short loc_18000E5A8
0x18000e53b  mov     ebx, 8007000Eh
0x18000e540  mov     edx, 1A4h; void *
0x18000e545  mov     r9d, ebx; char *
0x18000e548  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e54f  mov     rcx, [rbp+28h]; this
0x18000e553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e558  nop
0x18000e559  mov     rcx, [rbp+Str]; pv
0x18000e55d  test    rcx, rcx
0x18000e560  jz      short loc_18000E56E
0x18000e562  call    cs:__imp_CoTaskMemFree
0x18000e569  nop     dword ptr [rax+rax+00h]
0x18000e56e  mov     rcx, [rbp+28h]; this
0x18000e572  mov     r9d, ebx; char *
0x18000e575  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e57c  mov     edx, 87h; void *
0x18000e581  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e586  nop
0x18000e587  mov     rcx, [rbp+arg_8]
0x18000e58b  test    rcx, rcx
0x18000e58e  jz      short loc_18000E5A1
0x18000e590  mov     [rbp+arg_8], r15
0x18000e594  mov     rdx, [rcx]
0x18000e597  mov     rax, [rdx+10h]
0x18000e59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5a0  nop
0x18000e5a1  mov     eax, ebx
0x18000e5a3  jmp     loc_18000EB1F
0x18000e5a8  mov     rcx, [rbp+Str]; pv
0x18000e5ac  test    rcx, rcx
0x18000e5af  jz      short loc_18000E5BD
0x18000e5b1  call    cs:__imp_CoTaskMemFree
0x18000e5b8  nop     dword ptr [rax+rax+00h]
0x18000e5bd  mov     [rbp+arg_10], r15
0x18000e5c1  mov     [rbp+arg_18], r15
0x18000e5c5  lea     rax, [rbp+arg_18]
0x18000e5c9  mov     qword ptr [rsp+50h+ppv], rax; int
0x18000e5ce  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x18000e5d5  xor     edx, edx; pUnkOuter
0x18000e5d7  lea     r8d, [rdx+17h]; dwClsContext
0x18000e5db  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x18000e5e2  call    cs:__imp_CoCreateInstance
0x18000e5e9  nop     dword ptr [rax+rax+00h]
0x18000e5ee  mov     edi, eax
0x18000e5f0  test    eax, eax
0x18000e5f2  jns     short loc_18000E660
0x18000e5f4  mov     rcx, [rbp+28h]; this
0x18000e5f8  mov     r9d, eax; char *
0x18000e5fb  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e602  mov     edx, 8Dh; void *
0x18000e607  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e60c  nop
0x18000e60d  mov     rcx, [rbp+arg_18]
0x18000e611  test    rcx, rcx
0x18000e614  jz      short loc_18000E627
0x18000e616  mov     [rbp+arg_18], r15
0x18000e61a  mov     rax, [rcx]
0x18000e61d  mov     rax, [rax+10h]
0x18000e621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e626  nop
0x18000e627  mov     rcx, [rbp+arg_10]
0x18000e62b  test    rcx, rcx
0x18000e62e  jz      short loc_18000E641
0x18000e630  mov     [rbp+arg_10], r15
0x18000e634  mov     rax, [rcx]
0x18000e637  mov     rax, [rax+10h]
0x18000e63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e640  nop
0x18000e641  mov     rcx, [rbp+arg_8]
0x18000e645  test    rcx, rcx
0x18000e648  jz      short loc_18000E65B
0x18000e64a  mov     [rbp+arg_8], r15
0x18000e64e  mov     rax, [rcx]
0x18000e651  mov     rax, [rax+10h]
0x18000e655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e65a  nop
0x18000e65b  jmp     loc_18000E46C
0x18000e660  mov     rdi, [rbp+arg_18]
0x18000e664  mov     rax, [rdi]
0x18000e667  mov     r14, [rax+28h]
0x18000e66b  mov     rcx, [rbp+arg_10]
0x18000e66f  test    rcx, rcx
0x18000e672  jz      short loc_18000E685
0x18000e674  mov     [rbp+arg_10], r15
0x18000e678  mov     rdx, [rcx]
0x18000e67b  mov     rax, [rdx+10h]
0x18000e67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e684  nop
0x18000e685  lea     r8, [rbp+arg_10]
0x18000e689  mov     rdx, [rbx]
0x18000e68c  mov     rcx, rdi
0x18000e68f  mov     rax, r14
0x18000e692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e697  mov     ebx, eax
0x18000e699  test    eax, eax
0x18000e69b  jns     short loc_18000E709
0x18000e69d  mov     rcx, [rbp+28h]; this
0x18000e6a1  mov     r9d, eax; char *
0x18000e6a4  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e6ab  mov     edx, 8Eh; void *
0x18000e6b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6b5  nop
0x18000e6b6  mov     rcx, [rbp+arg_18]
0x18000e6ba  test    rcx, rcx
0x18000e6bd  jz      short loc_18000E6D0
0x18000e6bf  mov     [rbp+arg_18], r15
0x18000e6c3  mov     rax, [rcx]
0x18000e6c6  mov     rax, [rax+10h]
0x18000e6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6cf  nop
0x18000e6d0  mov     rcx, [rbp+arg_10]
0x18000e6d4  test    rcx, rcx
0x18000e6d7  jz      short loc_18000E6EA
0x18000e6d9  mov     [rbp+arg_10], r15
0x18000e6dd  mov     rax, [rcx]
0x18000e6e0  mov     rax, [rax+10h]
0x18000e6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6e9  nop
0x18000e6ea  mov     rcx, [rbp+arg_8]
0x18000e6ee  test    rcx, rcx
0x18000e6f1  jz      short loc_18000E704
0x18000e6f3  mov     [rbp+arg_8], r15
0x18000e6f7  mov     rax, [rcx]
0x18000e6fa  mov     rax, [rax+10h]
0x18000e6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e703  nop
  ... truncated ...
```
