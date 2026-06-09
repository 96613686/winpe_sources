# LoadDeviceProviders(_REG_FAX_SERVICE *)

- ea: `0x140003e50`
- end: `0x140004816`
- name: `?LoadDeviceProviders@@YAHPEAU_REG_FAX_SERVICE@@@Z`
- size: `2502`
- prototype: `__int64 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callers

- `0x140049f40`

## callees

- `0x140002c73`
- `0x140003528`
- `0x140003e50`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x1400698ec`
- `0x1400699d0`
- `0x140069f50`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400046f5`
- `KERNEL32!FreeLibrary` at `0x1400046f5`
- `KERNEL32!GetLastError` at `0x140003f4c`
- `KERNEL32!GetLastError` at `0x140004368`
- `KERNEL32!GetLastError` at `0x1400044bd`
- `KERNEL32!GetLastError` at `0x1400045ab`
- `KERNEL32!GetLastError` at `0x140004748`
- `KERNEL32!GetLastError` at `0x140003f4c`
- `KERNEL32!GetLastError` at `0x140004368`
- `KERNEL32!GetLastError` at `0x1400044bd`
- `KERNEL32!GetLastError` at `0x1400045ab`
- `KERNEL32!GetLastError` at `0x140004748`
- `KERNEL32!LoadLibraryW` at `0x14000434e`
- `KERNEL32!LoadLibraryW` at `0x14000434e`
- `KERNEL32!GetProcessHeap` at `0x140004578`
- `KERNEL32!GetProcessHeap` at `0x140004578`
- `KERNEL32!HeapCreate` at `0x140004593`
- `KERNEL32!HeapCreate` at `0x140004593`
- `KERNEL32!HeapDestroy` at `0x140004719`
- `KERNEL32!HeapDestroy` at `0x140004719`
- `msvcrt!_wcsicmp` at `0x14000424a`
- `msvcrt!_wcsicmp` at `0x140004268`
- `msvcrt!_wcsicmp` at `0x14000424a`
- `msvcrt!_wcsicmp` at `0x140004268`
- `msvcrt!_wsplitpath_s` at `0x1400041e6`
- `msvcrt!_wsplitpath_s` at `0x1400041e6`

## pseudocode

```c
__int64 __fastcall LoadDeviceProviders(struct _REG_FAX_SERVICE *a1)
{
  unsigned int v2; // r15d
  CMapDeviceId *v3; // rbx
  unsigned int v4; // r13d
  void *v5; // rax
  __int64 v6; // rbx
  char LastError; // al
  __int64 v8; // rsi
  HMODULE v9; // r12
  _WORD *v10; // r8
  __int64 v11; // rdx
  const WCHAR *v12; // rcx
  __int64 v13; // rax
  _WORD *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  _WORD *v17; // r8
  const WCHAR *v18; // rax
  __int64 v19; // rcx
  _WORD *v20; // rcx
  _WORD *v21; // r8
  __int64 v22; // rdx
  const WCHAR *v23; // rax
  __int64 v24; // rcx
  _WORD *v25; // rcx
  _WORD *v26; // r8
  __int64 v27; // rdx
  const WCHAR *v28; // rax
  __int64 v29; // rcx
  _WORD *v30; // rcx
  CMapDeviceId *v31; // rcx
  __int64 v32; // r9
  int v33; // eax
  unsigned __int16 *v34; // rdx
  HMODULE LibraryW; // rax
  DWORD v36; // edi
  int v37; // eax
  unsigned __int16 *v38; // rdx
  int FileVersion; // eax
  CMapDeviceId *v40; // rcx
  __int64 v41; // r9
  int v42; // eax
  unsigned __int16 *v43; // rdx
  HANDLE ProcessHeap; // rax
  __int64 *v45; // rax
  void *v46; // rcx
  DWORD v47; // eax
  __int64 *v48; // rax
  size_t FilenameCount; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v51[14]; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t String1[256]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Ext[256]; // [rsp+270h] [rbp+170h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_200271385d87382553faba38592a1280_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = 0;
  if ( *((_DWORD *)a1 + 2) )
  {
    while ( 1 )
    {
      memset_0(String1, 0, sizeof(String1));
      memset_0(Ext, 0, sizeof(Ext));
      if ( v3 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 4) != 0 && *((_BYTE *)v3 + 25) >= 5u )
        WPP_SF_d(*((_QWORD *)v3 + 2), 12, &WPP_200271385d87382553faba38592a1280_Traceguids, v4);
      v5 = (void *)pMemAlloc(0x8D0u);
      v6 = (__int64)v5;
      if ( v5 )
        break;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_200271385d87382553faba38592a1280_Traceguids,
          *(_QWORD *)(*(_QWORD *)a1 + 40LL * v4 + 8),
          LastError);
      }
      v8 = 40LL * v4;
      FaxLog(1, 1, 2, 3221257523LL, *(_QWORD *)(*(_QWORD *)a1 + v8), *(_QWORD *)(*(_QWORD *)a1 + v8 + 8), FilenameCount);
      v2 = 0;
LABEL_124:
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_129;
      }
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_200271385d87382553faba38592a1280_Traceguids,
        *(_QWORD *)(*(_QWORD *)a1 + v8));
LABEL_128:
      v3 = WPP_GLOBAL_Control;
LABEL_129:
      if ( ++v4 >= *((_DWORD *)a1 + 2) )
        return v2;
    }
    v9 = 0;
    memset_0(v5, 0, 0x8D0u);
    v10 = (_WORD *)(v6 + 64);
    v11 = 260;
    v8 = 40LL * v4;
    v12 = &Class;
    if ( *(_QWORD *)(v8 + *(_QWORD *)a1) )
      v12 = *(const WCHAR **)(v8 + *(_QWORD *)a1);
    v13 = 2147483646;
    do
    {
      if ( !v13 )
        break;
      if ( !*v12 )
        break;
      *v10++ = *v12++;
      --v13;
      --v11;
    }
    while ( v11 );
    v14 = v10 - 1;
    v15 = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v14 = v10;
    *v14 = 0;
    if ( !v11 )
      goto LABEL_107;
    v16 = 260;
    v17 = (_WORD *)(v6 + 584);
    v18 = &Class;
    if ( *(_QWORD *)(v8 + *(_QWORD *)a1 + 8) )
      v18 = *(const WCHAR **)(v8 + *(_QWORD *)a1 + 8);
    v19 = 2147483646;
    do
    {
      if ( !v19 )
        break;
      if ( !*v18 )
        break;
      *v17++ = *v18++;
      --v19;
      --v16;
    }
    while ( v16 );
    v20 = v17 - 1;
    v15 = v16 == 0 ? 0x8007007A : 0;
    if ( v16 )
      v20 = v17;
    *v20 = 0;
    if ( !v16 )
      goto LABEL_107;
    v21 = (_WORD *)(v6 + 1104);
    v22 = 260;
    v23 = &Class;
    if ( *(_QWORD *)(v8 + *(_QWORD *)a1 + 16) )
      v23 = *(const WCHAR **)(v8 + *(_QWORD *)a1 + 16);
    v24 = 2147483646;
    do
    {
      if ( !v24 )
        break;
      if ( !*v23 )
        break;
      *v21++ = *v23++;
      --v24;
      --v22;
    }
    while ( v22 );
    v25 = v21 - 1;
    v15 = v22 == 0 ? 0x8007007A : 0;
    if ( v22 )
      v25 = v21;
    *v25 = 0;
    if ( !v22 )
      goto LABEL_107;
    v26 = (_WORD *)(v6 + 1624);
    v27 = 260;
    v28 = &Class;
    if ( *(_QWORD *)(v8 + *(_QWORD *)a1 + 32) )
      v28 = *(const WCHAR **)(v8 + *(_QWORD *)a1 + 32);
    v29 = 2147483646;
    do
    {
      if ( !v29 )
        break;
      if ( !*v28 )
        break;
      *v26++ = *v28++;
      --v29;
      --v27;
    }
    while ( v27 );
    v30 = v26 - 1;
    v15 = v27 == 0 ? 0x8007007A : 0;
    if ( v27 )
      v30 = v26;
    *v30 = 0;
    if ( !v27 )
    {
LABEL_107:
      v31 = WPP_GLOBAL_Control;
LABEL_108:
      if ( v31 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 4) != 0 && *((_BYTE *)v31 + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)v31 + 2), 15, &WPP_200271385d87382553faba38592a1280_Traceguids, v15);
      FaxLog(1, 1, 2, 3221257523LL, *(_QWORD *)(v8 + *(_QWORD *)a1), *(_QWORD *)(v8 + *(_QWORD *)a1 + 8), FilenameCount);
      goto LABEL_113;
    }
    if ( _wsplitpath_s((const wchar_t *)(v6 + 584), 0, 0, 0, 0, String1, 0x100u, Ext, 0x100u) )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_200271385d87382553faba38592a1280_Traceguids);
        v31 = WPP_GLOBAL_Control;
      }
      v15 = 2147500037LL;
      goto LABEL_108;
    }
    if ( !_wcsicmp(String1, L"FXST30") && !_wcsicmp(Ext, L".DLL") )
      *(_DWORD *)(v6 + 2248) = 1;
    v32 = *(unsigned int *)(v8 + *(_QWORD *)a1 + 24);
    *(_DWORD *)(v6 + 2144) = v32;
    if ( (_DWORD)v32 != 0x10000 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_200271385d87382553faba38592a1280_Traceguids, v32);
      }
LABEL_66:
      v51[0] = 0;
      v33 = StringCchPrintfW(v51, 0xCu, L"0x%08X");
      v34 = v51;
      if ( v33 < 0 )
        v34 = 0;
      FaxLog(1, 1, 3, 3221257531LL, *(_QWORD *)(v8 + *(_QWORD *)a1), *(_QWORD *)(v8 + *(_QWORD *)a1 + 8), v34);
      *(_DWORD *)(v6 + 16) = 3;
      *(_DWORD *)(v6 + 20) = 31;
      goto LABEL_113;
    }
    LibraryW = LoadLibraryW((LPCWSTR)(v6 + 584));
    v9 = LibraryW;
    if ( !LibraryW )
    {
      v36 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_200271385d87382553faba38592a1280_Traceguids,
          *(_QWORD *)(v8 + *(_QWORD *)a1 + 8),
          v36);
      }
      v51[0] = 0;
      v37 = StringCchPrintfW(v51, 0xCu, L"%ld", v36);
      v38 = v51;
      if ( v37 < 0 )
        v38 = 0;
      FaxLog(1, 1, 3, 3221257522LL, *(_QWORD *)(v8 + *(_QWORD *)a1), *(_QWORD *)(v8 + *(_QWORD *)a1 + 8), v38);
      *(_DWORD *)(v6 + 16) = 4;
      goto LABEL_77;
    }
    *(_QWORD *)(v6 + 56) = LibraryW;
    *(_DWORD *)(v6 + 24) = 20;
    FileVersion = GetFileVersion(*(LPCWSTR *)(v8 + *(_QWORD *)a1 + 8));
    if ( FileVersion )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_200271385d87382553faba38592a1280_Traceguids,
        *(_QWORD *)(v8 + *(_QWORD *)a1 + 8),
        FileVersion);
    }
    v40 = WPP_GLOBAL_Control;
LABEL_84:
    v41 = *(unsigned int *)(v6 + 2144);
    if ( (_DWORD)v41 != 0x10000 )
    {
      if ( v40 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 4) != 0 && *((_BYTE *)v40 + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)v40 + 2), 21, &WPP_200271385d87382553faba38592a1280_Traceguids, v41);
      goto LABEL_66;
    }
    if ( (unsigned int)GetLegacyProviderEntryPoints(v9) )
    {
      if ( *(_DWORD *)(v6 + 2248) )
        ProcessHeap = GetProcessHeap();
      else
        ProcessHeap = HeapCreate(0, 0x19000u, 0x200000u);
      *(_QWORD *)(v6 + 2152) = ProcessHeap;
      if ( ProcessHeap )
      {
        v45 = (__int64 *)qword_1400A7358;
        *(_QWORD *)v6 = &g_DeviceProvidersListHead;
        *(_QWORD *)(v6 + 8) = v45;
        *v45 = v6;
        qword_1400A7358 = v6;
        *(_QWORD *)(v6 + 16) = 0;
        goto LABEL_128;
      }
      v36 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_200271385d87382553faba38592a1280_Traceguids, v36);
      }
      FaxLog(1, 1, 2, 3221257523LL, *(_QWORD *)(v8 + *(_QWORD *)a1), *(_QWORD *)(v8 + *(_QWORD *)a1 + 8), FilenameCount);
      *(_DWORD *)(v6 + 16) = 1;
    }
    else
    {
      v36 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_200271385d87382553faba38592a1280_Traceguids, v36);
      }
      v51[0] = 0;
      v42 = StringCchPrintfW(v51, 0xCu, L"%ld", v36);
      v43 = v51;
      if ( v42 < 0 )
        v43 = 0;
      FaxLog(1, 1, 3, 3221257529LL, *(_QWORD *)(v8 + *(_QWORD *)a1), *(_QWORD *)(v8 + *(_QWORD *)a1 + 8), v43);
      *(_DWORD *)(v6 + 16) = 5;
    }
LABEL_77:
    *(_DWORD *)(v6 + 20) = v36;
LABEL_113:
    v2 = 0;
    if ( *(_QWORD *)(v6 + 56) )
    {
      FreeLibrary(v9);
      *(_QWORD *)(v6 + 56) = 0;
    }
    v46 = *(void **)(v6 + 2152);
    if ( v46 && !*(_DWORD *)(v6 + 2248) )
    {
      if ( !HeapDestroy(v46)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v47 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_200271385d87382553faba38592a1280_Traceguids, v47);
      }
      *(_QWORD *)(v6 + 2152) = 0;
    }
    v48 = (__int64 *)qword_1400A7358;
    *(_QWORD *)v6 = &g_DeviceProvidersListHead;
    *(_QWORD *)(v6 + 8) = v48;
    *v48 = v6;
    qword_1400A7358 = v6;
    goto LABEL_124;
  }
  return v2;
}

```

## disassembly

```asm
0x140003e50  push    rbp
0x140003e52  push    rbx
0x140003e53  push    rsi
0x140003e54  push    rdi
0x140003e55  push    r12
0x140003e57  push    r13
0x140003e59  push    r14
0x140003e5b  push    r15
0x140003e5d  lea     rbp, [rsp-388h]
0x140003e65  sub     rsp, 488h
0x140003e6c  mov     rax, cs:__security_cookie
0x140003e73  xor     rax, rsp
0x140003e76  mov     [rbp+3C0h+var_50], rax
0x140003e7d  mov     r14, rcx
0x140003e80  mov     r15d, 1
0x140003e86  mov     rbx, cs:WPP_GLOBAL_Control
0x140003e8d  lea     rsi, WPP_GLOBAL_Control
0x140003e94  cmp     rbx, rsi
0x140003e97  jz      short loc_140003EC0
0x140003e99  test    byte ptr [rbx+1Ch], 4
0x140003e9d  jz      short loc_140003EC0
0x140003e9f  cmp     byte ptr [rbx+19h], 5
0x140003ea3  jb      short loc_140003EC0
0x140003ea5  mov     rcx, [rbx+10h]
0x140003ea9  lea     edx, [r15+0Ah]
0x140003ead  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x140003eb4  call    WPP_SF_
0x140003eb9  mov     rbx, cs:WPP_GLOBAL_Control
0x140003ec0  xor     edi, edi
0x140003ec2  mov     r13d, edi
0x140003ec5  cmp     [r14+8], edi
0x140003ec9  jbe     loc_1400047EF
0x140003ecf  xor     edx, edx; Val
0x140003ed1  lea     rcx, [rsp+4C0h+String1]; void *
0x140003ed6  mov     r8d, 200h; Size
0x140003edc  call    memset_0
0x140003ee1  xor     edx, edx; Val
0x140003ee3  lea     rcx, [rbp+3C0h+var_250]; void *
0x140003eea  mov     r8d, 200h; Size
0x140003ef0  call    memset_0
0x140003ef5  cmp     rbx, rsi
0x140003ef8  jz      short loc_140003F1E
0x140003efa  test    byte ptr [rbx+1Ch], 4
0x140003efe  jz      short loc_140003F1E
0x140003f00  cmp     byte ptr [rbx+19h], 5
0x140003f04  jb      short loc_140003F1E
0x140003f06  mov     rcx, [rbx+10h]
0x140003f0a  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x140003f11  mov     edx, 0Ch
0x140003f16  mov     r9d, r13d
0x140003f19  call    WPP_SF_d
0x140003f1e  mov     ecx, 8D0h; dwBytes
0x140003f23  call    pMemAlloc
0x140003f28  mov     rbx, rax
0x140003f2b  test    rax, rax
0x140003f2e  jnz     loc_140003FCC
0x140003f34  mov     rax, cs:WPP_GLOBAL_Control
0x140003f3b  cmp     rax, rsi
0x140003f3e  jz      short loc_140003F89
0x140003f40  test    byte ptr [rax+1Ch], 4
0x140003f44  jz      short loc_140003F89
0x140003f46  cmp     byte ptr [rax+19h], 2
0x140003f4a  jb      short loc_140003F89
0x140003f4c  call    cs:__imp_GetLastError
0x140003f53  nop     dword ptr [rax+rax+00h]
0x140003f58  mov     r9, [r14]
0x140003f5b  lea     edx, [rbx+0Dh]
0x140003f5e  mov     r8d, eax
0x140003f61  mov     eax, r13d
0x140003f64  mov     dword ptr [rsp+4C0h+DirCount], r8d
0x140003f69  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x140003f70  lea     rcx, [rax+rax*4]
0x140003f74  mov     r9, [r9+rcx*8+8]
0x140003f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f80  mov     rcx, [rcx+10h]
0x140003f84  call    WPP_SF_Sd
0x140003f89  mov     edx, 1
0x140003f8e  mov     eax, r13d
0x140003f91  mov     r9d, 0C0007D33h
0x140003f97  lea     rcx, [rax+rax*4]
0x140003f9b  lea     rsi, ds:0[rcx*8]
0x140003fa3  mov     rcx, [r14]
0x140003fa6  lea     r8d, [rdx+1]
0x140003faa  mov     rax, [rcx+rsi+8]
0x140003faf  mov     [rsp+4C0h+Filename], rax
0x140003fb4  mov     rax, [rcx+rsi]
0x140003fb8  mov     ecx, edx
0x140003fba  mov     [rsp+4C0h+DirCount], rax
0x140003fbf  call    FaxLog
0x140003fc4  mov     r15d, edi
0x140003fc7  jmp     loc_140004799
0x140003fcc  xor     edx, edx; Val
0x140003fce  mov     r8d, 8D0h; Size
0x140003fd4  mov     rcx, rbx; void *
0x140003fd7  mov     r12, rdi
0x140003fda  call    memset_0
0x140003fdf  mov     eax, r13d
0x140003fe2  lea     r8, [rbx+40h]
0x140003fe6  mov     r10d, 7FFFFFFEh
0x140003fec  mov     edx, 104h
0x140003ff1  lea     rcx, [rax+rax*4]
0x140003ff5  mov     rax, [r14]
0x140003ff8  lea     rsi, ds:0[rcx*8]
0x140004000  lea     rcx, Class
0x140004007  cmp     [rsi+rax], rdi
0x14000400b  cmovnz  rcx, [rsi+rax]
0x140004010  mov     eax, r10d
0x140004013  test    rax, rax
0x140004016  jz      short loc_140004037
0x140004018  movzx   r9d, word ptr [rcx]
0x14000401c  test    r9w, r9w
0x140004020  jz      short loc_140004037
0x140004022  mov     [r8], r9w
0x140004026  add     rcx, 2
0x14000402a  add     r8, 2
0x14000402e  dec     rax
0x140004031  sub     rdx, 1
0x140004035  jnz     short loc_140004013
0x140004037  mov     rax, rdx
0x14000403a  lea     rcx, [r8-2]
0x14000403e  neg     rax
0x140004041  mov     r11d, 8007007Ah
0x140004047  sbb     r9d, r9d
0x14000404a  not     r9d
0x14000404d  and     r9d, r11d
0x140004050  test    rdx, rdx
0x140004053  cmovnz  rcx, r8
0x140004057  mov     [rcx], di
0x14000405a  jz      loc_140004689
0x140004060  mov     rax, [r14]
0x140004063  lea     rdi, [rbx+248h]
0x14000406a  mov     edx, 104h
0x14000406f  mov     r8, rdi
0x140004072  mov     rcx, [rsi+rax+8]
0x140004077  lea     rax, Class
0x14000407e  test    rcx, rcx
0x140004081  cmovnz  rax, rcx
0x140004085  mov     rcx, r10
0x140004088  xor     r10d, r10d
0x14000408b  test    rcx, rcx
0x14000408e  jz      short loc_1400040AF
0x140004090  movzx   r9d, word ptr [rax]
0x140004094  test    r9w, r9w
0x140004098  jz      short loc_1400040AF
0x14000409a  mov     [r8], r9w
0x14000409e  add     rax, 2
0x1400040a2  add     r8, 2
0x1400040a6  dec     rcx
0x1400040a9  sub     rdx, 1
0x1400040ad  jnz     short loc_14000408B
0x1400040af  mov     rax, rdx
0x1400040b2  lea     rcx, [r8-2]
0x1400040b6  neg     rax
0x1400040b9  sbb     r9d, r9d
0x1400040bc  not     r9d
0x1400040bf  and     r9d, r11d
0x1400040c2  test    rdx, rdx
0x1400040c5  cmovnz  rcx, r8
0x1400040c9  mov     [rcx], r10w
0x1400040cd  jz      loc_140004687
0x1400040d3  mov     rax, [r14]
0x1400040d6  lea     r8, [rbx+450h]
0x1400040dd  mov     edx, 104h
0x1400040e2  mov     rcx, [rsi+rax+10h]
0x1400040e7  lea     rax, Class
0x1400040ee  test    rcx, rcx
0x1400040f1  cmovnz  rax, rcx
0x1400040f5  mov     ecx, 7FFFFFFEh
0x1400040fa  test    rcx, rcx
0x1400040fd  jz      short loc_14000411E
0x1400040ff  movzx   r9d, word ptr [rax]
0x140004103  test    r9w, r9w
0x140004107  jz      short loc_14000411E
0x140004109  mov     [r8], r9w
0x14000410d  add     rax, 2
0x140004111  add     r8, 2
0x140004115  dec     rcx
0x140004118  sub     rdx, 1
0x14000411c  jnz     short loc_1400040FA
0x14000411e  mov     rax, rdx
0x140004121  lea     rcx, [r8-2]
0x140004125  neg     rax
0x140004128  sbb     r9d, r9d
0x14000412b  not     r9d
0x14000412e  and     r9d, r11d
0x140004131  test    rdx, rdx
0x140004134  cmovnz  rcx, r8
0x140004138  mov     [rcx], r10w
0x14000413c  jz      loc_140004687
0x140004142  mov     rax, [r14]
0x140004145  lea     r8, [rbx+658h]
0x14000414c  mov     edx, 104h
0x140004151  mov     rcx, [rsi+rax+20h]
0x140004156  lea     rax, Class
0x14000415d  test    rcx, rcx
0x140004160  cmovnz  rax, rcx
0x140004164  mov     ecx, 7FFFFFFEh
0x140004169  test    rcx, rcx
0x14000416c  jz      short loc_14000418D
0x14000416e  movzx   r9d, word ptr [rax]
0x140004172  test    r9w, r9w
0x140004176  jz      short loc_14000418D
0x140004178  mov     [r8], r9w
0x14000417c  add     rax, 2
0x140004180  add     r8, 2
0x140004184  dec     rcx
0x140004187  sub     rdx, 1
0x14000418b  jnz     short loc_140004169
0x14000418d  mov     rax, rdx
0x140004190  lea     rcx, [r8-2]
0x140004194  neg     rax
0x140004197  sbb     r9d, r9d
0x14000419a  not     r9d
0x14000419d  and     r9d, r11d
0x1400041a0  test    rdx, rdx
0x1400041a3  cmovnz  rcx, r8
0x1400041a7  mov     [rcx], r10w
0x1400041ab  jz      loc_140004687
0x1400041b1  mov     ecx, 100h
0x1400041b6  lea     rax, [rbp+3C0h+var_250]
0x1400041bd  mov     [rsp+4C0h+ExtCount], rcx; ExtCount
0x1400041c2  xor     r9d, r9d; Dir
0x1400041c5  mov     [rsp+4C0h+Ext], rax; Ext
0x1400041ca  xor     r8d, r8d; DriveCount
0x1400041cd  mov     [rsp+4C0h+FilenameCount], rcx; FilenameCount
0x1400041d2  lea     rax, [rsp+4C0h+String1]
0x1400041d7  mov     [rsp+4C0h+Filename], rax; Filename
0x1400041dc  xor     edx, edx; Drive
0x1400041de  mov     rcx, rdi; FullPath
0x1400041e1  mov     [rsp+4C0h+DirCount], r10; DirCount
0x1400041e6  call    cs:__imp__wsplitpath_s
0x1400041ed  nop     dword ptr [rax+rax+00h]
0x1400041f2  test    eax, eax
0x1400041f4  jz      short loc_14000423E
0x1400041f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400041fd  lea     rdx, WPP_GLOBAL_Control
0x140004204  cmp     rcx, rdx
0x140004207  jz      short loc_140004231
0x140004209  test    byte ptr [rcx+1Ch], 4
0x14000420d  jz      short loc_140004231
0x14000420f  cmp     byte ptr [rcx+19h], 2
0x140004213  jb      short loc_140004231
0x140004215  mov     rcx, [rcx+10h]
0x140004219  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x140004220  mov     edx, 0Eh
0x140004225  call    WPP_SF_
0x14000422a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004231  xor     edi, edi
0x140004233  mov     r9d, 80004005h
0x140004239  jmp     loc_140004690
0x14000423e  lea     rdx, aFxst30; "FXST30"
0x140004245  lea     rcx, [rsp+4C0h+String1]; String1
0x14000424a  call    cs:__imp__wcsicmp
0x140004251  nop     dword ptr [rax+rax+00h]
0x140004256  test    eax, eax
0x140004258  jnz     short loc_140004282
0x14000425a  lea     rdx, aDll; ".DLL"
0x140004261  lea     rcx, [rbp+3C0h+var_250]; String1
0x140004268  call    cs:__imp__wcsicmp
0x14000426f  nop     dword ptr [rax+rax+00h]
0x140004274  test    eax, eax
0x140004276  jnz     short loc_140004282
0x140004278  mov     dword ptr [rbx+8C8h], 1
0x140004282  mov     rax, [r14]
0x140004285  mov     r9d, [rsi+rax+18h]
0x14000428a  mov     [rbx+860h], r9d
0x140004291  cmp     r9d, 10000h
0x140004298  jz      loc_14000434B
0x14000429e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042a5  lea     rax, WPP_GLOBAL_Control
0x1400042ac  cmp     rcx, rax
0x1400042af  jz      short loc_1400042D2
0x1400042b1  test    byte ptr [rcx+1Ch], 4
0x1400042b5  jz      short loc_1400042D2
0x1400042b7  cmp     byte ptr [rcx+19h], 2
0x1400042bb  jb      short loc_1400042D2
0x1400042bd  mov     rcx, [rcx+10h]
0x1400042c1  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x1400042c8  mov     edx, 10h
0x1400042cd  call    WPP_SF_d
0x1400042d2  xor     edi, edi
0x1400042d4  mov     r9d, [rbx+860h]
0x1400042db  lea     r8, a0x08x; "0x%08X"
0x1400042e2  mov     edx, 0Ch; unsigned __int64
0x1400042e7  mov     [rsp+4C0h+var_470], r9d
0x1400042ec  lea     rcx, [rsp+4C0h+var_46C]; unsigned __int16 *
0x1400042f1  mov     [rsp+4C0h+var_46C], di
0x1400042f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400042fb  mov     rcx, [r14]
0x1400042fe  lea     rdx, [rsp+4C0h+var_46C]
0x140004303  test    eax, eax
0x140004305  mov     r15d, 3
0x14000430b  mov     r9d, 0C0007D3Bh
0x140004311  mov     r8d, r15d
0x140004314  cmovs   rdx, rdi
0x140004318  mov     rax, [rsi+rcx+8]
0x14000431d  mov     [rsp+4C0h+FilenameCount], rdx
0x140004322  lea     edx, [r15-2]
0x140004326  mov     [rsp+4C0h+Filename], rax
0x14000432b  mov     rax, [rsi+rcx]
  ... truncated ...
```
