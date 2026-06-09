# inverted::CIndexScanner::NextKey(inverted::CIndexKey const * *)

- ea: `0x1800384b0`
- end: `0x180038f02`
- name: `?NextKey@CIndexScanner@inverted@@UEAA_NPEAPEBVCIndexKey@2@@Z`
- size: `2642`
- prototype: `bool __fastcall(inverted::CIndexScanner *__hidden this, const struct CIndexKey **)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180028470`
- `0x180034878`
- `0x180036d60`
- `0x1800384b0`
- `0x180038f08`
- `0x180038f28`
- `0x1800784cc`
- `0x1800793f0`
- `0x180079574`
- `0x1800f2f4c`
- `0x180118e40`
- `0x180142668`
- `0x18015708c`
- `0x180157c70`
- `0x18015d558`
- `0x180188d90`
- `0x18018e8bf`
- `0x180294310`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038af7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038bf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038af7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038bf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c89`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800385a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800385a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038b45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038be1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038c79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038b45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038be1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038c79`

## string_xrefs

- `0x180038e0f`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall inverted::CIndexScanner::NextKey(
        unsigned __int64 this,
        const struct CIndexKey **k,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // r14
  char *v4; // rdi
  __int64 v5; // rsi
  const struct CIndexKey *v6; // r13
  char *v7; // r15
  char *v8; // r12
  unsigned __int64 v9; // rbx
  unsigned int *v10; // rax
  __int64 v11; // rcx
  _BYTE **v12; // r8
  unsigned int *v13; // rax
  unsigned int v14; // edi
  __int64 j; // r9
  unsigned int *v16; // rax
  unsigned int v17; // edx
  int v18; // r8d
  int v19; // eax
  int v20; // r8d
  unsigned int *v21; // rax
  unsigned int v22; // esi
  unsigned int v23; // ecx
  int *v24; // r8
  __int64 v25; // rdx
  int v26; // eax
  int v27; // eax
  unsigned __int16 *v28; // rax
  _DWORD *v29; // r9
  _DWORD *v30; // r10
  _DWORD *v31; // rcx
  int v32; // r8d
  int v33; // ecx
  unsigned int v34; // eax
  char *v35; // rax
  bool v36; // r15
  bool NextDataPage; // bl
  unsigned int v38; // eax
  unsigned __int16 v39; // si
  unsigned __int16 v40; // di
  unsigned __int16 v41; // ax
  int v42; // eax
  int *v44; // rax
  int v45; // r10d
  unsigned int *v46; // rax
  unsigned int i; // r9d
  unsigned __int8 *v48; // rax
  bool v49; // cf
  LSTATUS v50; // eax
  DWORD v51; // ecx
  __int32 v52; // eax
  LSTATUS v53; // eax
  DWORD v54; // ecx
  __int32 v55; // eax
  LSTATUS v56; // eax
  DWORD v57; // ecx
  __int32 v58; // eax
  TPResultException *v59; // rbx
  std::_Ref_count_base *v60; // rax
  __int64 v61; // rax
  const wchar_t *lpData; // [rsp+20h] [rbp-E0h]
  __int64 v63; // [rsp+30h] [rbp-D0h]
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD v66; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v67[4]; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v68; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v69[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  BOOL v70; // [rsp+50h] [rbp-B0h]
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD lpcbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v73; // [rsp+60h] [rbp-A0h] BYREF
  const struct CIndexKey **v74; // [rsp+68h] [rbp-98h]
  std::_Ref_count_base *v75; // [rsp+70h] [rbp-90h]
  _BYTE v76[176]; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+130h] [rbp+30h]
  _DWORD v78[1664]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B88h] [rbp+1A88h]

  v74 = k;
  v3 = this;
  v4 = (char *)(this + 3456);
  v5 = *(_QWORD *)(this + 3456);
  v63 = v5;
  v6 = (const struct CIndexKey *)(this + 3476);
  v7 = (char *)(this + 3476);
  v8 = (char *)(this + 3476);
  while ( 1 )
  {
    LOBYTE(v70) = 0;
    v9 = *(_QWORD *)v4;
    if ( !*(_QWORD *)v4 )
      break;
    v8 = v7;
    if ( *(_QWORD *)(v9 + 1840) < *(_QWORD *)(v9 + 1848) )
    {
      v10 = *(unsigned int **)(v9 + 1856);
      if ( (unsigned __int64)v10 >= *(_QWORD *)(v9 + 1864) )
        goto LABEL_6;
      this = *(_QWORD *)(v9 + 1872) + 4LL * *v10;
      if ( this > *(_QWORD *)(v9 + 1880) )
        goto LABEL_6;
      if ( _InterlockedCompareExchange(&dword_1803690AC, 0, 0) )
        goto LABEL_12;
      CRegistry::CRegistry(
        (CRegistry *)v76,
        HKEY_LOCAL_MACHINE,
        L"SOFTWARE\\Microsoft\\Windows Search\\Databases",
        0x20019u,
        lpData);
      SetLastError(0);
      cbData = 4;
      Type = 0;
      *(_DWORD *)Data = 0;
      if ( hKey )
      {
        v50 = RegQueryValueExW(hKey, L"PageSize", 0, &Type, Data, &cbData);
        if ( !v50 && Type == 4 )
        {
          v52 = *(_DWORD *)Data;
          if ( *(_DWORD *)Data != 0x8000
            && *(_DWORD *)Data != 4096
            && *(_DWORD *)Data != 0x2000
            && *(_DWORD *)Data != 0x4000 )
          {
LABEL_82:
            v52 = 0x8000;
          }
          _InterlockedExchange(&dword_1803690AC, v52);
          CRegistry::~CRegistry((CRegistry *)v76);
LABEL_12:
          if ( dword_1803690AC == 0x2000 || (a3 = 664, dword_1803690AC != 4096) )
            a3 = 1664;
          this = **(unsigned int **)(v9 + 1840);
          k = (const struct CIndexKey **)(this + **(unsigned int **)(v9 + 1856));
          if ( (unsigned __int64)k > a3 )
          {
LABEL_6:
            MicrosoftTelemetryAssertTriggeredNoArgs(this, k, a3);
            inverted::CorruptionCallback::ReportCorruption(
              2147942413LL,
              "onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\DecodingLayerPages.h",
              403);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x193,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\DecodingLayerPages.h",
              (const char *)0x8007000DLL,
              (int)lpData);
          }
          *(_DWORD *)v7 = *(_DWORD *)(v9 + 52);
          if ( (*(_BYTE *)(v9 + 52) & 1) != 0 )
          {
            v44 = *(int **)(v9 + 1840);
            v45 = *v44;
            *(_QWORD *)(v9 + 1840) = v44 + 1;
            v46 = *(unsigned int **)(v9 + 1856);
            v24 = (int *)*v46;
            *(_QWORD *)(v9 + 1856) = v46 + 1;
            for ( i = 0; i < (unsigned int)v24; ++i )
            {
              v48 = *(unsigned __int8 **)(v9 + 1872);
              k = (const struct CIndexKey **)*v48;
              *(_QWORD *)(v9 + 1872) = v48 + 4;
              v7[i + 8 + v45] = (char)k;
            }
            LOWORD(v24) = v45 + (_WORD)v24;
            *((_WORD *)v7 + 3) = (_WORD)v24;
            goto LABEL_32;
          }
          v13 = *(unsigned int **)(v9 + 1856);
          v14 = *v13;
          *(_QWORD *)(v9 + 1856) = v13 + 1;
          if ( _InterlockedCompareExchange(&dword_1803690AC, 0, 0) )
            goto LABEL_17;
          CRegistry::CRegistry(
            (CRegistry *)v76,
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows Search\\Databases",
            0x20019u,
            lpData);
          SetLastError(0);
          lpcbData = 4;
          v66 = 0;
          *(_DWORD *)v67 = 0;
          if ( hKey )
          {
            v53 = RegQueryValueExW(hKey, L"PageSize", 0, &v66, v67, &lpcbData);
            if ( !v53 && v66 == 4 )
            {
              v55 = *(_DWORD *)v67;
              if ( *(_DWORD *)v67 != 0x8000
                && *(_DWORD *)v67 != 4096
                && *(_DWORD *)v67 != 0x2000
                && *(_DWORD *)v67 != 0x4000 )
              {
LABEL_88:
                v55 = 0x8000;
              }
              _InterlockedExchange(&dword_1803690AC, v55);
              CRegistry::~CRegistry((CRegistry *)v76);
LABEL_17:
              for ( j = 0; (unsigned int)j < v14; j = (unsigned int)(j + 1) )
              {
                v16 = *(unsigned int **)(v9 + 1872);
                v17 = *v16;
                *(_QWORD *)(v9 + 1872) = v16 + 1;
                v18 = *(_DWORD *)(v9 + 1792);
                v19 = (v17 >> 1) + v18;
                v20 = v18 - (v17 >> 1);
                if ( (v17 & 1) == 0 )
                  v20 = v19;
                *(_DWORD *)(v9 + 1792) = v20;
                v78[j] = v20;
              }
              v21 = *(unsigned int **)(v9 + 1840);
              v22 = *v21;
              *(_QWORD *)(v9 + 1840) = v21 + 1;
              if ( v22 > (*((_WORD *)v7 + 3) & 1) + (*((unsigned __int16 *)v7 + 3) >> 1) )
LABEL_136:
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x26E,
                  (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
                  (const char *)0x8007000DLL,
                  (int)lpData);
              if ( _InterlockedCompareExchange(&dword_1803690AC, 0, 0) )
              {
LABEL_23:
                if ( dword_1803690AC == 0x2000 || (v23 = 664, dword_1803690AC != 4096) )
                  v23 = 1664;
                if ( 2 * (v14 + v22) > v23 )
                  goto LABEL_136;
                v24 = v78;
                v25 = *((unsigned __int16 *)v7 + 3);
                v26 = (*((unsigned __int16 *)v7 + 3) >> 1) + (*((_WORD *)v7 + 3) & 1);
                if ( v26 == v22 && 2 * v26 - (_DWORD)v25 == 1 )
                  v7[v25 + 8] = 1;
                *((_WORD *)v7 + 3) = 2 * (v22 + v14);
                for ( k = (const struct CIndexKey **)&v7[2 * v22 + 8]; v14; --v14 )
                {
                  *(_BYTE *)k = *((_BYTE *)v24 + 1);
                  v27 = *v24++;
                  *((_BYTE *)k + 1) = v27;
                  k = (const struct CIndexKey **)((char *)k + 2);
                }
                this = *((unsigned __int16 *)v7 + 3);
                if ( (_WORD)this && v7[this + 7] == 1 && ((*v7 & 2) == 0 || (unsigned int)this > 2) )
                {
                  LOWORD(this) = this - 1;
                  *((_WORD *)v7 + 3) = this;
                }
                v5 = v63;
LABEL_32:
                if ( (*(_BYTE *)(v9 + 52) & 2) != 0 )
                {
                  a3 = (unsigned __int8)v7[9];
                  this = 256;
                  k = (const struct CIndexKey **)((unsigned __int8)v7[8] << 8);
                  LOWORD(a3) = ((unsigned __int8)v7[8] << 8) + a3;
                }
                else
                {
                  v28 = *(unsigned __int16 **)(v9 + 1888);
                  if ( (unsigned __int64)v28 >= *(_QWORD *)(v9 + 1896) )
                  {
                    MicrosoftTelemetryAssertTriggeredNoArgs(this, k, v24);
                    inverted::CorruptionCallback::ReportCorruption(
                      2147942413LL,
                      "onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\DecodingLayerPages.h",
                      444);
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x1BC,
                      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\DecodingLayerPages.h",
                      (const char *)0x8007000DLL,
                      (int)lpData);
                  }
                  a3 = *v28;
                  *(_QWORD *)(v9 + 1888) = v28 + 2;
                }
                *((_WORD *)v7 + 2) = a3;
                v29 = *(_DWORD **)(v9 + 1904);
                if ( (unsigned __int64)v29 >= *(_QWORD *)(v9 + 1912) )
                {
                  if ( *(_QWORD *)(v9 + 1840) < *(_QWORD *)(v9 + 1848) )
                  {
                    MicrosoftTelemetryAssertTriggeredNoArgs(this, k, a3);
                    inverted::CorruptionCallback::ReportCorruption(
                      2147942413LL,
                      "onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\DecodingLayerPages.h",
                      457);
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x1C9,
                      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\DecodingLayerPages.h",
                      (const char *)0x8007000DLL,
                      (int)lpData);
                  }
                  v35 = 0;
                }
                else
                {
                  v30 = *(_DWORD **)(v9 + 1920);
                  v31 = &v30[*v29 + 1];
                  if ( (unsigned __int64)v31 > *(_QWORD *)(v9 + 1928) )
                  {
                    MicrosoftTelemetryAssertTriggeredNoArgs(v31, k, a3);
                    if ( inverted::CorruptionCallback::s_pCallback )
                      inverted::CorruptionCallback::s_pCallback(
                        2147942413LL,
                        "onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\DecodingLayerPages.h",
                        558,
                        0);
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x22E,
                      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\DecodingLayerPages.h",
                      (const char *)0x8007000DLL,
                      (int)lpData);
                  }
                  v32 = *(_DWORD *)(v9 + 1768);
                  v33 = *v30 >> 1;
                  v34 = v33 + v32;
                  a3 = (unsigned int)(v32 - v33);
                  if ( (*(_BYTE *)v30 & 1) == 0 )
                    a3 = v34;
                  *(_DWORD *)(v9 + 1768) = a3;
                  *(_QWORD *)(v9 + 1776) = v30;
                  *(_QWORD *)(v9 + 1784) = v30;
                  this = 4LL * (unsigned int)(*v29 + 1);
                  *(_QWORD *)(v9 + 1904) = v29 + 1;
                  v35 = (char *)v30 + this;
                }
                *(_QWORD *)(v9 + 1920) = v35;
LABEL_42:
                v36 = v70;
                NextDataPage = 1;
                goto LABEL_43;
              }
              CRegistry::CRegistry(
                (CRegistry *)v76,
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows Search\\Databases",
                0x20019u,
                lpData);
              SetLastError(0);
              v73 = 4;
              v68 = 0;
              *(_DWORD *)v69 = 0;
              if ( hKey )
              {
                v56 = RegQueryValueExW(hKey, L"PageSize", 0, &v68, v69, &v73);
                if ( !v56 && v68 == 4 )
                {
                  v58 = *(_DWORD *)v69;
                  if ( *(_DWORD *)v69 != 0x8000
                    && *(_DWORD *)v69 != 4096
                    && *(_DWORD *)v69 != 0x2000
                    && *(_DWORD *)v69 != 0x4000 )
                  {
LABEL_94:
                    v58 = 0x8000;
                  }
                  _InterlockedExchange(&dword_1803690AC, v58);
                  CRegistry::~CRegistry((CRegistry *)v76);
                  goto LABEL_23;
                }
                v57 = v56;
              }
              else
              {
                v57 = 6;
              }
              SetLastError(v57);
              goto LABEL_94;
            }
            v54 = v53;
          }
          else
          {
            v54 = 6;
          }
          SetLastError(v54);
          goto LABEL_88;
        }
        v51 = v50;
      }
      else
      {
        v51 = 6;
      }
      SetLastError(v51);
      goto LABEL_82;
    }
    NextDataPage = inverted::CIndexScanner::_ReadNextDataPage((inverted::CIndexScanner *)v3);
    if ( !NextDataPage )
      goto LABEL_50;
    this = *(_QWORD *)v4;
    v36 = *(_DWORD *)(*(_QWORD *)v4 + 1724LL) != 0;
LABEL_43:
    if ( !v5 && (unsigned __int8)inverted::CIndexKey::operator<(v8, v3 + 96) )
      v36 = 1;
    v38 = *(_DWORD *)(v3 + 1768);
    if ( *(_DWORD *)v8 == v38 )
    {
      v39 = *(_WORD *)(v3 + 1774);
      v40 = *((_WORD *)v8 + 3);
      v41 = v40;
      if ( v40 >= v39 )
        v41 = *(_WORD *)(v3 + 1774);
      v42 = memcmp_0(v8 + 8, (const void *)(v3 + 1776), v41);
      if ( v42 )
      {
        if ( v42 >= 0 )
          goto LABEL_49;
        v5 = v63;
      }
      else
      {
        v49 = v40 < v39;
        if ( v40 == v39 )
          v49 = *((_WORD *)v8 + 2) < *(_WORD *)(v3 + 1772);
        if ( !v49 )
          goto LABEL_49;
        v5 = v63;
      }
    }
    else if ( *(_DWORD *)v8 >= v38 )
    {
      goto LABEL_49;
    }
    if ( !v36 )
      goto LABEL_50;
    v7 = v8;
    v4 = (char *)(v3 + 3456);
  }
  *(_BYTE *)(v3 + 5225) = 0;
  WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)(v3 + 5216), 0);
  if ( *(int *)(v3 + 5240) > 0 )
  {
    v61 = *(_QWORD *)(v3 + 5256);
    if ( v61 )
      _InterlockedIncrement((volatile signed __int32 *)(v61 + 8));
    v59 = *(TPResultException **)(v3 + 5248);
    v74 = (const struct CIndexKey **)v59;
    v75 = *(std::_Ref_count_base **)(v3 + 5256);
    v60 = v75;
    *(_QWORD *)(v3 + 5248) = 0;
    *(_QWORD *)(v3 + 5256) = 0;
    if ( v60 )
      std::_Ref_count_base::_Decref(v60);
    *(_DWORD *)(v3 + 5240) = 0;
    CInterlockedStack<std::function<void (void)>>::clear(v3 + 5232);
    if ( !v59 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E2,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
        (const char *)0x8000FFFFLL,
        (int)lpData);
    TPResultException::raise(v59);
  }
  v11 = *(_QWORD *)(v3 + 3464);
  if ( v11 )
  {
    v12 = *(_BYTE ***)(v3 + 3440);
    if ( !v12 || !*v12[21] && !*v12[22] && !*v12[20] )
    {
      ++*(_DWORD *)(v3 + 3448);
      std::unique_ptr<inverted::COccSet [0]>::swap(v4);
      *(_BYTE *)(v3 + 3472) = 0;
      inverted::CIndexKey::operator=(v6, *(_QWORD *)v4 + 52LL);
      TPUtils::task_group::run__lambda_4088de9e5b3b8fe93480fc6548dae01e___(v3 + 5216, v3);
      goto LABEL_42;
    }
  }
  *(_QWORD *)(v3 + 3464) = 0;
  if ( v11 )
    std::default_delete<inverted::CDecodedDataPage>::operator()(v11, v11);
LABEL_49:
  NextDataPage = 0;
LABEL_50:
  *v74 = v6;
  return NextDataPage;
}

```

## disassembly

```asm
0x1800384b0  mov     [rsp-8+arg_10], rbx
0x1800384b5  push    rbp
0x1800384b6  push    rsi
0x1800384b7  push    rdi
0x1800384b8  push    r12
0x1800384ba  push    r13
0x1800384bc  push    r14
0x1800384be  push    r15
0x1800384c0  lea     rbp, [rsp-1A50h]
0x1800384c8  mov     eax, 1B50h
0x1800384cd  call    _alloca_probe
0x1800384d2  sub     rsp, rax
0x1800384d5  mov     rax, cs:__security_cookie
0x1800384dc  xor     rax, rsp
0x1800384df  mov     [rbp+1A80h+var_40], rax
0x1800384e6  mov     [rsp+1B80h+var_1B18], rdx
0x1800384eb  mov     r14, rcx
0x1800384ee  lea     rdi, [rcx+0D80h]
0x1800384f5  mov     rsi, [rdi]
0x1800384f8  mov     [rsp+1B80h+var_1B50], rsi
0x1800384fd  lea     r13, [rcx+0D94h]
0x180038504  mov     r15, r13
0x180038507  mov     r12, r13
0x18003850a  mov     byte ptr [rsp+1B80h+var_1B30], 0
0x18003850f  mov     rbx, [rdi]
0x180038512  test    rbx, rbx
0x180038515  jz      short loc_180038593
0x180038517  mov     r12, r15
0x18003851a  mov     rax, [rbx+738h]
0x180038521  cmp     [rbx+730h], rax
0x180038528  jnb     loc_18003892D
0x18003852e  mov     rax, [rbx+740h]
0x180038535  cmp     rax, [rbx+748h]
0x18003853c  jnb     short loc_180038558
0x18003853e  mov     ecx, [rax]
0x180038540  mov     rax, [rbx+750h]
0x180038547  lea     rcx, [rax+rcx*4]
0x18003854b  cmp     rcx, [rbx+758h]
0x180038552  jbe     loc_180038616
0x180038558  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003855d  mov     r8d, 193h
0x180038563  lea     rdx, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18003856a  mov     ecx, 8007000Dh
0x18003856f  call    ?ReportCorruption@CorruptionCallback@inverted@@SAXJPEBD_KPEBV?$function@$$A6APEAEJ@Z@std@@@Z; inverted::CorruptionCallback::ReportCorruption(long,char const *,unsigned __int64,std::function<uchar * (long)> const *)
0x180038574  mov     rcx, [rbp+1A88h]; this
0x18003857b  mov     r9d, 8007000Dh; char *
0x180038581  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180038588  mov     edx, 193h; void *
0x18003858d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038593  mov     byte ptr [r14+1469h], 0
0x18003859b  xor     edx, edx; fCancelPendingCallbacks
0x18003859d  mov     rcx, [r14+1460h]; pwk
0x1800385a4  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800385aa  mov     eax, [r14+1478h]
0x1800385b1  test    eax, eax
0x1800385b3  jg      loc_180038EE0
0x1800385b9  lea     rdx, [r14+0D88h]
0x1800385c0  mov     rcx, [rdx]
0x1800385c3  test    rcx, rcx
0x1800385c6  jz      loc_180038A61
0x1800385cc  mov     r8, [r14+0D70h]
0x1800385d3  test    r8, r8
0x1800385d6  jnz     loc_180038D82
0x1800385dc  inc     dword ptr [r14+0D78h]
0x1800385e3  mov     rcx, rdi
0x1800385e6  call    ?swap@?$unique_ptr@$$BY0A@VCOccSet@inverted@@U?$default_delete@$$BY0A@VCOccSet@inverted@@@std@@@std@@QEAAXAEAV12@@Z; std::unique_ptr<inverted::COccSet [0]>::swap(std::unique_ptr<inverted::COccSet [0]> &)
0x1800385eb  mov     byte ptr [r14+0D90h], 0
0x1800385f3  mov     rdx, [rdi]
0x1800385f6  add     rdx, 34h ; '4'
0x1800385fa  mov     rcx, r13
0x1800385fd  call    ??4CIndexKey@inverted@@QEAAAEAV01@AEBV01@@Z; inverted::CIndexKey::operator=(inverted::CIndexKey const &)
0x180038602  mov     rdx, r14
0x180038605  lea     rcx, [r14+1460h]
0x18003860c  call    TPUtils__task_group__run__lambda_4088de9e5b3b8fe93480fc6548dae01e___
0x180038611  jmp     loc_18003887F
0x180038616  xor     ecx, ecx
0x180038618  xor     eax, eax
0x18003861a  lock cmpxchg cs:dword_1803690AC, ecx
0x180038622  jz      loc_180038AD8
0x180038628  mov     eax, cs:dword_1803690AC
0x18003862e  cmp     eax, 2000h
0x180038633  jnz     loc_180038E31
0x180038639  mov     r8d, 680h
0x18003863f  mov     rax, [rbx+740h]
0x180038646  mov     edx, [rax]
0x180038648  mov     rax, [rbx+730h]
0x18003864f  mov     ecx, [rax]
0x180038651  add     rdx, rcx
0x180038654  cmp     rdx, r8
0x180038657  ja      loc_180038558
0x18003865d  mov     eax, [rbx+34h]
0x180038660  mov     [r15], eax
0x180038663  test    byte ptr [rbx+34h], 1
0x180038667  jnz     loc_1800389D4
0x18003866d  mov     rax, [rbx+740h]
0x180038674  mov     edi, [rax]
0x180038676  add     rax, 4
0x18003867a  mov     [rbx+740h], rax
0x180038681  xor     ecx, ecx
0x180038683  xor     eax, eax
0x180038685  lock cmpxchg cs:dword_1803690AC, ecx
0x18003868d  jz      loc_180038B74
0x180038693  xor     r9d, r9d
0x180038696  test    edi, edi
0x180038698  jz      short loc_1800386E1
0x18003869a  nop     word ptr [rax+rax+00h]
0x1800386a0  mov     rax, [rbx+750h]
0x1800386a7  mov     edx, [rax]
0x1800386a9  add     rax, 4
0x1800386ad  mov     [rbx+750h], rax
0x1800386b4  mov     r8d, [rbx+700h]
0x1800386bb  mov     ecx, edx
0x1800386bd  shr     ecx, 1
0x1800386bf  lea     eax, [rcx+r8]
0x1800386c3  sub     r8d, ecx
0x1800386c6  test    dl, 1
0x1800386c9  cmovz   r8d, eax
0x1800386cd  mov     [rbx+700h], r8d
0x1800386d4  mov     [rbp+r9*4+1A80h+var_1A40], r8d
0x1800386d9  inc     r9d
0x1800386dc  cmp     r9d, edi
0x1800386df  jb      short loc_1800386A0
0x1800386e1  mov     rax, [rbx+730h]
0x1800386e8  mov     esi, [rax]
0x1800386ea  add     rax, 4
0x1800386ee  mov     [rbx+730h], rax
0x1800386f5  movzx   eax, word ptr [r15+6]
0x1800386fa  mov     ecx, eax
0x1800386fc  shr     ecx, 1
0x1800386fe  and     eax, 1
0x180038701  add     ecx, eax
0x180038703  cmp     esi, ecx
0x180038705  ja      loc_180038EC1
0x18003870b  xor     ecx, ecx
0x18003870d  xor     eax, eax
0x18003870f  lock cmpxchg cs:dword_1803690AC, ecx
0x180038717  jz      loc_180038C10
0x18003871d  mov     eax, cs:dword_1803690AC
0x180038723  cmp     eax, 2000h
0x180038728  jnz     loc_180038E67
0x18003872e  mov     ecx, 680h
0x180038733  lea     eax, [rdi+rsi]
0x180038736  add     eax, eax
0x180038738  cmp     eax, ecx
0x18003873a  ja      loc_180038EC1
0x180038740  lea     r8, [rbp+1A80h+var_1A40]
0x180038744  movzx   edx, word ptr [r15+6]
0x180038749  mov     ecx, edx
0x18003874b  shr     ecx, 1
0x18003874d  mov     eax, edx
0x18003874f  and     eax, 1
0x180038752  add     eax, ecx
0x180038754  cmp     eax, esi
0x180038756  jz      loc_180038A3A
0x18003875c  lea     eax, [rsi+rdi]
0x18003875f  add     ax, ax
0x180038762  mov     [r15+6], ax
0x180038767  lea     edx, [rsi+rsi]
0x18003876a  add     rdx, 8
0x18003876e  add     rdx, r15
0x180038771  test    edi, edi
0x180038773  jz      short loc_18003879A
0x180038775  nop     word ptr [rax+rax+00000000h]
0x180038780  movzx   eax, byte ptr [r8+1]
0x180038785  mov     [rdx], al
0x180038787  mov     eax, [r8]
0x18003878a  lea     r8, [r8+4]
0x18003878e  mov     [rdx+1], al
0x180038791  lea     rdx, [rdx+2]
0x180038795  add     edi, 0FFFFFFFFh
0x180038798  jnz     short loc_180038780
0x18003879a  movzx   ecx, word ptr [r15+6]
0x18003879f  test    cx, cx
0x1800387a2  jz      short loc_1800387B0
0x1800387a4  cmp     byte ptr [rcx+r15+7], 1
0x1800387aa  jz      loc_180038ABC
0x1800387b0  mov     rsi, [rsp+1B80h+var_1B50]
0x1800387b5  test    byte ptr [rbx+34h], 2
0x1800387b9  jnz     short loc_1800387E0
0x1800387bb  mov     rax, [rbx+760h]
0x1800387c2  cmp     rax, [rbx+768h]
0x1800387c9  jnb     loc_180038999
0x1800387cf  movzx   r8d, word ptr [rax]
0x1800387d3  add     rax, 4
0x1800387d7  mov     [rbx+760h], rax
0x1800387de  jmp     short loc_1800387F6
0x1800387e0  movzx   r8d, byte ptr [r15+9]
0x1800387e5  movzx   edx, byte ptr [r15+8]
0x1800387ea  mov     ecx, 100h
0x1800387ef  imul    edx, ecx
0x1800387f2  add     r8w, dx
0x1800387f6  mov     [r15+4], r8w
0x1800387fb  mov     r9, [rbx+770h]
0x180038802  cmp     r9, [rbx+778h]
0x180038809  jnb     loc_180038912
0x18003880f  mov     r10, [rbx+780h]
0x180038816  mov     eax, [r9]
0x180038819  inc     eax
0x18003881b  lea     rcx, [r10+rax*4]
0x18003881f  cmp     rcx, [rbx+788h]
0x180038826  ja      loc_18003894F
0x18003882c  mov     ecx, [r10]
0x18003882f  mov     r8d, [rbx+6E8h]
0x180038836  shr     ecx, 1
0x180038838  lea     eax, [rcx+r8]
0x18003883c  sub     r8d, ecx
0x18003883f  test    byte ptr [r10], 1
0x180038843  cmovz   r8d, eax
0x180038847  mov     [rbx+6E8h], r8d
0x18003884e  mov     [rbx+6F0h], r10
0x180038855  mov     [rbx+6F8h], r10
0x18003885c  mov     eax, [r9]
0x18003885f  inc     eax
0x180038861  lea     rcx, ds:0[rax*4]
0x180038869  lea     rax, [r9+4]
0x18003886d  mov     [rbx+770h], rax
0x180038874  lea     rax, [r10+rcx]
0x180038878  mov     [rbx+780h], rax
0x18003887f  mov     r15d, [rsp+1B80h+var_1B30]
0x180038884  mov     bl, 1
0x180038886  test    rsi, rsi
0x180038889  jz      loc_180038CC3
0x18003888f  mov     eax, [r14+6E8h]
0x180038896  cmp     [r12], eax
0x18003889a  jnz     loc_180038A7E
0x1800388a0  movzx   esi, word ptr [r14+6EEh]
0x1800388a8  movzx   edi, word ptr [r12+6]
0x1800388ae  movzx   eax, di
0x1800388b1  cmp     di, si
0x1800388b4  cmovnb  ax, si
0x1800388b8  movzx   r8d, ax; Size
0x1800388bc  lea     rdx, [r14+6F0h]; Buf2
0x1800388c3  lea     rcx, [r12+8]; Buf1
0x1800388c8  call    memcmp_0
0x1800388cd  test    eax, eax
0x1800388cf  jz      loc_180038A86
0x1800388d5  js      loc_180038E7C
0x1800388db  xor     bl, bl
0x1800388dd  mov     rax, [rsp+1B80h+var_1B18]
0x1800388e2  mov     [rax], r13
0x1800388e5  movzx   eax, bl
0x1800388e8  mov     rcx, [rbp+1A80h+var_40]
0x1800388ef  xor     rcx, rsp; StackCookie
0x1800388f2  call    __security_check_cookie
0x1800388f7  mov     rbx, [rsp+1B80h+arg_10]
0x1800388ff  add     rsp, 1B50h
0x180038906  pop     r15
0x180038908  pop     r14
0x18003890a  pop     r13
0x18003890c  pop     r12
0x18003890e  pop     rdi
0x18003890f  pop     rsi
0x180038910  pop     rbp
0x180038911  retn
0x180038912  mov     rax, [rbx+738h]
0x180038919  cmp     [rbx+730h], rax
0x180038920  jb      loc_180038E86
0x180038926  xor     eax, eax
0x180038928  jmp     loc_180038878
0x18003892d  mov     rcx, r14; this
0x180038930  call    ?_ReadNextDataPage@CIndexScanner@inverted@@AEAA_NXZ; inverted::CIndexScanner::_ReadNextDataPage(void)
0x180038935  movzx   ebx, al
0x180038938  test    al, al
0x18003893a  jz      short loc_1800388DD
0x18003893c  mov     rcx, [rdi]
0x18003893f  cmp     dword ptr [rcx+6BCh], 0
0x180038946  setnbe  r15b
0x18003894a  jmp     loc_180038886
0x18003894f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180038954  mov     rax, cs:?s_pCallback@CorruptionCallback@inverted@@0P6AXJPEBD_KPEBV?$function@$$A6APEAEJ@Z@std@@@ZEA; void (*inverted::CorruptionCallback::s_pCallback)(long,char const *,unsigned __int64,std::function<uchar * (long)> const *)
0x18003895b  test    rax, rax
0x18003895e  jz      short loc_18003897A
0x180038960  xor     r9d, r9d
0x180038963  mov     r8d, 22Eh
0x180038969  lea     rdx, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180038970  mov     ecx, 8007000Dh
0x180038975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003897a  mov     rcx, [rbp+1A88h]; this
0x180038981  mov     r9d, 8007000Dh; char *
0x180038987  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18003898e  mov     edx, 22Eh; void *
0x180038993  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038999  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003899e  mov     r8d, 1BCh
0x1800389a4  lea     rdx, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800389ab  mov     ecx, 8007000Dh
0x1800389b0  call    ?ReportCorruption@CorruptionCallback@inverted@@SAXJPEBD_KPEBV?$function@$$A6APEAEJ@Z@std@@@Z; inverted::CorruptionCallback::ReportCorruption(long,char const *,unsigned __int64,std::function<uchar * (long)> const *)
0x1800389b5  mov     rcx, [rbp+1A88h]; this
0x1800389bc  mov     r9d, 8007000Dh; char *
0x1800389c2  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800389c9  mov     edx, 1BCh; void *
0x1800389ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800389d4  mov     rax, [rbx+730h]
0x1800389db  mov     r10d, [rax]
0x1800389de  add     rax, 4
0x1800389e2  mov     [rbx+730h], rax
0x1800389e9  mov     rax, [rbx+740h]
0x1800389f0  mov     r8d, [rax]
0x1800389f3  add     rax, 4
0x1800389f7  mov     [rbx+740h], rax
  ... truncated ...
```
