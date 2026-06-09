# PCPStorageProvider::SetProperty(KspProp,uchar *,ulong,ulong)

- ea: `0x180021310`
- end: `0x180021955`
- name: `?SetProperty@PCPStorageProvider@@QEAAJW4KspProp@@PEAEKK@Z`
- size: `1605`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18001ffe0`
- `0x180080328`

## callees

- `0x180012640`
- `0x180015660`
- `0x1800157c0`
- `0x18001bb00`
- `0x180021310`
- `0x18002195c`
- `0x1800389c0`
- `0x1800764d0`
- `0x1800768a0`
- `0x180076998`
- `0x180076fca`
- `0x180077034`
- `0x18007704c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800214b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180021534`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800214b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180021534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002154b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002165e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002154b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002165e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002190c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002190c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021613`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021613`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800214d7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800214d7`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002188b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002188b`
- `CRYPT32!CertOpenStore` at `0x18002164a`
- `CRYPT32!CertOpenStore` at `0x18002164a`
- `CRYPT32!CertCreateCertificateContext` at `0x1800217df`
- `CRYPT32!CertCreateCertificateContext` at `0x1800217df`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18002168d`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18002168d`
- `CRYPT32!CertFreeCertificateContext` at `0x180021925`
- `CRYPT32!CertFreeCertificateContext` at `0x180021925`
- `CRYPT32!CertCloseStore` at `0x18002193b`
- `CRYPT32!CertCloseStore` at `0x18002193b`
- `TpmCoreProvisioning!TpmCertCheckEkCertMatchedEkPub` at `0x180021833`
- `TpmCoreProvisioning!TpmCertCheckEkCertMatchedEkPub` at `0x180021833`

## string_xrefs

- `0x1800217b9`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStoreECC`
- `0x1800216d2`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PCPStorageProvider::SetProperty(__int64 a1, int a2, const unsigned __int8 *a3, unsigned int a4)
{
  rsize_t v4; // rdi
  int v8; // r12d
  PCCERT_CONTEXT CertificateContext; // r13
  HCERTSTORE v10; // r15
  const struct std::nothrow_t *v11; // rdx
  size_t v12; // rsi
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rcx
  unsigned __int64 v15; // rdi
  void *v16; // rax
  void *v17; // rcx
  unsigned int v18; // ebx
  const char *v19; // r9
  __int64 result; // rax
  signed int LastError; // eax
  signed int v22; // eax
  void *v23; // rdi
  int v24; // ecx
  int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  signed int v27; // eax
  signed int v28; // eax
  void *v29; // rcx
  void *v30; // rax
  const wchar_t *v31; // rsi
  int PersistedStateLocation; // eax
  int KeyStorageLocation; // [rsp+50h] [rbp-4A8h] BYREF
  unsigned int v34[3]; // [rsp+54h] [rbp-4A4h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-498h] BYREF
  const wchar_t *v36; // [rsp+68h] [rbp-490h]
  _BYTE v37[32]; // [rsp+70h] [rbp-488h] BYREF
  WCHAR PathName; // [rsp+90h] [rbp-468h] BYREF
  _BYTE v39[526]; // [rsp+92h] [rbp-466h] BYREF
  WCHAR SubKey[264]; // [rsp+2A0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+0h]

  v4 = a4;
  v8 = 0;
  KeyStorageLocation = 0;
  KspFunctionLogger::KspFunctionLogger(
    (KspFunctionLogger *)v37,
    L"PCPStorageProvider::SetProperty",
    &KeyStorageLocation);
  PathName = 0;
  memset_0(v39, 0, 0x206u);
  CertificateContext = 0;
  v34[0] = 0;
  hKey = 0;
  v10 = 0;
  memset_0(SubKey, 0, 0x208u);
  try
  {
    v34[1] = 520;
    if ( a2 == 35 )
    {
      v12 = (unsigned int)v4;
      KspLoggingProvider::LogAlternateKeyStorageLocationProperty((struct PCPStorageProvider *)a1, a3, (unsigned int)v4);
      v14 = *(void **)(a1 + 128);
      if ( v14 )
      {
        operator delete(v14, v13);
        *(_QWORD *)(a1 + 128) = 0;
      }
      if ( !(_DWORD)v4 )
        goto LABEL_12;
      v15 = v4 + 2;
      v16 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)(a1 + 128) = v16;
      if ( v16 )
      {
        memset_0(v16, 0, v15);
        v17 = *(void **)(a1 + 128);
        if ( !v17 )
          goto LABEL_19;
        if ( a3 && v15 >= v12 )
        {
          memcpy_0(v17, a3, v12);
LABEL_11:
          KeyStorageLocation = PCPStorageProvider::GetKeyStorageLocation((PCPStorageProvider *)a1, 0, 0, 0, &PathName);
          if ( KeyStorageLocation >= 0 && !CreateDirectoryW(&PathName, 0) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            KeyStorageLocation = LastError;
            if ( LastError == -2147024713 )
              KeyStorageLocation = 0;
          }
          goto LABEL_12;
        }
        memset_0(v17, 0, v15);
        if ( a3 )
        {
          if ( v15 >= v12 )
            goto LABEL_11;
          *(_DWORD *)_o__errno() = 34;
        }
        else
        {
LABEL_19:
          *(_DWORD *)_o__errno() = 22;
        }
        invalid_parameter_noinfo();
        goto LABEL_11;
      }
      KeyStorageLocation = -2147024888;
LABEL_12:
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      if ( CertificateContext )
        CertFreeCertificateContext(CertificateContext);
      if ( v10 )
        CertCloseStore(v10, 0);
      goto LABEL_18;
    }
    if ( a2 == 38 )
    {
      v31 = L"TPMCoreProvisioningEKCertificatesECC";
      v36 = L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStoreECC";
      v8 = 1;
    }
    else
    {
      v36 = L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStore";
      if ( a2 != 41 && a2 != 70 )
      {
        if ( a2 == 75 )
        {
          if ( (_DWORD)v4 == 16 )
          {
            memcpy_s_1((void *const)(a1 + 144), 0x10u, a3, 0x10u);
            *(_DWORD *)(a1 + 160) = 0;
            goto LABEL_12;
          }
          KeyStorageLocation = -2146893785;
        }
        else
        {
          if ( a2 == 94 )
          {
            v29 = *(void **)(a1 + 96);
            if ( v29 )
            {
              operator delete(v29, v11);
              *(_QWORD *)(a1 + 96) = 0;
            }
            if ( (_DWORD)v4 )
            {
              v30 = operator new[](v4 + 2, (const struct std::nothrow_t *)&std::nothrow);
              *(_QWORD *)(a1 + 96) = v30;
              if ( v30 )
              {
                memset_0(v30, 0, v4 + 2);
                memcpy_s_1(*(void *const *)(a1 + 96), v4 + 2, a3, v4);
              }
              else
              {
                KeyStorageLocation = -2147024888;
              }
            }
            goto LABEL_12;
          }
          KeyStorageLocation = -2146893783;
        }
LABEL_18:
        v18 = KeyStorageLocation;
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v37);
        return v18;
      }
      v31 = L"TPMCoreProvisioningEKCertificates";
    }
    CertificateContext = CertCreateCertificateContext(0x10001u, a3, v4);
    if ( !CertificateContext )
    {
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      KeyStorageLocation = v22;
      if ( v22 < 0 )
        goto LABEL_12;
    }
    v23 = 0;
    if ( !v8 )
    {
      KeyStorageLocation = PCPStorageProvider::GetProperty(a1, 43, 0, 0, v34);
      if ( KeyStorageLocation < 0 )
        goto LABEL_12;
      v23 = operator new[](v34[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( !v23 )
      {
        KeyStorageLocation = -2147024888;
        goto LABEL_12;
      }
      KeyStorageLocation = PCPStorageProvider::GetProperty(a1, 43, v23, v34[0], v34);
      if ( KeyStorageLocation < 0 )
      {
LABEL_73:
        operator delete(v23, v26);
        goto LABEL_12;
      }
      KeyStorageLocation = TpmCertCheckEkCertMatchedEkPub(
                             CertificateContext->pbCertEncoded,
                             CertificateContext->cbCertEncoded,
                             (unsigned __int8 *)v23,
                             v34[0]);
      if ( KeyStorageLocation < 0 )
      {
        KeyStorageLocation = -2146893803;
        goto LABEL_73;
      }
    }
    PersistedStateLocation = RtlGetPersistedStateLocation(v31, 0, v36, 0);
    if ( PersistedStateLocation )
    {
      if ( (PersistedStateLocation & 0xFFFF000) == 0x290000 )
      {
        v24 = PersistedStateLocation & 0xFFF | 0x80280000;
      }
      else if ( (PersistedStateLocation & 0xFFF0000) == 0x70000 )
      {
        v24 = (unsigned __int16)PersistedStateLocation;
        if ( (_WORD)PersistedStateLocation )
          v24 = (unsigned __int16)PersistedStateLocation | 0x80070000;
      }
      else
      {
        v24 = PersistedStateLocation | 0x10000000;
      }
      KeyStorageLocation = v24;
      if ( v24 < 0 )
      {
LABEL_46:
        if ( !v23 )
          goto LABEL_12;
        goto LABEL_73;
      }
    }
    else
    {
      KeyStorageLocation = 0;
    }
    v25 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v25 > 0 )
      v25 = (unsigned __int16)v25 | 0x80070000;
    KeyStorageLocation = v25;
    if ( v25 >= 0 )
    {
      v10 = CertOpenStore((LPCSTR)4, 0, 0, 0, hKey);
      if ( v10 )
        goto LABEL_45;
      v27 = GetLastError();
      if ( v27 > 0 )
        v27 = (unsigned __int16)v27 | 0x80070000;
      KeyStorageLocation = v27;
      if ( v27 >= 0 )
      {
LABEL_45:
        if ( !CertAddCertificateContextToStore(v10, CertificateContext, 4u, 0) )
        {
          v28 = GetLastError();
          if ( v28 > 0 )
            v28 = (unsigned __int16)v28 | 0x80070000;
          KeyStorageLocation = v28;
        }
      }
    }
    goto LABEL_46;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x625,
                           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x180021310  push    rbx
0x180021312  push    rsi
0x180021313  push    rdi
0x180021314  push    r12
0x180021316  push    r13
0x180021318  push    r14
0x18002131a  push    r15
0x18002131c  sub     rsp, 4C0h
0x180021323  mov     rax, cs:__security_cookie
0x18002132a  xor     rax, rsp
0x18002132d  mov     [rsp+4F8h+var_48], rax
0x180021335  mov     edi, r9d
0x180021338  mov     r14, r8
0x18002133b  mov     esi, edx
0x18002133d  mov     rbx, rcx
0x180021340  xor     r12d, r12d
0x180021343  mov     [rsp+4F8h+var_4A8], r12d
0x180021348  lea     r8, [rsp+4F8h+var_4A8]; int *
0x18002134d  lea     rdx, aPcpstorageprov_3; "PCPStorageProvider::SetProperty"
0x180021354  lea     rcx, [rsp+4F8h+var_488]; this
0x180021359  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18002135e  nop
0x18002135f  mov     [rsp+4F8h+PathName], r12w
0x180021368  xor     edx, edx; Val
0x18002136a  mov     r8d, 206h; Size
0x180021370  lea     rcx, [rsp+4F8h+var_466]; void *
0x180021378  call    memset_0
0x18002137d  mov     r13d, r12d
0x180021380  mov     [rsp+4F8h+var_4A4], r12d
0x180021385  mov     [rsp+4F8h+hKey], r12
0x18002138a  mov     r15d, r12d
0x18002138d  xor     edx, edx; Val
0x18002138f  mov     r8d, 208h; Size
0x180021395  lea     rcx, [rsp+4F8h+SubKey]; void *
0x18002139d  call    memset_0
0x1800213a2  mov     [rsp+4F8h+var_4A4+4], 208h
0x1800213aa  cmp     esi, 23h ; '#'
0x1800213ad  jnz     loc_1800216C9
0x1800213b3  mov     esi, edi
0x1800213b5  mov     r8d, edi; unsigned __int64
0x1800213b8  mov     rdx, r14; unsigned __int8 *
0x1800213bb  mov     rcx, rbx; struct PCPStorageProvider *
0x1800213be  call    ?LogAlternateKeyStorageLocationProperty@KspLoggingProvider@@SAXPEAVPCPStorageProvider@@PEBE_K@Z; KspLoggingProvider::LogAlternateKeyStorageLocationProperty(PCPStorageProvider *,uchar const *,unsigned __int64)
0x1800213c3  mov     rcx, [rbx+80h]; void *
0x1800213ca  test    rcx, rcx
0x1800213cd  jnz     loc_1800218EE
0x1800213d3  test    edi, edi
0x1800213d5  jz      loc_18002145D
0x1800213db  add     rdi, 2
0x1800213df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800213e6  mov     rcx, rdi; unsigned __int64
0x1800213e9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800213ee  mov     [rbx+80h], rax
0x1800213f5  test    rax, rax
0x1800213f8  jz      loc_1800218FF
0x1800213fe  mov     r8, rdi; Size
0x180021401  xor     edx, edx; Val
0x180021403  mov     rcx, rax; void *
0x180021406  call    memset_0
0x18002140b  mov     rcx, [rbx+80h]; void *
0x180021412  test    rcx, rcx
0x180021415  jz      loc_1800214B1
0x18002141b  test    r14, r14
0x18002141e  jz      loc_18002151C
0x180021424  cmp     rdi, rsi
0x180021427  jb      loc_18002151C
0x18002142d  mov     r8, rsi; Size
0x180021430  mov     rdx, r14; Src
0x180021433  call    memcpy_0
0x180021438  lea     rax, [rsp+4F8h+PathName]
0x180021440  mov     qword ptr [rsp+4F8h+dwOptions], rax; pszDest
0x180021445  xor     r9d, r9d; unsigned __int8
0x180021448  xor     r8d, r8d; unsigned __int8
0x18002144b  xor     edx, edx; unsigned __int8
0x18002144d  mov     rcx, rbx; this
0x180021450  call    ?GetKeyStorageLocation@PCPStorageProvider@@QEAAJEEEPEAG@Z; PCPStorageProvider::GetKeyStorageLocation(uchar,uchar,uchar,ushort *)
0x180021455  mov     [rsp+4F8h+var_4A8], eax
0x180021459  test    eax, eax
0x18002145b  jns     short loc_1800214CD
0x18002145d  mov     rcx, [rsp+4F8h+hKey]; hKey
0x180021462  test    rcx, rcx
0x180021465  jnz     loc_18002190C
0x18002146b  test    r13, r13
0x18002146e  jnz     loc_180021922
0x180021474  test    r15, r15
0x180021477  jnz     loc_180021936
0x18002147d  mov     ebx, [rsp+4F8h+var_4A8]
0x180021481  lea     rcx, [rsp+4F8h+var_488]; this
0x180021486  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002148b  mov     eax, ebx
0x18002148d  mov     rcx, [rsp+4F8h+var_48]
0x180021495  xor     rcx, rsp; StackCookie
0x180021498  call    __security_check_cookie
0x18002149d  add     rsp, 4C0h
0x1800214a4  pop     r15
0x1800214a6  pop     r14
0x1800214a8  pop     r13
0x1800214aa  pop     r12
0x1800214ac  pop     rdi
0x1800214ad  pop     rsi
0x1800214ae  pop     rbx
0x1800214af  retn
0x1800214b1  call    cs:__imp__o__errno
0x1800214b8  nop     dword ptr [rax+rax+00h]
0x1800214bd  mov     dword ptr [rax], 16h
0x1800214c3  call    _invalid_parameter_noinfo
0x1800214c8  jmp     loc_180021438
0x1800214cd  xor     edx, edx; lpSecurityAttributes
0x1800214cf  lea     rcx, [rsp+4F8h+PathName]; lpPathName
0x1800214d7  call    cs:__imp_CreateDirectoryW
0x1800214de  nop     dword ptr [rax+rax+00h]
0x1800214e3  test    eax, eax
0x1800214e5  jnz     loc_18002145D
0x1800214eb  call    cs:__imp_GetLastError
0x1800214f2  nop     dword ptr [rax+rax+00h]
0x1800214f7  test    eax, eax
0x1800214f9  jle     short loc_180021503
0x1800214fb  movzx   eax, ax
0x1800214fe  or      eax, 80070000h
0x180021503  mov     [rsp+4F8h+var_4A8], eax
0x180021507  cmp     eax, 800700B7h
0x18002150c  jnz     loc_18002145D
0x180021512  mov     [rsp+4F8h+var_4A8], r12d
0x180021517  jmp     loc_18002145D
0x18002151c  mov     r8, rdi; Size
0x18002151f  xor     edx, edx; Val
0x180021521  call    memset_0
0x180021526  test    r14, r14
0x180021529  jz      short loc_1800214B1
0x18002152b  cmp     rdi, rsi
0x18002152e  jnb     loc_180021438
0x180021534  call    cs:__imp__o__errno
0x18002153b  nop     dword ptr [rax+rax+00h]
0x180021540  mov     dword ptr [rax], 22h ; '"'
0x180021546  jmp     loc_1800214C3
0x18002154b  call    cs:__imp_GetLastError
0x180021552  nop     dword ptr [rax+rax+00h]
0x180021557  test    eax, eax
0x180021559  jle     short loc_180021563
0x18002155b  movzx   eax, ax
0x18002155e  or      eax, 80070000h
0x180021563  mov     [rsp+4F8h+var_4A8], eax
0x180021567  test    eax, eax
0x180021569  js      short loc_1800215BF
0x18002156b  xor     edi, edi
0x18002156d  test    r12d, r12d
0x180021570  jnz     loc_18002185F
0x180021576  lea     rax, [rsp+4F8h+var_4A4]
0x18002157b  mov     qword ptr [rsp+4F8h+dwOptions], rax
0x180021580  xor     r9d, r9d
0x180021583  xor     r8d, r8d
0x180021586  mov     edx, 2Bh ; '+'
0x18002158b  mov     rcx, rbx
0x18002158e  call    ?GetProperty@PCPStorageProvider@@QEAAJW4KspProp@@PEAEKPEAKK@Z; PCPStorageProvider::GetProperty(KspProp,uchar *,ulong,ulong *,ulong)
0x180021593  mov     [rsp+4F8h+var_4A8], eax
0x180021597  test    eax, eax
0x180021599  js      short loc_1800215BF
0x18002159b  mov     ecx, [rsp+4F8h+var_4A4]; unsigned __int64
0x18002159f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800215a6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800215ab  mov     rdi, rax
0x1800215ae  test    rax, rax
0x1800215b1  jnz     loc_1800217FC
0x1800215b7  mov     [rsp+4F8h+var_4A8], 80070008h
0x1800215bf  xor     r12d, r12d
0x1800215c2  jmp     loc_18002145D
0x1800215c7  movzx   ecx, cx
0x1800215ca  test    ecx, ecx
0x1800215cc  jz      loc_1800218DA
0x1800215d2  or      ecx, 80070000h
0x1800215d8  jmp     loc_1800218DA
0x1800215dd  mov     [rsp+4F8h+lpdwDisposition], r12; lpdwDisposition
0x1800215e2  lea     rax, [rsp+4F8h+hKey]
0x1800215e7  mov     [rsp+4F8h+phkResult], rax; phkResult
0x1800215ec  mov     [rsp+4F8h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800215f1  mov     [rsp+4F8h+samDesired], 0F003Fh; samDesired
0x1800215f9  mov     [rsp+4F8h+dwOptions], r12d; dwOptions
0x1800215fe  xor     r9d, r9d; lpClass
0x180021601  xor     r8d, r8d; Reserved
0x180021604  lea     rdx, [rsp+4F8h+SubKey]; lpSubKey
0x18002160c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021613  call    cs:__imp_RegCreateKeyExW
0x18002161a  nop     dword ptr [rax+rax+00h]
0x18002161f  test    eax, eax
0x180021621  jle     short loc_18002162B
0x180021623  movzx   eax, ax
0x180021626  or      eax, 80070000h
0x18002162b  mov     [rsp+4F8h+var_4A8], eax
0x18002162f  test    eax, eax
0x180021631  js      short loc_18002169D
0x180021633  mov     rax, [rsp+4F8h+hKey]
0x180021638  mov     qword ptr [rsp+4F8h+dwOptions], rax; pvPara
0x18002163d  xor     r9d, r9d; dwFlags
0x180021640  xor     r8d, r8d; hCryptProv
0x180021643  xor     edx, edx; dwEncodingType
0x180021645  mov     ecx, 4; lpszStoreProvider
0x18002164a  call    cs:__imp_CertOpenStore
0x180021651  nop     dword ptr [rax+rax+00h]
0x180021656  mov     r15, rax
0x180021659  test    rax, rax
0x18002165c  jnz     short loc_18002167E
0x18002165e  call    cs:__imp_GetLastError
0x180021665  nop     dword ptr [rax+rax+00h]
0x18002166a  test    eax, eax
0x18002166c  jle     short loc_180021676
0x18002166e  movzx   eax, ax
0x180021671  or      eax, 80070000h
0x180021676  mov     [rsp+4F8h+var_4A8], eax
0x18002167a  test    eax, eax
0x18002167c  js      short loc_18002169D
0x18002167e  xor     r9d, r9d; ppStoreContext
0x180021681  mov     r8d, 4; dwAddDisposition
0x180021687  mov     rdx, r13; pCertContext
0x18002168a  mov     rcx, r15; hCertStore
0x18002168d  call    cs:__imp_CertAddCertificateContextToStore
0x180021694  nop     dword ptr [rax+rax+00h]
0x180021699  test    eax, eax
0x18002169b  jz      short loc_1800216AB
0x18002169d  test    rdi, rdi
0x1800216a0  jz      loc_18002145D
0x1800216a6  jmp     loc_180021852
0x1800216ab  call    cs:__imp_GetLastError
0x1800216b2  nop     dword ptr [rax+rax+00h]
0x1800216b7  test    eax, eax
0x1800216b9  jle     short loc_1800216C3
0x1800216bb  movzx   eax, ax
0x1800216be  or      eax, 80070000h
0x1800216c3  mov     [rsp+4F8h+var_4A8], eax
0x1800216c7  jmp     short loc_18002169D
0x1800216c9  cmp     esi, 26h ; '&'
0x1800216cc  jz      loc_1800217B2
0x1800216d2  lea     rax, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\TP"...
0x1800216d9  mov     [rsp+4F8h+var_490], rax
0x1800216de  cmp     esi, 29h ; ')'
0x1800216e1  jz      loc_1800217CD
0x1800216e7  cmp     esi, 46h ; 'F'
0x1800216ea  jz      loc_1800217CD
0x1800216f0  cmp     esi, 4Bh ; 'K'
0x1800216f3  jz      loc_180021779
0x1800216f9  cmp     esi, 5Eh ; '^'
0x1800216fc  jz      short loc_18002170B
0x1800216fe  mov     [rsp+4F8h+var_4A8], 80090029h
0x180021706  jmp     loc_18002147D
0x18002170b  mov     rcx, [rbx+60h]; void *
0x18002170f  test    rcx, rcx
0x180021712  jz      short loc_180021722
0x180021714  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021719  xor     r12d, r12d
0x18002171c  mov     [rbx+60h], r12
0x180021720  jmp     short loc_180021725
0x180021722  xor     r12d, r12d
0x180021725  test    edi, edi
0x180021727  jz      loc_18002145D
0x18002172d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021734  lea     rcx, [rdi+2]; unsigned __int64
0x180021738  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002173d  mov     [rbx+60h], rax
0x180021741  test    rax, rax
0x180021744  jnz     short loc_180021753
0x180021746  mov     [rsp+4F8h+var_4A8], 80070008h
0x18002174e  jmp     loc_18002145D
0x180021753  lea     r8, [rdi+2]; Size
0x180021757  xor     edx, edx; Val
0x180021759  mov     rcx, rax; void *
0x18002175c  call    memset_0
0x180021761  mov     r9, rdi; SourceSize
0x180021764  mov     r8, r14; Source
0x180021767  lea     rdx, [rdi+2]; DestinationSize
0x18002176b  mov     rcx, [rbx+60h]; Destination
0x18002176f  call    memcpy_s_1
0x180021774  jmp     loc_18002145D
0x180021779  cmp     edi, 10h
0x18002177c  jz      short loc_18002178B
0x18002177e  mov     [rsp+4F8h+var_4A8], 80090027h
0x180021786  jmp     loc_18002147D
0x18002178b  lea     rcx, [rbx+90h]; Destination
0x180021792  mov     r9d, 10h; SourceSize
0x180021798  mov     r8, r14; Source
0x18002179b  mov     edx, r9d; DestinationSize
0x18002179e  call    memcpy_s_1
0x1800217a3  xor     r12d, r12d
0x1800217a6  mov     [rbx+0A0h], r12d
0x1800217ad  jmp     loc_18002145D
0x1800217b2  lea     rsi, aTpmcoreprovisi_1; "TPMCoreProvisioningEKCertificatesECC"
0x1800217b9  lea     rax, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\TP"...
0x1800217c0  mov     [rsp+4F8h+var_490], rax
0x1800217c5  mov     r12d, 1
0x1800217cb  jmp     short loc_1800217D4
0x1800217cd  lea     rsi, aTpmcoreprovisi_2; "TPMCoreProvisioningEKCertificates"
0x1800217d4  mov     r8d, edi; cbCertEncoded
0x1800217d7  mov     rdx, r14; pbCertEncoded
0x1800217da  mov     ecx, 10001h; dwCertEncodingType
0x1800217df  call    cs:__imp_CertCreateCertificateContext
0x1800217e6  nop     dword ptr [rax+rax+00h]
0x1800217eb  mov     r13, rax
0x1800217ee  test    rax, rax
0x1800217f1  jnz     loc_18002156B
0x1800217f7  jmp     loc_18002154B
0x1800217fc  lea     rax, [rsp+4F8h+var_4A4]
0x180021801  mov     qword ptr [rsp+4F8h+dwOptions], rax
  ... truncated ...
```
