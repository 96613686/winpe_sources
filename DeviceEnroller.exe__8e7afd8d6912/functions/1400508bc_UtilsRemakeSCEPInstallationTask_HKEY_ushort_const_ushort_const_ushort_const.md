# UtilsRemakeSCEPInstallationTask(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x1400508bc`
- end: `0x140050fd2`
- name: `?UtilsRemakeSCEPInstallationTask@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `1814`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140050fd8`

## callees

- `0x1400042f0`
- `0x140004610`
- `0x140004e28`
- `0x140005c81`
- `0x1400095b4`
- `0x14000a0fc`
- `0x14000a6c4`
- `0x14001e838`
- `0x14001ed14`
- `0x14003d0d0`
- `0x1400508bc`
- `0x140059180`
- `0x14005d010`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserSid` at `0x140050d3e`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x140050d3e`
- `DMCmnUtils!DmRevertToSelf` at `0x140050a04`
- `DMCmnUtils!DmRevertToSelf` at `0x140050b2e`
- `DMCmnUtils!DmRevertToSelf` at `0x140050b69`
- `DMCmnUtils!DmRevertToSelf` at `0x140050bbb`
- `DMCmnUtils!DmRevertToSelf` at `0x140050c03`
- `DMCmnUtils!DmRevertToSelf` at `0x140050cef`
- `DMCmnUtils!DmRevertToSelf` at `0x140050d73`
- `DMCmnUtils!DmRevertToSelf` at `0x140050ddc`
- `DMCmnUtils!DmRevertToSelf` at `0x140050e0b`
- `DMCmnUtils!DmRevertToSelf` at `0x140050a04`
- `DMCmnUtils!DmRevertToSelf` at `0x140050b2e`
- `DMCmnUtils!DmRevertToSelf` at `0x140050b69`
- `DMCmnUtils!DmRevertToSelf` at `0x140050bbb`
- `DMCmnUtils!DmRevertToSelf` at `0x140050c03`
- `DMCmnUtils!DmRevertToSelf` at `0x140050cef`
- `DMCmnUtils!DmRevertToSelf` at `0x140050d73`
- `DMCmnUtils!DmRevertToSelf` at `0x140050ddc`
- `DMCmnUtils!DmRevertToSelf` at `0x140050e0b`
- `DMCmnUtils!DmImpersonate` at `0x1400509bc`
- `DMCmnUtils!DmImpersonate` at `0x140050ca6`
- `DMCmnUtils!DmImpersonate` at `0x1400509bc`
- `DMCmnUtils!DmImpersonate` at `0x140050ca6`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140050a6d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140050a9d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140050a6d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140050a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050d1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050d2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050d2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050a36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050d26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050ed5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050a36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050d26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050ed5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050a0c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050b71`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050bc3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050bdd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050c0b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050cf7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050d7b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050de4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050e13`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050a0c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050b71`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050bc3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050bdd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050c0b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050cf7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050d7b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050de4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140050e13`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UtilsRemakeSCEPInstallationTask(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  _QWORD *v7; // rsi
  char v8; // di
  char v9; // bl
  int v10; // eax
  unsigned int v11; // r14d
  int DWORD; // eax
  int v14; // eax
  const wchar_t *v15; // rax
  int v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  int v21; // ebx
  __int64 v22; // rdx
  char v23; // r14
  char v24; // di
  int v25; // eax
  int CurrentUserSid; // eax
  HRESULT v27; // eax
  int v28; // eax
  __int64 v29; // r8
  HRESULT v30; // eax
  HRESULT v31; // eax
  unsigned __int64 v32; // rdx
  void **v33; // rdi
  __int64 v34; // rbx
  void **v35; // rdx
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v44; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v45; // [rsp+3Ch] [rbp-C4h] BYREF
  char v46; // [rsp+40h] [rbp-C0h]
  char v47; // [rsp+42h] [rbp-BEh]
  HKEY v48; // [rsp+50h] [rbp-B0h]
  _QWORD *v49; // [rsp+58h] [rbp-A8h]
  void *Src[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v51; // [rsp+70h] [rbp-90h]
  unsigned __int64 v52; // [rsp+78h] [rbp-88h]
  unsigned __int16 v53[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v54[30]; // [rsp+90h] [rbp-70h]
  _BYTE v55[2514]; // [rsp+AEh] [rbp-52h] BYREF
  unsigned __int16 v56[2]; // [rsp+A80h] [rbp+980h] BYREF
  _BYTE v57[2556]; // [rsp+A84h] [rbp+984h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+14D8h] [rbp+13D8h]

  v48 = a1;
  *(_OWORD *)v53 = *(_OWORD *)L"-s -k \"%s\" -h %s -t %s";
  *(_OWORD *)v54 = *(_OWORD *)L"s\" -h %s -t %s";
  *(_OWORD *)&v54[14] = *(_OWORD *)L"s -t %s";
  memset_0(v55, 0, 0x9D0u);
  *(_DWORD *)v56 = 0;
  memset_0(v57, 0, 0x9FAu);
  v7 = operator new(0x20u);
  *v7 = &SCEPTaskSchedulerImpl::`vftable';
  v7[1] = 0;
  v7[2] = 0;
  v7[3] = 0;
  v49 = v7;
  v45 = 1;
  v44 = 1;
  hMem = 0;
  *(_OWORD *)Src = 0;
  v51 = 0;
  v52 = 7;
  LOWORD(Src[0]) = 0;
  v8 = 0;
  v46 = 0;
  v9 = 0;
  v47 = 0;
  if ( a4 )
  {
    v10 = DmImpersonate(a4);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC43,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
        (const char *)(unsigned int)v10,
        v36);
LABEL_5:
      std::wstring::~wstring(Src);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 32LL))(v7, 1);
      return v11;
    }
    v8 = 1;
    v46 = 1;
    v9 = 1;
    v47 = 1;
  }
  DWORD = OmaDmRegistryGetDWORD(v48, a2, L"RetryDelay", &v44);
  v11 = DWORD;
  if ( DWORD == -2147024894 )
  {
    v44 = 5;
  }
  else if ( DWORD < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)DWORD,
      v36);
    v18 = 0;
    if ( v8 )
    {
      if ( v9 )
        v18 = DmRevertToSelf();
      else
        v18 = CoRevertToSelf();
    }
    if ( v18 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
        (const char *)(unsigned int)v18,
        v39);
    goto LABEL_5;
  }
  v14 = OmaDmRegistryGetDWORD(v48, a2, L"RetryCount", &v45);
  v11 = v14;
  if ( v14 == -2147024894 )
  {
    v45 = 3;
  }
  else if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC58,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)v14,
      v36);
    v19 = 0;
    if ( v8 )
    {
      if ( v9 )
        v19 = DmRevertToSelf();
      else
        v19 = CoRevertToSelf();
    }
    if ( v19 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
        (const char *)(unsigned int)v19,
        v40);
    goto LABEL_5;
  }
  v15 = L"HKCU";
  if ( !a4 )
    v15 = (const wchar_t *)L"HKLM";
  v16 = StringCchPrintfW(v56, 0x4FFu, v53, a2, v15, a3);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)v16,
      v37);
    v17 = 0;
    if ( v8 )
    {
      if ( v9 )
        v17 = DmRevertToSelf();
      else
        v17 = CoRevertToSelf();
    }
    if ( v17 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
        (const char *)(unsigned int)v17,
        v38);
    goto LABEL_5;
  }
  v20 = 0;
  if ( v8 )
  {
    if ( v9 )
      v20 = DmRevertToSelf();
    else
      v20 = CoRevertToSelf();
  }
  if ( v20 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
      (const char *)(unsigned int)v20,
      v37);
  v21 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 *))*v7)(v7, v56);
  if ( v21 < 0 )
  {
    v22 = 3166;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)v21,
      v37);
LABEL_41:
    std::wstring::~wstring(Src);
    if ( hMem )
      LocalFree(hMem);
    (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 32LL))(v7, 1);
    return (unsigned int)v21;
  }
  v23 = 0;
  v46 = 0;
  v24 = 0;
  v47 = 0;
  if ( a4 )
  {
    v25 = DmImpersonate(a4);
    v21 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC69,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
        (const char *)(unsigned int)v25,
        v37);
      goto LABEL_41;
    }
    v23 = 1;
    v46 = 1;
    v24 = 1;
    v47 = 1;
  }
  hMem = 0;
  CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)&hMem);
  v21 = CurrentUserSid;
  if ( CurrentUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      v37);
    v27 = 0;
    if ( v23 )
    {
      if ( v24 )
        v27 = DmRevertToSelf();
      else
        v27 = CoRevertToSelf();
    }
    if ( v27 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
        (const char *)(unsigned int)v27,
        v41);
    goto LABEL_41;
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v7 + 8LL))(v7, v45, v44);
  v21 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)v28,
      v37);
    v30 = 0;
    if ( v23 )
    {
      if ( v24 )
        v30 = DmRevertToSelf();
      else
        v30 = CoRevertToSelf();
    }
    if ( v30 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
        (const char *)(unsigned int)v30,
        v42);
    goto LABEL_41;
  }
  v31 = 0;
  if ( v23 )
  {
    if ( v24 )
      v31 = DmRevertToSelf();
    else
      v31 = CoRevertToSelf();
  }
  if ( v31 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
      (const char *)(unsigned int)v31,
      v37);
  v32 = -1;
  do
    ++v32;
  while ( a3[v32] );
  if ( v32 > v52 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src, v32, v29, a3);
  }
  else
  {
    v33 = Src;
    if ( v52 > 7 )
      v33 = (void **)Src[0];
    v51 = v32;
    v34 = 2 * v32;
    memmove_0(v33, a3, 2 * v32);
    *(_WORD *)((char *)v33 + v34) = 0;
  }
  std::wstring::append(Src, hMem);
  v35 = Src;
  if ( v52 > 7 )
    v35 = (void **)Src[0];
  v21 = (*(__int64 (__fastcall **)(_QWORD *, void **, HLOCAL, _QWORD))(*v7 + 24LL))(v7, v35, hMem, 0);
  if ( v21 < 0 )
  {
    v22 = 3191;
    goto LABEL_40;
  }
  std::wstring::~wstring(Src);
  if ( hMem )
    LocalFree(hMem);
  (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 32LL))(v7, 1);
  return 0;
}

```

## disassembly

```asm
0x1400508bc  push    rbp
0x1400508be  push    rbx
0x1400508bf  push    rsi
0x1400508c0  push    rdi
0x1400508c1  push    r12
0x1400508c3  push    r13
0x1400508c5  push    r14
0x1400508c7  push    r15
0x1400508c9  lea     rbp, [rsp-1398h]
0x1400508d1  mov     eax, 1498h
0x1400508d6  call    _alloca_probe
0x1400508db  sub     rsp, rax
0x1400508de  mov     rax, cs:__security_cookie
0x1400508e5  xor     rax, rsp
0x1400508e8  mov     [rbp+13D0h+var_50], rax
0x1400508ef  mov     r15, r9
0x1400508f2  mov     r12, r8
0x1400508f5  mov     r13, rdx
0x1400508f8  mov     [rsp+14D0h+var_1480], rcx
0x1400508fd  movups  xmm0, xmmword ptr cs:aSKSHSTS; "-s -k \"%s\" -h %s -t %s"
0x140050904  movaps  xmmword ptr [rbp+13D0h+var_1450], xmm0
0x140050908  movups  xmm1, xmmword ptr cs:aSKSHSTS+10h; "s\" -h %s -t %s"
0x14005090f  movaps  xmmword ptr [rbp+13D0h+var_1440], xmm1
0x140050913  movups  xmm0, xmmword ptr cs:aSKSHSTS+1Eh; "s -t %s"
0x14005091a  movups  xmmword ptr [rbp+13D0h+var_1440+0Eh], xmm0
0x14005091e  xor     edx, edx; Val
0x140050920  mov     r8d, 9D0h; Size
0x140050926  lea     rcx, [rbp+13D0h+var_1422]; void *
0x14005092a  call    memset_0
0x14005092f  xor     r14d, r14d
0x140050932  mov     dword ptr [rbp+13D0h+var_A50], r14d
0x140050939  xor     edx, edx; Val
0x14005093b  mov     r8d, 9FAh; Size
0x140050941  lea     rcx, [rbp+13D0h+var_A4C]; void *
0x140050948  call    memset_0
0x14005094d  lea     ecx, [r14+20h]; Size
0x140050951  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140050956  mov     rsi, rax
0x140050959  lea     rax, ??_7SCEPTaskSchedulerImpl@@6B@; const SCEPTaskSchedulerImpl::`vftable'
0x140050960  mov     [rsi], rax
0x140050963  mov     [rsi+8], r14
0x140050967  mov     [rsi+10h], r14
0x14005096b  mov     [rsi+18h], r14
0x14005096f  mov     [rsp+14D0h+var_1478], rsi
0x140050974  lea     eax, [r14+1]
0x140050978  mov     [rsp+14D0h+var_1494], eax
0x14005097c  mov     [rsp+14D0h+var_1498], eax
0x140050980  mov     [rsp+14D0h+hMem], r14
0x140050985  xorps   xmm0, xmm0
0x140050988  movups  xmmword ptr [rsp+14D0h+Src], xmm0
0x14005098d  mov     [rsp+14D0h+var_1460], r14
0x140050992  mov     [rsp+14D0h+var_1458], 7
0x14005099b  mov     word ptr [rsp+14D0h+Src], r14w
0x1400509a1  mov     dil, r14b
0x1400509a4  mov     [rsp+14D0h+var_1490], r14b
0x1400509a9  mov     bl, r14b
0x1400509ac  mov     [rsp+14D0h+var_148E], bl
0x1400509b0  test    r15, r15
0x1400509b3  jz      loc_140050A59
0x1400509b9  mov     rcx, r15
0x1400509bc  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1400509c2  mov     r14d, eax
0x1400509c5  test    eax, eax
0x1400509c7  js      short loc_1400509D8
0x1400509c9  mov     dil, 1
0x1400509cc  mov     [rsp+14D0h+var_1490], dil
0x1400509d1  mov     bl, dil
0x1400509d4  mov     [rsp+14D0h+var_148E], bl
0x1400509d8  test    r14d, r14d
0x1400509db  jns     short loc_140050A59
0x1400509dd  mov     rcx, [rbp+13D8h]; this
0x1400509e4  mov     r9d, r14d; char *
0x1400509e7  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1400509ee  mov     edx, 0C43h; void *
0x1400509f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400509f8  nop
0x1400509f9  xor     eax, eax
0x1400509fb  test    dil, dil
0x1400509fe  jz      short loc_140050A12
0x140050a00  test    bl, bl
0x140050a02  jz      short loc_140050A0C
0x140050a04  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140050a0a  jmp     short loc_140050A12
0x140050a0c  call    cs:__imp_CoRevertToSelf
0x140050a12  mov     rcx, [rbp+13D8h]; this
0x140050a19  test    eax, eax
0x140050a1b  js      loc_140050FA8
0x140050a21  lea     rcx, [rsp+14D0h+Src]
0x140050a26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050a2b  nop
0x140050a2c  mov     rcx, [rsp+14D0h+hMem]; hMem
0x140050a31  test    rcx, rcx
0x140050a34  jz      short loc_140050A3D
0x140050a36  call    cs:__imp_LocalFree
0x140050a3c  nop
0x140050a3d  mov     rax, [rsi]
0x140050a40  mov     edx, 1
0x140050a45  mov     rcx, rsi
0x140050a48  mov     rax, [rax+20h]
0x140050a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050a51  mov     eax, r14d
0x140050a54  jmp     loc_140050EF2
0x140050a59  lea     r9, [rsp+14D0h+var_1498]
0x140050a5e  lea     r8, aRetrydelay_0; "RetryDelay"
0x140050a65  mov     rdx, r13
0x140050a68  mov     rcx, [rsp+14D0h+var_1480]
0x140050a6d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140050a73  mov     r14d, eax
0x140050a76  cmp     eax, 80070002h
0x140050a7b  jnz     loc_140050B39
0x140050a81  mov     [rsp+14D0h+var_1498], 5
0x140050a89  lea     r9, [rsp+14D0h+var_1494]
0x140050a8e  lea     r8, aRetrycount_0; "RetryCount"
0x140050a95  mov     rdx, r13
0x140050a98  mov     rcx, [rsp+14D0h+var_1480]
0x140050a9d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140050aa3  mov     r14d, eax
0x140050aa6  cmp     eax, 80070002h
0x140050aab  jnz     loc_140050B8B
0x140050ab1  mov     [rsp+14D0h+var_1494], 3
0x140050ab9  lea     rcx, aHklm; "HKLM"
0x140050ac0  lea     rax, aHkcu; "HKCU"
0x140050ac7  test    r15, r15
0x140050aca  cmovz   rax, rcx
0x140050ace  mov     [rsp+14D0h+var_14A8], r12
0x140050ad3  mov     qword ptr [rsp+14D0h+var_14B0], rax; int
0x140050ad8  mov     r9, r13
0x140050adb  lea     r8, [rbp+13D0h+var_1450]; unsigned __int16 *
0x140050adf  mov     edx, 4FFh; unsigned __int64
0x140050ae4  lea     rcx, [rbp+13D0h+var_A50]; unsigned __int16 *
0x140050aeb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140050af0  mov     r14d, eax
0x140050af3  xor     r13d, r13d
0x140050af6  test    eax, eax
0x140050af8  jns     loc_140050BF7
0x140050afe  mov     rcx, [rbp+13D8h]; this
0x140050b05  mov     r9d, eax; char *
0x140050b08  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140050b0f  mov     edx, 0C5Ah; void *
0x140050b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140050b19  nop
0x140050b1a  mov     eax, r13d
0x140050b1d  test    dil, dil
0x140050b20  jz      loc_140050BE3
0x140050b26  test    bl, bl
0x140050b28  jz      loc_140050BDD
0x140050b2e  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140050b34  jmp     loc_140050BE3
0x140050b39  test    r14d, r14d
0x140050b3c  jns     loc_140050A89
0x140050b42  mov     rcx, [rbp+13D8h]; this
0x140050b49  mov     r9d, r14d; char *
0x140050b4c  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140050b53  mov     edx, 0C4Eh; void *
0x140050b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140050b5d  nop
0x140050b5e  xor     eax, eax
0x140050b60  test    dil, dil
0x140050b63  jz      short loc_140050B77
0x140050b65  test    bl, bl
0x140050b67  jz      short loc_140050B71
0x140050b69  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140050b6f  jmp     short loc_140050B77
0x140050b71  call    cs:__imp_CoRevertToSelf
0x140050b77  mov     rcx, [rbp+13D8h]; this
0x140050b7e  test    eax, eax
0x140050b80  js      loc_140050F2A
0x140050b86  jmp     loc_140050A21
0x140050b8b  test    r14d, r14d
0x140050b8e  jns     loc_140050AB9
0x140050b94  mov     rcx, [rbp+13D8h]; this
0x140050b9b  mov     r9d, r14d; char *
0x140050b9e  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140050ba5  mov     edx, 0C58h; void *
0x140050baa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140050baf  nop
0x140050bb0  xor     eax, eax
0x140050bb2  test    dil, dil
0x140050bb5  jz      short loc_140050BC9
0x140050bb7  test    bl, bl
0x140050bb9  jz      short loc_140050BC3
0x140050bbb  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140050bc1  jmp     short loc_140050BC9
0x140050bc3  call    cs:__imp_CoRevertToSelf
0x140050bc9  mov     rcx, [rbp+13D8h]; this
0x140050bd0  test    eax, eax
0x140050bd2  js      loc_140050F3F
0x140050bd8  jmp     loc_140050A21
0x140050bdd  call    cs:__imp_CoRevertToSelf
0x140050be3  mov     rcx, [rbp+13D8h]; this
0x140050bea  test    eax, eax
0x140050bec  js      loc_140050F54
0x140050bf2  jmp     loc_140050A21
0x140050bf7  mov     eax, r13d
0x140050bfa  test    dil, dil
0x140050bfd  jz      short loc_140050C11
0x140050bff  test    bl, bl
0x140050c01  jz      short loc_140050C0B
0x140050c03  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140050c09  jmp     short loc_140050C11
0x140050c0b  call    cs:__imp_CoRevertToSelf
0x140050c11  mov     rcx, [rbp+13D8h]; this
0x140050c18  test    eax, eax
0x140050c1a  js      loc_140050FBD
0x140050c20  mov     rax, [rsi]
0x140050c23  lea     rdx, [rbp+13D0h+var_A50]
0x140050c2a  mov     rcx, rsi
0x140050c2d  mov     rax, [rax]
0x140050c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050c35  mov     ebx, eax
0x140050c37  test    eax, eax
0x140050c39  jns     short loc_140050C8E
0x140050c3b  mov     edx, 0C5Eh; void *
0x140050c40  mov     r9d, ebx; char *
0x140050c43  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140050c4a  mov     rcx, [rbp+13D8h]; this
0x140050c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140050c56  nop
0x140050c57  lea     rcx, [rsp+14D0h+Src]
0x140050c5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050c61  nop
0x140050c62  mov     rcx, [rsp+14D0h+hMem]; hMem
0x140050c67  test    rcx, rcx
0x140050c6a  jz      short loc_140050C73
0x140050c6c  call    cs:__imp_LocalFree
0x140050c72  nop
0x140050c73  mov     rax, [rsi]
0x140050c76  mov     edx, 1
0x140050c7b  mov     rcx, rsi
0x140050c7e  mov     rax, [rax+20h]
0x140050c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050c87  mov     eax, ebx
0x140050c89  jmp     loc_140050EF2
0x140050c8e  mov     r14b, r13b
0x140050c91  mov     [rsp+14D0h+var_1490], r13b
0x140050c96  mov     dil, r13b
0x140050c99  mov     [rsp+14D0h+var_148E], r13b
0x140050c9e  test    r15, r15
0x140050ca1  jz      short loc_140050D11
0x140050ca3  mov     rcx, r15
0x140050ca6  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x140050cac  mov     ebx, eax
0x140050cae  test    eax, eax
0x140050cb0  js      short loc_140050CC2
0x140050cb2  mov     r14b, 1
0x140050cb5  mov     [rsp+14D0h+var_1490], r14b
0x140050cba  mov     dil, r14b
0x140050cbd  mov     [rsp+14D0h+var_148E], r14b
0x140050cc2  test    ebx, ebx
0x140050cc4  jns     short loc_140050D11
0x140050cc6  mov     rcx, [rbp+13D8h]; this
0x140050ccd  mov     r9d, ebx; char *
0x140050cd0  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140050cd7  mov     edx, 0C69h; void *
0x140050cdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140050ce1  nop
0x140050ce2  mov     eax, r13d
0x140050ce5  test    r14b, r14b
0x140050ce8  jz      short loc_140050CFD
0x140050cea  test    dil, dil
0x140050ced  jz      short loc_140050CF7
0x140050cef  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140050cf5  jmp     short loc_140050CFD
0x140050cf7  call    cs:__imp_CoRevertToSelf
0x140050cfd  mov     rcx, [rbp+13D8h]; this
0x140050d04  test    eax, eax
0x140050d06  js      loc_140050F69
0x140050d0c  jmp     loc_140050C57
0x140050d11  mov     r15, [rsp+14D0h+hMem]
0x140050d16  test    r15, r15
0x140050d19  jz      short loc_140050D34
0x140050d1b  call    cs:__imp_GetLastError
0x140050d21  mov     ebx, eax
0x140050d23  mov     rcx, r15; hMem
0x140050d26  call    cs:__imp_LocalFree
0x140050d2c  mov     ecx, ebx; dwErrCode
0x140050d2e  call    cs:__imp_SetLastError
0x140050d34  mov     [rsp+14D0h+hMem], r13
0x140050d39  lea     rcx, [rsp+14D0h+hMem]
0x140050d3e  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x140050d44  mov     ebx, eax
0x140050d46  test    eax, eax
0x140050d48  jns     short loc_140050D95
0x140050d4a  mov     rcx, [rbp+13D8h]; this
0x140050d51  mov     r9d, eax; char *
0x140050d54  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x140050d5b  mov     edx, 0C6Bh; void *
0x140050d60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140050d65  nop
0x140050d66  mov     eax, r13d
0x140050d69  test    r14b, r14b
0x140050d6c  jz      short loc_140050D81
0x140050d6e  test    dil, dil
0x140050d71  jz      short loc_140050D7B
0x140050d73  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x140050d79  jmp     short loc_140050D81
0x140050d7b  call    cs:__imp_CoRevertToSelf
0x140050d81  mov     rcx, [rbp+13D8h]; this
0x140050d88  test    eax, eax
0x140050d8a  js      loc_140050F7E
  ... truncated ...
```
