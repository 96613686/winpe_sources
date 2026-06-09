# SSPI_AUTH_PROVIDER::OnAccessDenied(IHttpContext *)

- ea: `0x1800048f0`
- end: `0x180004f7a`
- name: `?OnAccessDenied@SSPI_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@@Z`
- size: `1674`
- prototype: `__int64 __fastcall(SSPI_AUTH_PROVIDER *this, struct IHttpContext *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001064`
- `0x1800048f0`
- `0x180005eac`
- `0x1800066cc`
- `0x180007d34`
- `0x180008480`
- `0x180008b46`
- `0x180008b5e`
- `0x180008ba0`
- `0x180009010`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x180004f30`
- `SspiCli!FreeCredentialsHandle` at `0x180004f30`
- `SspiCli!DeleteSecurityContext` at `0x180004c32`
- `SspiCli!DeleteSecurityContext` at `0x180004c32`
- `SspiCli!AcceptSecurityContext` at `0x180004b72`
- `SspiCli!AcceptSecurityContext` at `0x180004c1e`
- `SspiCli!AcceptSecurityContext` at `0x180004b72`
- `SspiCli!AcceptSecurityContext` at `0x180004c1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dcf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004d07`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004d1d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004de8`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004e03`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004e1c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004d07`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004d1d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004de8`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004e03`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004e1c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004a7d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004a7d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004d13`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004df9`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004e12`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004f47`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004d13`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004df9`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004e12`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004f47`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180004f3d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180004f3d`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x1800049b6`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x1800049b6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004ab2`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004bc1`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004ab2`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004bc1`
- `iisutil!uuencode` at `0x180004c92`
- `iisutil!uuencode` at `0x180004c92`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180004caf`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180004caf`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004c68`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004c68`

## pseudocode

```c
__int64 __fastcall SSPI_AUTH_PROVIDER::OnAccessDenied(SSPI_AUTH_PROVIDER *this, struct IHttpContext *a2)
{
  __int64 v2; // rax
  struct SSPI_CREDENTIAL *v3; // r14
  __int64 v5; // rax
  __int64 (__fastcall ***v6)(_QWORD, void *); // rax
  __int64 v7; // rax
  unsigned int *v8; // r13
  SSPI_AUTH_PROVIDER *v9; // rcx
  __int64 result; // rax
  int ReferencedCredential; // esi
  __int64 (__fastcall ***v12)(_QWORD, void *); // rax
  __int64 v13; // rdi
  const char *v14; // rax
  __int64 v15; // rdx
  signed __int64 v16; // r8
  SSPI_APP_CONTEXT *v17; // r15
  const char *v18; // rbx
  const char *v19; // rax
  int v20; // ecx
  const char *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rax
  signed int LastError; // eax
  __int64 v27; // rax
  __int64 v28; // rdi
  void *v29; // rbx
  unsigned int v30; // ecx
  __int64 v31; // rdx
  unsigned int fContextReq; // [rsp+50h] [rbp-B0h] BYREF
  struct SSPI_CREDENTIAL *Block; // [rsp+58h] [rbp-A8h] BYREF
  SSPI_APP_CONTEXT *pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h] BYREF
  __int128 v36; // [rsp+70h] [rbp-90h] BYREF
  struct _SecBufferDesc pInput; // [rsp+80h] [rbp-80h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+90h] [rbp-70h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h]
  struct _SecBuffer v41; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v42[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v43; // [rsp+E0h] [rbp-20h]
  unsigned int v44; // [rsp+E8h] [rbp-18h]
  __int16 v45; // [rsp+ECh] [rbp-14h]
  _BYTE v46[32]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v47; // [rsp+110h] [rbp+10h]
  unsigned __int16 v48; // [rsp+120h] [rbp+20h]
  _QWORD v49[4]; // [rsp+128h] [rbp+28h] BYREF
  const char *v50; // [rsp+148h] [rbp+48h]
  int v51; // [rsp+150h] [rbp+50h]
  __int16 v52; // [rsp+154h] [rbp+54h]
  struct _SecHandle phContext; // [rsp+158h] [rbp+58h] BYREF
  char v54[256]; // [rsp+170h] [rbp+70h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = 0;
  Block = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v2 + 160))(a2);
  v6 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v7 = (**v6)(v6, s_ModuleId);
  pfContextAttr = 0;
  v8 = (unsigned int *)v7;
  result = SSPI_AUTH_PROVIDER::SetupParsedAppContext(v9, a2, &pfContextAttr);
  ReferencedCredential = result;
  if ( (int)result >= 0 )
  {
    v12 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
    v40 = (**v12)(v12, s_ModuleId);
    v13 = v40;
    v14 = MULTISZA::First((MULTISZA *)(v8 + 4));
    v17 = pfContextAttr;
    v18 = v14;
    if ( v14 )
    {
      do
      {
        if ( !v13 )
          goto LABEL_60;
        v19 = *(const char **)(v13 + 40);
        v16 = v18 - v19;
        do
        {
          v20 = (unsigned __int8)v19[v16];
          v15 = (unsigned int)*(unsigned __int8 *)v19 - v20;
          if ( (_DWORD)v15 )
            break;
          ++v19;
        }
        while ( v20 );
        if ( (_DWORD)v15 || !*(_DWORD *)(v13 + 128) )
        {
LABEL_60:
          if ( !strcmp_0(v18, "Negotiate") && v8[35] && !*((_DWORD *)v17 + 2) )
          {
            v42[0] = 0;
            v44 = 32;
            v45 = 256;
            v43 = v42;
            LODWORD(pfContextAttr) = 0;
            ptsExpiry.QuadPart = 0;
            pInput = 0;
            v41 = 0;
            pOutput = 0;
            v36 = 0;
            phContext = 0;
            STRA::STRA((STRA *)v46, v54, 0x100u);
            v35 = 0;
            ReferencedCredential = SSPI_CREDENTIAL::GetReferencedCredential(v18, &Block, (struct MULTISZ *)(v8 + 18));
            if ( ReferencedCredential < 0 )
              goto LABEL_48;
            v3 = Block;
            if ( !BUFFER::Resize((BUFFER *)v42, *((_DWORD *)Block + 54)) )
            {
LABEL_46:
              ReferencedCredential = -2147024888;
              goto LABEL_47;
            }
            pOutput.ulVersion = 0;
            pOutput.pBuffers = (PSecBuffer)&v36;
            *((_QWORD *)&v36 + 1) = v43;
            *(_QWORD *)&v36 = v44 | 0x200000000LL;
            pInput.pBuffers = &v41;
            *(_QWORD *)&pInput.ulVersion = 0;
            pOutput.cBuffers = 1;
            fContextReq = 32769;
            ReferencedCredential = SSPI_APP_CONTEXT::AdjustFlagsForCbt(v17, a2, &fContextReq, &v41, &v35);
            if ( ReferencedCredential < 0 )
              goto LABEL_47;
            if ( v35 )
              ++pInput.cBuffers;
            ReferencedCredential = AcceptSecurityContext(
                                     (PCredHandle)((char *)v3 + 200),
                                     0,
                                     &pInput,
                                     fContextReq,
                                     0x10u,
                                     &phContext,
                                     &pOutput,
                                     (unsigned int *)&pfContextAttr,
                                     &ptsExpiry);
            if ( ReferencedCredential == -2146893022 )
            {
              SSPI_CREDENTIAL::RemoveCredentialFromCache(v3);
              Block = 0;
              ReferencedCredential = SSPI_CREDENTIAL::GetReferencedCredential(v18, &Block, (struct MULTISZ *)(v8 + 18));
              if ( ReferencedCredential < 0 )
              {
LABEL_48:
                STRA::~STRA((STRA *)v46);
                BUFFER::~BUFFER((BUFFER *)v42);
                v3 = Block;
                goto LABEL_51;
              }
              v3 = Block;
              if ( !BUFFER::Resize((BUFFER *)v42, *((_DWORD *)Block + 54)) )
                goto LABEL_46;
              *((_QWORD *)&v36 + 1) = v43;
              LODWORD(v36) = v44;
              ReferencedCredential = AcceptSecurityContext(
                                       (PCredHandle)((char *)v3 + 200),
                                       0,
                                       &pInput,
                                       fContextReq,
                                       0x10u,
                                       &phContext,
                                       &pOutput,
                                       (unsigned int *)&pfContextAttr,
                                       &ptsExpiry);
            }
            if ( ReferencedCredential < 0 )
              goto LABEL_47;
            DeleteSecurityContext(&phContext);
            if ( (_DWORD)v36 )
            {
              v49[0] = 0;
              v50 = (const char *)v49;
              v51 = 32;
              v52 = 256;
              ReferencedCredential = STRA::Copy((STRA *)v46, "Nego2 ");
              if ( ReferencedCredential < 0 )
                goto LABEL_45;
              if ( *((_DWORD *)v3 + 55) )
              {
                if ( !uuencode(*((unsigned __int8 **)&v36 + 1), v36, (struct BUFFER *)v49, 0) )
                {
                  LastError = GetLastError();
                  ReferencedCredential = LastError;
                  if ( LastError > 0 )
                    ReferencedCredential = (unsigned __int16)LastError | 0x80070000;
LABEL_45:
                  BUFFER::~BUFFER((BUFFER *)v49);
LABEL_47:
                  STRA::~STRA((STRA *)v46);
                  BUFFER::~BUFFER((BUFFER *)v42);
                  goto LABEL_51;
                }
                v21 = v50;
              }
              else
              {
                v21 = (const char *)*((_QWORD *)&v36 + 1);
              }
              ReferencedCredential = STRA::Append((STRA *)v46, v21);
              if ( ReferencedCredential < 0 )
                goto LABEL_45;
              v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
              ReferencedCredential = (*(__int64 (__fastcall **)(__int64, const char *, __int64, _QWORD, _DWORD))(*(_QWORD *)v22 + 40LL))(
                                       v22,
                                       "WWW-Authenticate",
                                       v47,
                                       v48,
                                       0);
              if ( ReferencedCredential < 0 )
                goto LABEL_45;
              BUFFER::~BUFFER((BUFFER *)v49);
            }
            STRA::~STRA((STRA *)v46);
            BUFFER::~BUFFER((BUFFER *)v42);
            v13 = v40;
          }
          v23 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
          v24 = -1;
          do
            ++v24;
          while ( v18[v24] );
          ReferencedCredential = (*(__int64 (__fastcall **)(__int64, const char *, const char *))(*(_QWORD *)v23 + 40LL))(
                                   v23,
                                   "WWW-Authenticate",
                                   v18);
          if ( ReferencedCredential < 0 )
            goto LABEL_51;
        }
        v25 = -1;
        do
          ++v25;
        while ( v18[v25] );
        v18 += v25 + 1;
      }
      while ( *v18 );
    }
    if ( !*((_DWORD *)v17 + 2) )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)v17 + 42, 1, 0) )
        goto LABEL_51;
LABEL_50:
      v27 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64, signed __int64, __int64))(*(_QWORD *)a2 + 32LL))(
              a2,
              v15,
              v16,
              1);
      v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
      v29 = (void *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 144LL))(
                      a2,
                      16 * ((unsigned int)*(unsigned __int16 *)(v28 + 552) + 2));
      memcpy_0(v29, *(const void **)(v28 + 560), 16LL * *(unsigned __int16 *)(v28 + 552));
      v30 = *(unsigned __int16 *)(v28 + 552);
      *(_QWORD *)(v28 + 560) = v29;
      v31 = 2LL * v30;
      *(_WORD *)(v28 + 552) = v30 + 1;
      *((_QWORD *)v29 + v31 + 1) = (char *)v17 + 16;
      *((_DWORD *)v29 + 2 * v31) = 1;
      *((_DWORD *)v29 + 2 * v31 + 1) = 64;
      ++*(_WORD *)(v28 + 552);
      *((_QWORD *)v29 + v31 + 3) = (char *)v17 + 80;
      *((_DWORD *)v29 + 2 * v31 + 4) = 3;
      *((_DWORD *)v29 + 2 * v31 + 5) = 24;
      goto LABEL_51;
    }
    v15 = v8[32];
    if ( (~*((_DWORD *)v17 + 5) & (unsigned int)v15) != 0 )
    {
      _m_prefetchw((char *)v17 + 20);
      do
        _InterlockedCompareExchange(
          (volatile signed __int32 *)v17 + 5,
          *((_DWORD *)v17 + 5) | v15,
          *((_DWORD *)v17 + 5));
      while ( (~*((_DWORD *)v17 + 5) & (unsigned int)v15) != 0 );
      goto LABEL_50;
    }
LABEL_51:
    if ( v3 && _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 1, 0xFFFFFFFF) == 1 )
    {
      *(_DWORD *)v3 = 1396917094;
      if ( *((_QWORD *)v3 + 25) != -1 && *((_QWORD *)v3 + 26) != -1 )
        FreeCredentialsHandle((PCredHandle)((char *)v3 + 200));
      MULTISZ::~MULTISZ((struct SSPI_CREDENTIAL *)((char *)v3 + 144));
      STRA::~STRA((struct SSPI_CREDENTIAL *)((char *)v3 + 8));
      operator delete(v3);
    }
    return (unsigned int)ReferencedCredential;
  }
  return result;
}

```

## disassembly

```asm
0x1800048f0  push    rbp
0x1800048f2  push    rbx
0x1800048f3  push    rsi
0x1800048f4  push    rdi
0x1800048f5  push    r12
0x1800048f7  push    r13
0x1800048f9  push    r14
0x1800048fb  push    r15
0x1800048fd  lea     rbp, [rsp-188h]
0x180004905  sub     rsp, 288h
0x18000490c  mov     rax, cs:__security_cookie
0x180004913  xor     rax, rsp
0x180004916  mov     [rbp+1C0h+var_50], rax
0x18000491d  mov     rax, [rdx]
0x180004920  xor     r14d, r14d
0x180004923  mov     rcx, rdx
0x180004926  mov     [rsp+2C0h+Block], r14
0x18000492b  mov     r12, rdx
0x18000492e  mov     rax, [rax+0A0h]
0x180004935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000493a  mov     rdx, rax
0x18000493d  mov     rcx, [rax]
0x180004940  mov     rax, [rcx+18h]
0x180004944  mov     rcx, rdx
0x180004947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494c  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x180004953  mov     r8, rax
0x180004956  mov     rcx, [rax]
0x180004959  mov     rax, [rcx]
0x18000495c  mov     rcx, r8
0x18000495f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004964  lea     r8, [rsp+2C0h+var_260]; struct SSPI_APP_CONTEXT **
0x180004969  mov     [rsp+2C0h+var_260], r14
0x18000496e  mov     rdx, r12; struct IHttpContext *
0x180004971  mov     r13, rax
0x180004974  call    ?SetupParsedAppContext@SSPI_AUTH_PROVIDER@@QEAAJPEAVIHttpContext@@PEAPEAVSSPI_APP_CONTEXT@@@Z; SSPI_AUTH_PROVIDER::SetupParsedAppContext(IHttpContext *,SSPI_APP_CONTEXT * *)
0x180004979  mov     esi, eax
0x18000497b  test    eax, eax
0x18000497d  js      loc_180004F57
0x180004983  mov     rax, [r12]
0x180004987  mov     rcx, r12
0x18000498a  mov     rax, [rax+38h]
0x18000498e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004993  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x18000499a  mov     r8, rax
0x18000499d  mov     rcx, [rax]
0x1800049a0  mov     rax, [rcx]
0x1800049a3  mov     rcx, r8
0x1800049a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ab  lea     rcx, [r13+10h]
0x1800049af  mov     [rbp+1C0h+var_218], rax
0x1800049b3  mov     rdi, rax
0x1800049b6  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x1800049bc  mov     r15, [rsp+2C0h+var_260]
0x1800049c1  lea     r9d, [r14+1]
0x1800049c5  mov     rbx, rax
0x1800049c8  test    rax, rax
0x1800049cb  jz      loc_180004D90
0x1800049d1  test    rdi, rdi
0x1800049d4  jz      short loc_180004A03
0x1800049d6  mov     rax, [rdi+28h]
0x1800049da  mov     r8, rbx
0x1800049dd  sub     r8, rax
0x1800049e0  movzx   edx, byte ptr [rax]
0x1800049e3  movzx   ecx, byte ptr [rax+r8]
0x1800049e8  sub     edx, ecx
0x1800049ea  jnz     short loc_1800049F3
0x1800049ec  add     rax, r9
0x1800049ef  test    ecx, ecx
0x1800049f1  jnz     short loc_1800049E0
0x1800049f3  test    edx, edx
0x1800049f5  jnz     short loc_180004A03
0x1800049f7  cmp     [rdi+80h], edx
0x1800049fd  jnz     loc_180004D74
0x180004a03  lea     rdx, aNegotiate_0; "Negotiate"
0x180004a0a  mov     rcx, rbx; Str1
0x180004a0d  call    strcmp_0
0x180004a12  xor     esi, esi
0x180004a14  test    eax, eax
0x180004a16  jnz     loc_180004D27
0x180004a1c  cmp     [r13+8Ch], esi
0x180004a23  jz      loc_180004D27
0x180004a29  cmp     [r15+8], esi
0x180004a2d  jnz     loc_180004D27
0x180004a33  xorps   xmm0, xmm0
0x180004a36  mov     [rbp+1C0h+var_200], rsi
0x180004a3a  xorps   xmm1, xmm1
0x180004a3d  mov     [rbp+1C0h+var_1D8], 20h ; ' '
0x180004a44  lea     rax, [rbp+1C0h+var_200]
0x180004a48  mov     [rbp+1C0h+var_1D4], 100h
0x180004a4e  mov     r8d, 100h
0x180004a54  mov     [rbp+1C0h+var_1E0], rax
0x180004a58  lea     rdx, [rbp+1C0h+var_150]
0x180004a5c  mov     dword ptr [rsp+2C0h+var_260], esi
0x180004a60  lea     rcx, [rbp+1C0h+var_1D0]
0x180004a64  mov     qword ptr [rbp+1C0h+var_230], rsi
0x180004a68  movups  xmmword ptr [rbp+1C0h+pInput.ulVersion], xmm0
0x180004a6c  movups  xmmword ptr [rbp+1C0h+var_210.cbBuffer], xmm1
0x180004a70  movups  xmmword ptr [rbp+1C0h+var_228.ulVersion], xmm0
0x180004a74  movups  [rsp+2C0h+var_250], xmm1
0x180004a79  movups  xmmword ptr [rbp+1C0h+phContext.dwLower], xmm0
0x180004a7d  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180004a83  lea     r8, [r13+48h]; struct MULTISZ *
0x180004a87  mov     [rsp+2C0h+var_258], esi
0x180004a8b  lea     rdx, [rsp+2C0h+Block]; struct SSPI_CREDENTIAL **
0x180004a90  mov     rcx, rbx; char *
0x180004a93  call    ?GetReferencedCredential@SSPI_CREDENTIAL@@SAJPEBDPEAPEAV1@PEAVMULTISZ@@@Z; SSPI_CREDENTIAL::GetReferencedCredential(char const *,SSPI_CREDENTIAL * *,MULTISZ *)
0x180004a98  mov     esi, eax
0x180004a9a  test    eax, eax
0x180004a9c  js      loc_180004E0E
0x180004aa2  mov     r14, [rsp+2C0h+Block]
0x180004aa7  lea     rcx, [rbp+1C0h+var_200]
0x180004aab  mov     edx, [r14+0D8h]
0x180004ab2  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180004ab8  xor     ecx, ecx
0x180004aba  test    al, al
0x180004abc  jz      loc_180004DF0
0x180004ac2  lea     rax, [rsp+2C0h+var_250]
0x180004ac7  mov     [rbp+1C0h+var_228.ulVersion], ecx
0x180004aca  mov     [rbp+1C0h+var_228.pBuffers], rax
0x180004ace  lea     r9, [rbp+1C0h+var_210]; struct _SecBuffer *
0x180004ad2  mov     rax, [rbp+1C0h+var_1E0]
0x180004ad6  lea     r8, [rsp+2C0h+fContextReq]; unsigned int *
0x180004adb  mov     qword ptr [rsp+2C0h+var_250+8], rax
0x180004ae0  mov     rdx, r12; struct IHttpContext *
0x180004ae3  mov     eax, [rbp+1C0h+var_1D8]
0x180004ae6  mov     dword ptr [rsp+2C0h+var_250], eax
0x180004aea  lea     rax, [rbp+1C0h+var_210]
0x180004aee  mov     [rbp+1C0h+pInput.pBuffers], rax
0x180004af2  lea     rax, [rsp+2C0h+var_258]
0x180004af7  mov     qword ptr [rbp+1C0h+pInput.ulVersion], rcx
0x180004afb  mov     rcx, r15; this
0x180004afe  mov     qword ptr [rsp+2C0h+TargetDataRep], rax; int *
0x180004b03  mov     [rbp+1C0h+var_228.cBuffers], 1
0x180004b0a  mov     dword ptr [rsp+2C0h+var_250+4], 2
0x180004b12  mov     [rsp+2C0h+fContextReq], 8001h
0x180004b1a  call    ?AdjustFlagsForCbt@SSPI_APP_CONTEXT@@QEAAJPEAVIHttpContext@@PEAKPEAU_SecBuffer@@PEAH@Z; SSPI_APP_CONTEXT::AdjustFlagsForCbt(IHttpContext *,ulong *,_SecBuffer *,int *)
0x180004b1f  mov     esi, eax
0x180004b21  test    eax, eax
0x180004b23  js      loc_180004DF5
0x180004b29  cmp     [rsp+2C0h+var_258], 0
0x180004b2e  jz      short loc_180004B33
0x180004b30  inc     [rbp+1C0h+pInput.cBuffers]
0x180004b33  mov     r9d, [rsp+2C0h+fContextReq]; fContextReq
0x180004b38  lea     rax, [rbp+1C0h+var_230]
0x180004b3c  mov     [rsp+2C0h+ptsExpiry], rax; ptsExpiry
0x180004b41  lea     rcx, [r14+0C8h]; phCredential
0x180004b48  lea     rax, [rsp+2C0h+var_260]
0x180004b4d  xor     edx, edx; phContext
0x180004b4f  mov     [rsp+2C0h+pfContextAttr], rax; pfContextAttr
0x180004b54  lea     r8, [rbp+1C0h+pInput]; pInput
0x180004b58  lea     rax, [rbp+1C0h+var_228]
0x180004b5c  mov     [rsp+2C0h+pOutput], rax; pOutput
0x180004b61  lea     rax, [rbp+1C0h+phContext]
0x180004b65  mov     [rsp+2C0h+phNewContext], rax; phNewContext
0x180004b6a  mov     [rsp+2C0h+TargetDataRep], 10h; TargetDataRep
0x180004b72  call    cs:__imp_AcceptSecurityContext
0x180004b78  mov     esi, eax
0x180004b7a  cmp     eax, 80090322h
0x180004b7f  jnz     loc_180004C26
0x180004b85  mov     rcx, r14; Block
0x180004b88  call    ?RemoveCredentialFromCache@SSPI_CREDENTIAL@@SAXPEAV1@@Z; SSPI_CREDENTIAL::RemoveCredentialFromCache(SSPI_CREDENTIAL *)
0x180004b8d  lea     r8, [r13+48h]; struct MULTISZ *
0x180004b91  mov     [rsp+2C0h+Block], 0
0x180004b9a  lea     rdx, [rsp+2C0h+Block]; struct SSPI_CREDENTIAL **
0x180004b9f  mov     rcx, rbx; char *
0x180004ba2  call    ?GetReferencedCredential@SSPI_CREDENTIAL@@SAJPEBDPEAPEAV1@PEAVMULTISZ@@@Z; SSPI_CREDENTIAL::GetReferencedCredential(char const *,SSPI_CREDENTIAL * *,MULTISZ *)
0x180004ba7  mov     esi, eax
0x180004ba9  test    eax, eax
0x180004bab  js      loc_180004E0E
0x180004bb1  mov     r14, [rsp+2C0h+Block]
0x180004bb6  lea     rcx, [rbp+1C0h+var_200]
0x180004bba  mov     edx, [r14+0D8h]
0x180004bc1  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180004bc7  test    al, al
0x180004bc9  jz      loc_180004DF0
0x180004bcf  mov     rax, [rbp+1C0h+var_1E0]
0x180004bd3  lea     rcx, [r14+0C8h]; phCredential
0x180004bda  mov     r9d, [rsp+2C0h+fContextReq]; fContextReq
0x180004bdf  lea     r8, [rbp+1C0h+pInput]; pInput
0x180004be3  mov     qword ptr [rsp+2C0h+var_250+8], rax
0x180004be8  xor     edx, edx; phContext
0x180004bea  mov     eax, [rbp+1C0h+var_1D8]
0x180004bed  mov     dword ptr [rsp+2C0h+var_250], eax
0x180004bf1  lea     rax, [rbp+1C0h+var_230]
0x180004bf5  mov     [rsp+2C0h+ptsExpiry], rax; ptsExpiry
0x180004bfa  lea     rax, [rsp+2C0h+var_260]
0x180004bff  mov     [rsp+2C0h+pfContextAttr], rax; pfContextAttr
0x180004c04  lea     rax, [rbp+1C0h+var_228]
0x180004c08  mov     [rsp+2C0h+pOutput], rax; pOutput
0x180004c0d  lea     rax, [rbp+1C0h+phContext]
0x180004c11  mov     [rsp+2C0h+phNewContext], rax; phNewContext
0x180004c16  mov     [rsp+2C0h+TargetDataRep], 10h; TargetDataRep
0x180004c1e  call    cs:__imp_AcceptSecurityContext
0x180004c24  mov     esi, eax
0x180004c26  test    esi, esi
0x180004c28  js      loc_180004DF5
0x180004c2e  lea     rcx, [rbp+1C0h+phContext]; phContext
0x180004c32  call    cs:__imp_DeleteSecurityContext
0x180004c38  xor     esi, esi
0x180004c3a  cmp     dword ptr [rsp+2C0h+var_250], esi
0x180004c3e  jz      loc_180004D0F
0x180004c44  lea     rax, [rbp+1C0h+var_198]
0x180004c48  mov     [rbp+1C0h+var_198], rsi
0x180004c4c  lea     rdx, aNego2; "Nego2 "
0x180004c53  mov     [rbp+1C0h+var_178], rax
0x180004c57  lea     rcx, [rbp+1C0h+var_1D0]
0x180004c5b  mov     [rbp+1C0h+var_170], 20h ; ' '
0x180004c62  mov     [rbp+1C0h+var_16C], 100h
0x180004c68  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004c6e  mov     esi, eax
0x180004c70  test    eax, eax
0x180004c72  js      loc_180004DE4
0x180004c78  cmp     dword ptr [r14+0DCh], 0
0x180004c80  jz      short loc_180004CA6
0x180004c82  mov     edx, dword ptr [rsp+2C0h+var_250]
0x180004c86  lea     r8, [rbp+1C0h+var_198]
0x180004c8a  mov     rcx, qword ptr [rsp+2C0h+var_250+8]
0x180004c8f  xor     r9d, r9d
0x180004c92  call    cs:__imp_?uuencode@@YAHPEAEKPEAVBUFFER@@H@Z; uuencode(uchar *,ulong,BUFFER *,int)
0x180004c98  test    eax, eax
0x180004c9a  jz      loc_180004DCF
0x180004ca0  mov     rdx, [rbp+1C0h+var_178]
0x180004ca4  jmp     short loc_180004CAB
0x180004ca6  mov     rdx, qword ptr [rsp+2C0h+var_250+8]
0x180004cab  lea     rcx, [rbp+1C0h+var_1D0]
0x180004caf  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180004cb5  mov     esi, eax
0x180004cb7  test    eax, eax
0x180004cb9  js      loc_180004DE4
0x180004cbf  mov     rax, [r12]
0x180004cc3  mov     rcx, r12
0x180004cc6  mov     rax, [rax+20h]
0x180004cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ccf  movzx   r9d, [rbp+1C0h+var_1A0]
0x180004cd4  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x180004cdb  mov     r8, [rbp+1C0h+var_1B0]
0x180004cdf  mov     r10, rax
0x180004ce2  mov     [rsp+2C0h+TargetDataRep], 0
0x180004cea  mov     rcx, [rax]
0x180004ced  mov     rax, [rcx+28h]
0x180004cf1  mov     rcx, r10
0x180004cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf9  lea     rcx, [rbp+1C0h+var_198]
0x180004cfd  mov     esi, eax
0x180004cff  test    eax, eax
0x180004d01  js      loc_180004DE8
0x180004d07  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180004d0d  xor     esi, esi
0x180004d0f  lea     rcx, [rbp+1C0h+var_1D0]
0x180004d13  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180004d19  lea     rcx, [rbp+1C0h+var_200]
0x180004d1d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180004d23  mov     rdi, [rbp+1C0h+var_218]
0x180004d27  mov     rax, [r12]
0x180004d2b  mov     rcx, r12
0x180004d2e  mov     rax, [rax+20h]
0x180004d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d37  or      r9, 0FFFFFFFFFFFFFFFFh
0x180004d3b  mov     rcx, [rax]
0x180004d3e  mov     r10, [rcx+28h]
0x180004d42  inc     r9
0x180004d45  cmp     [rbx+r9], sil
0x180004d49  jnz     short loc_180004D42
0x180004d4b  mov     rcx, rax
0x180004d4e  mov     [rsp+2C0h+TargetDataRep], esi
0x180004d52  mov     rax, r10
0x180004d55  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x180004d5c  mov     r8, rbx
0x180004d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d64  mov     esi, eax
0x180004d66  test    eax, eax
0x180004d68  js      loc_180004EFA
0x180004d6e  mov     r9d, 1
0x180004d74  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d78  inc     rax
0x180004d7b  cmp     byte ptr [rbx+rax], 0
0x180004d7f  jnz     short loc_180004D78
0x180004d81  inc     rbx
0x180004d84  add     rbx, rax
0x180004d87  cmp     byte ptr [rbx], 0
0x180004d8a  jnz     loc_1800049D1
0x180004d90  cmp     dword ptr [r15+8], 0
0x180004d95  jz      loc_180004E2C
0x180004d9b  mov     eax, [r15+14h]
0x180004d9f  mov     edx, [r13+80h]
0x180004da6  not     eax
0x180004da8  test    edx, eax
0x180004daa  jz      loc_180004EFA
0x180004db0  prefetchw byte ptr [r15+14h]
0x180004db5  mov     eax, [r15+14h]
0x180004db9  mov     ecx, edx
0x180004dbb  or      ecx, eax
0x180004dbd  lock cmpxchg [r15+14h], ecx
0x180004dc3  mov     ecx, [r15+14h]
0x180004dc7  not     ecx
0x180004dc9  test    edx, ecx
0x180004dcb  jnz     short loc_180004DB5
0x180004dcd  jmp     short loc_180004E3D
0x180004dcf  call    cs:__imp_GetLastError
  ... truncated ...
```
