# CUpdateDeploymentJob::PrepareDeployData(FullDeployableUpdate const *,IUpdateDeploymentDataProvider *,tagDSUpdateMetadata &,tagDSDeployment const &,int,tagSusDeployData * *)

- ea: `0x18002b4c0`
- end: `0x18002bd3b`
- name: `?PrepareDeployData@CUpdateDeploymentJob@@AEAAJPEBVFullDeployableUpdate@@PEAUIUpdateDeploymentDataProvider@@AEAUtagDSUpdateMetadata@@AEBUtagDSDeployment@@HPEAPEAUtagSusDeployData@@@Z`
- size: `2171`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *this, const struct FullDeployableUpdate *, struct IUpdateDeploymentDataProvider *, struct tagDSUpdateMetadata *, const struct tagDSDeployment *, int, struct tagSusDeployData **)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18002d3d0`
- `0x18002fcbc`

## callees

- `0x180003180`
- `0x180008b30`
- `0x180008f5c`
- `0x18000cd48`
- `0x18000db84`
- `0x18000dd60`
- `0x1800110fc`
- `0x180011b44`
- `0x1800217c8`
- `0x1800222dc`
- `0x180022790`
- `0x18002b304`
- `0x18002b4c0`
- `0x18003652c`
- `0x18003723c`
- `0x180047508`
- `0x180061960`
- `0x180061d54`
- `0x180062558`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18002b722`
- `RPCRT4!UuidFromStringW` at `0x18002b722`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bb8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bbc8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bb8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bbc8`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b8e4`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b91c`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b8e4`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b91c`

## string_xrefs

- `0x18002b51d`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002b5a8`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002bcc6`: `Deployment job Id %ws : Update %ws.%d, Top-level update %ws.%d deployment data prepared successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CUpdateDeploymentJob::PrepareDeployData(
        CUpdateDeploymentJob *this,
        const struct FullDeployableUpdate *a2,
        struct IUpdateDeploymentDataProvider *a3,
        struct tagDSUpdateMetadata *a4,
        const struct tagDSDeployment *a5,
        int a6,
        struct tagSusDeployData **a7)
{
  __int64 v9; // rdx
  struct tagSusDeployData *v11; // rax
  struct tagSusDeployData *v12; // rsi
  unsigned int v13; // edi
  signed int Index1ById; // ebx
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  RPC_STATUS v18; // eax
  unsigned int v19; // ebx
  int v20; // r9d
  wchar_t *v21; // r8
  char IsEnabled; // al
  OLECHAR *v23; // rcx
  _WORD *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdx
  wchar_t **v27; // rcx
  unsigned int v28; // ebx
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  unsigned __int64 v35; // r9
  const struct FullDeployableUpdate *v36; // r13
  int v37; // ecx
  unsigned int v38; // ebx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // eax
  int v43; // eax
  __int64 v44; // rdx
  const OLECHAR **v45; // rcx
  _WORD *v46; // rax
  const OLECHAR *v47; // rax
  int ServerProperties; // eax
  struct tagSusDeployData *v49; // rax
  struct tagSusDeployData *v50; // rdx
  int v51; // [rsp+20h] [rbp-E0h]
  _BYTE v54[80]; // [rsp+B0h] [rbp-50h] BYREF
  struct tagSusDeployData *v55; // [rsp+100h] [rbp+0h]
  void *v56; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v57; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  if ( !a2 )
  {
    v9 = 1744;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80004003LL,
      v51);
    return 2147500035LL;
  }
  if ( !a7 )
  {
    v9 = 1745;
    goto LABEL_3;
  }
  v56 = (void *)1;
  v55 = 0;
  v57 = 1;
  v11 = (struct tagSusDeployData *)operator new(0x128u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( v11 )
    memset(v11, 0, 0x128u);
  else
    v12 = 0;
  v55 = v12;
  v13 = -2147024882;
  Index1ById = v12 == 0 ? 0x8007000E : 0;
  if ( !v12 )
  {
    v15 = 1754;
LABEL_101:
    v13 = Index1ById;
    goto LABEL_102;
  }
  *((_QWORD *)v55 + 9) = SafeSusAllocArray(2u, 8u);
  if ( !*((_QWORD *)v55 + 9) )
  {
    v15 = 1757;
LABEL_56:
    Index1ById = -2147024882;
    goto LABEL_101;
  }
  *((_QWORD *)v55 + 1) = *((_QWORD *)this + 101);
  Index1ById = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 6), v55);
  if ( Index1ById < 0 )
  {
    v15 = 1762;
    goto LABEL_101;
  }
  if ( (*((_BYTE *)this + 792) & 0x40) == 0 || *((_DWORD *)a4 + 10) == -2145124307 )
    *((_DWORD *)v55 + 20) |= 1u;
  v16 = *((_DWORD *)this + 198);
  if ( (v16 & 1) != 0 && (v16 & 2) != 0 && (*((_BYTE *)a4 + 132) & 4) != 0 && *((_DWORD *)a4 + 20) != 4 )
  {
    *((_DWORD *)v55 + 20) |= 2u;
    *((_QWORD *)v55 + 1) = 0;
  }
  if ( (*((_BYTE *)this + 792) & 8) != 0 )
    *((_DWORD *)v55 + 20) |= 8u;
  if ( (*((_BYTE *)this + 792) & 0x20) != 0 )
    *((_DWORD *)v55 + 20) |= 0x40u;
  if ( (*((_BYTE *)this + 792) & 0x10) != 0 )
    *((_DWORD *)v55 + 20) |= 0x80u;
  if ( *((char *)this + 792) < 0 )
    *((_DWORD *)v55 + 20) |= 0x400u;
  if ( (*((_DWORD *)this + 198) & 0x200) != 0 )
    *((_DWORD *)v55 + 20) |= 0x100u;
  if ( (*((_DWORD *)this + 198) & 0x400) != 0 )
    *((_DWORD *)v55 + 20) |= 0x200u;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
  {
    v17 = *((_DWORD *)this + 198);
    if ( (v17 & 0x1000) != 0 )
    {
      *((_DWORD *)v55 + 20) |= 0x800u;
    }
    else if ( (v17 & 0x2000) != 0 )
    {
      *((_DWORD *)v55 + 20) |= 0x1000u;
    }
  }
  v18 = UuidFromStringW(*((RPC_WSTR *)a2 + 4), (UUID *)v55 + 2);
  Index1ById = v18;
  if ( v18 >= 1 )
    Index1ById = (unsigned __int16)v18 | 0x80010000;
  if ( Index1ById < 0 )
  {
    v15 = 1823;
    goto LABEL_101;
  }
  *((_DWORD *)v55 + 12) = *((_DWORD *)a2 + 10);
  *((_QWORD *)v55 + 7) = a4;
  Index1ById = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a5 + 13), (char *)v55 + 104);
  if ( Index1ById < 0 )
  {
    v15 = 1830;
    goto LABEL_101;
  }
  Index1ById = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a5 + 15), (char *)v55 + 248);
  if ( Index1ById < 0 )
  {
    v15 = 1831;
    goto LABEL_101;
  }
  *((_DWORD *)v55 + 16) = 2;
  v19 = 0;
  if ( *((_DWORD *)v55 + 16) )
  {
    while ( 1 )
    {
      *(_QWORD *)(*((_QWORD *)v55 + 9) + 8LL * v19) = SafeSusAllocArray(0x10u, 2u);
      v21 = *(wchar_t **)(*((_QWORD *)v55 + 9) + 8LL * v19);
      if ( !v21 )
        break;
      if ( LcidToLangString(*((_DWORD *)this + 200), *((_DWORD *)&v56 + v19), v21, v20) >= 0
        && ++v19 < *((_DWORD *)v55 + 16) )
      {
        continue;
      }
      goto LABEL_52;
    }
    v15 = 1838;
    goto LABEL_56;
  }
LABEL_52:
  if ( (*((_DWORD *)a4 + 46) & 0x100) == 0 )
  {
    Index1ById = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 8), (char *)v55 + 256);
    if ( Index1ById < 0 )
    {
      v15 = 1851;
      goto LABEL_101;
    }
  }
  if ( *((_DWORD *)a4 + 20) == 4 )
  {
    if ( *((_DWORD *)a5 + 22) == 1 || (*((_BYTE *)a4 + 184) & 0xC0) != 0 )
      *((_DWORD *)v55 + 20) |= 0x10u;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSysStringLenOnLPWSTR>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSysStringLenOnLPWSTR>::GetImpl'::`2'::impl);
    v23 = (OLECHAR *)*((_QWORD *)a5 + 16);
    if ( IsEnabled )
    {
      if ( v23 )
      {
        if ( *v23 )
        {
          Index1ById = DuplicateString<wchar_t *,wchar_t *>(v23, (char *)v55 + 264);
          if ( Index1ById < 0 )
          {
            v15 = 1874;
            goto LABEL_101;
          }
        }
      }
      v24 = (_WORD *)*((_QWORD *)a5 + 17);
      if ( v24 )
      {
        if ( *v24 )
        {
          Index1ById = DuplicateString<wchar_t *,wchar_t *>(v24, (char *)v55 + 272);
          if ( Index1ById < 0 )
          {
            v15 = 1880;
            goto LABEL_101;
          }
        }
      }
    }
    else
    {
      if ( SysStringLen(v23) )
      {
        Index1ById = DuplicateString<wchar_t *,wchar_t *>(*((_QWORD *)a5 + 16), (char *)v55 + 264);
        if ( Index1ById < 0 )
        {
          v15 = 1887;
          goto LABEL_101;
        }
      }
      if ( SysStringLen(*((BSTR *)a5 + 17)) )
      {
        Index1ById = DuplicateString<wchar_t *,wchar_t *>(*((_QWORD *)a5 + 17), (char *)v55 + 272);
        if ( Index1ById < 0 )
        {
          v15 = 1893;
          goto LABEL_101;
        }
      }
    }
    LODWORD(v56) = -1;
    Index1ById = CUpdateDeploymentJob::FindIndex1ById(
                   this,
                   (struct tagSusDeployData *)((char *)v55 + 32),
                   (unsigned int *)&v56);
    if ( Index1ById < 0 )
    {
      v15 = 1900;
      goto LABEL_101;
    }
    if ( (_DWORD)v56 == -1 )
    {
      v15 = 1901;
LABEL_93:
      Index1ById = -2145120257;
      goto LABEL_101;
    }
    v25 = *((_QWORD *)this + 87);
    v26 = *(_QWORD *)(v25 + 8LL * (unsigned int)v56);
    if ( *(_DWORD *)(v26 + 240) )
    {
      v31 = *((unsigned int *)this + 168);
      if ( (_DWORD)v31 == -1 )
      {
        v32 = 1674;
      }
      else
      {
        v33 = *(_QWORD *)(v25 + 8 * v31);
        v34 = *(_DWORD *)(v33 + 240);
        if ( v34 )
        {
          if ( v34 == *(_DWORD *)(v33 + 288) )
            goto LABEL_89;
          v32 = 1680;
        }
        else
        {
          v32 = 1678;
        }
      }
      Index1ById = -2145120257;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
        (const char *)0x80240FFFLL,
        v51);
      v15 = 1930;
      goto LABEL_101;
    }
    if ( *(_QWORD *)(v26 + 200) != *(_QWORD *)((char *)a4 + 4)
      || *(_QWORD *)(v26 + 208) != *(_QWORD *)((char *)a4 + 12)
      || *(_DWORD *)(v26 + 216) != *((_DWORD *)a4 + 5) )
    {
      v15 = 1919;
      goto LABEL_93;
    }
    v27 = *(wchar_t ***)(v26 + 280);
    v28 = *(_DWORD *)(v26 + 276);
    if ( v27 && v28 )
    {
      *((_QWORD *)v55 + 11) = SusDuplicateStringArray(v27, v28);
      if ( !*((_QWORD *)v55 + 11) )
      {
        v15 = 1946;
LABEL_102:
        v35 = v13;
        goto LABEL_135;
      }
      *((_DWORD *)v55 + 24) = v28;
    }
  }
LABEL_89:
  if ( a6 )
  {
    v56 = 0;
    v29 = WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v56);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A4,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
        (const char *)(unsigned int)v29,
        v51);
      v13 = v30;
      goto LABEL_127;
    }
    v36 = a2;
    v37 = *((_DWORD *)a2 + 14);
    v38 = 2;
    if ( v37 == 8 )
      v38 = 6;
    v39 = v37 - 1;
    if ( v39 )
    {
      v40 = v39 - 1;
      if ( v40 )
      {
        v41 = v40 - 2;
        if ( v41 )
        {
          if ( v41 == 4 )
            v42 = 8;
          else
            v42 = 0;
        }
        else
        {
          v42 = 4;
        }
      }
      else
      {
        v42 = 2;
      }
    }
    else
    {
      v42 = 1;
    }
    v51 = v42;
    v43 = (*(__int64 (__fastcall **)(struct IUpdateDeploymentDataProvider *, __int64, _QWORD, _QWORD))(*(_QWORD *)a3 + 24LL))(
            a3,
            4,
            *((unsigned int *)this + 200),
            v38);
    if ( v43 < 0 )
    {
      v13 = v43;
      v44 = 1976;
LABEL_126:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v44,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
        (const char *)v13,
        v51);
      DPFreeDeployableUpdateData(v56);
LABEL_127:
      if ( v56 )
        operator delete(v56, (const struct std::nothrow_t *)0x288);
      goto LABEL_137;
    }
    v45 = (const OLECHAR **)v56;
    v46 = (_WORD *)*((_QWORD *)v56 + 1);
    if ( v46 && *v46 )
    {
      *((_QWORD *)v55 + 2) = SysAllocString(*((const OLECHAR **)v56 + 1));
      if ( !*((_QWORD *)v55 + 2) )
      {
        v44 = 1983;
        goto LABEL_126;
      }
      v45 = (const OLECHAR **)v56;
    }
    if ( (v38 & 4) != 0 )
    {
      v47 = v45[2];
      if ( v47 )
      {
        if ( *v47 )
        {
          *((_QWORD *)v55 + 3) = SysAllocString(v45[2]);
          if ( !*((_QWORD *)v55 + 3) )
          {
            v44 = 1991;
            goto LABEL_126;
          }
          v45 = (const OLECHAR **)v56;
        }
      }
    }
    DPFreeDeployableUpdateData(v45);
    if ( v56 )
      operator delete(v56, (const struct std::nothrow_t *)0x288);
  }
  else
  {
    v36 = a2;
  }
  ServerProperties = CUpdateDeploymentJob::GetServerProperties(
                       this,
                       *((const wchar_t **)v36 + 6),
                       (struct tagSusDeployData *)((char *)v55 + 280));
  v13 = ServerProperties;
  if ( ServerProperties >= 0 )
  {
    *((_DWORD *)v55 + 72) = *((_DWORD *)v36 + 14);
    v49 = v55;
    v55 = 0;
    *a7 = v49;
    v57 = 0;
    Trace::GuidToString::GuidToString((Trace::GuidToString *)v54, (const struct _GUID *)this + 1);
    WUTrace(0, 0, 0x1000000, 4);
    v13 = 0;
    goto LABEL_137;
  }
  v35 = (unsigned int)ServerProperties;
  v15 = 1995;
LABEL_135:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
    (const char *)v35,
    v51);
LABEL_137:
  v50 = v55;
  v55 = 0;
  FreeObject(v57, v50);
  if ( v55 )
    operator delete(v55, (const struct std::nothrow_t *)0x128);
  return v13;
}

```

## disassembly

```asm
0x18002b4c0  mov     [rsp-8+arg_18], rbx
0x18002b4c5  push    rbp
0x18002b4c6  push    rsi
0x18002b4c7  push    rdi
0x18002b4c8  push    r12
0x18002b4ca  push    r13
0x18002b4cc  push    r14
0x18002b4ce  push    r15
0x18002b4d0  lea     rbp, [rsp-20h]
0x18002b4d5  sub     rsp, 120h
0x18002b4dc  mov     rax, cs:__security_cookie
0x18002b4e3  xor     rax, rsp
0x18002b4e6  mov     [rbp+50h+var_38], rax
0x18002b4ea  mov     r12, r9
0x18002b4ed  mov     [rsp+150h+var_D8], r8
0x18002b4f2  mov     [rsp+150h+var_E0], rdx
0x18002b4f7  mov     r15, rcx
0x18002b4fa  mov     r13, [rbp+50h+arg_20]
0x18002b501  mov     rax, [rbp+50h+arg_30]
0x18002b508  mov     [rbp+50h+var_D0], rax
0x18002b50c  xor     ebx, ebx
0x18002b50e  test    rdx, rdx
0x18002b511  jnz     short loc_18002B537
0x18002b513  mov     edx, 6D0h; void *
0x18002b518  mov     ebx, 80004003h
0x18002b51d  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002b524  mov     r9d, ebx; char *
0x18002b527  mov     rcx, [rbp+58h]; this
0x18002b52b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b530  mov     eax, ebx
0x18002b532  jmp     loc_18002BD14
0x18002b537  test    rax, rax
0x18002b53a  jnz     short loc_18002B543
0x18002b53c  mov     edx, 6D1h
0x18002b541  jmp     short loc_18002B518
0x18002b543  mov     ecx, 1
0x18002b548  mov     [rbp+50h+var_48], rcx
0x18002b54c  mov     [rbp+50h+var_50], rbx
0x18002b550  mov     [rbp+50h+var_40], ecx
0x18002b553  lea     rax, [rbp+50h+var_40]
0x18002b557  mov     [rbp+50h+var_B8], rax
0x18002b55b  lea     rax, [rbp+50h+var_50]
0x18002b55f  mov     [rbp+50h+var_B0], rax
0x18002b563  mov     [rbp+50h+var_A8], cl
0x18002b566  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b56d  mov     edi, 128h
0x18002b572  mov     ecx, edi; unsigned __int64
0x18002b574  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002b579  mov     rsi, rax
0x18002b57c  test    rax, rax
0x18002b57f  jz      short loc_18002B590
0x18002b581  mov     r8d, edi; Size
0x18002b584  xor     edx, edx; Val
0x18002b586  mov     rcx, rax; void *
0x18002b589  call    memset
0x18002b58e  jmp     short loc_18002B593
0x18002b590  mov     rsi, rbx
0x18002b593  mov     [rbp+50h+var_50], rsi
0x18002b597  mov     rax, rsi
0x18002b59a  neg     rax
0x18002b59d  sbb     ebx, ebx
0x18002b59f  not     ebx
0x18002b5a1  mov     edi, 8007000Eh
0x18002b5a6  and     ebx, edi
0x18002b5a8  lea     r14, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002b5af  test    rsi, rsi
0x18002b5b2  jnz     short loc_18002B5BE
0x18002b5b4  mov     edx, 6DAh
0x18002b5b9  jmp     loc_18002B83B
0x18002b5be  mov     edx, 8; unsigned __int64
0x18002b5c3  lea     ecx, [rdx-6]; unsigned __int64
0x18002b5c6  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18002b5cb  mov     rcx, [rbp+50h+var_50]
0x18002b5cf  mov     [rcx+48h], rax
0x18002b5d3  mov     rax, [rbp+50h+var_50]
0x18002b5d7  xor     ecx, ecx
0x18002b5d9  cmp     [rax+48h], rcx
0x18002b5dd  jnz     short loc_18002B5E9
0x18002b5df  mov     edx, 6DDh
0x18002b5e4  jmp     loc_18002B839
0x18002b5e9  mov     rcx, [r15+328h]
0x18002b5f0  mov     [rax+8], rcx
0x18002b5f4  mov     rdx, [rbp+50h+var_50]
0x18002b5f8  mov     rsi, [rsp+150h+var_E0]
0x18002b5fd  mov     rcx, [rsi+30h]
0x18002b601  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002b606  mov     ebx, eax
0x18002b608  xor     ecx, ecx
0x18002b60a  test    eax, eax
0x18002b60c  jns     short loc_18002B618
0x18002b60e  mov     edx, 6E2h
0x18002b613  jmp     loc_18002B83B
0x18002b618  test    byte ptr [r15+318h], 40h
0x18002b620  jz      short loc_18002B62D
0x18002b622  cmp     dword ptr [r12+28h], 8024002Dh
0x18002b62b  jnz     short loc_18002B635
0x18002b62d  mov     rax, [rbp+50h+var_50]
0x18002b631  or      dword ptr [rax+50h], 1
0x18002b635  mov     eax, [r15+318h]
0x18002b63c  test    al, 1
0x18002b63e  jz      short loc_18002B667
0x18002b640  test    al, 2
0x18002b642  jz      short loc_18002B667
0x18002b644  test    byte ptr [r12+84h], 4
0x18002b64d  jz      short loc_18002B667
0x18002b64f  cmp     dword ptr [r12+50h], 4
0x18002b655  jz      short loc_18002B667
0x18002b657  mov     rax, [rbp+50h+var_50]
0x18002b65b  or      dword ptr [rax+50h], 2
0x18002b65f  mov     rax, [rbp+50h+var_50]
0x18002b663  mov     [rax+8], rcx
0x18002b667  mov     ecx, 8
0x18002b66c  test    [r15+318h], cl
0x18002b673  jz      short loc_18002B67C
0x18002b675  mov     rax, [rbp+50h+var_50]
0x18002b679  or      [rax+50h], ecx
0x18002b67c  test    byte ptr [r15+318h], 20h
0x18002b684  jz      short loc_18002B68E
0x18002b686  mov     rax, [rbp+50h+var_50]
0x18002b68a  or      dword ptr [rax+50h], 40h
0x18002b68e  test    byte ptr [r15+318h], 10h
0x18002b696  jz      short loc_18002B6A1
0x18002b698  mov     rax, [rbp+50h+var_50]
0x18002b69c  bts     dword ptr [rax+50h], 7
0x18002b6a1  mov     ecx, 400h
0x18002b6a6  test    byte ptr [r15+318h], 80h
0x18002b6ae  jz      short loc_18002B6B7
0x18002b6b0  mov     rax, [rbp+50h+var_50]
0x18002b6b4  or      [rax+50h], ecx
0x18002b6b7  mov     edx, 200h
0x18002b6bc  test    [r15+318h], edx
0x18002b6c3  jz      short loc_18002B6CE
0x18002b6c5  mov     rax, [rbp+50h+var_50]
0x18002b6c9  bts     dword ptr [rax+50h], 8
0x18002b6ce  test    [r15+318h], ecx
0x18002b6d5  jz      short loc_18002B6DE
0x18002b6d7  mov     rax, [rbp+50h+var_50]
0x18002b6db  or      [rax+50h], edx
0x18002b6de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration> `wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl(void)'::`2'::impl
0x18002b6e5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(void)
0x18002b6ea  test    al, al
0x18002b6ec  jz      short loc_18002B716
0x18002b6ee  mov     eax, [r15+318h]
0x18002b6f5  mov     ecx, 1000h
0x18002b6fa  test    ecx, eax
0x18002b6fc  jz      short loc_18002B709
0x18002b6fe  mov     rax, [rbp+50h+var_50]
0x18002b702  bts     dword ptr [rax+50h], 0Bh
0x18002b707  jmp     short loc_18002B716
0x18002b709  bt      eax, 0Dh
0x18002b70d  jnb     short loc_18002B716
0x18002b70f  mov     rax, [rbp+50h+var_50]
0x18002b713  or      [rax+50h], ecx
0x18002b716  mov     rdx, [rbp+50h+var_50]
0x18002b71a  add     rdx, 20h ; ' '; Uuid
0x18002b71e  mov     rcx, [rsi+20h]; StringUuid
0x18002b722  call    cs:__imp_UuidFromStringW
0x18002b728  mov     ebx, eax
0x18002b72a  cmp     eax, 1
0x18002b72d  jl      short loc_18002B738
0x18002b72f  movzx   ebx, ax
0x18002b732  or      ebx, 80010000h
0x18002b738  test    ebx, ebx
0x18002b73a  jns     short loc_18002B746
0x18002b73c  mov     edx, 71Fh
0x18002b741  jmp     loc_18002B83B
0x18002b746  mov     ecx, [rsi+28h]
0x18002b749  mov     rax, [rbp+50h+var_50]
0x18002b74d  mov     [rax+30h], ecx
0x18002b750  mov     rax, [rbp+50h+var_50]
0x18002b754  mov     [rax+38h], r12
0x18002b758  mov     rdx, [rbp+50h+var_50]
0x18002b75c  add     rdx, 68h ; 'h'
0x18002b760  mov     rcx, [r13+68h]
0x18002b764  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002b769  mov     ebx, eax
0x18002b76b  test    eax, eax
0x18002b76d  jns     short loc_18002B779
0x18002b76f  mov     edx, 726h
0x18002b774  jmp     loc_18002B83B
0x18002b779  mov     rdx, [rbp+50h+var_50]
0x18002b77d  add     rdx, 0F8h
0x18002b784  mov     rcx, [r13+78h]
0x18002b788  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002b78d  mov     ebx, eax
0x18002b78f  xor     ecx, ecx
0x18002b791  test    eax, eax
0x18002b793  jns     short loc_18002B79F
0x18002b795  mov     edx, 727h
0x18002b79a  jmp     loc_18002B83B
0x18002b79f  mov     rax, [rbp+50h+var_50]
0x18002b7a3  mov     dword ptr [rax+40h], 2
0x18002b7aa  mov     ebx, ecx
0x18002b7ac  mov     rax, [rbp+50h+var_50]
0x18002b7b0  cmp     [rax+40h], ecx
0x18002b7b3  jbe     short loc_18002B800
0x18002b7b5  mov     edx, 2; unsigned __int64
0x18002b7ba  lea     ecx, [rdx+0Eh]; unsigned __int64
0x18002b7bd  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18002b7c2  mov     edx, ebx
0x18002b7c4  mov     rcx, [rbp+50h+var_50]
0x18002b7c8  mov     r8, [rcx+48h]
0x18002b7cc  mov     [r8+rdx*8], rax
0x18002b7d0  mov     rax, [rbp+50h+var_50]
0x18002b7d4  mov     rcx, [rax+48h]
0x18002b7d8  mov     r8, [rcx+rdx*8]; wchar_t *
0x18002b7dc  test    r8, r8
0x18002b7df  jz      short loc_18002B834
0x18002b7e1  mov     edx, dword ptr [rbp+rdx*4+50h+var_48]; int
0x18002b7e5  mov     ecx, [r15+320h]; unsigned int
0x18002b7ec  call    ?LcidToLangString@@YAJKHPEA_WH@Z; LcidToLangString(ulong,int,wchar_t *,int)
0x18002b7f1  test    eax, eax
0x18002b7f3  js      short loc_18002B800
0x18002b7f5  inc     ebx
0x18002b7f7  mov     rax, [rbp+50h+var_50]
0x18002b7fb  cmp     ebx, [rax+40h]
0x18002b7fe  jb      short loc_18002B7B5
0x18002b800  test    dword ptr [r12+0B8h], 100h
0x18002b80c  jnz     short loc_18002B842
0x18002b80e  mov     rdx, [rbp+50h+var_50]
0x18002b812  add     rdx, 100h
0x18002b819  mov     rcx, [rsi+40h]
0x18002b81d  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002b822  mov     ebx, eax
0x18002b824  xor     esi, esi
0x18002b826  test    eax, eax
0x18002b828  jns     short loc_18002B844
0x18002b82a  mov     edx, 73Bh
0x18002b82f  jmp     loc_18002BAA4
0x18002b834  mov     edx, 72Eh
0x18002b839  mov     ebx, edi
0x18002b83b  xor     esi, esi
0x18002b83d  jmp     loc_18002BAA4
0x18002b842  xor     esi, esi
0x18002b844  cmp     dword ptr [r12+50h], 4
0x18002b84a  jnz     loc_18002BA10
0x18002b850  cmp     dword ptr [r13+58h], 1
0x18002b855  jz      short loc_18002B862
0x18002b857  test    byte ptr [r12+0B8h], 0C0h
0x18002b860  jz      short loc_18002B86A
0x18002b862  mov     rax, [rbp+50h+var_50]
0x18002b866  or      dword ptr [rax+50h], 10h
0x18002b86a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSysStringLenOnLPWSTR@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSysStringLenOnLPWSTR@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSysStringLenOnLPWSTR> `wil::Feature<__WilFeatureTraits_Feature_FixSysStringLenOnLPWSTR>::GetImpl(void)'::`2'::impl
0x18002b871  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSysStringLenOnLPWSTR@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSysStringLenOnLPWSTR>::__private_IsEnabled(void)
0x18002b876  mov     rcx, [r13+80h]; pbstr
0x18002b87d  test    al, al
0x18002b87f  jz      short loc_18002B8E4
0x18002b881  test    rcx, rcx
0x18002b884  jz      short loc_18002B8AB
0x18002b886  cmp     [rcx], si
0x18002b889  jz      short loc_18002B8AB
0x18002b88b  mov     rdx, [rbp+50h+var_50]
0x18002b88f  add     rdx, 108h
0x18002b896  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002b89b  mov     ebx, eax
0x18002b89d  test    eax, eax
0x18002b89f  jns     short loc_18002B8AB
0x18002b8a1  mov     edx, 752h
0x18002b8a6  jmp     loc_18002BAA4
0x18002b8ab  mov     rcx, [r13+88h]
0x18002b8b2  test    rcx, rcx
0x18002b8b5  jz      loc_18002B94D
0x18002b8bb  cmp     [rcx], si
0x18002b8be  jz      loc_18002B94D
0x18002b8c4  mov     rdx, [rbp+50h+var_50]
0x18002b8c8  add     rdx, 110h
0x18002b8cf  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002b8d4  mov     ebx, eax
0x18002b8d6  test    eax, eax
0x18002b8d8  jns     short loc_18002B94D
0x18002b8da  mov     edx, 758h
0x18002b8df  jmp     loc_18002BAA4
0x18002b8e4  call    cs:__imp_SysStringLen
0x18002b8ea  test    eax, eax
0x18002b8ec  jz      short loc_18002B915
0x18002b8ee  mov     rdx, [rbp+50h+var_50]
0x18002b8f2  add     rdx, 108h
0x18002b8f9  mov     rcx, [r13+80h]
0x18002b900  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002b905  mov     ebx, eax
0x18002b907  test    eax, eax
0x18002b909  jns     short loc_18002B915
0x18002b90b  mov     edx, 75Fh
0x18002b910  jmp     loc_18002BAA4
0x18002b915  mov     rcx, [r13+88h]; pbstr
0x18002b91c  call    cs:__imp_SysStringLen
0x18002b922  test    eax, eax
0x18002b924  jz      short loc_18002B94D
0x18002b926  mov     rdx, [rbp+50h+var_50]
0x18002b92a  add     rdx, 110h
0x18002b931  mov     rcx, [r13+88h]
0x18002b938  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002b93d  mov     ebx, eax
0x18002b93f  test    eax, eax
0x18002b941  jns     short loc_18002B94D
0x18002b943  mov     edx, 765h
0x18002b948  jmp     loc_18002BAA4
0x18002b94d  or      r13d, 0FFFFFFFFh
0x18002b951  mov     dword ptr [rbp+50h+var_48], r13d
0x18002b955  mov     rdx, [rbp+50h+var_50]
  ... truncated ...
```
