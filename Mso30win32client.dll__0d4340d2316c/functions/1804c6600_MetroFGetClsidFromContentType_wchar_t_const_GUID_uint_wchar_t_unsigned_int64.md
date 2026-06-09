# MetroFGetClsidFromContentType(wchar_t const *,_GUID *,uint *,wchar_t *,unsigned __int64)

- ea: `0x1804c6600`
- end: `0x1804c6ad4`
- name: `?MetroFGetClsidFromContentType@@YA_NPEB_WPEAU_GUID@@PEAIPEA_W_K@Z`
- size: `1236`
- prototype: `bool __fastcall(const wchar_t *, struct _GUID *, unsigned int *, wchar_t *, unsigned __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1804c5740`
- `0x1804c5f34`
- `0x1806373f0`

## callees

- `0x18001d3ec`
- `0x180044ad0`
- `0x180190732`
- `0x180192520`
- `0x1804c6600`
- `0x1804c6ad4`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1804c6827`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1804c6827`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1804c678f`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1804c6816`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1804c68b8`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1804c68dd`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1804c678f`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1804c6816`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1804c68b8`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1804c68dd`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1804c67db`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1804c6884`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1804c6926`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1804c67db`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1804c6884`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1804c6926`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1804c67bd`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1804c6866`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1804c6908`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1804c67bd`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1804c6866`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1804c6908`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1804c6990`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1804c69cd`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1804c6a05`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1804c6990`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1804c69cd`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1804c6a05`
- `api-ms-win-crt-string-l1-1-0!wcsncat_s` at `0x1804c6750`
- `api-ms-win-crt-string-l1-1-0!wcsncat_s` at `0x1804c6750`
- `ole32!CLSIDFromString` at `0x1804c693b`
- `ole32!CLSIDFromString` at `0x1804c693b`

## string_xrefs

- `0x1804c68ce`: `CLSID`
- `0x1804c67ad`: `Extension`

## pseudocode

```c
bool __fastcall MetroFGetClsidFromContentType(const wchar_t *a1, struct _GUID *a2, unsigned int *a3, wchar_t *a4)
{
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // r9
  __int64 v11; // rcx
  HRESULT v12; // ebx
  unsigned __int64 v13; // r9
  __int64 v14; // rax
  bool v15; // bl
  __int64 v17; // rax
  __int64 v18; // rax
  __int128 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h]
  _OWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v22; // [rsp+68h] [rbp-98h]
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  _OWORD v25[2]; // [rsp+88h] [rbp-78h] BYREF
  char v26; // [rsp+A8h] [rbp-58h]
  __int128 v27; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-40h]
  _OWORD v29[2]; // [rsp+C8h] [rbp-38h] BYREF
  char v30; // [rsp+E8h] [rbp-18h]
  OLECHAR sz; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v32[4174]; // [rsp+F2h] [rbp-Eh] BYREF
  wchar_t Destination[28]; // [rsp+1140h] [rbp+1040h] BYREF
  _BYTE v34[4120]; // [rsp+1178h] [rbp+1078h] BYREF

  v24 = 0;
  v23 = 0;
  v27 = 0;
  v19 = 0;
  v25[1] = (unsigned __int64)&v23;
  wcscpy(Destination, L"MIME\\Database\\Content Type\\");
  v28 = 0;
  v29[1] = (unsigned __int64)&v27;
  v20 = 0;
  v25[0] = 0;
  v21[1] = (unsigned __int64)&v19;
  v29[0] = 0;
  v26 = 0;
  v21[0] = 0;
  v30 = 0;
  v22 = 0;
  memset_0(v34, 0, 0x1010u);
  sz = 0;
  memset_0(v32, 0, 0x1046u);
  if ( !a4 )
  {
    v12 = -2147467259;
    goto LABEL_33;
  }
  *a4 = 0;
  if ( !a2 )
  {
    v12 = -2147467261;
    goto LABEL_34;
  }
  if ( a1 && a3 )
  {
    *a3 = 0;
    v8 = -1;
    if ( wcsncat_s(Destination, 0x824u, a1, 0xFFFFFFFFFFFFFFFFuLL) == 80 )
    {
LABEL_18:
      v12 = -2147467259;
      goto LABEL_19;
    }
    v9 = -1;
    do
      ++v9;
    while ( Destination[v9] );
    if ( !v9 )
      goto LABEL_51;
    DynamicMsorid::InitForKey(
      (DynamicMsorid *)&v23,
      (const struct _msoreg *)&OrapiData::Mso::c_msoridHKCR,
      Destination,
      v9);
    if ( !v26 )
    {
LABEL_16:
      v11 = 508048472;
LABEL_17:
      MsoShipAssertTagProc(v11);
      goto LABEL_18;
    }
    DynamicMsorid::InitForValue(&v19, v25, L"Extension", 9, 1);
    if ( !MsoFRegReadWz((const struct _msoreg *)((unsigned __int64)v21 & -(__int64)(v22 != 0)), &sz, 0x824u) || !sz )
      goto LABEL_18;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v32[2 * v10 - 2] );
    if ( !v10 )
      goto LABEL_51;
    DynamicMsorid::InitForKey((DynamicMsorid *)&v23, (const struct _msoreg *)&OrapiData::Mso::c_msoridHKCR, &sz, v10);
    if ( !v26 )
      goto LABEL_16;
    DynamicMsorid::InitForValue(&v19, v25, &WindowName, 0, 1);
    if ( !MsoFRegReadWz((const struct _msoreg *)((unsigned __int64)v21 & -(__int64)(v22 != 0)), &sz, 0x824u) )
      goto LABEL_18;
    do
      ++v8;
    while ( *(_WORD *)&v32[2 * v8 - 2] );
    if ( !v8 )
    {
LABEL_51:
      v11 = 508048473;
      goto LABEL_17;
    }
    DynamicMsorid::InitForKey((DynamicMsorid *)&v23, (const struct _msoreg *)&OrapiData::Mso::c_msoridHKCR, &sz, v8);
    if ( !v26 )
    {
      v11 = 508048475;
      goto LABEL_17;
    }
    DynamicMsorid::InitForKey((DynamicMsorid *)&v27, (const struct _msoreg *)v25, L"CLSID", 5u);
    if ( !v30 )
      goto LABEL_16;
    DynamicMsorid::InitForValue(&v19, v29, &WindowName, 0, 1);
    if ( !MsoFRegReadWz((const struct _msoreg *)((unsigned __int64)v21 & -(__int64)(v22 != 0)), &sz, 0x824u) )
      goto LABEL_18;
    v12 = CLSIDFromString(&sz, a2);
    if ( v12 >= 0 )
    {
      v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_000ceedb_0000_0000_c000_000000000046.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_000ceedb_0000_0000_c000_000000000046.Data1 )
        v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_000ceedb_0000_0000_c000_000000000046.Data4;
      if ( !v14 )
        goto LABEL_31;
      v17 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_000ceeda_0000_0000_c000_000000000046.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_000ceeda_0000_0000_c000_000000000046.Data1 )
        v17 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_000ceeda_0000_0000_c000_000000000046.Data4;
      if ( !v17 )
        goto LABEL_31;
      v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_637b1c13_8617_4985_8fe7_e66935ba677d.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_637b1c13_8617_4985_8fe7_e66935ba677d.Data1 )
        v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_637b1c13_8617_4985_8fe7_e66935ba677d.Data4;
      if ( !v18 )
      {
LABEL_31:
        v11 = 3473616;
        goto LABEL_17;
      }
      MsoGetFmtUserTypeStg(a2, a3, a4, v13);
    }
LABEL_33:
    if ( v12 >= 0 )
      goto LABEL_34;
    goto LABEL_19;
  }
  v12 = -2147467261;
LABEL_19:
  if ( a2 )
    *a2 = GUID_NULL;
LABEL_34:
  v15 = v12 >= 0;
  if ( v22 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)v21);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v19);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
    v22 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v19);
  if ( v30 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)v29);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v27);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v29);
    v30 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v29);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v27);
  if ( v26 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)v25);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
    v26 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
  return v15;
}

```

## disassembly

```asm
0x1804c6600  push    rbp
0x1804c6602  push    rbx
0x1804c6603  push    rsi
0x1804c6604  push    rdi
0x1804c6605  push    r12
0x1804c6607  push    r14
0x1804c6609  push    r15
0x1804c660b  lea     rbp, [rsp-20A0h]
0x1804c6613  mov     eax, 21A0h
0x1804c6618  call    _alloca_probe
0x1804c661d  sub     rsp, rax
0x1804c6620  mov     rax, cs:__security_cookie
0x1804c6627  xor     rax, rsp
0x1804c662a  mov     [rbp+20D0h+var_40], rax
0x1804c6631  xorps   xmm1, xmm1
0x1804c6634  xor     eax, eax
0x1804c6636  xorps   xmm0, xmm0
0x1804c6639  mov     [rbp+20D0h+var_2150], rax
0x1804c663d  movups  [rsp+21D0h+var_2160], xmm0
0x1804c6642  xor     r12d, r12d
0x1804c6645  lea     rax, [rsp+21D0h+var_2160]
0x1804c664a  movups  [rbp+20D0h+var_2120], xmm0
0x1804c664e  mov     r14, r8
0x1804c6651  mov     rdi, rdx
0x1804c6654  movups  [rsp+21D0h+var_21A0], xmm0
0x1804c6659  mov     rsi, rcx
0x1804c665c  xor     edx, edx; Val
0x1804c665e  movups  xmm0, xmmword ptr cs:aMimeDatabaseCo; "MIME\\Database\\Content Type\\"
0x1804c6665  mov     r8d, 1010h; Size
0x1804c666b  lea     rcx, [rbp+20D0h+var_1058]; void *
0x1804c6672  movups  [rbp+20D0h+var_2138], xmm1
0x1804c6676  mov     qword ptr [rbp+20D0h+var_2138], rax
0x1804c667a  mov     r15, r9
0x1804c667d  xor     eax, eax
0x1804c667f  movaps  xmmword ptr [rbp+20D0h+Destination], xmm0
0x1804c6686  movups  xmm0, xmmword ptr cs:aMimeDatabaseCo+20h; "ntent Type\\"
0x1804c668d  mov     [rbp+20D0h+var_2110], rax
0x1804c6691  lea     rax, [rbp+20D0h+var_2120]
0x1804c6695  movups  [rbp+20D0h+var_20F8], xmm1
0x1804c6699  mov     qword ptr [rbp+20D0h+var_20F8], rax
0x1804c669d  xor     eax, eax
0x1804c669f  movups  [rsp+21D0h+var_2178], xmm1
0x1804c66a4  mov     [rsp+21D0h+var_2190], rax
0x1804c66a9  lea     rax, [rsp+21D0h+var_21A0]
0x1804c66ae  movups  [rbp+20D0h+var_2148], xmm1
0x1804c66b2  mov     qword ptr [rsp+21D0h+var_2178], rax
0x1804c66b7  movups  [rbp+20D0h+var_2108], xmm1
0x1804c66bb  mov     [rbp+20D0h+var_2128], r12b
0x1804c66bf  movups  [rsp+21D0h+var_2188], xmm1
0x1804c66c4  mov     [rbp+20D0h+var_20E8], r12b
0x1804c66c8  movups  xmm1, xmmword ptr cs:aMimeDatabaseCo+10h; "abase\\Content Type\\"
0x1804c66cf  mov     [rsp+21D0h+var_2168], r12b
0x1804c66d4  movaps  [rbp+20D0h+var_1070], xmm0
0x1804c66db  movsd   xmm0, qword ptr cs:aMimeDatabaseCo+30h; "pe\\"
0x1804c66e3  movaps  [rbp+20D0h+var_1080], xmm1
0x1804c66ea  movsd   [rbp+20D0h+var_1060], xmm0
0x1804c66f2  call    memset_0
0x1804c66f7  xor     edx, edx; Val
0x1804c66f9  mov     [rbp+20D0h+sz], r12w
0x1804c66fe  mov     r8d, 1046h; Size
0x1804c6704  lea     rcx, [rbp+20D0h+var_20DE]; void *
0x1804c6708  call    memset_0
0x1804c670d  test    r15, r15
0x1804c6710  jz      loc_1804C6971
0x1804c6716  mov     [r15], r12w
0x1804c671a  test    rdi, rdi
0x1804c671d  jz      loc_1804C6AB5
0x1804c6723  test    rsi, rsi
0x1804c6726  jz      loc_1804C6ABF
0x1804c672c  test    r14, r14
0x1804c672f  jz      loc_1804C6ABF
0x1804c6735  mov     r8, rsi; Source
0x1804c6738  mov     [r14], r12d
0x1804c673b  mov     esi, 824h
0x1804c6740  lea     rcx, [rbp+20D0h+Destination]; Destination
0x1804c6747  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1804c674b  mov     edx, esi; SizeInWords
0x1804c674d  mov     r9, rbx; MaxCount
0x1804c6750  call    cs:__imp_wcsncat_s
0x1804c6756  cmp     eax, 50h ; 'P'
0x1804c6759  jz      loc_1804C682D
0x1804c675f  lea     rax, [rbp+20D0h+Destination]
0x1804c6766  mov     r9, rbx
0x1804c6769  inc     r9
0x1804c676c  cmp     [rax+r9*2], r12w
0x1804c6771  jnz     short loc_1804C6769
0x1804c6773  test    r9, r9
0x1804c6776  jz      loc_1804C6AC9
0x1804c677c  lea     r8, [rbp+20D0h+Destination]
0x1804c6783  lea     rdx, ?c_msoridHKCR@Mso@OrapiData@@3U_msoreg@@B; _msoreg const OrapiData::Mso::c_msoridHKCR
0x1804c678a  lea     rcx, [rsp+21D0h+var_2160]
0x1804c678f  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x1804c6795  cmp     [rbp+20D0h+var_2128], r12b
0x1804c6799  jz      loc_1804C6822
0x1804c679f  mov     r9d, 9
0x1804c67a5  mov     [rsp+21D0h+var_21B0], 1
0x1804c67ad  lea     r8, aExtension_1; "Extension"
0x1804c67b4  lea     rdx, [rbp+20D0h+var_2148]
0x1804c67b8  lea     rcx, [rsp+21D0h+var_21A0]
0x1804c67bd  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x1804c67c3  mov     al, [rsp+21D0h+var_2168]
0x1804c67c7  lea     rdx, [rbp+20D0h+sz]
0x1804c67cb  neg     al
0x1804c67cd  mov     r8d, esi
0x1804c67d0  lea     rax, [rsp+21D0h+var_2188]
0x1804c67d5  sbb     rcx, rcx
0x1804c67d8  and     rcx, rax
0x1804c67db  call    cs:__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x1804c67e1  test    eax, eax
0x1804c67e3  jz      short loc_1804C682D
0x1804c67e5  cmp     [rbp+20D0h+sz], r12w
0x1804c67ea  jz      short loc_1804C682D
0x1804c67ec  lea     rax, [rbp+20D0h+sz]
0x1804c67f0  mov     r9, rbx
0x1804c67f3  inc     r9
0x1804c67f6  cmp     [rax+r9*2], r12w
0x1804c67fb  jnz     short loc_1804C67F3
0x1804c67fd  test    r9, r9
0x1804c6800  jz      loc_1804C6AC9
0x1804c6806  lea     r8, [rbp+20D0h+sz]
0x1804c680a  lea     rdx, ?c_msoridHKCR@Mso@OrapiData@@3U_msoreg@@B; _msoreg const OrapiData::Mso::c_msoridHKCR
0x1804c6811  lea     rcx, [rsp+21D0h+var_2160]
0x1804c6816  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x1804c681c  cmp     [rbp+20D0h+var_2128], r12b
0x1804c6820  jnz     short loc_1804C684B
0x1804c6822  mov     ecx, 1E483458h
0x1804c6827  call    cs:__imp_MsoShipAssertTagProc
0x1804c682d  mov     ebx, 80004005h
0x1804c6832  test    rdi, rdi
0x1804c6835  jz      loc_1804C697E
0x1804c683b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1804c6842  movdqu  xmmword ptr [rdi], xmm0
0x1804c6846  jmp     loc_1804C697E
0x1804c684b  xor     r9d, r9d
0x1804c684e  mov     [rsp+21D0h+var_21B0], 1
0x1804c6856  lea     r8, WindowName
0x1804c685d  lea     rdx, [rbp+20D0h+var_2148]
0x1804c6861  lea     rcx, [rsp+21D0h+var_21A0]
0x1804c6866  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x1804c686c  mov     al, [rsp+21D0h+var_2168]
0x1804c6870  lea     rdx, [rbp+20D0h+sz]
0x1804c6874  neg     al
0x1804c6876  mov     r8d, esi
0x1804c6879  lea     rax, [rsp+21D0h+var_2188]
0x1804c687e  sbb     rcx, rcx
0x1804c6881  and     rcx, rax
0x1804c6884  call    cs:__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x1804c688a  test    eax, eax
0x1804c688c  jz      short loc_1804C682D
0x1804c688e  lea     rax, [rbp+20D0h+sz]
0x1804c6892  inc     rbx
0x1804c6895  cmp     [rax+rbx*2], r12w
0x1804c689a  jnz     short loc_1804C6892
0x1804c689c  test    rbx, rbx
0x1804c689f  jz      loc_1804C6AC9
0x1804c68a5  mov     r9, rbx
0x1804c68a8  lea     r8, [rbp+20D0h+sz]
0x1804c68ac  lea     rdx, ?c_msoridHKCR@Mso@OrapiData@@3U_msoreg@@B; _msoreg const OrapiData::Mso::c_msoridHKCR
0x1804c68b3  lea     rcx, [rsp+21D0h+var_2160]
0x1804c68b8  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x1804c68be  cmp     [rbp+20D0h+var_2128], r12b
0x1804c68c2  jz      loc_1804C6A58
0x1804c68c8  mov     r9d, 5
0x1804c68ce  lea     r8, aClsid_5; "CLSID"
0x1804c68d5  lea     rdx, [rbp+20D0h+var_2148]
0x1804c68d9  lea     rcx, [rbp+20D0h+var_2120]
0x1804c68dd  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x1804c68e3  cmp     [rbp+20D0h+var_20E8], r12b
0x1804c68e7  jz      loc_1804C6822
0x1804c68ed  xor     r9d, r9d
0x1804c68f0  mov     [rsp+21D0h+var_21B0], 1
0x1804c68f8  lea     r8, WindowName
0x1804c68ff  lea     rdx, [rbp+20D0h+var_2108]
0x1804c6903  lea     rcx, [rsp+21D0h+var_21A0]
0x1804c6908  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x1804c690e  mov     al, [rsp+21D0h+var_2168]
0x1804c6912  lea     rdx, [rbp+20D0h+sz]
0x1804c6916  neg     al
0x1804c6918  mov     r8d, esi
0x1804c691b  lea     rax, [rsp+21D0h+var_2188]
0x1804c6920  sbb     rcx, rcx
0x1804c6923  and     rcx, rax
0x1804c6926  call    cs:__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x1804c692c  test    eax, eax
0x1804c692e  jz      loc_1804C682D
0x1804c6934  mov     rdx, rdi; pclsid
0x1804c6937  lea     rcx, [rbp+20D0h+sz]; lpsz
0x1804c693b  call    cs:__imp_CLSIDFromString
0x1804c6941  mov     ebx, eax
0x1804c6943  test    eax, eax
0x1804c6945  js      short loc_1804C6976
0x1804c6947  mov     rax, [rdi]
0x1804c694a  sub     rax, qword ptr cs:_GUID_000ceedb_0000_0000_c000_000000000046.Data1
0x1804c6951  jnz     short loc_1804C695E
0x1804c6953  mov     rax, [rdi+8]
0x1804c6957  sub     rax, qword ptr cs:_GUID_000ceedb_0000_0000_c000_000000000046.Data4
0x1804c695e  test    rax, rax
0x1804c6961  jnz     loc_1804C6A62
0x1804c6967  mov     ecx, 3500D0h
0x1804c696c  jmp     loc_1804C6827
0x1804c6971  mov     ebx, 80004005h
0x1804c6976  test    ebx, ebx
0x1804c6978  js      loc_1804C6832
0x1804c697e  shr     ebx, 1Fh
0x1804c6981  xor     bl, 1
0x1804c6984  cmp     [rsp+21D0h+var_2168], r12b
0x1804c6989  jz      short loc_1804C69AF
0x1804c698b  lea     rcx, [rsp+21D0h+var_2188]
0x1804c6990  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1804c6996  lea     rcx, [rsp+21D0h+var_21A0]; this
0x1804c699b  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c69a0  lea     rcx, [rsp+21D0h+var_2188]; this
0x1804c69a5  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c69aa  mov     [rsp+21D0h+var_2168], r12b
0x1804c69af  lea     rcx, [rsp+21D0h+var_2188]; this
0x1804c69b4  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c69b9  lea     rcx, [rsp+21D0h+var_21A0]; this
0x1804c69be  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c69c3  cmp     [rbp+20D0h+var_20E8], r12b
0x1804c69c7  jz      short loc_1804C69E9
0x1804c69c9  lea     rcx, [rbp+20D0h+var_2108]
0x1804c69cd  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1804c69d3  lea     rcx, [rbp+20D0h+var_2120]; this
0x1804c69d7  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c69dc  lea     rcx, [rbp+20D0h+var_2108]; this
0x1804c69e0  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c69e5  mov     [rbp+20D0h+var_20E8], r12b
0x1804c69e9  lea     rcx, [rbp+20D0h+var_2108]; this
0x1804c69ed  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c69f2  lea     rcx, [rbp+20D0h+var_2120]; this
0x1804c69f6  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c69fb  cmp     [rbp+20D0h+var_2128], r12b
0x1804c69ff  jz      short loc_1804C6A22
0x1804c6a01  lea     rcx, [rbp+20D0h+var_2148]
0x1804c6a05  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1804c6a0b  lea     rcx, [rsp+21D0h+var_2160]; this
0x1804c6a10  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c6a15  lea     rcx, [rbp+20D0h+var_2148]; this
0x1804c6a19  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c6a1e  mov     [rbp+20D0h+var_2128], r12b
0x1804c6a22  lea     rcx, [rbp+20D0h+var_2148]; this
0x1804c6a26  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c6a2b  lea     rcx, [rsp+21D0h+var_2160]; this
0x1804c6a30  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1804c6a35  mov     al, bl
0x1804c6a37  mov     rcx, [rbp+20D0h+var_40]
0x1804c6a3e  xor     rcx, rsp; StackCookie
0x1804c6a41  call    __security_check_cookie
0x1804c6a46  add     rsp, 21A0h
0x1804c6a4d  pop     r15
0x1804c6a4f  pop     r14
0x1804c6a51  pop     r12
0x1804c6a53  pop     rdi
0x1804c6a54  pop     rsi
0x1804c6a55  pop     rbx
0x1804c6a56  pop     rbp
0x1804c6a57  retn
0x1804c6a58  mov     ecx, 1E48345Bh
0x1804c6a5d  jmp     loc_1804C6827
0x1804c6a62  mov     rax, [rdi]
0x1804c6a65  sub     rax, qword ptr cs:_GUID_000ceeda_0000_0000_c000_000000000046.Data1
0x1804c6a6c  jnz     short loc_1804C6A79
0x1804c6a6e  mov     rax, [rdi+8]
0x1804c6a72  sub     rax, qword ptr cs:_GUID_000ceeda_0000_0000_c000_000000000046.Data4
0x1804c6a79  test    rax, rax
0x1804c6a7c  jz      loc_1804C6967
0x1804c6a82  mov     rax, [rdi]
0x1804c6a85  sub     rax, qword ptr cs:_GUID_637b1c13_8617_4985_8fe7_e66935ba677d.Data1
0x1804c6a8c  jnz     short loc_1804C6A99
0x1804c6a8e  mov     rax, [rdi+8]
0x1804c6a92  sub     rax, qword ptr cs:_GUID_637b1c13_8617_4985_8fe7_e66935ba677d.Data4
0x1804c6a99  test    rax, rax
0x1804c6a9c  jz      loc_1804C6967
0x1804c6aa2  mov     r8, r15; wchar_t *
0x1804c6aa5  mov     rdx, r14; unsigned int *
0x1804c6aa8  mov     rcx, rdi; struct _GUID *
0x1804c6aab  call    ?MsoGetFmtUserTypeStg@@YAXAEBU_GUID@@PEAIPEA_W_K@Z; MsoGetFmtUserTypeStg(_GUID const &,uint *,wchar_t *,unsigned __int64)
0x1804c6ab0  jmp     loc_1804C6976
0x1804c6ab5  mov     ebx, 80004003h
0x1804c6aba  jmp     loc_1804C697E
0x1804c6abf  mov     ebx, 80004003h
0x1804c6ac4  jmp     loc_1804C6832
0x1804c6ac9  mov     ecx, 1E483459h
0x1804c6ace  jmp     loc_1804C6827
```
