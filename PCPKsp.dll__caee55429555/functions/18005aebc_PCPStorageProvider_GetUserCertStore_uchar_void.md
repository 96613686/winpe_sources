# PCPStorageProvider::GetUserCertStore(uchar,void * *)

- ea: `0x18005aebc`
- end: `0x18005b2cb`
- name: `?GetUserCertStore@PCPStorageProvider@@AEAAJEPEAPEAX@Z`
- size: `1039`
- prototype: `__int64 __fastcall(PCPStorageProvider *__hidden this, unsigned __int8, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001bb00`

## callees

- `0x180011bd0`
- `0x180012640`
- `0x180015660`
- `0x1800157c0`
- `0x1800159f0`
- `0x18001b8ac`
- `0x1800222b4`
- `0x18003a8b0`
- `0x18005aebc`
- `0x1800764d0`
- `0x1800769bc`
- `0x18007704c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b027`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005b0ea`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005b0ea`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005b21a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005b21a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005b281`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005b281`
- `CRYPT32!CertOpenStore` at `0x18005b013`
- `CRYPT32!CertOpenStore` at `0x18005b013`
- `CRYPT32!CertCreateCertificateContext` at `0x18005b19e`
- `CRYPT32!CertCreateCertificateContext` at `0x18005b19e`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18005b1ca`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18005b1ca`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18005b1e7`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18005b1e7`
- `CRYPT32!CertFreeCertificateContext` at `0x18005b1fd`
- `CRYPT32!CertFreeCertificateContext` at `0x18005b256`
- `CRYPT32!CertFreeCertificateContext` at `0x18005b1fd`
- `CRYPT32!CertFreeCertificateContext` at `0x18005b256`
- `CRYPT32!CertCloseStore` at `0x18005b26c`
- `CRYPT32!CertCloseStore` at `0x18005b26c`

## pseudocode

```c
__int64 __fastcall PCPStorageProvider::GetUserCertStore(PCPStorageProvider *this, unsigned __int8 a2, void **a3)
{
  PCPStorageProvider *v3; // rcx
  unsigned int v4; // edx
  HCERTSTORE v5; // rsi
  signed int LastError; // eax
  __int64 FirstFileW; // r15
  const CERT_CONTEXT *v8; // rdi
  unsigned int i; // r14d
  __int64 v10; // rbx
  char *v11; // r12
  char *v12; // r9
  unsigned __int16 *v13; // rbx
  PCPStorageProviderKey *v14; // rax
  PCPStorageProviderKey *v15; // rax
  PCPStorageProviderKey *v16; // rbx
  const BYTE *v17; // rdx
  DWORD v18; // r8d
  const CERT_CONTEXT *CertificateContext; // rax
  unsigned int v20; // ebx
  unsigned __int8 v22; // [rsp+30h] [rbp-D0h] BYREF
  int IsAppContainer; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int8 v24; // [rsp+38h] [rbp-C8h]
  PCPStorageProvider *v25; // [rsp+40h] [rbp-C0h]
  void **v26; // [rsp+48h] [rbp-B8h]
  _QWORD pvData[6]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-80h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v30; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v31[526]; // [rsp+2F2h] [rbp+1F2h] BYREF
  __int16 v32; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v33[518]; // [rsp+502h] [rbp+402h] BYREF
  __int16 v34; // [rsp+708h] [rbp+608h]
  _BYTE v35[518]; // [rsp+70Ah] [rbp+60Ah] BYREF
  __int16 v36; // [rsp+910h] [rbp+810h] BYREF
  _BYTE v37[518]; // [rsp+912h] [rbp+812h] BYREF
  __int16 v38; // [rsp+B18h] [rbp+A18h]
  _BYTE v39[518]; // [rsp+B1Ah] [rbp+A1Ah] BYREF

  v26 = a3;
  v24 = a2;
  v25 = this;
  IsAppContainer = 0;
  KspFunctionLogger::KspFunctionLogger(
    (KspFunctionLogger *)v28,
    L"PCPStorageProvider::GetUserCertStore",
    &IsAppContainer);
  v22 = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v30 = 0;
  memset_0(v31, 0, 0x206u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  pvData[0] = 0;
  pvData[1] = L"Microsoft Platform Crypto Provider";
  memset(&pvData[2], 0, 32);
  IsAppContainer = PCPStorageProvider::IsAppContainer(v3, (bool *)&v22);
  if ( IsAppContainer < 0 )
    goto LABEL_38;
  v5 = CertOpenStore((LPCSTR)2, 0, 0, 0x2000u, 0);
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    IsAppContainer = LastError;
    goto LABEL_38;
  }
  FirstFileW = -1;
  v8 = 0;
  for ( i = 0; i < 2 && (!i || v22); ++i )
  {
    v10 = 520LL * i;
    v11 = &v33[v10 - 2];
    IsAppContainer = PCPStorageProvider::GetKeyStorageLocation(v25, v24, v22, i != 0, (STRSAFE_LPWSTR)&v33[v10 - 2]);
    if ( IsAppContainer < 0 )
      goto LABEL_29;
    v12 = &v33[v10 - 2];
    v13 = (unsigned __int16 *)&v37[v10 - 2];
    IsAppContainer = StringCchPrintfW(v13, 0x104u, L"%s*%s", v12, L".PCPKEY");
    if ( IsAppContainer < 0 )
      goto LABEL_29;
    FirstFileW = (__int64)FindFirstFileW(v13, &FindFileData);
    if ( FirstFileW != -1 )
    {
      do
      {
        IsAppContainer = StringCchPrintfW(&v30, 0x104u, L"%s%s", v11, FindFileData.cFileName);
        if ( IsAppContainer < 0 )
          goto LABEL_29;
        v14 = (PCPStorageProviderKey *)operator new(0x318u, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v14 )
        {
          v16 = 0;
LABEL_27:
          IsAppContainer = -2147024888;
          goto LABEL_30;
        }
        v15 = PCPStorageProviderKey::PCPStorageProviderKey(v14);
        v16 = v15;
        if ( !v15 )
          goto LABEL_27;
        PCPStorageProviderKey::InitializeLoadFromContainer(v15, v25, &v30, 0);
        if ( *((_BYTE *)v16 + 700)
          && (v18 = *((_DWORD *)v16 + 162)) != 0
          && (v17 = (const BYTE *)*((_QWORD *)v16 + 80)) != 0 )
        {
          CertificateContext = CertCreateCertificateContext(0x10001u, v17, v18);
          v8 = CertificateContext;
          if ( CertificateContext )
          {
            pvData[0] = *((_QWORD *)v16 + 10);
            if ( CertSetCertificateContextProperty(CertificateContext, 2u, 0, pvData) )
              CertAddCertificateContextToStore(v5, v8, 4u, 0);
LABEL_23:
            CertFreeCertificateContext(v8);
            v8 = 0;
          }
        }
        else if ( v8 )
        {
          goto LABEL_23;
        }
        PCPStorageProviderKey::`scalar deleting destructor'(v16, (unsigned int)v17);
      }
      while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    }
  }
  *v26 = v5;
  v5 = 0;
LABEL_29:
  v16 = 0;
LABEL_30:
  if ( v8 )
    CertFreeCertificateContext(v8);
  if ( v5 )
    CertCloseStore(v5, 0);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  if ( v16 )
    PCPStorageProviderKey::`scalar deleting destructor'(v16, v4);
LABEL_38:
  v20 = IsAppContainer;
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v28);
  return v20;
}

```

## disassembly

```asm
0x18005aebc  push    rbp
0x18005aebe  push    rbx
0x18005aebf  push    rsi
0x18005aec0  push    rdi
0x18005aec1  push    r12
0x18005aec3  push    r14
0x18005aec5  push    r15
0x18005aec7  lea     rbp, [rsp-0C30h]
0x18005aecf  sub     rsp, 0D30h
0x18005aed6  mov     rax, cs:__security_cookie
0x18005aedd  xor     rax, rsp
0x18005aee0  mov     [rbp+0C60h+var_40], rax
0x18005aee7  mov     [rsp+0D60h+var_D18], r8
0x18005aeec  lea     r8, [rsp+0D60h+var_D2C]; int *
0x18005aef1  mov     [rsp+0D60h+var_D28], dl
0x18005aef5  lea     rdx, aPcpstorageprov_23; "PCPStorageProvider::GetUserCertStore"
0x18005aefc  mov     [rsp+0D60h+var_D20], rcx
0x18005af01  lea     rcx, [rbp+0C60h+var_CE0]; this
0x18005af05  mov     [rsp+0D60h+var_D2C], 0
0x18005af0d  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18005af12  xor     eax, eax
0x18005af14  mov     [rsp+0D60h+var_D30], 0
0x18005af19  mov     ebx, 206h
0x18005af1e  mov     [rbp+0C60h+var_860], ax
0x18005af25  mov     r8d, ebx; Size
0x18005af28  lea     rcx, [rbp+0C60h+var_85E]; void *
0x18005af2f  xor     edx, edx; Val
0x18005af31  call    memset_0
0x18005af36  xor     eax, eax
0x18005af38  lea     rcx, [rbp+0C60h+var_656]; void *
0x18005af3f  mov     r8d, ebx; Size
0x18005af42  mov     [rbp+0C60h+var_658], ax
0x18005af49  xor     edx, edx; Val
0x18005af4b  call    memset_0
0x18005af50  xor     eax, eax
0x18005af52  lea     rcx, [rbp+0C60h+var_44E]; void *
0x18005af59  mov     r8d, ebx; Size
0x18005af5c  mov     [rbp+0C60h+var_450], ax
0x18005af63  xor     edx, edx; Val
0x18005af65  call    memset_0
0x18005af6a  xor     eax, eax
0x18005af6c  lea     rcx, [rbp+0C60h+var_246]; void *
0x18005af73  mov     r8d, ebx; Size
0x18005af76  mov     [rbp+0C60h+var_248], ax
0x18005af7d  xor     edx, edx; Val
0x18005af7f  call    memset_0
0x18005af84  xor     eax, eax
0x18005af86  lea     rcx, [rbp+0C60h+var_A6E]; void *
0x18005af8d  mov     r8d, ebx; Size
0x18005af90  mov     [rbp+0C60h+var_A70], ax
0x18005af97  xor     edx, edx; Val
0x18005af99  call    memset_0
0x18005af9e  xor     edx, edx; Val
0x18005afa0  lea     r8d, [rbx+4Ah]; Size
0x18005afa4  lea     rcx, [rbp+0C60h+FindFileData]; void *
0x18005afa8  call    memset_0
0x18005afad  lea     rax, aMicrosoftPlatf_0; "Microsoft Platform Crypto Provider"
0x18005afb4  mov     [rsp+0D60h+pvData], 0
0x18005afbd  lea     rdx, [rsp+0D60h+var_D30]; unsigned __int8 *
0x18005afc2  mov     [rsp+0D60h+var_D08], rax
0x18005afc7  mov     [rsp+0D60h+var_D00], 0
0x18005afd0  mov     [rsp+0D60h+var_CF8], 0
0x18005afd9  mov     [rsp+0D60h+var_CF0], 0
0x18005afe2  mov     [rsp+0D60h+var_CE8], 0
0x18005afeb  call    ?IsAppContainer@PCPStorageProvider@@QEAAJPEAE@Z; PCPStorageProvider::IsAppContainer(uchar *)
0x18005aff0  mov     [rsp+0D60h+var_D2C], eax
0x18005aff4  test    eax, eax
0x18005aff6  js      loc_18005B29A
0x18005affc  xor     edx, edx; dwEncodingType
0x18005affe  mov     [rsp+0D60h+pvPara], 0; pvPara
0x18005b007  mov     r9d, 2000h; dwFlags
0x18005b00d  xor     r8d, r8d; hCryptProv
0x18005b010  lea     ecx, [rdx+2]; lpszStoreProvider
0x18005b013  call    cs:__imp_CertOpenStore
0x18005b01a  nop     dword ptr [rax+rax+00h]
0x18005b01f  mov     rsi, rax
0x18005b022  test    rax, rax
0x18005b025  jnz     short loc_18005B048
0x18005b027  call    cs:__imp_GetLastError
0x18005b02e  nop     dword ptr [rax+rax+00h]
0x18005b033  test    eax, eax
0x18005b035  jle     short loc_18005B03F
0x18005b037  movzx   eax, ax
0x18005b03a  or      eax, 80070000h
0x18005b03f  mov     [rsp+0D60h+var_D2C], eax
0x18005b043  jmp     loc_18005B29A
0x18005b048  or      r15, 0FFFFFFFFFFFFFFFFh
0x18005b04c  xor     edi, edi
0x18005b04e  xor     r14d, r14d
0x18005b051  cmp     r14d, 2
0x18005b055  jnb     loc_18005B242
0x18005b05b  test    r14d, r14d
0x18005b05e  jz      short loc_18005B06B
0x18005b060  cmp     [rsp+0D60h+var_D30], 0
0x18005b065  jz      loc_18005B242
0x18005b06b  mov     r8b, [rsp+0D60h+var_D30]; unsigned __int8
0x18005b070  lea     r12, [rbp+0C60h+var_860]
0x18005b077  mov     dl, [rsp+0D60h+var_D28]; unsigned __int8
0x18005b07b  mov     rcx, [rsp+0D60h+var_D20]; this
0x18005b080  mov     eax, r14d
0x18005b083  imul    rbx, rax, 208h
0x18005b08a  add     r12, rbx
0x18005b08d  test    r14d, r14d
0x18005b090  mov     [rsp+0D60h+pvPara], r12; pszDest
0x18005b095  setnz   r9b; unsigned __int8
0x18005b099  call    ?GetKeyStorageLocation@PCPStorageProvider@@QEAAJEEEPEAG@Z; PCPStorageProvider::GetKeyStorageLocation(uchar,uchar,uchar,ushort *)
0x18005b09e  mov     [rsp+0D60h+var_D2C], eax
0x18005b0a2  test    eax, eax
0x18005b0a4  js      loc_18005B24C
0x18005b0aa  lea     rax, [rbp+0C60h+var_450]
0x18005b0b1  mov     r9, r12
0x18005b0b4  add     rbx, rax
0x18005b0b7  lea     r8, aSS_4; "%s*%s"
0x18005b0be  lea     rax, aPcpkey; ".PCPKEY"
0x18005b0c5  mov     rcx, rbx; unsigned __int16 *
0x18005b0c8  mov     edx, 104h; unsigned __int64
0x18005b0cd  mov     [rsp+0D60h+pvPara], rax
0x18005b0d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b0d7  mov     [rsp+0D60h+var_D2C], eax
0x18005b0db  test    eax, eax
0x18005b0dd  js      loc_18005B24C
0x18005b0e3  lea     rdx, [rbp+0C60h+FindFileData]; lpFindFileData
0x18005b0e7  mov     rcx, rbx; lpFileName
0x18005b0ea  call    cs:__imp_FindFirstFileW
0x18005b0f1  nop     dword ptr [rax+rax+00h]
0x18005b0f6  mov     r15, rax
0x18005b0f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b0fd  jz      loc_18005B22E
0x18005b103  lea     rax, [rbp+0C60h+FindFileData.cFileName]
0x18005b107  mov     r9, r12
0x18005b10a  lea     r8, aSS_0; "%s%s"
0x18005b111  mov     [rsp+0D60h+pvPara], rax
0x18005b116  mov     edx, 104h; unsigned __int64
0x18005b11b  lea     rcx, [rbp+0C60h+var_A70]; unsigned __int16 *
0x18005b122  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b127  mov     [rsp+0D60h+var_D2C], eax
0x18005b12b  test    eax, eax
0x18005b12d  js      loc_18005B24C
0x18005b133  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005b13a  mov     ecx, 318h; unsigned __int64
0x18005b13f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005b144  test    rax, rax
0x18005b147  jz      loc_18005B236
0x18005b14d  mov     rcx, rax; this
0x18005b150  call    ??0PCPStorageProviderKey@@QEAA@XZ; PCPStorageProviderKey::PCPStorageProviderKey(void)
0x18005b155  mov     rbx, rax
0x18005b158  test    rax, rax
0x18005b15b  jz      loc_18005B238
0x18005b161  mov     rdx, [rsp+0D60h+var_D20]; struct PCPStorageProvider *
0x18005b166  lea     r8, [rbp+0C60h+var_A70]; unsigned __int16 *
0x18005b16d  xor     r9d, r9d; unsigned __int8
0x18005b170  mov     rcx, rax; this
0x18005b173  call    ?InitializeLoadFromContainer@PCPStorageProviderKey@@QEAAJPEAVPCPStorageProvider@@PEBGE@Z; PCPStorageProviderKey::InitializeLoadFromContainer(PCPStorageProvider *,ushort const *,uchar)
0x18005b178  cmp     byte ptr [rbx+2BCh], 0
0x18005b17f  jz      short loc_18005B1F5
0x18005b181  mov     r8d, [rbx+288h]; cbCertEncoded
0x18005b188  test    r8d, r8d
0x18005b18b  jz      short loc_18005B1F5
0x18005b18d  mov     rdx, [rbx+280h]; pbCertEncoded
0x18005b194  test    rdx, rdx
0x18005b197  jz      short loc_18005B1F5
0x18005b199  mov     ecx, 10001h; dwCertEncodingType
0x18005b19e  call    cs:__imp_CertCreateCertificateContext
0x18005b1a5  nop     dword ptr [rax+rax+00h]
0x18005b1aa  mov     rdi, rax
0x18005b1ad  test    rax, rax
0x18005b1b0  jz      short loc_18005B20B
0x18005b1b2  mov     rcx, [rbx+50h]
0x18005b1b6  lea     r9, [rsp+0D60h+pvData]; pvData
0x18005b1bb  xor     r8d, r8d; dwFlags
0x18005b1be  mov     [rsp+0D60h+pvData], rcx
0x18005b1c3  mov     rcx, rax; pCertContext
0x18005b1c6  lea     edx, [r8+2]; dwPropId
0x18005b1ca  call    cs:__imp_CertSetCertificateContextProperty
0x18005b1d1  nop     dword ptr [rax+rax+00h]
0x18005b1d6  test    eax, eax
0x18005b1d8  jz      short loc_18005B1FA
0x18005b1da  xor     r9d, r9d; ppStoreContext
0x18005b1dd  mov     rdx, rdi; pCertContext
0x18005b1e0  mov     rcx, rsi; hCertStore
0x18005b1e3  lea     r8d, [r9+4]; dwAddDisposition
0x18005b1e7  call    cs:__imp_CertAddCertificateContextToStore
0x18005b1ee  nop     dword ptr [rax+rax+00h]
0x18005b1f3  jmp     short loc_18005B1FA
0x18005b1f5  test    rdi, rdi
0x18005b1f8  jz      short loc_18005B20B
0x18005b1fa  mov     rcx, rdi; pCertContext
0x18005b1fd  call    cs:__imp_CertFreeCertificateContext
0x18005b204  nop     dword ptr [rax+rax+00h]
0x18005b209  xor     edi, edi
0x18005b20b  mov     rcx, rbx; this
0x18005b20e  call    ??_GPCPStorageProviderKey@@QEAAPEAXI@Z; PCPStorageProviderKey::`scalar deleting destructor'(uint)
0x18005b213  lea     rdx, [rbp+0C60h+FindFileData]; lpFindFileData
0x18005b217  mov     rcx, r15; hFindFile
0x18005b21a  call    cs:__imp_FindNextFileW
0x18005b221  nop     dword ptr [rax+rax+00h]
0x18005b226  test    eax, eax
0x18005b228  jnz     loc_18005B103
0x18005b22e  inc     r14d
0x18005b231  jmp     loc_18005B051
0x18005b236  xor     ebx, ebx
0x18005b238  mov     [rsp+0D60h+var_D2C], 80070008h
0x18005b240  jmp     short loc_18005B24E
0x18005b242  mov     rax, [rsp+0D60h+var_D18]
0x18005b247  mov     [rax], rsi
0x18005b24a  xor     esi, esi
0x18005b24c  xor     ebx, ebx
0x18005b24e  test    rdi, rdi
0x18005b251  jz      short loc_18005B262
0x18005b253  mov     rcx, rdi; pCertContext
0x18005b256  call    cs:__imp_CertFreeCertificateContext
0x18005b25d  nop     dword ptr [rax+rax+00h]
0x18005b262  test    rsi, rsi
0x18005b265  jz      short loc_18005B278
0x18005b267  xor     edx, edx; dwFlags
0x18005b269  mov     rcx, rsi; hCertStore
0x18005b26c  call    cs:__imp_CertCloseStore
0x18005b273  nop     dword ptr [rax+rax+00h]
0x18005b278  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18005b27c  jz      short loc_18005B28D
0x18005b27e  mov     rcx, r15; hFindFile
0x18005b281  call    cs:__imp_FindClose
0x18005b288  nop     dword ptr [rax+rax+00h]
0x18005b28d  test    rbx, rbx
0x18005b290  jz      short loc_18005B29A
0x18005b292  mov     rcx, rbx; this
0x18005b295  call    ??_GPCPStorageProviderKey@@QEAAPEAXI@Z; PCPStorageProviderKey::`scalar deleting destructor'(uint)
0x18005b29a  mov     ebx, [rsp+0D60h+var_D2C]
0x18005b29e  lea     rcx, [rbp+0C60h+var_CE0]; this
0x18005b2a2  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18005b2a7  mov     eax, ebx
0x18005b2a9  mov     rcx, [rbp+0C60h+var_40]
0x18005b2b0  xor     rcx, rsp; StackCookie
0x18005b2b3  call    __security_check_cookie
0x18005b2b8  add     rsp, 0D30h
0x18005b2bf  pop     r15
0x18005b2c1  pop     r14
0x18005b2c3  pop     r12
0x18005b2c5  pop     rdi
0x18005b2c6  pop     rsi
0x18005b2c7  pop     rbx
0x18005b2c8  pop     rbp
0x18005b2c9  retn
```
