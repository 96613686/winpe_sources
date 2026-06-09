# CScriptAutoDetection::HasOnlyExpectedScripts(wchar_t const *,wchar_t const *)

- ea: `0x18003e790`
- end: `0x18003e90b`
- name: `?HasOnlyExpectedScripts@CScriptAutoDetection@@QEAAJPEB_W0@Z`
- size: `379`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, LPCWSTR pszText, PCWSTR pszFirst)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18003f2b0`

## callees

- `0x180005758`
- `0x18003e790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e7f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e7f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e84b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e84b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003e8c7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003e8c7`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18003e88a`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18003e88a`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18003e8ef`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18003e8ef`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18003e827`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18003e827`

## pseudocode

```c
__int64 __fastcall CScriptAutoDetection::HasOnlyExpectedScripts(
        PMAPPING_SERVICE_INFO *prgServices,
        LPCWSTR pszText,
        PCWSTR pszFirst)
{
  __int64 v3; // rdi
  HRESULT Services; // ebx
  struct _MAPPING_SERVICE_INFO *v9; // rcx
  unsigned int pszInputLanguage; // r8d
  bool v11; // di
  int v12; // esi
  bool v13; // zf
  const WCHAR *v14; // rdx
  PWSTR v15; // rax
  __int128 v16; // [rsp+30h] [rbp-49h] BYREF
  _MAPPING_ENUM_OPTIONS pOptions; // [rsp+40h] [rbp-39h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( pszText[v3] );
  if ( !v3 )
    return 0;
  v16 = xmmword_180095670;
  if ( *((_BYTE *)prgServices + 12) )
    goto LABEL_26;
  Services = 0;
  AcquireSRWLockExclusive(&s_srwElsServiceLock);
  if ( !*((_BYTE *)prgServices + 12) )
  {
    memset_0(&pOptions, 0, sizeof(pOptions));
    pOptions.Size = 80;
    pOptions.pGuid = (GUID *)&v16;
    Services = MappingGetServices(&pOptions, prgServices, (DWORD *)prgServices + 2);
    if ( Services >= 0 )
    {
      if ( *((_DWORD *)prgServices + 2) )
        *((_BYTE *)prgServices + 12) = 1;
      else
        Services = -2147467259;
    }
  }
  ReleaseSRWLockExclusive(&s_srwElsServiceLock);
  if ( Services >= 0 )
  {
LABEL_26:
    memset_0(&pOptions, 0, 0x40u);
    v9 = *prgServices;
    pOptions.Size = 64;
    Services = MappingRecognizeText(v9, pszText, v3, 0, 0, (PMAPPING_PROPERTY_BAG)&pOptions);
    if ( Services >= 0 )
    {
      pszInputLanguage = (unsigned int)pOptions.pszInputLanguage;
      v11 = 0;
      v12 = 0;
      if ( LODWORD(pOptions.pszInputLanguage) )
      {
        while ( 1 )
        {
          v13 = !v11;
          if ( v11 )
            break;
          v14 = *(const WCHAR **)&pOptions.pszCategory[36 * v12 + 12];
          if ( v14 && *v14 )
          {
            v15 = StrStrIW(pszFirst, v14);
            pszInputLanguage = (unsigned int)pOptions.pszInputLanguage;
            v11 = v15 == 0;
          }
          if ( ++v12 >= pszInputLanguage )
          {
            v13 = !v11;
            break;
          }
        }
        if ( !v13 )
          Services = 1;
      }
      MappingFreePropertyBag((PMAPPING_PROPERTY_BAG)&pOptions);
    }
  }
  return (unsigned int)Services;
}

```

## disassembly

```asm
0x18003e790  push    rbp
0x18003e792  push    rbx
0x18003e793  push    rsi
0x18003e794  push    rdi
0x18003e795  push    r12
0x18003e797  push    r13
0x18003e799  push    r14
0x18003e79b  push    r15
0x18003e79d  lea     rbp, [rsp-1Fh]
0x18003e7a2  sub     rsp, 98h
0x18003e7a9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e7ad  mov     r12, r8
0x18003e7b0  xor     r13d, r13d
0x18003e7b3  mov     r14, rdx
0x18003e7b6  mov     rsi, rcx
0x18003e7b9  inc     rdi
0x18003e7bc  cmp     [rdx+rdi*2], r13w
0x18003e7c1  jnz     short loc_18003E7B9
0x18003e7c3  mov     r15d, 1
0x18003e7c9  cmp     rdi, r15
0x18003e7cc  jnb     short loc_18003E7D5
0x18003e7ce  xor     eax, eax
0x18003e7d0  jmp     loc_18003E8F7
0x18003e7d5  movups  xmm0, cs:xmmword_180095670
0x18003e7dc  movdqu  [rbp+57h+var_A0], xmm0
0x18003e7e1  cmp     [rcx+0Ch], r13b
0x18003e7e5  jnz     short loc_18003E859
0x18003e7e7  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003e7ee  mov     ebx, r13d
0x18003e7f1  call    cs:__imp_AcquireSRWLockExclusive
0x18003e7f7  cmp     [rsi+0Ch], r13b
0x18003e7fb  jnz     short loc_18003E844
0x18003e7fd  mov     ebx, 50h ; 'P'
0x18003e802  lea     rcx, [rbp+57h+pOptions]; void *
0x18003e806  mov     r8d, ebx; Size
0x18003e809  xor     edx, edx; Val
0x18003e80b  call    memset_0
0x18003e810  lea     rax, [rbp+57h+var_A0]
0x18003e814  mov     [rbp+57h+pOptions.Size], rbx
0x18003e818  lea     r8, [rsi+8]; pdwServicesCount
0x18003e81c  mov     [rbp+57h+pOptions.pGuid], rax
0x18003e820  mov     rdx, rsi; prgServices
0x18003e823  lea     rcx, [rbp+57h+pOptions]; pOptions
0x18003e827  call    cs:__imp_MappingGetServices
0x18003e82d  mov     ebx, eax
0x18003e82f  test    eax, eax
0x18003e831  js      short loc_18003E844
0x18003e833  cmp     [rsi+8], r13d
0x18003e837  jbe     short loc_18003E83F
0x18003e839  mov     [rsi+0Ch], r15b
0x18003e83d  jmp     short loc_18003E844
0x18003e83f  mov     ebx, 80004005h
0x18003e844  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003e84b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e851  test    ebx, ebx
0x18003e853  js      loc_18003E8F5
0x18003e859  mov     ebx, 40h ; '@'
0x18003e85e  lea     rcx, [rbp+57h+pOptions]; void *
0x18003e862  mov     r8d, ebx; Size
0x18003e865  xor     edx, edx; Val
0x18003e867  call    memset_0
0x18003e86c  mov     rcx, [rsi]; pServiceInfo
0x18003e86f  lea     rax, [rbp+57h+pOptions]
0x18003e873  mov     [rsp+0D0h+pbag], rax; pbag
0x18003e878  mov     r8d, edi; dwLength
0x18003e87b  xor     r9d, r9d; dwIndex
0x18003e87e  mov     [rsp+0D0h+var_B0], r13; pOptions
0x18003e883  mov     rdx, r14; pszText
0x18003e886  mov     [rbp+57h+pOptions.Size], rbx
0x18003e88a  call    cs:__imp_MappingRecognizeText
0x18003e890  mov     ebx, eax
0x18003e892  test    eax, eax
0x18003e894  js      short loc_18003E8F5
0x18003e896  mov     r8d, dword ptr [rbp+57h+pOptions.pszInputLanguage]
0x18003e89a  mov     dil, r13b
0x18003e89d  mov     esi, r13d
0x18003e8a0  test    r8d, r8d
0x18003e8a3  jz      short loc_18003E8EB
0x18003e8a5  test    dil, dil
0x18003e8a8  jnz     short loc_18003E8E7
0x18003e8aa  mov     eax, esi
0x18003e8ac  lea     rcx, [rax+rax*8]
0x18003e8b0  mov     rax, [rbp+57h+pOptions.pszCategory]
0x18003e8b4  mov     rdx, [rax+rcx*8+18h]; pszSrch
0x18003e8b9  test    rdx, rdx
0x18003e8bc  jz      short loc_18003E8DC
0x18003e8be  cmp     [rdx], r13w
0x18003e8c2  jz      short loc_18003E8DC
0x18003e8c4  mov     rcx, r12; pszFirst
0x18003e8c7  call    cs:__imp_StrStrIW
0x18003e8cd  mov     r8d, dword ptr [rbp+57h+pOptions.pszInputLanguage]
0x18003e8d1  test    rax, rax
0x18003e8d4  movzx   edi, dil
0x18003e8d8  cmovz   edi, r15d
0x18003e8dc  add     esi, r15d
0x18003e8df  cmp     esi, r8d
0x18003e8e2  jb      short loc_18003E8A5
0x18003e8e4  test    dil, dil
0x18003e8e7  cmovnz  ebx, r15d
0x18003e8eb  lea     rcx, [rbp+57h+pOptions]; pBag
0x18003e8ef  call    cs:__imp_MappingFreePropertyBag
0x18003e8f5  mov     eax, ebx
0x18003e8f7  add     rsp, 98h
0x18003e8fe  pop     r15
0x18003e900  pop     r14
0x18003e902  pop     r13
0x18003e904  pop     r12
0x18003e906  pop     rdi
0x18003e907  pop     rsi
0x18003e908  pop     rbx
0x18003e909  pop     rbp
0x18003e90a  retn
```
