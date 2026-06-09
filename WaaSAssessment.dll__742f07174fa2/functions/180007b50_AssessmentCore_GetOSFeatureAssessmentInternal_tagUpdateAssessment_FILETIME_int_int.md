# AssessmentCore::GetOSFeatureAssessmentInternal(tagUpdateAssessment *,_FILETIME *,int,int)

- ea: `0x180007b50`
- end: `0x180008210`
- name: `?GetOSFeatureAssessmentInternal@AssessmentCore@@MEAAJPEAUtagUpdateAssessment@@PEAU_FILETIME@@HH@Z`
- size: `1728`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, struct tagUpdateAssessment *, struct _FILETIME *, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180006e28`
- `0x180007b50`
- `0x18001752c`
- `0x180018948`
- `0x180018ac4`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800081e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800081e8`
- `ntdll!RtlPublishWnfStateData` at `0x180008171`
- `ntdll!RtlPublishWnfStateData` at `0x180008171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000808f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000819b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000808f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000819b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007dc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ead`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007fca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008103`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007dc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ead`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007fca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080f0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008155`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008155`

## string_xrefs

- `0x1800080c3`: `Software\Microsoft\Windows\CurrentVersion\WaaSAssessment\Cache`
- `0x1800080ca`: `WaaSAssessmentCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AssessmentCore::GetOSFeatureAssessmentInternal(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        struct _FILETIME *a3,
        int a4,
        int a5)
{
  __int64 v7; // rdi
  __int64 *v8; // rbx
  int v9; // esi
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rax
  int v13; // eax
  unsigned __int16 *v14; // r13
  WCHAR *v15; // r12
  DWORD v16; // edi
  void *v17; // rdx
  __int64 v18; // rax
  unsigned __int16 *v19; // rax
  void *v20; // r13
  DWORD v21; // edi
  __int64 v22; // rax
  const unsigned __int16 *v23; // r12
  int v24; // eax
  unsigned __int16 *v25; // r13
  void *v26; // r12
  DWORD v27; // edi
  void *v28; // rsi
  DWORD v29; // edi
  unsigned __int16 *v30; // rdx
  __int64 v31; // rax
  unsigned __int16 *v32; // rax
  void *v33; // r13
  DWORD v34; // edi
  LPVOID v35; // rdx
  __int64 v36; // rax
  void *v37; // r13
  unsigned __int16 *v38; // rax
  DWORD v39; // edi
  struct _FILETIME *v40; // rcx
  int StateSeparationRegistryLocation; // ecx
  WCHAR *v42; // r13
  DWORD LastError; // edi
  int v44; // eax
  __int64 v45; // rcx
  unsigned __int16 *v47; // [rsp+48h] [rbp-99h] BYREF
  char v48; // [rsp+50h] [rbp-91h]
  int v49[2]; // [rsp+58h] [rbp-89h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-81h]
  int v51; // [rsp+68h] [rbp-79h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-71h]
  int v53; // [rsp+78h] [rbp-69h] BYREF
  LPVOID v54; // [rsp+80h] [rbp-61h]
  unsigned __int16 *v55; // [rsp+88h] [rbp-59h] BYREF
  struct _FILETIME *Data; // [rsp+90h] [rbp-51h] BYREF
  DWORD daysOutOfDate; // [rsp+98h] [rbp-49h]
  __int64 *v58; // [rsp+A0h] [rbp-41h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-39h] BYREF
  DWORD v60; // [rsp+B0h] [rbp-31h]
  LPVOID v61[2]; // [rsp+B8h] [rbp-29h] BYREF
  __int128 v62; // [rsp+C8h] [rbp-19h]
  __int128 v63; // [rsp+D8h] [rbp-9h]

  Data = a3;
  *(_OWORD *)v61 = 0;
  v62 = 0;
  v63 = 0;
  v7 = 0;
  v51 = 0;
  v59 = 0;
  v60 = 0;
  v58 = 0;
  v8 = 0;
  v53 = 0;
  *((_QWORD *)this + 290) = 0;
  if ( !a2 )
  {
    LogLevel(2u, L"Feature Assessment Result is null");
    v9 = -2147467261;
    goto LABEL_78;
  }
  *(_QWORD *)&a2->status = 0;
  a2->daysOutOfDate = 0;
  v9 = (*(__int64 (__fastcall **)(AssessmentCore *, __int64 **, LPVOID *, __int64, int, int))(*(_QWORD *)this + 152LL))(
         this,
         &v58,
         v61,
         6,
         a4,
         a5);
  if ( v58 )
    v8 = v58;
  if ( v9 >= 0 && v9 != 1 )
  {
    LogLevel(4u, L"Performing Feature Assessment");
    if ( (*((_BYTE *)this + 96) & 1) != 0 )
    {
      LogLevel(4u, L"Determining End of Support");
      v9 = (*(__int64 (__fastcall **)(AssessmentCore *, int *))(*(_QWORD *)this + 168LL))(this, &v53);
      if ( v9 < 0 )
        goto LABEL_78;
      if ( !v53 )
        goto LABEL_12;
      LogLevel(4u, L"OS is in End of Support state");
      a2->status = UpdateAssessmentStatus_NotLatestEndOfSupport;
      a2->impact = UpdateImpactLevel_High;
      a2->daysOutOfDate = -1;
    }
    if ( v53 )
    {
LABEL_67:
      if ( v9 >= 0 )
      {
        lpSubKey = 0;
        v47 = 0;
        v48 = 1;
        StateSeparationRegistryLocation = GetStateSeparationRegistryLocation(
                                            L"WaaSAssessmentCache",
                                            L"Software\\Microsoft\\Windows\\CurrentVersion\\WaaSAssessment\\Cache",
                                            &v47);
        v51 = StateSeparationRegistryLocation;
        if ( v48 )
        {
          v42 = (WCHAR *)lpSubKey;
          if ( lpSubKey )
          {
            LastError = GetLastError();
            CoTaskMemFree(v42);
            SetLastError(LastError);
            StateSeparationRegistryLocation = v51;
            v7 = 0;
          }
          lpSubKey = v47;
        }
        if ( StateSeparationRegistryLocation >= 0 )
        {
          Data = *(struct _FILETIME **)&a2->status;
          daysOutOfDate = a2->daysOutOfDate;
          RegSetKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"FeatureAssessment", 3u, &Data, 0xCu);
        }
        v44 = RtlPublishWnfStateData(WNF_WAAS_FEATURE_IMPACT, 0, &a2->impact, 4, 0) | 0x10000000;
        if ( v44 < 0 )
          LogLevel(2u, L"Failed to publish WNF FEATURE IMPACT 0x%x", (unsigned int)v44);
        if ( lpSubKey )
          CoTaskMemFree((LPVOID)lpSubKey);
      }
      goto LABEL_78;
    }
LABEL_12:
    v55 = 0;
    v54 = 0;
    lpSubKey = 0;
    pv = 0;
    v10 = *((_DWORD *)this + 16);
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( (unsigned int)(v11 - 1) > 1 )
          goto LABEL_51;
        v12 = *v8;
        v47 = 0;
        v48 = 1;
        v13 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, unsigned __int16 **))(v12 + 96))(v8, v61[1], &v47);
        v49[0] = v13;
        if ( v48 )
        {
          v14 = v47;
          v15 = (WCHAR *)lpSubKey;
          if ( lpSubKey )
          {
            v16 = GetLastError();
            CoTaskMemFree(v15);
            SetLastError(v16);
            v13 = v49[0];
            v7 = 0;
          }
          lpSubKey = v14;
        }
        if ( v13 < 0 )
        {
          LogLevel(4u, L"Servicing Branch Build not declared hr = 0x%x", (unsigned int)v13);
          v18 = *v8;
          v47 = 0;
          v48 = 1;
          v9 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, unsigned __int16 **))(v18 + 64))(v8, v61[1], &v47);
          if ( v48 )
          {
            v19 = v47;
            *(_QWORD *)v49 = v47;
            v20 = v54;
            if ( v54 )
            {
              v21 = GetLastError();
              CoTaskMemFree(v20);
              SetLastError(v21);
              v19 = *(unsigned __int16 **)v49;
              v7 = 0;
            }
            v54 = v19;
          }
          if ( v9 < 0 )
            goto LABEL_60;
          v17 = v54;
          v54 = 0;
        }
        else
        {
          v17 = (void *)lpSubKey;
          lpSubKey = 0;
        }
        CSpDynamicString::operator=(&v55, v17);
        v22 = *v8;
        v47 = 0;
        v48 = 1;
        v23 = (const unsigned __int16 *)((char *)this + 1776);
        v24 = (*(__int64 (__fastcall **)(__int64 *, char *, unsigned __int16 **))(v22 + 96))(
                v8,
                (char *)this + 1776,
                &v47);
        v49[0] = v24;
        if ( v48 )
        {
          v25 = v47;
          v26 = pv;
          if ( pv )
          {
            v27 = GetLastError();
            CoTaskMemFree(v26);
            SetLastError(v27);
            v24 = v49[0];
            v7 = 0;
          }
          pv = v25;
          v23 = (const unsigned __int16 *)((char *)this + 1776);
        }
        if ( v24 < 0 )
        {
          LogLevel(4u, L"Servicing Branch Build not declared hr = 0x%x", (unsigned int)v24);
        }
        else
        {
          v49[0] = 0;
          v9 = IsOSVersionGreaterThanList(v23, (const unsigned __int16 *)pv, v49);
          if ( v9 < 0 )
            goto LABEL_60;
          if ( !v49[0] )
            goto LABEL_52;
          v28 = pv;
          if ( pv )
          {
            v29 = GetLastError();
            CoTaskMemFree(v28);
            SetLastError(v29);
            v7 = 0;
          }
          pv = 0;
        }
        v30 = (unsigned __int16 *)v23;
LABEL_47:
        v36 = *v8;
        v47 = 0;
        v48 = 1;
        v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 *, unsigned __int16 **))(v36 + 64))(v8, v30, &v47);
        if ( v48 )
        {
          v37 = pv;
          v38 = v47;
          *(_QWORD *)v49 = v47;
          if ( pv )
          {
            v39 = GetLastError();
            CoTaskMemFree(v37);
            SetLastError(v39);
            v38 = *(unsigned __int16 **)v49;
            v7 = 0;
          }
          pv = v38;
        }
LABEL_51:
        if ( v9 >= 0 )
        {
LABEL_52:
          v9 = IsOSVersionGreaterThanList(v55, (const unsigned __int16 *)pv, &v51);
          if ( v9 >= 0 )
          {
            if ( v51 )
            {
              *(_QWORD *)&a2->status = 0;
              a2->daysOutOfDate = 0;
            }
            else if ( (*((_BYTE *)this + 96) & 4) != 0 )
            {
              v9 = (*(__int64 (__fastcall **)(AssessmentCore *, __int64 *, char *, _QWORD))(*(_QWORD *)this + 248LL))(
                     this,
                     &v59,
                     (char *)this + 140,
                     0);
              *(_QWORD *)&a2->status = v59;
              a2->daysOutOfDate = v60;
              v40 = Data;
              if ( Data )
              {
                *Data = 0;
                *v40 = *(struct _FILETIME *)((char *)this + 140);
              }
              v7 = 0;
            }
            else
            {
              v9 = -2147024894;
            }
          }
        }
LABEL_60:
        if ( pv )
          CoTaskMemFree(pv);
        if ( lpSubKey )
          CoTaskMemFree((LPVOID)lpSubKey);
        if ( v54 )
          CoTaskMemFree(v54);
        CoTaskMemFree(v55);
        goto LABEL_67;
      }
      v31 = *v8;
      v47 = 0;
      v48 = 1;
      v9 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, unsigned __int16 **))(v31 + 64))(v8, v61[1], &v47);
      if ( v48 )
      {
        v32 = v47;
        *(_QWORD *)v49 = v47;
        v33 = v54;
        if ( v54 )
        {
          v34 = GetLastError();
          CoTaskMemFree(v33);
          SetLastError(v34);
          v32 = *(unsigned __int16 **)v49;
          v7 = 0;
        }
        v54 = v32;
      }
      if ( v9 < 0 )
        goto LABEL_60;
      v35 = v54;
      v54 = 0;
    }
    else
    {
      v35 = v61[1];
    }
    CSpDynamicString::operator=(&v55, v35);
    v30 = (unsigned __int16 *)((char *)this + 1776);
    goto LABEL_47;
  }
  do
LABEL_78:
    CoTaskMemFree(v61[v7++]);
  while ( v7 != 6 );
  CoTaskMemFree(*((LPVOID *)this + 290));
  if ( v8 )
  {
    v45 = v8[1];
    if ( v45 )
    {
      v8[1] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    operator delete(v8);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007b50  push    rbp
0x180007b52  push    rbx
0x180007b53  push    rsi
0x180007b54  push    rdi
0x180007b55  push    r12
0x180007b57  push    r13
0x180007b59  push    r14
0x180007b5b  push    r15
0x180007b5d  lea     rbp, [rsp-17h]
0x180007b62  sub     rsp, 0F8h
0x180007b69  mov     rax, cs:__security_cookie
0x180007b70  xor     rax, rsp
0x180007b73  mov     [rbp+4Fh+var_48], rax
0x180007b77  mov     [rbp+4Fh+Data], r8
0x180007b7b  mov     r14, rdx
0x180007b7e  mov     r15, rcx
0x180007b81  xorps   xmm0, xmm0
0x180007b84  movups  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180007b88  movups  [rbp+4Fh+var_68], xmm0
0x180007b8c  movups  [rbp+4Fh+var_58], xmm0
0x180007b90  xor     edi, edi
0x180007b92  mov     [rbp+4Fh+var_C8], edi
0x180007b95  xor     eax, eax
0x180007b97  mov     [rbp+4Fh+var_88], rax
0x180007b9b  mov     [rbp+4Fh+var_80], eax
0x180007b9e  mov     [rbp+4Fh+var_90], rdi
0x180007ba2  mov     ebx, edi
0x180007ba4  mov     [rbp+4Fh+var_B8], edi
0x180007ba7  mov     [rcx+910h], rdi
0x180007bae  test    rdx, rdx
0x180007bb1  jnz     short loc_180007BCC
0x180007bb3  lea     rdx, aFeatureAssessm; "Feature Assessment Result is null"
0x180007bba  lea     ecx, [rdi+2]; unsigned __int8
0x180007bbd  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007bc2  mov     esi, 80004003h
0x180007bc7  jmp     loc_1800081A1
0x180007bcc  mov     [rdx], rax
0x180007bcf  mov     [rdx+8], eax
0x180007bd2  mov     rax, [rcx]
0x180007bd5  mov     r10, [rax+98h]
0x180007bdc  mov     eax, [rbp+4Fh+arg_20]
0x180007bdf  mov     [rsp+130h+cbData], eax
0x180007be3  mov     dword ptr [rsp+130h+lpData], r9d
0x180007be8  mov     r9d, 6
0x180007bee  lea     r8, [rbp+4Fh+var_78]
0x180007bf2  lea     rdx, [rbp+4Fh+var_90]
0x180007bf6  mov     rax, r10
0x180007bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bfe  mov     esi, eax
0x180007c00  mov     rax, [rbp+4Fh+var_90]
0x180007c04  test    rax, rax
0x180007c07  jz      short loc_180007C0D
0x180007c09  cmovnz  rbx, rax
0x180007c0d  test    esi, esi
0x180007c0f  js      loc_1800081A1
0x180007c15  cmp     esi, 1
0x180007c18  jz      loc_1800081A1
0x180007c1e  lea     rdx, aPerformingFeat; "Performing Feature Assessment"
0x180007c25  mov     r12d, 4
0x180007c2b  mov     ecx, r12d; unsigned __int8
0x180007c2e  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007c33  lea     r13d, [r12-1]
0x180007c38  test    byte ptr [r15+60h], 1
0x180007c3d  jbe     short loc_180007C91
0x180007c3f  lea     rdx, aDeterminingEnd; "Determining End of Support"
0x180007c46  mov     ecx, r12d; unsigned __int8
0x180007c49  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007c4e  mov     rax, [r15]
0x180007c51  lea     rdx, [rbp+4Fh+var_B8]
0x180007c55  mov     rcx, r15
0x180007c58  mov     rax, [rax+0A8h]
0x180007c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c64  mov     esi, eax
0x180007c66  test    eax, eax
0x180007c68  js      loc_1800081A1
0x180007c6e  cmp     [rbp+4Fh+var_B8], edi
0x180007c71  jz      short loc_180007C9A
0x180007c73  lea     rdx, aOsIsInEndOfSup; "OS is in End of Support state"
0x180007c7a  mov     ecx, r12d; unsigned __int8
0x180007c7d  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007c82  mov     [r14], r13d
0x180007c85  mov     [r14+4], r13d
0x180007c89  mov     dword ptr [r14+8], 0FFFFFFFFh
0x180007c91  cmp     [rbp+4Fh+var_B8], edi
0x180007c94  jnz     loc_18000809F
0x180007c9a  mov     [rbp+4Fh+var_A8], rdi
0x180007c9e  mov     [rbp+4Fh+var_B0], rdi
0x180007ca2  mov     [rbp+4Fh+lpSubKey], rdi
0x180007ca6  mov     [rsp+130h+pv], rdi
0x180007cab  mov     ecx, [r15+40h]
0x180007caf  test    ecx, ecx
0x180007cb1  jz      loc_180007F5A
0x180007cb7  sub     ecx, 1
0x180007cba  jz      loc_180007ED8
0x180007cc0  sub     ecx, 1
0x180007cc3  jz      short loc_180007CCE
0x180007cc5  cmp     ecx, 1
0x180007cc8  jnz     loc_180007FDB
0x180007cce  mov     rax, [rbx]
0x180007cd1  lea     rcx, [rbp+4Fh+lpSubKey]
0x180007cd5  mov     [rsp+130h+var_F0], rcx
0x180007cda  mov     [rsp+130h+var_E8], rdi
0x180007cdf  mov     [rsp+130h+var_E0], 1
0x180007ce4  lea     r8, [rsp+130h+var_E8]
0x180007ce9  mov     rdx, [rbp+4Fh+var_78+8]
0x180007ced  mov     rcx, rbx
0x180007cf0  mov     rax, [rax+60h]
0x180007cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf9  mov     [rsp+130h+var_D8], eax
0x180007cfd  cmp     [rsp+130h+var_E0], dil
0x180007d02  jz      short loc_180007D3E
0x180007d04  mov     r13, [rsp+130h+var_E8]
0x180007d09  mov     rsi, [rsp+130h+var_F0]
0x180007d0e  mov     r12, [rsi]
0x180007d11  test    r12, r12
0x180007d14  jz      short loc_180007D35
0x180007d16  call    cs:__imp_GetLastError
0x180007d1c  mov     edi, eax
0x180007d1e  mov     rcx, r12; pv
0x180007d21  call    cs:__imp_CoTaskMemFree
0x180007d27  mov     ecx, edi; dwErrCode
0x180007d29  call    cs:__imp_SetLastError
0x180007d2f  mov     eax, [rsp+130h+var_D8]
0x180007d33  xor     edi, edi
0x180007d35  mov     [rsi], r13
0x180007d38  mov     r12d, 4
0x180007d3e  test    eax, eax
0x180007d40  js      short loc_180007D4F
0x180007d42  mov     rdx, [rbp+4Fh+lpSubKey]
0x180007d46  mov     [rbp+4Fh+lpSubKey], rdi
0x180007d4a  jmp     loc_180007DE1
0x180007d4f  mov     r8d, eax
0x180007d52  lea     rdx, aServicingBranc; "Servicing Branch Build not declared hr "...
0x180007d59  mov     ecx, r12d; unsigned __int8
0x180007d5c  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007d61  mov     rax, [rbx]
0x180007d64  lea     rcx, [rbp+4Fh+var_B0]
0x180007d68  mov     [rsp+130h+var_F0], rcx
0x180007d6d  mov     [rsp+130h+var_E8], rdi
0x180007d72  mov     [rsp+130h+var_E0], 1
0x180007d77  lea     r8, [rsp+130h+var_E8]
0x180007d7c  mov     rdx, [rbp+4Fh+var_78+8]
0x180007d80  mov     rcx, rbx
0x180007d83  mov     rax, [rax+40h]
0x180007d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8c  mov     esi, eax
0x180007d8e  cmp     [rsp+130h+var_E0], dil
0x180007d93  jz      short loc_180007DD1
0x180007d95  mov     rax, [rsp+130h+var_E8]
0x180007d9a  mov     qword ptr [rsp+130h+var_D8], rax
0x180007d9f  mov     r12, [rsp+130h+var_F0]
0x180007da4  mov     r13, [r12]
0x180007da8  test    r13, r13
0x180007dab  jz      short loc_180007DCD
0x180007dad  call    cs:__imp_GetLastError
0x180007db3  mov     edi, eax
0x180007db5  mov     rcx, r13; pv
0x180007db8  call    cs:__imp_CoTaskMemFree
0x180007dbe  mov     ecx, edi; dwErrCode
0x180007dc0  call    cs:__imp_SetLastError
0x180007dc6  mov     rax, qword ptr [rsp+130h+var_D8]
0x180007dcb  xor     edi, edi
0x180007dcd  mov     [r12], rax
0x180007dd1  test    esi, esi
0x180007dd3  js      loc_180008067
0x180007dd9  mov     rdx, [rbp+4Fh+var_B0]
0x180007ddd  mov     [rbp+4Fh+var_B0], rdi
0x180007de1  lea     rcx, [rbp+4Fh+var_A8]
0x180007de5  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180007dea  mov     rax, [rbx]
0x180007ded  lea     rcx, [rsp+130h+pv]
0x180007df2  mov     [rsp+130h+var_F0], rcx
0x180007df7  mov     [rsp+130h+var_E8], rdi
0x180007dfc  mov     [rsp+130h+var_E0], 1
0x180007e01  lea     r12, [r15+6F0h]
0x180007e08  lea     r8, [rsp+130h+var_E8]
0x180007e0d  mov     rdx, r12
0x180007e10  mov     rcx, rbx
0x180007e13  mov     rax, [rax+60h]
0x180007e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e1c  mov     [rsp+130h+var_D8], eax
0x180007e20  cmp     [rsp+130h+var_E0], dil
0x180007e25  jz      short loc_180007E62
0x180007e27  mov     r13, [rsp+130h+var_E8]
0x180007e2c  mov     rsi, [rsp+130h+var_F0]
0x180007e31  mov     r12, [rsi]
0x180007e34  test    r12, r12
0x180007e37  jz      short loc_180007E58
0x180007e39  call    cs:__imp_GetLastError
0x180007e3f  mov     edi, eax
0x180007e41  mov     rcx, r12; pv
0x180007e44  call    cs:__imp_CoTaskMemFree
0x180007e4a  mov     ecx, edi; dwErrCode
0x180007e4c  call    cs:__imp_SetLastError
0x180007e52  mov     eax, [rsp+130h+var_D8]
0x180007e56  xor     edi, edi
0x180007e58  mov     [rsi], r13
0x180007e5b  lea     r12, [r15+6F0h]
0x180007e62  test    eax, eax
0x180007e64  js      short loc_180007EC2
0x180007e66  mov     [rsp+130h+var_D8], edi
0x180007e6a  lea     r8, [rsp+130h+var_D8]; int *
0x180007e6f  mov     rdx, [rsp+130h+pv]; unsigned __int16 *
0x180007e74  mov     rcx, r12; unsigned __int16 *
0x180007e77  call    ?IsOSVersionGreaterThanList@@YAJPEBG0AEAH@Z; IsOSVersionGreaterThanList(ushort const *,ushort const *,int &)
0x180007e7c  mov     esi, eax
0x180007e7e  test    eax, eax
0x180007e80  js      loc_180008067
0x180007e86  cmp     [rsp+130h+var_D8], edi
0x180007e8a  jz      loc_180007FE3
0x180007e90  mov     rsi, [rsp+130h+pv]
0x180007e95  test    rsi, rsi
0x180007e98  jz      short loc_180007EB5
0x180007e9a  call    cs:__imp_GetLastError
0x180007ea0  mov     edi, eax
0x180007ea2  mov     rcx, rsi; pv
0x180007ea5  call    cs:__imp_CoTaskMemFree
0x180007eab  mov     ecx, edi; dwErrCode
0x180007ead  call    cs:__imp_SetLastError
0x180007eb3  xor     edi, edi
0x180007eb5  mov     [rsp+130h+pv], rdi
0x180007eba  mov     rdx, r12
0x180007ebd  jmp     loc_180007F6E
0x180007ec2  mov     r8d, eax
0x180007ec5  lea     rdx, aServicingBranc; "Servicing Branch Build not declared hr "...
0x180007ecc  mov     ecx, 4; unsigned __int8
0x180007ed1  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007ed6  jmp     short loc_180007EBA
0x180007ed8  mov     rax, [rbx]
0x180007edb  lea     rcx, [rbp+4Fh+var_B0]
0x180007edf  mov     [rsp+130h+var_F0], rcx
0x180007ee4  mov     [rsp+130h+var_E8], rdi
0x180007ee9  mov     [rsp+130h+var_E0], 1
0x180007eee  lea     r8, [rsp+130h+var_E8]
0x180007ef3  mov     rdx, [rbp+4Fh+var_78+8]
0x180007ef7  mov     rcx, rbx
0x180007efa  mov     rax, [rax+40h]
0x180007efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f03  mov     esi, eax
0x180007f05  cmp     [rsp+130h+var_E0], dil
0x180007f0a  jz      short loc_180007F48
0x180007f0c  mov     rax, [rsp+130h+var_E8]
0x180007f11  mov     qword ptr [rsp+130h+var_D8], rax
0x180007f16  mov     r12, [rsp+130h+var_F0]
0x180007f1b  mov     r13, [r12]
0x180007f1f  test    r13, r13
0x180007f22  jz      short loc_180007F44
0x180007f24  call    cs:__imp_GetLastError
0x180007f2a  mov     edi, eax
0x180007f2c  mov     rcx, r13; pv
0x180007f2f  call    cs:__imp_CoTaskMemFree
0x180007f35  mov     ecx, edi; dwErrCode
0x180007f37  call    cs:__imp_SetLastError
0x180007f3d  mov     rax, qword ptr [rsp+130h+var_D8]
0x180007f42  xor     edi, edi
0x180007f44  mov     [r12], rax
0x180007f48  test    esi, esi
0x180007f4a  js      loc_180008067
0x180007f50  mov     rdx, [rbp+4Fh+var_B0]
0x180007f54  mov     [rbp+4Fh+var_B0], rdi
0x180007f58  jmp     short loc_180007F5E
0x180007f5a  mov     rdx, [rbp+4Fh+var_78+8]
0x180007f5e  lea     rcx, [rbp+4Fh+var_A8]
0x180007f62  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180007f67  lea     rdx, [r15+6F0h]
0x180007f6e  mov     rax, [rbx]
0x180007f71  lea     rcx, [rsp+130h+pv]
0x180007f76  mov     [rsp+130h+var_F0], rcx
0x180007f7b  mov     [rsp+130h+var_E8], rdi
0x180007f80  mov     [rsp+130h+var_E0], 1
0x180007f85  lea     r8, [rsp+130h+var_E8]
0x180007f8a  mov     rcx, rbx
0x180007f8d  mov     rax, [rax+40h]
0x180007f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f96  cmp     [rsp+130h+var_E0], dil
0x180007f9b  mov     esi, eax
0x180007f9d  jz      short loc_180007FDB
0x180007f9f  mov     r12, [rsp+130h+var_F0]
0x180007fa4  mov     r13, [r12]
0x180007fa8  mov     rax, [rsp+130h+var_E8]
0x180007fad  test    r13, r13
0x180007fb0  mov     qword ptr [rsp+130h+var_D8], rax
0x180007fb5  jz      short loc_180007FD7
0x180007fb7  call    cs:__imp_GetLastError
0x180007fbd  mov     edi, eax
0x180007fbf  mov     rcx, r13; pv
0x180007fc2  call    cs:__imp_CoTaskMemFree
0x180007fc8  mov     ecx, edi; dwErrCode
0x180007fca  call    cs:__imp_SetLastError
0x180007fd0  mov     rax, qword ptr [rsp+130h+var_D8]
0x180007fd5  xor     edi, edi
0x180007fd7  mov     [r12], rax
0x180007fdb  test    esi, esi
0x180007fdd  js      loc_180008067
0x180007fe3  lea     r8, [rbp+4Fh+var_C8]; int *
0x180007fe7  mov     rdx, [rsp+130h+pv]; unsigned __int16 *
0x180007fec  mov     rcx, [rbp+4Fh+var_A8]; unsigned __int16 *
0x180007ff0  call    ?IsOSVersionGreaterThanList@@YAJPEBG0AEAH@Z; IsOSVersionGreaterThanList(ushort const *,ushort const *,int &)
0x180007ff5  mov     esi, eax
0x180007ff7  test    eax, eax
  ... truncated ...
```
