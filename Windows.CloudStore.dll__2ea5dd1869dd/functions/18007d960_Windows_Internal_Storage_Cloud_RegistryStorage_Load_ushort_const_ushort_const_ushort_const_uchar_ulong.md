# Windows::Internal::Storage::Cloud::RegistryStorage::Load(ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x18007d960`
- end: `0x18007e05d`
- name: `?Load@RegistryStorage@Cloud@Storage@Internal@Windows@@UEAAJPEBG00PEAPEAEPEAK@Z`
- size: `1789`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::RegistryStorage *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18003f6c4`
- `0x18007d960`
- `0x18007e064`
- `0x1800c8458`
- `0x1800ff298`
- `0x1801201a0`
- `0x180120c94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dd6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dd6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ddc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007de63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ddc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007de63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007dd80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007de9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007dd80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007de9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007de2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007deee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dfd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007de2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007deee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007dfd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007dead`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007dead`

## string_xrefs

- `0x18007dac4`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x18007dadf`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x18007dafa`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x18007db10`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x18007dfb1`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x18007dfeb`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`
- `0x18007e03f`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Storage::Cloud::RegistryStorage::Load(
        HKEY *this,
        WCHAR *a2,
        WCHAR *a3,
        WCHAR *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  __int64 v10; // rdi
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  __int64 v13; // r8
  WCHAR *v14; // r9
  wchar_t v15; // r10
  unsigned int v16; // ebx
  WCHAR *v17; // rcx
  __int64 v18; // r8
  WCHAR *v19; // rax
  __int64 v20; // r9
  __int64 v21; // rax
  bool v22; // zf
  __int64 v23; // r8
  WCHAR *v24; // r9
  WCHAR v25; // cx
  WCHAR *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  WCHAR *v31; // rcx
  __int64 v32; // r8
  WCHAR *v33; // rax
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // r8
  WCHAR *v37; // r9
  WCHAR v38; // cx
  WCHAR *v39; // rcx
  __int64 v40; // r8
  WCHAR *v41; // rax
  __int64 v42; // r9
  __int64 v43; // rax
  __int64 v44; // r8
  WCHAR *v45; // r9
  WCHAR v46; // cx
  const WCHAR *v47; // r11
  WCHAR *v48; // rcx
  __int64 v49; // r8
  WCHAR *v50; // rax
  __int64 v51; // r9
  __int64 v52; // rdx
  WCHAR *v53; // r8
  WCHAR v54; // ax
  WCHAR *v55; // rcx
  unsigned int v56; // eax
  void *v57; // r8
  unsigned int v58; // eax
  void *v59; // rbx
  int v60; // edi
  HKEY v61; // rax
  size_t v62; // rax
  WCHAR *v63; // rax
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 v66; // rax
  const WCHAR *v67; // rcx
  __int64 v68; // r8
  WCHAR *v69; // r10
  WCHAR v70; // r9
  void *v71; // rcx
  void *v72; // rcx
  __int64 v73; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey[4]; // [rsp+40h] [rbp-C0h] BYREF
  char v80; // [rsp+60h] [rbp-A0h]
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  *a6 = 0;
  *a5 = 0;
  v10 = 2147483646;
  v11 = 2147483646;
  v12 = L"Store\\";
  v13 = 260;
  v14 = SubKey;
  do
  {
    if ( !v11 )
      break;
    v15 = *v12;
    if ( !*v12 )
      break;
    ++v12;
    *v14++ = v15;
    --v11;
    --v13;
  }
  while ( v13 );
  v16 = v13 == 0 ? 0x8007007A : 0;
  v17 = v14 - 1;
  if ( v13 )
    v17 = v14;
  *v17 = 0;
  if ( !v13 )
  {
    v27 = 170;
    goto LABEL_20;
  }
  v18 = 260;
  v19 = SubKey;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v16 = v18 == 0 ? 0x80070057 : 0;
  v20 = (260 - v18) & -(__int64)(v18 != 0);
  if ( !v18 )
    goto LABEL_19;
  v21 = 2147483646;
  v23 = 260 - v20;
  v22 = v20 == 260;
  v24 = &SubKey[v20];
  if ( !v22 )
  {
    do
    {
      if ( !v21 )
        break;
      v25 = *a3;
      if ( !*a3 )
        break;
      ++a3;
      *v24++ = v25;
      --v21;
      --v23;
    }
    while ( v23 );
  }
  v16 = v23 == 0 ? 0x8007007A : 0;
  v26 = v24 - 1;
  if ( v23 )
    v26 = v24;
  *v26 = 0;
  if ( !v23 )
  {
LABEL_19:
    v27 = 171;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
      (const char *)v16,
      phkResult);
    v28 = 160;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
      (const char *)v16,
      phkResult);
    v29 = 150;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
      (const char *)v16,
      phkResult);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
      (const char *)v16,
      phkResultb);
    return v16;
  }
  v64 = 260;
  v63 = SubKey;
  do
  {
    if ( !*v63 )
      break;
    ++v63;
    --v64;
  }
  while ( v64 );
  v16 = v64 == 0 ? 0x80070057 : 0;
  v65 = (260 - v64) & -(__int64)(v64 != 0);
  if ( !v64 )
    goto LABEL_93;
  v66 = 2147483646;
  v47 = L"\\";
  v67 = L"\\";
  v68 = 260 - v65;
  v69 = &SubKey[v65];
  if ( v65 != 260 )
  {
    do
    {
      if ( !v66 )
        break;
      v70 = *v67;
      if ( !*v67 )
        break;
      ++v67;
      *v69++ = v70;
      --v66;
      --v68;
    }
    while ( v68 );
  }
  v16 = v68 == 0 ? 0x8007007A : 0;
  v31 = v69 - 1;
  if ( v68 )
    v31 = v69;
  *v31 = 0;
  if ( !v68 )
  {
LABEL_93:
    v28 = 161;
    goto LABEL_21;
  }
  v32 = 260;
  v33 = SubKey;
  do
  {
    if ( !*v33 )
      break;
    ++v33;
    --v32;
  }
  while ( v32 );
  v16 = v32 == 0 ? 0x80070057 : 0;
  v34 = (260 - v32) & -(__int64)(v32 != 0);
  if ( !v32 )
    goto LABEL_38;
  v35 = 2147483646;
  v36 = 260 - v34;
  v22 = v34 == 260;
  v37 = &SubKey[v34];
  if ( !v22 )
  {
    do
    {
      if ( !v35 )
        break;
      v38 = *a2;
      if ( !*a2 )
        break;
      ++a2;
      *v37++ = v38;
      --v35;
      --v36;
    }
    while ( v36 );
  }
  v16 = v36 == 0 ? 0x8007007A : 0;
  v39 = v37 - 1;
  if ( v36 )
    v39 = v37;
  *v39 = 0;
  if ( !v36 )
  {
LABEL_38:
    v28 = 162;
    goto LABEL_21;
  }
  v40 = 260;
  v41 = SubKey;
  do
  {
    if ( !*v41 )
      break;
    ++v41;
    --v40;
  }
  while ( v40 );
  v16 = v40 == 0 ? 0x80070057 : 0;
  v42 = (260 - v40) & -(__int64)(v40 != 0);
  if ( !v40 )
    goto LABEL_62;
  v43 = 2147483646;
  v44 = 260 - v42;
  v22 = v42 == 260;
  v45 = &SubKey[v42];
  if ( !v22 )
  {
    do
    {
      if ( !v43 )
        break;
      v46 = *v47;
      if ( !*v47 )
        break;
      ++v47;
      *v45++ = v46;
      --v43;
      --v44;
    }
    while ( v44 );
  }
  v16 = v44 == 0 ? 0x8007007A : 0;
  v48 = v45 - 1;
  if ( v44 )
    v48 = v45;
  *v48 = 0;
  if ( !v44 )
  {
LABEL_62:
    v29 = 151;
    goto LABEL_22;
  }
  v49 = 260;
  v50 = SubKey;
  do
  {
    if ( !*v50 )
      break;
    ++v50;
    --v49;
  }
  while ( v49 );
  v16 = v49 == 0 ? 0x80070057 : 0;
  v51 = (260 - v49) & -(__int64)(v49 != 0);
  if ( !v49 )
    goto LABEL_61;
  v52 = 260 - v51;
  v53 = &SubKey[v51];
  if ( 260 != v51 )
  {
    do
    {
      if ( !v10 )
        break;
      v54 = *a4;
      if ( !*a4 )
        break;
      ++a4;
      *v53++ = v54;
      --v10;
      --v52;
    }
    while ( v52 );
  }
  v16 = v52 == 0 ? 0x8007007A : 0;
  v55 = v53 - 1;
  if ( v52 )
    v55 = v53;
  *v55 = 0;
  if ( !v52 )
  {
LABEL_61:
    v29 = 152;
    goto LABEL_22;
  }
  hKey[0] = 0;
  v56 = RegOpenKeyExW(this[2], SubKey, 0, 1u, hKey);
  if ( v56 == 2 || v56 == 1018 )
    goto LABEL_64;
  if ( v56 )
  {
    v73 = 58;
LABEL_112:
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v73,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
            (const char *)v56,
            phkResulta);
LABEL_95:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return v16;
  }
  cbData = 0;
  v56 = RegQueryValueExW(hKey[0], L"Data", 0, 0, 0, &cbData);
  if ( v56 == 2 || v56 == 1018 )
  {
LABEL_64:
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return 2147942402LL;
  }
  if ( v56 )
  {
    v73 = 61;
    goto LABEL_112;
  }
  v57 = 0;
  pv = 0;
  v58 = 234;
  while ( v58 == 234 )
  {
    hKey[2] = (HKEY)&pv;
    v80 = 1;
    v59 = 0;
    if ( is_mul_ok(cbData, 1u) )
    {
      v61 = (HKEY)CoTaskMemAlloc(cbData);
      v59 = v61;
      hKey[3] = v61;
      if ( v61 )
      {
        v62 = CTCoAllocPolicy::_CoTaskMemSize(v61);
        memset_0(v59, 0, v62);
        v60 = 0;
      }
      else
      {
        v60 = -2147024882;
      }
      v57 = pv;
    }
    else
    {
      v60 = -2147024362;
    }
    pv = v59;
    if ( v57 )
    {
      CoTaskMemFree(v57);
      v59 = pv;
    }
    if ( v60 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
        (const char *)(unsigned int)v60,
        phkResulta);
      v71 = pv;
      pv = 0;
      if ( v71 )
        CoTaskMemFree(v71);
      v16 = v60;
      goto LABEL_95;
    }
    v58 = RegQueryValueExW(hKey[0], L"Data", 0, 0, (LPBYTE)v59, &cbData);
    v57 = pv;
  }
  if ( v58 == 2 || v58 == 1018 )
  {
    pv = 0;
    if ( v57 )
      CoTaskMemFree(v57);
    v16 = -2147024894;
    goto LABEL_95;
  }
  if ( v58 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x47,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
            (const char *)v58,
            phkResulta);
    v72 = pv;
    pv = 0;
    if ( v72 )
      CoTaskMemFree(v72);
    goto LABEL_95;
  }
  *a6 = cbData;
  *a5 = (unsigned __int8 *)v57;
  pv = 0;
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return 0;
}

```

## disassembly

```asm
0x18007d960  push    rbp
0x18007d962  push    rbx
0x18007d963  push    rsi
0x18007d964  push    rdi
0x18007d965  push    r12
0x18007d967  push    r13
0x18007d969  push    r14
0x18007d96b  push    r15
0x18007d96d  lea     rbp, [rsp-198h]
0x18007d975  sub     rsp, 298h
0x18007d97c  mov     rax, cs:__security_cookie
0x18007d983  xor     rax, rsp
0x18007d986  mov     [rbp+1D0h+var_50], rax
0x18007d98d  mov     r14, r9
0x18007d990  mov     r11, r8
0x18007d993  mov     rsi, rdx
0x18007d996  mov     r15, rcx
0x18007d999  mov     r12, [rbp+1D0h+arg_20]
0x18007d9a0  mov     r13, [rbp+1D0h+arg_28]
0x18007d9a7  xor     r10d, r10d
0x18007d9aa  mov     [r13+0], r10d
0x18007d9ae  mov     [r12], r10
0x18007d9b2  mov     edi, 7FFFFFFEh
0x18007d9b7  mov     eax, edi
0x18007d9b9  lea     rcx, aStore_0; "Store\\"
0x18007d9c0  mov     edx, 104h
0x18007d9c5  mov     r8d, edx
0x18007d9c8  lea     r9, [rsp+2D0h+SubKey]
0x18007d9cd  test    rax, rax
0x18007d9d0  jz      short loc_18007D9F9
0x18007d9d2  movzx   r10d, word ptr [rcx]
0x18007d9d6  test    r10w, r10w
0x18007d9da  jz      short loc_18007D9F6
0x18007d9dc  add     rcx, 2
0x18007d9e0  mov     [r9], r10w
0x18007d9e4  add     r9, 2
0x18007d9e8  dec     rax
0x18007d9eb  xor     r10d, r10d
0x18007d9ee  sub     r8, 1
0x18007d9f2  jnz     short loc_18007D9CD
0x18007d9f4  jmp     short loc_18007D9F9
0x18007d9f6  xor     r10d, r10d
0x18007d9f9  mov     rax, r8
0x18007d9fc  neg     rax
0x18007d9ff  sbb     ebx, ebx
0x18007da01  not     ebx
0x18007da03  and     ebx, 8007007Ah
0x18007da09  lea     rcx, [r9-2]
0x18007da0d  test    r8, r8
0x18007da10  cmovnz  rcx, r9
0x18007da14  mov     [rcx], r10w
0x18007da18  jz      loc_18007E01C
0x18007da1e  mov     r8, rdx
0x18007da21  lea     rax, [rsp+2D0h+SubKey]
0x18007da26  cmp     [rax], r10w
0x18007da2a  jz      short loc_18007DA36
0x18007da2c  add     rax, 2
0x18007da30  sub     r8, 1
0x18007da34  jnz     short loc_18007DA26
0x18007da36  mov     rax, r8
0x18007da39  neg     rax
0x18007da3c  sbb     ebx, ebx
0x18007da3e  not     ebx
0x18007da40  and     ebx, 80070057h
0x18007da46  mov     rax, r8
0x18007da49  mov     rcx, rdx
0x18007da4c  sub     rcx, r8
0x18007da4f  neg     rax
0x18007da52  sbb     r9, r9
0x18007da55  and     r9, rcx
0x18007da58  test    r8, r8
0x18007da5b  jz      short loc_18007DAB5
0x18007da5d  mov     rax, rdi
0x18007da60  mov     r8, rdx
0x18007da63  sub     r8, r9
0x18007da66  lea     r9, [rsp+r9*2+2D0h+SubKey]
0x18007da6b  jz      short loc_18007DA90
0x18007da6d  test    rax, rax
0x18007da70  jz      short loc_18007DA90
0x18007da72  movzx   ecx, word ptr [r11]
0x18007da76  test    cx, cx
0x18007da79  jz      short loc_18007DA90
0x18007da7b  add     r11, 2
0x18007da7f  mov     [r9], cx
0x18007da83  add     r9, 2
0x18007da87  dec     rax
0x18007da8a  sub     r8, 1
0x18007da8e  jnz     short loc_18007DA6D
0x18007da90  mov     rax, r8
0x18007da93  neg     rax
0x18007da96  sbb     ebx, ebx
0x18007da98  not     ebx
0x18007da9a  and     ebx, 8007007Ah
0x18007daa0  lea     rcx, [r9-2]
0x18007daa4  test    r8, r8
0x18007daa7  cmovnz  rcx, r9
0x18007daab  mov     [rcx], r10w
0x18007daaf  jnz     loc_18007E026
0x18007dab5  mov     edx, 0ABh; void *
0x18007daba  mov     r9d, ebx; char *
0x18007dabd  mov     rcx, [rbp+1D8h]; this
0x18007dac4  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007dacb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dad0  mov     edx, 0A0h; void *
0x18007dad5  mov     rcx, [rbp+1D8h]; this
0x18007dadc  mov     r9d, ebx; char *
0x18007dadf  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007dae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007daeb  mov     edx, 96h; void *
0x18007daf0  mov     rcx, [rbp+1D8h]; this
0x18007daf7  mov     r9d, ebx; char *
0x18007dafa  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007db01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007db06  mov     rcx, [rbp+1D8h]; this
0x18007db0d  mov     r9d, ebx; char *
0x18007db10  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007db17  mov     edx, 37h ; '7'; void *
0x18007db1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007db21  mov     eax, ebx
0x18007db23  mov     rcx, [rbp+1D0h+var_50]
0x18007db2a  xor     rcx, rsp; StackCookie
0x18007db2d  call    __security_check_cookie
0x18007db32  add     rsp, 298h
0x18007db39  pop     r15
0x18007db3b  pop     r14
0x18007db3d  pop     r13
0x18007db3f  pop     r12
0x18007db41  pop     rdi
0x18007db42  pop     rsi
0x18007db43  pop     rbx
0x18007db44  pop     rbp
0x18007db45  retn
0x18007db46  mov     rax, r8
0x18007db49  neg     rax
0x18007db4c  sbb     ebx, ebx
0x18007db4e  not     ebx
0x18007db50  and     ebx, 8007007Ah
0x18007db56  lea     rcx, [r10-2]
0x18007db5a  test    r8, r8
0x18007db5d  cmovnz  rcx, r10
0x18007db61  xor     r10d, r10d
0x18007db64  mov     [rcx], r10w
0x18007db68  test    r8, r8
0x18007db6b  jz      loc_18007DF02
0x18007db71  mov     r8, rdx
0x18007db74  lea     rax, [rsp+2D0h+SubKey]
0x18007db79  cmp     [rax], r10w
0x18007db7d  jz      short loc_18007DB89
0x18007db7f  add     rax, 2
0x18007db83  sub     r8, 1
0x18007db87  jnz     short loc_18007DB79
0x18007db89  mov     rax, r8
0x18007db8c  neg     rax
0x18007db8f  sbb     ebx, ebx
0x18007db91  not     ebx
0x18007db93  and     ebx, 80070057h
0x18007db99  mov     rax, r8
0x18007db9c  mov     rcx, rdx
0x18007db9f  sub     rcx, r8
0x18007dba2  neg     rax
0x18007dba5  sbb     r9, r9
0x18007dba8  and     r9, rcx
0x18007dbab  test    r8, r8
0x18007dbae  jz      short loc_18007DC04
0x18007dbb0  mov     rax, rdi
0x18007dbb3  mov     r8, rdx
0x18007dbb6  sub     r8, r9
0x18007dbb9  lea     r9, [rsp+r9*2+2D0h+SubKey]
0x18007dbbe  jz      short loc_18007DBE2
0x18007dbc0  test    rax, rax
0x18007dbc3  jz      short loc_18007DBE2
0x18007dbc5  movzx   ecx, word ptr [rsi]
0x18007dbc8  test    cx, cx
0x18007dbcb  jz      short loc_18007DBE2
0x18007dbcd  add     rsi, 2
0x18007dbd1  mov     [r9], cx
0x18007dbd5  add     r9, 2
0x18007dbd9  dec     rax
0x18007dbdc  sub     r8, 1
0x18007dbe0  jnz     short loc_18007DBC0
0x18007dbe2  mov     rax, r8
0x18007dbe5  neg     rax
0x18007dbe8  sbb     ebx, ebx
0x18007dbea  not     ebx
0x18007dbec  and     ebx, 8007007Ah
0x18007dbf2  lea     rcx, [r9-2]
0x18007dbf6  xor     esi, esi
0x18007dbf8  test    r8, r8
0x18007dbfb  cmovnz  rcx, r9
0x18007dbff  mov     [rcx], si
0x18007dc02  jnz     short loc_18007DC0E
0x18007dc04  mov     edx, 0A2h
0x18007dc09  jmp     loc_18007DAD5
0x18007dc0e  mov     r8, rdx
0x18007dc11  lea     rax, [rsp+2D0h+SubKey]
0x18007dc16  cmp     [rax], si
0x18007dc19  jz      short loc_18007DC25
0x18007dc1b  add     rax, 2
0x18007dc1f  sub     r8, 1
0x18007dc23  jnz     short loc_18007DC16
0x18007dc25  mov     rax, r8
0x18007dc28  neg     rax
0x18007dc2b  sbb     ebx, ebx
0x18007dc2d  not     ebx
0x18007dc2f  mov     r10d, 80070057h
0x18007dc35  and     ebx, r10d
0x18007dc38  mov     rax, r8
0x18007dc3b  mov     rcx, rdx
0x18007dc3e  sub     rcx, r8
0x18007dc41  neg     rax
0x18007dc44  sbb     r9, r9
0x18007dc47  and     r9, rcx
0x18007dc4a  test    r8, r8
0x18007dc4d  jz      loc_18007DD40
0x18007dc53  mov     rax, rdi
0x18007dc56  mov     r8, rdx
0x18007dc59  sub     r8, r9
0x18007dc5c  lea     r9, [rsp+r9*2+2D0h+SubKey]
0x18007dc61  jz      short loc_18007DC86
0x18007dc63  test    rax, rax
0x18007dc66  jz      short loc_18007DC86
0x18007dc68  movzx   ecx, word ptr [r11]
0x18007dc6c  test    cx, cx
0x18007dc6f  jz      short loc_18007DC86
0x18007dc71  add     r11, 2
0x18007dc75  mov     [r9], cx
0x18007dc79  add     r9, 2
0x18007dc7d  dec     rax
0x18007dc80  sub     r8, 1
0x18007dc84  jnz     short loc_18007DC63
0x18007dc86  mov     rax, r8
0x18007dc89  neg     rax
0x18007dc8c  sbb     ebx, ebx
0x18007dc8e  not     ebx
0x18007dc90  mov     r11d, 8007007Ah
0x18007dc96  and     ebx, r11d
0x18007dc99  lea     rcx, [r9-2]
0x18007dc9d  test    r8, r8
0x18007dca0  cmovnz  rcx, r9
0x18007dca4  mov     [rcx], si
0x18007dca7  jz      loc_18007DD40
0x18007dcad  mov     r8, rdx
0x18007dcb0  lea     rax, [rsp+2D0h+SubKey]
0x18007dcb5  cmp     [rax], si
0x18007dcb8  jz      short loc_18007DCC4
0x18007dcba  add     rax, 2
0x18007dcbe  sub     r8, 1
0x18007dcc2  jnz     short loc_18007DCB5
0x18007dcc4  mov     rax, r8
0x18007dcc7  neg     rax
0x18007dcca  sbb     ebx, ebx
0x18007dccc  not     ebx
0x18007dcce  and     ebx, r10d
0x18007dcd1  mov     rax, r8
0x18007dcd4  mov     rcx, rdx
0x18007dcd7  sub     rcx, r8
0x18007dcda  neg     rax
0x18007dcdd  sbb     r9, r9
0x18007dce0  and     r9, rcx
0x18007dce3  test    r8, r8
0x18007dce6  jz      short loc_18007DD36
0x18007dce8  sub     rdx, r9
0x18007dceb  lea     r8, [rsp+2D0h+SubKey]
0x18007dcf0  lea     r8, [r8+r9*2]
0x18007dcf4  jz      short loc_18007DD19
0x18007dcf6  test    rdi, rdi
0x18007dcf9  jz      short loc_18007DD19
0x18007dcfb  movzx   eax, word ptr [r14]
0x18007dcff  test    ax, ax
0x18007dd02  jz      short loc_18007DD19
0x18007dd04  add     r14, 2
0x18007dd08  mov     [r8], ax
0x18007dd0c  add     r8, 2
0x18007dd10  dec     rdi
0x18007dd13  sub     rdx, 1
0x18007dd17  jnz     short loc_18007DCF6
0x18007dd19  mov     rax, rdx
0x18007dd1c  neg     rax
0x18007dd1f  sbb     ebx, ebx
0x18007dd21  not     ebx
0x18007dd23  and     ebx, r11d
0x18007dd26  lea     rcx, [r8-2]
0x18007dd2a  test    rdx, rdx
0x18007dd2d  cmovnz  rcx, r8
0x18007dd31  mov     [rcx], si
0x18007dd34  jnz     short loc_18007DD4A
0x18007dd36  mov     edx, 98h
0x18007dd3b  jmp     loc_18007DAF0
0x18007dd40  mov     edx, 97h
0x18007dd45  jmp     loc_18007DAF0
0x18007dd4a  mov     [rsp+2D0h+hKey], rsi
0x18007dd4f  lea     rax, [rsp+2D0h+hKey]
0x18007dd54  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007dd59  mov     r9d, 1; samDesired
0x18007dd5f  xor     r8d, r8d; ulOptions
0x18007dd62  lea     rdx, [rsp+2D0h+SubKey]; lpSubKey
0x18007dd67  mov     rcx, [r15+10h]; hKey
0x18007dd6b  call    cs:__imp_RegOpenKeyExW
0x18007dd71  cmp     eax, 2
0x18007dd74  jnz     short loc_18007DD90
  ... truncated ...
```
