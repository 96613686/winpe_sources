# ConfigProvider::ValidateIssuerThumbprint(IRequestContext *,ulong,ushort const *)

- ea: `0x180108008`
- end: `0x180108424`
- name: `?ValidateIssuerThumbprint@ConfigProvider@@AEAAHPEAVIRequestContext@@KPEBG@Z`
- size: `1052`
- prototype: `__int64 __fastcall(struct _CERT_CONTEXT *this, struct IRequestContext *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1801ac02c`

## callees

- `0x180005d10`
- `0x1800f3b70`
- `0x180108008`
- `0x180109050`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x18011f48c`
- `0x180122110`
- `0x1801aac64`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801081e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010830e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801081e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010830e`
- `CRYPT32!CertCloseStore` at `0x1801081b8`
- `CRYPT32!CertCloseStore` at `0x1801083f9`
- `CRYPT32!CertCloseStore` at `0x1801081b8`
- `CRYPT32!CertCloseStore` at `0x1801083f9`
- `CRYPT32!CertFindCertificateInStore` at `0x180108194`
- `CRYPT32!CertFindCertificateInStore` at `0x180108250`
- `CRYPT32!CertFindCertificateInStore` at `0x180108194`
- `CRYPT32!CertFindCertificateInStore` at `0x180108250`
- `CRYPT32!CertOpenStore` at `0x180108105`
- `CRYPT32!CertOpenStore` at `0x1801081d8`
- `CRYPT32!CertOpenStore` at `0x180108105`
- `CRYPT32!CertOpenStore` at `0x1801081d8`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x1801082cd`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x1801082cd`

## string_xrefs

- `0x180108079`: `onecore\admin\wmi\wmx\providers\config\configprovider.cpp`

## pseudocode

```c
__int64 __fastcall ConfigProvider::ValidateIssuerThumbprint(
        struct _CERT_CONTEXT *this,
        struct IRequestContext *a2,
        int a3,
        const unsigned __int16 *a4)
{
  struct CertHash *CertHash; // rbx
  HCERTSTORE v8; // r15
  DWORD LastError; // eax
  DWORD v10; // ebx
  PCCERT_CONTEXT CertificateInStore; // rax
  struct _CERT_CONTEXT *v12; // rbx
  DWORD v13; // eax
  DWORD v14; // ebx
  unsigned int v15; // esi
  PCCERT_CONTEXT v16; // rax
  const CERT_CHAIN_CONTEXT *v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  DWORD v20; // eax
  DWORD v21; // ebx
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int128 pvFindPara; // [rsp+30h] [rbp-10h] BYREF
  struct _CERT_CONTEXT *v25; // [rsp+80h] [rbp+40h] BYREF
  struct CertHash *v26; // [rsp+88h] [rbp+48h] BYREF
  int pbKeyUsage; // [rsp+90h] [rbp+50h] BYREF

  pbKeyUsage = a3;
  v25 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids);
  if ( !a2 )
  {
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp",
      0xC26u,
      L"3110",
      0x54Fu,
      0);
    return 0;
  }
  if ( !a4 )
  {
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp",
      0xC27u,
      L"3111",
      0x54Fu,
      a2);
    return 0;
  }
  CertHash = CertHash::CreateCertHash(a2, a4);
  v26 = CertHash;
  if ( !CertHash )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids);
LABEL_13:
    AutoCleanup<AutoDelete<CertHash>,CertHash *>::ReleasePtr(&v26);
    return 0;
  }
  v8 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"CA");
  if ( !v8 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, LastError);
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v10);
    goto LABEL_13;
  }
  v25 = 0;
  pvFindPara = 0;
  LODWORD(pvFindPara) = *(_DWORD *)CertHash;
  *((_QWORD *)&pvFindPara + 1) = *((_QWORD *)CertHash + 1);
  CertificateInStore = CertFindCertificateInStore(v8, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
  AutoCleanup<AutoCertContext,_CERT_CONTEXT const *>::operator=(&v25, CertificateInStore);
  v12 = v25;
  if ( !v25 )
  {
    CertCloseStore(v8, 0);
    v8 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"Root");
    if ( !v8 )
    {
      v13 = GetLastError();
      v14 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, v13);
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v14);
      v15 = 0;
      goto LABEL_52;
    }
    v16 = CertFindCertificateInStore(v8, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    AutoCleanup<AutoCertContext,_CERT_CONTEXT const *>::operator=(&v25, v16);
    v12 = v25;
    if ( !v25 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
        goto LABEL_48;
      v19 = 89;
      goto LABEL_47;
    }
  }
  v15 = 1;
  (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 200LL))(a2, 1);
  if ( (unsigned int)ConfigProvider::IsSelfSignedCertificate(v17, a2, v12) )
    goto LABEL_51;
  if ( !(*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      v23 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, v23);
    }
    goto LABEL_50;
  }
  pbKeyUsage = 0;
  if ( !CertGetIntendedKeyUsage(0x10001u, v12->pCertInfo, (BYTE *)&pbKeyUsage, 4u) )
  {
    v20 = GetLastError();
    v21 = v20;
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, v20);
      v22 = v21;
      goto LABEL_49;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
    {
LABEL_48:
      v22 = 2150859106LL;
LABEL_49:
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v22);
LABEL_50:
      v15 = 0;
      goto LABEL_51;
    }
    v19 = 86;
LABEL_47:
    WPP_SF_S(v18[2], v19, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, a4);
    goto LABEL_48;
  }
  if ( (pbKeyUsage & 4) == 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_48;
    v19 = 85;
    goto LABEL_47;
  }
LABEL_51:
  CertCloseStore(v8, 0);
LABEL_52:
  AutoCleanup<AutoCertContext,_CERT_CONTEXT const *>::ReleasePtr(&v25);
  AutoCleanup<AutoDelete<CertHash>,CertHash *>::ReleasePtr(&v26);
  return v15;
}

```

## disassembly

```asm
0x180108008  mov     [rsp-38h+pbKeyUsage], r8d
0x18010800d  mov     [rsp-38h+arg_0], rcx
0x180108012  push    rbp
0x180108013  push    rbx
0x180108014  push    rsi
0x180108015  push    rdi
0x180108016  push    r13
0x180108018  push    r14
0x18010801a  push    r15
0x18010801c  mov     rbp, rsp
0x18010801f  sub     rsp, 40h
0x180108023  mov     r14, r9
0x180108026  mov     rdi, rdx
0x180108029  lea     r13, WPP_GLOBAL_Control
0x180108030  lea     rsi, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x180108037  mov     rcx, cs:WPP_GLOBAL_Control
0x18010803e  cmp     rcx, r13
0x180108041  jz      short loc_18010805D
0x180108043  test    dword ptr [rcx+1Ch], 200000h
0x18010804a  jz      short loc_18010805D
0x18010804c  mov     edx, 51h ; 'Q'
0x180108051  mov     r8, rsi
0x180108054  mov     rcx, [rcx+10h]
0x180108058  call    WPP_SF_
0x18010805d  test    rdi, rdi
0x180108060  jnz     short loc_18010808C
0x180108062  mov     [rsp+40h+pvPara], rdi; struct IRequestContext *
0x180108067  lea     r8, a3110; "3110"
0x18010806e  mov     edx, 0C26h; unsigned int
0x180108073  mov     r9d, 54Fh; unsigned int
0x180108079  lea     rcx, aOnecoreAdminWm_139; "onecore\\admin\\wmi\\wmx\\providers\\co"...
0x180108080  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180108085  xor     eax, eax
0x180108087  jmp     loc_180108415
0x18010808c  test    r14, r14
0x18010808f  jnz     short loc_1801080A4
0x180108091  mov     [rsp+40h+pvPara], rdi
0x180108096  lea     r8, a3111; "3111"
0x18010809d  mov     edx, 0C27h
0x1801080a2  jmp     short loc_180108073
0x1801080a4  mov     rdx, r14; unsigned __int16 *
0x1801080a7  mov     rcx, rdi; struct IRequestContext *
0x1801080aa  call    ?CreateCertHash@CertHash@@SAPEAV1@PEAVIRequestContext@@PEBG@Z; CertHash::CreateCertHash(IRequestContext *,ushort const *)
0x1801080af  mov     rbx, rax
0x1801080b2  mov     [rbp+arg_8], rax
0x1801080b6  test    rax, rax
0x1801080b9  jnz     short loc_1801080EB
0x1801080bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801080c2  cmp     rcx, r13
0x1801080c5  jz      short loc_1801080E0
0x1801080c7  test    dword ptr [rcx+1Ch], 400000h
0x1801080ce  jz      short loc_1801080E0
0x1801080d0  lea     edx, [rax+52h]
0x1801080d3  mov     r8, rsi
0x1801080d6  mov     rcx, [rcx+10h]
0x1801080da  call    WPP_SF_
0x1801080df  nop
0x1801080e0  lea     rcx, [rbp+arg_8]
0x1801080e4  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VCertHash@@@@PEAVCertHash@@@@AEAAXXZ; AutoCleanup<AutoDelete<CertHash>,CertHash *>::ReleasePtr(void)
0x1801080e9  jmp     short loc_180108085
0x1801080eb  lea     rax, aCa; "CA"
0x1801080f2  mov     [rsp+40h+pvPara], rax; pvPara
0x1801080f7  mov     r9d, 28000h; dwFlags
0x1801080fd  xor     r8d, r8d; hCryptProv
0x180108100  xor     edx, edx; dwEncodingType
0x180108102  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180108105  call    cs:__imp_CertOpenStore
0x18010810b  mov     r15, rax
0x18010810e  test    rax, rax
0x180108111  jnz     short loc_180108156
0x180108113  call    cs:__imp_GetLastError
0x180108119  mov     ebx, eax
0x18010811b  mov     rcx, cs:WPP_GLOBAL_Control
0x180108122  cmp     rcx, r13
0x180108125  jz      short loc_180108143
0x180108127  test    dword ptr [rcx+1Ch], 800h
0x18010812e  jz      short loc_180108143
0x180108130  lea     edx, [r15+53h]
0x180108134  mov     r9d, eax
0x180108137  mov     r8, rsi
0x18010813a  mov     rcx, [rcx+10h]
0x18010813e  call    WPP_SF_d
0x180108143  mov     rax, [rdi]
0x180108146  mov     edx, ebx
0x180108148  mov     rcx, rdi
0x18010814b  mov     rax, [rax+48h]
0x18010814f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108154  jmp     short loc_1801080E0
0x180108156  mov     [rbp+arg_0], 0
0x18010815e  xorps   xmm0, xmm0
0x180108161  movups  [rbp+pvFindPara], xmm0
0x180108165  mov     eax, [rbx]
0x180108167  mov     dword ptr [rbp+pvFindPara], eax
0x18010816a  mov     rax, [rbx+8]
0x18010816e  mov     qword ptr [rbp+pvFindPara+8], rax
0x180108172  mov     [rsp+40h+pPrevCertContext], 0; pPrevCertContext
0x18010817b  lea     rax, [rbp+pvFindPara]
0x18010817f  mov     [rsp+40h+pvPara], rax; pvFindPara
0x180108184  mov     r9d, 10000h; dwFindType
0x18010818a  xor     r8d, r8d; dwFindFlags
0x18010818d  lea     edx, [r9+1]; dwCertEncodingType
0x180108191  mov     rcx, r15; hCertStore
0x180108194  call    cs:__imp_CertFindCertificateInStore
0x18010819a  mov     rdx, rax
0x18010819d  lea     rcx, [rbp+arg_0]
0x1801081a1  call    ??4?$AutoCleanup@VAutoCertContext@@PEBU_CERT_CONTEXT@@@@QEAAAEAVAutoCertContext@@PEBU_CERT_CONTEXT@@@Z; AutoCleanup<AutoCertContext,_CERT_CONTEXT const *>::operator=(_CERT_CONTEXT const *)
0x1801081a6  mov     rbx, [rbp+arg_0]
0x1801081aa  test    rbx, rbx
0x1801081ad  jnz     loc_18010826F
0x1801081b3  xor     edx, edx; dwFlags
0x1801081b5  mov     rcx, r15; hCertStore
0x1801081b8  call    cs:__imp_CertCloseStore
0x1801081be  lea     rax, aRoot_0; "Root"
0x1801081c5  mov     [rsp+40h+pvPara], rax; pvPara
0x1801081ca  mov     r9d, 28000h; dwFlags
0x1801081d0  xor     r8d, r8d; hCryptProv
0x1801081d3  xor     edx, edx; dwEncodingType
0x1801081d5  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x1801081d8  call    cs:__imp_CertOpenStore
0x1801081de  mov     r15, rax
0x1801081e1  test    rax, rax
0x1801081e4  jnz     short loc_18010822E
0x1801081e6  call    cs:__imp_GetLastError
0x1801081ec  mov     ebx, eax
0x1801081ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1801081f5  cmp     rcx, r13
0x1801081f8  jz      short loc_180108216
0x1801081fa  test    dword ptr [rcx+1Ch], 400000h
0x180108201  jz      short loc_180108216
0x180108203  lea     edx, [r15+54h]
0x180108207  mov     r9d, eax
0x18010820a  mov     r8, rsi
0x18010820d  mov     rcx, [rcx+10h]
0x180108211  call    WPP_SF_d
0x180108216  mov     rax, [rdi]
0x180108219  mov     edx, ebx
0x18010821b  mov     rcx, rdi
0x18010821e  mov     rax, [rax+48h]
0x180108222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108227  xor     esi, esi
0x180108229  jmp     loc_180108400
0x18010822e  mov     [rsp+40h+pPrevCertContext], 0; pPrevCertContext
0x180108237  lea     rax, [rbp+pvFindPara]
0x18010823b  mov     [rsp+40h+pvPara], rax; pvFindPara
0x180108240  mov     r9d, 10000h; dwFindType
0x180108246  xor     r8d, r8d; dwFindFlags
0x180108249  lea     edx, [r9+1]; dwCertEncodingType
0x18010824d  mov     rcx, r15; hCertStore
0x180108250  call    cs:__imp_CertFindCertificateInStore
0x180108256  mov     rdx, rax
0x180108259  lea     rcx, [rbp+arg_0]
0x18010825d  call    ??4?$AutoCleanup@VAutoCertContext@@PEBU_CERT_CONTEXT@@@@QEAAAEAVAutoCertContext@@PEBU_CERT_CONTEXT@@@Z; AutoCleanup<AutoCertContext,_CERT_CONTEXT const *>::operator=(_CERT_CONTEXT const *)
0x180108262  mov     rbx, [rbp+arg_0]
0x180108266  test    rbx, rbx
0x180108269  jz      loc_1801083B5
0x18010826f  mov     esi, 1
0x180108274  mov     rax, [rdi]
0x180108277  mov     edx, esi
0x180108279  mov     rcx, rdi
0x18010827c  mov     rax, [rax+0C8h]
0x180108283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108288  mov     r8, rbx; struct _CERT_CONTEXT *
0x18010828b  mov     rdx, rdi; struct IRequestContext *
0x18010828e  call    ?IsSelfSignedCertificate@ConfigProvider@@AEAAHPEAVIRequestContext@@PEBU_CERT_CONTEXT@@@Z; ConfigProvider::IsSelfSignedCertificate(IRequestContext *,_CERT_CONTEXT const *)
0x180108293  test    eax, eax
0x180108295  jnz     loc_1801083F4
0x18010829b  mov     rax, [rdi]
0x18010829e  mov     rcx, rdi
0x1801082a1  mov     rax, [rax+90h]
0x1801082a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801082ad  test    eax, eax
0x1801082af  jz      loc_18010836D
0x1801082b5  mov     [rbp+pbKeyUsage], 0
0x1801082bc  lea     r9d, [rsi+3]; cbKeyUsage
0x1801082c0  lea     r8, [rbp+pbKeyUsage]; pbKeyUsage
0x1801082c4  mov     rdx, [rbx+18h]; pCertInfo
0x1801082c8  mov     ecx, 10001h; dwCertEncodingType
0x1801082cd  call    cs:__imp_CertGetIntendedKeyUsage
0x1801082d3  test    eax, eax
0x1801082d5  jz      short loc_18010830E
0x1801082d7  mov     eax, [rbp+pbKeyUsage]
0x1801082da  test    al, 4
0x1801082dc  jnz     loc_1801083F4
0x1801082e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801082e9  cmp     rcx, r13
0x1801082ec  jz      loc_1801083DE
0x1801082f2  test    dword ptr [rcx+1Ch], 400000h
0x1801082f9  jz      loc_1801083DE
0x1801082ff  lea     edx, [rsi+54h]
0x180108302  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x180108309  jmp     loc_1801083D2
0x18010830e  call    cs:__imp_GetLastError
0x180108314  mov     ebx, eax
0x180108316  test    eax, eax
0x180108318  jnz     short loc_18010833C
0x18010831a  mov     rcx, cs:WPP_GLOBAL_Control
0x180108321  cmp     rcx, r13
0x180108324  jz      loc_1801083DE
0x18010832a  test    dword ptr [rcx+1Ch], 400000h
0x180108331  jz      loc_1801083DE
0x180108337  lea     edx, [rax+56h]
0x18010833a  jmp     short loc_180108302
0x18010833c  mov     rcx, cs:WPP_GLOBAL_Control
0x180108343  cmp     rcx, r13
0x180108346  jz      short loc_180108369
0x180108348  test    dword ptr [rcx+1Ch], 400000h
0x18010834f  jz      short loc_180108369
0x180108351  mov     edx, 57h ; 'W'
0x180108356  mov     r9d, ebx
0x180108359  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x180108360  mov     rcx, [rcx+10h]
0x180108364  call    WPP_SF_d
0x180108369  mov     edx, ebx
0x18010836b  jmp     short loc_1801083E3
0x18010836d  mov     rax, cs:WPP_GLOBAL_Control
0x180108374  cmp     rax, r13
0x180108377  jz      short loc_1801083F2
0x180108379  test    dword ptr [rax+1Ch], 400000h
0x180108380  jz      short loc_1801083F2
0x180108382  mov     rax, [rdi]
0x180108385  mov     rcx, rdi
0x180108388  mov     rax, [rax+98h]
0x18010838f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108394  mov     edx, 58h ; 'X'
0x180108399  mov     r9d, eax
0x18010839c  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x1801083a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801083aa  mov     rcx, [rcx+10h]
0x1801083ae  call    WPP_SF_d
0x1801083b3  jmp     short loc_1801083F2
0x1801083b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801083bc  cmp     rcx, r13
0x1801083bf  jz      short loc_1801083DE
0x1801083c1  test    dword ptr [rcx+1Ch], 400000h
0x1801083c8  jz      short loc_1801083DE
0x1801083ca  mov     edx, 59h ; 'Y'
0x1801083cf  mov     r8, rsi
0x1801083d2  mov     r9, r14
0x1801083d5  mov     rcx, [rcx+10h]
0x1801083d9  call    WPP_SF_S
0x1801083de  mov     edx, 80338162h
0x1801083e3  mov     rax, [rdi]
0x1801083e6  mov     rcx, rdi
0x1801083e9  mov     rax, [rax+48h]
0x1801083ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801083f2  xor     esi, esi
0x1801083f4  xor     edx, edx; dwFlags
0x1801083f6  mov     rcx, r15; hCertStore
0x1801083f9  call    cs:__imp_CertCloseStore
0x1801083ff  nop
0x180108400  lea     rcx, [rbp+arg_0]
0x180108404  call    ?ReleasePtr@?$AutoCleanup@VAutoCertContext@@PEBU_CERT_CONTEXT@@@@AEAAXXZ; AutoCleanup<AutoCertContext,_CERT_CONTEXT const *>::ReleasePtr(void)
0x180108409  nop
0x18010840a  lea     rcx, [rbp+arg_8]
0x18010840e  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VCertHash@@@@PEAVCertHash@@@@AEAAXXZ; AutoCleanup<AutoDelete<CertHash>,CertHash *>::ReleasePtr(void)
0x180108413  mov     eax, esi
0x180108415  add     rsp, 40h
0x180108419  pop     r15
0x18010841b  pop     r14
0x18010841d  pop     r13
0x18010841f  pop     rdi
0x180108420  pop     rsi
0x180108421  pop     rbx
0x180108422  pop     rbp
0x180108423  retn
```
