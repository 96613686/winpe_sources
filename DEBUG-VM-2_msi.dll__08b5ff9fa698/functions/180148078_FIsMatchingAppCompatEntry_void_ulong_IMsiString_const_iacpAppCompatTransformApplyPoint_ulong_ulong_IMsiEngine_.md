# FIsMatchingAppCompatEntry(void *,ulong,IMsiString const &,iacpAppCompatTransformApplyPoint,ulong *,ulong *,IMsiEngine &,IMsiDatabase &)

- ea: `0x180148078`
- end: `0x180148898`
- name: `?FIsMatchingAppCompatEntry@@YA_NPEAXKAEBVIMsiString@@W4iacpAppCompatTransformApplyPoint@@PEAK3AEAVIMsiEngine@@AEAVIMsiDatabase@@@Z`
- size: `2080`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180097d10`

## callees

- `0x180025a18`
- `0x1800616e0`
- `0x1800620e4`
- `0x180148078`
- `0x1801488a0`
- `0x1801571ac`
- `0x180214d90`
- `0x180215108`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1801484d9`
- `msvcrt!_wcsnicmp` at `0x1801485ca`
- `msvcrt!_wcsnicmp` at `0x180148668`
- `msvcrt!_wcsnicmp` at `0x1801484d9`
- `msvcrt!_wcsnicmp` at `0x1801485ca`
- `msvcrt!_wcsnicmp` at `0x180148668`
- `KERNEL32!lstrlenW` at `0x180148720`
- `KERNEL32!lstrlenW` at `0x180148720`
- `KERNEL32!lstrcmpiW` at `0x18014841a`
- `KERNEL32!lstrcmpiW` at `0x18014843f`
- `KERNEL32!lstrcmpiW` at `0x180148462`
- `KERNEL32!lstrcmpiW` at `0x180148485`
- `KERNEL32!lstrcmpiW` at `0x1801484a8`
- `KERNEL32!lstrcmpiW` at `0x18014841a`
- `KERNEL32!lstrcmpiW` at `0x18014843f`
- `KERNEL32!lstrcmpiW` at `0x180148462`
- `KERNEL32!lstrcmpiW` at `0x180148485`
- `KERNEL32!lstrcmpiW` at `0x1801484a8`

## string_xrefs

- `0x180148284`: `SHIMSERVICEPACKLEVEL`
- `0x18014849e`: `SHIMSERVICEPACKLEVEL`
- `0x180148118`: `MINMSIVERSION`
- `0x180148410`: `MINMSIVERSION`
- `0x1801487bd`: `APPCOMPAT: SdbQueryData failed unexpectedly.  Sdb may be invalid.`
- `0x180148184`: `APPCOMPAT: invalid minimum version string '%s' found.`
- `0x180148208`: `APPCOMPAT: skipping this entry.  Minimum MSI version required: '%s'; current version: %d.%02d.%04d.%02d.`
- `0x1801484cf`: `MSIPROPERTY_`
- `0x18014831b`: `APPCOMPAT: skipping transform because it should be applied at a different point of the install.`
- `0x180148756`: `APPCOMPAT: mismatched attributes.  Property: '%s'; expected value: '%s'; true value: '%s'`
- `0x180148515`: `APPCOMPAT: testing Property value.  Property: '%s'; expected value: '%s'`
- `0x1801485e9`: `APPCOMPAT: testing PackageCode.  Expected value: '%s'`
- `0x180148680`: `APPCOMPAT: testing cell data in '%s' table.`
- `0x18014865e`: `MSIDBCELL`
- `0x18014881e`: `APPCOMPAT: PackageCode attribute(s) exist, but no matching PackageCode found.  Actual PackageCode: '%s'`
- `0x1801486e8`: `APPCOMPAT: ignoring unknown data.  Data name: '%s', data type: %d`

## pseudocode

```c
char __fastcall FIsMatchingAppCompatEntry(
        void *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        _DWORD *a6,
        __int64 a7,
        struct IMsiDatabase *a8)
{
  void *v9; // r12
  char v10; // r13
  char v12; // r15
  int v14; // ebx
  LPCWSTR v15; // r14
  char v16; // bl
  const unsigned __int16 *v17; // rax
  __int64 v18; // rbx
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // rax
  unsigned int v21; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+64h] [rbp-9Ch]
  unsigned __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  __int64 v26; // [rsp+80h] [rbp-80h]
  void *v27; // [rsp+88h] [rbp-78h]
  struct IMsiDatabase *v28; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v29; // [rsp+A0h] [rbp-60h] BYREF
  int v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+ACh] [rbp-54h]
  _BYTE v32[256]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpString1; // [rsp+1B0h] [rbp+B0h] BYREF
  int v34; // [rsp+1B8h] [rbp+B8h]
  int v35; // [rsp+1BCh] [rbp+BCh]
  _BYTE v36[256]; // [rsp+1C0h] [rbp+C0h] BYREF

  v9 = a1;
  v26 = a7;
  v10 = 0;
  v25 = a3;
  v24 = a2;
  v27 = a1;
  v28 = a8;
  v21 = 0;
  memset_0(v32, 0, sizeof(v32));
  v29 = (unsigned __int16 *)v32;
  v30 = 256;
  v31 = 256;
  v12 = 1;
  if ( !(unsigned int)LocalSdbQueryData(
                        (_DWORD)v9,
                        a2,
                        (unsigned int)L"MINMSIVERSION",
                        (unsigned int)&v21,
                        (__int64)&v29,
                        0)
    && v21 == 1 )
  {
    v23 = 0;
    if ( !(unsigned int)ParseVersionString(v29, (char *)&v23 + 4, &v23) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: invalid minimum version string '%s' found.",
          v29,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( v30 > 256 )
        operator delete(v29);
      return 0;
    }
    if ( v23 > 0x50000271B0000LL )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: skipping this entry.  Minimum MSI version required: '%s'; current version: %d.%02d.%04d.%02d.",
          v29,
          (const unsigned __int16 *)5,
          0,
          (const unsigned __int16 *)0x271B,
          0,
          L"(NULL)",
          0,
          0);
LABEL_23:
      CTempBuffer<unsigned short,256>::~CTempBuffer<unsigned short,256>(&v29);
      return 0;
    }
  }
  v31 = 256;
  if ( !(unsigned int)LocalSdbQueryData(
                        (_DWORD)v9,
                        a2,
                        (unsigned int)L"SHIMVERSIONNT",
                        (unsigned int)&v21,
                        (__int64)&v29,
                        0)
    && v21 == 4 )
  {
    *a5 = *(_DWORD *)v29;
    v31 = 256;
    if ( !(unsigned int)LocalSdbQueryData(
                          (_DWORD)v9,
                          a2,
                          (unsigned int)L"SHIMSERVICEPACKLEVEL",
                          (unsigned int)&v21,
                          (__int64)&v29,
                          0)
      && v21 == 4 )
    {
      *a6 = *(_DWORD *)v29;
    }
  }
  v31 = 256;
  v14 = 1;
  if ( !(unsigned int)LocalSdbQueryData(
                        (_DWORD)v9,
                        a2,
                        (unsigned int)L"APPLYPOINT",
                        (unsigned int)&v21,
                        (__int64)&v29,
                        0)
    && v21 == 4 )
  {
    v14 = *(_DWORD *)v29;
  }
  if ( v14 != a4 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: skipping transform because it should be applied at a different point of the install.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_23;
  }
  memset_0(v36, 0, sizeof(v36));
  v34 = 256;
  lpString1 = (LPCWSTR)v36;
  v35 = 256;
  if ( !(unsigned __int8)GetSdbDataNames(v9, a2, &lpString1) )
    goto LABEL_74;
  v15 = lpString1;
  v16 = 0;
  v22 = 0;
  while ( *v15 )
  {
    LODWORD(v23) = 0;
    v31 = 256;
    if ( (unsigned int)LocalSdbQueryData((_DWORD)v9, v24, (_DWORD)v15, (unsigned int)&v21, (__int64)&v29, (__int64)&v23) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: SdbQueryData failed unexpectedly.  Sdb may be invalid.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_66;
    }
    v17 = (const unsigned __int16 *)v21;
    if ( v21 == 1 )
    {
      if ( !lstrcmpiW(v15, L"MINMSIVERSION") )
        goto LABEL_62;
      v17 = (const unsigned __int16 *)v21;
    }
    if ( (_DWORD)v17 == 4 )
    {
      if ( !lstrcmpiW(v15, L"APPLYPOINT") )
        goto LABEL_62;
      v17 = (const unsigned __int16 *)v21;
      if ( v21 == 4 )
      {
        if ( !lstrcmpiW(v15, L"SHIMFLAGS") )
          goto LABEL_62;
        v17 = (const unsigned __int16 *)v21;
        if ( v21 == 4 )
        {
          if ( !lstrcmpiW(v15, L"SHIMVERSIONNT") )
            goto LABEL_62;
          v17 = (const unsigned __int16 *)v21;
          if ( v21 == 4 )
          {
            if ( !lstrcmpiW(v15, L"SHIMSERVICEPACKLEVEL") )
              goto LABEL_62;
            v17 = (const unsigned __int16 *)v21;
          }
        }
      }
    }
    if ( (unsigned int)v17 > 1 )
      goto LABEL_60;
    if ( _wcsnicmp(v15, L"MSIPROPERTY_", 0xCu) )
    {
      v17 = (const unsigned __int16 *)v21;
      if ( v21 != 1 )
        goto LABEL_60;
      if ( !_wcsnicmp(v15, L"PACKAGECODE", 0xBu) )
      {
        v16 = 1;
        v22 = 1;
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: testing PackageCode.  Expected value: '%s'",
            v29,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v25 + 200LL))(
               v25,
               1,
               v29) )
        {
          v10 = 1;
        }
        goto LABEL_62;
      }
      v17 = (const unsigned __int16 *)v21;
      if ( v21 != 1 )
        goto LABEL_60;
      if ( _wcsnicmp(v15, L"MSIDBCELL", 9u) )
      {
        v17 = (const unsigned __int16 *)v21;
LABEL_60:
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: ignoring unknown data.  Data name: '%s', data type: %d",
            v15,
            v17,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_62;
      }
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: testing cell data in '%s' table.",
          v29,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( !FCheckDatabaseCell(v9, v23, v28, v29) )
        goto LABEL_66;
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(__int64, LPCWSTR))(*(_QWORD *)v26 + 184LL))(v26, v15 + 12);
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: testing Property value.  Property: '%s'; expected value: '%s'",
          v15 + 12,
          v29,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v18 + 200LL))(v18, 0, v29)
        || !(*(unsigned int (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v18 + 200LL))(v18, 7, v29) )
      {
        if ( g_dmDiagnosticMode )
        {
          v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 80LL))(v18);
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: mismatched attributes.  Property: '%s'; expected value: '%s'; true value: '%s'",
            v15 + 12,
            v29,
            v19,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_66:
        CTempBuffer<unsigned short,256>::~CTempBuffer<unsigned short,256>(&lpString1);
        goto LABEL_23;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v16 = v22;
      v9 = v27;
    }
LABEL_62:
    v15 += lstrlenW(v15) + 1;
  }
  if ( v16 == 1 && !v10 )
  {
    if ( g_dmDiagnosticMode )
    {
      v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: PackageCode attribute(s) exist, but no matching PackageCode found.  Actual PackageCode: '%s'",
        v20,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v12 = 0;
  }
LABEL_74:
  CTempBuffer<unsigned short,256>::~CTempBuffer<unsigned short,256>(&lpString1);
  CTempBuffer<unsigned short,256>::~CTempBuffer<unsigned short,256>(&v29);
  return v12;
}

```

## disassembly

```asm
0x180148078  mov     [rsp-8+arg_18], rbx
0x18014807d  push    rbp
0x18014807e  push    rsi
0x18014807f  push    rdi
0x180148080  push    r12
0x180148082  push    r13
0x180148084  push    r14
0x180148086  push    r15
0x180148088  lea     rbp, [rsp-1D0h]
0x180148090  sub     rsp, 2D0h
0x180148097  mov     rax, cs:__security_cookie
0x18014809e  xor     rax, rsp
0x1801480a1  mov     [rbp+200h+var_40], rax
0x1801480a8  mov     rax, [rbp+200h+arg_30]
0x1801480af  mov     r14d, edx
0x1801480b2  mov     rdi, [rbp+200h+arg_20]
0x1801480b9  mov     r12, rcx
0x1801480bc  mov     rbx, [rbp+200h+arg_28]
0x1801480c3  mov     r15d, 100h
0x1801480c9  mov     [rbp+200h+var_280], rax
0x1801480cd  xor     r13d, r13d
0x1801480d0  mov     rax, [rbp+200h+arg_38]
0x1801480d7  mov     esi, r9d
0x1801480da  mov     [rsp+300h+var_288], r8
0x1801480df  mov     r8d, r15d; Size
0x1801480e2  mov     [rsp+300h+var_290], edx
0x1801480e6  xor     edx, edx; Val
0x1801480e8  mov     [rbp+200h+var_278], rcx
0x1801480ec  lea     rcx, [rbp+200h+var_250]; void *
0x1801480f0  mov     [rbp+200h+var_270], rax
0x1801480f4  mov     dword ptr [rsp+300h+var_2A0], r13d
0x1801480f9  call    memset_0
0x1801480fe  lea     rax, [rbp+200h+var_250]
0x180148102  mov     [rsp+300h+var_2D8], r13
0x180148107  mov     [rbp+200h+var_260], rax
0x18014810b  lea     r9, [rsp+300h+var_2A0]
0x180148110  lea     rax, [rbp+200h+var_260]
0x180148114  mov     [rbp+200h+var_258], r15d
0x180148118  lea     r8, aMinmsiversion; "MINMSIVERSION"
0x18014811f  mov     [rsp+300h+var_2E0], rax
0x180148124  mov     edx, r14d
0x180148127  mov     [rbp+200h+var_254], r15d
0x18014812b  mov     rcx, r12
0x18014812e  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x180148133  lea     r15d, [r13+1]
0x180148137  test    eax, eax
0x180148139  jnz     loc_18014823F
0x18014813f  cmp     dword ptr [rsp+300h+var_2A0], r15d
0x180148144  jnz     loc_18014823F
0x18014814a  mov     rcx, [rbp+200h+var_260]
0x18014814e  lea     r8, [rsp+300h+var_298]
0x180148153  lea     rdx, [rsp+300h+var_298+4]
0x180148158  mov     dword ptr [rsp+300h+var_298+4], r13d
0x18014815d  mov     dword ptr [rsp+300h+var_298], r13d
0x180148162  call    ?ParseVersionString@@YA?AW4Bool@@PEBGAEAK1@Z; ParseVersionString(ushort const *,ulong &,ulong &)
0x180148167  test    eax, eax
0x180148169  jnz     short loc_1801481D4
0x18014816b  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180148172  jz      short loc_1801481BB
0x180148174  mov     rax, [rbp+200h+var_260]
0x180148178  lea     rdi, aNull; "(NULL)"
0x18014817f  mov     [rsp+300h+var_2A8], r13; void *
0x180148184  lea     r9, aAppcompatInval; "APPCOMPAT: invalid minimum version stri"...
0x18014818b  mov     [rsp+300h+var_2B0], r13d; unsigned int
0x180148190  xor     edx, edx; unsigned __int16
0x180148192  mov     [rsp+300h+var_2B8], rdi; unsigned __int16 *
0x180148197  xor     r8d, r8d; int
0x18014819a  mov     [rsp+300h+var_2C0], rdi; unsigned __int16 *
0x18014819f  mov     [rsp+300h+var_2C8], rdi; unsigned __int16 *
0x1801481a4  mov     [rsp+300h+var_2D0], rdi; unsigned __int16 *
0x1801481a9  lea     ecx, [rdx+9]; int
0x1801481ac  mov     [rsp+300h+var_2D8], rdi; unsigned __int16 *
0x1801481b1  mov     [rsp+300h+var_2E0], rax; unsigned __int16 *
0x1801481b6  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801481bb  cmp     [rbp+200h+var_258], 100h
0x1801481c2  jle     short loc_1801481CD
0x1801481c4  mov     rcx, [rbp+200h+var_260]; void *
0x1801481c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801481cd  xor     al, al
0x1801481cf  jmp     loc_18014886E
0x1801481d4  mov     eax, 50000h
0x1801481d9  cmp     dword ptr [rsp+300h+var_298+4], eax
0x1801481dd  ja      short loc_1801481EB
0x1801481df  jnz     short loc_18014823F
0x1801481e1  cmp     dword ptr [rsp+300h+var_298], 271B0000h
0x1801481e9  jbe     short loc_18014823F
0x1801481eb  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801481f2  jz      loc_18014834D
0x1801481f8  mov     rax, [rbp+200h+var_260]
0x1801481fc  lea     rdi, aNull; "(NULL)"
0x180148203  mov     [rsp+300h+var_2A8], r13
0x180148208  lea     r9, aAppcompatSkipp; "APPCOMPAT: skipping this entry.  Minimu"...
0x18014820f  mov     [rsp+300h+var_2B0], r13d
0x180148214  mov     [rsp+300h+var_2B8], rdi
0x180148219  mov     [rsp+300h+var_2C0], r13
0x18014821e  mov     [rsp+300h+var_2C8], 271Bh
0x180148227  mov     [rsp+300h+var_2D0], r13
0x18014822c  mov     [rsp+300h+var_2D8], 5
0x180148235  mov     [rsp+300h+var_2E0], rax
0x18014823a  jmp     loc_180148340
0x18014823f  lea     rax, [rbp+200h+var_260]
0x180148243  mov     [rsp+300h+var_2D8], r13
0x180148248  lea     r9, [rsp+300h+var_2A0]
0x18014824d  mov     [rsp+300h+var_2E0], rax
0x180148252  lea     r8, aShimversionnt_1; "SHIMVERSIONNT"
0x180148259  mov     [rbp+200h+var_254], 100h
0x180148260  mov     edx, r14d
0x180148263  mov     rcx, r12
0x180148266  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x18014826b  test    eax, eax
0x18014826d  jnz     short loc_1801482BD
0x18014826f  cmp     dword ptr [rsp+300h+var_2A0], 4
0x180148274  jnz     short loc_1801482BD
0x180148276  mov     rax, [rbp+200h+var_260]
0x18014827a  lea     r9, [rsp+300h+var_2A0]
0x18014827f  mov     [rsp+300h+var_2D8], r13
0x180148284  lea     r8, aShimservicepac_0; "SHIMSERVICEPACKLEVEL"
0x18014828b  mov     edx, r14d
0x18014828e  mov     ecx, [rax]
0x180148290  lea     rax, [rbp+200h+var_260]
0x180148294  mov     [rdi], ecx
0x180148296  mov     rcx, r12
0x180148299  mov     [rsp+300h+var_2E0], rax
0x18014829e  mov     [rbp+200h+var_254], 100h
0x1801482a5  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x1801482aa  test    eax, eax
0x1801482ac  jnz     short loc_1801482BD
0x1801482ae  cmp     dword ptr [rsp+300h+var_2A0], 4
0x1801482b3  jnz     short loc_1801482BD
0x1801482b5  mov     rax, [rbp+200h+var_260]
0x1801482b9  mov     ecx, [rax]
0x1801482bb  mov     [rbx], ecx
0x1801482bd  lea     rax, [rbp+200h+var_260]
0x1801482c1  mov     [rsp+300h+var_2D8], r13
0x1801482c6  lea     r9, [rsp+300h+var_2A0]
0x1801482cb  mov     [rsp+300h+var_2E0], rax
0x1801482d0  lea     r8, aApplypoint; "APPLYPOINT"
0x1801482d7  mov     [rbp+200h+var_254], 100h
0x1801482de  mov     edx, r14d
0x1801482e1  mov     rcx, r12
0x1801482e4  mov     ebx, r15d
0x1801482e7  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x1801482ec  test    eax, eax
0x1801482ee  jnz     short loc_1801482FD
0x1801482f0  cmp     dword ptr [rsp+300h+var_2A0], 4
0x1801482f5  jnz     short loc_1801482FD
0x1801482f7  mov     rax, [rbp+200h+var_260]
0x1801482fb  mov     ebx, [rax]
0x1801482fd  cmp     ebx, esi
0x1801482ff  jz      short loc_18014835B
0x180148301  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180148308  jz      short loc_18014834D
0x18014830a  mov     [rsp+300h+var_2A8], r13; void *
0x18014830f  lea     rdi, aNull; "(NULL)"
0x180148316  mov     [rsp+300h+var_2B0], r13d; unsigned int
0x18014831b  lea     r9, aAppcompatSkipp_0; "APPCOMPAT: skipping transform because i"...
0x180148322  mov     [rsp+300h+var_2B8], rdi; unsigned __int16 *
0x180148327  mov     [rsp+300h+var_2C0], rdi; unsigned __int16 *
0x18014832c  mov     [rsp+300h+var_2C8], rdi; unsigned __int16 *
0x180148331  mov     [rsp+300h+var_2D0], rdi; unsigned __int16 *
0x180148336  mov     [rsp+300h+var_2D8], rdi; unsigned __int16 *
0x18014833b  mov     [rsp+300h+var_2E0], rdi; unsigned __int16 *
0x180148340  xor     edx, edx; unsigned __int16
0x180148342  xor     r8d, r8d; int
0x180148345  lea     ecx, [rdx+9]; int
0x180148348  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18014834d  lea     rcx, [rbp+200h+var_260]
0x180148351  call    ??1?$CTempBuffer@G$0BAA@@@QEAA@XZ; CTempBuffer<ushort,256>::~CTempBuffer<ushort,256>(void)
0x180148356  jmp     loc_1801481CD
0x18014835b  mov     ebx, 100h
0x180148360  lea     rcx, [rbp+200h+var_140]; void *
0x180148367  mov     r8d, ebx; Size
0x18014836a  xor     edx, edx; Val
0x18014836c  call    memset_0
0x180148371  lea     rax, [rbp+200h+var_140]
0x180148378  mov     [rbp+200h+var_148], ebx
0x18014837e  lea     r8, [rbp+200h+lpString1]
0x180148385  mov     [rbp+200h+lpString1], rax
0x18014838c  mov     edx, r14d
0x18014838f  mov     [rbp+200h+var_144], ebx
0x180148395  mov     rcx, r12
0x180148398  call    ?GetSdbDataNames@@YA_NPEAXKAEAV?$CTempBufferRef@E@@@Z; GetSdbDataNames(void *,ulong,CTempBufferRef<uchar> &)
0x18014839d  test    al, al
0x18014839f  jz      loc_180148856
0x1801483a5  mov     r14, [rbp+200h+lpString1]
0x1801483ac  lea     rdi, aNull; "(NULL)"
0x1801483b3  mov     bl, r13b
0x1801483b6  mov     esi, 9
0x1801483bb  mov     byte ptr [rsp+300h+var_2A0+4], bl
0x1801483bf  xor     eax, eax
0x1801483c1  cmp     [r14], ax
0x1801483c5  jz      loc_1801487F4
0x1801483cb  mov     edx, [rsp+300h+var_290]
0x1801483cf  lea     r9, [rsp+300h+var_2A0]
0x1801483d4  mov     dword ptr [rsp+300h+var_298], eax
0x1801483d8  mov     r8, r14
0x1801483db  lea     rax, [rsp+300h+var_298]
0x1801483e0  mov     [rbp+200h+var_254], 100h
0x1801483e7  mov     [rsp+300h+var_2D8], rax
0x1801483ec  mov     rcx, r12
0x1801483ef  lea     rax, [rbp+200h+var_260]
0x1801483f3  mov     [rsp+300h+var_2E0], rax
0x1801483f8  call    ?LocalSdbQueryData@@YAKPEAXKPEBGPEAKAEAV?$CTempBufferRef@E@@2@Z; LocalSdbQueryData(void *,ulong,ushort const *,ulong *,CTempBufferRef<uchar> &,ulong *)
0x1801483fd  xor     ecx, ecx
0x1801483ff  test    eax, eax
0x180148401  jnz     loc_1801487B0
0x180148407  mov     eax, dword ptr [rsp+300h+var_2A0]
0x18014840b  cmp     eax, r15d
0x18014840e  jnz     short loc_18014842C
0x180148410  lea     rdx, aMinmsiversion; "MINMSIVERSION"
0x180148417  mov     rcx, r14; lpString1
0x18014841a  call    cs:__imp_lstrcmpiW
0x180148420  test    eax, eax
0x180148422  jz      loc_18014871D
0x180148428  mov     eax, dword ptr [rsp+300h+var_2A0]
0x18014842c  cmp     eax, 4
0x18014842f  jnz     loc_1801484BE
0x180148435  lea     rdx, aApplypoint; "APPLYPOINT"
0x18014843c  mov     rcx, r14; lpString1
0x18014843f  call    cs:__imp_lstrcmpiW
0x180148445  xor     ecx, ecx
0x180148447  test    eax, eax
0x180148449  jz      loc_18014871D
0x18014844f  mov     eax, dword ptr [rsp+300h+var_2A0]
0x180148453  cmp     eax, 4
0x180148456  jnz     short loc_1801484C0
0x180148458  lea     rdx, aShimflags; "SHIMFLAGS"
0x18014845f  mov     rcx, r14; lpString1
0x180148462  call    cs:__imp_lstrcmpiW
0x180148468  xor     ecx, ecx
0x18014846a  test    eax, eax
0x18014846c  jz      loc_18014871D
0x180148472  mov     eax, dword ptr [rsp+300h+var_2A0]
0x180148476  cmp     eax, 4
0x180148479  jnz     short loc_1801484C0
0x18014847b  lea     rdx, aShimversionnt_1; "SHIMVERSIONNT"
0x180148482  mov     rcx, r14; lpString1
0x180148485  call    cs:__imp_lstrcmpiW
0x18014848b  xor     ecx, ecx
0x18014848d  test    eax, eax
0x18014848f  jz      loc_18014871D
0x180148495  mov     eax, dword ptr [rsp+300h+var_2A0]
0x180148499  cmp     eax, 4
0x18014849c  jnz     short loc_1801484C0
0x18014849e  lea     rdx, aShimservicepac_0; "SHIMSERVICEPACKLEVEL"
0x1801484a5  mov     rcx, r14; lpString1
0x1801484a8  call    cs:__imp_lstrcmpiW
0x1801484ae  xor     ecx, ecx
0x1801484b0  test    eax, eax
0x1801484b2  jz      loc_18014871D
0x1801484b8  mov     eax, dword ptr [rsp+300h+var_2A0]
0x1801484bc  jmp     short loc_1801484C0
0x1801484be  xor     ecx, ecx
0x1801484c0  cmp     eax, r15d
0x1801484c3  ja      loc_1801486DB
0x1801484c9  mov     r8d, 0Ch; MaxCount
0x1801484cf  lea     rdx, aMsiproperty; "MSIPROPERTY_"
0x1801484d6  mov     rcx, r14; String1
0x1801484d9  call    cs:__imp__wcsnicmp
0x1801484df  xor     ecx, ecx
0x1801484e1  test    eax, eax
0x1801484e3  jnz     loc_1801485AD
0x1801484e9  mov     rcx, [rbp+200h+var_280]
0x1801484ed  lea     r12, [r14+18h]
0x1801484f1  mov     rdx, r12
0x1801484f4  mov     rax, [rcx]
0x1801484f7  mov     rax, [rax+0B8h]
0x1801484fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148503  mov     rbx, rax
0x180148506  xor     eax, eax
0x180148508  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18014850e  jz      short loc_18014854E
0x180148510  mov     [rsp+300h+var_2A8], rax; void *
0x180148515  lea     r9, aAppcompatTesti_0; "APPCOMPAT: testing Property value.  Pro"...
0x18014851c  mov     [rsp+300h+var_2B0], eax; unsigned int
0x180148520  xor     edx, edx; unsigned __int16
0x180148522  mov     rax, [rbp+200h+var_260]
0x180148526  xor     r8d, r8d; int
0x180148529  mov     [rsp+300h+var_2B8], rdi; unsigned __int16 *
0x18014852e  mov     ecx, esi; int
0x180148530  mov     [rsp+300h+var_2C0], rdi; unsigned __int16 *
0x180148535  mov     [rsp+300h+var_2C8], rdi; unsigned __int16 *
0x18014853a  mov     [rsp+300h+var_2D0], rdi; unsigned __int16 *
0x18014853f  mov     [rsp+300h+var_2D8], rax; unsigned __int16 *
0x180148544  mov     [rsp+300h+var_2E0], r12; unsigned __int16 *
0x180148549  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18014854e  mov     rax, [rbx]
0x180148551  xor     edx, edx
0x180148553  mov     r8, [rbp+200h+var_260]
0x180148557  mov     rcx, rbx
0x18014855a  mov     rax, [rax+0C8h]
0x180148561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148566  test    eax, eax
0x180148568  jz      loc_180148736
0x18014856e  mov     rax, [rbx]
0x180148571  mov     edx, 7
0x180148576  mov     r8, [rbp+200h+var_260]
0x18014857a  mov     rcx, rbx
0x18014857d  mov     rax, [rax+0C8h]
0x180148584  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
