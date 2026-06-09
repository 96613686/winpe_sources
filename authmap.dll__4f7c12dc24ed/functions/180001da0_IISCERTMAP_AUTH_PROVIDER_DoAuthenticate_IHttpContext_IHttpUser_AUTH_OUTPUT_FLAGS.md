# IISCERTMAP_AUTH_PROVIDER::DoAuthenticate(IHttpContext *,IHttpUser * *,AUTH_OUTPUT_FLAGS *)

- ea: `0x180001da0`
- end: `0x1800022a9`
- name: `?DoAuthenticate@IISCERTMAP_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAPEAVIHttpUser@@PEAW4AUTH_OUTPUT_FLAGS@@@Z`
- size: `1289`
- prototype: `__int64 __fastcall(IISCERTMAP_AUTH_PROVIDER *this, struct IHttpContext *, struct IHttpUser **, enum AUTH_OUTPUT_FLAGS *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180001da0`
- `0x180003824`
- `0x180003f3c`
- `0x180004ef8`
- `0x180005aec`
- `0x180006b58`
- `0x180006d92`
- `0x180006dd0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eef`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001dfd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001e22`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001dfd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001e22`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x1800021b8`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x1800021d4`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x1800021b8`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x1800021d4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001e3f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001e49`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000218b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002195`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001e3f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001e49`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000218b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002195`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000225f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002269`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002273`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000227e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000225f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002269`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002273`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000227e`
- `CRYPT32!CertFreeCertificateContext` at `0x180001f8b`
- `CRYPT32!CertFreeCertificateContext` at `0x180001f8b`
- `CRYPT32!CertCreateCertificateContext` at `0x180001ee1`
- `CRYPT32!CertCreateCertificateContext` at `0x180001ee1`

## pseudocode

```c
__int64 __fastcall IISCERTMAP_AUTH_PROVIDER::DoAuthenticate(
        IISCERTMAP_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        struct IHttpUser **a3,
        enum AUTH_OUTPUT_FLAGS *a4)
{
  void (__fastcall **v7)(struct IHttpContext *); // rax
  int v8; // r14d
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, __int64); // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdi
  PCCERT_CONTEXT CertificateContext; // r15
  signed int LastError; // eax
  signed int CacheKey; // ebx
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned int v21; // r14d
  int (__fastcall *v22)(struct IHttpServer *, _QWORD, void ***, struct IHttpTokenEntry **, __int64); // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  struct sockaddr *v25; // rbx
  void (__fastcall *v26)(struct IHttpServer *, __int64, void ***, struct IHttpTokenEntry **, __int64); // rbx
  __int64 v27; // rax
  _QWORD *v28; // rdi
  struct IHttpTokenEntry *v29; // r14
  int v30; // r8d
  __int64 v31; // rcx
  unsigned __int16 *v32; // rax
  struct IHttpTokenEntry *v34; // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+4Ch] [rbp-B4h] BYREF
  IISCERTMAP_AUTH_PROVIDER *v37; // [rsp+50h] [rbp-B0h]
  _BYTE v38[32]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v39; // [rsp+78h] [rbp-88h]
  int v40; // [rsp+88h] [rbp-78h]
  _BYTE v41[32]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v42; // [rsp+B0h] [rbp-50h]
  void **v43; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v44[56]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v45[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v46[64]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v47[64]; // [rsp+1D0h] [rbp+D0h] BYREF

  v37 = this;
  memset_0(v46, 0, sizeof(v46));
  STRU::STRU((STRU *)v38, v46, 0x40u);
  memset_0(v47, 0, sizeof(v47));
  STRU::STRU((STRU *)v41, v47, 0x40u);
  v43 = &TOKEN_KEY::`vftable';
  v34 = 0;
  STRU::STRU((STRU *)v44);
  STRU::STRU((STRU *)v45);
  v7 = *(void (__fastcall ***)(struct IHttpContext *))a2;
  v8 = 0;
  v36 = 0;
  (*v7)(a2);
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v11 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
  v12 = (__int64 (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v13 = (**v12)(v12, qword_18000D800);
  v14 = *(_QWORD *)(v10 + 840);
  v15 = v13;
  v35 = 0;
  CertificateContext = CertCreateCertificateContext(
                         0x10001u,
                         *(const BYTE **)(*(_QWORD *)(v14 + 32) + 8LL),
                         *(_DWORD *)(*(_QWORD *)(v14 + 32) + 4LL));
  if ( CertificateContext )
  {
    if ( *(_DWORD *)(v15 + 8) )
    {
      CacheKey = CERT_1TO1_MAPPER::Match(
                   (CERT_1TO1_MAPPER *)(v15 + 80),
                   CertificateContext,
                   &v35,
                   (struct STRU *)v41,
                   (struct STRU *)v38);
      if ( CacheKey < 0 )
      {
LABEL_12:
        CertFreeCertificateContext(CertificateContext);
        goto LABEL_13;
      }
      if ( v35 )
      {
        v8 = 1;
        goto LABEL_12;
      }
    }
    if ( *(_DWORD *)(v15 + 12) )
    {
      CacheKey = CERT_MANYTO1_MAPPER::Match(
                   (CERT_MANYTO1_MAPPER *)(v15 + 152),
                   CertificateContext,
                   &v35,
                   (struct STRU *)v41,
                   (struct STRU *)v38,
                   &v36);
      if ( CacheKey >= 0 )
        v8 = v35;
    }
    else
    {
      CacheKey = 0;
    }
    goto LABEL_12;
  }
  LastError = GetLastError();
  CacheKey = LastError;
  if ( LastError > 0 )
    CacheKey = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  if ( CacheKey >= 0 )
  {
    if ( v8 )
    {
      if ( v36 )
      {
        CacheKey = 0;
        v19 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
        *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19) + 536) = 0;
        v20 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v20 + 24LL))(
          v20,
          403,
          "Forbidden",
          12,
          0,
          0,
          0);
        *(_DWORD *)a4 = 2;
      }
      else
      {
        v21 = *(_DWORD *)(v15 + 72);
        CacheKey = TOKEN_KEY::CreateCacheKey((TOKEN_KEY *)&v43, v42, v39, v21);
        if ( CacheKey >= 0 )
        {
          v22 = *(int (__fastcall **)(struct IHttpServer *, _QWORD, void ***, struct IHttpTokenEntry **, __int64))(*(_QWORD *)s_pGlobalInfo + 80LL);
          v23 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
          if ( v22(s_pGlobalInfo, 0, &v43, &v34, v23) < 0 || !v34 )
          {
            v24 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
            v25 = *(struct sockaddr **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24) + 104);
            (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 24LL))(s_pGlobalInfo);
            CacheKey = IIS_LOGON_PROVIDER::IISLogonUser(
                         (IISCERTMAP_AUTH_PROVIDER *)((char *)v37 + 16),
                         v42,
                         v39,
                         v21,
                         *(const unsigned __int16 **)(v15 + 48),
                         v25,
                         &v34);
            (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 32LL))(s_pGlobalInfo);
            if ( CacheKey < 0 )
              goto LABEL_32;
            v26 = *(void (__fastcall **)(struct IHttpServer *, __int64, void ***, struct IHttpTokenEntry **, __int64))(*(_QWORD *)s_pGlobalInfo + 80LL);
            v27 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
            v26(s_pGlobalInfo, 1, &v43, &v34, v27);
          }
          v28 = operator new(0x88u);
          if ( !v28 )
          {
            (*(void (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v34 + 16LL))(v34);
            v34 = 0;
            CacheKey = -2147024888;
            goto LABEL_32;
          }
          *v28 = &IISCERTMAP_USER_CONTEXT::`vftable';
          STRU::STRU((STRU *)(v28 + 3));
          STRU::STRU((STRU *)(v28 + 10));
          v28[2] = 0;
          *((_DWORD *)v28 + 2) = 1;
          v29 = v34;
          if ( v34 )
          {
            CacheKey = STRU::Copy((STRU *)(v28 + 3), (const struct STRU *)v41);
            if ( CacheKey >= 0 )
            {
              CacheKey = STRU::Copy((STRU *)(v28 + 10), (const struct STRU *)v38);
              if ( CacheKey >= 0 )
              {
                v28[2] = v29;
                *a3 = (struct IHttpUser *)v28;
                TraceAuthSucceeded(a2, (struct IHttpUser *)v28, v30);
                CacheKey = 0;
                goto LABEL_32;
              }
            }
            v29 = v34;
          }
          else
          {
            CacheKey = -2147024809;
          }
          (*(void (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v29 + 16LL))(v29);
          v34 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v28 + 56LL))(v28);
        }
      }
    }
    else
    {
      *(_DWORD *)a4 = 1;
    }
  }
LABEL_32:
  if ( v40 )
  {
    v31 = (unsigned int)(2 * v40);
    v32 = v39;
    if ( 2 * v40 )
    {
      do
      {
        *(_BYTE *)v32 = 0;
        v32 = (unsigned __int16 *)((char *)v32 + 1);
        --v31;
      }
      while ( v31 );
    }
  }
  STRU::~STRU((STRU *)v45);
  STRU::~STRU((STRU *)v44);
  STRU::~STRU((STRU *)v41);
  STRU::~STRU((STRU *)v38);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x180001da0  push    rbp
0x180001da2  push    rbx
0x180001da3  push    rsi
0x180001da4  push    rdi
0x180001da5  push    r12
0x180001da7  push    r13
0x180001da9  push    r14
0x180001dab  push    r15
0x180001dad  lea     rbp, [rsp-168h]
0x180001db5  sub     rsp, 268h
0x180001dbc  mov     rax, cs:__security_cookie
0x180001dc3  xor     rax, rsp
0x180001dc6  mov     [rbp+1A0h+var_50], rax
0x180001dcd  mov     r13, r8
0x180001dd0  mov     [rsp+2A0h+var_250], rcx
0x180001dd5  mov     rsi, rdx
0x180001dd8  lea     rcx, [rbp+1A0h+var_150]; void *
0x180001ddc  mov     edi, 80h
0x180001de1  xor     edx, edx; Val
0x180001de3  mov     r8d, edi; Size
0x180001de6  mov     r12, r9
0x180001de9  call    memset_0
0x180001dee  lea     ebx, [rdi-40h]
0x180001df1  mov     r8d, ebx
0x180001df4  lea     rdx, [rbp+1A0h+var_150]
0x180001df8  lea     rcx, [rsp+2A0h+var_248]
0x180001dfd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001e03  mov     r8d, edi; Size
0x180001e06  lea     rcx, [rbp+1A0h+var_D0]; void *
0x180001e0d  xor     edx, edx; Val
0x180001e0f  call    memset_0
0x180001e14  mov     r8d, ebx
0x180001e17  lea     rdx, [rbp+1A0h+var_D0]
0x180001e1e  lea     rcx, [rbp+1A0h+var_210]
0x180001e22  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001e28  lea     rax, ??_7TOKEN_KEY@@6B@; const TOKEN_KEY::`vftable'
0x180001e2f  xor     r15d, r15d
0x180001e32  lea     rcx, [rbp+1A0h+var_1C8]
0x180001e36  mov     [rbp+1A0h+var_1D0], rax
0x180001e3a  mov     [rsp+2A0h+var_260], r15
0x180001e3f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001e45  lea     rcx, [rbp+1A0h+var_190]
0x180001e49  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001e4f  mov     rax, [rsi]
0x180001e52  mov     rcx, rsi
0x180001e55  mov     r14d, r15d
0x180001e58  mov     [rsp+2A0h+var_254], r15d
0x180001e5d  mov     rax, [rax]
0x180001e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e65  mov     rax, [rsi]
0x180001e68  mov     rcx, rsi
0x180001e6b  mov     rax, [rax+18h]
0x180001e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e74  mov     rdx, rax
0x180001e77  mov     rcx, [rax]
0x180001e7a  mov     rax, [rcx+8]
0x180001e7e  mov     rcx, rdx
0x180001e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e86  mov     rcx, [rsi]
0x180001e89  mov     rbx, rax
0x180001e8c  mov     rax, [rcx]
0x180001e8f  mov     rcx, rsi
0x180001e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e97  mov     rdx, rax
0x180001e9a  mov     rcx, [rax]
0x180001e9d  mov     rax, [rcx+10h]
0x180001ea1  mov     rcx, rdx
0x180001ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ea9  mov     rdx, cs:qword_18000D800
0x180001eb0  mov     r8, rax
0x180001eb3  mov     rcx, [rax]
0x180001eb6  mov     rax, [rcx]
0x180001eb9  mov     rcx, r8
0x180001ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec1  mov     rcx, [rbx+348h]
0x180001ec8  mov     rdi, rax
0x180001ecb  mov     [rsp+2A0h+var_258], r15d
0x180001ed0  mov     rdx, [rcx+20h]
0x180001ed4  mov     ecx, 10001h; dwCertEncodingType
0x180001ed9  mov     r8d, [rdx+4]; cbCertEncoded
0x180001edd  mov     rdx, [rdx+8]; pbCertEncoded
0x180001ee1  call    cs:__imp_CertCreateCertificateContext
0x180001ee7  mov     r15, rax
0x180001eea  test    rax, rax
0x180001eed  jnz     short loc_180001F0D
0x180001eef  call    cs:__imp_GetLastError
0x180001ef5  mov     ebx, eax
0x180001ef7  test    eax, eax
0x180001ef9  jle     loc_180001F94
0x180001eff  movzx   ebx, ax
0x180001f02  or      ebx, 80070000h
0x180001f08  jmp     loc_180001F94
0x180001f0d  cmp     [rdi+8], r14d
0x180001f11  jz      short loc_180001F47
0x180001f13  lea     rax, [rsp+2A0h+var_248]
0x180001f18  mov     rdx, r15; struct _CERT_CONTEXT *
0x180001f1b  lea     rcx, [rdi+50h]; this
0x180001f1f  mov     [rsp+2A0h+var_280], rax; struct STRU *
0x180001f24  lea     r9, [rbp+1A0h+var_210]; struct STRU *
0x180001f28  lea     r8, [rsp+2A0h+var_258]; int *
0x180001f2d  call    ?Match@CERT_1TO1_MAPPER@@QEAAJPEBU_CERT_CONTEXT@@PEAHPEAVSTRU@@2@Z; CERT_1TO1_MAPPER::Match(_CERT_CONTEXT const *,int *,STRU *,STRU *)
0x180001f32  mov     ebx, eax
0x180001f34  test    eax, eax
0x180001f36  js      short loc_180001F88
0x180001f38  cmp     [rsp+2A0h+var_258], r14d
0x180001f3d  jz      short loc_180001F47
0x180001f3f  mov     r14d, 1
0x180001f45  jmp     short loc_180001F88
0x180001f47  cmp     [rdi+0Ch], r14d
0x180001f4b  jz      short loc_180001F86
0x180001f4d  lea     rax, [rsp+2A0h+var_254]
0x180001f52  mov     rdx, r15; struct _CERT_CONTEXT *
0x180001f55  mov     [rsp+2A0h+var_278], rax; int *
0x180001f5a  lea     rcx, [rdi+98h]; this
0x180001f61  lea     rax, [rsp+2A0h+var_248]
0x180001f66  lea     r9, [rbp+1A0h+var_210]; struct STRU *
0x180001f6a  mov     [rsp+2A0h+var_280], rax; struct STRU *
0x180001f6f  lea     r8, [rsp+2A0h+var_258]; int *
0x180001f74  call    ?Match@CERT_MANYTO1_MAPPER@@QEAAJPEBU_CERT_CONTEXT@@PEAHPEAVSTRU@@21@Z; CERT_MANYTO1_MAPPER::Match(_CERT_CONTEXT const *,int *,STRU *,STRU *,int *)
0x180001f79  mov     ebx, eax
0x180001f7b  test    eax, eax
0x180001f7d  js      short loc_180001F88
0x180001f7f  mov     r14d, [rsp+2A0h+var_258]
0x180001f84  jmp     short loc_180001F88
0x180001f86  xor     ebx, ebx
0x180001f88  mov     rcx, r15; pCertContext
0x180001f8b  call    cs:__imp_CertFreeCertificateContext
0x180001f91  xor     r15d, r15d
0x180001f94  test    ebx, ebx
0x180001f96  js      loc_18000223D
0x180001f9c  test    r14d, r14d
0x180001f9f  jnz     short loc_180001FAE
0x180001fa1  mov     dword ptr [r12], 1
0x180001fa9  jmp     loc_18000223D
0x180001fae  cmp     [rsp+2A0h+var_254], r15d
0x180001fb3  jz      short loc_18000202D
0x180001fb5  mov     rax, [rsi]
0x180001fb8  mov     rcx, rsi
0x180001fbb  mov     ebx, r15d
0x180001fbe  mov     rax, [rax+20h]
0x180001fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc7  mov     rcx, rax
0x180001fca  mov     rdx, [rax]
0x180001fcd  mov     rax, [rdx+8]
0x180001fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fd6  mov     rcx, rsi
0x180001fd9  mov     [rax+218h], r15w
0x180001fe1  mov     rax, [rsi]
0x180001fe4  mov     rax, [rax+20h]
0x180001fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fed  mov     r10, rax
0x180001ff0  mov     dword ptr [rsp+2A0h+var_270], r15d
0x180001ff5  mov     edx, 193h
0x180001ffa  mov     [rsp+2A0h+var_278], r15
0x180001fff  mov     r9d, 0Ch
0x180002005  mov     dword ptr [rsp+2A0h+var_280], r15d
0x18000200a  mov     rcx, [rax]
0x18000200d  lea     r8, aForbidden; "Forbidden"
0x180002014  mov     rax, [rcx+18h]
0x180002018  mov     rcx, r10
0x18000201b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002020  mov     dword ptr [r12], 2
0x180002028  jmp     loc_18000223D
0x18000202d  mov     r14d, [rdi+48h]
0x180002031  lea     rcx, [rbp+1A0h+var_1D0]; this
0x180002035  mov     r8, [rsp+2A0h+var_228]; unsigned __int16 *
0x18000203a  mov     r9d, r14d; unsigned int
0x18000203d  mov     rdx, [rbp+1A0h+var_1F0]; unsigned __int16 *
0x180002041  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180002046  mov     ebx, eax
0x180002048  test    eax, eax
0x18000204a  js      loc_18000223D
0x180002050  mov     rax, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180002057  mov     rcx, [rax]
0x18000205a  mov     rbx, [rcx+50h]
0x18000205e  mov     rcx, [rsi]
0x180002061  mov     rax, [rcx+110h]
0x180002068  mov     rcx, rsi
0x18000206b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002070  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180002077  lea     r9, [rsp+2A0h+var_260]
0x18000207c  mov     [rsp+2A0h+var_280], rax
0x180002081  lea     r8, [rbp+1A0h+var_1D0]
0x180002085  mov     rax, rbx
0x180002088  xor     edx, edx
0x18000208a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000208f  test    eax, eax
0x180002091  js      short loc_18000209E
0x180002093  cmp     [rsp+2A0h+var_260], r15
0x180002098  jnz     loc_180002167
0x18000209e  mov     rax, [rsi]
0x1800020a1  mov     rcx, rsi
0x1800020a4  mov     rax, [rax+18h]
0x1800020a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ad  mov     rdx, rax
0x1800020b0  mov     rcx, [rax]
0x1800020b3  mov     rax, [rcx+8]
0x1800020b7  mov     rcx, rdx
0x1800020ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020bf  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800020c6  mov     rbx, [rax+68h]
0x1800020ca  mov     rax, [rcx]
0x1800020cd  mov     rax, [rax+18h]
0x1800020d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020d6  mov     rcx, [rsp+2A0h+var_250]
0x1800020db  lea     rax, [rsp+2A0h+var_260]
0x1800020e0  mov     r8, [rsp+2A0h+var_228]; unsigned __int16 *
0x1800020e5  add     rcx, 10h; this
0x1800020e9  mov     rdx, [rbp+1A0h+var_1F0]; unsigned __int16 *
0x1800020ed  mov     r9d, r14d; unsigned int
0x1800020f0  mov     [rsp+2A0h+var_270], rax; struct IHttpTokenEntry **
0x1800020f5  mov     rax, [rdi+30h]
0x1800020f9  mov     [rsp+2A0h+var_278], rbx; struct sockaddr *
0x1800020fe  mov     [rsp+2A0h+var_280], rax; unsigned __int16 *
0x180002103  call    ?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z; IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)
0x180002108  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000210f  mov     ebx, eax
0x180002111  mov     rax, [rcx]
0x180002114  mov     rax, [rax+20h]
0x180002118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000211d  test    ebx, ebx
0x18000211f  js      loc_18000223D
0x180002125  mov     rax, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000212c  mov     rcx, [rax]
0x18000212f  mov     rbx, [rcx+50h]
0x180002133  mov     rcx, [rsi]
0x180002136  mov     rax, [rcx+110h]
0x18000213d  mov     rcx, rsi
0x180002140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002145  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000214c  lea     r9, [rsp+2A0h+var_260]
0x180002151  mov     [rsp+2A0h+var_280], rax
0x180002156  lea     r8, [rbp+1A0h+var_1D0]
0x18000215a  mov     rax, rbx
0x18000215d  mov     edx, 1
0x180002162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002167  mov     ecx, 88h; Size
0x18000216c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002171  mov     rdi, rax
0x180002174  test    rax, rax
0x180002177  jz      loc_180002222
0x18000217d  lea     rax, ??_7IISCERTMAP_USER_CONTEXT@@6B@; const IISCERTMAP_USER_CONTEXT::`vftable'
0x180002184  lea     rcx, [rdi+18h]
0x180002188  mov     [rdi], rax
0x18000218b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002191  lea     rcx, [rdi+50h]
0x180002195  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000219b  mov     [rdi+10h], r15
0x18000219f  mov     dword ptr [rdi+8], 1
0x1800021a6  mov     r14, [rsp+2A0h+var_260]
0x1800021ab  test    r14, r14
0x1800021ae  jz      short loc_1800021F8
0x1800021b0  lea     rcx, [rdi+18h]
0x1800021b4  lea     rdx, [rbp+1A0h+var_210]
0x1800021b8  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x1800021be  mov     ebx, eax
0x1800021c0  test    eax, eax
0x1800021c2  jns     short loc_1800021CB
0x1800021c4  mov     r14, [rsp+2A0h+var_260]
0x1800021c9  jmp     short loc_1800021FD
0x1800021cb  lea     rcx, [rdi+50h]
0x1800021cf  lea     rdx, [rsp+2A0h+var_248]
0x1800021d4  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x1800021da  mov     ebx, eax
0x1800021dc  test    eax, eax
0x1800021de  js      short loc_1800021C4
0x1800021e0  mov     [rdi+10h], r14
0x1800021e4  mov     rdx, rdi; struct IHttpUser *
0x1800021e7  mov     rcx, rsi; struct IHttpContext *
0x1800021ea  mov     [r13+0], rdi
0x1800021ee  call    ?TraceAuthSucceeded@@YAJPEAVIHttpContext@@PEAVIHttpUser@@H@Z; TraceAuthSucceeded(IHttpContext *,IHttpUser *,int)
0x1800021f3  mov     ebx, r15d
0x1800021f6  jmp     short loc_18000223D
0x1800021f8  mov     ebx, 80070057h
0x1800021fd  mov     rax, [r14]
0x180002200  mov     rcx, r14
0x180002203  mov     rax, [rax+10h]
0x180002207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000220c  mov     [rsp+2A0h+var_260], r15
0x180002211  mov     rcx, rdi
0x180002214  mov     rax, [rdi]
0x180002217  mov     rax, [rax+38h]
0x18000221b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002220  jmp     short loc_18000223D
0x180002222  mov     rcx, [rsp+2A0h+var_260]
0x180002227  mov     rax, [rcx]
0x18000222a  mov     rax, [rax+10h]
0x18000222e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002233  mov     [rsp+2A0h+var_260], r15
0x180002238  mov     ebx, 80070008h
0x18000223d  mov     eax, [rbp+1A0h+var_218]
0x180002240  test    eax, eax
0x180002242  jz      short loc_18000225B
0x180002244  add     eax, eax
0x180002246  mov     ecx, eax
0x180002248  mov     rax, [rsp+2A0h+var_228]
0x18000224d  jz      short loc_18000225B
0x18000224f  mov     [rax], r15b
0x180002252  inc     rax
0x180002255  sub     rcx, 1
  ... truncated ...
```
