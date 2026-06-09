# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x18003bc44`
- end: `0x18003bfef`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `939`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003baf4`

## callees

- `0x18003bc44`
- `0x18003bff8`
- `0x18003c030`
- `0x18003c1e8`
- `0x18003c240`
- `0x18009c344`
- `0x1800aa594`
- `0x1800f3a5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003be3d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003bef9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003be3d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003bef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003bc78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003bc78`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003bc93`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003bc93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bde8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003be21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bfc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bd93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bde8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003be21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bfc2`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v5; // r9
  __int64 v6; // rcx
  void *v7; // rdx
  signed int LastError; // ebx
  _QWORD *v9; // r14
  unsigned __int16 *v10; // rdi
  __int64 v11; // rax
  int v12; // r15d
  _WORD *v13; // rbx
  __int64 v14; // rdx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // eax
  unsigned __int16 *v20; // rsi
  __int64 v21; // rax
  int v22; // r15d
  _WORD *v23; // rbx
  char *v24; // rsi
  void *v25; // rdx
  const wchar_t *v26; // rcx
  wchar_t *v27; // rax
  _BYTE *v28; // r12
  __int64 v29; // rax
  __int64 v30; // rsi
  int v31; // edi
  __int64 v32; // rax
  unsigned int v33; // edi
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rbx
  const wchar_t *v37; // rcx
  wchar_t *v38; // rax
  unsigned int v39; // r8d
  _BYTE *v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r12
  unsigned __int64 v43; // rdx
  size_t v44; // rbx
  _BYTE *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rbx
  char *v50; // rdi
  bool *v51; // [rsp+20h] [rbp-20h]
  unsigned int v52; // [rsp+20h] [rbp-20h]
  PVOID P[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  void *TokenHandle; // [rsp+80h] [rbp+40h] BYREF
  __int64 v56; // [rsp+88h] [rbp+48h]
  _BYTE *v57; // [rsp+90h] [rbp+50h]

  *a2 = 0;
  *(_OWORD *)P = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    v6 = -4;
    TokenHandle = (void *)-4LL;
  }
  else
  {
    if ( !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_6;
    }
    v6 = (__int64)TokenHandle;
  }
  LastError = ARI::ProcessToken::SysAppId::Open(
                (HANDLE)v6,
                P,
                (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **)&P[1],
                v5,
                v51);
  if ( TokenHandle != (void *)-4LL )
    CloseHandle(TokenHandle);
LABEL_6:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023728 || LastError == -2147024891 )
    goto LABEL_9;
  if ( LastError < 0 )
  {
    v14 = 165;
    goto LABEL_16;
  }
  v9 = P[1];
  v10 = (unsigned __int16 *)*((_QWORD *)P[1] + 4);
  v11 = v10[8] >> 1;
  v12 = v11 + 1;
  if ( (_DWORD)v11 == -1 )
  {
    v13 = (_WORD *)(2 * v11);
    memcpy_0(0, *((const void **)v10 + 3), 2 * v11);
    *v13 = 0;
LABEL_15:
    LastError = -2147418113;
    v14 = 168;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)LastError,
      (int)v51);
LABEL_17:
    ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)P);
    return (unsigned int)LastError;
  }
  v26 = (const wchar_t *)*((_QWORD *)v10 + 1);
  LODWORD(TokenHandle) = *v10 >> 1;
  v27 = wcschr(v26, 0x5Fu);
  v28 = (_BYTE *)*((_QWORD *)v10 + 1);
  v29 = ((char *)(v27 + 1) - v28) >> 1;
  v30 = (unsigned int)(v29 + 13);
  v31 = v29 + 14;
  if ( (_DWORD)v29 == -14 )
  {
    memcpy_0(0, v28, 0x1FFFFFFE4uLL);
    v32 = (unsigned int)((_DWORD)TokenHandle - 13);
    MEMORY[0x1FFFFFFE4] = *(_OWORD *)&v28[2 * v32];
    MEMORY[0x1FFFFFFEE] = *(_OWORD *)&v28[2 * v32 + 10];
    *(_WORD *)(2 * v30) = 0;
    v33 = v12 + v31;
    if ( !v33 )
    {
      *(_WORD *)(2 * v30) = 33;
      v34 = v9[4];
      v35 = *(unsigned __int16 *)(v34 + 16) >> 1;
      if ( ~(_DWORD)v30 >= (unsigned int)(v35 + 1) )
      {
        v36 = 2 * v35;
        memcpy_0((void *)(2LL * (unsigned int)v30 + 2), *(const void **)(v34 + 24), 2 * v35);
        *(_WORD *)(2LL * (unsigned int)v30 + 2 + v36) = 0;
      }
      goto LABEL_15;
    }
  }
  else
  {
    v33 = v12 + v31;
  }
  TokenHandle = 0;
  CoTaskMemFree(0);
  v19 = _AllocStringWorker<CTCoAllocPolicy>(v17, v16, v18, v33, (__int64)v51, (unsigned __int16 **)&TokenHandle);
  LastError = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)v19,
      v52);
    CoTaskMemFree(TokenHandle);
LABEL_9:
    if ( P[0] )
      ARI::Free(P[0], v7);
    return (unsigned int)LastError;
  }
  v20 = (unsigned __int16 *)v9[4];
  v21 = v20[8] >> 1;
  v22 = v21 + 1;
  if ( (_DWORD)v21 == -1 )
  {
    v23 = (_WORD *)(2 * v21);
    memcpy_0(0, *((const void **)v20 + 3), 2 * v21);
    v24 = (char *)TokenHandle;
    *v23 = 0;
  }
  else
  {
    v37 = (const wchar_t *)*((_QWORD *)v20 + 1);
    LODWORD(v56) = *v20 >> 1;
    v38 = wcschr(v37, 0x5Fu);
    v40 = (_BYTE *)*((_QWORD *)v20 + 1);
    v24 = (char *)TokenHandle;
    v41 = ((char *)(v38 + 1) - v40) >> 1;
    v57 = v40;
    v42 = (unsigned int)(v41 + 13);
    v43 = (unsigned int)(v41 + 14);
    if ( v33 < (unsigned int)v43
      || (v44 = 2LL * (unsigned int)v41,
          memcpy_0(TokenHandle, v40, v44),
          v45 = v57,
          v46 = (unsigned int)(v56 - 13),
          *(_OWORD *)&v24[v44] = *(_OWORD *)&v57[2 * v46],
          *(_OWORD *)&v24[v44 + 10] = *(_OWORD *)&v45[2 * v46 + 10],
          *(_WORD *)&v24[2 * v42] = 0,
          v33 < (int)v42 + v22 + 1) )
    {
      LastError = wil::details::in1diag3::Return_Win32(retaddr, (void *)v43, v39, (const char *)0x7A, v52);
      CoTaskMemFree(v24);
      goto LABEL_17;
    }
    *(_WORD *)&v24[2 * v42] = 33;
    v47 = v9[4];
    v48 = *(unsigned __int16 *)(v47 + 16) >> 1;
    if ( v33 - (unsigned int)v42 - 1 >= (int)v48 + 1 )
    {
      v49 = 2 * v48;
      v50 = &v24[2 * v42];
      memcpy_0(v50 + 2, *(const void **)(v47 + 24), 2 * v48);
      *(_WORD *)&v50[v49 + 2] = 0;
    }
  }
  *a2 = v24;
  CoTaskMemFree(0);
  if ( P[0] )
    ARI::Free(P[0], v25);
  return 0;
}

```

## disassembly

```asm
0x18003bc44  mov     [rsp-38h+arg_18], rbx
0x18003bc49  push    rbp
0x18003bc4a  push    rsi
0x18003bc4b  push    rdi
0x18003bc4c  push    r12
0x18003bc4e  push    r13
0x18003bc50  push    r14
0x18003bc52  push    r15
0x18003bc54  mov     rbp, rsp
0x18003bc57  sub     rsp, 40h
0x18003bc5b  xorps   xmm0, xmm0
0x18003bc5e  mov     qword ptr [rdx], 0
0x18003bc65  movdqu  xmmword ptr [rbp+P], xmm0
0x18003bc6a  mov     r13, rdx
0x18003bc6d  mov     [rbp+TokenHandle], 0
0x18003bc75  mov     rbx, rcx
0x18003bc78  call    cs:__imp_GetCurrentProcess
0x18003bc7e  cmp     rbx, rax
0x18003bc81  jz      loc_18003BFCD
0x18003bc87  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003bc8b  mov     edx, 8; DesiredAccess
0x18003bc90  mov     rcx, rbx; ProcessHandle
0x18003bc93  call    cs:__imp_OpenProcessToken
0x18003bc99  test    eax, eax
0x18003bc9b  jz      loc_18003BD74
0x18003bca1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003bca5  lea     r8, [rbp+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x18003bca9  lea     rdx, [rbp+P]; void *
0x18003bcad  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x18003bcb2  mov     rcx, [rbp+TokenHandle]; hObject
0x18003bcb6  mov     ebx, eax
0x18003bcb8  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x18003bcbc  jnz     loc_18003BD69
0x18003bcc2  test    ebx, ebx
0x18003bcc4  jle     short loc_18003BCCF
0x18003bcc6  movzx   ebx, bx
0x18003bcc9  or      ebx, 80070000h
0x18003bccf  cmp     ebx, 80070490h
0x18003bcd5  jnz     short loc_18003BCE7
0x18003bcd7  mov     rcx, [rbp+P]; P
0x18003bcdb  test    rcx, rcx
0x18003bcde  jz      short loc_18003BD4F
0x18003bce0  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18003bce5  jmp     short loc_18003BD4F
0x18003bce7  cmp     ebx, 80070005h
0x18003bced  jz      short loc_18003BCD7
0x18003bcef  test    ebx, ebx
0x18003bcf1  js      loc_18003BFDD
0x18003bcf7  mov     r14, [rbp+P+8]
0x18003bcfb  mov     rdi, [r14+20h]
0x18003bcff  movzx   eax, word ptr [rdi+10h]
0x18003bd03  shr     eax, 1
0x18003bd05  lea     r15d, [rax+1]
0x18003bd09  test    r15d, r15d
0x18003bd0c  jnz     loc_18003BE2C
0x18003bd12  mov     rdx, [rdi+18h]; Src
0x18003bd16  lea     rbx, [rax+rax]
0x18003bd1a  mov     r8, rbx; Size
0x18003bd1d  xor     ecx, ecx; void *
0x18003bd1f  call    memcpy_0
0x18003bd24  xor     eax, eax
0x18003bd26  mov     [rbx], ax
0x18003bd29  mov     ebx, 8000FFFFh
0x18003bd2e  mov     edx, 0A8h; void *
0x18003bd33  mov     rcx, [rbp+38h]; this
0x18003bd37  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18003bd3e  mov     r9d, ebx; char *
0x18003bd41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd46  lea     rcx, [rbp+P]; this
0x18003bd4a  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x18003bd4f  mov     eax, ebx
0x18003bd51  mov     rbx, [rsp+40h+arg_18]
0x18003bd59  add     rsp, 40h
0x18003bd5d  pop     r15
0x18003bd5f  pop     r14
0x18003bd61  pop     r13
0x18003bd63  pop     r12
0x18003bd65  pop     rdi
0x18003bd66  pop     rsi
0x18003bd67  pop     rbp
0x18003bd68  retn
0x18003bd69  call    cs:__imp_CloseHandle
0x18003bd6f  jmp     loc_18003BCC2
0x18003bd74  call    cs:__imp_GetLastError
0x18003bd7a  mov     ebx, eax
0x18003bd7c  test    eax, eax
0x18003bd7e  jz      loc_18003BCA1
0x18003bd84  jmp     loc_18003BCC2
0x18003bd89  xor     ecx, ecx; pv
0x18003bd8b  mov     [rbp+TokenHandle], 0
0x18003bd93  call    cs:__imp_CoTaskMemFree
0x18003bd99  lea     rax, [rbp+TokenHandle]
0x18003bd9d  mov     r9d, edi
0x18003bda0  mov     [rsp+40h+var_18], rax
0x18003bda5  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18003bdaa  mov     ebx, eax
0x18003bdac  test    eax, eax
0x18003bdae  js      short loc_18003BE05
0x18003bdb0  mov     rsi, [r14+20h]
0x18003bdb4  movzx   eax, word ptr [rsi+10h]
0x18003bdb8  shr     eax, 1
0x18003bdba  lea     r15d, [rax+1]
0x18003bdbe  test    r15d, r15d
0x18003bdc1  jnz     loc_18003BEE8
0x18003bdc7  mov     rdx, [rsi+18h]; Src
0x18003bdcb  lea     rbx, [rax+rax]
0x18003bdcf  mov     r8, rbx; Size
0x18003bdd2  xor     ecx, ecx; void *
0x18003bdd4  call    memcpy_0
0x18003bdd9  mov     rsi, [rbp+TokenHandle]
0x18003bddd  xor     eax, eax
0x18003bddf  mov     [rbx], ax
0x18003bde2  xor     ecx, ecx; pv
0x18003bde4  mov     [r13+0], rsi
0x18003bde8  call    cs:__imp_CoTaskMemFree
0x18003bdee  mov     rcx, [rbp+P]; P
0x18003bdf2  test    rcx, rcx
0x18003bdf5  jnz     short loc_18003BDFE
0x18003bdf7  xor     eax, eax
0x18003bdf9  jmp     loc_18003BD51
0x18003bdfe  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18003be03  jmp     short loc_18003BDF7
0x18003be05  mov     rcx, [rbp+38h]; this
0x18003be09  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18003be10  mov     r9d, ebx; char *
0x18003be13  mov     edx, 0ABh; void *
0x18003be18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003be1d  mov     rcx, [rbp+TokenHandle]; pv
0x18003be21  call    cs:__imp_CoTaskMemFree
0x18003be27  jmp     loc_18003BCD7
0x18003be2c  movzx   eax, word ptr [rdi]
0x18003be2f  mov     edx, 5Fh ; '_'; Ch
0x18003be34  mov     rcx, [rdi+8]; Str
0x18003be38  shr     eax, 1
0x18003be3a  mov     dword ptr [rbp+TokenHandle], eax
0x18003be3d  call    cs:__imp_wcschr
0x18003be43  mov     r12, [rdi+8]
0x18003be47  add     rax, 2
0x18003be4b  sub     rax, r12
0x18003be4e  sar     rax, 1
0x18003be51  lea     esi, [rax+0Dh]
0x18003be54  lea     edi, [rsi+1]
0x18003be57  test    edi, edi
0x18003be59  jnz     loc_18003BFE7
0x18003be5f  mov     eax, eax
0x18003be61  mov     rdx, r12; Src
0x18003be64  xor     ecx, ecx; void *
0x18003be66  lea     rbx, [rax+rax]
0x18003be6a  mov     r8, rbx; Size
0x18003be6d  call    memcpy_0
0x18003be72  mov     rax, [rbp+TokenHandle]
0x18003be76  add     eax, 0FFFFFFF3h
0x18003be79  mov     r8d, esi
0x18003be7c  movups  xmm0, xmmword ptr [r12+rax*2]
0x18003be81  movups  xmmword ptr [rbx], xmm0
0x18003be84  movups  xmm1, xmmword ptr [r12+rax*2+0Ah]
0x18003be8a  xor     eax, eax
0x18003be8c  movups  xmmword ptr [rbx+0Ah], xmm1
0x18003be90  mov     ds:0[rsi*2], ax
0x18003be98  add     edi, r15d
0x18003be9b  jnz     loc_18003BD89
0x18003bea1  mov     word ptr ds:0[rsi*2], 21h ; '!'
0x18003beab  not     esi
0x18003bead  mov     rdx, [r14+20h]
0x18003beb1  movzx   ecx, word ptr [rdx+10h]
0x18003beb5  shr     ecx, 1
0x18003beb7  lea     eax, [rcx+1]
0x18003beba  cmp     esi, eax
0x18003bebc  jb      loc_18003BD29
0x18003bec2  mov     rdx, [rdx+18h]; Src
0x18003bec6  lea     rdi, ds:2[r8*2]
0x18003bece  lea     rbx, [rcx+rcx]
0x18003bed2  mov     rcx, rdi; void *
0x18003bed5  mov     r8, rbx; Size
0x18003bed8  call    memcpy_0
0x18003bedd  xor     eax, eax
0x18003bedf  mov     [rdi+rbx], ax
0x18003bee3  jmp     loc_18003BD29
0x18003bee8  movzx   eax, word ptr [rsi]
0x18003beeb  mov     edx, 5Fh ; '_'; Ch
0x18003bef0  mov     rcx, [rsi+8]; Str
0x18003bef4  shr     eax, 1
0x18003bef6  mov     dword ptr [rbp+arg_8], eax
0x18003bef9  call    cs:__imp_wcschr
0x18003beff  mov     rcx, [rsi+8]
0x18003bf03  add     rax, 2
0x18003bf07  mov     rsi, [rbp+TokenHandle]
0x18003bf0b  sub     rax, rcx
0x18003bf0e  sar     rax, 1
0x18003bf11  mov     [rbp+arg_10], rcx
0x18003bf15  lea     r12d, [rax+0Dh]
0x18003bf19  lea     edx, [r12+1]; void *
0x18003bf1e  cmp     edi, edx
0x18003bf20  jb      loc_18003BFAE
0x18003bf26  mov     eax, eax
0x18003bf28  mov     rdx, rcx; Src
0x18003bf2b  mov     rcx, rsi; void *
0x18003bf2e  lea     rbx, [rax+rax]
0x18003bf32  mov     r8, rbx; Size
0x18003bf35  call    memcpy_0
0x18003bf3a  mov     rcx, [rbp+arg_8]
0x18003bf3e  mov     rax, [rbp+arg_10]
0x18003bf42  add     ecx, 0FFFFFFF3h
0x18003bf45  movups  xmm0, xmmword ptr [rax+rcx*2]
0x18003bf49  movups  xmmword ptr [rsi+rbx], xmm0
0x18003bf4d  movups  xmm1, xmmword ptr [rax+rcx*2+0Ah]
0x18003bf52  xor     eax, eax
0x18003bf54  movups  xmmword ptr [rsi+rbx+0Ah], xmm1
0x18003bf59  mov     [rsi+r12*2], ax
0x18003bf5e  lea     eax, [r15+1]
0x18003bf62  add     eax, r12d
0x18003bf65  cmp     edi, eax
0x18003bf67  jb      short loc_18003BFAE
0x18003bf69  mov     word ptr [rsi+r12*2], 21h ; '!'
0x18003bf70  sub     edi, r12d
0x18003bf73  mov     rdx, [r14+20h]
0x18003bf77  dec     edi
0x18003bf79  movzx   ecx, word ptr [rdx+10h]
0x18003bf7d  shr     ecx, 1
0x18003bf7f  lea     eax, [rcx+1]
0x18003bf82  cmp     edi, eax
0x18003bf84  jb      loc_18003BDE2
0x18003bf8a  mov     rdx, [rdx+18h]; Src
0x18003bf8e  lea     rbx, [rcx+rcx]
0x18003bf92  lea     rdi, [rsi+r12*2]
0x18003bf96  mov     r8, rbx; Size
0x18003bf99  lea     rcx, [rdi+2]; void *
0x18003bf9d  call    memcpy_0
0x18003bfa2  xor     eax, eax
0x18003bfa4  mov     [rdi+rbx+2], ax
0x18003bfa9  jmp     loc_18003BDE2
0x18003bfae  mov     rcx, [rbp+38h]; this
0x18003bfb2  mov     r9d, 7Ah ; 'z'; char *
0x18003bfb8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003bfbd  mov     rcx, rsi; pv
0x18003bfc0  mov     ebx, eax
0x18003bfc2  call    cs:__imp_CoTaskMemFree
0x18003bfc8  jmp     loc_18003BD46
0x18003bfcd  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x18003bfd4  mov     [rbp+TokenHandle], rcx
0x18003bfd8  jmp     loc_18003BCA5
0x18003bfdd  mov     edx, 0A5h
0x18003bfe2  jmp     loc_18003BD33
0x18003bfe7  add     edi, r15d
0x18003bfea  jmp     loc_18003BD89
```
