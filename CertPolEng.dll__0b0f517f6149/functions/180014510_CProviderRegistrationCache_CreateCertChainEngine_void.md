# CProviderRegistrationCache::CreateCertChainEngine(void)

- ea: `0x180014510`
- end: `0x180014652`
- name: `?CreateCertChainEngine@CProviderRegistrationCache@@AEAAKXZ`
- size: `322`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800043d0`

## callees

- `0x180003dc0`
- `0x180007ea0`
- `0x180014510`
- `0x18001a342`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145bb`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18001462e`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18001462e`
- `CRYPT32!CertAddStoreToCollection` at `0x1800145f1`
- `CRYPT32!CertAddStoreToCollection` at `0x1800145f1`
- `CRYPT32!CertOpenStore` at `0x1800145a9`
- `CRYPT32!CertOpenStore` at `0x1800145a9`
- `CRYPT32!CertCloseStore` at `0x180014580`
- `CRYPT32!CertCloseStore` at `0x180014580`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180014565`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180014565`

## string_xrefs

- `0x18001453b`: `CProviderRegistrationCache::CreateCertChainEngine`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::CreateCertChainEngine(
        CProviderRegistrationCache *this,
        __int64 a2,
        int *a3)
{
  void *v4; // rcx
  void *v5; // rcx
  HCERTSTORE v6; // rax
  __int64 v7; // rdx
  unsigned int LastError; // ebx
  __int64 i; // rdi
  _BYTE v11[32]; // [rsp+30h] [rbp-49h] BYREF
  struct _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v13; // [rsp+E0h] [rbp+67h] BYREF

  v13 = 0;
  CLogETWBlock::CLogETWBlock((CLogETWBlock *)v11, "CProviderRegistrationCache::CreateCertChainEngine", a3, 0, &v13);
  memset_0(&pConfig, 0, 0x58u);
  v4 = (void *)*((_QWORD *)this + 17);
  if ( v4 )
  {
    CertFreeCertificateChainEngine(v4);
    *((_QWORD *)this + 17) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 23);
  if ( v5 )
  {
    CertCloseStore(v5, 0);
    *((_QWORD *)this + 23) = 0;
  }
  v6 = CertOpenStore((LPCSTR)0xB, 0x10001u, 0, 0, 0);
  *((_QWORD *)this + 23) = v6;
  if ( !v6 )
    goto LABEL_6;
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 38); i = (unsigned int)(i + 1) )
  {
    if ( !CertAddStoreToCollection(
            *((HCERTSTORE *)this + 23),
            *(HCERTSTORE *)(*(_QWORD *)(*((_QWORD *)this + 18) + 8 * i) + 2104LL),
            0,
            0) )
      goto LABEL_6;
  }
  memset_0(&pConfig, 0, 0x58u);
  pConfig.hExclusiveRoot = (HCERTSTORE)*((_QWORD *)this + 23);
  pConfig.cbSize = 88;
  pConfig.dwFlags = 1;
  if ( CertCreateCertificateChainEngine(&pConfig, (HCERTCHAINENGINE *)this + 17) )
  {
    LastError = v13;
  }
  else
  {
LABEL_6:
    LastError = GetLastError();
    v13 = LastError;
  }
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v11, v7);
  return LastError;
}

```

## disassembly

```asm
0x180014510  push    rbp
0x180014512  push    rbx
0x180014513  push    rsi
0x180014514  push    rdi
0x180014515  lea     rbp, [rsp-3Fh]
0x18001451a  sub     rsp, 0B8h
0x180014521  mov     rbx, rcx
0x180014524  mov     [rbp+57h+arg_0], 0
0x18001452b  lea     rax, [rbp+57h+arg_0]
0x18001452f  xor     r9d, r9d; int *
0x180014532  lea     rcx, [rbp+57h+var_A0]; this
0x180014536  mov     [rsp+0D0h+pvPara], rax; unsigned int *
0x18001453b  lea     rdx, aCproviderregis_16; "CProviderRegistrationCache::CreateCertC"...
0x180014542  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x180014547  xor     edx, edx; Val
0x180014549  lea     rcx, [rbp+57h+pConfig]; void *
0x18001454d  lea     r8d, [rdx+58h]; Size
0x180014551  call    memset_0
0x180014556  lea     rsi, [rbx+88h]
0x18001455d  mov     rcx, [rsi]; hChainEngine
0x180014560  test    rcx, rcx
0x180014563  jz      short loc_180014572
0x180014565  call    cs:__imp_CertFreeCertificateChainEngine
0x18001456b  mov     qword ptr [rsi], 0
0x180014572  mov     rcx, [rbx+0B8h]; hCertStore
0x180014579  test    rcx, rcx
0x18001457c  jz      short loc_180014591
0x18001457e  xor     edx, edx; dwFlags
0x180014580  call    cs:__imp_CertCloseStore
0x180014586  mov     qword ptr [rbx+0B8h], 0
0x180014591  xor     r9d, r9d; dwFlags
0x180014594  mov     [rsp+0D0h+pvPara], 0; pvPara
0x18001459d  xor     r8d, r8d; hCryptProv
0x1800145a0  mov     edx, 10001h; dwEncodingType
0x1800145a5  lea     ecx, [r9+0Bh]; lpszStoreProvider
0x1800145a9  call    cs:__imp_CertOpenStore
0x1800145af  mov     [rbx+0B8h], rax
0x1800145b6  test    rax, rax
0x1800145b9  jnz     short loc_1800145C8
0x1800145bb  call    cs:__imp_GetLastError
0x1800145c1  mov     ebx, eax
0x1800145c3  mov     [rbp+57h+arg_0], eax
0x1800145c6  jmp     short loc_18001463B
0x1800145c8  xor     edi, edi
0x1800145ca  cmp     edi, [rbx+98h]
0x1800145d0  jnb     short loc_1800145FF
0x1800145d2  mov     rax, [rbx+90h]
0x1800145d9  xor     r9d, r9d; dwPriority
0x1800145dc  mov     rcx, [rbx+0B8h]; hCollectionStore
0x1800145e3  xor     r8d, r8d; dwUpdateFlags
0x1800145e6  mov     rdx, [rax+rdi*8]
0x1800145ea  mov     rdx, [rdx+838h]; hSiblingStore
0x1800145f1  call    cs:__imp_CertAddStoreToCollection
0x1800145f7  test    eax, eax
0x1800145f9  jz      short loc_1800145BB
0x1800145fb  inc     edi
0x1800145fd  jmp     short loc_1800145CA
0x1800145ff  xor     edx, edx; Val
0x180014601  lea     rcx, [rbp+57h+pConfig]; void *
0x180014605  lea     r8d, [rdx+58h]; Size
0x180014609  call    memset_0
0x18001460e  mov     rax, [rbx+0B8h]
0x180014615  lea     rcx, [rbp+57h+pConfig]; pConfig
0x180014619  mov     rdx, rsi; phChainEngine
0x18001461c  mov     [rbp+57h+pConfig.hExclusiveRoot], rax
0x180014620  mov     [rbp+57h+pConfig.cbSize], 58h ; 'X'
0x180014627  mov     [rbp+57h+pConfig.dwFlags], 1
0x18001462e  call    cs:__imp_CertCreateCertificateChainEngine
0x180014634  test    eax, eax
0x180014636  jz      short loc_1800145BB
0x180014638  mov     ebx, [rbp+57h+arg_0]
0x18001463b  lea     rcx, [rbp+57h+var_A0]; this
0x18001463f  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x180014644  mov     eax, ebx
0x180014646  add     rsp, 0B8h
0x18001464d  pop     rdi
0x18001464e  pop     rsi
0x18001464f  pop     rbx
0x180014650  pop     rbp
0x180014651  retn
```
