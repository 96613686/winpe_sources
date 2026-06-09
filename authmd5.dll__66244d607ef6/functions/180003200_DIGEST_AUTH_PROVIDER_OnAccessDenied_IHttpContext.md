# DIGEST_AUTH_PROVIDER::OnAccessDenied(IHttpContext *)

- ea: `0x180003200`
- end: `0x1800037fc`
- name: `?OnAccessDenied@DIGEST_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@@Z`
- size: `1532`
- prototype: `__int64 __fastcall(DIGEST_AUTH_PROVIDER *__hidden this, struct IHttpContext *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001064`
- `0x180003200`
- `0x1800048d0`
- `0x180005a64`
- `0x1800065c6`
- `0x180006600`
- `0x180007010`

## import_xrefs

- `SspiCli!AcceptSecurityContext` at `0x180003630`
- `SspiCli!AcceptSecurityContext` at `0x180003630`
- `SspiCli!DeleteSecurityContext` at `0x18000373d`
- `SspiCli!DeleteSecurityContext` at `0x18000373d`
- `SspiCli!FreeCredentialsHandle` at `0x180003775`
- `SspiCli!FreeCredentialsHandle` at `0x180003775`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000378c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800037a8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800037b5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800037bf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000378c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800037a8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800037b5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800037bf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800037c9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800037c9`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180003782`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180003782`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003272`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003272`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003265`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003289`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003265`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003289`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800032ae`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800032ae`
- `iisutil!PuDbgPrint` at `0x18000332b`
- `iisutil!PuDbgPrint` at `0x18000332b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003340`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003340`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003405`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800036a8`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003405`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800036a8`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003481`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003481`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000352a`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000352a`
- `iisutil!WriteRefTraceLogEx` at `0x180003670`
- `iisutil!WriteRefTraceLogEx` at `0x180003733`
- `iisutil!WriteRefTraceLogEx` at `0x180003670`
- `iisutil!WriteRefTraceLogEx` at `0x180003733`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800036c4`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800036c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000379e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000379e`

## string_xrefs

- `0x180003318`: `DIGEST_AUTH_PROVIDER::OnAccessDenied`
- `0x18000331f`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\digest_auth\digest_auth.cxx`
- `0x1800034a4`: `Error copying the URL.  hr = %x\n`
- `0x18000354d`: `Error reading the realm.  hr = %x\n`

## pseudocode

```c
__int64 __fastcall DIGEST_AUTH_PROVIDER::OnAccessDenied(DIGEST_AUTH_PROVIDER *this, struct IHttpContext *a2)
{
  const char *v4; // rcx
  struct MULTISZ *v5; // r8
  int ReferencedCredential; // eax
  volatile signed __int32 *v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 (__fastcall *v10)(struct IHttpContext *); // rax
  __int64 v11; // rax
  const char *v12; // rax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  __int64 (__fastcall *v19)(struct IHttpContext *); // rax
  __int64 v20; // rax
  __int64 (__fastcall ***v21)(_QWORD, void *); // rax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  __int64 (__fastcall ***v25)(_QWORD, void *); // rax
  __int64 v26; // rax
  unsigned int v27; // ebx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  unsigned int pfContextAttr; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+60h] [rbp-A0h] BYREF
  struct _SecBufferDesc pInput; // [rsp+70h] [rbp-90h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v37[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v38; // [rsp+90h] [rbp-70h]
  struct _SecHandle phContext; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v40[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v41; // [rsp+C8h] [rbp-38h]
  int v42; // [rsp+D0h] [rbp-30h]
  __int16 v43; // [rsp+D4h] [rbp-2Ch]
  _BYTE v44[32]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v46; // [rsp+108h] [rbp+8h]
  _BYTE v47[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v48; // [rsp+130h] [rbp+30h]
  unsigned int v49; // [rsp+140h] [rbp+40h]
  _BYTE v50[32]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v51; // [rsp+168h] [rbp+68h]
  int v52; // [rsp+178h] [rbp+78h]
  _BYTE v53[32]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v54; // [rsp+1A0h] [rbp+A0h]
  int v55; // [rsp+1B0h] [rbp+B0h]
  _DWORD v56[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v57; // [rsp+1C8h] [rbp+C8h]
  int v58; // [rsp+1D0h] [rbp+D0h]
  int v59; // [rsp+1D4h] [rbp+D4h]
  __int64 v60; // [rsp+1D8h] [rbp+D8h]
  int v61; // [rsp+1E0h] [rbp+E0h]
  int v62; // [rsp+1E4h] [rbp+E4h]
  __int64 v63; // [rsp+1E8h] [rbp+E8h]
  int v64; // [rsp+1F0h] [rbp+F0h]
  int v65; // [rsp+1F4h] [rbp+F4h]
  __int64 v66; // [rsp+1F8h] [rbp+F8h]
  int v67; // [rsp+200h] [rbp+100h]
  int v68; // [rsp+204h] [rbp+104h]
  __int64 v69; // [rsp+208h] [rbp+108h]
  unsigned __int16 v70[32]; // [rsp+210h] [rbp+110h] BYREF
  char v71[64]; // [rsp+250h] [rbp+150h] BYREF
  char v72[256]; // [rsp+290h] [rbp+190h] BYREF

  v43 = 256;
  v40[0] = 0;
  v41 = v40;
  v42 = 32;
  STRA::STRA((STRA *)v44, v72, 0x100u);
  STRA::STRA((STRA *)v53);
  STRA::STRA((STRA *)v50, v71, 0x40u);
  memset_0(v70, 0, sizeof(v70));
  STRU::STRU((STRU *)v47, v70, 0x20u);
  Block = 0;
  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  phContext.dwUpper = -1;
  pOutput = 0;
  phContext.dwLower = -1;
  pInput = 0;
  ReferencedCredential = SSPI_CREDENTIAL::GetReferencedCredential(v4, (struct SSPI_CREDENTIAL **)&Block, v5);
  v7 = (volatile signed __int32 *)Block;
  LODWORD(v8) = ReferencedCredential;
  if ( ReferencedCredential >= 0 )
  {
    if ( BUFFER::Resize((BUFFER *)v40, *((_DWORD *)Block + 54)) )
    {
      memset_0(v56, 0, 0x50u);
      pOutput.ulVersion = 0;
      pOutput.pBuffers = (PSecBuffer)v37;
      v37[0] = v42;
      v38 = v41;
      pInput.pBuffers = (PSecBuffer)v56;
      v9 = *(_QWORD *)a2;
      v37[1] = 2;
      v56[1] = 2;
      pOutput.cBuffers = 1;
      v10 = *(__int64 (__fastcall **)(struct IHttpContext *))(v9 + 24);
      pInput.ulVersion = 0;
      pInput.cBuffers = 5;
      v56[0] = 0;
      v57 = 0;
      v11 = v10(a2);
      v12 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 64LL))(v11);
      v13 = STRA::Copy((STRA *)v53, v12);
      LODWORD(v8) = v13;
      if ( v13 >= 0 )
      {
        v58 = v55;
        v60 = v54;
        v14 = *(_QWORD *)a2;
        v59 = 3;
        v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v14 + 24))(a2);
        v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        v17 = STRA::CopyW((STRA *)v50, *(const unsigned __int16 **)(v16 + 88));
        LODWORD(v8) = v17;
        if ( v17 >= 0 )
        {
          v61 = v52;
          v63 = v51;
          v18 = *(_QWORD *)a2;
          v62 = 3;
          v65 = 3;
          v64 = 0;
          v19 = *(__int64 (__fastcall **)(struct IHttpContext *))(v18 + 160);
          v66 = 0;
          v20 = v19(a2);
          v21 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
          v22 = (**v21)(v21, s_pModuleContext);
          v23 = STRU::Copy((STRU *)v47, (const struct STRU *)(v22 + 16));
          LODWORD(v8) = v23;
          if ( v23 >= 0 )
          {
            if ( v49 )
            {
              if ( v49 > 0x400 )
              {
                LODWORD(v8) = -2147467259;
                goto LABEL_31;
              }
              v67 = 2 * v49;
              v69 = v48;
            }
            else
            {
              v67 = 0;
              v69 = 0;
            }
            v24 = *(_QWORD *)a2;
            v68 = 3;
            v25 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(v24 + 56))(a2);
            v26 = (**v25)(v25, s_pModuleContext);
            v27 = 2052;
            if ( v26 && *(_DWORD *)(v26 + 208) )
              v27 = 2099204;
            (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 24LL))(s_pGlobalInfo);
            v8 = AcceptSecurityContext(
                   (PCredHandle)(v7 + 50),
                   0,
                   &pInput,
                   v27,
                   0x10u,
                   &phContext,
                   &pOutput,
                   &pfContextAttr,
                   &ptsExpiry);
            (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 32LL))(s_pGlobalInfo);
            v28 = *(_QWORD *)(*((_QWORD *)this + 2) + 80LL);
            if ( v28 )
              WriteRefTraceLogEx(v28, 1, phContext.dwLower, phContext.dwUpper, v8, 0);
            if ( (_DWORD)v8 == 590610 )
            {
              LODWORD(v8) = DIGEST_CONTEXT_CACHE::AddContextCacheEntry(*((DIGEST_CONTEXT_CACHE **)this + 3), &phContext);
              if ( (int)v8 >= 0 )
              {
                phContext.dwUpper = -1;
                phContext.dwLower = -1;
                LODWORD(v8) = STRA::Copy((STRA *)v44, "Digest ");
                if ( (int)v8 >= 0 )
                {
                  LODWORD(v8) = STRA::Append(
                                  (STRA *)v44,
                                  (const char *)pOutput.pBuffers->pvBuffer,
                                  pOutput.pBuffers->cbBuffer);
                  if ( (int)v8 >= 0 )
                  {
                    v29 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
                    LODWORD(v8) = (*(__int64 (__fastcall **)(__int64, const char *, __int64, _QWORD, _DWORD))(*(_QWORD *)v29 + 40LL))(
                                    v29,
                                    "WWW-Authenticate",
                                    v45,
                                    v46,
                                    0);
                  }
                }
              }
            }
          }
          else if ( (g_dwDebugFlags & 3) != 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
              747,
              "DIGEST_AUTH_PROVIDER::OnAccessDenied",
              "Error reading the realm.  hr = %x\n",
              v23);
          }
        }
        else if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
            715,
            "DIGEST_AUTH_PROVIDER::OnAccessDenied",
            "Error copying the URL.  hr = %x\n",
            v17);
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
          697,
          "DIGEST_AUTH_PROVIDER::OnAccessDenied",
          "Error getting the method.  hr = %x\n",
          v13);
      }
    }
    else
    {
      LODWORD(v8) = -2147024888;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
          641,
          "DIGEST_AUTH_PROVIDER::OnAccessDenied",
          "Error resize the output buffer. hr = 0x%x \n",
          -2147024888);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digest_auth.cxx",
      628,
      "DIGEST_AUTH_PROVIDER::OnAccessDenied",
      "Error get credential handle. hr = 0x%x \n",
      ReferencedCredential);
  }
LABEL_31:
  if ( phContext.dwLower != -1 && phContext.dwUpper != -1 )
  {
    v30 = *(_QWORD *)(*((_QWORD *)this + 2) + 80LL);
    if ( v30 )
      WriteRefTraceLogEx(v30, 0, phContext.dwLower, phContext.dwUpper, 0, 0);
    DeleteSecurityContext(&phContext);
  }
  if ( v7 && _InterlockedExchangeAdd(v7 + 1, 0xFFFFFFFF) == 1 )
  {
    *v7 = 1396917094;
    if ( *((_QWORD *)v7 + 25) != -1 && *((_QWORD *)v7 + 26) != -1 )
      FreeCredentialsHandle((PCredHandle)(v7 + 50));
    MULTISZ::~MULTISZ((MULTISZ *)(v7 + 36));
    STRA::~STRA((STRA *)(v7 + 2));
    operator delete((void *)v7);
  }
  STRU::~STRU((STRU *)v47);
  STRA::~STRA((STRA *)v50);
  STRA::~STRA((STRA *)v53);
  STRA::~STRA((STRA *)v44);
  BUFFER::~BUFFER((BUFFER *)v40);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003200  mov     [rsp-8+arg_10], rbx
0x180003205  mov     [rsp-8+arg_18], rsi
0x18000320a  push    rbp
0x18000320b  push    rdi
0x18000320c  push    r12
0x18000320e  push    r14
0x180003210  push    r15
0x180003212  lea     rbp, [rsp-2A0h]
0x18000321a  sub     rsp, 3A0h
0x180003221  mov     rax, cs:__security_cookie
0x180003228  xor     rax, rsp
0x18000322b  mov     [rbp+2C0h+var_30], rax
0x180003232  xor     r15d, r15d
0x180003235  mov     [rbp+2C0h+var_2EC], 100h
0x18000323b  mov     rsi, rdx
0x18000323e  mov     [rbp+2C0h+var_318], r15
0x180003242  mov     r14, rcx
0x180003245  lea     rax, [rbp+2C0h+var_318]
0x180003249  mov     r8d, 100h
0x18000324f  mov     [rbp+2C0h+var_2F8], rax
0x180003253  lea     edi, [r15+20h]
0x180003257  lea     rdx, [rbp+2C0h+var_130]
0x18000325e  mov     [rbp+2C0h+var_2F0], edi
0x180003261  lea     rcx, [rbp+2C0h+var_2E8]
0x180003265  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000326b  lea     rcx, [rbp+2C0h+var_240]
0x180003272  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003278  lea     ebx, [rdi+20h]
0x18000327b  mov     r8d, ebx
0x18000327e  lea     rdx, [rbp+2C0h+var_170]
0x180003285  lea     rcx, [rbp+2C0h+var_278]
0x180003289  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000328f  mov     r8d, ebx; Size
0x180003292  lea     rcx, [rbp+2C0h+var_1B0]; void *
0x180003299  xor     edx, edx; Val
0x18000329b  call    memset_0
0x1800032a0  mov     r8d, edi
0x1800032a3  lea     rdx, [rbp+2C0h+var_1B0]
0x1800032aa  lea     rcx, [rbp+2C0h+var_2B0]
0x1800032ae  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800032b4  xorps   xmm0, xmm0
0x1800032b7  mov     [rsp+3C0h+Block], r15
0x1800032bc  xorps   xmm1, xmm1
0x1800032bf  mov     [rsp+3C0h+var_370], r15d
0x1800032c4  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800032c8  mov     qword ptr [rbp+2C0h+var_340], r15
0x1800032cc  lea     rdx, [rsp+3C0h+Block]; struct SSPI_CREDENTIAL **
0x1800032d1  mov     [rbp+2C0h+phContext.dwUpper], r12
0x1800032d5  movups  xmmword ptr [rsp+3C0h+var_360.ulVersion], xmm0
0x1800032da  mov     [rbp+2C0h+phContext.dwLower], r12
0x1800032de  movups  xmmword ptr [rsp+3C0h+pInput.ulVersion], xmm1
0x1800032e3  call    ?GetReferencedCredential@SSPI_CREDENTIAL@@SAJPEBDPEAPEAV1@PEAVMULTISZ@@@Z; SSPI_CREDENTIAL::GetReferencedCredential(char const *,SSPI_CREDENTIAL * *,MULTISZ *)
0x1800032e8  mov     rdi, [rsp+3C0h+Block]
0x1800032ed  mov     ebx, eax
0x1800032ef  test    eax, eax
0x1800032f1  jns     short loc_180003336
0x1800032f3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800032fa  jz      loc_180003708
0x180003300  mov     dword ptr [rsp+3C0h+phNewContext], eax
0x180003304  mov     r8d, 274h
0x18000330a  lea     rax, aErrorGetCreden; "Error get credential handle. hr = 0x%x "...
0x180003311  mov     rcx, cs:g_pDebug
0x180003318  lea     r9, aDigestAuthProv; "DIGEST_AUTH_PROVIDER::OnAccessDenied"
0x18000331f  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003326  mov     qword ptr [rsp+3C0h+TargetDataRep], rax
0x18000332b  call    cs:__imp_PuDbgPrint
0x180003331  jmp     loc_180003708
0x180003336  mov     edx, [rdi+0D8h]
0x18000333c  lea     rcx, [rbp+2C0h+var_318]
0x180003340  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003346  test    al, al
0x180003348  jnz     short loc_18000336F
0x18000334a  test    byte ptr cs:g_dwDebugFlags, 3
0x180003351  mov     ebx, 80070008h
0x180003356  jz      loc_180003708
0x18000335c  mov     dword ptr [rsp+3C0h+phNewContext], ebx
0x180003360  lea     rax, aErrorResizeThe; "Error resize the output buffer. hr = 0x"...
0x180003367  mov     r8d, 281h
0x18000336d  jmp     short loc_180003311
0x18000336f  xor     edx, edx; Val
0x180003371  lea     rcx, [rbp+2C0h+var_200]; void *
0x180003378  lea     r8d, [rdx+50h]; Size
0x18000337c  call    memset_0
0x180003381  lea     rax, [rbp+2C0h+var_338]
0x180003385  mov     [rsp+3C0h+var_360.ulVersion], r15d
0x18000338a  mov     [rsp+3C0h+var_360.pBuffers], rax
0x18000338f  mov     ecx, 2
0x180003394  mov     eax, [rbp+2C0h+var_2F0]
0x180003397  mov     [rbp+2C0h+var_338], eax
0x18000339a  mov     rax, [rbp+2C0h+var_2F8]
0x18000339e  mov     [rbp+2C0h+var_330], rax
0x1800033a2  lea     rax, [rbp+2C0h+var_200]
0x1800033a9  mov     [rsp+3C0h+pInput.pBuffers], rax
0x1800033ae  mov     rax, [rsi]
0x1800033b1  mov     [rbp+2C0h+var_334], ecx
0x1800033b4  mov     [rbp+2C0h+var_1FC], ecx
0x1800033ba  mov     rcx, rsi
0x1800033bd  mov     [rsp+3C0h+var_360.cBuffers], 1
0x1800033c5  mov     rax, [rax+18h]
0x1800033c9  mov     [rsp+3C0h+pInput.ulVersion], r15d
0x1800033ce  mov     [rsp+3C0h+pInput.cBuffers], 5
0x1800033d6  mov     [rbp+2C0h+var_200], r15d
0x1800033dd  mov     [rbp+2C0h+var_1F8], r15
0x1800033e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e9  mov     rdx, rax
0x1800033ec  mov     rcx, [rax]
0x1800033ef  mov     rax, [rcx+40h]
0x1800033f3  mov     rcx, rdx
0x1800033f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033fb  mov     rdx, rax
0x1800033fe  lea     rcx, [rbp+2C0h+var_240]
0x180003405  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000340b  mov     ebx, eax
0x18000340d  test    eax, eax
0x18000340f  jns     short loc_180003434
0x180003411  test    byte ptr cs:g_dwDebugFlags, 3
0x180003418  jz      loc_180003708
0x18000341e  mov     dword ptr [rsp+3C0h+phNewContext], eax
0x180003422  mov     r8d, 2B9h
0x180003428  lea     rax, aErrorGettingTh; "Error getting the method.  hr = %x\n"
0x18000342f  jmp     loc_180003311
0x180003434  mov     eax, [rbp+2C0h+var_210]
0x18000343a  mov     rcx, rsi
0x18000343d  mov     [rbp+2C0h+var_1F0], eax
0x180003443  mov     rax, [rbp+2C0h+var_220]
0x18000344a  mov     [rbp+2C0h+var_1E8], rax
0x180003451  mov     rax, [rsi]
0x180003454  mov     [rbp+2C0h+var_1EC], 3
0x18000345e  mov     rax, [rax+18h]
0x180003462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003467  mov     rdx, rax
0x18000346a  mov     rcx, [rax]
0x18000346d  mov     rax, [rcx+8]
0x180003471  mov     rcx, rdx
0x180003474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003479  lea     rcx, [rbp+2C0h+var_278]
0x18000347d  mov     rdx, [rax+58h]
0x180003481  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180003487  mov     ebx, eax
0x180003489  test    eax, eax
0x18000348b  jns     short loc_1800034B0
0x18000348d  test    byte ptr cs:g_dwDebugFlags, 3
0x180003494  jz      loc_180003708
0x18000349a  mov     dword ptr [rsp+3C0h+phNewContext], eax
0x18000349e  mov     r8d, 2CBh
0x1800034a4  lea     rax, aErrorCopyingTh; "Error copying the URL.  hr = %x\n"
0x1800034ab  jmp     loc_180003311
0x1800034b0  mov     eax, [rbp+2C0h+var_248]
0x1800034b3  mov     rcx, rsi
0x1800034b6  mov     [rbp+2C0h+var_1E0], eax
0x1800034bc  mov     rax, [rbp+2C0h+var_258]
0x1800034c0  mov     [rbp+2C0h+var_1D8], rax
0x1800034c7  mov     rax, [rsi]
0x1800034ca  mov     [rbp+2C0h+var_1DC], 3
0x1800034d4  mov     [rbp+2C0h+var_1CC], 3
0x1800034de  mov     [rbp+2C0h+var_1D0], r15d
0x1800034e5  mov     rax, [rax+0A0h]
0x1800034ec  mov     [rbp+2C0h+var_1C8], r15
0x1800034f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f8  mov     rdx, rax
0x1800034fb  mov     rcx, [rax]
0x1800034fe  mov     rax, [rcx+18h]
0x180003502  mov     rcx, rdx
0x180003505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350a  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180003511  mov     r8, rax
0x180003514  mov     rcx, [rax]
0x180003517  mov     rax, [rcx]
0x18000351a  mov     rcx, r8
0x18000351d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003522  lea     rcx, [rbp+2C0h+var_2B0]
0x180003526  lea     rdx, [rax+10h]
0x18000352a  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180003530  mov     ebx, eax
0x180003532  test    eax, eax
0x180003534  jns     short loc_180003559
0x180003536  test    byte ptr cs:g_dwDebugFlags, 3
0x18000353d  jz      loc_180003708
0x180003543  mov     dword ptr [rsp+3C0h+phNewContext], eax
0x180003547  mov     r8d, 2EBh
0x18000354d  lea     rax, aErrorReadingTh; "Error reading the realm.  hr = %x\n"
0x180003554  jmp     loc_180003311
0x180003559  mov     eax, [rbp+2C0h+var_280]
0x18000355c  test    eax, eax
0x18000355e  jz      short loc_180003586
0x180003560  cmp     eax, 400h
0x180003565  jbe     short loc_180003571
0x180003567  mov     ebx, 80004005h
0x18000356c  jmp     loc_180003708
0x180003571  add     eax, eax
0x180003573  mov     [rbp+2C0h+var_1C0], eax
0x180003579  mov     rax, [rbp+2C0h+var_290]
0x18000357d  mov     [rbp+2C0h+var_1B8], rax
0x180003584  jmp     short loc_180003594
0x180003586  mov     [rbp+2C0h+var_1C0], r15d
0x18000358d  mov     [rbp+2C0h+var_1B8], r15
0x180003594  mov     rax, [rsi]
0x180003597  mov     rcx, rsi
0x18000359a  mov     [rbp+2C0h+var_1BC], 3
0x1800035a4  mov     rax, [rax+38h]
0x1800035a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ad  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x1800035b4  mov     r8, rax
0x1800035b7  mov     rcx, [rax]
0x1800035ba  mov     rax, [rcx]
0x1800035bd  mov     rcx, r8
0x1800035c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c5  mov     ebx, 804h
0x1800035ca  test    rax, rax
0x1800035cd  jz      short loc_1800035DE
0x1800035cf  cmp     [rax+0D0h], r15d
0x1800035d6  mov     ecx, 200804h
0x1800035db  cmovnz  ebx, ecx
0x1800035de  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800035e5  mov     rax, [rcx]
0x1800035e8  mov     rax, [rax+18h]
0x1800035ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f1  lea     rax, [rbp+2C0h+var_340]
0x1800035f5  mov     r9d, ebx; fContextReq
0x1800035f8  mov     [rsp+3C0h+ptsExpiry], rax; ptsExpiry
0x1800035fd  lea     rcx, [rdi+0C8h]; phCredential
0x180003604  lea     rax, [rsp+3C0h+var_370]
0x180003609  xor     edx, edx; phContext
0x18000360b  mov     [rsp+3C0h+pfContextAttr], rax; pfContextAttr
0x180003610  lea     r8, [rsp+3C0h+pInput]; pInput
0x180003615  lea     rax, [rsp+3C0h+var_360]
0x18000361a  mov     [rsp+3C0h+pOutput], rax; pOutput
0x18000361f  lea     rax, [rbp+2C0h+phContext]
0x180003623  mov     [rsp+3C0h+phNewContext], rax; phNewContext
0x180003628  mov     [rsp+3C0h+TargetDataRep], 10h; TargetDataRep
0x180003630  call    cs:__imp_AcceptSecurityContext
0x180003636  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000363d  movsxd  rbx, eax
0x180003640  mov     rax, [rcx]
0x180003643  mov     rax, [rax+20h]
0x180003647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364c  mov     rax, [r14+10h]
0x180003650  mov     rcx, [rax+50h]
0x180003654  test    rcx, rcx
0x180003657  jz      short loc_180003676
0x180003659  mov     r9, [rbp+2C0h+phContext.dwUpper]
0x18000365d  mov     edx, 1
0x180003662  mov     r8, [rbp+2C0h+phContext.dwLower]
0x180003666  mov     [rsp+3C0h+phNewContext], r15
0x18000366b  mov     qword ptr [rsp+3C0h+TargetDataRep], rbx
0x180003670  call    cs:__imp_WriteRefTraceLogEx
0x180003676  cmp     ebx, 90312h
0x18000367c  jnz     loc_180003708
0x180003682  mov     rcx, [r14+18h]; this
0x180003686  lea     rdx, [rbp+2C0h+phContext]; struct _SecHandle *
0x18000368a  call    ?AddContextCacheEntry@DIGEST_CONTEXT_CACHE@@QEAAJPEAU_SecHandle@@@Z; DIGEST_CONTEXT_CACHE::AddContextCacheEntry(_SecHandle *)
0x18000368f  mov     ebx, eax
0x180003691  test    eax, eax
0x180003693  js      short loc_180003708
0x180003695  lea     rdx, aDigest_1; "Digest "
0x18000369c  mov     [rbp+2C0h+phContext.dwUpper], r12
0x1800036a0  lea     rcx, [rbp+2C0h+var_2E8]
0x1800036a4  mov     [rbp+2C0h+phContext.dwLower], r12
0x1800036a8  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800036ae  mov     ebx, eax
0x1800036b0  test    eax, eax
0x1800036b2  js      short loc_180003708
0x1800036b4  mov     rdx, [rsp+3C0h+var_360.pBuffers]
0x1800036b9  lea     rcx, [rbp+2C0h+var_2E8]
0x1800036bd  mov     r8d, [rdx]
0x1800036c0  mov     rdx, [rdx+8]
0x1800036c4  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x1800036ca  mov     ebx, eax
0x1800036cc  test    eax, eax
0x1800036ce  js      short loc_180003708
0x1800036d0  mov     rax, [rsi]
0x1800036d3  mov     rcx, rsi
0x1800036d6  mov     rax, [rax+20h]
0x1800036da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036df  movzx   r9d, [rbp+2C0h+var_2B8]
0x1800036e4  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x1800036eb  mov     r8, [rbp+2C0h+var_2C8]
0x1800036ef  mov     r10, rax
0x1800036f2  mov     [rsp+3C0h+TargetDataRep], r15d
0x1800036f7  mov     rcx, [rax]
0x1800036fa  mov     rax, [rcx+28h]
0x1800036fe  mov     rcx, r10
0x180003701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003706  mov     ebx, eax
0x180003708  mov     r8, [rbp+2C0h+phContext.dwLower]
0x18000370c  cmp     r8, r12
0x18000370f  jz      short loc_180003743
0x180003711  mov     r9, [rbp+2C0h+phContext.dwUpper]
0x180003715  cmp     r9, r12
0x180003718  jz      short loc_180003743
0x18000371a  mov     rax, [r14+10h]
0x18000371e  mov     rcx, [rax+50h]
0x180003722  test    rcx, rcx
0x180003725  jz      short loc_180003739
0x180003727  mov     [rsp+3C0h+phNewContext], r15
0x18000372c  xor     edx, edx
0x18000372e  mov     qword ptr [rsp+3C0h+TargetDataRep], r15
0x180003733  call    cs:__imp_WriteRefTraceLogEx
0x180003739  lea     rcx, [rbp+2C0h+phContext]; phContext
0x18000373d  call    cs:__imp_DeleteSecurityContext
  ... truncated ...
```
