# EURL::IsScriptMappedAndEnabled(_HTTP_FILTER_CONTEXT *)

- ea: `0x1800022a0`
- end: `0x1800028cf`
- name: `?IsScriptMappedAndEnabled@EURL@@CAHPEAU_HTTP_FILTER_CONTEXT@@@Z`
- size: `1583`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002248`

## callees

- `0x1800022a0`
- `0x180002dbc`
- `0x180002e7c`
- `0x180002ee8`
- `0x1800030d4`
- `0x180003238`
- `0x180003950`
- `0x180004308`
- `0x18000430e`
- `0x1800043b0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1800024ee`
- `KERNEL32!GetModuleFileNameW` at `0x1800024ee`
- `KERNEL32!lstrlenW` at `0x18000253c`
- `KERNEL32!lstrlenW` at `0x180002564`
- `KERNEL32!lstrlenW` at `0x180002596`
- `KERNEL32!lstrlenW` at `0x180002691`
- `KERNEL32!lstrlenW` at `0x180002774`
- `KERNEL32!lstrlenW` at `0x18000253c`
- `KERNEL32!lstrlenW` at `0x180002564`
- `KERNEL32!lstrlenW` at `0x180002596`
- `KERNEL32!lstrlenW` at `0x180002691`
- `KERNEL32!lstrlenW` at `0x180002774`
- `KERNEL32!GetLastError` at `0x180002371`
- `KERNEL32!GetLastError` at `0x180002371`
- `ole32!CoCreateInstance` at `0x18000233f`
- `ole32!CoCreateInstance` at `0x18000233f`
- `ole32!CoUninitialize` at `0x1800027b4`
- `ole32!CoUninitialize` at `0x1800027b4`
- `ucrtbase_clr0400!_wcsnicmp` at `0x180002557`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800025c1`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800026d5`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18000271e`
- `ucrtbase_clr0400!_wcsnicmp` at `0x180002557`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800025c1`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800026d5`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18000271e`

## string_xrefs

- `0x18000251c`: `aspnet_isapi.dll`
- `0x18000268a`: `*.dll`
- `0x1800026c0`: `*.dll`

## pseudocode

```c
__int64 __fastcall EURL::IsScriptMappedAndEnabled(struct _HTTP_FILTER_CONTEXT *a1)
{
  int v2; // r13d
  BOOL v3; // r15d
  unsigned int v4; // edi
  int v5; // r12d
  BOOL v6; // ebx
  int v7; // r14d
  __int64 v8; // rax
  const unsigned __int16 *v9; // r14
  unsigned int v10; // ebx
  unsigned __int16 *v11; // r13
  int v12; // eax
  wchar_t *v13; // rbx
  wchar_t *v14; // rax
  size_t v15; // r13
  wchar_t *v16; // rcx
  int v17; // eax
  wchar_t *v18; // rbx
  size_t v19; // r13
  size_t v20; // r12
  BOOL v21; // esi
  __int64 v22; // rcx
  int v23; // r14d
  __int64 v24; // rcx
  unsigned __int16 *v26; // rsi
  int v27; // ecx
  unsigned int v28; // [rsp+44h] [rbp-C4h] BYREF
  BOOL v29; // [rsp+48h] [rbp-C0h]
  int v30; // [rsp+4Ch] [rbp-BCh]
  __int64 v31; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  int v33; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+64h] [rbp-A4h]
  __int64 v35; // [rsp+6Ch] [rbp-9Ch]
  wchar_t *String1; // [rsp+78h] [rbp-90h]
  int v37; // [rsp+80h] [rbp-88h]
  int v38; // [rsp+88h] [rbp-80h]
  int v39[3]; // [rsp+8Ch] [rbp-7Ch] BYREF
  size_t MaxCount; // [rsp+98h] [rbp-70h]
  unsigned __int16 *v41; // [rsp+A0h] [rbp-68h]
  WCHAR Filename[264]; // [rsp+A8h] [rbp-60h] BYREF

  v28 = 0;
  v2 = 0;
  v39[0] = 0;
  ppv = 0;
  v3 = 0;
  v4 = 1;
  LODWORD(v31) = 0;
  v5 = 1;
  v29 = 0;
  v38 = 0;
  v6 = 0;
  v30 = 0;
  v7 = 0;
  if ( !(unsigned int)EnsureCoInitialized(v39)
    && !CoCreateInstance(&CLSID_MSAdminBase_W, 0, 0x15u, &IID_IMSAdminBase_W, &ppv)
    && !((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, _QWORD, __int64 *))a1->GetServerVariable)(
          a1,
          "UNICODE_INSTANCE_ID",
          0,
          &v31)
    && GetLastError() == 122 )
  {
    v8 = ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(a1, (unsigned int)v31, 0);
    v9 = (const unsigned __int16 *)v8;
    if ( !v8 )
    {
LABEL_8:
      v7 = 0;
      goto LABEL_64;
    }
    if ( !((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, __int64, __int64 *))a1->GetServerVariable)(
            a1,
            "UNICODE_INSTANCE_ID",
            v8,
            &v31) )
    {
      GetLastWin32Error();
      goto LABEL_8;
    }
    v10 = v31 + 34;
    v41 = (unsigned __int16 *)((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(
                                a1,
                                (unsigned int)(v31 + 34),
                                0);
    v11 = v41;
    if ( (unsigned int)StringCbCopyW(v41, v10, L"/LM/W3SVC/") )
      goto LABEL_75;
    v12 = StringCbCatW(v11, v10, v9);
    v7 = 0;
    if ( v12 )
      goto LABEL_18;
    if ( (unsigned int)StringCbCatW(v11, v10, L"/root") )
      goto LABEL_18;
    v33 = 6014;
    v34 = 1;
    v35 = 5;
    String1 = 0;
    v37 = 0;
    if ( (*(unsigned int (__fastcall **)(LPVOID, _QWORD, unsigned __int16 *, int *, unsigned int *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           0,
           v11,
           &v33,
           &v28) != -2147024774 )
      goto LABEL_18;
    String1 = (wchar_t *)((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(
                           a1,
                           v28,
                           0);
    if ( !String1 )
      goto LABEL_18;
    HIDWORD(v35) = v28;
    if ( (*(unsigned int (__fastcall **)(LPVOID, _QWORD, unsigned __int16 *, int *, unsigned int *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           0,
           v11,
           &v33,
           &v28) )
    {
      goto LABEL_18;
    }
    v13 = String1;
    if ( !String1 )
      goto LABEL_18;
    if ( !GetModuleFileNameW(g_DllInstance, Filename, 0x105u) )
    {
      GetLastWin32Error();
LABEL_18:
      v6 = 0;
      v2 = 0;
      goto LABEL_64;
    }
    v14 = wcsrchr_0(Filename, 0x5Cu);
    if ( !v14 )
      goto LABEL_18;
    v14[1] = 0;
    if ( (unsigned int)StringCchCatW(Filename, 0x105u, L"aspnet_isapi.dll") )
      goto LABEL_18;
    v15 = (unsigned int)lstrlenW(Filename);
    while ( 1 )
    {
      if ( !*v13 )
        goto LABEL_18;
      if ( !_wcsnicmp(v13, L".axd,", 5u) )
        break;
      v13 += lstrlenW(v13) + 1;
    }
    v16 = wcschr_0(v13 + 5, 0x2Cu);
    if ( !v16 )
      v16 = &v13[lstrlenW(v13)];
    MaxCount = v15;
    if ( &v13[v15 + 5] != v16 )
    {
LABEL_75:
      v6 = 0;
      v7 = 0;
      v2 = 0;
      goto LABEL_64;
    }
    v7 = 0;
    if ( _wcsnicmp(v13 + 5, Filename, v15) )
      goto LABEL_18;
    v33 = 2168;
    v34 = 1;
    LODWORD(v35) = 5;
    v2 = 1;
    v37 = 0;
    v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, int *, unsigned int *))(*(_QWORD *)ppv + 80LL))(
            ppv,
            0,
            L"/LM/W3SVC",
            &v33,
            &v28);
    if ( v17 == -2147024774 )
    {
      String1 = (wchar_t *)((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(
                             a1,
                             v28,
                             0);
      if ( !String1 )
      {
LABEL_76:
        v6 = 0;
        goto LABEL_64;
      }
      HIDWORD(v35) = v28;
      v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, int *, unsigned int *))(*(_QWORD *)ppv + 80LL))(
              ppv,
              0,
              L"/LM/W3SVC",
              &v33,
              &v28);
    }
    if ( !v17 )
    {
      v18 = String1;
      if ( String1 )
      {
        v19 = (unsigned int)lstrlenW(L"*.dll");
        if ( !*v18 )
          goto LABEL_61;
        v20 = MaxCount;
        while ( 1 )
        {
          if ( v18[1] != 44 )
          {
LABEL_55:
            v21 = v29;
            goto LABEL_56;
          }
          v21 = *v18 == 49;
          if ( _wcsnicmp(v18 + 2, L"*.dll", v19) )
            break;
          v22 = (unsigned int)(v19 + 2);
          if ( v18[v22] != 44 )
          {
            if ( v18[v22] )
              break;
          }
          if ( !v38 )
          {
            v29 = v21;
            v38 = 1;
LABEL_56:
            v23 = v30;
            goto LABEL_57;
          }
          v23 = v30;
          if ( !v29 )
            goto LABEL_50;
          v29 = v21;
LABEL_57:
          v18 += lstrlenW(v18) + 1;
          if ( !*v18 )
          {
            if ( !v3 && (v23 || !v21) )
            {
LABEL_61:
              v5 = 1;
              goto LABEL_62;
            }
            v26 = v41;
            v33 = 6016;
            v34 = 1;
            v5 = 0;
            LODWORD(v35) = 1;
            v37 = 0;
            if ( (*(unsigned int (__fastcall **)(LPVOID, _QWORD, unsigned __int16 *, int *, unsigned int *))(*(_QWORD *)ppv + 80LL))(
                   ppv,
                   0,
                   v41,
                   &v33,
                   &v28) )
            {
LABEL_62:
              v6 = 0;
              v2 = 1;
            }
            else
            {
              v27 = *(_DWORD *)String1 & 0x5201;
              v33 = 2104;
              v34 = 1;
              LODWORD(v35) = 1;
              v6 = v27 == 513;
              v37 = 0;
              v2 = 1;
              if ( !(*(unsigned int (__fastcall **)(LPVOID, _QWORD, unsigned __int16 *, int *, unsigned int *))(*(_QWORD *)ppv + 80LL))(
                      ppv,
                      0,
                      v26,
                      &v33,
                      &v28) )
              {
                v7 = 1;
                goto LABEL_64;
              }
            }
            v7 = 0;
            goto LABEL_64;
          }
        }
        if ( _wcsnicmp(v18 + 2, Filename, v20) )
        {
          v23 = v30;
        }
        else
        {
          v24 = (unsigned int)(v20 + 2);
          if ( v18[v24] != 44 && v18[v24] )
            goto LABEL_55;
          v23 = v30;
          if ( v30 )
          {
            if ( v3 )
              v3 = v21;
          }
          else
          {
            v3 = v21;
            v30 = 1;
            v23 = 1;
          }
        }
LABEL_50:
        v21 = v29;
        goto LABEL_57;
      }
    }
    goto LABEL_76;
  }
LABEL_64:
  if ( v39[0] )
    CoUninitialize();
  if ( !v2 || v5 || !v6 || !v7 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x1800022a0  mov     rax, rsp
0x1800022a3  mov     [rax+10h], rbx
0x1800022a7  mov     [rax+18h], rsi
0x1800022ab  mov     [rax+20h], rdi
0x1800022af  push    rbp
0x1800022b0  push    r12
0x1800022b2  push    r13
0x1800022b4  push    r14
0x1800022b6  push    r15
0x1800022b8  lea     rbp, [rax-1E8h]
0x1800022bf  sub     rsp, 2C0h
0x1800022c6  mov     rax, cs:__security_cookie
0x1800022cd  xor     rax, rsp
0x1800022d0  mov     [rbp+1E0h+var_30], rax
0x1800022d7  xor     eax, eax
0x1800022d9  mov     rsi, rcx
0x1800022dc  lea     rcx, [rbp+1E0h+var_25C]; int *
0x1800022e0  mov     [rsp+2E0h+var_2A4], eax
0x1800022e4  mov     r13d, eax
0x1800022e7  mov     [rbp+1E0h+var_25C], eax
0x1800022ea  mov     [rsp+2E0h+var_290], rax
0x1800022ef  mov     r15d, eax
0x1800022f2  lea     edi, [rax+1]
0x1800022f5  mov     dword ptr [rsp+2E0h+var_298], eax
0x1800022f9  mov     r12d, edi
0x1800022fc  mov     [rsp+2E0h+var_2A0], eax
0x180002300  mov     [rbp+1E0h+var_260], eax
0x180002303  mov     ebx, eax
0x180002305  mov     [rsp+2E0h+var_29C], eax
0x180002309  mov     r14d, eax
0x18000230c  mov     [rsp+2E0h+var_2AC], eax
0x180002310  mov     [rsp+2E0h+var_2B0], eax
0x180002314  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x180002319  test    eax, eax
0x18000231b  jnz     loc_1800027AD
0x180002321  lea     rax, [rsp+2E0h+var_290]
0x180002326  xor     edx, edx; pUnkOuter
0x180002328  lea     r9, IID_IMSAdminBase_W; riid
0x18000232f  mov     [rsp+2E0h+ppv], rax; ppv
0x180002334  lea     r8d, [rdi+14h]; dwClsContext
0x180002338  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x18000233f  call    cs:__imp_CoCreateInstance
0x180002345  test    eax, eax
0x180002347  jnz     loc_1800027AD
0x18000234d  mov     rax, [rsi+20h]
0x180002351  lea     r9, [rsp+2E0h+var_298]
0x180002356  xor     r8d, r8d
0x180002359  lea     rdx, aUnicodeInstanc; "UNICODE_INSTANCE_ID"
0x180002360  mov     rcx, rsi
0x180002363  call    cs:__guard_dispatch_icall_fptr
0x180002369  test    eax, eax
0x18000236b  jnz     loc_1800027AD
0x180002371  call    cs:__imp_GetLastError
0x180002377  cmp     eax, 7Ah ; 'z'
0x18000237a  jnz     loc_1800027AD
0x180002380  mov     edx, dword ptr [rsp+2E0h+var_298]
0x180002384  xor     r8d, r8d
0x180002387  mov     rax, [rsi+38h]
0x18000238b  mov     rcx, rsi
0x18000238e  call    cs:__guard_dispatch_icall_fptr
0x180002394  mov     r14, rax
0x180002397  test    rax, rax
0x18000239a  jz      short loc_1800023C1
0x18000239c  mov     r8, rax
0x18000239f  lea     r9, [rsp+2E0h+var_298]
0x1800023a4  mov     rax, [rsi+20h]
0x1800023a8  lea     rdx, aUnicodeInstanc; "UNICODE_INSTANCE_ID"
0x1800023af  mov     rcx, rsi
0x1800023b2  call    cs:__guard_dispatch_icall_fptr
0x1800023b8  test    eax, eax
0x1800023ba  jnz     short loc_1800023C9
0x1800023bc  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800023c1  mov     r14d, ebx
0x1800023c4  jmp     loc_1800027AD
0x1800023c9  mov     ebx, dword ptr [rsp+2E0h+var_298]
0x1800023cd  xor     r8d, r8d
0x1800023d0  mov     rax, [rsi+38h]
0x1800023d4  add     ebx, 22h ; '"'
0x1800023d7  mov     edx, ebx
0x1800023d9  mov     rcx, rsi
0x1800023dc  call    cs:__guard_dispatch_icall_fptr
0x1800023e2  lea     r8, aLmW3svc_1; "/LM/W3SVC/"
0x1800023e9  mov     edx, ebx; unsigned __int64
0x1800023eb  mov     rcx, rax; unsigned __int16 *
0x1800023ee  mov     [rbp+1E0h+var_248], rax
0x1800023f2  mov     r13, rax
0x1800023f5  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800023fa  test    eax, eax
0x1800023fc  jnz     loc_1800028B7
0x180002402  mov     r8, r14; unsigned __int16 *
0x180002405  mov     edx, ebx; unsigned __int64
0x180002407  mov     rcx, r13; unsigned __int16 *
0x18000240a  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18000240f  xor     r14d, r14d
0x180002412  test    eax, eax
0x180002414  jnz     loc_1800024FD
0x18000241a  lea     r8, aRoot; "/root"
0x180002421  mov     edx, ebx; unsigned __int64
0x180002423  mov     rcx, r13; unsigned __int16 *
0x180002426  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18000242b  test    eax, eax
0x18000242d  jnz     loc_1800024FD
0x180002433  mov     rcx, [rsp+2E0h+var_290]
0x180002438  lea     rdx, [rsp+2E0h+var_2A4]
0x18000243d  mov     [rsp+2E0h+var_288], 177Eh
0x180002445  lea     r9, [rsp+2E0h+var_288]
0x18000244a  mov     [rsp+2E0h+var_284], rdi
0x18000244f  mov     r8, r13
0x180002452  mov     qword ptr [rsp+64h], 5
0x18000245b  mov     [rsp+2E0h+String1], r14
0x180002460  mov     [rsp+2E0h+var_268], r14d
0x180002465  mov     rax, [rcx]
0x180002468  mov     [rsp+2E0h+ppv], rdx
0x18000246d  xor     edx, edx
0x18000246f  mov     rax, [rax+50h]
0x180002473  call    cs:__guard_dispatch_icall_fptr
0x180002479  cmp     eax, 8007007Ah
0x18000247e  jnz     short loc_1800024FD
0x180002480  mov     edx, [rsp+2E0h+var_2A4]
0x180002484  xor     r8d, r8d
0x180002487  mov     rax, [rsi+38h]
0x18000248b  mov     rcx, rsi
0x18000248e  call    cs:__guard_dispatch_icall_fptr
0x180002494  mov     [rsp+2E0h+String1], rax
0x180002499  test    rax, rax
0x18000249c  jz      short loc_1800024FD
0x18000249e  mov     eax, [rsp+2E0h+var_2A4]
0x1800024a2  lea     rdx, [rsp+2E0h+var_2A4]
0x1800024a7  mov     rcx, [rsp+2E0h+var_290]
0x1800024ac  lea     r9, [rsp+2E0h+var_288]
0x1800024b1  mov     dword ptr [rsp+2E0h+var_278], eax
0x1800024b5  mov     r8, r13
0x1800024b8  mov     [rsp+2E0h+ppv], rdx
0x1800024bd  xor     edx, edx
0x1800024bf  mov     rax, [rcx]
0x1800024c2  mov     rax, [rax+50h]
0x1800024c6  call    cs:__guard_dispatch_icall_fptr
0x1800024cc  test    eax, eax
0x1800024ce  jnz     short loc_1800024FD
0x1800024d0  mov     rbx, [rsp+2E0h+String1]
0x1800024d5  test    rbx, rbx
0x1800024d8  jz      short loc_1800024FD
0x1800024da  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800024e1  lea     rdx, [rbp+1E0h+Filename]; lpFilename
0x1800024e5  mov     r13d, 105h
0x1800024eb  mov     r8d, r13d; nSize
0x1800024ee  call    cs:__imp_GetModuleFileNameW
0x1800024f4  test    eax, eax
0x1800024f6  jnz     short loc_180002509
0x1800024f8  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800024fd  mov     ebx, [rsp+2E0h+var_2AC]
0x180002501  mov     r13d, r14d
0x180002504  jmp     loc_1800027AD
0x180002509  mov     edx, 5Ch ; '\'; Ch
0x18000250e  lea     rcx, [rbp+1E0h+Filename]; Str
0x180002512  call    wcsrchr_0
0x180002517  test    rax, rax
0x18000251a  jz      short loc_1800024FD
0x18000251c  lea     r8, aAspnetIsapiDll; "aspnet_isapi.dll"
0x180002523  mov     [rax+2], r14w
0x180002528  mov     rdx, r13; unsigned __int64
0x18000252b  lea     rcx, [rbp+1E0h+Filename]; unsigned __int16 *
0x18000252f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002534  test    eax, eax
0x180002536  jnz     short loc_1800024FD
0x180002538  lea     rcx, [rbp+1E0h+Filename]; lpString
0x18000253c  call    cs:__imp_lstrlenW
0x180002542  mov     r13d, eax
0x180002545  jmp     short loc_180002572
0x180002547  mov     r8d, 5; MaxCount
0x18000254d  lea     rdx, aAxd; ".axd,"
0x180002554  mov     rcx, rbx; String1
0x180002557  call    cs:__imp__wcsnicmp
0x18000255d  test    eax, eax
0x18000255f  jz      short loc_18000257A
0x180002561  mov     rcx, rbx; lpString
0x180002564  call    cs:__imp_lstrlenW
0x18000256a  add     eax, edi
0x18000256c  cdqe
0x18000256e  lea     rbx, [rbx+rax*2]
0x180002572  cmp     [rbx], r14w
0x180002576  jnz     short loc_180002547
0x180002578  jmp     short loc_1800024FD
0x18000257a  lea     r14, [rbx+0Ah]
0x18000257e  mov     edx, 2Ch ; ','; Ch
0x180002583  mov     rcx, r14; Str
0x180002586  call    wcschr_0
0x18000258b  mov     rcx, rax
0x18000258e  test    rax, rax
0x180002591  jnz     short loc_1800025A3
0x180002593  mov     rcx, rbx; lpString
0x180002596  call    cs:__imp_lstrlenW
0x18000259c  movsxd  rcx, eax
0x18000259f  lea     rcx, [rbx+rcx*2]
0x1800025a3  lea     rax, [r14+r13*2]
0x1800025a7  mov     rdx, r13
0x1800025aa  mov     [rbp+1E0h+MaxCount], rdx
0x1800025ae  cmp     rax, rcx
0x1800025b1  jnz     loc_1800028B7
0x1800025b7  mov     r8, rdx; MaxCount
0x1800025ba  mov     rcx, r14; String1
0x1800025bd  lea     rdx, [rbp+1E0h+Filename]; String2
0x1800025c1  call    cs:__imp__wcsnicmp
0x1800025c7  xor     r14d, r14d
0x1800025ca  test    eax, eax
0x1800025cc  jnz     loc_1800024FD
0x1800025d2  mov     rcx, [rsp+2E0h+var_290]
0x1800025d7  lea     rdx, [rsp+2E0h+var_2A4]
0x1800025dc  mov     [rsp+2E0h+var_288], 878h
0x1800025e4  lea     r9, [rsp+2E0h+var_288]
0x1800025e9  mov     [rsp+2E0h+var_284], rdi
0x1800025ee  lea     r8, aLmW3svc; "/LM/W3SVC"
0x1800025f5  mov     [rsp+2E0h+var_27C], 5
0x1800025fd  mov     r13d, edi
0x180002600  mov     [rsp+2E0h+var_268], r14d
0x180002605  mov     rax, [rcx]
0x180002608  mov     [rsp+2E0h+ppv], rdx
0x18000260d  xor     edx, edx
0x18000260f  mov     rax, [rax+50h]
0x180002613  call    cs:__guard_dispatch_icall_fptr
0x180002619  cmp     eax, 8007007Ah
0x18000261e  jnz     short loc_180002674
0x180002620  mov     edx, [rsp+2E0h+var_2A4]
0x180002624  xor     r8d, r8d
0x180002627  mov     rax, [rsi+38h]
0x18000262b  mov     rcx, rsi
0x18000262e  call    cs:__guard_dispatch_icall_fptr
0x180002634  mov     [rsp+2E0h+String1], rax
0x180002639  test    rax, rax
0x18000263c  jz      loc_1800028C6
0x180002642  mov     eax, [rsp+2E0h+var_2A4]
0x180002646  lea     rdx, [rsp+2E0h+var_2A4]
0x18000264b  mov     rcx, [rsp+2E0h+var_290]
0x180002650  lea     r9, [rsp+2E0h+var_288]
0x180002655  mov     dword ptr [rsp+2E0h+var_278], eax
0x180002659  lea     r8, aLmW3svc; "/LM/W3SVC"
0x180002660  mov     [rsp+2E0h+ppv], rdx
0x180002665  xor     edx, edx
0x180002667  mov     rax, [rcx]
0x18000266a  mov     rax, [rax+50h]
0x18000266e  call    cs:__guard_dispatch_icall_fptr
0x180002674  test    eax, eax
0x180002676  jnz     loc_1800028C6
0x18000267c  mov     rbx, [rsp+2E0h+String1]
0x180002681  test    rbx, rbx
0x180002684  jz      loc_1800028C6
0x18000268a  lea     rcx, aDll; "*.dll"
0x180002691  call    cs:__imp_lstrlenW
0x180002697  mov     r13d, eax
0x18000269a  cmp     [rbx], r14w
0x18000269e  jz      loc_18000279E
0x1800026a4  mov     r12, [rbp+1E0h+MaxCount]
0x1800026a8  jmp     short loc_1800026AD
0x1800026aa  xor     r14d, r14d
0x1800026ad  mov     eax, 2Ch ; ','
0x1800026b2  cmp     [rbx+2], ax
0x1800026b6  jnz     loc_180002768
0x1800026bc  cmp     word ptr [rbx], 31h ; '1'
0x1800026c0  lea     rdx, aDll; "*.dll"
0x1800026c7  mov     esi, r14d
0x1800026ca  lea     rcx, [rbx+4]; String1
0x1800026ce  mov     r8, r13; MaxCount
0x1800026d1  setz    sil
0x1800026d5  call    cs:__imp__wcsnicmp
0x1800026db  xor     edx, edx
0x1800026dd  test    eax, eax
0x1800026df  jnz     short loc_180002713
0x1800026e1  lea     ecx, [r13+2]
0x1800026e5  lea     eax, [rdx+2Ch]
0x1800026e8  cmp     [rbx+rcx*2], ax
0x1800026ec  jz      short loc_1800026F4
0x1800026ee  cmp     [rbx+rcx*2], dx
0x1800026f2  jnz     short loc_180002713
0x1800026f4  cmp     [rbp+1E0h+var_260], edx
0x1800026f7  jnz     short loc_180002702
0x1800026f9  mov     [rsp+2E0h+var_2A0], esi
0x1800026fd  mov     [rbp+1E0h+var_260], edi
0x180002700  jmp     short loc_18000276C
0x180002702  mov     r14d, [rsp+2E0h+var_29C]
0x180002707  cmp     [rsp+2E0h+var_2A0], edx
0x18000270b  jz      short loc_180002752
0x18000270d  mov     [rsp+2E0h+var_2A0], esi
0x180002711  jmp     short loc_180002771
0x180002713  mov     r8, r12; MaxCount
0x180002716  lea     rdx, [rbp+1E0h+Filename]; String2
0x18000271a  lea     rcx, [rbx+4]; String1
0x18000271e  call    cs:__imp__wcsnicmp
0x180002724  xor     edx, edx
0x180002726  test    eax, eax
0x180002728  jnz     short loc_180002761
0x18000272a  lea     ecx, [r12+2]
0x18000272f  lea     eax, [rdx+2Ch]
0x180002732  cmp     [rbx+rcx*2], ax
0x180002736  jz      short loc_18000273E
0x180002738  cmp     [rbx+rcx*2], dx
0x18000273c  jnz     short loc_180002768
0x18000273e  mov     r14d, [rsp+2E0h+var_29C]
0x180002743  test    r14d, r14d
0x180002746  jnz     short loc_180002758
0x180002748  mov     r15d, esi
  ... truncated ...
```
